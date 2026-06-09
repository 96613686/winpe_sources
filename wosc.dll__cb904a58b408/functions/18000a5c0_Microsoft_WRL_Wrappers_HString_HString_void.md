# Microsoft::WRL::Wrappers::HString::~HString(void)

- ea: `0x18000a5c0`
- end: `0x18000a5df`
- name: `??1HString@Wrappers@WRL@Microsoft@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `23`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x1800552df`
- `0x18005561d`
- `0x180055653`
- `0x1800558e6`
- `0x180055a41`
- `0x180056881`
- `0x18005689a`
- `0x1800568fe`
- `0x180056917`
- `0x180056962`
- `0x180056d55`
- `0x180056f62`
- `0x180056f78`
- `0x180056f8e`
- `0x180057044`
- `0x1800571ab`
- `0x1800572a9`
- `0x1800572cd`
- `0x1800572f9`
- `0x1800581d0`
- `0x180058337`
- `0x1800584a1`
- `0x1800587f6`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5cc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18000a5cc`

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
0x18000a5c0  push    rbx
0x18000a5c2  sub     rsp, 20h
0x18000a5c6  mov     rbx, rcx
0x18000a5c9  mov     rcx, [rcx]; string
0x18000a5cc  call    cs:__imp_WindowsDeleteString
0x18000a5d2  mov     qword ptr [rbx], 0
0x18000a5d9  add     rsp, 20h
0x18000a5dd  pop     rbx
0x18000a5de  retn
```
