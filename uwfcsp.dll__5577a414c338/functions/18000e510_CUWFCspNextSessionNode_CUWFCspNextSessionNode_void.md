# CUWFCspNextSessionNode::~CUWFCspNextSessionNode(void)

- ea: `0x18000e510`
- end: `0x18000e554`
- name: `??1CUWFCspNextSessionNode@@MEAA@XZ`
- size: `68`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18000e560`
- `0x18000e5d0`

## callees

- `0x18000e510`
- `0x180019848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e548`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e548`

## pseudocode

```c
void __fastcall CUWFCspNextSessionNode::~CUWFCspNextSessionNode(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CUWFCspNextSessionNode::`vftable'{for `ICSPNode'};
  *(_QWORD *)&this->LockCount = &CUWFCspNextSessionNode::`vftable'{for `ICSPNodeTransactioning'};
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
0x18000e510  push    rbx
0x18000e512  sub     rsp, 20h
0x18000e516  lea     rax, ??_7CUWFCspNextSessionNode@@6BICSPNode@@@; const CUWFCspNextSessionNode::`vftable'{for `ICSPNode'}
0x18000e51d  mov     rbx, rcx
0x18000e520  mov     [rcx], rax
0x18000e523  lea     rax, ??_7CUWFCspNextSessionNode@@6BICSPNodeTransactioning@@@; const CUWFCspNextSessionNode::`vftable'{for `ICSPNodeTransactioning'}
0x18000e52a  mov     [rcx+8], rax
0x18000e52e  lock dec cs:dword_180028594
0x18000e535  call    ??1CCSPNodeImpl@@UEAA@XZ; CCSPNodeImpl::~CCSPNodeImpl(void)
0x18000e53a  lea     rcx, [rbx+50h]; lpCriticalSection
0x18000e53e  cmp     byte ptr [rcx+28h], 0
0x18000e542  jz      short loc_18000E54E
0x18000e544  mov     byte ptr [rcx+28h], 0
0x18000e548  call    cs:__imp_DeleteCriticalSection
0x18000e54e  add     rsp, 20h
0x18000e552  pop     rbx
0x18000e553  retn
```
