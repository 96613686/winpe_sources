# TcpSatisfyReceiveRequests

- ea: `0x140017f40`
- end: `0x140018572`
- name: `TcpSatisfyReceiveRequests`
- size: `1586`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140134880`

## callees

- `0x14000f4f0`
- `0x140014420`
- `0x140014974`
- `0x140016814`
- `0x140017f40`
- `0x140018578`
- `0x140018654`
- `0x140019ac8`
- `0x14014eaa4`
- `0x1401c0fd0`
- `0x1401c1200`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140018265`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001841a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x140018265`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x14001841a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001814b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140018343`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x14001814b`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x140018343`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140018253`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400183f0`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140018253`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400183f0`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x140018037`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x140018037`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x140018052`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x140018052`

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
      if ( dword_1402241D4 && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0) )
      {
        v51 = 0;
        if ( (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
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
      v17 = (char *)qword_140228690 + 64 * (unsigned __int64)v42;
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
        if ( dword_1402241D4
          && (!TcpipTraceFiltersExist || *((char *)SpinLock + 804) < 0)
          && (BYTE3(WPP_MAIN_CB.Dpc.DeferredRoutine) & 1) != 0 )
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
        if ( qword_1402284F8 )
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
0x140017f40  mov     r11, rsp
0x140017f43  push    rbp
0x140017f44  push    rbx
0x140017f45  push    rsi
0x140017f46  push    r13
0x140017f48  push    r14
0x140017f4a  push    r15
0x140017f4c  lea     rbp, [r11-4Fh]
0x140017f50  sub     rsp, 0F8h
0x140017f57  mov     rax, cs:__security_cookie
0x140017f5e  xor     rax, rsp
0x140017f61  mov     [rbp+47h+var_50], rax
0x140017f65  mov     rax, [rbp+47h+arg_28]
0x140017f69  mov     r15, rcx
0x140017f6c  mov     rcx, [rbp+47h+arg_20]
0x140017f70  mov     rsi, [r9]
0x140017f73  mov     [rbp+47h+var_A4], r8d
0x140017f77  xor     r8d, r8d
0x140017f7a  mov     [r11-38h], rdi
0x140017f7e  mov     r13d, r8d
0x140017f81  mov     rbx, [rcx]
0x140017f84  mov     dword ptr [rax], 2
0x140017f8a  mov     [rbp+47h+var_70], r9
0x140017f8e  mov     [rbp+47h+var_80], rdx
0x140017f92  mov     [rbp+47h+var_68], rcx
0x140017f96  mov     [rbp+47h+var_78], rax
0x140017f9a  mov     [rbp+47h+var_88], r8
0x140017f9e  mov     byte ptr [rbp+47h+var_A8], r8b
0x140017fa2  mov     [r11-40h], r12
0x140017fa6  mov     eax, [rbx+18h]
0x140017fa9  mov     r14, 7FFFFFFFFFFFFFFFh
0x140017fb3  mov     rdx, [rsi+8]
0x140017fb7  test    al, 4
0x140017fb9  jnz     loc_140018462
0x140017fbf  mov     edi, [rdx+18h]
0x140017fc2  mov     rcx, [rbx+28h]
0x140017fc6  sub     rcx, [rbx+30h]
0x140017fca  cmp     rdi, rcx
0x140017fcd  cmovnb  rdi, rcx
0x140017fd1  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x140017fd5  jz      loc_140018469
0x140017fdb  test    rdi, rdi
0x140017fde  jz      loc_1400180A0
0x140017fe4  mov     [rbp+47h+var_A0], r8
0x140017fe8  lea     r9, [rbp+47h+var_AC]
0x140017fec  mov     [rbp+47h+var_98], r8
0x140017ff0  lea     rcx, [rbp+47h+var_A0]
0x140017ff4  mov     [rbp+47h+var_B0], r8d
0x140017ff8  mov     [rbp+47h+var_AC], r8d
0x140017ffc  mov     [rbp+47h+var_90], r8
0x140018000  lea     r8, [rbp+47h+var_98]
0x140018004  mov     rax, [rdx+8]
0x140018008  mov     [rbp+47h+var_A0], rax
0x14001800c  mov     eax, [rdx+10h]
0x14001800f  lea     rdx, [rbp+47h+var_B0]
0x140018013  mov     [rbp+47h+var_B0], eax
0x140018016  mov     rax, [rbx+10h]
0x14001801a  mov     [rbp+47h+var_98], rax
0x14001801e  mov     eax, [rbx+1Ch]
0x140018021  mov     [rbp+47h+var_AC], eax
0x140018024  lea     rax, [rbp+47h+var_90]
0x140018028  mov     qword ptr [rsp+120h+var_F0], rax
0x14001802d  mov     byte ptr [rsp+120h+var_F8], 0
0x140018032  mov     [rsp+120h+var_100], rdi
0x140018037  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x14001803e  nop     dword ptr [rax+rax+00h]
0x140018043  mov     r9d, [rbp+47h+var_B0]
0x140018047  mov     r8, [rbp+47h+var_A0]
0x14001804b  mov     edx, dword ptr [rbp+47h+var_90]
0x14001804e  mov     rcx, [rsi+8]
0x140018052  call    cs:__imp_NetioAdvanceToLocationInNetBuffer
0x140018059  nop     dword ptr [rax+rax+00h]
0x14001805e  mov     rax, [rbp+47h+var_98]
0x140018062  mov     [rbx+10h], rax
0x140018066  mov     eax, [rbp+47h+var_AC]
0x140018069  mov     [rbx+1Ch], eax
0x14001806c  mov     rax, [rbp+47h+var_90]
0x140018070  add     [rbx+30h], rax
0x140018074  add     r13, rax
0x140018077  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x14001807d  mov     [rbp+47h+var_88], r13
0x140018081  test    eax, eax
0x140018083  jz      short loc_1400180A0
0x140018085  mov     rcx, [rsi+0F8h]
0x14001808c  and     rcx, r14
0x14001808f  jz      short loc_1400180A0
0x140018091  cmp     qword ptr [rbx+38h], 0
0x140018096  jnz     loc_1400182C8
0x14001809c  mov     [rbx+38h], rcx
0x1400180a0  mov     rax, [rbx+28h]
0x1400180a4  cmp     [rbx+30h], rax
0x1400180a8  jz      loc_140018340
0x1400180ae  xor     r12b, r12b
0x1400180b1  cmp     dword ptr [rsi+88h], 0
0x1400180b8  jge     loc_14001842F
0x1400180be  mov     r14b, 1
0x1400180c1  mov     rax, [rsi+8]
0x1400180c5  cmp     dword ptr [rax+18h], 0
0x1400180c9  jnz     loc_1400182B0
0x1400180cf  mov     r8d, [rbp+47h+var_A4]
0x1400180d3  mov     rdi, [rsi]
0x1400180d6  mov     edx, r8d
0x1400180d9  shl     rdx, 6
0x1400180dd  add     rdx, cs:qword_140228690
0x1400180e4  mov     qword ptr [rsi], 0
0x1400180eb  cmp     qword ptr [rdx+28h], 0
0x1400180f0  jnz     loc_1400182ED
0x1400180f6  mov     [rdx+28h], rsi
0x1400180fa  mov     ecx, r8d
0x1400180fd  mov     [rdx+30h], rsi
0x140018101  call    TcpScheduleFlushDelay
0x140018106  mov     rsi, rdi
0x140018109  test    rdi, rdi
0x14001810c  jnz     loc_1400182BA
0x140018112  test    r12b, r12b
0x140018115  jnz     loc_140018271
0x14001811b  movzx   ecx, byte ptr [r15+84h]
0x140018123  mov     rdi, [rbp+47h+var_80]
0x140018127  test    cl, cl
0x140018129  jnz     short loc_14001813F
0x14001812b  cmp     rdi, [r15+290h]
0x140018132  jz      short loc_14001813F
0x140018134  mov     eax, [rbx+18h]
0x140018137  test    al, 6
0x140018139  jnz     loc_140018271
0x14001813f  test    r14b, r14b
0x140018142  jz      loc_1400182F9
0x140018148  mov     rcx, r15; SpinLock
0x14001814b  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x140018152  nop     dword ptr [rax+rax+00h]
0x140018157  mov     rax, [rbp+47h+var_78]
0x14001815b  mov     dword ptr [rax], 1
0x140018161  cmp     cs:dword_1402241D4, 0
0x140018168  jz      short loc_140018184
0x14001816a  cmp     cs:TcpipTraceFiltersExist, 0
0x140018171  jnz     loc_14001855D
0x140018177  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, 1
0x14001817e  jnz     loc_14001847E
0x140018184  mov     rax, [rbx]
0x140018187  xor     edx, edx
0x140018189  mov     r9, [rbx+38h]
0x14001818d  mov     r8, [rbx+30h]
0x140018191  mov     rcx, [rbx+8]
0x140018195  mov     r14, [rbx+40h]
0x140018199  call    _guard_dispatch_icall
0x14001819e  mov     rax, cs:qword_1402284F8
0x1400181a5  test    rax, rax
0x1400181a8  jz      short loc_140018203
0x1400181aa  mov     rcx, [r15+20h]
0x1400181ae  mov     r9, [rbx+30h]
0x1400181b2  mov     r8, [r15+350h]
0x1400181b9  mov     rax, [rcx]
0x1400181bc  mov     rdx, [rax+10h]
0x1400181c0  movzx   eax, word ptr [r15+76h]
0x1400181c5  mov     word ptr [rsp+120h+var_E0], ax
0x1400181ca  movzx   eax, word ptr [r15+74h]
0x1400181cf  mov     word ptr [rsp+120h+var_E8], ax
0x1400181d4  mov     rax, [rcx+10h]
0x1400181d8  lea     rcx, TcpInetTransport
0x1400181df  mov     qword ptr [rsp+120h+var_F0], rax
0x1400181e4  mov     rax, [rdx]
0x1400181e7  mov     edx, 60Bh
0x1400181ec  mov     [rsp+120h+var_F8], rax
0x1400181f1  movzx   eax, word ptr [r15+332h]
0x1400181f9  mov     word ptr [rsp+120h+var_100], ax
0x1400181fe  call    InetTraceBasicDataCore
0x140018203  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x140018209  test    al, 10h
0x14001820b  jz      loc_140018336
0x140018211  and     eax, 1
0x140018214  test    eax, eax
0x140018216  jnz     loc_14001831D
0x14001821c  mov     eax, gs:1A4h
0x140018224  mov     r8, cs:TcpReceiveRequestPool
0x14001822b  lea     edi, [rax+1]
0x14001822e  shl     rdi, 7
0x140018232  add     rdi, r8
0x140018235  movzx   eax, byte ptr [rdi+0B0h]
0x14001823c  test    al, al
0x14001823e  jnz     short loc_14001824C
0x140018240  lea     rdx, [rdi+40h]
0x140018244  mov     rcx, r8
0x140018247  call    PplpLazyInitializeLookasideList
0x14001824c  mov     rdx, rbx; Entry
0x14001824f  lea     rcx, [rdi+40h]; Lookaside
0x140018253  call    cs:__imp_ExFreeToLookasideListEx
0x14001825a  nop     dword ptr [rax+rax+00h]
0x14001825f  mov     rcx, r15; SpinLock
0x140018262  mov     rbx, r14
0x140018265  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x14001826c  nop     dword ptr [rax+rax+00h]
0x140018271  mov     rax, [rbp+47h+var_70]
0x140018275  mov     r12, [rsp+120h+var_38]
0x14001827d  mov     rdi, [rsp+0F0h]
0x140018285  mov     [rax], rsi
0x140018288  mov     rax, [rbp+47h+var_68]
0x14001828c  mov     [rax], rbx
0x14001828f  mov     rax, r13
0x140018292  mov     rcx, [rbp+47h+var_50]
0x140018296  xor     rcx, rsp; StackCookie
0x140018299  call    __security_check_cookie
0x14001829e  add     rsp, 0F8h
0x1400182a5  pop     r15
0x1400182a7  pop     r14
0x1400182a9  pop     r13
0x1400182ab  pop     rsi
0x1400182ac  pop     rbx
0x1400182ad  pop     rbp
0x1400182ae  retn
0x1400182b0  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400182b4  jz      loc_1400180CF
0x1400182ba  cmp     byte ptr [rbp+47h+var_A8], 0
0x1400182be  jnz     short loc_140018271
0x1400182c0  xor     r8d, r8d
0x1400182c3  jmp     loc_140017FA6
0x1400182c8  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400182ce  test    eax, eax
0x1400182d0  jz      loc_1400180A0
0x1400182d6  mov     rdx, rcx
0x1400182d9  mov     r8d, 0Dh
0x1400182df  mov     rcx, [rbx+38h]
0x1400182e3  call    TcpipEtwTransferActivity
0x1400182e8  jmp     loc_1400180A0
0x1400182ed  mov     rax, [rdx+30h]
0x1400182f1  mov     [rax], rsi
0x1400182f4  jmp     loc_1400180FA
0x1400182f9  test    cl, cl
0x1400182fb  jnz     loc_140018148
0x140018301  cmp     rdi, [r15+290h]
0x140018308  jz      loc_140018148
0x14001830e  mov     rax, [rbp+47h+var_78]
0x140018312  mov     dword ptr [rax], 0
0x140018318  jmp     loc_140018271
0x14001831d  movzx   r8d, word ptr [rbx+20h]
0x140018322  mov     rdx, rbx
0x140018325  mov     rcx, cs:TcpReceiveRequestPool
0x14001832c  call    PplFreeToLookasideListProcessor
0x140018331  jmp     loc_14001825F
0x140018336  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageNoInline
0x14001833b  jmp     loc_140018214
0x140018340  mov     rcx, r15; SpinLock
0x140018343  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x14001834a  nop     dword ptr [rax+rax+00h]
0x14001834f  mov     rax, [rbp+47h+var_78]
0x140018353  mov     ecx, 1
0x140018358  xor     r14b, r14b
0x14001835b  mov     r12b, 1
0x14001835e  mov     [rax], ecx
0x140018360  cmp     cs:dword_1402241D4, 0
0x140018367  jz      short loc_140018389
0x140018369  cmp     cs:TcpipTraceFiltersExist, r14b
0x140018370  jnz     loc_140018548
0x140018376  test    byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+3, cl
0x14001837c  xorps   xmm0, xmm0
0x14001837f  movups  [rbp+47h+var_60], xmm0
0x140018383  jnz     loc_1400184E8
0x140018389  mov     r13, [rbx+40h]
0x14001838d  mov     r8, r15
0x140018390  xor     edx, edx
0x140018392  mov     qword ptr [rbp+47h+var_60], r13
0x140018396  mov     rcx, rbx
0x140018399  call    TcpCompleteClientReceiveRequest
0x14001839e  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x1400183a4  test    al, 10h
0x1400183a6  jz      loc_140018458
0x1400183ac  and     eax, 1
0x1400183af  test    eax, eax
0x1400183b1  jnz     loc_140018442
0x1400183b7  mov     eax, gs:1A4h
0x1400183bf  mov     r8, cs:TcpReceiveRequestPool
0x1400183c6  lea     r13d, [rax+1]
0x1400183ca  shl     r13, 7
0x1400183ce  add     r13, r8
0x1400183d1  movzx   eax, byte ptr [r13+0B0h]
0x1400183d9  test    al, al
0x1400183db  jnz     short loc_1400183E9
0x1400183dd  lea     rdx, [r13+40h]
0x1400183e1  mov     rcx, r8
0x1400183e4  call    PplpLazyInitializeLookasideList
0x1400183e9  mov     rdx, rbx; Entry
0x1400183ec  lea     rcx, [r13+40h]; Lookaside
0x1400183f0  call    cs:__imp_ExFreeToLookasideListEx
0x1400183f7  nop     dword ptr [rax+rax+00h]
0x1400183fc  mov     r13, qword ptr [rbp+47h+var_60]
0x140018400  mov     eax, [rbp+47h+var_A8]
0x140018403  test    r13, r13
0x140018406  movzx   eax, al
0x140018409  mov     ecx, 1
0x14001840e  cmovz   eax, ecx
0x140018411  mov     rbx, r13
0x140018414  mov     rcx, r15; SpinLock
0x140018417  mov     [rbp+47h+var_A8], eax
0x14001841a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x140018421  nop     dword ptr [rax+rax+00h]
0x140018426  mov     r13, [rbp+47h+var_88]
0x14001842a  jmp     loc_1400180C1
0x14001842f  mov     eax, [rbx+18h]
0x140018432  test    al, 8
0x140018434  jnz     loc_1400180BE
0x14001843a  xor     r14b, r14b
  ... truncated ...
```
