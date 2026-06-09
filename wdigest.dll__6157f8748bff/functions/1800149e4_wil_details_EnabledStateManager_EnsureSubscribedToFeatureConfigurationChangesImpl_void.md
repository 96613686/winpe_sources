# wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(void)

- ea: `0x1800149e4`
- end: `0x180014a9b`
- name: `?EnsureSubscribedToFeatureConfigurationChangesImpl@EnabledStateManager@details@wil@@AEAAIXZ`
- size: `183`
- prototype: `unsigned int __fastcall(wil::details::EnabledStateManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000b2ac`

## callees

- `0x1800149e4`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014a03`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014a03`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a91`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a1f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a68`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180014a91`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::EnsureSubscribedToFeatureConfigurationChangesImpl(
        RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  RTL_SRWLOCK *v3; // rsi
  unsigned int Ptr_high; // edi
  void (__fastcall *v6)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *); // rax

  if ( !LODWORD(this->Ptr) )
    return 0;
  v2 = this + 1;
  AcquireSRWLockExclusive(this + 1);
  v3 = this + 12;
  if ( this[12].Ptr )
  {
    Ptr_high = HIDWORD(this[3].Ptr);
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return Ptr_high;
  }
  v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_internalSubscribeFeatureStateChangeNotification;
  v3->Ptr = 0;
  if ( v6
    || (v6 = (void (__fastcall *)(RTL_SRWLOCK *, __int64 (__fastcall *)(void *), RTL_SRWLOCK *))g_wil_details_apiSubscribeFeatureStateChangeNotification) != 0 )
  {
    v6(this + 12, _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_, this);
  }
  if ( !v3->Ptr )
  {
    if ( v2 )
      ReleaseSRWLockExclusive(v2);
    return 0;
  }
  HIDWORD(this[3].Ptr) = 1;
  if ( v2 )
    ReleaseSRWLockExclusive(v2);
  return 1;
}

```

## disassembly

```asm
0x1800149e4  mov     [rsp+arg_0], rbx
0x1800149e9  mov     [rsp+arg_8], rsi
0x1800149ee  push    rdi
0x1800149ef  sub     rsp, 20h
0x1800149f3  mov     eax, [rcx]
0x1800149f5  mov     rdi, rcx
0x1800149f8  test    eax, eax
0x1800149fa  jz      short loc_180014A6E
0x1800149fc  lea     rbx, [rcx+8]
0x180014a00  mov     rcx, rbx; SRWLock
0x180014a03  call    cs:__imp_AcquireSRWLockExclusive
0x180014a09  lea     rsi, [rdi+60h]
0x180014a0d  cmp     qword ptr [rsi], 0
0x180014a11  jz      short loc_180014A29
0x180014a13  mov     edi, [rdi+1Ch]
0x180014a16  nop
0x180014a17  test    rbx, rbx
0x180014a1a  jz      short loc_180014A25
0x180014a1c  mov     rcx, rbx; SRWLock
0x180014a1f  call    cs:__imp_ReleaseSRWLockExclusive
0x180014a25  mov     eax, edi
0x180014a27  jmp     short loc_180014A70
0x180014a29  mov     rax, cs:g_wil_details_internalSubscribeFeatureStateChangeNotification
0x180014a30  mov     qword ptr [rsi], 0
0x180014a37  test    rax, rax
0x180014a3a  jnz     short loc_180014A48
0x180014a3c  mov     rax, cs:g_wil_details_apiSubscribeFeatureStateChangeNotification
0x180014a43  test    rax, rax
0x180014a46  jz      short loc_180014A5A
0x180014a48  mov     r8, rdi
0x180014a4b  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_fee8cea507d2413a58be13acfb66740a_@@CA@PEAX@Z; _lambda_fee8cea507d2413a58be13acfb66740a_::_lambda_invoker_cdecl_(void *)
0x180014a52  mov     rcx, rsi
0x180014a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a5a  cmp     qword ptr [rsi], 0
0x180014a5e  jnz     short loc_180014A80
0x180014a60  test    rbx, rbx
0x180014a63  jz      short loc_180014A6E
0x180014a65  mov     rcx, rbx; SRWLock
0x180014a68  call    cs:__imp_ReleaseSRWLockExclusive
0x180014a6e  xor     eax, eax
0x180014a70  mov     rbx, [rsp+28h+arg_0]
0x180014a75  mov     rsi, [rsp+28h+arg_8]
0x180014a7a  add     rsp, 20h
0x180014a7e  pop     rdi
0x180014a7f  retn
0x180014a80  mov     esi, 1
0x180014a85  nop
0x180014a86  mov     [rdi+1Ch], esi
0x180014a89  test    rbx, rbx
0x180014a8c  jz      short loc_180014A97
0x180014a8e  mov     rcx, rbx; SRWLock
0x180014a91  call    cs:__imp_ReleaseSRWLockExclusive
0x180014a97  mov     eax, esi
0x180014a99  jmp     short loc_180014A70
```
