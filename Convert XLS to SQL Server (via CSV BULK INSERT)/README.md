## How to convert XLS to SQL server (via CSV BULK insert) in C# using ByteScout Spreadsheet SDK

### The tutorial shows how to convert XLS to SQL server (via CSV BULK insert) in C#

The code below will help you to implement an C# app to convert XLS to SQL server (via CSV BULK insert). ByteScout Spreadsheet SDK can convert XLS to SQL server (via CSV BULK insert). It can be used from C#. ByteScout Spreadsheet SDK is the library (SDK) that is capable of writing, reading, modifying and calculating Excel and CSV spreadsheets. Most popular formulas can be calculated and reculculated with Excel installed. You may import or export data to and from CSV, XML, JSON as well as to and from databases, arrays.

The SDK samples like this one below explain how to quickly make your application do convert XLS to SQL server (via CSV BULK insert) in C# with the help of ByteScout Spreadsheet SDK. Just copy and paste the code into your C# application’s code and follow the instruction. Use of ByteScout Spreadsheet SDK in C# is also explained in the documentation included along with the product.

Trial version of ByteScout Spreadsheet SDK is available for free. Source code samples are included to help you with your C# app.

## REQUEST FREE TECH SUPPORT

[Click here to get in touch](https://bytescout.zendesk.com/hc/en-us/requests/new?subject=ByteScout%20Spreadsheet%20SDK%20Question)

or just send email to [support@bytescout.com](mailto:support@bytescout.com?subject=ByteScout%20Spreadsheet%20SDK%20Question) 

## ON-PREMISE OFFLINE SDK 

[Get Your 60 Day Free Trial](https://bytescout.com/download/web-installer?utm_source=github-readme)
[Explore SDK Docs](https://bytescout.com/documentation/index.html?utm_source=github-readme)
[Sign Up For Online Training](https://academy.bytescout.com/)


## ON-DEMAND REST WEB API

[Get your API key](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Documentation](https://pdf.co/documentation/api?utm_source=github-readme)
[Explore Web API Samples](https://github.com/bytescout/ByteScout-SDK-SourceCode/tree/master/PDF.co%20Web%20API)

## VIDEO REVIEW

[https://www.youtube.com/watch?v=nm_7I0PN1TY](https://www.youtube.com/watch?v=nm_7I0PN1TY)




<!-- code block begin -->

##### ****ExportToSQLServer.VS2005.csproj:**
    
```
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProductVersion>8.0.50727</ProductVersion>
    <SchemaVersion>2.0</SchemaVersion>
    <ProjectGuid>{8E22E915-5677-406D-8606-467F9C1CF2F4}</ProjectGuid>
    <OutputType>Exe</OutputType>
    <AppDesignerFolder>Properties</AppDesignerFolder>
    <RootNamespace>ExportToSQLServer</RootNamespace>
    <AssemblyName>ExportToSQLServer</AssemblyName>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>bin\Debug\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>bin\Release\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="Bytescout.Spreadsheet, Version=2.2.0.307, Culture=neutral, PublicKeyToken=f7dd1bd9d40a50eb, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
    </Reference>
    <Reference Include="System" />
    <Reference Include="System.Data" />
    <Reference Include="System.Xml" />
  </ItemGroup>
  <ItemGroup>
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Program.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
  </ItemGroup>
  <ItemGroup>
    <Content Include="SimpleReport.xls">
      <CopyToOutputDirectory>Always</CopyToOutputDirectory>
    </Content>
  </ItemGroup>
  <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
  <!-- To modify your build process, add your task inside one of the targets below and uncomment it. 
       Other similar extension points exist, see Microsoft.Common.targets.
  <Target Name="BeforeBuild">
  </Target>
  <Target Name="AfterBuild">
  </Target>
  -->
</Project>
```

<!-- code block end -->    

<!-- code block begin -->

##### ****ExportToSQLServer.csproj:**
    
```
<Project DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <PropertyGroup>
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>
    <Platform Condition=" '$(Platform)' == '' ">AnyCPU</Platform>
    <ProductVersion>8.0.50727</ProductVersion>
    <SchemaVersion>2.0</SchemaVersion>
    <ProjectGuid>{8E22E915-5677-406D-8606-467F9C1CF2F4}</ProjectGuid>
    <OutputType>Exe</OutputType>
    <AppDesignerFolder>Properties</AppDesignerFolder>
    <RootNamespace>ExportToSQLServer</RootNamespace>
    <AssemblyName>ExportToSQLServer</AssemblyName>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Debug|AnyCPU' ">
    <DebugSymbols>true</DebugSymbols>
    <DebugType>full</DebugType>
    <Optimize>false</Optimize>
    <OutputPath>bin\Debug\</OutputPath>
    <DefineConstants>DEBUG;TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <PropertyGroup Condition=" '$(Configuration)|$(Platform)' == 'Release|AnyCPU' ">
    <DebugType>pdbonly</DebugType>
    <Optimize>true</Optimize>
    <OutputPath>bin\Release\</OutputPath>
    <DefineConstants>TRACE</DefineConstants>
    <ErrorReport>prompt</ErrorReport>
    <WarningLevel>4</WarningLevel>
  </PropertyGroup>
  <ItemGroup>
    <Reference Include="Bytescout.Spreadsheet, Version=2.2.0.307, Culture=neutral, PublicKeyToken=f7dd1bd9d40a50eb, processorArchitecture=MSIL">
      <SpecificVersion>False</SpecificVersion>
    </Reference>
    <Reference Include="System" />
    <Reference Include="System.Data" />
    <Reference Include="System.Xml" />
  </ItemGroup>
  <ItemGroup>
  </ItemGroup>
  <ItemGroup>
    <Compile Include="Program.cs" />
    <Compile Include="Properties\AssemblyInfo.cs" />
  </ItemGroup>
  <ItemGroup>
    <Content Include="SimpleReport.xls">
      <CopyToOutputDirectory>Always</CopyToOutputDirectory>
    </Content>
  </ItemGroup>
  <Import Project="$(MSBuildBinPath)\Microsoft.CSharp.targets" />
  <!-- To modify your build process, add your task inside one of the targets below and uncomment it. 
       Other similar extension points exist, see Microsoft.Common.targets.
  <Target Name="BeforeBuild">
  </Target>
  <Target Name="AfterBuild">
  </Target>
  -->
</Project>
```

<!-- code block end -->    

<!-- code block begin -->

##### ****Program.cs:**
    
```
using System;
using System.IO;
using Bytescout.Spreadsheet;
using System.Data.SqlClient;

namespace ExportToSQLServer
{
	class Program
	{
		static void Main(string[] args)
		{
			try
			{
				// Load XLS document
				using (Spreadsheet document = new Spreadsheet())
				{
					document.LoadFromFile("SimpleReport.xls");
					string csvFile = Path.GetTempPath() + "SimpleReport.csv";

					// Save the document as CSV file
					document.Workbook.Worksheets[0].SaveAsCSV(csvFile);
					document.Close();

					if (File.Exists(csvFile))
					{
						// MODIFY THE CONNECTION STRING WITH YOUR CREDENTIALS!!!
						string connectionString = "Data Source=localhost;Initial Catalog=master;Integrated Security=true;";

						using (SqlConnection connection = new SqlConnection(connectionString))
						{
							connection.Open();

							// Drop test database if exists
							ExecuteQueryWithoutResult(connection,
													  "IF DB_ID ('XlsTests') IS NOT NULL DROP DATABASE XlsTests");
							// Create empty database
							ExecuteQueryWithoutResult(connection, "CREATE DATABASE XlsTests");
							// Switch to created database
							ExecuteQueryWithoutResult(connection, "USE XlsTests");
							// Create a table for CSV data
							ExecuteQueryWithoutResult(connection, 
							                          "CREATE TABLE CsvTest (Name VARCHAR(40), FullName VARCHAR(255))");
							// Export CSV data from local file
							ExecuteQueryWithoutResult(connection,
							                          "BULK INSERT CsvTest FROM '" + csvFile + "' " +
							                          "WITH ( FIELDTERMINATOR = ';', ROWTERMINATOR = '\n')");
							
							// Check the data successfully exported
							using (SqlCommand command = new SqlCommand("SELECT * from CsvTest", connection))
							{
								SqlDataReader reader = command.ExecuteReader();

								if (reader != null)
								{
									Console.WriteLine();
									Console.WriteLine("Exported CSV data:");
									Console.WriteLine();

									while (reader.Read())
									{
										Console.WriteLine(String.Format("{0}  |  {1}", reader[0], reader[1]));
									}
								}
							}

							Console.WriteLine();
							Console.WriteLine("Press any key.");
							Console.ReadKey();
						}
					}
				}
			}
			catch(Exception ex)
			{
				Console.WriteLine("Error: " + ex.Message);
				Console.ReadKey();
			}
		}

		static void ExecuteQueryWithoutResult(SqlConnection connection, string query)
		{
			using (SqlCommand command = new SqlCommand(query, connection))
			{
				command.ExecuteNonQuery();
			}
		}
	}
}

```

<!-- code block end -->