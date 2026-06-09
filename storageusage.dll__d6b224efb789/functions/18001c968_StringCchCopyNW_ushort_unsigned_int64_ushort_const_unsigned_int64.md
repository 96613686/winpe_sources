# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x18001c968`
- end: `0x18001c9b3`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001afb0`
- `0x18001d8b0`
- `0x18001f230`
- `0x18001f4a0`
- `0x180020c30`

## callees

- `0x18001c968`
- `0x18001c9bc`

## pseudocode

```c
__int64 __fastcall StringCchCopyNW(unsigned __int16 *a1, size_t a2, size_t *a3, size_t cchToCopy)
{
  unsigned int v4; // edx

  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF || cchToCopy > 0x7FFFFFFE )
    {
      v4 = -2147024809;
      *a1 = 0;
    }
    else
    {
      return (unsigned int)StringCopyWorkerW_0(a1, a2, a3, (STRSAFE_PCNZWCH)a3, cchToCopy);
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v4;
}

```

## disassembly

```asm
0x18001c968  sub     rsp, 38h
0x18001c96c  mov     rax, rdx
0x18001c96f  test    rdx, rdx
0x18001c972  jz      short loc_18001C99D
0x18001c974  cmp     rax, 7FFFFFFFh
0x18001c97a  jbe     short loc_18001C983
0x18001c97c  mov     edx, 80070057h; cchDest
0x18001c981  jmp     short loc_18001C9A7
0x18001c983  cmp     r9, 7FFFFFFEh
0x18001c98a  ja      short loc_18001C97C
0x18001c98c  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x18001c991  mov     r9, r8; pszSrc
0x18001c994  call    StringCopyWorkerW_0
0x18001c999  mov     edx, eax
0x18001c99b  jmp     short loc_18001C9AC
0x18001c99d  mov     edx, 80070057h
0x18001c9a2  test    rax, rax
0x18001c9a5  jz      short loc_18001C9AC
0x18001c9a7  xor     eax, eax
0x18001c9a9  mov     [rcx], ax
0x18001c9ac  mov     eax, edx
0x18001c9ae  add     rsp, 38h
0x18001c9b2  retn
```
