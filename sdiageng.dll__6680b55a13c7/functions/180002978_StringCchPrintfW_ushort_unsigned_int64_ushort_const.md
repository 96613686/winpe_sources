# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002978`
- end: `0x1800029fc`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `12`
- callee_count: `1`
- tags: ``

## callers

- `0x180002338`
- `0x180004518`
- `0x18000533c`
- `0x180007bc0`
- `0x18000988c`
- `0x180009c30`
- `0x18001483c`
- `0x180015730`
- `0x18001d544`
- `0x180026958`
- `0x180026bf4`
- `0x1800278d4`

## callees

- `0x180002978`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800029b7`
- `msvcrt!_vsnwprintf` at `0x1800029b7`

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
0x180002978  mov     [rsp+arg_10], r8
0x18000297d  mov     qword ptr [rsp+Args], r9
0x180002982  push    rbx
0x180002983  push    rdi
0x180002984  sub     rsp, 38h
0x180002988  mov     rax, rdx
0x18000298b  mov     rdi, rcx
0x18000298e  test    rdx, rdx
0x180002991  jz      short loc_1800029E4
0x180002993  cmp     rax, 7FFFFFFFh
0x180002999  jbe     short loc_1800029A2
0x18000299b  mov     edx, 80070057h
0x1800029a0  jmp     short loc_1800029EE
0x1800029a2  lea     rbx, [rdx-1]
0x1800029a6  mov     [rsp+48h+var_28], 0
0x1800029af  mov     rdx, rbx; BufferCount
0x1800029b2  lea     r9, [rsp+48h+Args]; Args
0x1800029b7  call    cs:__imp__vsnwprintf
0x1800029bd  test    eax, eax
0x1800029bf  js      short loc_1800029D7
0x1800029c1  cdqe
0x1800029c3  cmp     rax, rbx
0x1800029c6  ja      short loc_1800029D7
0x1800029c8  xor     edx, edx
0x1800029ca  cmp     rax, rbx
0x1800029cd  jnz     short loc_1800029F3
0x1800029cf  xor     eax, eax
0x1800029d1  mov     [rdi+rbx*2], ax
0x1800029d5  jmp     short loc_1800029F3
0x1800029d7  xor     eax, eax
0x1800029d9  mov     edx, 8007007Ah
0x1800029de  mov     [rdi+rbx*2], ax
0x1800029e2  jmp     short loc_1800029F3
0x1800029e4  mov     edx, 80070057h
0x1800029e9  test    rax, rax
0x1800029ec  jz      short loc_1800029F3
0x1800029ee  xor     ecx, ecx
0x1800029f0  mov     [rdi], cx
0x1800029f3  mov     eax, edx
0x1800029f5  add     rsp, 38h
0x1800029f9  pop     rdi
0x1800029fa  pop     rbx
0x1800029fb  retn
```
