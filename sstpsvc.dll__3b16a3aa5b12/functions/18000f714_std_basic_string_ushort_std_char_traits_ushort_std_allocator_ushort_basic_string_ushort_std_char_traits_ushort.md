# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &&)

- ea: `0x18000f714`
- end: `0x18000f73c`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z`
- size: `40`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f2ac`
- `0x18000f34c`
- `0x18000f4dc`
- `0x18000fd1c`
- `0x180013000`

## callees

- `0x1800125bc`

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
0x18000f714  push    rbx
0x18000f716  sub     rsp, 20h
0x18000f71a  xor     eax, eax
0x18000f71c  mov     qword ptr [rcx+18h], 7
0x18000f724  mov     [rcx+10h], rax
0x18000f728  mov     rbx, rcx
0x18000f72b  mov     [rcx], ax
0x18000f72e  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@$$QEAV12@@Z; std::wstring::assign(std::wstring &&)
0x18000f733  mov     rax, rbx
0x18000f736  add     rsp, 20h
0x18000f73a  pop     rbx
0x18000f73b  retn
```
