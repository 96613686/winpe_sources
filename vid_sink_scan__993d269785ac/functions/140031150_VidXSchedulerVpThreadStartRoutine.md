# VidXSchedulerVpThreadStartRoutine

- ea: `0x140031150`
- end: `0x140031813`
- name: `VidXSchedulerVpThreadStartRoutine`
- size: `1731`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting, installer_update, broker_com_uri`

## callees

- `0x140003100`
- `0x140008a58`
- `0x140021650`
- `0x1400217a0`
- `0x140024bb0`
- `0x140025304`
- `0x140031150`
- `0x140034a54`
- `0x140034bfc`

## import_xrefs

- `ntoskrnl!EtwEventEnabled` at `0x140031562`
- `ntoskrnl!EtwEventEnabled` at `0x140031562`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400316f4`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x1400316f4`
- `ntoskrnl!PsTerminateSystemThread` at `0x140031637`
- `ntoskrnl!PsTerminateSystemThread` at `0x140031637`
- `ntoskrnl!ZwSetInformationThread` at `0x140031251`
- `ntoskrnl!ZwSetInformationThread` at `0x140031251`
- `ntoskrnl!ZwQueryInformationThread` at `0x1400311c5`
- `ntoskrnl!ZwQueryInformationThread` at `0x1400311c5`
- `ntoskrnl!KeQueryGroupAffinity` at `0x1400311d5`
- `ntoskrnl!KeQueryGroupAffinity` at `0x1400311d5`
- `ntoskrnl!RtlNumberOfSetBitsUlongPtr` at `0x140031204`
- `ntoskrnl!RtlNumberOfSetBitsUlongPtr` at `0x140031204`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x14003125d`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400315d7`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x14003125d`
- `ntoskrnl!KeReenterRetpolinedCode` at `0x1400315d7`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031281`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400315fb`
- `ntoskrnl!KeWaitForSingleObject` at `0x140031281`
- `ntoskrnl!KeWaitForSingleObject` at `0x1400315fb`
- `ntoskrnl!KeSetEvent` at `0x1400315cb`
- `ntoskrnl!KeSetEvent` at `0x1400315cb`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400316d9`
- `ntoskrnl!KeInsertQueueDpc` at `0x1400316d9`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400316bd`
- `ntoskrnl!KeGetCurrentIrql` at `0x1400316bd`
- `HAL!KeQueryPerformanceCounter` at `0x140031471`
- `HAL!KeQueryPerformanceCounter` at `0x140031720`
- `HAL!KeQueryPerformanceCounter` at `0x140031471`
- `HAL!KeQueryPerformanceCounter` at `0x140031720`
- `winhvr!WinHvRunVpDispatchLoop` at `0x140031327`
- `winhvr!WinHvRunVpDispatchLoop` at `0x140031327`
- `winhvr!WinHvCancelVpDispatchLoop` at `0x1400317d4`
- `winhvr!WinHvCancelVpDispatchLoop` at `0x1400317d4`
- `winhvr!WinHvSetVpRegisters` at `0x14003168e`
- `winhvr!WinHvSetVpRegisters` at `0x14003168e`

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
0x140031150  push    rbp
0x140031152  push    rbx
0x140031153  push    rdi
0x140031154  push    r13
0x140031156  lea     rbp, [rsp-3Fh]
0x14003115b  sub     rsp, 0E8h
0x140031162  mov     rax, cs:__security_cookie
0x140031169  xor     rax, rsp
0x14003116c  mov     [rbp+57h+var_30], rax
0x140031170  movzx   eax, byte ptr [rcx+0Ch]
0x140031174  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x140031178  mov     rbx, [rcx]
0x14003117b  xorps   xmm0, xmm0
0x14003117e  movups  xmmword ptr [rbp+57h+Affinity.Mask], xmm0
0x140031182  add     rax, rax
0x140031185  mov     [rbp+57h+var_C0], 0
0x14003118c  movups  [rbp+57h+ThreadInformation], xmm0
0x140031190  mov     r13, rcx
0x140031193  mov     [rbp+57h+var_A0], rcx
0x140031197  mov     r9d, 10h; ThreadInformationLength
0x14003119d  mov     dword ptr [rbp+57h+var_B8], 0
0x1400311a4  movzx   eax, word ptr [rbx+rax*8+888h]
0x1400311ac  mov     edx, 1Eh; ThreadInformationClass
0x1400311b1  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400311b8  mov     [rbp+57h+Affinity.Group], ax
0x1400311bc  mov     [rsp+100h+ReturnLength], 0; ReturnLength
0x1400311c5  call    cs:__imp_ZwQueryInformationThread
0x1400311cc  nop     dword ptr [rax+rax+00h]
0x1400311d1  movzx   ecx, [rbp+57h+Affinity.Group]; GroupNumber
0x1400311d5  call    cs:__imp_KeQueryGroupAffinity
0x1400311dc  nop     dword ptr [rax+rax+00h]
0x1400311e1  cmp     qword ptr [rbp+57h+ThreadInformation], rax
0x1400311e5  jnz     loc_1400316EA
0x1400311eb  movzx   eax, byte ptr [r13+0Ch]
0x1400311f0  add     rax, 88h
0x1400311f6  add     rax, rax
0x1400311f9  mov     rbx, [rbx+rax*8]
0x1400311fd  mov     rcx, rbx; Target
0x140031200  bsf     rdi, rbx
0x140031204  call    cs:__imp_RtlNumberOfSetBitsUlongPtr
0x14003120b  nop     dword ptr [rax+rax+00h]
0x140031210  mov     rcx, [r13+0]
0x140031214  xor     edx, edx
0x140031216  mov     r8d, eax
0x140031219  mov     eax, [r13+8]
0x14003121d  add     rax, [rcx+288h]
0x140031224  div     r8
0x140031227  test    edx, edx
0x140031229  jnz     loc_140031705
0x14003122f  movzx   eax, [rbp+57h+Affinity.Group]
0x140031233  lea     r8, [rbp+57h+var_C0]; ThreadInformation
0x140031237  mov     r9d, 4; ThreadInformationLength
0x14003123d  mov     word ptr [rbp+57h+var_C0], ax
0x140031241  mov     edx, 21h ; '!'; ThreadInformationClass
0x140031246  mov     byte ptr [rbp+57h+var_C0+2], dil
0x14003124a  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140031251  call    cs:__imp_ZwSetInformationThread
0x140031258  nop     dword ptr [rax+rax+00h]
0x14003125d  call    cs:__imp_KeReenterRetpolinedCode
0x140031264  nop     dword ptr [rax+rax+00h]
0x140031269  lea     rcx, [r13+160h]; Object
0x140031270  mov     [rsp+100h+ReturnLength], 0; Timeout
0x140031279  xor     r9d, r9d; Alertable
0x14003127c  xor     r8d, r8d; WaitMode
0x14003127f  xor     edx, edx; WaitReason
0x140031281  call    cs:__imp_KeWaitForSingleObject
0x140031288  nop     dword ptr [rax+rax+00h]
0x14003128d  cmp     dword ptr [r13+178h], 0
0x140031295  jnz     loc_140031635
0x14003129b  mov     [rsp+100h+arg_8], rsi
0x1400312a3  mov     [rsp+100h+arg_10], r12
0x1400312ab  mov     [rsp+100h+arg_18], r14
0x1400312b3  mov     [rsp+100h+var_20], r15
0x1400312bb  nop     dword ptr [rax+rax+00h]
0x1400312c0  mov     rsi, [r13+180h]
0x1400312c7  mov     r13, 624DD2F1A9FBE77h
0x1400312d1  mov     [rbp+57h+var_B8], 0
0x1400312d9  mov     rbx, [rsi]
0x1400312dc  mov     rax, [rbx]
0x1400312df  mov     r12d, [rbx+8]
0x1400312e3  mov     r15, [rax+288h]
0x1400312ea  nop     word ptr [rax+rax+00h]
0x1400312f0  movzx   eax, byte ptr [rsi+20h]
0x1400312f4  xor     edx, edx
0x1400312f6  test    al, al
0x1400312f8  jz      short loc_140031303
0x1400312fa  mov     edx, 1
0x1400312ff  mov     byte ptr [rsi+20h], 0
0x140031303  mov     rax, [rbx]
0x140031306  lea     r9, [rbp+57h+var_B8]
0x14003130a  mov     r8d, edx
0x14003130d  or      r8d, 2
0x140031311  mov     ecx, [rax+20h]
0x140031314  and     ecx, 400h
0x14003131a  test    rcx, rcx
0x14003131d  mov     rcx, r15
0x140031320  cmovz   r8d, edx
0x140031324  mov     edx, r12d
0x140031327  call    cs:__imp_WinHvRunVpDispatchLoop
0x14003132e  nop     dword ptr [rax+rax+00h]
0x140031333  cmp     dword ptr [rbp+57h+var_B8], 1
0x140031337  jnz     loc_1400315B7
0x14003133d  mov     rdx, [rbx+8F0h]
0x140031344  mov     rcx, rbx
0x140031347  call    VidInterceptPreprocess
0x14003134c  mov     byte ptr [rbx+147h], 1
0x140031353  cmp     dword ptr [rbx+238h], 0
0x14003135a  jnz     loc_140031719
0x140031360  mov     rax, [rbx+158h]
0x140031367  mov     rcx, rbx
0x14003136a  call    _guard_dispatch_icall
0x14003136f  test    eax, eax
0x140031371  jnz     loc_1400315AE
0x140031377  mov     [rbp+57h+var_54], eax
0x14003137a  xorps   xmm0, xmm0
0x14003137d  mov     rax, [rbx]
0x140031380  xor     ecx, ecx
0x140031382  mov     [rbp+57h+var_80], rax
0x140031386  mov     eax, [rbx+8]
0x140031389  mov     [rbp+57h+var_78], eax
0x14003138c  mov     eax, [rbx+30h]
0x14003138f  mov     [rbp+57h+var_74], eax
0x140031392  mov     eax, [rbx+200h]
0x140031398  mov     [rbp+57h+var_58], eax
0x14003139b  mov     rax, [rbx+208h]
0x1400313a2  mov     [rbp+57h+var_70], rax
0x1400313a6  mov     rax, [rbx+210h]
0x1400313ad  mov     [rbp+57h+var_68], rax
0x1400313b1  mov     rax, [rbx+218h]
0x1400313b8  mov     qword ptr [rbp+57h+PerformanceFrequency], rax
0x1400313bc  mov     eax, 1
0x1400313c1  movups  [rbp+57h+var_B0], xmm0
0x1400313c5  lock cmpxchg [rbx+130h], ecx
0x1400313cd  jnz     loc_14003177D
0x1400313d3  mov     rax, cs:VidDeviceExtension
0x1400313da  mov     eax, [rax+288h]
0x1400313e0  test    al, 20h
0x1400313e2  jz      loc_1400317F1
0x1400313e8  mov     r9d, [rbx+23Ch]
0x1400313ef  mov     qword ptr [rbp+57h+var_B0], 0
0x1400313f7  mov     dword ptr [rbx+23Ch], 0
0x140031401  test    r9d, r9d
0x140031404  jnz     loc_14003165D
0x14003140a  mov     rax, cs:VidDeviceExtension
0x140031411  mov     eax, [rax+288h]
0x140031417  test    al, 20h
0x140031419  jz      short loc_140031426
0x14003141b  mov     rax, [rbx+180h]
0x140031422  mov     byte ptr [rax+20h], 1
0x140031426  mov     rax, cs:VidDeviceExtension
0x14003142d  mov     r14, [rbp+57h+var_80]
0x140031431  mov     eax, [rax+288h]
0x140031437  test    al, 20h
0x140031439  jz      short loc_14003146D
0x14003143b  mov     byte ptr [rbx+147h], 0
0x140031442  lea     rdi, [rbx+740h]
0x140031449  prefetchw byte ptr [rdi+60h]
0x14003144d  mov     eax, [rdi+60h]
0x140031450  mov     ecx, eax
0x140031452  bts     ecx, 1Eh
0x140031456  lock cmpxchg [rdi+60h], ecx
0x14003145b  jnz     short loc_140031450
0x14003145d  and     eax, 1C00000h
0x140031462  cmp     eax, 400000h
0x140031467  jz      loc_14003169F
0x14003146d  lea     rcx, [rbp+57h+PerformanceFrequency]; PerformanceFrequency
0x140031471  call    cs:__imp_KeQueryPerformanceCounter
0x140031478  nop     dword ptr [rax+rax+00h]
0x14003147d  mov     ecx, [rbp+57h+var_58]
0x140031480  mov     [rbp+57h+var_68], rax
0x140031484  sub     rax, [rbp+57h+var_70]
0x140031488  imul    rax, 0F4240h
0x14003148f  lea     r8d, [rcx+rcx]
0x140031493  mov     rcx, [r14+5F8h]
0x14003149a  cqo
0x14003149c  idiv    qword ptr [rbp+57h+PerformanceFrequency]
0x1400314a0  lea     edx, [r8+0D0h]
0x1400314a7  mov     rdi, rax
0x1400314aa  lock inc qword ptr [rcx+rdx*8]
0x1400314af  mov     rcx, [r14+5F8h]
0x1400314b6  lea     edx, [r8+0D1h]
0x1400314bd  lock add [rcx+rdx*8], rdi
0x1400314c2  mov     rcx, cs:VidDeviceExtension
0x1400314c9  mov     eax, [rcx+70Ch]
0x1400314cf  test    eax, eax
0x1400314d1  jz      loc_1400312F0
0x1400314d7  mov     rax, cs:VidDeviceExtension
0x1400314de  mov     ecx, [rax+710h]
0x1400314e4  imul    rcx, 3E8h
0x1400314eb  cmp     rdi, rcx
0x1400314ee  jbe     loc_1400312F0
0x1400314f4  mov     rax, cs:VidDeviceExtension
0x1400314fb  mov     r8d, [rax+718h]
0x140031502  mov     rax, cs:VidDeviceExtension
0x140031509  mov     r10d, [rax+714h]
0x140031510  mov     rax, r13
0x140031513  imul    r10, qword ptr [rbp+57h+PerformanceFrequency]
0x140031518  movsxd  rcx, [rbp+57h+var_58]
0x14003151c  mov     r9, [rbp+57h+var_68]
0x140031520  mul     r10
0x140031523  shl     rcx, 4
0x140031527  sub     r10, rdx
0x14003152a  add     rcx, 678h
0x140031531  shr     r10, 1
0x140031534  add     rcx, r14
0x140031537  add     rdx, r10
0x14003153a  shr     rdx, 9
0x14003153e  call    VidRateLimiterCheckRequest
0x140031543  test    al, al
0x140031545  jz      loc_1400312F0
0x14003154b  mov     rcx, cs:VID_TRACE_ETW_GUID_Context; RegHandle
0x140031552  test    rcx, rcx
0x140031555  jz      loc_1400312F0
0x14003155b  lea     rdx, VID_INTERCEPT_DURATION_THRESHOLD_EXCEEDED; EventDescriptor
0x140031562  call    cs:__imp_EtwEventEnabled
0x140031569  nop     dword ptr [rax+rax+00h]
0x14003156e  test    al, al
0x140031570  jz      loc_1400312F0
0x140031576  mov     eax, [rbp+57h+var_74]
0x140031579  lea     r9, [r14+78h]
0x14003157d  movups  xmm0, xmmword ptr [r14+290h]
0x140031585  mov     r8, [r14+288h]
0x14003158c  lea     rdx, [rbp+57h+var_90]
0x140031590  mov     [rsp+100h+var_D0], rdi
0x140031595  mov     dword ptr [rsp+100h+var_D8], eax
0x140031599  mov     eax, [rbp+57h+var_78]
0x14003159c  movaps  [rbp+57h+var_90], xmm0
0x1400315a0  mov     dword ptr [rsp+100h+ReturnLength], eax
0x1400315a4  call    VidTraceInterceptDurationThresholdExceededRoutine
0x1400315a9  jmp     loc_1400312F0
0x1400315ae  cmp     eax, 2
0x1400315b1  jz      loc_1400312F0
0x1400315b7  mov     r13, [rbp+57h+var_A0]
0x1400315bb  mov     r8b, 1; Wait
0x1400315be  xor     edx, edx; Increment
0x1400315c0  mov     rcx, [r13+180h]
0x1400315c7  add     rcx, 8; Event
0x1400315cb  call    cs:__imp_KeSetEvent
0x1400315d2  nop     dword ptr [rax+rax+00h]
0x1400315d7  call    cs:__imp_KeReenterRetpolinedCode
0x1400315de  nop     dword ptr [rax+rax+00h]
0x1400315e3  xor     r9d, r9d; Alertable
0x1400315e6  mov     [rsp+100h+ReturnLength], 0; Timeout
0x1400315ef  xor     r8d, r8d; WaitMode
0x1400315f2  lea     rcx, [r13+160h]; Object
0x1400315f9  xor     edx, edx; WaitReason
0x1400315fb  call    cs:__imp_KeWaitForSingleObject
0x140031602  nop     dword ptr [rax+rax+00h]
0x140031607  cmp     dword ptr [r13+178h], 0
0x14003160f  jz      loc_1400312C0
0x140031615  mov     r15, [rsp+100h+var_20]
0x14003161d  mov     r14, [rsp+100h+arg_18]
0x140031625  mov     r12, [rsp+100h+arg_10]
0x14003162d  mov     rsi, [rsp+100h+arg_8]
0x140031635  xor     ecx, ecx; ExitStatus
0x140031637  call    cs:__imp_PsTerminateSystemThread
0x14003163e  nop     dword ptr [rax+rax+00h]
0x140031643  mov     rcx, [rbp+57h+var_30]
0x140031647  xor     rcx, rsp; StackCookie
0x14003164a  call    __security_check_cookie
0x14003164f  add     rsp, 0E8h
0x140031656  pop     r13
0x140031658  pop     rdi
0x140031659  pop     rbx
0x14003165a  pop     rbp
0x14003165b  retn
0x14003165d  mov     rcx, [rbx]
0x140031660  lea     r8, [rbp+57h+var_B0]
0x140031664  mov     [rsp+100h+var_D0], r8
0x140031669  lea     rdx, [rbx+240h]
0x140031670  lea     rax, [rbx+340h]
0x140031677  xor     r8d, r8d
0x14003167a  mov     [rsp+100h+var_D8], rax
0x14003167f  mov     rcx, [rcx+288h]
0x140031686  mov     [rsp+100h+ReturnLength], rdx
0x14003168b  mov     edx, [rbx+8]
0x14003168e  call    cs:__imp_WinHvSetVpRegisters
0x140031695  nop     dword ptr [rax+rax+00h]
0x14003169a  jmp     loc_14003140A
0x14003169f  prefetchw byte ptr [rdi+60h]
0x1400316a3  mov     eax, [rdi+60h]
0x1400316a6  mov     ecx, eax
0x1400316a8  bts     ecx, 17h
0x1400316ac  lock cmpxchg [rdi+60h], ecx
0x1400316b1  jnz     short loc_1400316A6
0x1400316b3  bt      eax, 1Dh
0x1400316b7  jb      loc_14003146D
0x1400316bd  call    cs:__imp_KeGetCurrentIrql
0x1400316c4  nop     dword ptr [rax+rax+00h]
0x1400316c9  mov     rcx, rdi; Dpc
0x1400316cc  cmp     al, 2
0x1400316ce  jbe     loc_140031807
0x1400316d4  xor     r8d, r8d; SystemArgument2
0x1400316d7  xor     edx, edx; SystemArgument1
0x1400316d9  call    cs:__imp_KeInsertQueueDpc
0x1400316e0  nop     dword ptr [rax+rax+00h]
0x1400316e5  jmp     loc_14003146D
0x1400316ea  xor     edx, edx; PreviousAffinity
0x1400316ec  mov     [rbp+57h+Affinity.Mask], rax
0x1400316f0  lea     rcx, [rbp+57h+Affinity]; Affinity
  ... truncated ...
```
