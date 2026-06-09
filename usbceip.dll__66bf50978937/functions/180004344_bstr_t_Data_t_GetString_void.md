# _bstr_t::Data_t::GetString(void)

- ea: `0x180004344`
- end: `0x18000437f`
- name: `?GetString@Data_t@_bstr_t@@QEBAPEBDXZ`
- size: `59`
- prototype: `char *__fastcall(_bstr_t::Data_t *this)`
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800045d0`
- `0x180005b1c`
- `0x180006c28`
- `0x180006f18`
- `0x180007b44`

## callees

- `0x180004344`
- `0x18000e190`
- `0x18000e1c4`

## pseudocode

```c
char *__fastcall _bstr_t::Data_t::GetString(_bstr_t::Data_t *this)
{
  char *result; // rax
  struct IErrorInfo *v3; // rdx

  result = (char *)*((_QWORD *)this + 1);
  if ( !result )
  {
    result = _com_util::ConvertBSTRToString(*(LPCWCH *)this);
    *((_QWORD *)this + 1) = result;
    if ( !result )
    {
      if ( *(_QWORD *)this )
        _com_issue_error(-2147024882, v3);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180004344  push    rbx
0x180004346  sub     rsp, 20h
0x18000434a  mov     rax, [rcx+8]
0x18000434e  mov     rbx, rcx
0x180004351  test    rax, rax
0x180004354  jnz     short loc_180004379
0x180004356  mov     rcx, [rcx]; lpWideCharStr
0x180004359  call    ?ConvertBSTRToString@_com_util@@YAPEADPEAG@Z; _com_util::ConvertBSTRToString(ushort *)
0x18000435e  mov     [rbx+8], rax
0x180004362  test    rax, rax
0x180004365  jnz     short loc_180004379
0x180004367  cmp     [rbx], rax
0x18000436a  jz      short loc_180004377
0x18000436c  mov     ecx, 8007000Eh; int
0x180004371  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x180004377  xor     eax, eax
0x180004379  add     rsp, 20h
0x18000437d  pop     rbx
0x18000437e  retn
```
