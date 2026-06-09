# CVolumeManager::~CVolumeManager(void)

- ea: `0x18000eff0`
- end: `0x18000f035`
- name: `??1CVolumeManager@@QEAA@XZ`
- size: `69`
- prototype: `void __fastcall(CVolumeManager *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000ef50`

## callees

- `0x180001b64`
- `0x18000eed8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f021`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000f021`

## pseudocode

```c
void __fastcall CVolumeManager::~CVolumeManager(CVolumeManager *this)
{
  *(_QWORD *)this = &CVolumeManager::`vftable'{for `PTimerCallback'};
  *((_QWORD *)this + 1) = &CVolumeManager::`vftable'{for `PWorkItem'};
  CVolumeManager::UnInitialize(this);
  *((_DWORD *)this + 4) = 1733127254;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 208));
  CNewTimer::~CNewTimer((CVolumeManager *)((char *)this + 24));
}

```

## disassembly

```asm
0x18000eff0  push    rbx
0x18000eff2  sub     rsp, 20h
0x18000eff6  lea     rax, ??_7CVolumeManager@@6BPTimerCallback@@@; const CVolumeManager::`vftable'{for `PTimerCallback'}
0x18000effd  mov     rbx, rcx
0x18000f000  mov     [rcx], rax
0x18000f003  lea     rax, ??_7CVolumeManager@@6BPWorkItem@@@; const CVolumeManager::`vftable'{for `PWorkItem'}
0x18000f00a  mov     [rcx+8], rax
0x18000f00e  call    ?UnInitialize@CVolumeManager@@QEAAXXZ; CVolumeManager::UnInitialize(void)
0x18000f013  lea     rcx, [rbx+0D0h]; lpCriticalSection
0x18000f01a  mov     dword ptr [rbx+10h], 674D6C56h
0x18000f021  call    cs:__imp_DeleteCriticalSection
0x18000f027  lea     rcx, [rbx+18h]; this
0x18000f02b  add     rsp, 20h
0x18000f02f  pop     rbx
0x18000f030  jmp     ??1CNewTimer@@QEAA@XZ; CNewTimer::~CNewTimer(void)
```
