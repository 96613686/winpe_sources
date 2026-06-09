# ThStartCallback

- ea: `0x14000a0d4`
- end: `0x14000a39c`
- name: `ThStartCallback`
- size: `712`
- prototype: `__int64 __fastcall(PEVENT_RECORD Event)`
- caller_count: `1`
- callee_count: `12`
- tags: `authz_impersonation, service_task`

## callers

- `0x140003a30`

## callees

- `0x140002c20`
- `0x140004c2c`
- `0x140009ea8`
- `0x14000a0d4`
- `0x140011728`
- `0x14001b7c8`
- `0x14001b968`
- `0x14001ceb0`
- `0x14001d51c`
- `0x14001d700`
- `0x1400400d6`
- `0x140040130`

## string_xrefs

- `0x14000a149`: `ProcessId`
- `0x14000a121`: `TThreadId`

## pseudocode

```c
void __fastcall ThStartCallback(PEVENT_RECORD Event)
{
  unsigned int v2; // esi
  unsigned int v3; // r14d
  struct _THREAD_RECORD *v4; // r15
  char v5; // r12
  UCHAR v6; // cl
  struct _THREAD_RECORD *GlobalThreadById; // rax
  struct _THREAD_RECORD *v8; // rbx
  unsigned int v9; // eax
  unsigned int v10; // eax
  LARGE_INTEGER *p_TimeStamp; // rsi
  __int64 v12; // r8
  __int64 v13; // r9
  struct _THREAD_RECORD *v14; // rdx
  unsigned int v15; // [rsp+20h] [rbp-89h] BYREF
  unsigned int v16; // [rsp+24h] [rbp-85h] BYREF
  struct _THREAD_RECORD *ProcessById; // [rsp+28h] [rbp-81h] BYREF
  unsigned int v18[4]; // [rsp+30h] [rbp-79h] BYREF
  struct _EVENT_RECORD Eventa; // [rsp+40h] [rbp-69h] BYREF

  if ( !Event )
    return;
  v16 = 4;
  v18[0] = 0;
  v15 = 0;
  if ( GetMofData(Event, L"TThreadId", &v15, &v16) )
    return;
  v2 = v15;
  if ( GetMofData(Event, L"ProcessId", &v15, &v16) )
    return;
  v3 = v15;
  ProcessById = FindProcessById(v15, 1u);
  v4 = ProcessById;
  if ( !ProcessById )
  {
    if ( !AddProcess(v3, &ProcessById) )
      return;
    v4 = ProcessById;
  }
  v5 = 0;
  if ( !v2 )
  {
    v6 = dword_14008210C + byte_1400820F1++;
    Event->BufferContext.ProcessorNumber = v6;
  }
  GlobalThreadById = FindGlobalThreadById(v2, Event);
  ProcessById = GlobalThreadById;
  v8 = GlobalThreadById;
  if ( !v2 || !GlobalThreadById || *((_DWORD *)GlobalThreadById + 27) )
    goto LABEL_19;
  if ( !*((_BYTE *)GlobalThreadById + 104) )
  {
    memset_0(&Eventa, 0, sizeof(Eventa));
    Eventa.EventHeader.TimeStamp.QuadPart = Event->EventHeader.TimeStamp.QuadPart;
    Eventa.EventHeader.EventDescriptor.Opcode = 2;
    Eventa.EventHeader.ThreadId = v2;
    Eventa.EventHeader.UserTime = *((_DWORD *)v8 + 49);
    Eventa.EventHeader.KernelTime = *((_DWORD *)v8 + 47);
    v9 = *((_DWORD *)v8 + 46);
    if ( *((_DWORD *)v8 + 47) < v9 )
      *((_DWORD *)v8 + 47) = v9;
    v10 = *((_DWORD *)v8 + 48);
    if ( *((_DWORD *)v8 + 49) < v10 )
      *((_DWORD *)v8 + 49) = v10;
    ThEndCallback(&Eventa);
LABEL_19:
    if ( !AddThread(v2, Event, &ProcessById) )
      return;
    v8 = ProcessById;
    goto LABEL_21;
  }
  *((_BYTE *)GlobalThreadById + 104) = 0;
  v5 = 1;
LABEL_21:
  *((_QWORD *)v8 + 11) = v4;
  p_TimeStamp = &Event->EventHeader.TimeStamp;
  *((_QWORD *)v8 + 21) = Event->EventHeader.TimeStamp.QuadPart;
  v16 = 4;
  if ( !GetMofData(Event, L"SubProcessTag", v18, &v16) )
  {
    if ( v18[0] && v3 == Event->EventHeader.ProcessId )
      *((_QWORD *)v8 + 12) = FindOrAddService(v18[0], v3);
    if ( Event->EventHeader.EventDescriptor.Opcode == 3 )
    {
      if ( *((_BYTE *)g_TraceContext + 8505) && !(_BYTE)word_1400820C8 )
      {
        if ( *(unsigned __int64 *)&CurrentSystem < p_TimeStamp->QuadPart )
        {
          if ( (*((_DWORD *)g_TraceContext + 1604) & 0x1000) != 0 )
            CalculateTimeStamp((union _LARGE_INTEGER *)&CurrentSystem, &Event->EventHeader.TimeStamp);
          else
            CurrentSystem = (struct _FILETIME)p_TimeStamp->QuadPart;
        }
        LOBYTE(word_1400820C8) = 1;
      }
      *((_DWORD *)v8 + 46) = Event->EventHeader.KernelTime;
      *((_DWORD *)v8 + 48) = Event->EventHeader.UserTime;
    }
    else
    {
      *((_DWORD *)v8 + 46) = 0;
      *((_DWORD *)v8 + 48) = 0;
    }
    if ( Event->EventHeader.EventDescriptor.Opcode == 3 )
      v14 = v8;
    else
      v14 = 0;
    AdjustThreadTime(Event, v14, v12, v13);
    if ( !v5 )
    {
      *((_QWORD *)v8 + 29) = 0;
      *((_QWORD *)v8 + 30) = 0;
      *((_DWORD *)v8 + 64) = 0;
      *((_DWORD *)v8 + 62) = *((_DWORD *)v8 + 46);
      *((_DWORD *)v8 + 63) = *((_DWORD *)v8 + 48);
    }
  }
}

```

## disassembly

```asm
0x14000a0d4  test    rcx, rcx
0x14000a0d7  jz      locret_14000A39B
0x14000a0dd  push    rbp
0x14000a0de  push    rbx
0x14000a0df  push    rsi
0x14000a0e0  push    rdi
0x14000a0e1  push    r12
0x14000a0e3  push    r13
0x14000a0e5  push    r14
0x14000a0e7  push    r15
0x14000a0e9  lea     rbp, [rsp-1Fh]
0x14000a0ee  sub     rsp, 0C8h
0x14000a0f5  mov     rax, cs:__security_cookie
0x14000a0fc  xor     rax, rsp
0x14000a0ff  mov     [rbp+57h+var_50], rax
0x14000a103  xor     r13d, r13d
0x14000a106  mov     [rsp+100h+var_DC], 4
0x14000a10e  lea     r9, [rsp+100h+var_DC]; unsigned int *
0x14000a113  mov     [rbp+57h+var_D0], r13d
0x14000a117  lea     r8, [rsp+100h+var_E0]; void *
0x14000a11c  mov     [rsp+100h+var_E0], r13d
0x14000a121  lea     rdx, aTthreadid; "TThreadId"
0x14000a128  mov     rdi, rcx
0x14000a12b  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000a130  test    eax, eax
0x14000a132  jnz     loc_14000A37C
0x14000a138  mov     esi, [rsp+100h+var_E0]
0x14000a13c  lea     r9, [rsp+100h+var_DC]; unsigned int *
0x14000a141  lea     r8, [rsp+100h+var_E0]; void *
0x14000a146  mov     rcx, rdi; Event
0x14000a149  lea     rdx, aProcessid; "ProcessId"
0x14000a150  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000a155  test    eax, eax
0x14000a157  jnz     loc_14000A37C
0x14000a15d  mov     r14d, [rsp+100h+var_E0]
0x14000a162  mov     dl, 1; unsigned __int8
0x14000a164  mov     ecx, r14d; unsigned int
0x14000a167  call    ?FindProcessById@@YAPEAU_PROCESS_RECORD@@KE@Z; FindProcessById(ulong,uchar)
0x14000a16c  mov     [rsp+100h+var_D8], rax
0x14000a171  mov     r15, rax
0x14000a174  test    rax, rax
0x14000a177  jnz     short loc_14000A193
0x14000a179  lea     rdx, [rsp+100h+var_D8]; struct _PROCESS_RECORD **
0x14000a17e  mov     ecx, r14d; unsigned int
0x14000a181  call    ?AddProcess@@YAEKPEAPEAU_PROCESS_RECORD@@@Z; AddProcess(ulong,_PROCESS_RECORD * *)
0x14000a186  test    al, al
0x14000a188  jz      loc_14000A37C
0x14000a18e  mov     r15, [rsp+100h+var_D8]
0x14000a193  mov     r12b, r13b
0x14000a196  test    esi, esi
0x14000a198  jnz     short loc_14000A1B3
0x14000a19a  mov     al, cs:byte_1400820F1
0x14000a1a0  mov     cl, al
0x14000a1a2  add     cl, byte ptr cs:dword_14008210C
0x14000a1a8  inc     al
0x14000a1aa  mov     cs:byte_1400820F1, al
0x14000a1b0  mov     [rdi+50h], cl
0x14000a1b3  mov     rdx, rdi; struct _EVENT_RECORD *
0x14000a1b6  mov     ecx, esi; unsigned int
0x14000a1b8  call    ?FindGlobalThreadById@@YAPEAU_THREAD_RECORD@@KPEAU_EVENT_RECORD@@@Z; FindGlobalThreadById(ulong,_EVENT_RECORD *)
0x14000a1bd  mov     [rsp+100h+var_D8], rax
0x14000a1c2  mov     rbx, rax
0x14000a1c5  test    esi, esi
0x14000a1c7  jz      loc_14000A24E
0x14000a1cd  test    rax, rax
0x14000a1d0  jz      short loc_14000A24E
0x14000a1d2  cmp     [rax+6Ch], r13d
0x14000a1d6  jnz     short loc_14000A24E
0x14000a1d8  cmp     [rax+68h], r13b
0x14000a1dc  jz      short loc_14000A1EA
0x14000a1de  mov     [rax+68h], r13b
0x14000a1e2  mov     r12b, 1
0x14000a1e5  jmp     loc_14000A26A
0x14000a1ea  xor     edx, edx; Val
0x14000a1ec  lea     rcx, [rbp+57h+Event]; void *
0x14000a1f0  lea     r8d, [rdx+70h]; Size
0x14000a1f4  call    memset_0
0x14000a1f9  mov     rax, [rdi+10h]
0x14000a1fd  mov     qword ptr [rbp+57h+Event.EventHeader.TimeStamp], rax
0x14000a201  mov     [rbp+57h+Event.EventHeader.EventDescriptor.Opcode], 2
0x14000a205  mov     [rbp+57h+Event.EventHeader.ThreadId], esi
0x14000a208  mov     eax, [rbx+0C4h]
0x14000a20e  mov     dword ptr [rbp+57h+Event.EventHeader.38h+4], eax
0x14000a211  mov     eax, [rbx+0BCh]
0x14000a217  mov     dword ptr [rbp+57h+Event.EventHeader.38h], eax
0x14000a21a  mov     eax, [rbx+0B8h]
0x14000a220  cmp     [rbx+0BCh], eax
0x14000a226  jnb     short loc_14000A22E
0x14000a228  mov     [rbx+0BCh], eax
0x14000a22e  mov     eax, [rbx+0C0h]
0x14000a234  cmp     [rbx+0C4h], eax
0x14000a23a  jnb     short loc_14000A242
0x14000a23c  mov     [rbx+0C4h], eax
0x14000a242  mov     rdx, rbx
0x14000a245  lea     rcx, [rbp+57h+Event]; Event
0x14000a249  call    ThEndCallback
0x14000a24e  lea     r8, [rsp+100h+var_D8]; struct _THREAD_RECORD **
0x14000a253  mov     rdx, rdi; struct _EVENT_RECORD *
0x14000a256  mov     ecx, esi; unsigned int
0x14000a258  call    ?AddThread@@YAEKPEAU_EVENT_RECORD@@PEAPEAU_THREAD_RECORD@@@Z; AddThread(ulong,_EVENT_RECORD *,_THREAD_RECORD * *)
0x14000a25d  test    al, al
0x14000a25f  jz      loc_14000A37C
0x14000a265  mov     rbx, [rsp+100h+var_D8]
0x14000a26a  mov     [rbx+58h], r15
0x14000a26e  lea     rsi, [rdi+10h]
0x14000a272  mov     rax, [rsi]
0x14000a275  lea     r9, [rsp+100h+var_DC]; unsigned int *
0x14000a27a  mov     [rbx+0A8h], rax
0x14000a281  lea     r8, [rbp+57h+var_D0]; void *
0x14000a285  lea     rdx, aSubprocesstag; "SubProcessTag"
0x14000a28c  mov     [rsp+100h+var_DC], 4
0x14000a294  mov     rcx, rdi; Event
0x14000a297  call    ?GetMofData@@YAKPEAU_EVENT_RECORD@@PEAGPEAXPEAK@Z; GetMofData(_EVENT_RECORD *,ushort *,void *,ulong *)
0x14000a29c  test    eax, eax
0x14000a29e  jnz     loc_14000A37C
0x14000a2a4  mov     ecx, [rbp+57h+var_D0]; unsigned int
0x14000a2a7  test    ecx, ecx
0x14000a2a9  jz      short loc_14000A2BD
0x14000a2ab  cmp     r14d, [rdi+0Ch]
0x14000a2af  jnz     short loc_14000A2BD
0x14000a2b1  mov     edx, r14d; unsigned int
0x14000a2b4  call    ?FindOrAddService@@YAPEAU_SERVICE_RECORD@@KK@Z; FindOrAddService(ulong,ulong)
0x14000a2b9  mov     [rbx+60h], rax
0x14000a2bd  cmp     byte ptr [rdi+2Dh], 3
0x14000a2c1  jnz     short loc_14000A327
0x14000a2c3  mov     rcx, cs:?g_TraceContext@@3PEAU_TRACE_CONTEXT_BLOCK@@EA; _TRACE_CONTEXT_BLOCK * g_TraceContext
0x14000a2ca  cmp     [rcx+2139h], r13b
0x14000a2d1  jz      short loc_14000A313
0x14000a2d3  cmp     byte ptr cs:word_1400820C8, r13b
0x14000a2da  jnz     short loc_14000A313
0x14000a2dc  mov     rax, [rsi]
0x14000a2df  cmp     qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime, rax; _SYSTEM_RECORD CurrentSystem ...
0x14000a2e6  jnb     short loc_14000A30C
0x14000a2e8  test    dword ptr [rcx+1910h], 1000h
0x14000a2f2  jz      short loc_14000A305
0x14000a2f4  mov     rdx, rsi; union _LARGE_INTEGER *
0x14000a2f7  lea     rcx, ?CurrentSystem@@3U_SYSTEM_RECORD@@A; union _LARGE_INTEGER *
0x14000a2fe  call    ?CalculateTimeStamp@@YAXPEAT_LARGE_INTEGER@@0@Z; CalculateTimeStamp(_LARGE_INTEGER *,_LARGE_INTEGER *)
0x14000a303  jmp     short loc_14000A30C
0x14000a305  mov     qword ptr cs:?CurrentSystem@@3U_SYSTEM_RECORD@@A.dwLowDateTime, rax; _SYSTEM_RECORD CurrentSystem ...
0x14000a30c  mov     byte ptr cs:word_1400820C8, 1
0x14000a313  mov     eax, [rdi+38h]
0x14000a316  mov     [rbx+0B8h], eax
0x14000a31c  mov     eax, [rdi+3Ch]
0x14000a31f  mov     [rbx+0C0h], eax
0x14000a325  jmp     short loc_14000A335
0x14000a327  mov     [rbx+0B8h], r13d
0x14000a32e  mov     [rbx+0C0h], r13d
0x14000a335  cmp     byte ptr [rdi+2Dh], 3
0x14000a339  mov     rcx, rdi
0x14000a33c  jnz     short loc_14000A343
0x14000a33e  mov     rdx, rbx
0x14000a341  jmp     short loc_14000A345
0x14000a343  xor     edx, edx
0x14000a345  call    AdjustThreadTime
0x14000a34a  test    r12b, r12b
0x14000a34d  jnz     short loc_14000A37C
0x14000a34f  mov     [rbx+0E8h], r13
0x14000a356  mov     [rbx+0F0h], r13
0x14000a35d  mov     [rbx+100h], r13d
0x14000a364  mov     eax, [rbx+0B8h]
0x14000a36a  mov     [rbx+0F8h], eax
0x14000a370  mov     eax, [rbx+0C0h]
0x14000a376  mov     [rbx+0FCh], eax
0x14000a37c  mov     rcx, [rbp+57h+var_50]
0x14000a380  xor     rcx, rsp; StackCookie
0x14000a383  call    __security_check_cookie
0x14000a388  add     rsp, 0C8h
0x14000a38f  pop     r15
0x14000a391  pop     r14
0x14000a393  pop     r13
0x14000a395  pop     r12
0x14000a397  pop     rdi
0x14000a398  pop     rsi
0x14000a399  pop     rbx
0x14000a39a  pop     rbp
0x14000a39b  retn
```
