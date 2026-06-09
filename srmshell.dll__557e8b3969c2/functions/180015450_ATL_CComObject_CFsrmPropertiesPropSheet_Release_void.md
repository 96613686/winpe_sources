# ATL::CComObject<CFsrmPropertiesPropSheet>::Release(void)

- ea: `0x180015450`
- end: `0x1800154c5`
- name: `?Release@?$CComObject@VCFsrmPropertiesPropSheet@@@ATL@@UEAAKXZ`
- size: `117`
- prototype: `__int64 __fastcall(_DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180015450`
- `0x180020010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<CFsrmPropertiesPropSheet>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 32LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x180015450  mov     [rsp+arg_0], rbx
0x180015455  push    rdi
0x180015456  sub     rsp, 30h
0x18001545a  mov     rdi, rcx
0x18001545d  mov     ebx, [rcx+8]
0x180015460  cmp     ebx, 7FFFFFFFh
0x180015466  jnz     short loc_18001546F
0x180015468  mov     ebx, 7FFFFFFEh
0x18001546d  jmp     short loc_1800154B8
0x18001546f  sub     ebx, 1
0x180015472  mov     [rcx+8], ebx
0x180015475  jnz     short loc_1800154B8
0x180015477  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18001547e  mov     rax, [rcx]
0x180015481  mov     rax, [rax+8]
0x180015485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001548a  nop
0x18001548b  test    rdi, rdi
0x18001548e  jz      short loc_1800154A5
0x180015490  mov     rax, [rdi]
0x180015493  mov     edx, 1
0x180015498  mov     rcx, rdi
0x18001549b  mov     rax, [rax+20h]
0x18001549f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154a4  nop
0x1800154a5  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x1800154ac  mov     rdx, [rcx]
0x1800154af  mov     rax, [rdx+10h]
0x1800154b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800154b8  mov     eax, ebx
0x1800154ba  mov     rbx, [rsp+38h+arg_0]
0x1800154bf  add     rsp, 30h
0x1800154c3  pop     rdi
0x1800154c4  retn
```
