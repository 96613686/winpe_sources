# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000d86c`
- end: `0x18000d883`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION **this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ecf4`
- `0x1800109d8`

## callees

- `0x18000d86c`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18000d878`
- `KERNEL32!LeaveCriticalSection` at `0x18000d878`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        struct _RTL_CRITICAL_SECTION **this)
{
  struct _RTL_CRITICAL_SECTION *v1; // rcx

  v1 = *this;
  if ( v1 )
    LeaveCriticalSection(v1);
}

```

## disassembly

```asm
0x18000d86c  sub     rsp, 28h
0x18000d870  mov     rcx, [rcx]; lpCriticalSection
0x18000d873  test    rcx, rcx
0x18000d876  jz      short loc_18000D87E
0x18000d878  call    cs:LeaveCriticalSection
0x18000d87e  add     rsp, 28h
0x18000d882  retn
```
