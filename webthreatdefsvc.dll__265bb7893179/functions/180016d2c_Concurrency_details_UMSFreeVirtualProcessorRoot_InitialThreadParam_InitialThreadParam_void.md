# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180016d2c`
- end: `0x180016d43`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_4`
- size: `23`
- prototype: `void __fastcall(HMODULE *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001bb80`

## callees

- `0x180016d2c`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180016d38`
- `KERNEL32!FreeLibrary` at `0x180016d38`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        HMODULE *this)
{
  HMODULE v1; // rcx

  v1 = *this;
  if ( v1 )
    FreeLibrary(v1);
}

```

## disassembly

```asm
0x180016d2c  sub     rsp, 28h
0x180016d30  mov     rcx, [rcx]; hLibModule
0x180016d33  test    rcx, rcx
0x180016d36  jz      short loc_180016D3E
0x180016d38  call    cs:FreeLibrary
0x180016d3e  add     rsp, 28h
0x180016d42  retn
```
