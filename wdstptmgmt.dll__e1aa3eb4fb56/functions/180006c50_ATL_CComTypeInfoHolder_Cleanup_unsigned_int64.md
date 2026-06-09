# ATL::CComTypeInfoHolder::Cleanup(unsigned __int64)

- ea: `0x180006c50`
- end: `0x180006cbe`
- name: `?Cleanup@CComTypeInfoHolder@ATL@@SAX_K@Z`
- size: `110`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002024`
- `0x180006c50`
- `0x180020010`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180006ca0`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180006ca0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall ATL::CComTypeInfoHolder::Cleanup(__int64 a1)
{
  __int64 v2; // rcx
  char *v3; // rcx
  char *v4; // rbx

  if ( a1 )
  {
    v2 = *(_QWORD *)(a1 + 24);
    if ( v2 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
    *(_QWORD *)(a1 + 24) = 0;
    v3 = *(char **)(a1 + 40);
    if ( v3 )
    {
      v4 = v3 - 8;
      `eh vector destructor iterator'(v3, 0x10u, *((_QWORD *)v3 - 1), (void (*)(void *))ATL::CComBSTR::~CComBSTR);
      operator delete[](v4);
    }
    *(_QWORD *)(a1 + 40) = 0;
  }
}

```

## disassembly

```asm
0x180006c50  test    rcx, rcx
0x180006c53  jz      short locret_180006CBC
0x180006c55  mov     [rsp+arg_0], rbx
0x180006c5a  push    rdi
0x180006c5b  sub     rsp, 20h
0x180006c5f  mov     rdi, rcx
0x180006c62  mov     rcx, [rcx+18h]
0x180006c66  test    rcx, rcx
0x180006c69  jz      short loc_180006C77
0x180006c6b  mov     rax, [rcx]
0x180006c6e  mov     rax, [rax+10h]
0x180006c72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c77  and     qword ptr [rdi+18h], 0
0x180006c7c  mov     rcx, [rdi+28h]; void *
0x180006c80  test    rcx, rcx
0x180006c83  jz      short loc_180006CAD
0x180006c85  lea     rbx, [rcx-8]
0x180006c89  lea     r9, ??1CComBSTR@ATL@@QEAA@XZ; void (*)(void *)
0x180006c90  mov     r8, [rbx]; unsigned __int64
0x180006c93  mov     edx, 10h; unsigned __int64
0x180006c98  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x180006c9d  mov     rcx, rbx
0x180006ca0  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180006ca7  nop     dword ptr [rax+rax+00h]
0x180006cac  nop
0x180006cad  and     qword ptr [rdi+28h], 0
0x180006cb2  mov     rbx, [rsp+28h+arg_0]
0x180006cb7  add     rsp, 20h
0x180006cbb  pop     rdi
0x180006cbc  retn
```
