# TcpSatisfyReceiveRequests

- ea: `0x1400ae1c0`
- end: `0x1400ae7f2`
- name: `TcpSatisfyReceiveRequests`
- size: `1586`
- prototype: `__int64 __usercall@<rax>(PKSPIN_LOCK SpinLock@<rcx>, __int64, __int64)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1400ad3b0`

## callees

- `0x14001e920`
- `0x140053b50`
- `0x1400540a4`
- `0x140055e64`
- `0x1400ae1c0`
- `0x1400ae7f8`
- `0x1400ae8d4`
- `0x1400ae96c`
- `0x14014cefc`
- `0x1401bf4d0`
- `0x1401bf700`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae4e5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae69a`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae4e5`
- `ntoskrnl!KeAcquireSpinLockAtDpcLevel` at `0x1400ae69a`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae3cb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae5c3`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae3cb`
- `ntoskrnl!KeReleaseSpinLockFromDpcLevel` at `0x1400ae5c3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae4d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae670`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae4d3`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x1400ae670`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ae2b7`
- `NETIO!RtlCopyMdlToMdlIndirect` at `0x1400ae2b7`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x1400ae2d2`
- `NETIO!NetioAdvanceToLocationInNetBuffer` at `0x1400ae2d2`

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
            (unsigned int)&TCP_DELIVERY_SATISFIED,
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
      v17 = (char *)qword_140224610 + 64 * (unsigned __int64)v42;
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
            (unsigned int)&TCP_DELIVERY_SATISFIED,
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
        if ( qword_140224478 )
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
0x1400ae1c0  mov     r11, rsp
0x1400ae1c3  push    rbp
0x1400ae1c4  push    rbx
0x1400ae1c5  push    rsi
0x1400ae1c6  push    r13
0x1400ae1c8  push    r14
0x1400ae1ca  push    r15
0x1400ae1cc  lea     rbp, [r11-4Fh]
0x1400ae1d0  sub     rsp, 0F8h
0x1400ae1d7  mov     rax, cs:__security_cookie
0x1400ae1de  xor     rax, rsp
0x1400ae1e1  mov     [rbp+47h+var_50], rax
0x1400ae1e5  mov     rax, [rbp+47h+arg_28]
0x1400ae1e9  mov     r15, rcx
0x1400ae1ec  mov     rcx, [rbp+47h+arg_20]
0x1400ae1f0  mov     rsi, [r9]
0x1400ae1f3  mov     [rbp+47h+var_A4], r8d
0x1400ae1f7  xor     r8d, r8d
0x1400ae1fa  mov     [r11-38h], rdi
0x1400ae1fe  mov     r13d, r8d
0x1400ae201  mov     rbx, [rcx]
0x1400ae204  mov     dword ptr [rax], 2
0x1400ae20a  mov     [rbp+47h+var_70], r9
0x1400ae20e  mov     [rbp+47h+var_80], rdx
0x1400ae212  mov     [rbp+47h+var_68], rcx
0x1400ae216  mov     [rbp+47h+var_78], rax
0x1400ae21a  mov     [rbp+47h+var_88], r8
0x1400ae21e  mov     byte ptr [rbp+47h+var_A8], r8b
0x1400ae222  mov     [r11-40h], r12
0x1400ae226  mov     eax, [rbx+18h]
0x1400ae229  mov     r14, 7FFFFFFFFFFFFFFFh
0x1400ae233  mov     rdx, [rsi+8]
0x1400ae237  test    al, 4
0x1400ae239  jnz     loc_1400AE6E2
0x1400ae23f  mov     edi, [rdx+18h]
0x1400ae242  mov     rcx, [rbx+28h]
0x1400ae246  sub     rcx, [rbx+30h]
0x1400ae24a  cmp     rdi, rcx
0x1400ae24d  cmovnb  rdi, rcx
0x1400ae251  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400ae255  jz      loc_1400AE6E9
0x1400ae25b  test    rdi, rdi
0x1400ae25e  jz      loc_1400AE320
0x1400ae264  mov     [rbp+47h+var_A0], r8
0x1400ae268  lea     r9, [rbp+47h+var_AC]
0x1400ae26c  mov     [rbp+47h+var_98], r8
0x1400ae270  lea     rcx, [rbp+47h+var_A0]
0x1400ae274  mov     [rbp+47h+var_B0], r8d
0x1400ae278  mov     [rbp+47h+var_AC], r8d
0x1400ae27c  mov     [rbp+47h+var_90], r8
0x1400ae280  lea     r8, [rbp+47h+var_98]
0x1400ae284  mov     rax, [rdx+8]
0x1400ae288  mov     [rbp+47h+var_A0], rax
0x1400ae28c  mov     eax, [rdx+10h]
0x1400ae28f  lea     rdx, [rbp+47h+var_B0]
0x1400ae293  mov     [rbp+47h+var_B0], eax
0x1400ae296  mov     rax, [rbx+10h]
0x1400ae29a  mov     [rbp+47h+var_98], rax
0x1400ae29e  mov     eax, [rbx+1Ch]
0x1400ae2a1  mov     [rbp+47h+var_AC], eax
0x1400ae2a4  lea     rax, [rbp+47h+var_90]
0x1400ae2a8  mov     qword ptr [rsp+120h+var_F0], rax
0x1400ae2ad  mov     byte ptr [rsp+120h+var_F8], 0
0x1400ae2b2  mov     [rsp+120h+var_100], rdi
0x1400ae2b7  call    cs:__imp_RtlCopyMdlToMdlIndirect
0x1400ae2be  nop     dword ptr [rax+rax+00h]
0x1400ae2c3  mov     r9d, [rbp+47h+var_B0]
0x1400ae2c7  mov     r8, [rbp+47h+var_A0]
0x1400ae2cb  mov     edx, dword ptr [rbp+47h+var_90]
0x1400ae2ce  mov     rcx, [rsi+8]
0x1400ae2d2  call    cs:__imp_NetioAdvanceToLocationInNetBuffer
0x1400ae2d9  nop     dword ptr [rax+rax+00h]
0x1400ae2de  mov     rax, [rbp+47h+var_98]
0x1400ae2e2  mov     [rbx+10h], rax
0x1400ae2e6  mov     eax, [rbp+47h+var_AC]
0x1400ae2e9  mov     [rbx+1Ch], eax
0x1400ae2ec  mov     rax, [rbp+47h+var_90]
0x1400ae2f0  add     [rbx+30h], rax
0x1400ae2f4  add     r13, rax
0x1400ae2f7  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400ae2fd  mov     [rbp+47h+var_88], r13
0x1400ae301  test    eax, eax
0x1400ae303  jz      short loc_1400AE320
0x1400ae305  mov     rcx, [rsi+0F8h]
0x1400ae30c  and     rcx, r14
0x1400ae30f  jz      short loc_1400AE320
0x1400ae311  cmp     qword ptr [rbx+38h], 0
0x1400ae316  jnz     loc_1400AE548
0x1400ae31c  mov     [rbx+38h], rcx
0x1400ae320  mov     rax, [rbx+28h]
0x1400ae324  cmp     [rbx+30h], rax
0x1400ae328  jz      loc_1400AE5C0
0x1400ae32e  xor     r12b, r12b
0x1400ae331  cmp     dword ptr [rsi+88h], 0
0x1400ae338  jge     loc_1400AE6AF
0x1400ae33e  mov     r14b, 1
0x1400ae341  mov     rax, [rsi+8]
0x1400ae345  cmp     dword ptr [rax+18h], 0
0x1400ae349  jnz     loc_1400AE530
0x1400ae34f  mov     r8d, [rbp+47h+var_A4]
0x1400ae353  mov     rdi, [rsi]
0x1400ae356  mov     edx, r8d
0x1400ae359  shl     rdx, 6
0x1400ae35d  add     rdx, cs:qword_140224610
0x1400ae364  mov     qword ptr [rsi], 0
0x1400ae36b  cmp     qword ptr [rdx+28h], 0
0x1400ae370  jnz     loc_1400AE56D
0x1400ae376  mov     [rdx+28h], rsi
0x1400ae37a  mov     ecx, r8d
0x1400ae37d  mov     [rdx+30h], rsi
0x1400ae381  call    TcpScheduleFlushDelay
0x1400ae386  mov     rsi, rdi
0x1400ae389  test    rdi, rdi
0x1400ae38c  jnz     loc_1400AE53A
0x1400ae392  test    r12b, r12b
0x1400ae395  jnz     loc_1400AE4F1
0x1400ae39b  movzx   ecx, byte ptr [r15+84h]
0x1400ae3a3  mov     rdi, [rbp+47h+var_80]
0x1400ae3a7  test    cl, cl
0x1400ae3a9  jnz     short loc_1400AE3BF
0x1400ae3ab  cmp     rdi, [r15+290h]
0x1400ae3b2  jz      short loc_1400AE3BF
0x1400ae3b4  mov     eax, [rbx+18h]
0x1400ae3b7  test    al, 6
0x1400ae3b9  jnz     loc_1400AE4F1
0x1400ae3bf  test    r14b, r14b
0x1400ae3c2  jz      loc_1400AE579
0x1400ae3c8  mov     rcx, r15; SpinLock
0x1400ae3cb  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400ae3d2  nop     dword ptr [rax+rax+00h]
0x1400ae3d7  mov     rax, [rbp+47h+var_78]
0x1400ae3db  mov     dword ptr [rax], 1
0x1400ae3e1  cmp     cs:dword_1402201D4, 0
0x1400ae3e8  jz      short loc_1400AE404
0x1400ae3ea  cmp     cs:TcpipTraceFiltersExist, 0
0x1400ae3f1  jnz     loc_1400AE7DD
0x1400ae3f7  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, 1
0x1400ae3fe  jnz     loc_1400AE6FE
0x1400ae404  mov     rax, [rbx]
0x1400ae407  xor     edx, edx
0x1400ae409  mov     r9, [rbx+38h]
0x1400ae40d  mov     r8, [rbx+30h]
0x1400ae411  mov     rcx, [rbx+8]
0x1400ae415  mov     r14, [rbx+40h]
0x1400ae419  call    _guard_dispatch_icall
0x1400ae41e  mov     rax, cs:qword_140224478
0x1400ae425  test    rax, rax
0x1400ae428  jz      short loc_1400AE483
0x1400ae42a  mov     rcx, [r15+20h]
0x1400ae42e  mov     r9, [rbx+30h]
0x1400ae432  mov     r8, [r15+350h]
0x1400ae439  mov     rax, [rcx]
0x1400ae43c  mov     rdx, [rax+10h]
0x1400ae440  movzx   eax, word ptr [r15+76h]
0x1400ae445  mov     word ptr [rsp+120h+var_E0], ax
0x1400ae44a  movzx   eax, word ptr [r15+74h]
0x1400ae44f  mov     word ptr [rsp+120h+var_E8], ax
0x1400ae454  mov     rax, [rcx+10h]
0x1400ae458  lea     rcx, TcpInetTransport
0x1400ae45f  mov     qword ptr [rsp+120h+var_F0], rax
0x1400ae464  mov     rax, [rdx]
0x1400ae467  mov     edx, 60Bh
0x1400ae46c  mov     [rsp+120h+var_F8], rax
0x1400ae471  movzx   eax, word ptr [r15+332h]
0x1400ae479  mov     word ptr [rsp+120h+var_100], ax
0x1400ae47e  call    InetTraceBasicDataCore
0x1400ae483  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x1400ae489  test    al, 10h
0x1400ae48b  jz      loc_1400AE5B6
0x1400ae491  and     eax, 1
0x1400ae494  test    eax, eax
0x1400ae496  jnz     loc_1400AE59D
0x1400ae49c  mov     eax, gs:1A4h
0x1400ae4a4  mov     r8, cs:TcpReceiveRequestPool
0x1400ae4ab  lea     edi, [rax+1]
0x1400ae4ae  shl     rdi, 7
0x1400ae4b2  add     rdi, r8
0x1400ae4b5  movzx   eax, byte ptr [rdi+0B0h]
0x1400ae4bc  test    al, al
0x1400ae4be  jnz     short loc_1400AE4CC
0x1400ae4c0  lea     rdx, [rdi+40h]
0x1400ae4c4  mov     rcx, r8
0x1400ae4c7  call    PplpLazyInitializeLookasideList
0x1400ae4cc  mov     rdx, rbx; Entry
0x1400ae4cf  lea     rcx, [rdi+40h]; Lookaside
0x1400ae4d3  call    cs:__imp_ExFreeToLookasideListEx
0x1400ae4da  nop     dword ptr [rax+rax+00h]
0x1400ae4df  mov     rcx, r15; SpinLock
0x1400ae4e2  mov     rbx, r14
0x1400ae4e5  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400ae4ec  nop     dword ptr [rax+rax+00h]
0x1400ae4f1  mov     rax, [rbp+47h+var_70]
0x1400ae4f5  mov     r12, [rsp+120h+var_38]
0x1400ae4fd  mov     rdi, [rsp+0F0h]
0x1400ae505  mov     [rax], rsi
0x1400ae508  mov     rax, [rbp+47h+var_68]
0x1400ae50c  mov     [rax], rbx
0x1400ae50f  mov     rax, r13
0x1400ae512  mov     rcx, [rbp+47h+var_50]
0x1400ae516  xor     rcx, rsp; StackCookie
0x1400ae519  call    __security_check_cookie
0x1400ae51e  add     rsp, 0F8h
0x1400ae525  pop     r15
0x1400ae527  pop     r14
0x1400ae529  pop     r13
0x1400ae52b  pop     rsi
0x1400ae52c  pop     rbx
0x1400ae52d  pop     rbp
0x1400ae52e  retn
0x1400ae530  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x1400ae534  jz      loc_1400AE34F
0x1400ae53a  cmp     byte ptr [rbp+47h+var_A8], 0
0x1400ae53e  jnz     short loc_1400AE4F1
0x1400ae540  xor     r8d, r8d
0x1400ae543  jmp     loc_1400AE226
0x1400ae548  mov     eax, cs:Microsoft_Windows_Networking_CorrelationEnabled
0x1400ae54e  test    eax, eax
0x1400ae550  jz      loc_1400AE320
0x1400ae556  mov     rdx, rcx
0x1400ae559  mov     r8d, 0Dh
0x1400ae55f  mov     rcx, [rbx+38h]
0x1400ae563  call    TcpipEtwTransferActivity
0x1400ae568  jmp     loc_1400AE320
0x1400ae56d  mov     rax, [rdx+30h]
0x1400ae571  mov     [rax], rsi
0x1400ae574  jmp     loc_1400AE37A
0x1400ae579  test    cl, cl
0x1400ae57b  jnz     loc_1400AE3C8
0x1400ae581  cmp     rdi, [r15+290h]
0x1400ae588  jz      loc_1400AE3C8
0x1400ae58e  mov     rax, [rbp+47h+var_78]
0x1400ae592  mov     dword ptr [rax], 0
0x1400ae598  jmp     loc_1400AE4F1
0x1400ae59d  movzx   r8d, word ptr [rbx+20h]
0x1400ae5a2  mov     rdx, rbx
0x1400ae5a5  mov     rcx, cs:TcpReceiveRequestPool
0x1400ae5ac  call    PplFreeToLookasideListProcessor
0x1400ae5b1  jmp     loc_1400AE4DF
0x1400ae5b6  call    Feature_Servicing_TCPIPPPLOptimization__private_IsEnabledDeviceUsageNoInline
0x1400ae5bb  jmp     loc_1400AE494
0x1400ae5c0  mov     rcx, r15; SpinLock
0x1400ae5c3  call    cs:__imp_KeReleaseSpinLockFromDpcLevel
0x1400ae5ca  nop     dword ptr [rax+rax+00h]
0x1400ae5cf  mov     rax, [rbp+47h+var_78]
0x1400ae5d3  mov     ecx, 1
0x1400ae5d8  xor     r14b, r14b
0x1400ae5db  mov     r12b, 1
0x1400ae5de  mov     [rax], ecx
0x1400ae5e0  cmp     cs:dword_1402201D4, 0
0x1400ae5e7  jz      short loc_1400AE609
0x1400ae5e9  cmp     cs:TcpipTraceFiltersExist, r14b
0x1400ae5f0  jnz     loc_1400AE7C8
0x1400ae5f6  test    byte ptr cs:WPP_MAIN_CB.Reserved+3, cl
0x1400ae5fc  xorps   xmm0, xmm0
0x1400ae5ff  movups  [rbp+47h+var_60], xmm0
0x1400ae603  jnz     loc_1400AE768
0x1400ae609  mov     r13, [rbx+40h]
0x1400ae60d  mov     r8, r15
0x1400ae610  xor     edx, edx
0x1400ae612  mov     qword ptr [rbp+47h+var_60], r13
0x1400ae616  mov     rcx, rbx
0x1400ae619  call    TcpCompleteClientReceiveRequest
0x1400ae61e  mov     eax, cs:Feature_Servicing_TCPIPPPLOptimization__private_featureState
0x1400ae624  test    al, 10h
0x1400ae626  jz      loc_1400AE6D8
0x1400ae62c  and     eax, 1
0x1400ae62f  test    eax, eax
0x1400ae631  jnz     loc_1400AE6C2
0x1400ae637  mov     eax, gs:1A4h
0x1400ae63f  mov     r8, cs:TcpReceiveRequestPool
0x1400ae646  lea     r13d, [rax+1]
0x1400ae64a  shl     r13, 7
0x1400ae64e  add     r13, r8
0x1400ae651  movzx   eax, byte ptr [r13+0B0h]
0x1400ae659  test    al, al
0x1400ae65b  jnz     short loc_1400AE669
0x1400ae65d  lea     rdx, [r13+40h]
0x1400ae661  mov     rcx, r8
0x1400ae664  call    PplpLazyInitializeLookasideList
0x1400ae669  mov     rdx, rbx; Entry
0x1400ae66c  lea     rcx, [r13+40h]; Lookaside
0x1400ae670  call    cs:__imp_ExFreeToLookasideListEx
0x1400ae677  nop     dword ptr [rax+rax+00h]
0x1400ae67c  mov     r13, qword ptr [rbp+47h+var_60]
0x1400ae680  mov     eax, [rbp+47h+var_A8]
0x1400ae683  test    r13, r13
0x1400ae686  movzx   eax, al
0x1400ae689  mov     ecx, 1
0x1400ae68e  cmovz   eax, ecx
0x1400ae691  mov     rbx, r13
0x1400ae694  mov     rcx, r15; SpinLock
0x1400ae697  mov     [rbp+47h+var_A8], eax
0x1400ae69a  call    cs:__imp_KeAcquireSpinLockAtDpcLevel
0x1400ae6a1  nop     dword ptr [rax+rax+00h]
0x1400ae6a6  mov     r13, [rbp+47h+var_88]
0x1400ae6aa  jmp     loc_1400AE341
0x1400ae6af  mov     eax, [rbx+18h]
0x1400ae6b2  test    al, 8
0x1400ae6b4  jnz     loc_1400AE33E
0x1400ae6ba  xor     r14b, r14b
  ... truncated ...
```
