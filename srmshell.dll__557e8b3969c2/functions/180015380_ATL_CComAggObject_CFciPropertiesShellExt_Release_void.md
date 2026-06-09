# ATL::CComAggObject<CFciPropertiesShellExt>::Release(void)

- ea: `0x180015380`
- end: `0x1800153f5`
- name: `?Release@?$CComAggObject@VCFciPropertiesShellExt@@@ATL@@UEAAKXZ`
- size: `117`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015380`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComAggObject<CFciPropertiesShellExt>::Release(_DWORD *a1)
{
  int v2; // ebx
  unsigned int v3; // ebx

  v2 = a1[2];
  if ( v2 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v2 - 1;
    a1[2] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180015380  mov     [rsp+arg_0], rbx
0x180015385  push    rdi
0x180015386  sub     rsp, 30h
0x18001538a  mov     rdi, rcx
0x18001538d  mov     ebx, [rcx+8]
0x180015390  cmp     ebx, 7FFFFFFFh
0x180015396  jnz     short loc_18001539F
0x180015398  mov     ebx, 7FFFFFFEh
0x18001539d  jmp     short loc_1800153E8
0x18001539f  sub     ebx, 1
0x1800153a2  mov     [rcx+8], ebx
0x1800153a5  jnz     short loc_1800153E8
0x1800153a7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800153ae  mov     rax, [rcx]
0x1800153b1  mov     rax, [rax+8]
0x1800153b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153ba  nop
0x1800153bb  test    rdi, rdi
0x1800153be  jz      short loc_1800153D5
0x1800153c0  mov     rax, [rdi]
0x1800153c3  mov     edx, 1
0x1800153c8  mov     rcx, rdi
0x1800153cb  mov     rax, [rax+18h]
0x1800153cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153d4  nop
0x1800153d5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800153dc  mov     rdx, [rcx]
0x1800153df  mov     rax, [rdx+10h]
0x1800153e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800153e8  mov     eax, ebx
0x1800153ea  mov     rbx, [rsp+38h+arg_0]
0x1800153ef  add     rsp, 30h
0x1800153f3  pop     rdi
0x1800153f4  retn
```
