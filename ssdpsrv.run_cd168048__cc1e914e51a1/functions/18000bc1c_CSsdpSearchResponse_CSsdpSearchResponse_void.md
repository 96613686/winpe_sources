# CSsdpSearchResponse::~CSsdpSearchResponse(void)

- ea: `0x18000bc1c`
- end: `0x18000bc97`
- name: `??1CSsdpSearchResponse@@EEAA@XZ`
- size: `123`
- prototype: `void __fastcall(CSsdpSearchResponse *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000c040`

## callees

- `0x180003a60`
- `0x18000ba2c`
- `0x18000bc1c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000bc4c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc67`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000bc67`

## pseudocode

```c
void __fastcall CSsdpSearchResponse::~CSsdpSearchResponse(struct _RTL_CRITICAL_SECTION *this)
{
  __int64 DebugInfo; // rcx
  HANDLE OwningThread; // rcx

  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CSsdpSearchResponse::`vftable';
  DebugInfo = (__int64)this[4].DebugInfo;
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
0x18000bc1c  push    rbx
0x18000bc1e  sub     rsp, 20h
0x18000bc22  lea     rax, ??_7CSsdpSearchResponse@@6B@; const CSsdpSearchResponse::`vftable'
0x18000bc29  mov     rbx, rcx
0x18000bc2c  mov     [rcx], rax
0x18000bc2f  mov     rcx, [rcx+0A0h]; unsigned __int64
0x18000bc36  test    rcx, rcx
0x18000bc39  jz      short loc_18000BC40
0x18000bc3b  call    ?UnreferenceSocket@@YAX_K@Z; UnreferenceSocket(unsigned __int64)
0x18000bc40  mov     rcx, [rbx+128h]; Block
0x18000bc47  test    rcx, rcx
0x18000bc4a  jz      short loc_18000BC63
0x18000bc4c  call    cs:__imp_free
0x18000bc53  nop     dword ptr [rax+rax+00h]
0x18000bc58  mov     qword ptr [rbx+128h], 0
0x18000bc63  lea     rcx, [rbx+78h]; lpCriticalSection
0x18000bc67  call    cs:__imp_DeleteCriticalSection
0x18000bc6e  nop     dword ptr [rax+rax+00h]
0x18000bc73  lea     rcx, [rbx+10h]; this
0x18000bc77  lea     rax, ??_7?$CTimer@VCSsdpSearchResponse@@@@6B@; const CTimer<CSsdpSearchResponse>::`vftable'
0x18000bc7e  mov     [rcx], rax
0x18000bc81  call    ??1CTimerBase@@UEAA@XZ; CTimerBase::~CTimerBase(void)
0x18000bc86  lea     rax, ??_7CWorkItem@@6B@; const CWorkItem::`vftable'
0x18000bc8d  mov     [rbx], rax
0x18000bc90  add     rsp, 20h
0x18000bc94  pop     rbx
0x18000bc95  retn
```
