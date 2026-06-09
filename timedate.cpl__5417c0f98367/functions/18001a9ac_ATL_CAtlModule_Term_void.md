# ATL::CAtlModule::Term(void)

- ea: `0x18001a9ac`
- end: `0x18001aa12`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x1800181d0`
- `0x18001aa18`
- `0x180029880`

## callees

- `0x1800189a4`
- `0x18001a9ac`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a9fb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001a9fb`

## pseudocode

```c
void __fastcall ATL::CAtlModule::Term(ATL::CAtlModule *this)
{
  unsigned __int64 v1; // rdi
  __int64 v3; // rcx

  v1 = (unsigned __int64)this + 8;
  if ( *((_DWORD *)this + 2) )
  {
    if ( *((_QWORD *)this + 2) )
    {
      ATL::AtlCallTermFunc((struct ATL::_ATL_MODULE70 *)(v1 & -(__int64)(this != 0)));
      *((_QWORD *)this + 2) = 0;
    }
    v3 = *((_QWORD *)this + 8);
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
    *(_DWORD *)v1 = 0;
  }
}

```

## disassembly

```asm
0x18001a9ac  mov     [rsp+arg_0], rbx
0x18001a9b1  push    rdi
0x18001a9b2  sub     rsp, 20h
0x18001a9b6  lea     rdi, [rcx+8]
0x18001a9ba  mov     rbx, rcx
0x18001a9bd  cmp     dword ptr [rdi], 0
0x18001a9c0  jz      short loc_18001AA07
0x18001a9c2  cmp     qword ptr [rcx+10h], 0
0x18001a9c7  jz      short loc_18001A9E2
0x18001a9c9  mov     rax, rcx
0x18001a9cc  neg     rax
0x18001a9cf  sbb     rcx, rcx
0x18001a9d2  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x18001a9d5  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x18001a9da  mov     qword ptr [rbx+10h], 0
0x18001a9e2  mov     rcx, [rbx+40h]
0x18001a9e6  test    rcx, rcx
0x18001a9e9  jz      short loc_18001A9F7
0x18001a9eb  mov     rax, [rcx]
0x18001a9ee  mov     rax, [rax+10h]
0x18001a9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a9f7  lea     rcx, [rbx+18h]; lpCriticalSection
0x18001a9fb  call    cs:__imp_DeleteCriticalSection
0x18001aa01  mov     dword ptr [rdi], 0
0x18001aa07  mov     rbx, [rsp+28h+arg_0]
0x18001aa0c  add     rsp, 20h
0x18001aa10  pop     rdi
0x18001aa11  retn
```
