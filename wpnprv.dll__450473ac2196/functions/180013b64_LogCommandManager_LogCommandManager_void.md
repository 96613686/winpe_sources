# LogCommandManager::~LogCommandManager(void)

- ea: `0x180013b64`
- end: `0x180013b8d`
- name: `??1LogCommandManager@@UEAA@XZ`
- size: `41`
- prototype: `void __fastcall(LogCommandManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180013bf0`

## callees

- `0x180013b94`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013b7a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180013b7a`

## pseudocode

```c
void __fastcall LogCommandManager::~LogCommandManager(LogCommandManager *this)
{
  LogCommandManager::PrecommandScenario::~PrecommandScenario((LogCommandManager *)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180013b64  push    rbx
0x180013b66  sub     rsp, 20h
0x180013b6a  mov     rbx, rcx
0x180013b6d  add     rcx, 38h ; '8'; this
0x180013b71  call    ??1PrecommandScenario@LogCommandManager@@QEAA@XZ; LogCommandManager::PrecommandScenario::~PrecommandScenario(void)
0x180013b76  lea     rcx, [rbx+10h]; lpCriticalSection
0x180013b7a  call    cs:__imp_DeleteCriticalSection
0x180013b80  mov     dword ptr [rbx+0Ch], 0C0000001h
0x180013b87  add     rsp, 20h
0x180013b8b  pop     rbx
0x180013b8c  retn
```
