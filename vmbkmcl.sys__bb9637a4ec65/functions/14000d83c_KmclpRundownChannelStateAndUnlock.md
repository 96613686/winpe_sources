# KmclpRundownChannelStateAndUnlock

- ea: `0x14000d83c`
- end: `0x14000d9a1`
- name: `KmclpRundownChannelStateAndUnlock`
- size: `357`
- prototype: `__int64 __fastcall(PVOID Context)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000c87c`
- `0x14000cfe4`
- `0x14001d3b0`

## callees

- `0x140006e00`
- `0x14000ab90`
- `0x14000bb70`
- `0x14000d83c`
- `0x14000f688`

## import_xrefs

- `ntoskrnl!KeInitializeEvent` at `0x14000d8b8`
- `ntoskrnl!KeInitializeEvent` at `0x14000d8b8`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d952`
- `ntoskrnl!KeWaitForSingleObject` at `0x14000d952`

## pseudocode

```c
void __fastcall KmclpRundownChannelStateAndUnlock(_DWORD *Context, __int64 a2, __int64 a3)
{
  char v3; // di
  __int128 Event; // [rsp+40h] [rbp-28h] BYREF
  __int128 Event_16; // [rsp+50h] [rbp-18h]

  v3 = a2;
  Event = 0;
  Event_16 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qLLd(WPP_GLOBAL_Control->AttachedDevice, 116, a3, Context, Context[550], Context[551], (unsigned __int8)a2);
  }
  if ( v3 )
  {
    KeInitializeEvent((PRKEVENT)&Event, SynchronizationEvent, 0);
    *((_QWORD *)&Event_16 + 1) = *((_QWORD *)Context + 276);
    *((_QWORD *)Context + 276) = &Event;
  }
  else
  {
    *((_BYTE *)Context + 2344) |= 0x40u;
  }
  if ( (unsigned int)(Context[550] - 8) <= 3 )
    KmclUnlockChannel((__int64)Context);
  else
    KmclpContinueChannelRundownAndUnlock((char *)Context, a2, a3);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x75u,
        (__int64)WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
        Context);
    }
    KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    {
      WPP_SF_q(
        (__int64)WPP_GLOBAL_Control->AttachedDevice,
        0x76u,
        (__int64)WPP_fa014546bb113ca58de70d4b381949e7_Traceguids,
        Context);
    }
  }
}

```

## disassembly

```asm
0x14000d83c  mov     rax, rsp
0x14000d83f  mov     [rax+8], rbx
0x14000d843  mov     [rax+10h], rdi
0x14000d847  push    r14
0x14000d849  sub     rsp, 60h
0x14000d84d  xorps   xmm0, xmm0
0x14000d850  movzx   edi, dl
0x14000d853  movups  xmmword ptr [rax-28h], xmm0
0x14000d857  mov     rbx, rcx
0x14000d85a  movups  xmmword ptr [rax-18h], xmm0
0x14000d85e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d865  lea     r14, WPP_GLOBAL_Control
0x14000d86c  cmp     rcx, r14
0x14000d86f  jz      short loc_14000D8A7
0x14000d871  mov     eax, [rcx+2Ch]
0x14000d874  test    al, 1
0x14000d876  jz      short loc_14000D8A7
0x14000d878  cmp     byte ptr [rcx+29h], 4
0x14000d87c  jb      short loc_14000D8A7
0x14000d87e  mov     eax, [rbx+89Ch]
0x14000d884  mov     edx, 74h ; 't'
0x14000d889  mov     rcx, [rcx+18h]
0x14000d88d  mov     r9, rbx
0x14000d890  mov     [rsp+68h+var_38], edi
0x14000d894  mov     [rsp+68h+var_40], eax
0x14000d898  mov     eax, [rbx+898h]
0x14000d89e  mov     dword ptr [rsp+68h+Timeout], eax
0x14000d8a2  call    WPP_SF_qLLd
0x14000d8a7  test    dil, dil
0x14000d8aa  jz      short loc_14000D8DE
0x14000d8ac  xor     r8d, r8d; State
0x14000d8af  lea     rcx, [rsp+68h+Event]; Event
0x14000d8b4  lea     edx, [r8+1]; Type
0x14000d8b8  call    cs:__imp_KeInitializeEvent
0x14000d8bf  nop     dword ptr [rax+rax+00h]
0x14000d8c4  mov     rax, [rbx+8A0h]
0x14000d8cb  mov     [rsp+68h+var_10], rax
0x14000d8d0  lea     rax, [rsp+68h+Event]
0x14000d8d5  mov     [rbx+8A0h], rax
0x14000d8dc  jmp     short loc_14000D8E5
0x14000d8de  or      byte ptr [rbx+928h], 40h
0x14000d8e5  mov     eax, [rbx+898h]
0x14000d8eb  mov     rcx, rbx; Context
0x14000d8ee  sub     eax, 8
0x14000d8f1  cmp     eax, 3
0x14000d8f4  jbe     short loc_14000D8FD
0x14000d8f6  call    KmclpContinueChannelRundownAndUnlock
0x14000d8fb  jmp     short loc_14000D902
0x14000d8fd  call    KmclUnlockChannel
0x14000d902  test    dil, dil
0x14000d905  jz      loc_14000D98F
0x14000d90b  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d912  cmp     rcx, r14
0x14000d915  jz      short loc_14000D93C
0x14000d917  mov     eax, [rcx+2Ch]
0x14000d91a  test    al, 1
0x14000d91c  jz      short loc_14000D93C
0x14000d91e  cmp     byte ptr [rcx+29h], 4
0x14000d922  jb      short loc_14000D93C
0x14000d924  mov     rcx, [rcx+18h]
0x14000d928  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000d92f  mov     edx, 75h ; 'u'
0x14000d934  mov     r9, rbx
0x14000d937  call    WPP_SF_q
0x14000d93c  xor     r9d, r9d; Alertable
0x14000d93f  mov     [rsp+68h+Timeout], 0; Timeout
0x14000d948  xor     r8d, r8d; WaitMode
0x14000d94b  lea     rcx, [rsp+68h+Event]; Object
0x14000d950  xor     edx, edx; WaitReason
0x14000d952  call    cs:__imp_KeWaitForSingleObject
0x14000d959  nop     dword ptr [rax+rax+00h]
0x14000d95e  mov     rcx, cs:WPP_GLOBAL_Control
0x14000d965  cmp     rcx, r14
0x14000d968  jz      short loc_14000D98F
0x14000d96a  mov     eax, [rcx+2Ch]
0x14000d96d  test    al, 1
0x14000d96f  jz      short loc_14000D98F
0x14000d971  cmp     byte ptr [rcx+29h], 4
0x14000d975  jb      short loc_14000D98F
0x14000d977  mov     rcx, [rcx+18h]
0x14000d97b  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14000d982  mov     edx, 76h ; 'v'
0x14000d987  mov     r9, rbx
0x14000d98a  call    WPP_SF_q
0x14000d98f  mov     rbx, [rsp+68h+arg_0]
0x14000d994  mov     rdi, [rsp+68h+arg_8]
0x14000d999  add     rsp, 60h
0x14000d99d  pop     r14
0x14000d99f  retn
```
