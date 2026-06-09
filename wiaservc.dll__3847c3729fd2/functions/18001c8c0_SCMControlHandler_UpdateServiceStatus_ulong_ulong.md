# SCMControlHandler::UpdateServiceStatus(ulong,ulong)

- ea: `0x18001c8c0`
- end: `0x18001cae0`
- name: `?UpdateServiceStatus@SCMControlHandler@@UEAAJKK@Z`
- size: `544`
- prototype: `__int64 __fastcall(SCMControlHandler *__hidden this, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000b6a0`
- `0x18000cba0`
- `0x18000d770`
- `0x18000d7b0`
- `0x18001c8c0`
- `0x18002c868`
- `0x18002c8b0`
- `0x18002e9d8`
- `0x18002eab4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18001cab5`
- `KERNEL32!GetLastError` at `0x18001cab5`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001ca81`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x18001ca81`

## string_xrefs

- `0x18001c935`: `SERVICE_UNKNOWN`
- `0x18001c92a`: `SERVICE_PAUSE_PENDING`
- `0x18001c909`: `SERVICE_STOP_PENDING`
- `0x18001c940`: `SERVICE_PAUSED`
- `0x18001c8fe`: `SERVICE_START_PENDING`
- `0x18001c91f`: `SERVICE_CONTINUE_PENDING`
- `0x18001c8f3`: `SERVICE_STOPPED`
- `0x18001c914`: `SERVICE_RUNNING`
- `0x18001c9b2`: `SCMControlHandler::UpdateServiceStatus`
- `0x18001c9e2`: `SCMControlHandler::UpdateServiceStatus`
- `0x18001ca20`: `SCMControlHandler::UpdateServiceStatus`
- `0x18001ca6d`: `SCMControlHandler::UpdateServiceStatus`
- `0x18001c9a1`: `Attempting to update service status when the SCMControlHandler has not been successfully initialized.`
- `0x18001c9c9`: `Attempting to update service status when the SCMControlHandler has not been successfully initialized.`
- `0x18001ca08`: `Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d`
- `0x18001ca4a`: `Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d`

## pseudocode

```c
signed int __fastcall SCMControlHandler::UpdateServiceStatus(SCMControlHandler *this, int a2, int a3)
{
  signed int result; // eax
  const char *v6; // r14
  unsigned int v7; // edx
  int v8; // r8d
  char *v9; // rbx
  void *v10; // rdx
  void **lpMem; // rax
  void *v12; // rdx
  __int64 v13; // rcx
  const char *v14; // r9
  char *v15; // rbx
  void *v16; // rdx
  __int64 v17; // rcx
  void **v18; // rax
  void *v19; // rdx
  __int64 v20; // rcx
  const char *v21; // [rsp+30h] [rbp-59h]
  _DWORD v22[2]; // [rsp+38h] [rbp-51h]
  const char *v23; // [rsp+40h] [rbp-49h]
  int v24; // [rsp+48h] [rbp-41h]
  const char *v25; // [rsp+50h] [rbp-39h]
  int v26; // [rsp+58h] [rbp-31h]
  const char *v27; // [rsp+60h] [rbp-29h]
  int v28; // [rsp+68h] [rbp-21h]
  const char *v29; // [rsp+70h] [rbp-19h]
  int v30; // [rsp+78h] [rbp-11h]
  const char *v31; // [rsp+80h] [rbp-9h]
  int v32; // [rsp+88h] [rbp-1h]
  const char *v33; // [rsp+90h] [rbp+7h]
  int v34; // [rsp+98h] [rbp+Fh]
  const char *v35; // [rsp+A0h] [rbp+17h]
  int v36; // [rsp+A8h] [rbp+1Fh]
  const char *v37; // [rsp+B0h] [rbp+27h]
  int v38; // [rsp+B8h] [rbp+2Fh]

  if ( *((_DWORD *)this + 4) == 1230206533 )
  {
    result = 0;
    v26 = 1;
    v22[0] = 0;
    v23 = "SERVICE_STOPPED";
    v25 = "SERVICE_START_PENDING";
    v27 = "SERVICE_STOP_PENDING";
    v29 = "SERVICE_RUNNING";
    v31 = "SERVICE_CONTINUE_PENDING";
    v33 = "SERVICE_PAUSE_PENDING";
    v6 = "SERVICE_UNKNOWN";
    v21 = "SERVICE_UNKNOWN";
    v35 = "SERVICE_PAUSED";
    v24 = 0;
    v28 = 1;
    v30 = 0;
    v32 = 1;
    v34 = 1;
    v36 = 0;
    v37 = "SERVICE_UNKNOWN";
    v38 = 0;
    if ( a2 && a2 != *((_DWORD *)this + 23) )
    {
      result = 1;
      *((_DWORD *)this + 23) = a2;
    }
    v7 = *((_DWORD *)this + 23);
    *((_DWORD *)this + 28) = a3;
    v8 = v22[4 * v7];
    if ( v8 )
      ++*((_DWORD *)this + 27);
    else
      *((_DWORD *)this + 27) = 0;
    if ( result || v8 )
    {
      if ( v7 >= 9 )
        v14 = "SERVICE_UNKNOWN";
      else
        v14 = *(const char **)&v22[4 * v7 - 2];
      v15 = (char *)WiaTrace_TraceLogWithSubCompTraceLevel(
                      2,
                      0,
                      "Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d",
                      v14,
                      v7,
                      a3);
      WriteDbgTraceInfoWI("SCMControlHandler::UpdateServiceStatus", v15);
      WiaTrcLib::Free((WiaTrcLib *)v15, v16);
      v17 = *((unsigned int *)this + 23);
      if ( (unsigned int)v17 < 9 )
        v6 = *(const char **)&v22[4 * v17 - 2];
      v18 = (void **)WiaTrace_TraceWithSubCompTraceLevel(
                       2,
                       0,
                       "Updating service status. CurrentState=%s, StateCode=%d, WaitHint=%d",
                       v6,
                       v17,
                       *((_DWORD *)this + 28));
      WiaTrace_ProcessTrace_Ex(v20, v19, (void *)"SCMControlHandler::UpdateServiceStatus", 4, v18);
      if ( SetServiceStatus(*((SERVICE_STATUS_HANDLE *)this + 10), (LPSERVICE_STATUS)((char *)this + 88)) )
      {
        return 0;
      }
      else
      {
        result = GetLastError();
        if ( result > 0 )
          return (unsigned __int16)result | 0x80070000;
      }
    }
  }
  else
  {
    v9 = (char *)WiaTrace_TraceLogWithSubComp(
                   1,
                   "Attempting to update service status when the SCMControlHandler has not been successfully initialized.");
    WriteDbgTraceWarningWI("SCMControlHandler::UpdateServiceStatus", v9);
    WiaTrcLib::Free((WiaTrcLib *)v9, v10);
    lpMem = (void **)WiaTrace_TraceWithSubComp(
                       1,
                       "Attempting to update service status when the SCMControlHandler has not been successfully initialized.");
    WiaTrace_ProcessTrace_Ex(v13, v12, (void *)"SCMControlHandler::UpdateServiceStatus", 2, lpMem);
    return -2147418113;
  }
  return result;
}

```

## disassembly

```asm
0x18001c8c0  push    rbp
0x18001c8c2  push    rbx
0x18001c8c3  push    rsi
0x18001c8c4  push    rdi
0x18001c8c5  push    r14
0x18001c8c7  lea     rbp, [rsp-37h]
0x18001c8cc  sub     rsp, 0C0h
0x18001c8d3  cmp     dword ptr [rcx+10h], 49537645h
0x18001c8da  mov     r10d, r8d
0x18001c8dd  mov     rdi, rcx
0x18001c8e0  mov     esi, 1
0x18001c8e5  jnz     loc_18001C9A1
0x18001c8eb  xor     eax, eax
0x18001c8ed  mov     [rbp+57h+var_88], esi
0x18001c8f0  mov     [rbp+57h+var_A8], eax
0x18001c8f3  lea     rcx, aServiceStopped; "SERVICE_STOPPED"
0x18001c8fa  mov     [rbp+57h+var_A0], rcx
0x18001c8fe  lea     rcx, aServiceStartPe; "SERVICE_START_PENDING"
0x18001c905  mov     [rbp+57h+var_90], rcx
0x18001c909  lea     rcx, aServiceStopPen; "SERVICE_STOP_PENDING"
0x18001c910  mov     [rbp+57h+var_80], rcx
0x18001c914  lea     rcx, aServiceRunning; "SERVICE_RUNNING"
0x18001c91b  mov     [rbp+57h+var_70], rcx
0x18001c91f  lea     rcx, aServiceContinu; "SERVICE_CONTINUE_PENDING"
0x18001c926  mov     [rbp+57h+var_60], rcx
0x18001c92a  lea     rcx, aServicePausePe; "SERVICE_PAUSE_PENDING"
0x18001c931  mov     [rbp+57h+var_50], rcx
0x18001c935  lea     r14, aServiceUnknown; "SERVICE_UNKNOWN"
0x18001c93c  mov     [rbp+57h+var_B0], r14
0x18001c940  lea     rcx, aServicePaused; "SERVICE_PAUSED"
0x18001c947  mov     [rbp+57h+var_40], rcx
0x18001c94b  mov     [rbp+57h+var_98], eax
0x18001c94e  mov     [rbp+57h+var_78], esi
0x18001c951  mov     [rbp+57h+var_68], eax
0x18001c954  mov     [rbp+57h+var_58], esi
0x18001c957  mov     [rbp+57h+var_48], esi
0x18001c95a  mov     [rbp+57h+var_38], eax
0x18001c95d  mov     [rbp+57h+var_30], r14
0x18001c961  mov     [rbp+57h+var_28], eax
0x18001c964  test    edx, edx
0x18001c966  jnz     loc_18001CA9A
0x18001c96c  mov     edx, [rdi+5Ch]
0x18001c96f  mov     ecx, edx
0x18001c971  mov     [rdi+70h], r10d
0x18001c975  add     rcx, rcx
0x18001c978  mov     r8d, [rbp+rcx*8+57h+var_A8]
0x18001c97d  test    r8d, r8d
0x18001c980  jnz     loc_18001CA92
0x18001c986  mov     [rdi+6Ch], r8d
0x18001c98a  test    eax, eax
0x18001c98c  jnz     short loc_18001C9F5
0x18001c98e  test    r8d, r8d
0x18001c991  jnz     short loc_18001C9F5
0x18001c993  add     rsp, 0C0h
0x18001c99a  pop     r14
0x18001c99c  pop     rdi
0x18001c99d  pop     rsi
0x18001c99e  pop     rbx
0x18001c99f  pop     rbp
0x18001c9a0  retn
0x18001c9a1  lea     rdx, aAttemptingToUp; "Attempting to update service status whe"...
0x18001c9a8  mov     ecx, esi
0x18001c9aa  call    WiaTrace_TraceLogWithSubComp
0x18001c9af  mov     rdx, rax; char *
0x18001c9b2  lea     rcx, aScmcontrolhand_6; "SCMControlHandler::UpdateServiceStatus"
0x18001c9b9  mov     rbx, rax
0x18001c9bc  call    ?WriteDbgTraceWarningWI@@YAXPEAD0ZZ; WriteDbgTraceWarningWI(char *,char *,...)
0x18001c9c1  mov     rcx, rbx; this
0x18001c9c4  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001c9c9  lea     rdx, aAttemptingToUp; "Attempting to update service status whe"...
0x18001c9d0  mov     ecx, esi
0x18001c9d2  call    WiaTrace_TraceWithSubComp
0x18001c9d7  mov     r9d, 2; int
0x18001c9dd  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001c9e2  lea     r8, aScmcontrolhand_6; "SCMControlHandler::UpdateServiceStatus"
0x18001c9e9  call    WiaTrace_ProcessTrace_Ex
0x18001c9ee  mov     eax, 8000FFFFh
0x18001c9f3  jmp     short loc_18001C993
0x18001c9f5  cmp     edx, 9
0x18001c9f8  jnb     loc_18001CAAD
0x18001c9fe  mov     r9, [rbp+rcx*8+57h+var_B0]
0x18001ca03  mov     [rsp+0E0h+var_B8], r10d
0x18001ca08  lea     r8, aUpdatingServic; "Updating service status. CurrentState=%"...
0x18001ca0f  mov     dword ptr [rsp+0E0h+lpMem], edx
0x18001ca13  xor     edx, edx
0x18001ca15  lea     ecx, [rdx+2]
0x18001ca18  call    WiaTrace_TraceLogWithSubCompTraceLevel
0x18001ca1d  mov     rdx, rax; char *
0x18001ca20  lea     rcx, aScmcontrolhand_6; "SCMControlHandler::UpdateServiceStatus"
0x18001ca27  mov     rbx, rax
0x18001ca2a  call    ?WriteDbgTraceInfoWI@@YAXPEAD0ZZ; WriteDbgTraceInfoWI(char *,char *,...)
0x18001ca2f  mov     rcx, rbx; this
0x18001ca32  call    ?Free@WiaTrcLib@@YAHPEAX@Z; WiaTrcLib::Free(void *)
0x18001ca37  mov     ecx, [rdi+5Ch]
0x18001ca3a  mov     edx, [rdi+70h]
0x18001ca3d  cmp     ecx, 9
0x18001ca40  jb      loc_18001CAD0
0x18001ca46  mov     [rsp+0E0h+var_B8], edx
0x18001ca4a  lea     r8, aUpdatingServic; "Updating service status. CurrentState=%"...
0x18001ca51  xor     edx, edx
0x18001ca53  mov     dword ptr [rsp+0E0h+lpMem], ecx
0x18001ca57  mov     r9, r14
0x18001ca5a  lea     ecx, [rdx+2]
0x18001ca5d  call    WiaTrace_TraceWithSubCompTraceLevel
0x18001ca62  mov     r9d, 4; int
0x18001ca68  mov     [rsp+0E0h+lpMem], rax; lpMem
0x18001ca6d  lea     r8, aScmcontrolhand_6; "SCMControlHandler::UpdateServiceStatus"
0x18001ca74  call    WiaTrace_ProcessTrace_Ex
0x18001ca79  mov     rcx, [rdi+50h]; hServiceStatus
0x18001ca7d  lea     rdx, [rdi+58h]; lpServiceStatus
0x18001ca81  call    cs:__imp_SetServiceStatus
0x18001ca87  test    eax, eax
0x18001ca89  jz      short loc_18001CAB5
0x18001ca8b  xor     eax, eax
0x18001ca8d  jmp     loc_18001C993
0x18001ca92  add     [rdi+6Ch], esi
0x18001ca95  jmp     loc_18001C98A
0x18001ca9a  cmp     edx, [rdi+5Ch]
0x18001ca9d  jz      loc_18001C96C
0x18001caa3  mov     eax, esi
0x18001caa5  mov     [rdi+5Ch], edx
0x18001caa8  jmp     loc_18001C96C
0x18001caad  mov     r9, r14
0x18001cab0  jmp     loc_18001CA03
0x18001cab5  call    cs:__imp_GetLastError
0x18001cabb  test    eax, eax
0x18001cabd  jle     loc_18001C993
0x18001cac3  movzx   eax, ax
0x18001cac6  or      eax, 80070000h
0x18001cacb  jmp     loc_18001C993
0x18001cad0  mov     rax, rcx
0x18001cad3  add     rax, rax
0x18001cad6  mov     r14, [rbp+rax*8+57h+var_B0]
0x18001cadb  jmp     loc_18001CA46
```
