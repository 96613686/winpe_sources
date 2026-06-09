# api_guard::invoke_function_and_handle_exception__lambda_b76d9fc2f8f8aac7e097c1fb0852fccd__&_

- ea: `0x14003bbd0`
- end: `0x14003bc26`
- name: `api_guard::invoke_function_and_handle_exception__lambda_b76d9fc2f8f8aac7e097c1fb0852fccd__&_`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140042430`

## callees

- `0x14003bbd0`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bc0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bc0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bbf8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bbf8`

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
0x14003bbd0  mov     [rsp+string], rcx
0x14003bbd5  push    rbx
0x14003bbd6  sub     rsp, 20h
0x14003bbda  mov     rbx, rdx
0x14003bbdd  mov     rdx, [rdx]
0x14003bbe0  add     rdx, 68h ; 'h'
0x14003bbe4  lea     rcx, [rsp+28h+string]
0x14003bbe9  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003bbee  mov     rdx, [rbx+8]
0x14003bbf2  mov     rdx, [rdx]; newString
0x14003bbf5  mov     rcx, [rax]; string
0x14003bbf8  call    cs:__imp_WindowsDuplicateString
0x14003bbff  nop     dword ptr [rax+rax+00h]
0x14003bc04  mov     ebx, eax
0x14003bc06  mov     rcx, [rsp+28h+string]; string
0x14003bc0b  call    cs:__imp_WindowsDeleteString
0x14003bc12  nop     dword ptr [rax+rax+00h]
0x14003bc17  mov     eax, ebx
0x14003bc19  jmp     short loc_14003BC1F
0x14003bc1b  mov     eax, dword ptr [rsp+28h+string]
0x14003bc1f  add     rsp, 20h
0x14003bc23  pop     rbx
0x14003bc24  retn
```
