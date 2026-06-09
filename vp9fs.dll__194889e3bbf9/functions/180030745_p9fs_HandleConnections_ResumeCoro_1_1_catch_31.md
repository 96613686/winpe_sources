# _p9fs::HandleConnections$_ResumeCoro$1_::_1_::catch$31

- ea: `0x180030745`
- end: `0x18003078c`
- name: `_p9fs::HandleConnections$_ResumeCoro$1_::_1_::catch$31`
- size: `71`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x18000fddc`
- `0x1800167c0`

## string_xrefs

- `0x180030759`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::HandleConnections__ResumeCoro_1_::_1_::catch_31(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 488),
    (void *)0x5CC,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
    a4);
  p9fs::CancelToken::Cancel(*(p9fs::CancelToken **)(*(_QWORD *)(a2 + 72) + 3336LL));
  return 0;
}

```

## disassembly

```asm
0x180030745  mov     [rsp+arg_8], rdx
0x18003074a  push    rbp
0x18003074b  sub     rsp, 30h
0x18003074f  mov     rbp, rdx
0x180030752  mov     rcx, [rbp+1E8h]; this
0x180030759  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180030760  mov     edx, 5CCh; void *
0x180030765  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003076a  mov     rcx, [rbp+48h]
0x18003076e  mov     rcx, [rcx+0D08h]; this
0x180030775  call    ?Cancel@CancelToken@p9fs@@QEAAXXZ; p9fs::CancelToken::Cancel(void)
0x18003077a  nop
0x18003077b  mov     rax, 0
0x180030785  add     rsp, 30h
0x180030789  pop     rbp
0x18003078a  retn
```
