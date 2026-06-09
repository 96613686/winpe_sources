# CClusterConnection::ProcessWitnessInterfaceList(void)

- ea: `0x1800101c0`
- end: `0x180010894`
- name: `?ProcessWitnessInterfaceList@CClusterConnection@@QEAAKXZ`
- size: `1748`
- prototype: `unsigned int __fastcall(CClusterConnection *__hidden this)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x180033f10`

## callees

- `0x18000e25c`
- `0x18000f59c`
- `0x1800100c4`
- `0x1800101c0`
- `0x18001089c`
- `0x1800108c8`
- `0x18001093c`
- `0x1800109f0`
- `0x180010aac`
- `0x180010b90`
- `0x180010c2c`
- `0x180024520`
- `0x1800250b0`
- `0x180035098`
- `0x180035380`
- `0x1800355b0`
- `0x180035674`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001040b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010675`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800103ed`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001040b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010657`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180010675`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010861`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180010861`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101ed`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800101ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800104b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800105c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010623`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800106f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010787`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800104b6`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800105c5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010623`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800106f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180010787`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180010266`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800102d2`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180010266`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800102d2`

## pseudocode

```c
__int64 __fastcall CClusterConnection::ProcessWitnessInterfaceList(CClusterConnection *this)
{
  int v2; // r13d
  __int64 v3; // r9
  RPC_STATUS v4; // esi
  __int64 v5; // r8
  PVOID *v6; // rcx
  __int64 v7; // r8
  unsigned int v8; // r14d
  __int64 v9; // rdx
  __int64 v10; // rax
  void *v11; // rcx
  unsigned int v12; // r8d
  PVOID v13; // rcx
  __int64 v14; // rsi
  ULONGLONG TickCount64; // rax
  int v16; // eax
  _QWORD *v17; // rax
  _QWORD *v18; // r9
  _QWORD *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rsi
  ULONGLONG v23; // rax
  _QWORD *v24; // rax
  void *v25; // rcx
  __int64 v26; // rdx
  __int64 v27; // rcx
  _QWORD *v28; // r8
  PVOID v29; // rcx
  __int64 v30; // rsi
  ULONGLONG v31; // rax
  int v32; // eax
  _QWORD *v33; // r8
  _QWORD *v34; // r9
  _QWORD *v35; // r8
  int v36; // eax
  _QWORD *v37; // rax
  _QWORD *v38; // r9
  unsigned int Reply; // [rsp+60h] [rbp+30h] BYREF

  Reply = 0;
  v2 = 0;
  EnterCriticalSection(*((LPCRITICAL_SECTION *)this + 54));
  v3 = *((unsigned int *)this + 80);
  if ( (_DWORD)v3 )
  {
    if ( (unsigned int)(v3 - 3) >= 2 )
    {
      if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
        && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
      {
        WPP_SF_dq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 31, (char *)this + 280, v3, this);
      }
      goto LABEL_127;
    }
    v4 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 280), &Reply);
    v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_dq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 30, v5, *((unsigned int *)this + 80), this);
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    if ( v4 )
      Reply = v4;
    else
      v4 = Reply;
  }
  else
  {
    v8 = RpcAsyncCompleteCall((PRPC_ASYNC_STATE)((char *)this + 280), &Reply);
    v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) >= 3u )
    {
      WPP_SF_ddq(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 29, v7, v8, Reply, this);
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    if ( v8 == 997 )
      goto LABEL_127;
    v4 = Reply;
    if ( Reply == 997 )
      goto LABEL_127;
    if ( v8 )
    {
      v4 = v8;
      Reply = v8;
    }
  }
  if ( !v4 && !*((_QWORD *)this + 50) )
  {
    if ( v6 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) )
    {
      WPP_SF_(v6[2], 32, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids);
      v6 = (PVOID *)WPP_witness_GLOBAL_Control;
    }
    v4 = 87;
    Reply = 87;
  }
  if ( *((_DWORD *)this + 52) )
  {
    if ( v6 != &WPP_witness_GLOBAL_Control && (*((_BYTE *)v6 + 28) & 1) != 0 && *((_BYTE *)v6 + 25) )
      WPP_SF_(v6[2], 33, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids);
    v4 = 1067;
    Reply = 1067;
  }
  if ( v4 )
  {
    CClusterConnection::FreeRpcBinding(this);
    v10 = *((_QWORD *)this + 50);
    if ( v10 )
    {
      v11 = *(void **)(v10 + 8);
      if ( v11 )
      {
        LocalFree(v11);
        *(_QWORD *)(*((_QWORD *)this + 50) + 8LL) = 0;
      }
      LocalFree(*((HLOCAL *)this + 50));
      *((_QWORD *)this + 50) = 0;
    }
    v12 = Reply;
    switch ( Reply )
    {
      case 5u:
      case 0x4DCu:
        v20 = WPP_witness_GLOBAL_Control;
        if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
          && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
        {
          v21 = 34;
          goto LABEL_76;
        }
        break;
      case 0x57u:
      case 0x103u:
        v20 = WPP_witness_GLOBAL_Control;
        if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
          && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
        {
          v21 = 35;
LABEL_76:
          WPP_SF_qD(v20[2], v21, Reply, this, Reply);
          v12 = Reply;
        }
        break;
      case 0x42Bu:
      case 0x71Au:
        goto LABEL_112;
      default:
        v13 = WPP_witness_GLOBAL_Control;
        if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
          && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
        {
          WPP_SF_qD(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 36, Reply, this, Reply);
          v12 = Reply;
        }
        if ( *((_DWORD *)this + 118) != 2 || *((_DWORD *)this + 119) != v12 || (v14 = *((_QWORD *)this + 60)) == 0 )
        {
LABEL_55:
          v16 = *((_DWORD *)this + 113);
          if ( (v16 & 1) != 0 )
          {
            if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 4) != 0 )
            {
              v17 = (_QWORD *)((char *)this + 24);
              if ( *((_QWORD *)this + 6) > 7u )
                v17 = (_QWORD *)*v17;
              McTemplateU0zqq_EventWriteTransfer(v13, v9, v17, v12);
LABEL_66:
              v12 = Reply;
            }
          }
          else
          {
            LOBYTE(v13) = ((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits >> 2) & ((v16 & 2) != 0);
            if ( (_BYTE)v13 )
            {
              v18 = (_QWORD *)((char *)this + 56);
              if ( *((_QWORD *)this + 10) > 7u )
                v18 = (_QWORD *)*v18;
              v19 = (_QWORD *)((char *)this + 24);
              if ( *((_QWORD *)this + 6) > 7u )
                v19 = (_QWORD *)*v19;
              McTemplateU0zzqq_EventWriteTransfer((_DWORD)v13, v9, (_DWORD)v19, (_DWORD)v18, v12);
              goto LABEL_66;
            }
          }
          *((_DWORD *)this + 118) = 2;
LABEL_87:
          *((_DWORD *)this + 119) = v12;
          *((_QWORD *)this + 60) = GetTickCount64();
          goto LABEL_112;
        }
        TickCount64 = GetTickCount64();
        v13 = (PVOID)(v14 + 43200000);
        if ( TickCount64 > v14 + 43200000 )
        {
          v12 = Reply;
          goto LABEL_55;
        }
LABEL_112:
        *((_DWORD *)this + 4) = 128;
        CClusterConnection::PendAndRetry(this, 0x4E20u);
        goto LABEL_127;
    }
    if ( *((_DWORD *)this + 118) == 3 && *((_DWORD *)this + 119) == v12 )
    {
      v22 = *((_QWORD *)this + 60);
      if ( v22 )
      {
        v23 = GetTickCount64();
        v20 = (_QWORD *)(v22 + 43200000);
        if ( v23 <= v22 + 43200000 )
          goto LABEL_112;
        v12 = Reply;
      }
    }
    if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 1) != 0 )
    {
      v24 = (_QWORD *)((char *)this + 88);
      if ( *((_QWORD *)this + 14) > 7u )
        v24 = (_QWORD *)*v24;
      McTemplateU0zq_EventWriteTransfer(v20, WitnessClientRequestWitnessServerListFailed, v24, v12);
      v12 = Reply;
    }
    *((_DWORD *)this + 118) = 3;
    goto LABEL_87;
  }
  *((_DWORD *)this + 4) = 5;
  CClusterConnection::ParseWitnessInterfaceList(this);
  v25 = *(void **)(*((_QWORD *)this + 50) + 8LL);
  if ( v25 )
  {
    LocalFree(v25);
    *(_QWORD *)(*((_QWORD *)this + 50) + 8LL) = 0;
  }
  LocalFree(*((HLOCAL *)this + 50));
  *((_QWORD *)this + 50) = 0;
  CClusterConnection::SelectWitnessNode(this);
  v28 = (_QWORD *)*((_QWORD *)this + 33);
  if ( !v28 )
  {
    v29 = WPP_witness_GLOBAL_Control;
    if ( WPP_witness_GLOBAL_Control != &WPP_witness_GLOBAL_Control
      && (*((_BYTE *)WPP_witness_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_witness_GLOBAL_Control + 25) )
    {
      WPP_SF_q(*((_QWORD *)WPP_witness_GLOBAL_Control + 2), 37, &WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids, this);
    }
    if ( *((_DWORD *)this + 118) != 2
      || *((_DWORD *)this + 119) != 1168
      || (v30 = *((_QWORD *)this + 60)) == 0
      || (v31 = GetTickCount64(), v29 = (PVOID)(v30 + 43200000), v31 > v30 + 43200000) )
    {
      v32 = *((_DWORD *)this + 113);
      if ( (v32 & 1) != 0 )
      {
        if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 4) != 0 )
        {
          v33 = (_QWORD *)((char *)this + 24);
          if ( *((_QWORD *)this + 6) > 7u )
            v33 = (_QWORD *)*v33;
          McTemplateU0zqq_EventWriteTransfer(v29, v26, v33, 1168);
        }
      }
      else if ( (((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits >> 2) & ((v32 & 2) != 0)) != 0 )
      {
        v34 = (_QWORD *)((char *)this + 56);
        if ( *((_QWORD *)this + 10) > 7u )
          v34 = (_QWORD *)*v34;
        v35 = (_QWORD *)((char *)this + 24);
        if ( *((_QWORD *)this + 6) > 7u )
          v35 = (_QWORD *)*v35;
        LOBYTE(v29) = ((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits >> 2) & ((v32 & 2) != 0);
        McTemplateU0zzqq_EventWriteTransfer((_DWORD)v29, v26, (_DWORD)v35, (_DWORD)v34, 144);
      }
      *((_DWORD *)this + 118) = 2;
      *((_DWORD *)this + 119) = 1168;
      *((_QWORD *)this + 60) = GetTickCount64();
    }
    CClusterConnection::DeleteWitnessNodes(this);
    CClusterConnection::FreeRpcBinding(this);
    goto LABEL_112;
  }
  v36 = *((_DWORD *)this + 113);
  if ( (v36 & 1) != 0 )
  {
    if ( (Microsoft_Windows_SMBWitnessClientEnableBits & 2) != 0 )
    {
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      McTemplateU0zz_EventWriteTransfer(v27, WitnessClientServerSelectionSuccess, v28);
    }
  }
  else
  {
    LOBYTE(v27) = ((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits >> 1) & ((v36 & 2) != 0);
    if ( (_BYTE)v27 )
    {
      v37 = (_QWORD *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) > 7u )
        v37 = (_QWORD *)*v37;
      v38 = (_QWORD *)((char *)this + 24);
      if ( *((_QWORD *)this + 6) > 7u )
        v38 = (_QWORD *)*v38;
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      McTemplateU0zzz_EventWriteTransfer(
        v27,
        (unsigned int)WitnessClientServerSelectionSuccess_ShareLevel,
        (_DWORD)v28,
        (_DWORD)v38,
        (__int64)v37);
    }
  }
  CClusterConnection::FreeRpcBinding(this);
  *((_DWORD *)this + 4) = 6;
  v2 = 1;
LABEL_127:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 54));
  if ( v2 )
    CClusterConnection::IssueRegister(this);
  return 0;
}

```

## disassembly

```asm
0x1800101c0  mov     [rsp-28h+arg_8], rbx
0x1800101c5  mov     [rsp-28h+arg_10], rsi
0x1800101ca  push    rbp
0x1800101cb  push    rdi
0x1800101cc  push    r13
0x1800101ce  push    r14
0x1800101d0  push    r15
0x1800101d2  mov     rbp, rsp
0x1800101d5  sub     rsp, 30h
0x1800101d9  mov     rbx, rcx
0x1800101dc  mov     [rbp+Reply], 0
0x1800101e3  mov     rcx, [rcx+1B0h]; lpCriticalSection
0x1800101ea  xor     r13d, r13d
0x1800101ed  call    cs:__imp_EnterCriticalSection
0x1800101f4  nop     dword ptr [rax+rax+00h]
0x1800101f9  lea     r8, [rbx+118h]
0x180010200  mov     r9d, [r8+28h]
0x180010204  mov     ecx, r9d
0x180010207  test    r9d, r9d
0x18001020a  jz      loc_1800102CB
0x180010210  sub     ecx, 3
0x180010213  jz      short loc_18001025F
0x180010215  cmp     ecx, 1
0x180010218  jz      short loc_18001025F
0x18001021a  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010221  lea     r15, WPP_witness_GLOBAL_Control
0x180010228  cmp     rcx, r15
0x18001022b  jz      loc_18001085A
0x180010231  lea     edi, [r13+1]
0x180010235  test    [rcx+1Ch], dil
0x180010239  jz      loc_18001085A
0x18001023f  cmp     byte ptr [rcx+19h], 3
0x180010243  jb      loc_18001085A
0x180010249  mov     rcx, [rcx+10h]
0x18001024d  lea     edx, [rdi+1Eh]
0x180010250  mov     [rsp+30h+var_10], rbx
0x180010255  call    WPP_SF_dq
0x18001025a  jmp     loc_18001085A
0x18001025f  lea     rdx, [rbp+Reply]; Reply
0x180010263  mov     rcx, r8; pAsync
0x180010266  call    cs:__imp_RpcAsyncCompleteCall
0x18001026d  nop     dword ptr [rax+rax+00h]
0x180010272  mov     esi, eax
0x180010274  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001027b  lea     r15, WPP_witness_GLOBAL_Control
0x180010282  mov     edi, 1
0x180010287  cmp     rcx, r15
0x18001028a  jz      short loc_1800102B7
0x18001028c  test    [rcx+1Ch], dil
0x180010290  jz      short loc_1800102B7
0x180010292  cmp     byte ptr [rcx+19h], 3
0x180010296  jb      short loc_1800102B7
0x180010298  mov     r9d, [rbx+140h]
0x18001029f  lea     edx, [rdi+1Dh]
0x1800102a2  mov     rcx, [rcx+10h]
0x1800102a6  mov     [rsp+30h+var_10], rbx
0x1800102ab  call    WPP_SF_dq
0x1800102b0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800102b7  test    esi, esi
0x1800102b9  jz      short loc_1800102C3
0x1800102bb  mov     [rbp+Reply], esi
0x1800102be  jmp     loc_18001034C
0x1800102c3  mov     esi, [rbp+Reply]
0x1800102c6  jmp     loc_18001034C
0x1800102cb  lea     rdx, [rbp+Reply]; Reply
0x1800102cf  mov     rcx, r8; pAsync
0x1800102d2  call    cs:__imp_RpcAsyncCompleteCall
0x1800102d9  nop     dword ptr [rax+rax+00h]
0x1800102de  mov     r14d, eax
0x1800102e1  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800102e8  lea     r15, WPP_witness_GLOBAL_Control
0x1800102ef  mov     edi, 1
0x1800102f4  cmp     rcx, r15
0x1800102f7  jz      short loc_180010327
0x1800102f9  test    [rcx+1Ch], dil
0x1800102fd  jz      short loc_180010327
0x1800102ff  cmp     byte ptr [rcx+19h], 3
0x180010303  jb      short loc_180010327
0x180010305  mov     eax, [rbp+Reply]
0x180010308  lea     edx, [rdi+1Ch]
0x18001030b  mov     rcx, [rcx+10h]
0x18001030f  mov     r9d, r14d
0x180010312  mov     [rsp+30h+var_8], rbx
0x180010317  mov     dword ptr [rsp+30h+var_10], eax
0x18001031b  call    WPP_SF_ddq
0x180010320  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010327  mov     eax, 3E5h
0x18001032c  cmp     r14d, eax
0x18001032f  jz      loc_18001085A
0x180010335  mov     esi, [rbp+Reply]
0x180010338  cmp     esi, eax
0x18001033a  jz      loc_18001085A
0x180010340  test    r14d, r14d
0x180010343  jz      short loc_18001034C
0x180010345  mov     esi, r14d
0x180010348  mov     [rbp+Reply], r14d
0x18001034c  test    esi, esi
0x18001034e  jnz     short loc_18001038C
0x180010350  cmp     [rbx+190h], r13
0x180010357  jnz     short loc_18001038C
0x180010359  cmp     rcx, r15
0x18001035c  jz      short loc_180010384
0x18001035e  test    [rcx+1Ch], dil
0x180010362  jz      short loc_180010384
0x180010364  cmp     [rcx+19h], dil
0x180010368  jb      short loc_180010384
0x18001036a  mov     rcx, [rcx+10h]
0x18001036e  lea     edx, [rsi+20h]
0x180010371  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x180010378  call    WPP_SF_
0x18001037d  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x180010384  mov     esi, 57h ; 'W'
0x180010389  mov     [rbp+Reply], esi
0x18001038c  mov     r14d, 42Bh
0x180010392  cmp     [rbx+0D0h], r13d
0x180010399  jz      short loc_1800103C8
0x18001039b  cmp     rcx, r15
0x18001039e  jz      short loc_1800103C1
0x1800103a0  test    [rcx+1Ch], dil
0x1800103a4  jz      short loc_1800103C1
0x1800103a6  cmp     [rcx+19h], dil
0x1800103aa  jb      short loc_1800103C1
0x1800103ac  mov     rcx, [rcx+10h]
0x1800103b0  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x1800103b7  mov     edx, 21h ; '!'
0x1800103bc  call    WPP_SF_
0x1800103c1  mov     esi, r14d
0x1800103c4  mov     [rbp+Reply], r14d
0x1800103c8  mov     rcx, rbx; this
0x1800103cb  test    esi, esi
0x1800103cd  jz      loc_18001063B
0x1800103d3  call    ?FreeRpcBinding@CClusterConnection@@AEAAXXZ; CClusterConnection::FreeRpcBinding(void)
0x1800103d8  mov     rax, [rbx+190h]
0x1800103df  test    rax, rax
0x1800103e2  jz      short loc_18001041E
0x1800103e4  mov     rcx, [rax+8]; hMem
0x1800103e8  test    rcx, rcx
0x1800103eb  jz      short loc_180010404
0x1800103ed  call    cs:__imp_LocalFree
0x1800103f4  nop     dword ptr [rax+rax+00h]
0x1800103f9  mov     rax, [rbx+190h]
0x180010400  mov     [rax+8], r13
0x180010404  mov     rcx, [rbx+190h]; hMem
0x18001040b  call    cs:__imp_LocalFree
0x180010412  nop     dword ptr [rax+rax+00h]
0x180010417  mov     [rbx+190h], r13
0x18001041e  mov     r8d, [rbp+Reply]
0x180010422  cmp     r8d, 5
0x180010426  jz      loc_180010575
0x18001042c  cmp     r8d, 4DCh
0x180010433  jz      loc_180010575
0x180010439  cmp     r8d, 57h ; 'W'
0x18001043d  jz      loc_180010556
0x180010443  cmp     r8d, 103h
0x18001044a  jz      loc_180010556
0x180010450  cmp     r8d, r14d
0x180010453  jz      loc_1800107AA
0x180010459  cmp     r8d, 71Ah
0x180010460  jz      loc_1800107AA
0x180010466  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001046d  cmp     rcx, r15
0x180010470  jz      short loc_180010498
0x180010472  test    [rcx+1Ch], dil
0x180010476  jz      short loc_180010498
0x180010478  cmp     [rcx+19h], dil
0x18001047c  jb      short loc_180010498
0x18001047e  mov     rcx, [rcx+10h]
0x180010482  mov     edx, 24h ; '$'
0x180010487  mov     r9, rbx
0x18001048a  mov     dword ptr [rsp+30h+var_10], r8d
0x18001048f  call    WPP_SF_qD
0x180010494  mov     r8d, [rbp+Reply]
0x180010498  cmp     dword ptr [rbx+1D8h], 2
0x18001049f  jnz     short loc_1800104D6
0x1800104a1  cmp     [rbx+1DCh], r8d
0x1800104a8  jnz     short loc_1800104D6
0x1800104aa  mov     rsi, [rbx+1E0h]
0x1800104b1  test    rsi, rsi
0x1800104b4  jz      short loc_1800104D6
0x1800104b6  call    cs:__imp_GetTickCount64
0x1800104bd  nop     dword ptr [rax+rax+00h]
0x1800104c2  lea     rcx, [rsi+2932E00h]
0x1800104c9  cmp     rax, rcx
0x1800104cc  jbe     loc_1800107AA
0x1800104d2  mov     r8d, [rbp+Reply]
0x1800104d6  mov     eax, [rbx+1C4h]
0x1800104dc  test    dil, al
0x1800104df  jz      short loc_180010505
0x1800104e1  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 4
0x1800104e8  jz      short loc_180010547
0x1800104ea  lea     rax, [rbx+18h]
0x1800104ee  cmp     qword ptr [rax+18h], 7
0x1800104f3  jbe     short loc_1800104F8
0x1800104f5  mov     rax, [rax]
0x1800104f8  mov     r9d, r8d
0x1800104fb  mov     r8, rax
0x1800104fe  call    McTemplateU0zqq_EventWriteTransfer
0x180010503  jmp     short loc_180010543
0x180010505  test    al, 2
0x180010507  mov     al, cs:Microsoft_Windows_SMBWitnessClientEnableBits
0x18001050d  setnz   cl
0x180010510  shr     al, 2
0x180010513  and     cl, al
0x180010515  test    dil, cl
0x180010518  jz      short loc_180010547
0x18001051a  lea     r9, [rbx+38h]
0x18001051e  cmp     qword ptr [r9+18h], 7
0x180010523  jbe     short loc_180010528
0x180010525  mov     r9, [r9]
0x180010528  lea     rax, [rbx+18h]
0x18001052c  cmp     qword ptr [rax+18h], 7
0x180010531  jbe     short loc_180010536
0x180010533  mov     rax, [rax]
0x180010536  mov     dword ptr [rsp+30h+var_10], r8d
0x18001053b  mov     r8, rax
0x18001053e  call    McTemplateU0zzqq_EventWriteTransfer
0x180010543  mov     r8d, [rbp+Reply]
0x180010547  mov     dword ptr [rbx+1D8h], 2
0x180010551  jmp     loc_18001061C
0x180010556  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001055d  cmp     rcx, r15
0x180010560  jz      short loc_1800105A7
0x180010562  test    [rcx+1Ch], dil
0x180010566  jz      short loc_1800105A7
0x180010568  cmp     [rcx+19h], dil
0x18001056c  jb      short loc_1800105A7
0x18001056e  mov     edx, 23h ; '#'
0x180010573  jmp     short loc_180010592
0x180010575  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18001057c  cmp     rcx, r15
0x18001057f  jz      short loc_1800105A7
0x180010581  test    [rcx+1Ch], dil
0x180010585  jz      short loc_1800105A7
0x180010587  cmp     [rcx+19h], dil
0x18001058b  jb      short loc_1800105A7
0x18001058d  mov     edx, 22h ; '"'
0x180010592  mov     rcx, [rcx+10h]
0x180010596  mov     r9, rbx
0x180010599  mov     dword ptr [rsp+30h+var_10], r8d
0x18001059e  call    WPP_SF_qD
0x1800105a3  mov     r8d, [rbp+Reply]
0x1800105a7  cmp     dword ptr [rbx+1D8h], 3
0x1800105ae  jnz     short loc_1800105E5
0x1800105b0  cmp     [rbx+1DCh], r8d
0x1800105b7  jnz     short loc_1800105E5
0x1800105b9  mov     rsi, [rbx+1E0h]
0x1800105c0  test    rsi, rsi
0x1800105c3  jz      short loc_1800105E5
0x1800105c5  call    cs:__imp_GetTickCount64
0x1800105cc  nop     dword ptr [rax+rax+00h]
0x1800105d1  lea     rcx, [rsi+2932E00h]
0x1800105d8  cmp     rax, rcx
0x1800105db  jbe     loc_1800107AA
0x1800105e1  mov     r8d, [rbp+Reply]
0x1800105e5  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, dil
0x1800105ec  jz      short loc_180010612
0x1800105ee  lea     rax, [rbx+58h]
0x1800105f2  cmp     qword ptr [rax+18h], 7
0x1800105f7  jbe     short loc_1800105FC
0x1800105f9  mov     rax, [rax]
0x1800105fc  mov     r9d, r8d
0x1800105ff  lea     rdx, WitnessClientRequestWitnessServerListFailed
0x180010606  mov     r8, rax
0x180010609  call    McTemplateU0zq_EventWriteTransfer
0x18001060e  mov     r8d, [rbp+Reply]
0x180010612  mov     dword ptr [rbx+1D8h], 3
0x18001061c  mov     [rbx+1DCh], r8d
0x180010623  call    cs:__imp_GetTickCount64
0x18001062a  nop     dword ptr [rax+rax+00h]
0x18001062f  mov     [rbx+1E0h], rax
0x180010636  jmp     loc_1800107AA
0x18001063b  mov     dword ptr [rbx+10h], 5
0x180010642  call    ?ParseWitnessInterfaceList@CClusterConnection@@AEAAXXZ; CClusterConnection::ParseWitnessInterfaceList(void)
0x180010647  mov     rax, [rbx+190h]
0x18001064e  mov     rcx, [rax+8]; hMem
0x180010652  test    rcx, rcx
0x180010655  jz      short loc_18001066E
0x180010657  call    cs:__imp_LocalFree
0x18001065e  nop     dword ptr [rax+rax+00h]
0x180010663  mov     rax, [rbx+190h]
0x18001066a  mov     [rax+8], r13
0x18001066e  mov     rcx, [rbx+190h]; hMem
0x180010675  call    cs:__imp_LocalFree
0x18001067c  nop     dword ptr [rax+rax+00h]
0x180010681  mov     rcx, rbx; this
0x180010684  mov     [rbx+190h], r13
0x18001068b  call    ?SelectWitnessNode@CClusterConnection@@AEAAPEAVCWitnessServer@@XZ; CClusterConnection::SelectWitnessNode(void)
0x180010690  mov     r8, [rbx+108h]
0x180010697  test    r8, r8
0x18001069a  jnz     loc_1800107C3
0x1800106a0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x1800106a7  cmp     rcx, r15
0x1800106aa  jz      short loc_1800106CF
0x1800106ac  test    [rcx+1Ch], dil
0x1800106b0  jz      short loc_1800106CF
0x1800106b2  cmp     [rcx+19h], dil
0x1800106b6  jb      short loc_1800106CF
0x1800106b8  mov     rcx, [rcx+10h]
0x1800106bc  lea     edx, [r8+25h]
0x1800106c0  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
  ... truncated ...
```
