# EntryPointCrossPlatTask(void *)

- ea: `0x100439f60`
- end: `0x10043a13e`
- name: `?EntryPointCrossPlatTask@@YAPEAXPEAX@Z`
- size: `478`
- prototype: `void *__fastcall(void *)`
- caller_count: `0`
- callee_count: `6`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x100401010`
- `0x1004010b0`
- `0x1004095e0`
- `0x100439f60`
- `0x10043a150`
- `0x10044edd0`

## import_xrefs

- `sqlmin!?WaitForDone@StartupDependencies@@SAXW4Components@1@@Z` at `0x100439fcb`
- `sqlmin!?WaitForDone@StartupDependencies@@SAXW4Components@1@@Z` at `0x100439fcb`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a108`
- `sqldk!?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z` at `0x10043a108`
- `sqldk!SystemThread_TlsOffset` at `0x10043a0ef`
- `sqldk!SystemThread_TlsIndex` at `0x10043a0e6`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10043a11e`
- `sqldk!?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z` at `0x10043a11e`
- `sqldk!?hdl_prntbackout@@YAHHHHHPEAD@Z` at `0x100439f87`
- `sqldk!?ex_raisecontrol@@YAHVSQLError@@ZZ` at `0x10043a09c`
- `sqldk!?ex_raisecontrol@@YAHVSQLError@@ZZ` at `0x10043a09c`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x10043a03d`
- `sqldk!?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z` at `0x10043a03d`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void *__fastcall EntryPointCrossPlatTask(__int64 *a1)
{
  __int64 v2; // rax
  char v3; // bl
  __int64 v4; // rbx
  __int64 v5; // rcx
  void *result; // rax
  __int128 v7; // [rsp+38h] [rbp-F0h] BYREF
  int v8; // [rsp+48h] [rbp-E0h]
  __int64 v9; // [rsp+50h] [rbp-D8h] BYREF
  int v10; // [rsp+58h] [rbp-D0h]
  __int16 v11; // [rsp+5Ch] [rbp-CCh]
  __int64 v12; // [rsp+60h] [rbp-C8h]
  __int128 v13; // [rsp+70h] [rbp-B8h] BYREF
  int v14; // [rsp+80h] [rbp-A8h]
  int v15; // [rsp+90h] [rbp-98h] BYREF
  __int64 v16; // [rsp+98h] [rbp-90h]
  __int64 v17; // [rsp+A0h] [rbp-88h]
  __int64 v18; // [rsp+A8h] [rbp-80h]
  __int64 v19; // [rsp+B0h] [rbp-78h]
  __int64 v20; // [rsp+B8h] [rbp-70h]
  __int64 v21; // [rsp+C0h] [rbp-68h]
  __m128i si128; // [rsp+C8h] [rbp-60h]
  int v23; // [rsp+D8h] [rbp-50h]
  _BYTE v24[24]; // [rsp+E0h] [rbp-48h] BYREF
  _BYTE v25[40]; // [rsp+F8h] [rbp-30h] BYREF

  v20 = -2;
  try
  {
    ExcHandler::ExcHandler((ExcHandler *)v25, 0, 0, 0, hdl_prntbackout, 0);
    v2 = *a1;
    v9 = 0;
    v10 = 0;
    v11 = 0;
    v12 = v2;
    CAutoSetupExecContextsForInternalTasks::Setup(&v9, 0, 0);
    StartupDependencies::WaitForDone(11);
    v3 = 0;
    while ( !v3 )
    {
      ExecuteSqlBatches((unsigned int *)&v7, (__int64)a1);
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      v23 = 0;
      if ( (_DWORD)v7 )
      {
        if ( (int)v7 / 100 == 12 && (_DWORD)v7 == 1205 )
        {
          SOS_Task::ResetAbort(0x7FFFFFFF);
          v15 = 4195594;
          v16 = 0;
          v18 = 0;
          v17 = 0;
          v19 = 0;
          SOS_Task::Sleep(0x64u, (const struct SOS_WaitInfo *)&v15);
        }
        else
        {
          v13 = v7;
          v14 = v8;
          ex_raisecontrol(&v13);
        }
      }
      else
      {
        v3 = 1;
      }
    }
    if ( v9 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v9 + 16LL))(v9, 0);
    if ( v9 )
      (**(void (__fastcall ***)(__int64, __int64))v9)(v9, 1);
    ExcHandler::~ExcHandler((ExcHandler *)v25);
  }
  catch ( SQLError v24 )
  {
    try
    {
      ExceptionBackout::ExceptionBackout((ExceptionBackout *)&v7, (const struct SQLError *)v24);
      scierrlog(0xC308u);
      SQLExit(378);
      v21 = 0;
      ExceptionBackout::~ExceptionBackout((ExceptionBackout *)&v7);
    }
    catch ( ShortStackException )
    {
      goto LABEL_14;
    }
LABEL_18:
    result = 0;
  }
LABEL_14:
  v4 = *((_QWORD *)NtCurrentTeb()->ThreadLocalStoragePointer + SystemThread_TlsIndex) + SystemThread_TlsOffset;
  v5 = *(_QWORD *)(v4 + 256);
  if ( !v5 )
  {
    SystemThread::MakeMiniSOSThread(0);
    v5 = *(_QWORD *)(v4 + 256);
  }
  if ( !*(_DWORD *)(v5 + 556) )
    goto LABEL_18;
  ExceptionPostCatchActions((struct Worker *)v5);
  goto LABEL_18;
}

```

## disassembly

```asm
0x100439f60  mov     r11, rsp
0x100439f63  push    rdi
0x100439f64  sub     rsp, 120h
0x100439f6b  mov     qword ptr [r11-70h], 0FFFFFFFFFFFFFFFEh
0x100439f73  mov     [r11+8], rbx
0x100439f77  mov     [r11+10h], rsi
0x100439f7b  mov     rdi, rcx
0x100439f7e  xor     edx, edx; unsigned __int16
0x100439f80  xor     esi, esi
0x100439f82  mov     [rsp+128h+var_100], rsi; struct Worker *
0x100439f87  mov     rax, cs:__imp_?hdl_prntbackout@@YAHHHHHPEAD@Z; hdl_prntbackout(int,int,int,int,char *)
0x100439f8e  mov     [rsp+128h+var_108], rax; int (*)(int, int, int, int, char *)
0x100439f93  xor     r9d, r9d; unsigned __int8
0x100439f96  xor     r8d, r8d; unsigned __int8
0x100439f99  lea     rcx, [r11-30h]; this
0x100439f9d  call    ??0ExcHandler@@QEAA@GEEP6AHHHHHPEAD@ZPEAVWorker@@@Z; ExcHandler::ExcHandler(ushort,uchar,uchar,int (*)(int,int,int,int,char *),Worker *)
0x100439fa2  nop
0x100439fa3  mov     rax, [rdi]
0x100439fa6  mov     [rsp+128h+var_D8], rsi
0x100439fab  mov     [rsp+128h+var_D0], esi
0x100439faf  mov     [rsp+128h+var_CC], si
0x100439fb4  mov     [rsp+128h+var_C8], rax
0x100439fb9  xor     r8d, r8d
0x100439fbc  xor     edx, edx
0x100439fbe  lea     rcx, [rsp+128h+var_D8]
0x100439fc3  call    ?Setup@CAutoSetupExecContextsForInternalTasks@@QEAAXW4EStartupErrorHandling@1@PEAVXactWorkspace@@@Z; CAutoSetupExecContextsForInternalTasks::Setup(CAutoSetupExecContextsForInternalTasks::EStartupErrorHandling,XactWorkspace *)
0x100439fc8  lea     ecx, [rsi+0Bh]
0x100439fcb  call    cs:__imp_?WaitForDone@StartupDependencies@@SAXW4Components@1@@Z; StartupDependencies::WaitForDone(StartupDependencies::Components)
0x100439fd1  xor     bl, bl
0x100439fd3  mov     [rsp+128h+var_F8], bl
0x100439fd7  test    bl, bl
0x100439fd9  jnz     loc_10043A0A7
0x100439fdf  mov     rdx, rdi
0x100439fe2  lea     rcx, [rsp+128h+var_F0]
0x100439fe7  call    ?ExecuteSqlBatches@@YA?AVSQLError@@PEAUTaskParameters@@@Z; ExecuteSqlBatches(TaskParameters *)
0x100439fec  movdqa  xmm0, cs:__xmm@00000000ffffffff0000000000000000
0x100439ff4  movdqu  [rsp+128h+var_60], xmm0
0x100439ffd  mov     [rsp+128h+var_50], esi
0x10043a004  mov     ecx, dword ptr [rsp+128h+var_F0]
0x10043a008  test    ecx, ecx
0x10043a00a  jnz     short loc_10043A017
0x10043a00c  mov     bl, 1
0x10043a00e  mov     [rsp+128h+var_F8], bl
0x10043a012  jmp     loc_10043A0A2
0x10043a017  mov     eax, 51EB851Fh
0x10043a01c  imul    ecx
0x10043a01e  sar     edx, 5
0x10043a021  mov     eax, edx
0x10043a023  shr     eax, 1Fh
0x10043a026  add     edx, eax
0x10043a028  cmp     edx, 0Ch
0x10043a02b  jnz     short loc_10043A082
0x10043a02d  lea     eax, [rcx-4B0h]
0x10043a033  cmp     eax, 5
0x10043a036  jnz     short loc_10043A082
0x10043a038  mov     ecx, 7FFFFFFFh
0x10043a03d  call    cs:__imp_?ResetAbort@SOS_Task@@SAXW4TASK_ABORT_TYPE@1@@Z; SOS_Task::ResetAbort(SOS_Task::TASK_ABORT_TYPE)
0x10043a043  mov     [rsp+128h+var_98], 40050Ah
0x10043a04e  mov     [rsp+128h+var_90], rsi
0x10043a056  mov     [rsp+128h+var_80], rsi
0x10043a05e  mov     [rsp+128h+var_88], rsi
0x10043a066  mov     [rsp+128h+var_78], rsi
0x10043a06e  lea     rdx, [rsp+128h+var_98]
0x10043a076  mov     ecx, 64h ; 'd'
0x10043a07b  call    ?Sleep@SOS_Task@@SA?AW4SOS_RESULT@@KPEBVSOS_WaitInfo@@@Z; SOS_Task::Sleep(ulong,SOS_WaitInfo const *)
0x10043a080  jmp     short loc_10043A0A2
0x10043a082  movups  xmm0, [rsp+128h+var_F0]
0x10043a087  movaps  [rsp+128h+var_B8], xmm0
0x10043a08c  mov     eax, [rsp+128h+var_E0]
0x10043a090  mov     [rsp+128h+var_A8], eax
0x10043a097  lea     rcx, [rsp+128h+var_B8]
0x10043a09c  call    cs:__imp_?ex_raisecontrol@@YAHVSQLError@@ZZ; ex_raisecontrol(SQLError,...)
0x10043a0a2  jmp     loc_100439FD7
0x10043a0a7  mov     rcx, [rsp+128h+var_D8]
0x10043a0ac  test    rcx, rcx
0x10043a0af  jz      short loc_10043A0BA
0x10043a0b1  mov     rax, [rcx]
0x10043a0b4  xor     edx, edx
0x10043a0b6  call    qword ptr [rax+10h]
0x10043a0b9  nop
0x10043a0ba  mov     rcx, [rsp+128h+var_D8]
0x10043a0bf  test    rcx, rcx
0x10043a0c2  jz      short loc_10043A0CF
0x10043a0c4  mov     rax, [rcx]
0x10043a0c7  mov     edx, 1
0x10043a0cc  call    qword ptr [rax]
0x10043a0ce  nop
0x10043a0cf  lea     rcx, [rsp+128h+var_30]; this
0x10043a0d7  call    ??1ExcHandler@@QEAA@XZ; ExcHandler::~ExcHandler(void)
0x10043a0dc  nop
0x10043a0dd  mov     rdx, gs:58h
0x10043a0e6  mov     rax, cs:__imp_SystemThread_TlsIndex
0x10043a0ed  mov     ecx, [rax]
0x10043a0ef  mov     rax, cs:__imp_SystemThread_TlsOffset
0x10043a0f6  mov     ebx, [rax]
0x10043a0f8  add     rbx, [rdx+rcx*8]
0x10043a0fc  mov     rcx, [rbx+100h]
0x10043a103  test    rcx, rcx
0x10043a106  jnz     short loc_10043A115
0x10043a108  call    cs:__imp_?MakeMiniSOSThread@SystemThread@@SAXPEAX@Z; SystemThread::MakeMiniSOSThread(void *)
0x10043a10e  mov     rcx, [rbx+100h]
0x10043a115  cmp     dword ptr [rcx+22Ch], 0
0x10043a11c  jz      short loc_10043A124
0x10043a11e  call    cs:__imp_?ExceptionPostCatchActions@@YAXPEAVWorker@@@Z; ExceptionPostCatchActions(Worker *)
0x10043a124  xor     eax, eax
0x10043a126  lea     r11, [rsp+128h+var_8]
0x10043a12e  mov     rbx, [r11+10h]
0x10043a132  mov     rsi, [r11+18h]
0x10043a136  mov     rsp, r11
0x10043a139  pop     rdi
0x10043a13a  retn
0x10043a13b  jmp     short loc_10043A124
```
