# ATL::CRegParser::SkipWhiteSpace(void)

- ea: `0x180005ef0`
- end: `0x180005f24`
- name: `?SkipWhiteSpace@CRegParser@ATL@@IEAAXXZ`
- size: `52`
- prototype: `void __fastcall(ATL::CRegParser *__hidden this)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1800033ac`
- `0x180004b60`
- `0x18000527c`
- `0x180005e5c`

## callees

- `0x180005ef0`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005f13`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x180005f13`

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
0x180005ef0  push    rbx
0x180005ef2  sub     rsp, 20h
0x180005ef6  mov     rbx, rcx
0x180005ef9  mov     rcx, [rbx]; lpsz
0x180005efc  movzx   edx, word ptr [rcx]
0x180005eff  sub     edx, 9
0x180005f02  jz      short loc_180005F13
0x180005f04  sub     edx, 1
0x180005f07  jz      short loc_180005F13
0x180005f09  sub     edx, 3
0x180005f0c  jz      short loc_180005F13
0x180005f0e  cmp     edx, 13h
0x180005f11  jnz     short loc_180005F1E
0x180005f13  call    cs:__imp_CharNextW
0x180005f19  mov     [rbx], rax
0x180005f1c  jmp     short loc_180005EF9
0x180005f1e  add     rsp, 20h
0x180005f22  pop     rbx
0x180005f23  retn
```
