# CoCreateCOMTaskServerObject

- ea: `0x1800183f4`
- end: `0x1800185ac`
- name: `CoCreateCOMTaskServerObject`
- size: `440`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800185b4`

## callees

- `0x180005910`
- `0x180005cd8`
- `0x180007528`
- `0x18000934c`
- `0x18000b82c`
- `0x1800175fc`
- `0x180017bf8`
- `0x18001815c`
- `0x1800182ac`
- `0x1800183b4`
- `0x1800183f4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800184d9`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800184d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800184e7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018481`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001856e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180018481`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001856e`

## string_xrefs

- `0x18001849d`: `shell\lib\comtaskserverutil.cpp`
- `0x180018522`: `shell\lib\comtaskserverutil.cpp`
- `0x180018425`: `CoCreateCOMTaskServerObject`
- `0x1800184d0`: `Global\ShellCreateObjectTaskReadyEvent`

## pseudocode

```c
__int64 __fastcall CoCreateCOMTaskServerObject(
        __int64 a1,
        __int64 a2,
        wil::details *a3,
        __int64 a4,
        int a5,
        LPVOID *a6)
{
  LPVOID *ppv; // rdi
  __int64 *v7; // rax
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  HRESULT Instance; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  wil::details *v13; // rcx
  wil::details *Event; // rbx
  struct IRegisteredTask *v15; // rcx
  int LastErrorFailHr; // eax
  __int64 v17; // rdx
  __int64 v18; // r9
  void *v19; // rdx
  void *v20; // rdx
  int v22; // [rsp+30h] [rbp-50h] BYREF
  const char *v23; // [rsp+38h] [rbp-48h]
  __int64 v24; // [rsp+40h] [rbp-40h]
  char v25; // [rsp+48h] [rbp-38h]
  _BYTE v26[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  wil::details *v28; // [rsp+A0h] [rbp+20h] BYREF

  v28 = a3;
  ppv = a6;
  *a6 = 0;
  v7 = wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(
         a1,
         (void (__cdecl *)())_lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_);
  v25 = 0;
  v23 = "CoCreateCOMTaskServerObject";
  v22 = 0;
  v24 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v26,
    (struct wil::details::IFailureCallback *)v7,
    (struct wil::CallContextInfo *)&v22,
    1);
  Instance = WaitForEventIfPresent(v9, v8);
  v11 = Instance;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, ppv);
    v11 = Instance;
    if ( Instance < 0 )
    {
      if ( Instance != -2147221164 )
      {
        v12 = 100;
        goto LABEL_6;
      }
      v28 = 0;
      Event = (wil::details *)CreateEventExW(0, L"Global\\ShellCreateObjectTaskReadyEvent", 1u, 0x1F0003u);
      if ( Event )
      {
        GetLastError();
        _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
          &v28,
          Event);
      }
      else
      {
        LastErrorFailHr = wil::details::GetLastErrorFailHr(v13);
        v11 = LastErrorFailHr;
        if ( LastErrorFailHr < 0 )
        {
          v17 = 107;
          goto LABEL_14;
        }
      }
      LastErrorFailHr = RunTaskSchedulerTask(v15);
      v11 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v17 = 110;
LABEL_14:
        v18 = (unsigned int)LastErrorFailHr;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)v18);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
          &v28,
          v19);
        goto LABEL_22;
      }
      if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(&v28) )
      {
        v11 = -2147023436;
        v17 = 111;
        v18 = 2147943860LL;
        goto LABEL_15;
      }
      LastErrorFailHr = CoCreateInstance(
                          &CLSID_CreateObjectAsSystem,
                          0,
                          4u,
                          &GUID_75121952_e0d0_43e5_9380_1d80483acf72,
                          ppv);
      v11 = LastErrorFailHr;
      if ( LastErrorFailHr < 0 )
      {
        v17 = 113;
        goto LABEL_14;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(
        &v28,
        v20);
    }
    v11 = 0;
    goto LABEL_22;
  }
  v12 = 96;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (int)"shell\\lib\\comtaskserverutil.cpp",
    (const char *)(unsigned int)Instance);
LABEL_22:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v22);
  return v11;
}

```

## disassembly

```asm
0x1800183f4  mov     [rsp-8+arg_0], rbx
0x1800183f9  mov     [rsp-8+arg_8], rdi
0x1800183fe  mov     [rsp-8+arg_10], r8
0x180018403  push    rbp
0x180018404  mov     rbp, rsp
0x180018407  sub     rsp, 80h
0x18001840e  mov     rdi, [rbp+arg_28]
0x180018412  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_(void)
0x180018419  mov     qword ptr [rdi], 0
0x180018420  call    ?get@?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@QEAAPEAVCoCreateInstanceAsSystemTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(void (*)(void))
0x180018425  lea     rcx, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x18001842c  mov     [rbp+var_38], 0
0x180018430  mov     [rbp+var_48], rcx
0x180018434  lea     r8, [rbp+var_50]; struct wil::CallContextInfo *
0x180018438  lea     rcx, [rbp+var_30]; this
0x18001843c  mov     [rbp+var_50], 0
0x180018443  mov     r9b, 1; bool
0x180018446  mov     [rbp+var_40], 0
0x18001844e  mov     rdx, rax; struct wil::details::IFailureCallback *
0x180018451  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x180018456  call    ?WaitForEventIfPresent@@YAJPEBGK@Z; WaitForEventIfPresent(ushort const *,ulong)
0x18001845b  mov     ebx, eax
0x18001845d  test    eax, eax
0x18001845f  jns     short loc_180018468
0x180018461  mov     edx, 60h ; '`'
0x180018466  jmp     short loc_180018499
0x180018468  xor     edx, edx; pUnkOuter
0x18001846a  mov     [rsp+80h+ppv], rdi; int
0x18001846f  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180018476  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18001847d  lea     r8d, [rdx+4]; dwClsContext
0x180018481  call    cs:__imp_CoCreateInstance
0x180018487  mov     ebx, eax
0x180018489  test    eax, eax
0x18001848b  jns     short loc_1800184B1
0x18001848d  cmp     eax, 80040154h
0x180018492  jz      short loc_1800184BC
0x180018494  mov     edx, 64h ; 'd'; void *
0x180018499  mov     rcx, [rbp+8]; this
0x18001849d  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x1800184a4  mov     r9d, eax; char *
0x1800184a7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800184ac  jmp     loc_18001858C
0x1800184b1  cmp     eax, 80040154h
0x1800184b6  jnz     loc_18001858A
0x1800184bc  mov     r9d, 1F0003h; dwDesiredAccess
0x1800184c2  mov     [rbp+arg_10], 0
0x1800184ca  mov     r8d, 1; dwFlags
0x1800184d0  lea     rdx, aGlobalShellcre; "Global\\ShellCreateObjectTaskReadyEvent"
0x1800184d7  xor     ecx, ecx; lpEventAttributes
0x1800184d9  call    cs:__imp_CreateEventExW
0x1800184df  mov     rbx, rax
0x1800184e2  test    rax, rax
0x1800184e5  jz      short loc_18001850B
0x1800184e7  call    cs:__imp_GetLastError
0x1800184ed  mov     rdx, rbx
0x1800184f0  lea     rcx, [rbp+arg_10]
0x1800184f4  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x1800184f9  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x1800184fe  mov     ebx, eax
0x180018500  test    eax, eax
0x180018502  jns     short loc_180018539
0x180018504  mov     edx, 6Eh ; 'n'
0x180018509  jmp     short loc_18001851B
0x18001850b  call    ?GetLastErrorFailHr@details@wil@@YAJXZ; wil::details::GetLastErrorFailHr(void)
0x180018510  mov     ebx, eax
0x180018512  test    eax, eax
0x180018514  jns     short loc_1800184F9
0x180018516  mov     edx, 6Bh ; 'k'; void *
0x18001851b  mov     r9d, eax; char *
0x18001851e  mov     rcx, [rbp+8]; this
0x180018522  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x180018529  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001852e  lea     rcx, [rbp+arg_10]
0x180018532  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180018537  jmp     short loc_18001858C
0x180018539  lea     rcx, [rbp+arg_10]
0x18001853d  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x180018542  test    al, al
0x180018544  jnz     short loc_180018555
0x180018546  mov     ebx, 800705B4h
0x18001854b  mov     edx, 6Fh ; 'o'
0x180018550  mov     r9d, ebx
0x180018553  jmp     short loc_18001851E
0x180018555  xor     edx, edx; pUnkOuter
0x180018557  mov     [rsp+80h+ppv], rdi; ppv
0x18001855c  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x180018563  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18001856a  lea     r8d, [rdx+4]; dwClsContext
0x18001856e  call    cs:__imp_CoCreateInstance
0x180018574  mov     ebx, eax
0x180018576  test    eax, eax
0x180018578  jns     short loc_180018581
0x18001857a  mov     edx, 71h ; 'q'
0x18001857f  jmp     short loc_18001851B
0x180018581  lea     rcx, [rbp+arg_10]
0x180018585  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001858a  xor     ebx, ebx
0x18001858c  lea     rcx, [rbp+var_50]; this
0x180018590  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x180018595  lea     r11, [rsp+80h+var_s0]
0x18001859d  mov     eax, ebx
0x18001859f  mov     rbx, [r11+10h]
0x1800185a3  mov     rdi, [r11+18h]
0x1800185a7  mov     rsp, r11
0x1800185aa  pop     rbp
0x1800185ab  retn
```
