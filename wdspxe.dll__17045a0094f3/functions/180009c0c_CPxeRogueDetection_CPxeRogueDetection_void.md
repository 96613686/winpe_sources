# CPxeRogueDetection::~CPxeRogueDetection(void)

- ea: `0x180009c0c`
- end: `0x180009cb1`
- name: `??1CPxeRogueDetection@@QEAA@XZ`
- size: `165`
- prototype: `void __fastcall(CPxeRogueDetection *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops`

## callers

- `0x180012170`

## callees

- `0x180009c0c`

## import_xrefs

- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c21`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c41`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c21`
- `msvcrt!??_V@YAXPEAX@Z` at `0x180009c41`
- `KERNEL32!DeleteCriticalSection` at `0x180009ca5`
- `KERNEL32!CloseHandle` at `0x180009c61`
- `KERNEL32!CloseHandle` at `0x180009c79`
- `KERNEL32!CloseHandle` at `0x180009c91`
- `KERNEL32!CloseHandle` at `0x180009c61`
- `KERNEL32!CloseHandle` at `0x180009c79`
- `KERNEL32!CloseHandle` at `0x180009c91`

## pseudocode

```c
void __fastcall CPxeRogueDetection::~CPxeRogueDetection(struct _RTL_CRITICAL_SECTION *this)
{
  void *SpinCount; // rcx
  PRTL_CRITICAL_SECTION_DEBUG DebugInfo; // rcx
  HANDLE OwningThread; // rcx
  void *v5; // rcx
  HANDLE LockSemaphore; // rcx

  SpinCount = (void *)this[5].SpinCount;
  if ( SpinCount )
  {
    operator delete[](SpinCount);
    this[5].SpinCount = 0;
  }
  DebugInfo = this[6].DebugInfo;
  if ( DebugInfo )
  {
    operator delete[](DebugInfo);
    this[6].DebugInfo = 0;
  }
  OwningThread = this[6].OwningThread;
  if ( OwningThread )
    CloseHandle(OwningThread);
  v5 = *(void **)&this[6].LockCount;
  if ( v5 )
    CloseHandle(v5);
  LockSemaphore = this[6].LockSemaphore;
  if ( LockSemaphore )
    CloseHandle(LockSemaphore);
  DeleteCriticalSection(this);
}

```

## disassembly

```asm
0x180009c0c  push    rbx
0x180009c0e  sub     rsp, 20h
0x180009c12  mov     rbx, rcx
0x180009c15  mov     rcx, [rcx+0E8h]
0x180009c1c  test    rcx, rcx
0x180009c1f  jz      short loc_180009C35
0x180009c21  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009c28  nop     dword ptr [rax+rax+00h]
0x180009c2d  and     qword ptr [rbx+0E8h], 0
0x180009c35  mov     rcx, [rbx+0F0h]
0x180009c3c  test    rcx, rcx
0x180009c3f  jz      short loc_180009C55
0x180009c41  call    cs:__imp_??_V@YAXPEAX@Z; operator delete[](void *)
0x180009c48  nop     dword ptr [rax+rax+00h]
0x180009c4d  and     qword ptr [rbx+0F0h], 0
0x180009c55  mov     rcx, [rbx+100h]; hObject
0x180009c5c  test    rcx, rcx
0x180009c5f  jz      short loc_180009C6D
0x180009c61  call    cs:__imp_CloseHandle
0x180009c68  nop     dword ptr [rax+rax+00h]
0x180009c6d  mov     rcx, [rbx+0F8h]; hObject
0x180009c74  test    rcx, rcx
0x180009c77  jz      short loc_180009C85
0x180009c79  call    cs:__imp_CloseHandle
0x180009c80  nop     dword ptr [rax+rax+00h]
0x180009c85  mov     rcx, [rbx+108h]; hObject
0x180009c8c  test    rcx, rcx
0x180009c8f  jz      short loc_180009C9D
0x180009c91  call    cs:__imp_CloseHandle
0x180009c98  nop     dword ptr [rax+rax+00h]
0x180009c9d  mov     rcx, rbx
0x180009ca0  add     rsp, 20h
0x180009ca4  pop     rbx
0x180009ca5  jmp     cs:__imp_DeleteCriticalSection
```
