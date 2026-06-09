# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180006ca8`
- end: `0x180006d2b`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x1800059a8`
- `0x1800091dc`
- `0x18001458c`
- `0x1800150b0`
- `0x1800185c0`
- `0x180019cb8`

## callees

- `0x18000292c`
- `0x180006ca8`

## pseudocode

```c
__int64 StringCchPrintfW(unsigned __int16 *a1, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  unsigned int v4; // edx
  unsigned __int64 v5; // rbx
  int v6; // eax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( a2 )
  {
    if ( a2 <= 0x7FFFFFFF )
    {
      v5 = a2 - 1;
      v6 = vsnwprintf(a1, a2 - 1, a3, Args);
      if ( v6 < 0 || v6 > v5 )
      {
        v4 = -2147024774;
        a1[v5] = 0;
      }
      else
      {
        v4 = 0;
        if ( v6 == v5 )
          a1[v5] = 0;
      }
    }
    else
    {
      v4 = -2147024809;
      *a1 = 0;
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
0x180006ca8  mov     [rsp+arg_10], r8
0x180006cad  mov     qword ptr [rsp+Args], r9
0x180006cb2  push    rbx
0x180006cb3  push    rdi
0x180006cb4  sub     rsp, 38h
0x180006cb8  mov     rax, rdx
0x180006cbb  mov     rdi, rcx
0x180006cbe  test    rdx, rdx
0x180006cc1  jz      short loc_180006D13
0x180006cc3  cmp     rax, 7FFFFFFFh
0x180006cc9  jbe     short loc_180006CD2
0x180006ccb  mov     edx, 80070057h
0x180006cd0  jmp     short loc_180006D1D
0x180006cd2  lea     rbx, [rdx-1]
0x180006cd6  mov     [rsp+48h+var_28], 0
0x180006cdf  mov     rdx, rbx; BufferCount
0x180006ce2  lea     r9, [rsp+48h+Args]; Args
0x180006ce7  call    _vsnwprintf
0x180006cec  test    eax, eax
0x180006cee  js      short loc_180006D06
0x180006cf0  cdqe
0x180006cf2  cmp     rax, rbx
0x180006cf5  ja      short loc_180006D06
0x180006cf7  xor     edx, edx
0x180006cf9  cmp     rax, rbx
0x180006cfc  jnz     short loc_180006D22
0x180006cfe  xor     eax, eax
0x180006d00  mov     [rdi+rbx*2], ax
0x180006d04  jmp     short loc_180006D22
0x180006d06  xor     eax, eax
0x180006d08  mov     edx, 8007007Ah
0x180006d0d  mov     [rdi+rbx*2], ax
0x180006d11  jmp     short loc_180006D22
0x180006d13  mov     edx, 80070057h
0x180006d18  test    rax, rax
0x180006d1b  jz      short loc_180006D22
0x180006d1d  xor     ecx, ecx
0x180006d1f  mov     [rdi], cx
0x180006d22  mov     eax, edx
0x180006d24  add     rsp, 38h
0x180006d28  pop     rdi
0x180006d29  pop     rbx
0x180006d2a  retn
```
