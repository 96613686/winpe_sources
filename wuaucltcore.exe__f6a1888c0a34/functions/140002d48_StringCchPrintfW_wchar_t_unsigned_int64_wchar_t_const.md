# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x140002d48`
- end: `0x140002dff`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `183`
- prototype: `__int64(wchar_t *Buffer, unsigned __int64, const wchar_t *, ...)`
- caller_count: `10`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140005738`
- `0x14000b530`
- `0x14000fb58`
- `0x14001052c`
- `0x1400109ec`
- `0x1400110ac`
- `0x140021193`
- `0x140021284`
- `0x1400213bd`
- `0x140021433`

## callees

- `0x140001dd4`
- `0x140002d48`
- `0x14001a8ef`
- `0x14001aa60`

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
0x140002d48  mov     [rsp+arg_10], r8
0x140002d4d  mov     qword ptr [rsp+arg_18], r9
0x140002d52  push    rbx
0x140002d53  push    rbp
0x140002d54  push    rsi
0x140002d55  push    rdi
0x140002d56  push    r14
0x140002d58  push    r15
0x140002d5a  sub     rsp, 48h
0x140002d5e  mov     rax, cs:__security_cookie
0x140002d65  xor     rax, rsp
0x140002d68  mov     [rsp+78h+var_40], rax
0x140002d6d  lea     rax, [rdx-1]
0x140002d71  xor     ebx, ebx
0x140002d73  mov     rbp, r8
0x140002d76  mov     r14, rcx
0x140002d79  cmp     rax, 7FFFFFFEh
0x140002d7f  jbe     short loc_140002D90
0x140002d81  mov     edi, 80070057h
0x140002d86  test    rdx, rdx
0x140002d89  jz      short loc_140002DE3
0x140002d8b  mov     [rcx], bx
0x140002d8e  jmp     short loc_140002DE3
0x140002d90  lea     r15, [rsp+78h+arg_18]
0x140002d98  mov     edi, ebx
0x140002d9a  lea     rsi, [rdx-1]
0x140002d9e  call    __local_stdio_printf_options
0x140002da3  mov     [rsp+78h+ArgList], r15; ArgList
0x140002da8  mov     r9, rbp; Format
0x140002dab  mov     r8, rsi; BufferCount
0x140002dae  mov     [rsp+78h+Locale], rbx; Locale
0x140002db3  mov     rdx, r14; Buffer
0x140002db6  mov     rcx, [rax]
0x140002db9  or      rcx, 1; Options
0x140002dbd  call    _o___stdio_common_vswprintf_0
0x140002dc2  or      ecx, 0FFFFFFFFh
0x140002dc5  test    eax, eax
0x140002dc7  cmovs   eax, ecx
0x140002dca  test    eax, eax
0x140002dcc  js      short loc_140002DD9
0x140002dce  cdqe
0x140002dd0  cmp     rax, rsi
0x140002dd3  ja      short loc_140002DD9
0x140002dd5  jnz     short loc_140002DE3
0x140002dd7  jmp     short loc_140002DDE
0x140002dd9  mov     edi, 8007007Ah
0x140002dde  mov     [r14+rsi*2], bx
0x140002de3  mov     eax, edi
0x140002de5  mov     rcx, [rsp+78h+var_40]
0x140002dea  xor     rcx, rsp; StackCookie
0x140002ded  call    __security_check_cookie
0x140002df2  add     rsp, 48h
0x140002df6  pop     r15
0x140002df8  pop     r14
0x140002dfa  pop     rdi
0x140002dfb  pop     rsi
0x140002dfc  pop     rbp
0x140002dfd  pop     rbx
0x140002dfe  retn
```
