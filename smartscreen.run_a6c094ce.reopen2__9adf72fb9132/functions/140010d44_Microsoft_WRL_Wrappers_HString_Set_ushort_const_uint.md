# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x140010d44`
- end: `0x140010d95`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `81`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400054f0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140010d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140010d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140010d5f`

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
0x140010d44  mov     [rsp+arg_0], rbx
0x140010d49  mov     [rsp+arg_8], rsi
0x140010d4e  push    rdi
0x140010d4f  sub     rsp, 20h
0x140010d53  mov     rbx, rcx
0x140010d56  mov     edi, r8d
0x140010d59  mov     rcx, [rcx]; string
0x140010d5c  mov     rsi, rdx
0x140010d5f  call    cs:__imp_WindowsDeleteString
0x140010d66  nop     dword ptr [rax+rax+00h]
0x140010d6b  mov     r8, rbx
0x140010d6e  mov     qword ptr [rbx], 0
0x140010d75  mov     edx, edi
0x140010d77  mov     rcx, rsi
0x140010d7a  mov     rbx, [rsp+28h+arg_0]
0x140010d7f  mov     rsi, [rsp+28h+arg_8]
0x140010d84  add     rsp, 20h
0x140010d88  pop     rdi
0x140010d89  jmp     cs:__imp_WindowsCreateString
```
