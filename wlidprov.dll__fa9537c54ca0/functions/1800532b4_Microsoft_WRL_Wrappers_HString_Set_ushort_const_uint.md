# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x1800532b4`
- end: `0x1800532fa`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180052f8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800532cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800532f3`

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
0x1800532b4  mov     [rsp+arg_0], rbx
0x1800532b9  mov     [rsp+arg_8], rsi
0x1800532be  push    rdi
0x1800532bf  sub     rsp, 20h
0x1800532c3  mov     rbx, rcx
0x1800532c6  mov     edi, r8d
0x1800532c9  mov     rcx, [rcx]; string
0x1800532cc  mov     rsi, rdx
0x1800532cf  call    cs:__imp_WindowsDeleteString
0x1800532d5  mov     r8, rbx
0x1800532d8  mov     qword ptr [rbx], 0
0x1800532df  mov     edx, edi
0x1800532e1  mov     rcx, rsi
0x1800532e4  mov     rbx, [rsp+28h+arg_0]
0x1800532e9  mov     rsi, [rsp+28h+arg_8]
0x1800532ee  add     rsp, 20h
0x1800532f2  pop     rdi
0x1800532f3  jmp     cs:__imp_WindowsCreateString
```
