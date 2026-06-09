# Windows::Internal::String::Initialize(HSTRING__ * const &)

- ea: `0x180034664`
- end: `0x1800346af`
- name: `?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z`
- size: `75`
- prototype: `__int64 __fastcall(Windows::Internal::String *__hidden this, HSTRING *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180030d00`

## callees

- `0x180034664`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034685`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003469c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003469c`

## pseudocode

```c
__int64 __fastcall Windows::Internal::String::Initialize(HSTRING *this, HSTRING *a2)
{
  HRESULT v3; // edi
  HSTRING v4; // rcx
  HSTRING newString; // [rsp+30h] [rbp+8h] BYREF

  newString = 0;
  v3 = WindowsDuplicateString(*a2, &newString);
  if ( v3 >= 0 )
  {
    v4 = *this;
    *this = newString;
    WindowsDeleteString(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180034664  mov     [rsp+arg_8], rbx
0x180034669  push    rdi
0x18003466a  sub     rsp, 20h
0x18003466e  mov     rax, rdx
0x180034671  mov     [rsp+28h+newString], 0
0x18003467a  mov     rbx, rcx
0x18003467d  lea     rdx, [rsp+28h+newString]; newString
0x180034682  mov     rcx, [rax]; string
0x180034685  call    cs:__imp_WindowsDuplicateString
0x18003468b  mov     edi, eax
0x18003468d  test    eax, eax
0x18003468f  js      short loc_1800346A2
0x180034691  mov     rdx, [rsp+28h+newString]
0x180034696  mov     rcx, [rbx]; string
0x180034699  mov     [rbx], rdx
0x18003469c  call    cs:__imp_WindowsDeleteString
0x1800346a2  mov     rbx, [rsp+28h+arg_8]
0x1800346a7  mov     eax, edi
0x1800346a9  add     rsp, 20h
0x1800346ad  pop     rdi
0x1800346ae  retn
```
