# CreatePlan9FileSystem$catch$10

- ea: `0x180032d0b`
- end: `0x180032d41`
- name: `CreatePlan9FileSystem$catch$10`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x18002751c`

## string_xrefs

- `0x180032d1c`: `onecore\vm\dv\storage\plan9\dll\windows\p9fs.cpp`

## pseudocode

```c
__int64 __fastcall CreatePlan9FileSystem_catch_10(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 32) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0x31A,
                           (unsigned int)"onecore\\vm\\dv\\storage\\plan9\\dll\\windows\\p9fs.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x180032d0b  mov     [rsp+arg_8], rdx
0x180032d10  push    rbp
0x180032d11  sub     rsp, 20h
0x180032d15  mov     rbp, rdx
0x180032d18  mov     rcx, [rbp+58h]; this
0x180032d1c  lea     r8, aOnecoreVmDvSto_8; "onecore\\vm\\dv\\storage\\plan9\\dll\\w"...
0x180032d23  mov     edx, 31Ah; void *
0x180032d28  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180032d2d  mov     [rbp+20h], eax
0x180032d30  mov     rax, 0
0x180032d3a  add     rsp, 20h
0x180032d3e  pop     rbp
0x180032d3f  retn
```
