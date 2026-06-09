# CVolume::~CVolume(void)

- ea: `0x18000c638`
- end: `0x18000c69f`
- name: `??1CVolume@@UEAA@XZ`
- size: `103`
- prototype: `void __fastcall(CVolume *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000f600`

## callees

- `0x18000d3b4`
- `0x18000d814`
- `0x18000d8d4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c663`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c67c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c689`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c663`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c67c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000c689`

## pseudocode

```c
void __fastcall CVolume::~CVolume(CVolume *this)
{
  *(_QWORD *)this = &CVolume::`vftable';
  CVolume::UnInitialize(this);
  CTrkRegistryKey::~CTrkRegistryKey((CVolume *)((char *)this + 2888));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 616));
  CLogFile::~CLogFile((CVolume *)((char *)this + 312));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 168));
  *(_QWORD *)this = &PLogFileNotify::`vftable';
}

```

## disassembly

```asm
0x18000c638  push    rbx
0x18000c63a  sub     rsp, 20h
0x18000c63e  lea     rax, ??_7CVolume@@6B@; const CVolume::`vftable'
0x18000c645  mov     rbx, rcx
0x18000c648  mov     [rcx], rax
0x18000c64b  call    ?UnInitialize@CVolume@@QEAAXXZ; CVolume::UnInitialize(void)
0x18000c650  lea     rcx, [rbx+0B48h]; this
0x18000c657  call    ??1CTrkRegistryKey@@QEAA@XZ; CTrkRegistryKey::~CTrkRegistryKey(void)
0x18000c65c  lea     rcx, [rbx+268h]; lpCriticalSection
0x18000c663  call    cs:__imp_DeleteCriticalSection
0x18000c669  lea     rcx, [rbx+138h]; this
0x18000c670  call    ??1CLogFile@@QEAA@XZ; CLogFile::~CLogFile(void)
0x18000c675  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18000c67c  call    cs:__imp_DeleteCriticalSection
0x18000c682  lea     rcx, [rbx+0A8h]; lpCriticalSection
0x18000c689  call    cs:__imp_DeleteCriticalSection
0x18000c68f  lea     rax, ??_7PLogFileNotify@@6B@; const PLogFileNotify::`vftable'
0x18000c696  mov     [rbx], rax
0x18000c699  add     rsp, 20h
0x18000c69d  pop     rbx
0x18000c69e  retn
```
