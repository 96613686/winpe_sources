# CRegEventProvider::EnqueueEvent(CRegistryEventRequest *)

- ea: `0x1800080b8`
- end: `0x180008133`
- name: `?EnqueueEvent@CRegEventProvider@@QEAAXPEAVCRegistryEventRequest@@@Z`
- size: `123`
- prototype: `void __fastcall(CRegEventProvider *__hidden this, struct CRegistryEventRequest *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180007fe0`
- `0x180013d88`

## callees

- `0x1800080b8`
- `0x1800082d0`
- `0x180015532`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSemaphore` at `0x18000812c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000810e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000810e`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x1800080ed`
- `wbemcomn!?Enqueue@CFlexQueue@@QEAA_NPEAX@Z` at `0x1800080ed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CRegEventProvider::EnqueueEvent(CRegEventProvider *this, struct CRegistryEventRequest *a2)
{
  char pExceptionObject; // [rsp+30h] [rbp+8h] BYREF
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+38h] [rbp+10h] BYREF

  CInCritSec::CInCritSec((CInCritSec *)&lpCriticalSection, (struct _RTL_CRITICAL_SECTION *)((char *)this + 232));
  if ( a2 )
    _InterlockedIncrement((volatile signed __int32 *)a2 + 2);
  if ( !CFlexQueue::Enqueue((CRegEventProvider *)((char *)this + 272), a2) )
    throw (CX_MemoryException *)&pExceptionObject;
  LeaveCriticalSection(lpCriticalSection);
  ReleaseSemaphore(*((HANDLE *)this + 28), 1, 0);
}

```

## disassembly

```asm
0x1800080b8  mov     [rsp+arg_10], rbx
0x1800080bd  push    rdi
0x1800080be  sub     rsp, 20h
0x1800080c2  mov     rbx, rdx
0x1800080c5  mov     rdi, rcx
0x1800080c8  lea     rdx, [rcx+0E8h]; struct _RTL_CRITICAL_SECTION *
0x1800080cf  lea     rcx, [rsp+28h+lpCriticalSection]; this
0x1800080d4  call    ??0CInCritSec@@QEAA@PEAU_RTL_CRITICAL_SECTION@@@Z; CInCritSec::CInCritSec(_RTL_CRITICAL_SECTION *)
0x1800080d9  nop
0x1800080da  test    rbx, rbx
0x1800080dd  jz      short loc_1800080E3
0x1800080df  lock inc dword ptr [rbx+8]
0x1800080e3  lea     rcx, [rdi+110h]
0x1800080ea  mov     rdx, rbx
0x1800080ed  call    cs:__imp_?Enqueue@CFlexQueue@@QEAA_NPEAX@Z; CFlexQueue::Enqueue(void *)
0x1800080f3  test    al, al
0x1800080f5  jnz     short loc_180008109
0x1800080f7  lea     rdx, _TI2?AVCX_MemoryException@@; pThrowInfo
0x1800080fe  lea     rcx, [rsp+28h+pExceptionObject]; pExceptionObject
0x180008103  call    _CxxThrowException_0
0x180008109  mov     rcx, [rsp+28h+lpCriticalSection]; lpCriticalSection
0x18000810e  call    cs:__imp_LeaveCriticalSection
0x180008114  xor     r8d, r8d
0x180008117  lea     edx, [r8+1]
0x18000811b  mov     rcx, [rdi+0E0h]
0x180008122  mov     rbx, [rsp+28h+arg_10]
0x180008127  add     rsp, 20h
0x18000812b  pop     rdi
0x18000812c  jmp     cs:__imp_ReleaseSemaphore
```
