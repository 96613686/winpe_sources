# VidSynicPortpEntryUnregisterAndFree

- ea: `0x140097194`
- end: `0x1400972c0`
- name: `VidSynicPortpEntryUnregisterAndFree`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14009640c`
- `0x1400967c0`

## callees

- `0x14009712c`
- `0x140097194`
- `0x1400973a4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140097281`
- `ntoskrnl!KeWaitForSingleObject` at `0x140097281`
- `ntoskrnl!KeInitializeEvent` at `0x140097244`
- `ntoskrnl!KeInitializeEvent` at `0x140097244`
- `winhvr!WinHvDisconnectDoorbell` at `0x1400971ed`
- `winhvr!WinHvDisconnectDoorbell` at `0x1400971ed`
- `winhvr!WinHvGetPortProperty` at `0x14009722c`
- `winhvr!WinHvGetPortProperty` at `0x14009722c`
- `winhvr!WinHvDisconnectPort` at `0x1400971fb`
- `winhvr!WinHvDisconnectPort` at `0x1400971fb`
- `winhvr!WinHvDeletePort` at `0x14009729b`
- `winhvr!WinHvDeletePort` at `0x14009729b`

## pseudocode

```c
__int64 __fastcall VidSynicPortpEntryUnregisterAndFree(__int64 a1, int *a2)
{
  int v4; // eax
  __int64 v5; // rdi
  __int64 v6; // rcx
  __int64 v7; // rdx
  signed __int64 v8; // rax
  __int64 v9; // rcx
  struct _KEVENT Event; // [rsp+30h] [rbp-28h] BYREF
  unsigned __int64 v12; // [rsp+68h] [rbp+10h] BYREF

  v12 = 0;
  memset(&Event, 0, sizeof(Event));
  v4 = *a2;
  if ( *a2 == 3 )
  {
    VidSynicPortpUnmapMonitorPage(a2);
    v4 = *a2;
  }
  v5 = -1;
  v6 = -1;
  if ( !*((_BYTE *)a2 + 40) )
    v6 = *(_QWORD *)(a1 + 648);
  v7 = (unsigned int)a2[2];
  if ( v4 == 4 )
    WinHvDisconnectDoorbell(v6, v7);
  else
    WinHvDisconnectPort(v6, v7);
  if ( *((_BYTE *)a2 + 40) )
  {
    v5 = *(_QWORD *)(a1 + 648);
  }
  else if ( *a2 != 3 )
  {
    WinHvGetPortProperty(-1, (unsigned int)a2[1], 8, &v12);
    KeInitializeEvent(&Event, SynchronizationEvent, 0);
    *((_QWORD *)a2 + 4) = &Event;
    v8 = _InterlockedExchangeAdd64((volatile signed __int64 *)a2 + 3, v12);
    v12 += v8;
    if ( v12 )
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    *((_QWORD *)a2 + 4) = 0;
  }
  WinHvDeletePort(v5, (unsigned int)a2[1]);
  return VidSynicPortpEntryFree(v9, a2);
}

```

## disassembly

```asm
0x140097194  mov     r11, rsp
0x140097197  mov     [r11+8], rbx
0x14009719b  mov     [r11+20h], rsi
0x14009719f  push    rdi
0x1400971a0  sub     rsp, 50h
0x1400971a4  xor     eax, eax
0x1400971a6  mov     qword ptr [r11+10h], 0
0x1400971ae  xorps   xmm0, xmm0
0x1400971b1  mov     rbx, rdx
0x1400971b4  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x1400971b9  mov     [r11-18h], rax
0x1400971bd  mov     rsi, rcx
0x1400971c0  mov     eax, [rdx]
0x1400971c2  cmp     eax, 3
0x1400971c5  jnz     short loc_1400971D1
0x1400971c7  mov     rcx, rdx
0x1400971ca  call    VidSynicPortpUnmapMonitorPage
0x1400971cf  mov     eax, [rbx]
0x1400971d1  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1400971d5  cmp     byte ptr [rbx+28h], 0
0x1400971d9  mov     rcx, rdi
0x1400971dc  jnz     short loc_1400971E5
0x1400971de  mov     rcx, [rsi+288h]
0x1400971e5  mov     edx, [rbx+8]
0x1400971e8  cmp     eax, 4
0x1400971eb  jnz     short loc_1400971FB
0x1400971ed  call    cs:__imp_WinHvDisconnectDoorbell
0x1400971f4  nop     dword ptr [rax+rax+00h]
0x1400971f9  jmp     short loc_140097207
0x1400971fb  call    cs:__imp_WinHvDisconnectPort
0x140097202  nop     dword ptr [rax+rax+00h]
0x140097207  cmp     byte ptr [rbx+28h], 0
0x14009720b  jz      short loc_140097216
0x14009720d  mov     rdi, [rsi+288h]
0x140097214  jmp     short loc_140097295
0x140097216  cmp     dword ptr [rbx], 3
0x140097219  jz      short loc_140097295
0x14009721b  mov     edx, [rbx+4]
0x14009721e  lea     r9, [rsp+58h+arg_8]
0x140097223  mov     r8d, 8
0x140097229  mov     rcx, rdi
0x14009722c  call    cs:__imp_WinHvGetPortProperty
0x140097233  nop     dword ptr [rax+rax+00h]
0x140097238  xor     r8d, r8d; State
0x14009723b  lea     rcx, [rsp+58h+Event]; Event
0x140097240  lea     edx, [r8+1]; Type
0x140097244  call    cs:__imp_KeInitializeEvent
0x14009724b  nop     dword ptr [rax+rax+00h]
0x140097250  lea     rax, [rsp+58h+Event]
0x140097255  mov     [rbx+20h], rax
0x140097259  mov     rax, [rsp+58h+arg_8]
0x14009725e  lock xadd [rbx+18h], rax
0x140097264  add     [rsp+58h+arg_8], rax
0x140097269  jz      short loc_14009728D
0x14009726b  xor     r9d, r9d; Alertable
0x14009726e  mov     [rsp+58h+Timeout], 0; Timeout
0x140097277  xor     r8d, r8d; WaitMode
0x14009727a  lea     rcx, [rsp+58h+Event]; Object
0x14009727f  xor     edx, edx; WaitReason
0x140097281  call    cs:__imp_KeWaitForSingleObject
0x140097288  nop     dword ptr [rax+rax+00h]
0x14009728d  mov     qword ptr [rbx+20h], 0
0x140097295  mov     edx, [rbx+4]
0x140097298  mov     rcx, rdi
0x14009729b  call    cs:__imp_WinHvDeletePort
0x1400972a2  nop     dword ptr [rax+rax+00h]
0x1400972a7  mov     rdx, rbx
0x1400972aa  call    VidSynicPortpEntryFree
0x1400972af  mov     rbx, [rsp+58h+arg_0]
0x1400972b4  mov     rsi, [rsp+58h+arg_18]
0x1400972b9  add     rsp, 50h
0x1400972bd  pop     rdi
0x1400972be  retn
```
