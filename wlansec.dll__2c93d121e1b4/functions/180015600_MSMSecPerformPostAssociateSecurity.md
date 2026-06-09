# MSMSecPerformPostAssociateSecurity

- ea: `0x180015600`
- end: `0x180015ee6`
- name: `MSMSecPerformPostAssociateSecurity`
- size: `2278`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)`
- caller_count: `0`
- callee_count: `28`
- tags: `broker_com_uri`

## callees

- `0x180006d98`
- `0x18000892c`
- `0x180008998`
- `0x18000a26c`
- `0x18000b6dc`
- `0x1800125b0`
- `0x180013600`
- `0x180013bc0`
- `0x1800148d0`
- `0x180014998`
- `0x180015600`
- `0x1800166b4`
- `0x1800169c0`
- `0x180016a08`
- `0x180017338`
- `0x1800176e0`
- `0x180018488`
- `0x180018d40`
- `0x180018dd8`
- `0x18002913c`
- `0x18002ab18`
- `0x18002b078`
- `0x18002bb08`
- `0x180031c30`
- `0x180035038`
- `0x180050da8`
- `0x1800558c0`
- `0x180055a38`

## import_xrefs

- `MobileNetworking!ReleaseWriteLock` at `0x180015858`
- `MobileNetworking!ReleaseWriteLock` at `0x18001599e`
- `MobileNetworking!ReleaseWriteLock` at `0x180015b76`
- `MobileNetworking!ReleaseWriteLock` at `0x180015c32`
- `MobileNetworking!ReleaseWriteLock` at `0x180015858`
- `MobileNetworking!ReleaseWriteLock` at `0x18001599e`
- `MobileNetworking!ReleaseWriteLock` at `0x180015b76`
- `MobileNetworking!ReleaseWriteLock` at `0x180015c32`
- `MobileNetworking!AcquireWriteLock` at `0x1800159d0`
- `MobileNetworking!AcquireWriteLock` at `0x180015a43`
- `MobileNetworking!AcquireWriteLock` at `0x180015bf0`
- `MobileNetworking!AcquireWriteLock` at `0x1800159d0`
- `MobileNetworking!AcquireWriteLock` at `0x180015a43`
- `MobileNetworking!AcquireWriteLock` at `0x180015bf0`

## string_xrefs

- `0x180015657`: `MSMSecPerformPostAssociateSecurity`
- `0x18001584e`: `MSMSecPerformPostAssociateSecurity`
- `0x180015887`: `MSMSecPerformPostAssociateSecurity`
- `0x180015949`: `MSMSecPerformPostAssociateSecurity`
- `0x180015a36`: `MSMSecPerformPostAssociateSecurity`
- `0x180015b6c`: `MSMSecPerformPostAssociateSecurity`
- `0x180015b9b`: `MSMSecPerformPostAssociateSecurity`
- `0x180015be6`: `MSMSecPerformPostAssociateSecurity`
- `0x180015c25`: `MSMSecPerformPostAssociateSecurity`
- `0x180015e76`: `MSMSecPerformPostAssociateSecurity`

## pseudocode

```c
__int64 __fastcall MSMSecPerformPostAssociateSecurity(
        void *a1,
        void *a2,
        struct _DOT11_PORT_STATE *a3,
        unsigned int a4,
        struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *a5)
{
  struct MSMSEC_PORT_CONTEXT *v5; // r14
  unsigned int v10; // eax
  unsigned int v11; // edi
  struct MSMSEC_INTF_CONTEXT *v12; // rsi
  int v13; // ecx
  int v14; // ebp
  __int64 v15; // rdx
  __int64 v16; // r8
  PVOID *v17; // rbx
  unsigned int Port; // eax
  __int64 v19; // r8
  DOT11_AUTH_ALGORITHM *p_AuthAlgo; // rax
  unsigned int v21; // eax
  int v22; // r15d
  PVOID *v23; // rcx
  __int64 v24; // r9
  PVOID *v25; // rcx
  unsigned int v27; // eax
  struct MSMSEC_PORT_CONTEXT **v28; // rdx
  __int64 v29; // rdx
  _QWORD *v30; // rcx
  __int64 v31; // rax
  unsigned int v32; // r10d
  __int64 v33; // rdx
  int v34; // eax
  int v35; // r11d
  __int64 v36; // r8
  char v37; // r10
  __int64 v38; // rdx
  struct MSMSEC_PORT_CONTEXT *v39; // [rsp+58h] [rbp-60h] BYREF
  struct MSMSEC_INTF_CONTEXT *v40; // [rsp+60h] [rbp-58h] BYREF

  v5 = 0;
  v40 = 0;
  v39 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x100) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 80, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
  v10 = IncThreadCountAndCheckInitializedEx("MSMSecPerformPostAssociateSecurity", 683);
  v11 = v10;
  if ( v10 )
  {
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_34;
    v29 = 81;
    goto LABEL_61;
  }
  if ( !a1 || !a3 || !a4 || !a5 )
  {
    v11 = 87;
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_34;
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 82, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids);
    goto LABEL_33;
  }
  v10 = ValidateAssociationCompletionParams(a4, a5);
  v11 = v10;
  if ( !v10 )
  {
    v10 = SecMgrValidateRefAndLockAdapter(a1, &v40);
    v11 = v10;
    if ( !v10 )
    {
      v12 = v40;
      PreparePeerKeyOnAssociationCompletion(v40, a5);
      v13 = (int)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 0x20) != 0 )
        WPP_SF_Lqq(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          85,
          &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
          *((unsigned int *)v12 + 624),
          a1,
          a2);
      v14 = 1;
      if ( (byte_1800AED45 & 1) != 0 )
        McTemplateU0qjb6_EventWriteTransfer(
          v13,
          (unsigned int)"&R",
          *((_DWORD *)v12 + 624),
          (_DWORD)v12 + 32,
          (__int64)a3);
      if ( (unsigned int)IsValidIntfSecStateForAction(*((unsigned int *)v12 + 681), 4) )
      {
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) != 0 )
        {
          WPP_SF_LDDDDDD(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            87,
            &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            *((unsigned int *)v12 + 624),
            a3->PeerMacAddress[0],
            a3->PeerMacAddress[1],
            a3->PeerMacAddress[2],
            a3->PeerMacAddress[3],
            a3->PeerMacAddress[4],
            a3->PeerMacAddress[5]);
          v17 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( *((_DWORD *)v12 + 664) < 0x80u )
        {
          Port = SecMgrFindPort(v12, (unsigned __int8 (*)[6])a3, &v39);
          v11 = Port;
          if ( Port )
          {
            if ( Port == 1168 )
            {
              v19 = *((_QWORD *)v12 + 348);
              if ( *(_DWORD *)(v19 + 16) == 1 )
                p_AuthAlgo = *(DOT11_AUTH_ALGORITHM **)(v19 + 24);
              else
                p_AuthAlgo = &a5->AuthAlgo;
              v21 = SecMgrCreatePort(
                      v12,
                      *((void **)v12 + 331),
                      (struct DOT11_MSMSEC_CONNECTION_PROFILE *)v19,
                      (const unsigned __int8 (*)[6])((char *)v12 + 2360),
                      (const unsigned __int8 (*)[6])a3,
                      *p_AuthAlgo,
                      &v39);
              v11 = v21;
              if ( !v21 )
              {
                v5 = v39;
                TracePortId(*((_DWORD *)v39 + 78), ">>> Refing >>>");
                SecMgrRefPortEx(v5, "MSMSecPerformPostAssociateSecurity", 778);
                SecMgrIntfStateTransition(v12, 5, 327679);
                TraceAdapterId(*((_DWORD *)v12 + 624), "<<< Unlocking <<<");
                ReleaseWriteLock(v12, (char *)v12 + 2512, "MSMSecPerformPostAssociateSecurity", 786);
                TracePortId(*((_DWORD *)v5 + 78), ">>> Locking >>>");
                AcquireWriteLock(v5, (char *)v5 + 320, "MSMSecPerformPostAssociateSecurity", 791);
                *((_DWORD *)v5 + 109) = 0;
                v27 = SecMgrSetPortParams(v5, a2, a3, a4, a5);
                v11 = v27;
                if ( v27 )
                {
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                    goto LABEL_56;
                  v38 = 91;
                }
                else
                {
                  v27 = SecMgrPostAssociateSecurity(v5);
                  v11 = v27;
                  if ( !v27 )
                  {
                    TraceAdapterId(*((_DWORD *)v12 + 624), ">>> Locking >>>");
                    AcquireWriteLock(v12, (char *)v12 + 2512, "MSMSecPerformPostAssociateSecurity", 803);
                    SecMgrIntfStateTransition(v12, 3, 327679);
                    v28 = (struct MSMSEC_PORT_CONTEXT **)*((_QWORD *)v12 + 335);
                    if ( *v28 != (struct MSMSEC_INTF_CONTEXT *)((char *)v12 + 2672) )
                      __fastfail(v11 + 3);
                    *(_QWORD *)v5 = (char *)v12 + 2672;
                    *((_QWORD *)v5 + 1) = v28;
                    v22 = 1;
                    *v28 = v5;
                    *((_QWORD *)v12 + 335) = v5;
                    v17 = (PVOID *)WPP_GLOBAL_Control;
                    goto LABEL_28;
                  }
                  v30 = WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
                    goto LABEL_56;
                  v38 = 92;
                }
                WPP_SF_d(v30[7], v38, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v27);
                goto LABEL_56;
              }
              v17 = (PVOID *)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
              {
                v5 = v39;
LABEL_24:
                v22 = 0;
                goto LABEL_31;
              }
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
              {
                v5 = v39;
                goto LABEL_80;
              }
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 90, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v21);
              v5 = v39;
LABEL_78:
              v17 = (PVOID *)WPP_GLOBAL_Control;
LABEL_80:
              v22 = 0;
              goto LABEL_28;
            }
            v5 = v39;
          }
          else
          {
            v11 = 183;
          }
          v17 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
            goto LABEL_24;
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
            goto LABEL_80;
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 89, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v11);
          goto LABEL_78;
        }
        v11 = 1292;
        if ( v17 != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)v17 + 68) & 1) == 0 )
            goto LABEL_69;
          WPP_SF_d(v17[7], 88, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, 128);
          goto LABEL_68;
        }
      }
      else
      {
        v11 = 5023;
        v17 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
          {
LABEL_69:
            v22 = 0;
LABEL_28:
            if ( v17 != &WPP_GLOBAL_Control && (*((_DWORD *)v17 + 17) & 0x100) != 0 )
              WPP_SF_Ls((unsigned int)v17[7], 11, v16, *((_DWORD *)v12 + 624), (__int64)"<<< Unlocking <<<");
LABEL_31:
            ReleaseWriteLock(v12, (char *)v12 + 2512, "MSMSecPerformPostAssociateSecurity", 820);
            v14 = 0;
            if ( !v22 )
            {
LABEL_32:
              TraceAdapterId(*((_DWORD *)v12 + 624), "<<< Derefing <<<");
              SecMgrDerefAdapterEx(v12, "MSMSecPerformPostAssociateSecurity", 855);
LABEL_33:
              v23 = (PVOID *)WPP_GLOBAL_Control;
              goto LABEL_34;
            }
LABEL_56:
            TracePortId(*((_DWORD *)v5 + 78), "<<< Unlocking <<<");
            ReleaseWriteLock(v5, (char *)v5 + 320, "MSMSecPerformPostAssociateSecurity", 824);
            TracePortId(*((_DWORD *)v5 + 78), "<<< Derefing <<<");
            SecMgrDerefPortEx(v5, "MSMSecPerformPostAssociateSecurity", 828);
            if ( v14 )
            {
              SecMgrPreDestroyInfraPort(v5);
              SecMgrDestroyPort(v5, 0);
              TraceAdapterId(*((_DWORD *)v12 + 624), ">>> Locking >>>");
              AcquireWriteLock(v12, (char *)v12 + 2512, "MSMSecPerformPostAssociateSecurity", 844);
              SecMgrIntfStateTransition(v12, 3, 327679);
              TraceAdapterId(*((_DWORD *)v12 + 624), "<<< Unlocking <<<");
              ReleaseWriteLock(v12, (char *)v12 + 2512, "MSMSecPerformPostAssociateSecurity", 851);
            }
            goto LABEL_32;
          }
          v31 = IntfActionStr(4, v15, v16, "<<< Unlocking <<<");
          v34 = IntfSecStateStr(v32, v33, v31);
          WPP_SF_SLSL(
            (unsigned int)v17[7],
            v35 + 82,
            (unsigned int)&WPP_5807585f210c3b3262a513c5e260de7e_Traceguids,
            v34,
            v37,
            v36,
            v35);
LABEL_68:
          v17 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_69;
        }
      }
      v22 = 0;
      goto LABEL_31;
    }
    v23 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
      goto LABEL_37;
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) == 0 )
      goto LABEL_34;
    v29 = 84;
LABEL_61:
    WPP_SF_d(v23[7], v29, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v10);
    goto LABEL_33;
  }
  v23 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    goto LABEL_37;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0 )
  {
    v29 = 83;
    goto LABEL_61;
  }
LABEL_34:
  if ( v23 != &WPP_GLOBAL_Control && (*((_DWORD *)v23 + 17) & 0x400) != 0 )
    WPP_SF_sd(
      (unsigned int)v23[7],
      24,
      (unsigned int)&WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids,
      (unsigned int)"MSMSecPerformPostAssociateSecurity",
      89);
LABEL_37:
  v24 = (unsigned int)_InterlockedDecrement(&dword_1800AEF94);
  v25 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_DWORD *)WPP_GLOBAL_Control + 17) & 0x400) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, &WPP_0c0bf6275506325847d38564a7df1e9a_Traceguids, v24);
      v25 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v25 != &WPP_GLOBAL_Control && (*((_DWORD *)v25 + 17) & 0x100) != 0 )
      WPP_SF_d(v25[7], 93, &WPP_5807585f210c3b3262a513c5e260de7e_Traceguids, v11);
  }
  return v11;
}

```

## disassembly

```asm
0x180015600  mov     [rsp+arg_8], rdx
0x180015605  push    rbx
0x180015606  push    rbp
0x180015607  push    rsi
0x180015608  push    rdi
0x180015609  push    r12
0x18001560b  push    r13
0x18001560d  push    r14
0x18001560f  push    r15
0x180015611  sub     rsp, 78h
0x180015615  xor     r14d, r14d
0x180015618  mov     [rsp+0B8h+var_58], 0
0x180015621  mov     [rsp+0B8h+var_60], r14
0x180015626  mov     r12d, r9d
0x180015629  mov     r15, r8
0x18001562c  mov     rbp, rdx
0x18001562f  mov     rbx, rcx
0x180015632  mov     rcx, cs:WPP_GLOBAL_Control
0x180015639  lea     rsi, WPP_GLOBAL_Control
0x180015640  cmp     rcx, rsi
0x180015643  jz      short loc_180015652
0x180015645  test    dword ptr [rcx+44h], 100h
0x18001564c  jnz     loc_180015C86
0x180015652  mov     edx, 2ABh; int
0x180015657  lea     rcx, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x18001565e  call    ?IncThreadCountAndCheckInitializedEx@@YAKPEBDH@Z; IncThreadCountAndCheckInitializedEx(char const *,int)
0x180015663  mov     edi, eax
0x180015665  test    eax, eax
0x180015667  jnz     loc_180015AA0
0x18001566d  test    rbx, rbx
0x180015670  jz      loc_1800157F8
0x180015676  test    r15, r15
0x180015679  jz      loc_1800157F8
0x18001567f  test    r12d, r12d
0x180015682  jz      loc_1800157F8
0x180015688  mov     r13, [rsp+0B8h+arg_20]
0x180015690  test    r13, r13
0x180015693  jz      loc_1800157F8
0x180015699  mov     rdx, r13; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x18001569c  mov     ecx, r12d; unsigned int
0x18001569f  call    ?ValidateAssociationCompletionParams@@YAKKPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z; ValidateAssociationCompletionParams(ulong,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)
0x1800156a4  mov     edi, eax
0x1800156a6  test    eax, eax
0x1800156a8  jnz     loc_180015CA0
0x1800156ae  lea     rdx, [rsp+0B8h+var_58]; struct MSMSEC_INTF_CONTEXT **
0x1800156b3  mov     rcx, rbx; void *
0x1800156b6  call    ?SecMgrValidateRefAndLockAdapter@@YAKPEAXPEAPEAUMSMSEC_INTF_CONTEXT@@@Z; SecMgrValidateRefAndLockAdapter(void *,MSMSEC_INTF_CONTEXT * *)
0x1800156bb  mov     edi, eax
0x1800156bd  test    eax, eax
0x1800156bf  jnz     loc_180015C43
0x1800156c5  mov     rsi, [rsp+0B8h+var_58]
0x1800156ca  mov     rdx, r13; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x1800156cd  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x1800156d0  mov     [rsp+0B8h+var_68], r14d
0x1800156d5  call    ?PreparePeerKeyOnAssociationCompletion@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z; PreparePeerKeyOnAssociationCompletion(MSMSEC_INTF_CONTEXT *,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)
0x1800156da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800156e1  lea     rdi, WPP_GLOBAL_Control
0x1800156e8  cmp     rcx, rdi
0x1800156eb  jnz     loc_1800158FC
0x1800156f1  mov     ebp, 1
0x1800156f6  test    cs:byte_1800AED45, bpl
0x1800156fd  jnz     loc_1800157D7
0x180015703  mov     ecx, [rsi+0AA4h]
0x180015709  mov     edx, 4
0x18001570e  call    ?IsValidIntfSecStateForAction@@YAHW4MSMSEC_INTF_SEC_STATE@@W4SECMGR_INTF_ACTION@@@Z; IsValidIntfSecStateForAction(MSMSEC_INTF_SEC_STATE,SECMGR_INTF_ACTION)
0x180015713  lea     r9, aUnlocking; "<<< Unlocking <<<"
0x18001571a  test    eax, eax
0x18001571c  jz      loc_180015A7C
0x180015722  mov     rbx, cs:WPP_GLOBAL_Control
0x180015729  cmp     rbx, rdi
0x18001572c  jnz     loc_180015AC7
0x180015732  mov     r9d, 80h
0x180015738  cmp     [rsi+0A60h], r9d
0x18001573f  jnb     loc_180015D3D
0x180015745  lea     r8, [rsp+0B8h+var_60]; struct MSMSEC_PORT_CONTEXT **
0x18001574a  mov     rdx, r15; unsigned __int8 (*)[6]
0x18001574d  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180015750  call    ?SecMgrFindPort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAY05EPEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrFindPort(MSMSEC_INTF_CONTEXT *,uchar (*)[6],MSMSEC_PORT_CONTEXT * *)
0x180015755  mov     edi, eax
0x180015757  test    eax, eax
0x180015759  jz      loc_180015D5A
0x18001575f  cmp     eax, 490h
0x180015764  jnz     loc_180015D61
0x18001576a  mov     r8, [rsi+0AE0h]; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x180015771  cmp     [r8+10h], ebp
0x180015775  jnz     loc_180015C7D
0x18001577b  mov     rax, [r8+18h]
0x18001577f  mov     eax, [rax]
0x180015781  lea     rcx, [rsp+0B8h+var_60]
0x180015786  mov     rdx, [rsi+0A58h]; void *
0x18001578d  lea     r9, [rsi+938h]; unsigned __int8 (*)[6]
0x180015794  mov     [rsp+0B8h+var_88], rcx; struct MSMSEC_PORT_CONTEXT **
0x180015799  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x18001579c  mov     [rsp+0B8h+var_90], eax; enum _DOT11_AUTH_ALGORITHM
0x1800157a0  mov     [rsp+0B8h+var_98], r15; unsigned __int8 (*)[6]
0x1800157a5  call    ?SecMgrCreatePort@@YAKPEAUMSMSEC_INTF_CONTEXT@@PEAXPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@AEAY05$$CBE3W4_DOT11_AUTH_ALGORITHM@@PEAPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrCreatePort(MSMSEC_INTF_CONTEXT *,void *,DOT11_MSMSEC_CONNECTION_PROFILE *,uchar const (&)[6],uchar const (&)[6],_DOT11_AUTH_ALGORITHM,MSMSEC_PORT_CONTEXT * *)
0x1800157aa  mov     edi, eax
0x1800157ac  test    eax, eax
0x1800157ae  jz      loc_180015931
0x1800157b4  mov     rbx, cs:WPP_GLOBAL_Control
0x1800157bb  lea     r12, WPP_GLOBAL_Control
0x1800157c2  cmp     rbx, r12
0x1800157c5  jnz     loc_180015DFA
0x1800157cb  mov     r14, [rsp+0B8h+var_60]
0x1800157d0  mov     r15d, [rsp+0B8h+var_68]
0x1800157d5  jmp     short loc_180015841
0x1800157d7  mov     r8d, [rsi+9C0h]
0x1800157de  lea     r9, [rsi+20h]
0x1800157e2  lea     rdx, MsmSecPortUp; "&R"
0x1800157e9  mov     [rsp+0B8h+var_98], r15
0x1800157ee  call    McTemplateU0qjb6_EventWriteTransfer
0x1800157f3  jmp     loc_180015703
0x1800157f8  mov     edi, 57h ; 'W'
0x1800157fd  mov     rcx, cs:WPP_GLOBAL_Control
0x180015804  cmp     rcx, rsi
0x180015807  jz      loc_1800158B6
0x18001580d  lea     ebp, [rdi-56h]
0x180015810  test    [rcx+44h], bpl
0x180015814  jz      loc_1800158A4
0x18001581a  mov     rcx, [rcx+38h]
0x18001581e  lea     edx, [rdi-5]
0x180015821  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180015828  call    WPP_SF_
0x18001582d  jmp     short loc_18001589D
0x18001582f  cmp     rbx, r12
0x180015832  jz      short loc_180015841
0x180015834  test    dword ptr [rbx+44h], 100h
0x18001583b  jnz     loc_180015E53
0x180015841  lea     rdx, [rsi+9D0h]
0x180015848  mov     r9d, 334h
0x18001584e  lea     r8, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x180015855  mov     rcx, rsi
0x180015858  call    cs:__imp_ReleaseWriteLock
0x18001585f  nop     dword ptr [rax+rax+00h]
0x180015864  xor     ebp, ebp
0x180015866  test    r15d, r15d
0x180015869  jnz     loc_180015B49
0x18001586f  mov     ecx, [rsi+9C0h]; unsigned int
0x180015875  lea     rdx, aDerefing; "<<< Derefing <<<"
0x18001587c  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180015881  mov     r8d, 357h; int
0x180015887  lea     rdx, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x18001588e  mov     rcx, rsi; struct MSMSEC_INTF_CONTEXT *
0x180015891  call    ?SecMgrDerefAdapterEx@@YAXPEAUMSMSEC_INTF_CONTEXT@@PEBDH@Z; SecMgrDerefAdapterEx(MSMSEC_INTF_CONTEXT *,char const *,int)
0x180015896  lea     rsi, WPP_GLOBAL_Control
0x18001589d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158a4  cmp     rcx, rsi
0x1800158a7  jz      short loc_1800158B6
0x1800158a9  test    dword ptr [rcx+44h], 400h
0x1800158b0  jnz     loc_180015E72
0x1800158b6  or      r9d, 0FFFFFFFFh
0x1800158ba  lock xadd cs:dword_1800AEF94, r9d
0x1800158c3  dec     r9d
0x1800158c6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800158cd  cmp     rcx, rsi
0x1800158d0  jz      short loc_1800158E8
0x1800158d2  test    dword ptr [rcx+44h], 400h
0x1800158d9  jnz     loc_180015E9B
0x1800158df  cmp     rcx, rsi
0x1800158e2  jnz     loc_180015EBC
0x1800158e8  mov     eax, edi
0x1800158ea  add     rsp, 78h
0x1800158ee  pop     r15
0x1800158f0  pop     r14
0x1800158f2  pop     r13
0x1800158f4  pop     r12
0x1800158f6  pop     rdi
0x1800158f7  pop     rsi
0x1800158f8  pop     rbp
0x1800158f9  pop     rbx
0x1800158fa  retn
0x1800158fc  test    byte ptr [rcx+44h], 20h
0x180015900  jz      loc_1800156F1
0x180015906  mov     r9d, [rsi+9C0h]
0x18001590d  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180015914  mov     rcx, [rcx+38h]
0x180015918  mov     edx, 55h ; 'U'
0x18001591d  mov     qword ptr [rsp+0B8h+var_90], rbp
0x180015922  mov     [rsp+0B8h+var_98], rbx
0x180015927  call    WPP_SF_Lqq
0x18001592c  jmp     loc_1800156F1
0x180015931  mov     r14, [rsp+0B8h+var_60]
0x180015936  lea     rdx, aRefing; ">>> Refing >>>"
0x18001593d  mov     ecx, [r14+138h]; unsigned int
0x180015944  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180015949  lea     rdi, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x180015950  mov     r8d, 30Ah; int
0x180015956  mov     rdx, rdi; char *
0x180015959  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x18001595c  call    ?SecMgrRefPortEx@@YAXPEAUMSMSEC_PORT_CONTEXT@@PEBDH@Z; SecMgrRefPortEx(MSMSEC_PORT_CONTEXT *,char const *,int)
0x180015961  xor     r9d, r9d
0x180015964  mov     r8d, 4FFFFh
0x18001596a  mov     rcx, rsi
0x18001596d  lea     edx, [r9+5]
0x180015971  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x180015976  mov     ecx, [rsi+9C0h]; unsigned int
0x18001597c  lea     rdx, aUnlocking; "<<< Unlocking <<<"
0x180015983  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180015988  lea     rbx, [rsi+9D0h]
0x18001598f  mov     r9d, 312h
0x180015995  mov     rdx, rbx
0x180015998  mov     r8, rdi
0x18001599b  mov     rcx, rsi
0x18001599e  call    cs:__imp_ReleaseWriteLock
0x1800159a5  nop     dword ptr [rax+rax+00h]
0x1800159aa  mov     ecx, [r14+138h]; unsigned int
0x1800159b1  lea     rdx, aLocking; ">>> Locking >>>"
0x1800159b8  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x1800159bd  lea     rdx, [r14+140h]
0x1800159c4  mov     r9d, 317h
0x1800159ca  mov     r8, rdi
0x1800159cd  mov     rcx, r14
0x1800159d0  call    cs:__imp_AcquireWriteLock
0x1800159d7  nop     dword ptr [rax+rax+00h]
0x1800159dc  mov     rdx, [rsp+0B8h+arg_8]; void *
0x1800159e4  mov     r9d, r12d; unsigned int
0x1800159e7  mov     r8, r15; struct _DOT11_PORT_STATE *
0x1800159ea  mov     dword ptr [r14+1B4h], 0
0x1800159f5  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x1800159f8  mov     [rsp+0B8h+var_98], r13; struct DOT11_ASSOCIATION_COMPLETION_PARAMETERS *
0x1800159fd  call    ?SecMgrSetPortParams@@YAKPEAUMSMSEC_PORT_CONTEXT@@PEAXPEAU_DOT11_PORT_STATE@@KPEAUDOT11_ASSOCIATION_COMPLETION_PARAMETERS@@@Z; SecMgrSetPortParams(MSMSEC_PORT_CONTEXT *,void *,_DOT11_PORT_STATE *,ulong,DOT11_ASSOCIATION_COMPLETION_PARAMETERS *)
0x180015a02  mov     edi, eax
0x180015a04  test    eax, eax
0x180015a06  jnz     loc_180015B32
0x180015a0c  mov     rcx, r14; struct MSMSEC_PORT_CONTEXT *
0x180015a0f  call    ?SecMgrPostAssociateSecurity@@YAKPEAUMSMSEC_PORT_CONTEXT@@@Z; SecMgrPostAssociateSecurity(MSMSEC_PORT_CONTEXT *)
0x180015a14  mov     edi, eax
0x180015a16  test    eax, eax
0x180015a18  jnz     loc_180015E30
0x180015a1e  mov     ecx, [rsi+9C0h]; unsigned int
0x180015a24  lea     rdx, aLocking; ">>> Locking >>>"
0x180015a2b  call    ?TraceAdapterId@@YAXKPEBD@Z; TraceAdapterId(ulong,char const *)
0x180015a30  mov     r9d, 323h
0x180015a36  lea     r8, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x180015a3d  mov     rdx, rbx
0x180015a40  mov     rcx, rsi
0x180015a43  call    cs:__imp_AcquireWriteLock
0x180015a4a  nop     dword ptr [rax+rax+00h]
0x180015a4f  xor     r9d, r9d
0x180015a52  lea     edx, [rdi+3]
0x180015a55  mov     r8d, 4FFFFh
0x180015a5b  mov     rcx, rsi
0x180015a5e  call    ?SecMgrIntfStateTransition@@YAXPEAUMSMSEC_INTF_CONTEXT@@W4MSMSEC_INTF_SEC_STATE@@KK@Z; SecMgrIntfStateTransition(MSMSEC_INTF_CONTEXT *,MSMSEC_INTF_SEC_STATE,ulong,ulong)
0x180015a63  lea     rax, [rsi+0A70h]
0x180015a6a  mov     rdx, [rax+8]
0x180015a6e  cmp     [rdx], rax
0x180015a71  jz      loc_180015DCF
0x180015a77  lea     ecx, [rdi+3]
0x180015a7a  int     29h; Win8: RtlFailFast(ecx)
0x180015a7c  mov     edi, 139Fh
0x180015a81  mov     rbx, cs:WPP_GLOBAL_Control
0x180015a88  lea     r12, WPP_GLOBAL_Control
0x180015a8f  cmp     rbx, r12
0x180015a92  jnz     loc_180015CC4
0x180015a98  mov     r15d, r14d
0x180015a9b  jmp     loc_180015841
0x180015aa0  mov     rcx, cs:WPP_GLOBAL_Control
0x180015aa7  cmp     rcx, rsi
0x180015aaa  jz      loc_1800158B6
0x180015ab0  mov     ebp, 1
0x180015ab5  test    [rcx+44h], bpl
0x180015ab9  jz      loc_1800158A4
0x180015abf  lea     edx, [rbp+50h]
0x180015ac2  jmp     loc_180015C65
0x180015ac7  test    byte ptr [rbx+44h], 2
0x180015acb  jz      loc_180015732
0x180015ad1  movzx   ecx, byte ptr [r15+4]
0x180015ad6  mov     edx, 57h ; 'W'
0x180015adb  movzx   r8d, byte ptr [r15+3]
0x180015ae0  movzx   r9d, byte ptr [r15+2]
0x180015ae5  movzx   eax, byte ptr [r15+5]
0x180015aea  movzx   r10d, byte ptr [r15+1]
0x180015aef  movzx   r11d, byte ptr [r15]
0x180015af3  mov     [rsp+0B8h+var_70], eax
0x180015af7  mov     [rsp+0B8h+var_78], ecx
0x180015afb  mov     rcx, [rbx+38h]
0x180015aff  mov     [rsp+0B8h+var_80], r8d
0x180015b04  lea     r8, WPP_5807585f210c3b3262a513c5e260de7e_Traceguids
0x180015b0b  mov     dword ptr [rsp+0B8h+var_88], r9d
0x180015b10  mov     r9d, [rsi+9C0h]
0x180015b17  mov     [rsp+0B8h+var_90], r10d
0x180015b1c  mov     dword ptr [rsp+0B8h+var_98], r11d
0x180015b21  call    WPP_SF_LDDDDDD
0x180015b26  mov     rbx, cs:WPP_GLOBAL_Control
0x180015b2d  jmp     loc_180015732
0x180015b32  mov     rcx, cs:WPP_GLOBAL_Control
0x180015b39  lea     r12, WPP_GLOBAL_Control
0x180015b40  cmp     rcx, r12
0x180015b43  jnz     loc_180015E02
0x180015b49  mov     ecx, [r14+138h]; unsigned int
0x180015b50  lea     r15, aUnlocking; "<<< Unlocking <<<"
0x180015b57  mov     rdx, r15; char *
0x180015b5a  call    ?TracePortId@@YAXKPEBD@Z; TracePortId(ulong,char const *)
0x180015b5f  lea     rdx, [r14+140h]
0x180015b66  mov     r9d, 338h
0x180015b6c  lea     r8, aMsmsecperformp_3; "MSMSecPerformPostAssociateSecurity"
0x180015b73  mov     rcx, r14
0x180015b76  call    cs:__imp_ReleaseWriteLock
0x180015b7d  nop     dword ptr [rax+rax+00h]
0x180015b82  mov     ecx, [r14+138h]; unsigned int
  ... truncated ...
```
