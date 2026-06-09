# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180010228`
- end: `0x180010247`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x18003835b`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010234`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180010234`

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
0x180010228  push    rbx
0x18001022a  sub     rsp, 20h
0x18001022e  mov     rbx, rcx
0x180010231  mov     rcx, [rcx]; string
0x180010234  call    cs:__imp_WindowsDeleteString
0x18001023a  mov     qword ptr [rbx], 0
0x180010241  add     rsp, 20h
0x180010245  pop     rbx
0x180010246  retn
```
