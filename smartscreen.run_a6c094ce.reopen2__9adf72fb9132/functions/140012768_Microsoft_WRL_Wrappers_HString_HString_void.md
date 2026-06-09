# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x140012768`
- end: `0x14001278e`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `38`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x140065330`
- `0x1400654c0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012774`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140012774`

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
0x140012768  push    rbx
0x14001276a  sub     rsp, 20h
0x14001276e  mov     rbx, rcx
0x140012771  mov     rcx, [rcx]; string
0x140012774  call    cs:__imp_WindowsDeleteString
0x14001277b  nop     dword ptr [rax+rax+00h]
0x140012780  mov     qword ptr [rbx], 0
0x140012787  add     rsp, 20h
0x14001278b  pop     rbx
0x14001278c  retn
```
