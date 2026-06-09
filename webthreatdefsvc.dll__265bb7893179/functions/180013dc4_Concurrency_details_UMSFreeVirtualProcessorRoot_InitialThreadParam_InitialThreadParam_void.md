# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180013dc4`
- end: `0x180013ddb`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_3`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1800157cc`

## callees

- `0x180013dc4`

## import_xrefs

- `ADVAPI32!LsaClose` at `0x180013dd0`
- `ADVAPI32!LsaClose` at `0x180013dd0`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    LsaClose(v1);
}

```

## disassembly

```asm
0x180013dc4  sub     rsp, 28h
0x180013dc8  mov     rcx, [rcx]; ObjectHandle
0x180013dcb  test    rcx, rcx
0x180013dce  jz      short loc_180013DD6
0x180013dd0  call    cs:LsaClose
0x180013dd6  add     rsp, 28h
0x180013dda  retn
```
