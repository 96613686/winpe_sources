# ATL::_dynamic_atexit_destructor_for___AtlComModule__

- ea: `0x180031890`
- end: `0x180031920`
- name: `ATL::_dynamic_atexit_destructor_for___AtlComModule__`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180003890`
- `0x180031890`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800318fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800318fb`

## pseudocode

```c
__int64 ATL::_dynamic_atexit_destructor_for___AtlComModule__()
{
  __int64 *v0; // rax
  __int64 *i; // rbx
  __int64 v2; // rdi
  __int64 v3; // rcx

  if ( ATL::_AtlComModule )
  {
    v0 = off_180041528;
    for ( i = off_180041520[0]; i < v0; ++i )
    {
      v2 = *i;
      if ( *i )
      {
        v3 = *(_QWORD *)(v2 + 32);
        if ( v3 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
        *(_QWORD *)(v2 + 32) = 0;
        v0 = off_180041528;
      }
    }
    DeleteCriticalSection(&stru_180041530);
    ATL::_AtlComModule = 0;
  }
  return wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::destroy(&ATL::_AtlComModule);
}

```

## disassembly

```asm
0x180031890  sub     rsp, 28h
0x180031894  cmp     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x18003189b  jz      short loc_180031910
0x18003189d  mov     rax, cs:off_180041528
0x1800318a4  mov     [rsp+28h+arg_0], rbx
0x1800318a9  mov     rbx, cs:off_180041520
0x1800318b0  cmp     rbx, rax
0x1800318b3  jnb     short loc_1800318F4
0x1800318b5  mov     [rsp+28h+var_8], rdi
0x1800318ba  mov     rdi, [rbx]
0x1800318bd  test    rdi, rdi
0x1800318c0  jz      short loc_1800318E6
0x1800318c2  mov     rcx, [rdi+20h]
0x1800318c6  test    rcx, rcx
0x1800318c9  jz      short loc_1800318D7
0x1800318cb  mov     rax, [rcx]
0x1800318ce  mov     rax, [rax+10h]
0x1800318d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800318d7  mov     qword ptr [rdi+20h], 0
0x1800318df  mov     rax, cs:off_180041528
0x1800318e6  add     rbx, 8
0x1800318ea  cmp     rbx, rax
0x1800318ed  jb      short loc_1800318BA
0x1800318ef  mov     rdi, [rsp+28h+var_8]
0x1800318f4  lea     rcx, stru_180041530; lpCriticalSection
0x1800318fb  call    cs:__imp_DeleteCriticalSection
0x180031901  mov     rbx, [rsp+28h+arg_0]
0x180031906  mov     cs:?_AtlComModule@ATL@@3VCAtlComModule@1@A, 0; ATL::CAtlComModule ATL::_AtlComModule
0x180031910  lea     rcx, ?_AtlComModule@ATL@@3VCAtlComModule@1@A; ATL::CAtlComModule ATL::_AtlComModule
0x180031917  add     rsp, 28h
0x18003191b  jmp     ?destroy@?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@UEAAXXZ; wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::destroy(void)
```
