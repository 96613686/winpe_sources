# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x1800031f8`
- end: `0x18000327c`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002440`

## callees

- `0x1800031f8`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180003237`
- `msvcrt!_vsnwprintf` at `0x180003237`

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
0x1800031f8  mov     [rsp+arg_10], r8
0x1800031fd  mov     qword ptr [rsp+Args], r9
0x180003202  push    rbx
0x180003203  push    rdi
0x180003204  sub     rsp, 38h
0x180003208  mov     rax, rdx
0x18000320b  mov     rdi, rcx
0x18000320e  test    rdx, rdx
0x180003211  jz      short loc_180003264
0x180003213  cmp     rax, 7FFFFFFFh
0x180003219  jbe     short loc_180003222
0x18000321b  mov     edx, 80070057h
0x180003220  jmp     short loc_18000326E
0x180003222  lea     rbx, [rdx-1]
0x180003226  mov     [rsp+48h+var_28], 0
0x18000322f  mov     rdx, rbx; BufferCount
0x180003232  lea     r9, [rsp+48h+Args]; Args
0x180003237  call    cs:__imp__vsnwprintf
0x18000323d  test    eax, eax
0x18000323f  js      short loc_180003257
0x180003241  cdqe
0x180003243  cmp     rax, rbx
0x180003246  ja      short loc_180003257
0x180003248  xor     edx, edx
0x18000324a  cmp     rax, rbx
0x18000324d  jnz     short loc_180003273
0x18000324f  xor     eax, eax
0x180003251  mov     [rdi+rbx*2], ax
0x180003255  jmp     short loc_180003273
0x180003257  xor     eax, eax
0x180003259  mov     edx, 8007007Ah
0x18000325e  mov     [rdi+rbx*2], ax
0x180003262  jmp     short loc_180003273
0x180003264  mov     edx, 80070057h
0x180003269  test    rax, rax
0x18000326c  jz      short loc_180003273
0x18000326e  xor     ecx, ecx
0x180003270  mov     [rdi], cx
0x180003273  mov     eax, edx
0x180003275  add     rsp, 38h
0x180003279  pop     rdi
0x18000327a  pop     rbx
0x18000327b  retn
```
