# ThEndCallback

- ea: `0x140009ea8`
- end: `0x14000a0cd`
- name: `ThEndCallback`
- size: `549`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `3`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140003a30`
- `0x14000a0d4`
- `0x140017398`

## callees

- `0x140002c20`
- `0x140004c2c`
- `0x140009ac8`
- `0x140009ea8`
- `0x14001b968`
- `0x14001ceb0`
- `0x14001d700`

## string_xrefs

- `0x140009fb4`: `ProcessId`

## pseudocode

```c
void __fastcall ThEndCallback(PEVENT_RECORD Event, struct _THREAD_RECORD *a2)
{
  ULONG ThreadId; // ebp
  struct _THREAD_RECORD *v3; // rsi
  UCHAR v5; // dl
  ULONG v6; // ecx
  struct _THREAD_RECORD *v7; // rbx
  struct _THREAD_RECORD *v8; // r14
  struct _PROCESS_RECORD *ProcessById; // rax
  struct _THREAD_RECORD *v10; // rdx
  LARGE_INTEGER TimeStamp; // rax
  struct _PROCESS_RECORD *v12; // rax
  ULONG UserTime; // eax
  ULONG KernelTime; // eax
  LARGE_INTEGER v15; // rax
  int v16; // eax
  struct _THREAD_RECORD *GlobalThreadById; // [rsp+40h] [rbp+8h] BYREF
  unsigned int v18; // [rsp+48h] [rbp+10h] BYREF

  if ( !Event )
    return;
  ThreadId = Event->EventHeader.ThreadId;
  v3 = a2;
  if ( !ThreadId )
  {
    v5 = dword_14008210C + byte_1400820F2++;
    Event->BufferContext.ProcessorNumber = v5;
    v6 = 0;
    goto LABEL_6;
  }
  if ( !a2 )
  {
    v6 = Event->EventHeader.ThreadId;
LABEL_6:
    GlobalThreadById = FindGlobalThreadById(v6, Event);
    v7 = GlobalThreadById;
    v8 = GlobalThreadById;
    v3 = GlobalThreadById;
    if ( !GlobalThreadById )
    {
      if ( AddThread(ThreadId, Event, &GlobalThreadById) )
      {
        ProcessById = FindProcessById(0, 0);
        v10 = GlobalThreadById;
        *((_QWORD *)GlobalThreadById + 11) = ProcessById;
        *((_DWORD *)v10 + 27) = 1;
        *((_BYTE *)v10 + 104) = 1;
        TimeStamp = Event->EventHeader.TimeStamp;
        *((LARGE_INTEGER *)v10 + 22) = TimeStamp;
        *((LARGE_INTEGER *)v10 + 21) = TimeStamp;
        TimeStamp.LowPart = Event->EventHeader.KernelTime;
        *((_DWORD *)v10 + 47) = TimeStamp.LowPart;
        *((_DWORD *)v10 + 46) = TimeStamp.LowPart;
        TimeStamp.LowPart = Event->EventHeader.UserTime;
        *((_DWORD *)v10 + 49) = TimeStamp.LowPart;
        *((_DWORD *)v10 + 48) = TimeStamp.LowPart;
        AdjustThreadTime((__int64)Event, (__int64)v10);
      }
      return;
    }
    goto LABEL_10;
  }
  v8 = a2;
  v7 = a2;
LABEL_10:
  if ( *((_DWORD *)v7 + 27) )
    return;
  if ( *((_BYTE *)v7 + 104) )
  {
    LODWORD(GlobalThreadById) = 0;
    v18 = 4;
    if ( (unsigned int)GetMofData(Event, L"ProcessId", (BYTE *)&GlobalThreadById, &v18) )
      return;
    v12 = FindProcessById((int)GlobalThreadById, 1);
    if ( v12 )
    {
      *((_BYTE *)v7 + 104) = 0;
      *((_QWORD *)v7 + 11) = v12;
    }
  }
  if ( Event->EventHeader.EventDescriptor.Opcode == 4 )
  {
    if ( *((_BYTE *)g_TraceContext + 8505) && !HIBYTE(word_1400820C8) )
    {
      if ( *(unsigned __int64 *)&SystemTimeAsFileTime > Event->EventHeader.TimeStamp.QuadPart )
        SystemTimeAsFileTime = (struct _FILETIME)Event->EventHeader.TimeStamp.QuadPart;
      HIBYTE(word_1400820C8) = 1;
    }
    StopThreadTrans((char *)v8 + 32, Event, v3);
  }
  *((_DWORD *)v7 + 27) = 1;
  UserTime = Event->EventHeader.UserTime;
  if ( *((_DWORD *)v7 + 49) < UserTime )
    *((_DWORD *)v7 + 49) = UserTime;
  KernelTime = Event->EventHeader.KernelTime;
  if ( *((_DWORD *)v7 + 47) < KernelTime )
    *((_DWORD *)v7 + 47) = KernelTime;
  v15 = Event->EventHeader.TimeStamp;
  *((LARGE_INTEGER *)v7 + 22) = v15;
  if ( v15.QuadPart > *(unsigned __int64 *)&SystemTimeAsFileTime )
    *((struct _FILETIME *)v7 + 22) = SystemTimeAsFileTime;
  v16 = *((_DWORD *)v7 + 47) - *((_DWORD *)v7 + 62);
  if ( *((int *)v7 + 64) > 0 )
  {
    *((_DWORD *)v7 + 58) += v16;
    *((_DWORD *)v7 + 59) += *((_DWORD *)v7 + 49) - *((_DWORD *)v7 + 63);
  }
  else
  {
    *((_DWORD *)v7 + 60) += v16;
    *((_DWORD *)v7 + 61) += *((_DWORD *)v7 + 49) - *((_DWORD *)v7 + 63);
  }
}

```

## disassembly

```asm
0x140009ea8  test    rcx, rcx
0x140009eab  jz      locret_14000A0CC
0x140009eb1  mov     [rsp+arg_10], rbx
0x140009eb6  mov     [rsp+arg_18], rbp
0x140009ebb  push    rsi
0x140009ebc  push    rdi
0x140009ebd  push    r14
0x140009ebf  sub     rsp, 20h
0x140009ec3  mov     ebp, [rcx+8]
0x140009ec6  mov     rsi, rdx
0x140009ec9  mov     rdi, rcx
0x140009ecc  test    ebp, ebp
0x140009ece  jnz     short loc_140009EED
0x140009ed0  mov     al, cs:byte_1400820F2
0x140009ed6  mov     dl, al
0x140009ed8  inc     al
0x140009eda  add     dl, byte ptr cs:dword_14008210C
0x140009ee0  mov     cs:byte_1400820F2, al
0x140009ee6  mov     [rcx+50h], dl
0x140009ee9  xor     ecx, ecx
0x140009eeb  jmp     short loc_140009EF8
0x140009eed  test    rdx, rdx
0x140009ef0  jnz     loc_140009F84
0x140009ef6  mov     ecx, ebp; unsigned int
0x140009ef8  mov     rdx, rdi; struct _EVENT_RECORD *
0x140009efb  call    ?FindGlobalThreadById@@YAPEAU_THREAD_RECORD@@KPEAU_EVENT_RECORD@@@Z; FindGlobalThreadById(ulong,_EVENT_RECORD *)
0x140009f00  mov     [rsp+38h+arg_0], rax
0x140009f05  mov     rbx, rax
0x140009f08  mov     r14, rax
0x140009f0b  mov     rsi, rax
0x140009f0e  test    rax, rax
0x140009f11  jnz     short loc_140009F8A
0x140009f13  lea     r8, [rsp+38h+arg_0]; struct _THREAD_RECORD **
0x140009f18  mov     rdx, rdi; struct _EVENT_RECORD *
0x140009f1b  mov     ecx, ebp; unsigned int
0x140009f1d  call    ?AddThread@@YAEKPEAU_EVENT_RECORD@@PEAPEAU_THREAD_RECORD@@@Z; AddThread(ulong,_EVENT_RECORD *,_THREAD_RECORD * *)
0x140009f22  test    al, al
0x140009f24  jz      loc_14000A0BA
0x140009f2a  xor     edx, edx; unsigned __int8
0x140009f2c  xor     ecx, ecx; unsigned int
0x140009f2e  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x140009f33  mov     rdx, [rsp+38h+arg_0]
0x140009f38  mov     rcx, rdi
0x140009f3b  mov     [rdx+58h], rax
0x140009f3f  mov     dword ptr [rdx+6Ch], 1
0x140009f46  mov     byte ptr [rdx+68h], 1
0x140009f4a  mov     rax, [rdi+10h]
0x140009f4e  mov     [rdx+0B0h], rax
0x140009f55  mov     [rdx+0A8h], rax
0x140009f5c  mov     eax, [rdi+38h]
0x140009f5f  mov     [rdx+0BCh], eax
0x140009f65  mov     [rdx+0B8h], eax
0x140009f6b  mov     eax, [rdi+3Ch]
0x140009f6e  mov     [rdx+0C4h], eax
0x140009f74  mov     [rdx+0C0h], eax
0x140009f7a  call    AdjustThreadTime
0x140009f7f  jmp     loc_14000A0BA
0x140009f84  mov     r14, rdx
0x140009f87  mov     rbx, rdx
0x140009f8a  cmp     dword ptr [rbx+6Ch], 0
0x140009f8e  jnz     loc_14000A0BA
0x140009f94  cmp     byte ptr [rbx+68h], 0
0x140009f98  jz      short loc_140009FE3
0x140009f9a  lea     r9, [rsp+38h+arg_8]; unsigned int *
0x140009f9f  mov     dword ptr [rsp+38h+arg_0], 0
0x140009fa7  lea     r8, [rsp+38h+arg_0]; void *
0x140009fac  mov     [rsp+38h+arg_8], 4
0x140009fb4  lea     rdx, aProcessid; "ProcessId"
0x140009fbb  mov     rcx, rdi; Event
0x140009fbe  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x140009fc3  test    eax, eax
0x140009fc5  jnz     loc_14000A0BA
0x140009fcb  mov     ecx, dword ptr [rsp+38h+arg_0]; unsigned int
0x140009fcf  mov     dl, 1; unsigned __int8
0x140009fd1  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x140009fd6  test    rax, rax
0x140009fd9  jz      short loc_140009FE3
0x140009fdb  mov     byte ptr [rbx+68h], 0
0x140009fdf  mov     [rbx+58h], rax
0x140009fe3  cmp     byte ptr [rdi+2Dh], 4
0x140009fe7  jnz     short loc_14000A02C
0x140009fe9  mov     rax, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x140009ff0  cmp     byte ptr [rax+2139h], 0
0x140009ff7  jz      short loc_14000A01D
0x140009ff9  cmp     byte ptr cs:word_1400820C8+1, 0
0x14000a000  jnz     short loc_14000A01D
0x14000a002  mov     rax, [rdi+10h]
0x14000a006  cmp     qword ptr cs:SystemTimeAsFileTime.dwLowDateTime, rax
0x14000a00d  jbe     short loc_14000A016
0x14000a00f  mov     qword ptr cs:SystemTimeAsFileTime.dwLowDateTime, rax
0x14000a016  mov     byte ptr cs:word_1400820C8+1, 1
0x14000a01d  lea     rcx, [r14+20h]
0x14000a021  mov     r8, rsi
0x14000a024  mov     rdx, rdi
0x14000a027  call    StopThreadTrans
0x14000a02c  mov     dword ptr [rbx+6Ch], 1
0x14000a033  mov     eax, [rdi+3Ch]
0x14000a036  cmp     [rbx+0C4h], eax
0x14000a03c  jnb     short loc_14000A044
0x14000a03e  mov     [rbx+0C4h], eax
0x14000a044  mov     eax, [rdi+38h]
0x14000a047  cmp     [rbx+0BCh], eax
0x14000a04d  jnb     short loc_14000A055
0x14000a04f  mov     [rbx+0BCh], eax
0x14000a055  mov     rax, [rdi+10h]
0x14000a059  mov     [rbx+0B0h], rax
0x14000a060  mov     rcx, qword ptr cs:SystemTimeAsFileTime.dwLowDateTime
0x14000a067  cmp     rax, rcx
0x14000a06a  jbe     short loc_14000A073
0x14000a06c  mov     [rbx+0B0h], rcx
0x14000a073  mov     eax, [rbx+0BCh]
0x14000a079  sub     eax, [rbx+0F8h]
0x14000a07f  cmp     dword ptr [rbx+100h], 0
0x14000a086  jg      short loc_14000A0A2
0x14000a088  add     [rbx+0F0h], eax
0x14000a08e  mov     eax, [rbx+0C4h]
0x14000a094  sub     eax, [rbx+0FCh]
0x14000a09a  add     [rbx+0F4h], eax
0x14000a0a0  jmp     short loc_14000A0BA
0x14000a0a2  add     [rbx+0E8h], eax
0x14000a0a8  mov     eax, [rbx+0C4h]
0x14000a0ae  sub     eax, [rbx+0FCh]
0x14000a0b4  add     [rbx+0ECh], eax
0x14000a0ba  mov     rbx, [rsp+38h+arg_10]
0x14000a0bf  mov     rbp, [rsp+38h+arg_18]
0x14000a0c4  add     rsp, 20h
0x14000a0c8  pop     r14
0x14000a0ca  pop     rdi
0x14000a0cb  pop     rsi
0x14000a0cc  retn
```
