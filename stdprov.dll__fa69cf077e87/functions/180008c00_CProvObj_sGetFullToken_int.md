# CProvObj::sGetFullToken(int)

- ea: `0x180008c00`
- end: `0x180008c28`
- name: `?sGetFullToken@CProvObj@@QEAAPEBGH@Z`
- size: `40`
- prototype: `const unsigned __int16 *__fastcall(CProvObj *__hidden this, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800121e0`

## callees

- `0x180008c00`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008c10`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008c10`

## pseudocode

```c
const unsigned __int16 *__fastcall CProvObj::sGetFullToken(CProvObj *this, int a2)
{
  CFlexArray *v2; // rcx
  _QWORD *v3; // rax

  v2 = (CProvObj *)((char *)this + 8);
  if ( a2 < *(_DWORD *)v2 && a2 >= 0 && (v3 = CFlexArray::GetAt(v2, a2)) != 0 )
    return (const unsigned __int16 *)v3[4];
  else
    return 0;
}

```

## disassembly

```asm
0x180008c00  sub     rsp, 28h
0x180008c04  add     rcx, 8
0x180008c08  cmp     edx, [rcx]
0x180008c0a  jge     short loc_180008C24
0x180008c0c  test    edx, edx
0x180008c0e  js      short loc_180008C24
0x180008c10  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180008c16  test    rax, rax
0x180008c19  jz      short loc_180008C24
0x180008c1b  mov     rax, [rax+20h]
0x180008c1f  add     rsp, 28h
0x180008c23  retn
0x180008c24  xor     eax, eax
0x180008c26  jmp     short loc_180008C1F
```
