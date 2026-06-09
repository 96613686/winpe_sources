# CSusEventSystem::Init(CSusClientGlobal *,CSusTestHook *)

- ea: `0x180016ce8`
- end: `0x1800170c6`
- name: `?Init@CSusEventSystem@@QEAAJPEAVCSusClientGlobal@@PEAVCSusTestHook@@@Z`
- size: `990`
- prototype: `__int64 __fastcall(CSusEventSystem *__hidden this, struct CSusClientGlobal *, struct CSusTestHook *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180013c88`

## callees

- `0x180016ce8`
- `0x18005fb4c`
- `0x180103acc`
- `0x18012b618`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016da7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ddc`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d1d`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016d76`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016da7`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180016ddc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016d47`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016e7e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016df1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d35`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016d8b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016dbc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180016df1`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016ef9`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016f61`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016fc4`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016ef9`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016f61`
- `ntdll!RtlSubscribeWnfStateChangeNotification` at `0x180016fc4`
- `USERENV!RegisterGPNotification` at `0x180016e69`
- `USERENV!RegisterGPNotification` at `0x180016e69`

## string_xrefs

- `0x180016f14`: `Fail to register notification for the policy allow update service: %lx`
- `0x180016f77`: `Fail to register notification for the policy update service URL: %lx`
- `0x180016fda`: `Fail to register notification for the policy allow non-Microsoft signed update: %lx`

## pseudocode

```c
__int64 __fastcall CSusEventSystem::Init(CSusEventSystem *this, struct CSusClientGlobal *a2, struct CSusTestHook *a3)
{
  HANDLE EventW; // rax
  void *v5; // rcx
  HANDLE v6; // rbx
  signed int LastError; // eax
  signed int v8; // ecx
  __int64 result; // rax
  HANDLE v10; // rax
  void *v11; // rcx
  HANDLE v12; // rbx
  HANDLE v13; // rax
  void *v14; // rcx
  HANDLE v15; // rbx
  HANDLE v16; // rax
  void *v17; // rcx
  HANDLE v18; // rbx
  void *v19; // rbx
  int v20; // esi
  unsigned int v21; // ebx
  BOOL v22; // eax
  signed int v23; // eax
  signed int v24; // edx
  int v25; // eax
  int v26; // eax
  int v27; // eax
  __int64 v28; // rax
  __int64 v29; // r8
  __int64 v30; // rdx
  __int64 v31; // rcx
  signed int v32; // [rsp+30h] [rbp-28h]
  __int64 v33; // [rsp+30h] [rbp-28h]
  __int64 v34; // [rsp+30h] [rbp-28h]
  __int64 v35; // [rsp+30h] [rbp-28h]

  *((_QWORD *)this + 1) = a3;
  *((_QWORD *)this + 147) = a2;
  EventW = CreateEventW(0, 1, 0, 0);
  v5 = (void *)*((_QWORD *)this + 35);
  v6 = EventW;
  if ( v5 )
    CloseHandle(v5);
  *((_QWORD *)this + 35) = v6;
  if ( !v6 )
    goto LABEL_4;
  v10 = CreateEventW(0, 0, 0, 0);
  v11 = (void *)*((_QWORD *)this + 34);
  v12 = v10;
  if ( v11 )
    CloseHandle(v11);
  *((_QWORD *)this + 34) = v12;
  if ( !v12 )
    goto LABEL_4;
  v13 = CreateEventW(0, 0, 1, 0);
  v14 = (void *)*((_QWORD *)this + 36);
  v15 = v13;
  if ( v14 )
    CloseHandle(v14);
  *((_QWORD *)this + 36) = v15;
  if ( !v15 )
    goto LABEL_4;
  v16 = CreateEventW(0, 0, 0, 0);
  v17 = (void *)*((_QWORD *)this + 37);
  v18 = v16;
  if ( v17 )
    CloseHandle(v17);
  *((_QWORD *)this + 37) = v18;
  if ( !v18 )
  {
LABEL_4:
    LastError = GetLastError();
    v8 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v8 = LastError;
    if ( v8 >= 0 )
      return (unsigned int)-2147418113;
    return (unsigned int)v8;
  }
  v19 = (void *)*((_QWORD *)this + 36);
  *((_DWORD *)this + 272) = 1;
  v20 = CIpAddressMonitor::Init((CSusEventSystem *)((char *)this + 1000), v19);
  result = CIpAddressMonitor::Init((CSusEventSystem *)((char *)this + 912), v19);
  if ( v20 >= 0 )
    result = (unsigned int)v20;
  if ( (int)result >= 0 )
  {
    result = CPowerStateMonitor::Init((CSusEventSystem *)((char *)this + 1152), *((void *const *)this + 37));
    v21 = result;
    if ( (int)result >= 0 )
    {
      v22 = RegisterGPNotification(*((HANDLE *)this + 35), 1);
      *((_DWORD *)this + 208) = v22;
      if ( v22 )
      {
LABEL_29:
        v25 = RtlSubscribeWnfStateChangeNotification(
                (char *)this + 840,
                WNF_ENTR_ALLOWUPDATESERVICE_POLICY_VALUE_CHANGED,
                0,
                EnterprisePolicyChangeCallback,
                *((_QWORD *)this + 35),
                0,
                0,
                0);
        if ( v25 < 0 )
        {
          LODWORD(v33) = v25 | 0x10000000;
          WUTrace(0, 0, 2048, 1, 0, L"Fail to register notification for the policy allow update service: %lx", v33);
        }
        v26 = RtlSubscribeWnfStateChangeNotification(
                (char *)this + 848,
                WNF_ENTR_UPDATESERVICEURL_POLICY_VALUE_CHANGED,
                0,
                EnterprisePolicyChangeCallback,
                *((_QWORD *)this + 35),
                0,
                0,
                0);
        if ( v26 < 0 )
        {
          LODWORD(v34) = v26 | 0x10000000;
          WUTrace(0, 0, 2048, 1, 0, L"Fail to register notification for the policy update service URL: %lx", v34);
        }
        v27 = RtlSubscribeWnfStateChangeNotification(
                (char *)this + 856,
                WNF_ENTR_ALLOWNONMICROSOFTSIGNEDUPDATE_POLICY_VALUE_CHANGED,
                0,
                EnterprisePolicyChangeCallback,
                *((_QWORD *)this + 35),
                0,
                0,
                0);
        if ( v27 < 0 )
        {
          LODWORD(v35) = v27 | 0x10000000;
          WUTrace(
            0,
            0,
            2048,
            1,
            0,
            L"Fail to register notification for the policy allow non-Microsoft signed update: %lx",
            v35);
        }
        v28 = *((_QWORD *)this + 34);
        v29 = *((_QWORD *)this + 37);
        v30 = *((_QWORD *)this + 36);
        v31 = *((_QWORD *)this + 35);
        *((_DWORD *)this + 76) = 0;
        *((_QWORD *)this + 39) = v28;
        *((_QWORD *)this + (unsigned int)++*((_DWORD *)this + 76) + 39) = v31;
        *((_QWORD *)this + (unsigned int)++*((_DWORD *)this + 76) + 39) = v30;
        *((_QWORD *)this + (unsigned int)++*((_DWORD *)this + 76) + 39) = v29;
        *((_DWORD *)this + 206) = ++*((_DWORD *)this + 76);
        result = v21;
        *((_DWORD *)this + 66) = 1;
        return result;
      }
      v23 = GetLastError();
      v24 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v24 = v23;
      if ( v24 < 0 )
      {
        if ( v24 == -2147024895 )
        {
          WUTrace(0, 0, 2048, 4, 0, L"GP notifications disabled; GP isn't present");
          goto LABEL_28;
        }
      }
      else
      {
        v24 = -2147418113;
      }
      v32 = v24;
      WUTrace(0, 0, 2048, 1, 0, L"Fail to register group policy notification: %lx", v32);
LABEL_28:
      v21 = 0;
      goto LABEL_29;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180016ce8  mov     [rsp+arg_0], rbx
0x180016ced  mov     [rsp+arg_8], rbp
0x180016cf2  mov     [rsp+arg_10], rsi
0x180016cf7  push    rdi
0x180016cf8  push    r14
0x180016cfa  push    r15
0x180016cfc  sub     rsp, 40h
0x180016d00  mov     [rcx+8], r8
0x180016d04  xor     r9d, r9d; lpName
0x180016d07  mov     [rcx+498h], rdx
0x180016d0e  mov     rbp, rcx
0x180016d11  xor     r8d, r8d; bInitialState
0x180016d14  xor     ecx, ecx; lpEventAttributes
0x180016d16  lea     r15d, [r9+1]
0x180016d1a  mov     edx, r15d; bManualReset
0x180016d1d  call    cs:__imp_CreateEventW
0x180016d23  mov     rcx, [rbp+118h]; hObject
0x180016d2a  xor     r14d, r14d
0x180016d2d  mov     rbx, rax
0x180016d30  test    rcx, rcx
0x180016d33  jz      short loc_180016D3B
0x180016d35  call    cs:__imp_CloseHandle
0x180016d3b  mov     [rbp+118h], rbx
0x180016d42  test    rbx, rbx
0x180016d45  jnz     short loc_180016D6C
0x180016d47  call    cs:__imp_GetLastError
0x180016d4d  movzx   ecx, ax
0x180016d50  mov     edx, 8000FFFFh
0x180016d55  or      ecx, 80070000h
0x180016d5b  test    eax, eax
0x180016d5d  cmovle  ecx, eax
0x180016d60  test    ecx, ecx
0x180016d62  cmovns  ecx, edx
0x180016d65  mov     eax, ecx
0x180016d67  jmp     loc_180017079
0x180016d6c  xor     r9d, r9d; lpName
0x180016d6f  xor     r8d, r8d; bInitialState
0x180016d72  xor     edx, edx; bManualReset
0x180016d74  xor     ecx, ecx; lpEventAttributes
0x180016d76  call    cs:__imp_CreateEventW
0x180016d7c  mov     rcx, [rbp+110h]; hObject
0x180016d83  mov     rbx, rax
0x180016d86  test    rcx, rcx
0x180016d89  jz      short loc_180016D91
0x180016d8b  call    cs:__imp_CloseHandle
0x180016d91  mov     [rbp+110h], rbx
0x180016d98  test    rbx, rbx
0x180016d9b  jz      short loc_180016D47
0x180016d9d  xor     r9d, r9d; lpName
0x180016da0  mov     r8d, r15d; bInitialState
0x180016da3  xor     edx, edx; bManualReset
0x180016da5  xor     ecx, ecx; lpEventAttributes
0x180016da7  call    cs:__imp_CreateEventW
0x180016dad  mov     rcx, [rbp+120h]; hObject
0x180016db4  mov     rbx, rax
0x180016db7  test    rcx, rcx
0x180016dba  jz      short loc_180016DC2
0x180016dbc  call    cs:__imp_CloseHandle
0x180016dc2  mov     [rbp+120h], rbx
0x180016dc9  test    rbx, rbx
0x180016dcc  jz      loc_180016D47
0x180016dd2  xor     r9d, r9d; lpName
0x180016dd5  xor     r8d, r8d; bInitialState
0x180016dd8  xor     edx, edx; bManualReset
0x180016dda  xor     ecx, ecx; lpEventAttributes
0x180016ddc  call    cs:__imp_CreateEventW
0x180016de2  mov     rcx, [rbp+128h]; hObject
0x180016de9  mov     rbx, rax
0x180016dec  test    rcx, rcx
0x180016def  jz      short loc_180016DF7
0x180016df1  call    cs:__imp_CloseHandle
0x180016df7  mov     [rbp+128h], rbx
0x180016dfe  test    rbx, rbx
0x180016e01  jz      loc_180016D47
0x180016e07  mov     rbx, [rbp+120h]
0x180016e0e  lea     rdi, [rbp+390h]
0x180016e15  lea     rcx, [rdi+58h]; this
0x180016e19  mov     [rdi+0B0h], r15d
0x180016e20  mov     rdx, rbx; void *
0x180016e23  call    ?Init@CIpAddressMonitor@@QEAAJPEAX@Z; CIpAddressMonitor::Init(void *)
0x180016e28  mov     rdx, rbx; void *
0x180016e2b  mov     rcx, rdi; this
0x180016e2e  mov     esi, eax
0x180016e30  call    ?Init@CIpAddressMonitor@@QEAAJPEAX@Z; CIpAddressMonitor::Init(void *)
0x180016e35  test    esi, esi
0x180016e37  cmovns  eax, esi
0x180016e3a  test    eax, eax
0x180016e3c  js      loc_180017079
0x180016e42  mov     rdx, [rbp+128h]; void *
0x180016e49  lea     rcx, [rbp+480h]; this
0x180016e50  call    ?Init@CPowerStateMonitor@@QEAAJQEAX@Z; CPowerStateMonitor::Init(void * const)
0x180016e55  mov     ebx, eax
0x180016e57  test    eax, eax
0x180016e59  js      loc_180017079
0x180016e5f  mov     rcx, [rbp+118h]; hEvent
0x180016e66  mov     edx, r15d; bMachine
0x180016e69  call    cs:__imp_RegisterGPNotification
0x180016e6f  mov     [rbp+340h], eax
0x180016e75  mov     edi, 800h
0x180016e7a  test    eax, eax
0x180016e7c  jnz     short loc_180016EC6
0x180016e7e  call    cs:__imp_GetLastError
0x180016e84  movzx   edx, ax
0x180016e87  or      edx, 80070000h
0x180016e8d  test    eax, eax
0x180016e8f  cmovle  edx, eax
0x180016e92  test    edx, edx
0x180016e94  js      loc_180017092
0x180016e9a  mov     edx, 8000FFFFh
0x180016e9f  mov     dword ptr [rsp+58h+var_28], edx
0x180016ea3  lea     rax, aFailToRegister_0; "Fail to register group policy notificat"...
0x180016eaa  mov     [rsp+58h+var_30], rax
0x180016eaf  mov     r9d, r15d
0x180016eb2  mov     r8d, edi
0x180016eb5  mov     [rsp+58h+var_38], r14
0x180016eba  xor     edx, edx
0x180016ebc  xor     ecx, ecx
0x180016ebe  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180016ec3  mov     ebx, r14d
0x180016ec6  mov     rax, [rbp+118h]
0x180016ecd  lea     rcx, [rbp+348h]
0x180016ed4  mov     rdx, cs:WNF_ENTR_ALLOWUPDATESERVICE_POLICY_VALUE_CHANGED
0x180016edb  lea     r9, ?EnterprisePolicyChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; EnterprisePolicyChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016ee2  mov     [rsp+58h+var_20], r14d
0x180016ee7  xor     r8d, r8d
0x180016eea  mov     dword ptr [rsp+58h+var_28], r14d
0x180016eef  mov     [rsp+58h+var_30], r14
0x180016ef4  mov     [rsp+58h+var_38], rax
0x180016ef9  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016eff  mov     esi, 10000000h
0x180016f04  test    eax, eax
0x180016f06  jns     short loc_180016F2E
0x180016f08  or      eax, esi
0x180016f0a  mov     r9d, r15d
0x180016f0d  mov     dword ptr [rsp+58h+var_28], eax
0x180016f11  mov     r8d, edi
0x180016f14  lea     rax, aFailToRegister; "Fail to register notification for the p"...
0x180016f1b  xor     edx, edx
0x180016f1d  mov     [rsp+58h+var_30], rax
0x180016f22  xor     ecx, ecx
0x180016f24  mov     [rsp+58h+var_38], r14
0x180016f29  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180016f2e  mov     rax, [rbp+118h]
0x180016f35  lea     rcx, [rbp+350h]
0x180016f3c  mov     rdx, cs:WNF_ENTR_UPDATESERVICEURL_POLICY_VALUE_CHANGED
0x180016f43  lea     r9, ?EnterprisePolicyChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; EnterprisePolicyChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016f4a  mov     [rsp+58h+var_20], r14d
0x180016f4f  xor     r8d, r8d
0x180016f52  mov     dword ptr [rsp+58h+var_28], r14d
0x180016f57  mov     [rsp+58h+var_30], r14
0x180016f5c  mov     [rsp+58h+var_38], rax
0x180016f61  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016f67  test    eax, eax
0x180016f69  jns     short loc_180016F91
0x180016f6b  or      eax, esi
0x180016f6d  mov     r9d, r15d
0x180016f70  mov     dword ptr [rsp+58h+var_28], eax
0x180016f74  mov     r8d, edi
0x180016f77  lea     rax, aFailToRegister_2; "Fail to register notification for the p"...
0x180016f7e  xor     edx, edx
0x180016f80  mov     [rsp+58h+var_30], rax
0x180016f85  xor     ecx, ecx
0x180016f87  mov     [rsp+58h+var_38], r14
0x180016f8c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180016f91  mov     rax, [rbp+118h]
0x180016f98  lea     rcx, [rbp+358h]
0x180016f9f  mov     rdx, cs:WNF_ENTR_ALLOWNONMICROSOFTSIGNEDUPDATE_POLICY_VALUE_CHANGED
0x180016fa6  lea     r9, ?EnterprisePolicyChangeCallback@@YAJU_WNF_STATE_NAME@@KPEAU_WNF_TYPE_ID@@PEAXPEBXK@Z; EnterprisePolicyChangeCallback(_WNF_STATE_NAME,ulong,_WNF_TYPE_ID *,void *,void const *,ulong)
0x180016fad  mov     [rsp+58h+var_20], r14d
0x180016fb2  xor     r8d, r8d
0x180016fb5  mov     dword ptr [rsp+58h+var_28], r14d
0x180016fba  mov     [rsp+58h+var_30], r14
0x180016fbf  mov     [rsp+58h+var_38], rax
0x180016fc4  call    cs:__imp_RtlSubscribeWnfStateChangeNotification
0x180016fca  test    eax, eax
0x180016fcc  jns     short loc_180016FF4
0x180016fce  or      eax, esi
0x180016fd0  mov     r9d, r15d
0x180016fd3  mov     dword ptr [rsp+58h+var_28], eax
0x180016fd7  mov     r8d, edi
0x180016fda  lea     rax, aFailToRegister_1; "Fail to register notification for the p"...
0x180016fe1  xor     edx, edx
0x180016fe3  mov     [rsp+58h+var_30], rax
0x180016fe8  xor     ecx, ecx
0x180016fea  mov     [rsp+58h+var_38], r14
0x180016fef  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180016ff4  mov     rax, [rbp+110h]
0x180016ffb  mov     r8, [rbp+128h]
0x180017002  mov     rdx, [rbp+120h]
0x180017009  mov     rcx, [rbp+118h]
0x180017010  mov     [rbp+130h], r14d
0x180017017  mov     [rbp+138h], rax
0x18001701e  add     [rbp+130h], r15d
0x180017025  mov     eax, [rbp+130h]
0x18001702b  mov     [rbp+rax*8+138h], rcx
0x180017033  add     [rbp+130h], r15d
0x18001703a  mov     eax, [rbp+130h]
0x180017040  mov     [rbp+rax*8+138h], rdx
0x180017048  add     [rbp+130h], r15d
0x18001704f  mov     eax, [rbp+130h]
0x180017055  mov     [rbp+rax*8+138h], r8
0x18001705d  add     [rbp+130h], r15d
0x180017064  mov     eax, [rbp+130h]
0x18001706a  mov     [rbp+338h], eax
0x180017070  mov     eax, ebx
0x180017072  mov     [rbp+108h], r15d
0x180017079  mov     rbx, [rsp+58h+arg_0]
0x18001707e  mov     rbp, [rsp+58h+arg_8]
0x180017083  mov     rsi, [rsp+58h+arg_10]
0x180017088  add     rsp, 40h
0x18001708c  pop     r15
0x18001708e  pop     r14
0x180017090  pop     rdi
0x180017091  retn
0x180017092  cmp     edx, 80070001h
0x180017098  jnz     loc_180016E9F
0x18001709e  lea     rax, aGpNotification; "GP notifications disabled; GP isn't pre"...
0x1800170a5  mov     r9d, 4
0x1800170ab  mov     [rsp+58h+var_30], rax
0x1800170b0  mov     r8d, edi
0x1800170b3  xor     edx, edx
0x1800170b5  mov     [rsp+58h+var_38], r14
0x1800170ba  xor     ecx, ecx
0x1800170bc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800170c1  jmp     loc_180016EC3
```
