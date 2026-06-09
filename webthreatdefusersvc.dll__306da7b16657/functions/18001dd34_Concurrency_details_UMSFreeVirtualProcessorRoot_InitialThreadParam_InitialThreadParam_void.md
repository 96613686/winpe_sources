# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x18001dd34`
- end: `0x18001dd4b`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_0`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **this)`
- caller_count: `24`
- callee_count: `1`
- tags: ``

## callers

- `0x18001dc60`
- `0x18001e5e8`
- `0x18001e694`
- `0x18001e7d0`
- `0x18001f074`
- `0x18001f1a4`
- `0x18001f264`
- `0x18001f308`
- `0x18001f354`
- `0x18001f3b8`
- `0x18001f468`
- `0x18001f4ec`
- `0x18001f90c`
- `0x18001fa70`
- `0x18001fb2c`
- `0x18001fba8`
- `0x18001fcd8`
- `0x180020b64`
- `0x180020bbc`
- `0x180020c6c`
- `0x180020cd4`
- `0x180020e48`
- `0x180027fb0`
- `0x180028390`

## callees

- `0x18001dd34`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd40`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd40`

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
0x18001dd34  sub     rsp, 28h
0x18001dd38  mov     rcx, [rcx]; SRWLock
0x18001dd3b  test    rcx, rcx
0x18001dd3e  jz      short loc_18001DD46
0x18001dd40  call    cs:ReleaseSRWLockExclusive
0x18001dd46  add     rsp, 28h
0x18001dd4a  retn
```
