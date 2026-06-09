# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800063b4`
- end: `0x180006437`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180003f78`
- `0x180009a7c`
- `0x18000b35c`

## callees

- `0x1800031bc`
- `0x1800063b4`

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
0x1800063b4  mov     [rsp+arg_10], r8
0x1800063b9  mov     qword ptr [rsp+Args], r9
0x1800063be  push    rbx
0x1800063bf  push    rdi
0x1800063c0  sub     rsp, 38h
0x1800063c4  mov     rax, rdx
0x1800063c7  mov     rdi, rcx
0x1800063ca  test    rdx, rdx
0x1800063cd  jz      short loc_18000641F
0x1800063cf  cmp     rax, 7FFFFFFFh
0x1800063d5  jbe     short loc_1800063DE
0x1800063d7  mov     edx, 80070057h
0x1800063dc  jmp     short loc_180006429
0x1800063de  lea     rbx, [rdx-1]
0x1800063e2  mov     [rsp+48h+var_28], 0
0x1800063eb  mov     rdx, rbx; BufferCount
0x1800063ee  lea     r9, [rsp+48h+Args]; Args
0x1800063f3  call    _vsnwprintf
0x1800063f8  test    eax, eax
0x1800063fa  js      short loc_180006412
0x1800063fc  cdqe
0x1800063fe  cmp     rax, rbx
0x180006401  ja      short loc_180006412
0x180006403  xor     edx, edx
0x180006405  cmp     rax, rbx
0x180006408  jnz     short loc_18000642E
0x18000640a  xor     eax, eax
0x18000640c  mov     [rdi+rbx*2], ax
0x180006410  jmp     short loc_18000642E
0x180006412  xor     eax, eax
0x180006414  mov     edx, 8007007Ah
0x180006419  mov     [rdi+rbx*2], ax
0x18000641d  jmp     short loc_18000642E
0x18000641f  mov     edx, 80070057h
0x180006424  test    rax, rax
0x180006427  jz      short loc_18000642E
0x180006429  xor     ecx, ecx
0x18000642b  mov     [rdi], cx
0x18000642e  mov     eax, edx
0x180006430  add     rsp, 38h
0x180006434  pop     rdi
0x180006435  pop     rbx
0x180006436  retn
```
