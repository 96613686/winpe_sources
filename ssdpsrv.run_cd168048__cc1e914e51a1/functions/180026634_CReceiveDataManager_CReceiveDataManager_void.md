# CReceiveDataManager::~CReceiveDataManager(void)

- ea: `0x180026634`
- end: `0x1800266a8`
- name: `??1CReceiveDataManager@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(CReceiveDataManager *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180038080`

## callees

- `0x180026634`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18002669c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026663`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026680`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026646`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026663`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026680`

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
0x180026634  push    rbx
0x180026636  sub     rsp, 20h
0x18002663a  mov     rbx, rcx
0x18002663d  mov     rcx, [rcx+38h]; hObject
0x180026641  test    rcx, rcx
0x180026644  jz      short loc_18002665A
0x180026646  call    cs:__imp_CloseHandle
0x18002664d  nop     dword ptr [rax+rax+00h]
0x180026652  mov     qword ptr [rbx+38h], 0
0x18002665a  mov     rcx, [rbx+40h]; hObject
0x18002665e  test    rcx, rcx
0x180026661  jz      short loc_180026677
0x180026663  call    cs:__imp_CloseHandle
0x18002666a  nop     dword ptr [rax+rax+00h]
0x18002666f  mov     qword ptr [rbx+40h], 0
0x180026677  mov     rcx, [rbx+48h]; hObject
0x18002667b  test    rcx, rcx
0x18002667e  jz      short loc_180026694
0x180026680  call    cs:__imp_CloseHandle
0x180026687  nop     dword ptr [rax+rax+00h]
0x18002668c  mov     qword ptr [rbx+48h], 0
0x180026694  mov     rcx, rbx
0x180026697  add     rsp, 20h
0x18002669b  pop     rbx
0x18002669c  jmp     cs:__imp_DeleteCriticalSection
```
