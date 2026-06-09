# WcShouldSkipReparsePointInDirectoryEntry

- ea: `0x14001414c`
- end: `0x140014191`
- name: `WcShouldSkipReparsePointInDirectoryEntry`
- size: `69`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x14002b6cc`
- `0x14002fe84`

## callees

- `0x14001414c`

## pseudocode

```c
bool __fastcall WcShouldSkipReparsePointInDirectoryEntry(int a1, int a2, __int64 a3, __int64 a4)
{
  char v4; // r8
  int v5; // ecx
  int v6; // ecx
  int v7; // ecx
  int v8; // ecx
  int v9; // ecx

  v4 = 0;
  v5 = a1 - 33;
  if ( !v5 )
    return *(_DWORD *)(a4 + 8) == a2;
  v6 = v5 - 27;
  if ( !v6 )
    return *(_DWORD *)(a4 + 68) == a2;
  v7 = v6 - 3;
  if ( !v7 )
    return *(_DWORD *)(a4 + 68) == a2;
  v8 = v7 - 15;
  if ( !v8 )
    return *(_DWORD *)(a4 + 68) == a2;
  v9 = v8 - 1;
  if ( !v9 || (unsigned int)(v9 - 1) <= 1 )
    return *(_DWORD *)(a4 + 68) == a2;
  return v4;
}

```

## disassembly

```asm
0x14001414c  xor     r8b, r8b
0x14001414f  sub     ecx, 21h ; '!'
0x140014152  jz      short loc_14001417C
0x140014154  sub     ecx, 1Bh
0x140014157  jz      short loc_140014172
0x140014159  sub     ecx, 3
0x14001415c  jz      short loc_140014172
0x14001415e  sub     ecx, 0Fh
0x140014161  jz      short loc_140014172
0x140014163  sub     ecx, 1
0x140014166  jz      short loc_140014172
0x140014168  sub     ecx, 1
0x14001416b  jz      short loc_140014172
0x14001416d  cmp     ecx, 1
0x140014170  jnz     short loc_14001418D
0x140014172  cmp     [r9+44h], edx
0x140014176  setz    r8b
0x14001417a  jmp     short loc_14001418D
0x14001417c  cmp     [r9+8], edx
0x140014180  mov     eax, 1
0x140014185  movzx   r8d, r8b
0x140014189  cmovz   r8d, eax
0x14001418d  mov     al, r8b
0x140014190  retn
```
