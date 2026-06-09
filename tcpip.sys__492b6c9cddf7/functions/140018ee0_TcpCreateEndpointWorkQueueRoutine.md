# TcpCreateEndpointWorkQueueRoutine

- ea: `0x140018ee0`
- end: `0x14001932a`
- name: `TcpCreateEndpointWorkQueueRoutine`
- size: `1098`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f1780`

## callees

- `0x140018ee0`
- `0x140019480`
- `0x1400198a0`
- `0x14003a350`
- `0x14003a490`
- `0x140094c40`
- `0x1400b955c`
- `0x14010c464`
- `0x14014f35c`
- `0x1401bf390`
- `0x1401bf5c0`
- `0x1401bf640`
- `0x1401bf940`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x1400190a8`
- `ntoskrnl!KfRaiseIrql` at `0x1400190a8`
- `ntoskrnl!KeLowerIrql` at `0x140019177`
- `ntoskrnl!KeLowerIrql` at `0x140019177`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140018f32`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x140018f32`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140019117`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140019117`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019167`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140019167`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019100`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400191d1`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019242`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019100`
- `ntoskrnl!PsGetProcessStartKey` at `0x1400191d1`
- `ntoskrnl!PsGetProcessStartKey` at `0x140019242`
- `ntoskrnl!PsGetProcessId` at `0x1400190ee`
- `ntoskrnl!PsGetProcessId` at `0x1400191a8`
- `ntoskrnl!PsGetProcessId` at `0x140019219`
- `ntoskrnl!PsGetProcessId` at `0x14001929c`
- `ntoskrnl!PsGetProcessId` at `0x1400190ee`
- `ntoskrnl!PsGetProcessId` at `0x1400191a8`
- `ntoskrnl!PsGetProcessId` at `0x140019219`
- `ntoskrnl!PsGetProcessId` at `0x14001929c`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001930e`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001930e`

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
0x140018ee0  push    rbp
0x140018ee2  push    rbx
0x140018ee3  push    rsi
0x140018ee4  push    rdi
0x140018ee5  push    r12
0x140018ee7  push    r13
0x140018ee9  push    r14
0x140018eeb  push    r15
0x140018eed  lea     rbp, [rsp-1Fh]
0x140018ef2  sub     rsp, 0E8h
0x140018ef9  mov     rax, cs:__security_cookie
0x140018f00  xor     rax, rsp
0x140018f03  mov     [rbp+57h+var_50], rax
0x140018f07  mov     r12, rcx
0x140018f0a  xor     r13d, r13d
0x140018f0d  mov     r14, 0FFFFF78000000014h
0x140018f17  mov     rcx, [r12-58h]
0x140018f1c  lea     rbx, [r12-90h]
0x140018f24  mov     r12, [r12]
0x140018f28  test    rcx, rcx
0x140018f2b  jz      short loc_140018F3E
0x140018f2d  mov     edx, 1
0x140018f32  call    cs:__imp_ObReferenceSecurityDescriptor
0x140018f39  nop     dword ptr [rax+rax+00h]
0x140018f3e  mov     rax, [rbx+20h]
0x140018f42  lea     rsi, [rbx+50h]
0x140018f46  mov     [rsp+120h+var_E0], rsi
0x140018f4b  mov     r8d, 1
0x140018f51  mov     [rsp+120h+var_E8], r13
0x140018f56  mov     r9d, 6
0x140018f5c  xor     ecx, ecx
0x140018f5e  movzx   edi, word ptr [rax+18h]
0x140018f62  lea     rax, [rbx+0D0h]
0x140018f69  mov     [rsp+120h+var_F0], rax
0x140018f6e  movzx   edx, di
0x140018f71  mov     rax, [rbx+30h]
0x140018f75  mov     [rsp+120h+var_F8], rax
0x140018f7a  mov     rax, [rbx+28h]
0x140018f7e  mov     [rsp+120h+var_100], rax
0x140018f83  call    WfpAleEndpointCreationHandler
0x140018f88  mov     r15d, eax
0x140018f8b  test    eax, eax
0x140018f8d  js      short loc_140018FAE
0x140018f8f  mov     rdx, [rsi]
0x140018f92  mov     r9d, 6
0x140018f98  movzx   r8d, di
0x140018f9c  xor     ecx, ecx
0x140018f9e  call    QimInspectCreateEndpoint
0x140018fa3  mov     r15d, eax
0x140018fa6  test    eax, eax
0x140018fa8  js      loc_14001930B
0x140018fae  cmp     cs:dword_1402201D4, r13d
0x140018fb5  jnz     loc_140019051
0x140018fbb  test    r15d, r15d
0x140018fbe  js      loc_1400190A6
0x140018fc4  cmp     cs:dword_1402201D4, r13d
0x140018fcb  jz      short loc_140018FFE
0x140018fcd  test    byte ptr cs:WPP_MAIN_CB.Reserved, 40h
0x140018fd4  xorps   xmm0, xmm0
0x140018fd7  movups  [rbp+57h+var_60], xmm0
0x140018fdb  jnz     loc_140019215
0x140018fe1  cmp     cs:dword_1402201D4, r13d
0x140018fe8  jz      short loc_140018FFE
0x140018fea  test    byte ptr cs:WPP_MAIN_CB.Reserved, 1
0x140018ff1  xorps   xmm0, xmm0
0x140018ff4  movups  [rbp+57h+var_60], xmm0
0x140018ff8  jnz     loc_140019298
0x140018ffe  mov     rcx, [rbx+0A0h]
0x140019005  mov     edx, r15d
0x140019008  mov     rax, [rbx+98h]
0x14001900f  test    r15d, r15d
0x140019012  js      loc_1400192DD
0x140019018  lea     r9, TcpTlProviderEndpointDispatch
0x14001901f  mov     r8, rbx
0x140019022  call    _guard_dispatch_icall
0x140019027  test    r12, r12
0x14001902a  jnz     loc_140018F17
0x140019030  mov     rcx, [rbp+57h+var_50]
0x140019034  xor     rcx, rsp; StackCookie
0x140019037  call    __security_check_cookie
0x14001903c  add     rsp, 0E8h
0x140019043  pop     r15
0x140019045  pop     r14
0x140019047  pop     r13
0x140019049  pop     r12
0x14001904b  pop     rdi
0x14001904c  pop     rsi
0x14001904d  pop     rbx
0x14001904e  pop     rbp
0x14001904f  retn
0x140019051  test    byte ptr cs:WPP_MAIN_CB+14Ch, 8
0x140019058  xorps   xmm0, xmm0
0x14001905b  movups  [rbp+57h+var_60], xmm0
0x14001905f  jz      loc_140018FBB
0x140019065  mov     dword ptr [rsp+120h+var_E8], r15d
0x14001906a  lea     r8, [rbp+57h+var_60]
0x14001906e  mov     eax, r15d
0x140019071  mov     qword ptr [rbp+57h+var_60], rbx
0x140019075  not     eax
0x140019077  lea     rdx, INET_INSPECT
0x14001907e  shr     eax, 1Fh
0x140019081  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140019088  mov     dword ptr [rsp+120h+var_F0], eax
0x14001908c  mov     r9, rbx
0x14001908f  mov     dword ptr [rsp+120h+var_F8], 10h
0x140019097  mov     [rsp+120h+var_100], rsi
0x14001909c  call    McTemplateK0ppqqq_EtwWriteTransfer
0x1400190a1  jmp     loc_140018FBB
0x1400190a6  mov     cl, 2; NewIrql
0x1400190a8  call    cs:__imp_KfRaiseIrql
0x1400190af  nop     dword ptr [rax+rax+00h]
0x1400190b4  mov     rdi, [rbx+28h]
0x1400190b8  lea     rcx, [rbp+57h+Src]; void *
0x1400190bc  xor     edx, edx; Val
0x1400190be  mov     r8d, 60h ; '`'; Size
0x1400190c4  movzx   esi, al
0x1400190c7  call    memset
0x1400190cc  mov     rdx, [r14]
0x1400190cf  mov     [rbp+57h+var_80], rdx
0x1400190d3  mov     [rbp+57h+var_88], r15d
0x1400190d7  mov     [rbp+57h+var_68], r13d
0x1400190db  mov     [rbp+57h+var_64], 6
0x1400190e2  test    rdi, rdi
0x1400190e5  jz      loc_1400192F7
0x1400190eb  mov     rcx, rdi; Process
0x1400190ee  call    cs:__imp_PsGetProcessId
0x1400190f5  nop     dword ptr [rax+rax+00h]
0x1400190fa  mov     rcx, rdi
0x1400190fd  mov     [rbp+57h+var_78], eax
0x140019100  call    cs:__imp_PsGetProcessStartKey
0x140019107  nop     dword ptr [rax+rax+00h]
0x14001910c  mov     [rbp+57h+var_70], rax
0x140019110  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x140019117  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001911e  nop     dword ptr [rax+rax+00h]
0x140019123  mov     rdx, qword ptr cs:TcpFailureTraceRingBuffer
0x14001912a  mov     ecx, [rdx+8]
0x14001912d  sub     ecx, [rdx+0Ch]
0x140019130  cmp     ecx, [rdx+4]
0x140019133  jz      loc_14001920D
0x140019139  mov     rdi, qword ptr cs:TcpFailureTraceRingBuffer
0x140019140  lea     rdx, [rbp+57h+Src]; Src
0x140019144  mov     ecx, [rdi]
0x140019146  mov     eax, [rdi+4]
0x140019149  mov     r8d, ecx; Size
0x14001914c  dec     eax
0x14001914e  and     eax, [rdi+8]
0x140019151  imul    ecx, eax
0x140019154  add     rcx, [rdi+10h]; void *
0x140019158  call    memmove
0x14001915d  inc     dword ptr [rdi+8]
0x140019160  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x140019167  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001916e  nop     dword ptr [rax+rax+00h]
0x140019173  movzx   ecx, sil; NewIrql
0x140019177  call    cs:__imp_KeLowerIrql
0x14001917e  nop     dword ptr [rax+rax+00h]
0x140019183  cmp     cs:dword_1402201D4, r13d
0x14001918a  jz      loc_140018FFE
0x140019190  cmp     byte ptr cs:WPP_MAIN_CB.Reserved, r13b
0x140019197  xorps   xmm0, xmm0
0x14001919a  movups  [rbp+57h+var_60], xmm0
0x14001919e  jge     loc_140018FE1
0x1400191a4  mov     rcx, [rbx+28h]; Process
0x1400191a8  call    cs:__imp_PsGetProcessId
0x1400191af  nop     dword ptr [rax+rax+00h]
0x1400191b4  mov     rcx, [rbx+20h]
0x1400191b8  mov     r14, rax
0x1400191bb  mov     rdx, [rbx+58h]
0x1400191bf  mov     qword ptr [rbp+57h+var_60+8], r13
0x1400191c3  mov     qword ptr [rbp+57h+var_60], rbx
0x1400191c7  movzx   edi, word ptr [rcx+18h]
0x1400191cb  mov     rcx, [rbx+28h]
0x1400191cf  mov     esi, [rdx]
0x1400191d1  call    cs:__imp_PsGetProcessStartKey
0x1400191d8  nop     dword ptr [rax+rax+00h]
0x1400191dd  mov     [rsp+120h+var_D8], rax
0x1400191e2  lea     r8, [rbp+57h+var_60]
0x1400191e6  mov     dword ptr [rsp+120h+var_E0], edi
0x1400191ea  lea     rdx, TCP_CREATE_ENDPOINT_INSPECTION_FAILURE
0x1400191f1  mov     dword ptr [rsp+120h+var_E8], esi
0x1400191f5  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400191fc  mov     dword ptr [rsp+120h+var_F0], r14d
0x140019201  mov     dword ptr [rsp+120h+var_F8], r15d
0x140019206  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x14001920b  jmp     short loc_140019289
0x14001920d  inc     dword ptr [rdx+0Ch]
0x140019210  jmp     loc_140019139
0x140019215  mov     rcx, [rbx+28h]; Process
0x140019219  call    cs:__imp_PsGetProcessId
0x140019220  nop     dword ptr [rax+rax+00h]
0x140019225  mov     rcx, [rbx+20h]
0x140019229  mov     r14, rax
0x14001922c  mov     rdx, [rbx+58h]
0x140019230  mov     qword ptr [rbp+57h+var_60+8], r13
0x140019234  mov     qword ptr [rbp+57h+var_60], rbx
0x140019238  movzx   edi, word ptr [rcx+18h]
0x14001923c  mov     rcx, [rbx+28h]
0x140019240  mov     esi, [rdx]
0x140019242  call    cs:__imp_PsGetProcessStartKey
0x140019249  nop     dword ptr [rax+rax+00h]
0x14001924e  mov     [rsp+120h+var_D0], rax
0x140019253  mov     r9, rbx
0x140019256  mov     dword ptr [rsp+120h+var_D8], edi
0x14001925a  lea     r8, [rbp+57h+var_60]
0x14001925e  mov     dword ptr [rsp+120h+var_E0], esi
0x140019262  lea     rdx, TCP_CREATE_ENDPOINT_COMPLETE_V2
0x140019269  mov     dword ptr [rsp+120h+var_E8], r14d
0x14001926e  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x140019275  mov     dword ptr [rsp+120h+var_F0], r13d
0x14001927a  mov     [rsp+120h+var_F8], r13
0x14001927f  mov     dword ptr [rsp+120h+var_100], r13d
0x140019284  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x140019289  mov     r14, 0FFFFF78000000014h
0x140019293  jmp     loc_140018FE1
0x140019298  mov     rcx, [rbx+28h]; Process
0x14001929c  call    cs:__imp_PsGetProcessId
0x1400192a3  nop     dword ptr [rax+rax+00h]
0x1400192a8  mov     rcx, [rbx+20h]
0x1400192ac  lea     r8, [rbp+57h+var_60]
0x1400192b0  mov     dword ptr [rsp+120h+var_F0], eax
0x1400192b4  mov     r9d, r15d
0x1400192b7  mov     qword ptr [rbp+57h+var_60+8], r13
0x1400192bb  mov     qword ptr [rbp+57h+var_60], rbx
0x1400192bf  movzx   edx, word ptr [rcx+18h]
0x1400192c3  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x1400192ca  mov     dword ptr [rsp+120h+var_F8], edx
0x1400192ce  mov     [rsp+120h+var_100], rbx
0x1400192d3  call    McTemplateK0qpqq_EtwWriteTransfer
0x1400192d8  jmp     loc_140018FFE
0x1400192dd  xor     r9d, r9d
0x1400192e0  xor     r8d, r8d
0x1400192e3  call    _guard_dispatch_icall
0x1400192e8  xor     edx, edx
0x1400192ea  mov     rcx, rbx; SpinLock
0x1400192ed  call    TcpCloseEndpoint
0x1400192f2  jmp     loc_140019027
0x1400192f7  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x1400192fe  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x140019306  jmp     loc_140019110
0x14001930b  mov     rcx, [rsi]
0x14001930e  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x140019315  nop     dword ptr [rax+rax+00h]
0x14001931a  mov     rcx, [rsi]
0x14001931d  call    WfpAleEndpointTeardownHandler
0x140019322  mov     [rsi], r13
0x140019325  jmp     loc_140018FAE
```
