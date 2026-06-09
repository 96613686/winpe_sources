# PkCompleteInsertion

- ea: `0x1400045d0`
- end: `0x140004627`
- name: `PkCompleteInsertion`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140005fe0`
- `0x14001172c`

## callees

- `0x1400045d0`

## pseudocode

```c
__int64 __fastcall PkCompleteInsertion(__int64 a1, int a2)
{
  int v2; // r10d
  _DWORD *v3; // rax
  unsigned int v4; // r8d
  int v5; // r9d
  unsigned int v6; // edx
  _UNKNOWN *retaddr; // [rsp+0h] [rbp+0h] BYREF

  v2 = *(_DWORD *)(a1 + 128);
  v3 = *(_DWORD **)a1;
  v4 = *(_DWORD *)(a1 + 16);
  *(_DWORD *)(a1 + 128) = a2;
  *v3 = a2;
  _InterlockedOr((volatile signed __int32 *)&retaddr, 0);
  v5 = v3[2];
  v6 = v3[1];
  if ( v6 >= v4 || (v6 & 7) != 0 )
    return 3221225730LL;
  *(_DWORD *)(a1 + 132) = v6;
  if ( v2 == v6 )
  {
    if ( !v5 )
      return 532;
    ++**(_QWORD **)(a1 + 152);
  }
  return 0;
}

```

## disassembly

```asm
0x1400045d0  mov     r10d, [rcx+80h]
0x1400045d7  mov     rax, [rcx]
0x1400045da  mov     r8d, [rcx+10h]
0x1400045de  mov     [rcx+80h], edx
0x1400045e4  mov     [rax], edx
0x1400045e6  lock or dword ptr [rsp+0], 0
0x1400045eb  mov     r9d, [rax+8]
0x1400045ef  mov     edx, [rax+4]
0x1400045f2  cmp     edx, r8d
0x1400045f5  jnb     short loc_140004621
0x1400045f7  test    dl, 7
0x1400045fa  jnz     short loc_140004621
0x1400045fc  mov     [rcx+84h], edx
0x140004602  cmp     r10d, edx
0x140004605  jnz     short loc_14000461D
0x140004607  test    r9d, r9d
0x14000460a  jnz     short loc_140004613
0x14000460c  mov     eax, 214h
0x140004611  retn
0x140004613  mov     rax, [rcx+98h]
0x14000461a  inc     qword ptr [rax]
0x14000461d  xor     eax, eax
0x14000461f  retn
0x140004621  mov     eax, 0C0000102h
0x140004626  retn
```
