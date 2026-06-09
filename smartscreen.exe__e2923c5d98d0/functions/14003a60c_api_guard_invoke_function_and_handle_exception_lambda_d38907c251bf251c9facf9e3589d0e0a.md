# api_guard::invoke_function_and_handle_exception__lambda_d38907c251bf251c9facf9e3589d0e0a__&_

- ea: `0x14003a60c`
- end: `0x14003a656`
- name: `api_guard::invoke_function_and_handle_exception__lambda_d38907c251bf251c9facf9e3589d0e0a__&_`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140040dc0`

## callees

- `0x14003a60c`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a641`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a634`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a634`

## pseudocode

```c
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_d38907c251bf251c9facf9e3589d0e0a____(
        HSTRING a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  HSTRING *v3; // rax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = a1;
  v2 = a2;
  v3 = (HSTRING *)windows::rt::create_hstring(&string, *a2 + 72LL);
  LODWORD(v2) = WindowsDuplicateString(*v3, *(HSTRING **)v2[1]);
  WindowsDeleteString(string);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003a60c  mov     [rsp+string], rcx
0x14003a611  push    rbx
0x14003a612  sub     rsp, 20h
0x14003a616  mov     rbx, rdx
0x14003a619  mov     rdx, [rdx]
0x14003a61c  add     rdx, 48h ; 'H'
0x14003a620  lea     rcx, [rsp+28h+string]
0x14003a625  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003a62a  mov     rdx, [rbx+8]
0x14003a62e  mov     rdx, [rdx]; newString
0x14003a631  mov     rcx, [rax]; string
0x14003a634  call    cs:__imp_WindowsDuplicateString
0x14003a63a  mov     ebx, eax
0x14003a63c  mov     rcx, [rsp+28h+string]; string
0x14003a641  call    cs:__imp_WindowsDeleteString
0x14003a647  mov     eax, ebx
0x14003a649  jmp     short loc_14003A64F
0x14003a64b  mov     eax, dword ptr [rsp+28h+string]
0x14003a64f  add     rsp, 20h
0x14003a653  pop     rbx
0x14003a654  retn
```
