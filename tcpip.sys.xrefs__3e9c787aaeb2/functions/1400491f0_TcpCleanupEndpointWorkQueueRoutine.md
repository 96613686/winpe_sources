# TcpCleanupEndpointWorkQueueRoutine

- ea: `0x1400491f0`
- end: `0x14004975a`
- name: `TcpCleanupEndpointWorkQueueRoutine`
- size: `1386`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140048790`
- `0x140048c10`
- `0x1400a7060`
- `0x1400d71b0`
- `0x140164ac0`

## callees

- `0x140014974`
- `0x14001d418`
- `0x140048f70`
- `0x140049000`
- `0x140049190`
- `0x1400491f0`
- `0x140049760`
- `0x14004a260`
- `0x140072e40`
- `0x140095d30`
- `0x140096000`
- `0x1400b48c8`
- `0x1400b5c30`
- `0x1400b6760`
- `0x1400ed04c`
- `0x140154ad4`
- `0x1401bf9a0`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140049670`
- `ntoskrnl!IoQueueWorkItem` at `0x140049670`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049379`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140049379`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004936d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14004936d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004930c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14004930c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400492fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400492fb`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140049421`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140049421`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140049539`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140049539`
- `ntoskrnl!ObfDereferenceObject` at `0x140049436`
- `ntoskrnl!ObfDereferenceObject` at `0x140049446`
- `ntoskrnl!ObfDereferenceObject` at `0x140049436`
- `ntoskrnl!ObfDereferenceObject` at `0x140049446`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004973f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004973f`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400493da`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400493da`
- `NETIO!NetioNrtDisassociateContext` at `0x14004971f`
- `NETIO!NetioNrtDisassociateContext` at `0x14004971f`

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
  __int64 v34; // r8
  __int64 v35; // r9
  __int64 v36; // rcx
  signed __int64 v37; // rax
  signed __int64 v38; // rax
  char *v39; // rbx
  __int64 v40; // r8
  __int64 i; // rsi
  _QWORD *v42; // rbx
  _QWORD v43[2]; // [rsp+38h] [rbp-90h] BYREF
  _OWORD v44[2]; // [rsp+48h] [rbp-80h] BYREF
  __int128 v45; // [rsp+68h] [rbp-60h]

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
      v40 = v3[12];
      if ( v40 )
        TcpCheckAndDeplumbWakePattern(v3[4], v3[13], v40, *((unsigned __int16 *)v3 + 57), (__int64)(v3 + 21));
    }
    v4 = v3[12];
    if ( v4 )
    {
      v5 = v3[13];
      *((_QWORD *)&v44[1] + 1) = v3[12];
      *(_OWORD *)((char *)v44 + 8) = 0;
      v6 = *(void **)(v5 + 40);
      v7 = *(_QWORD *)(v5 + 48);
      v45 = 0;
      *(_QWORD *)&v44[0] = v6;
      v8 = *(__int64 (__fastcall **)())(v7 + 152);
      if ( v8 == IpNlpDereferenceLocalAddress )
      {
        IppDereferenceNlClient(v6);
        IppDereferenceLocalAddress(v4);
      }
      else
      {
        ((void (__fastcall *)(_OWORD *))v8)(v44);
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
      memset(v44, 0, sizeof(v44));
      LODWORD(v15) = 5;
      v16 = *v14;
      *(_QWORD *)&v45 = 0;
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
                *((_QWORD *)v44 + v15) = v19[4];
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
          for ( i = 0; (unsigned int)i < (unsigned int)v15; *v42 = 0 )
          {
            v42 = (_QWORD *)v44 + i;
            PtClientReleasePortRange(*v42);
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
      *(_QWORD *)&v44[1] = 0;
      *(_QWORD *)&v26 = *(_QWORD *)(v27 + 40);
      v28 = *(_QWORD *)(v27 + 48);
      v44[0] = v26;
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
        ((void (__fastcall *)(_OWORD *))v29)(v44);
      }
    }
    if ( v3[36] )
      NetioNrtDisassociateContext(v3);
    v33 = (void *)v3[37];
    if ( v33 )
      ExFreePoolWithTag(v33, 0x49546354u);
    InetDereferenceAf(v3[4]);
    v36 = v3[3];
    v37 = _InterlockedExchangeAdd64((volatile signed __int64 *)(v36 + 16), 0xFFFFFFFFFFFFFFFFuLL);
    v31 = v37 <= 1;
    v38 = v37 - 1;
    if ( v31 )
    {
      if ( v38 )
        __fastfail(0xEu);
      InetCleanupClient();
    }
    if ( Microsoft_Windows_Networking_CorrelationEnabled )
    {
      v43[1] = 0;
      v43[0] = v3;
      EtwEx_tidActivityInfo(v36, ActivityStop, v43);
    }
    v39 = (char *)TcpEndpointPool + 128 * (unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1);
    if ( !v39[176] )
      PplpLazyInitializeLookasideList(TcpEndpointPool, v39 + 64, v34, v35);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v39 + 64), v3);
  }
  while ( a1 );
}

```

## disassembly

```asm
0x1400491f0  push    rbx
0x1400491f2  push    rbp
0x1400491f3  push    rsi
0x1400491f4  push    rdi
0x1400491f5  push    r12
0x1400491f7  push    r13
0x1400491f9  push    r14
0x1400491fb  push    r15
0x1400491fd  sub     rsp, 88h
0x140049204  mov     rax, cs:__security_cookie
0x14004920b  xor     rax, rsp
0x14004920e  mov     [rsp+0C8h+var_50], rax
0x140049213  mov     r13, rcx
0x140049216  lea     rbp, IpNlpDereferenceLocalAddress
0x14004921d  lea     rsi, IpNlpDereferenceCompartment
0x140049224  mov     rdi, r13
0x140049227  mov     r13, [r13+0]
0x14004922b  add     rdi, 0FFFFFFFFFFFFFF70h
0x140049232  mov     eax, [rdi+10h]
0x140049235  test    al, 20h
0x140049237  jz      loc_14004960E
0x14004923d  mov     eax, [rdi+10h]
0x140049240  and     al, 3
0x140049242  cmp     al, 1
0x140049244  jz      loc_140049570
0x14004924a  mov     rbx, [rdi+60h]
0x14004924e  test    rbx, rbx
0x140049251  jz      short loc_140049298
0x140049253  mov     rax, [rdi+68h]
0x140049257  xorps   xmm0, xmm0
0x14004925a  xorps   xmm1, xmm1
0x14004925d  mov     [rsp+0C8h+var_68], rbx
0x140049262  movdqu  [rsp+0C8h+var_80+8], xmm0
0x140049268  mov     rcx, [rax+28h]; Context
0x14004926c  mov     rax, [rax+30h]
0x140049270  movdqu  [rsp+0C8h+var_60], xmm1
0x140049276  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14004927b  mov     rax, [rax+98h]
0x140049282  cmp     rax, rbp
0x140049285  jnz     loc_14004970D
0x14004928b  call    IppDereferenceNlClient
0x140049290  mov     rcx, rbx
0x140049293  call    IppDereferenceLocalAddress
0x140049298  mov     rcx, [rdi+68h]
0x14004929c  cmp     rcx, [rdi+20h]
0x1400492a0  jz      short loc_1400492A7
0x1400492a2  call    _InetDereferenceAf
0x1400492a7  mov     rax, [rdi+58h]
0x1400492ab  test    rax, rax
0x1400492ae  jz      loc_1400493AC
0x1400492b4  mov     esi, [rax]
0x1400492b6  mov     rbx, cs:TcpCompartmentSet
0x1400492bd  mov     [rsp+0C8h+var_98], 0
0x1400492c2  mov     [rsp+0C8h+var_94], 0
0x1400492ca  cmp     esi, 1
0x1400492cd  jnz     loc_1400496D4
0x1400492d3  mov     rsi, [rbx+148h]
0x1400492da  mov     rax, [rsi+20h]
0x1400492de  xorps   xmm0, xmm0
0x1400492e1  movups  [rsp+0C8h+var_80], xmm0
0x1400492e6  mov     r12d, 5
0x1400492ec  movups  xmmword ptr [rsp+58h], xmm0
0x1400492f1  mov     r14, [rax]
0x1400492f4  xor     eax, eax
0x1400492f6  mov     qword ptr [rsp+0C8h+var_60], rax
0x1400492fb  call    cs:__imp_KeEnterCriticalRegion
0x140049302  nop     dword ptr [rax+rax+00h]
0x140049307  mov     dl, 1; Wait
0x140049309  mov     rcx, r14; Resource
0x14004930c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140049313  nop     dword ptr [rax+rax+00h]
0x140049318  cmp     cs:PortTrackerEnabled, 0
0x14004931f  lea     rbx, [r14+88h]
0x140049326  jz      short loc_140049347
0x140049328  xor     ebp, ebp
0x14004932a  xor     r12d, r12d
0x14004932d  nop     dword ptr [rax]
0x140049330  mov     rax, [rbx]
0x140049333  test    rax, rax
0x140049336  jz      short loc_14004936A
0x140049338  cmp     [rax+18h], rdi
0x14004933c  jz      loc_140049681
0x140049342  mov     rbx, rax
0x140049345  jmp     short loc_140049330
0x140049347  mov     rcx, [r14+88h]
0x14004934e  test    rcx, rcx
0x140049351  jz      short loc_140049368
0x140049353  cmp     [rcx+18h], rdi
0x140049357  jz      loc_1400496AF
0x14004935d  mov     rbx, rcx
0x140049360  mov     rcx, [rbx]
0x140049363  test    rcx, rcx
0x140049366  jnz     short loc_140049353
0x140049368  xor     ebp, ebp
0x14004936a  mov     rcx, r14; Resource
0x14004936d  call    cs:__imp_ExReleaseResourceLite
0x140049374  nop     dword ptr [rax+rax+00h]
0x140049379  call    cs:__imp_KeLeaveCriticalRegion
0x140049380  nop     dword ptr [rax+rax+00h]
0x140049385  cmp     cs:PortTrackerEnabled, 0
0x14004938c  jnz     loc_1400495A7
0x140049392  cmp     ebp, 105h
0x140049398  jz      loc_1400492FB
0x14004939e  lea     rsi, IpNlpDereferenceCompartment
0x1400493a5  lea     rbp, IpNlpDereferenceLocalAddress
0x1400493ac  mov     rax, [rdi+98h]
0x1400493b3  test    rax, rax
0x1400493b6  jz      short loc_1400493C6
0x1400493b8  mov     rcx, [rdi+0A0h]
0x1400493bf  xor     edx, edx
0x1400493c1  call    _guard_dispatch_icall
0x1400493c6  mov     rbx, [rdi+50h]
0x1400493ca  test    rbx, rbx
0x1400493cd  jz      short loc_1400493EE
0x1400493cf  mov     rcx, rbx
0x1400493d2  call    QimInspectCleanupEndpoint
0x1400493d7  mov     rcx, rbx
0x1400493da  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x1400493e1  nop     dword ptr [rax+rax+00h]
0x1400493e6  mov     rcx, rbx
0x1400493e9  call    WfpAleEndpointTeardownHandler
0x1400493ee  mov     rdx, [rdi+0D0h]
0x1400493f5  test    rdx, rdx
0x1400493f8  jz      short loc_140049403
0x1400493fa  mov     rcx, [rdi+20h]
0x1400493fe  call    InetCleanupSessionInformationAf
0x140049403  mov     rcx, [rdi+0E8h]
0x14004940a  test    rcx, rcx
0x14004940d  jnz     loc_1400495EC
0x140049413  mov     rcx, [rdi+38h]
0x140049417  test    rcx, rcx
0x14004941a  jz      short loc_14004942D
0x14004941c  mov     edx, 1
0x140049421  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140049428  nop     dword ptr [rax+rax+00h]
0x14004942d  mov     rcx, [rdi+30h]; Object
0x140049431  test    rcx, rcx
0x140049434  jz      short loc_140049442
0x140049436  call    cs:__imp_ObfDereferenceObject
0x14004943d  nop     dword ptr [rax+rax+00h]
0x140049442  mov     rcx, [rdi+28h]; Object
0x140049446  call    cs:__imp_ObfDereferenceObject
0x14004944d  nop     dword ptr [rax+rax+00h]
0x140049452  mov     rbx, [rdi+58h]
0x140049456  test    rbx, rbx
0x140049459  jz      short loc_1400494B2
0x14004945b  mov     rax, [rdi+20h]
0x14004945f  mov     [rsp+0C8h+var_70], 0
0x140049468  mov     qword ptr [rsp+0C8h+var_80+8], rbx
0x14004946d  mov     rcx, [rax+28h]; Context
0x140049471  mov     rax, [rax+30h]
0x140049475  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14004947a  mov     rax, [rax+0E0h]
0x140049481  cmp     rax, rsi
0x140049484  jnz     loc_1400496C5
0x14004948a  call    IppDereferenceNlClient
0x14004948f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140049496  lock xadd [rbx+20h], rax
0x14004949c  sub     rax, 1
0x1400494a0  jg      short loc_1400494B2
0x1400494a2  test    rax, rax
0x1400494a5  jz      loc_140049659
0x1400494ab  mov     ecx, 0Eh
0x1400494b0  int     29h; Win8: RtlFailFast(ecx)
0x1400494b2  lea     rdx, [rdi+120h]
0x1400494b9  cmp     qword ptr [rdx], 0
0x1400494bd  jnz     loc_14004971C
0x1400494c3  mov     rcx, [rdi+128h]; P
0x1400494ca  test    rcx, rcx
0x1400494cd  jnz     loc_14004973A
0x1400494d3  mov     rcx, [rdi+20h]
0x1400494d7  call    _InetDereferenceAf
0x1400494dc  mov     rcx, [rdi+18h]
0x1400494e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400494e7  lock xadd [rcx+10h], rax
0x1400494ed  sub     rax, 1
0x1400494f1  jle     loc_1400495D7
0x1400494f7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400494fd  test    eax, eax
0x1400494ff  jnz     loc_14004961F
0x140049505  mov     eax, gs:1A4h
0x14004950d  mov     rcx, cs:TcpEndpointPool
0x140049514  lea     ebx, [rax+1]
0x140049517  shl     rbx, 7
0x14004951b  add     rbx, rcx
0x14004951e  movzx   eax, byte ptr [rbx+0B0h]
0x140049525  test    al, al
0x140049527  jnz     short loc_140049532
0x140049529  lea     rdx, [rbx+40h]
0x14004952d  call    PplpLazyInitializeLookasideList
0x140049532  mov     rdx, rdi; Entry
0x140049535  lea     rcx, [rbx+40h]; Lookaside
0x140049539  call    cs:__imp_ExFreeToLookasideListEx
0x140049540  nop     dword ptr [rax+rax+00h]
0x140049545  test    r13, r13
0x140049548  jnz     loc_140049224
0x14004954e  mov     rcx, [rsp+0C8h+var_50]
0x140049553  xor     rcx, rsp; StackCookie
0x140049556  call    __security_check_cookie
0x14004955b  add     rsp, 88h
0x140049562  pop     r15
0x140049564  pop     r14
0x140049566  pop     r13
0x140049568  pop     r12
0x14004956a  pop     rdi
0x14004956b  pop     rsi
0x14004956c  pop     rbp
0x14004956d  pop     rbx
0x14004956e  retn
0x140049570  lock dec cs:TcpBoundEndpointCount
0x140049577  mov     r8, [rdi+60h]
0x14004957b  test    r8, r8
0x14004957e  jz      loc_14004924A
0x140049584  movzx   r9d, word ptr [rdi+72h]
0x140049589  lea     rax, [rdi+0A8h]
0x140049590  mov     rdx, [rdi+68h]
0x140049594  mov     rcx, [rdi+20h]
0x140049598  mov     [rsp+0C8h+var_A8], rax
0x14004959d  call    TcpCheckAndDeplumbWakePattern
0x1400495a2  jmp     loc_14004924A
0x1400495a7  xor     esi, esi
0x1400495a9  test    r12d, r12d
0x1400495ac  jz      loc_140049392
0x1400495b2  lea     rbx, [rsp+0C8h+var_80]
0x1400495b7  mov     rcx, [rbx+rsi*8]
0x1400495bb  lea     rbx, [rbx+rsi*8]
0x1400495bf  call    PtClientReleasePortRange
0x1400495c4  inc     esi
0x1400495c6  mov     qword ptr [rbx], 0
0x1400495cd  cmp     esi, r12d
0x1400495d0  jb      short loc_1400495B2
0x1400495d2  jmp     loc_140049392
0x1400495d7  test    rax, rax
0x1400495da  jz      loc_140049750
0x1400495e0  mov     ecx, 0Eh
0x1400495e5  int     29h; Win8: RtlFailFast(ecx)
0x1400495e7  jmp     loc_1400494F7
0x1400495ec  mov     rdx, [rdi+0E0h]
0x1400495f3  test    rdx, rdx
0x1400495f6  jz      short loc_1400495FD
0x1400495f8  call    InetCleanupSessionInformationAf
0x1400495fd  mov     rcx, [rdi+0E8h]
0x140049604  call    _InetDereferenceAf
0x140049609  jmp     loc_140049413
0x14004960e  lea     rcx, aTcpEndpointWas; "TCP_ENDPOINT was cleaned up without bei"...
0x140049615  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004961a  jmp     loc_14004923D
0x14004961f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140049625  mov     [rsp+0C8h+var_88], 0
0x14004962e  mov     [rsp+0C8h+var_90], rdi
0x140049633  test    eax, eax
0x140049635  jz      loc_140049505
0x14004963b  lea     r8, [rsp+0C8h+var_90]
0x140049640  mov     dword ptr [rsp+0C8h+var_A8], 1
0x140049648  lea     rdx, ActivityStop
0x14004964f  call    EtwEx_tidActivityInfo
0x140049654  jmp     loc_140049505
0x140049659  mov     rcx, [rbx+80h]; IoWorkItem
0x140049660  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140049667  mov     r9, rbx; Context
0x14004966a  mov     r8d, 1; QueueType
0x140049670  call    cs:__imp_IoQueueWorkItem
0x140049677  nop     dword ptr [rax+rax+00h]
0x14004967c  jmp     loc_1400494B2
0x140049681  cmp     r12d, 5
0x140049685  jz      loc_140049730
0x14004968b  mov     rcx, [rax]
0x14004968e  mov     [rbx], rcx
0x140049691  jnb     short loc_14004969F
0x140049693  mov     rcx, [rax+20h]
0x140049697  mov     qword ptr [rsp+r12*8+0C8h+var_80], rcx
0x14004969c  inc     r12d
0x14004969f  mov     rdx, rax
0x1400496a2  mov     rcx, r14
0x1400496a5  call    DeleteExclusion
0x1400496aa  jmp     loc_140049330
0x1400496af  mov     rax, [rcx]
0x1400496b2  mov     rdx, rcx
0x1400496b5  mov     rcx, r14
0x1400496b8  mov     [rbx], rax
0x1400496bb  call    DeleteExclusion
0x1400496c0  jmp     loc_140049360
0x1400496c5  lea     rcx, [rsp+0C8h+var_80]
0x1400496ca  call    _guard_dispatch_icall
0x1400496cf  jmp     loc_1400494B2
0x1400496d4  lea     r8, [rsp+0C8h+var_98]
0x1400496d9  mov     rcx, rbx; SpinLock
0x1400496dc  lea     rdx, [rsp+0C8h+var_94]
0x1400496e1  call    RtlAcquireScalableReadLock
0x1400496e6  xor     r8d, r8d
0x1400496e9  mov     edx, esi
0x1400496eb  mov     rcx, rbx
0x1400496ee  call    InetGetCompartmentUnderLock
0x1400496f3  movzx   r8d, [rsp+0C8h+var_98]
0x1400496f9  mov     rcx, rbx
0x1400496fc  mov     edx, [rsp+0C8h+var_94]
0x140049700  mov     rsi, rax
0x140049703  call    RtlReleaseScalableReadLock
0x140049708  jmp     loc_1400492DA
0x14004970d  lea     rcx, [rsp+0C8h+var_80]
  ... truncated ...
```
