# ATL::CAtlModule::Term(void)

- ea: `0x180010340`
- end: `0x1800103b0`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `112`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18000da20`
- `0x180015da0`
- `0x1800309a0`

## callees

- `0x180010340`
- `0x180016894`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010399`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010399`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v2; // rdi
  __int64 v3; // rcx

  v2 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v2 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v2 = 0;
  }
}

```

## disassembly

```asm
0x180010340  push    rdi
0x180010342  sub     rsp, 30h
0x180010346  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x18001034f  mov     [rsp+38h+arg_0], rbx
0x180010354  mov     rbx, rcx
0x180010357  lea     rdi, [rcx+8]
0x18001035b  cmp     dword ptr [rdi], 0
0x18001035e  jz      short loc_1800103A5
0x180010360  cmp     qword ptr [rcx+10h], 0
0x180010365  jz      short loc_180010380
0x180010367  mov     rax, rcx
0x18001036a  neg     rax
0x18001036d  sbb     rcx, rcx
0x180010370  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180010373  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180010378  mov     qword ptr [rbx+10h], 0
0x180010380  mov     rcx, [rbx+40h]
0x180010384  test    rcx, rcx
0x180010387  jz      short loc_180010395
0x180010389  mov     rax, [rcx]
0x18001038c  mov     rax, [rax+10h]
0x180010390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010395  lea     rcx, [rbx+18h]; lpCriticalSection
0x180010399  call    cs:__imp_DeleteCriticalSection
0x18001039f  mov     dword ptr [rdi], 0
0x1800103a5  mov     rbx, [rsp+38h+arg_0]
0x1800103aa  add     rsp, 30h
0x1800103ae  pop     rdi
0x1800103af  retn
```
