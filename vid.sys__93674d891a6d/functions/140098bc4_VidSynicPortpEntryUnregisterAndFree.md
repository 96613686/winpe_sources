# VidSynicPortpEntryUnregisterAndFree

- ea: `0x140098bc4`
- end: `0x140098cf0`
- name: `VidSynicPortpEntryUnregisterAndFree`
- size: `300`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140097e3c`
- `0x1400981f0`

## callees

- `0x140098b5c`
- `0x140098bc4`
- `0x140098dd4`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x140098cb1`
- `ntoskrnl!KeWaitForSingleObject` at `0x140098cb1`
- `ntoskrnl!KeInitializeEvent` at `0x140098c74`
- `ntoskrnl!KeInitializeEvent` at `0x140098c74`
- `winhvr!WinHvDisconnectDoorbell` at `0x140098c1d`
- `winhvr!WinHvDisconnectDoorbell` at `0x140098c1d`
- `winhvr!WinHvGetPortProperty` at `0x140098c5c`
- `winhvr!WinHvGetPortProperty` at `0x140098c5c`
- `winhvr!WinHvDisconnectPort` at `0x140098c2b`
- `winhvr!WinHvDisconnectPort` at `0x140098c2b`
- `winhvr!WinHvDeletePort` at `0x140098ccb`
- `winhvr!WinHvDeletePort` at `0x140098ccb`

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
0x140098bc4  mov     r11, rsp
0x140098bc7  mov     [r11+8], rbx
0x140098bcb  mov     [r11+20h], rsi
0x140098bcf  push    rdi
0x140098bd0  sub     rsp, 50h
0x140098bd4  xor     eax, eax
0x140098bd6  mov     qword ptr [r11+10h], 0
0x140098bde  xorps   xmm0, xmm0
0x140098be1  mov     rbx, rdx
0x140098be4  movups  xmmword ptr [rsp+58h+Event.Header], xmm0
0x140098be9  mov     [r11-18h], rax
0x140098bed  mov     rsi, rcx
0x140098bf0  mov     eax, [rdx]
0x140098bf2  cmp     eax, 3
0x140098bf5  jnz     short loc_140098C01
0x140098bf7  mov     rcx, rdx
0x140098bfa  call    VidSynicPortpUnmapMonitorPage
0x140098bff  mov     eax, [rbx]
0x140098c01  or      rdi, 0FFFFFFFFFFFFFFFFh
0x140098c05  cmp     byte ptr [rbx+28h], 0
0x140098c09  mov     rcx, rdi
0x140098c0c  jnz     short loc_140098C15
0x140098c0e  mov     rcx, [rsi+288h]
0x140098c15  mov     edx, [rbx+8]
0x140098c18  cmp     eax, 4
0x140098c1b  jnz     short loc_140098C2B
0x140098c1d  call    cs:__imp_WinHvDisconnectDoorbell
0x140098c24  nop     dword ptr [rax+rax+00h]
0x140098c29  jmp     short loc_140098C37
0x140098c2b  call    cs:__imp_WinHvDisconnectPort
0x140098c32  nop     dword ptr [rax+rax+00h]
0x140098c37  cmp     byte ptr [rbx+28h], 0
0x140098c3b  jz      short loc_140098C46
0x140098c3d  mov     rdi, [rsi+288h]
0x140098c44  jmp     short loc_140098CC5
0x140098c46  cmp     dword ptr [rbx], 3
0x140098c49  jz      short loc_140098CC5
0x140098c4b  mov     edx, [rbx+4]
0x140098c4e  lea     r9, [rsp+58h+arg_8]
0x140098c53  mov     r8d, 8
0x140098c59  mov     rcx, rdi
0x140098c5c  call    cs:__imp_WinHvGetPortProperty
0x140098c63  nop     dword ptr [rax+rax+00h]
0x140098c68  xor     r8d, r8d; State
0x140098c6b  lea     rcx, [rsp+58h+Event]; Event
0x140098c70  lea     edx, [r8+1]; Type
0x140098c74  call    cs:__imp_KeInitializeEvent
0x140098c7b  nop     dword ptr [rax+rax+00h]
0x140098c80  lea     rax, [rsp+58h+Event]
0x140098c85  mov     [rbx+20h], rax
0x140098c89  mov     rax, [rsp+58h+arg_8]
0x140098c8e  lock xadd [rbx+18h], rax
0x140098c94  add     [rsp+58h+arg_8], rax
0x140098c99  jz      short loc_140098CBD
0x140098c9b  xor     r9d, r9d; Alertable
0x140098c9e  mov     [rsp+58h+Timeout], 0; Timeout
0x140098ca7  xor     r8d, r8d; WaitMode
0x140098caa  lea     rcx, [rsp+58h+Event]; Object
0x140098caf  xor     edx, edx; WaitReason
0x140098cb1  call    cs:__imp_KeWaitForSingleObject
0x140098cb8  nop     dword ptr [rax+rax+00h]
0x140098cbd  mov     qword ptr [rbx+20h], 0
0x140098cc5  mov     edx, [rbx+4]
0x140098cc8  mov     rcx, rdi
0x140098ccb  call    cs:__imp_WinHvDeletePort
0x140098cd2  nop     dword ptr [rax+rax+00h]
0x140098cd7  mov     rdx, rbx
0x140098cda  call    VidSynicPortpEntryFree
0x140098cdf  mov     rbx, [rsp+58h+arg_0]
0x140098ce4  mov     rsi, [rsp+58h+arg_18]
0x140098ce9  add     rsp, 50h
0x140098ced  pop     rdi
0x140098cee  retn
```
