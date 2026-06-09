# SrvXsAddPrintJob

- ea: `0x140044a90`
- end: `0x140044de9`
- name: `SrvXsAddPrintJob`
- size: `857`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x14001878c`
- `0x14002a3e0`
- `0x14002a840`
- `0x1400413a0`
- `0x140044a90`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140044beb`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140044beb`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c91`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c43`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044c91`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044bd6`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140044bd6`
- `ntoskrnl!KeWaitForSingleObject` at `0x140044d6d`
- `ntoskrnl!KeWaitForSingleObject` at `0x140044d6d`
- `ntoskrnl!KeInitializeEvent` at `0x140044b5c`
- `ntoskrnl!KeInitializeEvent` at `0x140044b5c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c37`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c85`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c37`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044c85`
- `msrpc!RpcAsyncCompleteCall` at `0x140044d83`
- `msrpc!RpcAsyncCompleteCall` at `0x140044d83`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044b72`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044b72`

## pseudocode

```c
__int64 __fastcall SrvXsAddPrintJob(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        __int64 a7,
        _DWORD *a8)
{
  unsigned int v9; // eax
  unsigned int v10; // ebx
  int v12; // edx
  unsigned int v13; // ebx
  __int128 v16; // [rsp+60h] [rbp-D8h] BYREF
  _DWORD *v17; // [rsp+70h] [rbp-C8h]
  struct _KEVENT Event; // [rsp+78h] [rbp-C0h] BYREF
  struct _RPC_ASYNC_STATE pAsync; // [rsp+90h] [rbp-A8h] BYREF

  *(_QWORD *)&v16 = a1;
  v17 = a8;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  *a8 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_449961259f2532308161ede427ce4710_Traceguids);
  }
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v9 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v10 = v9;
  if ( !v9 )
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
      XsAddJob((unsigned int)&pAsync, v12, v16, a2, a3, a7, (__int64)a8);
      if ( a4 && a5 && a6 )
      {
        v16 = SumGuid_PRINT;
        SrvAdminSumTraceIPAddress(&v16, a4, a5, a6);
      }
      KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      v13 = RpcAsyncCompleteCall(&pAsync, 0);
      _InterlockedDecrement(&SrvXsConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 19, WPP_449961259f2532308161ede427ce4710_Traceguids, v13, *a8);
      }
      if ( !v13 )
        return *a8 != 0 ? 0xC0000022 : 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 17, WPP_449961259f2532308161ede427ce4710_Traceguids);
      }
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
    }
    return 3221225506LL;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
  {
    if ( BYTE1(WPP_GLOBAL_Control->Timer) )
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_449961259f2532308161ede427ce4710_Traceguids, v9);
  }
  return v10;
}

```

## disassembly

```asm
0x140044a90  push    rbx
0x140044a92  push    rsi
0x140044a93  push    r12
0x140044a95  push    r13
0x140044a97  push    r14
0x140044a99  push    r15
0x140044a9b  sub     rsp, 108h
0x140044aa2  mov     rax, cs:__security_cookie
0x140044aa9  xor     rax, rsp
0x140044aac  mov     [rsp+138h+var_48], rax
0x140044ab4  mov     r13, r9
0x140044ab7  mov     [rsp+138h+var_F0], r8
0x140044abc  mov     [rsp+138h+var_E8], rdx
0x140044ac1  mov     qword ptr [rsp+138h+var_D8], rcx
0x140044ac6  mov     r15, [rsp+138h+arg_20]
0x140044ace  mov     r12, [rsp+138h+arg_28]
0x140044ad6  mov     rax, [rsp+138h+arg_30]
0x140044ade  mov     [rsp+138h+var_F8], rax
0x140044ae3  mov     rsi, [rsp+138h+arg_38]
0x140044aeb  mov     [rsp+138h+var_C8], rsi
0x140044af0  xorps   xmm0, xmm0
0x140044af3  xor     eax, eax
0x140044af5  movups  xmmword ptr [rsp+138h+Event.Header], xmm0
0x140044afa  mov     [rsp+138h+Event.Header.WaitListHead.Blink], rax
0x140044b02  lea     ebx, [rax+58h]
0x140044b05  mov     r8d, ebx; Size
0x140044b08  xor     edx, edx; Val
0x140044b0a  lea     rcx, [rsp+138h+pAsync]; void *
0x140044b12  call    memset
0x140044b17  mov     dword ptr [rsi], 0
0x140044b1d  lea     r14, WPP_GLOBAL_Control; __annotation("TMF:",
0x140044b24  mov     rcx, cs:WPP_GLOBAL_Control
0x140044b2b  cmp     rcx, r14
0x140044b2e  jz      short loc_140044B52
0x140044b30  test    dword ptr [rcx+2Ch], 8000h
0x140044b37  jz      short loc_140044B52
0x140044b39  cmp     byte ptr [rcx+29h], 2
0x140044b3d  jb      short loc_140044B52
0x140044b3f  lea     edx, [rbx-49h]
0x140044b42  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044b49  mov     rcx, [rcx+18h]
0x140044b4d  call    WPP_SF_
0x140044b52  xor     r8d, r8d; State
0x140044b55  xor     edx, edx; Type
0x140044b57  lea     rcx, [rsp+138h+Event]; Event
0x140044b5c  call    cs:__imp_KeInitializeEvent
0x140044b63  nop     dword ptr [rax+rax+00h]
0x140044b68  mov     edx, ebx; Size
0x140044b6a  lea     rcx, [rsp+138h+pAsync]; pAsync
0x140044b72  call    cs:__imp_RpcAsyncInitializeHandle
0x140044b79  nop     dword ptr [rax+rax+00h]
0x140044b7e  mov     ebx, eax
0x140044b80  test    eax, eax
0x140044b82  jz      short loc_140044BBE
0x140044b84  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044b8b  cmp     rcx, r14
0x140044b8e  jz      short loc_140044BB7
0x140044b90  test    dword ptr [rcx+2Ch], 8000h
0x140044b97  jz      short loc_140044BB7
0x140044b99  cmp     byte ptr [rcx+29h], 1
0x140044b9d  jb      short loc_140044BB7
0x140044b9f  mov     edx, 10h
0x140044ba4  mov     r9d, eax
0x140044ba7  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044bae  mov     rcx, [rcx+18h]
0x140044bb2  call    WPP_SF_d
0x140044bb7  mov     eax, ebx
0x140044bb9  jmp     loc_140044C54
0x140044bbe  mov     [rsp+138h+pAsync.NotificationType], 1
0x140044bc9  lea     rax, [rsp+138h+Event]
0x140044bce  mov     qword ptr [rsp+138h+pAsync.u], rax
0x140044bd6  call    cs:__imp_KeEnterCriticalRegion
0x140044bdd  nop     dword ptr [rax+rax+00h]
0x140044be2  mov     dl, 1; Wait
0x140044be4  lea     rcx, SrvXsResource; Resource
0x140044beb  call    cs:__imp_ExAcquireResourceSharedLite
0x140044bf2  nop     dword ptr [rax+rax+00h]
0x140044bf7  cmp     cs:SrvXsStatus, 2
0x140044bfe  jz      short loc_140044C77
0x140044c00  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044c07  cmp     rcx, r14
0x140044c0a  jz      short loc_140044C30
0x140044c0c  test    dword ptr [rcx+2Ch], 8000h
0x140044c13  jz      short loc_140044C30
0x140044c15  cmp     byte ptr [rcx+29h], 1
0x140044c19  jb      short loc_140044C30
0x140044c1b  mov     edx, 11h
0x140044c20  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044c27  mov     rcx, [rcx+18h]
0x140044c2b  call    WPP_SF_
0x140044c30  lea     rcx, SrvXsResource; Resource
0x140044c37  call    cs:__imp_ExReleaseResourceLite
0x140044c3e  nop     dword ptr [rax+rax+00h]
0x140044c43  call    cs:__imp_KeLeaveCriticalRegion
0x140044c4a  nop     dword ptr [rax+rax+00h]
0x140044c4f  mov     eax, 0C0000022h
0x140044c54  mov     rcx, [rsp+138h+var_48]
0x140044c5c  xor     rcx, rsp; StackCookie
0x140044c5f  call    __security_check_cookie
0x140044c64  add     rsp, 108h
0x140044c6b  pop     r15
0x140044c6d  pop     r14
0x140044c6f  pop     r13
0x140044c71  pop     r12
0x140044c73  pop     rsi
0x140044c74  pop     rbx
0x140044c75  retn
0x140044c77  lock inc cs:SrvXsConnectCount
0x140044c7e  lea     rcx, SrvXsResource; Resource
0x140044c85  call    cs:__imp_ExReleaseResourceLite
0x140044c8c  nop     dword ptr [rax+rax+00h]
0x140044c91  call    cs:__imp_KeLeaveCriticalRegion
0x140044c98  nop     dword ptr [rax+rax+00h]
0x140044c9d  nop
0x140044c9e  mov     [rsp+138h+var_108], rsi
0x140044ca3  mov     rax, [rsp+138h+var_F8]
0x140044ca8  mov     [rsp+138h+var_110], rax
0x140044cad  mov     rax, [rsp+138h+var_F0]
0x140044cb2  mov     [rsp+138h+Timeout], rax
0x140044cb7  mov     r9, [rsp+138h+var_E8]
0x140044cbc  mov     r8, qword ptr [rsp+138h+var_D8]
0x140044cc1  lea     rcx, [rsp+138h+pAsync]
0x140044cc9  call    XsAddJob
0x140044cce  test    r13, r13
0x140044cd1  jz      short loc_140044CFD
0x140044cd3  test    r15, r15
0x140044cd6  jz      short loc_140044CFD
0x140044cd8  test    r12, r12
0x140044cdb  jz      short loc_140044CFD
0x140044cdd  movups  xmm0, cs:SumGuid_PRINT
0x140044ce4  movdqu  [rsp+138h+var_D8], xmm0
0x140044cea  mov     r9, r12
0x140044ced  mov     r8, r15
0x140044cf0  mov     rdx, r13
0x140044cf3  lea     rcx, [rsp+138h+var_D8]
0x140044cf8  call    SrvAdminSumTraceIPAddress
0x140044cfd  jmp     short loc_140044D47
0x140044cff  mov     ebx, eax
0x140044d01  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140044d08  mov     rcx, cs:WPP_GLOBAL_Control
0x140044d0f  cmp     rcx, rax
0x140044d12  jz      short loc_140044D3B
0x140044d14  test    dword ptr [rcx+2Ch], 8000h
0x140044d1b  jz      short loc_140044D3B
0x140044d1d  cmp     byte ptr [rcx+29h], 2
0x140044d21  jb      short loc_140044D3B
0x140044d23  mov     edx, 12h
0x140044d28  mov     r9d, ebx
0x140044d2b  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044d32  mov     rcx, [rcx+18h]
0x140044d36  call    WPP_SF_d
0x140044d3b  lea     r14, WPP_GLOBAL_Control
0x140044d42  mov     rsi, [rsp+138h+var_C8]
0x140044d47  test    ebx, ebx
0x140044d49  jz      short loc_140044D57
0x140044d4b  lock dec cs:SrvXsConnectCount
0x140044d52  jmp     loc_140044BB7
0x140044d57  mov     [rsp+138h+Timeout], 0; Timeout
0x140044d60  xor     r9d, r9d; Alertable
0x140044d63  xor     r8d, r8d; WaitMode
0x140044d66  xor     edx, edx; WaitReason
0x140044d68  lea     rcx, [rsp+138h+Event]; Object
0x140044d6d  call    cs:__imp_KeWaitForSingleObject
0x140044d74  nop     dword ptr [rax+rax+00h]
0x140044d79  xor     edx, edx; Reply
0x140044d7b  lea     rcx, [rsp+138h+pAsync]; pAsync
0x140044d83  call    cs:__imp_RpcAsyncCompleteCall
0x140044d8a  nop     dword ptr [rax+rax+00h]
0x140044d8f  mov     ebx, eax
0x140044d91  lock dec cs:SrvXsConnectCount
0x140044d98  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x140044d9f  cmp     rcx, r14
0x140044da2  jz      short loc_140044DD1
0x140044da4  test    dword ptr [rcx+2Ch], 8000h
0x140044dab  jz      short loc_140044DD1
0x140044dad  cmp     byte ptr [rcx+29h], 2
0x140044db1  jb      short loc_140044DD1
0x140044db3  mov     edx, 13h
0x140044db8  mov     eax, [rsi]
0x140044dba  mov     dword ptr [rsp+138h+Timeout], eax
0x140044dbe  mov     r9d, ebx
0x140044dc1  lea     r8, WPP_449961259f2532308161ede427ce4710_Traceguids
0x140044dc8  mov     rcx, [rcx+18h]
0x140044dcc  call    WPP_SF_Dd
0x140044dd1  test    ebx, ebx
0x140044dd3  jnz     loc_140044C4F
0x140044dd9  mov     eax, [rsi]
0x140044ddb  neg     eax
0x140044ddd  sbb     eax, eax
0x140044ddf  and     eax, 0C0000022h
0x140044de4  jmp     loc_140044C54
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
