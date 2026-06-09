# TMAddJob(_TMSTATEVAR *)

- ea: `0x14006f580`
- end: `0x14006f66d`
- name: `?TMAddJob@@YAHPEAU_TMSTATEVAR@@@Z`
- size: `237`
- prototype: `__int64 __fastcall(struct _TMSTATEVAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x140066f9c`

## callees

- `0x140013fe8`
- `0x14006f580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006f5e4`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006f5e4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f65f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14006f65f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f59d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14006f59d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14006f636`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x14006f636`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f644`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14006f644`

## string_xrefs

- `0x14006f5ff`: `Create thread: uActiveThreads = %d.`
- `0x14006f5c3`: `Trigger event: uIdleThreads = %d.`

## pseudocode

```c
__int64 __fastcall TMAddJob(struct _TMSTATEVAR *a1)
{
  unsigned int v1; // ebx
  HANDLE v2; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  int v5; // [rsp+44h] [rbp+Ch]

  v5 = HIDWORD(a1);
  ThreadId = 0;
  EnterCriticalSection(*(LPCRITICAL_SECTION *)(tmStateVar + 40LL));
  v1 = 1;
  if ( (dword_1400CB948 & 1) != 0 )
    goto LABEL_7;
  if ( !HIDWORD(qword_1400CB94C) )
  {
    if ( (unsigned int)qword_1400CB94C >= *tmStateVar )
      goto LABEL_8;
    PrvSpoolssTelemetry::WriteDbgTraceInfo("TMAddJob", L"Create thread: uActiveThreads = %d.");
    v2 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)xTMThreadProc, &tmStateVar, 0, &ThreadId);
    if ( v2 )
    {
      CloseHandle(v2);
      LODWORD(qword_1400CB94C) = qword_1400CB94C + 1;
      goto LABEL_8;
    }
LABEL_7:
    v1 = 0;
    goto LABEL_8;
  }
  --HIDWORD(qword_1400CB94C);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("TMAddJob", L"Trigger event: uIdleThreads = %d.");
  SetEvent(hObject);
LABEL_8:
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(tmStateVar + 40LL));
  return v1;
}

```

## disassembly

```asm
0x14006f580  mov     qword ptr [rsp+ThreadId], rcx
0x14006f585  push    rbx
0x14006f586  sub     rsp, 30h
0x14006f58a  mov     rcx, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x14006f591  mov     [rsp+38h+ThreadId], 0
0x14006f599  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f59d  call    cs:__imp_EnterCriticalSection
0x14006f5a3  mov     ebx, 1
0x14006f5a8  test    byte ptr cs:dword_1400CB948, bl
0x14006f5ae  jnz     loc_14006F652
0x14006f5b4  mov     r8d, dword ptr cs:qword_1400CB94C+4
0x14006f5bb  test    r8d, r8d
0x14006f5be  jz      short loc_14006F5EC
0x14006f5c0  dec     r8d
0x14006f5c3  lea     rdx, aTriggerEventUi; "Trigger event: uIdleThreads = %d."
0x14006f5ca  lea     rcx, aTmaddjob; "TMAddJob"
0x14006f5d1  mov     dword ptr cs:qword_1400CB94C+4, r8d
0x14006f5d8  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f5dd  mov     rcx, cs:hObject; hEvent
0x14006f5e4  call    cs:__imp_SetEvent
0x14006f5ea  jmp     short loc_14006F654
0x14006f5ec  mov     rax, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x14006f5f3  mov     r8d, dword ptr cs:qword_1400CB94C
0x14006f5fa  cmp     r8d, [rax]
0x14006f5fd  jnb     short loc_14006F654
0x14006f5ff  lea     rdx, aCreateThreadUa; "Create thread: uActiveThreads = %d."
0x14006f606  lea     rcx, aTmaddjob; "TMAddJob"
0x14006f60d  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14006f612  lea     rax, [rsp+38h+ThreadId]
0x14006f617  xor     edx, edx; dwStackSize
0x14006f619  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x14006f61e  lea     r9, ?tmStateVar@@3U_TMSTATEVAR@@A; lpParameter
0x14006f625  lea     r8, ?xTMThreadProc@@YAKPEAX@Z; lpStartAddress
0x14006f62c  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x14006f634  xor     ecx, ecx; lpThreadAttributes
0x14006f636  call    cs:__imp_CreateThread
0x14006f63c  test    rax, rax
0x14006f63f  jz      short loc_14006F652
0x14006f641  mov     rcx, rax; hObject
0x14006f644  call    cs:__imp_CloseHandle
0x14006f64a  add     dword ptr cs:qword_1400CB94C, ebx
0x14006f650  jmp     short loc_14006F654
0x14006f652  xor     ebx, ebx
0x14006f654  mov     rcx, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x14006f65b  mov     rcx, [rcx+28h]; lpCriticalSection
0x14006f65f  call    cs:__imp_LeaveCriticalSection
0x14006f665  mov     eax, ebx
0x14006f667  add     rsp, 30h
0x14006f66b  pop     rbx
0x14006f66c  retn
```
