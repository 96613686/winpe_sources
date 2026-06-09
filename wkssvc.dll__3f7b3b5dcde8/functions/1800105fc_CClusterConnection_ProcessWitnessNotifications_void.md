# CClusterConnection::ProcessWitnessNotifications(void)

- ea: `0x1800105fc`
- end: `0x180010a2e`
- name: `?ProcessWitnessNotifications@CClusterConnection@@QEAAKXZ`
- size: `1074`
- prototype: `__int64 __fastcall(CClusterConnection *this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x1800310e0`

## callees

- `0x18000e568`
- `0x18000fac0`
- `0x18000fc08`
- `0x18000ff00`
- `0x180010018`
- `0x1800105fc`
- `0x180011174`
- `0x180011260`
- `0x180022b54`
- `0x180032278`
- `0x180032490`
- `0x1800326a8`
- `0x180032760`
- `0x180034010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109bc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800108ea`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800109bc`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a18`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010a18`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001061e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001061e`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001068f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800106e9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18001068f`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800106e9`

## pseudocode

```c
__int64 __fastcall CClusterConnection::ProcessWitnessNotifications(CClusterConnection *this)
{
  __int64 v2; // r9
  __int64 v3; // r8
  unsigned int v4; // r14d
  PVOID *v5; // rcx
  int v6; // edx
  int v7; // r12d
  _QWORD *v8; // r9
  int v9; // eax
  _QWORD *v10; // rax
  _QWORD *v11; // rcx
  _QWORD *v12; // rax
  void *v13; // rcx
  unsigned int v14; // eax
  __int64 v15; // r8
  int v16; // r15d
  void *v17; // rcx
  int Reply; // [rsp+70h] [rbp+38h] BYREF

  Reply = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 54));
  v2 = *((unsigned int *)this + 80);
  if ( (_DWORD)v2 )
  {
    if ( (unsigned int)(v2 - 3) >= 2 )
    {
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 45, (char *)this + 280, v2, this);
      }
      goto LABEL_84;
    }
    v4 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 280), &Reply);
    v5 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 44, v3, *((unsigned int *)this + 80), this);
      v5 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    if ( !v4 )
    {
      v6 = Reply;
LABEL_21:
      v7 = 0;
      if ( !v6 && !*((_QWORD *)this + 49) )
      {
        if ( v5 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) )
        {
          WPP_SF_(v5[2], 46, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids);
          v5 = (PVOID *)WPP_witness_GLOBAL_Control;
        }
        v6 = 87;
        Reply = 87;
      }
      if ( *((_DWORD *)this + 52) )
      {
        if ( v5 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) )
        {
          WPP_SF_(v5[2], 47, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids);
          v5 = (PVOID *)WPP_witness_GLOBAL_Control;
        }
        v6 = 1067;
        Reply = 1067;
      }
      if ( v6 )
      {
        if ( v6 != 1460 && v6 != 1067 && v6 != 1818 )
        {
          v8 = (_QWORD *)*((_QWORD *)this + 33);
          if ( v8 )
          {
            v9 = *((_DWORD *)this + 113);
            if ( (v9 & 1) != 0 )
            {
              if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 1) == 0 )
                goto LABEL_55;
              v10 = (_QWORD *)((char *)this + 24);
              if ( *((_QWORD *)this + 6) > 7u )
                v10 = (_QWORD *)*v10;
              if ( v8[3] > 7u )
                v8 = (_QWORD *)*v8;
              McTemplateU0qzz_EventWriteTransfer(
                (_DWORD)v5,
                (unsigned int)WitnessClientServerFailure,
                v6,
                (_DWORD)v8,
                (__int64)v10);
            }
            else
            {
              if ( ((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits & ((v9 & 2) != 0)) == 0 )
                goto LABEL_55;
              v11 = (_QWORD *)((char *)this + 56);
              if ( *((_QWORD *)this + 10) > 7u )
                v11 = (_QWORD *)*v11;
              v12 = (_QWORD *)((char *)this + 24);
              if ( *((_QWORD *)this + 6) > 7u )
                v12 = (_QWORD *)*v12;
              if ( v8[3] > 7u )
                v8 = (_QWORD *)*v8;
              McTemplateU0qzzz_EventWriteTransfer(
                (_DWORD)v11,
                (unsigned int)WitnessClientServerFailure_ShareLevel,
                v6,
                (_DWORD)v8,
                (__int64)v12,
                (__int64)v11);
            }
            v5 = (PVOID *)WPP_witness_GLOBAL_Control;
            v6 = Reply;
          }
        }
      }
LABEL_55:
      if ( gWitnessNotifyCallBack )
      {
        if ( gWitnessNotifyCallBack(*((void **)this + 49), *((enum _RPC_ASYNC_EVENT *)this + 80), v6) != 1246 )
        {
          v13 = (void *)*((_QWORD *)this + 49);
          if ( v13 )
          {
            LocalFree(v13);
            *((_QWORD *)this + 49) = 0;
          }
        }
        v5 = (PVOID *)WPP_witness_GLOBAL_Control;
        v6 = Reply;
      }
      if ( v6 )
      {
        if ( v6 == 1460 )
        {
          if ( v5 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 3u )
            WPP_SF_qD(v5[2], 49, v3, this, v4);
          goto LABEL_72;
        }
      }
      else if ( *((_QWORD *)this + 49) )
      {
        v14 = CClusterConnection::ProcessNotificationMessage(this);
        if ( v14
          && WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
          && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
        {
          WPP_SF_dq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 48, v15, v14, this);
        }
LABEL_72:
        v16 = 1;
LABEL_78:
        v17 = (void *)*((_QWORD *)this + 49);
        if ( v17 )
        {
          LocalFree(v17);
          *((_QWORD *)this + 49) = 0;
        }
        if ( v16 )
        {
          *((_DWORD *)this + 4) = 7;
          CClusterConnection::IssueNotify(this);
        }
        else if ( v7 )
        {
          CClusterConnection::WitnessUnRegisterHelper(this);
          CClusterConnection::ResetWitnessNode(this);
          CClusterConnection::DeleteWitnessNodes(this);
          *((_DWORD *)this + 4) = 128;
          CClusterConnection::PendAndRetry(this, 0);
        }
        goto LABEL_84;
      }
      v16 = 0;
      if ( v5 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v5 + 28) & 1) != 0 && *((_BYTE *)v5 + 25) >= 3u )
        WPP_SF_dq(v5[2], 50, v3, v4, this);
      v7 = 1;
      goto LABEL_78;
    }
LABEL_20:
    v6 = v4;
    Reply = v4;
    goto LABEL_21;
  }
  v4 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 280), &Reply);
  v5 = (PVOID *)WPP_witness_GLOBAL_Control;
  if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
    && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
  {
    WPP_SF_ddq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 43, v3, v4, Reply, this);
    v5 = (PVOID *)WPP_witness_GLOBAL_Control;
  }
  if ( v4 != 997 )
  {
    v6 = Reply;
    if ( Reply != 997 )
    {
      if ( !v4 )
        goto LABEL_21;
      goto LABEL_20;
    }
  }
LABEL_84:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 54));
  return 0;
}

```

## disassembly

```asm
0x1800105fc  push    rbp
0x1800105fe  push    rbx
0x1800105ff  push    rsi
0x180010600  push    r12
0x180010602  push    r14
0x180010604  push    r15
0x180010606  mov     rbp, rsp
0x180010609  sub     rsp, 38h
0x18001060d  mov     rbx, rcx
0x180010610  mov     [rbp+Reply], 0
0x180010617  mov     rcx, [rcx+1B0h]; lpCriticalSection
0x18001061e  call    cs:__imp_EnterCriticalSection
0x180010624  lea     r8, [rbx+118h]
0x18001062b  mov     r9d, [r8+28h]
0x18001062f  mov     ecx, r9d
0x180010632  test    r9d, r9d
0x180010635  jz      loc_1800106E2
0x18001063b  sub     ecx, 3
0x18001063e  jz      short loc_180010688
0x180010640  cmp     ecx, 1
0x180010643  jz      short loc_180010688
0x180010645  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001064c  lea     rsi, WPP_witness_GLOBAL_Control
0x180010653  cmp     rcx, rsi
0x180010656  jz      loc_180010A11
0x18001065c  test    byte ptr [rcx+1Ch], 1
0x180010660  jz      loc_180010A11
0x180010666  cmp     byte ptr [rcx+19h], 3
0x18001066a  jb      loc_180010A11
0x180010670  mov     rcx, [rcx+10h]
0x180010674  mov     edx, 2Dh ; '-'
0x180010679  mov     [rsp+38h+var_18], rbx
0x18001067e  call    WPP_SF_dq
0x180010683  jmp     loc_180010A11
0x180010688  lea     rdx, [rbp+Reply]; Reply
0x18001068c  mov     rcx, r8; pAsync
0x18001068f  call    cs:__imp_RpcAsyncCompleteCall
0x180010695  mov     r14d, eax
0x180010698  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001069f  lea     rsi, WPP_witness_GLOBAL_Control
0x1800106a6  cmp     rcx, rsi
0x1800106a9  jz      short loc_1800106D8
0x1800106ab  test    byte ptr [rcx+1Ch], 1
0x1800106af  jz      short loc_1800106D8
0x1800106b1  cmp     byte ptr [rcx+19h], 3
0x1800106b5  jb      short loc_1800106D8
0x1800106b7  mov     r9d, [rbx+140h]
0x1800106be  mov     edx, 2Ch ; ','
0x1800106c3  mov     rcx, [rcx+10h]
0x1800106c7  mov     [rsp+38h+var_18], rbx
0x1800106cc  call    WPP_SF_dq
0x1800106d1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800106d8  test    r14d, r14d
0x1800106db  jnz     short loc_180010753
0x1800106dd  mov     edx, [rbp+Reply]
0x1800106e0  jmp     short loc_180010759
0x1800106e2  lea     rdx, [rbp+Reply]; Reply
0x1800106e6  mov     rcx, r8; pAsync
0x1800106e9  call    cs:__imp_RpcAsyncCompleteCall
0x1800106ef  mov     r14d, eax
0x1800106f2  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800106f9  lea     rsi, WPP_witness_GLOBAL_Control
0x180010700  cmp     rcx, rsi
0x180010703  jz      short loc_180010735
0x180010705  test    byte ptr [rcx+1Ch], 1
0x180010709  jz      short loc_180010735
0x18001070b  cmp     byte ptr [rcx+19h], 3
0x18001070f  jb      short loc_180010735
0x180010711  mov     eax, [rbp+Reply]
0x180010714  mov     edx, 2Bh ; '+'
0x180010719  mov     rcx, [rcx+10h]
0x18001071d  mov     r9d, r14d
0x180010720  mov     [rsp+38h+var_10], rbx
0x180010725  mov     dword ptr [rsp+38h+var_18], eax
0x180010729  call    WPP_SF_ddq
0x18001072e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010735  mov     eax, 3E5h
0x18001073a  cmp     r14d, eax
0x18001073d  jz      loc_180010A11
0x180010743  mov     edx, [rbp+Reply]
0x180010746  cmp     edx, eax
0x180010748  jz      loc_180010A11
0x18001074e  test    r14d, r14d
0x180010751  jz      short loc_180010759
0x180010753  mov     edx, r14d
0x180010756  mov     [rbp+Reply], edx
0x180010759  xor     r12d, r12d
0x18001075c  test    edx, edx
0x18001075e  jnz     short loc_18001079E
0x180010760  cmp     [rbx+188h], r12
0x180010767  jnz     short loc_18001079E
0x180010769  cmp     rcx, rsi
0x18001076c  jz      short loc_180010796
0x18001076e  test    byte ptr [rcx+1Ch], 1
0x180010772  jz      short loc_180010796
0x180010774  cmp     byte ptr [rcx+19h], 1
0x180010778  jb      short loc_180010796
0x18001077a  mov     rcx, [rcx+10h]
0x18001077e  lea     edx, [r12+2Eh]
0x180010783  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18001078a  call    WPP_SF_
0x18001078f  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010796  mov     edx, 57h ; 'W'
0x18001079b  mov     [rbp+Reply], edx
0x18001079e  mov     r15d, 42Bh
0x1800107a4  cmp     [rbx+0D0h], r12d
0x1800107ab  jz      short loc_1800107E0
0x1800107ad  cmp     rcx, rsi
0x1800107b0  jz      short loc_1800107DA
0x1800107b2  test    byte ptr [rcx+1Ch], 1
0x1800107b6  jz      short loc_1800107DA
0x1800107b8  cmp     byte ptr [rcx+19h], 1
0x1800107bc  jb      short loc_1800107DA
0x1800107be  mov     rcx, [rcx+10h]
0x1800107c2  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x1800107c9  mov     edx, 2Fh ; '/'
0x1800107ce  call    WPP_SF_
0x1800107d3  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800107da  mov     edx, r15d
0x1800107dd  mov     [rbp+Reply], edx
0x1800107e0  test    edx, edx
0x1800107e2  jz      loc_1800108B6
0x1800107e8  cmp     edx, 5B4h
0x1800107ee  jz      loc_1800108B6
0x1800107f4  cmp     edx, r15d
0x1800107f7  jz      loc_1800108B6
0x1800107fd  cmp     edx, 71Ah
0x180010803  jz      loc_1800108B6
0x180010809  mov     r9, [rbx+108h]
0x180010810  test    r9, r9
0x180010813  jz      loc_1800108B6
0x180010819  mov     eax, [rbx+1C4h]
0x18001081f  test    al, 1
0x180010821  jz      short loc_18001085E
0x180010823  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 1
0x18001082a  jz      loc_1800108B6
0x180010830  lea     rax, [rbx+18h]
0x180010834  cmp     qword ptr [rax+18h], 7
0x180010839  jbe     short loc_18001083E
0x18001083b  mov     rax, [rax]
0x18001083e  cmp     qword ptr [r9+18h], 7
0x180010843  jbe     short loc_180010848
0x180010845  mov     r9, [r9]
0x180010848  mov     r8d, edx
0x18001084b  mov     [rsp+38h+var_18], rax
0x180010850  lea     rdx, WitnessClientServerFailure
0x180010857  call    McTemplateU0qzz_EventWriteTransfer
0x18001085c  jmp     short loc_1800108AC
0x18001085e  test    al, 2
0x180010860  setnz   al
0x180010863  and     al, cs:Microsoft_Windows_SMBWitnessClientEnableBits
0x180010869  test    al, 1
0x18001086b  jz      short loc_1800108B6
0x18001086d  lea     rcx, [rbx+38h]
0x180010871  cmp     qword ptr [rcx+18h], 7
0x180010876  jbe     short loc_18001087B
0x180010878  mov     rcx, [rcx]
0x18001087b  lea     rax, [rbx+18h]
0x18001087f  cmp     qword ptr [rax+18h], 7
0x180010884  jbe     short loc_180010889
0x180010886  mov     rax, [rax]
0x180010889  cmp     qword ptr [r9+18h], 7
0x18001088e  jbe     short loc_180010893
0x180010890  mov     r9, [r9]
0x180010893  mov     r8d, edx
0x180010896  mov     [rsp+38h+var_10], rcx
0x18001089b  lea     rdx, WitnessClientServerFailure_ShareLevel
0x1800108a2  mov     [rsp+38h+var_18], rax
0x1800108a7  call    McTemplateU0qzzz_EventWriteTransfer
0x1800108ac  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800108b3  mov     edx, [rbp+Reply]
0x1800108b6  mov     rax, cs:?gWitnessNotifyCallBack@@3P6AKPEAXW4_RPC_ASYNC_EVENT@@J@ZEA; ulong (*gWitnessNotifyCallBack)(void *,_RPC_ASYNC_EVENT,long)
0x1800108bd  test    rax, rax
0x1800108c0  jz      short loc_180010901
0x1800108c2  mov     rcx, [rbx+188h]
0x1800108c9  mov     r8d, edx
0x1800108cc  mov     edx, [rbx+140h]
0x1800108d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800108d7  cmp     eax, 4DEh
0x1800108dc  jz      short loc_1800108F7
0x1800108de  mov     rcx, [rbx+188h]; hMem
0x1800108e5  test    rcx, rcx
0x1800108e8  jz      short loc_1800108F7
0x1800108ea  call    cs:__imp_LocalFree
0x1800108f0  mov     [rbx+188h], r12
0x1800108f7  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800108fe  mov     edx, [rbp+Reply]
0x180010901  test    edx, edx
0x180010903  jnz     short loc_18001094A
0x180010905  cmp     [rbx+188h], r12
0x18001090c  jz      short loc_180010981
0x18001090e  mov     rcx, rbx; this
0x180010911  call    ?ProcessNotificationMessage@CClusterConnection@@AEAAKXZ; CClusterConnection::ProcessNotificationMessage(void)
0x180010916  test    eax, eax
0x180010918  jz      short loc_180010979
0x18001091a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010921  cmp     rcx, rsi
0x180010924  jz      short loc_180010979
0x180010926  test    byte ptr [rcx+1Ch], 1
0x18001092a  jz      short loc_180010979
0x18001092c  cmp     byte ptr [rcx+19h], 3
0x180010930  jb      short loc_180010979
0x180010932  mov     rcx, [rcx+10h]
0x180010936  mov     edx, 30h ; '0'
0x18001093b  mov     r9d, eax
0x18001093e  mov     [rsp+38h+var_18], rbx
0x180010943  call    WPP_SF_dq
0x180010948  jmp     short loc_180010979
0x18001094a  cmp     edx, 5B4h
0x180010950  jnz     short loc_180010981
0x180010952  cmp     rcx, rsi
0x180010955  jz      short loc_180010979
0x180010957  test    byte ptr [rcx+1Ch], 1
0x18001095b  jz      short loc_180010979
0x18001095d  cmp     byte ptr [rcx+19h], 3
0x180010961  jb      short loc_180010979
0x180010963  mov     rcx, [rcx+10h]
0x180010967  mov     edx, 31h ; '1'
0x18001096c  mov     r9, rbx
0x18001096f  mov     dword ptr [rsp+38h+var_18], r14d
0x180010974  call    WPP_SF_qD
0x180010979  mov     r15d, 1
0x18001097f  jmp     short loc_1800109B0
0x180010981  xor     r15d, r15d
0x180010984  cmp     rcx, rsi
0x180010987  jz      short loc_1800109AA
0x180010989  test    byte ptr [rcx+1Ch], 1
0x18001098d  jz      short loc_1800109AA
0x18001098f  cmp     byte ptr [rcx+19h], 3
0x180010993  jb      short loc_1800109AA
0x180010995  mov     rcx, [rcx+10h]
0x180010999  lea     edx, [r15+32h]
0x18001099d  mov     r9d, r14d
0x1800109a0  mov     [rsp+38h+var_18], rbx
0x1800109a5  call    WPP_SF_dq
0x1800109aa  mov     r12d, 1
0x1800109b0  mov     rcx, [rbx+188h]; hMem
0x1800109b7  test    rcx, rcx
0x1800109ba  jz      short loc_1800109CD
0x1800109bc  call    cs:__imp_LocalFree
0x1800109c2  mov     qword ptr [rbx+188h], 0
0x1800109cd  test    r15d, r15d
0x1800109d0  jz      short loc_1800109E3
0x1800109d2  mov     rcx, rbx; this
0x1800109d5  mov     dword ptr [rbx+10h], 7
0x1800109dc  call    ?IssueNotify@CClusterConnection@@AEAAXXZ; CClusterConnection::IssueNotify(void)
0x1800109e1  jmp     short loc_180010A11
0x1800109e3  test    r12d, r12d
0x1800109e6  jz      short loc_180010A11
0x1800109e8  mov     rcx, rbx; this
0x1800109eb  call    ?WitnessUnRegisterHelper@CClusterConnection@@AEAAKXZ; CClusterConnection::WitnessUnRegisterHelper(void)
0x1800109f0  mov     rcx, rbx; this
0x1800109f3  call    ?ResetWitnessNode@CClusterConnection@@AEAAXXZ; CClusterConnection::ResetWitnessNode(void)
0x1800109f8  mov     rcx, rbx; this
0x1800109fb  call    ?DeleteWitnessNodes@CClusterConnection@@AEAAXXZ; CClusterConnection::DeleteWitnessNodes(void)
0x180010a00  xor     edx, edx; unsigned int
0x180010a02  mov     dword ptr [rbx+10h], 80h
0x180010a09  mov     rcx, rbx; this
0x180010a0c  call    ?PendAndRetry@CClusterConnection@@AEAAXK@Z; CClusterConnection::PendAndRetry(ulong)
0x180010a11  mov     rcx, [rbx+1B0h]; lpCriticalSection
0x180010a18  call    cs:__imp_LeaveCriticalSection
0x180010a1e  xor     eax, eax
0x180010a20  add     rsp, 38h
0x180010a24  pop     r15
0x180010a26  pop     r14
0x180010a28  pop     r12
0x180010a2a  pop     rsi
0x180010a2b  pop     rbx
0x180010a2c  pop     rbp
0x180010a2d  retn
```
