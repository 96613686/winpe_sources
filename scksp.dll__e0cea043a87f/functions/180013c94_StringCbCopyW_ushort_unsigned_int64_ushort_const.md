# StringCbCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180013c94`
- end: `0x180013cdd`
- name: `?StringCbCopyW@@YAJPEAG_KPEBG@Z`
- size: `73`
- prototype: `int(unsigned __int16 *, unsigned __int64, const unsigned __int16 *)`
- caller_count: `9`
- callee_count: `2`
- tags: ``

## callers

- `0x180017f6c`
- `0x18002cb34`
- `0x18002ec40`
- `0x18002fb68`
- `0x18003001c`
- `0x180030378`
- `0x180031a94`
- `0x180032cf4`
- `0x180033ce0`

## callees

- `0x180013c94`
- `0x180013db8`

## pseudocode

```c
__int64 __fastcall StringCbCopyW(unsigned __int16 *a1, unsigned __int64 a2, size_t *a3)
{
  unsigned int v3; // edx

  if ( a2 >> 1 )
  {
    if ( a2 >> 1 <= 0x7FFFFFFF )
    {
      return (unsigned int)StringCopyWorkerW_0(a1, a2 >> 1, a3, (STRSAFE_PCNZWCH)a3, 0x7FFFFFFEu);
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
0x180013c94  sub     rsp, 38h
0x180013c98  mov     rax, rdx
0x180013c9b  shr     rax, 1
0x180013c9e  jz      short loc_180013CC7
0x180013ca0  cmp     rax, 7FFFFFFFh
0x180013ca6  jbe     short loc_180013CAF
0x180013ca8  mov     edx, 80070057h
0x180013cad  jmp     short loc_180013CD1
0x180013caf  mov     r9, r8; pszSrc
0x180013cb2  mov     [rsp+38h+cchToCopy], 7FFFFFFEh; cchToCopy
0x180013cbb  mov     rdx, rax; cchDest
0x180013cbe  call    StringCopyWorkerW_0
0x180013cc3  mov     edx, eax
0x180013cc5  jmp     short loc_180013CD6
0x180013cc7  mov     edx, 80070057h
0x180013ccc  test    rax, rax
0x180013ccf  jz      short loc_180013CD6
0x180013cd1  xor     eax, eax
0x180013cd3  mov     [rcx], ax
0x180013cd6  mov     eax, edx
0x180013cd8  add     rsp, 38h
0x180013cdc  retn
```
