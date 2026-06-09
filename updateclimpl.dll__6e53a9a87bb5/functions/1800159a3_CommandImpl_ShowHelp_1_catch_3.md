# _CommandImpl::ShowHelp_::_1_::catch$3

- ea: `0x1800159a3`
- end: `0x1800159d9`
- name: `_CommandImpl::ShowHelp_::_1_::catch$3`
- size: `54`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, const char *)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000bf94`

## string_xrefs

- `0x1800159b4`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`

## pseudocode

```c
__int64 __fastcall CommandImpl::ShowHelp_::_1_::catch_3(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 96) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 72),
                           (void *)0xCC,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x1800159a3  mov     [rsp+arg_8], rdx
0x1800159a8  push    rbp
0x1800159a9  sub     rsp, 20h
0x1800159ad  mov     rbp, rdx
0x1800159b0  mov     rcx, [rbp+48h]; this
0x1800159b4  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x1800159bb  mov     edx, 0CCh; void *
0x1800159c0  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x1800159c5  mov     [rbp+60h], eax
0x1800159c8  mov     rax, 0
0x1800159d2  add     rsp, 20h
0x1800159d6  pop     rbp
0x1800159d7  retn
```
