# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800085f0`
- end: `0x18000860f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18000c12b`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800085fc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800085fc`

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
0x1800085f0  push    rbx
0x1800085f2  sub     rsp, 20h
0x1800085f6  mov     rbx, rcx
0x1800085f9  mov     rcx, [rcx]; string
0x1800085fc  call    cs:__imp_WindowsDeleteString
0x180008602  mov     qword ptr [rbx], 0
0x180008609  add     rsp, 20h
0x18000860d  pop     rbx
0x18000860e  retn
```
