# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180021950`
- end: `0x18002196f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180028b79`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002195c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002195c`

## pseudocode

```c
void __fastcall Microsoft::WRL::Wrappers::HString::~HString(HSTRING *this)
{
  WindowsDeleteString(*this);
  *this = 0;
}

```

## disassembly

```asm
0x180021950  push    rbx
0x180021952  sub     rsp, 20h
0x180021956  mov     rbx, rcx
0x180021959  mov     rcx, [rcx]; string
0x18002195c  call    cs:__imp_WindowsDeleteString
0x180021962  mov     qword ptr [rbx], 0
0x180021969  add     rsp, 20h
0x18002196d  pop     rbx
0x18002196e  retn
```
