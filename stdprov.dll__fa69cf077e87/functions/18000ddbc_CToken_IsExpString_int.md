# CToken::IsExpString(int)

- ea: `0x18000ddbc`
- end: `0x18000ddee`
- name: `?IsExpString@CToken@@QEAAHH@Z`
- size: `50`
- prototype: `_BOOL8 __fastcall(CToken *this, int)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000dbf8`
- `0x18000dd8c`

## callees

- `0x18000ca90`
- `0x18000ddbc`

## import_xrefs

- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ddc8`
- `wbemcomn!?GetAt@CFlexArray@@QEBAPEAXH@Z` at `0x18000ddc8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
_BOOL8 __fastcall CToken::IsExpString(CToken *this, int a2)
{
  CFlexArray *v2; // rcx
  TString *v3; // rax
  unsigned __int16 v4; // dx

  v2 = (CToken *)((char *)this + 48);
  return *(_DWORD *)v2 > a2
      && (v3 = (TString *)CFlexArray::GetAt(v2, a2)) != 0
      && (unsigned int)TString::Find(v3, v4) != -1;
}

```

## disassembly

```asm
0x18000ddbc  sub     rsp, 28h
0x18000ddc0  add     rcx, 30h ; '0'
0x18000ddc4  cmp     [rcx], edx
0x18000ddc6  jle     short loc_18000DDE7
0x18000ddc8  call    cs:__imp_?GetAt@CFlexArray@@QEBAPEAXH@Z; CFlexArray::GetAt(int)
0x18000ddce  test    rax, rax
0x18000ddd1  jz      short loc_18000DDE7
0x18000ddd3  mov     rcx, rax; this
0x18000ddd6  call    ?Find@TString@@QEAAHG@Z; TString::Find(ushort)
0x18000dddb  xor     ecx, ecx
0x18000dddd  cmp     eax, 0FFFFFFFFh
0x18000dde0  setnz   cl
0x18000dde3  mov     eax, ecx
0x18000dde5  jmp     short loc_18000DDE9
0x18000dde7  xor     eax, eax
0x18000dde9  add     rsp, 28h
0x18000dded  retn
```
