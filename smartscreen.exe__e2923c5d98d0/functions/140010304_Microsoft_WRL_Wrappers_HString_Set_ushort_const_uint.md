# Microsoft::WRL::Wrappers::HString::Set(ushort const *,uint)

- ea: `0x140010304`
- end: `0x14001034a`
- name: `?Set@HString@Wrappers@WRL@Microsoft@@QEAAJPEBGI@Z`
- size: `70`
- prototype: `__int64 __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this, const unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400051b0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140010343`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001031f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14001031f`

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
0x140010304  mov     [rsp+arg_0], rbx
0x140010309  mov     [rsp+arg_8], rsi
0x14001030e  push    rdi
0x14001030f  sub     rsp, 20h
0x140010313  mov     rbx, rcx
0x140010316  mov     edi, r8d
0x140010319  mov     rcx, [rcx]; string
0x14001031c  mov     rsi, rdx
0x14001031f  call    cs:__imp_WindowsDeleteString
0x140010325  mov     r8, rbx
0x140010328  mov     qword ptr [rbx], 0
0x14001032f  mov     edx, edi
0x140010331  mov     rcx, rsi
0x140010334  mov     rbx, [rsp+28h+arg_0]
0x140010339  mov     rsi, [rsp+28h+arg_8]
0x14001033e  add     rsp, 20h
0x140010342  pop     rdi
0x140010343  jmp     cs:__imp_WindowsCreateString
```
