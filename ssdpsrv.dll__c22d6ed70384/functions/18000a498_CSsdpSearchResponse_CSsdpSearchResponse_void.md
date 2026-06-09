# CSsdpSearchResponse::~CSsdpSearchResponse(void)

- ea: `0x18000a498`
- end: `0x18000a506`
- name: `??1CSsdpSearchResponse@@EEAA@XZ`
- size: `110`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a730`

## callees

- `0x1800023d0`
- `0x18000a358`
- `0x18000a498`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a4c8`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a4c8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4dd`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000a4dd`

## pseudocode

```c
void __fastcall CSsdpSearchResponse::~CSsdpSearchResponse(struct _RTL_CRITICAL_SECTION *this)
{
  unsigned __int64 DebugInfo; // rcx
  HANDLE OwningThread; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CSsdpSearchResponse::`vftable';
  DebugInfo = (unsigned __int64)this[4].DebugInfo;
  if ( DebugInfo )
    UnreferenceSocket(DebugInfo);
  OwningThread = this[7].OwningThread;
  if ( OwningThread )
  {
    free(OwningThread);
    this[7].OwningThread = 0;
  }
  DeleteCriticalSection(this + 3);
  this->OwningThread = &CTimer<CSsdpSearchResponse>::`vftable';
  CTimerBase::~CTimerBase((CTimerBase *)&this->OwningThread);
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWorkItem::`vftable';
}

```

## disassembly

```asm
0x18000a498  push    rbx
0x18000a49a  sub     rsp, 20h
0x18000a49e  lea     rax, ??_7CSsdpSearchResponse@@6B@; const CSsdpSearchResponse::`vftable'
0x18000a4a5  mov     rbx, rcx
0x18000a4a8  mov     [rcx], rax
0x18000a4ab  mov     rcx, [rcx+0A0h]; unsigned __int64
0x18000a4b2  test    rcx, rcx
0x18000a4b5  jz      short loc_18000A4BC
0x18000a4b7  call    ?UnreferenceSocket@@YAX_K@Z; UnreferenceSocket(unsigned __int64)
0x18000a4bc  mov     rcx, [rbx+128h]; Block
0x18000a4c3  test    rcx, rcx
0x18000a4c6  jz      short loc_18000A4D9
0x18000a4c8  call    cs:__imp_free
0x18000a4ce  mov     qword ptr [rbx+128h], 0
0x18000a4d9  lea     rcx, [rbx+78h]; lpCriticalSection
0x18000a4dd  call    cs:__imp_DeleteCriticalSection
0x18000a4e3  lea     rcx, [rbx+10h]; this
0x18000a4e7  lea     rax, ??_7?$CTimer@VCSsdpSearchResponse@@@@6B@; const CTimer<CSsdpSearchResponse>::`vftable'
0x18000a4ee  mov     [rcx], rax
0x18000a4f1  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000a4f6  lea     rax, ??_7CWorkItem@@6B@; const CWorkItem::`vftable'
0x18000a4fd  mov     [rbx], rax
0x18000a500  add     rsp, 20h
0x18000a504  pop     rbx
0x18000a505  retn
```
