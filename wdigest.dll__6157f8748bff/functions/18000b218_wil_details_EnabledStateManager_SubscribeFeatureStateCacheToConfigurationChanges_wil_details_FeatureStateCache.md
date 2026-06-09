# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000b218`
- end: `0x18000b2a3`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `139`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18000ad50`
- `0x18000d700`

## callees

- `0x18000b218`
- `0x18000e5c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b23c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b23c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b292`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b292`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  _DWORD v9[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v10; // [rsp+28h] [rbp-30h]

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    if ( !a4
      || a4 != *(_DWORD *)(a1 + 28)
      || (v9[1] = 0,
          v9[0] = a3,
          v10 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v9, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    if ( v8 )
      ReleaseSRWLockExclusive(v8);
  }
}

```

## disassembly

```asm
0x18000b218  push    rbx
0x18000b21a  push    rbp
0x18000b21b  push    rsi
0x18000b21c  push    rdi
0x18000b21d  push    r14
0x18000b21f  sub     rsp, 30h
0x18000b223  mov     eax, [rcx]
0x18000b225  mov     r14d, r9d
0x18000b228  mov     esi, r8d
0x18000b22b  mov     rbp, rdx
0x18000b22e  mov     rdi, rcx
0x18000b231  test    eax, eax
0x18000b233  jz      short loc_18000B298
0x18000b235  lea     rbx, [rcx+8]
0x18000b239  mov     rcx, rbx; SRWLock
0x18000b23c  call    cs:__imp_AcquireSRWLockExclusive
0x18000b242  mov     eax, [rdi+1Ch]
0x18000b245  test    r14d, r14d
0x18000b248  jz      short loc_18000B278
0x18000b24a  cmp     r14d, eax
0x18000b24d  jnz     short loc_18000B278
0x18000b24f  lea     rcx, [rdi+40h]; this
0x18000b253  mov     [rsp+58h+var_34], 0
0x18000b25b  mov     r8d, 10h; unsigned __int64
0x18000b261  mov     [rsp+58h+var_38], esi
0x18000b265  lea     rdx, [rsp+58h+var_38]; void *
0x18000b26a  mov     [rsp+58h+var_30], rbp
0x18000b26f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000b274  test    al, al
0x18000b276  jnz     short loc_18000B28A
0x18000b278  neg     esi
0x18000b27a  sbb     eax, eax
0x18000b27c  and     eax, 83Ah
0x18000b281  add     eax, 0FFFFF7C1h
0x18000b286  lock and [rbp+0], eax
0x18000b28a  test    rbx, rbx
0x18000b28d  jz      short loc_18000B298
0x18000b28f  mov     rcx, rbx; SRWLock
0x18000b292  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b298  add     rsp, 30h
0x18000b29c  pop     r14
0x18000b29e  pop     rdi
0x18000b29f  pop     rsi
0x18000b2a0  pop     rbp
0x18000b2a1  pop     rbx
0x18000b2a2  retn
```
