# ServiceControl

- ea: `0x18002d570`
- end: `0x18002d6c0`
- name: `ServiceControl`
- size: `336`
- prototype: `void __stdcall(DWORD dwControl)`
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x18001c208`
- `0x18002c448`
- `0x18002d570`
- `0x18003dc84`

## import_xrefs

- `RPCRT4!RpcServerUnregisterIf` at `0x18002d6a2`
- `RPCRT4!RpcServerUnregisterIf` at `0x18002d6a2`
- `KERNEL32!SetEvent` at `0x18002d6b4`
- `KERNEL32!SetEvent` at `0x18002d6b4`
- `KERNEL32!Sleep` at `0x18002d67e`
- `KERNEL32!Sleep` at `0x18002d67e`

## string_xrefs

- `0x18002d578`: `Service control code=%ld`
- `0x18002d684`: `ServiceControl: calling RpcServerUnregisterIf`

## pseudocode

```c
void __fastcall ServiceControl(DWORD dwControl)
{
  __int64 v2; // rdx
  DWORD v3; // ecx
  DWORD v4; // r9d
  DWORD v5; // r8d
  __int64 v6; // rdx

  TRACELogPrint(0x40002u, "Service control code=%ld", dwControl);
  if ( ((dwControl - 1) & 0xFFFFFFFB) != 0 )
  {
    if ( dwControl == 2 )
    {
      TRACELogPrint(0x80002u, "Somebody did a 'NET PAUSE TAPISRV'... not allowing new clients...");
      dword_180051900 |= 4u;
      v3 = 7;
      gdwServiceState = 7;
      gdwCheckPoint = 0;
    }
    else if ( dwControl == 3 )
    {
      TRACELogPrint(0x80002u, "Somebody did a 'NET CONTINUE TAPISRV'... allowing new clients...");
      dword_180051900 &= ~4u;
      v3 = 4;
      gdwCheckPoint = 0;
      gdwServiceState = 4;
    }
    else
    {
      v3 = gdwServiceState;
      if ( gdwServiceState == 2 || gdwServiceState == 3 )
      {
        v4 = *(_DWORD *)&gdwWaitHint;
        v5 = ++gdwCheckPoint;
        goto LABEL_9;
      }
    }
    v4 = 0;
    v5 = 0;
LABEL_9:
    ReportStatusToSCMgr(v3, v2, v5, v4);
    return;
  }
  TRACELogPrint(0x80002u, "Somebody did a 'NET STOP TAPISRV'... exiting...");
  SendReinitMsgToAllXxxApps();
  gdwCheckPoint = 0;
  gdwServiceState = 3;
  ReportStatusToSCMgr(3u, v6, 0, 0xFA0u);
  Sleep(0xFA0u);
  TRACELogPrint(0x80002u, "ServiceControl: calling RpcServerUnregisterIf");
  RpcServerUnregisterIf(qword_180041EE0, 0, 1u);
  if ( ghEventService )
    SetEvent(ghEventService);
}

```

## disassembly

```asm
0x18002d570  push    rbx
0x18002d572  sub     rsp, 20h
0x18002d576  mov     ebx, ecx
0x18002d578  lea     rdx, aServiceControl; "Service control code=%ld"
0x18002d57f  mov     r8d, ecx
0x18002d582  mov     ecx, 40002h
0x18002d587  call    TRACELogPrint
0x18002d58c  lea     eax, [rbx-1]
0x18002d58f  test    eax, 0FFFFFFFBh
0x18002d594  jz      loc_18002D63E
0x18002d59a  cmp     ebx, 2
0x18002d59d  jnz     short loc_18002D5CC
0x18002d59f  lea     rdx, aSomebodyDidANe_1; "Somebody did a 'NET PAUSE TAPISRV'... n"...
0x18002d5a6  mov     ecx, 80002h
0x18002d5ab  call    TRACELogPrint
0x18002d5b0  or      cs:dword_180051900, 4
0x18002d5b7  lea     ecx, [rbx+5]
0x18002d5ba  mov     cs:gdwServiceState, ecx
0x18002d5c0  mov     cs:gdwCheckPoint, 0
0x18002d5ca  jmp     short loc_18002D614
0x18002d5cc  cmp     ebx, 3
0x18002d5cf  jnz     short loc_18002D602
0x18002d5d1  lea     rdx, aSomebodyDidANe_0; "Somebody did a 'NET CONTINUE TAPISRV'.."...
0x18002d5d8  mov     ecx, 80002h
0x18002d5dd  call    TRACELogPrint
0x18002d5e2  and     cs:dword_180051900, 0FFFFFFFBh
0x18002d5e9  lea     ecx, [rbx+1]
0x18002d5ec  mov     cs:gdwCheckPoint, 0
0x18002d5f6  mov     cs:gdwServiceState, 4
0x18002d600  jmp     short loc_18002D614
0x18002d602  mov     ecx, cs:gdwServiceState
0x18002d608  mov     eax, ecx
0x18002d60a  sub     eax, 2
0x18002d60d  jz      short loc_18002D624
0x18002d60f  cmp     eax, 1
0x18002d612  jz      short loc_18002D624
0x18002d614  xor     r9d, r9d
0x18002d617  xor     r8d, r8d
0x18002d61a  add     rsp, 20h
0x18002d61e  pop     rbx
0x18002d61f  jmp     ReportStatusToSCMgr
0x18002d624  mov     r8d, cs:gdwCheckPoint
0x18002d62b  mov     r9d, cs:gdwWaitHint
0x18002d632  inc     r8d
0x18002d635  mov     cs:gdwCheckPoint, r8d
0x18002d63c  jmp     short loc_18002D61A
0x18002d63e  lea     rdx, aSomebodyDidANe; "Somebody did a 'NET STOP TAPISRV'... ex"...
0x18002d645  mov     ecx, 80002h
0x18002d64a  call    TRACELogPrint
0x18002d64f  call    SendReinitMsgToAllXxxApps
0x18002d654  xor     r8d, r8d
0x18002d657  mov     cs:gdwCheckPoint, 0
0x18002d661  mov     ebx, 0FA0h
0x18002d666  mov     cs:gdwServiceState, 3
0x18002d670  mov     r9d, ebx
0x18002d673  lea     ecx, [r8+3]
0x18002d677  call    ReportStatusToSCMgr
0x18002d67c  mov     ecx, ebx; dwMilliseconds
0x18002d67e  call    cs:__imp_Sleep
0x18002d684  lea     rdx, aServicecontrol; "ServiceControl: calling RpcServerUnregi"...
0x18002d68b  mov     ecx, 80002h
0x18002d690  call    TRACELogPrint
0x18002d695  xor     edx, edx; MgrTypeUuid
0x18002d697  lea     rcx, qword_180041EE0; IfSpec
0x18002d69e  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18002d6a2  call    cs:__imp_RpcServerUnregisterIf
0x18002d6a8  mov     rcx, cs:ghEventService; hEvent
0x18002d6af  test    rcx, rcx
0x18002d6b2  jz      short loc_18002D6BA
0x18002d6b4  call    cs:__imp_SetEvent
0x18002d6ba  add     rsp, 20h
0x18002d6be  pop     rbx
0x18002d6bf  retn
```
