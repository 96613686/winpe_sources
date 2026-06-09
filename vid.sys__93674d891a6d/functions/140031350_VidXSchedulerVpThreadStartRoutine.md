# VidXSchedulerVpThreadStartRoutine

- ea: `0x140031350`
- end: `0x140031a13`
- name: `VidXSchedulerVpThreadStartRoutine`
- size: `1731`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x1400030c0`
- `0x140008328`
- `0x140021c60`
- `0x140021db0`
- `0x140024d50`
- `0x1400254a4`
- `0x140031350`
- `0x140034ca4`
- `0x140034e4c`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140031762`
- `ntoskrnl!EtwEventEnabled` at `0x140031762`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400318f4`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400318f4`
- `ntoskrnl!PsTerminateSystemThread` at `0x140031837`
- `ntoskrnl!PsTerminateSystemThread` at `0x140031837`
- `ntoskrnl!ZwSetInformationThread` at `0x140031451`
- `ntoskrnl!ZwSetInformationThread` at `0x140031451`
- `ntoskrnl!ZwQueryInformationThread` at `0x1400313c5`
- `ntoskrnl!ZwQueryInformationThread` at `0x1400313c5`
- `ntoskrnl!KeQueryGroupAffinity` at `0x1400313d5`
- `ntoskrnl!KeQueryGroupAffinity` at `0x1400313d5`
- `ntoskrnl!RtlNumberOfSetBitsUlongPtr` at `0x140031404`
- `ntoskrnl!RtlNumberOfSetBitsUlongPtr` at `0x140031404`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x14003145d`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400317d7`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x14003145d`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400317d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031481`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400317fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031481`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400317fb`
- `ntoskrnl!KeSetEvent` at `0x1400317cb`
- `ntoskrnl!KeSetEvent` at `0x1400317cb`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400318d9`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400318d9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400318bd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400318bd`
- `HAL!KeQueryPerformanceCounter` at `0x140031671`
- `HAL!KeQueryPerformanceCounter` at `0x140031920`
- `HAL!KeQueryPerformanceCounter` at `0x140031671`
- `HAL!KeQueryPerformanceCounter` at `0x140031920`
- `winhvr!WinHvRunVpDispatchLoop` at `0x140031527`
- `winhvr!WinHvRunVpDispatchLoop` at `0x140031527`
- `winhvr!WinHvCancelVpDispatchLoop` at `0x1400319d4`
- `winhvr!WinHvCancelVpDispatchLoop` at `0x1400319d4`
- `winhvr!WinHvSetVpRegisters` at `0x14003188e`
- `winhvr!WinHvSetVpRegisters` at `0x14003188e`

## pseudocode

```c
NTSTATUS __fastcall VidXSchedulerVpThreadStartRoutine(__int64 *a1)
{
  __int64 v1; // rax
  __int64 v2; // rbx
  __int64 *v3; // r13
  KAFFINITY GroupAffinity; // rax
  unsigned __int64 v5; // rbx
  __int64 v6; // rdi
  int i; // edx
  _BYTE *v8; // rsi
  _DWORD *v9; // rbx
  unsigned int v10; // r12d
  __int64 v11; // r15
  unsigned int v12; // edx
  __int64 v13; // r8
  int v14; // eax
  signed __int32 v15; // eax
  __int64 v16; // r9
  LARGE_INTEGER v17; // r14
  signed __int32 v18; // eax
  signed __int32 v19; // ett
  int v20; // r8d
  unsigned __int64 v21; // rdi
  int v22; // ecx
  __int64 v23; // r8
  signed __int32 v25; // eax
  signed __int32 v26; // ett
  KIRQL CurrentIrql; // al
  struct _KDPC *v28; // rcx
  LARGE_INTEGER PerformanceCounter; // rax
  LARGE_INTEGER v30; // rcx
  LONGLONG v31; // rax
  unsigned __int64 v32; // rax
  char v33; // r8
  unsigned int v34; // ecx
  signed __int32 v35; // edx
  int v36; // [rsp+40h] [rbp-69h] BYREF
  __int64 v37; // [rsp+48h] [rbp-61h] BYREF
  __int128 v38; // [rsp+50h] [rbp-59h] BYREF
  __int64 *v39; // [rsp+60h] [rbp-49h]
  __int128 v40; // [rsp+70h] [rbp-39h] BYREF
  LARGE_INTEGER v41; // [rsp+80h] [rbp-29h]
  int v42; // [rsp+88h] [rbp-21h]
  int v43; // [rsp+8Ch] [rbp-1Dh]
  __int64 v44; // [rsp+90h] [rbp-19h]
  LARGE_INTEGER v45; // [rsp+98h] [rbp-11h]
  union _LARGE_INTEGER PerformanceFrequency; // [rsp+A0h] [rbp-9h] BYREF
  int v47; // [rsp+A8h] [rbp-1h]
  int v48; // [rsp+ACh] [rbp+3h]
  struct _GROUP_AFFINITY Affinity; // [rsp+B0h] [rbp+7h] BYREF
  __int128 ThreadInformation; // [rsp+C0h] [rbp+17h] BYREF

  v1 = *((unsigned __int8 *)a1 + 12);
  v2 = *a1;
  Affinity = 0;
  v36 = 0;
  ThreadInformation = 0;
  v3 = a1;
  v39 = a1;
  LODWORD(v37) = 0;
  Affinity.Group = *(_WORD *)(v2 + 16 * v1 + 2184);
  ZwQueryInformationThread(
    (HANDLE)0xFFFFFFFFFFFFFFFELL,
    MaxThreadInfoClass|ThreadPriority,
    &ThreadInformation,
    0x10u,
    0);
  GroupAffinity = KeQueryGroupAffinity(Affinity.Group);
  if ( (_QWORD)ThreadInformation != GroupAffinity )
  {
    Affinity.Mask = GroupAffinity;
    KeSetSystemGroupAffinityThread(&Affinity, 0);
  }
  v5 = *(_QWORD *)(v2 + 16 * (*((unsigned __int8 *)v3 + 12) + 136LL));
  _BitScanForward64((unsigned __int64 *)&v6, v5);
  for ( i = (*(_QWORD *)(*v3 + 648) + (unsigned __int64)*((unsigned int *)v3 + 2)) % RtlNumberOfSetBitsUlongPtr(v5); i; --i )
  {
    v5 ^= 1LL << v6;
    _BitScanForward64((unsigned __int64 *)&v6, v5);
  }
  LOWORD(v36) = Affinity.Group;
  BYTE2(v36) = v6;
  ZwSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, (THREADINFOCLASS)33, &v36, 4u);
  KeReenterRetpolinedCode();
  KeWaitForSingleObject(v3 + 44, Executive, 0, 0, 0);
  while ( !*((_DWORD *)v3 + 94) )
  {
    v8 = (_BYTE *)v3[48];
    v37 = 0;
    v9 = *(_DWORD **)v8;
    v10 = *(_DWORD *)(*(_QWORD *)v8 + 8LL);
    v11 = *(_QWORD *)(**(_QWORD **)v8 + 648LL);
    while ( 1 )
    {
      v12 = 0;
      if ( v8[32] )
      {
        v12 = 1;
        v8[32] = 0;
      }
      v13 = v12 | 2;
      if ( (*(_DWORD *)(*(_QWORD *)v9 + 32LL) & 0x400) == 0 )
        v13 = v12;
      WinHvRunVpDispatchLoop(v11, v10, v13, &v37);
      if ( (_DWORD)v37 != 1 )
        break;
      VidInterceptPreprocess((LARGE_INTEGER *)v9, *((unsigned __int8 **)v9 + 286));
      *((_BYTE *)v9 + 327) = 1;
      if ( v9[142] )
      {
        PerformanceCounter = KeQueryPerformanceCounter((PLARGE_INTEGER)v9 + 70);
        v30 = *(LARGE_INTEGER *)v9;
        *((LARGE_INTEGER *)v9 + 69) = PerformanceCounter;
        v31 = 1000000 * (PerformanceCounter.QuadPart - *((_QWORD *)v9 + 68));
        v9[142] = 0;
        v32 = v31 / *((_QWORD *)v9 + 70);
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v30.QuadPart + 1528) + 1648LL));
        _InterlockedAdd64((volatile signed __int64 *)(*(_QWORD *)(*(_QWORD *)v9 + 1528LL) + 1656LL), v32);
      }
      v14 = (*((__int64 (__fastcall **)(_DWORD *))v9 + 43))(v9);
      if ( v14 )
      {
        if ( v14 != 2 )
          break;
      }
      else
      {
        v48 = 0;
        v41 = *(LARGE_INTEGER *)v9;
        v42 = v9[2];
        v43 = v9[12];
        v47 = v9[128];
        v44 = *((_QWORD *)v9 + 65);
        v45 = *(LARGE_INTEGER *)(v9 + 132);
        PerformanceFrequency = *(union _LARGE_INTEGER *)(v9 + 134);
        v38 = 0;
        v15 = _InterlockedCompareExchange(v9 + 76, 0, 1);
        if ( v15 != 1 )
        {
          do
          {
            v33 = 0;
            v34 = v15 & 0xFFFFFFFE;
            v35 = v15;
            if ( (v15 & 2) != 0 )
            {
              v34 = v15 & 0xFFFFFFFA | 4;
            }
            else if ( (v15 & 8) != 0 )
            {
              v34 = v15 & 0xFFFFFFF6;
              v33 = 1;
            }
            v15 = _InterlockedCompareExchange(v9 + 76, v34, v15);
          }
          while ( v15 != v35 );
          if ( v33 )
          {
            *((_BYTE *)v9 + 326) = 1;
            if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
              WinHvCancelVpDispatchLoop(*(_QWORD *)(*(_QWORD *)v9 + 648LL), (unsigned int)v9[2]);
            VidMessageSlotCancelWait((PRKDPC)v9 + 29);
          }
        }
        if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) == 0 )
          VidVpRegCacheSet(v9, 1, &v38);
        v16 = (unsigned int)v9[143];
        *(_QWORD *)&v38 = 0;
        v9[143] = 0;
        if ( (_DWORD)v16 )
          WinHvSetVpRegisters(*(_QWORD *)(*(_QWORD *)v9 + 648LL), (unsigned int)v9[2], 0, v16, v9 + 144, v9 + 208, &v38);
        if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
          *(_BYTE *)(*((_QWORD *)v9 + 48) + 32LL) = 1;
        v17 = v41;
        if ( (*((_DWORD *)VidDeviceExtension + 162) & 0x20) != 0 )
        {
          *((_BYTE *)v9 + 327) = 0;
          _m_prefetchw(v9 + 488);
          v18 = v9[488];
          do
          {
            v19 = v18;
            v18 = _InterlockedCompareExchange(v9 + 488, v18 | 0x40000000, v18);
          }
          while ( v19 != v18 );
          if ( (v18 & 0x1C00000) == 0x400000 )
          {
            _m_prefetchw(v9 + 488);
            v25 = v9[488];
            do
            {
              v26 = v25;
              v25 = _InterlockedCompareExchange(v9 + 488, v25 | 0x800000, v25);
            }
            while ( v26 != v25 );
            if ( (v25 & 0x20000000) == 0 )
            {
              CurrentIrql = KeGetCurrentIrql();
              v28 = (struct _KDPC *)(v9 + 464);
              if ( CurrentIrql <= 2u )
                VidpMessageSlotEventSignalInternal(v28, 0);
              else
                KeInsertQueueDpc(v28, 0, 0);
            }
          }
        }
        v45 = KeQueryPerformanceCounter(&PerformanceFrequency);
        v20 = 2 * v47;
        v21 = 1000000 * (v45.QuadPart - v44) / PerformanceFrequency.QuadPart;
        _InterlockedIncrement64((volatile signed __int64 *)(*(_QWORD *)(v17.QuadPart + 1528)
                                                          + 8LL * (unsigned int)(2 * v47 + 208)));
        _InterlockedAdd64(
          (volatile signed __int64 *)(*(_QWORD *)(v17.QuadPart + 1528) + 8LL * (unsigned int)(v20 + 209)),
          v21);
        if ( *((_DWORD *)VidDeviceExtension + 451)
          && v21 > 1000 * (unsigned __int64)*((unsigned int *)VidDeviceExtension + 452)
          && (unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))VidRateLimiterCheckRequest)(
                                v17.QuadPart + 16LL * v47 + 1656,
                                PerformanceFrequency.QuadPart
                              * (unsigned __int64)*((unsigned int *)VidDeviceExtension + 453)
                              / 0x3E8,
                                *((unsigned int *)VidDeviceExtension + 454),
                                (LARGE_INTEGER)v45.QuadPart)
          && VID_TRACE_ETW_GUID_Context )
        {
          if ( EtwEventEnabled(VID_TRACE_ETW_GUID_Context, &VID_INTERCEPT_DURATION_THRESHOLD_EXCEEDED) )
          {
            v23 = *(_QWORD *)(v17.QuadPart + 648);
            v40 = *(_OWORD *)(v17.QuadPart + 656);
            VidTraceInterceptDurationThresholdExceededRoutine(
              v22,
              (unsigned int)&v40,
              v23,
              v17.LowPart + 120,
              v42,
              v43,
              v21);
          }
        }
      }
    }
    v3 = v39;
    KeSetEvent((PRKEVENT)(v39[48] + 8), 0, 1u);
    KeReenterRetpolinedCode();
    KeWaitForSingleObject(v3 + 44, Executive, 0, 0, 0);
  }
  return PsTerminateSystemThread(0);
}

```

## disassembly

```asm
0x140031350  push    rbp
0x140031352  push    rbx
0x140031353  push    rdi
0x140031354  push    r13
0x140031356  lea     rbp, [rsp-3Fh]
0x14003135b  sub     rsp, 0E8h
0x140031362  mov     rax, cs:__security_cookie
0x140031369  xor     rax, rsp
0x14003136c  mov     [rbp+57h+var_30], rax
0x140031370  movzx   eax, byte ptr [rcx+0Ch]
0x140031374  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x140031378  mov     rbx, [rcx]
0x14003137b  xorps   xmm0, xmm0
0x14003137e  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x140031382  add     rax, rax
0x140031385  mov     [rbp+57h+var_C0], 0
0x14003138c  movups  [rbp+57h+ThreadInformation], xmm0
0x140031390  mov     r13, rcx
0x140031393  mov     [rbp+57h+var_A0], rcx
0x140031397  mov     r9d, 10h; ThreadInformationLength
0x14003139d  mov     dword ptr [rbp+57h+var_B8], 0
0x1400313a4  movzx   eax, word ptr [rbx+rax*8+888h]
0x1400313ac  mov     edx, 1Eh; ThreadInformationClass
0x1400313b1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400313b8  mov     [rbp+57h+Affinity.Group], ax
0x1400313bc  mov     [rsp+100h+ReturnLength], 0; ReturnLength
0x1400313c5  call    cs:__imp_ZwQueryInformationThread
0x1400313cc  nop     dword ptr [rax+rax+00h]
0x1400313d1  movzx   ecx, [rbp+57h+Affinity.Group]; GroupNumber
0x1400313d5  call    cs:__imp_KeQueryGroupAffinity
0x1400313dc  nop     dword ptr [rax+rax+00h]
0x1400313e1  cmp     qword ptr [rbp+57h+ThreadInformation], rax
0x1400313e5  jnz     loc_1400318EA
0x1400313eb  movzx   eax, byte ptr [r13+0Ch]
0x1400313f0  add     rax, 88h
0x1400313f6  add     rax, rax
0x1400313f9  mov     rbx, [rbx+rax*8]
0x1400313fd  mov     rcx, rbx; Target
0x140031400  bsf     rdi, rbx
0x140031404  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x14003140b  nop     dword ptr [rax+rax+00h]
0x140031410  mov     rcx, [r13+0]
0x140031414  xor     edx, edx
0x140031416  mov     r8d, eax
0x140031419  mov     eax, [r13+8]
0x14003141d  add     rax, [rcx+288h]
0x140031424  div     r8
0x140031427  test    edx, edx
0x140031429  jnz     loc_140031905
0x14003142f  movzx   eax, [rbp+57h+Affinity.Group]
0x140031433  lea     r8, [rbp+57h+var_C0]; ThreadInformation
0x140031437  mov     r9d, 4; ThreadInformationLength
0x14003143d  mov     word ptr [rbp+57h+var_C0], ax
0x140031441  mov     edx, 21h ; '!'; ThreadInformationClass
0x140031446  mov     byte ptr [rbp+57h+var_C0+2], dil
0x14003144a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140031451  call    cs:__imp_ZwSetInformationThread
0x140031458  nop     dword ptr [rax+rax+00h]
0x14003145d  call    cs:__imp_KeReenterRetpolinedCode
0x140031464  nop     dword ptr [rax+rax+00h]
0x140031469  lea     rcx, [r13+160h]; Object
0x140031470  mov     [rsp+100h+ReturnLength], 0; Timeout
0x140031479  xor     r9d, r9d; Alertable
0x14003147c  xor     r8d, r8d; WaitMode
0x14003147f  xor     edx, edx; WaitReason
0x140031481  call    cs:__imp_KeWaitForSingleObject
0x140031488  nop     dword ptr [rax+rax+00h]
0x14003148d  cmp     dword ptr [r13+178h], 0
0x140031495  jnz     loc_140031835
0x14003149b  mov     [rsp+100h+arg_8], rsi
0x1400314a3  mov     [rsp+100h+arg_10], r12
0x1400314ab  mov     [rsp+100h+arg_18], r14
0x1400314b3  mov     [rsp+100h+var_20], r15
0x1400314bb  nop     dword ptr [rax+rax+00h]
0x1400314c0  mov     rsi, [r13+180h]
0x1400314c7  mov     r13, 624DD2F1A9FBE77h
0x1400314d1  mov     [rbp+57h+var_B8], 0
0x1400314d9  mov     rbx, [rsi]
0x1400314dc  mov     rax, [rbx]
0x1400314df  mov     r12d, [rbx+8]
0x1400314e3  mov     r15, [rax+288h]
0x1400314ea  nop     word ptr [rax+rax+00h]
0x1400314f0  movzx   eax, byte ptr [rsi+20h]
0x1400314f4  xor     edx, edx
0x1400314f6  test    al, al
0x1400314f8  jz      short loc_140031503
0x1400314fa  mov     edx, 1
0x1400314ff  mov     byte ptr [rsi+20h], 0
0x140031503  mov     rax, [rbx]
0x140031506  lea     r9, [rbp+57h+var_B8]
0x14003150a  mov     r8d, edx
0x14003150d  or      r8d, 2
0x140031511  mov     ecx, [rax+20h]
0x140031514  and     ecx, 400h
0x14003151a  test    rcx, rcx
0x14003151d  mov     rcx, r15
0x140031520  cmovz   r8d, edx
0x140031524  mov     edx, r12d
0x140031527  call    cs:__imp_WinHvRunVpDispatchLoop
0x14003152e  nop     dword ptr [rax+rax+00h]
0x140031533  cmp     dword ptr [rbp+57h+var_B8], 1
0x140031537  jnz     loc_1400317B7
0x14003153d  mov     rdx, [rbx+8F0h]
0x140031544  mov     rcx, rbx
0x140031547  call    VidInterceptPreprocess
0x14003154c  mov     byte ptr [rbx+147h], 1
0x140031553  cmp     dword ptr [rbx+238h], 0
0x14003155a  jnz     loc_140031919
0x140031560  mov     rax, [rbx+158h]
0x140031567  mov     rcx, rbx
0x14003156a  call    _guard_dispatch_icall
0x14003156f  test    eax, eax
0x140031571  jnz     loc_1400317AE
0x140031577  mov     [rbp+57h+var_54], eax
0x14003157a  xorps   xmm0, xmm0
0x14003157d  mov     rax, [rbx]
0x140031580  xor     ecx, ecx
0x140031582  mov     [rbp+57h+var_80], rax
0x140031586  mov     eax, [rbx+8]
0x140031589  mov     [rbp+57h+var_78], eax
0x14003158c  mov     eax, [rbx+30h]
0x14003158f  mov     [rbp+57h+var_74], eax
0x140031592  mov     eax, [rbx+200h]
0x140031598  mov     [rbp+57h+var_58], eax
0x14003159b  mov     rax, [rbx+208h]
0x1400315a2  mov     [rbp+57h+var_70], rax
0x1400315a6  mov     rax, [rbx+210h]
0x1400315ad  mov     [rbp+57h+var_68], rax
0x1400315b1  mov     rax, [rbx+218h]
0x1400315b8  mov     qword ptr [rbp+57h+PerformanceFrequency], rax
0x1400315bc  mov     eax, 1
0x1400315c1  movups  [rbp+57h+var_B0], xmm0
0x1400315c5  lock cmpxchg [rbx+130h], ecx
0x1400315cd  jnz     loc_14003197D
0x1400315d3  mov     rax, cs:VidDeviceExtension
0x1400315da  mov     eax, [rax+288h]
0x1400315e0  test    al, 20h
0x1400315e2  jz      loc_1400319F1
0x1400315e8  mov     r9d, [rbx+23Ch]
0x1400315ef  mov     qword ptr [rbp+57h+var_B0], 0
0x1400315f7  mov     dword ptr [rbx+23Ch], 0
0x140031601  test    r9d, r9d
0x140031604  jnz     loc_14003185D
0x14003160a  mov     rax, cs:VidDeviceExtension
0x140031611  mov     eax, [rax+288h]
0x140031617  test    al, 20h
0x140031619  jz      short loc_140031626
0x14003161b  mov     rax, [rbx+180h]
0x140031622  mov     byte ptr [rax+20h], 1
0x140031626  mov     rax, cs:VidDeviceExtension
0x14003162d  mov     r14, [rbp+57h+var_80]
0x140031631  mov     eax, [rax+288h]
0x140031637  test    al, 20h
0x140031639  jz      short loc_14003166D
0x14003163b  mov     byte ptr [rbx+147h], 0
0x140031642  lea     rdi, [rbx+740h]
0x140031649  prefetchw byte ptr [rdi+60h]
0x14003164d  mov     eax, [rdi+60h]
0x140031650  mov     ecx, eax
0x140031652  bts     ecx, 1Eh
0x140031656  lock cmpxchg [rdi+60h], ecx
0x14003165b  jnz     short loc_140031650
0x14003165d  and     eax, 1C00000h
0x140031662  cmp     eax, 400000h
0x140031667  jz      loc_14003189F
0x14003166d  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x140031671  call    cs:__imp_KeQueryPerformanceCounter
0x140031678  nop     dword ptr [rax+rax+00h]
0x14003167d  mov     ecx, [rbp+57h+var_58]
0x140031680  mov     [rbp+57h+var_68], rax
0x140031684  sub     rax, [rbp+57h+var_70]
0x140031688  imul    rax, 0F4240h
0x14003168f  lea     r8d, [rcx+rcx]
0x140031693  mov     rcx, [r14+5F8h]
0x14003169a  cqo
0x14003169c  idiv    qword ptr [rbp+57h+PerformanceFrequency]
0x1400316a0  lea     edx, [r8+0D0h]
0x1400316a7  mov     rdi, rax
0x1400316aa  lock inc qword ptr [rcx+rdx*8]
0x1400316af  mov     rcx, [r14+5F8h]
0x1400316b6  lea     edx, [r8+0D1h]
0x1400316bd  lock add [rcx+rdx*8], rdi
0x1400316c2  mov     rcx, cs:VidDeviceExtension
0x1400316c9  mov     eax, [rcx+70Ch]
0x1400316cf  test    eax, eax
0x1400316d1  jz      loc_1400314F0
0x1400316d7  mov     rax, cs:VidDeviceExtension
0x1400316de  mov     ecx, [rax+710h]
0x1400316e4  imul    rcx, 3E8h
0x1400316eb  cmp     rdi, rcx
0x1400316ee  jbe     loc_1400314F0
0x1400316f4  mov     rax, cs:VidDeviceExtension
0x1400316fb  mov     r8d, [rax+718h]
0x140031702  mov     rax, cs:VidDeviceExtension
0x140031709  mov     r10d, [rax+714h]
0x140031710  mov     rax, r13
0x140031713  imul    r10, qword ptr [rbp+57h+PerformanceFrequency]
0x140031718  movsxd  rcx, [rbp+57h+var_58]
0x14003171c  mov     r9, [rbp+57h+var_68]
0x140031720  mul     r10
0x140031723  shl     rcx, 4
0x140031727  sub     r10, rdx
0x14003172a  add     rcx, 678h
0x140031731  shr     r10, 1
0x140031734  add     rcx, r14
0x140031737  add     rdx, r10
0x14003173a  shr     rdx, 9
0x14003173e  call    VidRateLimiterCheckRequest
0x140031743  test    al, al
0x140031745  jz      loc_1400314F0
0x14003174b  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x140031752  test    rcx, rcx
0x140031755  jz      loc_1400314F0
0x14003175b  lea     rdx, VID_INTERCEPT_DURATION_THRESHOLD_EXCEEDED; EventDescriptor
0x140031762  call    cs:__imp_EtwEventEnabled
0x140031769  nop     dword ptr [rax+rax+00h]
0x14003176e  test    al, al
0x140031770  jz      loc_1400314F0
0x140031776  mov     eax, [rbp+57h+var_74]
0x140031779  lea     r9, [r14+78h]
0x14003177d  movups  xmm0, xmmword ptr [r14+290h]
0x140031785  mov     r8, [r14+288h]
0x14003178c  lea     rdx, [rbp+57h+var_90]
0x140031790  mov     [rsp+100h+var_D0], rdi
0x140031795  mov     dword ptr [rsp+100h+var_D8], eax
0x140031799  mov     eax, [rbp+57h+var_78]
0x14003179c  movaps  [rbp+57h+var_90], xmm0
0x1400317a0  mov     dword ptr [rsp+100h+ReturnLength], eax
0x1400317a4  call    VidTraceInterceptDurationThresholdExceededRoutine
0x1400317a9  jmp     loc_1400314F0
0x1400317ae  cmp     eax, 2
0x1400317b1  jz      loc_1400314F0
0x1400317b7  mov     r13, [rbp+57h+var_A0]
0x1400317bb  mov     r8b, 1; Wait
0x1400317be  xor     edx, edx; Increment
0x1400317c0  mov     rcx, [r13+180h]
0x1400317c7  add     rcx, 8; Event
0x1400317cb  call    cs:__imp_KeSetEvent
0x1400317d2  nop     dword ptr [rax+rax+00h]
0x1400317d7  call    cs:__imp_KeReenterRetpolinedCode
0x1400317de  nop     dword ptr [rax+rax+00h]
0x1400317e3  xor     r9d, r9d; Alertable
0x1400317e6  mov     [rsp+100h+ReturnLength], 0; Timeout
0x1400317ef  xor     r8d, r8d; WaitMode
0x1400317f2  lea     rcx, [r13+160h]; Object
0x1400317f9  xor     edx, edx; WaitReason
0x1400317fb  call    cs:__imp_KeWaitForSingleObject
0x140031802  nop     dword ptr [rax+rax+00h]
0x140031807  cmp     dword ptr [r13+178h], 0
0x14003180f  jz      loc_1400314C0
0x140031815  mov     r15, [rsp+100h+var_20]
0x14003181d  mov     r14, [rsp+100h+arg_18]
0x140031825  mov     r12, [rsp+100h+arg_10]
0x14003182d  mov     rsi, [rsp+100h+arg_8]
0x140031835  xor     ecx, ecx; ExitStatus
0x140031837  call    cs:__imp_PsTerminateSystemThread
0x14003183e  nop     dword ptr [rax+rax+00h]
0x140031843  mov     rcx, [rbp+57h+var_30]
0x140031847  xor     rcx, rsp; StackCookie
0x14003184a  call    __security_check_cookie
0x14003184f  add     rsp, 0E8h
0x140031856  pop     r13
0x140031858  pop     rdi
0x140031859  pop     rbx
0x14003185a  pop     rbp
0x14003185b  retn
0x14003185d  mov     rcx, [rbx]
0x140031860  lea     r8, [rbp+57h+var_B0]
0x140031864  mov     [rsp+100h+var_D0], r8
0x140031869  lea     rdx, [rbx+240h]
0x140031870  lea     rax, [rbx+340h]
0x140031877  xor     r8d, r8d
0x14003187a  mov     [rsp+100h+var_D8], rax
0x14003187f  mov     rcx, [rcx+288h]
0x140031886  mov     [rsp+100h+ReturnLength], rdx
0x14003188b  mov     edx, [rbx+8]
0x14003188e  call    cs:__imp_WinHvSetVpRegisters
0x140031895  nop     dword ptr [rax+rax+00h]
0x14003189a  jmp     loc_14003160A
0x14003189f  prefetchw byte ptr [rdi+60h]
0x1400318a3  mov     eax, [rdi+60h]
0x1400318a6  mov     ecx, eax
0x1400318a8  bts     ecx, 17h
0x1400318ac  lock cmpxchg [rdi+60h], ecx
0x1400318b1  jnz     short loc_1400318A6
0x1400318b3  bt      eax, 1Dh
0x1400318b7  jb      loc_14003166D
0x1400318bd  call    cs:__imp_KeGetCurrentIrql
0x1400318c4  nop     dword ptr [rax+rax+00h]
0x1400318c9  mov     rcx, rdi; Dpc
0x1400318cc  cmp     al, 2
0x1400318ce  jbe     loc_140031A07
0x1400318d4  xor     r8d, r8d; SystemArgument2
0x1400318d7  xor     edx, edx; SystemArgument1
0x1400318d9  call    cs:__imp_KeInsertQueueDpc
0x1400318e0  nop     dword ptr [rax+rax+00h]
0x1400318e5  jmp     loc_14003166D
0x1400318ea  xor     edx, edx; PreviousAffinity
0x1400318ec  mov     [rbp+57h+Affinity.Mask], rax
0x1400318f0  lea     rcx, [rbp+57h+Affinity]; Affinity
  ... truncated ...
```
