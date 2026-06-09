# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180007b44`
- end: `0x180007b5b`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `16`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180006cc0`
- `0x180006d30`
- `0x180008438`
- `0x1800084ec`
- `0x180008588`
- `0x180009dbc`
- `0x180009e88`
- `0x180009fb8`
- `0x18000a0a4`
- `0x18000a434`
- `0x18000a4dc`
- `0x18000a65c`
- `0x18000b21c`
- `0x18000b2b0`
- `0x18000b348`
- `0x18000b740`

## callees

- `0x180007b44`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b50`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007b50`

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
0x180007b44  sub     rsp, 28h
0x180007b48  mov     rcx, [rcx]; SRWLock
0x180007b4b  test    rcx, rcx
0x180007b4e  jz      short loc_180007B56
0x180007b50  call    cs:__imp_ReleaseSRWLockExclusive
0x180007b56  add     rsp, 28h
0x180007b5a  retn
```
