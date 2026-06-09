# StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)

- ea: `0x180004558`
- end: `0x18000460f`
- name: `?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ`
- size: `183`
- prototype: `__int64(wchar_t *Buffer, __int64, const wchar_t *, ...)`
- caller_count: `6`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x180007654`
- `0x18000bfc0`
- `0x180015534`
- `0x180015625`
- `0x18001575e`
- `0x1800157d4`

## callees

- `0x1800043d8`
- `0x180004558`
- `0x180010144`
- `0x180010310`

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
0x180004558  mov     [rsp+arg_10], r8
0x18000455d  mov     qword ptr [rsp+arg_18], r9
0x180004562  push    rbx
0x180004563  push    rbp
0x180004564  push    rsi
0x180004565  push    rdi
0x180004566  push    r14
0x180004568  push    r15
0x18000456a  sub     rsp, 48h
0x18000456e  mov     rax, cs:__security_cookie
0x180004575  xor     rax, rsp
0x180004578  mov     [rsp+78h+var_40], rax
0x18000457d  lea     rax, [rdx-1]
0x180004581  xor     ebx, ebx
0x180004583  mov     rbp, r8
0x180004586  mov     r14, rcx
0x180004589  cmp     rax, 7FFFFFFEh
0x18000458f  jbe     short loc_1800045A0
0x180004591  mov     edi, 80070057h
0x180004596  test    rdx, rdx
0x180004599  jz      short loc_1800045F3
0x18000459b  mov     [rcx], bx
0x18000459e  jmp     short loc_1800045F3
0x1800045a0  lea     r15, [rsp+78h+arg_18]
0x1800045a8  mov     edi, ebx
0x1800045aa  lea     rsi, [rdx-1]
0x1800045ae  call    __local_stdio_printf_options
0x1800045b3  mov     [rsp+78h+ArgList], r15; ArgList
0x1800045b8  mov     r9, rbp; Format
0x1800045bb  mov     r8, rsi; BufferCount
0x1800045be  mov     [rsp+78h+Locale], rbx; Locale
0x1800045c3  mov     rdx, r14; Buffer
0x1800045c6  mov     rcx, [rax]
0x1800045c9  or      rcx, 1; Options
0x1800045cd  call    _o___stdio_common_vswprintf_0
0x1800045d2  or      ecx, 0FFFFFFFFh
0x1800045d5  test    eax, eax
0x1800045d7  cmovs   eax, ecx
0x1800045da  test    eax, eax
0x1800045dc  js      short loc_1800045E9
0x1800045de  cdqe
0x1800045e0  cmp     rax, rsi
0x1800045e3  ja      short loc_1800045E9
0x1800045e5  jnz     short loc_1800045F3
0x1800045e7  jmp     short loc_1800045EE
0x1800045e9  mov     edi, 8007007Ah
0x1800045ee  mov     [r14+rsi*2], bx
0x1800045f3  mov     eax, edi
0x1800045f5  mov     rcx, [rsp+78h+var_40]
0x1800045fa  xor     rcx, rsp; StackCookie
0x1800045fd  call    __security_check_cookie
0x180004602  add     rsp, 48h
0x180004606  pop     r15
0x180004608  pop     r14
0x18000460a  pop     rdi
0x18000460b  pop     rsi
0x18000460c  pop     rbp
0x18000460d  pop     rbx
0x18000460e  retn
```
