# LB_ABANDONED_CALL_MANAGER::CallbackSignal(void *,uchar)

- ea: `0x180023d58`
- end: `0x180023f94`
- name: `?CallbackSignal@LB_ABANDONED_CALL_MANAGER@@QEAAXPEAXE@Z`
- size: `572`
- prototype: `void __fastcall(LB_ABANDONED_CALL_MANAGER *__hidden this, void *, unsigned __int8)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180023fe0`

## callees

- `0x18001f848`
- `0x18001f870`
- `0x18001f898`
- `0x18001f920`
- `0x18001fac8`
- `0x18002079c`
- `0x180023d58`
- `0x180023f9c`

## import_xrefs

- `ntdll!RtlLeaveCriticalSection` at `0x180023de4`
- `ntdll!RtlLeaveCriticalSection` at `0x180023e95`
- `ntdll!RtlLeaveCriticalSection` at `0x180023f76`
- `ntdll!RtlLeaveCriticalSection` at `0x180023de4`
- `ntdll!RtlLeaveCriticalSection` at `0x180023e95`
- `ntdll!RtlLeaveCriticalSection` at `0x180023f76`
- `ntdll!RtlEnterCriticalSection` at `0x180023dcf`
- `ntdll!RtlEnterCriticalSection` at `0x180023e32`
- `ntdll!RtlEnterCriticalSection` at `0x180023f19`
- `ntdll!RtlEnterCriticalSection` at `0x180023dcf`
- `ntdll!RtlEnterCriticalSection` at `0x180023e32`
- `ntdll!RtlEnterCriticalSection` at `0x180023f19`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180023e0f`
- `KERNEL32!RegisterWaitForSingleObject` at `0x180023e0f`
- `KERNEL32!UnregisterWait` at `0x180023db0`
- `KERNEL32!UnregisterWait` at `0x180023edd`
- `KERNEL32!UnregisterWait` at `0x180023db0`
- `KERNEL32!UnregisterWait` at `0x180023edd`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180023f02`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180023f02`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180023f10`
- `RPCRT4!RpcSsDestroyClientContext` at `0x180023f10`

## pseudocode

```c
void __fastcall LB_ABANDONED_CALL_MANAGER::CallbackSignal(LB_ABANDONED_CALL_MANAGER *this, _DWORD **a2, char a3)
{
  _DWORD *v3; // rbx
  struct _RTL_CRITICAL_SECTION *v5; // rbp
  unsigned int i; // r9d
  __int64 v8; // rdi
  LB_ARBITRATOR *v9; // rcx
  _QWORD *v10; // rax
  __int64 v11; // rcx
  _QWORD *v12; // rdx
  unsigned int v13; // edx
  __int64 j; // rdx
  __int64 v15; // rdi
  _QWORD *v16; // rax
  __int64 v17; // rcx
  _QWORD *v18; // rdx
  unsigned int v19; // edx

  v3 = *a2;
  v5 = g_pAbandonedCallManager;
  if ( !**a2 )
  {
    for ( i = 0; i < v3[12]; ++i )
    {
      v8 = *((_QWORD *)v3 + 3) + 184LL * i;
      if ( a2 == (_DWORD **)(v8 + 168) )
        goto LABEL_7;
    }
    v8 = 0;
LABEL_7:
    UnregisterWait(*(HANDLE *)(v8 + 176));
    *(_QWORD *)(v8 + 176) = 0;
    if ( a3 )
      LBS_CALL::AbortAndWait((LBS_CALL *)v8, 0);
    RtlEnterCriticalSection(v5);
    if ( (unsigned int)LB_ARBITRATOR::CompleteAbandonedCall(v9, (struct LBS_CALL *)v8) )
    {
      RtlLeaveCriticalSection(v5);
      if ( RegisterWaitForSingleObject(
             (PHANDLE)(v8 + 176),
             *(HANDLE *)(v8 + 56),
             SignalCallbackFunction,
             (PVOID)(v8 + 168),
             0x2BF20u,
             8u) )
      {
        return;
      }
      *(_QWORD *)(v8 + 176) = 0;
      LBS_CALL::AbortAndWait((LBS_CALL *)v8, 1);
      RtlEnterCriticalSection(v5);
      *(_DWORD *)(v8 + 152) = 2;
    }
    if ( LB_ARBITRATOR::GetNumberOfPendingCalls((LB_ARBITRATOR *)v3, 0) )
    {
      v3 = 0;
LABEL_20:
      RtlLeaveCriticalSection(v5);
      if ( v3 )
        LB_ARBITRATOR::`scalar deleting destructor'((LB_ARBITRATOR *)v3, v13);
      return;
    }
    v10 = v3 + 2;
    v11 = *((_QWORD *)v3 + 1);
    if ( !v11 || (v12 = (_QWORD *)*((_QWORD *)v3 + 2)) == 0 )
    {
LABEL_18:
      *v10 = 0;
      *((_QWORD *)v3 + 2) = 0;
      goto LABEL_20;
    }
    if ( *(_QWORD **)(v11 + 8) == v10 && (_QWORD *)*v12 == v10 )
    {
      *v12 = v11;
      *(_QWORD *)(v11 + 8) = v12;
      goto LABEL_18;
    }
LABEL_38:
    __fastfail(3u);
  }
  for ( j = 0; (unsigned int)j < v3[4]; j = (unsigned int)(j + 1) )
  {
    v15 = *((_QWORD *)v3 + 1) + 144 * j;
    if ( a2 == (_DWORD **)(v15 + 128) )
      goto LABEL_27;
  }
  v15 = 0;
LABEL_27:
  UnregisterWait(*(HANDLE *)(v15 + 136));
  *(_QWORD *)(v15 + 136) = 0;
  if ( a3 )
    LB_USE_COUNT_CONTAINER::AbortAndWait((PRPC_ASYNC_STATE)v15, 0);
  if ( RpcAsyncCompleteCall((PRPC_ASYNC_STATE)v15, 0) )
    RpcSsDestroyClientContext((void **)(v15 + 112));
  RtlEnterCriticalSection(v5);
  *(_DWORD *)(v15 + 120) = 2;
  if ( (unsigned int)LBSVirtualChannelState::GetNumberOfPendingCalls((LBSVirtualChannelState *)v3) )
  {
    v3 = 0;
  }
  else
  {
    v16 = v3 + 6;
    v17 = *((_QWORD *)v3 + 3);
    if ( v17 )
    {
      v18 = (_QWORD *)*((_QWORD *)v3 + 4);
      if ( v18 )
      {
        if ( *(_QWORD **)(v17 + 8) != v16 || (_QWORD *)*v18 != v16 )
          goto LABEL_38;
        *v18 = v17;
        *(_QWORD *)(v17 + 8) = v18;
      }
    }
    *v16 = 0;
    *((_QWORD *)v3 + 4) = 0;
  }
  RtlLeaveCriticalSection(v5);
  if ( v3 )
    LBSVirtualChannelState::`scalar deleting destructor'((LBSVirtualChannelState *)v3, v19);
}

```

## disassembly

```asm
0x180023d58  push    rbx
0x180023d5a  push    rbp
0x180023d5b  push    rsi
0x180023d5c  push    rdi
0x180023d5d  push    r14
0x180023d5f  sub     rsp, 30h
0x180023d63  mov     rbx, [rdx]
0x180023d66  mov     r14b, r8b
0x180023d69  mov     rbp, cs:?g_pAbandonedCallManager@@3PEAVLB_ABANDONED_CALL_MANAGER@@EA; LB_ABANDONED_CALL_MANAGER * g_pAbandonedCallManager
0x180023d70  mov     r10, rdx
0x180023d73  cmp     dword ptr [rbx], 0
0x180023d76  jnz     loc_180023EB1
0x180023d7c  xor     r9d, r9d
0x180023d7f  cmp     r9d, [rbx+30h]
0x180023d83  jnb     short loc_180023DA4
0x180023d85  mov     eax, r9d
0x180023d88  imul    rdi, rax, 0B8h
0x180023d8f  add     rdi, [rbx+18h]
0x180023d93  lea     rax, [rdi+0A8h]
0x180023d9a  cmp     r10, rax
0x180023d9d  jz      short loc_180023DA6
0x180023d9f  inc     r9d
0x180023da2  jmp     short loc_180023D7F
0x180023da4  xor     edi, edi
0x180023da6  lea     rsi, [rdi+0B0h]
0x180023dad  mov     rcx, [rsi]; WaitHandle
0x180023db0  call    cs:__imp_UnregisterWait
0x180023db6  mov     qword ptr [rsi], 0
0x180023dbd  test    r14b, r14b
0x180023dc0  jz      short loc_180023DCC
0x180023dc2  xor     edx, edx; int
0x180023dc4  mov     rcx, rdi; this
0x180023dc7  call    ?AbortAndWait@LBS_CALL@@QEAAXH@Z; LBS_CALL::AbortAndWait(int)
0x180023dcc  mov     rcx, rbp; CriticalSection
0x180023dcf  call    cs:__imp_RtlEnterCriticalSection
0x180023dd5  mov     rdx, rdi; struct LBS_CALL *
0x180023dd8  call    ?CompleteAbandonedCall@LB_ARBITRATOR@@AEAAHPEAVLBS_CALL@@@Z; LB_ARBITRATOR::CompleteAbandonedCall(LBS_CALL *)
0x180023ddd  test    eax, eax
0x180023ddf  jz      short loc_180023E42
0x180023de1  mov     rcx, rbp; CriticalSection
0x180023de4  call    cs:__imp_RtlLeaveCriticalSection
0x180023dea  mov     rdx, [rdi+38h]; hObject
0x180023dee  lea     r9, [rdi+0A8h]; Context
0x180023df5  lea     r8, ?SignalCallbackFunction@@YAXPEAXE@Z; Callback
0x180023dfc  mov     [rsp+58h+dwFlags], 8; dwFlags
0x180023e04  mov     rcx, rsi; phNewWaitObject
0x180023e07  mov     [rsp+58h+dwMilliseconds], 2BF20h; dwMilliseconds
0x180023e0f  call    cs:__imp_RegisterWaitForSingleObject
0x180023e15  test    eax, eax
0x180023e17  jnz     loc_180023F89
0x180023e1d  lea     edx, [rax+1]; int
0x180023e20  mov     qword ptr [rsi], 0
0x180023e27  mov     rcx, rdi; this
0x180023e2a  call    ?AbortAndWait@LBS_CALL@@QEAAXH@Z; LBS_CALL::AbortAndWait(int)
0x180023e2f  mov     rcx, rbp; CriticalSection
0x180023e32  call    cs:__imp_RtlEnterCriticalSection
0x180023e38  mov     dword ptr [rdi+98h], 2
0x180023e42  xor     edx, edx; int
0x180023e44  mov     rcx, rbx; this
0x180023e47  call    ?GetNumberOfPendingCalls@LB_ARBITRATOR@@AEAAKH@Z; LB_ARBITRATOR::GetNumberOfPendingCalls(int)
0x180023e4c  test    eax, eax
0x180023e4e  jnz     short loc_180023E90
0x180023e50  lea     rax, [rbx+8]
0x180023e54  mov     rcx, [rax]
0x180023e57  test    rcx, rcx
0x180023e5a  jz      short loc_180023E7F
0x180023e5c  mov     rdx, [rax+8]
0x180023e60  test    rdx, rdx
0x180023e63  jz      short loc_180023E7F
0x180023e65  cmp     [rcx+8], rax
0x180023e69  jnz     loc_180023F6A
0x180023e6f  cmp     [rdx], rax
0x180023e72  jnz     loc_180023F6A
0x180023e78  mov     [rdx], rcx
0x180023e7b  mov     [rcx+8], rdx
0x180023e7f  mov     qword ptr [rax], 0
0x180023e86  mov     qword ptr [rbx+10h], 0
0x180023e8e  jmp     short loc_180023E92
0x180023e90  xor     ebx, ebx
0x180023e92  mov     rcx, rbp; CriticalSection
0x180023e95  call    cs:__imp_RtlLeaveCriticalSection
0x180023e9b  test    rbx, rbx
0x180023e9e  jz      loc_180023F89
0x180023ea4  mov     rcx, rbx; this
0x180023ea7  call    ??_GLB_ARBITRATOR@@QEAAPEAXI@Z; LB_ARBITRATOR::`scalar deleting destructor'(uint)
0x180023eac  jmp     loc_180023F89
0x180023eb1  xor     edx, edx
0x180023eb3  cmp     edx, [rbx+10h]
0x180023eb6  jnb     short loc_180023ED4
0x180023eb8  lea     rdi, [rdx+rdx*8]
0x180023ebc  shl     rdi, 4
0x180023ec0  add     rdi, [rbx+8]
0x180023ec4  lea     rax, [rdi+80h]
0x180023ecb  cmp     r10, rax
0x180023ece  jz      short loc_180023ED6
0x180023ed0  inc     edx
0x180023ed2  jmp     short loc_180023EB3
0x180023ed4  xor     edi, edi
0x180023ed6  mov     rcx, [rdi+88h]; WaitHandle
0x180023edd  call    cs:__imp_UnregisterWait
0x180023ee3  mov     qword ptr [rdi+88h], 0
0x180023eee  test    r14b, r14b
0x180023ef1  jz      short loc_180023EFD
0x180023ef3  xor     edx, edx; int
0x180023ef5  mov     rcx, rdi; pAsync
0x180023ef8  call    ?AbortAndWait@LB_USE_COUNT_CONTAINER@@QEAAXH@Z; LB_USE_COUNT_CONTAINER::AbortAndWait(int)
0x180023efd  xor     edx, edx; Reply
0x180023eff  mov     rcx, rdi; pAsync
0x180023f02  call    cs:__imp_RpcAsyncCompleteCall
0x180023f08  test    eax, eax
0x180023f0a  jz      short loc_180023F16
0x180023f0c  lea     rcx, [rdi+70h]; ContextHandle
0x180023f10  call    cs:__imp_RpcSsDestroyClientContext
0x180023f16  mov     rcx, rbp; CriticalSection
0x180023f19  call    cs:__imp_RtlEnterCriticalSection
0x180023f1f  mov     rcx, rbx; this
0x180023f22  mov     dword ptr [rdi+78h], 2
0x180023f29  call    ?GetNumberOfPendingCalls@LBSVirtualChannelState@@QEAAHXZ; LBSVirtualChannelState::GetNumberOfPendingCalls(void)
0x180023f2e  test    eax, eax
0x180023f30  jnz     short loc_180023F71
0x180023f32  lea     rax, [rbx+18h]
0x180023f36  mov     rcx, [rax]
0x180023f39  test    rcx, rcx
0x180023f3c  jz      short loc_180023F59
0x180023f3e  mov     rdx, [rax+8]
0x180023f42  test    rdx, rdx
0x180023f45  jz      short loc_180023F59
0x180023f47  cmp     [rcx+8], rax
0x180023f4b  jnz     short loc_180023F6A
0x180023f4d  cmp     [rdx], rax
0x180023f50  jnz     short loc_180023F6A
0x180023f52  mov     [rdx], rcx
0x180023f55  mov     [rcx+8], rdx
0x180023f59  mov     qword ptr [rax], 0
0x180023f60  mov     qword ptr [rbx+20h], 0
0x180023f68  jmp     short loc_180023F73
0x180023f6a  mov     ecx, 3
0x180023f6f  int     29h; Win8: RtlFailFast(ecx)
0x180023f71  xor     ebx, ebx
0x180023f73  mov     rcx, rbp; CriticalSection
0x180023f76  call    cs:__imp_RtlLeaveCriticalSection
0x180023f7c  test    rbx, rbx
0x180023f7f  jz      short loc_180023F89
0x180023f81  mov     rcx, rbx; this
0x180023f84  call    ??_GLBSVirtualChannelState@@QEAAPEAXI@Z; LBSVirtualChannelState::`scalar deleting destructor'(uint)
0x180023f89  add     rsp, 30h
0x180023f8d  pop     r14
0x180023f8f  pop     rdi
0x180023f90  pop     rsi
0x180023f91  pop     rbp
0x180023f92  pop     rbx
0x180023f93  retn
```
