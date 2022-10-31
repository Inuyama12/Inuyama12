-  <PropertyGroup Label="UserMacros" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <LinkIncremental>true</LinkIncremental>
    <IntDir>$(SolutionDir)\BuildTemp\$(Configuration)\</IntDir>
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\DEBUG_BUILDS\</OutDir>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <LinkIncremental>false</LinkIncremental>
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\</OutDir>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
  6  
Chapter11_SearchAlgorithms/Chapter11_SearchAlgorithms.vcxproj
@@ -18,13 +18,17 @@
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <UseDebugLibraries>true</UseDebugLibraries>
    <CharacterSet>MultiByte</CharacterSet>
    <CharacterSet>Unicode</CharacterSet>
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\DEBUG_BUILDS\</OutDir>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <UseDebugLibraries>false</UseDebugLibraries>
    <WholeProgramOptimization>true</WholeProgramOptimization>
    <CharacterSet>Unicode</CharacterSet>
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\</OutDir>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings">
  2  
Chapter11_StateMachines/Chapter11_StateMachines.vcxproj
@@ -38,9 +38,11 @@
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\</OutDir>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <IntDir>$(SolutionDir)\BuildTemp\$(ProjectName)_$(Configuration)\</IntDir>
    <OutDir>$(SolutionDir)\bin\DEBUG_BUILDS\</OutDir>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
 96  
Chapter1_BasicMemory/Chapter1_BasicMemory.vcxproj
@@ -0,0 +1,96 @@
<?xml version="1.0" encoding="utf-8"?>
<Project DefaultTargets="Build" ToolsVersion="4.0" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">
  <ItemGroup Label="ProjectConfigurations">
    <ProjectConfiguration Include="Debug|Win32">
      <Configuration>Debug</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
    <ProjectConfiguration Include="Release|Win32">
      <Configuration>Release</Configuration>
      <Platform>Win32</Platform>
    </ProjectConfiguration>
  </ItemGroup>
  <PropertyGroup Label="Globals">
    <ProjectGuid>{AB736FAE-3FEF-40C0-B426-BFC3E3FA569F}</ProjectGuid>
    <RootNamespace>Chapter1__01</RootNamespace>
    <ProjectName>Chapter1_BasicMemory</ProjectName>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.Default.props" />
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <CharacterSet>MultiByte</CharacterSet>
    <WholeProgramOptimization>true</WholeProgramOptimization>
  </PropertyGroup>
  <PropertyGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="Configuration">
    <ConfigurationType>Application</ConfigurationType>
    <CharacterSet>MultiByte</CharacterSet>
  </PropertyGroup>
  <Import Project="$(VCTargetsPath)\Microsoft.Cpp.props" />
  <ImportGroup Label="ExtensionSettings">
  </ImportGroup>
  <ImportGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'" Label="PropertySheets">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <ImportGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'" Label="PropertySheets">
    <Import Project="$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props" Condition="exists('$(UserRootDir)\Microsoft.Cpp.$(Platform).user.props')" Label="LocalAppDataPlatform" />
  </ImportGroup>
  <PropertyGroup Label="UserMacros" />
  <PropertyGroup>
    <_ProjectFileVersion>10.0.30319.1</_ProjectFileVersion>
    <OutDir Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">$(SolutionDir)\bin\DEBUG_BUILDS\</OutDir>
    <IntDir Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">$(SolutionDir)BuildTemp\$(ProjectName)$(Configuration)\</IntDir>
    <OutDir Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">$(SolutionDir)\bin\</OutDir>
    <IntDir Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">$(SolutionDir)BuildTemp\$(ProjectName)$(Configuration)\</IntDir>
  </PropertyGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Debug|Win32'">
    <ClCompile>
      <Optimization>Disabled</Optimization>
      <AdditionalIncludeDirectories>%(AdditionalIncludeDirectories)</AdditionalIncludeDirectories>
      <MinimalRebuild>true</MinimalRebuild>
      <BasicRuntimeChecks>EnableFastChecks</BasicRuntimeChecks>
      <RuntimeLibrary>MultiThreadedDebugDLL</RuntimeLibrary>
      <WarningLevel>Level3</WarningLevel>
      <DebugInformationFormat>EditAndContinue</DebugInformationFormat>
    </ClCompile>
    <Link>
      <AdditionalDependencies>allegro-5.0.10-monolith-md-debug.lib;%(AdditionalDependencies)</AdditionalDependencies>
      <AdditionalLibraryDirectories>%(AdditionalLibraryDirectories)</AdditionalLibraryDirectories>
      <GenerateDebugInformation>true</GenerateDebugInformation>
      <SubSystem>Windows</SubSystem>
      <TargetMachine>MachineX86</TargetMachine>
    </Link>
    <PostBuildEvent>
      <Command>copy "$(SolutionDir)game.map" "$(OutDir)game.map" /y &amp;&amp; copy "$(SolutionDir)arial.ttf" "$(OutDir)arial.ttf" /y </Command>
    </PostBuildEvent>
  </ItemDefinitionGroup>
  <ItemDefinitionGroup Condition="'$(Configuration)|$(Platform)'=='Release|Win32'">
    <ClCompile>
      <Optimization>MaxSpeed</Optimization>
      <IntrinsicFunctions>true</IntrinsicFunctions>
      <RuntimeLibrary>MultiThreadedDLL</RuntimeLibrary>
      <FunctionLevelLinking>true</FunctionLevelLinking>
      <WarningLevel>Level3</WarningLevel>
      <DebugInformationFormat>ProgramDatabase</DebugInformationFormat>
    </ClCompile>
    <Link>
      <AdditionalDependencies>%(AdditionalDependencies)</AdditionalDependencies>
      <GenerateDebugInformation>true</GenerateDebugInformation>
      <SubSystem>Windows</SubSystem>
      <OptimizeReferences>true</OptimizeReferences>
      <EnableCOMDATFolding>true</EnableCOMDATFolding>
      <TargetMachine>MachineX86</TargetMachine>
    </Link>
    <PostBuildEvent>
      <Command>copy "$(SolutionDir)game.map" "$(OutDir)game.map" /y &amp;&amp; copy "$(SolutionDir)arial.ttf" "$(OutDir)arial.ttf" /y </Command>
    </PostBuildEvent>
  </ItemDefinitionGroup>
  <ItemGroup>
    <ClCompile Include="game-BasicMem.cpp" />
</ItemGroup>
  <C1Compile Include='game-BasicMem.ccp' />
  
