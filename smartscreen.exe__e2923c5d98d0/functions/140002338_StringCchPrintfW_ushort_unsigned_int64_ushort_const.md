# StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)

- ea: `0x140002338`
- end: `0x140002402`
- name: `?StringCchPrintfW@@YAJPEAG_KPEBGZZ`
- size: `202`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const unsigned __int16 *, ...)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x140001e30`
- `0x14002e05c`
- `0x14002ff1c`

## callees

- `0x140002338`
- `0x140002408`
- `0x140025aa0`

## import_xrefs

- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1400023a7`
- `api-ms-win-crt-stdio-l1-1-0!__stdio_common_vswprintf` at `0x1400023a7`

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
0x140002338  mov     r11, rsp
0x14000233b  mov     [r11+18h], r8
0x14000233f  mov     [r11+20h], r9
0x140002343  push    rbx
0x140002344  push    rbp
0x140002345  push    rsi
0x140002346  push    rdi
0x140002347  sub     rsp, 48h
0x14000234b  mov     rax, cs:__security_cookie
0x140002352  xor     rax, rsp
0x140002355  mov     [rsp+68h+var_30], rax
0x14000235a  mov     rsi, r8
0x14000235d  mov     rax, rdx
0x140002360  mov     rdi, rcx
0x140002363  test    rdx, rdx
0x140002366  jz      loc_1400023F1
0x14000236c  cmp     rax, 7FFFFFFFh
0x140002372  ja      short loc_1400023EA
0x140002374  mov     qword ptr [r11-38h], 0
0x14000237c  lea     rbp, [r11+20h]
0x140002380  lea     rbx, [rdx-1]
0x140002384  call    __local_stdio_printf_options
0x140002389  mov     [rsp+68h+ArgList], rbp; ArgList
0x14000238e  mov     r9, rsi; Format
0x140002391  mov     r8, rbx; BufferCount
0x140002394  mov     [rsp+68h+Locale], 0; Locale
0x14000239d  mov     rdx, rdi; Buffer
0x1400023a0  mov     rcx, [rax]
0x1400023a3  or      rcx, 1; Options
0x1400023a7  call    cs:__imp___stdio_common_vswprintf
0x1400023ad  test    eax, eax
0x1400023af  js      short loc_1400023C7
0x1400023b1  cdqe
0x1400023b3  cmp     rax, rbx
0x1400023b6  ja      short loc_1400023C7
0x1400023b8  xor     edx, edx
0x1400023ba  cmp     rax, rbx
0x1400023bd  jnz     short loc_1400023D2
0x1400023bf  xor     eax, eax
0x1400023c1  mov     [rdi+rbx*2], ax
0x1400023c5  jmp     short loc_1400023D2
0x1400023c7  xor     eax, eax
0x1400023c9  mov     edx, 8007007Ah
0x1400023ce  mov     [rdi+rbx*2], ax
0x1400023d2  mov     eax, edx
0x1400023d4  mov     rcx, [rsp+68h+var_30]
0x1400023d9  xor     rcx, rsp; StackCookie
0x1400023dc  call    __security_check_cookie
0x1400023e1  add     rsp, 48h
0x1400023e5  pop     rdi
0x1400023e6  pop     rsi
0x1400023e7  pop     rbp
0x1400023e8  pop     rbx
0x1400023e9  retn
0x1400023ea  mov     edx, 80070057h
0x1400023ef  jmp     short loc_1400023FB
0x1400023f1  mov     edx, 80070057h
0x1400023f6  test    rax, rax
0x1400023f9  jz      short loc_1400023D2
0x1400023fb  xor     ecx, ecx
0x1400023fd  mov     [rdi], cx
0x140002400  jmp     short loc_1400023D2
```
