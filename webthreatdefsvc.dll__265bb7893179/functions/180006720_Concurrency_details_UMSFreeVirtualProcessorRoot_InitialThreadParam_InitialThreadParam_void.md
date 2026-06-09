# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180006720`
- end: `0x180006737`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(HKEY *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001b32d`

## callees

- `0x180006720`

## import_xrefs

- `ADVAPI32!RegCloseKey` at `0x18000672c`
- `ADVAPI32!RegCloseKey` at `0x18000672c`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(HKEY *this)
{
  HKEY v1; // rcx

  v1 = *this;
  if ( v1 )
    RegCloseKey(v1);
}

```

## disassembly

```asm
0x180006720  sub     rsp, 28h
0x180006724  mov     rcx, [rcx]; hKey
0x180006727  test    rcx, rcx
0x18000672a  jz      short loc_180006732
0x18000672c  call    cs:RegCloseKey
0x180006732  add     rsp, 28h
0x180006736  retn
```
