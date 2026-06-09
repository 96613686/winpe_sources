# TcpCreateEndpointWorkQueueRoutine

- ea: `0x14001f820`
- end: `0x14001fc6a`
- name: `TcpCreateEndpointWorkQueueRoutine`
- size: `1098`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1400f7ff0`

## callees

- `0x14001f820`
- `0x14001fdc0`
- `0x1400201e0`
- `0x140048a40`
- `0x140049000`
- `0x14005d040`
- `0x1400f44bc`
- `0x140116164`
- `0x14015109c`
- `0x1401c0fd0`
- `0x1401c1200`
- `0x1401c1280`
- `0x1401c1580`

## import_xrefs

- `ntoskrnl!KfRaiseIrql` at `0x14001f9e8`
- `ntoskrnl!KfRaiseIrql` at `0x14001f9e8`
- `ntoskrnl!KeLowerIrql` at `0x14001fab7`
- `ntoskrnl!KeLowerIrql` at `0x14001fab7`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14001f872`
- `ntoskrnl!ObReferenceSecurityDescriptor` at `0x14001f872`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001fa57`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001fa57`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001faa7`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001faa7`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fa40`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fb11`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fb82`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fa40`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fb11`
- `ntoskrnl!PsGetProcessStartKey` at `0x14001fb82`
- `ntoskrnl!PsGetProcessId` at `0x14001fa2e`
- `ntoskrnl!PsGetProcessId` at `0x14001fae8`
- `ntoskrnl!PsGetProcessId` at `0x14001fb59`
- `ntoskrnl!PsGetProcessId` at `0x14001fbdc`
- `ntoskrnl!PsGetProcessId` at `0x14001fa2e`
- `ntoskrnl!PsGetProcessId` at `0x14001fae8`
- `ntoskrnl!PsGetProcessId` at `0x14001fb59`
- `ntoskrnl!PsGetProcessId` at `0x14001fbdc`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001fc4e`
- `NETIO!WfpStreamEndpointCleanupBegin` at `0x14001fc4e`

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
  unsigned __int8 v14; // al
  KSPIN_LOCK v15; // rcx
  char v16; // r14
  int *v17; // rdx
  __int16 v18; // di
  int v19; // esi
  char v20; // al
  int v21; // r9d
  unsigned __int8 ProcessId; // al
  KSPIN_LOCK v23; // rcx
  char v24; // r14
  int *v25; // rdx
  __int16 v26; // di
  int v27; // esi
  char ProcessStartKey; // al
  char v29; // al
  KSPIN_LOCK v30; // rcx
  int v31; // [rsp+20h] [rbp-A9h]
  _QWORD Src[12]; // [rsp+60h] [rbp-69h] BYREF
  __int128 v33; // [rsp+C0h] [rbp-9h] BYREF

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
    if ( dword_1402241D4 )
    {
      v33 = 0;
      if ( (BYTE4(WPP_MAIN_CB.Dpc.DeferredContext) & 8) != 0 )
      {
        *(_QWORD *)&v33 = v3;
        McTemplateK0ppqqq_EtwWriteTransfer(
          &MICROSOFT_TCPIP_PROVIDER_Context,
          INET_INSPECT,
          &v33,
          v3,
          v3 + 10,
          16,
          Endpoint >= 0,
          Endpoint);
      }
    }
    if ( Endpoint >= 0 )
    {
      if ( !dword_1402241D4 )
        goto LABEL_14;
      v33 = 0;
      if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredRoutine & 0x40) != 0 )
      {
        ProcessId = (unsigned __int8)PsGetProcessId((PEPROCESS)v3[5]);
        v23 = v3[4];
        v24 = ProcessId;
        v25 = (int *)v3[11];
        v33 = (unsigned __int64)v3;
        v26 = *(_WORD *)(v23 + 24);
        v27 = *v25;
        ProcessStartKey = PsGetProcessStartKey(v3[5]);
        McTemplateK0pqbr1qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_COMPLETE_V2,
          (unsigned int)&v33,
          (_DWORD)v3,
          0,
          0,
          0,
          v24,
          v27,
          v26,
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
    if ( dword_1402241D4 )
    {
      v33 = 0;
      if ( SLOBYTE(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
      {
        v14 = (unsigned __int8)PsGetProcessId((PEPROCESS)v3[5]);
        v15 = v3[4];
        v16 = v14;
        v17 = (int *)v3[11];
        v33 = (unsigned __int64)v3;
        v18 = *(_WORD *)(v15 + 24);
        v19 = *v17;
        v20 = PsGetProcessStartKey(v3[5]);
        McTemplateK0qbr0qqqqx_EtwWriteTransfer(
          (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
          (unsigned int)TCP_CREATE_ENDPOINT_INSPECTION_FAILURE,
          (unsigned int)&v33,
          v21,
          v31,
          Endpoint,
          v16,
          v19,
          v18,
          v20);
      }
LABEL_11:
      if ( dword_1402241D4 )
      {
        v33 = 0;
        if ( ((__int64)WPP_MAIN_CB.Dpc.DeferredRoutine & 1) != 0 )
        {
          v29 = (unsigned __int8)PsGetProcessId((PEPROCESS)v3[5]);
          v30 = v3[4];
          v33 = (unsigned __int64)v3;
          McTemplateK0qpqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            *(unsigned __int16 *)(v30 + 24),
            (unsigned int)&v33,
            Endpoint,
            (char)v3,
            *(_WORD *)(v30 + 24),
            v29);
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
0x14001f820  push    rbp
0x14001f822  push    rbx
0x14001f823  push    rsi
0x14001f824  push    rdi
0x14001f825  push    r12
0x14001f827  push    r13
0x14001f829  push    r14
0x14001f82b  push    r15
0x14001f82d  lea     rbp, [rsp-1Fh]
0x14001f832  sub     rsp, 0E8h
0x14001f839  mov     rax, cs:__security_cookie
0x14001f840  xor     rax, rsp
0x14001f843  mov     [rbp+57h+var_50], rax
0x14001f847  mov     r12, rcx
0x14001f84a  xor     r13d, r13d
0x14001f84d  mov     r14, 0FFFFF78000000014h
0x14001f857  mov     rcx, [r12-58h]
0x14001f85c  lea     rbx, [r12-90h]
0x14001f864  mov     r12, [r12]
0x14001f868  test    rcx, rcx
0x14001f86b  jz      short loc_14001F87E
0x14001f86d  mov     edx, 1
0x14001f872  call    cs:__imp_ObReferenceSecurityDescriptor
0x14001f879  nop     dword ptr [rax+rax+00h]
0x14001f87e  mov     rax, [rbx+20h]
0x14001f882  lea     rsi, [rbx+50h]
0x14001f886  mov     [rsp+120h+var_E0], rsi
0x14001f88b  mov     r8d, 1
0x14001f891  mov     [rsp+120h+var_E8], r13
0x14001f896  mov     r9d, 6
0x14001f89c  xor     ecx, ecx
0x14001f89e  movzx   edi, word ptr [rax+18h]
0x14001f8a2  lea     rax, [rbx+0D0h]
0x14001f8a9  mov     [rsp+120h+var_F0], rax
0x14001f8ae  movzx   edx, di
0x14001f8b1  mov     rax, [rbx+30h]
0x14001f8b5  mov     [rsp+120h+var_F8], rax
0x14001f8ba  mov     rax, [rbx+28h]
0x14001f8be  mov     [rsp+120h+var_100], rax
0x14001f8c3  call    WfpAleEndpointCreationHandler
0x14001f8c8  mov     r15d, eax
0x14001f8cb  test    eax, eax
0x14001f8cd  js      short loc_14001F8EE
0x14001f8cf  mov     rdx, [rsi]
0x14001f8d2  mov     r9d, 6
0x14001f8d8  movzx   r8d, di
0x14001f8dc  xor     ecx, ecx
0x14001f8de  call    QimInspectCreateEndpoint
0x14001f8e3  mov     r15d, eax
0x14001f8e6  test    eax, eax
0x14001f8e8  js      loc_14001FC4B
0x14001f8ee  cmp     cs:dword_1402241D4, r13d
0x14001f8f5  jnz     loc_14001F991
0x14001f8fb  test    r15d, r15d
0x14001f8fe  js      loc_14001F9E6
0x14001f904  cmp     cs:dword_1402241D4, r13d
0x14001f90b  jz      short loc_14001F93E
0x14001f90d  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 40h
0x14001f914  xorps   xmm0, xmm0
0x14001f917  movups  [rbp+57h+var_60], xmm0
0x14001f91b  jnz     loc_14001FB55
0x14001f921  cmp     cs:dword_1402241D4, r13d
0x14001f928  jz      short loc_14001F93E
0x14001f92a  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, 1
0x14001f931  xorps   xmm0, xmm0
0x14001f934  movups  [rbp+57h+var_60], xmm0
0x14001f938  jnz     loc_14001FBD8
0x14001f93e  mov     rcx, [rbx+0A0h]
0x14001f945  mov     edx, r15d
0x14001f948  mov     rax, [rbx+98h]
0x14001f94f  test    r15d, r15d
0x14001f952  js      loc_14001FC1D
0x14001f958  lea     r9, TcpTlProviderEndpointDispatch
0x14001f95f  mov     r8, rbx
0x14001f962  call    _guard_dispatch_icall
0x14001f967  test    r12, r12
0x14001f96a  jnz     loc_14001F857
0x14001f970  mov     rcx, [rbp+57h+var_50]
0x14001f974  xor     rcx, rsp; StackCookie
0x14001f977  call    __security_check_cookie
0x14001f97c  add     rsp, 0E8h
0x14001f983  pop     r15
0x14001f985  pop     r14
0x14001f987  pop     r13
0x14001f989  pop     r12
0x14001f98b  pop     rdi
0x14001f98c  pop     rsi
0x14001f98d  pop     rbx
0x14001f98e  pop     rbp
0x14001f98f  retn
0x14001f991  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredContext+4, 8
0x14001f998  xorps   xmm0, xmm0
0x14001f99b  movups  [rbp+57h+var_60], xmm0
0x14001f99f  jz      loc_14001F8FB
0x14001f9a5  mov     dword ptr [rsp+120h+var_E8], r15d
0x14001f9aa  lea     r8, [rbp+57h+var_60]
0x14001f9ae  mov     eax, r15d
0x14001f9b1  mov     qword ptr [rbp+57h+var_60], rbx
0x14001f9b5  not     eax
0x14001f9b7  lea     rdx, INET_INSPECT
0x14001f9be  shr     eax, 1Fh
0x14001f9c1  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001f9c8  mov     dword ptr [rsp+120h+var_F0], eax
0x14001f9cc  mov     r9, rbx
0x14001f9cf  mov     dword ptr [rsp+120h+var_F8], 10h
0x14001f9d7  mov     [rsp+120h+var_100], rsi
0x14001f9dc  call    McTemplateK0ppqqq_EtwWriteTransfer
0x14001f9e1  jmp     loc_14001F8FB
0x14001f9e6  mov     cl, 2; NewIrql
0x14001f9e8  call    cs:__imp_KfRaiseIrql
0x14001f9ef  nop     dword ptr [rax+rax+00h]
0x14001f9f4  mov     rdi, [rbx+28h]
0x14001f9f8  lea     rcx, [rbp+57h+Src]; void *
0x14001f9fc  xor     edx, edx; Val
0x14001f9fe  mov     r8d, 60h ; '`'; Size
0x14001fa04  movzx   esi, al
0x14001fa07  call    memset
0x14001fa0c  mov     rdx, [r14]
0x14001fa0f  mov     [rbp+57h+var_80], rdx
0x14001fa13  mov     [rbp+57h+var_88], r15d
0x14001fa17  mov     [rbp+57h+var_68], r13d
0x14001fa1b  mov     [rbp+57h+var_64], 6
0x14001fa22  test    rdi, rdi
0x14001fa25  jz      loc_14001FC37
0x14001fa2b  mov     rcx, rdi; Process
0x14001fa2e  call    cs:__imp_PsGetProcessId
0x14001fa35  nop     dword ptr [rax+rax+00h]
0x14001fa3a  mov     rcx, rdi
0x14001fa3d  mov     [rbp+57h+var_78], eax
0x14001fa40  call    cs:__imp_PsGetProcessStartKey
0x14001fa47  nop     dword ptr [rax+rax+00h]
0x14001fa4c  mov     [rbp+57h+var_70], rax
0x14001fa50  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x14001fa57  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001fa5e  nop     dword ptr [rax+rax+00h]
0x14001fa63  mov     rdx, qword ptr cs:TcpFailureTraceRingBuffer
0x14001fa6a  mov     ecx, [rdx+8]
0x14001fa6d  sub     ecx, [rdx+0Ch]
0x14001fa70  cmp     ecx, [rdx+4]
0x14001fa73  jz      loc_14001FB4D
0x14001fa79  mov     rdi, qword ptr cs:TcpFailureTraceRingBuffer
0x14001fa80  lea     rdx, [rbp+57h+Src]; Src
0x14001fa84  mov     ecx, [rdi]
0x14001fa86  mov     eax, [rdi+4]
0x14001fa89  mov     r8d, ecx; Size
0x14001fa8c  dec     eax
0x14001fa8e  and     eax, [rdi+8]
0x14001fa91  imul    ecx, eax
0x14001fa94  add     rcx, [rdi+10h]; void *
0x14001fa98  call    memmove
0x14001fa9d  inc     dword ptr [rdi+8]
0x14001faa0  lea     rcx, TcpFailureTraceRingBuffer+8; SpinLock
0x14001faa7  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001faae  nop     dword ptr [rax+rax+00h]
0x14001fab3  movzx   ecx, sil; NewIrql
0x14001fab7  call    cs:__imp_KeLowerIrql
0x14001fabe  nop     dword ptr [rax+rax+00h]
0x14001fac3  cmp     cs:dword_1402241D4, r13d
0x14001faca  jz      loc_14001F93E
0x14001fad0  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine, r13b
0x14001fad7  xorps   xmm0, xmm0
0x14001fada  movups  [rbp+57h+var_60], xmm0
0x14001fade  jge     loc_14001F921
0x14001fae4  mov     rcx, [rbx+28h]; Process
0x14001fae8  call    cs:__imp_PsGetProcessId
0x14001faef  nop     dword ptr [rax+rax+00h]
0x14001faf4  mov     rcx, [rbx+20h]
0x14001faf8  mov     r14, rax
0x14001fafb  mov     rdx, [rbx+58h]
0x14001faff  mov     qword ptr [rbp+57h+var_60+8], r13
0x14001fb03  mov     qword ptr [rbp+57h+var_60], rbx
0x14001fb07  movzx   edi, word ptr [rcx+18h]
0x14001fb0b  mov     rcx, [rbx+28h]
0x14001fb0f  mov     esi, [rdx]
0x14001fb11  call    cs:__imp_PsGetProcessStartKey
0x14001fb18  nop     dword ptr [rax+rax+00h]
0x14001fb1d  mov     [rsp+120h+var_D8], rax
0x14001fb22  lea     r8, [rbp+57h+var_60]
0x14001fb26  mov     dword ptr [rsp+120h+var_E0], edi
0x14001fb2a  lea     rdx, TCP_CREATE_ENDPOINT_INSPECTION_FAILURE
0x14001fb31  mov     dword ptr [rsp+120h+var_E8], esi
0x14001fb35  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001fb3c  mov     dword ptr [rsp+120h+var_F0], r14d
0x14001fb41  mov     dword ptr [rsp+120h+var_F8], r15d
0x14001fb46  call    McTemplateK0qbr0qqqqx_EtwWriteTransfer
0x14001fb4b  jmp     short loc_14001FBC9
0x14001fb4d  inc     dword ptr [rdx+0Ch]
0x14001fb50  jmp     loc_14001FA79
0x14001fb55  mov     rcx, [rbx+28h]; Process
0x14001fb59  call    cs:__imp_PsGetProcessId
0x14001fb60  nop     dword ptr [rax+rax+00h]
0x14001fb65  mov     rcx, [rbx+20h]
0x14001fb69  mov     r14, rax
0x14001fb6c  mov     rdx, [rbx+58h]
0x14001fb70  mov     qword ptr [rbp+57h+var_60+8], r13
0x14001fb74  mov     qword ptr [rbp+57h+var_60], rbx
0x14001fb78  movzx   edi, word ptr [rcx+18h]
0x14001fb7c  mov     rcx, [rbx+28h]
0x14001fb80  mov     esi, [rdx]
0x14001fb82  call    cs:__imp_PsGetProcessStartKey
0x14001fb89  nop     dword ptr [rax+rax+00h]
0x14001fb8e  mov     [rsp+120h+var_D0], rax
0x14001fb93  mov     r9, rbx
0x14001fb96  mov     dword ptr [rsp+120h+var_D8], edi
0x14001fb9a  lea     r8, [rbp+57h+var_60]
0x14001fb9e  mov     dword ptr [rsp+120h+var_E0], esi
0x14001fba2  lea     rdx, TCP_CREATE_ENDPOINT_COMPLETE_V2
0x14001fba9  mov     dword ptr [rsp+120h+var_E8], r14d
0x14001fbae  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001fbb5  mov     dword ptr [rsp+120h+var_F0], r13d
0x14001fbba  mov     [rsp+120h+var_F8], r13
0x14001fbbf  mov     dword ptr [rsp+120h+var_100], r13d
0x14001fbc4  call    McTemplateK0pqbr1qqqqx_EtwWriteTransfer
0x14001fbc9  mov     r14, 0FFFFF78000000014h
0x14001fbd3  jmp     loc_14001F921
0x14001fbd8  mov     rcx, [rbx+28h]; Process
0x14001fbdc  call    cs:__imp_PsGetProcessId
0x14001fbe3  nop     dword ptr [rax+rax+00h]
0x14001fbe8  mov     rcx, [rbx+20h]
0x14001fbec  lea     r8, [rbp+57h+var_60]
0x14001fbf0  mov     dword ptr [rsp+120h+var_F0], eax
0x14001fbf4  mov     r9d, r15d
0x14001fbf7  mov     qword ptr [rbp+57h+var_60+8], r13
0x14001fbfb  mov     qword ptr [rbp+57h+var_60], rbx
0x14001fbff  movzx   edx, word ptr [rcx+18h]
0x14001fc03  lea     rcx, MICROSOFT_TCPIP_PROVIDER_Context
0x14001fc0a  mov     dword ptr [rsp+120h+var_F8], edx
0x14001fc0e  mov     [rsp+120h+var_100], rbx
0x14001fc13  call    McTemplateK0qpqq_EtwWriteTransfer
0x14001fc18  jmp     loc_14001F93E
0x14001fc1d  xor     r9d, r9d
0x14001fc20  xor     r8d, r8d
0x14001fc23  call    _guard_dispatch_icall
0x14001fc28  xor     edx, edx
0x14001fc2a  mov     rcx, rbx; SpinLock
0x14001fc2d  call    TcpCloseEndpoint
0x14001fc32  jmp     loc_14001F967
0x14001fc37  mov     [rbp+57h+var_78], 0FFFFFFFFh
0x14001fc3e  mov     [rbp+57h+var_70], 0FFFFFFFFFFFFFFFFh
0x14001fc46  jmp     loc_14001FA50
0x14001fc4b  mov     rcx, [rsi]
0x14001fc4e  call    cs:__imp_WfpStreamEndpointCleanupBegin
0x14001fc55  nop     dword ptr [rax+rax+00h]
0x14001fc5a  mov     rcx, [rsi]
0x14001fc5d  call    WfpAleEndpointTeardownHandler
0x14001fc62  mov     [rsi], r13
0x14001fc65  jmp     loc_14001F8EE
```
