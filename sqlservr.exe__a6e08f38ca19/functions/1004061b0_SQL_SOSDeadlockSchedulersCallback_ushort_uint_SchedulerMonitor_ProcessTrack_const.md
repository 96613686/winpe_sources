# SQL_SOSDeadlockSchedulersCallback(ushort,uint,SchedulerMonitor::ProcessTrack const *)

- ea: `0x1004061b0`
- end: `0x100406346`
- name: `?SQL_SOSDeadlockSchedulersCallback@@YAXGIPEBVProcessTrack@SchedulerMonitor@@@Z`
- size: `406`
- prototype: `void __fastcall(unsigned __int16, unsigned int, const struct SchedulerMonitor::ProcessTrack *)`
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x1004061b0`
- `0x1004403d0`

## import_xrefs

- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406297`
- `sqllang!?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z` at `0x100406297`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x1004062bb`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x100406304`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x1004062bb`
- `sqldk!?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ` at `0x100406304`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x10040623a`
- `sqldk!?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ` at `0x10040623a`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100406311`
- `sqldk!?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ` at `0x100406311`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x1004062b0`
- `sqldk!?GetIdlePercentage@CSystemTimes@@QEBAIXZ` at `0x1004062b0`

## pseudocode

```c
void __fastcall SQL_SOSDeadlockSchedulersCallback(
        unsigned __int16 a1,
        int a2,
        const struct SchedulerMonitor::ProcessTrack *a3)
{
  unsigned int v4; // ebp
  int v6; // edi
  __int64 v7; // rax
  unsigned int IdlePercentage; // ebx
  unsigned int v9; // eax
  unsigned int ProcessUtilization; // ebx
  const wchar_t *WaitString; // rax
  __int64 v12; // [rsp+20h] [rbp-68h]
  int v13; // [rsp+50h] [rbp-38h] BYREF
  __int64 v14; // [rsp+58h] [rbp-30h]
  __int64 v15; // [rsp+60h] [rbp-28h]
  __int64 v16; // [rsp+68h] [rbp-20h]
  __int64 v17; // [rsp+70h] [rbp-18h]

  v4 = a1;
  if ( *(_DWORD *)a3 == 60 * (*(_DWORD *)a3 / 0x3Cu) )
  {
    if ( a2 == 4194491 || a2 == 536872088 || a2 == 4194654 || a2 == 4194689 || (v6 = 0, a2 == 4194400) )
      v6 = 1;
    v7 = qword_10049F340;
    if ( *(char *)(qword_10049F340 + 38) < 0 || (*(_BYTE *)(qword_10049F340 + 157) & 0x10) != 0 )
      goto LABEL_16;
    if ( !v6 )
    {
      if ( !SchedulerMonitor::ProcessTrack::IsProcessStarved(a3) && !dword_1004A3644 )
      {
LABEL_15:
        dword_1004A3644 = 1;
        stackTrace(0, 0, L"Deadlocked Schedulers", 1184, 3, 0, 257, 0, 0);
LABEL_16:
        if ( v6 )
        {
          v13 = a2;
          v14 = 0;
          v16 = 0;
          v15 = 0;
          v17 = 0;
          ProcessUtilization = SchedulerMonitor::ProcessTrack::GetProcessUtilization(a3);
          WaitString = SOS_WaitInfo::GetWaitString((SOS_WaitInfo *)&v13);
          scierrlog(0x45E0u, v4, WaitString, ProcessUtilization);
        }
        else
        {
          IdlePercentage = CSystemTimes::GetIdlePercentage((const struct SchedulerMonitor::ProcessTrack *)((char *)a3 + 144));
          v9 = SchedulerMonitor::ProcessTrack::GetProcessUtilization(a3);
          LODWORD(v12) = IdlePercentage;
          scierrlog(0x45DCu, v4, 5000 * *(_DWORD *)a3 / 0x3E8u, v9, v12);
        }
        return;
      }
      v7 = qword_10049F340;
    }
    if ( (*(_BYTE *)(v7 + 157) & 0x40) == 0 )
      goto LABEL_16;
    goto LABEL_15;
  }
}

```

## disassembly

```asm
0x1004061b0  mov     r11, rsp
0x1004061b3  mov     [r11+18h], rbx
0x1004061b7  mov     [r11+20h], rbp
0x1004061bb  push    rsi
0x1004061bc  sub     rsp, 80h
0x1004061c3  mov     ebx, edx
0x1004061c5  movzx   ebp, cx
0x1004061c8  mov     eax, 88888889h
0x1004061cd  mov     rsi, r8
0x1004061d0  mul     dword ptr [r8]
0x1004061d3  shr     edx, 5
0x1004061d6  imul    eax, edx, 3Ch ; '<'
0x1004061d9  cmp     [r8], eax
0x1004061dc  jnz     loc_100406331
0x1004061e2  mov     [r11+8], rdi
0x1004061e6  mov     [r11+10h], r14
0x1004061ea  xor     r14d, r14d
0x1004061ed  cmp     ebx, 4000BBh
0x1004061f3  jz      short loc_100406218
0x1004061f5  cmp     ebx, 20000498h
0x1004061fb  jz      short loc_100406218
0x1004061fd  cmp     ebx, 40015Eh
0x100406203  jz      short loc_100406218
0x100406205  cmp     ebx, 400181h
0x10040620b  jz      short loc_100406218
0x10040620d  mov     edi, r14d
0x100406210  cmp     ebx, 400060h
0x100406216  jnz     short loc_10040621D
0x100406218  mov     edi, 1
0x10040621d  mov     rax, cs:qword_10049F340
0x100406224  cmp     [rax+26h], r14b
0x100406228  jl      short loc_10040629D
0x10040622a  test    byte ptr [rax+9Dh], 10h
0x100406231  jnz     short loc_10040629D
0x100406233  test    edi, edi
0x100406235  jnz     short loc_100406254
0x100406237  mov     rcx, rsi
0x10040623a  call    cs:__imp_?IsProcessStarved@ProcessTrack@SchedulerMonitor@@QEBAHXZ; SchedulerMonitor::ProcessTrack::IsProcessStarved(void)
0x100406240  test    eax, eax
0x100406242  jnz     short loc_10040624D
0x100406244  cmp     cs:dword_1004A3644, r14d
0x10040624b  jz      short loc_10040625D
0x10040624d  mov     rax, cs:qword_10049F340
0x100406254  test    byte ptr [rax+9Dh], 40h
0x10040625b  jz      short loc_10040629D
0x10040625d  mov     [rsp+88h+var_48], r14
0x100406262  lea     r8, aDeadlockedSche; "Deadlocked Schedulers"
0x100406269  mov     [rsp+88h+var_50], r14
0x10040626e  mov     r9d, 4A0h
0x100406274  mov     [rsp+88h+var_58], 101h
0x10040627c  xor     edx, edx
0x10040627e  mov     [rsp+88h+var_60], r14
0x100406283  xor     ecx, ecx
0x100406285  mov     dword ptr [rsp+88h+var_68], 3
0x10040628d  mov     cs:dword_1004A3644, 1
0x100406297  call    cs:__imp_?stackTrace@@YAXPEAVSOS_Task@@PEAVExecutionContext@@PEB_WKW4StackTraceClass@@PEAVCDStream@@W4WatsonBucketHint@@PEBU_GUID@@PEAVCopiedStackInfo@@@Z; stackTrace(SOS_Task *,ExecutionContext *,wchar_t const *,ulong,StackTraceClass,CDStream *,WatsonBucketHint,_GUID const *,CopiedStackInfo *)
0x10040629d  test    edi, edi
0x10040629f  mov     rdi, [rsp+88h+arg_0]
0x1004062a7  jnz     short loc_1004062E9
0x1004062a9  lea     rcx, [rsi+90h]
0x1004062b0  call    cs:__imp_?GetIdlePercentage@CSystemTimes@@QEBAIXZ; CSystemTimes::GetIdlePercentage(void)
0x1004062b6  mov     rcx, rsi
0x1004062b9  mov     ebx, eax
0x1004062bb  call    cs:__imp_?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ; SchedulerMonitor::ProcessTrack::GetProcessUtilization(void)
0x1004062c1  imul    ecx, [rsi], 1388h
0x1004062c7  mov     r9d, eax
0x1004062ca  mov     eax, 10624DD3h
0x1004062cf  mov     dword ptr [rsp+88h+var_68], ebx
0x1004062d3  mul     ecx
0x1004062d5  mov     ecx, 45DCh; unsigned int
0x1004062da  shr     edx, 6
0x1004062dd  mov     r8d, edx
0x1004062e0  mov     edx, ebp
0x1004062e2  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x1004062e7  jmp     short loc_100406329
0x1004062e9  mov     rcx, rsi
0x1004062ec  mov     [rsp+88h+var_38], ebx
0x1004062f0  mov     [rsp+88h+var_30], r14
0x1004062f5  mov     [rsp+88h+var_20], r14
0x1004062fa  mov     [rsp+88h+var_28], r14
0x1004062ff  mov     [rsp+88h+var_18], r14
0x100406304  call    cs:__imp_?GetProcessUtilization@ProcessTrack@SchedulerMonitor@@QEBAIXZ; SchedulerMonitor::ProcessTrack::GetProcessUtilization(void)
0x10040630a  lea     rcx, [rsp+88h+var_38]
0x10040630f  mov     ebx, eax
0x100406311  call    cs:__imp_?GetWaitString@SOS_WaitInfo@@QEBAPEB_WXZ; SOS_WaitInfo::GetWaitString(void)
0x100406317  mov     r9d, ebx
0x10040631a  mov     edx, ebp
0x10040631c  mov     r8, rax
0x10040631f  mov     ecx, 45E0h; unsigned int
0x100406324  call    ?scierrlog@@YAXKZZ; scierrlog(ulong,...)
0x100406329  mov     r14, [rsp+88h+arg_8]
0x100406331  lea     r11, [rsp+88h+var_8]
0x100406339  mov     rbx, [r11+20h]
0x10040633d  mov     rbp, [r11+28h]
0x100406341  mov     rsp, r11
0x100406344  pop     rsi
0x100406345  retn
```
