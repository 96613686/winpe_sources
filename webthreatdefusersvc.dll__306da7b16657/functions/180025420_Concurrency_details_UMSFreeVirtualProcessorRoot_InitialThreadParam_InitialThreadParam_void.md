# Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(void)

- ea: `0x180025420`
- end: `0x180025437`
- name: `??1InitialThreadParam@UMSFreeVirtualProcessorRoot@details@Concurrency@@QEAA@XZ_2`
- size: `23`
- prototype: `void __fastcall(SC_HANDLE *this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180025510`
- `0x180028a84`

## callees

- `0x180025420`

## import_xrefs

- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002542c`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x18002542c`

## pseudocode

```c
void __fastcall Concurrency::details::UMSFreeVirtualProcessorRoot::InitialThreadParam::~InitialThreadParam(
        SC_HANDLE *this)
{
  SC_HANDLE v1; // rcx

  v1 = *this;
  if ( v1 )
    CloseServiceHandle(v1);
}

```

## disassembly

```asm
0x180025420  sub     rsp, 28h
0x180025424  mov     rcx, [rcx]; hSCObject
0x180025427  test    rcx, rcx
0x18002542a  jz      short loc_180025432
0x18002542c  call    cs:CloseServiceHandle
0x180025432  add     rsp, 28h
0x180025436  retn
```
