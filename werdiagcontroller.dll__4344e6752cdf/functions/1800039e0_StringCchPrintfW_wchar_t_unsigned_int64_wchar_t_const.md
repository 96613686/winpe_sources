# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x1800039e0`
- end: `0x180003a63`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `131`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800030b0`
- `0x180003b98`
- `0x180004420`

## callees

- `0x180001fc0`
- `0x1800039e0`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
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
0x1800039e0  mov     [rsp+arg_10], r8
0x1800039e5  mov     qword ptr [rsp+Args], r9
0x1800039ea  push    rbx
0x1800039eb  push    rdi
0x1800039ec  sub     rsp, 38h
0x1800039f0  mov     rax, rdx
0x1800039f3  mov     rdi, rcx
0x1800039f6  test    rdx, rdx
0x1800039f9  jz      short loc_180003A4B
0x1800039fb  cmp     rax, 7FFFFFFFh
0x180003a01  jbe     short loc_180003A0A
0x180003a03  mov     edx, 80070057h
0x180003a08  jmp     short loc_180003A55
0x180003a0a  lea     rbx, [rdx-1]
0x180003a0e  mov     [rsp+48h+var_28], 0
0x180003a17  mov     rdx, rbx; BufferCount
0x180003a1a  lea     r9, [rsp+48h+Args]; Args
0x180003a1f  call    _vsnwprintf
0x180003a24  test    eax, eax
0x180003a26  js      short loc_180003A3E
0x180003a28  cdqe
0x180003a2a  cmp     rax, rbx
0x180003a2d  ja      short loc_180003A3E
0x180003a2f  xor     edx, edx
0x180003a31  cmp     rax, rbx
0x180003a34  jnz     short loc_180003A5A
0x180003a36  xor     eax, eax
0x180003a38  mov     [rdi+rbx*2], ax
0x180003a3c  jmp     short loc_180003A5A
0x180003a3e  xor     eax, eax
0x180003a40  mov     edx, 8007007Ah
0x180003a45  mov     [rdi+rbx*2], ax
0x180003a49  jmp     short loc_180003A5A
0x180003a4b  mov     edx, 80070057h
0x180003a50  test    rax, rax
0x180003a53  jz      short loc_180003A5A
0x180003a55  xor     ecx, ecx
0x180003a57  mov     [rdi], cx
0x180003a5a  mov     eax, edx
0x180003a5c  add     rsp, 38h
0x180003a60  pop     rdi
0x180003a61  pop     rbx
0x180003a62  retn
```
