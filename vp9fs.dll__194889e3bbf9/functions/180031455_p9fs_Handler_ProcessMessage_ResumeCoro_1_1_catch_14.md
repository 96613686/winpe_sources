# _p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$14

- ea: `0x180031455`
- end: `0x180031493`
- name: `_p9fs::Handler::ProcessMessage$_ResumeCoro$1_::_1_::catch$14`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x1800167c0`
- `0x18001c9c8`

## string_xrefs

- `0x180031469`: `onecore\vm\dv\storage\plan9\dll\p9handler.cpp`

## pseudocode

```c
void __fastcall __noreturn p9fs::Handler::ProcessMessage__ResumeCoro_1_::_1_::catch_14(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  p9fs::util *v4; // rcx

  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 280),
    (void *)0x4EF,
    (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\p9handler.cpp",
    a4);
  p9fs::util::LinuxErrorFromCaughtException(v4);
}

```

## disassembly

```asm
0x180031455  mov     [rsp+arg_8], rdx
0x18003145a  push    rbp
0x18003145b  sub     rsp, 20h
0x18003145f  mov     rbp, rdx
0x180031462  mov     rcx, [rbp+118h]; this
0x180031469  lea     r8, aOnecoreVmDvSto_6; "onecore\\vm\\dv\\storage\\plan9\\dll\\p"...
0x180031470  mov     edx, 4EFh; void *
0x180031475  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x18003147a  call    ?LinuxErrorFromCaughtException@util@p9fs@@YAJXZ; p9fs::util::LinuxErrorFromCaughtException(void)
0x18003147f  mov     [rbp+40h], eax
0x180031482  mov     rax, 0
0x18003148c  add     rsp, 20h
0x180031490  pop     rbp
0x180031491  retn
```
