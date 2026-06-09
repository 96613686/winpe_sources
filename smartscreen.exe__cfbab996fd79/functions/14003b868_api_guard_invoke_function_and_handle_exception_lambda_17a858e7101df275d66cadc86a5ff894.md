# api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894__&_

- ea: `0x14003b868`
- end: `0x14003b8be`
- name: `api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894__&_`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140042340`

## callees

- `0x14003b868`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003b8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003b8a3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003b890`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003b890`

## pseudocode

```c
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894____(
        HSTRING a1,
        __int64 a2)
{
  __int64 v3; // rdx
  HSTRING *v4; // rax
  unsigned int v5; // ebx
  wil *v6; // rcx
  __int64 result; // rax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = a1;
  v3 = *(_QWORD *)a2 + 64LL;
  try
  {
    v4 = (HSTRING *)windows::rt::create_hstring(&string, v3);
    v5 = WindowsDuplicateString(*v4, **(HSTRING ***)(a2 + 8));
    WindowsDeleteString(string);
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
0x14003b868  mov     [rsp+string], rcx
0x14003b86d  push    rbx
0x14003b86e  sub     rsp, 20h
0x14003b872  mov     rbx, rdx
0x14003b875  mov     rdx, [rdx]
0x14003b878  add     rdx, 40h ; '@'
0x14003b87c  lea     rcx, [rsp+28h+string]
0x14003b881  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003b886  mov     rdx, [rbx+8]
0x14003b88a  mov     rdx, [rdx]; newString
0x14003b88d  mov     rcx, [rax]; string
0x14003b890  call    cs:__imp_WindowsDuplicateString
0x14003b897  nop     dword ptr [rax+rax+00h]
0x14003b89c  mov     ebx, eax
0x14003b89e  mov     rcx, [rsp+28h+string]; string
0x14003b8a3  call    cs:__imp_WindowsDeleteString
0x14003b8aa  nop     dword ptr [rax+rax+00h]
0x14003b8af  mov     eax, ebx
0x14003b8b1  jmp     short loc_14003B8B7
0x14003b8b3  mov     eax, dword ptr [rsp+28h+string]
0x14003b8b7  add     rsp, 20h
0x14003b8bb  pop     rbx
0x14003b8bc  retn
```
