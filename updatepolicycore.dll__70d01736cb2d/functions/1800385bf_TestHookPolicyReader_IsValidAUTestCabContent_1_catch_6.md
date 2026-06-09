# _TestHookPolicyReader::IsValidAUTestCabContent_::_1_::catch$6

- ea: `0x1800385bf`
- end: `0x1800385f6`
- name: `_TestHookPolicyReader::IsValidAUTestCabContent_::_1_::catch$6`
- size: `55`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001a190`

## string_xrefs

- `0x1800385d3`: `C:\__w\1\s\src\Client\policy\src\TestHooks\PolicyReader.cpp`

## pseudocode

```c
__int64 __fastcall TestHookPolicyReader::IsValidAUTestCabContent_::_1_::catch_6(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  wil::details::in1diag3::Log_CaughtException(
    *(wil::details::in1diag3 **)(a2 + 136),
    (void *)0xE5,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\policy\\src\\TestHooks\\PolicyReader.cpp",
    a4);
  return 0;
}

```

## disassembly

```asm
0x1800385bf  mov     [rsp+arg_8], rdx
0x1800385c4  push    rbp
0x1800385c5  sub     rsp, 20h
0x1800385c9  mov     rbp, rdx
0x1800385cc  mov     rcx, [rbp+88h]; this
0x1800385d3  lea     r8, aCW1SSrcClientP_2; "C:\\__w\\1\\s\\src\\Client\\policy\\src"...
0x1800385da  mov     edx, 0E5h; void *
0x1800385df  call    ?Log_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Log_CaughtException(void *,uint,char const *)
0x1800385e4  nop
0x1800385e5  mov     rax, 0
0x1800385ef  add     rsp, 20h
0x1800385f3  pop     rbp
0x1800385f4  retn
```
