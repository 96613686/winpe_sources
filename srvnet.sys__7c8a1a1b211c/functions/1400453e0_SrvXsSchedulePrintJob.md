# SrvXsSchedulePrintJob

- ea: `0x1400453e0`
- end: `0x1400456b2`
- name: `SrvXsSchedulePrintJob`
- size: `722`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x1400188c8`
- `0x14002a3e0`
- `0x14002a840`
- `0x1400453e0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400454fa`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400454fa`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045552`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400455a3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140045552`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400455a3`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400454e5`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400454e5`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045635`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045635`
- `ntoskrnl!KeInitializeEvent` at `0x140045471`
- `ntoskrnl!KeInitializeEvent` at `0x140045471`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045546`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045597`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045546`
- `ntoskrnl!ExReleaseResourceLite` at `0x140045597`
- `msrpc!RpcAsyncCompleteCall` at `0x140045648`
- `msrpc!RpcAsyncCompleteCall` at `0x140045648`
- `msrpc!RpcAsyncInitializeHandle` at `0x140045484`
- `msrpc!RpcAsyncInitializeHandle` at `0x140045484`

## pseudocode

```c
__int64 __fastcall SrvXsSchedulePrintJob(int a1, int a2)
{
  unsigned int v4; // eax
  unsigned int v5; // ebx
  int v7; // edx
  unsigned int v8; // ebx
  int v9; // [rsp+30h] [rbp-A8h] BYREF
  struct _KEVENT Event; // [rsp+38h] [rbp-A0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+50h] [rbp-88h] BYREF

  v9 = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_449961259f2532308161ede427ce4710_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v4 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v5 = v4;
  if ( !v4 )
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
      XsScheduleJob((unsigned int)&pAsync, v7, a1, a2, (__int64)&v9);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v8 = RpcAsyncCompleteCall(&pAsync, 0);
      _InterlockedDecrement(&SrvXsConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 24, WPP_449961259f2532308161ede427ce4710_Traceguids, v8, v9);
      }
      if ( !v8 )
        return v9 != 0 ? 0xC0000022 : 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_449961259f2532308161ede427ce4710_Traceguids);
      }
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
    }
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_449961259f2532308161ede427ce4710_Traceguids, v4);
  }
  return v5;
}

```

## disassembly

```asm
0x1400453e0  mov     [rsp+arg_10], rbx
0x1400453e5  push    rsi
0x1400453e6  push    r14
0x1400453e8  push    r15
0x1400453ea  sub     rsp, 0C0h
0x1400453f1  mov     rax, cs:__security_cookie
0x1400453f8  xor     rax, rsp
0x1400453fb  mov     [rsp+0D8h+var_28], rax
0x140045403  mov     r15d, edx
0x140045406  mov     r14, rcx
0x140045409  mov     [rsp+0D8h+var_A8], 0
0x140045411  xorps   xmm0, xmm0
0x140045414  xor     eax, eax
0x140045416  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x14004541b  mov     [rsp+0D8h+Event.Header.WaitListHead.Blink], rax
0x140045420  lea     ebx, [rax+58h]
0x140045423  mov     r8d, ebx; Size
0x140045426  xor     edx, edx; Val
0x140045428  lea     rcx, [rsp+0D8h+pAsync]; void *
0x14004542d  call    memset
0x140045432  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x140045439  mov     rcx, cs:WPP_GLOBAL_Control
0x140045440  cmp     rcx, rsi
0x140045443  jz      short loc_140045467
0x140045445  test    dword ptr [rcx+2Ch], 8000h
0x14004544c  jz      short loc_140045467
0x14004544e  cmp     byte ptr [rcx+29h], 2
0x140045452  jb      short loc_140045467
0x140045454  lea     edx, [rbx-44h]
0x140045457  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x14004545e  mov     rcx, [rcx+18h]
0x140045462  call    WPP_SF_
0x140045467  xor     r8d, r8d; State
0x14004546a  xor     edx, edx; Type
0x14004546c  lea     rcx, [rsp+0D8h+Event]; Event
0x140045471  call    cs:__imp_KeInitializeEvent
0x140045478  nop     dword ptr [rax+rax+00h]
0x14004547d  mov     edx, ebx; Size
0x14004547f  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x140045484  call    cs:__imp_RpcAsyncInitializeHandle
0x14004548b  nop     dword ptr [rax+rax+00h]
0x140045490  mov     ebx, eax
0x140045492  test    eax, eax
0x140045494  jz      short loc_1400454D0
0x140045496  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x14004549d  cmp     rcx, rsi
0x1400454a0  jz      short loc_1400454C9
0x1400454a2  test    dword ptr [rcx+2Ch], 8000h
0x1400454a9  jz      short loc_1400454C9
0x1400454ab  cmp     byte ptr [rcx+29h], 1
0x1400454af  jb      short loc_1400454C9
0x1400454b1  mov     edx, 15h
0x1400454b6  mov     r9d, eax
0x1400454b9  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x1400454c0  mov     rcx, [rcx+18h]
0x1400454c4  call    WPP_SF_d
0x1400454c9  mov     eax, ebx
0x1400454cb  jmp     loc_140045563
0x1400454d0  mov     [rsp+0D8h+pAsync.NotificationType], 1
0x1400454d8  lea     rax, [rsp+0D8h+Event]
0x1400454dd  mov     qword ptr [rsp+0D8h+pAsync.u], rax
0x1400454e5  call    cs:__imp_KeEnterCriticalRegion
0x1400454ec  nop     dword ptr [rax+rax+00h]
0x1400454f1  mov     dl, 1; Wait
0x1400454f3  lea     rcx, SrvXsResource; Resource
0x1400454fa  call    cs:__imp_ExAcquireResourceSharedLite
0x140045501  nop     dword ptr [rax+rax+00h]
0x140045506  cmp     cs:SrvXsStatus, 2
0x14004550d  jz      short loc_140045589
0x14004550f  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045516  cmp     rcx, rsi
0x140045519  jz      short loc_14004553F
0x14004551b  test    dword ptr [rcx+2Ch], 8000h
0x140045522  jz      short loc_14004553F
0x140045524  cmp     byte ptr [rcx+29h], 1
0x140045528  jb      short loc_14004553F
0x14004552a  mov     edx, 16h
0x14004552f  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140045536  mov     rcx, [rcx+18h]
0x14004553a  call    WPP_SF_
0x14004553f  lea     rcx, SrvXsResource; Resource
0x140045546  call    cs:__imp_ExReleaseResourceLite
0x14004554d  nop     dword ptr [rax+rax+00h]
0x140045552  call    cs:__imp_KeLeaveCriticalRegion
0x140045559  nop     dword ptr [rax+rax+00h]
0x14004555e  mov     eax, 0C0000022h
0x140045563  mov     rcx, [rsp+0D8h+var_28]
0x14004556b  xor     rcx, rsp; StackCookie
0x14004556e  call    __security_check_cookie
0x140045573  mov     rbx, [rsp+0D8h+arg_10]
0x14004557b  add     rsp, 0C0h
0x140045582  pop     r15
0x140045584  pop     r14
0x140045586  pop     rsi
0x140045587  retn
0x140045589  lock inc cs:SrvXsConnectCount
0x140045590  lea     rcx, SrvXsResource; Resource
0x140045597  call    cs:__imp_ExReleaseResourceLite
0x14004559e  nop     dword ptr [rax+rax+00h]
0x1400455a3  call    cs:__imp_KeLeaveCriticalRegion
0x1400455aa  nop     dword ptr [rax+rax+00h]
0x1400455af  nop
0x1400455b0  lea     rax, [rsp+0D8h+var_A8]
0x1400455b5  mov     [rsp+0D8h+Timeout], rax
0x1400455ba  mov     r9d, r15d
0x1400455bd  mov     r8, r14
0x1400455c0  lea     rcx, [rsp+0D8h+pAsync]
0x1400455c5  call    XsScheduleJob
0x1400455ca  jmp     short loc_14004560F
0x1400455cc  mov     ebx, eax
0x1400455ce  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400455d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1400455dc  cmp     rcx, rax
0x1400455df  jz      short loc_140045608
0x1400455e1  test    dword ptr [rcx+2Ch], 8000h
0x1400455e8  jz      short loc_140045608
0x1400455ea  cmp     byte ptr [rcx+29h], 2
0x1400455ee  jb      short loc_140045608
0x1400455f0  mov     edx, 17h
0x1400455f5  mov     r9d, ebx
0x1400455f8  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x1400455ff  mov     rcx, [rcx+18h]
0x140045603  call    WPP_SF_d
0x140045608  lea     rsi, WPP_GLOBAL_Control
0x14004560f  test    ebx, ebx
0x140045611  jz      short loc_14004561F
0x140045613  lock dec cs:SrvXsConnectCount
0x14004561a  jmp     loc_1400454C9
0x14004561f  mov     [rsp+0D8h+Timeout], 0; Timeout
0x140045628  xor     r9d, r9d; Alertable
0x14004562b  xor     r8d, r8d; WaitMode
0x14004562e  xor     edx, edx; WaitReason
0x140045630  lea     rcx, [rsp+0D8h+Event]; Object
0x140045635  call    cs:__imp_KeWaitForSingleObject
0x14004563c  nop     dword ptr [rax+rax+00h]
0x140045641  xor     edx, edx; Reply
0x140045643  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x140045648  call    cs:__imp_RpcAsyncCompleteCall
0x14004564f  nop     dword ptr [rax+rax+00h]
0x140045654  mov     ebx, eax
0x140045656  lock dec cs:SrvXsConnectCount
0x14004565d  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045664  cmp     rcx, rsi
0x140045667  jz      short loc_140045698
0x140045669  test    dword ptr [rcx+2Ch], 8000h
0x140045670  jz      short loc_140045698
0x140045672  cmp     byte ptr [rcx+29h], 2
0x140045676  jb      short loc_140045698
0x140045678  mov     edx, 18h
0x14004567d  mov     eax, [rsp+0D8h+var_A8]
0x140045681  mov     dword ptr [rsp+0D8h+Timeout], eax
0x140045685  mov     r9d, ebx
0x140045688  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x14004568f  mov     rcx, [rcx+18h]
0x140045693  call    WPP_SF_Dd
0x140045698  test    ebx, ebx
0x14004569a  jnz     loc_14004555E
0x1400456a0  mov     eax, [rsp+0D8h+var_A8]
0x1400456a4  neg     eax
0x1400456a6  sbb     eax, eax
0x1400456a8  and     eax, 0C0000022h
0x1400456ad  jmp     loc_140045563
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
