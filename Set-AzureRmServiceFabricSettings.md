---
external help file: Microsoft.Azure.Commands.ServiceFabric.dll-Help.xml
online version: 
schema: 2.0.0
---

# Set-AzureRmServiceFabricSettings

## SYNOPSIS
Add or update one or more ServiceFabric settings in a cluster.

## SYNTAX

### OneSetting
```
Set-AzureRmServiceFabricSettings [-ResourceGroupName] <String> [-Name] <String> -Section <String>
 -Parameter <String> -Value <String> [-WhatIf] [-Confirm] [<CommonParameters>]
```

### BatchSettings
```
Set-AzureRmServiceFabricSettings [-ResourceGroupName] <String> [-Name] <String>
 -SettingsSectionDescriptions <PSSettingsSectionDescription[]> [-WhatIf] [-Confirm] [<CommonParameters>]
```

## DESCRIPTION
Use **Set-AzureRmServiceFabricSettings** to add or update ServiceFabric settings in a cluster.

## EXAMPLES

### Example 1
```
PS c:\> Set-AzureRmServiceFabricSettings -ResourceGroupName myResourceGroup -ClusterName myCluster -Section EseStore -Parameter Maxcursors -Value 1000
```

This command will Set 'Maxcursors' to value '1000' under the section 'EseStore'.

### Example 2
```
PS c:\>$settingsSectionDescription1 = New-Object Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsSectionDescription
PS c:\> $settingsSectionDescription1.Name = 'NamingService'
PS c:\>$settingsSectionDescription1.Parameters = New-Object "System.Collections.Generic.List[Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsParameterDescription]"

PS c:\>$parameter1 = New-Object Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsParameterDescription
PS c:\>$parameter1.Name = 'MaxOperationTimeout'
PS c:\>$parameter1.Value = '1000'

PS c:\>$parameter2 = New-Object Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsParameterDescription
PS c:\>$parameter2.Name = 'MaxFileOperationTimeout'
PS c:\>$parameter2.Value = '900'

PS c:\>$settingsSectionDescription1.Parameters.Add($parameter1)
PS c:\>$settingsSectionDescription1.Parameters.Add($parameter2)

PS c:\>$settingsSectionDescription2 = New-Object Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsSectionDescription
PS c:\>$settingsSectionDescription2.Name = 'EseStore'
PS c:\>$settingsSectionDescription2.Parameters =  New-Object "System.Collections.Generic.List[Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsParameterDescription]"

PS c:\>$parameter3 = New-Object Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsParameterDescription
PS c:\>$parameter3.Name = 'MaxCursors'
PS c:\>$parameter3.Value = '1000'

PS c:\>$settingsSectionDescription2.Parameters.Add($parameter3)
PS c:\>$arry=$settingsSectionDescription1 , $settingsSectionDescription2

PS c:\> Set-AzureRmServiceFabricSettings -SettingsSectionDescriptions $arry -ClusterName myclustername -ResourceGroupName clusterresourcegroup
```

This example updates a set of various fabric settings.

## PARAMETERS

### -Confirm
Prompts you for confirmation before running the cmdlet.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: cf

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### -Name
Name of the cluster.

```yaml
Type: String
Parameter Sets: (All)
Aliases: ClusterName

Required: True
Position: 1
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Parameter
Parameter.

```yaml
Type: String
Parameter Sets: OneSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -ResourceGroupName
Name of the resource group.

```yaml
Type: String
Parameter Sets: (All)
Aliases: 

Required: True
Position: 0
Default value: None
Accept pipeline input: True (ByPropertyName)
Accept wildcard characters: False
```

### -Section
Section.

```yaml
Type: String
Parameter Sets: OneSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -SettingsSectionDescriptions
Fabric Settings.

```yaml
Type: PSSettingsSectionDescription[]
Parameter Sets: BatchSettings
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -Value
Config Value.

```yaml
Type: String
Parameter Sets: OneSetting
Aliases: 

Required: True
Position: Named
Default value: None
Accept pipeline input: True (ByValue)
Accept wildcard characters: False
```

### -WhatIf
Shows what would happen if the cmdlet runs. The cmdlet is not run.

```yaml
Type: SwitchParameter
Parameter Sets: (All)
Aliases: wi

Required: False
Position: Named
Default value: None
Accept pipeline input: False
Accept wildcard characters: False
```

### CommonParameters
This cmdlet supports the common parameters: -Debug, -ErrorAction, -ErrorVariable, -InformationAction, -InformationVariable, -OutVariable, -OutBuffer, -PipelineVariable, -Verbose, -WarningAction, and -WarningVariable. For more information, see about_CommonParameters (http://go.microsoft.com/fwlink/?LinkID=113216).

## INPUTS

### System.String
Microsoft.Azure.Commands.ServiceFabric.Models.PSSettingsSectionDescription[]

## OUTPUTS

### Microsoft.Azure.Commands.ServiceFabric.Models.PsCluster

## NOTES

## RELATED LINKS

