# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18002e220`
- end: `0x18002e2b9`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006f90`
- `0x180027220`
- `0x18002d110`
- `0x1800315e0`
- `0x1800346e4`

## callees

- `0x180022240`
- `0x180028b1c`
- `0x18002e220`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e24b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002e24b`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  int v9; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v11; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v9 = *(_DWORD *)(a1 + 28);
    v12 = v8;
    if ( !a4
      || a4 != v9
      || (Source[1] = 0,
          Source[0] = a3,
          v11 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), Source, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x18002e220  mov     [rsp+arg_8], rbx
0x18002e225  mov     [rsp+arg_10], rbp
0x18002e22a  push    rsi
0x18002e22b  push    rdi
0x18002e22c  push    r14
0x18002e22e  sub     rsp, 30h
0x18002e232  mov     eax, [rcx]
0x18002e234  mov     ebp, r9d
0x18002e237  mov     edi, r8d
0x18002e23a  mov     rsi, rdx
0x18002e23d  mov     r14, rcx
0x18002e240  test    eax, eax
0x18002e242  jz      short loc_18002E2A6
0x18002e244  lea     rbx, [rcx+8]
0x18002e248  mov     rcx, rbx; SRWLock
0x18002e24b  call    cs:__imp_AcquireSRWLockExclusive
0x18002e251  mov     eax, [r14+1Ch]
0x18002e255  mov     [rsp+48h+arg_0], rbx
0x18002e25a  test    ebp, ebp
0x18002e25c  jz      short loc_18002E28B
0x18002e25e  cmp     ebp, eax
0x18002e260  jnz     short loc_18002E28B
0x18002e262  lea     rcx, [r14+40h]; this
0x18002e266  mov     [rsp+48h+var_24], 0
0x18002e26e  mov     r8d, 10h; SourceSize
0x18002e274  mov     [rsp+48h+Source], edi
0x18002e278  lea     rdx, [rsp+48h+Source]; Source
0x18002e27d  mov     [rsp+48h+var_20], rsi
0x18002e282  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002e287  test    al, al
0x18002e289  jnz     short loc_18002E29C
0x18002e28b  neg     edi
0x18002e28d  sbb     eax, eax
0x18002e28f  and     eax, 83Ah
0x18002e294  add     eax, 0FFFFF7C1h
0x18002e299  lock and [rsi], eax
0x18002e29c  lea     rcx, [rsp+48h+arg_0]
0x18002e2a1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002e2a6  mov     rbx, [rsp+48h+arg_8]
0x18002e2ab  mov     rbp, [rsp+48h+arg_10]
0x18002e2b0  add     rsp, 30h
0x18002e2b4  pop     r14
0x18002e2b6  pop     rdi
0x18002e2b7  pop     rsi
0x18002e2b8  retn
```
