# api_guard::invoke_function_and_handle_exception__lambda_5cf637ae0f65dbab49ab4620979fb99a__&_

- ea: `0x14003ba4c`
- end: `0x14003bac6`
- name: `api_guard::invoke_function_and_handle_exception__lambda_5cf637ae0f65dbab49ab4620979fb99a__&_`
- size: `122`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140042270`

## callees

- `0x140004370`
- `0x14003ba4c`
- `0x14003be7c`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ba98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003ba98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003ba85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003ba85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_5cf637ae0f65dbab49ab4620979fb99a____(
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
0x14003ba4c  mov     [rsp+string], rcx
0x14003ba51  push    rbx
0x14003ba52  sub     rsp, 40h
0x14003ba56  mov     rbx, rdx
0x14003ba59  mov     rcx, [rdx]
0x14003ba5c  add     rcx, 88h
0x14003ba63  lea     rdx, [rsp+48h+var_28]
0x14003ba68  call    ??$value_or@AEAY00$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY00$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[1]>(ushort const (&)[1])
0x14003ba6d  nop
0x14003ba6e  mov     rdx, rax
0x14003ba71  lea     rcx, [rsp+48h+string]
0x14003ba76  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003ba7b  mov     rdx, [rbx+8]
0x14003ba7f  mov     rdx, [rdx]; newString
0x14003ba82  mov     rcx, [rax]; string
0x14003ba85  call    cs:__imp_WindowsDuplicateString
0x14003ba8c  nop     dword ptr [rax+rax+00h]
0x14003ba91  mov     ebx, eax
0x14003ba93  mov     rcx, [rsp+48h+string]; string
0x14003ba98  call    cs:__imp_WindowsDeleteString
0x14003ba9f  nop     dword ptr [rax+rax+00h]
0x14003baa4  mov     [rsp+48h+string], 0
0x14003baad  lea     rcx, [rsp+48h+var_28]; this
0x14003bab2  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003bab7  mov     eax, ebx
0x14003bab9  jmp     short loc_14003BABF
0x14003babb  mov     eax, dword ptr [rsp+48h+string]
0x14003babf  add     rsp, 40h
0x14003bac3  pop     rbx
0x14003bac4  retn
```
