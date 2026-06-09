# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18001dd54`
- end: `0x18001dd6b`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_1`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18001f1a4`

## callees

- `0x18001dd54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001dd60`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001dd60`

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
0x18001dd54  sub     rsp, 28h
0x18001dd58  mov     rcx, [rcx]; SRWLock
0x18001dd5b  test    rcx, rcx
0x18001dd5e  jz      short loc_18001DD66
0x18001dd60  call    cs:ReleaseSRWLockShared
0x18001dd66  add     rsp, 28h
0x18001dd6a  retn
```
