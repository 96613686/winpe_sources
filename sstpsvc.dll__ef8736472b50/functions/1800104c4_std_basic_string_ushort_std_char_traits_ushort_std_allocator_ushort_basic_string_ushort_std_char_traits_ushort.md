# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x1800104c4`
- end: `0x1800104ed`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z`
- size: `41`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18001004c`
- `0x1800100f4`
- `0x180010288`
- `0x180010b08`
- `0x180013fe0`

## callees

- `0x180013588`

## pseudocode

```c
_QWORD *__fastcall std::wstring::wstring(_QWORD *a1, void *a2)
{
  a1[3] = 7;
  a1[2] = 0;
  *(_WORD *)a1 = 0;
  std::wstring::assign(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x1800104c4  push    rbx
0x1800104c6  sub     rsp, 20h
0x1800104ca  xor     eax, eax
0x1800104cc  mov     qword ptr [rcx+18h], 7
0x1800104d4  mov     [rcx+10h], rax
0x1800104d8  mov     rbx, rcx
0x1800104db  mov     [rcx], ax
0x1800104de  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x1800104e3  mov     rax, rbx
0x1800104e6  add     rsp, 20h
0x1800104ea  pop     rbx
0x1800104eb  retn
```
