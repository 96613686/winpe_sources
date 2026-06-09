# ATL::CRegParser::SkipWhiteSpace(void)

- ea: `0x180008084`
- end: `0x1800080b8`
- name: `?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(ATL::CRegParser *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180005e28`
- `0x180006f50`
- `0x1800074dc`
- `0x180007ff0`

## callees

- `0x180008084`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080a7`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1800080a7`

## pseudocode

```c
void __fastcall ATL::CRegParser::SkipWhiteSpace(LPCWSTR *this)
{
  while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
    *this = CharNextW(*this);
}

```

## disassembly

```asm
0x180008084  push    rbx
0x180008086  sub     rsp, 20h
0x18000808a  mov     rbx, rcx
0x18000808d  mov     rcx, [rbx]; lpsz
0x180008090  movzx   edx, word ptr [rcx]
0x180008093  sub     edx, 9
0x180008096  jz      short loc_1800080A7
0x180008098  sub     edx, 1
0x18000809b  jz      short loc_1800080A7
0x18000809d  sub     edx, 3
0x1800080a0  jz      short loc_1800080A7
0x1800080a2  cmp     edx, 13h
0x1800080a5  jnz     short loc_1800080B2
0x1800080a7  call    cs:__imp_CharNextW
0x1800080ad  mov     [rbx], rax
0x1800080b0  jmp     short loc_18000808D
0x1800080b2  add     rsp, 20h
0x1800080b6  pop     rbx
0x1800080b7  retn
```
