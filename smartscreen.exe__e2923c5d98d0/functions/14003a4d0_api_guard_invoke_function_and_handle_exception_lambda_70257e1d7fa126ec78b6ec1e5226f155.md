# api_guard::invoke_function_and_handle_exception__lambda_70257e1d7fa126ec78b6ec1e5226f155__&_

- ea: `0x14003a4d0`
- end: `0x14003a53b`
- name: `api_guard::invoke_function_and_handle_exception__lambda_70257e1d7fa126ec78b6ec1e5226f155__&_`
- size: `107`
- prototype: `__int64 __fastcall(HSTRING, _QWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x140040d00`

## callees

- `0x140004190`
- `0x14003a4d0`
- `0x14003a828`
- `0x140040514`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14003a513`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a506`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14003a506`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x14003a4d0  mov     [rsp+string], rcx
0x14003a4d5  push    rbx
0x14003a4d6  sub     rsp, 40h
0x14003a4da  mov     rbx, rdx
0x14003a4dd  mov     rcx, [rdx]
0x14003a4e0  add     rcx, 60h ; '`'
0x14003a4e4  lea     rdx, [rsp+48h+var_28]
0x14003a4e9  call    ??$value_or@AEAY00$$CBG@?$optional@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@std@@QEGBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAY00$$CBG@Z; std::optional<std::wstring>::value_or<ushort const (&)[1]>(ushort const (&)[1])
0x14003a4ee  nop
0x14003a4ef  mov     rdx, rax
0x14003a4f2  lea     rcx, [rsp+48h+string]
0x14003a4f7  call    ?create_hstring@rt@windows@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; windows::rt::create_hstring(std::wstring const &)
0x14003a4fc  mov     rdx, [rbx+8]
0x14003a500  mov     rdx, [rdx]; newString
0x14003a503  mov     rcx, [rax]; string
0x14003a506  call    cs:__imp_WindowsDuplicateString
0x14003a50c  mov     ebx, eax
0x14003a50e  mov     rcx, [rsp+48h+string]; string
0x14003a513  call    cs:__imp_WindowsDeleteString
0x14003a519  mov     [rsp+48h+string], 0
0x14003a522  lea     rcx, [rsp+48h+var_28]; this
0x14003a527  call    ??1path@@QEAA@XZ; path::~path(void)
0x14003a52c  mov     eax, ebx
0x14003a52e  jmp     short loc_14003A534
0x14003a530  mov     eax, dword ptr [rsp+48h+string]
0x14003a534  add     rsp, 40h
0x14003a538  pop     rbx
0x14003a539  retn
```
