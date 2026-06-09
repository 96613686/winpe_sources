# RtlStringCchPrintfW

- ea: `0x1800040f0`
- end: `0x18000416d`
- name: `RtlStringCchPrintfW`
- size: `125`
- prototype: `__int64(wchar_t *, unsigned __int64, const wchar_t *, ...)`
- caller_count: `10`
- callee_count: `1`
- tags: ``

## callers

- `0x180001190`
- `0x1800020e0`
- `0x1800027a0`
- `0x180004180`
- `0x180005540`
- `0x1800056d0`
- `0x1800126cc`
- `0x180012ffc`
- `0x180014a84`
- `0x1800156c0`

## callees

- `0x1800040f0`

## import_xrefs

- `msvcrt!_vsnwprintf` at `0x180004124`
- `msvcrt!_vsnwprintf` at `0x180004124`

## pseudocode

```c
__int64 RtlStringCchPrintfW(wchar_t *a1, unsigned __int64 a2, const wchar_t *a3, ...)
{
  unsigned __int64 v4; // rsi
  unsigned int v5; // ebx
  int v6; // eax
  __int64 result; // rax
  va_list Args; // [rsp+68h] [rbp+20h] BYREF

  va_start(Args, a3);
  if ( !a2 )
    return 3221225485LL;
  if ( a2 > 0x7FFFFFFF )
  {
    result = 3221225485LL;
    *a1 = 0;
  }
  else
  {
    v4 = a2 - 1;
    v5 = 0;
    v6 = _vsnwprintf(a1, a2 - 1, a3, Args);
    if ( v6 < 0 || v6 > v4 )
    {
      a1[v4] = 0;
      return (unsigned int)-2147483643;
    }
    else if ( v6 == v4 )
    {
      a1[v4] = 0;
    }
    return v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800040f0  mov     [rsp+arg_10], r8
0x1800040f5  mov     qword ptr [rsp+Args], r9
0x1800040fa  push    rbx
0x1800040fb  push    rdi
0x1800040fc  sub     rsp, 38h
0x180004100  mov     rdi, rcx
0x180004103  test    rdx, rdx
0x180004106  jz      short loc_18000415C
0x180004108  cmp     rdx, 7FFFFFFFh
0x18000410f  ja      short loc_180004145
0x180004111  mov     [rsp+48h+var_18], rsi
0x180004116  lea     r9, [rsp+48h+Args]; Args
0x18000411b  lea     rsi, [rdx-1]
0x18000411f  xor     ebx, ebx
0x180004121  mov     rdx, rsi; BufferCount
0x180004124  call    cs:__imp__vsnwprintf
0x18000412a  test    eax, eax
0x18000412c  jns     short loc_18000414C
0x18000412e  mov     [rdi+rsi*2], bx
0x180004132  mov     ebx, 80000005h
0x180004137  mov     rsi, [rsp+48h+var_18]
0x18000413c  mov     eax, ebx
0x18000413e  add     rsp, 38h
0x180004142  pop     rdi
0x180004143  pop     rbx
0x180004144  retn
0x180004145  mov     eax, 0C000000Dh
0x18000414a  jmp     short loc_180004166
0x18000414c  movsxd  rcx, eax
0x18000414f  cmp     rcx, rsi
0x180004152  ja      short loc_18000412E
0x180004154  jnz     short loc_180004137
0x180004156  mov     [rdi+rsi*2], bx
0x18000415a  jmp     short loc_180004137
0x18000415c  mov     eax, 0C000000Dh
0x180004161  test    rdx, rdx
0x180004164  jz      short loc_18000413E
0x180004166  xor     ebx, ebx
0x180004168  mov     [rcx], bx
0x18000416b  jmp     short loc_18000413E
```
