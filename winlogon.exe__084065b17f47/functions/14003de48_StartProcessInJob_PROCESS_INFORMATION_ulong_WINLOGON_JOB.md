# StartProcessInJob(_PROCESS_INFORMATION *,ulong,_WINLOGON_JOB * *)

- ea: `0x14003de48`
- end: `0x14003e121`
- name: `?StartProcessInJob@@YAKPEAU_PROCESS_INFORMATION@@KPEAPEAU_WINLOGON_JOB@@@Z`
- size: `729`
- prototype: `unsigned int(struct _PROCESS_INFORMATION *, unsigned int, struct _WINLOGON_JOB **)`
- caller_count: `6`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x140006c3c`
- `0x14003a054`
- `0x140059928`
- `0x1400727a0`
- `0x140076178`
- `0x14007916c`

## callees

- `0x1400057f4`
- `0x14000d4e0`
- `0x1400198e0`
- `0x14001a200`
- `0x140036074`
- `0x14003de48`
- `0x14003e128`
- `0x140053720`
- `0x14005fe8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dfbc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df10`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003df58`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003dfbc`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14003e06b`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x14003e06b`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003dff1`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x14003dff1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e053`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x14003ded3`
- `api-ms-win-security-base-l1-1-0!AllocateLocallyUniqueId` at `0x14003ded3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003df28`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003df28`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14003dfb2`
- `api-ms-win-core-job-l2-1-0!AssignProcessToJobObject` at `0x14003dfb2`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x14003df01`
- `api-ms-win-core-job-l2-1-0!CreateJobObjectW` at `0x14003df01`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14003e044`
- `api-ms-win-core-threadpool-legacy-l1-1-0!UnregisterWaitEx` at `0x14003e044`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x14003df4e`
- `api-ms-win-core-kernel32-legacy-l1-1-0!RegisterWaitForSingleObject` at `0x14003df4e`

## pseudocode

```c
__int64 __fastcall StartProcessInJob(struct _PROCESS_INFORMATION *a1, ULONG a2, struct _LUID **a3)
{
  struct _LUID *v6; // rdi
  int v7; // r13d
  __int64 v8; // r8
  int v9; // r15d
  DWORD LastError; // ebx
  struct _LUID *v11; // rax
  HANDLE JobObjectW; // rax
  DWORD v13; // eax
  CUser *v14; // rcx
  __int64 v15; // rdx
  void *v16; // rcx
  struct _LIST_ENTRY *Flink; // rax
  struct _LUID *v19; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v20; // [rsp+48h] [rbp-D0h]
  WCHAR Name[64]; // [rsp+50h] [rbp-C8h] BYREF

  v6 = *a3;
  v19 = *a3;
  v7 = 0;
  JobManagerpLock();
  v9 = 1;
  LODWORD(v20) = 1;
  if ( !JobManagerIsStarted )
  {
    LastError = 1115;
    goto LABEL_22;
  }
  if ( v6 )
    goto LABEL_43;
  v11 = (struct _LUID *)WLAlloc(0x40u);
  v6 = v11;
  v19 = v11;
  if ( !v11 )
  {
    LastError = 14;
    goto LABEL_22;
  }
  v7 = 1;
  HIDWORD(v20) = 1;
  AllocateLocallyUniqueId(v11 + 2);
  StringCchPrintfW(Name, 0x40u, L"Winlogon Job %x-%x", (unsigned int)v6[2].HighPart, v6[2].LowPart);
  JobObjectW = CreateJobObjectW(0, Name);
  v6[3] = (struct _LUID)JobObjectW;
  if ( !JobObjectW )
    goto LABEL_7;
  if ( !a2
    || (v6[7].LowPart = a2,
        v6[7].LowPart += GetTickCount(),
        RegisterWaitForSingleObject((PHANDLE)&v6[5], a1->hProcess, JobManagerCallback, v6, a2, 8u)) )
  {
LABEL_43:
    if ( AssignProcessToJobObject(*(HANDLE *)&v6[3], a1->hProcess) )
    {
      if ( ResumeThread(a1->hThread) == -1 )
      {
LABEL_7:
        LastError = GetLastError();
        goto LABEL_22;
      }
      v6[6].HighPart = 1;
      v6[4] = (struct _LUID)a1->hProcess;
      a1->hProcess = 0;
      *a3 = v6;
      LastError = 0;
    }
    else
    {
      v13 = GetLastError();
      LastError = v13;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
      {
        v15 = 28;
        goto LABEL_14;
      }
    }
  }
  else
  {
    v13 = GetLastError();
    LastError = v13;
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v15 = 27;
LABEL_14:
      WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_0dafbddec43b3b8d75685e9f611780a0_Traceguids, v13);
    }
  }
LABEL_22:
  if ( LastError )
  {
    if ( v6 && v7 )
    {
      if ( v6[5] )
      {
        JobManagerpUnlock();
        v9 = 0;
        UnregisterWaitEx(*(HANDLE *)&v6[5], (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
      v16 = (void *)v6[3];
      if ( v16 )
        CloseHandle(v16);
      UHHeapFree((void **)&v19);
    }
    TerminateProcess(a1->hProcess, 5u);
  }
  else if ( v7 )
  {
    Flink = JobManagerList.Flink;
    if ( JobManagerList.Flink->Blink != &JobManagerList )
      __fastfail(3u);
    *v6 = (struct _LUID)JobManagerList.Flink;
    v6[1] = (struct _LUID)&JobManagerList;
    Flink->Blink = (struct _LIST_ENTRY *)v6;
    JobManagerList.Flink = (struct _LIST_ENTRY *)v6;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x200) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_DDqqD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        29,
        v8,
        v6[2].LowPart,
        v6[2].HighPart,
        *(_QWORD *)&v6[3],
        *(_QWORD *)&v6[4],
        v6[6].LowPart,
        v19,
        v20);
    }
  }
  if ( v9 )
    JobManagerpUnlock();
  return LastError;
}

```

## disassembly

```asm
0x14003de48  push    rbx
0x14003de4a  push    rsi
0x14003de4b  push    rdi
0x14003de4c  push    r12
0x14003de4e  push    r13
0x14003de50  push    r14
0x14003de52  push    r15
0x14003de54  sub     rsp, 0E0h
0x14003de5b  mov     rax, cs:__security_cookie
0x14003de62  xor     rax, rsp
0x14003de65  mov     [rsp+118h+var_48], rax
0x14003de6d  mov     r12, r8
0x14003de70  mov     esi, edx
0x14003de72  mov     r14, rcx
0x14003de75  mov     rdi, [r8]
0x14003de78  mov     [rsp+118h+var_D8], rdi
0x14003de7d  xor     r13d, r13d
0x14003de80  call    ?JobManagerpLock@@YAKXZ; JobManagerpLock(void)
0x14003de85  lea     r15d, [r13+1]
0x14003de89  mov     [rsp+118h+var_D0], r15d
0x14003de8e  cmp     cs:?JobManagerIsStarted@@3HA, r13d; int JobManagerIsStarted
0x14003de95  jnz     short loc_14003DEA1
0x14003de97  mov     ebx, 45Bh
0x14003de9c  jmp     loc_14003E018
0x14003dea1  test    rdi, rdi
0x14003dea4  jnz     loc_14003DFA8
0x14003deaa  lea     ecx, [rdi+40h]; unsigned __int64
0x14003dead  call    ?WLAlloc@@YAPEAX_K@Z; WLAlloc(unsigned __int64)
0x14003deb2  mov     rdi, rax
0x14003deb5  mov     [rsp+118h+var_D8], rax
0x14003deba  test    rax, rax
0x14003debd  jnz     short loc_14003DEC7
0x14003debf  lea     ebx, [rax+0Eh]
0x14003dec2  jmp     loc_14003E018
0x14003dec7  mov     r13d, r15d
0x14003deca  mov     [rsp+118h+var_CC], r15d
0x14003decf  lea     rcx, [rax+10h]; Luid
0x14003ded3  call    cs:__imp_AllocateLocallyUniqueId
0x14003ded9  mov     eax, [rdi+10h]
0x14003dedc  mov     [rsp+118h+dwMilliseconds], eax
0x14003dee0  mov     r9d, [rdi+14h]
0x14003dee4  lea     r8, aWinlogonJobXX; "Winlogon Job %x-%x"
0x14003deeb  mov     edx, 40h ; '@'; unsigned __int64
0x14003def0  lea     rcx, [rsp+118h+Name]; unsigned __int16 *
0x14003def5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14003defa  lea     rdx, [rsp+118h+Name]; lpName
0x14003deff  xor     ecx, ecx; lpJobAttributes
0x14003df01  call    cs:__imp_CreateJobObjectW
0x14003df07  mov     [rdi+18h], rax
0x14003df0b  test    rax, rax
0x14003df0e  jnz     short loc_14003DF1D
0x14003df10  call    cs:__imp_GetLastError
0x14003df16  mov     ebx, eax
0x14003df18  jmp     loc_14003E018
0x14003df1d  test    esi, esi
0x14003df1f  jz      loc_14003DFA8
0x14003df25  mov     [rdi+38h], esi
0x14003df28  call    cs:__imp_GetTickCount
0x14003df2e  add     [rdi+38h], eax
0x14003df31  lea     rcx, [rdi+28h]; phNewWaitObject
0x14003df35  mov     [rsp+118h+dwFlags], 8; dwFlags
0x14003df3d  mov     [rsp+118h+dwMilliseconds], esi; dwMilliseconds
0x14003df41  mov     r9, rdi; Context
0x14003df44  lea     r8, ?JobManagerCallback@@YAXPEAXE@Z; Callback
0x14003df4b  mov     rdx, [r14]; hObject
0x14003df4e  call    cs:__imp_RegisterWaitForSingleObject
0x14003df54  test    eax, eax
0x14003df56  jnz     short loc_14003DFA8
0x14003df58  call    cs:__imp_GetLastError
0x14003df5e  mov     ebx, eax
0x14003df60  lea     rsi, WPP_GLOBAL_Control
0x14003df67  mov     rcx, cs:WPP_GLOBAL_Control
0x14003df6e  cmp     rcx, rsi
0x14003df71  jz      loc_14003E01F
0x14003df77  test    dword ptr [rcx+1Ch], 200h
0x14003df7e  jz      loc_14003E01F
0x14003df84  cmp     byte ptr [rcx+19h], 2
0x14003df88  jb      loc_14003E01F
0x14003df8e  mov     edx, 1Bh
0x14003df93  mov     r9d, eax
0x14003df96  lea     r8, WPP_0dafbddec43b3b8d75685e9f611780a0_Traceguids
0x14003df9d  mov     rcx, [rcx+10h]
0x14003dfa1  call    WPP_SF_d
0x14003dfa6  jmp     short loc_14003E01F
0x14003dfa8  mov     rbx, rdi
0x14003dfab  mov     rdx, [r14]; hProcess
0x14003dfae  mov     rcx, [rbx+18h]; hJob
0x14003dfb2  call    cs:__imp_AssignProcessToJobObject
0x14003dfb8  test    eax, eax
0x14003dfba  jnz     short loc_14003DFED
0x14003dfbc  call    cs:__imp_GetLastError
0x14003dfc2  mov     ebx, eax
0x14003dfc4  lea     rsi, WPP_GLOBAL_Control
0x14003dfcb  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dfd2  cmp     rcx, rsi
0x14003dfd5  jz      short loc_14003E01F
0x14003dfd7  test    dword ptr [rcx+1Ch], 200h
0x14003dfde  jz      short loc_14003E01F
0x14003dfe0  cmp     byte ptr [rcx+19h], 3
0x14003dfe4  jb      short loc_14003E01F
0x14003dfe6  mov     edx, 1Ch
0x14003dfeb  jmp     short loc_14003DF93
0x14003dfed  mov     rcx, [r14+8]; hThread
0x14003dff1  call    cs:__imp_ResumeThread
0x14003dff7  cmp     eax, 0FFFFFFFFh
0x14003dffa  jz      loc_14003DF10
0x14003e000  mov     [rbx+34h], r15d
0x14003e004  mov     rax, [r14]
0x14003e007  mov     [rbx+20h], rax
0x14003e00b  mov     qword ptr [r14], 0
0x14003e012  mov     [r12], rdi
0x14003e016  xor     ebx, ebx
0x14003e018  lea     rsi, WPP_GLOBAL_Control
0x14003e01f  test    ebx, ebx
0x14003e021  jz      short loc_14003E073
0x14003e023  test    rdi, rdi
0x14003e026  jz      short loc_14003E063
0x14003e028  test    r13d, r13d
0x14003e02b  jz      short loc_14003E063
0x14003e02d  cmp     qword ptr [rdi+28h], 0
0x14003e032  jz      short loc_14003E04A
0x14003e034  call    ?JobManagerpUnlock@@YAKXZ; JobManagerpUnlock(void)
0x14003e039  xor     r15d, r15d
0x14003e03c  or      rdx, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x14003e040  mov     rcx, [rdi+28h]; WaitHandle
0x14003e044  call    cs:__imp_UnregisterWaitEx
0x14003e04a  mov     rcx, [rdi+18h]; hObject
0x14003e04e  test    rcx, rcx
0x14003e051  jz      short loc_14003E059
0x14003e053  call    cs:__imp_CloseHandle
0x14003e059  lea     rcx, [rsp+118h+var_D8]
0x14003e05e  call    UHHeapFree
0x14003e063  mov     edx, 5; uExitCode
0x14003e068  mov     rcx, [r14]; hProcess
0x14003e06b  call    cs:__imp_TerminateProcess
0x14003e071  jmp     short loc_14003E0F2
0x14003e073  test    r13d, r13d
0x14003e076  jz      short loc_14003E0F2
0x14003e078  mov     rax, cs:?JobManagerList@@3U_LIST_ENTRY@@A; _LIST_ENTRY JobManagerList
0x14003e07f  lea     rcx, ?JobManagerList@@3U_LIST_ENTRY@@A; _LIST_ENTRY JobManagerList
0x14003e086  cmp     [rax+8], rcx
0x14003e08a  jz      short loc_14003E093
0x14003e08c  mov     ecx, 3
0x14003e091  int     29h; Win8: RtlFailFast(ecx)
0x14003e093  mov     [rdi], rax
0x14003e096  mov     [rdi+8], rcx
0x14003e09a  mov     [rax+8], rdi
0x14003e09e  mov     cs:?JobManagerList@@3U_LIST_ENTRY@@A, rdi; _LIST_ENTRY JobManagerList
0x14003e0a5  mov     rcx, cs:WPP_GLOBAL_Control
0x14003e0ac  cmp     rcx, rsi
0x14003e0af  jz      short loc_14003E0F2
0x14003e0b1  test    dword ptr [rcx+1Ch], 200h
0x14003e0b8  jz      short loc_14003E0F2
0x14003e0ba  cmp     byte ptr [rcx+19h], 4
0x14003e0be  jb      short loc_14003E0F2
0x14003e0c0  mov     edx, 1Dh
0x14003e0c5  mov     eax, [rdi+30h]
0x14003e0c8  mov     [rsp+118h+var_E0], eax
0x14003e0cc  mov     rax, [rdi+20h]
0x14003e0d0  mov     [rsp+118h+var_E8], rax
0x14003e0d5  mov     rax, [rdi+18h]
0x14003e0d9  mov     qword ptr [rsp+118h+dwFlags], rax
0x14003e0de  mov     eax, [rdi+14h]
0x14003e0e1  mov     [rsp+118h+dwMilliseconds], eax
0x14003e0e5  mov     r9d, [rdi+10h]
0x14003e0e9  mov     rcx, [rcx+10h]
0x14003e0ed  call    WPP_SF_DDqqD
0x14003e0f2  test    r15d, r15d
0x14003e0f5  jz      short loc_14003E0FC
0x14003e0f7  call    ?JobManagerpUnlock@@YAKXZ; JobManagerpUnlock(void)
0x14003e0fc  mov     eax, ebx
0x14003e0fe  mov     rcx, [rsp+118h+var_48]
0x14003e106  xor     rcx, rsp; StackCookie
0x14003e109  call    __security_check_cookie
0x14003e10e  add     rsp, 0E0h
0x14003e115  pop     r15
0x14003e117  pop     r14
0x14003e119  pop     r13
0x14003e11b  pop     r12
0x14003e11d  pop     rdi
0x14003e11e  pop     rsi
0x14003e11f  pop     rbx
0x14003e120  retn
0x14009e7c4  push    rbp
0x14009e7c6  sub     rsp, 40h
0x14009e7ca  mov     rbp, rdx
0x14009e7cd  add     rsp, 40h
0x14009e7d1  pop     rbp
0x14009e7d2  retn
```
