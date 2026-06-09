# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180019940`
- end: `0x180019a03`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `195`
- prototype: ``
- caller_count: `9`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180015630`
- `0x180019920`
- `0x180027444`
- `0x18002752c`
- `0x180027614`
- `0x180029aac`
- `0x180029b98`
- `0x180029c84`
- `0x18002c24c`

## callees

- `0x180002aa0`
- `0x180019940`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800199ef`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800199ef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019972`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019972`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rdi
  unsigned int v9; // eax
  _DWORD v10[2]; // [rsp+28h] [rbp-50h] BYREF
  volatile signed __int32 *v11; // [rsp+30h] [rbp-48h]

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v10[1] = 0,
          v10[0] = a3,
          v11 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v10, 0x10u)) )
    {
      v9 = -2111;
      if ( a3 )
        v9 = -5;
      _InterlockedAnd(a2, v9);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x180019940  push    rbx
0x180019942  push    rbp
0x180019943  push    rsi
0x180019944  push    rdi
0x180019945  push    r14
0x180019947  push    r15
0x180019949  sub     rsp, 48h
0x18001994d  mov     ebp, r9d
0x180019950  mov     r15d, r8d
0x180019953  mov     rsi, rdx
0x180019956  mov     r14, rcx
0x180019959  mov     [rsp+78h+var_58], 0
0x180019961  mov     eax, [rcx]
0x180019963  test    eax, eax
0x180019965  jz      loc_1800199F6
0x18001996b  lea     rdi, [rcx+8]
0x18001996f  mov     rcx, rdi; SRWLock
0x180019972  call    cs:__imp_AcquireSRWLockExclusive
0x180019978  mov     [rsp+78h+arg_0], rdi
0x180019980  mov     ebx, 2
0x180019985  mov     [rsp+78h+var_58], ebx
0x180019989  and     ebx, 0FFFFFFFDh
0x18001998c  mov     [rsp+78h+var_58], ebx
0x180019990  or      ebx, 1
0x180019993  mov     [rsp+78h+var_58], ebx
0x180019997  mov     eax, [r14+1Ch]
0x18001999b  test    ebp, ebp
0x18001999d  jz      short loc_1800199CD
0x18001999f  cmp     ebp, eax
0x1800199a1  jnz     short loc_1800199CD
0x1800199a3  mov     [rsp+78h+var_4C], 0
0x1800199ab  mov     [rsp+78h+var_50], r15d
0x1800199b0  mov     [rsp+78h+var_48], rsi
0x1800199b5  lea     rcx, [r14+40h]; this
0x1800199b9  mov     r8d, 10h; unsigned __int64
0x1800199bf  lea     rdx, [rsp+78h+var_50]; void *
0x1800199c4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800199c9  test    al, al
0x1800199cb  jnz     short loc_1800199E0
0x1800199cd  mov     eax, 0FFFFF7C1h
0x1800199d2  mov     ecx, 0FFFFFFFBh
0x1800199d7  test    r15d, r15d
0x1800199da  cmovnz  eax, ecx
0x1800199dd  lock and [rsi], eax
0x1800199e0  and     ebx, 0FFFFFFFEh
0x1800199e3  mov     [rsp+78h+var_58], ebx
0x1800199e7  test    rdi, rdi
0x1800199ea  jz      short loc_1800199F6
0x1800199ec  mov     rcx, rdi; SRWLock
0x1800199ef  call    cs:__imp_ReleaseSRWLockExclusive
0x1800199f5  nop
0x1800199f6  add     rsp, 48h
0x1800199fa  pop     r15
0x1800199fc  pop     r14
0x1800199fe  pop     rdi
0x1800199ff  pop     rsi
0x180019a00  pop     rbp
0x180019a01  pop     rbx
0x180019a02  retn
```
