# RStartServiceW

- ea: `0x14002ab00`
- end: `0x14002add5`
- name: `RStartServiceW`
- size: `725`
- prototype: `__int64 __fastcall(void *, unsigned int, struct _STRING_PTRSW *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x14002a920`

## callees

- `0x140003e54`
- `0x140004c58`
- `0x1400083f0`
- `0x14000ac50`
- `0x14001761c`
- `0x140019014`
- `0x14001f99c`
- `0x140022c34`
- `0x140025a50`
- `0x14002ab00`
- `0x140043dc4`
- `0x140081b6c`
- `0x1400835d4`

## import_xrefs

- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14002ac5b`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x14002ac5b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ad97`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x14002ad97`
- `ntdll!RtlAreAllAccessesGranted` at `0x14002abc7`
- `ntdll!RtlAreAllAccessesGranted` at `0x14002abc7`
- `ntdll!RtlFreeHeap` at `0x14002adb4`
- `ntdll!RtlFreeHeap` at `0x14002adb4`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002ad4c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x14002ad4c`

## pseudocode

```c
__int64 __fastcall RStartServiceW(ACCESS_MASK *a1, unsigned int a2, struct _STRING_PTRSW *a3)
{
  struct _TOKEN_USER *v3; // r14
  unsigned int started; // ebx
  __int64 v8; // r9
  __int64 v10; // rdi
  char v11; // al
  unsigned int TriggerStartFlag; // eax
  int ClientSid; // eax
  unsigned int v14; // [rsp+30h] [rbp-20h] BYREF
  struct _TOKEN_USER *v15; // [rsp+38h] [rbp-18h] BYREF
  LPWSTR StringSid; // [rsp+40h] [rbp-10h] BYREF
  unsigned int Pid; // [rsp+98h] [rbp+48h] BYREF

  v3 = 0;
  Pid = 0;
  v15 = 0;
  StringSid = 0;
  v14 = 0;
  ScSetTcpKeepalive();
  if ( ScShutdownInProgress )
  {
    started = 1115;
LABEL_45:
    if ( StringSid )
      LocalFree(StringSid);
    if ( v3 )
      RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v3);
    return started;
  }
  if ( !(unsigned int)ScIsValidServiceHandle(a1) )
  {
    started = 6;
    goto LABEL_45;
  }
  if ( !a2 )
  {
LABEL_14:
    if ( RtlAreAllAccessesGranted(a1[2], 0x10u) )
    {
      v10 = *((_QWORD *)a1 + 2);
      if ( *(_DWORD *)(v10 + 36) == 4 )
      {
        started = 1058;
      }
      else if ( (*(_DWORD *)(v10 + 52) & 1) != 0 )
      {
        CServiceRecord::LogPidsWithOpenHandles((CServiceRecord *)v10);
        started = 1072;
      }
      else if ( (*(_DWORD *)(v10 + 80) & 0x400) != 0 )
      {
        started = 50;
      }
      else
      {
        if ( I_RpcBindingInqLocalClientPID(0, &Pid) )
        {
          v11 = 0;
          Pid = 0;
        }
        else
        {
          v11 = Pid;
        }
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        {
          WPP_SF_Sd(
            WPP_GLOBAL_Control->StubInfo,
            12,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *(_QWORD *)(v10 + 56),
            v11);
        }
        started = CServiceRecord::WaitForServiceStart((CServiceRecord *)v10);
        if ( !started )
        {
          TriggerStartFlag = ScGetTriggerStartFlag(a2, a3, Pid, &v14);
          started = ScStartServiceAndDependencies((struct CServiceRecord *)v10, a2, a3, v14, TriggerStartFlag | 8, 0);
        }
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
        {
          WPP_SF_SLd(
            WPP_GLOBAL_Control->StubInfo,
            13,
            (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
            *(_QWORD *)(v10 + 56),
            started,
            *(_DWORD *)(v10 + 172));
        }
        if ( !started )
        {
          if ( !*(_DWORD *)(v10 + 172) )
          {
            ClientSid = ScGetClientSid((PVOID *)&v15);
            v3 = v15;
            if ( !ClientSid
              && ConvertSidToStringSidW(v15->User.Sid, &StringSid)
              && WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 4) != 0 )
            {
              WPP_SF_SS(
                WPP_GLOBAL_Control->StubInfo,
                14,
                (unsigned int)WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids,
                *(_QWORD *)(v10 + 56),
                (__int64)StringSid);
            }
          }
          started = *(_DWORD *)(v10 + 172);
        }
      }
    }
    else
    {
      started = 5;
    }
    goto LABEL_45;
  }
  if ( !a3 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_(WPP_GLOBAL_Control->StubInfo, 10, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids);
    started = 87;
    goto LABEL_45;
  }
  v8 = 0;
  while ( *((_QWORD *)a3 + v8) )
  {
    v8 = (unsigned int)(v8 + 1);
    if ( (unsigned int)v8 >= a2 )
      goto LABEL_14;
  }
  if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 11, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids, v8);
  return 87;
}

```

## disassembly

```asm
0x14002ab00  mov     [rsp-28h+arg_0], rbx
0x14002ab05  mov     [rsp-28h+arg_8], rsi
0x14002ab0a  push    rbp
0x14002ab0b  push    rdi
0x14002ab0c  push    r12
0x14002ab0e  push    r14
0x14002ab10  push    r15
0x14002ab12  mov     rbp, rsp
0x14002ab15  sub     rsp, 50h
0x14002ab19  xor     r14d, r14d
0x14002ab1c  mov     [rbp+Pid], 0
0x14002ab23  mov     [rbp+var_18], r14
0x14002ab27  mov     r12, r8
0x14002ab2a  mov     [rbp+StringSid], r14
0x14002ab2e  mov     r15d, edx
0x14002ab31  mov     rdi, rcx
0x14002ab34  mov     [rbp+var_20], 0
0x14002ab3b  call    ?ScSetTcpKeepalive@@YAXXZ; ScSetTcpKeepalive(void)
0x14002ab40  cmp     cs:?ScShutdownInProgress@@3KA, r14d; ulong ScShutdownInProgress
0x14002ab47  jz      short loc_14002AB53
0x14002ab49  mov     ebx, 45Bh
0x14002ab4e  jmp     loc_14002AD8E
0x14002ab53  mov     rcx, rdi; void *
0x14002ab56  call    ?ScIsValidServiceHandle@@YAHPEAX@Z; ScIsValidServiceHandle(void *)
0x14002ab5b  test    eax, eax
0x14002ab5d  jnz     short loc_14002AB67
0x14002ab5f  lea     ebx, [rax+6]
0x14002ab62  jmp     loc_14002AD8E
0x14002ab67  test    r15d, r15d
0x14002ab6a  jz      short loc_14002ABBF
0x14002ab6c  test    r12, r12
0x14002ab6f  jnz     short loc_14002ABA9
0x14002ab71  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab78  lea     rsi, WPP_GLOBAL_Control
0x14002ab7f  cmp     rcx, rsi
0x14002ab82  jz      short loc_14002AB9F
0x14002ab84  test    byte ptr [rcx+1Ch], 1
0x14002ab88  jz      short loc_14002AB9F
0x14002ab8a  mov     rcx, [rcx+10h]
0x14002ab8e  lea     edx, [r12+0Ah]
0x14002ab93  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14002ab9a  call    WPP_SF_
0x14002ab9f  mov     ebx, 57h ; 'W'
0x14002aba4  jmp     loc_14002AD8E
0x14002aba9  xor     r9d, r9d
0x14002abac  test    r15d, r15d
0x14002abaf  jz      short loc_14002ABBF
0x14002abb1  cmp     [r12+r9*8], r14
0x14002abb5  jz      short loc_14002ABDB
0x14002abb7  inc     r9d
0x14002abba  cmp     r9d, r15d
0x14002abbd  jb      short loc_14002ABB1
0x14002abbf  mov     ecx, [rdi+8]; GrantedAccess
0x14002abc2  mov     edx, 10h; DesiredAccess
0x14002abc7  call    cs:__imp_RtlAreAllAccessesGranted
0x14002abcd  test    al, al
0x14002abcf  jnz     short loc_14002AC13
0x14002abd1  mov     ebx, 5
0x14002abd6  jmp     loc_14002AD8E
0x14002abdb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002abe2  lea     rsi, WPP_GLOBAL_Control
0x14002abe9  cmp     rcx, rsi
0x14002abec  jz      short loc_14002AC09
0x14002abee  test    byte ptr [rcx+1Ch], 1
0x14002abf2  jz      short loc_14002AC09
0x14002abf4  mov     rcx, [rcx+10h]
0x14002abf8  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14002abff  mov     edx, 0Bh
0x14002ac04  call    WPP_SF_d
0x14002ac09  mov     eax, 57h ; 'W'
0x14002ac0e  jmp     loc_14002ADBC
0x14002ac13  mov     rdi, [rdi+10h]
0x14002ac17  mov     eax, [rdi+24h]
0x14002ac1a  cmp     eax, 4
0x14002ac1d  jnz     short loc_14002AC29
0x14002ac1f  mov     ebx, 422h
0x14002ac24  jmp     loc_14002AD8E
0x14002ac29  mov     eax, [rdi+34h]
0x14002ac2c  test    al, 1
0x14002ac2e  jz      short loc_14002AC42
0x14002ac30  mov     rcx, rdi; this
0x14002ac33  call    ?LogPidsWithOpenHandles@CServiceRecord@@QEAAXXZ; CServiceRecord::LogPidsWithOpenHandles(void)
0x14002ac38  mov     ebx, 430h
0x14002ac3d  jmp     loc_14002AD8E
0x14002ac42  test    dword ptr [rdi+50h], 400h
0x14002ac49  jz      short loc_14002AC55
0x14002ac4b  mov     ebx, 32h ; '2'
0x14002ac50  jmp     loc_14002AD8E
0x14002ac55  lea     rdx, [rbp+Pid]; Pid
0x14002ac59  xor     ecx, ecx; Binding
0x14002ac5b  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x14002ac61  test    eax, eax
0x14002ac63  jz      short loc_14002AC6C
0x14002ac65  xor     eax, eax
0x14002ac67  mov     [rbp+Pid], eax
0x14002ac6a  jmp     short loc_14002AC6F
0x14002ac6c  mov     eax, [rbp+Pid]
0x14002ac6f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac76  lea     rsi, WPP_GLOBAL_Control
0x14002ac7d  cmp     rcx, rsi
0x14002ac80  jz      short loc_14002ACA5
0x14002ac82  test    byte ptr [rcx+1Ch], 4
0x14002ac86  jz      short loc_14002ACA5
0x14002ac88  mov     r9, [rdi+38h]
0x14002ac8c  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14002ac93  mov     rcx, [rcx+10h]
0x14002ac97  mov     edx, 0Ch
0x14002ac9c  mov     [rsp+50h+var_30], eax
0x14002aca0  call    WPP_SF_Sd
0x14002aca5  mov     rcx, rdi; this
0x14002aca8  call    ?WaitForServiceStart@CServiceRecord@@QEAAKXZ; CServiceRecord::WaitForServiceStart(void)
0x14002acad  mov     ebx, eax
0x14002acaf  test    eax, eax
0x14002acb1  jnz     short loc_14002ACE6
0x14002acb3  mov     r8d, [rbp+Pid]; unsigned int
0x14002acb7  lea     r9, [rbp+var_20]; unsigned int *
0x14002acbb  mov     rdx, r12; struct _STRING_PTRSW *
0x14002acbe  mov     ecx, r15d; unsigned int
0x14002acc1  call    ?ScGetTriggerStartFlag@@YAKKPEAU_STRING_PTRSW@@KPEAK@Z; ScGetTriggerStartFlag(ulong,_STRING_PTRSW *,ulong,ulong *)
0x14002acc6  mov     r9d, [rbp+var_20]; unsigned int
0x14002acca  or      eax, 8
0x14002accd  mov     [rsp+50h+var_28], r14; struct CServiceRecord *
0x14002acd2  mov     r8, r12; struct _STRING_PTRSW *
0x14002acd5  mov     edx, r15d; unsigned int
0x14002acd8  mov     [rsp+50h+var_30], eax; unsigned int
0x14002acdc  mov     rcx, rdi; this
0x14002acdf  call    ?ScStartServiceAndDependencies@@YAKPEAVCServiceRecord@@KPEAU_STRING_PTRSW@@KK0@Z; ScStartServiceAndDependencies(CServiceRecord *,ulong,_STRING_PTRSW *,ulong,ulong,CServiceRecord *)
0x14002ace4  mov     ebx, eax
0x14002ace6  mov     rax, cs:WPP_GLOBAL_Control
0x14002aced  cmp     rax, rsi
0x14002acf0  jz      short loc_14002AD26
0x14002acf2  test    byte ptr [rax+1Ch], 4
0x14002acf6  jz      short loc_14002AD26
0x14002acf8  mov     eax, [rdi+0ACh]
0x14002acfe  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14002ad05  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad0c  mov     edx, 0Dh
0x14002ad11  mov     r9, [rdi+38h]
0x14002ad15  mov     dword ptr [rsp+50h+var_28], eax
0x14002ad19  mov     [rsp+50h+var_30], ebx
0x14002ad1d  mov     rcx, [rcx+10h]
0x14002ad21  call    WPP_SF_SLd
0x14002ad26  test    ebx, ebx
0x14002ad28  jnz     short loc_14002AD8E
0x14002ad2a  mov     eax, [rdi+0ACh]
0x14002ad30  test    eax, eax
0x14002ad32  jnz     short loc_14002AD88
0x14002ad34  lea     rcx, [rbp+var_18]; struct _TOKEN_USER **
0x14002ad38  call    ?ScGetClientSid@@YAKPEAPEAU_TOKEN_USER@@@Z; ScGetClientSid(_TOKEN_USER * *)
0x14002ad3d  mov     r14, [rbp+var_18]
0x14002ad41  test    eax, eax
0x14002ad43  jnz     short loc_14002AD88
0x14002ad45  mov     rcx, [r14]; Sid
0x14002ad48  lea     rdx, [rbp+StringSid]; StringSid
0x14002ad4c  call    cs:__imp_ConvertSidToStringSidW
0x14002ad52  test    eax, eax
0x14002ad54  jz      short loc_14002AD88
0x14002ad56  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad5d  cmp     rcx, rsi
0x14002ad60  jz      short loc_14002AD88
0x14002ad62  test    byte ptr [rcx+1Ch], 4
0x14002ad66  jz      short loc_14002AD88
0x14002ad68  mov     rax, [rbp+StringSid]
0x14002ad6c  lea     edx, [rbx+0Eh]
0x14002ad6f  mov     r9, [rdi+38h]
0x14002ad73  lea     r8, WPP_91aecf8c7c2c39cfbebddfe21418e6fb_Traceguids
0x14002ad7a  mov     rcx, [rcx+10h]
0x14002ad7e  mov     qword ptr [rsp+50h+var_30], rax
0x14002ad83  call    WPP_SF_SS
0x14002ad88  mov     ebx, [rdi+0ACh]
0x14002ad8e  mov     rcx, [rbp+StringSid]; hMem
0x14002ad92  test    rcx, rcx
0x14002ad95  jz      short loc_14002AD9D
0x14002ad97  call    cs:__imp_LocalFree
0x14002ad9d  test    r14, r14
0x14002ada0  jz      short loc_14002ADBA
0x14002ada2  mov     rcx, gs:60h
0x14002adab  mov     r8, r14; P
0x14002adae  xor     edx, edx; Flags
0x14002adb0  mov     rcx, [rcx+30h]; HeapHandle
0x14002adb4  call    cs:__imp_RtlFreeHeap
0x14002adba  mov     eax, ebx
0x14002adbc  lea     r11, [rsp+50h+var_s0]
0x14002adc1  mov     rbx, [r11+30h]
0x14002adc5  mov     rsi, [r11+38h]
0x14002adc9  mov     rsp, r11
0x14002adcc  pop     r15
0x14002adce  pop     r14
0x14002add0  pop     r12
0x14002add2  pop     rdi
0x14002add3  pop     rbp
0x14002add4  retn
```
