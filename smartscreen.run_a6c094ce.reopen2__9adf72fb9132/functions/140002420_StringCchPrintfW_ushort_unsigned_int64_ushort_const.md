# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140002420`
- end: `0x1400024f1`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `209`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001ef0`
- `0x14002f264`
- `0x14003129c`

## callees

- `0x140002420`
- `0x1400024f8`
- `0x140026c20`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000248f`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x14000248f`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, unsigned __int64 a2, const unsigned __int16 *a3, ...)
{
  size_t v5; // rbx
  unsigned __int64 *v6; // rax
  int v7; // eax
  unsigned int v8; // edx
  va_list va; // [rsp+88h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( a2 )
  {
    if ( a2 > 0x7FFFFFFF )
    {
      v8 = -2147024809;
      *Buffer = 0;
    }
    else
    {
      v5 = a2 - 1;
      v6 = _local_stdio_printf_options();
      v7 = __stdio_common_vswprintf(*v6 | 1, Buffer, v5, a3, 0, va);
      if ( v7 < 0 || v7 > v5 )
      {
        v8 = -2147024774;
        Buffer[v5] = 0;
      }
      else
      {
        v8 = 0;
        if ( v7 == v5 )
          Buffer[v5] = 0;
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v8;
}

```

## disassembly

```asm
0x140002420  mov     r11, rsp
0x140002423  mov     [r11+18h], r8
0x140002427  mov     [r11+20h], r9
0x14000242b  push    rbx
0x14000242c  push    rbp
0x14000242d  push    rsi
0x14000242e  push    rdi
0x14000242f  sub     rsp, 48h
0x140002433  mov     rax, cs:__security_cookie
0x14000243a  xor     rax, rsp
0x14000243d  mov     [rsp+68h+var_30], rax
0x140002442  mov     rsi, r8
0x140002445  mov     rax, rdx
0x140002448  mov     rdi, rcx
0x14000244b  test    rdx, rdx
0x14000244e  jz      loc_1400024E0
0x140002454  cmp     rax, 7FFFFFFFh
0x14000245a  ja      short loc_1400024D9
0x14000245c  mov     qword ptr [r11-38h], 0
0x140002464  lea     rbp, [r11+20h]
0x140002468  lea     rbx, [rdx-1]
0x14000246c  call    __local_stdio_printf_options
0x140002471  mov     [rsp+68h+ArgList], rbp; ArgList
0x140002476  mov     r9, rsi; Format
0x140002479  mov     r8, rbx; BufferCount
0x14000247c  mov     [rsp+68h+Locale], 0; Locale
0x140002485  mov     rdx, rdi; Buffer
0x140002488  mov     rcx, [rax]
0x14000248b  or      rcx, 1; Options
0x14000248f  call    cs:__imp___stdio_common_vswprintf
0x140002496  nop     dword ptr [rax+rax+00h]
0x14000249b  test    eax, eax
0x14000249d  js      short loc_1400024B5
0x14000249f  cdqe
0x1400024a1  cmp     rax, rbx
0x1400024a4  ja      short loc_1400024B5
0x1400024a6  xor     edx, edx
0x1400024a8  cmp     rax, rbx
0x1400024ab  jnz     short loc_1400024C0
0x1400024ad  xor     eax, eax
0x1400024af  mov     [rdi+rbx*2], ax
0x1400024b3  jmp     short loc_1400024C0
0x1400024b5  xor     eax, eax
0x1400024b7  mov     edx, 8007007Ah
0x1400024bc  mov     [rdi+rbx*2], ax
0x1400024c0  mov     eax, edx
0x1400024c2  mov     rcx, [rsp+68h+var_30]
0x1400024c7  xor     rcx, rsp; StackCookie
0x1400024ca  call    __security_check_cookie
0x1400024cf  add     rsp, 48h
0x1400024d3  pop     rdi
0x1400024d4  pop     rsi
0x1400024d5  pop     rbp
0x1400024d6  pop     rbx
0x1400024d7  retn
0x1400024d9  mov     edx, 80070057h
0x1400024de  jmp     short loc_1400024EA
0x1400024e0  mov     edx, 80070057h
0x1400024e5  test    rax, rax
0x1400024e8  jz      short loc_1400024C0
0x1400024ea  xor     ecx, ecx
0x1400024ec  mov     [rdi], cx
0x1400024ef  jmp     short loc_1400024C0
```
