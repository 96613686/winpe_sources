# TMAddJob(_TMSTATEVAR *)

- ea: `0x140076418`
- end: `0x140076524`
- name: `?TMAddJob@@YAHPEAU_TMSTATEVAR@@@Z`
- size: `268`
- prototype: `__int64 __fastcall(struct _TMSTATEVAR *)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14006e838`

## callees

- `0x140015290`
- `0x140076418`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140076482`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x140076482`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007650f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007650f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076435`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140076435`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400764da`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x1400764da`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400764ee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400764ee`

## string_xrefs

- `0x140076461`: `Trigger event: uIdleThreads = %d.`
- `0x1400764a3`: `Create thread: uActiveThreads = %d.`

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
  if ( (dword_1400D2AB8 & 1) != 0 )
    goto LABEL_7;
  if ( !HIDWORD(qword_1400D2ABC) )
  {
    if ( (unsigned int)qword_1400D2ABC >= *tmStateVar )
      goto LABEL_8;
    PrvSpoolssTelemetry::WriteDbgTraceInfo("TMAddJob", L"Create thread: uActiveThreads = %d.");
    v2 = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)xTMThreadProc, &tmStateVar, 0, &ThreadId);
    if ( v2 )
    {
      CloseHandle(v2);
      LODWORD(qword_1400D2ABC) = qword_1400D2ABC + 1;
      goto LABEL_8;
    }
LABEL_7:
    v1 = 0;
    goto LABEL_8;
  }
  --HIDWORD(qword_1400D2ABC);
  PrvSpoolssTelemetry::WriteDbgTraceInfo("TMAddJob", L"Trigger event: uIdleThreads = %d.");
  SetEvent(hObject);
LABEL_8:
  LeaveCriticalSection(*(LPCRITICAL_SECTION *)(tmStateVar + 40LL));
  return v1;
}

```

## disassembly

```asm
0x140076418  mov     qword ptr [rsp+ThreadId], rcx
0x14007641d  push    rbx
0x14007641e  sub     rsp, 30h
0x140076422  mov     rcx, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x140076429  mov     [rsp+38h+ThreadId], 0
0x140076431  mov     rcx, [rcx+28h]; lpCriticalSection
0x140076435  call    cs:__imp_EnterCriticalSection
0x14007643c  nop     dword ptr [rax+rax+00h]
0x140076441  mov     ebx, 1
0x140076446  test    byte ptr cs:dword_1400D2AB8, bl
0x14007644c  jnz     loc_140076502
0x140076452  mov     r8d, dword ptr cs:qword_1400D2ABC+4
0x140076459  test    r8d, r8d
0x14007645c  jz      short loc_140076490
0x14007645e  dec     r8d
0x140076461  lea     rdx, aTriggerEventUi; "Trigger event: uIdleThreads = %d."
0x140076468  lea     rcx, aTmaddjob; "TMAddJob"
0x14007646f  mov     dword ptr cs:qword_1400D2ABC+4, r8d
0x140076476  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x14007647b  mov     rcx, cs:hObject; hEvent
0x140076482  call    cs:__imp_SetEvent
0x140076489  nop     dword ptr [rax+rax+00h]
0x14007648e  jmp     short loc_140076504
0x140076490  mov     rax, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x140076497  mov     r8d, dword ptr cs:qword_1400D2ABC
0x14007649e  cmp     r8d, [rax]
0x1400764a1  jnb     short loc_140076504
0x1400764a3  lea     rdx, aCreateThreadUa; "Create thread: uActiveThreads = %d."
0x1400764aa  lea     rcx, aTmaddjob; "TMAddJob"
0x1400764b1  call    ?WriteDbgTraceInfo@PrvSpoolssTelemetry@@SAXPEADPEAGZZ; PrvSpoolssTelemetry::WriteDbgTraceInfo(char *,ushort *,...)
0x1400764b6  lea     rax, [rsp+38h+ThreadId]
0x1400764bb  xor     edx, edx; dwStackSize
0x1400764bd  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x1400764c2  lea     r9, ?tmStateVar@@3U_TMSTATEVAR@@A; lpParameter
0x1400764c9  lea     r8, ?xTMThreadProc@@YAKPEAX@Z; lpStartAddress
0x1400764d0  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x1400764d8  xor     ecx, ecx; lpThreadAttributes
0x1400764da  call    cs:__imp_CreateThread
0x1400764e1  nop     dword ptr [rax+rax+00h]
0x1400764e6  test    rax, rax
0x1400764e9  jz      short loc_140076502
0x1400764eb  mov     rcx, rax; hObject
0x1400764ee  call    cs:__imp_CloseHandle
0x1400764f5  nop     dword ptr [rax+rax+00h]
0x1400764fa  add     dword ptr cs:qword_1400D2ABC, ebx
0x140076500  jmp     short loc_140076504
0x140076502  xor     ebx, ebx
0x140076504  mov     rcx, cs:?tmStateVar@@3U_TMSTATEVAR@@A; _TMSTATEVAR tmStateVar
0x14007650b  mov     rcx, [rcx+28h]; lpCriticalSection
0x14007650f  call    cs:__imp_LeaveCriticalSection
0x140076516  nop     dword ptr [rax+rax+00h]
0x14007651b  mov     eax, ebx
0x14007651d  add     rsp, 30h
0x140076521  pop     rbx
0x140076522  retn
```
