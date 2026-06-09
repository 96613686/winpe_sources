# ATL::CAtlModule::Term(void)

- ea: `0x180001fc0`
- end: `0x180002026`
- name: `?Term@CAtlModule@ATL@@QEAAXXZ`
- size: `102`
- prototype: `void __fastcall(ATL::CAtlModule *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003640`
- `0x1800059d0`
- `0x18000818c`

## callees

- `0x180001fc0`
- `0x1800063a0`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000200f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000200f`

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
0x180001fc0  mov     [rsp+arg_0], rbx
0x180001fc5  push    rdi
0x180001fc6  sub     rsp, 20h
0x180001fca  mov     rbx, rcx
0x180001fcd  lea     rdi, [rcx+8]
0x180001fd1  cmp     dword ptr [rdi], 0
0x180001fd4  jz      short loc_18000201B
0x180001fd6  cmp     qword ptr [rcx+10h], 0
0x180001fdb  jz      short loc_180001FF6
0x180001fdd  mov     rax, rcx
0x180001fe0  neg     rax
0x180001fe3  sbb     rcx, rcx
0x180001fe6  and     rcx, rdi; struct ATL::_ATL_MODULE70 *
0x180001fe9  call    ?AtlCallTermFunc@ATL@@YAXPEAU_ATL_MODULE70@1@@Z; ATL::AtlCallTermFunc(ATL::_ATL_MODULE70 *)
0x180001fee  mov     qword ptr [rbx+10h], 0
0x180001ff6  mov     rcx, [rbx+40h]
0x180001ffa  test    rcx, rcx
0x180001ffd  jz      short loc_18000200B
0x180001fff  mov     rax, [rcx]
0x180002002  mov     rax, [rax+10h]
0x180002006  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000200b  lea     rcx, [rbx+18h]; lpCriticalSection
0x18000200f  call    cs:__imp_DeleteCriticalSection
0x180002015  mov     dword ptr [rdi], 0
0x18000201b  mov     rbx, [rsp+28h+arg_0]
0x180002020  add     rsp, 20h
0x180002024  pop     rdi
0x180002025  retn
```
