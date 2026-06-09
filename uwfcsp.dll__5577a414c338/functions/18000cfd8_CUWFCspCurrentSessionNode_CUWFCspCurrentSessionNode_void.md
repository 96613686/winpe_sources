# CUWFCspCurrentSessionNode::~CUWFCspCurrentSessionNode(void)

- ea: `0x18000cfd8`
- end: `0x18000d01c`
- name: `??1CUWFCspCurrentSessionNode@@MEAA@XZ`
- size: `68`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000d030`
- `0x18000d0a0`

## callees

- `0x18000cfd8`
- `0x180019848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d010`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000d010`

## pseudocode

```c
void __fastcall CUWFCspCurrentSessionNode::~CUWFCspCurrentSessionNode(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CUWFCspCurrentSessionNode::`vftable'{for `ICSPNode'};
  *(_QWORD *)&this->LockCount = &CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'};
  _InterlockedDecrement(&dword_180028594);
  CCSPNodeImpl::~CCSPNodeImpl((CCSPNodeImpl *)this);
  if ( LOBYTE(this[3].DebugInfo) )
  {
    LOBYTE(this[3].DebugInfo) = 0;
    DeleteCriticalSection(this + 2);
  }
}

```

## disassembly

```asm
0x18000cfd8  push    rbx
0x18000cfda  sub     rsp, 20h
0x18000cfde  lea     rax, ??_7CUWFCspCurrentSessionNode@@6BICSPNode@@@; const CUWFCspCurrentSessionNode::`vftable'{for `ICSPNode'}
0x18000cfe5  mov     rbx, rcx
0x18000cfe8  mov     [rcx], rax
0x18000cfeb  lea     rax, ??_7CUWFCspNode@@6BICSPNodeTransactioning@@@; const CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000cff2  mov     [rcx+8], rax
0x18000cff6  lock dec cs:dword_180028594
0x18000cffd  call    ??1CCSPNodeImpl@@UEAA@XZ; CCSPNodeImpl::~CCSPNodeImpl(void)
0x18000d002  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000d006  cmp     byte ptr [rcx+28h], 0
0x18000d00a  jz      short loc_18000D016
0x18000d00c  mov     byte ptr [rcx+28h], 0
0x18000d010  call    cs:__imp_DeleteCriticalSection
0x18000d016  add     rsp, 20h
0x18000d01a  pop     rbx
0x18000d01b  retn
```
