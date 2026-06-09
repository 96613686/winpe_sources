# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x18000caac`
- end: `0x18000cb37`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `139`
- prototype: `__int64(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180003548`
- `0x18000e2a4`
- `0x180010324`

## callees

- `0x18000caac`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x18000caeb`
- `msvcrt!_vsnwprintf` at `0x18000caeb`

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
0x18000caac  mov     [rsp+arg_10], r8
0x18000cab1  mov     qword ptr [rsp+Args], r9
0x18000cab6  push    rbx
0x18000cab7  push    rdi
0x18000cab8  sub     rsp, 38h
0x18000cabc  mov     rax, rdx
0x18000cabf  mov     rdi, rcx
0x18000cac2  test    rdx, rdx
0x18000cac5  jz      short loc_18000CB1E
0x18000cac7  cmp     rax, 7FFFFFFFh
0x18000cacd  jbe     short loc_18000CAD6
0x18000cacf  mov     edx, 80070057h
0x18000cad4  jmp     short loc_18000CB28
0x18000cad6  lea     rbx, [rdx-1]
0x18000cada  mov     [rsp+48h+var_28], 0
0x18000cae3  mov     rdx, rbx; BufferCount
0x18000cae6  lea     r9, [rsp+48h+Args]; Args
0x18000caeb  call    cs:__imp__vsnwprintf
0x18000caf2  nop     dword ptr [rax+rax+00h]
0x18000caf7  test    eax, eax
0x18000caf9  js      short loc_18000CB11
0x18000cafb  cdqe
0x18000cafd  cmp     rax, rbx
0x18000cb00  ja      short loc_18000CB11
0x18000cb02  xor     edx, edx
0x18000cb04  cmp     rax, rbx
0x18000cb07  jnz     short loc_18000CB2D
0x18000cb09  xor     eax, eax
0x18000cb0b  mov     [rdi+rbx*2], ax
0x18000cb0f  jmp     short loc_18000CB2D
0x18000cb11  xor     eax, eax
0x18000cb13  mov     edx, 8007007Ah
0x18000cb18  mov     [rdi+rbx*2], ax
0x18000cb1c  jmp     short loc_18000CB2D
0x18000cb1e  mov     edx, 80070057h
0x18000cb23  test    rax, rax
0x18000cb26  jz      short loc_18000CB2D
0x18000cb28  xor     ecx, ecx
0x18000cb2a  mov     [rdi], cx
0x18000cb2d  mov     eax, edx
0x18000cb2f  add     rsp, 38h
0x18000cb33  pop     rdi
0x18000cb34  pop     rbx
0x18000cb35  retn
```
