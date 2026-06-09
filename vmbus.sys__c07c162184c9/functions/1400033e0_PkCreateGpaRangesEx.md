# PkCreateGpaRangesEx

- ea: `0x1400033e0`
- end: `0x140003423`
- name: `PkCreateGpaRangesEx`
- size: `67`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x1400030fc`
- `0x14000f070`

## callees

- `0x1400033e0`
- `0x140014ce0`
- `0x140014ffc`

## pseudocode

```c
char *__fastcall PkCreateGpaRangesEx(
        gsl::details *a1,
        __int64 *a2,
        unsigned __int64 a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  unsigned __int64 v7[3]; // [rsp+30h] [rbp-18h] BYREF

  if ( !a3 && a4 )
  {
    gsl::details::terminate(a1);
    JUMPOUT(0x140003422LL);
  }
  v7[0] = a4;
  v7[1] = a3;
  return anonymous_namespace_::PkCreateGpaRangesEx__anonymous_namespace_::MdlWrapper_(
           (unsigned __int64)a1,
           a2,
           v7,
           a5,
           a6,
           0);
}

```

## disassembly

```asm
0x1400033e0  sub     rsp, 48h
0x1400033e4  mov     eax, r9d
0x1400033e7  test    r8, r8
0x1400033ea  jnz     short loc_1400033F1
0x1400033ec  test    r9d, r9d
0x1400033ef  jnz     short loc_14000341D
0x1400033f1  mov     r9d, [rsp+48h+arg_20]
0x1400033f6  mov     [rsp+48h+var_18], rax
0x1400033fb  mov     eax, [rsp+48h+arg_28]
0x1400033ff  mov     [rsp+48h+var_10], r8
0x140003404  lea     r8, [rsp+48h+var_18]
0x140003409  mov     [rsp+48h+var_20], 0
0x14000340e  mov     [rsp+48h+var_28], eax
0x140003412  call    _anonymous_namespace___PkCreateGpaRangesEx__anonymous_namespace___MdlWrapper_
0x140003417  add     rsp, 48h
0x14000341b  retn
0x14000341d  call    ?terminate@details@gsl@@YAXXZ; gsl::details::terminate(void)
```
