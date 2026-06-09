# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180005968`
- end: `0x1800059eb`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `131`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `6`
- callee_count: `2`
- tags: ``

## callers

- `0x180003bd0`
- `0x180006730`
- `0x180007f18`
- `0x180007fc4`
- `0x18000834c`
- `0x180008828`

## callees

- `0x180002b9c`
- `0x180005968`

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
0x180005968  mov     [rsp+arg_10], r8
0x18000596d  mov     qword ptr [rsp+Args], r9
0x180005972  push    rbx
0x180005973  push    rdi
0x180005974  sub     rsp, 38h
0x180005978  mov     rax, rdx
0x18000597b  mov     rdi, rcx
0x18000597e  test    rdx, rdx
0x180005981  jz      short loc_1800059D3
0x180005983  cmp     rax, 7FFFFFFFh
0x180005989  jbe     short loc_180005992
0x18000598b  mov     edx, 80070057h
0x180005990  jmp     short loc_1800059DD
0x180005992  lea     rbx, [rdx-1]
0x180005996  mov     [rsp+48h+var_28], 0
0x18000599f  mov     rdx, rbx; BufferCount
0x1800059a2  lea     r9, [rsp+48h+Args]; Args
0x1800059a7  call    _vsnwprintf
0x1800059ac  test    eax, eax
0x1800059ae  js      short loc_1800059C6
0x1800059b0  cdqe
0x1800059b2  cmp     rax, rbx
0x1800059b5  ja      short loc_1800059C6
0x1800059b7  xor     edx, edx
0x1800059b9  cmp     rax, rbx
0x1800059bc  jnz     short loc_1800059E2
0x1800059be  xor     eax, eax
0x1800059c0  mov     [rdi+rbx*2], ax
0x1800059c4  jmp     short loc_1800059E2
0x1800059c6  xor     eax, eax
0x1800059c8  mov     edx, 8007007Ah
0x1800059cd  mov     [rdi+rbx*2], ax
0x1800059d1  jmp     short loc_1800059E2
0x1800059d3  mov     edx, 80070057h
0x1800059d8  test    rax, rax
0x1800059db  jz      short loc_1800059E2
0x1800059dd  xor     ecx, ecx
0x1800059df  mov     [rdi], cx
0x1800059e2  mov     eax, edx
0x1800059e4  add     rsp, 38h
0x1800059e8  pop     rdi
0x1800059e9  pop     rbx
0x1800059ea  retn
```
