# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180009474`
- end: `0x1800094f8`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180002ba0`
- `0x180006b90`
- `0x180009570`

## callees

- `0x180009474`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x1800094b3`
- `msvcrt!_vsnwprintf` at `0x1800094b3`

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
0x180009474  mov     [rsp+arg_10], r8
0x180009479  mov     qword ptr [rsp+Args], r9
0x18000947e  push    rbx
0x18000947f  push    rdi
0x180009480  sub     rsp, 38h
0x180009484  mov     rax, rdx
0x180009487  mov     rdi, rcx
0x18000948a  test    rdx, rdx
0x18000948d  jz      short loc_1800094E0
0x18000948f  cmp     rax, 7FFFFFFFh
0x180009495  jbe     short loc_18000949E
0x180009497  mov     edx, 80070057h
0x18000949c  jmp     short loc_1800094EA
0x18000949e  lea     rbx, [rdx-1]
0x1800094a2  mov     [rsp+48h+var_28], 0
0x1800094ab  mov     rdx, rbx; BufferCount
0x1800094ae  lea     r9, [rsp+48h+Args]; Args
0x1800094b3  call    cs:__imp__vsnwprintf
0x1800094b9  test    eax, eax
0x1800094bb  js      short loc_1800094D3
0x1800094bd  cdqe
0x1800094bf  cmp     rax, rbx
0x1800094c2  ja      short loc_1800094D3
0x1800094c4  xor     edx, edx
0x1800094c6  cmp     rax, rbx
0x1800094c9  jnz     short loc_1800094EF
0x1800094cb  xor     eax, eax
0x1800094cd  mov     [rdi+rbx*2], ax
0x1800094d1  jmp     short loc_1800094EF
0x1800094d3  xor     eax, eax
0x1800094d5  mov     edx, 8007007Ah
0x1800094da  mov     [rdi+rbx*2], ax
0x1800094de  jmp     short loc_1800094EF
0x1800094e0  mov     edx, 80070057h
0x1800094e5  test    rax, rax
0x1800094e8  jz      short loc_1800094EF
0x1800094ea  xor     ecx, ecx
0x1800094ec  mov     [rdi], cx
0x1800094ef  mov     eax, edx
0x1800094f1  add     rsp, 38h
0x1800094f5  pop     rdi
0x1800094f6  pop     rbx
0x1800094f7  retn
```
