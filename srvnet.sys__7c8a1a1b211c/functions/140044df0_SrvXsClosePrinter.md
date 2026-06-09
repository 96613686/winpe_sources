# SrvXsClosePrinter

- ea: `0x140044df0`
- end: `0x1400450de`
- name: `SrvXsClosePrinter`
- size: `750`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x1400187f4`
- `0x14002a3e0`
- `0x14002a840`
- `0x140044df0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140044f11`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140044f11`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044f69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044fbb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044f69`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044fbb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044efc`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044efc`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045061`
- `ntoskrnl!KeWaitForSingleObject` at `0x140045061`
- `ntoskrnl!KeInitializeEvent` at `0x140044e85`
- `ntoskrnl!KeInitializeEvent` at `0x140044e85`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044f5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044faf`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044f5d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044faf`
- `msrpc!RpcSsDestroyClientContext` at `0x140044fee`
- `msrpc!RpcSsDestroyClientContext` at `0x140044fee`
- `msrpc!RpcAsyncCompleteCall` at `0x140045074`
- `msrpc!RpcAsyncCompleteCall` at `0x140045074`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044e98`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044e98`

## pseudocode

```c
__int64 __fastcall SrvXsClosePrinter(void **a1)
{
  unsigned int v2; // eax
  unsigned int v3; // ebx
  __int64 v5; // rdx
  unsigned int v6; // ebx
  int v7; // [rsp+30h] [rbp-A8h] BYREF
  void **ContextHandle; // [rsp+38h] [rbp-A0h]
  struct _KEVENT Event; // [rsp+40h] [rbp-98h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-78h] BYREF

  ContextHandle = a1;
  v7 = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 25, WPP_449961259f2532308161ede427ce4710_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v2 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v3 = v2;
  if ( !v2 )
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
      XsClosePrinter(&pAsync, v5, a1, &v7);
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v6 = RpcAsyncCompleteCall(&pAsync, 0);
      _InterlockedDecrement(&SrvXsConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_449961259f2532308161ede427ce4710_Traceguids, v6, v7);
      }
      if ( !v6 )
        return v7 != 0 ? 0xC0000022 : 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_449961259f2532308161ede427ce4710_Traceguids);
      }
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
    }
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_449961259f2532308161ede427ce4710_Traceguids, v2);
  }
  return v3;
}

```

## disassembly

```asm
0x140044df0  mov     [rsp+arg_8], rbx
0x140044df5  mov     [rsp+arg_10], rsi
0x140044dfa  push    r14
0x140044dfc  sub     rsp, 0D0h
0x140044e03  mov     rax, cs:__security_cookie
0x140044e0a  xor     rax, rsp
0x140044e0d  mov     [rsp+0D8h+var_18], rax
0x140044e15  mov     r14, rcx
0x140044e18  mov     [rsp+0D8h+ContextHandle], rcx
0x140044e1d  mov     [rsp+0D8h+var_A8], 0
0x140044e25  xorps   xmm0, xmm0
0x140044e28  xor     eax, eax
0x140044e2a  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x140044e2f  mov     [rsp+0D8h+Event.Header.WaitListHead.Blink], rax
0x140044e34  lea     ebx, [rax+58h]
0x140044e37  mov     r8d, ebx; Size
0x140044e3a  xor     edx, edx; Val
0x140044e3c  lea     rcx, [rsp+0D8h+pAsync]; void *
0x140044e41  call    memset
0x140044e46  lea     rsi, WPP_GLOBAL_Control; __annotation("TMF:",
0x140044e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x140044e54  cmp     rcx, rsi
0x140044e57  jz      short loc_140044E7B
0x140044e59  test    dword ptr [rcx+2Ch], 8000h
0x140044e60  jz      short loc_140044E7B
0x140044e62  cmp     byte ptr [rcx+29h], 2
0x140044e66  jb      short loc_140044E7B
0x140044e68  lea     edx, [rbx-3Fh]
0x140044e6b  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044e72  mov     rcx, [rcx+18h]
0x140044e76  call    WPP_SF_
0x140044e7b  xor     r8d, r8d; State
0x140044e7e  xor     edx, edx; Type
0x140044e80  lea     rcx, [rsp+0D8h+Event]; Event
0x140044e85  call    cs:__imp_KeInitializeEvent
0x140044e8c  nop     dword ptr [rax+rax+00h]
0x140044e91  mov     edx, ebx; Size
0x140044e93  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x140044e98  call    cs:__imp_RpcAsyncInitializeHandle
0x140044e9f  nop     dword ptr [rax+rax+00h]
0x140044ea4  mov     ebx, eax
0x140044ea6  test    eax, eax
0x140044ea8  jz      short loc_140044EE4
0x140044eaa  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044eb1  cmp     rcx, rsi
0x140044eb4  jz      short loc_140044EDD
0x140044eb6  test    dword ptr [rcx+2Ch], 8000h
0x140044ebd  jz      short loc_140044EDD
0x140044ebf  cmp     byte ptr [rcx+29h], 1
0x140044ec3  jb      short loc_140044EDD
0x140044ec5  mov     edx, 1Ah
0x140044eca  mov     r9d, eax
0x140044ecd  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044ed4  mov     rcx, [rcx+18h]
0x140044ed8  call    WPP_SF_d
0x140044edd  mov     eax, ebx
0x140044edf  jmp     loc_140044F7A
0x140044ee4  mov     [rsp+0D8h+pAsync.NotificationType], 1
0x140044eef  lea     rax, [rsp+0D8h+Event]
0x140044ef4  mov     qword ptr [rsp+0D8h+pAsync.u], rax
0x140044efc  call    cs:__imp_KeEnterCriticalRegion
0x140044f03  nop     dword ptr [rax+rax+00h]
0x140044f08  mov     dl, 1; Wait
0x140044f0a  lea     rcx, SrvXsResource; Resource
0x140044f11  call    cs:__imp_ExAcquireResourceSharedLite
0x140044f18  nop     dword ptr [rax+rax+00h]
0x140044f1d  cmp     cs:SrvXsStatus, 2
0x140044f24  jz      short loc_140044FA1
0x140044f26  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044f2d  cmp     rcx, rsi
0x140044f30  jz      short loc_140044F56
0x140044f32  test    dword ptr [rcx+2Ch], 8000h
0x140044f39  jz      short loc_140044F56
0x140044f3b  cmp     byte ptr [rcx+29h], 1
0x140044f3f  jb      short loc_140044F56
0x140044f41  mov     edx, 1Bh
0x140044f46  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044f4d  mov     rcx, [rcx+18h]
0x140044f51  call    WPP_SF_
0x140044f56  lea     rcx, SrvXsResource; Resource
0x140044f5d  call    cs:__imp_ExReleaseResourceLite
0x140044f64  nop     dword ptr [rax+rax+00h]
0x140044f69  call    cs:__imp_KeLeaveCriticalRegion
0x140044f70  nop     dword ptr [rax+rax+00h]
0x140044f75  mov     eax, 0C0000022h
0x140044f7a  mov     rcx, [rsp+0D8h+var_18]
0x140044f82  xor     rcx, rsp; StackCookie
0x140044f85  call    __security_check_cookie
0x140044f8a  lea     r11, [rsp+0D8h+var_8]
0x140044f92  mov     rbx, [r11+18h]
0x140044f96  mov     rsi, [r11+20h]
0x140044f9a  mov     rsp, r11
0x140044f9d  pop     r14
0x140044f9f  retn
0x140044fa1  lock inc cs:SrvXsConnectCount
0x140044fa8  lea     rcx, SrvXsResource; Resource
0x140044faf  call    cs:__imp_ExReleaseResourceLite
0x140044fb6  nop     dword ptr [rax+rax+00h]
0x140044fbb  call    cs:__imp_KeLeaveCriticalRegion
0x140044fc2  nop     dword ptr [rax+rax+00h]
0x140044fc7  nop
0x140044fc8  lea     r9, [rsp+0D8h+var_A8]
0x140044fcd  mov     r8, r14
0x140044fd0  lea     rcx, [rsp+0D8h+pAsync]
0x140044fd5  call    XsClosePrinter
0x140044fda  jmp     short loc_14004503B
0x140044fdc  mov     ebx, eax
0x140044fde  mov     rcx, [rsp+0D8h+ContextHandle]; ContextHandle
0x140044fe3  test    rcx, rcx
0x140044fe6  jz      short loc_140044FFA
0x140044fe8  cmp     qword ptr [rcx], 0
0x140044fec  jz      short loc_140044FFA
0x140044fee  call    cs:__imp_RpcSsDestroyClientContext
0x140044ff5  nop     dword ptr [rax+rax+00h]
0x140044ffa  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140045001  mov     rcx, cs:WPP_GLOBAL_Control
0x140045008  cmp     rcx, rax
0x14004500b  jz      short loc_140045034
0x14004500d  test    dword ptr [rcx+2Ch], 8000h
0x140045014  jz      short loc_140045034
0x140045016  cmp     byte ptr [rcx+29h], 2
0x14004501a  jb      short loc_140045034
0x14004501c  mov     edx, 1Ch
0x140045021  mov     r9d, ebx
0x140045024  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x14004502b  mov     rcx, [rcx+18h]
0x14004502f  call    WPP_SF_d
0x140045034  lea     rsi, WPP_GLOBAL_Control
0x14004503b  test    ebx, ebx
0x14004503d  jz      short loc_14004504B
0x14004503f  lock dec cs:SrvXsConnectCount
0x140045046  jmp     loc_140044EDD
0x14004504b  mov     [rsp+0D8h+Timeout], 0; Timeout
0x140045054  xor     r9d, r9d; Alertable
0x140045057  xor     r8d, r8d; WaitMode
0x14004505a  xor     edx, edx; WaitReason
0x14004505c  lea     rcx, [rsp+0D8h+Event]; Object
0x140045061  call    cs:__imp_KeWaitForSingleObject
0x140045068  nop     dword ptr [rax+rax+00h]
0x14004506d  xor     edx, edx; Reply
0x14004506f  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x140045074  call    cs:__imp_RpcAsyncCompleteCall
0x14004507b  nop     dword ptr [rax+rax+00h]
0x140045080  mov     ebx, eax
0x140045082  lock dec cs:SrvXsConnectCount
0x140045089  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140045090  cmp     rcx, rsi
0x140045093  jz      short loc_1400450C4
0x140045095  test    dword ptr [rcx+2Ch], 8000h
0x14004509c  jz      short loc_1400450C4
0x14004509e  cmp     byte ptr [rcx+29h], 2
0x1400450a2  jb      short loc_1400450C4
0x1400450a4  mov     edx, 1Dh
0x1400450a9  mov     eax, [rsp+0D8h+var_A8]
0x1400450ad  mov     dword ptr [rsp+0D8h+Timeout], eax
0x1400450b1  mov     r9d, ebx
0x1400450b4  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x1400450bb  mov     rcx, [rcx+18h]
0x1400450bf  call    WPP_SF_Dd
0x1400450c4  test    ebx, ebx
0x1400450c6  jnz     loc_140044F75
0x1400450cc  mov     eax, [rsp+0D8h+var_A8]
0x1400450d0  neg     eax
0x1400450d2  sbb     eax, eax
0x1400450d4  and     eax, 0C0000022h
0x1400450d9  jmp     loc_140044F7A
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
