# ASRS
A copy of ASRS Database Online for easier access & analysis.

## Dataset
The dataset are parquet files partitioned by a `Year` column.

You can use Pandas to read the dataset in Python (`pyarrow` or `fastparquet` needs to be installed first):
```
import pandas as pd

ASRS_df = pd.read_parquet("path/to/ASRS.parquet.zip")
```

## Schema
In this dataset, the columns names are in the format of table names plus the original field names, separated by double underscores, e.g., `TableName__FieldName`. Two changes are introduced to the orignal column names:
- Spaces are replaced with `_`.
- `/` are replaced with `_And_`.

To keep the data to its original format as much as possible, all columns are parsed and read as `str`. Besides the orignal columns, a `Year` column of the `int` type is added for conveniences of filtering and partition. Below are a complete list of available columns.

```
# Dataframe columns & dtypes for ASRS Database Online

dtypes = {
    '__ACN': str,
    'Time__Date': str,
    'Time__Local_Time_Of_Day': str,
    'Place__Locale_Reference': str,
    'Place__State_Reference': str,
    'Place__Relative_Position.Angle.Radial': str,
    'Place__Relative_Position.Distance.Nautical_Miles': str,
    'Place__Altitude.AGL.Single_Value': str,
    'Place__Altitude.MSL.Single_Value': str,
    'Environment__Flight_Conditions': str,
    'Environment__Weather_Elements_And_Visibility': str,
    'Environment__Work_Environment_Factor': str,
    'Environment__Light': str,
    'Environment__Ceiling': str,
    'Environment__RVR.Single_Value': str,
    'Aircraft_1__ATC_And_Advisory': str,
    'Aircraft_1__Aircraft_Operator': str,
    'Aircraft_1__Make_Model_Name': str,
    'Aircraft_1__Aircraft_Zone': str,
    'Aircraft_1__Crew_Size': str,
    'Aircraft_1__Operating_Under_FAR_Part': str,
    'Aircraft_1__Flight_Plan': str,
    'Aircraft_1__Mission': str,
    'Aircraft_1__Nav_In_Use': str,
    'Aircraft_1__Flight_Phase': str,
    'Aircraft_1__Route_In_Use': str,
    'Aircraft_1__Airspace': str,
    'Aircraft_1__Maintenance_Status.Maintenance_Deferred': str,
    'Aircraft_1__Maintenance_Status.Records_Complete': str,
    'Aircraft_1__Maintenance_Status.Released_For_Service': str,
    'Aircraft_1__Maintenance_Status.Required_And_Correct_Doc_On_Board': str,
    'Aircraft_1__Maintenance_Status.Maintenance_Type': str,
    'Aircraft_1__Maintenance_Status.Maintenance_Items_Involved': str,
    'Aircraft_1__Cabin_Lighting': str,
    'Aircraft_1__Number_Of_Seats.Number': str,
    'Aircraft_1__Passengers_On_Board.Number': str,
    'Aircraft_1__Crew_Size_Flight_Attendant.Number_Of_Crew': str,
    'Component__Aircraft_Component': str,
    'Component__Manufacturer': str,
    'Component__Aircraft_Reference': str,
    'Component__Problem': str,
    'Aircraft_2__ATC_And_Advisory': str,
    'Aircraft_2__Aircraft_Operator': str,
    'Aircraft_2__Make_Model_Name': str,
    'Aircraft_2__Aircraft_Zone': str,
    'Aircraft_2__Crew_Size': str,
    'Aircraft_2__Operating_Under_FAR_Part': str,
    'Aircraft_2__Flight_Plan': str,
    'Aircraft_2__Mission': str,
    'Aircraft_2__Nav_In_Use': str,
    'Aircraft_2__Flight_Phase': str,
    'Aircraft_2__Route_In_Use': str,
    'Aircraft_2__Airspace': str,
    'Aircraft_2__Maintenance_Status.Maintenance_Deferred': str,
    'Aircraft_2__Maintenance_Status.Records_Complete': str,
    'Aircraft_2__Maintenance_Status.Released_For_Service': str,
    'Aircraft_2__Maintenance_Status.Required_And_Correct_Doc_On_Board': str,
    'Aircraft_2__Maintenance_Status.Maintenance_Type': str,
    'Aircraft_2__Maintenance_Status.Maintenance_Items_Involved': str,
    'Aircraft_2__Cabin_Lighting': str,
    'Aircraft_2__Number_Of_Seats.Number': str,
    'Aircraft_2__Passengers_On_Board.Number': str,
    'Aircraft_2__Crew_Size_Flight_Attendant.Number_Of_Crew': str,
    'Person_1__Location_Of_Person': str,
    'Person_1__Location_In_Aircraft': str,
    'Person_1__Reporter_Organization': str,
    'Person_1__Function': str,
    'Person_1__Qualification': str,
    'Person_1__Experience': str,
    'Person_1__Cabin_Activity': str,
    'Person_1__Human_Factors': str,
    'Person_1__Communication_Breakdown': str,
    'Person_1__ASRS_Report_Number.Accession_Number': str,
    'Person_2__Location_Of_Person': str,
    'Person_2__Location_In_Aircraft': str,
    'Person_2__Reporter_Organization': str,
    'Person_2__Function': str,
    'Person_2__Qualification': str,
    'Person_2__Experience': str,
    'Person_2__Cabin_Activity': str,
    'Person_2__Human_Factors': str,
    'Person_2__Communication_Breakdown': str,
    'Person_2__ASRS_Report_Number.Accession_Number': str,
    'Events__Anomaly': str,
    'Events__Miss_Distance': str,
    'Events__Were_Passengers_Involved_In_Event': str,
    'Events__Detector': str,
    'Events__When_Detected': str,
    'Events__Result': str,
    'Assessments__Contributing_Factors_And_Situations': str,
    'Assessments__Primary_Problem': str,
    'Report_1__Narrative': str,
    'Report_1__Callback': str,
    'Report_2__Narrative': str,
    'Report_2__Callback': str,
    'Report_1__Synopsis': str,
}
```
