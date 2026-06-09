# api_guard::invoke_function_and_handle_exception__lambda_197e2936c54a44fbf47f4af53352a813__&_

- ea: `0x14003b8c4`
- end: `0x14003b93b`
- name: `api_guard::invoke_function_and_handle_exception__lambda_197e2936c54a44fbf47f4af53352a813__&_`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140042550`

## callees

- `0x140004370`
- `0x14003b8c4`
- `0x14003be7c`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003b90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003b90d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003b8fa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003b8fa`

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
    v3 = std::optional<std::wstring>::value_or<unsigned short const (&)[1]>();
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
0x14003b8c4  mov     [rsp+string], rcx
0x14003b8c9  push    rbx
0x14003b8ca  sub     rsp, 40h
0x14003b8ce  mov     rbx, rdx
0x14003b8d1  mov     rcx, [rdx]
0x14003b8d4  add     rcx, 40h ; '@'
0x14003b8d8  lea     rdx, [rsp+48h+var_28]
0x14003b8dd  call    ??$value_or@AEAY00$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY00$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[1]>(ushort const (&)[1])
0x14003b8e2  nop
0x14003b8e3  mov     rdx, rax
0x14003b8e6  lea     rcx, [rsp+48h+string]
0x14003b8eb  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003b8f0  mov     rdx, [rbx+8]
0x14003b8f4  mov     rdx, [rdx]; newString
0x14003b8f7  mov     rcx, [rax]; string
0x14003b8fa  call    cs:__imp_WindowsDuplicateString
0x14003b901  nop     dword ptr [rax+rax+00h]
0x14003b906  mov     ebx, eax
0x14003b908  mov     rcx, [rsp+48h+string]; string
0x14003b90d  call    cs:__imp_WindowsDeleteString
0x14003b914  nop     dword ptr [rax+rax+00h]
0x14003b919  mov     [rsp+48h+string], 0
0x14003b922  lea     rcx, [rsp+48h+var_28]; this
0x14003b927  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003b92c  mov     eax, ebx
0x14003b92e  jmp     short loc_14003B934
0x14003b930  mov     eax, dword ptr [rsp+48h+string]
0x14003b934  add     rsp, 40h
0x14003b938  pop     rbx
0x14003b939  retn
```
