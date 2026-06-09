# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180009e30`
- end: `0x180009e6e`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `62`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `20`
- callee_count: `2`
- tags: ``

## callers

- `0x180009f2c`
- `0x18000a194`
- `0x18000a288`
- `0x18000ad30`
- `0x18000b484`
- `0x18000d1c0`
- `0x18000d350`
- `0x18001069c`
- `0x1800107c4`
- `0x180011c4c`
- `0x180013b28`
- `0x180014e5c`
- `0x18001541c`
- `0x18001558c`
- `0x1800165ac`
- `0x180018140`
- `0x18001847c`
- `0x18001bd30`
- `0x180023aa0`
- `0x180023c00`

## callees

- `0x180009e30`
- `0x180009e74`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
    }
    else
    {
      v3 = -2147024809;
      *a1 = 0;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v3;
}

```

## disassembly

```asm
0x180009e30  sub     rsp, 38h
0x180009e34  mov     rax, rdx
0x180009e37  test    rdx, rdx
0x180009e3a  jz      short loc_180009E57
0x180009e3c  cmp     rax, 7FFFFFFFh
0x180009e42  jbe     short loc_180009E4B
0x180009e44  mov     edx, 80070057h; cchDest
0x180009e49  jmp     short loc_180009E61
0x180009e4b  mov     r9, r8; pszSrc
0x180009e4e  call    StringCopyWorkerW
0x180009e53  mov     edx, eax
0x180009e55  jmp     short loc_180009E66
0x180009e57  mov     edx, 80070057h
0x180009e5c  test    rax, rax
0x180009e5f  jz      short loc_180009E66
0x180009e61  xor     eax, eax
0x180009e63  mov     [rcx], ax
0x180009e66  mov     eax, edx
0x180009e68  add     rsp, 38h
0x180009e6c  retn
```
