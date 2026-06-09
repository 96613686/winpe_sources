# SmpExecuteImage

- ea: `0x1400053e0`
- end: `0x140005991`
- name: `SmpExecuteImage`
- size: `1457`
- prototype: ``
- caller_count: `6`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140003450`
- `0x1400036d0`
- `0x1400050a0`
- `0x140014fc4`
- `0x1400151e0`
- `0x140017ad0`

## callees

- `0x1400010ec`
- `0x140001450`
- `0x140003114`
- `0x1400053e0`
- `0x140008d90`
- `0x140012bb8`
- `0x14001cc29`
- `0x14001cc40`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x140005787`
- `ntdll!NtQueryInformationProcess` at `0x140005787`
- `ntdll!NtClose` at `0x1400058d6`
- `ntdll!NtClose` at `0x1400058e0`
- `ntdll!NtClose` at `0x1400058d6`
- `ntdll!NtClose` at `0x1400058e0`
- `ntdll!NtQuerySystemInformation` at `0x140005574`
- `ntdll!NtQuerySystemInformation` at `0x140005574`
- `ntdll!EtwEventWrite` at `0x1400057ea`
- `ntdll!EtwEventWrite` at `0x14000593d`
- `ntdll!EtwEventWrite` at `0x1400057ea`
- `ntdll!EtwEventWrite` at `0x14000593d`
- `ntdll!EtwEventEnabled` at `0x1400057ae`
- `ntdll!EtwEventEnabled` at `0x140005901`
- `ntdll!EtwEventEnabled` at `0x1400057ae`
- `ntdll!EtwEventEnabled` at `0x140005901`
- `ntdll!NtSetInformationProcess` at `0x140005812`
- `ntdll!NtSetInformationProcess` at `0x140005812`
- `ntdll!NtResumeThread` at `0x1400058a0`
- `ntdll!NtResumeThread` at `0x1400058a0`
- `ntdll!NtWaitForSingleObject` at `0x140005892`
- `ntdll!NtWaitForSingleObject` at `0x1400058c1`
- `ntdll!NtWaitForSingleObject` at `0x140005892`
- `ntdll!NtWaitForSingleObject` at `0x1400058c1`
- `ntdll!NtTerminateProcess` at `0x140005883`
- `ntdll!NtTerminateProcess` at `0x140005883`
- `ntdll!RtlTestBit` at `0x1400055a9`
- `ntdll!RtlTestBit` at `0x1400055a9`
- `ntdll!RtlInterlockedSetBitRun` at `0x1400055c2`
- `ntdll!RtlInterlockedSetBitRun` at `0x1400055c2`
- `ntdll!RtlFindSetBits` at `0x14000561a`
- `ntdll!RtlFindSetBits` at `0x14000561a`
- `ntdll!RtlCreateProcessParametersEx` at `0x1400054c1`
- `ntdll!RtlCreateProcessParametersEx` at `0x1400054c1`
- `ntdll!RtlCreateUserProcessEx` at `0x140005743`
- `ntdll!RtlCreateUserProcessEx` at `0x140005743`
- `ntdll!RtlDestroyProcessParameters` at `0x140005750`
- `ntdll!RtlDestroyProcessParameters` at `0x140005750`

## pseudocode

```c
__int64 __fastcall SmpExecuteImage(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6, _OWORD *a7)
{
  _OWORD *v7; // rsi
  __int64 v8; // r12
  int v10; // eax
  unsigned int UserProcess; // ebx
  __int64 v12; // r8
  ULONG v13; // ecx
  signed __int32 v14; // r12d
  unsigned __int32 v15; // r14d
  ULONG i; // ebx
  unsigned __int32 v17; // eax
  unsigned __int32 v18; // edx
  __int16 SetBits; // ax
  __int16 v20; // bx
  __int64 v21; // r8
  _OWORD *v22; // r9
  __int64 v23; // rax
  __int64 v24; // rax
  void *v25; // rcx
  NTSTATUS InformationProcess; // eax
  int v27; // edx
  void *v28; // rcx
  int ProcessId; // eax
  int v30; // eax
  __int64 v31; // r8
  void *v32; // rcx
  __int64 v33; // r8
  PRTL_USER_PROCESS_PARAMETERS ProcessParameters; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v37[2]; // [rsp+70h] [rbp-90h] BYREF
  _OWORD v38[3]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v39; // [rsp+B0h] [rbp-50h]
  _OWORD v40[3]; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v41; // [rsp+F0h] [rbp-10h]
  _OWORD ProcessInformation[3]; // [rsp+F8h] [rbp-8h] BYREF
  _OWORD v43[6]; // [rsp+130h] [rbp+30h] BYREF
  int v44; // [rsp+190h] [rbp+90h]
  _BYTE SystemInformation[1040]; // [rsp+1A0h] [rbp+A0h] BYREF
  _QWORD *v46; // [rsp+5B0h] [rbp+4B0h] BYREF
  __int64 v47; // [rsp+5B8h] [rbp+4B8h]

  v7 = v43;
  v8 = a5;
  v37[0] = a5;
  v36 = 0;
  ProcessParameters = 0;
  v41 = 0;
  v44 = 0;
  if ( a7 )
    v7 = a7;
  memset(v40, 0, sizeof(v40));
  memset(v38, 0, sizeof(v38));
  v39 = 0;
  memset(v43, 0, sizeof(v43));
  v10 = RtlCreateProcessParametersEx(&ProcessParameters, a1, 0, a2, a3, SmpDefaultEnvironment, 0, 0, 0, 0, 1);
  UserProcess = v10;
  if ( v10 < 0 )
  {
    if ( a1 )
      v12 = *(_QWORD *)(a1 + 8);
    else
      v12 = 0;
    SmpLogFailureString("SmpExecuteImage", 9898, v12, (unsigned int)v10);
    return UserProcess;
  }
  v13 = SmpDebug;
  if ( (a6 & 1) != 0 )
    v13 = 1;
  ProcessParameters->DebugFlags = v13;
  if ( (a6 & 0x400) != 0 )
  {
    ProcessParameters->Flags |= 0x40000u;
    memset_0(SystemInformation, 0, 0x408u);
    v14 = SmpActiveProcessorCount;
    v15 = MEMORY[0x7FFE03C0];
    if ( (unsigned int)SmpActiveProcessorCount < MEMORY[0x7FFE03C0]
      && NtQuerySystemInformation(SystemNumaProcessorMap, SystemInformation, 0x408u, 0) >= 0 )
    {
      for ( i = 0; i < SmpMaximumNodeCount; ++i )
      {
        if ( *(_QWORD *)&SystemInformation[16 * i + 8] && !RtlTestBit(&SmpNodeBitmap, i) )
          RtlInterlockedSetBitRun(&SmpNodeBitmap, i, 1);
      }
      v17 = _InterlockedCompareExchange(&SmpActiveProcessorCount, v15, v14);
      if ( v17 != v14 )
      {
        do
        {
          if ( v17 >= v15 )
            break;
          v18 = v17;
          v17 = _InterlockedCompareExchange(&SmpActiveProcessorCount, v15, v17);
        }
        while ( v17 != v18 );
      }
    }
    SetBits = RtlFindSetBits(
                &SmpNodeBitmap,
                1u,
                _InterlockedExchangeAdd(&SmpCurrentNodeCount, 1u) % (unsigned int)SmpMaximumNodeCount);
    v8 = v37[0];
    v20 = SetBits + 1;
  }
  else
  {
    v20 = 0;
  }
  if ( (a6 & 0x1000) != 0 )
    ProcessParameters->Flags |= 0x400000u;
  if ( (a6 & 0x4000) != 0 )
    ProcessParameters->Flags |= 0x800000u;
  if ( (a6 & 0x8000) != 0 )
    ProcessParameters->Flags |= 0x80000000;
  ProcessParameters->Flags |= 0x20000u;
  *(_DWORD *)v7 = 104;
  SmpEventWriteULONGString(&SmssEvt_ExecuteImage_Start);
  if ( !(unsigned int)Feature_WinlogonProcessMitigations__private_IsEnabledDeviceUsageNoInline() )
  {
    WORD1(v40[0]) = v20;
    v22 = v40;
    v41 = v8;
    LOWORD(v40[0]) = 1;
    memset((char *)v40 + 4, 0, 44);
    goto LABEL_41;
  }
  v23 = 0;
  WORD1(v38[0]) = v20;
  memset((char *)v38 + 4, 0, 44);
  LOWORD(v38[0]) = 2;
  v39 = (unsigned __int64)v8;
  if ( (a6 & 0x20000) != 0 )
  {
    v23 = 1;
    *((_QWORD *)&v39 + 1) = 1;
  }
  else if ( (a6 & 0x40000) != 0 )
  {
    *((_QWORD *)&v39 + 1) = 2;
    v23 = 2;
  }
  if ( (a6 & 0x80000) != 0 )
  {
    v24 = v23 | 4;
LABEL_39:
    *((_QWORD *)&v39 + 1) = v24;
    goto LABEL_40;
  }
  if ( (a6 & 0x100000) != 0 )
  {
    v24 = v23 | 8;
    goto LABEL_39;
  }
LABEL_40:
  v22 = v38;
LABEL_41:
  LOBYTE(v21) = (a6 & 0x400) != 0;
  UserProcess = RtlCreateUserProcessEx(a1, ProcessParameters, v21, v22, v7);
  RtlDestroyProcessParameters(ProcessParameters);
  if ( (UserProcess & 0x80000000) == 0 )
  {
    v25 = (void *)*((_QWORD *)v7 + 1);
    memset(ProcessInformation, 0, 44);
    InformationProcess = NtQueryInformationProcess(v25, ProcessBasicInformation, ProcessInformation, 0x30u, 0);
    v27 = ProcessInformation[2];
    if ( InformationProcess < 0 )
      v27 = 0;
    LODWORD(v37[0]) = v27;
    if ( SmpTraceHandle && EtwEventEnabled(SmpTraceHandle, &SmssEvt_ExecuteImage_Stop) )
    {
      v46 = v37;
      v47 = 4;
      EtwEventWrite(SmpTraceHandle, &SmssEvt_ExecuteImage_Stop, 1, &v46);
    }
    if ( (a6 & 0x2000) != 0 )
    {
      v28 = (void *)*((_QWORD *)v7 + 1);
      v36 = 1;
      UserProcess = NtSetInformationProcess(v28, ProcessBreakOnTermination, &v36, 4u);
      if ( (UserProcess & 0x80000000) != 0 )
      {
        ProcessId = SmpGetProcessId(*((_QWORD *)v7 + 1));
        SmLogFailureInt((unsigned int)"SmpExecuteImage", 10027, ProcessId, 0, UserProcess);
LABEL_57:
        NtTerminateProcess(*((HANDLE *)v7 + 1), UserProcess);
        NtWaitForSingleObject(*((HANDLE *)v7 + 1), 0, 0);
        goto LABEL_65;
      }
    }
    v30 = a6 & 0x20;
    if ( (a6 & 0x20) == 0 )
    {
      if ( *((_DWORD *)v7 + 18) != 1 && (a6 & 0x8000) == 0 )
      {
        UserProcess = -1073741701;
        if ( a1 )
          v31 = *(_QWORD *)(a1 + 8);
        else
          v31 = 0;
        SmpLogFailureString("SmpExecuteImage", 10043, v31, 3221225595LL);
        goto LABEL_57;
      }
      NtResumeThread(*((HANDLE *)v7 + 2), 0);
      if ( (a6 & 2) == 0 )
      {
        if ( (a6 & 0x10000) != 0 )
          v32 = (void *)*((_QWORD *)v7 + 1);
        else
          v32 = (void *)*((_QWORD *)v7 + 2);
        NtWaitForSingleObject(v32, 0, 0);
      }
      v30 = 0;
    }
    if ( v30 )
      return UserProcess;
LABEL_65:
    NtClose(*((HANDLE *)v7 + 2));
    NtClose(*((HANDLE *)v7 + 1));
    return UserProcess;
  }
  LODWORD(v37[0]) = 0;
  if ( SmpTraceHandle && EtwEventEnabled(SmpTraceHandle, &SmssEvt_ExecuteImage_Stop) )
  {
    v46 = v37;
    v47 = 4;
    EtwEventWrite(SmpTraceHandle, &SmssEvt_ExecuteImage_Stop, 1, &v46);
  }
  if ( a1 )
    v33 = *(_QWORD *)(a1 + 8);
  else
    v33 = 0;
  SmpLogFailureString("SmpExecuteImage", 10013, v33, UserProcess);
  return UserProcess;
}

```

## disassembly

```asm
0x1400053e0  push    rbp
0x1400053e2  push    rbx
0x1400053e3  push    rsi
0x1400053e4  push    r12
0x1400053e6  push    r13
0x1400053e8  push    r14
0x1400053ea  push    r15
0x1400053ec  lea     rbp, [rsp-4D0h]
0x1400053f4  sub     rsp, 5D0h
0x1400053fb  mov     rax, cs:__security_cookie
0x140005402  xor     rax, rsp
0x140005405  mov     [rbp+500h+var_40], rax
0x14000540c  mov     rax, [rbp+500h+arg_30]
0x140005413  lea     rsi, [rbp+500h+var_4D0]
0x140005417  mov     r12, [rbp+500h+arg_20]
0x14000541e  xorps   xmm0, xmm0
0x140005421  xor     r14d, r14d
0x140005424  mov     [rsp+600h+var_590], r12
0x140005429  xorps   xmm1, xmm1
0x14000542c  mov     [rsp+600h+var_598], r14d
0x140005431  mov     r15, rcx
0x140005434  mov     [rsp+600h+ProcessParameters], r14
0x140005439  xor     ecx, ecx
0x14000543b  mov     r9, rdx
0x14000543e  test    rax, rax
0x140005441  mov     [rbp+500h+var_510], rcx
0x140005445  mov     [rbp+500h+var_470], ecx
0x14000544b  mov     r13d, 1
0x140005451  mov     [rsp+600h+var_5B0], r13d
0x140005456  lea     rcx, [rsp+600h+ProcessParameters]
0x14000545b  mov     [rsp+600h+var_5B8], r14
0x140005460  cmovnz  rsi, rax
0x140005464  mov     rax, cs:SmpDefaultEnvironment
0x14000546b  mov     rdx, r15
0x14000546e  mov     [rsp+600h+var_5C0], r14
0x140005473  mov     [rsp+600h+var_5C8], r14
0x140005478  mov     [rsp+600h+var_5D0], r14
0x14000547d  mov     [rsp+600h+var_5D8], rax
0x140005482  mov     [rsp+600h+ReturnLength], r8
0x140005487  xor     r8d, r8d
0x14000548a  movups  [rbp+500h+var_540], xmm0
0x14000548e  movups  [rbp+500h+var_530], xmm0
0x140005492  movups  [rbp+500h+var_520], xmm0
0x140005496  movups  [rbp+500h+var_580], xmm1
0x14000549a  movups  [rbp+500h+var_570], xmm1
0x14000549e  movups  [rbp+500h+var_560], xmm1
0x1400054a2  movups  [rbp+500h+var_550], xmm1
0x1400054a6  movups  [rbp+500h+var_4D0], xmm0
0x1400054aa  movups  [rbp+500h+var_4C0], xmm0
0x1400054ae  movups  [rbp+500h+var_4B0], xmm0
0x1400054b2  movups  [rbp+500h+var_4A0], xmm0
0x1400054b6  movups  [rbp+500h+var_490], xmm0
0x1400054ba  movups  [rbp+500h+var_480], xmm0
0x1400054c1  call    cs:__imp_RtlCreateProcessParametersEx
0x1400054c7  mov     ebx, eax
0x1400054c9  test    eax, eax
0x1400054cb  jns     short loc_1400054F4
0x1400054cd  test    r15, r15
0x1400054d0  jz      short loc_1400054D8
0x1400054d2  mov     r8, [r15+8]
0x1400054d6  jmp     short loc_1400054DB
0x1400054d8  mov     r8, r14
0x1400054db  mov     r9d, ebx
0x1400054de  lea     rcx, aSmpexecuteimag; "SmpExecuteImage"
0x1400054e5  mov     edx, 26AAh
0x1400054ea  call    SmpLogFailureString
0x1400054ef  jmp     loc_14000596D
0x1400054f4  mov     ecx, cs:SmpDebug
0x1400054fa  mov     rax, [rsp+600h+ProcessParameters]
0x1400054ff  mov     [rsp+600h+arg_18], rdi
0x140005507  mov     edi, [rbp+500h+arg_28]
0x14000550d  test    r13b, dil
0x140005510  cmovnz  ecx, r13d
0x140005514  mov     r13d, edi
0x140005517  mov     [rax+0Ch], ecx
0x14000551a  and     r13d, 400h
0x140005521  jz      loc_14000562A
0x140005527  mov     rax, [rsp+600h+ProcessParameters]
0x14000552c  lea     rcx, [rbp+500h+SystemInformation]; void *
0x140005533  xor     edx, edx; Val
0x140005535  mov     r8d, 408h; Size
0x14000553b  or      dword ptr [rax+8], 40000h
0x140005542  call    memset_0
0x140005547  mov     r12d, cs:SmpActiveProcessorCount
0x14000554e  mov     r14d, ds:7FFE03C0h
0x140005556  cmp     r12d, r14d
0x140005559  jnb     loc_1400055F7
0x14000555f  xor     r9d, r9d; ReturnLength
0x140005562  lea     rdx, [rbp+500h+SystemInformation]; SystemInformation
0x140005569  mov     r8d, 408h; SystemInformationLength
0x14000556f  mov     ecx, 37h ; '7'; SystemInformationClass
0x140005574  call    cs:__imp_NtQuerySystemInformation
0x14000557a  test    eax, eax
0x14000557c  js      short loc_1400055F7
0x14000557e  xor     ebx, ebx
0x140005580  cmp     cs:SmpMaximumNodeCount, ebx
0x140005586  jbe     short loc_1400055D2
0x140005588  nop     dword ptr [rax+rax+00000000h]
0x140005590  mov     eax, ebx
0x140005592  add     rax, rax
0x140005595  cmp     [rbp+rax*8+500h+var_458], 0
0x14000559e  jz      short loc_1400055C8
0x1400055a0  mov     edx, ebx; BitNumber
0x1400055a2  lea     rcx, SmpNodeBitmap; BitMapHeader
0x1400055a9  call    cs:__imp_RtlTestBit
0x1400055af  test    al, al
0x1400055b1  jnz     short loc_1400055C8
0x1400055b3  mov     r8d, 1
0x1400055b9  lea     rcx, SmpNodeBitmap
0x1400055c0  mov     edx, ebx
0x1400055c2  call    cs:__imp_RtlInterlockedSetBitRun
0x1400055c8  inc     ebx
0x1400055ca  cmp     ebx, cs:SmpMaximumNodeCount
0x1400055d0  jb      short loc_140005590
0x1400055d2  mov     eax, r12d
0x1400055d5  lock cmpxchg cs:SmpActiveProcessorCount, r14d
0x1400055de  cmp     eax, r12d
0x1400055e1  jz      short loc_1400055F7
0x1400055e3  cmp     eax, r14d
0x1400055e6  jnb     short loc_1400055F7
0x1400055e8  mov     edx, eax
0x1400055ea  lock cmpxchg cs:SmpActiveProcessorCount, r14d
0x1400055f3  cmp     eax, edx
0x1400055f5  jnz     short loc_1400055E3
0x1400055f7  mov     ecx, 1
0x1400055fc  mov     eax, ecx
0x1400055fe  lock xadd cs:SmpCurrentNodeCount, eax
0x140005606  xor     edx, edx
0x140005608  div     cs:SmpMaximumNodeCount
0x14000560e  mov     r8d, edx; HintIndex
0x140005611  mov     edx, ecx; NumberToFind
0x140005613  lea     rcx, SmpNodeBitmap; BitMapHeader
0x14000561a  call    cs:__imp_RtlFindSetBits
0x140005620  mov     r12, [rsp+600h+var_590]
0x140005625  lea     ebx, [rax+1]
0x140005628  jmp     short loc_14000562D
0x14000562a  mov     ebx, r14d
0x14000562d  bt      edi, 0Ch
0x140005631  jnb     short loc_14000563F
0x140005633  mov     rax, [rsp+600h+ProcessParameters]
0x140005638  or      dword ptr [rax+8], 400000h
0x14000563f  bt      edi, 0Eh
0x140005643  jnb     short loc_140005651
0x140005645  mov     rax, [rsp+600h+ProcessParameters]
0x14000564a  or      dword ptr [rax+8], 800000h
0x140005651  mov     r14d, edi
0x140005654  and     r14d, 8000h
0x14000565b  jz      short loc_140005669
0x14000565d  mov     rax, [rsp+600h+ProcessParameters]
0x140005662  or      dword ptr [rax+8], 80000000h
0x140005669  mov     rax, [rsp+600h+ProcessParameters]
0x14000566e  lea     rcx, SmssEvt_ExecuteImage_Start; EventDescriptor
0x140005675  mov     r8, r15
0x140005678  mov     edx, edi
0x14000567a  or      dword ptr [rax+8], 20000h
0x140005681  mov     dword ptr [rsi], 68h ; 'h'
0x140005687  call    SmpEventWriteULONGString
0x14000568c  call    Feature_WinlogonProcessMitigations__private_IsEnabledDeviceUsageNoInline
0x140005691  test    eax, eax
0x140005693  jnz     short loc_1400056C5
0x140005695  xor     eax, eax
0x140005697  mov     word ptr [rbp+500h+var_540+2], bx
0x14000569b  mov     qword ptr [rbp+500h+var_520+4], rax
0x14000569f  lea     r9, [rbp+500h+var_540]
0x1400056a3  mov     dword ptr [rbp+500h+var_520+0Ch], eax
0x1400056a6  xorps   xmm0, xmm0
0x1400056a9  mov     eax, 1
0x1400056ae  mov     [rbp+500h+var_510], r12
0x1400056b2  xorps   xmm1, xmm1
0x1400056b5  mov     word ptr [rbp+500h+var_540], ax
0x1400056b9  movdqu  [rbp+500h+var_540+4], xmm0
0x1400056be  movdqu  [rbp+500h+var_530+4], xmm1
0x1400056c3  jmp     short loc_14000572F
0x1400056c5  xor     eax, eax
0x1400056c7  mov     word ptr [rbp+500h+var_580+2], bx
0x1400056cb  mov     qword ptr [rbp+500h+var_580+4], rax
0x1400056cf  mov     ecx, 2
0x1400056d4  mov     qword ptr [rbp+500h+var_580+0Ch], rax
0x1400056d8  mov     qword ptr [rbp+500h+var_570+4], rax
0x1400056dc  mov     qword ptr [rbp+500h+var_570+0Ch], rax
0x1400056e0  mov     qword ptr [rbp+500h+var_560+4], rax
0x1400056e4  mov     dword ptr [rbp+500h+var_560+0Ch], eax
0x1400056e7  mov     qword ptr [rbp+500h+var_550+8], rax
0x1400056eb  mov     word ptr [rbp+500h+var_580], cx
0x1400056ef  mov     qword ptr [rbp+500h+var_550], r12
0x1400056f3  bt      edi, 11h
0x1400056f7  jnb     short loc_140005704
0x1400056f9  mov     eax, 1
0x1400056fe  mov     qword ptr [rbp+500h+var_550+8], rax
0x140005702  jmp     short loc_140005711
0x140005704  bt      edi, 12h
0x140005708  jnb     short loc_140005711
0x14000570a  mov     qword ptr [rbp+500h+var_550+8], rcx
0x14000570e  mov     rax, rcx
0x140005711  bt      edi, 13h
0x140005715  jnb     short loc_14000571D
0x140005717  or      rax, 4
0x14000571b  jmp     short loc_140005727
0x14000571d  bt      edi, 14h
0x140005721  jnb     short loc_14000572B
0x140005723  or      rax, 8
0x140005727  mov     qword ptr [rbp+500h+var_550+8], rax
0x14000572b  lea     r9, [rbp+500h+var_580]
0x14000572f  mov     rdx, [rsp+600h+ProcessParameters]
0x140005734  test    r13d, r13d
0x140005737  mov     rcx, r15
0x14000573a  mov     [rsp+600h+ReturnLength], rsi
0x14000573f  setnz   r8b
0x140005743  call    cs:__imp_RtlCreateUserProcessEx
0x140005749  mov     rcx, [rsp+600h+ProcessParameters]; ProcessParameters
0x14000574e  mov     ebx, eax
0x140005750  call    cs:__imp_RtlDestroyProcessParameters
0x140005756  test    ebx, ebx
0x140005758  js      loc_1400058E8
0x14000575e  mov     rcx, [rsi+8]; ProcessHandle
0x140005762  lea     r8, [rbp+500h+ProcessInformation]; ProcessInformation
0x140005766  xorps   xmm0, xmm0
0x140005769  xor     r12d, r12d
0x14000576c  movups  [rbp+500h+var_4F8], xmm0
0x140005770  xor     eax, eax
0x140005772  mov     [rsp+600h+ReturnLength], r12; ReturnLength
0x140005777  mov     r9d, 30h ; '0'; ProcessInformationLength
0x14000577d  xor     edx, edx; ProcessInformationClass
0x14000577f  movups  [rbp+500h+var_4F8+0Ch], xmm0
0x140005783  movups  [rbp+500h+ProcessInformation], xmm0
0x140005787  call    cs:__imp_NtQueryInformationProcess
0x14000578d  mov     rdx, [rbp+500h+var_4E8]
0x140005791  test    eax, eax
0x140005793  mov     rcx, cs:SmpTraceHandle; RegHandle
0x14000579a  cmovs   rdx, r12
0x14000579e  mov     dword ptr [rsp+600h+var_590], edx
0x1400057a2  test    rcx, rcx
0x1400057a5  jz      short loc_1400057F0
0x1400057a7  lea     rdx, SmssEvt_ExecuteImage_Stop; EventDescriptor
0x1400057ae  call    cs:__imp_EtwEventEnabled
0x1400057b4  test    al, al
0x1400057b6  jz      short loc_1400057F0
0x1400057b8  mov     rcx, cs:SmpTraceHandle
0x1400057bf  lea     rax, [rsp+600h+var_590]
0x1400057c4  lea     r9, [rbp+500h+var_50]
0x1400057cb  mov     [rbp+500h+var_50], rax
0x1400057d2  mov     r8d, 1
0x1400057d8  mov     [rbp+500h+var_48], 4
0x1400057e3  lea     rdx, SmssEvt_ExecuteImage_Stop
0x1400057ea  call    cs:__imp_EtwEventWrite
0x1400057f0  bt      edi, 0Dh
0x1400057f4  jnb     short loc_140005844
0x1400057f6  mov     rcx, [rsi+8]; ProcessHandle
0x1400057fa  lea     r8, [rsp+600h+var_598]; ProcessInformation
0x1400057ff  mov     r9d, 4; ProcessInformationLength
0x140005805  mov     [rsp+600h+var_598], 1
0x14000580d  mov     edx, 1Dh; ProcessInformationClass
0x140005812  call    cs:__imp_NtSetInformationProcess
0x140005818  mov     ebx, eax
0x14000581a  test    eax, eax
0x14000581c  jns     short loc_140005844
0x14000581e  mov     rcx, [rsi+8]
0x140005822  call    SmpGetProcessId
0x140005827  mov     r8, rax
0x14000582a  mov     dword ptr [rsp+600h+ReturnLength], ebx
0x14000582e  xor     r9d, r9d
0x140005831  lea     rcx, aSmpexecuteimag; "SmpExecuteImage"
0x140005838  mov     edx, 272Bh
0x14000583d  call    SmLogFailureInt
0x140005842  jmp     short loc_14000587D
0x140005844  mov     eax, edi
0x140005846  and     eax, 20h
0x140005849  jnz     short loc_1400058CA
0x14000584b  cmp     dword ptr [rsi+48h], 1
0x14000584f  jz      short loc_14000589A
0x140005851  test    r14d, r14d
0x140005854  jnz     short loc_14000589A
0x140005856  mov     ebx, 0C000007Bh
0x14000585b  test    r15, r15
0x14000585e  jz      short loc_140005866
0x140005860  mov     r8, [r15+8]
0x140005864  jmp     short loc_140005869
0x140005866  mov     r8, r12
0x140005869  mov     r9d, ebx
0x14000586c  lea     rcx, aSmpexecuteimag; "SmpExecuteImage"
0x140005873  mov     edx, 273Bh
0x140005878  call    SmpLogFailureString
0x14000587d  mov     rcx, [rsi+8]; ProcessHandle
0x140005881  mov     edx, ebx; ExitStatus
0x140005883  call    cs:__imp_NtTerminateProcess
0x140005889  mov     rcx, [rsi+8]; Object
0x14000588d  xor     r8d, r8d; Timeout
0x140005890  xor     edx, edx; Alertable
0x140005892  call    cs:__imp_NtWaitForSingleObject
0x140005898  jmp     short loc_1400058D2
0x14000589a  mov     rcx, [rsi+10h]; ThreadHandle
0x14000589e  xor     edx, edx; SuspendCount
0x1400058a0  call    cs:__imp_NtResumeThread
0x1400058a6  test    dil, 2
0x1400058aa  jnz     short loc_1400058C7
0x1400058ac  xor     r8d, r8d; Timeout
0x1400058af  xor     edx, edx; Alertable
0x1400058b1  bt      edi, 10h
0x1400058b5  jnb     short loc_1400058BD
0x1400058b7  mov     rcx, [rsi+8]
  ... truncated ...
```
