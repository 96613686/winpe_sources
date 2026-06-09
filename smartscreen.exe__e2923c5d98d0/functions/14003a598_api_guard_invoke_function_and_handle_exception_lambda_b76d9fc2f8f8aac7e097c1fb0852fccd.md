# api_guard::invoke_function_and_handle_exception__lambda_b76d9fc2f8f8aac7e097c1fb0852fccd__&_

- ea: `0x14003a598`
- end: `0x14003a5e2`
- name: `api_guard::invoke_function_and_handle_exception__lambda_b76d9fc2f8f8aac7e097c1fb0852fccd__&_`
- size: `74`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140040cd0`

## callees

- `0x14003a598`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a5cd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a5c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a5c0`

## pseudocode

```c
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_b76d9fc2f8f8aac7e097c1fb0852fccd____(
        HSTRING a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  HSTRING *v3; // rax
  HSTRING string; // [rsp+30h] [rbp+8h] BYREF

  string = a1;
  v2 = a2;
  v3 = (HSTRING *)windows::rt::create_hstring(&string, *a2 + 104LL);
  LODWORD(v2) = WindowsDuplicateString(*v3, *(HSTRING **)v2[1]);
  WindowsDeleteString(string);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003a598  mov     [rsp+string], rcx
0x14003a59d  push    rbx
0x14003a59e  sub     rsp, 20h
0x14003a5a2  mov     rbx, rdx
0x14003a5a5  mov     rdx, [rdx]
0x14003a5a8  add     rdx, 68h ; 'h'
0x14003a5ac  lea     rcx, [rsp+28h+string]
0x14003a5b1  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003a5b6  mov     rdx, [rbx+8]
0x14003a5ba  mov     rdx, [rdx]; newString
0x14003a5bd  mov     rcx, [rax]; string
0x14003a5c0  call    cs:__imp_WindowsDuplicateString
0x14003a5c6  mov     ebx, eax
0x14003a5c8  mov     rcx, [rsp+28h+string]; string
0x14003a5cd  call    cs:__imp_WindowsDeleteString
0x14003a5d3  mov     eax, ebx
0x14003a5d5  jmp     short loc_14003A5DB
0x14003a5d7  mov     eax, dword ptr [rsp+28h+string]
0x14003a5db  add     rsp, 20h
0x14003a5df  pop     rbx
0x14003a5e0  retn
```
