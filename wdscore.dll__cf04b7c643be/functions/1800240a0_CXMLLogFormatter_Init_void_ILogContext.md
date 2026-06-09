# CXMLLogFormatter::Init(void *,ILogContext *)

- ea: `0x1800240a0`
- end: `0x180024104`
- name: `?Init@CXMLLogFormatter@@UEAA?AW4tagLOGRESULT@@PEAXPEAVILogContext@@@Z`
- size: `100`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x1800240a0`
- `0x18002410c`
- `0x18002a010`

## pseudocode

```c
__int64 __fastcall CXMLLogFormatter::Init(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v3; // ebx
  unsigned int v5; // esi
  wchar_t *v6; // rax

  v3 = 0;
  v5 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a3 + 56LL))(a3);
  while ( v3 < v5 )
  {
    v6 = (wchar_t *)(*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)a3 + 48LL))(a3, v3);
    if ( !(unsigned int)CXMLLogFormatter::IsLegalXMLName(v6) )
      return 0;
    ++v3;
  }
  return 1;
}

```

## disassembly

```asm
0x1800240a0  mov     [rsp+arg_0], rbx
0x1800240a5  mov     [rsp+arg_8], rsi
0x1800240aa  push    rdi
0x1800240ab  sub     rsp, 20h
0x1800240af  mov     rax, [r8]
0x1800240b2  xor     ebx, ebx
0x1800240b4  mov     rcx, r8
0x1800240b7  mov     rdi, r8
0x1800240ba  mov     rax, [rax+38h]
0x1800240be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240c3  mov     esi, eax
0x1800240c5  cmp     ebx, esi
0x1800240c7  jnb     short loc_1800240EE
0x1800240c9  mov     rcx, [rdi]
0x1800240cc  mov     edx, ebx
0x1800240ce  mov     rax, [rcx+30h]
0x1800240d2  mov     rcx, rdi
0x1800240d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800240da  mov     rcx, rax; String1
0x1800240dd  call    ?IsLegalXMLName@CXMLLogFormatter@@CAHPEBG@Z; CXMLLogFormatter::IsLegalXMLName(ushort const *)
0x1800240e2  test    eax, eax
0x1800240e4  jz      short loc_1800240EA
0x1800240e6  inc     ebx
0x1800240e8  jmp     short loc_1800240C5
0x1800240ea  xor     eax, eax
0x1800240ec  jmp     short loc_1800240F3
0x1800240ee  mov     eax, 1
0x1800240f3  mov     rbx, [rsp+28h+arg_0]
0x1800240f8  mov     rsi, [rsp+28h+arg_8]
0x1800240fd  add     rsp, 20h
0x180024101  pop     rdi
0x180024102  retn
```
