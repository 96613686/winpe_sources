# CWmiEventSinkAvFw::~CWmiEventSinkAvFw(void)

- ea: `0x180038acc`
- end: `0x180038aef`
- name: `??1CWmiEventSinkAvFw@@QEAA@XZ`
- size: `35`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180023920`

## callees

- `0x180038acc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038ae4`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180038ae4`

## pseudocode

```c
void __fastcall CWmiEventSinkAvFw::~CWmiEventSinkAvFw(struct _RTL_CRITICAL_SECTION *this)
{
  bool v1; // zf

  v1 = LODWORD(this[2].DebugInfo) == 0;
  this->DebugInfo = (PRTL_CRITICAL_SECTION_DEBUG)&CWmiEventSinkAvFw::`vftable';
  if ( !v1 )
    DeleteCriticalSection(this + 1);
}

```

## disassembly

```asm
0x180038acc  sub     rsp, 28h
0x180038ad0  cmp     dword ptr [rcx+50h], 0
0x180038ad4  lea     rax, ??_7CWmiEventSinkAvFw@@6B@; const CWmiEventSinkAvFw::`vftable'
0x180038adb  mov     [rcx], rax
0x180038ade  jz      short loc_180038AEA
0x180038ae0  add     rcx, 28h ; '('; lpCriticalSection
0x180038ae4  call    cs:__imp_DeleteCriticalSection
0x180038aea  add     rsp, 28h
0x180038aee  retn
```
