# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140006328`
- end: `0x1400063ab`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x140003b94`
- `0x140006a7c`
- `0x14000897c`

## callees

- `0x14000226c`
- `0x140006328`

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
0x140006328  mov     [rsp+arg_10], r8
0x14000632d  mov     qword ptr [rsp+Args], r9
0x140006332  push    rbx
0x140006333  push    rdi
0x140006334  sub     rsp, 38h
0x140006338  mov     rax, rdx
0x14000633b  mov     rdi, rcx
0x14000633e  test    rdx, rdx
0x140006341  jz      short loc_140006393
0x140006343  cmp     rax, 7FFFFFFFh
0x140006349  jbe     short loc_140006352
0x14000634b  mov     edx, 80070057h
0x140006350  jmp     short loc_14000639D
0x140006352  lea     rbx, [rdx-1]
0x140006356  mov     [rsp+48h+var_28], 0
0x14000635f  mov     rdx, rbx; BufferCount
0x140006362  lea     r9, [rsp+48h+Args]; Args
0x140006367  call    _vsnwprintf
0x14000636c  test    eax, eax
0x14000636e  js      short loc_140006386
0x140006370  cdqe
0x140006372  cmp     rax, rbx
0x140006375  ja      short loc_140006386
0x140006377  xor     edx, edx
0x140006379  cmp     rax, rbx
0x14000637c  jnz     short loc_1400063A2
0x14000637e  xor     eax, eax
0x140006380  mov     [rdi+rbx*2], ax
0x140006384  jmp     short loc_1400063A2
0x140006386  xor     eax, eax
0x140006388  mov     edx, 8007007Ah
0x14000638d  mov     [rdi+rbx*2], ax
0x140006391  jmp     short loc_1400063A2
0x140006393  mov     edx, 80070057h
0x140006398  test    rax, rax
0x14000639b  jz      short loc_1400063A2
0x14000639d  xor     ecx, ecx
0x14000639f  mov     [rdi], cx
0x1400063a2  mov     eax, edx
0x1400063a4  add     rsp, 38h
0x1400063a8  pop     rdi
0x1400063a9  pop     rbx
0x1400063aa  retn
```
