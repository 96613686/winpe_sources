# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18002ade8`
- end: `0x18002ae2e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180025180`
- `0x18002b29c`
- `0x18002e110`
- `0x180050b28`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18002ae27`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae03`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002ae03`

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
0x18002ade8  mov     [rsp+arg_0], rbx
0x18002aded  mov     [rsp+arg_8], rsi
0x18002adf2  push    rdi
0x18002adf3  sub     rsp, 20h
0x18002adf7  mov     rbx, rcx
0x18002adfa  mov     edi, r8d
0x18002adfd  mov     rcx, [rcx]; string
0x18002ae00  mov     rsi, rdx
0x18002ae03  call    cs:__imp_WindowsDeleteString
0x18002ae09  mov     r8, rbx
0x18002ae0c  mov     qword ptr [rbx], 0
0x18002ae13  mov     edx, edi
0x18002ae15  mov     rcx, rsi
0x18002ae18  mov     rbx, [rsp+28h+arg_0]
0x18002ae1d  mov     rsi, [rsp+28h+arg_8]
0x18002ae22  add     rsp, 20h
0x18002ae26  pop     rdi
0x18002ae27  jmp     cs:__imp_WindowsCreateString
```
