# wil::details::FeatureStateManager::SubscribeToEnabledStateChanges(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)

- ea: `0x18000fd60`
- end: `0x18000fe69`
- name: `?SubscribeToEnabledStateChanges@FeatureStateManager@details@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z`
- size: `265`
- prototype: `void(wil::details::FeatureStateManager *__hidden this, struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010740`

## callees

- `0x18000fd60`
- `0x18000ff94`
- `0x180013010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000fdf1`
- `KERNEL32!GetProcAddress` at `0x18000fdf1`
- `KERNEL32!GetModuleHandleW` at `0x18000fdd4`
- `KERNEL32!GetModuleHandleW` at `0x18000fdd4`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fd98`
- `KERNEL32!AcquireSRWLockExclusive` at `0x18000fd98`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe43`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000fe43`

## string_xrefs

- `0x18000fdcd`: `ntdll.dll`
- `0x18000fde7`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000fd60  mov     [rsp+arg_0], rbx
0x18000fd65  mov     [rsp+arg_8], rbp
0x18000fd6a  mov     [rsp+arg_10], rsi
0x18000fd6f  push    rdi
0x18000fd70  push    r14
0x18000fd72  push    r15
0x18000fd74  sub     rsp, 30h
0x18000fd78  and     qword ptr [rdx], 0
0x18000fd7c  mov     rbp, r9
0x18000fd7f  cmp     byte ptr [rcx], 0
0x18000fd82  mov     r15, r8
0x18000fd85  mov     r14, rdx
0x18000fd88  mov     rbx, rcx
0x18000fd8b  jz      loc_18000FE4F
0x18000fd91  lea     rdi, [rcx+20h]
0x18000fd95  mov     rcx, rdi; SRWLock
0x18000fd98  call    cs:__imp_AcquireSRWLockExclusive
0x18000fd9f  nop     dword ptr [rax+rax+00h]
0x18000fda4  lea     rsi, [rbx+90h]
0x18000fdab  cmp     qword ptr [rsi], 0
0x18000fdaf  jnz     short loc_18000FE29
0x18000fdb1  and     qword ptr [rsi], 0
0x18000fdb5  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000fdbc  test    rax, rax
0x18000fdbf  jnz     short loc_18000FE10
0x18000fdc1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fdc8  test    rax, rax
0x18000fdcb  jnz     short loc_18000FDE7
0x18000fdcd  lea     rcx, ModuleName; "ntdll.dll"
0x18000fdd4  call    cs:__imp_GetModuleHandleW
0x18000fddb  nop     dword ptr [rax+rax+00h]
0x18000fde0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fde7  lea     rdx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000fdee  mov     rcx, rax; hModule
0x18000fdf1  call    cs:__imp_GetProcAddress
0x18000fdf8  nop     dword ptr [rax+rax+00h]
0x18000fdfd  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000fe04  test    rax, rax
0x18000fe07  jnz     short loc_18000FE10
0x18000fe09  mov     eax, 0C0000139h
0x18000fe0e  jmp     short loc_18000FE25
0x18000fe10  mov     r9, rsi
0x18000fe13  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1ad7ecfab602a777ecf020873216a663_@@CA@PEAX@Z; _lambda_1ad7ecfab602a777ecf020873216a663_::_lambda_invoker_cdecl_(void *)
0x18000fe1a  xor     r8d, r8d
0x18000fe1d  mov     rdx, rbx
0x18000fe20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe25  test    eax, eax
0x18000fe27  jnz     short loc_18000FE3B
0x18000fe29  lea     rcx, [rbx+48h]; this
0x18000fe2d  mov     r9, rbp; void *
0x18000fe30  mov     r8, r15; void (*)(void *)
0x18000fe33  mov     rdx, r14; struct FEATURE_STATE_CHANGE_SUBSCRIPTION__ **
0x18000fe36  call    ?SubscribeUnderLock@SubscriptionList@details_abi@wil@@QEAAXPEAPEAUFEATURE_STATE_CHANGE_SUBSCRIPTION__@@P6AXPEAX@Z1@Z; wil::details_abi::SubscriptionList::SubscribeUnderLock(FEATURE_STATE_CHANGE_SUBSCRIPTION__ * *,void (*)(void *),void *)
0x18000fe3b  test    rdi, rdi
0x18000fe3e  jz      short loc_18000FE4F
0x18000fe40  mov     rcx, rdi; SRWLock
0x18000fe43  call    cs:__imp_ReleaseSRWLockExclusive
0x18000fe4a  nop     dword ptr [rax+rax+00h]
0x18000fe4f  mov     rbx, [rsp+48h+arg_0]
0x18000fe54  mov     rbp, [rsp+48h+arg_8]
0x18000fe59  mov     rsi, [rsp+48h+arg_10]
0x18000fe5e  add     rsp, 30h
0x18000fe62  pop     r15
0x18000fe64  pop     r14
0x18000fe66  pop     rdi
0x18000fe67  retn
```
