# _p9fs::Plan9FileSystem::Teardown_::_1_::catch$7

- ea: `0x180032bb0`
- end: `0x180032bf3`
- name: `_p9fs::Plan9FileSystem::Teardown_::_1_::catch$7`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x1800167c0`
- `0x18001ca68`
- `0x180032bb0`

## string_xrefs

- `0x180032bd0`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
__int64 __fastcall p9fs::Plan9FileSystem::Teardown_::_1_::catch_7(wil *a1, __int64 a2)
{
  const char *v3; // r9

  if ( (unsigned int)wil::ResultFromCaughtException(a1) != -2147023901 )
    wil::details::in1diag3::Log_CaughtException(
      *(wil::details::in1diag3 **)(a2 + 152),
      (void *)0x2AC,
      (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
      v3);
  return 0;
}

```

## disassembly

```asm
0x180032bb0  mov     [rsp+arg_8], rdx
0x180032bb5  push    rbp
0x180032bb6  sub     rsp, 30h
0x180032bba  mov     rbp, rdx
0x180032bbd  call    ?ResultFromCaughtException@wil@@YAJXZ; wil::ResultFromCaughtException(void)
0x180032bc2  cmp     eax, 800703E3h
0x180032bc7  jz      short loc_180032BE2
0x180032bc9  mov     rcx, [rbp+98h]; this
0x180032bd0  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180032bd7  mov     edx, 2ACh; void *
0x180032bdc  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x180032be1  nop
0x180032be2  mov     rax, 0
0x180032bec  add     rsp, 30h
0x180032bf0  pop     rbp
0x180032bf1  retn
```
