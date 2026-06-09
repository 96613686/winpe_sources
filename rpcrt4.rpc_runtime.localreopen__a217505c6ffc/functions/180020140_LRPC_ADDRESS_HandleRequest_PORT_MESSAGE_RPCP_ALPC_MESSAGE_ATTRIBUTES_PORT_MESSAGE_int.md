# LRPC_ADDRESS::HandleRequest(_PORT_MESSAGE *,RPCP_ALPC_MESSAGE_ATTRIBUTES *,_PORT_MESSAGE *,int)

- ea: `0x180020140`
- end: `0x180020a50`
- name: `?HandleRequest@LRPC_ADDRESS@@AEAAXPEAU_PORT_MESSAGE@@PEAVRPCP_ALPC_MESSAGE_ATTRIBUTES@@0H@Z`
- size: `2320`
- prototype: `void __fastcall(LRPC_ADDRESS *this, struct _PORT_MESSAGE *, struct RPCP_ALPC_MESSAGE_ATTRIBUTES *, struct _PORT_MESSAGE *, int)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180020a60`

## callees

- `0x18001831c`
- `0x180019640`
- `0x180019b58`
- `0x180019fe0`
- `0x18001a040`
- `0x18001a170`
- `0x18001a264`
- `0x18001a30c`
- `0x18001a690`
- `0x18001b2c0`
- `0x18001b4d0`
- `0x18001c008`
- `0x180020140`
- `0x1800217d0`
- `0x180023020`
- `0x180025d70`
- `0x1800263a0`
- `0x180027e20`
- `0x18007e700`
- `0x18009858c`
- `0x1800a112c`
- `0x1800a1188`
- `0x1800a84a4`
- `0x1800cec91`
- `0x1800ceda0`
- `0x1800d7010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x1800207ba`
- `ntdll!EtwEventActivityIdControl` at `0x1800207ba`
- `ntdll!RtlLeaveCriticalSection` at `0x180020822`
- `ntdll!RtlLeaveCriticalSection` at `0x180020857`
- `ntdll!RtlLeaveCriticalSection` at `0x180020822`
- `ntdll!RtlLeaveCriticalSection` at `0x180020857`
- `ntdll!RtlEnterCriticalSection` at `0x1800207df`
- `ntdll!RtlEnterCriticalSection` at `0x1800207df`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180020302`
- `api-ms-win-core-interlocked-l1-1-0!InterlockedPopEntrySList` at `0x180020302`

## pseudocode

```c
void __fastcall LRPC_ADDRESS::HandleRequest(
        LRPC_ADDRESS *this,
        struct _PORT_MESSAGE *a2,
        struct RPCP_ALPC_MESSAGE_ATTRIBUTES *a3,
        struct _PORT_MESSAGE *a4,
        int a5)
{
  int v7; // r8d
  int v9; // r10d
  __int64 v10; // rdx
  RPCP_ALPC_HANDLE_ATTR *v11; // rsi
  unsigned __int64 v12; // rcx
  __int64 v14; // r15
  __int64 v15; // r12
  size_t v16; // r8
  char *v17; // r13
  _QWORD *v18; // r14
  signed __int64 v19; // rbx
  int DoNotUseThisField_low; // eax
  signed __int64 v21; // rdx
  PSLIST_ENTRY v22; // rax
  PSLIST_ENTRY v23; // rax
  int v24; // r14d
  int v25; // r14d
  int v26; // r15d
  BOOL v27; // esi
  BOOL v28; // r15d
  LRPC_SASSOCIATION *v29; // rbx
  int v30; // eax
  unsigned __int64 v31; // rcx
  BCACHE *v32; // rcx
  LRPC_SCALL *v33; // rax
  CALL *v34; // rcx
  _BYTE *p_DoNotUseThisField; // r13
  int v36; // ecx
  int v37; // r13d
  struct _PORT_MESSAGE *v38; // r12
  int v39; // eax
  void *v40; // rdx
  LRPC_ADDRESS *v41; // r8
  unsigned int HeaderSize; // eax
  BCACHE *v43; // rcx
  struct _SLIST_ENTRY *v44; // rax
  struct _SLIST_ENTRY *v45; // r14
  struct _RTL_CRITICAL_SECTION *v46; // r14
  __int64 v47; // r15
  _QWORD *v48; // rcx
  LRPC_SCALL *v49; // rax
  int v50; // [rsp+40h] [rbp-98h] BYREF
  struct _PORT_MESSAGE *v51; // [rsp+48h] [rbp-90h]
  size_t Size; // [rsp+50h] [rbp-88h]
  _QWORD *v53; // [rsp+58h] [rbp-80h]
  CALL *v54; // [rsp+60h] [rbp-78h]
  __int64 v55; // [rsp+68h] [rbp-70h] BYREF
  ULONG Length; // [rsp+70h] [rbp-68h]
  int v57; // [rsp+74h] [rbp-64h]
  SIZE_T ClientViewSize; // [rsp+78h] [rbp-60h]

  v7 = *(_DWORD *)a3;
  v9 = *((_DWORD *)a3 + 1);
  v10 = (v7 >> 31) & 0x18;
  v11 = 0;
  v12 = (v7 & 0x40000000 | 0x10000000uLL) >> 25;
  v14 = *(_QWORD *)((char *)a3 + v10 + v12);
  if ( (v9 & 0x10000000) != 0 )
    v11 = (struct RPCP_ALPC_MESSAGE_ATTRIBUTES *)((char *)a3 + v10 + (HIBYTE(v7) & 0x20) + v12);
  if ( (v9 & 0x40000000) == 0 )
  {
    v15 = 0;
    if ( a2->u1.s1.TotalLength >= 0x68u )
    {
      v16 = 0;
      Size = 0;
      goto LABEL_6;
    }
    goto LABEL_29;
  }
  HeaderSize = RpcpAlpcpGetHeaderSize(v7 & 0x80000000);
  v15 = *(_QWORD *)((char *)a3 + HeaderSize + 16);
  if ( a2->u1.s1.TotalLength < 0x70u
    || (v16 = *(_QWORD *)&a2[2].MessageId, Size = v16, *(_QWORD *)((char *)a3 + HeaderSize + 24) < v16) )
  {
LABEL_29:
    v25 = 1728;
    v26 = 1;
    goto LABEL_30;
  }
  if ( (*(_DWORD *)((_BYTE *)a3 + HeaderSize) & 0x40000) == 0 )
  {
    v44 = BCACHE::Allocate(v43, v16);
    v45 = v44;
    if ( !v44 )
    {
      v25 = 14;
      if ( (LOBYTE(a2[1].DoNotUseThisField) & 2) != 0 )
        v26 = LRPC_SASSOCIATION::CFCallDispatchFailure((LRPC_SASSOCIATION *)v14, (struct _LRPC_REQUEST_MESSAGE *)a2);
      else
        v26 = 0;
LABEL_30:
      if ( v11 )
        RPCP_ALPC_HANDLE_ATTR::Cleanup(v11);
      v27 = v26 == 0;
      v28 = v15 != 0;
      v29 = *(LRPC_SASSOCIATION **)((char *)a3
                                  + ((*(int *)a3 >> 31) & 0x18)
                                  + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25));
      SetFaultPacket((struct _LRPC_FAULT_MESSAGE *)a2, v25, v27, a5);
      v30 = LRPC_ADDRESS::AlpcSend(this, a2, v28, 0, 0, 0, 0);
      if ( v30 < 0
        && (*(unsigned int (__fastcall **)(LRPC_ADDRESS *, _QWORD))(*(_QWORD *)this + 184LL))(this, (unsigned int)v30) == 14 )
      {
        SetCommonFaultFields((struct _LRPC_FAULT_MESSAGE *)a2, v25, 0, v27);
        LRPC_ADDRESS::AlpcSend(this, a2, v28, 0, 0, 0, 0);
      }
      LRPC_SASSOCIATION::MessageReceived(v29);
      v31 = *((_QWORD *)this + 37);
      if ( v31 && (unsigned __int64)a2 > v31 && (unsigned __int64)a2 < v31 + *((unsigned int *)this + 76) )
        LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(this, a2);
      else
        FreeEmergencyOrNormalMessage(a2);
      if ( a4 )
        goto LABEL_36;
      return;
    }
    memcpy_0(v44, (const void *)v15, Size);
    LRPC_ADDRESS::AlpcFreeView(this, (void *)v15);
    v9 = *((_DWORD *)a3 + 1);
    v16 = Size;
    v15 = (unsigned __int64)v45 | 1;
  }
LABEL_6:
  if ( (v9 & 0x8000000) != 0 )
    v17 = (char *)a3
        + (HIBYTE(*(_DWORD *)a3) & 0x20)
        + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25)
        + ((*(int *)a3 >> 31) & 0x18)
        + ((*(_DWORD *)a3 & 0x10000000) != 0 ? 0x18 : 0);
  else
    v17 = 0;
  if ( (v9 & 0x2000000) != 0 )
  {
    v16 = Size;
    v18 = (_QWORD *)((char *)a3
                   + ((*(_DWORD *)a3 & 0x10000000) != 0 ? 0x18 : 0)
                   + ((*(_DWORD *)a3 >> 23) & 8)
                   + (HIBYTE(*(_DWORD *)a3) & 0x20)
                   + ((*(_DWORD *)a3 & 0x40000000 | 0x10000000uLL) >> 25)
                   + ((*(int *)a3 >> 31) & 0x18)
                   + ((*(_DWORD *)a3 & 0x8000000) != 0 ? 0x18 : 0));
  }
  else
  {
    v18 = 0;
  }
  v19 = 0;
  v53 = v18;
  if ( !a4 )
  {
    v51 = a2;
    v24 = 14;
    goto LABEL_51;
  }
  *(_OWORD *)&a4->u1.s1.DataLength = *(_OWORD *)&a2->u1.s1.DataLength;
  *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&a4->8 + 8) = *(union _PORT_MESSAGE::$C6BC508B531A81D74C33985719C23F49 *)((char *)&a2->8 + 8);
  a4->ClientViewSize = a2->ClientViewSize;
  DoNotUseThisField_low = LODWORD(a2[1].DoNotUseThisField);
  if ( (DoNotUseThisField_low & 0x40) == 0 )
  {
    v21 = *(_QWORD *)(v14 + 400);
    LODWORD(v51) = HIDWORD(a2[1].DoNotUseThisField);
    if ( v21 && v21 == _InterlockedCompareExchange64((volatile signed __int64 *)(v14 + 400), 0, v21) )
    {
      v19 = v21;
LABEL_17:
      *(_DWORD *)(v19 + 532) = (_DWORD)v51;
      *(_QWORD *)(v19 + 24) = 0;
      *(_QWORD *)(v19 + 40) = 0;
      *(_QWORD *)(v19 + 312) = 0;
      *(_QWORD *)(v19 + 592) = 0;
      REFERENCED_OBJECT::SingleThreadedAddReference((REFERENCED_OBJECT *)v19);
      if ( dword_1800FE624 )
      {
        if ( UuidCreate((UUID *)(v19 + 208)) )
          *(GUID *)(v19 + 208) = g_NullActivityId;
        EtwEventActivityIdControl(2);
      }
      else
      {
        *(GUID *)(v19 + 208) = g_NullActivityId;
      }
LABEL_19:
      if ( v17 )
      {
        *(_OWORD *)(v19 + 624) = *(_OWORD *)v17;
        *(_QWORD *)(v19 + 640) = *((_QWORD *)v17 + 2);
        _InterlockedOr((volatile signed __int32 *)(v19 + 232), 0x8000u);
      }
      else
      {
        _InterlockedAnd((volatile signed __int32 *)(v19 + 232), 0xFFFF7FFF);
      }
      if ( v18 )
      {
        *(_QWORD *)(v19 + 648) = *v18;
        _InterlockedOr((volatile signed __int32 *)(v19 + 232), 0x10000u);
      }
      else
      {
        _InterlockedAnd((volatile signed __int32 *)(v19 + 232), 0xFFFEFFFF);
      }
      v24 = RpcpConvertToLongRunning();
      if ( v24 )
      {
        v51 = a4;
      }
      else
      {
        if ( (*(_DWORD *)(v19 + 232) & 0x400) != 0 )
        {
          if ( !*(_DWORD *)(v14 + 200) )
          {
            *(_DWORD *)(v19 + 232) &= ~0x400u;
LABEL_27:
            LRPC_SCALL::HandleRequest((LRPC_SCALL *)v19, a2, a4, (void *)v15, Size, v11);
            return;
          }
        }
        else
        {
          v46 = (struct _RTL_CRITICAL_SECTION *)(v14 + 112);
          RtlEnterCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 112));
          if ( !*(_DWORD *)(v14 + 200) )
          {
            v47 = v14 + 248;
            v48 = *(_QWORD **)(v47 + 8);
            if ( *v48 != v47 )
              __fastfail(3u);
            *(_QWORD *)(v19 + 552) = v48;
            *(_QWORD *)(v19 + 544) = v47;
            *v48 = v19 + 544;
            *(_QWORD *)(v47 + 8) = v19 + 544;
            RtlLeaveCriticalSection(v46);
            goto LABEL_27;
          }
          RtlLeaveCriticalSection((PRTL_CRITICAL_SECTION)(v14 + 112));
        }
        v24 = 1727;
        v51 = a4;
      }
LABEL_51:
      p_DoNotUseThisField = (_BYTE *)&a2[1].DoNotUseThisField;
      if ( !v11 )
        goto LABEL_53;
      goto LABEL_52;
    }
    v22 = InterlockedPopEntrySList((PSLIST_HEADER)(v14 + 416));
    if ( v22 )
    {
      v23 = v22 - 37;
      if ( v23 )
      {
        v19 = (signed __int64)v23;
        goto LABEL_17;
      }
    }
    v50 = 0;
    if ( gfRPCVerifierEnabled )
    {
      v49 = (LRPC_SCALL *)AllocWrapper(0x290u);
      v54 = v49;
      if ( v49 )
      {
        LRPC_SCALL::LRPC_SCALL(v49, &v50, (struct LRPC_SASSOCIATION *)v14, (unsigned int)v51);
        v34 = v54;
        *(_QWORD *)v54 = &LRPC_SCALL_AVRF::`vftable';
LABEL_40:
        v24 = v50;
        if ( v50 )
        {
          (*(void (__fastcall **)(CALL *, __int64))(*(_QWORD *)v34 + 8LL))(v34, 1);
        }
        else
        {
          v19 = (signed __int64)v34;
          CALL::CreateAndSetActivityId(v34);
        }
        goto LABEL_42;
      }
    }
    else
    {
      v33 = (LRPC_SCALL *)AllocWrapper(0x290u);
      if ( v33 )
      {
        v34 = LRPC_SCALL::LRPC_SCALL(v33, &v50, (struct LRPC_SASSOCIATION *)v14, (unsigned int)v51);
        if ( v34 )
          goto LABEL_40;
      }
    }
    v24 = 14;
LABEL_42:
    if ( v24 )
    {
      v51 = a4;
      goto LABEL_51;
    }
    v18 = v53;
    goto LABEL_19;
  }
  if ( (DoNotUseThisField_low & 2) != 0 )
  {
    v24 = 1728;
    v51 = a4;
    goto LABEL_51;
  }
  if ( !v11 )
  {
    LRPC_SASSOCIATION::HandlePipeChunk((LRPC_SASSOCIATION *)v14, a2, a4, (void *)v15, v16, a5);
    return;
  }
  v24 = 1728;
  v51 = a4;
  p_DoNotUseThisField = (_BYTE *)&a2[1].DoNotUseThisField;
LABEL_52:
  RPCP_ALPC_HANDLE_ATTR::Cleanup(v11);
LABEL_53:
  if ( (*p_DoNotUseThisField & 2) != 0 )
  {
    Length = a2[2].u1.Length;
    ClientViewSize = a2[1].ClientViewSize;
    v57 = 256;
    v55 = 1;
    LRPC_SASSOCIATION::ProcessCausalFlowGapBatch((LRPC_SASSOCIATION *)v14, (struct _LRPC_BROKEN_FLOWS_MESSAGE *)&v55);
    v36 = (unsigned __int8)v57;
  }
  else
  {
    v36 = 1;
  }
  v50 = v36;
  if ( v15 )
  {
    if ( (v15 & 1) != 0 )
    {
      v37 = 0;
      LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(*(LRPC_ADDRESS **)(v14 + 56), (void *)(v15 ^ 1));
      v36 = v50;
    }
    else
    {
      v37 = 1;
    }
  }
  else
  {
    v37 = 0;
  }
  v38 = v51;
  Size = *(_QWORD *)(v14 + 56);
  v50 = v36 == 0;
  SetFaultPacket((struct _LRPC_FAULT_MESSAGE *)v51, v24, v50, a5);
  v39 = LRPC_ADDRESS::AlpcSend((LRPC_ADDRESS *)Size, v38, v37, 0, 0, 0, 0);
  if ( v39 < 0
    && (*(unsigned int (__fastcall **)(size_t, _QWORD))(*(_QWORD *)Size + 184LL))(Size, (unsigned int)v39) == 14 )
  {
    SetCommonFaultFields((struct _LRPC_FAULT_MESSAGE *)v38, v24, 0, v50);
    LRPC_ADDRESS::AlpcSend((LRPC_ADDRESS *)Size, v38, v37, 0, 0, 0, 0);
  }
  if ( (unsigned int)LRPC_ADDRESS::IsBufferInCompletionList(*(LRPC_ADDRESS **)(v14 + 56), a2) )
    LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(v41, v40);
  else
    FreeEmergencyOrNormalMessage(a2);
  LRPC_SASSOCIATION::MessageReceived((LRPC_SASSOCIATION *)v14);
  if ( v19 )
    (*(void (__fastcall **)(signed __int64, __int64))(*(_QWORD *)v19 + 8LL))(v19, 1);
  if ( a4 )
LABEL_36:
    BCACHE::Free(v32, a4);
}

```

## disassembly

```asm
0x180020140  push    rbx
0x180020142  push    rbp
0x180020143  push    rsi
0x180020144  push    rdi
0x180020145  push    r13
0x180020147  push    r15
0x180020149  sub     rsp, 0A8h
0x180020150  mov     rax, cs:__security_cookie
0x180020157  xor     rax, rsp
0x18002015a  mov     [rsp+0D8h+var_58], rax
0x180020162  mov     r13, rcx
0x180020165  mov     rbx, r8
0x180020168  mov     r8d, [r8]
0x18002016b  mov     rdi, rdx
0x18002016e  mov     ecx, r8d
0x180020171  movsxd  rdx, r8d
0x180020174  sar     rdx, 3Fh
0x180020178  and     ecx, 40000000h
0x18002017e  mov     r10d, [rbx+4]
0x180020182  and     edx, 18h
0x180020185  bts     rcx, 1Ch
0x18002018a  xor     esi, esi
0x18002018c  shr     rcx, 19h
0x180020190  mov     rbp, r9
0x180020193  lea     rax, [rdx+rbx]
0x180020197  mov     r15, [rax+rcx]
0x18002019b  bt      r10d, 1Ch
0x1800201a0  jnb     short loc_1800201B5
0x1800201a2  mov     esi, r8d
0x1800201a5  shr     rsi, 18h
0x1800201a9  and     esi, 20h
0x1800201ac  add     rsi, rdx
0x1800201af  add     rsi, rbx
0x1800201b2  add     rsi, rcx
0x1800201b5  mov     [rsp+0D8h+var_38], r12
0x1800201bd  mov     [rsp+0D8h+var_40], r14
0x1800201c5  bt      r10d, 1Eh
0x1800201ca  jb      loc_18002070A
0x1800201d0  xor     r12d, r12d
0x1800201d3  cmp     word ptr [rdi+2], 68h ; 'h'
0x1800201d8  jb      loc_180020452
0x1800201de  xor     r8d, r8d
0x1800201e1  mov     [rsp+0D8h+Size], r8
0x1800201e6  bt      r10d, 1Bh
0x1800201eb  jnb     loc_180020909
0x1800201f1  mov     ecx, [rbx]
0x1800201f3  mov     eax, ecx
0x1800201f5  and     eax, 40000000h
0x1800201fa  movsxd  rdx, ecx
0x1800201fd  bts     rax, 1Ch
0x180020202  sar     rdx, 3Fh
0x180020206  shr     rax, 19h
0x18002020a  and     edx, 18h
0x18002020d  add     rdx, rax
0x180020210  mov     eax, ecx
0x180020212  shr     rax, 18h
0x180020216  and     ecx, 10000000h
0x18002021c  and     eax, 20h
0x18002021f  add     rax, rbx
0x180020222  neg     ecx
0x180020224  sbb     r13, r13
0x180020227  add     rax, rdx
0x18002022a  and     r13d, 18h
0x18002022e  add     r13, rax
0x180020231  bt      r10d, 19h
0x180020236  jnb     loc_180020792
0x18002023c  mov     edx, [rbx]
0x18002023e  mov     eax, edx
0x180020240  and     eax, 40000000h
0x180020245  movsxd  r8, edx
0x180020248  bts     rax, 1Ch
0x18002024d  sar     r8, 3Fh
0x180020251  shr     rax, 19h
0x180020255  and     r8d, 18h
0x180020259  add     r8, rax
0x18002025c  mov     eax, edx
0x18002025e  shr     rax, 18h
0x180020262  and     eax, 20h
0x180020265  add     r8, rax
0x180020268  mov     eax, edx
0x18002026a  shr     rax, 17h
0x18002026e  and     eax, 8
0x180020271  add     r8, rax
0x180020274  mov     eax, edx
0x180020276  and     eax, 10000000h
0x18002027b  neg     eax
0x18002027d  sbb     rcx, rcx
0x180020280  and     edx, 8000000h
0x180020286  and     ecx, 18h
0x180020289  add     rcx, rbx
0x18002028c  neg     edx
0x18002028e  sbb     r14, r14
0x180020291  add     rcx, r8
0x180020294  mov     r8, [rsp+0D8h+Size]
0x180020299  and     r14d, 18h
0x18002029d  add     r14, rcx
0x1800202a0  xor     ebx, ebx
0x1800202a2  mov     [rsp+0D8h+var_80], r14
0x1800202a7  test    rbp, rbp
0x1800202aa  jz      loc_1800205E6
0x1800202b0  movups  xmm0, xmmword ptr [rdi]
0x1800202b3  movups  xmmword ptr [rbp+0], xmm0
0x1800202b7  movups  xmm1, xmmword ptr [rdi+10h]
0x1800202bb  movups  xmmword ptr [rbp+10h], xmm1
0x1800202bf  movsd   xmm0, qword ptr [rdi+20h]
0x1800202c4  movsd   qword ptr [rbp+20h], xmm0
0x1800202c9  mov     eax, [rdi+30h]
0x1800202cc  test    al, 40h
0x1800202ce  jnz     loc_180020583
0x1800202d4  mov     rdx, [r15+190h]
0x1800202db  mov     eax, [rdi+34h]
0x1800202de  mov     dword ptr [rsp+0D8h+var_90], eax
0x1800202e2  test    rdx, rdx
0x1800202e5  jz      short loc_1800202FB
0x1800202e7  xor     ecx, ecx
0x1800202e9  mov     rax, rdx
0x1800202ec  lock cmpxchg [r15+190h], rcx
0x1800202f5  jz      loc_1800209A9
0x1800202fb  lea     rcx, [r15+1A0h]; ListHead
0x180020302  call    cs:__imp_InterlockedPopEntrySList
0x180020309  nop     dword ptr [rax+rax+00h]
0x18002030e  test    rax, rax
0x180020311  jz      loc_180020516
0x180020317  add     rax, 0FFFFFFFFFFFFFDB0h
0x18002031d  jz      loc_180020516
0x180020323  mov     rbx, rax
0x180020326  mov     r9d, dword ptr [rsp+0D8h+var_90]
0x18002032b  mov     rcx, rbx; this
0x18002032e  mov     [rbx+214h], r9d
0x180020335  mov     qword ptr [rbx+18h], 0
0x18002033d  mov     qword ptr [rbx+28h], 0
0x180020345  mov     qword ptr [rbx+138h], 0
0x180020350  mov     qword ptr [rbx+250h], 0
0x18002035b  nop
0x18002035c  call    ?SingleThreadedAddReference@REFERENCED_OBJECT@@QEAAXXZ; REFERENCED_OBJECT::SingleThreadedAddReference(void)
0x180020361  cmp     cs:dword_1800FE624, 0
0x180020368  jnz     loc_18002079A
0x18002036e  movups  xmm0, xmmword ptr cs:?g_NullActivityId@@3U_GUID@@B.Data1; _GUID const g_NullActivityId ...
0x180020375  movups  xmmword ptr [rbx+0D0h], xmm0
0x18002037c  test    r13, r13
0x18002037f  jz      loc_1800208CB
0x180020385  movups  xmm0, xmmword ptr [r13+0]
0x18002038a  movups  xmmword ptr [rbx+270h], xmm0
0x180020391  movsd   xmm1, qword ptr [r13+10h]
0x180020397  movsd   qword ptr [rbx+280h], xmm1
0x18002039f  lock or dword ptr [rbx+0E8h], 8000h
0x1800203aa  test    r14, r14
0x1800203ad  jz      loc_1800206FA
0x1800203b3  mov     rax, [r14]
0x1800203b6  mov     [rbx+288h], rax
0x1800203bd  lock or dword ptr [rbx+0E8h], 10000h
0x1800203c8  call    ?RpcpConvertToLongRunning@@YAJXZ; RpcpConvertToLongRunning(void)
0x1800203cd  mov     r14d, eax
0x1800203d0  test    eax, eax
0x1800203d2  jnz     loc_1800208FF
0x1800203d8  mov     eax, [rbx+0E8h]
0x1800203de  bt      eax, 0Ah
0x1800203e2  jnb     loc_1800207D8
0x1800203e8  mov     eax, [r15+0C8h]
0x1800203ef  test    eax, eax
0x1800203f1  jnz     loc_180020863
0x1800203f7  and     dword ptr [rbx+0E8h], 0FFFFFBFFh
0x180020401  mov     rax, [rsp+0D8h+Size]
0x180020406  mov     r9, r12; void *
0x180020409  mov     [rsp+0D8h+var_B0], rsi; struct RPCP_ALPC_HANDLE_ATTR *
0x18002040e  mov     r8, rbp; struct _PORT_MESSAGE *
0x180020411  mov     rdx, rdi; struct _PORT_MESSAGE *
0x180020414  mov     [rsp+0D8h+var_B8], rax; unsigned __int64
0x180020419  mov     rcx, rbx; this
0x18002041c  call    ?HandleRequest@LRPC_SCALL@@QEAAXPEAU_PORT_MESSAGE@@0PEAX_KPEAVRPCP_ALPC_HANDLE_ATTR@@@Z; LRPC_SCALL::HandleRequest(_PORT_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,RPCP_ALPC_HANDLE_ATTR *)
0x180020421  mov     r14, [rsp+0D8h+var_40]
0x180020429  mov     r12, [rsp+0D8h+var_38]
0x180020431  mov     rcx, [rsp+0D8h+var_58]
0x180020439  xor     rcx, rsp; StackCookie
0x18002043c  call    __security_check_cookie
0x180020441  add     rsp, 0A8h
0x180020448  pop     r15
0x18002044a  pop     r13
0x18002044c  pop     rdi
0x18002044d  pop     rsi
0x18002044e  pop     rbp
0x18002044f  pop     rbx
0x180020450  retn
0x180020452  mov     r14d, 6C0h
0x180020458  mov     r15d, 1
0x18002045e  test    rsi, rsi
0x180020461  jnz     loc_18002094A
0x180020467  movsxd  rcx, dword ptr [rbx]
0x18002046a  xor     esi, esi
0x18002046c  mov     r9d, [rsp+0D8h+arg_20]; int
0x180020474  mov     rax, rcx
0x180020477  test    r15d, r15d
0x18002047a  mov     edx, r14d; int
0x18002047d  setz    sil
0x180020481  xor     r15d, r15d
0x180020484  test    r12, r12
0x180020487  mov     r8d, esi; int
0x18002048a  setnz   r15b
0x18002048e  and     ecx, 40000000h
0x180020494  sar     rax, 3Fh
0x180020498  bts     rcx, 1Ch
0x18002049d  shr     rcx, 19h
0x1800204a1  and     eax, 18h
0x1800204a4  add     rax, rbx
0x1800204a7  mov     rbx, [rcx+rax]
0x1800204ab  mov     rcx, rdi; struct _LRPC_FAULT_MESSAGE *
0x1800204ae  call    ?SetFaultPacket@@YAXPEAU_LRPC_FAULT_MESSAGE@@JHH@Z; SetFaultPacket(_LRPC_FAULT_MESSAGE *,long,int,int)
0x1800204b3  xor     r12d, r12d
0x1800204b6  xor     r9d, r9d; void *
0x1800204b9  mov     [rsp+0D8h+var_A8], r12; struct LRPC_SYSTEM_HANDLE_DATA *
0x1800204be  mov     r8d, r15d; int
0x1800204c1  mov     [rsp+0D8h+var_B0], r12; unsigned __int64
0x1800204c6  mov     rdx, rdi; struct _PORT_MESSAGE *
0x1800204c9  mov     rcx, r13; this
0x1800204cc  mov     [rsp+0D8h+var_B8], r12; void *
0x1800204d1  call    ?AlpcSend@LRPC_ADDRESS@@QEAAJPEAU_PORT_MESSAGE@@HPEAX1_KPEAVLRPC_SYSTEM_HANDLE_DATA@@@Z; LRPC_ADDRESS::AlpcSend(_PORT_MESSAGE *,int,void *,void *,unsigned __int64,LRPC_SYSTEM_HANDLE_DATA *)
0x1800204d6  mov     edx, eax
0x1800204d8  test    eax, eax
0x1800204da  js      loc_180020957
0x1800204e0  mov     rcx, rbx; this
0x1800204e3  call    ?MessageReceived@LRPC_SASSOCIATION@@QEAAXXZ; LRPC_SASSOCIATION::MessageReceived(void)
0x1800204e8  mov     rcx, [r13+128h]
0x1800204ef  test    rcx, rcx
0x1800204f2  jnz     loc_1800205BA
0x1800204f8  mov     rcx, rdi; void *
0x1800204fb  call    ?FreeEmergencyOrNormalMessage@@YAXPEAX@Z; FreeEmergencyOrNormalMessage(void *)
0x180020500  test    rbp, rbp
0x180020503  jz      loc_180020421
0x180020509  mov     rdx, rbp; void *
0x18002050c  call    ?Free@BCACHE@@QEAAXPEAX@Z; BCACHE::Free(void *)
0x180020511  jmp     loc_180020421
0x180020516  cmp     cs:?gfRPCVerifierEnabled@@3HA, ebx; int gfRPCVerifierEnabled
0x18002051c  mov     ecx, 290h; dwBytes
0x180020521  mov     [rsp+0D8h+var_98], ebx
0x180020525  jnz     loc_18002087D
0x18002052b  call    ?AllocWrapper@@YAPEAX_K@Z; AllocWrapper(unsigned __int64)
0x180020530  test    rax, rax
0x180020533  jz      loc_180020833
0x180020539  mov     r9d, dword ptr [rsp+0D8h+var_90]; unsigned int
0x18002053e  lea     rdx, [rsp+0D8h+var_98]; int *
0x180020543  mov     r8, r15; struct LRPC_SASSOCIATION *
0x180020546  mov     rcx, rax; this
0x180020549  call    ??0LRPC_SCALL@@QEAA@PEAJPEAVLRPC_SASSOCIATION@@K@Z; LRPC_SCALL::LRPC_SCALL(long *,LRPC_SASSOCIATION *,ulong)
0x18002054e  mov     rcx, rax; this
0x180020551  test    rax, rax
0x180020554  jz      loc_180020833
0x18002055a  mov     r14d, [rsp+0D8h+var_98]
0x18002055f  test    r14d, r14d
0x180020562  jnz     loc_1800208B5
0x180020568  mov     rbx, rcx
0x18002056b  call    ?CreateAndSetActivityId@CALL@@QEAAXXZ; CALL::CreateAndSetActivityId(void)
0x180020570  test    r14d, r14d
0x180020573  jnz     loc_180020873
0x180020579  mov     r14, [rsp+0D8h+var_80]
0x18002057e  jmp     loc_18002037C
0x180020583  test    al, 2
0x180020585  jnz     loc_1800208DB
0x18002058b  test    rsi, rsi
0x18002058e  jnz     loc_1800208EB
0x180020594  mov     eax, [rsp+0D8h+arg_20]
0x18002059b  mov     r9, r12; void *
0x18002059e  mov     dword ptr [rsp+0D8h+var_B0], eax; int
0x1800205a2  mov     rdx, rdi; struct _PORT_MESSAGE *
0x1800205a5  mov     [rsp+0D8h+var_B8], r8; unsigned __int64
0x1800205aa  mov     rcx, r15; this
0x1800205ad  mov     r8, rbp; struct _PORT_MESSAGE *
0x1800205b0  call    ?HandlePipeChunk@LRPC_SASSOCIATION@@AEAAXPEAU_LRPC_REQUEST_MESSAGE@@PEAU_PORT_MESSAGE@@PEAX_KH@Z; LRPC_SASSOCIATION::HandlePipeChunk(_LRPC_REQUEST_MESSAGE *,_PORT_MESSAGE *,void *,unsigned __int64,int)
0x1800205b5  jmp     loc_180020421
0x1800205ba  cmp     rdi, rcx
0x1800205bd  jbe     loc_1800204F8
0x1800205c3  mov     eax, [r13+130h]
0x1800205ca  add     rax, rcx
0x1800205cd  cmp     rdi, rax
0x1800205d0  jnb     loc_1800204F8
0x1800205d6  mov     rdx, rdi; void *
0x1800205d9  mov     rcx, r13; this
0x1800205dc  call    ?RpcFreeLrpcAddressBuffer@LRPC_ADDRESS@@QEAAXPEAX@Z; LRPC_ADDRESS::RpcFreeLrpcAddressBuffer(void *)
0x1800205e1  jmp     loc_180020500
0x1800205e6  mov     [rsp+0D8h+var_90], rdi
0x1800205eb  mov     r14d, 0Eh
0x1800205f1  lea     r13, [rdi+30h]
0x1800205f5  test    rsi, rsi
0x1800205f8  jz      short loc_180020602
0x1800205fa  mov     rcx, rsi; this
0x1800205fd  call    ?Cleanup@RPCP_ALPC_HANDLE_ATTR@@QEAAXXZ; RPCP_ALPC_HANDLE_ATTR::Cleanup(void)
0x180020602  test    byte ptr [r13+0], 2
0x180020607  mov     esi, 1
0x18002060c  jz      loc_18002084D
0x180020612  mov     eax, [rdi+50h]
0x180020615  lea     rdx, [rsp+0D8h+var_70]; struct _LRPC_BROKEN_FLOWS_MESSAGE *
0x18002061a  mov     [rsp+0D8h+var_68], eax
0x18002061e  mov     rcx, r15; this
0x180020621  mov     rax, [rdi+48h]
0x180020625  mov     [rsp+0D8h+var_60], rax
0x18002062a  mov     [rsp+0D8h+var_64], 100h
0x180020632  mov     [rsp+0D8h+var_70], 1
0x18002063b  call    ?ProcessCausalFlowGapBatch@LRPC_SASSOCIATION@@QEAAXPEAU_LRPC_BROKEN_FLOWS_MESSAGE@@@Z; LRPC_SASSOCIATION::ProcessCausalFlowGapBatch(_LRPC_BROKEN_FLOWS_MESSAGE *)
0x180020640  movzx   ecx, byte ptr [rsp+0D8h+var_64]
0x180020645  mov     [rsp+0D8h+var_98], ecx
0x180020649  test    r12, r12
  ... truncated ...
```
