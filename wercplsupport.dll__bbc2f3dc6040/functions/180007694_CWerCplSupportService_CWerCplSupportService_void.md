# CWerCplSupportService::~CWerCplSupportService(void)

- ea: `0x180007694`
- end: `0x1800076c0`
- name: `??1CWerCplSupportService@@AEAA@XZ`
- size: `44`
- prototype: `void __fastcall(CWerCplSupportService *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180012610`

## callees

- `0x180007694`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800076b9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800076ab`

## pseudocode

```c
void __fastcall CWerCplSupportService::~CWerCplSupportService(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx

  OwningThread = this[1].OwningThread;
  if ( (unsigned __int64)OwningThread + 1 > 1 )
    CloseHandle(OwningThread);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180007694  push    rbx
0x180007696  sub     rsp, 20h
0x18000769a  mov     rbx, rcx
0x18000769d  mov     rcx, [rcx+38h]; hObject
0x1800076a1  lea     rax, [rcx+1]
0x1800076a5  cmp     rax, 1
0x1800076a9  jbe     short loc_1800076B1
0x1800076ab  call    cs:__imp_CloseHandle
0x1800076b1  mov     rcx, rbx
0x1800076b4  add     rsp, 20h
0x1800076b8  pop     rbx
0x1800076b9  jmp     cs:__imp_DeleteCriticalSection
```
