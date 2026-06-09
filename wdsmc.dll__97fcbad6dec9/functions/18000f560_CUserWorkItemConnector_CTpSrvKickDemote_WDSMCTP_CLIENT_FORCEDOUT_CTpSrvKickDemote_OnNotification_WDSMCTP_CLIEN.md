# CUserWorkItemConnector<CTpSrvKickDemote,_WDSMCTP_CLIENT_FORCEDOUT,&CTpSrvKickDemote::OnNotification(_WDSMCTP_CLIENT_FORCEDOUT *)>::_ThreadProc(void *)

- ea: `0x18000f560`
- end: `0x18000f5c4`
- name: `?_ThreadProc@?$CUserWorkItemConnector@VCTpSrvKickDemote@@U_WDSMCTP_CLIENT_FORCEDOUT@@$1?OnNotification@1@QEAAXPEAU2@@Z@@SAKPEAX@Z`
- size: `100`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops`

## callees

- `0x18000ee88`
- `0x18000f560`
- `0x18001a9a8`
- `0x180024c14`
- `0x180024ce0`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000f59b`
- `KERNEL32!SetEvent` at `0x18000f59b`

## pseudocode

```c
__int64 __fastcall CUserWorkItemConnector<CTpSrvKickDemote,_WDSMCTP_CLIENT_FORCEDOUT,&public: void CTpSrvKickDemote::OnNotification(_WDSMCTP_CLIENT_FORCEDOUT *)>::_ThreadProc(
        LPVOID lpThreadParameter)
{
  CTpSrvKickDemote **v1; // rbx

  v1 = *(CTpSrvKickDemote ***)lpThreadParameter;
  CTpSrvKickDemote::OnNotification(
    **(CTpSrvKickDemote ***)lpThreadParameter,
    *((struct _WDSMCTP_CLIENT_FORCEDOUT **)lpThreadParameter + 1));
  CMRSWLock::ReaderLock((LPCRITICAL_SECTION)(v1 + 4));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v1 + 4, 0xFFFFFFFF) == 1 )
    SetEvent(v1[3]);
  CMRSWLock::ReaderRelease((struct _RTL_CRITICAL_SECTION *)(v1 + 4));
  operator delete(lpThreadParameter);
  return 0;
}

```

## disassembly

```asm
0x18000f560  mov     [rsp+arg_8], rbx
0x18000f565  mov     [rsp+arg_10], rsi
0x18000f56a  push    rdi
0x18000f56b  sub     rsp, 20h
0x18000f56f  mov     rbx, [rcx]
0x18000f572  mov     rdi, rcx
0x18000f575  mov     rdx, [rcx+8]; struct _WDSMCTP_CLIENT_FORCEDOUT *
0x18000f579  mov     rcx, [rbx]; this
0x18000f57c  call    ?OnNotification@CTpSrvKickDemote@@QEAAXPEAU_WDSMCTP_CLIENT_FORCEDOUT@@@Z; CTpSrvKickDemote::OnNotification(_WDSMCTP_CLIENT_FORCEDOUT *)
0x18000f581  lea     rcx, [rbx+20h]; lpCriticalSection
0x18000f585  call    ?ReaderLock@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderLock(void)
0x18000f58a  or      eax, 0FFFFFFFFh
0x18000f58d  lock xadd [rbx+10h], eax
0x18000f592  cmp     eax, 1
0x18000f595  jnz     short loc_18000F5A1
0x18000f597  mov     rcx, [rbx+18h]; hEvent
0x18000f59b  call    cs:__imp_SetEvent
0x18000f5a1  lea     rcx, [rbx+20h]; this
0x18000f5a5  call    ?ReaderRelease@CMRSWLock@@QEAAXXZ; CMRSWLock::ReaderRelease(void)
0x18000f5aa  mov     rcx, rdi; void *
0x18000f5ad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f5b2  mov     rbx, [rsp+28h+arg_8]
0x18000f5b7  xor     eax, eax
0x18000f5b9  mov     rsi, [rsp+28h+arg_10]
0x18000f5be  add     rsp, 20h
0x18000f5c2  pop     rdi
0x18000f5c3  retn
```
