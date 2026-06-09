# CoCreateCOMTaskServerObject

- ea: `0x18001de34`
- end: `0x18001dfbb`
- name: `CoCreateCOMTaskServerObject`
- size: `391`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPVOID *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001dc9c`

## callees

- `0x1800172a8`
- `0x18001d588`
- `0x18001de34`
- `0x18002f78c`
- `0x18002f8c0`
- `0x1800301a4`
- `0x1800301e0`
- `0x180032110`
- `0x180062528`
- `0x180062584`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dec1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df7d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001dec1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001df7d`

## string_xrefs

- `0x18001dedd`: `shell\lib\comtaskserverutil.cpp`
- `0x18001df1f`: `shell\lib\comtaskserverutil.cpp`
- `0x18001de65`: `CoCreateCOMTaskServerObject`

## pseudocode

```c
__int64 __fastcall CoCreateCOMTaskServerObject(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, LPVOID *a6)
{
  LPVOID *v6; // rdi
  struct wil::details::IFailureCallback *v7; // rax
  unsigned int v8; // edx
  const unsigned __int16 *v9; // rcx
  HRESULT Instance; // eax
  unsigned int v11; // ebx
  __int64 v12; // rdx
  HRESULT v13; // eax
  const unsigned __int16 *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  int ppv; // [rsp+20h] [rbp-60h]
  int v19; // [rsp+30h] [rbp-50h] BYREF
  const char *v20; // [rsp+38h] [rbp-48h]
  __int64 v21; // [rsp+40h] [rbp-40h]
  char v22; // [rsp+48h] [rbp-38h]
  _BYTE v23[48]; // [rsp+50h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+8h]
  __int64 v25; // [rsp+A0h] [rbp+20h] BYREF

  v25 = a3;
  v6 = a6;
  *a6 = 0;
  v7 = (struct wil::details::IFailureCallback *)wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(
                                                  a1,
                                                  _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_);
  v22 = 0;
  v20 = "CoCreateCOMTaskServerObject";
  v19 = 0;
  v21 = 0;
  wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(
    (wil::details::ThreadFailureCallbackHolder *)v23,
    v7,
    (struct wil::CallContextInfo *)&v19,
    1);
  Instance = WaitForEventIfPresent(v9, v8);
  v11 = Instance;
  if ( Instance >= 0 )
  {
    Instance = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
    v11 = Instance;
    if ( Instance < 0 )
    {
      if ( Instance != -2147221164 )
      {
        v12 = 100;
        goto LABEL_6;
      }
      v25 = 0;
      v13 = _create___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEAAJW4EventOptions_2_PEBGPEAU_SECURITY_ATTRIBUTES__PEA_N_Z(&v25);
      v11 = v13;
      if ( v13 < 0 )
      {
        v15 = 107;
LABEL_10:
        v16 = (unsigned int)v13;
LABEL_11:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v15,
          (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
          (const char *)v16,
          ppv);
        __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
        goto LABEL_20;
      }
      v13 = RunTaskSchedulerTask(v14);
      v11 = v13;
      if ( v13 < 0 )
      {
        v15 = 110;
        goto LABEL_10;
      }
      if ( !(unsigned __int8)_wait___event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_returncode_policy_3__wil__QEBA_NKH_Z(&v25) )
      {
        v11 = -2147023436;
        v15 = 111;
        v16 = 2147943860LL;
        goto LABEL_11;
      }
      v13 = CoCreateInstance(&CLSID_CreateObjectAsSystem, 0, 4u, &GUID_75121952_e0d0_43e5_9380_1d80483acf72, v6);
      v11 = v13;
      if ( v13 < 0 )
      {
        v15 = 113;
        goto LABEL_10;
      }
      __1__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAA_XZ(&v25);
    }
    v11 = 0;
    goto LABEL_20;
  }
  v12 = 96;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v12,
    (unsigned int)"shell\\lib\\comtaskserverutil.cpp",
    (const char *)(unsigned int)Instance,
    ppv);
LABEL_20:
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)&v19);
  return v11;
}

```

## disassembly

```asm
0x18001de34  mov     [rsp-8+arg_0], rbx
0x18001de39  mov     [rsp-8+arg_8], rdi
0x18001de3e  mov     [rsp-8+arg_10], r8
0x18001de43  push    rbp
0x18001de44  mov     rbp, rsp
0x18001de47  sub     rsp, 80h
0x18001de4e  mov     rdi, [rbp+arg_28]
0x18001de52  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1ed552633946a27b818d04b3bf9896b5_@@CA@XZ; _lambda_1ed552633946a27b818d04b3bf9896b5_::_lambda_invoker_cdecl_(void)
0x18001de59  mov     qword ptr [rdi], 0
0x18001de60  call    ?get@?$static_lazy@VCoCreateInstanceAsSystemTelemetry@@@details@wil@@QEAAPEAVCoCreateInstanceAsSystemTelemetry@@P6AXXZ@Z; wil::details::static_lazy<CoCreateInstanceAsSystemTelemetry>::get(void (*)(void))
0x18001de65  lea     rcx, aCocreatecomtas; "CoCreateCOMTaskServerObject"
0x18001de6c  mov     [rbp+var_38], 0
0x18001de70  mov     [rbp+var_48], rcx
0x18001de74  lea     r8, [rbp+var_50]; struct wil::CallContextInfo *
0x18001de78  lea     rcx, [rbp+var_30]; this
0x18001de7c  mov     [rbp+var_50], 0
0x18001de83  mov     r9b, 1; bool
0x18001de86  mov     [rbp+var_40], 0
0x18001de8e  mov     rdx, rax; struct wil::details::IFailureCallback *
0x18001de91  call    ??0ThreadFailureCallbackHolder@details@wil@@QEAA@PEAUIFailureCallback@12@PEAUCallContextInfo@2@_N@Z; wil::details::ThreadFailureCallbackHolder::ThreadFailureCallbackHolder(wil::details::IFailureCallback *,wil::CallContextInfo *,bool)
0x18001de96  call    ?WaitForEventIfPresent@@YAJPEBGK@Z; WaitForEventIfPresent(ushort const *,ulong)
0x18001de9b  mov     ebx, eax
0x18001de9d  test    eax, eax
0x18001de9f  jns     short loc_18001DEA8
0x18001dea1  mov     edx, 60h ; '`'
0x18001dea6  jmp     short loc_18001DED9
0x18001dea8  xor     edx, edx; pUnkOuter
0x18001deaa  mov     qword ptr [rsp+80h+ppv], rdi; int
0x18001deaf  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18001deb6  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18001debd  lea     r8d, [rdx+4]; dwClsContext
0x18001dec1  call    cs:__imp_CoCreateInstance
0x18001dec7  mov     ebx, eax
0x18001dec9  test    eax, eax
0x18001decb  jns     short loc_18001DEF1
0x18001decd  cmp     eax, 80040154h
0x18001ded2  jz      short loc_18001DEFC
0x18001ded4  mov     edx, 64h ; 'd'; void *
0x18001ded9  mov     rcx, [rbp+8]; this
0x18001dedd  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001dee4  mov     r9d, eax; char *
0x18001dee7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001deec  jmp     loc_18001DF9B
0x18001def1  cmp     eax, 80040154h
0x18001def6  jnz     loc_18001DF99
0x18001defc  lea     rcx, [rbp+arg_10]
0x18001df00  mov     [rbp+arg_10], 0
0x18001df08  call    ?create@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEAAJW4EventOptions@2@PEBGPEAU_SECURITY_ATTRIBUTES@@PEA_N@Z
0x18001df0d  mov     ebx, eax
0x18001df0f  test    eax, eax
0x18001df11  jns     short loc_18001DF36
0x18001df13  mov     edx, 6Bh ; 'k'; void *
0x18001df18  mov     r9d, eax; char *
0x18001df1b  mov     rcx, [rbp+8]; this
0x18001df1f  lea     r8, aShellLibComtas; "shell\\lib\\comtaskserverutil.cpp"
0x18001df26  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df2b  lea     rcx, [rbp+arg_10]
0x18001df2f  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001df34  jmp     short loc_18001DF9B
0x18001df36  call    ?RunTaskSchedulerTask@@YAJPEBG@Z; RunTaskSchedulerTask(ushort const *)
0x18001df3b  mov     ebx, eax
0x18001df3d  test    eax, eax
0x18001df3f  jns     short loc_18001DF48
0x18001df41  mov     edx, 6Eh ; 'n'
0x18001df46  jmp     short loc_18001DF18
0x18001df48  lea     rcx, [rbp+arg_10]
0x18001df4c  call    ?wait@?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_returncode_policy@3@@wil@@QEBA_NKH@Z
0x18001df51  test    al, al
0x18001df53  jnz     short loc_18001DF64
0x18001df55  mov     ebx, 800705B4h
0x18001df5a  mov     edx, 6Fh ; 'o'
0x18001df5f  mov     r9d, ebx
0x18001df62  jmp     short loc_18001DF1B
0x18001df64  xor     edx, edx; pUnkOuter
0x18001df66  mov     qword ptr [rsp+80h+ppv], rdi; ppv
0x18001df6b  lea     r9, _GUID_75121952_e0d0_43e5_9380_1d80483acf72; riid
0x18001df72  lea     rcx, CLSID_CreateObjectAsSystem; rclsid
0x18001df79  lea     r8d, [rdx+4]; dwClsContext
0x18001df7d  call    cs:__imp_CoCreateInstance
0x18001df83  mov     ebx, eax
0x18001df85  test    eax, eax
0x18001df87  jns     short loc_18001DF90
0x18001df89  mov     edx, 71h ; 'q'
0x18001df8e  jmp     short loc_18001DF18
0x18001df90  lea     rcx, [rbp+arg_10]
0x18001df94  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x18001df99  xor     ebx, ebx
0x18001df9b  lea     rcx, [rbp+var_50]; this
0x18001df9f  call    ??1ActivityThreadWatcher@wil@@QEAA@XZ; wil::ActivityThreadWatcher::~ActivityThreadWatcher(void)
0x18001dfa4  lea     r11, [rsp+80h+var_s0]
0x18001dfac  mov     eax, ebx
0x18001dfae  mov     rbx, [r11+10h]
0x18001dfb2  mov     rdi, [r11+18h]
0x18001dfb6  mov     rsp, r11
0x18001dfb9  pop     rbp
0x18001dfba  retn
```
