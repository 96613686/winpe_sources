# _CommandImpl::ShowDetailedHelp_::_1_::catch$3

- ea: `0x180015a03`
- end: `0x180015a4e`
- name: `_CommandImpl::ShowDetailedHelp_::_1_::catch$3`
- size: `75`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000bdfc`

## string_xrefs

- `0x180015a2b`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`

## pseudocode

```c
__int64 __fastcall CommandImpl::ShowDetailedHelp_::_1_::catch_3(__int64 a1, __int64 a2)
{
  int v3; // [rsp+28h] [rbp-10h]

  v3 = *(_DWORD *)(a2 + 48);
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 120),
    (void *)0xD6,
    (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
    "Failed to load detailed help message for %ws with id %u",
    *(const char **)(a2 + 64),
    v3);
  return 0;
}

```

## disassembly

```asm
0x180015a03  mov     [rsp+arg_8], rdx
0x180015a08  push    rbp
0x180015a09  sub     rsp, 30h
0x180015a0d  mov     rbp, rdx
0x180015a10  mov     rcx, [rbp+78h]; this
0x180015a14  mov     eax, [rbp+30h]
0x180015a17  mov     [rsp+38h+var_10], eax
0x180015a1b  mov     rax, [rbp+40h]
0x180015a1f  mov     [rsp+38h+var_18], rax; char *
0x180015a24  lea     r9, aFailedToLoadDe; "Failed to load detailed help message fo"...
0x180015a2b  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180015a32  mov     edx, 0D6h; void *
0x180015a37  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180015a3c  nop
0x180015a3d  mov     rax, 0
0x180015a47  add     rsp, 30h
0x180015a4b  pop     rbp
0x180015a4c  retn
```
