# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x1800047ac`
- end: `0x1800047ca`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `21`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180004890`
- `0x180006890`
- `0x180007ea0`
- `0x180007f58`
- `0x180007ffc`
- `0x1800082f0`
- `0x180008438`
- `0x180008580`
- `0x1800086c8`
- `0x180009bb4`
- `0x180009c8c`
- `0x180009d20`
- `0x180009d7c`
- `0x180009f20`
- `0x180009fc4`
- `0x18000a354`
- `0x18000a570`
- `0x18000b894`
- `0x18000b93c`
- `0x18000bd5c`
- `0x18000bf50`

## callees

- `0x1800047ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800047b8`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
        RTL_SRWLOCK **a1)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x1800047ac  sub     rsp, 28h
0x1800047b0  mov     rcx, [rcx]; SRWLock
0x1800047b3  test    rcx, rcx
0x1800047b6  jz      short loc_1800047C4
0x1800047b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1800047bf  nop     dword ptr [rax+rax+00h]
0x1800047c4  add     rsp, 28h
0x1800047c8  retn
```
