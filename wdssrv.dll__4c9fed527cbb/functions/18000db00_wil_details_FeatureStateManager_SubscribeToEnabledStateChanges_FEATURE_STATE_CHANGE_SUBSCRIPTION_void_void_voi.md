# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000db00`
- end: `0x18000dc09`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e630`

## callees

- `0x18000db00`
- `0x18000dd34`
- `0x18001d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000db74`
- `KERNEL32!GetModuleHandleW` at `0x18000db74`
- `KERNEL32!GetProcAddress` at `0x18000db91`
- `KERNEL32!GetProcAddress` at `0x18000db91`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000db38`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000db38`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dbe3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dbe3`

## string_xrefs

- `0x18000db6d`: `ntdll.dll`
- `0x18000db87`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(
        RTL_SRWLOCK *this,
        struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **a2,
        void (*a3)(void *),
        void *a4)
{
  RTL_SRWLOCK *v8; // rdi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v11; // eax

  *a2 = 0;
  if ( LOBYTE(this->Ptr) )
  {
    v8 = this + 4;
    AcquireSRWLockExclusive(this + 4);
    if ( this[18].Ptr )
      goto LABEL_10;
    this[18].Ptr = 0;
    ProcAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
    if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
      goto LABEL_8;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlRegisterFeatureConfigurationChangeNotification");
    g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)ProcAddress;
    if ( ProcAddress )
LABEL_8:
      v11 = ((__int64 (__fastcall *)(__int64 (__fastcall *)(void *), RTL_SRWLOCK *, _QWORD, RTL_SRWLOCK *))ProcAddress)(
              _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_,
              this,
              0,
              &this[18]);
    else
      v11 = -1073741511;
    if ( !v11 )
LABEL_10:
      wil::details_abi::SubscriptionList::SubscribeUnderLock((wil::details_abi::SubscriptionList *)&this[9], a2, a3, a4);
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000db00  mov     [rsp+arg_0], rbx
0x18000db05  mov     [rsp+arg_8], rbp
0x18000db0a  mov     [rsp+arg_10], rsi
0x18000db0f  push    rdi
0x18000db10  push    r14
0x18000db12  push    r15
0x18000db14  sub     rsp, 30h
0x18000db18  and     qword ptr [rdx], 0
0x18000db1c  mov     rbp, r9
0x18000db1f  cmp     byte ptr [rcx], 0
0x18000db22  mov     r15, r8
0x18000db25  mov     r14, rdx
0x18000db28  mov     rbx, rcx
0x18000db2b  jz      loc_18000DBEF
0x18000db31  lea     rdi, [rcx+20h]
0x18000db35  mov     rcx, rdi; SRWLock
0x18000db38  call    cs:__imp_AcquireSRWLockExclusive
0x18000db3f  nop     dword ptr [rax+rax+00h]
0x18000db44  lea     rsi, [rbx+90h]
0x18000db4b  cmp     qword ptr [rsi], 0
0x18000db4f  jnz     short loc_18000DBC9
0x18000db51  and     qword ptr [rsi], 0
0x18000db55  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000db5c  test    rax, rax
0x18000db5f  jnz     short loc_18000DBB0
0x18000db61  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000db68  test    rax, rax
0x18000db6b  jnz     short loc_18000DB87
0x18000db6d  lea     rcx, ModuleName; "ntdll.dll"
0x18000db74  call    cs:__imp_GetModuleHandleW
0x18000db7b  nop     dword ptr [rax+rax+00h]
0x18000db80  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000db87  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000db8e  mov     rcx, rax; hModule
0x18000db91  call    cs:__imp_GetProcAddress
0x18000db98  nop     dword ptr [rax+rax+00h]
0x18000db9d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000dba4  test    rax, rax
0x18000dba7  jnz     short loc_18000DBB0
0x18000dba9  mov     eax, 0C0000139h
0x18000dbae  jmp     short loc_18000DBC5
0x18000dbb0  mov     r9, rsi
0x18000dbb3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000dbba  xor     r8d, r8d
0x18000dbbd  mov     rdx, rbx
0x18000dbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbc5  test    eax, eax
0x18000dbc7  jnz     short loc_18000DBDB
0x18000dbc9  lea     rcx, [rbx+48h]; this
0x18000dbcd  mov     r9, rbp; void *
0x18000dbd0  mov     r8, r15; void (*)(void *)
0x18000dbd3  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000dbd6  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000dbdb  test    rdi, rdi
0x18000dbde  jz      short loc_18000DBEF
0x18000dbe0  mov     rcx, rdi; SRWLock
0x18000dbe3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000dbea  nop     dword ptr [rax+rax+00h]
0x18000dbef  mov     rbx, [rsp+48h+arg_0]
0x18000dbf4  mov     rbp, [rsp+48h+arg_8]
0x18000dbf9  mov     rsi, [rsp+48h+arg_10]
0x18000dbfe  add     rsp, 30h
0x18000dc02  pop     r15
0x18000dc04  pop     r14
0x18000dc06  pop     rdi
0x18000dc07  retn
```
