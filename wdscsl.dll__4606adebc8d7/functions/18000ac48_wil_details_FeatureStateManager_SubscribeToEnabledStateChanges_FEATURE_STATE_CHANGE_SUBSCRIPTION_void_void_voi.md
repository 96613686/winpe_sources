# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ac48`
- end: `0x18000ad51`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b520`

## callees

- `0x18000ac48`
- `0x18000ae7c`
- `0x18000e010`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad2b`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000ad2b`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ac80`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000ac80`
- `KERNEL32!GetProcAddress` at `0x18000acd9`
- `KERNEL32!GetProcAddress` at `0x18000acd9`
- `KERNEL32!GetModuleHandleW` at `0x18000acbc`
- `KERNEL32!GetModuleHandleW` at `0x18000acbc`

## string_xrefs

- `0x18000acb5`: `ntdll.dll`
- `0x18000accf`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000ac48  mov     [rsp+arg_0], rbx
0x18000ac4d  mov     [rsp+arg_8], rbp
0x18000ac52  mov     [rsp+arg_10], rsi
0x18000ac57  push    rdi
0x18000ac58  push    r14
0x18000ac5a  push    r15
0x18000ac5c  sub     rsp, 30h
0x18000ac60  and     qword ptr [rdx], 0
0x18000ac64  mov     rbp, r9
0x18000ac67  cmp     byte ptr [rcx], 0
0x18000ac6a  mov     r15, r8
0x18000ac6d  mov     r14, rdx
0x18000ac70  mov     rbx, rcx
0x18000ac73  jz      loc_18000AD37
0x18000ac79  lea     rdi, [rcx+20h]
0x18000ac7d  mov     rcx, rdi; SRWLock
0x18000ac80  call    cs:__imp_AcquireSRWLockExclusive
0x18000ac87  nop     dword ptr [rax+rax+00h]
0x18000ac8c  lea     rsi, [rbx+90h]
0x18000ac93  cmp     qword ptr [rsi], 0
0x18000ac97  jnz     short loc_18000AD11
0x18000ac99  and     qword ptr [rsi], 0
0x18000ac9d  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000aca4  test    rax, rax
0x18000aca7  jnz     short loc_18000ACF8
0x18000aca9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000acb0  test    rax, rax
0x18000acb3  jnz     short loc_18000ACCF
0x18000acb5  lea     rcx, ModuleName; "ntdll.dll"
0x18000acbc  call    cs:__imp_GetModuleHandleW
0x18000acc3  nop     dword ptr [rax+rax+00h]
0x18000acc8  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000accf  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000acd6  mov     rcx, rax; hModule
0x18000acd9  call    cs:__imp_GetProcAddress
0x18000ace0  nop     dword ptr [rax+rax+00h]
0x18000ace5  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000acec  test    rax, rax
0x18000acef  jnz     short loc_18000ACF8
0x18000acf1  mov     eax, 0C0000139h
0x18000acf6  jmp     short loc_18000AD0D
0x18000acf8  mov     r9, rsi
0x18000acfb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000ad02  xor     r8d, r8d
0x18000ad05  mov     rdx, rbx
0x18000ad08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad0d  test    eax, eax
0x18000ad0f  jnz     short loc_18000AD23
0x18000ad11  lea     rcx, [rbx+48h]; this
0x18000ad15  mov     r9, rbp; void *
0x18000ad18  mov     r8, r15; void (*)(void *)
0x18000ad1b  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000ad1e  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000ad23  test    rdi, rdi
0x18000ad26  jz      short loc_18000AD37
0x18000ad28  mov     rcx, rdi; SRWLock
0x18000ad2b  call    cs:__imp_ReleaseSRWLockExclusive
0x18000ad32  nop     dword ptr [rax+rax+00h]
0x18000ad37  mov     rbx, [rsp+48h+arg_0]
0x18000ad3c  mov     rbp, [rsp+48h+arg_8]
0x18000ad41  mov     rsi, [rsp+48h+arg_10]
0x18000ad46  add     rsp, 30h
0x18000ad4a  pop     r15
0x18000ad4c  pop     r14
0x18000ad4e  pop     rdi
0x18000ad4f  retn
```
