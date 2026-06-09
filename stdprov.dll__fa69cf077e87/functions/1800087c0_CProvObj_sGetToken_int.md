# CProvObj::sGetToken(int)

- ea: `0x1800087c0`
- end: `0x1800087e8`
- name: `?sGetToken@CProvObj@@QEAAPEBGH@Z`
- size: `40`
- prototype: `const unsigned __int16 *__fastcall(CProvObj *__hidden this, int)`
- caller_count: `6`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180001640`
- `0x1800101d4`
- `0x180010dc8`
- `0x180011300`
- `0x180011cf0`
- `0x1800121e0`

## callees

- `0x1800087c0`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800087d0`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x1800087d0`

## pseudocode

```c
const unsigned __int16 *__fastcall CProvObj::sGetToken(CProvObj *this, int a2)
{
  CFlexArray *v2; // rcx
  _QWORD *v3; // rax

  v2 = (CProvObj *)((char *)this + 8);
  if ( a2 < *(_DWORD *)v2 && a2 >= 0 && (v3 = CFlexArray::GetAt(v2, a2)) != 0 )
    return (const unsigned __int16 *)v3[2];
  else
    return 0;
}

```

## disassembly

```asm
0x1800087c0  sub     rsp, 28h
0x1800087c4  add     rcx, 8
0x1800087c8  cmp     edx, [rcx]
0x1800087ca  jge     short loc_1800087E4
0x1800087cc  test    edx, edx
0x1800087ce  js      short loc_1800087E4
0x1800087d0  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x1800087d6  test    rax, rax
0x1800087d9  jz      short loc_1800087E4
0x1800087db  mov     rax, [rax+10h]
0x1800087df  add     rsp, 28h
0x1800087e3  retn
0x1800087e4  xor     eax, eax
0x1800087e6  jmp     short loc_1800087DF
```
