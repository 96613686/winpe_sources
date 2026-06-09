# Microsoft.VisualStudio.Setup.Installer.CommonErrors.LocalCommonErrorsList::.cctor

- ea: `0x532b0`
- end: `0x53618`
- name: `Microsoft.VisualStudio.Setup.Installer.CommonErrors.LocalCommonErrorsList::.cctor`
- size: `872`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callees

- `0x52d60`
- `0x52de0`
- `0x52e00`

## string_xrefs

- `0x533d7`: `Microsoft.VisualStudio.Setup.Configuration`
- `0x534ed`: `Microsoft.VisualStudio.OfficeDeveloperTools.WindowsIdentityFoundation.Msu`
- `0x534f5`: `Microsoft.Windows.D3DCompiler.Msu.Win7`

## pseudocode

```c

```

## disassembly

```asm
0x532b0  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::.ctor()
0x532b5  stloc.0
0x532b6  ldloc.0
0x532b7  ldc.i4.1
0x532b8  newarr   [mscorlib]System.String
0x532bd  dup
0x532be  ldc.i4.0
0x532bf  ldstr    a1073741790// "-1073741790"
0x532c4  stelem.ref
0x532c5  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode__1073741790_Message()
0x532ca  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x532cf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x532d4  ldloc.0
0x532d5  ldc.i4.s 0xA
0x532d7  newarr   [mscorlib]System.String
0x532dc  dup
0x532dd  ldc.i4.0
0x532de  ldstr    a0x80072ee7// "0x80072ee7"
0x532e3  stelem.ref
0x532e4  dup
0x532e5  ldc.i4.1
0x532e6  ldstr    a0x80072ee2// "0x80072ee2"
0x532eb  stelem.ref
0x532ec  dup
0x532ed  ldc.i4.2
0x532ee  ldstr    a0x80070006// "0x80070006"
0x532f3  stelem.ref
0x532f4  dup
0x532f5  ldc.i4.3
0x532f6  ldstr    a0x80070002// "0x80070002"
0x532fb  stelem.ref
0x532fc  dup
0x532fd  ldc.i4.4
0x532fe  ldstr    a0x80072efd// "0x80072efd"
0x53303  stelem.ref
0x53304  dup
0x53305  ldc.i4.5
0x53306  ldstr    a0x80072eff// "0x80072eff"
0x5330b  stelem.ref
0x5330c  dup
0x5330d  ldc.i4.6
0x5330e  ldstr    a0x80072f7d// "0x80072f7d"
0x53313  stelem.ref
0x53314  dup
0x53315  ldc.i4.7
0x53316  ldstr    a0x80131505// "0x80131505"
0x5331b  stelem.ref
0x5331c  dup
0x5331d  ldc.i4.8
0x5331e  ldstr    a0x80131509// "0x80131509"
0x53323  stelem.ref
0x53324  dup
0x53325  ldc.i4.s 9
0x53327  ldstr    a0x80131620// "0x80131620"
0x5332c  stelem.ref
0x5332d  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Error_NoInternetConnection_Message()
0x53332  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53337  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5333c  ldloc.0
0x5333d  ldc.i4.1
0x5333e  newarr   [mscorlib]System.String
0x53343  dup
0x53344  ldc.i4.0
0x53345  ldstr    a0x80096004// "0x80096004"
0x5334a  stelem.ref
0x5334b  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_0x80096004_Message()
0x53350  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53355  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5335a  ldloc.0
0x5335b  ldc.i4.1
0x5335c  newarr   [mscorlib]System.String
0x53361  dup
0x53362  ldc.i4.0
0x53363  ldstr    a1310// "1310"
0x53368  stelem.ref
0x53369  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1310_Message()
0x5336e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53373  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x53378  ldloc.0
0x53379  ldc.i4.1
0x5337a  newarr   [mscorlib]System.String
0x5337f  dup
0x53380  ldc.i4.0
0x53381  ldstr    a1303// "1303"
0x53386  stelem.ref
0x53387  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1303_Message()
0x5338c  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53391  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x53396  ldloc.0
0x53397  ldc.i4.1
0x53398  newarr   [mscorlib]System.String
0x5339d  dup
0x5339e  ldc.i4.0
0x5339f  ldstr    a1601// "1601"
0x533a4  stelem.ref
0x533a5  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1601_Message()
0x533aa  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x533af  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x533b4  ldloc.0
0x533b5  ldc.i4.1
0x533b6  newarr   [mscorlib]System.String
0x533bb  dup
0x533bc  ldc.i4.0
0x533bd  ldstr    a1603// "1603"
0x533c2  stelem.ref
0x533c3  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Error_WindowsInstallerServiceUnavailable_Message()
0x533c8  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x533cd  stloc.1
0x533ce  ldloc.1
0x533cf  ldc.i4.1
0x533d0  newarr   [mscorlib]System.String
0x533d5  dup
0x533d6  ldc.i4.0
0x533d7  ldstr    aMicrosoftVisua_15// "Microsoft.VisualStudio.Setup.Configurat"...
0x533dc  stelem.ref
0x533dd  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::set_PackageIds(string[] value)
0x533e2  ldloc.1
0x533e3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x533e8  ldloc.0
0x533e9  ldc.i4.1
0x533ea  newarr   [mscorlib]System.String
0x533ef  dup
0x533f0  ldc.i4.0
0x533f1  ldstr    a1603// "1603"
0x533f6  stelem.ref
0x533f7  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Error_MicrosoftLicensing_Message()
0x533fc  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53401  stloc.1
0x53402  ldloc.1
0x53403  ldc.i4.1
0x53404  newarr   [mscorlib]System.String
0x53409  dup
0x5340a  ldc.i4.0
0x5340b  ldstr    aMicrosoftVisua_16// "Microsoft.VisualStudio.Licensing"
0x53410  stelem.ref
0x53411  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::set_PackageIds(string[] value)
0x53416  ldloc.1
0x53417  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5341c  ldloc.0
0x5341d  ldc.i4.1
0x5341e  newarr   [mscorlib]System.String
0x53423  dup
0x53424  ldc.i4.0
0x53425  ldstr    a1618// "1618"
0x5342a  stelem.ref
0x5342b  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1618_Message()
0x53430  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53435  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5343a  ldloc.0
0x5343b  ldc.i4.1
0x5343c  newarr   [mscorlib]System.String
0x53441  dup
0x53442  ldc.i4.0
0x53443  ldstr    a1625// "1625"
0x53448  stelem.ref
0x53449  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1625_Message()
0x5344e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53453  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x53458  ldloc.0
0x53459  ldc.i4.1
0x5345a  newarr   [mscorlib]System.String
0x5345f  dup
0x53460  ldc.i4.0
0x53461  ldstr    a1632// "1632"
0x53466  stelem.ref
0x53467  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1632_Message()
0x5346c  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53471  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x53476  ldloc.0
0x53477  ldc.i4.1
0x53478  newarr   [mscorlib]System.String
0x5347d  dup
0x5347e  ldc.i4.0
0x5347f  ldstr    a1714// "1714"
0x53484  stelem.ref
0x53485  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_1714_Message()
0x5348a  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x5348f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x53494  ldloc.0
0x53495  ldc.i4.1
0x53496  newarr   [mscorlib]System.String
0x5349b  dup
0x5349c  ldc.i4.0
0x5349d  ldstr    a1719// "1719"
0x534a2  stelem.ref
0x534a3  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_Error_WindowsInstallerServiceUnavailable_Message()
0x534a8  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x534ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x534b2  ldloc.0
0x534b3  ldc.i4.1
0x534b4  newarr   [mscorlib]System.String
0x534b9  dup
0x534ba  ldc.i4.0
0x534bb  ldstr    a2_0// "2"
0x534c0  stelem.ref
0x534c1  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode_2_Message()
0x534c6  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x534cb  stloc.1
0x534cc  ldloc.1
0x534cd  ldc.i4.8
0x534ce  newarr   [mscorlib]System.String
0x534d3  dup
0x534d4  ldc.i4.0
0x534d5  ldstr    aMicrosoftDiagn// "Microsoft.DiagnosticsHub.KB2882822.Win7"
0x534da  stelem.ref
0x534db  dup
0x534dc  ldc.i4.1
0x534dd  ldstr    aMicrosoftNet48// "Microsoft.Net.4.8.KB5003304"
0x534e2  stelem.ref
0x534e3  dup
0x534e4  ldc.i4.2
0x534e5  ldstr    aMicrosoftNet48_0// "Microsoft.Net.4.8.KB5003306"
0x534ea  stelem.ref
0x534eb  dup
0x534ec  ldc.i4.3
0x534ed  ldstr    aMicrosoftVisua_17// "Microsoft.VisualStudio.OfficeDeveloperT"...
0x534f2  stelem.ref
0x534f3  dup
0x534f4  ldc.i4.4
0x534f5  ldstr    aMicrosoftWindo// "Microsoft.Windows.D3DCompiler.Msu.Win7"
0x534fa  stelem.ref
0x534fb  dup
0x534fc  ldc.i4.5
0x534fd  ldstr    aMicrosoftWindo_0// "Microsoft.Windows.UniversalCRT.Msu.7"
0x53502  stelem.ref
0x53503  dup
0x53504  ldc.i4.6
0x53505  ldstr    aMicrosoftWindo_1// "Microsoft.Windows.UniversalCRT.Msu.8"
0x5350a  stelem.ref
0x5350b  dup
0x5350c  ldc.i4.7
0x5350d  ldstr    aMicrosoftWindo_2// "Microsoft.Windows.UniversalCRT.Msu.81"
0x53512  stelem.ref
0x53513  callvirt instance modreq(System.Runtime.CompilerServices.IsExternalInit) void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::set_PackageIds(string[] value)
0x53518  ldloc.1
0x53519  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5351e  ldloc.0
0x5351f  ldc.i4.1
0x53520  newarr   [mscorlib]System.String
0x53525  dup
0x53526  ldc.i4.0
0x53527  ldstr    a2146233033// "-2146233033"
0x5352c  stelem.ref
0x5352d  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode__2146233033_Message()
0x53532  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53537  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5353c  ldloc.0
0x5353d  ldc.i4.1
0x5353e  newarr   [mscorlib]System.String
0x53543  dup
0x53544  ldc.i4.0
0x53545  ldstr    a2146233079// "-2146233079"
0x5354a  stelem.ref
0x5354b  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode__2146233079_Message()
0x53550  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53555  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo>::Add(var<u1>)
0x5355a  ldloc.0
0x5355b  ldc.i4.1
0x5355c  newarr   [mscorlib]System.String
0x53561  dup
0x53562  ldc.i4.0
0x53563  ldstr    a2147024891// "-2147024891"
0x53568  stelem.ref
0x53569  call     string [Microsoft.VisualStudio.Setup.InstallerResources]Microsoft.VisualStudio.Setup.Installer.Resources::get_ErrorCode__2147024891_Message()
0x5356e  newobj   instance void Microsoft.VisualStudio.Setup.Installer.CommonErrors.CommonErrorInfo::.ctor(string[] ErrorCodes, string Message)
0x53573  stloc.1
0x53574  ldloc.1
0x53575  ldc.i4.s 0xB
0x53577  newarr   [mscorlib]System.String
0x5357c  dup
0x5357d  ldc.i4.0
0x5357e  ldstr    aWin10sdkHidden// "Win10SDK_Hidden_10.0.10240_2"
0x53583  stelem.ref
0x53584  dup
0x53585  ldc.i4.1
0x53586  ldstr    aWin10sdk100105// "Win10SDK_10.0.10586.212"
0x5358b  stelem.ref
0x5358c  dup
0x5358d  ldc.i4.2
0x5358e  ldstr    aWin10sdk100143// "Win10SDK_10.0.14393.795"
0x53593  stelem.ref
0x53594  dup
0x53595  ldc.i4.3
0x53596  ldstr    aWin10sdk100150// "Win10SDK_10.0.15063"
0x5359b  stelem.ref
0x5359c  dup
0x5359d  ldc.i4.4
0x5359e  ldstr    aWin10sdk100162// "Win10SDK_10.0.16299"
0x535a3  stelem.ref
0x535a4  dup
0x535a5  ldc.i4.5
0x535a6  ldstr    aWin10sdk100171// "Win10SDK_10.0.17134"
0x535ab  stelem.ref
0x535ac  dup
0x535ad  ldc.i4.6
0x535ae  ldstr    aWin10sdk100177// "Win10SDK_10.0.17763"
0x535b3  stelem.ref
0x535b4  dup
0x535b5  ldc.i4.7
0x535b6  ldstr    aWin10sdkIpover// "Win10SDK_IpOverUsb"
  ... truncated ...
```
