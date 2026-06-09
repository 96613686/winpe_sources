# _CommandImpl::ProcessExternalCommand_AnalyzeCommandTraits__::_1_::catch$3

- ea: `0x180015ac6`
- end: `0x180015b5a`
- name: `_CommandImpl::ProcessExternalCommand_AnalyzeCommandTraits__::_1_::catch$3`
- size: `148`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x180008f78`
- `0x18000917c`
- `0x18000bdfc`
- `0x18000bf94`

## string_xrefs

- `0x180015ae6`: `updiag.dll`
- `0x180015b0d`: `updiag.dll`
- `0x180015b01`: `ProcessAnalyzeCommand`
- `0x180015b20`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`
- `0x180015b35`: `C:\__w\1\s\src\updatecli\libs\main\CommandImpl.hpp`
- `0x180015b19`: `Failed to get external command function from %ws!%hs`

## pseudocode

```c
__int64 __fastcall CommandImpl::ProcessExternalCommand_AnalyzeCommandTraits__::_1_::catch_3(__int64 a1, __int64 a2)
{
  __int64 v3; // rax
  __int64 v4; // rax
  const char *v5; // r9

  v3 = std::operator<<<wchar_t,std::char_traits<wchar_t>>((__int64)&std::wcerr, (__int64)L"! ");
  v4 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v3, (__int64)L"updiag.dll");
  std::endl<wchar_t,std::char_traits<wchar_t>>(v4);
  wil::details::in1diag3::Log_CaughtExceptionMsg(
    *(wil::details::in1diag3 **)(a2 + 88),
    (void *)0xB8,
    (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
    "Failed to get external command function from %ws!%hs",
    L"updiag.dll",
    "ProcessAnalyzeCommand");
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 88),
                           (void *)0xB9,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
                           v5);
  return 0;
}

```

## disassembly

```asm
0x180015ac6  mov     [rsp+arg_8], rdx
0x180015acb  push    rbp
0x180015acc  sub     rsp, 30h
0x180015ad0  mov     rbp, rdx
0x180015ad3  lea     rdx, asc_1800184B0; "! "
0x180015ada  lea     rcx, ?wcerr@std@@3V?$basic_ostream@_WU?$char_traits@_W@std@@@1@A; std::wostream std::wcerr
0x180015ae1  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180015ae6  lea     rdx, aUpdiagDll; "updiag.dll"
0x180015aed  mov     rcx, rax
0x180015af0  call    ??$?6_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@PEB_W@Z; std::operator<<<wchar_t,std::char_traits<wchar_t>>(std::wostream &,wchar_t const *)
0x180015af5  mov     rcx, rax
0x180015af8  call    ??$endl@_WU?$char_traits@_W@std@@@std@@YAAEAV?$basic_ostream@_WU?$char_traits@_W@std@@@0@AEAV10@@Z; std::endl<wchar_t,std::char_traits<wchar_t>>(std::wostream &)
0x180015afd  mov     rcx, [rbp+58h]; this
0x180015b01  lea     rax, aProcessanalyze; "ProcessAnalyzeCommand"
0x180015b08  mov     [rsp+38h+var_10], rax
0x180015b0d  lea     rax, aUpdiagDll; "updiag.dll"
0x180015b14  mov     [rsp+38h+var_18], rax; char *
0x180015b19  lea     r9, aFailedToGetExt; "Failed to get external command function"...
0x180015b20  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180015b27  mov     edx, 0B8h; void *
0x180015b2c  call    ?Log_CaughtExceptionMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Log_CaughtExceptionMsg(void *,uint,char const *,char const *,...)
0x180015b31  mov     rcx, [rbp+58h]; this
0x180015b35  lea     r8, aCW1SSrcUpdatec_1; "C:\\__w\\1\\s\\src\\updatecli\\libs\\ma"...
0x180015b3c  mov     edx, 0B9h; void *
0x180015b41  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x180015b46  mov     [rbp+30h], eax
0x180015b49  mov     rax, 0
0x180015b53  add     rsp, 30h
0x180015b57  pop     rbp
0x180015b58  retn
```
