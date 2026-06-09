# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x1800144b0`
- end: `0x1800144cf`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Microsoft::WRL::Wrappers::HString *__hidden this)`
- caller_count: `13`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180030f70`
- `0x1800310a0`
- `0x1800310c0`
- `0x180031180`
- `0x1800311a0`
- `0x180031200`
- `0x180031260`
- `0x1800315e4`
- `0x180031730`
- `0x180031742`
- `0x180031754`
- `0x180031766`
- `0x180031bed`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800144bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800144bc`

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
0x1800144b0  push    rbx
0x1800144b2  sub     rsp, 20h
0x1800144b6  mov     rbx, rcx
0x1800144b9  mov     rcx, [rcx]; string
0x1800144bc  call    cs:__imp_WindowsDeleteString
0x1800144c2  mov     qword ptr [rbx], 0
0x1800144c9  add     rsp, 20h
0x1800144cd  pop     rbx
0x1800144ce  retn
```
