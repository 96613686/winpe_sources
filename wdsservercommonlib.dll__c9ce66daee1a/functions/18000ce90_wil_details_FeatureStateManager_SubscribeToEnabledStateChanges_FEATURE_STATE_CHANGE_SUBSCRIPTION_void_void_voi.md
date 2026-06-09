# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000ce90`
- end: `0x18000cf99`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d770`

## callees

- `0x18000ce90`
- `0x18000d0c4`
- `0x180030010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000cf21`
- `KERNEL32!GetProcAddress` at `0x18000cf21`
- `KERNEL32!GetModuleHandleW` at `0x18000cf04`
- `KERNEL32!GetModuleHandleW` at `0x18000cf04`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cec8`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000cec8`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cf73`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000cf73`

## string_xrefs

- `0x18000cefd`: `ntdll.dll`
- `0x18000cf17`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000ce90  mov     [rsp+arg_0], rbx
0x18000ce95  mov     [rsp+arg_8], rbp
0x18000ce9a  mov     [rsp+arg_10], rsi
0x18000ce9f  push    rdi
0x18000cea0  push    r14
0x18000cea2  push    r15
0x18000cea4  sub     rsp, 30h
0x18000cea8  and     qword ptr [rdx], 0
0x18000ceac  mov     rbp, r9
0x18000ceaf  cmp     byte ptr [rcx], 0
0x18000ceb2  mov     r15, r8
0x18000ceb5  mov     r14, rdx
0x18000ceb8  mov     rbx, rcx
0x18000cebb  jz      loc_18000CF7F
0x18000cec1  lea     rdi, [rcx+20h]
0x18000cec5  mov     rcx, rdi; SRWLock
0x18000cec8  call    cs:__imp_AcquireSRWLockExclusive
0x18000cecf  nop     dword ptr [rax+rax+00h]
0x18000ced4  lea     rsi, [rbx+90h]
0x18000cedb  cmp     qword ptr [rsi], 0
0x18000cedf  jnz     short loc_18000CF59
0x18000cee1  and     qword ptr [rsi], 0
0x18000cee5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000ceec  test    rax, rax
0x18000ceef  jnz     short loc_18000CF40
0x18000cef1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cef8  test    rax, rax
0x18000cefb  jnz     short loc_18000CF17
0x18000cefd  lea     rcx, ModuleName; "ntdll.dll"
0x18000cf04  call    cs:__imp_GetModuleHandleW
0x18000cf0b  nop     dword ptr [rax+rax+00h]
0x18000cf10  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf17  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000cf1e  mov     rcx, rax; hModule
0x18000cf21  call    cs:__imp_GetProcAddress
0x18000cf28  nop     dword ptr [rax+rax+00h]
0x18000cf2d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000cf34  test    rax, rax
0x18000cf37  jnz     short loc_18000CF40
0x18000cf39  mov     eax, 0C0000139h
0x18000cf3e  jmp     short loc_18000CF55
0x18000cf40  mov     r9, rsi
0x18000cf43  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000cf4a  xor     r8d, r8d
0x18000cf4d  mov     rdx, rbx
0x18000cf50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf55  test    eax, eax
0x18000cf57  jnz     short loc_18000CF6B
0x18000cf59  lea     rcx, [rbx+48h]; this
0x18000cf5d  mov     r9, rbp; void *
0x18000cf60  mov     r8, r15; void (*)(void *)
0x18000cf63  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000cf66  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000cf6b  test    rdi, rdi
0x18000cf6e  jz      short loc_18000CF7F
0x18000cf70  mov     rcx, rdi; SRWLock
0x18000cf73  call    cs:__imp_ReleaseSRWLockExclusive
0x18000cf7a  nop     dword ptr [rax+rax+00h]
0x18000cf7f  mov     rbx, [rsp+48h+arg_0]
0x18000cf84  mov     rbp, [rsp+48h+arg_8]
0x18000cf89  mov     rsi, [rsp+48h+arg_10]
0x18000cf8e  add     rsp, 30h
0x18000cf92  pop     r15
0x18000cf94  pop     r14
0x18000cf96  pop     rdi
0x18000cf97  retn
```
