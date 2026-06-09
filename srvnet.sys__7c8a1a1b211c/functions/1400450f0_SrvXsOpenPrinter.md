# SrvXsOpenPrinter

- ea: `0x1400450f0`
- end: `0x1400453da`
- name: `SrvXsOpenPrinter`
- size: `746`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x1400163d8`
- `0x140018838`
- `0x14002a3e0`
- `0x14002a840`
- `0x1400450f0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004521d`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x14004521d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045275`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400452c1`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045275`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400452c1`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140045208`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140045208`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004535a`
- `ntoskrnl!KeWaitForSingleObject` at `0x14004535a`
- `ntoskrnl!KeInitializeEvent` at `0x140045191`
- `ntoskrnl!KeInitializeEvent` at `0x140045191`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045269`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400452b5`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045269`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400452b5`
- `msrpc!RpcAsyncCompleteCall` at `0x14004536d`
- `msrpc!RpcAsyncCompleteCall` at `0x14004536d`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400451a4`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400451a4`

## pseudocode

```c
__int64 __fastcall SrvXsOpenPrinter(__int64 a1, _QWORD *a2, _DWORD *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // ebx
  int v9; // edx
  unsigned int v10; // ebx
  _QWORD v11[3]; // [rsp+30h] [rbp-C8h] BYREF
  struct _KEVENT Event; // [rsp+48h] [rbp-B0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-98h] BYREF

  v11[1] = a2;
  v11[2] = a3;
  v11[0] = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_Z(WPP_GLOBAL_Control->AttachedDevice, 10, WPP_449961259f2532308161ede427ce4710_Traceguids, a1);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v6 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v7 = v6;
  if ( !v6 )
  {
    pAsync.NotificationType = RpcNotificationTypeEvent;
    pAsync.u.Event = &Event;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&SrvXsResource, 1u);
    if ( SrvXsStatus == 2 )
    {
      _InterlockedIncrement(&SrvXsConnectCount);
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
      XsOpenPrinter((unsigned int)&pAsync, v9, a1, (unsigned int)v11, (__int64)a3);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v10 = RpcAsyncCompleteCall(&pAsync, 0);
      _InterlockedDecrement(&SrvXsConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 14, WPP_449961259f2532308161ede427ce4710_Traceguids, v10, *a3);
      }
      if ( !v10 && !*a3 )
      {
        *a2 = v11[0];
        return 0;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 12, WPP_449961259f2532308161ede427ce4710_Traceguids);
      }
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
    }
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 11, WPP_449961259f2532308161ede427ce4710_Traceguids, v6);
  }
  return v7;
}

```

## disassembly

```asm
0x1400450f0  push    rbx
0x1400450f2  push    rsi
0x1400450f3  push    r12
0x1400450f5  push    r14
0x1400450f7  push    r15
0x1400450f9  sub     rsp, 0D0h
0x140045100  mov     rax, cs:__security_cookie
0x140045107  xor     rax, rsp
0x14004510a  mov     [rsp+0F8h+var_38], rax
0x140045112  mov     rsi, r8
0x140045115  mov     r15, rdx
0x140045118  mov     r12, rcx
0x14004511b  mov     [rsp+0F8h+var_C0], rdx
0x140045120  mov     [rsp+0F8h+var_B8], r8
0x140045125  mov     [rsp+0F8h+var_C8], 0
0x14004512e  xorps   xmm0, xmm0
0x140045131  xor     eax, eax
0x140045133  movups  xmmword ptr [rsp+0F8h+Event.Header], xmm0
0x140045138  mov     [rsp+0F8h+Event.Header.WaitListHead.Blink], rax
0x14004513d  lea     ebx, [rax+58h]
0x140045140  mov     r8d, ebx; Size
0x140045143  xor     edx, edx; Val
0x140045145  lea     rcx, [rsp+0F8h+pAsync]; void *
0x14004514a  call    memset
0x14004514f  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x140045156  mov     rcx, cs:WPP_GLOBAL_Control
0x14004515d  cmp     rcx, r14
0x140045160  jz      short loc_140045187
0x140045162  test    dword ptr [rcx+2Ch], 8000h
0x140045169  jz      short loc_140045187
0x14004516b  cmp     byte ptr [rcx+29h], 2
0x14004516f  jb      short loc_140045187
0x140045171  lea     edx, [rbx-4Eh]
0x140045174  mov     r9, r12
0x140045177  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x14004517e  mov     rcx, [rcx+18h]
0x140045182  call    WPP_SF_Z
0x140045187  xor     r8d, r8d; State
0x14004518a  xor     edx, edx; Type
0x14004518c  lea     rcx, [rsp+0F8h+Event]; Event
0x140045191  call    cs:__imp_KeInitializeEvent
0x140045198  nop     dword ptr [rax+rax+00h]
0x14004519d  mov     edx, ebx; Size
0x14004519f  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x1400451a4  call    cs:__imp_RpcAsyncInitializeHandle
0x1400451ab  nop     dword ptr [rax+rax+00h]
0x1400451b0  mov     ebx, eax
0x1400451b2  test    eax, eax
0x1400451b4  jz      short loc_1400451F0
0x1400451b6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400451bd  cmp     rcx, r14
0x1400451c0  jz      short loc_1400451E9
0x1400451c2  test    dword ptr [rcx+2Ch], 8000h
0x1400451c9  jz      short loc_1400451E9
0x1400451cb  cmp     byte ptr [rcx+29h], 1
0x1400451cf  jb      short loc_1400451E9
0x1400451d1  mov     edx, 0Bh
0x1400451d6  mov     r9d, eax
0x1400451d9  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x1400451e0  mov     rcx, [rcx+18h]
0x1400451e4  call    WPP_SF_d
0x1400451e9  mov     eax, ebx
0x1400451eb  jmp     loc_140045286
0x1400451f0  mov     [rsp+0F8h+pAsync.NotificationType], 1
0x1400451fb  lea     rax, [rsp+0F8h+Event]
0x140045200  mov     qword ptr [rsp+0F8h+pAsync.u], rax
0x140045208  call    cs:__imp_KeEnterCriticalRegion
0x14004520f  nop     dword ptr [rax+rax+00h]
0x140045214  mov     dl, 1; Wait
0x140045216  lea     rcx, SrvXsResource; Resource
0x14004521d  call    cs:__imp_ExAcquireResourceSharedLite
0x140045224  nop     dword ptr [rax+rax+00h]
0x140045229  cmp     cs:SrvXsStatus, 2
0x140045230  jz      short loc_1400452A7
0x140045232  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045239  cmp     rcx, r14
0x14004523c  jz      short loc_140045262
0x14004523e  test    dword ptr [rcx+2Ch], 8000h
0x140045245  jz      short loc_140045262
0x140045247  cmp     byte ptr [rcx+29h], 1
0x14004524b  jb      short loc_140045262
0x14004524d  mov     edx, 0Ch
0x140045252  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140045259  mov     rcx, [rcx+18h]
0x14004525d  call    WPP_SF_
0x140045262  lea     rcx, SrvXsResource; Resource
0x140045269  call    cs:__imp_ExReleaseResourceLite
0x140045270  nop     dword ptr [rax+rax+00h]
0x140045275  call    cs:__imp_KeLeaveCriticalRegion
0x14004527c  nop     dword ptr [rax+rax+00h]
0x140045281  mov     eax, 0C0000022h
0x140045286  mov     rcx, [rsp+0F8h+var_38]
0x14004528e  xor     rcx, rsp; StackCookie
0x140045291  call    __security_check_cookie
0x140045296  add     rsp, 0D0h
0x14004529d  pop     r15
0x14004529f  pop     r14
0x1400452a1  pop     r12
0x1400452a3  pop     rsi
0x1400452a4  pop     rbx
0x1400452a5  retn
0x1400452a7  lock inc cs:SrvXsConnectCount
0x1400452ae  lea     rcx, SrvXsResource; Resource
0x1400452b5  call    cs:__imp_ExReleaseResourceLite
0x1400452bc  nop     dword ptr [rax+rax+00h]
0x1400452c1  call    cs:__imp_KeLeaveCriticalRegion
0x1400452c8  nop     dword ptr [rax+rax+00h]
0x1400452cd  nop
0x1400452ce  mov     [rsp+0F8h+Timeout], rsi
0x1400452d3  lea     r9, [rsp+0F8h+var_C8]
0x1400452d8  mov     r8, r12
0x1400452db  lea     rcx, [rsp+0F8h+pAsync]
0x1400452e0  call    XsOpenPrinter
0x1400452e5  jmp     short loc_140045334
0x1400452e7  mov     ebx, eax
0x1400452e9  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400452f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400452f7  cmp     rcx, rax
0x1400452fa  jz      short loc_140045323
0x1400452fc  test    dword ptr [rcx+2Ch], 8000h
0x140045303  jz      short loc_140045323
0x140045305  cmp     byte ptr [rcx+29h], 2
0x140045309  jb      short loc_140045323
0x14004530b  mov     edx, 0Dh
0x140045310  mov     r9d, ebx
0x140045313  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x14004531a  mov     rcx, [rcx+18h]
0x14004531e  call    WPP_SF_d
0x140045323  lea     r14, WPP_GLOBAL_Control
0x14004532a  mov     r15, [rsp+0F8h+var_C0]
0x14004532f  mov     rsi, [rsp+0F8h+var_B8]
0x140045334  test    ebx, ebx
0x140045336  jz      short loc_140045344
0x140045338  lock dec cs:SrvXsConnectCount
0x14004533f  jmp     loc_1400451E9
0x140045344  mov     [rsp+0F8h+Timeout], 0; Timeout
0x14004534d  xor     r9d, r9d; Alertable
0x140045350  xor     r8d, r8d; WaitMode
0x140045353  xor     edx, edx; WaitReason
0x140045355  lea     rcx, [rsp+0F8h+Event]; Object
0x14004535a  call    cs:__imp_KeWaitForSingleObject
0x140045361  nop     dword ptr [rax+rax+00h]
0x140045366  xor     edx, edx; Reply
0x140045368  lea     rcx, [rsp+0F8h+pAsync]; pAsync
0x14004536d  call    cs:__imp_RpcAsyncCompleteCall
0x140045374  nop     dword ptr [rax+rax+00h]
0x140045379  mov     ebx, eax
0x14004537b  lock dec cs:SrvXsConnectCount
0x140045382  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045389  cmp     rcx, r14
0x14004538c  jz      short loc_1400453BB
0x14004538e  test    dword ptr [rcx+2Ch], 8000h
0x140045395  jz      short loc_1400453BB
0x140045397  cmp     byte ptr [rcx+29h], 2
0x14004539b  jb      short loc_1400453BB
0x14004539d  mov     edx, 0Eh
0x1400453a2  mov     eax, [rsi]
0x1400453a4  mov     dword ptr [rsp+0F8h+Timeout], eax
0x1400453a8  mov     r9d, ebx
0x1400453ab  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x1400453b2  mov     rcx, [rcx+18h]
0x1400453b6  call    WPP_SF_Dd
0x1400453bb  test    ebx, ebx
0x1400453bd  jnz     loc_140045281
0x1400453c3  cmp     [rsi], ebx
0x1400453c5  jnz     loc_140045281
0x1400453cb  mov     rax, [rsp+0F8h+var_C8]
0x1400453d0  mov     [r15], rax
0x1400453d3  xor     eax, eax
0x1400453d5  jmp     loc_140045286
0x140057508  push    rbp
0x14005750a  sub     rsp, 30h
0x14005750e  mov     rbp, rdx
0x140057511  mov     rcx, [rcx]
0x140057514  mov     ecx, [rcx]; ExceptionCode
0x140057516  call    cs:__imp_I_RpcExceptionFilter
0x14005751d  nop     dword ptr [rax+rax+00h]
0x140057522  nop
0x140057523  add     rsp, 30h
0x140057527  pop     rbp
0x140057528  retn
```
