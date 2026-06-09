# wil::make_unique_hlocal<uchar [0]>(unsigned __int64)

- ea: `0x180027154`
- end: `0x180027191`
- name: `??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `61`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18002893c`

## callees

- `0x180027154`
- `0x180027198`
- `0x180029d60`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal<unsigned char [0]>(_QWORD *a1)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<unsigned char [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, v2, v3, v4);
  return a1;
}

```

## disassembly

```asm
0x180027154  mov     [rsp+arg_0], rcx
0x180027159  push    rbx
0x18002715a  sub     rsp, 30h
0x18002715e  mov     rbx, rcx
0x180027161  mov     [rsp+38h+var_18], 0
0x180027169  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x18002716e  mov     [rsp+38h+var_18], 1
0x180027176  mov     rcx, [rsp+38h]; this
0x18002717b  cmp     qword ptr [rbx], 0
0x18002717f  jnz     short loc_180027187
0x180027181  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x180027187  mov     rax, rbx
0x18002718a  add     rsp, 30h
0x18002718e  pop     rbx
0x18002718f  retn
```
