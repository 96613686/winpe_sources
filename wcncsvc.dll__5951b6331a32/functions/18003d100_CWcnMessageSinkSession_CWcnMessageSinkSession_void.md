# CWcnMessageSinkSession::~CWcnMessageSinkSession(void)

- ea: `0x18003d100`
- end: `0x18003d135`
- name: `??1CWcnMessageSinkSession@@AEAA@XZ`
- size: `53`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18003dbb4`

## callees

- `0x18000a5ac`
- `0x18003b38c`
- `0x18003d100`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003d11e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003d11e`

## pseudocode

```c
void __fastcall CWcnMessageSinkSession::~CWcnMessageSinkSession(struct _RTL_CRITICAL_SECTION *this)
{
  CWcnMessageSinkManager *OwningThread; // rcx

  OwningThread = (CWcnMessageSinkManager *)this->OwningThread;
  if ( OwningThread )
    CWcnMessageSinkManager::RemoveSession(OwningThread, (struct CWcnMessageSinkSession *)this);
  DeleteCriticalSection(this + 1);
  CSbSafeBuffer::~CSbSafeBuffer((CSbSafeBuffer *)&this[4].OwningThread);
}

```

## disassembly

```asm
0x18003d100  push    rbx
0x18003d102  sub     rsp, 20h
0x18003d106  mov     rbx, rcx
0x18003d109  mov     rcx, [rcx+10h]; this
0x18003d10d  test    rcx, rcx
0x18003d110  jz      short loc_18003D11A
0x18003d112  mov     rdx, rbx; struct CWcnMessageSinkSession *
0x18003d115  call    ?RemoveSession@CWcnMessageSinkManager@@QEAAXPEAVCWcnMessageSinkSession@@@Z; CWcnMessageSinkManager::RemoveSession(CWcnMessageSinkSession *)
0x18003d11a  lea     rcx, [rbx+28h]; lpCriticalSection
0x18003d11e  call    cs:__imp_DeleteCriticalSection
0x18003d124  lea     rcx, [rbx+0B0h]; this
0x18003d12b  add     rsp, 20h
0x18003d12f  pop     rbx
0x18003d130  jmp     ??1CSbSafeBuffer@@QEAA@XZ; CSbSafeBuffer::~CSbSafeBuffer(void)
```
