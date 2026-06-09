# StringCchCopyW(ushort *,unsigned __int64,ushort const *)

- ea: `0x180006a08`
- end: `0x180006a45`
- name: `?StringCchCopyW@@YAJPEAG_KPEBG@Z`
- size: `61`
- prototype: `__int64 __fastcall(unsigned __int16 *, size_t, size_t *)`
- caller_count: `8`
- callee_count: `2`
- tags: ``

## callers

- `0x180002660`
- `0x180005850`
- `0x180008924`
- `0x180009f7c`
- `0x18000d094`
- `0x18000d91c`
- `0x18000de20`
- `0x18000efe4`

## callees

- `0x180006a08`
- `0x180006a4c`

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
0x180006a08  sub     rsp, 38h
0x180006a0c  mov     rax, rdx
0x180006a0f  test    rdx, rdx
0x180006a12  jz      short loc_180006A2F
0x180006a14  cmp     rax, 7FFFFFFFh
0x180006a1a  jbe     short loc_180006A23
0x180006a1c  mov     edx, 80070057h; cchDest
0x180006a21  jmp     short loc_180006A39
0x180006a23  mov     r9, r8; pszSrc
0x180006a26  call    StringCopyWorkerW
0x180006a2b  mov     edx, eax
0x180006a2d  jmp     short loc_180006A3E
0x180006a2f  mov     edx, 80070057h
0x180006a34  test    rax, rax
0x180006a37  jz      short loc_180006A3E
0x180006a39  xor     eax, eax
0x180006a3b  mov     [rcx], ax
0x180006a3e  mov     eax, edx
0x180006a40  add     rsp, 38h
0x180006a44  retn
```
