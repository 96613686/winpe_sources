# THREAD_MANAGER::TerminateThreadManager(void (*)(void *),void *)

- ea: `0x180003418`
- end: `0x1800034d7`
- name: `?TerminateThreadManager@THREAD_MANAGER@@QEAAXP6AXPEAX@Z0@Z`
- size: `191`
- prototype: `void __fastcall(THREAD_MANAGER *__hidden this, void (*)(void *), void *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003be0`

## callees

- `0x180002a90`
- `0x180002c34`
- `0x180003418`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000348f`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x18000348f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000349c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180003464`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000349c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034aa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180003472`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800034aa`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bf`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800034bf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000344a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180003433`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000344a`

## pseudocode

```c
void __fastcall THREAD_MANAGER::TerminateThreadManager(THREAD_MANAGER *this, void (*a2)(void *), void *a3)
{
  void *v4; // rcx
  void *v5; // rcx
  void *v6; // rbx
  HANDLE ProcessHeap; // rax
  struct _PROC_THREAD_ATTRIBUTE_LIST *v8; // rcx
  void *v9; // rbx
  HANDLE v10; // rax
  unsigned int v11; // edx

  THREAD_MANAGER::DrainThreads(this, a2, a3);
  v4 = (void *)*((_QWORD *)this + 12);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 12) = 0;
  }
  v5 = (void *)*((_QWORD *)this + 11);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 11) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 19);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v6);
    *((_QWORD *)this + 19) = 0;
  }
  v8 = (struct _PROC_THREAD_ATTRIBUTE_LIST *)*((_QWORD *)this + 21);
  if ( v8 )
  {
    DeleteProcThreadAttributeList(v8);
    v9 = (void *)*((_QWORD *)this + 21);
    v10 = GetProcessHeap();
    HeapFree(v10, 0, v9);
    *((_QWORD *)this + 21) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  THREAD_MANAGER::`scalar deleting destructor'(this, v11);
}

```

## disassembly

```asm
0x180003418  mov     [rsp+arg_0], rbx
0x18000341d  push    rdi
0x18000341e  sub     rsp, 20h
0x180003422  mov     rdi, rcx
0x180003425  call    ?DrainThreads@THREAD_MANAGER@@AEAAXP6AXPEAX@Z0@Z; THREAD_MANAGER::DrainThreads(void (*)(void *),void *)
0x18000342a  mov     rcx, [rdi+60h]; hObject
0x18000342e  test    rcx, rcx
0x180003431  jz      short loc_180003441
0x180003433  call    cs:__imp_CloseHandle
0x180003439  mov     qword ptr [rdi+60h], 0
0x180003441  mov     rcx, [rdi+58h]; hObject
0x180003445  test    rcx, rcx
0x180003448  jz      short loc_180003458
0x18000344a  call    cs:__imp_CloseHandle
0x180003450  mov     qword ptr [rdi+58h], 0
0x180003458  mov     rbx, [rdi+98h]
0x18000345f  test    rbx, rbx
0x180003462  jz      short loc_180003483
0x180003464  call    cs:__imp_GetProcessHeap
0x18000346a  mov     r8, rbx; lpMem
0x18000346d  xor     edx, edx; dwFlags
0x18000346f  mov     rcx, rax; hHeap
0x180003472  call    cs:__imp_HeapFree
0x180003478  mov     qword ptr [rdi+98h], 0
0x180003483  mov     rcx, [rdi+0A8h]; lpAttributeList
0x18000348a  test    rcx, rcx
0x18000348d  jz      short loc_1800034BB
0x18000348f  call    cs:__imp_DeleteProcThreadAttributeList
0x180003495  mov     rbx, [rdi+0A8h]
0x18000349c  call    cs:__imp_GetProcessHeap
0x1800034a2  mov     r8, rbx; lpMem
0x1800034a5  xor     edx, edx; dwFlags
0x1800034a7  mov     rcx, rax; hHeap
0x1800034aa  call    cs:__imp_HeapFree
0x1800034b0  mov     qword ptr [rdi+0A8h], 0
0x1800034bb  lea     rcx, [rdi+8]; lpCriticalSection
0x1800034bf  call    cs:__imp_DeleteCriticalSection
0x1800034c5  mov     rcx, rdi; this
0x1800034c8  mov     rbx, [rsp+28h+arg_0]
0x1800034cd  add     rsp, 20h
0x1800034d1  pop     rdi
0x1800034d2  jmp     ??_GTHREAD_MANAGER@@AEAAPEAXI@Z; THREAD_MANAGER::`scalar deleting destructor'(uint)
```
