# TcpCreateEndpointWorkQueueRoutine

- ea: `0x140019180`
- end: `0x1400195ca`
- name: `TcpCreateEndpointWorkQueueRoutine`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f1670`

## callees

- `0x140019180`
- `0x140019720`
- `0x140019b40`
- `0x14003a5f0`
- `0x14003a730`
- `0x140095af0`
- `0x1400b917c`
- `0x14010c5a4`
- `0x14014f49c`
- `0x1401bf4d0`
- `0x1401bf700`
- `0x1401bf780`
- `0x1401bfa80`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x140019348`
- `ntoskrnl!KfRaiseIrql` at `0x140019348`
- `ntoskrnl!KeLowerIrql` at `0x140019417`
- `ntoskrnl!KeLowerIrql` at `0x140019417`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400191d2`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x1400191d2`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400193b7`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400193b7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019407`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019407`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400193a0`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019471`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400194e2`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400193a0`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019471`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400194e2`
- `ntoskrnl!PsGetProcessId` at `0x14001938e`
- `ntoskrnl!PsGetProcessId` at `0x140019448`
- `ntoskrnl!PsGetProcessId` at `0x1400194b9`
- `ntoskrnl!PsGetProcessId` at `0x14001953c`
- `ntoskrnl!PsGetProcessId` at `0x14001938e`
- `ntoskrnl!PsGetProcessId` at `0x140019448`
- `ntoskrnl!PsGetProcessId` at `0x1400194b9`
- `ntoskrnl!PsGetProcessId` at `0x14001953c`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400195ae`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x1400195ae`

## pseudocode

```c
__int64 __fastcall TcpCreateEndpointWorkQueueRoutine(_QWORD *a1)
{
  __int64 v2; // rcx
  KSPIN_LOCK *v3; // rbx
  _QWORD *v4; // rsi
  unsigned __int16 v5; // di
  int Endpoint; // r15d
  KSPIN_LOCK v7; // rcx
  __int64 (__fastcall *v8)(KSPIN_LOCK, _QWORD, KSPIN_LOCK *, __int64 (__fastcall **)()); // rax
  __int64 result; // rax
  KIRQL v10; // al
  struct _KPROCESS *v11; // rdi
  KIRQL v12; // si
  _DWORD *v13; // rdi
  int v14; // r9d
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v16; // rcx
  char v17; // r14
  int *v18; // rdx
  __int16 v19; // di
  int v20; // esi
  char ProcessStartKey; // al
  char v22; // al
  KSPIN_LOCK v23; // rcx
  _QWORD Src[12]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v25; // [rsp+C0h] [rbp-9h] BYREF

  do
  {
    v2 = *(a1 - 11);
    v3 = a1 - 18;
    a1 = (_QWORD *)*a1;
    if ( v2 )
      ObReferenceSecurityDescriptor(v2, 1);
    v4 = v3 + 10;
    v5 = *(_WORD *)(v3[4] + 24);
    Endpoint = WfpAleEndpointCreationHandler(0, v5, 1, 6, v3[5], v3[6], (__int64)(v3 + 26), 0, (__int64)(v3 + 10));
    if ( Endpoint >= 0 )
    {
      Endpoint = QimInspectCreateEndpoint(0, *v4, v5, 6);
      if ( Endpoint < 0 )
      {
        WfpStreamEndpointCleanupBegin(*v4);
        WfpAleEndpointTeardownHandler(*v4);
        *v4 = 0;
      }
    }
    if ( dword_1402201D4 )
    {
      v25 = 0;
      if ( (*((_BYTE *)&WPP_MAIN_CB.Reserved + 12) & 8) != 0 )
      {
        *(_QWORD *)&v25 = v3;
        McTemplateK0ppqqq_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          INET_INSPECT,
          &v25,
          v3,
          v3 + 10,
          16,
          Endpoint >= 0,
          Endpoint);
      }
    }
    if ( Endpoint >= 0 )
    {
      if ( !dword_1402201D4 )
        goto LABEL_14;
      v25 = 0;
      if ( ((__int64)WPP_MAIN_CB.Reserved & 0x40) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)v3[5]);
        v16 = v3[4];
        v17 = ProcessId;
        v18 = (int *)v3[11];
        v25 = (unsigned __int64)v3;
        v19 = *(_WORD *)(v16 + 24);
        v20 = *v18;
        ProcessStartKey = PsGetProcessStartKey(v3[5]);
        McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_COMPLETE_V2,
          (unsigned int)&v25,
          (_DWORD)v3,
          0,
          0,
          0,
          v17,
          v20,
          v19,
          ProcessStartKey);
      }
      goto LABEL_11;
    }
    v10 = KfRaiseIrql(2u);
    v11 = (struct _KPROCESS *)v3[5];
    v12 = v10;
    memset(Src, 0, sizeof(Src));
    Src[8] = MEMORY[0xFFFFF78000000014];
    LODWORD(Src[7]) = Endpoint;
    Src[11] = 0x600000000LL;
    if ( v11 )
    {
      LODWORD(Src[9]) = (unsigned int)PsGetProcessId(v11);
      Src[10] = PsGetProcessStartKey(v11);
    }
    else
    {
      LODWORD(Src[9]) = -1;
      Src[10] = -1;
    }
    KeAcquireSpinLockAtDpcLevel((PKSPIN_LOCK)&TcpFailureTraceRingBuffer + 1);
    if ( *((_DWORD *)TcpFailureTraceRingBuffer + 2) - *((_DWORD *)TcpFailureTraceRingBuffer + 3) == *((_DWORD *)TcpFailureTraceRingBuffer + 1) )
      ++*((_DWORD *)TcpFailureTraceRingBuffer + 3);
    v13 = TcpFailureTraceRingBuffer;
    memmove(
      (void *)(*((_QWORD *)TcpFailureTraceRingBuffer + 2)
             + (*((_DWORD *)TcpFailureTraceRingBuffer + 2)
              & (unsigned int)(*((_DWORD *)TcpFailureTraceRingBuffer + 1) - 1))
             * *(_DWORD *)TcpFailureTraceRingBuffer),
      Src,
      *(unsigned int *)TcpFailureTraceRingBuffer);
    ++v13[2];
    KeReleaseSpinLockFromDpcLevel((PKSPIN_LOCK)&TcpFailureTraceRingBuffer + 1);
    KeLowerIrql(v12);
    if ( dword_1402201D4 )
    {
      v25 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Reserved) < 0 )
      {
        PsGetProcessId((PEPROCESS)v3[5]);
        v25 = (unsigned __int64)v3;
        PsGetProcessStartKey(v3[5]);
        McTemplateK0qbr0qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_INSPECTION_FAILURE,
          (unsigned int)&v25,
          v14);
      }
LABEL_11:
      if ( dword_1402201D4 )
      {
        v25 = 0;
        if ( ((__int64)WPP_MAIN_CB.Reserved & 1) != 0 )
        {
          v22 = (unsigned __int8)PsGetProcessId((PEPROCESS)v3[5]);
          v23 = v3[4];
          v25 = (unsigned __int64)v3;
          McTemplateK0qpqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            *(unsigned __int16 *)(v23 + 24),
            (unsigned int)&v25,
            Endpoint,
            (char)v3,
            *(_WORD *)(v23 + 24),
            v22);
        }
      }
    }
LABEL_14:
    v7 = v3[20];
    v8 = (__int64 (__fastcall *)(KSPIN_LOCK, _QWORD, KSPIN_LOCK *, __int64 (__fastcall **)()))v3[19];
    if ( Endpoint < 0 )
    {
      v8(v7, (unsigned int)Endpoint, 0, 0);
      result = TcpCloseEndpoint(v3);
    }
    else
    {
      result = v8(v7, (unsigned int)Endpoint, v3, TcpTlProviderEndpointDispatch);
    }
  }
  while ( a1 );
  return result;
}

```

## disassembly

```asm
0x140019180  push    rbp
0x140019182  push    rbx
0x140019183  push    rsi
0x140019184  push    rdi
0x140019185  push    r12
0x140019187  push    r13
0x140019189  push    r14
0x14001918b  push    r15
0x14001918d  lea     rbp, [rsp-1Fh]
0x140019192  sub     rsp, 0E8h
0x140019199  mov     rax, cs:__security_cookie
0x1400191a0  xor     rax, rsp
0x1400191a3  mov     [rbp+57h+var_50], rax
0x1400191a7  mov     r12, rcx
0x1400191aa  xor     r13d, r13d
0x1400191ad  mov     r14, 0FFFFF78000000014h
0x1400191b7  mov     rcx, [r12-58h]
0x1400191bc  lea     rbx, [r12-90h]
0x1400191c4  mov     r12, [r12]
0x1400191c8  test    rcx, rcx
0x1400191cb  jz      short loc_1400191DE
0x1400191cd  mov     edx, 1
0x1400191d2  call    cs:__imp_ObReferenceSecurityDescriptor
0x1400191d9  nop     dword ptr [rax+rax+00h]
0x1400191de  mov     rax, [rbx+20h]
0x1400191e2  lea     rsi, [rbx+50h]
0x1400191e6  mov     [rsp+120h+var_E0], rsi
0x1400191eb  mov     r8d, 1
0x1400191f1  mov     [rsp+120h+var_E8], r13
0x1400191f6  mov     r9d, 6
0x1400191fc  xor     ecx, ecx
0x1400191fe  movzx   edi, word ptr [rax+18h]
0x140019202  lea     rax, [rbx+0D0h]
0x140019209  mov     [rsp+120h+var_F0], rax
0x14001920e  movzx   edx, di
0x140019211  mov     rax, [rbx+30h]
0x140019215  mov     [rsp+120h+var_F8], rax
0x14001921a  mov     rax, [rbx+28h]
0x14001921e  mov     [rsp+120h+var_100], rax
0x140019223  call    WfpAleEndpointCreationHandler
0x140019228  mov     r15d, eax
0x14001922b  test    eax, eax
0x14001922d  js      short loc_14001924E
0x14001922f  mov     rdx, [rsi]
0x140019232  mov     r9d, 6
0x140019238  movzx   r8d, di
0x14001923c  xor     ecx, ecx
0x14001923e  call    QimInspectCreateEndpoint
0x140019243  mov     r15d, eax
0x140019246  test    eax, eax
0x140019248  js      loc_1400195AB
0x14001924e  cmp     cs:dword_1402201D4, r13d
0x140019255  jnz     loc_1400192F1
0x14001925b  test    r15d, r15d
0x14001925e  js      loc_140019346
0x140019264  cmp     cs:dword_1402201D4, r13d
0x14001926b  jz      short loc_14001929E
0x14001926d  test    byte ptr cs:WPP_MAIN_CB.Reserved, 40h
0x140019274  xorps   xmm0, xmm0
0x140019277  movups  [rbp+57h+var_60], xmm0
0x14001927b  jnz     loc_1400194B5
0x140019281  cmp     cs:dword_1402201D4, r13d
0x140019288  jz      short loc_14001929E
0x14001928a  test    byte ptr cs:WPP_MAIN_CB.Reserved, 1
0x140019291  xorps   xmm0, xmm0
0x140019294  movups  [rbp+57h+var_60], xmm0
0x140019298  jnz     loc_140019538
0x14001929e  mov     rcx, [rbx+0A0h]
0x1400192a5  mov     edx, r15d
0x1400192a8  mov     rax, [rbx+98h]
0x1400192af  test    r15d, r15d
0x1400192b2  js      loc_14001957D
0x1400192b8  lea     r9, TcpTlProviderEndpointDispatch
0x1400192bf  mov     r8, rbx
0x1400192c2  call    _guard_dispatch_icall
0x1400192c7  test    r12, r12
0x1400192ca  jnz     loc_1400191B7
0x1400192d0  mov     rcx, [rbp+57h+var_50]
0x1400192d4  xor     rcx, rsp; StackCookie
0x1400192d7  call    __security_check_cookie
0x1400192dc  add     rsp, 0E8h
0x1400192e3  pop     r15
0x1400192e5  pop     r14
0x1400192e7  pop     r13
0x1400192e9  pop     r12
0x1400192eb  pop     rdi
0x1400192ec  pop     rsi
0x1400192ed  pop     rbx
0x1400192ee  pop     rbp
0x1400192ef  retn
0x1400192f1  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x1400192f8  xorps   xmm0, xmm0
0x1400192fb  movups  [rbp+57h+var_60], xmm0
0x1400192ff  jz      loc_14001925B
0x140019305  mov     dword ptr [rsp+120h+var_E8], r15d
0x14001930a  lea     r8, [rbp+57h+var_60]
0x14001930e  mov     eax, r15d
0x140019311  mov     qword ptr [rbp+57h+var_60], rbx
0x140019315  not     eax
0x140019317  lea     rdx, INET_INSPECT
0x14001931e  shr     eax, 1Fh
0x140019321  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140019328  mov     dword ptr [rsp+120h+var_F0], eax
0x14001932c  mov     r9, rbx
0x14001932f  mov     dword ptr [rsp+120h+var_F8], 10h
0x140019337  mov     [rsp+120h+var_100], rsi
0x14001933c  call    McTemplateK0ppqqq_EtwWriteTransfer
0x140019341  jmp     loc_14001925B
0x140019346  mov     cl, 2; NewIrql
0x140019348  call    cs:__imp_KfRaiseIrql
0x14001934f  nop     dword ptr [rax+rax+00h]
0x140019354  mov     rdi, [rbx+28h]
0x140019358  lea     rcx, [rbp+57h+Src]; void *
0x14001935c  xor     edx, edx; Val
0x14001935e  mov     r8d, 60h ; '`'; Size
0x140019364  movzx   esi, al
0x140019367  call    memset
0x14001936c  mov     rdx, [r14]
0x14001936f  mov     [rbp+57h+var_80], rdx
0x140019373  mov     [rbp+57h+var_88], r15d
0x140019377  mov     [rbp+57h+var_68], r13d
0x14001937b  mov     [rbp+57h+var_64], 6
0x140019382  test    rdi, rdi
0x140019385  jz      loc_140019597
0x14001938b  mov     rcx, rdi; Process
0x14001938e  call    cs:__imp_PsGetProcessId
0x140019395  nop     dword ptr [rax+rax+00h]
0x14001939a  mov     rcx, rdi
0x14001939d  mov     [rbp+57h+var_78], eax
0x1400193a0  call    cs:__imp_PsGetProcessStartKey
0x1400193a7  nop     dword ptr [rax+rax+00h]
0x1400193ac  mov     [rbp+57h+var_70], rax
0x1400193b0  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x1400193b7  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400193be  nop     dword ptr [rax+rax+00h]
0x1400193c3  mov     rdx, qword ptr cs:TcpFailureTraceRingBuffer
0x1400193ca  mov     ecx, [rdx+8]
0x1400193cd  sub     ecx, [rdx+0Ch]
0x1400193d0  cmp     ecx, [rdx+4]
0x1400193d3  jz      loc_1400194AD
0x1400193d9  mov     rdi, qword ptr cs:TcpFailureTraceRingBuffer
0x1400193e0  lea     rdx, [rbp+57h+Src]; Src
0x1400193e4  mov     ecx, [rdi]
0x1400193e6  mov     eax, [rdi+4]
0x1400193e9  mov     r8d, ecx; Size
0x1400193ec  dec     eax
0x1400193ee  and     eax, [rdi+8]
0x1400193f1  imul    ecx, eax
0x1400193f4  add     rcx, [rdi+10h]; void *
0x1400193f8  call    memmove
0x1400193fd  inc     dword ptr [rdi+8]
0x140019400  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x140019407  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001940e  nop     dword ptr [rax+rax+00h]
0x140019413  movzx   ecx, sil; NewIrql
0x140019417  call    cs:__imp_KeLowerIrql
0x14001941e  nop     dword ptr [rax+rax+00h]
0x140019423  cmp     cs:dword_1402201D4, r13d
0x14001942a  jz      loc_14001929E
0x140019430  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, r13b
0x140019437  xorps   xmm0, xmm0
0x14001943a  movups  [rbp+57h+var_60], xmm0
0x14001943e  jge     loc_140019281
0x140019444  mov     rcx, [rbx+28h]; Process
0x140019448  call    cs:__imp_PsGetProcessId
0x14001944f  nop     dword ptr [rax+rax+00h]
0x140019454  mov     rcx, [rbx+20h]
0x140019458  mov     r14, rax
0x14001945b  mov     rdx, [rbx+58h]
0x14001945f  mov     qword ptr [rbp+57h+var_60+8], r13
0x140019463  mov     qword ptr [rbp+57h+var_60], rbx
0x140019467  movzx   edi, word ptr [rcx+18h]
0x14001946b  mov     rcx, [rbx+28h]
0x14001946f  mov     esi, [rdx]
0x140019471  call    cs:__imp_PsGetProcessStartKey
0x140019478  nop     dword ptr [rax+rax+00h]
0x14001947d  mov     [rsp+120h+var_D8], rax
0x140019482  lea     r8, [rbp+57h+var_60]
0x140019486  mov     dword ptr [rsp+120h+var_E0], edi
0x14001948a  lea     rdx, TCP_CREATE_ENDPOINT_INSPECTION_FAILURE
0x140019491  mov     dword ptr [rsp+120h+var_E8], esi
0x140019495  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001949c  mov     dword ptr [rsp+120h+var_F0], r14d
0x1400194a1  mov     dword ptr [rsp+120h+var_F8], r15d
0x1400194a6  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x1400194ab  jmp     short loc_140019529
0x1400194ad  inc     dword ptr [rdx+0Ch]
0x1400194b0  jmp     loc_1400193D9
0x1400194b5  mov     rcx, [rbx+28h]; Process
0x1400194b9  call    cs:__imp_PsGetProcessId
0x1400194c0  nop     dword ptr [rax+rax+00h]
0x1400194c5  mov     rcx, [rbx+20h]
0x1400194c9  mov     r14, rax
0x1400194cc  mov     rdx, [rbx+58h]
0x1400194d0  mov     qword ptr [rbp+57h+var_60+8], r13
0x1400194d4  mov     qword ptr [rbp+57h+var_60], rbx
0x1400194d8  movzx   edi, word ptr [rcx+18h]
0x1400194dc  mov     rcx, [rbx+28h]
0x1400194e0  mov     esi, [rdx]
0x1400194e2  call    cs:__imp_PsGetProcessStartKey
0x1400194e9  nop     dword ptr [rax+rax+00h]
0x1400194ee  mov     [rsp+120h+var_D0], rax
0x1400194f3  mov     r9, rbx
0x1400194f6  mov     dword ptr [rsp+120h+var_D8], edi
0x1400194fa  lea     r8, [rbp+57h+var_60]
0x1400194fe  mov     dword ptr [rsp+120h+var_E0], esi
0x140019502  lea     rdx, TCP_CREATE_ENDPOINT_COMPLETE_V2
0x140019509  mov     dword ptr [rsp+120h+var_E8], r14d
0x14001950e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140019515  mov     dword ptr [rsp+120h+var_F0], r13d
0x14001951a  mov     [rsp+120h+var_F8], r13
0x14001951f  mov     dword ptr [rsp+120h+var_100], r13d
0x140019524  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x140019529  mov     r14, 0FFFFF78000000014h
0x140019533  jmp     loc_140019281
0x140019538  mov     rcx, [rbx+28h]; Process
0x14001953c  call    cs:__imp_PsGetProcessId
0x140019543  nop     dword ptr [rax+rax+00h]
0x140019548  mov     rcx, [rbx+20h]
0x14001954c  lea     r8, [rbp+57h+var_60]
0x140019550  mov     dword ptr [rsp+120h+var_F0], eax
0x140019554  mov     r9d, r15d
0x140019557  mov     qword ptr [rbp+57h+var_60+8], r13
0x14001955b  mov     qword ptr [rbp+57h+var_60], rbx
0x14001955f  movzx   edx, word ptr [rcx+18h]
0x140019563  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001956a  mov     dword ptr [rsp+120h+var_F8], edx
0x14001956e  mov     [rsp+120h+var_100], rbx
0x140019573  call    McTemplateK0qpqq_EtwWriteTransfer
0x140019578  jmp     loc_14001929E
0x14001957d  xor     r9d, r9d
0x140019580  xor     r8d, r8d
0x140019583  call    _guard_dispatch_icall
0x140019588  xor     edx, edx
0x14001958a  mov     rcx, rbx; SpinLock
0x14001958d  call    TcpCloseEndpoint
0x140019592  jmp     loc_1400192C7
0x140019597  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x14001959e  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x1400195a6  jmp     loc_1400193B0
0x1400195ab  mov     rcx, [rsi]
0x1400195ae  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x1400195b5  nop     dword ptr [rax+rax+00h]
0x1400195ba  mov     rcx, [rsi]
0x1400195bd  call    WfpAleEndpointTeardownHandler
0x1400195c2  mov     [rsi], r13
0x1400195c5  jmp     loc_14001924E
```
