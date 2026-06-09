# TcpCleanupEndpointWorkQueueRoutine

- ea: `0x140039590`
- end: `0x140039afa`
- name: `TcpCleanupEndpointWorkQueueRoutine`
- size: `1386`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003a900`
- `0x14003ae70`
- `0x14008f168`
- `0x1400b4f60`
- `0x140162e40`

## callees

- `0x140030820`
- `0x140039590`
- `0x140039b00`
- `0x140039bb0`
- `0x14003a470`
- `0x14003a560`
- `0x14003a5f0`
- `0x1400540a4`
- `0x14005ec78`
- `0x14005f710`
- `0x140060240`
- `0x1400a3050`
- `0x1400a3320`
- `0x1400e702c`
- `0x1400f5dc8`
- `0x140152bf4`
- `0x1401bdde0`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140039a10`
- `ntoskrnl!IoQueueWorkItem` at `0x140039a10`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039719`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039719`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003970d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003970d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400396ac`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x1400396ac`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003969b`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14003969b`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400397c1`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x1400397c1`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400398d9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400398d9`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397d6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397e6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397d6`
- `ntoskrnl!ObfDereferenceObject` at `0x1400397e6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039adf`
- `ntoskrnl!ExFreePoolWithTag` at `0x140039adf`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14003977a`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14003977a`
- `NETIO!NetioNrtDisassociateContext` at `0x140039abf`
- `NETIO!NetioNrtDisassociateContext` at `0x140039abf`

## pseudocode

```c
void __fastcall TcpCleanupEndpointWorkQueueRoutine(_QWORD *a1)
{
  _QWORD *v2; // rdi
  _QWORD *v3; // rdi
  __int64 v4; // rbx
  __int64 v5; // rax
  void *v6; // rcx
  __int64 v7; // rax
  __int64 (__fastcall *v8)(); // rax
  __int64 v9; // rcx
  unsigned int *v10; // rax
  unsigned int v11; // esi
  PKSPIN_LOCK v12; // rbx
  __int64 CompartmentUnderLock; // rsi
  struct _ERESOURCE **v14; // rax
  __int64 v15; // r12
  struct _ERESOURCE *v16; // r14
  PVOID *p_SharedWaiters; // rbx
  int v18; // ebp
  PVOID *v19; // rax
  PVOID *SharedWaiters; // rcx
  void (__fastcall *v21)(_QWORD, _QWORD); // rax
  __int64 v22; // rbx
  __int64 v23; // rcx
  __int64 v24; // rcx
  void *v25; // rcx
  __int128 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rax
  __int64 (__fastcall *v29)(); // rax
  signed __int64 v30; // rax
  bool v31; // cc
  signed __int64 v32; // rax
  void *v33; // rcx
  __int64 v34; // rcx
  signed __int64 v35; // rax
  signed __int64 v36; // rax
  char *v37; // rbx
  __int64 v38; // r8
  __int64 i; // rsi
  _QWORD *v40; // rbx
  _QWORD v41[2]; // [rsp+38h] [rbp-90h] BYREF
  _OWORD v42[2]; // [rsp+48h] [rbp-80h] BYREF
  __int128 v43; // [rsp+68h] [rbp-60h]

  do
  {
    v2 = a1;
    a1 = (_QWORD *)*a1;
    v3 = v2 - 18;
    if ( (v3[2] & 0x20) == 0 )
      MicrosoftTelemetryAssertTriggeredMsgKM("TCP_ENDPOINT was cleaned up without being closed");
    if ( (v3[2] & 3) == 1 )
    {
      _InterlockedDecrement(&TcpBoundEndpointCount);
      v38 = v3[12];
      if ( v38 )
        TcpCheckAndDeplumbWakePattern(v3[4], v3[13], v38, *((unsigned __int16 *)v3 + 57), (__int64)(v3 + 21));
    }
    v4 = v3[12];
    if ( v4 )
    {
      v5 = v3[13];
      *((_QWORD *)&v42[1] + 1) = v3[12];
      *(_OWORD *)((char *)v42 + 8) = 0;
      v6 = *(void **)(v5 + 40);
      v7 = *(_QWORD *)(v5 + 48);
      v43 = 0;
      *(_QWORD *)&v42[0] = v6;
      v8 = *(__int64 (__fastcall **)())(v7 + 152);
      if ( v8 == IpNlpDereferenceLocalAddress )
      {
        IppDereferenceNlClient(v6);
        IppDereferenceLocalAddress(v4);
      }
      else
      {
        ((void (__fastcall *)(_OWORD *))v8)(v42);
      }
    }
    v9 = v3[13];
    if ( v9 != v3[4] )
      InetDereferenceAf(v9);
    v10 = (unsigned int *)v3[11];
    if ( v10 )
    {
      v11 = *v10;
      v12 = TcpCompartmentSet;
      if ( *v10 == 1 )
      {
        CompartmentUnderLock = TcpCompartmentSet[41];
      }
      else
      {
        RtlAcquireScalableReadLock(TcpCompartmentSet);
        CompartmentUnderLock = InetGetCompartmentUnderLock(v12, v11, 0);
        RtlReleaseScalableReadLock(v12, 0, 0);
      }
      v14 = *(struct _ERESOURCE ***)(CompartmentUnderLock + 32);
      memset(v42, 0, sizeof(v42));
      LODWORD(v15) = 5;
      v16 = *v14;
      *(_QWORD *)&v43 = 0;
      do
      {
        KeEnterCriticalRegion();
        ExAcquireResourceExclusiveLite(v16, 1u);
        p_SharedWaiters = &v16[1].SharedWaiters;
        if ( PortTrackerEnabled )
        {
          v18 = 0;
          v15 = 0;
          while ( 1 )
          {
            v19 = (PVOID *)*p_SharedWaiters;
            if ( !*p_SharedWaiters )
              break;
            if ( v19[3] == v3 )
            {
              if ( (_DWORD)v15 == 5 )
              {
                v18 = 261;
                break;
              }
              *p_SharedWaiters = *v19;
              if ( (unsigned int)v15 < 5 )
              {
                *((_QWORD *)v42 + v15) = v19[4];
                v15 = (unsigned int)(v15 + 1);
              }
              DeleteExclusion(v16, v19);
            }
            else
            {
              p_SharedWaiters = (PVOID *)*p_SharedWaiters;
            }
          }
        }
        else
        {
          SharedWaiters = (PVOID *)v16[1].SharedWaiters;
          if ( SharedWaiters )
          {
            do
            {
              if ( SharedWaiters[3] == v3 )
              {
                *p_SharedWaiters = *SharedWaiters;
                DeleteExclusion(v16, SharedWaiters);
              }
              else
              {
                p_SharedWaiters = SharedWaiters;
              }
              SharedWaiters = (PVOID *)*p_SharedWaiters;
            }
            while ( *p_SharedWaiters );
          }
          v18 = 0;
        }
        ExReleaseResourceLite(v16);
        KeLeaveCriticalRegion();
        if ( PortTrackerEnabled )
        {
          for ( i = 0; (unsigned int)i < (unsigned int)v15; *v40 = 0 )
          {
            v40 = (_QWORD *)v42 + i;
            PtClientReleasePortRange(*v40);
            i = (unsigned int)(i + 1);
          }
        }
      }
      while ( v18 == 261 );
    }
    v21 = (void (__fastcall *)(_QWORD, _QWORD))v3[19];
    if ( v21 )
      v21(v3[20], 0);
    v22 = v3[10];
    if ( v22 )
    {
      QimInspectCleanupEndpoint(v3[10]);
      WfpStreamEndpointCleanupBegin(v22);
      WfpAleEndpointTeardownHandler(v22);
    }
    if ( v3[26] )
      InetCleanupSessionInformationAf(v3[4]);
    v23 = v3[29];
    if ( v23 )
    {
      if ( v3[28] )
        InetCleanupSessionInformationAf(v23);
      InetDereferenceAf(v3[29]);
    }
    v24 = v3[7];
    if ( v24 )
      ObDereferenceSecurityDescriptor(v24, 1);
    v25 = (void *)v3[6];
    if ( v25 )
      ObfDereferenceObject(v25);
    ObfDereferenceObject((PVOID)v3[5]);
    *((_QWORD *)&v26 + 1) = v3[11];
    if ( *((_QWORD *)&v26 + 1) )
    {
      v27 = v3[4];
      *(_QWORD *)&v42[1] = 0;
      *(_QWORD *)&v26 = *(_QWORD *)(v27 + 40);
      v28 = *(_QWORD *)(v27 + 48);
      v42[0] = v26;
      v29 = *(__int64 (__fastcall **)())(v28 + 224);
      if ( v29 == IpNlpDereferenceCompartment )
      {
        IppDereferenceNlClient((PVOID)v26);
        v30 = _InterlockedExchangeAdd64(
                (volatile signed __int64 *)(*((_QWORD *)&v26 + 1) + 32LL),
                0xFFFFFFFFFFFFFFFFuLL);
        v31 = v30 <= 1;
        v32 = v30 - 1;
        if ( v31 )
        {
          if ( v32 )
            __fastfail(0xEu);
          IoQueueWorkItem(
            *(PIO_WORKITEM *)(*((_QWORD *)&v26 + 1) + 128LL),
            IppCleanupCompartmentWorkerRoutine,
            DelayedWorkQueue,
            *((PVOID *)&v26 + 1));
        }
      }
      else
      {
        ((void (__fastcall *)(_OWORD *))v29)(v42);
      }
    }
    if ( v3[36] )
      NetioNrtDisassociateContext(v3);
    v33 = (void *)v3[37];
    if ( v33 )
      ExFreePoolWithTag(v33, 0x49546354u);
    InetDereferenceAf(v3[4]);
    v34 = v3[3];
    v35 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v34 + 16), 0xFFFFFFFFFFFFFFFFuLL);
    v31 = v35 <= 1;
    v36 = v35 - 1;
    if ( v31 )
    {
      if ( v36 )
        __fastfail(0xEu);
      InetCleanupClient((_QWORD *)v34);
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v41[1] = 0;
      v41[0] = v3;
      EtwEx_tidActivityInfo(v34, &ActivityStop, v41);
    }
    v37 = (char *)TcpEndpointPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v37[176] )
      PplpLazyInitializeLookasideList(TcpEndpointPool, v37 + 64);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v37 + 64), v3);
  }
  while ( a1 );
}

```

## disassembly

```asm
0x140039590  push    rbx
0x140039592  push    rbp
0x140039593  push    rsi
0x140039594  push    rdi
0x140039595  push    r12
0x140039597  push    r13
0x140039599  push    r14
0x14003959b  push    r15
0x14003959d  sub     rsp, 88h
0x1400395a4  mov     rax, cs:__security_cookie
0x1400395ab  xor     rax, rsp
0x1400395ae  mov     [rsp+0C8h+var_50], rax
0x1400395b3  mov     r13, rcx
0x1400395b6  lea     rbp, IpNlpDereferenceLocalAddress
0x1400395bd  lea     rsi, IpNlpDereferenceCompartment
0x1400395c4  mov     rdi, r13
0x1400395c7  mov     r13, [r13+0]
0x1400395cb  add     rdi, 0FFFFFFFFFFFFFF70h
0x1400395d2  mov     eax, [rdi+10h]
0x1400395d5  test    al, 20h
0x1400395d7  jz      loc_1400399AE
0x1400395dd  mov     eax, [rdi+10h]
0x1400395e0  and     al, 3
0x1400395e2  cmp     al, 1
0x1400395e4  jz      loc_140039910
0x1400395ea  mov     rbx, [rdi+60h]
0x1400395ee  test    rbx, rbx
0x1400395f1  jz      short loc_140039638
0x1400395f3  mov     rax, [rdi+68h]
0x1400395f7  xorps   xmm0, xmm0
0x1400395fa  xorps   xmm1, xmm1
0x1400395fd  mov     [rsp+0C8h+var_68], rbx
0x140039602  movdqu  [rsp+0C8h+var_80+8], xmm0
0x140039608  mov     rcx, [rax+28h]; Context
0x14003960c  mov     rax, [rax+30h]
0x140039610  movdqu  [rsp+0C8h+var_60], xmm1
0x140039616  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14003961b  mov     rax, [rax+98h]
0x140039622  cmp     rax, rbp
0x140039625  jnz     loc_140039AAD
0x14003962b  call    IppDereferenceNlClient
0x140039630  mov     rcx, rbx
0x140039633  call    IppDereferenceLocalAddress
0x140039638  mov     rcx, [rdi+68h]
0x14003963c  cmp     rcx, [rdi+20h]
0x140039640  jz      short loc_140039647
0x140039642  call    _InetDereferenceAf
0x140039647  mov     rax, [rdi+58h]
0x14003964b  test    rax, rax
0x14003964e  jz      loc_14003974C
0x140039654  mov     esi, [rax]
0x140039656  mov     rbx, cs:TcpCompartmentSet
0x14003965d  mov     [rsp+0C8h+var_98], 0
0x140039662  mov     [rsp+0C8h+var_94], 0
0x14003966a  cmp     esi, 1
0x14003966d  jnz     loc_140039A74
0x140039673  mov     rsi, [rbx+148h]
0x14003967a  mov     rax, [rsi+20h]
0x14003967e  xorps   xmm0, xmm0
0x140039681  movups  [rsp+0C8h+var_80], xmm0
0x140039686  mov     r12d, 5
0x14003968c  movups  xmmword ptr [rsp+58h], xmm0
0x140039691  mov     r14, [rax]
0x140039694  xor     eax, eax
0x140039696  mov     qword ptr [rsp+0C8h+var_60], rax
0x14003969b  call    cs:__imp_KeEnterCriticalRegion
0x1400396a2  nop     dword ptr [rax+rax+00h]
0x1400396a7  mov     dl, 1; Wait
0x1400396a9  mov     rcx, r14; Resource
0x1400396ac  call    cs:__imp_ExAcquireResourceExclusiveLite
0x1400396b3  nop     dword ptr [rax+rax+00h]
0x1400396b8  cmp     cs:PortTrackerEnabled, 0
0x1400396bf  lea     rbx, [r14+88h]
0x1400396c6  jz      short loc_1400396E7
0x1400396c8  xor     ebp, ebp
0x1400396ca  xor     r12d, r12d
0x1400396cd  nop     dword ptr [rax]
0x1400396d0  mov     rax, [rbx]
0x1400396d3  test    rax, rax
0x1400396d6  jz      short loc_14003970A
0x1400396d8  cmp     [rax+18h], rdi
0x1400396dc  jz      loc_140039A21
0x1400396e2  mov     rbx, rax
0x1400396e5  jmp     short loc_1400396D0
0x1400396e7  mov     rcx, [r14+88h]
0x1400396ee  test    rcx, rcx
0x1400396f1  jz      short loc_140039708
0x1400396f3  cmp     [rcx+18h], rdi
0x1400396f7  jz      loc_140039A4F
0x1400396fd  mov     rbx, rcx
0x140039700  mov     rcx, [rbx]
0x140039703  test    rcx, rcx
0x140039706  jnz     short loc_1400396F3
0x140039708  xor     ebp, ebp
0x14003970a  mov     rcx, r14; Resource
0x14003970d  call    cs:__imp_ExReleaseResourceLite
0x140039714  nop     dword ptr [rax+rax+00h]
0x140039719  call    cs:__imp_KeLeaveCriticalRegion
0x140039720  nop     dword ptr [rax+rax+00h]
0x140039725  cmp     cs:PortTrackerEnabled, 0
0x14003972c  jnz     loc_140039947
0x140039732  cmp     ebp, 105h
0x140039738  jz      loc_14003969B
0x14003973e  lea     rsi, IpNlpDereferenceCompartment
0x140039745  lea     rbp, IpNlpDereferenceLocalAddress
0x14003974c  mov     rax, [rdi+98h]
0x140039753  test    rax, rax
0x140039756  jz      short loc_140039766
0x140039758  mov     rcx, [rdi+0A0h]
0x14003975f  xor     edx, edx
0x140039761  call    _guard_dispatch_icall
0x140039766  mov     rbx, [rdi+50h]
0x14003976a  test    rbx, rbx
0x14003976d  jz      short loc_14003978E
0x14003976f  mov     rcx, rbx
0x140039772  call    QimInspectCleanupEndpoint
0x140039777  mov     rcx, rbx
0x14003977a  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x140039781  nop     dword ptr [rax+rax+00h]
0x140039786  mov     rcx, rbx
0x140039789  call    WfpAleEndpointTeardownHandler
0x14003978e  mov     rdx, [rdi+0D0h]
0x140039795  test    rdx, rdx
0x140039798  jz      short loc_1400397A3
0x14003979a  mov     rcx, [rdi+20h]
0x14003979e  call    InetCleanupSessionInformationAf
0x1400397a3  mov     rcx, [rdi+0E8h]
0x1400397aa  test    rcx, rcx
0x1400397ad  jnz     loc_14003998C
0x1400397b3  mov     rcx, [rdi+38h]
0x1400397b7  test    rcx, rcx
0x1400397ba  jz      short loc_1400397CD
0x1400397bc  mov     edx, 1
0x1400397c1  call    cs:__imp_ObDereferenceSecurityDescriptor
0x1400397c8  nop     dword ptr [rax+rax+00h]
0x1400397cd  mov     rcx, [rdi+30h]; Object
0x1400397d1  test    rcx, rcx
0x1400397d4  jz      short loc_1400397E2
0x1400397d6  call    cs:__imp_ObfDereferenceObject
0x1400397dd  nop     dword ptr [rax+rax+00h]
0x1400397e2  mov     rcx, [rdi+28h]; Object
0x1400397e6  call    cs:__imp_ObfDereferenceObject
0x1400397ed  nop     dword ptr [rax+rax+00h]
0x1400397f2  mov     rbx, [rdi+58h]
0x1400397f6  test    rbx, rbx
0x1400397f9  jz      short loc_140039852
0x1400397fb  mov     rax, [rdi+20h]
0x1400397ff  mov     [rsp+0C8h+var_70], 0
0x140039808  mov     qword ptr [rsp+0C8h+var_80+8], rbx
0x14003980d  mov     rcx, [rax+28h]; Context
0x140039811  mov     rax, [rax+30h]
0x140039815  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14003981a  mov     rax, [rax+0E0h]
0x140039821  cmp     rax, rsi
0x140039824  jnz     loc_140039A65
0x14003982a  call    IppDereferenceNlClient
0x14003982f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140039836  lock xadd [rbx+20h], rax
0x14003983c  sub     rax, 1
0x140039840  jg      short loc_140039852
0x140039842  test    rax, rax
0x140039845  jz      loc_1400399F9
0x14003984b  mov     ecx, 0Eh
0x140039850  int     29h; Win8: RtlFailFast(ecx)
0x140039852  lea     rdx, [rdi+120h]
0x140039859  cmp     qword ptr [rdx], 0
0x14003985d  jnz     loc_140039ABC
0x140039863  mov     rcx, [rdi+128h]; P
0x14003986a  test    rcx, rcx
0x14003986d  jnz     loc_140039ADA
0x140039873  mov     rcx, [rdi+20h]
0x140039877  call    _InetDereferenceAf
0x14003987c  mov     rcx, [rdi+18h]
0x140039880  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140039887  lock xadd [rcx+10h], rax
0x14003988d  sub     rax, 1
0x140039891  jle     loc_140039977
0x140039897  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14003989d  test    eax, eax
0x14003989f  jnz     loc_1400399BF
0x1400398a5  mov     eax, gs:1A4h
0x1400398ad  mov     rcx, cs:TcpEndpointPool
0x1400398b4  lea     ebx, [rax+1]
0x1400398b7  shl     rbx, 7
0x1400398bb  add     rbx, rcx
0x1400398be  movzx   eax, byte ptr [rbx+0B0h]
0x1400398c5  test    al, al
0x1400398c7  jnz     short loc_1400398D2
0x1400398c9  lea     rdx, [rbx+40h]
0x1400398cd  call    PplpLazyInitializeLookasideList
0x1400398d2  mov     rdx, rdi; Entry
0x1400398d5  lea     rcx, [rbx+40h]; Lookaside
0x1400398d9  call    cs:__imp_ExFreeToLookasideListEx
0x1400398e0  nop     dword ptr [rax+rax+00h]
0x1400398e5  test    r13, r13
0x1400398e8  jnz     loc_1400395C4
0x1400398ee  mov     rcx, [rsp+0C8h+var_50]
0x1400398f3  xor     rcx, rsp; StackCookie
0x1400398f6  call    __security_check_cookie
0x1400398fb  add     rsp, 88h
0x140039902  pop     r15
0x140039904  pop     r14
0x140039906  pop     r13
0x140039908  pop     r12
0x14003990a  pop     rdi
0x14003990b  pop     rsi
0x14003990c  pop     rbp
0x14003990d  pop     rbx
0x14003990e  retn
0x140039910  lock dec cs:TcpBoundEndpointCount
0x140039917  mov     r8, [rdi+60h]
0x14003991b  test    r8, r8
0x14003991e  jz      loc_1400395EA
0x140039924  movzx   r9d, word ptr [rdi+72h]
0x140039929  lea     rax, [rdi+0A8h]
0x140039930  mov     rdx, [rdi+68h]
0x140039934  mov     rcx, [rdi+20h]
0x140039938  mov     [rsp+0C8h+var_A8], rax
0x14003993d  call    TcpCheckAndDeplumbWakePattern
0x140039942  jmp     loc_1400395EA
0x140039947  xor     esi, esi
0x140039949  test    r12d, r12d
0x14003994c  jz      loc_140039732
0x140039952  lea     rbx, [rsp+0C8h+var_80]
0x140039957  mov     rcx, [rbx+rsi*8]
0x14003995b  lea     rbx, [rbx+rsi*8]
0x14003995f  call    PtClientReleasePortRange
0x140039964  inc     esi
0x140039966  mov     qword ptr [rbx], 0
0x14003996d  cmp     esi, r12d
0x140039970  jb      short loc_140039952
0x140039972  jmp     loc_140039732
0x140039977  test    rax, rax
0x14003997a  jz      loc_140039AF0
0x140039980  mov     ecx, 0Eh
0x140039985  int     29h; Win8: RtlFailFast(ecx)
0x140039987  jmp     loc_140039897
0x14003998c  mov     rdx, [rdi+0E0h]
0x140039993  test    rdx, rdx
0x140039996  jz      short loc_14003999D
0x140039998  call    InetCleanupSessionInformationAf
0x14003999d  mov     rcx, [rdi+0E8h]
0x1400399a4  call    _InetDereferenceAf
0x1400399a9  jmp     loc_1400397B3
0x1400399ae  lea     rcx, aTcpEndpointWas; "TCP_ENDPOINT was cleaned up without bei"...
0x1400399b5  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400399ba  jmp     loc_1400395DD
0x1400399bf  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400399c5  mov     [rsp+0C8h+var_88], 0
0x1400399ce  mov     [rsp+0C8h+var_90], rdi
0x1400399d3  test    eax, eax
0x1400399d5  jz      loc_1400398A5
0x1400399db  lea     r8, [rsp+0C8h+var_90]
0x1400399e0  mov     dword ptr [rsp+0C8h+var_A8], 1
0x1400399e8  lea     rdx, ActivityStop
0x1400399ef  call    EtwEx_tidActivityInfo
0x1400399f4  jmp     loc_1400398A5
0x1400399f9  mov     rcx, [rbx+80h]; IoWorkItem
0x140039a00  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140039a07  mov     r9, rbx; Context
0x140039a0a  mov     r8d, 1; QueueType
0x140039a10  call    cs:__imp_IoQueueWorkItem
0x140039a17  nop     dword ptr [rax+rax+00h]
0x140039a1c  jmp     loc_140039852
0x140039a21  cmp     r12d, 5
0x140039a25  jz      loc_140039AD0
0x140039a2b  mov     rcx, [rax]
0x140039a2e  mov     [rbx], rcx
0x140039a31  jnb     short loc_140039A3F
0x140039a33  mov     rcx, [rax+20h]
0x140039a37  mov     qword ptr [rsp+r12*8+0C8h+var_80], rcx
0x140039a3c  inc     r12d
0x140039a3f  mov     rdx, rax
0x140039a42  mov     rcx, r14
0x140039a45  call    DeleteExclusion
0x140039a4a  jmp     loc_1400396D0
0x140039a4f  mov     rax, [rcx]
0x140039a52  mov     rdx, rcx
0x140039a55  mov     rcx, r14
0x140039a58  mov     [rbx], rax
0x140039a5b  call    DeleteExclusion
0x140039a60  jmp     loc_140039700
0x140039a65  lea     rcx, [rsp+0C8h+var_80]
0x140039a6a  call    _guard_dispatch_icall
0x140039a6f  jmp     loc_140039852
0x140039a74  lea     r8, [rsp+0C8h+var_98]
0x140039a79  mov     rcx, rbx; SpinLock
0x140039a7c  lea     rdx, [rsp+0C8h+var_94]
0x140039a81  call    RtlAcquireScalableReadLock
0x140039a86  xor     r8d, r8d
0x140039a89  mov     edx, esi
0x140039a8b  mov     rcx, rbx
0x140039a8e  call    InetGetCompartmentUnderLock
0x140039a93  movzx   r8d, [rsp+0C8h+var_98]
0x140039a99  mov     rcx, rbx
0x140039a9c  mov     edx, [rsp+0C8h+var_94]
0x140039aa0  mov     rsi, rax
0x140039aa3  call    RtlReleaseScalableReadLock
0x140039aa8  jmp     loc_14003967A
0x140039aad  lea     rcx, [rsp+0C8h+var_80]
  ... truncated ...
```
