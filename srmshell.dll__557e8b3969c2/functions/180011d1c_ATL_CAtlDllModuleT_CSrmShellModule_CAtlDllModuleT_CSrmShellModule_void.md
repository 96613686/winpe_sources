# ATL::CAtlDllModuleT<CSrmShellModule>::~CAtlDllModuleT<CSrmShellModule>(void)

- ea: `0x180011d1c`
- end: `0x180011d73`
- name: `??1?$CAtlDllModuleT@VCSrmShellModule@@@ATL@@UEAA@XZ`
- size: `87`
- prototype: `void __fastcall(ATL::CAtlModule *this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18001e5b4`
- `0x18001e5c6`

## callees

- `0x180011d1c`
- `0x180011ea0`
- `0x180020010`

## pseudocode

```c
void __fastcall ATL::CAtlDllModuleT<CSrmShellModule>::~CAtlDllModuleT<CSrmShellModule>(ATL::CAtlModule *this)
{
  struct ATL::_ATL_OBJMAP_ENTRY30 **v2; // rbx
  __int64 *v3; // rax

  v2 = off_18002B290;
  v3 = off_18002B298;
  while ( v2 < (struct ATL::_ATL_OBJMAP_ENTRY30 **)v3 )
  {
    if ( *v2 )
    {
      (*((void (__fastcall **)(_QWORD))*v2 + 8))(0);
      v3 = off_18002B298;
    }
    ++v2;
  }
  ATL::CAtlModule::~CAtlModule(this);
}

```

## disassembly

```asm
0x180011d1c  mov     [rsp+arg_8], rbx
0x180011d21  mov     [rsp+arg_0], rcx
0x180011d26  push    rdi
0x180011d27  sub     rsp, 20h
0x180011d2b  mov     rdi, rcx
0x180011d2e  mov     rbx, cs:off_18002B290
0x180011d35  mov     rax, cs:off_18002B298
0x180011d3c  jmp     short loc_180011D5C
0x180011d3e  mov     rdx, [rbx]
0x180011d41  test    rdx, rdx
0x180011d44  jz      short loc_180011D58
0x180011d46  xor     ecx, ecx
0x180011d48  mov     rax, [rdx+40h]
0x180011d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011d51  mov     rax, cs:off_18002B298
0x180011d58  add     rbx, 8
0x180011d5c  cmp     rbx, rax
0x180011d5f  jb      short loc_180011D3E
0x180011d61  mov     rcx, rdi; this
0x180011d64  mov     rbx, [rsp+28h+arg_8]
0x180011d69  add     rsp, 20h
0x180011d6d  pop     rdi
0x180011d6e  jmp     ??1CAtlModule@ATL@@UEAA@XZ; ATL::CAtlModule::~CAtlModule(void)
```
