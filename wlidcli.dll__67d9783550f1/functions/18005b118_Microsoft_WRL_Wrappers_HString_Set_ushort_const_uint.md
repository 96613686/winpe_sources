# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x18005b118`
- end: `0x18005b15e`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18005ade8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18005b157`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b133`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18005b133`

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
0x18005b118  mov     [rsp+arg_0], rbx
0x18005b11d  mov     [rsp+arg_8], rsi
0x18005b122  push    rdi
0x18005b123  sub     rsp, 20h
0x18005b127  mov     rbx, rcx
0x18005b12a  mov     edi, r8d
0x18005b12d  mov     rcx, [rcx]; string
0x18005b130  mov     rsi, rdx
0x18005b133  call    cs:__imp_WindowsDeleteString
0x18005b139  mov     r8, rbx
0x18005b13c  mov     qword ptr [rbx], 0
0x18005b143  mov     edx, edi
0x18005b145  mov     rcx, rsi
0x18005b148  mov     rbx, [rsp+28h+arg_0]
0x18005b14d  mov     rsi, [rsp+28h+arg_8]
0x18005b152  add     rsp, 20h
0x18005b156  pop     rdi
0x18005b157  jmp     cs:__imp_WindowsCreateString
```
