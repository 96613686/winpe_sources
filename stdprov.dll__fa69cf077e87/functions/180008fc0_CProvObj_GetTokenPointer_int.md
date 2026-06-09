# CProvObj::GetTokenPointer(int)

- ea: `0x180008fc0`
- end: `0x180008fd8`
- name: `?GetTokenPointer@CProvObj@@AEAAPEAVCToken@@H@Z`
- size: `24`
- prototype: `struct CToken *__fastcall(CProvObj *__hidden this, int)`
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000dd8c`
- `0x18000deb4`
- `0x18000dee8`
- `0x180012478`

## callees

- `0x180008fc0`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x180008fcc`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
struct CToken *__fastcall CProvObj::GetTokenPointer(CProvObj *this, int a2)
{
  CFlexArray *v2; // rcx

  v2 = (CProvObj *)((char *)this + 8);
  if ( a2 >= *(_DWORD *)v2 || a2 < 0 )
    return 0;
  else
    return (struct CToken *)CFlexArray::GetAt(v2, a2);
}

```

## disassembly

```asm
0x180008fc0  add     rcx, 8
0x180008fc4  cmp     edx, [rcx]
0x180008fc6  jge     short loc_180008FD4
0x180008fc8  test    edx, edx
0x180008fca  js      short loc_180008FD4
0x180008fcc  jmp     cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x180008fd3  retn
0x180008fd4  xor     eax, eax
0x180008fd6  jmp     short locret_180008FD3
```
