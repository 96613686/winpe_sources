# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180003a2c`
- end: `0x180003a69`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180002ca0`
- `0x180004e0c`
- `0x18000fb24`
- `0x180010504`
- `0x180012f30`
- `0x180013c34`
- `0x180013f64`
- `0x1800159c8`
- `0x180016c10`

## callees

- `0x180003a2c`
- `0x180003a70`

## pseudocode

```c
__int64 __fastcall StringCchCopyW(unsigned __int16 *a1, size_t a2, size_t *a3)
{
  unsigned int v3; // edx
  size_t v5; // [rsp+20h] [rbp-18h]

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v3 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW(a1, a2, a3, (STRSAFE_PCNZWCH)a3, v5);
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
0x180003a2c  sub     rsp, 38h
0x180003a30  mov     rax, rdx
0x180003a33  test    rdx, rdx
0x180003a36  jz      short loc_180003A58
0x180003a38  cmp     rax, 7FFFFFFFh
0x180003a3e  ja      short loc_180003A51
0x180003a40  mov     r9, r8; pszSrc
0x180003a43  call    StringCopyWorkerW
0x180003a48  mov     edx, eax
0x180003a4a  mov     eax, edx
0x180003a4c  add     rsp, 38h
0x180003a50  retn
0x180003a51  mov     edx, 80070057h
0x180003a56  jmp     short loc_180003A62
0x180003a58  mov     edx, 80070057h
0x180003a5d  test    rax, rax
0x180003a60  jz      short loc_180003A4A
0x180003a62  xor     eax, eax
0x180003a64  mov     [rcx], ax
0x180003a67  jmp     short loc_180003A4A
```
