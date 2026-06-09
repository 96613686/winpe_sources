# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000d8ac`
- end: `0x18000d8c3`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_2`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ecf4`

## callees

- `0x18000d8ac`

## import_xrefs

- `KERNEL32!ReleaseSRWLockShared` at `0x18000d8b8`
- `KERNEL32!ReleaseSRWLockShared` at `0x18000d8b8`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        RTL_SRWLOCK **this)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *this;
  if ( v1 )
    ReleaseSRWLockShared(v1);
}

```

## disassembly

```asm
0x18000d8ac  sub     rsp, 28h
0x18000d8b0  mov     rcx, [rcx]; SRWLock
0x18000d8b3  test    rcx, rcx
0x18000d8b6  jz      short loc_18000D8BE
0x18000d8b8  call    cs:ReleaseSRWLockShared
0x18000d8be  add     rsp, 28h
0x18000d8c2  retn
```
