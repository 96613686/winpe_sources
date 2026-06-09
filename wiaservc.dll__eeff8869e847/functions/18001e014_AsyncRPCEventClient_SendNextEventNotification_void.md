# AsyncRPCEventClient::SendNextEventNotification(void)

- ea: `0x18001e014`
- end: `0x18001e35c`
- name: `?SendNextEventNotification@AsyncRPCEventClient@@QEAAJXZ`
- size: `840`
- prototype: `__int64 __fastcall(AsyncRPCEventClient *__hidden this)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18001de10`
- `0x180053788`

## callees

- `0x18000ac34`
- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18000da10`
- `0x18001e014`
- `0x180023070`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002de18`
- `0x18002def8`
- `0x18002e9d8`
- `0x18002eab4`
- `0x180078010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x18001e344`
- `KERNEL32!LeaveCriticalSection` at `0x18001e344`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0bb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0eb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0a3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0bb`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0d3`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e0eb`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18001e194`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18001e194`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e256`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001e256`

## string_xrefs

- `0x18001e275`: `Call to client through RpcAsyncCompleteCall failed 0x%x`
- `0x18001e299`: `Call to client through RpcAsyncCompleteCall failed 0x%x`
- `0x18001e1fe`: `Calling RpcAsyncCompleteCall`
- `0x18001e224`: `Calling RpcAsyncCompleteCall`

## pseudocode

```c
__int64 __fastcall AsyncRPCEventClient::SendNextEventNotification(AsyncRPCEventClient *this)
{
  unsigned int v2; // esi
  struct _RTL_CRITICAL_SECTION *v3; // r15
  int v4; // r12d
  __int64 v5; // rdx
  __int64 *v6; // rdx
  __int64 v7; // rbx
  char *v8; // rbx
  void *v9; // rdx
  void **lpMem; // rax
  void *v11; // rdx
  __int64 v12; // rcx
  RPC_STATUS v13; // eax
  RPC_STATUS v14; // r13d
  char *v15; // rbx
  void *v16; // rdx
  void **v17; // rax
  void *v18; // rdx
  __int64 v19; // rcx
  char *v20; // rbx
  void *v21; // rdx
  void **v22; // rax
  void *v23; // rdx
  __int64 v24; // rcx
  RPC_STATUS v25; // eax
  char *v26; // rbx
  void *v27; // rdx
  void **v28; // rax
  void *v29; // rdx
  __int64 v30; // rcx
  unsigned int NotificationsQueued; // [rsp+80h] [rbp+8h] BYREF
  int Reply; // [rsp+88h] [rbp+10h] BYREF
  int v34; // [rsp+90h] [rbp+18h]
  char *v35; // [rsp+98h] [rbp+20h]

  v2 = 0;
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 88);
  v35 = (char *)this + 88;
  v4 = CRIT_SECT::Lock((AsyncRPCEventClient *)((char *)this + 88));
  v34 = v4;
  if ( *((_QWORD *)this + 18) )
  {
    if ( *((_QWORD *)this + 19) )
    {
      Reply = 0;
      v5 = *((_QWORD *)this + 8);
      if ( v5 )
      {
        v6 = (__int64 *)(v5 + 8);
        v7 = *v6;
        CSimpleLinkedList<USDWrapper *>::Remove((char *)this + 56, v6);
        if ( v7 )
        {
          *(_OWORD *)*((_QWORD *)this + 19) = *(_OWORD *)(v7 + 12);
          *(_QWORD *)(*((_QWORD *)this + 19) + 16LL) = SysAllocString(*(const OLECHAR **)(v7 + 32));
          *(_QWORD *)(*((_QWORD *)this + 19) + 24LL) = SysAllocString(*(const OLECHAR **)(v7 + 40));
          *(_QWORD *)(*((_QWORD *)this + 19) + 32LL) = SysAllocString(*(const OLECHAR **)(v7 + 48));
          *(_QWORD *)(*((_QWORD *)this + 19) + 48LL) = SysAllocString(*(const OLECHAR **)(v7 + 56));
          *(_DWORD *)(*((_QWORD *)this + 19) + 40LL) = *(_DWORD *)(v7 + 64);
          *(_DWORD *)(*((_QWORD *)this + 19) + 56LL) = *(_DWORD *)(v7 + 68);
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
          NotificationsQueued = 0;
          v8 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Calling RpcServerUnsubscribeForNotification");
          WriteDbgTraceInfoWI("AsyncRPCEventClient::SendNextEventNotification", v8);
          WiaTrcLib::Free((WiaTrcLib *)v8, v9);
          lpMem = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Calling RpcServerUnsubscribeForNotification");
          WiaTrace_ProcessTrace_Ex(v12, v11, (void *)"AsyncRPCEventClient::SendNextEventNotification", 4, lpMem);
          v13 = RpcServerUnsubscribeForNotification(
                  *(RPC_BINDING_HANDLE *)(*((_QWORD *)this + 18) + 32LL),
                  RpcNotificationClientDisconnect,
                  &NotificationsQueued);
          v14 = v13;
          if ( v13 )
          {
            v15 = (char *)WiaTrace_TraceLogWithSubComp(
                            0,
                            "RpcServerUnsubscribeForNotification returned rpcStatus (%#x)",
                            v13);
            WriteDbgTraceWarningWI("AsyncRPCEventClient::SendNextEventNotification", v15);
            WiaTrcLib::Free((WiaTrcLib *)v15, v16);
            v17 = (void **)WiaTrace_TraceWithSubComp(
                             0,
                             "RpcServerUnsubscribeForNotification returned rpcStatus (%#x)",
                             v14);
            WiaTrace_ProcessTrace_Ex(v19, v18, (void *)"AsyncRPCEventClient::SendNextEventNotification", 2, v17);
          }
          v20 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(0, 0, "Calling RpcAsyncCompleteCall");
          WriteDbgTraceInfoWI("AsyncRPCEventClient::SendNextEventNotification", v20);
          WiaTrcLib::Free((WiaTrcLib *)v20, v21);
          v22 = (void **)WiaTrace_TraceWithSubCompTraceLevel(0, 0, "Calling RpcAsyncCompleteCall");
          WiaTrace_ProcessTrace_Ex(v24, v23, (void *)"AsyncRPCEventClient::SendNextEventNotification", 4, v22);
          v25 = RpcAsyncCompleteCall(*((PRPC_ASYNC_STATE *)this + 18), &Reply);
          if ( v25 > 0 )
          {
            v2 = (unsigned __int16)v25 | 0x80070000;
          }
          else
          {
            if ( !v25 )
            {
LABEL_12:
              *((_QWORD *)this + 18) = 0;
              *((_QWORD *)this + 19) = 0;
              goto LABEL_13;
            }
            v2 = v25;
          }
          v26 = (char *)WiaTrace_TraceLog("Call to client through RpcAsyncCompleteCall failed 0x%x");
          WriteDbgTraceErrorWI("AsyncRPCEventClient::SendNextEventNotification", v26);
          WiaTrcLib::Free((WiaTrcLib *)v26, v27);
          v28 = (void **)WiaTrace_Trace("Call to client through RpcAsyncCompleteCall failed 0x%x", v2);
          WiaTrace_ProcessTrace_Ex(v30, v29, (void *)"AsyncRPCEventClient::SendNextEventNotification", 1, v28);
          goto LABEL_12;
        }
      }
    }
  }
LABEL_13:
  if ( v4 )
    LeaveCriticalSection(v3);
  return v2;
}

```

## disassembly

```asm
0x18001e014  push    rbx
0x18001e016  push    rsi
0x18001e017  push    rdi
0x18001e018  push    r12
0x18001e01a  push    r13
0x18001e01c  push    r14
0x18001e01e  push    r15
0x18001e020  sub     rsp, 40h
0x18001e024  mov     r14, rcx
0x18001e027  xor     edi, edi
0x18001e029  mov     esi, edi
0x18001e02b  lea     r15, [rcx+58h]
0x18001e02f  mov     [rsp+78h+arg_18], r15
0x18001e037  mov     rcx, r15; this
0x18001e03a  call    ?Lock@CRIT_SECT@@QEAAHXZ; CRIT_SECT::Lock(void)
0x18001e03f  mov     r12d, eax
0x18001e042  mov     [rsp+78h+arg_10], eax
0x18001e049  cmp     [r14+90h], rdi
0x18001e050  jz      loc_18001E2C6
0x18001e056  cmp     [r14+98h], rdi
0x18001e05d  jz      loc_18001E2C6
0x18001e063  mov     [rsp+78h+Reply], edi
0x18001e06a  lea     rcx, [r14+38h]
0x18001e06e  mov     rdx, [rcx+8]
0x18001e072  test    rdx, rdx
0x18001e075  jz      loc_18001E2C6
0x18001e07b  add     rdx, 8
0x18001e07f  mov     rbx, [rdx]
0x18001e082  call    ?Remove@?$CSimpleLinkedList@PEAVUSDWrapper@@@@QEAAXAEBQEAVUSDWrapper@@@Z; CSimpleLinkedList<USDWrapper *>::Remove(USDWrapper * const &)
0x18001e087  test    rbx, rbx
0x18001e08a  jz      loc_18001E2C6
0x18001e090  movups  xmm0, xmmword ptr [rbx+0Ch]
0x18001e094  mov     rax, [r14+98h]
0x18001e09b  movdqu  xmmword ptr [rax], xmm0
0x18001e09f  mov     rcx, [rbx+20h]; psz
0x18001e0a3  call    cs:__imp_SysAllocString
0x18001e0a9  mov     rcx, rax
0x18001e0ac  mov     rax, [r14+98h]
0x18001e0b3  mov     [rax+10h], rcx
0x18001e0b7  mov     rcx, [rbx+28h]; psz
0x18001e0bb  call    cs:__imp_SysAllocString
0x18001e0c1  mov     rcx, rax
0x18001e0c4  mov     rax, [r14+98h]
0x18001e0cb  mov     [rax+18h], rcx
0x18001e0cf  mov     rcx, [rbx+30h]; psz
0x18001e0d3  call    cs:__imp_SysAllocString
0x18001e0d9  mov     rcx, rax
0x18001e0dc  mov     rax, [r14+98h]
0x18001e0e3  mov     [rax+20h], rcx
0x18001e0e7  mov     rcx, [rbx+38h]; psz
0x18001e0eb  call    cs:__imp_SysAllocString
0x18001e0f1  mov     rdx, rax
0x18001e0f4  mov     rax, [r14+98h]
0x18001e0fb  mov     [rax+30h], rdx
0x18001e0ff  mov     rdx, [r14+98h]
0x18001e106  mov     eax, [rbx+40h]
0x18001e109  mov     [rdx+28h], eax
0x18001e10c  mov     rdx, [r14+98h]
0x18001e113  mov     eax, [rbx+44h]
0x18001e116  mov     [rdx+38h], eax
0x18001e119  mov     rax, [rbx]
0x18001e11c  mov     rcx, rbx
0x18001e11f  mov     rax, [rax+10h]
0x18001e123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e128  mov     [rsp+78h+NotificationsQueued], edi
0x18001e12f  lea     r8, aCallingRpcserv_0; "Calling RpcServerUnsubscribeForNotifica"...
0x18001e136  xor     edx, edx
0x18001e138  xor     ecx, ecx
0x18001e13a  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001e13f  mov     rbx, rax
0x18001e142  mov     rdx, rax; char *
0x18001e145  lea     rcx, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e14c  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001e151  mov     rcx, rbx; this
0x18001e154  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e159  lea     r8, aCallingRpcserv_0; "Calling RpcServerUnsubscribeForNotifica"...
0x18001e160  xor     edx, edx
0x18001e162  xor     ecx, ecx
0x18001e164  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001e169  mov     [rsp+78h+lpMem], rax; lpMem
0x18001e16e  lea     r9d, [rdi+4]; int
0x18001e172  lea     r8, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e179  call    WiaTrace_ProcessTrace_Ex
0x18001e17e  mov     rcx, [r14+90h]
0x18001e185  lea     r8, [rsp+78h+NotificationsQueued]; NotificationsQueued
0x18001e18d  lea     edx, [rdi+1]; Notification
0x18001e190  mov     rcx, [rcx+20h]; Binding
0x18001e194  call    cs:__imp_RpcServerUnsubscribeForNotification
0x18001e19a  mov     r13d, eax
0x18001e19d  test    eax, eax
0x18001e19f  jz      short loc_18001E1F7
0x18001e1a1  mov     r8d, eax
0x18001e1a4  lea     rdx, aRpcserverunsub; "RpcServerUnsubscribeForNotification ret"...
0x18001e1ab  xor     ecx, ecx
0x18001e1ad  call    WiaTrace_TraceLogWithSubComp
0x18001e1b2  mov     rbx, rax
0x18001e1b5  mov     rdx, rax; char *
0x18001e1b8  lea     rcx, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e1bf  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001e1c4  mov     rcx, rbx; this
0x18001e1c7  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e1cc  mov     r8d, r13d
0x18001e1cf  lea     rdx, aRpcserverunsub; "RpcServerUnsubscribeForNotification ret"...
0x18001e1d6  xor     ecx, ecx
0x18001e1d8  call    WiaTrace_TraceWithSubComp
0x18001e1dd  mov     [rsp+78h+lpMem], rax; lpMem
0x18001e1e2  lea     r9d, [rdi+2]; int
0x18001e1e6  lea     r13, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e1ed  mov     r8, r13; int
0x18001e1f0  call    WiaTrace_ProcessTrace_Ex
0x18001e1f5  jmp     short loc_18001E1FE
0x18001e1f7  lea     r13, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e1fe  lea     r8, aCallingRpcasyn_0; "Calling RpcAsyncCompleteCall"
0x18001e205  xor     edx, edx
0x18001e207  xor     ecx, ecx
0x18001e209  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001e20e  mov     rbx, rax
0x18001e211  mov     rdx, rax; char *
0x18001e214  mov     rcx, r13; char *
0x18001e217  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001e21c  mov     rcx, rbx; this
0x18001e21f  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e224  lea     r8, aCallingRpcasyn_0; "Calling RpcAsyncCompleteCall"
0x18001e22b  xor     edx, edx
0x18001e22d  xor     ecx, ecx
0x18001e22f  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001e234  mov     [rsp+78h+lpMem], rax; lpMem
0x18001e239  mov     r9d, 4; int
0x18001e23f  mov     r8, r13; int
0x18001e242  call    WiaTrace_ProcessTrace_Ex
0x18001e247  lea     rdx, [rsp+78h+Reply]; Reply
0x18001e24f  mov     rcx, [r14+90h]; pAsync
0x18001e256  call    cs:__imp_RpcAsyncCompleteCall
0x18001e25c  test    eax, eax
0x18001e25e  jg      short loc_18001E266
0x18001e260  jz      short loc_18001E2B8
0x18001e262  mov     esi, eax
0x18001e264  jmp     short loc_18001E26F
0x18001e266  movzx   esi, ax
0x18001e269  or      esi, 80070000h
0x18001e26f  mov     [rsp+78h+var_48], esi
0x18001e273  mov     edx, esi
0x18001e275  lea     rcx, aCallToClientTh; "Call to client through RpcAsyncComplete"...
0x18001e27c  call    WiaTrace_TraceLog
0x18001e281  mov     rbx, rax
0x18001e284  mov     rdx, rax; char *
0x18001e287  mov     rcx, r13; char *
0x18001e28a  call    ?WriteDbgTraceErrorWI@@YAXPEAD0ZZ; WriteDbgTraceErrorWI(char *,char *,...)
0x18001e28f  mov     rcx, rbx; this
0x18001e292  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e297  mov     edx, esi
0x18001e299  lea     rcx, aCallToClientTh; "Call to client through RpcAsyncComplete"...
0x18001e2a0  call    WiaTrace_Trace
0x18001e2a5  mov     [rsp+78h+lpMem], rax; lpMem
0x18001e2aa  mov     r9d, 1; int
0x18001e2b0  mov     r8, r13; int
0x18001e2b3  call    WiaTrace_ProcessTrace_Ex
0x18001e2b8  mov     [r14+90h], rdi
0x18001e2bf  mov     [r14+98h], rdi
0x18001e2c6  jmp     short loc_18001E33C
0x18001e2c8  mov     edi, eax
0x18001e2ca  mov     r8d, eax
0x18001e2cd  lea     rdx, aRuntimeEventCl; "Runtime event client error: We caught e"...
0x18001e2d4  mov     ecx, 1
0x18001e2d9  call    WiaTrace_TraceLogWithSubComp
0x18001e2de  mov     rbx, rax
0x18001e2e1  mov     rdx, rax; char *
0x18001e2e4  lea     rcx, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e2eb  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001e2f0  mov     rcx, rbx; this
0x18001e2f3  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001e2f8  mov     r8d, edi
0x18001e2fb  lea     rdx, aRuntimeEventCl; "Runtime event client error: We caught e"...
0x18001e302  mov     ecx, 1
0x18001e307  call    WiaTrace_TraceWithSubComp
0x18001e30c  mov     [rsp+78h+lpMem], rax; lpMem
0x18001e311  mov     r9d, 2; int
0x18001e317  lea     r8, aAsyncrpceventc_4; "AsyncRPCEventClient::SendNextEventNotif"...
0x18001e31e  call    WiaTrace_ProcessTrace_Ex
0x18001e323  mov     esi, 8000FFFFh
0x18001e328  mov     [rsp+78h+var_48], esi
0x18001e32c  mov     r12d, [rsp+78h+arg_10]
0x18001e334  mov     r15, [rsp+78h+arg_18]
0x18001e33c  test    r12d, r12d
0x18001e33f  jz      short loc_18001E34A
0x18001e341  mov     rcx, r15; lpCriticalSection
0x18001e344  call    cs:__imp_LeaveCriticalSection
0x18001e34a  mov     eax, esi
0x18001e34c  add     rsp, 40h
0x18001e350  pop     r15
0x18001e352  pop     r14
0x18001e354  pop     r13
0x18001e356  pop     r12
0x18001e358  pop     rdi
0x18001e359  pop     rsi
0x18001e35a  pop     rbx
0x18001e35b  retn
```
