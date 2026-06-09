# api_guard::invoke_function_and_handle_exception__lambda_d38907c251bf251c9facf9e3589d0e0a__&_

- ea: `0x14003bc50`
- end: `0x14003bca6`
- name: `api_guard::invoke_function_and_handle_exception__lambda_d38907c251bf251c9facf9e3589d0e0a__&_`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140042520`

## callees

- `0x14003bc50`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bc8b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bc78`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bc78`

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
0x14003bc50  mov     [rsp+string], rcx
0x14003bc55  push    rbx
0x14003bc56  sub     rsp, 20h
0x14003bc5a  mov     rbx, rdx
0x14003bc5d  mov     rdx, [rdx]
0x14003bc60  add     rdx, 48h ; 'H'
0x14003bc64  lea     rcx, [rsp+28h+string]
0x14003bc69  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003bc6e  mov     rdx, [rbx+8]
0x14003bc72  mov     rdx, [rdx]; newString
0x14003bc75  mov     rcx, [rax]; string
0x14003bc78  call    cs:__imp_WindowsDuplicateString
0x14003bc7f  nop     dword ptr [rax+rax+00h]
0x14003bc84  mov     ebx, eax
0x14003bc86  mov     rcx, [rsp+28h+string]; string
0x14003bc8b  call    cs:__imp_WindowsDeleteString
0x14003bc92  nop     dword ptr [rax+rax+00h]
0x14003bc97  mov     eax, ebx
0x14003bc99  jmp     short loc_14003BC9F
0x14003bc9b  mov     eax, dword ptr [rsp+28h+string]
0x14003bc9f  add     rsp, 20h
0x14003bca3  pop     rbx
0x14003bca4  retn
```
