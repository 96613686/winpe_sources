# CUWFCspNode::~CUWFCspNode(void)

- ea: `0x180007e9c`
- end: `0x180007ee0`
- name: `??1CUWFCspNode@@MEAA@XZ`
- size: `68`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1800081d0`
- `0x180008320`

## callees

- `0x180007e9c`
- `0x180019848`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ed4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180007ed4`

## pseudocode

```c
void __fastcall CUWFCspNode::~CUWFCspNode(struct _RTL_CRITICAL_SECTION *this)
{
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CUWFCspNode::`vftable'{for `ICSPNode'};
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
0x180007e9c  push    rbx
0x180007e9e  sub     rsp, 20h
0x180007ea2  lea     rax, ??_7CUWFCspNode@@6BICSPNode@@@; const CUWFCspNode::`vftable'{for `ICSPNode'}
0x180007ea9  mov     rbx, rcx
0x180007eac  mov     [rcx], rax
0x180007eaf  lea     rax, ??_7CUWFCspNode@@6BICSPNodeTransactioning@@@; const CUWFCspNode::`vftable'{for `ICSPNodeTransactioning'}
0x180007eb6  mov     [rcx+8], rax
0x180007eba  lock dec cs:dword_180028594
0x180007ec1  call    ??1CCSPNodeImpl@@UEAA@XZ; CCSPNodeImpl::~CCSPNodeImpl(void)
0x180007ec6  lea     rcx, [rbx+50h]; lpCriticalSection
0x180007eca  cmp     byte ptr [rcx+28h], 0
0x180007ece  jz      short loc_180007EDA
0x180007ed0  mov     byte ptr [rcx+28h], 0
0x180007ed4  call    cs:__imp_DeleteCriticalSection
0x180007eda  add     rsp, 20h
0x180007ede  pop     rbx
0x180007edf  retn
```
