# CommandImpl::ProcessExternalCommand<AnalyzeCommandTraits>(wchar_t const *,wchar_t const *)

- ea: `0x180008f30`
- end: `0x180008f72`
- name: `??$ProcessExternalCommand@UAnalyzeCommandTraits@@@CommandImpl@@CAJPEB_W0@Z`
- size: `66`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000892c`
- `0x180008f30`
- `0x1800148e0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008f5d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008f5d`

## pseudocode

```c
__int64 __fastcall CommandImpl::ProcessExternalCommand<AnalyzeCommandTraits>(__int64 a1)
{
  unsigned int v2; // ebx
  __int64 result; // rax
  __int64 v4; // rax
  __int64 v5; // rax
  const char *v6; // r9
  HMODULE hLibModule[4]; // [rsp+38h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  try
  {
    CommandImpl::GetExternalCommandFunction(hLibModule);
    v2 = ((__int64 (__fastcall *)(__int64))hLibModule[1])(a1);
    if ( hLibModule[0] )
      FreeLibrary(hLibModule[0]);
    result = v2;
  }
  catch ( ... )
  {
    v4 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(&std::wcerr, L"! ");
    v5 = std::operator<<<wchar_t,std::char_traits<wchar_t>>(v4, L"updiag.dll");
    std::endl<wchar_t,std::char_traits<wchar_t>>(v5);
    wil::details::in1diag3::Log_CaughtExceptionMsg(
      retaddr,
      (void *)0xB8,
      (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
      "Failed to get external command function from %ws!%hs",
      L"updiag.dll",
      "ProcessAnalyzeCommand");
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB9,
                           (unsigned int)"C:\\__w\\1\\s\\src\\updatecli\\libs\\main\\CommandImpl.hpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180008f30  push    rbx
0x180008f32  sub     rsp, 50h
0x180008f36  mov     rbx, rcx
0x180008f39  lea     rcx, [rsp+58h+hLibModule]
0x180008f3e  call    ?GetExternalCommandFunction@CommandImpl@@CA?AU?$pair@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@P6AJPEB_W@Z@std@@PEB_WPEBD@Z; CommandImpl::GetExternalCommandFunction(wchar_t const *,char const *)
0x180008f43  nop
0x180008f44  mov     rcx, rbx
0x180008f47  mov     rax, [rsp+58h+var_18]
0x180008f4c  call    _guard_dispatch_icall
0x180008f51  mov     ebx, eax
0x180008f53  mov     rcx, [rsp+58h+hLibModule]; hLibModule
0x180008f58  test    rcx, rcx
0x180008f5b  jz      short loc_180008F63
0x180008f5d  call    cs:__imp_FreeLibrary
0x180008f63  mov     eax, ebx
0x180008f65  jmp     short loc_180008F6B
0x180008f67  mov     eax, [rsp+58h+var_28]
0x180008f6b  add     rsp, 50h
0x180008f6f  pop     rbx
0x180008f70  retn
```
