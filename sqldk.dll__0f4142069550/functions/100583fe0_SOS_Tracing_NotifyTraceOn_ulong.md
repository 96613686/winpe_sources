# SOS_Tracing::NotifyTraceOn(ulong)

- ea: `0x100583fe0`
- end: `0x1005843b5`
- name: `?NotifyTraceOn@SOS_Tracing@@SAXK@Z`
- size: `981`
- prototype: `void __fastcall(unsigned int)`
- caller_count: `22`
- callee_count: `5`
- tags: `authz_impersonation, service_task`

## callers

- `0x1005ac680`
- `0x1005b42b0`
- `0x1005b4510`
- `0x1005b67f0`
- `0x1005b6880`
- `0x1005b68c0`
- `0x1005b68e0`
- `0x1005b6900`
- `0x1005b6920`
- `0x1005b6940`
- `0x1005b6990`
- `0x1005b69b0`
- `0x1005b6a30`
- `0x1005b6a50`
- `0x1005b6a70`
- `0x1005b6a90`
- `0x1005b6ab0`
- `0x1005b6ad0`
- `0x1005b6af0`
- `0x1005b6b50`
- `0x1005b6b70`
- `0x1005b6b90`

## callees

- `0x100403070`
- `0x1004b3270`
- `0x1004b47c0`
- `0x100583fe0`
- `0x10059ec40`

## import_xrefs

- `KERNEL32!IsProcessInJob` at `0x1005841b3`
- `KERNEL32!IsProcessInJob` at `0x1005841b3`
- `KERNEL32!CreateJobObjectW` at `0x1005841d6`
- `KERNEL32!CreateJobObjectW` at `0x1005841d6`
- `KERNEL32!SetInformationJobObject` at `0x100584227`
- `KERNEL32!SetInformationJobObject` at `0x100584250`
- `KERNEL32!SetInformationJobObject` at `0x100584227`
- `KERNEL32!SetInformationJobObject` at `0x100584250`
- `KERNEL32!AssignProcessToJobObject` at `0x100584266`
- `KERNEL32!AssignProcessToJobObject` at `0x100584266`
- `KERNEL32!GetSystemInfo` at `0x1005841fb`
- `KERNEL32!GetSystemInfo` at `0x1005841fb`
- `KERNEL32!GetCurrentProcess` at `0x1005841a4`
- `KERNEL32!GetCurrentProcess` at `0x10058425a`
- `KERNEL32!GetCurrentProcess` at `0x1005841a4`
- `KERNEL32!GetCurrentProcess` at `0x10058425a`

## pseudocode

```c
void __fastcall SOS_Tracing::NotifyTraceOn(int *a1)
{
  __int64 v1; // rdx
  __int64 v2; // rax
  __int64 v3; // r8
  unsigned __int64 v4; // rax
  __int64 v5; // r8
  HANDLE CurrentProcess; // rax
  HANDLE JobObjectW; // rbx
  HANDLE v8; // rax
  WINBOOL Result; // [rsp+20h] [rbp-60h] BYREF
  _DWORD v10[2]; // [rsp+28h] [rbp-58h] BYREF
  struct _SYSTEM_INFO SystemInfo; // [rsp+30h] [rbp-50h] BYREF
  __int64 v12; // [rsp+60h] [rbp-20h]
  __int64 JobObjectInformation; // [rsp+68h] [rbp-18h] BYREF
  __int16 v14; // [rsp+70h] [rbp-10h]

  v1 = (unsigned int)a1;
  if ( (unsigned int)((_DWORD)a1 - 6500) > 0x6A3 )
  {
    v2 = 0;
    a1 = &dword_10076944C;
    while ( (_DWORD)v1 != *a1 )
    {
      v2 = (unsigned int)(v2 + 1);
      a1 += 2;
      if ( (unsigned int)v2 >= 5 )
        goto LABEL_7;
    }
    v1 = (unsigned int)dword_100769448[2 * v2];
  }
LABEL_7:
  v3 = (unsigned int)(v1 - 6500);
  if ( (unsigned int)v3 > 0x6A3 )
  {
    switch ( (_DWORD)v1 )
    {
      case 0x9D9:
        SOS_Tracing_osTrace |= 2u;
        return;
      case 0xE46:
        SOS_PublicGlobals::sm_MallocSpyStatus = 1;
        SOS_OS::CreateStackStores(a1, v1, v3, &_NULL_IMPORT_DESCRIPTOR);
        return;
      case 0x2269:
        SOS_Tracing_osTrace |= 0x840u;
        return;
      case 0x226A:
        SOS_Tracing_osTrace |= 0xC00u;
        return;
      case 0xE2F:
        SOS_Tracing_osTrace |= 1u;
        return;
      case 0xE30:
        SOS_Tracing_osTrace |= 4u;
        return;
      case 0x130:
        *(_QWORD *)&SystemInfo.dwOemId = 0;
        memset((char *)&SystemInfo.lpMaximumApplicationAddress + 4, 0, 20);
        SystemInfo.lpMinimumApplicationAddress = (LPVOID)983040;
        LODWORD(SystemInfo.lpMaximumApplicationAddress) = 2;
        *(struct _SYSTEM_INFO *)&SOS_PublicGlobals::sm_memObjControlFlags = SystemInfo;
        *(_DWORD *)&SystemInfo.wProcessorLevel = 1000000;
        SystemInfo.dwAllocationGranularity = -1;
        v12 = 0;
        SOS_PublicGlobals::sm_memObjControlEnabled = 1;
        qword_100718E10 = 0;
        return;
    }
  }
  else
  {
    v4 = (unsigned __int64)(unsigned int)v3 >> 3;
    v5 = ((_BYTE)v1 - 100) & 7;
    *((_BYTE *)&SOS_PublicGlobals::sm_traceFlags + v4) |= 1 << v5;
    switch ( (_DWORD)v1 )
    {
      case 0x1F79:
        if ( (byte_1007149B2 & 0x40) == 0 )
        {
          SOS_ResourceManager::sm_UnitOfFairness = 1;
          SOS_ResourceManager::PropagateCpuChanges((SOS_ResourceManager *)&SOS_PublicGlobals::sm_ResourceManager);
        }
        return;
      case 0x1F7A:
        SOS_ResourceManager::sm_UnitOfFairness = 2;
        SOS_ResourceManager::PropagateCpuChanges((SOS_ResourceManager *)&SOS_PublicGlobals::sm_ResourceManager);
        return;
      case 0x1F84:
        LODWORD(qword_1007157C8) = qword_1007157C8 & 0xFFFFFFDF;
        return;
      case 0x1F8E:
        if ( (SOS_OS_sm_osProcessStatus & 1) == 0 )
        {
          if ( (SOS_PublicGlobals::sm_osOptions & 0x100) == 0 )
            SOS_PublicGlobals::sm_osStatus |= 0x20u;
          SOS_OS_AffinityType = 3;
          SOS_PublicGlobals::sm_osOptions |= 0x60u;
        }
        return;
      case 0x1FB1:
        SOS_OS_TaskStoreDisabled = 1;
        return;
      case 0x1F9F:
        if ( PageExclusionBitmap::sm_pageExclusionBitmap )
        {
          PageExclusionBitmap::sm_pageExclusionBitmap = 0;
          SOS_OS_LogUnlocalizedRoutine(L"Page exclusion bitmap is disabled.\n", v1, v5, &_NULL_IMPORT_DESCRIPTOR);
        }
        return;
      case 0x1FAC:
        SOS_OS_DetourPmoEnabled = 1;
        return;
      case 0x1FBE:
        SOS_Tracing_osTrace |= 0x1000u;
        return;
      case 0x1FF3:
        if ( (SOS_OS_sm_osProcessStatus & 1) == 0 )
        {
          Result = 0;
          CurrentProcess = GetCurrentProcess();
          if ( IsProcessInJob(CurrentProcess, 0, &Result) )
          {
            if ( !Result )
            {
              JobObjectW = CreateJobObjectW(0, 0);
              if ( JobObjectW )
              {
                memset(&SystemInfo, 0, sizeof(SystemInfo));
                GetSystemInfo(&SystemInfo);
                v14 = 0;
                JobObjectInformation = 1LL << (LOBYTE(SystemInfo.dwNumberOfProcessors) - 1);
                if ( SetInformationJobObject(
                       JobObjectW,
                       MaxJobObjectInfoClass|JobObjectBasicLimitInformation,
                       &JobObjectInformation,
                       0x10u) )
                {
                  v10[0] = 5;
                  v10[1] = 9900;
                  if ( SetInformationJobObject(JobObjectW, MaxJobObjectInfoClass|JobObjectBasicProcessIdList, v10, 8u) )
                  {
                    v8 = GetCurrentProcess();
                    if ( AssignProcessToJobObject(JobObjectW, v8) )
                      SOS_OS_NtJobObjectHandle = JobObjectW;
                  }
                }
              }
            }
          }
        }
        return;
    }
  }
  if ( (_DWORD)v1 == 8017 && (SOS_OS_sm_osProcessStatus & 1) == 0 )
    SOS_PublicGlobals::sm_osStatus |= 0x20u;
}

```

## disassembly

```asm
0x100583fe0  mov     [rsp-8+arg_10], rdi
0x100583fe5  push    rbp
0x100583fe6  mov     rbp, rsp
0x100583fe9  sub     rsp, 80h
0x100583ff0  mov     rax, cs:__security_cookie
0x100583ff7  xor     rax, rsp
0x100583ffa  mov     [rbp+var_8], rax
0x100583ffe  lea     eax, [rcx-1964h]
0x100584004  xor     edi, edi
0x100584006  lea     r9, __NULL_IMPORT_DESCRIPTOR
0x10058400d  mov     edx, ecx
0x10058400f  cmp     eax, 6A3h
0x100584014  jbe     short loc_100584039
0x100584016  mov     eax, edi
0x100584018  lea     rcx, dword_10076944C
0x10058401f  nop
0x100584020  cmp     edx, [rcx]
0x100584022  jz      short loc_100584031
0x100584024  inc     eax
0x100584026  add     rcx, 8
0x10058402a  cmp     eax, 5
0x10058402d  jb      short loc_100584020
0x10058402f  jmp     short loc_100584039
0x100584031  mov     edx, rva dword_100769448[r9+rax*8]
0x100584039  lea     r8d, [rdx-1964h]
0x100584040  cmp     r8d, 6A3h
0x100584047  ja      loc_10058429C
0x10058404d  mov     eax, r8d
0x100584050  lea     rcx, rva ?sm_traceFlags@SOS_PublicGlobals@@2PAEA[r9]; uchar near * SOS_PublicGlobals::sm_traceFlags ...
0x100584057  shr     rax, 3
0x10058405b  and     r8d, 7
0x10058405f  add     rcx, rax
0x100584062  movzx   eax, byte ptr [rcx]
0x100584065  bts     eax, r8d
0x100584069  mov     [rcx], al
0x10058406b  cmp     edx, 1F79h
0x100584071  jnz     short loc_10058409C
0x100584073  test    cs:byte_1007149B2, 40h
0x10058407a  jnz     loc_10058427F
0x100584080  mov     eax, 1
0x100584085  lea     rcx, ?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; this
0x10058408c  mov     cs:?sm_UnitOfFairness@SOS_ResourceManager@@0W4UnitOfFairness@1@A, eax; SOS_ResourceManager::UnitOfFairness SOS_ResourceManager::sm_UnitOfFairness
0x100584092  call    ?PropagateCpuChanges@SOS_ResourceManager@@AEAAXXZ; SOS_ResourceManager::PropagateCpuChanges(void)
0x100584097  jmp     loc_10058427F
0x10058409c  cmp     edx, 1F7Ah
0x1005840a2  jnz     short loc_1005840BF
0x1005840a4  lea     rcx, ?sm_ResourceManager@SOS_PublicGlobals@@2VSOS_ResourceManager@@A; this
0x1005840ab  mov     cs:?sm_UnitOfFairness@SOS_ResourceManager@@0W4UnitOfFairness@1@A, 2; SOS_ResourceManager::UnitOfFairness SOS_ResourceManager::sm_UnitOfFairness
0x1005840b5  call    ?PropagateCpuChanges@SOS_ResourceManager@@AEAAXXZ; SOS_ResourceManager::PropagateCpuChanges(void)
0x1005840ba  jmp     loc_10058427F
0x1005840bf  cmp     edx, 1F84h
0x1005840c5  jnz     short loc_1005840D3
0x1005840c7  and     dword ptr cs:qword_1007157C8, 0FFFFFFDFh
0x1005840ce  jmp     loc_10058427F
0x1005840d3  cmp     edx, 1F8Eh
0x1005840d9  jnz     short loc_100584113
0x1005840db  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1005840e2  jnz     loc_10058427F
0x1005840e8  mov     eax, cs:?sm_osOptions@SOS_PublicGlobals@@2KA; ulong SOS_PublicGlobals::sm_osOptions
0x1005840ee  bt      eax, 8
0x1005840f2  jb      short loc_1005840FB
0x1005840f4  or      cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 20h; ulong SOS_PublicGlobals::sm_osStatus
0x1005840fb  or      eax, 60h
0x1005840fe  mov     cs:?SOS_OS_AffinityType@@3W4OS_AFFINITY@SOS_OS@@A, 3; SOS_OS::OS_AFFINITY SOS_OS_AffinityType
0x100584108  mov     cs:?sm_osOptions@SOS_PublicGlobals@@2KA, eax; ulong SOS_PublicGlobals::sm_osOptions
0x10058410e  jmp     loc_10058427F
0x100584113  cmp     edx, 1FB1h
0x100584119  jnz     short loc_10058412B
0x10058411b  mov     eax, 1
0x100584120  mov     cs:?SOS_OS_TaskStoreDisabled@@3HA, eax; int SOS_OS_TaskStoreDisabled
0x100584126  jmp     loc_10058427F
0x10058412b  cmp     edx, 1F9Fh
0x100584131  jnz     short loc_100584159
0x100584133  cmp     cs:?sm_pageExclusionBitmap@PageExclusionBitmap@@0PEAEEA, rdi; uchar * PageExclusionBitmap::sm_pageExclusionBitmap
0x10058413a  jz      loc_10058427F
0x100584140  lea     rcx, aPageExclusionB_0; "Page exclusion bitmap is disabled.\n"
0x100584147  mov     cs:?sm_pageExclusionBitmap@PageExclusionBitmap@@0PEAEEA, rdi; uchar * PageExclusionBitmap::sm_pageExclusionBitmap
0x10058414e  call    cs:?SOS_OS_LogUnlocalizedRoutine@@3P6AXPEB_WZZEA; SOS_OS::LogUnlocalizedRoutine(wchar_t const *,...)
0x100584154  jmp     loc_10058427F
0x100584159  cmp     edx, 1FACh
0x10058415f  jnz     short loc_100584171
0x100584161  mov     eax, 1
0x100584166  mov     cs:?SOS_OS_DetourPmoEnabled@@3HA, eax; int SOS_OS_DetourPmoEnabled
0x10058416c  jmp     loc_10058427F
0x100584171  cmp     edx, 1FBEh
0x100584177  jnz     short loc_100584188
0x100584179  or      cs:?SOS_Tracing_osTrace@@3KA, 1000h; ulong SOS_Tracing_osTrace
0x100584183  jmp     loc_10058427F
0x100584188  cmp     edx, 1FF3h
0x10058418e  jnz     loc_10058438F
0x100584194  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x10058419b  jnz     loc_10058427F
0x1005841a1  mov     [rbp+Result], edi
0x1005841a4  call    cs:__imp_GetCurrentProcess
0x1005841aa  lea     r8, [rbp+Result]; Result
0x1005841ae  xor     edx, edx; JobHandle
0x1005841b0  mov     rcx, rax; ProcessHandle
0x1005841b3  call    cs:__imp_IsProcessInJob
0x1005841b9  test    eax, eax
0x1005841bb  jz      loc_10058427F
0x1005841c1  cmp     [rbp+Result], edi
0x1005841c4  jnz     loc_10058427F
0x1005841ca  xor     edx, edx; lpName
0x1005841cc  mov     [rsp+80h+arg_8], rbx
0x1005841d4  xor     ecx, ecx; lpJobAttributes
0x1005841d6  call    cs:__imp_CreateJobObjectW
0x1005841dc  mov     rbx, rax
0x1005841df  test    rax, rax
0x1005841e2  jz      loc_100584277
0x1005841e8  xorps   xmm0, xmm0
0x1005841eb  lea     rcx, [rbp+SystemInfo]; lpSystemInfo
0x1005841ef  movups  xmmword ptr [rbp+SystemInfo], xmm0
0x1005841f3  movups  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], xmm0
0x1005841f7  movups  xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors], xmm0
0x1005841fb  call    cs:__imp_GetSystemInfo
0x100584201  mov     ecx, [rbp+SystemInfo.dwNumberOfProcessors]
0x100584204  lea     r8, [rbp+JobObjectInformation]; lpJobObjectInformation
0x100584208  dec     ecx
0x10058420a  mov     [rbp+var_10], di
0x10058420e  mov     r9d, 10h; cbJobObjectInformationLength
0x100584214  mov     eax, 1
0x100584219  shl     rax, cl
0x10058421c  mov     rcx, rbx; hJob
0x10058421f  mov     [rbp+JobObjectInformation], rax
0x100584223  lea     edx, [r9-2]; JobObjectInformationClass
0x100584227  call    cs:__imp_SetInformationJobObject
0x10058422d  test    eax, eax
0x10058422f  jz      short loc_100584277
0x100584231  mov     r9d, 8; cbJobObjectInformationLength
0x100584237  mov     [rbp+var_58], 5
0x10058423e  lea     r8, [rbp+var_58]; lpJobObjectInformation
0x100584242  mov     [rbp+var_54], 26ACh
0x100584249  mov     rcx, rbx; hJob
0x10058424c  lea     edx, [r9+7]; JobObjectInformationClass
0x100584250  call    cs:__imp_SetInformationJobObject
0x100584256  test    eax, eax
0x100584258  jz      short loc_100584277
0x10058425a  call    cs:__imp_GetCurrentProcess
0x100584260  mov     rdx, rax; hProcess
0x100584263  mov     rcx, rbx; hJob
0x100584266  call    cs:__imp_AssignProcessToJobObject
0x10058426c  test    eax, eax
0x10058426e  jz      short loc_100584277
0x100584270  mov     cs:?SOS_OS_NtJobObjectHandle@@3PEAXEA, rbx; void * SOS_OS_NtJobObjectHandle
0x100584277  mov     rbx, [rsp+80h+arg_8]
0x10058427f  mov     rcx, [rbp+var_8]
0x100584283  xor     rcx, rsp; StackCookie
0x100584286  call    __security_check_cookie
0x10058428b  mov     rdi, [rsp+80h+arg_10]
0x100584293  add     rsp, 80h
0x10058429a  pop     rbp
0x10058429b  retn
0x10058429c  cmp     edx, 9D9h
0x1005842a2  jnz     short loc_1005842AD
0x1005842a4  or      cs:?SOS_Tracing_osTrace@@3KA, 2; ulong SOS_Tracing_osTrace
0x1005842ab  jmp     short loc_10058427F
0x1005842ad  cmp     edx, 0E46h
0x1005842b3  jnz     short loc_1005842C7
0x1005842b5  mov     eax, 1
0x1005842ba  mov     cs:?sm_MallocSpyStatus@SOS_PublicGlobals@@2HA, eax; int SOS_PublicGlobals::sm_MallocSpyStatus
0x1005842c0  call    ?CreateStackStores@SOS_OS@@SA?AW4SOS_RESULT@@XZ; SOS_OS::CreateStackStores(void)
0x1005842c5  jmp     short loc_10058427F
0x1005842c7  cmp     edx, 2269h
0x1005842cd  jnz     short loc_1005842DB
0x1005842cf  or      cs:?SOS_Tracing_osTrace@@3KA, 840h; ulong SOS_Tracing_osTrace
0x1005842d9  jmp     short loc_10058427F
0x1005842db  cmp     edx, 226Ah
0x1005842e1  jnz     short loc_1005842EF
0x1005842e3  or      cs:?SOS_Tracing_osTrace@@3KA, 0C00h; ulong SOS_Tracing_osTrace
0x1005842ed  jmp     short loc_10058427F
0x1005842ef  cmp     edx, 0E2Fh
0x1005842f5  jnz     short loc_100584303
0x1005842f7  or      cs:?SOS_Tracing_osTrace@@3KA, 1; ulong SOS_Tracing_osTrace
0x1005842fe  jmp     loc_10058427F
0x100584303  cmp     edx, 0E30h
0x100584309  jnz     short loc_100584317
0x10058430b  or      cs:?SOS_Tracing_osTrace@@3KA, 4; ulong SOS_Tracing_osTrace
0x100584312  jmp     loc_10058427F
0x100584317  cmp     edx, 130h
0x10058431d  jnz     short loc_10058438F
0x10058431f  xorps   xmm0, xmm0
0x100584322  mov     qword ptr [rbp+SystemInfo], rdi
0x100584326  movdqu  xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress+4], xmm0
0x10058432b  mov     dword ptr [rbp+SystemInfo.lpMinimumApplicationAddress+4], edi
0x10058432e  mov     eax, 1
0x100584333  mov     dword ptr [rbp+SystemInfo.lpMinimumApplicationAddress], 0F0000h
0x10058433a  movups  xmm0, xmmword ptr [rbp+SystemInfo]
0x10058433e  mov     dword ptr [rbp+SystemInfo.lpMaximumApplicationAddress], 2
0x100584345  movups  xmm1, xmmword ptr [rbp+SystemInfo.lpMaximumApplicationAddress]
0x100584349  mov     [rbp+SystemInfo.dwProcessorType], edi
0x10058434c  movaps  xmmword ptr cs:?sm_memObjControlFlags@SOS_PublicGlobals@@2PAVMemObjControlFlags@@A, xmm0; MemObjControlFlags near * SOS_PublicGlobals::sm_memObjControlFlags
0x100584353  mov     dword ptr [rbp+SystemInfo.wProcessorLevel], 0F4240h
0x10058435a  mov     [rbp+SystemInfo.dwAllocationGranularity], 0FFFFFFFFh
0x100584361  movups  xmm0, xmmword ptr [rbp+SystemInfo.dwNumberOfProcessors]
0x100584365  mov     [rbp+var_20], rdi
0x100584369  movaps  xmmword ptr cs:?sm_memObjControlFlags@SOS_PublicGlobals@@2PAVMemObjControlFlags@@A+10h, xmm1; MemObjControlFlags near * SOS_PublicGlobals::sm_memObjControlFlags
0x100584370  movsd   xmm1, [rbp+var_20]
0x100584375  movaps  xmmword ptr cs:?sm_memObjControlFlags@SOS_PublicGlobals@@2PAVMemObjControlFlags@@A+20h, xmm0; MemObjControlFlags near * SOS_PublicGlobals::sm_memObjControlFlags
0x10058437c  mov     cs:?sm_memObjControlEnabled@SOS_PublicGlobals@@2HA, eax; int SOS_PublicGlobals::sm_memObjControlEnabled
0x100584382  movsd   cs:qword_100718E10, xmm1
0x10058438a  jmp     loc_10058427F
0x10058438f  cmp     edx, 1F51h
0x100584395  jnz     loc_10058427F
0x10058439b  test    byte ptr cs:?SOS_OS_sm_osProcessStatus@@3KA, 1; ulong SOS_OS_sm_osProcessStatus
0x1005843a2  jnz     loc_10058427F
0x1005843a8  or      cs:?sm_osStatus@SOS_PublicGlobals@@2KA, 20h; ulong SOS_PublicGlobals::sm_osStatus
0x1005843af  jmp     loc_10058427F
```
