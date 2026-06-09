# wil::details::GetLastErrorFailHr(void)

- ea: `0x180008d28`
- end: `0x180008d53`
- name: `?GetLastErrorFailHr@details@wil@@YAJXZ`
- size: `43`
- prototype: `signed int __fastcall(wil::details *this, __int64, __int64, const char *)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x180007f30`
- `0x180008098`
- `0x18000be04`

## callees

- `0x180008cc0`
- `0x180008d28`

## pseudocode

```c
signed int __fastcall wil::details::GetLastErrorFailHr(wil::details *this, __int64 a2, __int64 a3, const char *a4)
{
  signed int result; // eax
  const char *v5; // [rsp+20h] [rbp-18h]
  const char *retaddr; // [rsp+38h] [rbp+0h]

  result = wil::details::GetLastErrorFail(0, 0, 0, a4, v5, retaddr);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180008d28  sub     rsp, 38h
0x180008d2c  mov     rax, [rsp+38h]
0x180008d31  xor     r8d, r8d; unsigned int
0x180008d34  xor     edx, edx; void *
0x180008d36  mov     [rsp+38h+var_10], rax; char *
0x180008d3b  xor     ecx, ecx; this
0x180008d3d  call    ?GetLastErrorFail@details@wil@@YAKPEAXIPEBD110@Z; wil::details::GetLastErrorFail(void *,uint,char const *,char const *,char const *,void *)
0x180008d42  test    eax, eax
0x180008d44  jle     short loc_180008D4E
0x180008d46  movzx   eax, ax
0x180008d49  or      eax, 80070000h
0x180008d4e  add     rsp, 38h
0x180008d52  retn
```
