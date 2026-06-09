# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180001ca8`
- end: `0x180001d5f`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `183`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const wchar_t *, ...)`
- caller_count: `9`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180004dfc`
- `0x18000a4a4`
- `0x18000d7fc`
- `0x18000e3ec`
- `0x18000e8b8`
- `0x1800164b3`
- `0x1800165a4`
- `0x1800166dd`
- `0x180016753`

## callees

- `0x180001b44`
- `0x180001ca8`
- `0x18000fbca`
- `0x18000fce0`

## pseudocode

```c
__int64 StringCchPrintfW(wchar_t *Buffer, __int64 a2, const wchar_t *a3, ...)
{
  unsigned int v5; // edi
  size_t v6; // rsi
  unsigned __int64 *v7; // rax
  int v8; // eax
  va_list va; // [rsp+98h] [rbp+20h] BYREF

  va_start(va, a3);
  if ( (unsigned __int64)(a2 - 1) <= 0x7FFFFFFE )
  {
    v5 = 0;
    v6 = a2 - 1;
    v7 = _local_stdio_printf_options();
    v8 = o___stdio_common_vswprintf_0(*v7 | 1, Buffer, v6, a3, 0, va);
    if ( v8 < 0 )
      v8 = -1;
    if ( v8 < 0 || v8 > v6 )
    {
      v5 = -2147024774;
    }
    else if ( v8 != v6 )
    {
      return v5;
    }
    Buffer[v6] = 0;
    return v5;
  }
  v5 = -2147024809;
  if ( a2 )
    *Buffer = 0;
  return v5;
}

```

## disassembly

```asm
0x180001ca8  mov     [rsp+arg_10], r8
0x180001cad  mov     qword ptr [rsp+arg_18], r9
0x180001cb2  push    rbx
0x180001cb3  push    rbp
0x180001cb4  push    rsi
0x180001cb5  push    rdi
0x180001cb6  push    r14
0x180001cb8  push    r15
0x180001cba  sub     rsp, 48h
0x180001cbe  mov     rax, cs:__security_cookie
0x180001cc5  xor     rax, rsp
0x180001cc8  mov     [rsp+78h+var_40], rax
0x180001ccd  lea     rax, [rdx-1]
0x180001cd1  xor     ebx, ebx
0x180001cd3  mov     rbp, r8
0x180001cd6  mov     r14, rcx
0x180001cd9  cmp     rax, 7FFFFFFEh
0x180001cdf  jbe     short loc_180001CF0
0x180001ce1  mov     edi, 80070057h
0x180001ce6  test    rdx, rdx
0x180001ce9  jz      short loc_180001D43
0x180001ceb  mov     [rcx], bx
0x180001cee  jmp     short loc_180001D43
0x180001cf0  lea     r15, [rsp+78h+arg_18]
0x180001cf8  mov     edi, ebx
0x180001cfa  lea     rsi, [rdx-1]
0x180001cfe  call    __local_stdio_printf_options
0x180001d03  mov     [rsp+78h+ArgList], r15; ArgList
0x180001d08  mov     r9, rbp; Format
0x180001d0b  mov     r8, rsi; BufferCount
0x180001d0e  mov     [rsp+78h+Locale], rbx; Locale
0x180001d13  mov     rdx, r14; Buffer
0x180001d16  mov     rcx, [rax]
0x180001d19  or      rcx, 1; Options
0x180001d1d  call    _o___stdio_common_vswprintf_0
0x180001d22  or      ecx, 0FFFFFFFFh
0x180001d25  test    eax, eax
0x180001d27  cmovs   eax, ecx
0x180001d2a  test    eax, eax
0x180001d2c  js      short loc_180001D39
0x180001d2e  cdqe
0x180001d30  cmp     rax, rsi
0x180001d33  ja      short loc_180001D39
0x180001d35  jnz     short loc_180001D43
0x180001d37  jmp     short loc_180001D3E
0x180001d39  mov     edi, 8007007Ah
0x180001d3e  mov     [r14+rsi*2], bx
0x180001d43  mov     eax, edi
0x180001d45  mov     rcx, [rsp+78h+var_40]
0x180001d4a  xor     rcx, rsp; StackCookie
0x180001d4d  call    __security_check_cookie
0x180001d52  add     rsp, 48h
0x180001d56  pop     r15
0x180001d58  pop     r14
0x180001d5a  pop     rdi
0x180001d5b  pop     rsi
0x180001d5c  pop     rbp
0x180001d5d  pop     rbx
0x180001d5e  retn
```
