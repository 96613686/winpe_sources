# TcpSatisfyReceiveRequests

- ea: `0x1400ae5a0`
- end: `0x1400aebd2`
- name: `TcpSatisfyReceiveRequests`
- size: `1586`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ad790`

## callees

- `0x14001e680`
- `0x1400538b0`
- `0x140053e04`
- `0x140055bc4`
- `0x1400ae5a0`
- `0x1400aebd8`
- `0x1400aecb4`
- `0x1400aed4c`
- `0x14014cd6c`
- `0x1401bf390`
- `0x1401bf5c0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae8c5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400aea7a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae8c5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400aea7a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae7ab`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae9a3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae7ab`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae9a3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae8b3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400aea50`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae8b3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400aea50`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ae697`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ae697`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x1400ae6b2`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x1400ae6b2`

## pseudocode

```c
__int64 __fastcall TcpSatisfyReceiveRequests(
        PKSPIN_LOCK SpinLock,
        __int64 a2,
        unsigned int a3,
        int **a4,
        _QWORD *a5,
        _DWORD *a6)
{
  int *v7; // rsi
  __int64 v8; // r13
  _DWORD *v9; // rbx
  __int64 v10; // rdx
  unsigned __int64 v11; // rdi
  __int64 v12; // rax
  char v13; // r12
  bool v14; // r14
  unsigned int v15; // r8d
  __int64 *v16; // rdi
  char *v17; // rdx
  char v18; // cl
  char v19; // di
  _DWORD *v20; // r14
  int IsEnabledDeviceUsageNoInline; // eax
  unsigned __int64 v22; // rdi
  _DWORD *v24; // r13
  unsigned __int64 v26; // r13
  int v27; // eax
  __int64 v28; // [rsp+28h] [rbp-B9h]
  int v29; // [rsp+30h] [rbp-B1h]
  char v30; // [rsp+38h] [rbp-A9h]
  char v31; // [rsp+38h] [rbp-A9h]
  int v32; // [rsp+40h] [rbp-A1h]
  int v33; // [rsp+48h] [rbp-99h]
  char v34; // [rsp+48h] [rbp-99h]
  char v35; // [rsp+48h] [rbp-99h]
  char v36; // [rsp+58h] [rbp-89h]
  int v37; // [rsp+68h] [rbp-79h]
  int v38; // [rsp+68h] [rbp-79h]
  unsigned int v39; // [rsp+78h] [rbp-69h] BYREF
  int v40; // [rsp+7Ch] [rbp-65h] BYREF
  int v41; // [rsp+80h] [rbp-61h]
  unsigned int v42; // [rsp+84h] [rbp-5Dh]
  __int64 v43; // [rsp+88h] [rbp-59h] BYREF
  void (__fastcall *v44)(_QWORD, _QWORD, _QWORD, _QWORD); // [rsp+90h] [rbp-51h] BYREF
  __int64 v45; // [rsp+98h] [rbp-49h] BYREF
  __int64 v46; // [rsp+A0h] [rbp-41h]
  __int64 v47; // [rsp+A8h] [rbp-39h]
  _DWORD *v48; // [rsp+B0h] [rbp-31h]
  int **v49; // [rsp+B8h] [rbp-29h]
  _QWORD *v50; // [rsp+C0h] [rbp-21h]
  __int128 v51; // [rsp+C8h] [rbp-19h] BYREF

  v7 = *a4;
  v42 = a3;
  v8 = 0;
  v9 = (_DWORD *)*a5;
  *a6 = 2;
  v49 = a4;
  v47 = a2;
  v50 = a5;
  v48 = a6;
  v46 = 0;
  LOBYTE(v41) = 0;
  while ( 1 )
  {
    v10 = *((_QWORD *)v7 + 1);
    if ( (v9[6] & 4) != 0 )
    {
      v11 = -1;
LABEL_66:
      v13 = 0;
      v8 += *(unsigned int *)(v10 + 24);
      v46 = v8;
      v14 = 0;
      goto LABEL_14;
    }
    v11 = *(unsigned int *)(v10 + 24);
    if ( v11 >= *((_QWORD *)v9 + 5) - *((_QWORD *)v9 + 6) )
      v11 = *((_QWORD *)v9 + 5) - *((_QWORD *)v9 + 6);
    if ( v11 == -1 )
      goto LABEL_66;
    if ( v11 )
    {
      v43 = 0;
      v44 = 0;
      v39 = 0;
      v40 = 0;
      v45 = 0;
      v43 = *(_QWORD *)(v10 + 8);
      v39 = *(_DWORD *)(v10 + 16);
      v44 = (void (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))*((_QWORD *)v9 + 2);
      v40 = v9[7];
      LOBYTE(v29) = 0;
      RtlCopyMdlToMdlIndirect(&v43, &v39, &v44, &v40, v11, v29, &v45);
      NetioAdvanceToLocationInNetBuffer(*((_QWORD *)v7 + 1), (unsigned int)v45, v43, v39);
      *((_QWORD *)v9 + 2) = v44;
      v9[7] = v40;
      v12 = v45;
      *((_QWORD *)v9 + 6) += v45;
      v8 += v12;
      v46 = v8;
      if ( Microsoft_Windows_Networking_CorrelationEnabled )
      {
        if ( (*((_QWORD *)v7 + 31) & 0x7FFFFFFFFFFFFFFFLL) != 0 )
        {
          if ( *((_QWORD *)v9 + 7) )
          {
            if ( Microsoft_Windows_Networking_CorrelationEnabled )
              TcpipEtwTransferActivity(*((_QWORD *)v9 + 7), *((_QWORD *)v7 + 31) & 0x7FFFFFFFFFFFFFFFLL, 13);
          }
          else
          {
            *((_QWORD *)v9 + 7) = *((_QWORD *)v7 + 31) & 0x7FFFFFFFFFFFFFFFLL;
          }
        }
      }
    }
    if ( *((_QWORD *)v9 + 6) == *((_QWORD *)v9 + 5) )
    {
      KeReleaseSpinLockFromDpcLevel(SpinLock);
      v14 = 0;
      v13 = 1;
      *v48 = 1;
      if ( dword_1402201D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
      {
        v51 = 0;
        if ( (BYTE3(WPP_MAIN_CB.Reserved) & 1) != 0 )
        {
          v38 = *((_DWORD *)SpinLock + 132);
          v35 = *((_QWORD *)v9 + 5);
          v31 = *((_QWORD *)v9 + 6);
          *(_QWORD *)&v51 = SpinLock;
          McTemplateK0ppppqpqqqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_DELIVERY_SATISFIED,
            (unsigned int)&v51,
            (_DWORD)SpinLock,
            v47,
            (char)v9,
            v31,
            0,
            v35,
            0,
            0,
            1,
            v38);
        }
      }
      v24 = (_DWORD *)*((_QWORD *)v9 + 8);
      *(_QWORD *)&v51 = v24;
      TcpCompleteClientReceiveRequest(v9, 0, SpinLock);
      if ( (Feature_Servicing_TCPIPPPLOptimization__private_featureState & 0x10) != 0
         ? Feature_Servicing_TCPIPPPLOptimization__private_featureState & 1
         : Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageNoInline() )
      {
        PplFreeToLookasideListProcessor(TcpReceiveRequestPool, v9, *((unsigned __int16 *)v9 + 16));
      }
      else
      {
        v26 = TcpReceiveRequestPool + ((unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1) << 7);
        if ( !*(_BYTE *)(v26 + 176) )
          PplpLazyInitializeLookasideList(TcpReceiveRequestPool, v26 + 64);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v26 + 64), v9);
        v24 = (_DWORD *)v51;
      }
      v27 = (unsigned __int8)v41;
      if ( !v24 )
        v27 = 1;
      v9 = v24;
      v41 = v27;
      KeAcquireSpinLockAtDpcLevel(SpinLock);
      v8 = v46;
    }
    else
    {
      v13 = 0;
      v14 = v7[34] < 0 || (v9[6] & 8) != 0;
    }
LABEL_14:
    if ( !*(_DWORD *)(*((_QWORD *)v7 + 1) + 24LL) || v11 == -1 )
    {
      v15 = v42;
      v16 = *(__int64 **)v7;
      v17 = (char *)qword_140224650 + 64 * (unsigned __int64)v42;
      *(_QWORD *)v7 = 0;
      if ( *((_QWORD *)v17 + 5) )
        **((_QWORD **)v17 + 6) = v7;
      else
        *((_QWORD *)v17 + 5) = v7;
      *((_QWORD *)v17 + 6) = v7;
      TcpScheduleFlushDelay(v15);
      v7 = (int *)v16;
      if ( !v16 )
        break;
    }
    if ( (_BYTE)v41 )
      goto LABEL_36;
  }
  if ( !v13 )
  {
    v18 = *((_BYTE *)SpinLock + 132);
    v19 = v47;
    if ( v18 || v47 == SpinLock[82] || (v9[6] & 6) == 0 )
    {
      if ( v14 || v18 || v47 == SpinLock[82] )
      {
        KeReleaseSpinLockFromDpcLevel(SpinLock);
        *v48 = 1;
        if ( dword_1402201D4
          && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
          && (BYTE3(WPP_MAIN_CB.Reserved) & 1) != 0 )
        {
          v37 = *((_DWORD *)SpinLock + 132);
          v36 = (SpinLock[15] & 0x200000) != 0;
          v34 = *((_QWORD *)v9 + 5);
          v30 = *((_QWORD *)v9 + 6);
          v51 = (unsigned __int64)SpinLock;
          McTemplateK0ppppqpqqqq_EtwWriteTransfer(
            (unsigned int)&MICROSOFT_TCPIP_PROVIDER_Context,
            (unsigned int)TCP_DELIVERY_SATISFIED,
            (unsigned int)&v51,
            (_DWORD)SpinLock,
            v19,
            (char)v9,
            v30,
            0,
            v34,
            0,
            v36,
            0,
            v37);
        }
        v20 = (_DWORD *)*((_QWORD *)v9 + 8);
        (*(void (__fastcall **)(_QWORD, _QWORD, _QWORD, _QWORD))v9)(
          *((_QWORD *)v9 + 1),
          0,
          *((_QWORD *)v9 + 6),
          *((_QWORD *)v9 + 7));
        if ( qword_1402244B8 )
        {
          LOWORD(v33) = *((_WORD *)SpinLock + 59);
          LOWORD(v32) = *((_WORD *)SpinLock + 58);
          LOWORD(v28) = *((_WORD *)SpinLock + 409);
          InetTraceBasicDataCore(
            &TcpInetTransport,
            1547,
            SpinLock[106],
            *((_QWORD *)v9 + 6),
            v28,
            **(_QWORD **)(*(_QWORD *)SpinLock[4] + 16LL),
            *(_QWORD *)(SpinLock[4] + 16),
            v32,
            v33);
        }
        if ( (Feature_Servicing_TCPIPPPLOptimization__private_featureState & 0x10) != 0 )
          IsEnabledDeviceUsageNoInline = Feature_Servicing_TCPIPPPLOptimization__private_featureState & 1;
        else
          IsEnabledDeviceUsageNoInline = Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageNoInline();
        if ( IsEnabledDeviceUsageNoInline )
        {
          PplFreeToLookasideListProcessor(TcpReceiveRequestPool, v9, *((unsigned __int16 *)v9 + 16));
        }
        else
        {
          v22 = TcpReceiveRequestPool + ((unsigned __int64)(unsigned int)(HIDWORD(KeGetPcr()[1].LockArray) + 1) << 7);
          if ( !*(_BYTE *)(v22 + 176) )
            PplpLazyInitializeLookasideList(TcpReceiveRequestPool, v22 + 64);
          ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)(v22 + 64), v9);
        }
        v9 = v20;
        KeAcquireSpinLockAtDpcLevel(SpinLock);
      }
      else
      {
        *v48 = 0;
      }
    }
  }
LABEL_36:
  *v49 = v7;
  *v50 = v9;
  return v8;
}

```

## disassembly

```asm
0x1400ae5a0  mov     r11, rsp
0x1400ae5a3  push    rbp
0x1400ae5a4  push    rbx
0x1400ae5a5  push    rsi
0x1400ae5a6  push    r13
0x1400ae5a8  push    r14
0x1400ae5aa  push    r15
0x1400ae5ac  lea     rbp, [r11-4Fh]
0x1400ae5b0  sub     rsp, 0F8h
0x1400ae5b7  mov     rax, cs:__security_cookie
0x1400ae5be  xor     rax, rsp
0x1400ae5c1  mov     [rbp+47h+var_50], rax
0x1400ae5c5  mov     rax, [rbp+47h+arg_28]
0x1400ae5c9  mov     r15, rcx
0x1400ae5cc  mov     rcx, [rbp+47h+arg_20]
0x1400ae5d0  mov     rsi, [r9]
0x1400ae5d3  mov     [rbp+47h+var_A4], r8d
0x1400ae5d7  xor     r8d, r8d
0x1400ae5da  mov     [r11-38h], rdi
0x1400ae5de  mov     r13d, r8d
0x1400ae5e1  mov     rbx, [rcx]
0x1400ae5e4  mov     dword ptr [rax], 2
0x1400ae5ea  mov     [rbp+47h+var_70], r9
0x1400ae5ee  mov     [rbp+47h+var_80], rdx
0x1400ae5f2  mov     [rbp+47h+var_68], rcx
0x1400ae5f6  mov     [rbp+47h+var_78], rax
0x1400ae5fa  mov     [rbp+47h+var_88], r8
0x1400ae5fe  mov     byte ptr [rbp+47h+var_A8], r8b
0x1400ae602  mov     [r11-40h], r12
0x1400ae606  mov     eax, [rbx+18h]
0x1400ae609  mov     r14, 7FFFFFFFFFFFFFFFh
0x1400ae613  mov     rdx, [rsi+8]
0x1400ae617  test    al, 4
0x1400ae619  jnz     loc_1400AEAC2
0x1400ae61f  mov     edi, [rdx+18h]
0x1400ae622  mov     rcx, [rbx+28h]
0x1400ae626  sub     rcx, [rbx+30h]
0x1400ae62a  cmp     rdi, rcx
0x1400ae62d  cmovnb  rdi, rcx
0x1400ae631  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400ae635  jz      loc_1400AEAC9
0x1400ae63b  test    rdi, rdi
0x1400ae63e  jz      loc_1400AE700
0x1400ae644  mov     [rbp+47h+var_A0], r8
0x1400ae648  lea     r9, [rbp+47h+var_AC]
0x1400ae64c  mov     [rbp+47h+var_98], r8
0x1400ae650  lea     rcx, [rbp+47h+var_A0]
0x1400ae654  mov     [rbp+47h+var_B0], r8d
0x1400ae658  mov     [rbp+47h+var_AC], r8d
0x1400ae65c  mov     [rbp+47h+var_90], r8
0x1400ae660  lea     r8, [rbp+47h+var_98]
0x1400ae664  mov     rax, [rdx+8]
0x1400ae668  mov     [rbp+47h+var_A0], rax
0x1400ae66c  mov     eax, [rdx+10h]
0x1400ae66f  lea     rdx, [rbp+47h+var_B0]
0x1400ae673  mov     [rbp+47h+var_B0], eax
0x1400ae676  mov     rax, [rbx+10h]
0x1400ae67a  mov     [rbp+47h+var_98], rax
0x1400ae67e  mov     eax, [rbx+1Ch]
0x1400ae681  mov     [rbp+47h+var_AC], eax
0x1400ae684  lea     rax, [rbp+47h+var_90]
0x1400ae688  mov     qword ptr [rsp+120h+var_F0], rax
0x1400ae68d  mov     byte ptr [rsp+120h+var_F8], 0
0x1400ae692  mov     [rsp+120h+var_100], rdi
0x1400ae697  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400ae69e  nop     dword ptr [rax+rax+00h]
0x1400ae6a3  mov     r9d, [rbp+47h+var_B0]
0x1400ae6a7  mov     r8, [rbp+47h+var_A0]
0x1400ae6ab  mov     edx, dword ptr [rbp+47h+var_90]
0x1400ae6ae  mov     rcx, [rsi+8]
0x1400ae6b2  call    cs:__imp_NetioAdvanceToLocationInNetBuffer
0x1400ae6b9  nop     dword ptr [rax+rax+00h]
0x1400ae6be  mov     rax, [rbp+47h+var_98]
0x1400ae6c2  mov     [rbx+10h], rax
0x1400ae6c6  mov     eax, [rbp+47h+var_AC]
0x1400ae6c9  mov     [rbx+1Ch], eax
0x1400ae6cc  mov     rax, [rbp+47h+var_90]
0x1400ae6d0  add     [rbx+30h], rax
0x1400ae6d4  add     r13, rax
0x1400ae6d7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400ae6dd  mov     [rbp+47h+var_88], r13
0x1400ae6e1  test    eax, eax
0x1400ae6e3  jz      short loc_1400AE700
0x1400ae6e5  mov     rcx, [rsi+0F8h]
0x1400ae6ec  and     rcx, r14
0x1400ae6ef  jz      short loc_1400AE700
0x1400ae6f1  cmp     qword ptr [rbx+38h], 0
0x1400ae6f6  jnz     loc_1400AE928
0x1400ae6fc  mov     [rbx+38h], rcx
0x1400ae700  mov     rax, [rbx+28h]
0x1400ae704  cmp     [rbx+30h], rax
0x1400ae708  jz      loc_1400AE9A0
0x1400ae70e  xor     r12b, r12b
0x1400ae711  cmp     dword ptr [rsi+88h], 0
0x1400ae718  jge     loc_1400AEA8F
0x1400ae71e  mov     r14b, 1
0x1400ae721  mov     rax, [rsi+8]
0x1400ae725  cmp     dword ptr [rax+18h], 0
0x1400ae729  jnz     loc_1400AE910
0x1400ae72f  mov     r8d, [rbp+47h+var_A4]
0x1400ae733  mov     rdi, [rsi]
0x1400ae736  mov     edx, r8d
0x1400ae739  shl     rdx, 6
0x1400ae73d  add     rdx, cs:qword_140224650
0x1400ae744  mov     qword ptr [rsi], 0
0x1400ae74b  cmp     qword ptr [rdx+28h], 0
0x1400ae750  jnz     loc_1400AE94D
0x1400ae756  mov     [rdx+28h], rsi
0x1400ae75a  mov     ecx, r8d
0x1400ae75d  mov     [rdx+30h], rsi
0x1400ae761  call    TcpScheduleFlushDelay
0x1400ae766  mov     rsi, rdi
0x1400ae769  test    rdi, rdi
0x1400ae76c  jnz     loc_1400AE91A
0x1400ae772  test    r12b, r12b
0x1400ae775  jnz     loc_1400AE8D1
0x1400ae77b  movzx   ecx, byte ptr [r15+84h]
0x1400ae783  mov     rdi, [rbp+47h+var_80]
0x1400ae787  test    cl, cl
0x1400ae789  jnz     short loc_1400AE79F
0x1400ae78b  cmp     rdi, [r15+290h]
0x1400ae792  jz      short loc_1400AE79F
0x1400ae794  mov     eax, [rbx+18h]
0x1400ae797  test    al, 6
0x1400ae799  jnz     loc_1400AE8D1
0x1400ae79f  test    r14b, r14b
0x1400ae7a2  jz      loc_1400AE959
0x1400ae7a8  mov     rcx, r15; SpinLock
0x1400ae7ab  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400ae7b2  nop     dword ptr [rax+rax+00h]
0x1400ae7b7  mov     rax, [rbp+47h+var_78]
0x1400ae7bb  mov     dword ptr [rax], 1
0x1400ae7c1  cmp     cs:dword_1402201D4, 0
0x1400ae7c8  jz      short loc_1400AE7E4
0x1400ae7ca  cmp     cs:TcpipTraceFiltersExist, 0
0x1400ae7d1  jnz     loc_1400AEBBD
0x1400ae7d7  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 1
0x1400ae7de  jnz     loc_1400AEADE
0x1400ae7e4  mov     rax, [rbx]
0x1400ae7e7  xor     edx, edx
0x1400ae7e9  mov     r9, [rbx+38h]
0x1400ae7ed  mov     r8, [rbx+30h]
0x1400ae7f1  mov     rcx, [rbx+8]
0x1400ae7f5  mov     r14, [rbx+40h]
0x1400ae7f9  call    _guard_dispatch_icall
0x1400ae7fe  mov     rax, cs:qword_1402244B8
0x1400ae805  test    rax, rax
0x1400ae808  jz      short loc_1400AE863
0x1400ae80a  mov     rcx, [r15+20h]
0x1400ae80e  mov     r9, [rbx+30h]
0x1400ae812  mov     r8, [r15+350h]
0x1400ae819  mov     rax, [rcx]
0x1400ae81c  mov     rdx, [rax+10h]
0x1400ae820  movzx   eax, word ptr [r15+76h]
0x1400ae825  mov     word ptr [rsp+120h+var_E0], ax
0x1400ae82a  movzx   eax, word ptr [r15+74h]
0x1400ae82f  mov     word ptr [rsp+120h+var_E8], ax
0x1400ae834  mov     rax, [rcx+10h]
0x1400ae838  lea     rcx, TcpInetTransport
0x1400ae83f  mov     qword ptr [rsp+120h+var_F0], rax
0x1400ae844  mov     rax, [rdx]
0x1400ae847  mov     edx, 60Bh
0x1400ae84c  mov     [rsp+120h+var_F8], rax
0x1400ae851  movzx   eax, word ptr [r15+332h]
0x1400ae859  mov     word ptr [rsp+120h+var_100], ax
0x1400ae85e  call    InetTraceBasicDataCore
0x1400ae863  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x1400ae869  test    al, 10h
0x1400ae86b  jz      loc_1400AE996
0x1400ae871  and     eax, 1
0x1400ae874  test    eax, eax
0x1400ae876  jnz     loc_1400AE97D
0x1400ae87c  mov     eax, gs:1A4h
0x1400ae884  mov     r8, cs:TcpReceiveRequestPool
0x1400ae88b  lea     edi, [rax+1]
0x1400ae88e  shl     rdi, 7
0x1400ae892  add     rdi, r8
0x1400ae895  movzx   eax, byte ptr [rdi+0B0h]
0x1400ae89c  test    al, al
0x1400ae89e  jnz     short loc_1400AE8AC
0x1400ae8a0  lea     rdx, [rdi+40h]
0x1400ae8a4  mov     rcx, r8
0x1400ae8a7  call    PplpLazyInitializeLookasideList
0x1400ae8ac  mov     rdx, rbx; Entry
0x1400ae8af  lea     rcx, [rdi+40h]; Lookaside
0x1400ae8b3  call    cs:__imp_ExFreeToLookasideListEx
0x1400ae8ba  nop     dword ptr [rax+rax+00h]
0x1400ae8bf  mov     rcx, r15; SpinLock
0x1400ae8c2  mov     rbx, r14
0x1400ae8c5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400ae8cc  nop     dword ptr [rax+rax+00h]
0x1400ae8d1  mov     rax, [rbp+47h+var_70]
0x1400ae8d5  mov     r12, [rsp+120h+var_38]
0x1400ae8dd  mov     rdi, [rsp+0F0h]
0x1400ae8e5  mov     [rax], rsi
0x1400ae8e8  mov     rax, [rbp+47h+var_68]
0x1400ae8ec  mov     [rax], rbx
0x1400ae8ef  mov     rax, r13
0x1400ae8f2  mov     rcx, [rbp+47h+var_50]
0x1400ae8f6  xor     rcx, rsp; StackCookie
0x1400ae8f9  call    __security_check_cookie
0x1400ae8fe  add     rsp, 0F8h
0x1400ae905  pop     r15
0x1400ae907  pop     r14
0x1400ae909  pop     r13
0x1400ae90b  pop     rsi
0x1400ae90c  pop     rbx
0x1400ae90d  pop     rbp
0x1400ae90e  retn
0x1400ae910  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400ae914  jz      loc_1400AE72F
0x1400ae91a  cmp     byte ptr [rbp+47h+var_A8], 0
0x1400ae91e  jnz     short loc_1400AE8D1
0x1400ae920  xor     r8d, r8d
0x1400ae923  jmp     loc_1400AE606
0x1400ae928  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400ae92e  test    eax, eax
0x1400ae930  jz      loc_1400AE700
0x1400ae936  mov     rdx, rcx
0x1400ae939  mov     r8d, 0Dh
0x1400ae93f  mov     rcx, [rbx+38h]
0x1400ae943  call    TcpipEtwTransferActivity
0x1400ae948  jmp     loc_1400AE700
0x1400ae94d  mov     rax, [rdx+30h]
0x1400ae951  mov     [rax], rsi
0x1400ae954  jmp     loc_1400AE75A
0x1400ae959  test    cl, cl
0x1400ae95b  jnz     loc_1400AE7A8
0x1400ae961  cmp     rdi, [r15+290h]
0x1400ae968  jz      loc_1400AE7A8
0x1400ae96e  mov     rax, [rbp+47h+var_78]
0x1400ae972  mov     dword ptr [rax], 0
0x1400ae978  jmp     loc_1400AE8D1
0x1400ae97d  movzx   r8d, word ptr [rbx+20h]
0x1400ae982  mov     rdx, rbx
0x1400ae985  mov     rcx, cs:TcpReceiveRequestPool
0x1400ae98c  call    PplFreeToLookasideListProcessor
0x1400ae991  jmp     loc_1400AE8BF
0x1400ae996  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageNoInline
0x1400ae99b  jmp     loc_1400AE874
0x1400ae9a0  mov     rcx, r15; SpinLock
0x1400ae9a3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400ae9aa  nop     dword ptr [rax+rax+00h]
0x1400ae9af  mov     rax, [rbp+47h+var_78]
0x1400ae9b3  mov     ecx, 1
0x1400ae9b8  xor     r14b, r14b
0x1400ae9bb  mov     r12b, 1
0x1400ae9be  mov     [rax], ecx
0x1400ae9c0  cmp     cs:dword_1402201D4, 0
0x1400ae9c7  jz      short loc_1400AE9E9
0x1400ae9c9  cmp     cs:TcpipTraceFiltersExist, r14b
0x1400ae9d0  jnz     loc_1400AEBA8
0x1400ae9d6  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, cl
0x1400ae9dc  xorps   xmm0, xmm0
0x1400ae9df  movups  [rbp+47h+var_60], xmm0
0x1400ae9e3  jnz     loc_1400AEB48
0x1400ae9e9  mov     r13, [rbx+40h]
0x1400ae9ed  mov     r8, r15
0x1400ae9f0  xor     edx, edx
0x1400ae9f2  mov     qword ptr [rbp+47h+var_60], r13
0x1400ae9f6  mov     rcx, rbx
0x1400ae9f9  call    TcpCompleteClientReceiveRequest
0x1400ae9fe  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x1400aea04  test    al, 10h
0x1400aea06  jz      loc_1400AEAB8
0x1400aea0c  and     eax, 1
0x1400aea0f  test    eax, eax
0x1400aea11  jnz     loc_1400AEAA2
0x1400aea17  mov     eax, gs:1A4h
0x1400aea1f  mov     r8, cs:TcpReceiveRequestPool
0x1400aea26  lea     r13d, [rax+1]
0x1400aea2a  shl     r13, 7
0x1400aea2e  add     r13, r8
0x1400aea31  movzx   eax, byte ptr [r13+0B0h]
0x1400aea39  test    al, al
0x1400aea3b  jnz     short loc_1400AEA49
0x1400aea3d  lea     rdx, [r13+40h]
0x1400aea41  mov     rcx, r8
0x1400aea44  call    PplpLazyInitializeLookasideList
0x1400aea49  mov     rdx, rbx; Entry
0x1400aea4c  lea     rcx, [r13+40h]; Lookaside
0x1400aea50  call    cs:__imp_ExFreeToLookasideListEx
0x1400aea57  nop     dword ptr [rax+rax+00h]
0x1400aea5c  mov     r13, qword ptr [rbp+47h+var_60]
0x1400aea60  mov     eax, [rbp+47h+var_A8]
0x1400aea63  test    r13, r13
0x1400aea66  movzx   eax, al
0x1400aea69  mov     ecx, 1
0x1400aea6e  cmovz   eax, ecx
0x1400aea71  mov     rbx, r13
0x1400aea74  mov     rcx, r15; SpinLock
0x1400aea77  mov     [rbp+47h+var_A8], eax
0x1400aea7a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400aea81  nop     dword ptr [rax+rax+00h]
0x1400aea86  mov     r13, [rbp+47h+var_88]
0x1400aea8a  jmp     loc_1400AE721
0x1400aea8f  mov     eax, [rbx+18h]
0x1400aea92  test    al, 8
0x1400aea94  jnz     loc_1400AE71E
0x1400aea9a  xor     r14b, r14b
  ... truncated ...
```
