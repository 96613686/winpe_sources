# api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894__&_

- ea: `0x14003a260`
- end: `0x14003a2aa`
- name: `api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894__&_`
- size: `74`
- prototype: `__int64 __fastcall(HSTRING, __int64)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140040be0`

## callees

- `0x14003a260`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a295`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a288`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a288`

## pseudocode

```c
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_17a858e7101df275d66cadc86a5ff894____(
        HSTRING a1,
        __int64 a2)
{
  HSTRING *hstring; // rax
  unsigned int v4; // ebx
  wil *v5; // rcx
  __int64 result; // rax

  try
  {
    hstring = (HSTRING *)windows::rt::create_hstring();
    v4 = WindowsDuplicateString(*hstring, **(HSTRING ***)(a2 + 8));
    WindowsDeleteString(a1);
    result = v4;
  }
  catch ( ... )
  {
    return (unsigned int)wil::ResultFromCaughtException(v5);
  }
  return result;
}

```

## disassembly

```asm
0x14003a260  mov     [rsp+string], rcx
0x14003a265  push    rbx
0x14003a266  sub     rsp, 20h
0x14003a26a  mov     rbx, rdx
0x14003a26d  mov     rdx, [rdx]
0x14003a270  add     rdx, 40h ; '@'
0x14003a274  lea     rcx, [rsp+28h+string]
0x14003a279  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003a27e  mov     rdx, [rbx+8]
0x14003a282  mov     rdx, [rdx]; newString
0x14003a285  mov     rcx, [rax]; string
0x14003a288  call    cs:__imp_WindowsDuplicateString
0x14003a28e  mov     ebx, eax
0x14003a290  mov     rcx, [rsp+28h+string]; string
0x14003a295  call    cs:__imp_WindowsDeleteString
0x14003a29b  mov     eax, ebx
0x14003a29d  jmp     short loc_14003A2A3
0x14003a29f  mov     eax, dword ptr [rsp+28h+string]
0x14003a2a3  add     rsp, 20h
0x14003a2a7  pop     rbx
0x14003a2a8  retn
```
