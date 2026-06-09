# api_guard::invoke_function_and_handle_exception__lambda_197e2936c54a44fbf47f4af53352a813__&_

- ea: `0x14003a2b0`
- end: `0x14003a31b`
- name: `api_guard::invoke_function_and_handle_exception__lambda_197e2936c54a44fbf47f4af53352a813__&_`
- size: `107`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140040df0`

## callees

- `0x140004190`
- `0x14003a2b0`
- `0x14003a828`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a2f3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a2e6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a2e6`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_197e2936c54a44fbf47f4af53352a813____(
        HSTRING a1,
        __int64 a2)
{
  __int64 v3; // rdx
  HSTRING *v4; // rax
  unsigned int v5; // ebx
  wil *v6; // rcx
  __int64 result; // rax
  _BYTE v8[40]; // [rsp+20h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  string = a1;
  try
  {
    v3 = std::optional<std::wstring>::value_or<unsigned short const (&)[1]>(*(_QWORD *)a2 + 64LL, v8);
    v4 = (HSTRING *)windows::rt::create_hstring(&string, v3);
    v5 = WindowsDuplicateString(*v4, **(HSTRING ***)(a2 + 8));
    WindowsDeleteString(string);
    string = 0;
    path::~path((path *)v8);
    result = v5;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v6);
  }
  return result;
}

```

## disassembly

```asm
0x14003a2b0  mov     [rsp+string], rcx
0x14003a2b5  push    rbx
0x14003a2b6  sub     rsp, 40h
0x14003a2ba  mov     rbx, rdx
0x14003a2bd  mov     rcx, [rdx]
0x14003a2c0  add     rcx, 40h ; '@'
0x14003a2c4  lea     rdx, [rsp+48h+var_28]
0x14003a2c9  call    ??$value_or@AEAY00$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY00$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[1]>(ushort const (&)[1])
0x14003a2ce  nop
0x14003a2cf  mov     rdx, rax
0x14003a2d2  lea     rcx, [rsp+48h+string]
0x14003a2d7  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003a2dc  mov     rdx, [rbx+8]
0x14003a2e0  mov     rdx, [rdx]; newString
0x14003a2e3  mov     rcx, [rax]; string
0x14003a2e6  call    cs:__imp_WindowsDuplicateString
0x14003a2ec  mov     ebx, eax
0x14003a2ee  mov     rcx, [rsp+48h+string]; string
0x14003a2f3  call    cs:__imp_WindowsDeleteString
0x14003a2f9  mov     [rsp+48h+string], 0
0x14003a302  lea     rcx, [rsp+48h+var_28]; this
0x14003a307  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003a30c  mov     eax, ebx
0x14003a30e  jmp     short loc_14003A314
0x14003a310  mov     eax, dword ptr [rsp+48h+string]
0x14003a314  add     rsp, 40h
0x14003a318  pop     rbx
0x14003a319  retn
```
