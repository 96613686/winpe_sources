# sub_18002BFFA

- ea: `0x18002bffa`
- end: `0x18002c030`
- name: `sub_18002BFFA`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800271d0`

## string_xrefs

- `0x18002c00b`: `onecore\amcore\webdefense\services\webthreatdefusersvc\servicemain.cpp`

## pseudocode

```c
__int64 __fastcall sub_18002BFFA(__int64 a1, __int64 a2)
{
  *(_DWORD *)(a2 + 64) = sub_1800271D0(
                           *(_QWORD *)(a2 + 56),
                           183,
                           (int)"onecore\\amcore\\webdefense\\services\\webthreatdefusersvc\\servicemain.cpp");
  return 0;
}

```

## disassembly

```asm
0x18002bffa  mov     [rsp+arg_8], rdx
0x18002bfff  push    rbp
0x18002c000  sub     rsp, 30h
0x18002c004  mov     rbp, rdx
0x18002c007  mov     rcx, [rbp+38h]
0x18002c00b  lea     r8, aOnecoreAmcoreW_5; "onecore\\amcore\\webdefense\\services\\"...
0x18002c012  mov     edx, 0B7h
0x18002c017  call    sub_1800271D0
0x18002c01c  mov     [rbp+40h], eax
0x18002c01f  mov     rax, 0
0x18002c029  add     rsp, 30h
0x18002c02d  pop     rbp
0x18002c02e  retn
```
