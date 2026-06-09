# PopDiagInitialize

- ea: `0x140c775dc`
- end: `0x140c77873`
- name: `PopDiagInitialize`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x140c2464c`

## callees

- `0x14025be90`
- `0x140411260`
- `0x1404b1cb4`
- `0x1404f72f0`
- `0x140609c74`
- `0x140609cb4`
- `0x14060bbac`
- `0x1406dc8c0`
- `0x14079429c`
- `0x140797c64`
- `0x1407dba70`
- `0x140979f10`
- `0x14097a6d0`
- `0x140c775dc`

## import_xrefs

- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c77770`
- `ext-ms-win-kmpdc-l1-1-0!PdcTaskClientRegister` at `0x140c77770`

## pseudocode

```c
__int64 PopDiagInitialize()
{
  __int64 v0; // rcx
  int IsEnabledDeviceUsageNoInline; // eax
  BOOL v3; // [rsp+30h] [rbp-39h] BYREF
  int Variant; // [rsp+34h] [rbp-35h] BYREF
  int v5; // [rsp+38h] [rbp-31h] BYREF
  __int64 v6; // [rsp+40h] [rbp-29h] BYREF
  _BYTE v7[32]; // [rsp+50h] [rbp-19h] BYREF
  BOOL *v8; // [rsp+70h] [rbp+7h]
  __int64 v9; // [rsp+78h] [rbp+Fh]
  int *p_Variant; // [rsp+80h] [rbp+17h]
  __int64 v11; // [rsp+88h] [rbp+1Fh]
  int *v12; // [rsp+90h] [rbp+27h]
  __int64 v13; // [rsp+98h] [rbp+2Fh]
  __int64 *v14; // [rsp+A0h] [rbp+37h]
  __int64 v15; // [rsp+A8h] [rbp+3Fh]

  if ( EtwRegister(&POP_ETW_PROVIDER, PopDiagTraceControlCallback, &PopDiagHandle, &PopDiagHandle) >= 0 )
  {
    PopDiagHandleRegistered = 1;
    EtwSetInformation(
      PopDiagHandle,
      EventProviderSetTraits,
      &`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits,
      (unsigned __int16)`EnableManifestedProviderForMicrosoftTelemetry'::`2'::Traits);
  }
  PopDiagDeviceRundownWorkItem.Parameter = 0;
  PopDiagDeviceRundownWorkItem.WorkerRoutine = (void (__fastcall *)(void *))PopDiagDeviceRundownWorker;
  PopDiagDeviceRundownWorkItem.List.Flink = 0;
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B718, PopDiagTraceControlCallback, &dword_140E0B718);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B6E0, 0, 0);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B670, 0, 0);
  TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B6A8, 0, 0);
  if ( EtwRegister(&POP_TRIGGER_ETW_PROVIDER, 0, 0, &PopTriggerDiagHandle) >= 0 )
    PopTriggerDiagHandleRegistered = 1;
  if ( PopTriggerDiagHandleRegistered )
    PopThermalDeferedTraceThermalZoneEnumeration();
  PopDiagSleepStudyInitialize();
  if ( (int)TraceLoggingRegisterEx_EtwRegister_EtwSetInformation(&dword_140E0B940, 0, 0) >= 0 )
    PotsPowerTransitionsHandleRegistered = 1;
  qword_140EF9668 = 0;
  PopTelemetryOsState = 0;
  LOBYTE(v0) = 1;
  qword_140EF9678 = MEMORY[0xFFFFF78000000014];
  qword_140EF9680 = MEMORY[0xFFFFF78000000008];
  qword_140EF9688 = KiQueryUnbiasedInterruptTime(v0);
  byte_140EF96AC = 1;
  PopTransitionTelemetryOsState(1);
  PdcTaskClientRegister(68, &PopSleepStudyTaskClientActivator);
  if ( (unsigned int)dword_140E0B718 > 5 && (unsigned __int8)tlgKeywordOn(&dword_140E0B718, 0x400000000000LL) )
  {
    if ( (Feature_AusterityModeEnabled__private_featureState & 0x10) != 0 )
      IsEnabledDeviceUsageNoInline = Feature_AusterityModeEnabled__private_featureState & 1;
    else
      IsEnabledDeviceUsageNoInline = Feature_AusterityModeEnabled__private_IsEnabledDeviceUsageNoInline();
    v9 = 4;
    v8 = &v3;
    v3 = IsEnabledDeviceUsageNoInline != 0;
    Variant = Feature_AusterityModeEnabled__private_GetVariant();
    v11 = 4;
    p_Variant = &Variant;
    v5 = (unsigned __int64)wil_details_FeatureStateCache_GetCachedVariantState(
                             &Feature_AusterityModeEnabled__private_featureState,
                             Feature_AusterityModeEnabled__private_descriptor) >> 32;
    v13 = 4;
    v12 = &v5;
    v6 = 0x1000000;
    v14 = &v6;
    v15 = 8;
    tlgWriteTransfer_EtwWriteTransfer(&dword_140E0B718, &byte_14004C167, 0, 0, 6, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x140c775dc  push    rbp
0x140c775de  lea     rbp, [rsp-57h]
0x140c775e3  sub     rsp, 0C0h
0x140c775ea  mov     rax, cs:__security_cookie
0x140c775f1  xor     rax, rsp
0x140c775f4  mov     [rbp+57h+var_10], rax
0x140c775f8  lea     r8, PopDiagHandle; CallbackContext
0x140c775ff  mov     r9, r8; RegHandle
0x140c77602  lea     rdx, PopDiagTraceControlCallback; EnableCallback
0x140c77609  lea     rcx, POP_ETW_PROVIDER; ProviderId
0x140c77610  call    EtwRegister
0x140c77615  test    eax, eax
0x140c77617  js      short loc_140C77640
0x140c77619  movzx   r9d, cs:?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; InformationLength
0x140c77621  lea     r8, ?Traits@?1??EnableManifestedProviderForMicrosoftTelemetry@@9@9; EventInformation
0x140c77628  mov     rcx, cs:PopDiagHandle; RegHandle
0x140c7762f  mov     edx, 2; InformationClass
0x140c77634  mov     cs:PopDiagHandleRegistered, 1
0x140c7763b  call    EtwSetInformation
0x140c77640  lea     rax, PopDiagDeviceRundownWorker
0x140c77647  mov     cs:PopDiagDeviceRundownWorkItem.Parameter, 0
0x140c77652  lea     r8, dword_140E0B718
0x140c77659  mov     cs:PopDiagDeviceRundownWorkItem.WorkerRoutine, rax
0x140c77660  lea     rdx, PopDiagTraceControlCallback
0x140c77667  mov     cs:PopDiagDeviceRundownWorkItem.List.Flink, 0
0x140c77672  lea     rcx, dword_140E0B718
0x140c77679  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c7767e  xor     r8d, r8d
0x140c77681  lea     rcx, dword_140E0B6E0
0x140c77688  xor     edx, edx
0x140c7768a  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c7768f  xor     r8d, r8d
0x140c77692  lea     rcx, dword_140E0B670
0x140c77699  xor     edx, edx
0x140c7769b  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c776a0  xor     r8d, r8d
0x140c776a3  lea     rcx, dword_140E0B6A8
0x140c776aa  xor     edx, edx
0x140c776ac  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c776b1  lea     r9, PopTriggerDiagHandle; RegHandle
0x140c776b8  xor     r8d, r8d; CallbackContext
0x140c776bb  xor     edx, edx; EnableCallback
0x140c776bd  lea     rcx, POP_TRIGGER_ETW_PROVIDER; ProviderId
0x140c776c4  call    EtwRegister
0x140c776c9  test    eax, eax
0x140c776cb  js      short loc_140C776D4
0x140c776cd  mov     cs:PopTriggerDiagHandleRegistered, 1
0x140c776d4  cmp     cs:PopTriggerDiagHandleRegistered, 0
0x140c776db  jz      short loc_140C776E2
0x140c776dd  call    PopThermalDeferedTraceThermalZoneEnumeration
0x140c776e2  call    PopDiagSleepStudyInitialize
0x140c776e7  xor     r8d, r8d
0x140c776ea  lea     rcx, dword_140E0B940
0x140c776f1  xor     edx, edx
0x140c776f3  call    TraceLoggingRegisterEx_EtwRegister_EtwSetInformation
0x140c776f8  test    eax, eax
0x140c776fa  js      short loc_140C77703
0x140c776fc  mov     cs:PotsPowerTransitionsHandleRegistered, 1
0x140c77703  mov     cs:qword_140EF9668, 0
0x140c7770e  mov     rax, 0FFFFF78000000014h
0x140c77718  mov     cs:PopTelemetryOsState, 0
0x140c77723  mov     cl, 1
0x140c77725  mov     rax, [rax]
0x140c77728  mov     cs:qword_140EF9678, rax
0x140c7772f  mov     rax, 0FFFFF78000000008h
0x140c77739  mov     rax, [rax]
0x140c7773c  mov     cs:qword_140EF9680, rax
0x140c77743  call    KiQueryUnbiasedInterruptTime
0x140c77748  xor     r8d, r8d
0x140c7774b  mov     cs:qword_140EF9688, rax
0x140c77752  mov     cs:byte_140EF96AC, 1
0x140c77759  lea     edx, [r8+1]
0x140c7775d  mov     ecx, edx
0x140c7775f  call    PopTransitionTelemetryOsState
0x140c77764  lea     rdx, PopSleepStudyTaskClientActivator
0x140c7776b  mov     ecx, 44h ; 'D'
0x140c77770  call    cs:__imp_PdcTaskClientRegister
0x140c77777  nop     dword ptr [rax+rax+00h]
0x140c7777c  mov     eax, cs:dword_140E0B718
0x140c77782  cmp     eax, 5
0x140c77785  jbe     loc_140C7785B
0x140c7778b  mov     rdx, 400000000000h
0x140c77795  lea     rcx, dword_140E0B718
0x140c7779c  call    _tlgKeywordOn
0x140c777a1  test    al, al
0x140c777a3  jz      loc_140C7785B
0x140c777a9  mov     eax, cs:Feature_AusterityModeEnabled__private_featureState
0x140c777af  test    al, 10h
0x140c777b1  jz      short loc_140C777B8
0x140c777b3  and     eax, 1
0x140c777b6  jmp     short loc_140C777BD
0x140c777b8  call    Feature_AusterityModeEnabled__private_IsEnabledDeviceUsageNoInline
0x140c777bd  xor     ecx, ecx
0x140c777bf  mov     [rbp+57h+var_48], 4
0x140c777c7  test    eax, eax
0x140c777c9  lea     rax, [rbp+57h+var_90]
0x140c777cd  mov     [rbp+57h+var_50], rax
0x140c777d1  setnz   cl
0x140c777d4  mov     [rbp+57h+var_90], ecx
0x140c777d7  call    Feature_AusterityModeEnabled__private_GetVariant
0x140c777dc  mov     [rbp+57h+var_8C], eax
0x140c777df  lea     rdx, Feature_AusterityModeEnabled__private_descriptor
0x140c777e6  lea     rax, [rbp+57h+var_8C]
0x140c777ea  mov     [rbp+57h+var_38], 4
0x140c777f2  lea     rcx, Feature_AusterityModeEnabled__private_featureState
0x140c777f9  mov     [rbp+57h+var_40], rax
0x140c777fd  call    wil_details_FeatureStateCache_GetCachedVariantState
0x140c77802  shr     rax, 20h
0x140c77806  lea     rdx, byte_14004C167
0x140c7780d  mov     [rbp+57h+var_88], eax
0x140c77810  lea     rcx, dword_140E0B718
0x140c77817  lea     rax, [rbp+57h+var_88]
0x140c7781b  mov     [rbp+57h+var_28], 4
0x140c77823  mov     [rbp+57h+var_30], rax
0x140c77827  xor     r9d, r9d
0x140c7782a  lea     rax, [rbp+57h+var_80]
0x140c7782e  mov     [rbp+57h+var_80], 1000000h
0x140c77836  mov     [rbp+57h+var_20], rax
0x140c7783a  xor     r8d, r8d
0x140c7783d  lea     rax, [rbp+57h+var_70]
0x140c77841  mov     [rbp+57h+var_18], 8
0x140c77849  mov     [rsp+0C0h+var_98], rax
0x140c7784e  mov     [rsp+0C0h+var_A0], 6
0x140c77856  call    _tlgWriteTransfer_EtwWriteTransfer
0x140c7785b  xor     eax, eax
0x140c7785d  mov     rcx, [rbp+57h+var_10]
0x140c77861  xor     rcx, rsp; StackCookie
0x140c77864  call    __security_check_cookie
0x140c77869  add     rsp, 0C0h
0x140c77870  pop     rbp
0x140c77871  retn
```
