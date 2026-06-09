# SrvNotifyGroveler

- ea: `0x140048020`
- end: `0x1400484af`
- name: `SrvNotifyGroveler`
- size: `1167`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x14001ba3c`
- `0x14002a3e0`
- `0x14002a840`
- `0x140047ae4`
- `0x140047e98`
- `0x140048020`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048151`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048209`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048151`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140048209`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004817d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004822f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004817d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004822f`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004813c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400481f4`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14004813c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400481f4`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400483ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400483f2`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400483ad`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400483f2`
- `ntoskrnl!KeInitializeEvent` at `0x1400480a2`
- `ntoskrnl!KeInitializeEvent` at `0x1400480a2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048171`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048223`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048171`
- `ntoskrnl!ExReleaseResourceLite` at `0x140048223`
- `msrpc!RpcAsyncCancelCall` at `0x1400483ca`
- `msrpc!RpcAsyncCancelCall` at `0x1400483ca`
- `msrpc!RpcAsyncCompleteCall` at `0x14004843e`
- `msrpc!RpcAsyncCompleteCall` at `0x14004843e`
- `msrpc!I_RpcExceptionFilter` at `0x14005753e`
- `msrpc!I_RpcExceptionFilter` at `0x14005753e`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400480b8`
- `msrpc!RpcAsyncInitializeHandle` at `0x1400480b8`

## pseudocode

```c
RPC_STATUS __fastcall SrvNotifyGroveler(__int64 a1, int a2, int a3, __int64 a4, int a5, int a6)
{
  int v8; // r13d
  RPC_STATUS result; // eax
  unsigned int v10; // ebx
  PDEVICE_OBJECT v11; // rcx
  __int64 v12; // rdx
  __int64 v13; // r9
  unsigned int v14; // r14d
  int v15; // edx
  unsigned int v16; // ebx
  _DWORD Reply[4]; // [rsp+48h] [rbp-E0h] BYREF
  __int64 v19; // [rsp+58h] [rbp-D0h]
  union _LARGE_INTEGER Timeout; // [rsp+60h] [rbp-C8h] BYREF
  struct _KEVENT Event; // [rsp+68h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-A8h] BYREF

  v8 = a1;
  v19 = a1;
  Reply[2] = a2;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  Reply[0] = 0;
  Timeout.QuadPart = -10000000;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  result = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v10 = result;
  if ( result )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      v12 = 15;
      v13 = (unsigned int)result;
      return WPP_SF_d(v11->AttachedDevice, v12, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v13);
    }
    return result;
  }
  v14 = 0;
  pAsync.NotificationType = RpcNotificationTypeEvent;
  pAsync.u.Event = &Event;
  while ( 1 )
  {
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&SrvGrovelerResource, 1u);
    if ( SrvGrovelerStatus == 2 )
      goto LABEL_19;
    ExReleaseResourceLite(&SrvGrovelerResource);
    KeLeaveCriticalRegion();
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids);
    }
    result = SrvGrovelerConnect();
    v10 = result;
    if ( result < 0 )
      break;
    KeEnterCriticalRegion();
    ExAcquireResourceSharedLite(&SrvGrovelerResource, 1u);
LABEL_19:
    _InterlockedIncrement(&SrvGrovelerConnectCount);
    ExReleaseResourceLite(&SrvGrovelerResource);
    KeLeaveCriticalRegion();
    result = NotifyGroveler((unsigned int)&pAsync, v15, v8, a2, a3, a4, a5, a6);
    if ( !v10 )
    {
      if ( KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout) )
      {
        v16 = RpcAsyncCancelCall(&pAsync, 1);
        if ( !v16 )
          KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
        {
          WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v16);
        }
      }
      result = RpcAsyncCompleteCall(&pAsync, Reply);
      _InterlockedDecrement(&SrvGrovelerConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        return WPP_SF_Dd(
                 WPP_GLOBAL_Control->AttachedDevice,
                 22,
                 WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids,
                 (unsigned int)result,
                 Reply[0]);
      }
      return result;
    }
    _InterlockedDecrement(&SrvGrovelerConnectCount);
    if ( v14 >= 3 || v10 != -1073610724 && v10 != -1073610729 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
      {
        result = HIDWORD(WPP_GLOBAL_Control->Timer);
        if ( (result & 0x10) != 0 )
        {
          if ( BYTE1(WPP_GLOBAL_Control->Timer) )
            return WPP_SF_Dd(
                     WPP_GLOBAL_Control->AttachedDevice,
                     20,
                     WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids,
                     v10,
                     v14);
        }
      }
      return result;
    }
    SrvGrovelerDisconnect();
    ++v14;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v10, v14);
    }
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control )
  {
    result = HIDWORD(WPP_GLOBAL_Control->Timer);
    if ( (result & 0x10) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        v12 = 17;
        v13 = v10;
        return WPP_SF_d(v11->AttachedDevice, v12, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids, v13);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x140048020  mov     [rsp+arg_18], r9
0x140048025  mov     [rsp+arg_10], r8d
0x14004802a  push    rbx
0x14004802b  push    rdi
0x14004802c  push    r12
0x14004802e  push    r13
0x140048030  push    r14
0x140048032  push    r15
0x140048034  sub     rsp, 0F8h
0x14004803b  mov     rax, cs:__security_cookie
0x140048042  xor     rax, rsp
0x140048045  mov     [rsp+128h+var_48], rax
0x14004804d  mov     r15, r9
0x140048050  mov     r12d, r8d
0x140048053  mov     [rsp+128h+var_E8], edx
0x140048057  mov     r13, rcx
0x14004805a  mov     [rsp+128h+var_D0], rcx
0x14004805f  mov     [rsp+128h+var_D8], edx
0x140048063  xorps   xmm0, xmm0
0x140048066  xor     eax, eax
0x140048068  movups  xmmword ptr [rsp+128h+Event.Header], xmm0
0x14004806d  mov     [rsp+128h+Event.Header.WaitListHead.Blink], rax
0x140048072  lea     ebx, [rax+58h]
0x140048075  mov     r8d, ebx; Size
0x140048078  xor     edx, edx; Val
0x14004807a  lea     rcx, [rsp+128h+pAsync]; void *
0x140048082  call    memset
0x140048087  mov     [rsp+128h+Reply], 0
0x14004808f  mov     qword ptr [rsp+128h+var_C8], 0FFFFFFFFFF676980h
0x140048098  xor     r8d, r8d; State
0x14004809b  xor     edx, edx; Type
0x14004809d  lea     rcx, [rsp+128h+Event]; Event
0x1400480a2  call    cs:__imp_KeInitializeEvent
0x1400480a9  nop     dword ptr [rax+rax+00h]
0x1400480ae  mov     edx, ebx; Size
0x1400480b0  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1400480b8  call    cs:__imp_RpcAsyncInitializeHandle
0x1400480bf  nop     dword ptr [rax+rax+00h]
0x1400480c4  mov     ebx, eax
0x1400480c6  test    eax, eax
0x1400480c8  jz      short loc_140048115
0x1400480ca  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400480d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1400480d8  cmp     rcx, rdi
0x1400480db  jz      loc_14004848C
0x1400480e1  test    dword ptr [rcx+2Ch], 8000h
0x1400480e8  jz      loc_14004848C
0x1400480ee  cmp     byte ptr [rcx+29h], 1
0x1400480f2  jb      loc_14004848C
0x1400480f8  mov     edx, 0Fh
0x1400480fd  mov     r9d, eax
0x140048100  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140048107  mov     rcx, [rcx+18h]
0x14004810b  call    WPP_SF_d
0x140048110  jmp     loc_14004848C
0x140048115  xor     r14d, r14d
0x140048118  mov     [rsp+128h+var_E4], r14d
0x14004811d  mov     [rsp+128h+pAsync.NotificationType], 1
0x140048128  lea     rax, [rsp+128h+Event]
0x14004812d  mov     qword ptr [rsp+128h+pAsync.u], rax
0x140048135  lea     rdi, WPP_GLOBAL_Control
0x14004813c  call    cs:__imp_KeEnterCriticalRegion
0x140048143  nop     dword ptr [rax+rax+00h]
0x140048148  mov     dl, 1; Wait
0x14004814a  lea     rcx, SrvGrovelerResource; Resource
0x140048151  call    cs:__imp_ExAcquireResourceSharedLite
0x140048158  nop     dword ptr [rax+rax+00h]
0x14004815d  cmp     cs:SrvGrovelerStatus, 2
0x140048164  jz      loc_140048215
0x14004816a  lea     rcx, SrvGrovelerResource; Resource
0x140048171  call    cs:__imp_ExReleaseResourceLite
0x140048178  nop     dword ptr [rax+rax+00h]
0x14004817d  call    cs:__imp_KeLeaveCriticalRegion
0x140048184  nop     dword ptr [rax+rax+00h]
0x140048189  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048190  cmp     rcx, rdi
0x140048193  jz      short loc_1400481B7
0x140048195  mov     eax, [rcx+2Ch]
0x140048198  test    al, 10h
0x14004819a  jz      short loc_1400481B7
0x14004819c  cmp     byte ptr [rcx+29h], 2
0x1400481a0  jb      short loc_1400481B7
0x1400481a2  mov     edx, 10h
0x1400481a7  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x1400481ae  mov     rcx, [rcx+18h]
0x1400481b2  call    WPP_SF_
0x1400481b7  call    SrvGrovelerConnect
0x1400481bc  mov     ebx, eax
0x1400481be  test    eax, eax
0x1400481c0  jns     short loc_1400481F4
0x1400481c2  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400481c9  cmp     rcx, rdi
0x1400481cc  jz      loc_14004848C
0x1400481d2  mov     eax, [rcx+2Ch]
0x1400481d5  test    al, 10h
0x1400481d7  jz      loc_14004848C
0x1400481dd  cmp     byte ptr [rcx+29h], 1
0x1400481e1  jb      loc_14004848C
0x1400481e7  mov     edx, 11h
0x1400481ec  mov     r9d, ebx
0x1400481ef  jmp     loc_140048100
0x1400481f4  call    cs:__imp_KeEnterCriticalRegion
0x1400481fb  nop     dword ptr [rax+rax+00h]
0x140048200  mov     dl, 1; Wait
0x140048202  lea     rcx, SrvGrovelerResource; Resource
0x140048209  call    cs:__imp_ExAcquireResourceSharedLite
0x140048210  nop     dword ptr [rax+rax+00h]
0x140048215  lock inc cs:SrvGrovelerConnectCount
0x14004821c  lea     rcx, SrvGrovelerResource; Resource
0x140048223  call    cs:__imp_ExReleaseResourceLite
0x14004822a  nop     dword ptr [rax+rax+00h]
0x14004822f  call    cs:__imp_KeLeaveCriticalRegion
0x140048236  nop     dword ptr [rax+rax+00h]
0x14004823b  nop
0x14004823c  mov     eax, [rsp+128h+arg_28]
0x140048243  mov     [rsp+128h+var_F0], eax
0x140048247  mov     eax, [rsp+128h+arg_20]
0x14004824e  mov     [rsp+128h+var_F8], eax
0x140048252  mov     [rsp+128h+var_100], r15
0x140048257  mov     dword ptr [rsp+128h+Timeout], r12d
0x14004825c  mov     r9d, [rsp+128h+var_E8]
0x140048261  mov     r8, r13
0x140048264  lea     rcx, [rsp+128h+pAsync]
0x14004826c  call    NotifyGroveler
0x140048271  jmp     short loc_1400482D6
0x140048273  mov     ebx, eax
0x140048275  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x14004827c  mov     rcx, cs:WPP_GLOBAL_Control
0x140048283  cmp     rcx, rax
0x140048286  jz      short loc_1400482AD
0x140048288  mov     eax, [rcx+2Ch]
0x14004828b  test    al, 10h
0x14004828d  jz      short loc_1400482AD
0x14004828f  cmp     byte ptr [rcx+29h], 1
0x140048293  jb      short loc_1400482AD
0x140048295  mov     edx, 12h
0x14004829a  mov     r9d, ebx
0x14004829d  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x1400482a4  mov     rcx, [rcx+18h]
0x1400482a8  call    WPP_SF_d
0x1400482ad  lea     rdi, WPP_GLOBAL_Control
0x1400482b4  mov     r15, [rsp+128h+arg_18]
0x1400482bc  mov     r12d, [rsp+128h+arg_10]
0x1400482c4  mov     r14d, [rsp+128h+var_E4]
0x1400482c9  mov     r13, [rsp+128h+var_D0]
0x1400482ce  mov     eax, [rsp+128h+var_D8]
0x1400482d2  mov     [rsp+128h+var_E8], eax
0x1400482d6  test    ebx, ebx
0x1400482d8  jz      loc_140048396
0x1400482de  lock dec cs:SrvGrovelerConnectCount
0x1400482e5  cmp     r14d, 3
0x1400482e9  jnb     short loc_14004834F
0x1400482eb  cmp     ebx, 0C002001Ch
0x1400482f1  jz      short loc_1400482FB
0x1400482f3  cmp     ebx, 0C0020017h
0x1400482f9  jnz     short loc_14004834F
0x1400482fb  call    SrvGrovelerDisconnect
0x140048300  inc     r14d
0x140048303  mov     [rsp+128h+var_E4], r14d
0x140048308  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004830f  cmp     rcx, rdi
0x140048312  jz      loc_14004813C
0x140048318  mov     eax, [rcx+2Ch]
0x14004831b  test    al, 10h
0x14004831d  jz      loc_14004813C
0x140048323  cmp     byte ptr [rcx+29h], 2
0x140048327  jb      loc_14004813C
0x14004832d  mov     edx, 13h
0x140048332  mov     dword ptr [rsp+128h+Timeout], r14d
0x140048337  mov     r9d, ebx
0x14004833a  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140048341  mov     rcx, [rcx+18h]
0x140048345  call    WPP_SF_Dd
0x14004834a  jmp     loc_14004813C
0x14004834f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048356  cmp     rcx, rdi
0x140048359  jz      loc_14004848C
0x14004835f  mov     eax, [rcx+2Ch]
0x140048362  test    al, 10h
0x140048364  jz      loc_14004848C
0x14004836a  cmp     byte ptr [rcx+29h], 1
0x14004836e  jb      loc_14004848C
0x140048374  mov     edx, 14h
0x140048379  mov     dword ptr [rsp+128h+Timeout], r14d
0x14004837e  mov     r9d, ebx
0x140048381  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140048388  mov     rcx, [rcx+18h]
0x14004838c  call    WPP_SF_Dd
0x140048391  jmp     loc_14004848C
0x140048396  lea     rax, [rsp+128h+var_C8]
0x14004839b  mov     [rsp+128h+Timeout], rax; Timeout
0x1400483a0  xor     r9d, r9d; Alertable
0x1400483a3  xor     r8d, r8d; WaitMode
0x1400483a6  xor     edx, edx; WaitReason
0x1400483a8  lea     rcx, [rsp+128h+Event]; Object
0x1400483ad  call    cs:__imp_KeWaitForSingleObject
0x1400483b4  nop     dword ptr [rax+rax+00h]
0x1400483b9  test    eax, eax
0x1400483bb  jz      short loc_140048431
0x1400483bd  mov     edx, 1; fAbort
0x1400483c2  lea     rcx, [rsp+128h+pAsync]; pAsync
0x1400483ca  call    cs:__imp_RpcAsyncCancelCall
0x1400483d1  nop     dword ptr [rax+rax+00h]
0x1400483d6  mov     ebx, eax
0x1400483d8  test    eax, eax
0x1400483da  jnz     short loc_1400483FE
0x1400483dc  mov     [rsp+128h+Timeout], 0; Timeout
0x1400483e5  xor     r9d, r9d; Alertable
0x1400483e8  xor     r8d, r8d; WaitMode
0x1400483eb  xor     edx, edx; WaitReason
0x1400483ed  lea     rcx, [rsp+128h+Event]; Object
0x1400483f2  call    cs:__imp_KeWaitForSingleObject
0x1400483f9  nop     dword ptr [rax+rax+00h]
0x1400483fe  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140048405  cmp     rcx, rdi
0x140048408  jz      short loc_140048431
0x14004840a  test    dword ptr [rcx+2Ch], 8000h
0x140048411  jz      short loc_140048431
0x140048413  cmp     byte ptr [rcx+29h], 2
0x140048417  jb      short loc_140048431
0x140048419  mov     edx, 15h
0x14004841e  mov     r9d, ebx
0x140048421  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140048428  mov     rcx, [rcx+18h]
0x14004842c  call    WPP_SF_d
0x140048431  lea     rdx, [rsp+128h+Reply]; Reply
0x140048436  lea     rcx, [rsp+128h+pAsync]; pAsync
0x14004843e  call    cs:__imp_RpcAsyncCompleteCall
0x140048445  nop     dword ptr [rax+rax+00h]
0x14004844a  mov     r9d, eax
0x14004844d  lock dec cs:SrvGrovelerConnectCount
0x140048454  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004845b  cmp     rcx, rdi
0x14004845e  jz      short loc_14004848C
0x140048460  test    dword ptr [rcx+2Ch], 8000h
0x140048467  jz      short loc_14004848C
0x140048469  cmp     byte ptr [rcx+29h], 2
0x14004846d  jb      short loc_14004848C
0x14004846f  mov     edx, 16h
0x140048474  mov     eax, [rsp+128h+Reply]
0x140048478  mov     dword ptr [rsp+128h+Timeout], eax
0x14004847c  lea     r8, WPP_59b675c1b97c3d49ebd45fd26b3e0b21_Traceguids
0x140048483  mov     rcx, [rcx+18h]
0x140048487  call    WPP_SF_Dd
0x14004848c  mov     rcx, [rsp+128h+var_48]
0x140048494  xor     rcx, rsp; StackCookie
0x140048497  call    __security_check_cookie
0x14004849c  add     rsp, 0F8h
0x1400484a3  pop     r15
0x1400484a5  pop     r14
0x1400484a7  pop     r13
0x1400484a9  pop     r12
0x1400484ab  pop     rdi
0x1400484ac  pop     rbx
0x1400484ad  retn
0x140057530  push    rbp
0x140057532  sub     rsp, 40h
0x140057536  mov     rbp, rdx
0x140057539  mov     rcx, [rcx]
0x14005753c  mov     ecx, [rcx]; ExceptionCode
0x14005753e  call    cs:__imp_I_RpcExceptionFilter
0x140057545  nop     dword ptr [rax+rax+00h]
0x14005754a  nop
0x14005754b  add     rsp, 40h
0x14005754f  pop     rbp
0x140057550  retn
```
