# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x180061964`
- end: `0x1800619aa`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800615c0`
- `0x180061718`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006197f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18006197f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800619a3`

## pseudocode

```c
HRESULT __fastcall Microsoft::WRL::Wrappers::HString::Set(HSTRING *this, const unsigned __int16 *a2, UINT32 a3)
{
  WindowsDeleteString(*this);
  *this = 0;
  return WindowsCreateString(a2, a3, this);
}

```

## disassembly

```asm
0x180061964  mov     [rsp+arg_0], rbx
0x180061969  mov     [rsp+arg_8], rsi
0x18006196e  push    rdi
0x18006196f  sub     rsp, 20h
0x180061973  mov     rbx, rcx
0x180061976  mov     edi, r8d
0x180061979  mov     rcx, [rcx]; string
0x18006197c  mov     rsi, rdx
0x18006197f  call    cs:__imp_WindowsDeleteString
0x180061985  mov     r8, rbx
0x180061988  mov     qword ptr [rbx], 0
0x18006198f  mov     edx, edi
0x180061991  mov     rcx, rsi
0x180061994  mov     rbx, [rsp+28h+arg_0]
0x180061999  mov     rsi, [rsp+28h+arg_8]
0x18006199e  add     rsp, 20h
0x1800619a2  pop     rdi
0x1800619a3  jmp     cs:__imp_WindowsCreateString
```
