# ATL::CComObject<CWscAdmin>::Release(void)

- ea: `0x180003d10`
- end: `0x180003d83`
- name: `?Release@?$CComObject@VCWscAdmin@@@ATL@@UEAAKXZ`
- size: `115`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180003d10`
- `0x18000c010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CWscAdmin>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[2];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 40LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180003d10  mov     [rsp+arg_0], rbx
0x180003d15  push    rdi
0x180003d16  sub     rsp, 20h
0x180003d1a  mov     ebx, [rcx+8]
0x180003d1d  mov     rdi, rcx
0x180003d20  cmp     ebx, 7FFFFFFFh
0x180003d26  jnz     short loc_180003D2F
0x180003d28  mov     ebx, 7FFFFFFEh
0x180003d2d  jmp     short loc_180003D76
0x180003d2f  sub     ebx, 1
0x180003d32  mov     [rcx+8], ebx
0x180003d35  jnz     short loc_180003D76
0x180003d37  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d3e  mov     rax, [rcx]
0x180003d41  mov     rax, [rax+8]
0x180003d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d4a  test    rdi, rdi
0x180003d4d  jz      short loc_180003D63
0x180003d4f  mov     rax, [rdi]
0x180003d52  mov     edx, 1
0x180003d57  mov     rcx, rdi
0x180003d5a  mov     rax, [rax+28h]
0x180003d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d63  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180003d6a  mov     rdx, [rcx]
0x180003d6d  mov     rax, [rdx+10h]
0x180003d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003d76  mov     eax, ebx
0x180003d78  mov     rbx, [rsp+28h+arg_0]
0x180003d7d  add     rsp, 20h
0x180003d81  pop     rdi
0x180003d82  retn
```
