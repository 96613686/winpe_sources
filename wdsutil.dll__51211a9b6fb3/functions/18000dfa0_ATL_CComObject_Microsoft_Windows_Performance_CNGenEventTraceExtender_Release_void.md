# ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(void)

- ea: `0x18000dfa0`
- end: `0x18000e017`
- name: `?Release@?$CComObject@VCNGenEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000dfa0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CNGenEventTraceExtender>::Release(_DWORD *a1)
{
  int v1; // ebx
  unsigned int v3; // ebx

  v1 = a1[6];
  if ( v1 == 0x7FFFFFFF )
  {
    return 2147483646;
  }
  else
  {
    v3 = v1 - 1;
    a1[6] = v3;
    if ( !v3 )
    {
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 8LL))(ATL::_pAtlModule);
      if ( a1 )
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 136LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000dfa0  mov     [rsp+arg_0], rbx
0x18000dfa5  push    rdi
0x18000dfa6  sub     rsp, 20h
0x18000dfaa  mov     ebx, [rcx+18h]
0x18000dfad  mov     rdi, rcx
0x18000dfb0  cmp     ebx, 7FFFFFFFh
0x18000dfb6  jnz     short loc_18000DFBF
0x18000dfb8  mov     ebx, 7FFFFFFEh
0x18000dfbd  jmp     short loc_18000E009
0x18000dfbf  sub     ebx, 1
0x18000dfc2  mov     [rcx+18h], ebx
0x18000dfc5  jnz     short loc_18000E009
0x18000dfc7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dfce  mov     rax, [rcx]
0x18000dfd1  mov     rax, [rax+8]
0x18000dfd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dfda  test    rdi, rdi
0x18000dfdd  jz      short loc_18000DFF6
0x18000dfdf  mov     rax, [rdi]
0x18000dfe2  mov     edx, 1
0x18000dfe7  mov     rcx, rdi
0x18000dfea  mov     rax, [rax+88h]
0x18000dff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dff6  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000dffd  mov     rdx, [rcx]
0x18000e000  mov     rax, [rdx+10h]
0x18000e004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e009  mov     eax, ebx
0x18000e00b  mov     rbx, [rsp+28h+arg_0]
0x18000e010  add     rsp, 20h
0x18000e014  pop     rdi
0x18000e015  retn
```
