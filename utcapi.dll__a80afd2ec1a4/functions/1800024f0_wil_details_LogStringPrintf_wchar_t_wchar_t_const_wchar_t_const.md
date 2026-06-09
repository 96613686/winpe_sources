# wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)

- ea: `0x1800024f0`
- end: `0x180002567`
- name: `?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ`
- size: `119`
- prototype: `wchar_t *(wil::details *__hidden this, wchar_t *, const wchar_t *, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002058`

## callees

- `0x180001cb0`
- `0x1800024f0`

## pseudocode

```c
wchar_t *wil::details::LogStringPrintf(wil::details *this, wchar_t *a2, const wchar_t *a3, const wchar_t *a4, ...)
{
  unsigned __int64 v4; // rdi
  wchar_t *v6; // rbx
  size_t v7; // rdi
  int v8; // eax
  __int64 v9; // rax
  const wchar_t *Args; // [rsp+78h] [rbp+20h] BYREF

  Args = a4;
  v4 = ((char *)a2 - (char *)this) >> 1;
  v6 = (wchar_t *)this;
  if ( v4 )
  {
    if ( v4 > 0x7FFFFFFF )
    {
      *(_WORD *)this = 0;
    }
    else
    {
      v7 = v4 - 1;
      v8 = vsnwprintf((wchar_t *)this, v7, a3, (va_list)&Args);
      if ( v8 < 0 || v8 >= v7 )
        v6[v7] = 0;
    }
  }
  if ( a2 != v6 )
  {
    v9 = -1;
    do
      ++v9;
    while ( v6[v9] );
    v6 += v9;
  }
  return v6;
}

```

## disassembly

```asm
0x1800024f0  mov     [rsp+arg_10], r8
0x1800024f5  mov     [rsp+Args], r9
0x1800024fa  push    rbx
0x1800024fb  push    rbp
0x1800024fc  push    rsi
0x1800024fd  push    rdi
0x1800024fe  sub     rsp, 38h
0x180002502  mov     rdi, rdx
0x180002505  lea     r9, [rsp+58h+Args]; Args
0x18000250a  sub     rdi, rcx
0x18000250d  xor     ebp, ebp
0x18000250f  sar     rdi, 1
0x180002512  mov     rsi, rdx
0x180002515  mov     rbx, rcx
0x180002518  jz      short loc_180002544
0x18000251a  cmp     rdi, 7FFFFFFFh
0x180002521  ja      short loc_180002541
0x180002523  dec     rdi
0x180002526  mov     rdx, rdi; BufferCount
0x180002529  call    _vsnwprintf
0x18000252e  test    eax, eax
0x180002530  js      short loc_18000253B
0x180002532  cdqe
0x180002534  cmp     rax, rdi
0x180002537  ja      short loc_18000253B
0x180002539  jnz     short loc_180002544
0x18000253b  mov     [rbx+rdi*2], bp
0x18000253f  jmp     short loc_180002544
0x180002541  mov     [rcx], bp
0x180002544  cmp     rsi, rbx
0x180002547  jz      short loc_18000255A
0x180002549  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000254d  inc     rax
0x180002550  cmp     [rbx+rax*2], bp
0x180002554  jnz     short loc_18000254D
0x180002556  lea     rbx, [rbx+rax*2]
0x18000255a  mov     rax, rbx
0x18000255d  add     rsp, 38h
0x180002561  pop     rdi
0x180002562  pop     rsi
0x180002563  pop     rbp
0x180002564  pop     rbx
0x180002565  retn
```
