# wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)

- ea: `0x1800024c8`
- end: `0x18000253e`
- name: `?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ`
- size: `118`
- prototype: `wchar_t *(wil::details *__hidden this, wchar_t *, const wchar_t *, const wchar_t *, ...)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000203c`

## callees

- `0x180001cb0`
- `0x1800024c8`

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
0x1800024c8  mov     [rsp+arg_10], r8
0x1800024cd  mov     [rsp+Args], r9
0x1800024d2  push    rbx
0x1800024d3  push    rbp
0x1800024d4  push    rsi
0x1800024d5  push    rdi
0x1800024d6  sub     rsp, 38h
0x1800024da  mov     rdi, rdx
0x1800024dd  lea     r9, [rsp+58h+Args]; Args
0x1800024e2  sub     rdi, rcx
0x1800024e5  xor     ebp, ebp
0x1800024e7  sar     rdi, 1
0x1800024ea  mov     rsi, rdx
0x1800024ed  mov     rbx, rcx
0x1800024f0  jz      short loc_18000251C
0x1800024f2  cmp     rdi, 7FFFFFFFh
0x1800024f9  ja      short loc_180002519
0x1800024fb  dec     rdi
0x1800024fe  mov     rdx, rdi; BufferCount
0x180002501  call    _vsnwprintf
0x180002506  test    eax, eax
0x180002508  js      short loc_180002513
0x18000250a  cdqe
0x18000250c  cmp     rax, rdi
0x18000250f  ja      short loc_180002513
0x180002511  jnz     short loc_18000251C
0x180002513  mov     [rbx+rdi*2], bp
0x180002517  jmp     short loc_18000251C
0x180002519  mov     [rcx], bp
0x18000251c  cmp     rsi, rbx
0x18000251f  jz      short loc_180002532
0x180002521  or      rax, 0FFFFFFFFFFFFFFFFh
0x180002525  inc     rax
0x180002528  cmp     [rbx+rax*2], bp
0x18000252c  jnz     short loc_180002525
0x18000252e  lea     rbx, [rbx+rax*2]
0x180002532  mov     rax, rbx
0x180002535  add     rsp, 38h
0x180002539  pop     rdi
0x18000253a  pop     rsi
0x18000253b  pop     rbp
0x18000253c  pop     rbx
0x18000253d  retn
```
