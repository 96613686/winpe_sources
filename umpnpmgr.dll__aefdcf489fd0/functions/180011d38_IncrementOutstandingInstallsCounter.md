# IncrementOutstandingInstallsCounter

- ea: `0x180011d38`
- end: `0x180011d73`
- name: `IncrementOutstandingInstallsCounter`
- size: `59`
- prototype: `void()`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x180008d20`

## callees

- `0x180011d38`
- `0x180013ed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d43`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011d43`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011d6c`

## pseudocode

```c
void IncrementOutstandingInstallsCounter()
{
  EnterCriticalSection(&PnpIdleStopLock);
  if ( ++PnpServiceOutstandingInstalls == 1 )
    EvaluateIdleStopPolicy();
  LeaveCriticalSection(&PnpIdleStopLock);
}

```

## disassembly

```asm
0x180011d38  sub     rsp, 28h
0x180011d3c  lea     rcx, PnpIdleStopLock; lpCriticalSection
0x180011d43  call    cs:__imp_EnterCriticalSection
0x180011d49  mov     eax, cs:PnpServiceOutstandingInstalls
0x180011d4f  inc     eax
0x180011d51  mov     cs:PnpServiceOutstandingInstalls, eax
0x180011d57  cmp     eax, 1
0x180011d5a  jnz     short loc_180011D61
0x180011d5c  call    EvaluateIdleStopPolicy
0x180011d61  lea     rcx, PnpIdleStopLock
0x180011d68  add     rsp, 28h
0x180011d6c  jmp     cs:__imp_LeaveCriticalSection
```
