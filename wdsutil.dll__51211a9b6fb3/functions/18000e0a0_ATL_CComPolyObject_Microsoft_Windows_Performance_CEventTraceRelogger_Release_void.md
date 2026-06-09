# ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(void)

- ea: `0x18000e0a0`
- end: `0x18000e114`
- name: `?Release@?$CComPolyObject@VCEventTraceRelogger@Performance@Windows@Microsoft@@@ATL@@UEAAKXZ`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000e0a0`
- `0x180034010`

## pseudocode

```c
__int64 __fastcall ATL::CComPolyObject<Microsoft::Windows::Performance::CEventTraceRelogger>::Release(_DWORD *a1)
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
        (*(void (__fastcall **)(_DWORD *, __int64))(*(_QWORD *)a1 + 24LL))(a1, 1);
      (*(void (__fastcall **)(struct ATL::CAtlModule *))(*(_QWORD *)ATL::_pAtlModule + 16LL))(ATL::_pAtlModule);
    }
  }
  return v3;
}

```

## disassembly

```asm
0x18000e0a0  mov     [rsp+arg_0], rbx
0x18000e0a5  push    rdi
0x18000e0a6  sub     rsp, 20h
0x18000e0aa  mov     ebx, [rcx+8]
0x18000e0ad  mov     rdi, rcx
0x18000e0b0  cmp     ebx, 7FFFFFFFh
0x18000e0b6  jnz     short loc_18000E0BF
0x18000e0b8  mov     ebx, 7FFFFFFEh
0x18000e0bd  jmp     short loc_18000E106
0x18000e0bf  sub     ebx, 1
0x18000e0c2  mov     [rcx+8], ebx
0x18000e0c5  jnz     short loc_18000E106
0x18000e0c7  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e0ce  mov     rax, [rcx]
0x18000e0d1  mov     rax, [rax+8]
0x18000e0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0da  test    rdi, rdi
0x18000e0dd  jz      short loc_18000E0F3
0x18000e0df  mov     rax, [rdi]
0x18000e0e2  mov     edx, 1
0x18000e0e7  mov     rcx, rdi
0x18000e0ea  mov     rax, [rax+18h]
0x18000e0ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0f3  mov     rcx, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x18000e0fa  mov     rdx, [rcx]
0x18000e0fd  mov     rax, [rdx+10h]
0x18000e101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e106  mov     eax, ebx
0x18000e108  mov     rbx, [rsp+28h+arg_0]
0x18000e10d  add     rsp, 20h
0x18000e111  pop     rdi
0x18000e112  retn
```
