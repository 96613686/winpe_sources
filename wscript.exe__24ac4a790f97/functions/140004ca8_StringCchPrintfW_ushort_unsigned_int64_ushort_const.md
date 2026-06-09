# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140004ca8`
- end: `0x140004d2c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x1400038f0`
- `0x1400072c0`
- `0x140007f74`
- `0x140016f68`

## callees

- `0x140004ca8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x140004ce7`
- `msvcrt!_vsnwprintf` at `0x140004ce7`

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
      v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
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
0x140004ca8  mov     [rsp+arg_10], r8
0x140004cad  mov     qword ptr [rsp+Args], r9
0x140004cb2  push    rbx
0x140004cb3  push    rdi
0x140004cb4  sub     rsp, 38h
0x140004cb8  mov     rax, rdx
0x140004cbb  mov     rdi, rcx
0x140004cbe  test    rdx, rdx
0x140004cc1  jz      short loc_140004D14
0x140004cc3  cmp     rax, 7FFFFFFFh
0x140004cc9  jbe     short loc_140004CD2
0x140004ccb  mov     edx, 80070057h
0x140004cd0  jmp     short loc_140004D1E
0x140004cd2  lea     rbx, [rdx-1]
0x140004cd6  mov     [rsp+48h+var_28], 0
0x140004cdf  mov     rdx, rbx; BufferCount
0x140004ce2  lea     r9, [rsp+48h+Args]; Args
0x140004ce7  call    cs:__imp__vsnwprintf
0x140004ced  test    eax, eax
0x140004cef  js      short loc_140004D07
0x140004cf1  cdqe
0x140004cf3  cmp     rax, rbx
0x140004cf6  ja      short loc_140004D07
0x140004cf8  xor     edx, edx
0x140004cfa  cmp     rax, rbx
0x140004cfd  jnz     short loc_140004D23
0x140004cff  xor     eax, eax
0x140004d01  mov     [rdi+rbx*2], ax
0x140004d05  jmp     short loc_140004D23
0x140004d07  xor     eax, eax
0x140004d09  mov     edx, 8007007Ah
0x140004d0e  mov     [rdi+rbx*2], ax
0x140004d12  jmp     short loc_140004D23
0x140004d14  mov     edx, 80070057h
0x140004d19  test    rax, rax
0x140004d1c  jz      short loc_140004D23
0x140004d1e  xor     ecx, ecx
0x140004d20  mov     [rdi], cx
0x140004d23  mov     eax, edx
0x140004d25  add     rsp, 38h
0x140004d29  pop     rdi
0x140004d2a  pop     rbx
0x140004d2b  retn
```
