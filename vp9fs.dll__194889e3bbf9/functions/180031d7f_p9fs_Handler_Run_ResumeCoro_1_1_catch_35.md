# _p9fs::Handler::Run$_ResumeCoro$1_::_1_::catch$35

- ea: `0x180031d7f`
- end: `0x180031db6`
- name: `_p9fs::Handler::Run$_ResumeCoro$1_::_1_::catch$35`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x1800167c0`

## string_xrefs

- `0x180031d93`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::Handler::Run__ResumeCoro_1_::_1_::catch_35(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 824),
    (void *)0x53D,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x180031d7f  mov     [rsp+arg_8], rdx
0x180031d84  push    rbp
0x180031d85  sub     rsp, 30h
0x180031d89  mov     rbp, rdx
0x180031d8c  mov     rcx, [rbp+338h]; this
0x180031d93  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180031d9a  mov     edx, 53Dh; void *
0x180031d9f  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180031da4  nop
0x180031da5  mov     rax, 0
0x180031daf  add     rsp, 30h
0x180031db3  pop     rbp
0x180031db4  retn
```
