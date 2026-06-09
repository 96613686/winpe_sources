# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x180080770`
- end: `0x18008078f`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180095125`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008077c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18008077c`

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
0x180080770  push    rbx
0x180080772  sub     rsp, 20h
0x180080776  mov     rbx, rcx
0x180080779  mov     rcx, [rcx]; string
0x18008077c  call    cs:__imp_WindowsDeleteString
0x180080782  mov     qword ptr [rbx], 0
0x180080789  add     rsp, 20h
0x18008078d  pop     rbx
0x18008078e  retn
```
