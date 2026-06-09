# api_guard::invoke_function_and_handle_exception__lambda_70257e1d7fa126ec78b6ec1e5226f155__&_

- ea: `0x14003bafc`
- end: `0x14003bb73`
- name: `api_guard::invoke_function_and_handle_exception__lambda_70257e1d7fa126ec78b6ec1e5226f155__&_`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140042460`

## callees

- `0x140004370`
- `0x14003bafc`
- `0x14003be7c`
- `0x140041c5c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bb45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003bb45`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bb32`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003bb32`

## pseudocode

```c
__int64 __fastcall api_guard::invoke_function_and_handle_exception__lambda_70257e1d7fa126ec78b6ec1e5226f155____(
        HSTRING a1,
        _QWORD *a2)
{
  _QWORD *v2; // rbx
  __int64 v3; // rax
  HSTRING *v4; // rax
  _BYTE v6[40]; // [rsp+20h] [rbp-28h] BYREF
  HSTRING string; // [rsp+50h] [rbp+8h] BYREF

  string = a1;
  v2 = a2;
  v3 = std::optional<std::wstring>::value_or<unsigned short const (&)[1]>(*a2 + 96LL, v6);
  v4 = (HSTRING *)windows::rt::create_hstring(&string, v3);
  LODWORD(v2) = WindowsDuplicateString(*v4, *(HSTRING **)v2[1]);
  WindowsDeleteString(string);
  string = 0;
  path::~path((path *)v6);
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14003bafc  mov     [rsp+string], rcx
0x14003bb01  push    rbx
0x14003bb02  sub     rsp, 40h
0x14003bb06  mov     rbx, rdx
0x14003bb09  mov     rcx, [rdx]
0x14003bb0c  add     rcx, 60h ; '`'
0x14003bb10  lea     rdx, [rsp+48h+var_28]
0x14003bb15  call    ??$value_or@AEAY00$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY00$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[1]>(ushort const (&)[1])
0x14003bb1a  nop
0x14003bb1b  mov     rdx, rax
0x14003bb1e  lea     rcx, [rsp+48h+string]
0x14003bb23  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003bb28  mov     rdx, [rbx+8]
0x14003bb2c  mov     rdx, [rdx]; newString
0x14003bb2f  mov     rcx, [rax]; string
0x14003bb32  call    cs:__imp_WindowsDuplicateString
0x14003bb39  nop     dword ptr [rax+rax+00h]
0x14003bb3e  mov     ebx, eax
0x14003bb40  mov     rcx, [rsp+48h+string]; string
0x14003bb45  call    cs:__imp_WindowsDeleteString
0x14003bb4c  nop     dword ptr [rax+rax+00h]
0x14003bb51  mov     [rsp+48h+string], 0
0x14003bb5a  lea     rcx, [rsp+48h+var_28]; this
0x14003bb5f  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003bb64  mov     eax, ebx
0x14003bb66  jmp     short loc_14003BB6C
0x14003bb68  mov     eax, dword ptr [rsp+48h+string]
0x14003bb6c  add     rsp, 40h
0x14003bb70  pop     rbx
0x14003bb71  retn
```
