# SrvXsDownLevelAPI

- ea: `0x1400446d0`
- end: `0x140044a0d`
- name: `SrvXsDownLevelAPI`
- size: `829`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x14001389c`
- `0x140015790`
- `0x140016384`
- `0x140018884`
- `0x1400189b4`
- `0x14002a3e0`
- `0x14002a840`
- `0x1400446d0`

## import_xrefs

- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400447e2`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x1400447e2`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004483d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044869`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004483d`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140044869`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400447ca`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400447ca`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400448ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x140044932`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400448ee`
- `ntoskrnl!KeWaitForSingleObject` at `0x140044932`
- `ntoskrnl!KeInitializeEvent` at `0x140044742`
- `ntoskrnl!KeInitializeEvent` at `0x140044742`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044831`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004485d`
- `ntoskrnl!ExReleaseResourceLite` at `0x140044831`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004485d`
- `msrpc!RpcAsyncCancelCall` at `0x14004490a`
- `msrpc!RpcAsyncCancelCall` at `0x14004490a`
- `msrpc!RpcAsyncCompleteCall` at `0x14004498c`
- `msrpc!RpcAsyncCompleteCall` at `0x14004498c`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044755`
- `msrpc!RpcAsyncInitializeHandle` at `0x140044755`

## pseudocode

```c
__int64 __fastcall SrvXsDownLevelAPI(__int64 a1)
{
  unsigned int v3; // eax
  unsigned int v4; // ebx
  __int64 v5; // rdx
  RPC_STATUS v6; // esi
  RPC_STATUS v7; // eax
  int v8; // [rsp+30h] [rbp-A8h] BYREF
  union _LARGE_INTEGER Timeout; // [rsp+38h] [rbp-A0h] BYREF
  struct _KEVENT Event; // [rsp+40h] [rbp-98h] BYREF
  _RPC_ASYNC_STATE pAsync; // [rsp+60h] [rbp-78h] BYREF

  v8 = 5;
  memset(&Event, 0, sizeof(Event));
  memset(&pAsync, 0, sizeof(pAsync));
  if ( !a1 )
    return 3221225485LL;
  Timeout.QuadPart = -50000000;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  v3 = RpcAsyncInitializeHandle(&pAsync, 0x58u);
  v4 = v3;
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0 )
    {
      if ( BYTE1(WPP_GLOBAL_Control->Timer) )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v3);
    }
    return v4;
  }
  pAsync.NotificationType = RpcNotificationTypeEvent;
  pAsync.u.Event = &Event;
  KeEnterCriticalRegion();
  ExAcquireResourceSharedLite(&SrvXsResource, 1u);
  if ( SrvXsStatus == 2 )
  {
    _InterlockedIncrement(&SrvXsConnectCount);
    ExReleaseResourceLite(&SrvXsResource);
    KeLeaveCriticalRegion();
    XsProcDownLevelAPI(&pAsync, v5, a1, &v8);
    v4 = KeWaitForSingleObject(&Event, Executive, 0, 0, &Timeout);
    if ( v4 )
    {
      v6 = RpcAsyncCancelCall(&pAsync, 1);
      if ( !v6 )
        KeWaitForSingleObject(&Event, Executive, 0, 0, 0);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 29, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v4, v6);
      }
    }
    v7 = RpcAsyncCompleteCall(&pAsync, 0);
    _InterlockedDecrement(&SrvXsConnectCount);
    if ( (v4 & 0x80000000) == 0 )
      v4 = v7;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      WPP_SF_DDD(WPP_GLOBAL_Control->AttachedDevice, 30, WPP_892563a873b4365dd8b1a9616810a533_Traceguids, v4, v8, v7);
    }
    return v4;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x8000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_892563a873b4365dd8b1a9616810a533_Traceguids);
  }
  ExReleaseResourceLite(&SrvXsResource);
  KeLeaveCriticalRegion();
  return 3221225506LL;
}

```

## disassembly

```asm
0x1400446d0  mov     [rsp+arg_8], rbx
0x1400446d5  mov     [rsp+arg_10], rsi
0x1400446da  push    rdi
0x1400446db  sub     rsp, 0D0h
0x1400446e2  mov     rax, cs:__security_cookie
0x1400446e9  xor     rax, rsp
0x1400446ec  mov     [rsp+0D8h+var_18], rax
0x1400446f4  mov     rdi, rcx
0x1400446f7  mov     [rsp+0D8h+var_A8], 5
0x1400446ff  xorps   xmm0, xmm0
0x140044702  xor     eax, eax
0x140044704  movups  xmmword ptr [rsp+0D8h+Event.Header], xmm0
0x140044709  mov     [rsp+0D8h+Event.Header.WaitListHead.Blink], rax
0x14004470e  lea     ebx, [rax+58h]
0x140044711  mov     r8d, ebx; Size
0x140044714  xor     edx, edx; Val
0x140044716  lea     rcx, [rsp+0D8h+pAsync]; void *
0x14004471b  call    memset
0x140044720  test    rdi, rdi
0x140044723  jnz     short loc_14004472F
0x140044725  mov     eax, 0C000000Dh
0x14004472a  jmp     loc_1400449E7
0x14004472f  mov     qword ptr [rsp+0D8h+var_A0], 0FFFFFFFFFD050F80h
0x140044738  xor     r8d, r8d; State
0x14004473b  xor     edx, edx; Type
0x14004473d  lea     rcx, [rsp+0D8h+Event]; Event
0x140044742  call    cs:__imp_KeInitializeEvent
0x140044749  nop     dword ptr [rax+rax+00h]
0x14004474e  mov     edx, ebx; Size
0x140044750  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x140044755  call    cs:__imp_RpcAsyncInitializeHandle
0x14004475c  nop     dword ptr [rax+rax+00h]
0x140044761  mov     ebx, eax
0x140044763  test    eax, eax
0x140044765  jz      short loc_1400447B2
0x140044767  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x14004476e  mov     rcx, cs:WPP_GLOBAL_Control
0x140044775  cmp     rcx, rdi
0x140044778  jz      loc_1400449E5
0x14004477e  test    dword ptr [rcx+2Ch], 8000h
0x140044785  jz      loc_1400449E5
0x14004478b  cmp     byte ptr [rcx+29h], 1
0x14004478f  jb      loc_1400449E5
0x140044795  mov     edx, 1Ah
0x14004479a  mov     r9d, eax
0x14004479d  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x1400447a4  mov     rcx, [rcx+18h]
0x1400447a8  call    WPP_SF_d
0x1400447ad  jmp     loc_1400449E5
0x1400447b2  mov     [rsp+0D8h+pAsync.NotificationType], 1
0x1400447bd  lea     rax, [rsp+0D8h+Event]
0x1400447c2  mov     qword ptr [rsp+0D8h+pAsync.u], rax
0x1400447ca  call    cs:__imp_KeEnterCriticalRegion
0x1400447d1  nop     dword ptr [rax+rax+00h]
0x1400447d6  mov     dl, 1; Wait
0x1400447d8  lea     rsi, SrvXsResource
0x1400447df  mov     rcx, rsi; Resource
0x1400447e2  call    cs:__imp_ExAcquireResourceSharedLite
0x1400447e9  nop     dword ptr [rax+rax+00h]
0x1400447ee  cmp     cs:SrvXsStatus, 2
0x1400447f5  jz      short loc_140044853
0x1400447f7  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x1400447fe  mov     rcx, cs:WPP_GLOBAL_Control
0x140044805  cmp     rcx, rdi
0x140044808  jz      short loc_14004482E
0x14004480a  test    dword ptr [rcx+2Ch], 8000h
0x140044811  jz      short loc_14004482E
0x140044813  cmp     byte ptr [rcx+29h], 1
0x140044817  jb      short loc_14004482E
0x140044819  mov     edx, 1Bh
0x14004481e  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140044825  mov     rcx, [rcx+18h]
0x140044829  call    WPP_SF_
0x14004482e  mov     rcx, rsi; Resource
0x140044831  call    cs:__imp_ExReleaseResourceLite
0x140044838  nop     dword ptr [rax+rax+00h]
0x14004483d  call    cs:__imp_KeLeaveCriticalRegion
0x140044844  nop     dword ptr [rax+rax+00h]
0x140044849  mov     eax, 0C0000022h
0x14004484e  jmp     loc_1400449E7
0x140044853  lock inc cs:SrvXsConnectCount
0x14004485a  mov     rcx, rsi; Resource
0x14004485d  call    cs:__imp_ExReleaseResourceLite
0x140044864  nop     dword ptr [rax+rax+00h]
0x140044869  call    cs:__imp_KeLeaveCriticalRegion
0x140044870  nop     dword ptr [rax+rax+00h]
0x140044875  nop
0x140044876  lea     r9, [rsp+0D8h+var_A8]
0x14004487b  mov     r8, rdi
0x14004487e  lea     rcx, [rsp+0D8h+pAsync]
0x140044883  call    XsProcDownLevelAPI
0x140044888  jmp     short loc_1400448C7
0x14004488a  mov     ebx, eax
0x14004488c  lea     rax, WPP_GLOBAL_Control; __annotation("TMF:",
0x140044893  mov     rcx, cs:WPP_GLOBAL_Control
0x14004489a  cmp     rcx, rax
0x14004489d  jz      short loc_1400448C7
0x14004489f  test    dword ptr [rcx+2Ch], 8000h
0x1400448a6  jz      short loc_1400448C7
0x1400448a8  cmp     byte ptr [rcx+29h], 1
0x1400448ac  jb      short loc_1400448C7
0x1400448ae  mov     edx, 1Ch
0x1400448b3  mov     r9d, ebx
0x1400448b6  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x1400448bd  mov     rcx, [rcx+18h]
0x1400448c1  call    WPP_SF_d
0x1400448c6  nop
0x1400448c7  test    ebx, ebx
0x1400448c9  jz      short loc_1400448D7
0x1400448cb  lock dec cs:SrvXsConnectCount
0x1400448d2  jmp     loc_1400449E5
0x1400448d7  lea     rax, [rsp+0D8h+var_A0]
0x1400448dc  mov     [rsp+0D8h+Timeout], rax; Timeout
0x1400448e1  xor     r9d, r9d; Alertable
0x1400448e4  xor     r8d, r8d; WaitMode
0x1400448e7  xor     edx, edx; WaitReason
0x1400448e9  lea     rcx, [rsp+0D8h+Event]; Object
0x1400448ee  call    cs:__imp_KeWaitForSingleObject
0x1400448f5  nop     dword ptr [rax+rax+00h]
0x1400448fa  mov     ebx, eax
0x1400448fc  test    eax, eax
0x1400448fe  jz      short loc_14004497E
0x140044900  mov     edx, 1; fAbort
0x140044905  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x14004490a  call    cs:__imp_RpcAsyncCancelCall
0x140044911  nop     dword ptr [rax+rax+00h]
0x140044916  mov     esi, eax
0x140044918  test    eax, eax
0x14004491a  jnz     short loc_14004493E
0x14004491c  mov     [rsp+0D8h+Timeout], 0; Timeout
0x140044925  xor     r9d, r9d; Alertable
0x140044928  xor     r8d, r8d; WaitMode
0x14004492b  xor     edx, edx; WaitReason
0x14004492d  lea     rcx, [rsp+0D8h+Event]; Object
0x140044932  call    cs:__imp_KeWaitForSingleObject
0x140044939  nop     dword ptr [rax+rax+00h]
0x14004493e  lea     rdi, WPP_GLOBAL_Control; __annotation("TMF:",
0x140044945  mov     rcx, cs:WPP_GLOBAL_Control
0x14004494c  cmp     rcx, rdi
0x14004494f  jz      short loc_140044985
0x140044951  test    dword ptr [rcx+2Ch], 8000h
0x140044958  jz      short loc_140044985
0x14004495a  cmp     byte ptr [rcx+29h], 1
0x14004495e  jb      short loc_140044985
0x140044960  mov     edx, 1Dh
0x140044965  mov     dword ptr [rsp+0D8h+Timeout], esi
0x140044969  mov     r9d, ebx
0x14004496c  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x140044973  mov     rcx, [rcx+18h]
0x140044977  call    WPP_SF_Dd
0x14004497c  jmp     short loc_140044985
0x14004497e  lea     rdi, WPP_GLOBAL_Control
0x140044985  xor     edx, edx; Reply
0x140044987  lea     rcx, [rsp+0D8h+pAsync]; pAsync
0x14004498c  call    cs:__imp_RpcAsyncCompleteCall
0x140044993  nop     dword ptr [rax+rax+00h]
0x140044998  lock dec cs:SrvXsConnectCount
0x14004499f  test    ebx, ebx
0x1400449a1  cmovns  ebx, eax
0x1400449a4  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1400449ab  cmp     rcx, rdi
0x1400449ae  jz      short loc_1400449E5
0x1400449b0  test    dword ptr [rcx+2Ch], 8000h
0x1400449b7  jz      short loc_1400449E5
0x1400449b9  cmp     byte ptr [rcx+29h], 2
0x1400449bd  jb      short loc_1400449E5
0x1400449bf  mov     edx, 1Eh
0x1400449c4  mov     [rsp+0D8h+var_B0], eax
0x1400449c8  mov     r8d, [rsp+0D8h+var_A8]
0x1400449cd  mov     dword ptr [rsp+0D8h+Timeout], r8d
0x1400449d2  mov     r9d, ebx
0x1400449d5  lea     r8, WPP_892563a873b4365dd8b1a9616810a533_Traceguids
0x1400449dc  mov     rcx, [rcx+18h]
0x1400449e0  call    WPP_SF_DDD
0x1400449e5  mov     eax, ebx
0x1400449e7  mov     rcx, [rsp+0D8h+var_18]
0x1400449ef  xor     rcx, rsp; StackCookie
0x1400449f2  call    __security_check_cookie
0x1400449f7  lea     r11, [rsp+0D8h+var_8]
0x1400449ff  mov     rbx, [r11+18h]
0x140044a03  mov     rsi, [r11+20h]
0x140044a07  mov     rsp, r11
0x140044a0a  pop     rdi
0x140044a0b  retn
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
