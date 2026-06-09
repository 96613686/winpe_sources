# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000d9d0`
- end: `0x18000dad9`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e2b0`

## callees

- `0x18000d9d0`
- `0x18000dc04`
- `0x180031010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000da61`
- `KERNEL32!GetProcAddress` at `0x18000da61`
- `KERNEL32!GetModuleHandleW` at `0x18000da44`
- `KERNEL32!GetModuleHandleW` at `0x18000da44`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000da08`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000da08`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dab3`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000dab3`

## string_xrefs

- `0x18000da3d`: `ntdll.dll`
- `0x18000da57`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000d9d0  mov     [rsp+arg_0], rbx
0x18000d9d5  mov     [rsp+arg_8], rbp
0x18000d9da  mov     [rsp+arg_10], rsi
0x18000d9df  push    rdi
0x18000d9e0  push    r14
0x18000d9e2  push    r15
0x18000d9e4  sub     rsp, 30h
0x18000d9e8  and     qword ptr [rdx], 0
0x18000d9ec  mov     rbp, r9
0x18000d9ef  cmp     byte ptr [rcx], 0
0x18000d9f2  mov     r15, r8
0x18000d9f5  mov     r14, rdx
0x18000d9f8  mov     rbx, rcx
0x18000d9fb  jz      loc_18000DABF
0x18000da01  lea     rdi, [rcx+20h]
0x18000da05  mov     rcx, rdi; SRWLock
0x18000da08  call    cs:__imp_AcquireSRWLockExclusive
0x18000da0f  nop     dword ptr [rax+rax+00h]
0x18000da14  lea     rsi, [rbx+90h]
0x18000da1b  cmp     qword ptr [rsi], 0
0x18000da1f  jnz     short loc_18000DA99
0x18000da21  and     qword ptr [rsi], 0
0x18000da25  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000da2c  test    rax, rax
0x18000da2f  jnz     short loc_18000DA80
0x18000da31  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000da38  test    rax, rax
0x18000da3b  jnz     short loc_18000DA57
0x18000da3d  lea     rcx, ModuleName; "ntdll.dll"
0x18000da44  call    cs:__imp_GetModuleHandleW
0x18000da4b  nop     dword ptr [rax+rax+00h]
0x18000da50  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000da57  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000da5e  mov     rcx, rax; hModule
0x18000da61  call    cs:__imp_GetProcAddress
0x18000da68  nop     dword ptr [rax+rax+00h]
0x18000da6d  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000da74  test    rax, rax
0x18000da77  jnz     short loc_18000DA80
0x18000da79  mov     eax, 0C0000139h
0x18000da7e  jmp     short loc_18000DA95
0x18000da80  mov     r9, rsi
0x18000da83  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000da8a  xor     r8d, r8d
0x18000da8d  mov     rdx, rbx
0x18000da90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da95  test    eax, eax
0x18000da97  jnz     short loc_18000DAAB
0x18000da99  lea     rcx, [rbx+48h]; this
0x18000da9d  mov     r9, rbp; void *
0x18000daa0  mov     r8, r15; void (*)(void *)
0x18000daa3  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000daa6  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000daab  test    rdi, rdi
0x18000daae  jz      short loc_18000DABF
0x18000dab0  mov     rcx, rdi; SRWLock
0x18000dab3  call    cs:__imp_ReleaseSRWLockExclusive
0x18000daba  nop     dword ptr [rax+rax+00h]
0x18000dabf  mov     rbx, [rsp+48h+arg_0]
0x18000dac4  mov     rbp, [rsp+48h+arg_8]
0x18000dac9  mov     rsi, [rsp+48h+arg_10]
0x18000dace  add     rsp, 30h
0x18000dad2  pop     r15
0x18000dad4  pop     r14
0x18000dad6  pop     rdi
0x18000dad7  retn
```
