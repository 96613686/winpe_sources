# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180019bf8`
- end: `0x180019c0f`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_5`
- size: `23`
- prototype: `void __fastcall(HSTRING *this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180019bc4`
- `0x180019fa8`

## callees

- `0x180019bf8`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180019c04`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        HSTRING *this)
{
  HSTRING v1; // rcx

  v1 = *this;
  if ( v1 )
    WindowsDeleteString(v1);
}

```

## disassembly

```asm
0x180019bf8  sub     rsp, 28h
0x180019bfc  mov     rcx, [rcx]; string
0x180019bff  test    rcx, rcx
0x180019c02  jz      short loc_180019C0A
0x180019c04  call    cs:WindowsDeleteString
0x180019c0a  add     rsp, 28h
0x180019c0e  retn
```
