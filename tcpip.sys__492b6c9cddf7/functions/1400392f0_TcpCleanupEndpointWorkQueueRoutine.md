# TcpCleanupEndpointWorkQueueRoutine

- ea: `0x1400392f0`
- end: `0x14003985a`
- name: `TcpCleanupEndpointWorkQueueRoutine`
- size: `1386`
- prototype: ``
- caller_count: `5`
- callee_count: `19`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14003a660`
- `0x14003abd0`
- `0x14008e2b8`
- `0x1400b5340`
- `0x140162d00`

## callees

- `0x140030580`
- `0x1400392f0`
- `0x140039860`
- `0x140039910`
- `0x14003a1d0`
- `0x14003a2c0`
- `0x14003a350`
- `0x140053e04`
- `0x14005e9d8`
- `0x14005f470`
- `0x14005ffa0`
- `0x1400a2180`
- `0x1400a2450`
- `0x1400e713c`
- `0x1400f5ed8`
- `0x140152ab4`
- `0x1401bdca0`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!IoQueueWorkItem` at `0x140039770`
- `ntoskrnl!IoQueueWorkItem` at `0x140039770`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039479`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x140039479`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003946d`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003946d`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003940c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x14003940c`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400393fb`
- `ntoskrnl!KeEnterCriticalRegion` at `0x1400393fb`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140039521`
- `ntoskrnl!ObDereferenceSecurityDescriptor` at `0x140039521`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140039639`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140039639`
- `ntoskrnl!ObfDereferenceObject` at `0x140039536`
- `ntoskrnl!ObfDereferenceObject` at `0x140039546`
- `ntoskrnl!ObfDereferenceObject` at `0x140039536`
- `ntoskrnl!ObfDereferenceObject` at `0x140039546`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003983f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003983f`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400394da`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400394da`
- `NETIO!NetioNrtDisassociateContext` at `0x14003981f`
- `NETIO!NetioNrtDisassociateContext` at `0x14003981f`

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
      EtwEx_tidActivityInfo(v34, ActivityStop, v41);
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
0x1400392f0  push    rbx
0x1400392f2  push    rbp
0x1400392f3  push    rsi
0x1400392f4  push    rdi
0x1400392f5  push    r12
0x1400392f7  push    r13
0x1400392f9  push    r14
0x1400392fb  push    r15
0x1400392fd  sub     rsp, 88h
0x140039304  mov     rax, cs:__security_cookie
0x14003930b  xor     rax, rsp
0x14003930e  mov     [rsp+0C8h+var_50], rax
0x140039313  mov     r13, rcx
0x140039316  lea     rbp, IpNlpDereferenceLocalAddress
0x14003931d  lea     rsi, IpNlpDereferenceCompartment
0x140039324  mov     rdi, r13
0x140039327  mov     r13, [r13+0]
0x14003932b  add     rdi, 0FFFFFFFFFFFFFF70h
0x140039332  mov     eax, [rdi+10h]
0x140039335  test    al, 20h
0x140039337  jz      loc_14003970E
0x14003933d  mov     eax, [rdi+10h]
0x140039340  and     al, 3
0x140039342  cmp     al, 1
0x140039344  jz      loc_140039670
0x14003934a  mov     rbx, [rdi+60h]
0x14003934e  test    rbx, rbx
0x140039351  jz      short loc_140039398
0x140039353  mov     rax, [rdi+68h]
0x140039357  xorps   xmm0, xmm0
0x14003935a  xorps   xmm1, xmm1
0x14003935d  mov     [rsp+0C8h+var_68], rbx
0x140039362  movdqu  [rsp+0C8h+var_80+8], xmm0
0x140039368  mov     rcx, [rax+28h]; Context
0x14003936c  mov     rax, [rax+30h]
0x140039370  movdqu  [rsp+0C8h+var_60], xmm1
0x140039376  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14003937b  mov     rax, [rax+98h]
0x140039382  cmp     rax, rbp
0x140039385  jnz     loc_14003980D
0x14003938b  call    IppDereferenceNlClient
0x140039390  mov     rcx, rbx
0x140039393  call    IppDereferenceLocalAddress
0x140039398  mov     rcx, [rdi+68h]
0x14003939c  cmp     rcx, [rdi+20h]
0x1400393a0  jz      short loc_1400393A7
0x1400393a2  call    _InetDereferenceAf
0x1400393a7  mov     rax, [rdi+58h]
0x1400393ab  test    rax, rax
0x1400393ae  jz      loc_1400394AC
0x1400393b4  mov     esi, [rax]
0x1400393b6  mov     rbx, cs:TcpCompartmentSet
0x1400393bd  mov     [rsp+0C8h+var_98], 0
0x1400393c2  mov     [rsp+0C8h+var_94], 0
0x1400393ca  cmp     esi, 1
0x1400393cd  jnz     loc_1400397D4
0x1400393d3  mov     rsi, [rbx+148h]
0x1400393da  mov     rax, [rsi+20h]
0x1400393de  xorps   xmm0, xmm0
0x1400393e1  movups  [rsp+0C8h+var_80], xmm0
0x1400393e6  mov     r12d, 5
0x1400393ec  movups  xmmword ptr [rsp+58h], xmm0
0x1400393f1  mov     r14, [rax]
0x1400393f4  xor     eax, eax
0x1400393f6  mov     qword ptr [rsp+0C8h+var_60], rax
0x1400393fb  call    cs:__imp_KeEnterCriticalRegion
0x140039402  nop     dword ptr [rax+rax+00h]
0x140039407  mov     dl, 1; Wait
0x140039409  mov     rcx, r14; Resource
0x14003940c  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140039413  nop     dword ptr [rax+rax+00h]
0x140039418  cmp     cs:PortTrackerEnabled, 0
0x14003941f  lea     rbx, [r14+88h]
0x140039426  jz      short loc_140039447
0x140039428  xor     ebp, ebp
0x14003942a  xor     r12d, r12d
0x14003942d  nop     dword ptr [rax]
0x140039430  mov     rax, [rbx]
0x140039433  test    rax, rax
0x140039436  jz      short loc_14003946A
0x140039438  cmp     [rax+18h], rdi
0x14003943c  jz      loc_140039781
0x140039442  mov     rbx, rax
0x140039445  jmp     short loc_140039430
0x140039447  mov     rcx, [r14+88h]
0x14003944e  test    rcx, rcx
0x140039451  jz      short loc_140039468
0x140039453  cmp     [rcx+18h], rdi
0x140039457  jz      loc_1400397AF
0x14003945d  mov     rbx, rcx
0x140039460  mov     rcx, [rbx]
0x140039463  test    rcx, rcx
0x140039466  jnz     short loc_140039453
0x140039468  xor     ebp, ebp
0x14003946a  mov     rcx, r14; Resource
0x14003946d  call    cs:__imp_ExReleaseResourceLite
0x140039474  nop     dword ptr [rax+rax+00h]
0x140039479  call    cs:__imp_KeLeaveCriticalRegion
0x140039480  nop     dword ptr [rax+rax+00h]
0x140039485  cmp     cs:PortTrackerEnabled, 0
0x14003948c  jnz     loc_1400396A7
0x140039492  cmp     ebp, 105h
0x140039498  jz      loc_1400393FB
0x14003949e  lea     rsi, IpNlpDereferenceCompartment
0x1400394a5  lea     rbp, IpNlpDereferenceLocalAddress
0x1400394ac  mov     rax, [rdi+98h]
0x1400394b3  test    rax, rax
0x1400394b6  jz      short loc_1400394C6
0x1400394b8  mov     rcx, [rdi+0A0h]
0x1400394bf  xor     edx, edx
0x1400394c1  call    _guard_dispatch_icall
0x1400394c6  mov     rbx, [rdi+50h]
0x1400394ca  test    rbx, rbx
0x1400394cd  jz      short loc_1400394EE
0x1400394cf  mov     rcx, rbx
0x1400394d2  call    QimInspectCleanupEndpoint
0x1400394d7  mov     rcx, rbx
0x1400394da  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x1400394e1  nop     dword ptr [rax+rax+00h]
0x1400394e6  mov     rcx, rbx
0x1400394e9  call    WfpAleEndpointTeardownHandler
0x1400394ee  mov     rdx, [rdi+0D0h]
0x1400394f5  test    rdx, rdx
0x1400394f8  jz      short loc_140039503
0x1400394fa  mov     rcx, [rdi+20h]
0x1400394fe  call    InetCleanupSessionInformationAf
0x140039503  mov     rcx, [rdi+0E8h]
0x14003950a  test    rcx, rcx
0x14003950d  jnz     loc_1400396EC
0x140039513  mov     rcx, [rdi+38h]
0x140039517  test    rcx, rcx
0x14003951a  jz      short loc_14003952D
0x14003951c  mov     edx, 1
0x140039521  call    cs:__imp_ObDereferenceSecurityDescriptor
0x140039528  nop     dword ptr [rax+rax+00h]
0x14003952d  mov     rcx, [rdi+30h]; Object
0x140039531  test    rcx, rcx
0x140039534  jz      short loc_140039542
0x140039536  call    cs:__imp_ObfDereferenceObject
0x14003953d  nop     dword ptr [rax+rax+00h]
0x140039542  mov     rcx, [rdi+28h]; Object
0x140039546  call    cs:__imp_ObfDereferenceObject
0x14003954d  nop     dword ptr [rax+rax+00h]
0x140039552  mov     rbx, [rdi+58h]
0x140039556  test    rbx, rbx
0x140039559  jz      short loc_1400395B2
0x14003955b  mov     rax, [rdi+20h]
0x14003955f  mov     [rsp+0C8h+var_70], 0
0x140039568  mov     qword ptr [rsp+0C8h+var_80+8], rbx
0x14003956d  mov     rcx, [rax+28h]; Context
0x140039571  mov     rax, [rax+30h]
0x140039575  mov     qword ptr [rsp+0C8h+var_80], rcx
0x14003957a  mov     rax, [rax+0E0h]
0x140039581  cmp     rax, rsi
0x140039584  jnz     loc_1400397C5
0x14003958a  call    IppDereferenceNlClient
0x14003958f  mov     rax, 0FFFFFFFFFFFFFFFFh
0x140039596  lock xadd [rbx+20h], rax
0x14003959c  sub     rax, 1
0x1400395a0  jg      short loc_1400395B2
0x1400395a2  test    rax, rax
0x1400395a5  jz      loc_140039759
0x1400395ab  mov     ecx, 0Eh
0x1400395b0  int     29h; Win8: RtlFailFast(ecx)
0x1400395b2  lea     rdx, [rdi+120h]
0x1400395b9  cmp     qword ptr [rdx], 0
0x1400395bd  jnz     loc_14003981C
0x1400395c3  mov     rcx, [rdi+128h]; P
0x1400395ca  test    rcx, rcx
0x1400395cd  jnz     loc_14003983A
0x1400395d3  mov     rcx, [rdi+20h]
0x1400395d7  call    _InetDereferenceAf
0x1400395dc  mov     rcx, [rdi+18h]
0x1400395e0  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1400395e7  lock xadd [rcx+10h], rax
0x1400395ed  sub     rax, 1
0x1400395f1  jle     loc_1400396D7
0x1400395f7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400395fd  test    eax, eax
0x1400395ff  jnz     loc_14003971F
0x140039605  mov     eax, gs:1A4h
0x14003960d  mov     rcx, cs:TcpEndpointPool
0x140039614  lea     ebx, [rax+1]
0x140039617  shl     rbx, 7
0x14003961b  add     rbx, rcx
0x14003961e  movzx   eax, byte ptr [rbx+0B0h]
0x140039625  test    al, al
0x140039627  jnz     short loc_140039632
0x140039629  lea     rdx, [rbx+40h]
0x14003962d  call    PplpLazyInitializeLookasideList
0x140039632  mov     rdx, rdi; Entry
0x140039635  lea     rcx, [rbx+40h]; Lookaside
0x140039639  call    cs:__imp_ExFreeToLookasideListEx
0x140039640  nop     dword ptr [rax+rax+00h]
0x140039645  test    r13, r13
0x140039648  jnz     loc_140039324
0x14003964e  mov     rcx, [rsp+0C8h+var_50]
0x140039653  xor     rcx, rsp; StackCookie
0x140039656  call    __security_check_cookie
0x14003965b  add     rsp, 88h
0x140039662  pop     r15
0x140039664  pop     r14
0x140039666  pop     r13
0x140039668  pop     r12
0x14003966a  pop     rdi
0x14003966b  pop     rsi
0x14003966c  pop     rbp
0x14003966d  pop     rbx
0x14003966e  retn
0x140039670  lock dec cs:TcpBoundEndpointCount
0x140039677  mov     r8, [rdi+60h]
0x14003967b  test    r8, r8
0x14003967e  jz      loc_14003934A
0x140039684  movzx   r9d, word ptr [rdi+72h]
0x140039689  lea     rax, [rdi+0A8h]
0x140039690  mov     rdx, [rdi+68h]
0x140039694  mov     rcx, [rdi+20h]
0x140039698  mov     [rsp+0C8h+var_A8], rax
0x14003969d  call    TcpCheckAndDeplumbWakePattern
0x1400396a2  jmp     loc_14003934A
0x1400396a7  xor     esi, esi
0x1400396a9  test    r12d, r12d
0x1400396ac  jz      loc_140039492
0x1400396b2  lea     rbx, [rsp+0C8h+var_80]
0x1400396b7  mov     rcx, [rbx+rsi*8]
0x1400396bb  lea     rbx, [rbx+rsi*8]
0x1400396bf  call    PtClientReleasePortRange
0x1400396c4  inc     esi
0x1400396c6  mov     qword ptr [rbx], 0
0x1400396cd  cmp     esi, r12d
0x1400396d0  jb      short loc_1400396B2
0x1400396d2  jmp     loc_140039492
0x1400396d7  test    rax, rax
0x1400396da  jz      loc_140039850
0x1400396e0  mov     ecx, 0Eh
0x1400396e5  int     29h; Win8: RtlFailFast(ecx)
0x1400396e7  jmp     loc_1400395F7
0x1400396ec  mov     rdx, [rdi+0E0h]
0x1400396f3  test    rdx, rdx
0x1400396f6  jz      short loc_1400396FD
0x1400396f8  call    InetCleanupSessionInformationAf
0x1400396fd  mov     rcx, [rdi+0E8h]
0x140039704  call    _InetDereferenceAf
0x140039709  jmp     loc_140039513
0x14003970e  lea     rcx, aTcpEndpointWas; "TCP_ENDPOINT was cleaned up without bei"...
0x140039715  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14003971a  jmp     loc_14003933D
0x14003971f  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x140039725  mov     [rsp+0C8h+var_88], 0
0x14003972e  mov     [rsp+0C8h+var_90], rdi
0x140039733  test    eax, eax
0x140039735  jz      loc_140039605
0x14003973b  lea     r8, [rsp+0C8h+var_90]
0x140039740  mov     dword ptr [rsp+0C8h+var_A8], 1
0x140039748  lea     rdx, ActivityStop
0x14003974f  call    EtwEx_tidActivityInfo
0x140039754  jmp     loc_140039605
0x140039759  mov     rcx, [rbx+80h]; IoWorkItem
0x140039760  lea     rdx, IppCleanupCompartmentWorkerRoutine; WorkerRoutine
0x140039767  mov     r9, rbx; Context
0x14003976a  mov     r8d, 1; QueueType
0x140039770  call    cs:__imp_IoQueueWorkItem
0x140039777  nop     dword ptr [rax+rax+00h]
0x14003977c  jmp     loc_1400395B2
0x140039781  cmp     r12d, 5
0x140039785  jz      loc_140039830
0x14003978b  mov     rcx, [rax]
0x14003978e  mov     [rbx], rcx
0x140039791  jnb     short loc_14003979F
0x140039793  mov     rcx, [rax+20h]
0x140039797  mov     qword ptr [rsp+r12*8+0C8h+var_80], rcx
0x14003979c  inc     r12d
0x14003979f  mov     rdx, rax
0x1400397a2  mov     rcx, r14
0x1400397a5  call    DeleteExclusion
0x1400397aa  jmp     loc_140039430
0x1400397af  mov     rax, [rcx]
0x1400397b2  mov     rdx, rcx
0x1400397b5  mov     rcx, r14
0x1400397b8  mov     [rbx], rax
0x1400397bb  call    DeleteExclusion
0x1400397c0  jmp     loc_140039460
0x1400397c5  lea     rcx, [rsp+0C8h+var_80]
0x1400397ca  call    _guard_dispatch_icall
0x1400397cf  jmp     loc_1400395B2
0x1400397d4  lea     r8, [rsp+0C8h+var_98]
0x1400397d9  mov     rcx, rbx; SpinLock
0x1400397dc  lea     rdx, [rsp+0C8h+var_94]
0x1400397e1  call    RtlAcquireScalableReadLock
0x1400397e6  xor     r8d, r8d
0x1400397e9  mov     edx, esi
0x1400397eb  mov     rcx, rbx
0x1400397ee  call    InetGetCompartmentUnderLock
0x1400397f3  movzx   r8d, [rsp+0C8h+var_98]
0x1400397f9  mov     rcx, rbx
0x1400397fc  mov     edx, [rsp+0C8h+var_94]
0x140039800  mov     rsi, rax
0x140039803  call    RtlReleaseScalableReadLock
0x140039808  jmp     loc_1400393DA
0x14003980d  lea     rcx, [rsp+0C8h+var_80]
  ... truncated ...
```
