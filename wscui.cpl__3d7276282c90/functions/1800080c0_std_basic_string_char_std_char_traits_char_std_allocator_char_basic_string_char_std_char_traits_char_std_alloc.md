# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::basic_string<char,std::char_traits<char>,std::allocator<char>>(char const *)

- ea: `0x1800080c0`
- end: `0x1800080ea`
- name: `??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@PEBD@Z`
- size: `42`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180008810`
- `0x180008850`
- `0x180008890`

## callees

- `0x180008560`

## pseudocode

```c
_QWORD *__fastcall std::string::string(_QWORD *a1, void *a2)
{
  a1[3] = 15;
  a1[2] = 0;
  *(_BYTE *)a1 = 0;
  std::string::assign(a1, a2);
  return a1;
}

```

## disassembly

```asm
0x1800080c0  push    rbx
0x1800080c2  sub     rsp, 20h
0x1800080c6  mov     qword ptr [rcx+18h], 0Fh
0x1800080ce  mov     rbx, rcx
0x1800080d1  mov     qword ptr [rcx+10h], 0
0x1800080d9  mov     byte ptr [rcx], 0
0x1800080dc  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD@Z; std::string::assign(char const *)
0x1800080e1  mov     rax, rbx
0x1800080e4  add     rsp, 20h
0x1800080e8  pop     rbx
0x1800080e9  retn
```
