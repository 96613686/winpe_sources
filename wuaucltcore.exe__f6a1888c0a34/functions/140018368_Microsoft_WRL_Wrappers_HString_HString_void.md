# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140018368`
- end: `0x140018387`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `3`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1400219bd`
- `0x140021a05`
- `0x140021b13`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018374`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140018374`

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
0x140018368  push    rbx
0x14001836a  sub     rsp, 20h
0x14001836e  mov     rbx, rcx
0x140018371  mov     rcx, [rcx]; string
0x140018374  call    cs:__imp_WindowsDeleteString
0x14001837a  mov     qword ptr [rbx], 0
0x140018381  add     rsp, 20h
0x140018385  pop     rbx
0x140018386  retn
```
