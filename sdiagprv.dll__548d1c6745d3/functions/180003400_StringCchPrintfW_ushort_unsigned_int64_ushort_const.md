# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180003400`
- end: `0x180003484`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180008f00`
- `0x180009c70`
- `0x18000c2a0`
- `0x18000dc8c`
- `0x18000f654`

## callees

- `0x180003400`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000343f`
- `msvcrt!_vsnwprintf` at `0x18000343f`

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
0x180003400  mov     [rsp+arg_10], r8
0x180003405  mov     qword ptr [rsp+Args], r9
0x18000340a  push    rbx
0x18000340b  push    rdi
0x18000340c  sub     rsp, 38h
0x180003410  mov     rax, rdx
0x180003413  mov     rdi, rcx
0x180003416  test    rdx, rdx
0x180003419  jz      short loc_18000346C
0x18000341b  cmp     rax, 7FFFFFFFh
0x180003421  jbe     short loc_18000342A
0x180003423  mov     edx, 80070057h
0x180003428  jmp     short loc_180003476
0x18000342a  lea     rbx, [rdx-1]
0x18000342e  mov     [rsp+48h+var_28], 0
0x180003437  mov     rdx, rbx; BufferCount
0x18000343a  lea     r9, [rsp+48h+Args]; Args
0x18000343f  call    cs:__imp__vsnwprintf
0x180003445  test    eax, eax
0x180003447  js      short loc_18000345F
0x180003449  cdqe
0x18000344b  cmp     rax, rbx
0x18000344e  ja      short loc_18000345F
0x180003450  xor     edx, edx
0x180003452  cmp     rax, rbx
0x180003455  jnz     short loc_18000347B
0x180003457  xor     eax, eax
0x180003459  mov     [rdi+rbx*2], ax
0x18000345d  jmp     short loc_18000347B
0x18000345f  xor     eax, eax
0x180003461  mov     edx, 8007007Ah
0x180003466  mov     [rdi+rbx*2], ax
0x18000346a  jmp     short loc_18000347B
0x18000346c  mov     edx, 80070057h
0x180003471  test    rax, rax
0x180003474  jz      short loc_18000347B
0x180003476  xor     ecx, ecx
0x180003478  mov     [rdi], cx
0x18000347b  mov     eax, edx
0x18000347d  add     rsp, 38h
0x180003481  pop     rdi
0x180003482  pop     rbx
0x180003483  retn
```
