# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18002fba0`
- end: `0x18002fbbf`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180040adf`
- `0x180040b03`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbac`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002fbac`

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
0x18002fba0  push    rbx
0x18002fba2  sub     rsp, 20h
0x18002fba6  mov     rbx, rcx
0x18002fba9  mov     rcx, [rcx]; string
0x18002fbac  call    cs:__imp_WindowsDeleteString
0x18002fbb2  mov     qword ptr [rbx], 0
0x18002fbb9  add     rsp, 20h
0x18002fbbd  pop     rbx
0x18002fbbe  retn
```
