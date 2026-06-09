# StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)

- ea: `0x180013ce4`
- end: `0x180013d2f`
- name: `?StringCchCopyNW@@YAJPEAG_KPEBG1@Z`
- size: `75`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int64)`
- caller_count: `5`
- callee_count: `2`
- tags: ``

## callers

- `0x18001423c`
- `0x180033f5c`
- `0x1800344c4`
- `0x180034edc`
- `0x1800361c0`

## callees

- `0x180013ce4`
- `0x180013db8`

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
0x180013ce4  sub     rsp, 38h
0x180013ce8  mov     rax, rdx
0x180013ceb  test    rdx, rdx
0x180013cee  jz      short loc_180013D19
0x180013cf0  cmp     rax, 7FFFFFFFh
0x180013cf6  jbe     short loc_180013CFF
0x180013cf8  mov     edx, 80070057h; cchDest
0x180013cfd  jmp     short loc_180013D23
0x180013cff  cmp     r9, 7FFFFFFEh
0x180013d06  ja      short loc_180013CF8
0x180013d08  mov     [rsp+38h+cchToCopy], r9; cchToCopy
0x180013d0d  mov     r9, r8; pszSrc
0x180013d10  call    StringCopyWorkerW_0
0x180013d15  mov     edx, eax
0x180013d17  jmp     short loc_180013D28
0x180013d19  mov     edx, 80070057h
0x180013d1e  test    rax, rax
0x180013d21  jz      short loc_180013D28
0x180013d23  xor     eax, eax
0x180013d25  mov     [rcx], ax
0x180013d28  mov     eax, edx
0x180013d2a  add     rsp, 38h
0x180013d2e  retn
```
