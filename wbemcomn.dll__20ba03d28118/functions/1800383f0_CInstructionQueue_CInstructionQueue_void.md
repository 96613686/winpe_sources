# CInstructionQueue::~CInstructionQueue(void)

- ea: `0x1800383f0`
- end: `0x180038454`
- name: `??1CInstructionQueue@@QEAA@XZ`
- size: `100`
- prototype: `void __fastcall(CInstructionQueue *__hidden this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180038460`
- `0x180044970`
- `0x180046090`

## callees

- `0x180016730`
- `0x180016ae8`
- `0x1800383f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038442`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038442`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038437`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180038437`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003842b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18003842b`

## pseudocode

```c
void __fastcall CInstructionQueue::~CInstructionQueue(CInstructionQueue *this)
{
  unsigned int v2; // edx
  CInstructionQueue::CQueueEl *v3; // rcx
  LPCRITICAL_SECTION lpCriticalSection[3]; // [rsp+20h] [rbp-18h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 8));
  while ( 1 )
  {
    v3 = *(CInstructionQueue::CQueueEl **)this;
    if ( !*(_QWORD *)this )
      break;
    *(_QWORD *)this = *((_QWORD *)v3 + 2);
    CInstructionQueue::CQueueEl::`scalar deleting destructor'(v3, v2);
  }
  CloseHandle(*((HANDLE *)this + 6));
  LeaveCriticalSection(lpCriticalSection[0]);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x1800383f0  mov     [rsp+arg_8], rbx
0x1800383f5  mov     [rsp+arg_0], rcx
0x1800383fa  push    rdi
0x1800383fb  sub     rsp, 30h
0x1800383ff  mov     rbx, rcx
0x180038402  lea     rdx, [rcx+8]; struct _RTL_CRITICAL_SECTION *
0x180038406  lea     rcx, [rsp+38h+lpCriticalSection]; this
0x18003840b  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x180038410  nop
0x180038411  jmp     short loc_18003841F
0x180038413  mov     rax, [rcx+10h]
0x180038417  mov     [rbx], rax
0x18003841a  call    ??_GCQueueEl@CInstructionQueue@@QEAAPEAXI@Z; CInstructionQueue::CQueueEl::`scalar deleting destructor'(uint)
0x18003841f  mov     rcx, [rbx]; this
0x180038422  test    rcx, rcx
0x180038425  jnz     short loc_180038413
0x180038427  mov     rcx, [rbx+30h]; hObject
0x18003842b  call    cs:__imp_CloseHandle
0x180038431  nop
0x180038432  mov     rcx, [rsp+38h+lpCriticalSection]; lpCriticalSection
0x180038437  call    cs:__imp_LeaveCriticalSection
0x18003843d  nop
0x18003843e  lea     rcx, [rbx+8]; lpCriticalSection
0x180038442  call    cs:__imp_DeleteCriticalSection
0x180038448  nop
0x180038449  mov     rbx, [rsp+38h+arg_8]
0x18003844e  add     rsp, 30h
0x180038452  pop     rdi
0x180038453  retn
```
