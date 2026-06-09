# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140011eb0`
- end: `0x140011ecf`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140063670`
- `0x140063800`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140011ebc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140011ebc`

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
0x140011eb0  push    rbx
0x140011eb2  sub     rsp, 20h
0x140011eb6  mov     rbx, rcx
0x140011eb9  mov     rcx, [rcx]; string
0x140011ebc  call    cs:__imp_WindowsDeleteString
0x140011ec2  mov     qword ptr [rbx], 0
0x140011ec9  add     rsp, 20h
0x140011ecd  pop     rbx
0x140011ece  retn
```
