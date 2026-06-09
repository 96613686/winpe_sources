# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18001e958`
- end: `0x18001e99e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18001e5a0`
- `0x1800230c8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e997`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e973`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e973`

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
0x18001e958  mov     [rsp+arg_0], rbx
0x18001e95d  mov     [rsp+arg_8], rsi
0x18001e962  push    rdi
0x18001e963  sub     rsp, 20h
0x18001e967  mov     rbx, rcx
0x18001e96a  mov     edi, r8d
0x18001e96d  mov     rcx, [rcx]; string
0x18001e970  mov     rsi, rdx
0x18001e973  call    cs:__imp_WindowsDeleteString
0x18001e979  mov     r8, rbx
0x18001e97c  mov     qword ptr [rbx], 0
0x18001e983  mov     edx, edi
0x18001e985  mov     rcx, rsi
0x18001e988  mov     rbx, [rsp+28h+arg_0]
0x18001e98d  mov     rsi, [rsp+28h+arg_8]
0x18001e992  add     rsp, 20h
0x18001e996  pop     rdi
0x18001e997  jmp     cs:__imp_WindowsCreateString
```
