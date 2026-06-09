# CReceiveDataManager::~CReceiveDataManager(void)

- ea: `0x180024af4`
- end: `0x180024b51`
- name: `??1CReceiveDataManager@@QEAA@XZ`
- size: `93`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180035550`

## callees

- `0x180024af4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180024b4a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b34`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b06`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b1d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180024b34`

## pseudocode

```c
void __fastcall CReceiveDataManager::~CReceiveDataManager(struct _RTL_CRITICAL_SECTION *this)
{
  HANDLE OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  void *SpinCount; // rcx

  OwningThread = this[1].OwningThread;
  if ( OwningThread )
  {
    CloseHandle(OwningThread);
    this[1].OwningThread = 0;
  }
  LockSemaphore = this[1].LockSemaphore;
  if ( LockSemaphore )
  {
    CloseHandle(LockSemaphore);
    this[1].LockSemaphore = 0;
  }
  SpinCount = (void *)this[1].SpinCount;
  if ( SpinCount )
  {
    CloseHandle(SpinCount);
    this[1].SpinCount = 0;
  }
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180024af4  push    rbx
0x180024af6  sub     rsp, 20h
0x180024afa  mov     rbx, rcx
0x180024afd  mov     rcx, [rcx+38h]; hObject
0x180024b01  test    rcx, rcx
0x180024b04  jz      short loc_180024B14
0x180024b06  call    cs:__imp_CloseHandle
0x180024b0c  mov     qword ptr [rbx+38h], 0
0x180024b14  mov     rcx, [rbx+40h]; hObject
0x180024b18  test    rcx, rcx
0x180024b1b  jz      short loc_180024B2B
0x180024b1d  call    cs:__imp_CloseHandle
0x180024b23  mov     qword ptr [rbx+40h], 0
0x180024b2b  mov     rcx, [rbx+48h]; hObject
0x180024b2f  test    rcx, rcx
0x180024b32  jz      short loc_180024B42
0x180024b34  call    cs:__imp_CloseHandle
0x180024b3a  mov     qword ptr [rbx+48h], 0
0x180024b42  mov     rcx, rbx
0x180024b45  add     rsp, 20h
0x180024b49  pop     rbx
0x180024b4a  jmp     cs:__imp_DeleteCriticalSection
```
