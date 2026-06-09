# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18000d88c`
- end: `0x18000d8a3`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_1`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d7ac`
- `0x18000e138`
- `0x18000e1e4`
- `0x18000e320`
- `0x18000ebc4`
- `0x18000ecf4`
- `0x18000edb4`
- `0x18000ee58`
- `0x18000eea4`
- `0x18000ef08`
- `0x18000efb8`
- `0x18000f03c`
- `0x18000f410`
- `0x18000f574`
- `0x18000f630`
- `0x18000f6ac`
- `0x18000f878`
- `0x1800106f8`
- `0x180010750`
- `0x1800107fc`
- `0x180010864`
- `0x1800109d8`
- `0x1800182cc`
- `0x180018604`

## callees

- `0x18000d88c`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d898`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x18000d898`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        RTL_SRWLOCK **this)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *this;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x18000d88c  sub     rsp, 28h
0x18000d890  mov     rcx, [rcx]; SRWLock
0x18000d893  test    rcx, rcx
0x18000d896  jz      short loc_18000D89E
0x18000d898  call    cs:ReleaseSRWLockExclusive
0x18000d89e  add     rsp, 28h
0x18000d8a2  retn
```
