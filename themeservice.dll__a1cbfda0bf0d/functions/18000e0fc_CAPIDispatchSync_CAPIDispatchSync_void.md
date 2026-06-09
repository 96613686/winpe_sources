# CAPIDispatchSync::~CAPIDispatchSync(void)

- ea: `0x18000e0fc`
- end: `0x18000e170`
- name: `??1CAPIDispatchSync@@QEAA@XZ`
- size: `116`
- prototype: `void __fastcall(struct _RTL_CRITICAL_SECTION *this)`
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update`

## callers

- `0x18000eba0`

## callees

- `0x18000e0fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18000e169`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e116`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e12d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e15b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e116`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e12d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e144`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000e15b`

## pseudocode

```c
void __fastcall CAPIDispatchSync::~CAPIDispatchSync(struct _RTL_CRITICAL_SECTION *this)
{
  void *v2; // rcx
  HANDLE OwningThread; // rcx
  HANDLE LockSemaphore; // rcx
  void *SpinCount; // rcx

  v2 = *(void **)&this[1].LockCount;
  *(_QWORD *)&this[1].LockCount = 0;
  if ( v2 )
    CloseHandle(v2);
  OwningThread = this[1].OwningThread;
  this[1].OwningThread = 0;
  if ( OwningThread )
    CloseHandle(OwningThread);
  LockSemaphore = this[1].LockSemaphore;
  this[1].LockSemaphore = 0;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  SpinCount = (void *)this[1].SpinCount;
  this[1].SpinCount = 0;
  if ( SpinCount )
    CloseHandle(SpinCount);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x18000e0fc  push    rbx
0x18000e0fe  sub     rsp, 20h
0x18000e102  mov     rbx, rcx
0x18000e105  mov     rcx, [rcx+30h]; hObject
0x18000e109  mov     qword ptr [rbx+30h], 0
0x18000e111  test    rcx, rcx
0x18000e114  jz      short loc_18000E11C
0x18000e116  call    cs:__imp_CloseHandle
0x18000e11c  mov     rcx, [rbx+38h]; hObject
0x18000e120  mov     qword ptr [rbx+38h], 0
0x18000e128  test    rcx, rcx
0x18000e12b  jz      short loc_18000E133
0x18000e12d  call    cs:__imp_CloseHandle
0x18000e133  mov     rcx, [rbx+40h]; hObject
0x18000e137  mov     qword ptr [rbx+40h], 0
0x18000e13f  test    rcx, rcx
0x18000e142  jz      short loc_18000E14A
0x18000e144  call    cs:__imp_CloseHandle
0x18000e14a  mov     rcx, [rbx+48h]; hObject
0x18000e14e  mov     qword ptr [rbx+48h], 0
0x18000e156  test    rcx, rcx
0x18000e159  jz      short loc_18000E161
0x18000e15b  call    cs:__imp_CloseHandle
0x18000e161  mov     rcx, rbx
0x18000e164  add     rsp, 20h
0x18000e168  pop     rbx
0x18000e169  jmp     cs:__imp_DeleteCriticalSection
```
