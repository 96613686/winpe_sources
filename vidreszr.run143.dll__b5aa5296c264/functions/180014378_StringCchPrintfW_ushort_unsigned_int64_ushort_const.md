# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180014378`
- end: `0x1800143fb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800095d0`
- `0x180009910`

## callees

- `0x180002678`
- `0x180014378`

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
0x180014378  mov     [rsp+arg_10], r8
0x18001437d  mov     qword ptr [rsp+Args], r9
0x180014382  push    rbx
0x180014383  push    rdi
0x180014384  sub     rsp, 38h
0x180014388  mov     rax, rdx
0x18001438b  mov     rdi, rcx
0x18001438e  test    rdx, rdx
0x180014391  jz      short loc_1800143E3
0x180014393  cmp     rax, 7FFFFFFFh
0x180014399  jbe     short loc_1800143A2
0x18001439b  mov     edx, 80070057h
0x1800143a0  jmp     short loc_1800143ED
0x1800143a2  lea     rbx, [rdx-1]
0x1800143a6  mov     [rsp+48h+var_28], 0
0x1800143af  mov     rdx, rbx; BufferCount
0x1800143b2  lea     r9, [rsp+48h+Args]; Args
0x1800143b7  call    _vsnwprintf
0x1800143bc  test    eax, eax
0x1800143be  js      short loc_1800143D6
0x1800143c0  cdqe
0x1800143c2  cmp     rax, rbx
0x1800143c5  ja      short loc_1800143D6
0x1800143c7  xor     edx, edx
0x1800143c9  cmp     rax, rbx
0x1800143cc  jnz     short loc_1800143F2
0x1800143ce  xor     eax, eax
0x1800143d0  mov     [rdi+rbx*2], ax
0x1800143d4  jmp     short loc_1800143F2
0x1800143d6  xor     eax, eax
0x1800143d8  mov     edx, 8007007Ah
0x1800143dd  mov     [rdi+rbx*2], ax
0x1800143e1  jmp     short loc_1800143F2
0x1800143e3  mov     edx, 80070057h
0x1800143e8  test    rax, rax
0x1800143eb  jz      short loc_1800143F2
0x1800143ed  xor     ecx, ecx
0x1800143ef  mov     [rdi], cx
0x1800143f2  mov     eax, edx
0x1800143f4  add     rsp, 38h
0x1800143f8  pop     rdi
0x1800143f9  pop     rbx
0x1800143fa  retn
```
