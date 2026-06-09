# ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(void)

- ea: `0x18002eae0`
- end: `0x18002eb57`
- name: `?Release@?$CComObject@VCElfImageEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18002eae0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComObject<Microsoft::Windows::Performance::CElfImageEventTraceExtender>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 160LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18002eae0  mov     [rsp+arg_0], rbx
0x18002eae5  push    rdi
0x18002eae6  sub     rsp, 20h
0x18002eaea  mov     ebx, [rcx+18h]
0x18002eaed  mov     rdi, rcx
0x18002eaf0  cmp     ebx, 7FFFFFFFh
0x18002eaf6  jnz     short loc_18002EAFF
0x18002eaf8  mov     ebx, 7FFFFFFEh
0x18002eafd  jmp     short loc_18002EB49
0x18002eaff  sub     ebx, 1
0x18002eb02  mov     [rcx+18h], ebx
0x18002eb05  jnz     short loc_18002EB49
0x18002eb07  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002eb0e  mov     rax, [rcx]
0x18002eb11  mov     rax, [rax+8]
0x18002eb15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb1a  test    rdi, rdi
0x18002eb1d  jz      short loc_18002EB36
0x18002eb1f  mov     rax, [rdi]
0x18002eb22  mov     edx, 1
0x18002eb27  mov     rcx, rdi
0x18002eb2a  mov     rax, [rax+0A0h]
0x18002eb31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb36  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18002eb3d  mov     rdx, [rcx]
0x18002eb40  mov     rax, [rdx+10h]
0x18002eb44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002eb49  mov     eax, ebx
0x18002eb4b  mov     rbx, [rsp+28h+arg_0]
0x18002eb50  add     rsp, 20h
0x18002eb54  pop     rdi
0x18002eb55  retn
```
