# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x180002a6c`
- end: `0x180002af0`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `132`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180002b00`

## callees

- `0x180002a6c`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180002aab`
- `msvcrt!_vsnwprintf` at `0x180002aab`

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
0x180002a6c  mov     [rsp+arg_10], r8
0x180002a71  mov     qword ptr [rsp+Args], r9
0x180002a76  push    rbx
0x180002a77  push    rdi
0x180002a78  sub     rsp, 38h
0x180002a7c  mov     rax, rdx
0x180002a7f  mov     rdi, rcx
0x180002a82  test    rdx, rdx
0x180002a85  jz      short loc_180002AD8
0x180002a87  cmp     rax, 7FFFFFFFh
0x180002a8d  jbe     short loc_180002A96
0x180002a8f  mov     edx, 80070057h
0x180002a94  jmp     short loc_180002AE2
0x180002a96  lea     rbx, [rdx-1]
0x180002a9a  mov     [rsp+48h+var_28], 0
0x180002aa3  mov     rdx, rbx; BufferCount
0x180002aa6  lea     r9, [rsp+48h+Args]; Args
0x180002aab  call    cs:__imp__vsnwprintf
0x180002ab1  test    eax, eax
0x180002ab3  js      short loc_180002ACB
0x180002ab5  cdqe
0x180002ab7  cmp     rax, rbx
0x180002aba  ja      short loc_180002ACB
0x180002abc  xor     edx, edx
0x180002abe  cmp     rax, rbx
0x180002ac1  jnz     short loc_180002AE7
0x180002ac3  xor     eax, eax
0x180002ac5  mov     [rdi+rbx*2], ax
0x180002ac9  jmp     short loc_180002AE7
0x180002acb  xor     eax, eax
0x180002acd  mov     edx, 8007007Ah
0x180002ad2  mov     [rdi+rbx*2], ax
0x180002ad6  jmp     short loc_180002AE7
0x180002ad8  mov     edx, 80070057h
0x180002add  test    rax, rax
0x180002ae0  jz      short loc_180002AE7
0x180002ae2  xor     ecx, ecx
0x180002ae4  mov     [rdi], cx
0x180002ae7  mov     eax, edx
0x180002ae9  add     rsp, 38h
0x180002aed  pop     rdi
0x180002aee  pop     rbx
0x180002aef  retn
```
