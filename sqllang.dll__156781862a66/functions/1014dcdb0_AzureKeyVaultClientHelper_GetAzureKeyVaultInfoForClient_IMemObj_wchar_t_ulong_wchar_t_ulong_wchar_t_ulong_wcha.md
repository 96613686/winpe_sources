# AzureKeyVaultClientHelper::GetAzureKeyVaultInfoForClient(IMemObj *,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong,wchar_t *,ulong,uchar * *,ulong &,uchar * *,ulong &,uchar *,ulong &,wchar_t *,ulong,wchar_t *,ulong,IMetadataAccess *,CSECCryptoContext &,ulong,_GUID,bool)

- ea: `0x1014dcdb0`
- end: `0x1014ddb2c`
- name: `?GetAzureKeyVaultInfoForClient@AzureKeyVaultClientHelper@@CA?AVCSECCryptoError@@PEAVIMemObj@@PEA_WK1K1K1KPEAPEAEAEAK23PEAE31K1KPEAVIMetadataAccess@@AEAVCSECCryptoContext@@KU_GUID@@_N@Z`
- size: `3452`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `service_task, broker_com_uri`

## callers

- `0x1014dc130`

## callees

- `0x100401070`
- `0x100401090`
- `0x100401400`
- `0x100401433`
- `0x100403080`
- `0x100755b10`
- `0x1007d40d0`
- `0x10121d660`
- `0x10149ce80`
- `0x10149cf70`
- `0x1014be930`
- `0x1014bf200`
- `0x1014bf6a0`
- `0x1014dcdb0`
- `0x1014df5c0`
- `0x1014e72b0`
- `0x1014e7320`
- `0x101e88fe0`
- `0x101e96da0`

## import_xrefs

- `KERNEL32!MultiByteToWideChar` at `0x1014dd91c`
- `KERNEL32!MultiByteToWideChar` at `0x1014dd960`
- `KERNEL32!MultiByteToWideChar` at `0x1014dd91c`
- `KERNEL32!MultiByteToWideChar` at `0x1014dd960`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd54c`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd6cd`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd7f8`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd54c`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd6cd`
- `secforwarder!CertFreeCertificateContext` at `0x1014dd7f8`
- `secforwarder!CertCloseStore` at `0x1014dd561`
- `secforwarder!CertCloseStore` at `0x1014dd6e2`
- `secforwarder!CertCloseStore` at `0x1014dd80d`
- `secforwarder!CertCloseStore` at `0x1014dd561`
- `secforwarder!CertCloseStore` at `0x1014dd6e2`
- `secforwarder!CertCloseStore` at `0x1014dd80d`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dd680`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dd7c2`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dd680`
- `sqldk!??_U@YAPEAX_KPEAVIMemObj@@HPEBDHE@Z` at `0x1014dd7c2`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd2e9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd31d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd45a`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd2e9`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd31d`
- `sqldk!??3@YAXPEAX_K@Z` at `0x1014dd45a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd44a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd53c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd57c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd64d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd793`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd9e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd9fd`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd44a`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd53c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd57c`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd64d`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd793`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd9e6`
- `sqldk!??_V@YAXPEAX@Z` at `0x1014dd9fd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014dd8bd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014dd8d4`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014dd8bd`
- `api-ms-win-crt-runtime-l1-1-0!_errno` at `0x1014dd8d4`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1014dd8e0`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo` at `0x1014dd8e0`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd346`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd369`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd3e2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd3fb`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd346`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd369`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd3e2`
- `api-ms-win-crt-string-l1-1-0!_wcsicmp` at `0x1014dd3fb`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x1014dd334`
- `sqlmin!??0AutoForcePhysMaster@@QEAA@XZ` at `0x1014dd334`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x1014dd43f`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x1014dd81b`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x1014dd43f`
- `sqlmin!??1AutoMasterUsageContext@@IEAA@XZ` at `0x1014dd81b`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd14e`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd15d`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd177`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1bc`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1c8`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1d4`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1f2`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd205`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd213`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd222`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd230`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd23c`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda18`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda56`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda62`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda6e`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda8d`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda9c`
- `sqlmin!GetXdbServerGlobals` at `0x1014ddaaa`
- `sqlmin!GetXdbServerGlobals` at `0x1014ddab6`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd14e`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd15d`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd177`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1bc`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1c8`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1d4`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd1f2`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd205`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd213`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd222`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd230`
- `sqlmin!GetXdbServerGlobals` at `0x1014dd23c`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda18`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda56`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda62`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda6e`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda8d`
- `sqlmin!GetXdbServerGlobals` at `0x1014dda9c`
- `sqlmin!GetXdbServerGlobals` at `0x1014ddaaa`
- `sqlmin!GetXdbServerGlobals` at `0x1014ddab6`
- `sqlfabric!GetManagedIdentityRegionalAuthNEndpoint` at `0x1014dda30`
- `sqlfabric!GetManagedIdentityRegionalAuthNEndpoint` at `0x1014dda30`
- `sqlfabric!GetAzureKeyVaultPrincipalCertificate` at `0x1014dd85a`
- `sqlfabric!GetAzureKeyVaultPrincipalCertificate` at `0x1014dd85a`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014dcf96`
- `sqlfabric!?FDatabaseLevelKeys@CFabricReplicaController@@QEAA_NXZ` at `0x1014dcf96`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014dcf66`
- `sqlfabric!?FPerDatabaseCMK@CFabricReplicaController@@QEAA_NXZ` at `0x1014dcf66`
- `sqlfabric!?GetFabricReplicaControllerByPhysicalDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@U_GUID@@@Z` at `0x1014dcf4e`
- `sqlfabric!?GetFabricReplicaControllerByPhysicalDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@U_GUID@@@Z` at `0x1014dcf4e`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014dcf33`
- `sqlfabric!?GetFabricReplicaControllerByDbIdWithRef@CFabricReplicaManager@@QEAAPEAVCFabricReplicaController@@AEBK@Z` at `0x1014dcf33`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x1014dcfde`
- `sqlfabric!GetServerManagedIdentityTypeWinFabProperty` at `0x1014dcfde`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x1014dd192`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x1014dd2ac`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x1014dd192`
- `sqlfabric!GetAzureKeyVaultClientId` at `0x1014dd2ac`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014dcf0c`
- `sqlfabric!?GetReplicaManagerWithRef@FabricStatefulServiceFactory@@SAPEAVCFabricReplicaManager@@XZ` at `0x1014dcf0c`

## string_xrefs

- `0x1014dd670`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014dd7b2`: `sql\ntdbms\msql\security\src\seccryptmd.cpp`
- `0x1014dcff4`: `Failed to get AzureKeyVaultIdentityType property from service fabric. HRESULT is:%lx`
- `0x1014dd285`: `Didn't find AzureKeyVaultClientId property after successfully calling service fabric`
- `0x1014dd1b0`: `Didn't find AzureKeyVaultClientId property, failed to get it from service fabric`
- `0x1014dd1a4`: `Didn't find AzureKeyVaultClientId property, failed to get it from service fabric. HRESULT is:%lx`
- `0x1014dd000`: `Failed to get AzureKeyVaultIdentityType property from service fabric`

## pseudocode

```c

```
