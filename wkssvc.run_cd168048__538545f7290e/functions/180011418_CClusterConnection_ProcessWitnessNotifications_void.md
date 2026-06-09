# CClusterConnection::ProcessWitnessNotifications(void)

- ea: `0x180011418`
- end: `0x18001186f`
- name: `?ProcessWitnessNotifications@CClusterConnection@@QEAAKXZ`
- size: `1111`
- prototype: `unsigned int __fastcall(CClusterConnection *__hidden this)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180033f20`

## callees

- `0x18000f2c8`
- `0x18001089c`
- `0x1800109f0`
- `0x180010ce8`
- `0x180010e00`
- `0x180011418`
- `0x18001208c`
- `0x180012188`
- `0x180024520`
- `0x180035150`
- `0x180035380`
- `0x1800355b0`
- `0x180035674`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117f0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180011718`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800117f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011852`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011852`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001143a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001143a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800114b1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180011511`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800114b1`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180011511`

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
0x180011418  push    rbp
0x18001141a  push    rbx
0x18001141b  push    rsi
0x18001141c  push    r12
0x18001141e  push    r14
0x180011420  push    r15
0x180011422  mov     rbp, rsp
0x180011425  sub     rsp, 38h
0x180011429  mov     rbx, rcx
0x18001142c  mov     [rbp+Reply], 0
0x180011433  mov     rcx, [rcx+1B0h]; lpCriticalSection
0x18001143a  call    cs:__imp_EnterCriticalSection
0x180011441  nop     dword ptr [rax+rax+00h]
0x180011446  lea     r8, [rbx+118h]
0x18001144d  mov     r9d, [r8+28h]
0x180011451  mov     ecx, r9d
0x180011454  test    r9d, r9d
0x180011457  jz      loc_18001150A
0x18001145d  sub     ecx, 3
0x180011460  jz      short loc_1800114AA
0x180011462  cmp     ecx, 1
0x180011465  jz      short loc_1800114AA
0x180011467  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001146e  lea     rsi, WPP_witness_GLOBAL_Control
0x180011475  cmp     rcx, rsi
0x180011478  jz      loc_18001184B
0x18001147e  test    byte ptr [rcx+1Ch], 1
0x180011482  jz      loc_18001184B
0x180011488  cmp     byte ptr [rcx+19h], 3
0x18001148c  jb      loc_18001184B
0x180011492  mov     rcx, [rcx+10h]
0x180011496  mov     edx, 2Dh ; '-'
0x18001149b  mov     [rsp+38h+var_18], rbx
0x1800114a0  call    WPP_SF_dq
0x1800114a5  jmp     loc_18001184B
0x1800114aa  lea     rdx, [rbp+Reply]; Reply
0x1800114ae  mov     rcx, r8; pAsync
0x1800114b1  call    cs:__imp_RpcAsyncCompleteCall
0x1800114b8  nop     dword ptr [rax+rax+00h]
0x1800114bd  mov     r14d, eax
0x1800114c0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800114c7  lea     rsi, WPP_witness_GLOBAL_Control
0x1800114ce  cmp     rcx, rsi
0x1800114d1  jz      short loc_180011500
0x1800114d3  test    byte ptr [rcx+1Ch], 1
0x1800114d7  jz      short loc_180011500
0x1800114d9  cmp     byte ptr [rcx+19h], 3
0x1800114dd  jb      short loc_180011500
0x1800114df  mov     r9d, [rbx+140h]
0x1800114e6  mov     edx, 2Ch ; ','
0x1800114eb  mov     rcx, [rcx+10h]
0x1800114ef  mov     [rsp+38h+var_18], rbx
0x1800114f4  call    WPP_SF_dq
0x1800114f9  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011500  test    r14d, r14d
0x180011503  jnz     short loc_180011581
0x180011505  mov     edx, [rbp+Reply]
0x180011508  jmp     short loc_180011587
0x18001150a  lea     rdx, [rbp+Reply]; Reply
0x18001150e  mov     rcx, r8; pAsync
0x180011511  call    cs:__imp_RpcAsyncCompleteCall
0x180011518  nop     dword ptr [rax+rax+00h]
0x18001151d  mov     r14d, eax
0x180011520  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011527  lea     rsi, WPP_witness_GLOBAL_Control
0x18001152e  cmp     rcx, rsi
0x180011531  jz      short loc_180011563
0x180011533  test    byte ptr [rcx+1Ch], 1
0x180011537  jz      short loc_180011563
0x180011539  cmp     byte ptr [rcx+19h], 3
0x18001153d  jb      short loc_180011563
0x18001153f  mov     eax, [rbp+Reply]
0x180011542  mov     edx, 2Bh ; '+'
0x180011547  mov     rcx, [rcx+10h]
0x18001154b  mov     r9d, r14d
0x18001154e  mov     [rsp+38h+var_10], rbx
0x180011553  mov     dword ptr [rsp+38h+var_18], eax
0x180011557  call    WPP_SF_ddq
0x18001155c  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011563  mov     eax, 3E5h
0x180011568  cmp     r14d, eax
0x18001156b  jz      loc_18001184B
0x180011571  mov     edx, [rbp+Reply]
0x180011574  cmp     edx, eax
0x180011576  jz      loc_18001184B
0x18001157c  test    r14d, r14d
0x18001157f  jz      short loc_180011587
0x180011581  mov     edx, r14d
0x180011584  mov     [rbp+Reply], edx
0x180011587  xor     r12d, r12d
0x18001158a  test    edx, edx
0x18001158c  jnz     short loc_1800115CC
0x18001158e  cmp     [rbx+188h], r12
0x180011595  jnz     short loc_1800115CC
0x180011597  cmp     rcx, rsi
0x18001159a  jz      short loc_1800115C4
0x18001159c  test    byte ptr [rcx+1Ch], 1
0x1800115a0  jz      short loc_1800115C4
0x1800115a2  cmp     byte ptr [rcx+19h], 1
0x1800115a6  jb      short loc_1800115C4
0x1800115a8  mov     rcx, [rcx+10h]
0x1800115ac  lea     edx, [r12+2Eh]
0x1800115b1  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x1800115b8  call    WPP_SF_
0x1800115bd  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800115c4  mov     edx, 57h ; 'W'
0x1800115c9  mov     [rbp+Reply], edx
0x1800115cc  mov     r15d, 42Bh
0x1800115d2  cmp     [rbx+0D0h], r12d
0x1800115d9  jz      short loc_18001160E
0x1800115db  cmp     rcx, rsi
0x1800115de  jz      short loc_180011608
0x1800115e0  test    byte ptr [rcx+1Ch], 1
0x1800115e4  jz      short loc_180011608
0x1800115e6  cmp     byte ptr [rcx+19h], 1
0x1800115ea  jb      short loc_180011608
0x1800115ec  mov     rcx, [rcx+10h]
0x1800115f0  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x1800115f7  mov     edx, 2Fh ; '/'
0x1800115fc  call    WPP_SF_
0x180011601  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011608  mov     edx, r15d
0x18001160b  mov     [rbp+Reply], edx
0x18001160e  test    edx, edx
0x180011610  jz      loc_1800116E4
0x180011616  cmp     edx, 5B4h
0x18001161c  jz      loc_1800116E4
0x180011622  cmp     edx, r15d
0x180011625  jz      loc_1800116E4
0x18001162b  cmp     edx, 71Ah
0x180011631  jz      loc_1800116E4
0x180011637  mov     r9, [rbx+108h]
0x18001163e  test    r9, r9
0x180011641  jz      loc_1800116E4
0x180011647  mov     eax, [rbx+1C4h]
0x18001164d  test    al, 1
0x18001164f  jz      short loc_18001168C
0x180011651  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 1
0x180011658  jz      loc_1800116E4
0x18001165e  lea     rax, [rbx+18h]
0x180011662  cmp     qword ptr [rax+18h], 7
0x180011667  jbe     short loc_18001166C
0x180011669  mov     rax, [rax]
0x18001166c  cmp     qword ptr [r9+18h], 7
0x180011671  jbe     short loc_180011676
0x180011673  mov     r9, [r9]
0x180011676  mov     r8d, edx
0x180011679  mov     [rsp+38h+var_18], rax
0x18001167e  lea     rdx, WitnessClientServerFailure
0x180011685  call    McTemplateU0qzz_EventWriteTransfer
0x18001168a  jmp     short loc_1800116DA
0x18001168c  test    al, 2
0x18001168e  setnz   al
0x180011691  and     al, cs:Microsoft_Windows_SMBWitnessClientEnableBits
0x180011697  test    al, 1
0x180011699  jz      short loc_1800116E4
0x18001169b  lea     rcx, [rbx+38h]
0x18001169f  cmp     qword ptr [rcx+18h], 7
0x1800116a4  jbe     short loc_1800116A9
0x1800116a6  mov     rcx, [rcx]
0x1800116a9  lea     rax, [rbx+18h]
0x1800116ad  cmp     qword ptr [rax+18h], 7
0x1800116b2  jbe     short loc_1800116B7
0x1800116b4  mov     rax, [rax]
0x1800116b7  cmp     qword ptr [r9+18h], 7
0x1800116bc  jbe     short loc_1800116C1
0x1800116be  mov     r9, [r9]
0x1800116c1  mov     r8d, edx
0x1800116c4  mov     [rsp+38h+var_10], rcx
0x1800116c9  lea     rdx, WitnessClientServerFailure_ShareLevel
0x1800116d0  mov     [rsp+38h+var_18], rax
0x1800116d5  call    McTemplateU0qzzz_EventWriteTransfer
0x1800116da  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800116e1  mov     edx, [rbp+Reply]
0x1800116e4  mov     rax, cs:?gWitnessNotifyCallBack@@3P6AKPEAXW4_RPC_ASYNC_EVENT@@J@ZEA; ulong (*gWitnessNotifyCallBack)(void *,_RPC_ASYNC_EVENT,long)
0x1800116eb  test    rax, rax
0x1800116ee  jz      short loc_180011735
0x1800116f0  mov     rcx, [rbx+188h]
0x1800116f7  mov     r8d, edx
0x1800116fa  mov     edx, [rbx+140h]
0x180011700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011705  cmp     eax, 4DEh
0x18001170a  jz      short loc_18001172B
0x18001170c  mov     rcx, [rbx+188h]; hMem
0x180011713  test    rcx, rcx
0x180011716  jz      short loc_18001172B
0x180011718  call    cs:__imp_LocalFree
0x18001171f  nop     dword ptr [rax+rax+00h]
0x180011724  mov     [rbx+188h], r12
0x18001172b  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011732  mov     edx, [rbp+Reply]
0x180011735  test    edx, edx
0x180011737  jnz     short loc_18001177E
0x180011739  cmp     [rbx+188h], r12
0x180011740  jz      short loc_1800117B5
0x180011742  mov     rcx, rbx; this
0x180011745  call    ?ProcessNotificationMessage@CClusterConnection@@AEAAKXZ; CClusterConnection::ProcessNotificationMessage(void)
0x18001174a  test    eax, eax
0x18001174c  jz      short loc_1800117AD
0x18001174e  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180011755  cmp     rcx, rsi
0x180011758  jz      short loc_1800117AD
0x18001175a  test    byte ptr [rcx+1Ch], 1
0x18001175e  jz      short loc_1800117AD
0x180011760  cmp     byte ptr [rcx+19h], 3
0x180011764  jb      short loc_1800117AD
0x180011766  mov     rcx, [rcx+10h]
0x18001176a  mov     edx, 30h ; '0'
0x18001176f  mov     r9d, eax
0x180011772  mov     [rsp+38h+var_18], rbx
0x180011777  call    WPP_SF_dq
0x18001177c  jmp     short loc_1800117AD
0x18001177e  cmp     edx, 5B4h
0x180011784  jnz     short loc_1800117B5
0x180011786  cmp     rcx, rsi
0x180011789  jz      short loc_1800117AD
0x18001178b  test    byte ptr [rcx+1Ch], 1
0x18001178f  jz      short loc_1800117AD
0x180011791  cmp     byte ptr [rcx+19h], 3
0x180011795  jb      short loc_1800117AD
0x180011797  mov     rcx, [rcx+10h]
0x18001179b  mov     edx, 31h ; '1'
0x1800117a0  mov     r9, rbx
0x1800117a3  mov     dword ptr [rsp+38h+var_18], r14d
0x1800117a8  call    WPP_SF_qD
0x1800117ad  mov     r15d, 1
0x1800117b3  jmp     short loc_1800117E4
0x1800117b5  xor     r15d, r15d
0x1800117b8  cmp     rcx, rsi
0x1800117bb  jz      short loc_1800117DE
0x1800117bd  test    byte ptr [rcx+1Ch], 1
0x1800117c1  jz      short loc_1800117DE
0x1800117c3  cmp     byte ptr [rcx+19h], 3
0x1800117c7  jb      short loc_1800117DE
0x1800117c9  mov     rcx, [rcx+10h]
0x1800117cd  lea     edx, [r15+32h]
0x1800117d1  mov     r9d, r14d
0x1800117d4  mov     [rsp+38h+var_18], rbx
0x1800117d9  call    WPP_SF_dq
0x1800117de  mov     r12d, 1
0x1800117e4  mov     rcx, [rbx+188h]; hMem
0x1800117eb  test    rcx, rcx
0x1800117ee  jz      short loc_180011807
0x1800117f0  call    cs:__imp_LocalFree
0x1800117f7  nop     dword ptr [rax+rax+00h]
0x1800117fc  mov     qword ptr [rbx+188h], 0
0x180011807  test    r15d, r15d
0x18001180a  jz      short loc_18001181D
0x18001180c  mov     rcx, rbx; this
0x18001180f  mov     dword ptr [rbx+10h], 7
0x180011816  call    ?IssueNotify@CClusterConnection@@AEAAXXZ; CClusterConnection::IssueNotify(void)
0x18001181b  jmp     short loc_18001184B
0x18001181d  test    r12d, r12d
0x180011820  jz      short loc_18001184B
0x180011822  mov     rcx, rbx; this
0x180011825  call    ?WitnessUnRegisterHelper@CClusterConnection@@AEAAKXZ; CClusterConnection::WitnessUnRegisterHelper(void)
0x18001182a  mov     rcx, rbx; this
0x18001182d  call    ?ResetWitnessNode@CClusterConnection@@AEAAXXZ; CClusterConnection::ResetWitnessNode(void)
0x180011832  mov     rcx, rbx; this
0x180011835  call    ?DeleteWitnessNodes@CClusterConnection@@AEAAXXZ; CClusterConnection::DeleteWitnessNodes(void)
0x18001183a  xor     edx, edx; unsigned int
0x18001183c  mov     dword ptr [rbx+10h], 80h
0x180011843  mov     rcx, rbx; this
0x180011846  call    ?PendAndRetry@CClusterConnection@@AEAAXK@Z; CClusterConnection::PendAndRetry(ulong)
0x18001184b  mov     rcx, [rbx+1B0h]; lpCriticalSection
0x180011852  call    cs:__imp_LeaveCriticalSection
0x180011859  nop     dword ptr [rax+rax+00h]
0x18001185e  xor     eax, eax
0x180011860  add     rsp, 38h
0x180011864  pop     r15
0x180011866  pop     r14
0x180011868  pop     r12
0x18001186a  pop     rsi
0x18001186b  pop     rbx
0x18001186c  pop     rbp
0x18001186d  retn
```
