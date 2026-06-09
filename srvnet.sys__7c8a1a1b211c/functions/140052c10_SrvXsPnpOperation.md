# SrvXsPnpOperation

- ea: `0x140052c10`
- end: `0x140053031`
- name: `SrvXsPnpOperation`
- size: `1057`
- prototype: `__int64 __fastcall(ULONG_PTR BugCheckParameter1)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140046b14`
- `0x1400527c0`

## callees

- `0x14000ebd0`
- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x140016450`
- `0x140018914`
- `0x14002a3e0`
- `0x14002a840`
- `0x140052c10`

## import_xrefs

- `ntoskrnl!KeBugCheckEx` at `0x140057934`
- `ntoskrnl!KeBugCheckEx` at `0x140057934`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140052d00`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140052d00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052d33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400578d9`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140052d33`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400578d9`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052ceb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x140052ceb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052e0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057967`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057a0e`
- `ntoskrnl!KeWaitForSingleObject` at `0x140052e0c`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057967`
- `ntoskrnl!KeWaitForSingleObject` at `0x140057a0e`
- `ntoskrnl!KeInitializeEvent` at `0x140052ca4`
- `ntoskrnl!KeInitializeEvent` at `0x140052ca4`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052d27`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400578cd`
- `ntoskrnl!ExReleaseResourceLite` at `0x140052d27`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400578cd`
- `msrpc!RpcAsyncCancelCall` at `0x1400579ea`
- `msrpc!RpcAsyncCancelCall` at `0x1400579ea`
- `msrpc!RpcAsyncCompleteCall` at `0x140052e2d`
- `msrpc!RpcAsyncCompleteCall` at `0x140052e2d`
- `msrpc!I_RpcExceptionFilter` at `0x14005749e`
- `msrpc!I_RpcExceptionFilter` at `0x14005749e`
- `msrpc!RpcAsyncInitializeHandle` at `0x140052cbd`
- `msrpc!RpcAsyncInitializeHandle` at `0x140052cbd`

## pseudocode

```c
void __fastcall SrvXsPnpOperation(ULONG_PTR BugCheckParameter1, unsigned __int8 a2)
{
  unsigned int v5; // eax
  int v6; // edx
  int v7; // r8d
  char v8; // bl
  int v9; // r8d
  int v10; // edx
  NTSTATUS v11; // eax
  int v12; // edx
  int v13; // r8d
  ULONG_PTR v14; // rbx
  unsigned int v15; // eax
  unsigned int v16; // ebx
  int v17; // ecx
  unsigned int v18; // eax
  int v19; // edx
  int v20; // r8d
  char v21; // bl
  int v22; // edx
  unsigned int v23; // ebx
  int v24; // r8d
  int v25; // [rsp+40h] [rbp-D8h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+48h] [rbp-D0h] BYREF
  ULONG_PTR v27; // [rsp+50h] [rbp-C8h]
  struct _KEVENT Event; // [rsp+58h] [rbp-C0h] BYREF
  ULONG_PTR v29; // [rsp+70h] [rbp-A8h]
  struct _RPC_ASYNC_STATE pAsync; // [rsp+80h] [rbp-98h] BYREF

  v29 = BugCheckParameter1;
  v27 = BugCheckParameter1;
  v25 = 0;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  Timeout.QuadPart = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_Zd(
      WPP_GLOBAL_Control->AttachedDevice,
      14,
      (unsigned int)WPP_892563a873b4365dd8b1a9616810a533_Traceguids,
      BugCheckParameter1,
      a2);
  }
  Timeout.QuadPart = -50000000;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v5 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v8 = v5;
  if ( v5 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 15, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v5);
    }
    if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
      McTemplateK0qhzr1d_EtwWriteTransfer(
        *(_WORD *)BugCheckParameter1 >> 1,
        v6,
        v7,
        0,
        *(_WORD *)BugCheckParameter1 >> 1,
        *(_QWORD *)(BugCheckParameter1 + 8),
        v8);
  }
  else
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
      XsProcessPnp((unsigned int)&pAsync, v10, a2, BugCheckParameter1, (__int64)&v25);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 18, WPP_892563a873b4365dd8b1a9616810a533_Traceguids);
      }
      v11 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
      v14 = v11;
      if ( v11 )
      {
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) )
        {
          WPP_SF_d(
            WPP_GLOBAL_Control->AttachedDevice,
            19,
            WPP_892563a873b4365dd8b1a9616810a533_Traceguids,
            (unsigned int)v11);
        }
        if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
          McTemplateK0qhzr1d_EtwWriteTransfer(
            *(_WORD *)BugCheckParameter1 >> 1,
            v12,
            v13,
            3,
            *(_WORD *)BugCheckParameter1 >> 1,
            *(_QWORD *)(BugCheckParameter1 + 8),
            v14);
        if ( SrvNetDebugMode )
          KeBugCheckEx(0x54u, BugCheckParameter1, v14, 0, 0);
        Timeout.QuadPart = -6000000000LL;
        v18 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
        v21 = v18;
        if ( v18 )
        {
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 20, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v18);
          }
          if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
            McTemplateK0qhzr1d_EtwWriteTransfer(
              *(_WORD *)BugCheckParameter1 >> 1,
              v19,
              v20,
              4,
              *(_WORD *)BugCheckParameter1 >> 1,
              *(_QWORD *)(BugCheckParameter1 + 8),
              v21);
          v23 = RpcAsyncCancelCall(&pAsync, 1);
          if ( v23 )
          {
            if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
              McTemplateK0qhzr1d_EtwWriteTransfer(
                *(_WORD *)BugCheckParameter1 >> 1,
                v22,
                v24,
                5,
                *(_WORD *)BugCheckParameter1 >> 1,
                *(_QWORD *)(BugCheckParameter1 + 8),
                v23);
          }
          else
          {
            KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
          }
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
            && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
          {
            WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 21, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v23);
          }
        }
      }
      v15 = RpcAsyncCompleteCall(&pAsync, 0);
      v16 = v15;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 22, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v15);
      }
      _InterlockedDecrement(&SrvXsConnectCount);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 23, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v16, v25);
      }
    }
    else
    {
      v17 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 16, WPP_892563a873b4365dd8b1a9616810a533_Traceguids);
      }
      if ( (WPP_MAIN_CB.Queue.Wcb.NumberOfChannels & 0x80000) != 0 )
        McTemplateK0qhzr1d_EtwWriteTransfer(
          v17,
          *(_WORD *)BugCheckParameter1 >> 1,
          v9,
          1,
          *(_WORD *)BugCheckParameter1 >> 1,
          *(_QWORD *)(BugCheckParameter1 + 8),
          0);
      ExReleaseResourceLite(&SrvXsResource);
      KeLeaveCriticalRegion();
    }
  }
}

```

## disassembly

```asm
0x140052c10  mov     [rsp+arg_10], rbx
0x140052c15  push    rsi
0x140052c16  push    rdi
0x140052c17  push    r12
0x140052c19  push    r14
0x140052c1b  push    r15
0x140052c1d  sub     rsp, 0F0h
0x140052c24  mov     rax, cs:__security_cookie
0x140052c2b  xor     rax, rsp
0x140052c2e  mov     [rsp+118h+var_38], rax
0x140052c36  movzx   edi, dl
0x140052c39  mov     r15, rcx
0x140052c3c  mov     [rsp+118h+var_A8], rcx
0x140052c41  mov     r14, rcx
0x140052c44  mov     [rsp+118h+var_C8], rcx
0x140052c49  xor     r12d, r12d
0x140052c4c  mov     [rsp+118h+var_D8], r12d
0x140052c51  xorps   xmm0, xmm0
0x140052c54  xor     eax, eax
0x140052c56  movups  xmmword ptr [rsp+118h+Event.Header], xmm0
0x140052c5b  mov     [rsp+118h+Event.Header.WaitListHead.Blink], rax
0x140052c60  xor     edx, edx; Val
0x140052c62  mov     r8d, 58h ; 'X'; Size
0x140052c68  lea     rcx, [rsp+118h+pAsync]; void *
0x140052c70  call    memset
0x140052c75  mov     qword ptr [rsp+118h+var_D0], r12
0x140052c7a  lea     rsi, WPP_GLOBAL_Control
0x140052c81  mov     rcx, cs:WPP_GLOBAL_Control
0x140052c88  cmp     rcx, rsi
0x140052c8b  jnz     loc_140052EA6
0x140052c91  mov     qword ptr [rsp+118h+var_D0], 0FFFFFFFFFD050F80h
0x140052c9a  xor     r8d, r8d; State
0x140052c9d  xor     edx, edx; Type
0x140052c9f  lea     rcx, [rsp+118h+Event]; Event
0x140052ca4  call    cs:__imp_KeInitializeEvent
0x140052cab  nop     dword ptr [rax+rax+00h]
0x140052cb0  mov     edx, 58h ; 'X'; Size
0x140052cb5  lea     rcx, [rsp+118h+pAsync]; pAsync
0x140052cbd  call    cs:__imp_RpcAsyncInitializeHandle
0x140052cc4  nop     dword ptr [rax+rax+00h]
0x140052cc9  mov     ebx, eax
0x140052ccb  test    eax, eax
0x140052ccd  jnz     loc_140052EDE
0x140052cd3  mov     [rsp+118h+pAsync.NotificationType], 1
0x140052cde  lea     rax, [rsp+118h+Event]
0x140052ce3  mov     qword ptr [rsp+118h+pAsync.u], rax
0x140052ceb  call    cs:__imp_KeEnterCriticalRegion
0x140052cf2  nop     dword ptr [rax+rax+00h]
0x140052cf7  mov     dl, 1; Wait
0x140052cf9  lea     rcx, SrvXsResource; Resource
0x140052d00  call    cs:__imp_ExAcquireResourceSharedLite
0x140052d07  nop     dword ptr [rax+rax+00h]
0x140052d0c  cmp     cs:SrvXsStatus, 2
0x140052d13  jnz     loc_140052F23
0x140052d19  lock inc cs:SrvXsConnectCount
0x140052d20  lea     rcx, SrvXsResource; Resource
0x140052d27  call    cs:__imp_ExReleaseResourceLite
0x140052d2e  nop     dword ptr [rax+rax+00h]
0x140052d33  call    cs:__imp_KeLeaveCriticalRegion
0x140052d3a  nop     dword ptr [rax+rax+00h]
0x140052d3f  nop
0x140052d40  lea     rax, [rsp+118h+var_D8]
0x140052d45  mov     [rsp+118h+Timeout], rax
0x140052d4a  mov     r9, r15
0x140052d4d  movzx   r8d, dil
0x140052d51  lea     rcx, [rsp+118h+pAsync]
0x140052d59  call    XsProcessPnp
0x140052d5e  jmp     short loc_140052DDD
0x140052d60  mov     ebx, eax
0x140052d62  lea     rax, WPP_GLOBAL_Control
0x140052d69  mov     rcx, cs:WPP_GLOBAL_Control
0x140052d70  cmp     rcx, rax
0x140052d73  jz      short loc_140052D9C
0x140052d75  test    dword ptr [rcx+2Ch], 8000h
0x140052d7c  jz      short loc_140052D9C
0x140052d7e  cmp     byte ptr [rcx+29h], 2
0x140052d82  jb      short loc_140052D9C
0x140052d84  mov     edx, 11h
0x140052d89  mov     r9d, ebx
0x140052d8c  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052d93  mov     rcx, [rcx+18h]
0x140052d97  call    WPP_SF_d
0x140052d9c  mov     r14, [rsp+118h+var_C8]
0x140052da1  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x140052da8  jz      short loc_140052DCE
0x140052daa  movzx   ecx, word ptr [r14]
0x140052dae  shr     cx, 1
0x140052db1  mov     [rsp+118h+var_E8], ebx
0x140052db5  mov     rax, [r14+8]
0x140052db9  mov     [rsp+118h+var_F0], rax
0x140052dbe  mov     word ptr [rsp+118h+Timeout], cx
0x140052dc3  mov     r9d, 2
0x140052dc9  call    McTemplateK0qhzr1d_EtwWriteTransfer
0x140052dce  xor     r12d, r12d
0x140052dd1  lea     rsi, WPP_GLOBAL_Control
0x140052dd8  mov     r15, [rsp+118h+var_A8]
0x140052ddd  test    ebx, ebx
0x140052ddf  jnz     loc_140052E9D
0x140052de5  mov     rcx, cs:WPP_GLOBAL_Control
0x140052dec  cmp     rcx, rsi
0x140052def  jnz     loc_140052F65
0x140052df5  lea     rax, [rsp+118h+var_D0]
0x140052dfa  mov     [rsp+118h+Timeout], rax; Timeout
0x140052dff  xor     r9d, r9d; Alertable
0x140052e02  xor     r8d, r8d; WaitMode
0x140052e05  xor     edx, edx; WaitReason
0x140052e07  lea     rcx, [rsp+118h+Event]; Object
0x140052e0c  call    cs:__imp_KeWaitForSingleObject
0x140052e13  nop     dword ptr [rax+rax+00h]
0x140052e18  movsxd  rbx, eax
0x140052e1b  test    eax, eax
0x140052e1d  jnz     loc_140052F96
0x140052e23  xor     edx, edx; Reply
0x140052e25  lea     rcx, [rsp+118h+pAsync]; pAsync
0x140052e2d  call    cs:__imp_RpcAsyncCompleteCall
0x140052e34  nop     dword ptr [rax+rax+00h]
0x140052e39  mov     ebx, eax
0x140052e3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140052e42  cmp     rcx, rsi
0x140052e45  jz      short loc_140052E54
0x140052e47  test    dword ptr [rcx+2Ch], 8000h
0x140052e4e  jnz     loc_140052FDB
0x140052e54  lock dec cs:SrvXsConnectCount
0x140052e5b  mov     rcx, cs:WPP_GLOBAL_Control
0x140052e62  cmp     rcx, rsi
0x140052e65  jz      short loc_140052E74
0x140052e67  test    dword ptr [rcx+2Ch], 8000h
0x140052e6e  jnz     loc_140053002
0x140052e74  mov     rcx, [rsp+118h+var_38]
0x140052e7c  xor     rcx, rsp; StackCookie
0x140052e7f  call    __security_check_cookie
0x140052e84  mov     rbx, [rsp+118h+arg_10]
0x140052e8c  add     rsp, 0F0h
0x140052e93  pop     r15
0x140052e95  pop     r14
0x140052e97  pop     r12
0x140052e99  pop     rdi
0x140052e9a  pop     rsi
0x140052e9b  retn
0x140052e9d  lock dec cs:SrvXsConnectCount
0x140052ea4  jmp     short loc_140052E74
0x140052ea6  test    dword ptr [rcx+2Ch], 8000h
0x140052ead  jz      loc_140052C91
0x140052eb3  cmp     byte ptr [rcx+29h], 1
0x140052eb7  jb      loc_140052C91
0x140052ebd  mov     edx, 0Eh
0x140052ec2  mov     dword ptr [rsp+118h+Timeout], edi
0x140052ec6  mov     r9, r15
0x140052ec9  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052ed0  mov     rcx, [rcx+18h]
0x140052ed4  call    WPP_SF_Zd
0x140052ed9  jmp     loc_140052C91
0x140052ede  mov     rcx, cs:WPP_GLOBAL_Control
0x140052ee5  cmp     rcx, rsi
0x140052ee8  jz      loc_140057864
0x140052eee  test    dword ptr [rcx+2Ch], 8000h
0x140052ef5  jz      loc_140057864
0x140052efb  cmp     byte ptr [rcx+29h], 1
0x140052eff  jb      loc_140057864
0x140052f05  mov     edx, 0Fh
0x140052f0a  mov     r9d, ebx
0x140052f0d  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052f14  mov     rcx, [rcx+18h]
0x140052f18  call    WPP_SF_d
0x140052f1d  nop
0x140052f1e  jmp     loc_140057864
0x140052f23  mov     rcx, cs:WPP_GLOBAL_Control
0x140052f2a  cmp     rcx, rsi
0x140052f2d  jz      loc_140057898
0x140052f33  test    dword ptr [rcx+2Ch], 8000h
0x140052f3a  jz      loc_140057898
0x140052f40  cmp     byte ptr [rcx+29h], 1
0x140052f44  jb      loc_140057898
0x140052f4a  mov     edx, 10h
0x140052f4f  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052f56  mov     rcx, [rcx+18h]
0x140052f5a  call    WPP_SF_
0x140052f5f  nop
0x140052f60  jmp     loc_140057898
0x140052f65  test    dword ptr [rcx+2Ch], 8000h
0x140052f6c  jz      loc_140052DF5
0x140052f72  cmp     byte ptr [rcx+29h], 1
0x140052f76  jb      loc_140052DF5
0x140052f7c  mov     edx, 12h
0x140052f81  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052f88  mov     rcx, [rcx+18h]
0x140052f8c  call    WPP_SF_
0x140052f91  jmp     loc_140052DF5
0x140052f96  mov     rcx, cs:WPP_GLOBAL_Control
0x140052f9d  cmp     rcx, rsi
0x140052fa0  jz      loc_1400578EB
0x140052fa6  test    dword ptr [rcx+2Ch], 8000h
0x140052fad  jz      loc_1400578EB
0x140052fb3  cmp     byte ptr [rcx+29h], 1
0x140052fb7  jb      loc_1400578EB
0x140052fbd  mov     edx, 13h
0x140052fc2  mov     r9d, ebx
0x140052fc5  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052fcc  mov     rcx, [rcx+18h]
0x140052fd0  call    WPP_SF_d
0x140052fd5  nop
0x140052fd6  jmp     loc_1400578EB
0x140052fdb  cmp     byte ptr [rcx+29h], 2
0x140052fdf  jb      loc_140052E54
0x140052fe5  mov     edx, 16h
0x140052fea  mov     r9d, ebx
0x140052fed  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140052ff4  mov     rcx, [rcx+18h]
0x140052ff8  call    WPP_SF_d
0x140052ffd  jmp     loc_140052E54
0x140053002  cmp     byte ptr [rcx+29h], 2
0x140053006  jb      loc_140052E74
0x14005300c  mov     edx, 17h
0x140053011  mov     eax, [rsp+118h+var_D8]
0x140053015  mov     dword ptr [rsp+118h+Timeout], eax
0x140053019  mov     r9d, ebx
0x14005301c  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140053023  mov     rcx, [rcx+18h]
0x140053027  call    WPP_SF_Dd
0x14005302c  jmp     loc_140052E74
0x140057490  push    rbp
0x140057492  sub     rsp, 40h
0x140057496  mov     rbp, rdx
0x140057499  mov     rcx, [rcx]
0x14005749c  mov     ecx, [rcx]; ExceptionCode
0x14005749e  call    cs:__imp_I_RpcExceptionFilter
0x1400574a5  nop     dword ptr [rax+rax+00h]
0x1400574aa  nop
0x1400574ab  add     rsp, 40h
0x1400574af  pop     rbp
0x1400574b0  retn
0x140057864  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14005786b  jz      loc_140052E74
0x140057871  movzx   ecx, word ptr [r15]
0x140057875  shr     cx, 1
0x140057878  mov     [rsp+118h+var_E8], ebx
0x14005787c  mov     rax, [r15+8]
0x140057880  mov     [rsp+118h+var_F0], rax
0x140057885  mov     word ptr [rsp+118h+Timeout], cx
0x14005788a  xor     r9d, r9d
0x14005788d  call    McTemplateK0qhzr1d_EtwWriteTransfer
0x140057892  nop
0x140057893  jmp     loc_140052E74
0x140057898  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x14005789f  jz      short loc_1400578C6
0x1400578a1  movzx   edx, word ptr [r15]
0x1400578a5  shr     dx, 1
0x1400578a8  mov     [rsp+118h+var_E8], r12d
0x1400578ad  mov     rax, [r15+8]
0x1400578b1  mov     [rsp+118h+var_F0], rax
0x1400578b6  mov     word ptr [rsp+118h+Timeout], dx
0x1400578bb  mov     r9d, 1
0x1400578c1  call    McTemplateK0qhzr1d_EtwWriteTransfer
0x1400578c6  lea     rcx, SrvXsResource; Resource
0x1400578cd  call    cs:__imp_ExReleaseResourceLite
0x1400578d4  nop     dword ptr [rax+rax+00h]
0x1400578d9  call    cs:__imp_KeLeaveCriticalRegion
0x1400578e0  nop     dword ptr [rax+rax+00h]
0x1400578e5  nop
0x1400578e6  jmp     loc_140052E74
0x1400578eb  test    byte ptr cs:WPP_MAIN_CB.Queue+12h, 8
0x1400578f2  jz      short loc_140057918
0x1400578f4  movzx   ecx, word ptr [r15]
0x1400578f8  shr     cx, 1
0x1400578fb  mov     [rsp+118h+var_E8], ebx
0x1400578ff  mov     rax, [r14+8]
0x140057903  mov     [rsp+118h+var_F0], rax
0x140057908  mov     word ptr [rsp+118h+Timeout], cx
0x14005790d  mov     r9d, 3
0x140057913  call    McTemplateK0qhzr1d_EtwWriteTransfer
0x140057918  cmp     cs:SrvNetDebugMode, 0
0x14005791f  jz      short loc_140057941
0x140057921  mov     r8, rbx; BugCheckParameter2
0x140057924  mov     [rsp+118h+Timeout], r12; BugCheckParameter4
0x140057929  xor     r9d, r9d; BugCheckParameter3
0x14005792c  mov     rdx, r14; BugCheckParameter1
0x14005792f  mov     ecx, 54h ; 'T'; BugCheckCode
0x140057934  call    cs:__imp_KeBugCheckEx
0x140057941  mov     rax, 0FFFFFFFE9A5F4400h
0x14005794b  mov     qword ptr [rsp+118h+var_D0], rax
0x140057950  lea     rax, [rsp+118h+var_D0]
0x140057955  mov     [rsp+118h+Timeout], rax; Timeout
0x14005795a  xor     r9d, r9d; Alertable
0x14005795d  xor     r8d, r8d; WaitMode
0x140057960  xor     edx, edx; WaitReason
0x140057962  lea     rcx, [rsp+118h+Event]; Object
0x140057967  call    cs:__imp_KeWaitForSingleObject
0x14005796e  nop     dword ptr [rax+rax+00h]
0x140057973  mov     ebx, eax
0x140057975  test    eax, eax
0x140057977  jz      loc_140052E23
0x14005797d  mov     rcx, cs:WPP_GLOBAL_Control
0x140057984  cmp     rcx, rsi
0x140057987  jz      short loc_1400579B0
0x140057989  test    dword ptr [rcx+2Ch], 8000h
0x140057990  jz      short loc_1400579B0
0x140057992  cmp     byte ptr [rcx+29h], 1
0x140057996  jb      short loc_1400579B0
0x140057998  mov     edx, 14h
0x14005799d  mov     r9d, eax
  ... truncated ...
```
