# Microsoft::Diagnostics::UtcApiWrapper::AutoScenarioList::~AutoScenarioList(void)

- ea: `0x18008d4ac`
- end: `0x18008d4c3`
- name: `??1AutoScenarioList@UtcApiWrapper@Diagnostics@Microsoft@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(void **this)`
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x18009a6f3`
- `0x18009a783`

## callees

- `0x18008d4ac`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008d4b8`

## pseudocode

```c
void __fastcall Microsoft::Diagnostics::UtcApiWrapper::AutoScenarioList::~AutoScenarioList(void **this)
{
  void *v1; // rcx

  v1 = *this;
  if ( v1 )
    CoTaskMemFree(v1);
}

```

## disassembly

```asm
0x18008d4ac  sub     rsp, 28h
0x18008d4b0  mov     rcx, [rcx]; pv
0x18008d4b3  test    rcx, rcx
0x18008d4b6  jz      short loc_18008D4BE
0x18008d4b8  call    cs:__imp_CoTaskMemFree
0x18008d4be  add     rsp, 28h
0x18008d4c2  retn
```
