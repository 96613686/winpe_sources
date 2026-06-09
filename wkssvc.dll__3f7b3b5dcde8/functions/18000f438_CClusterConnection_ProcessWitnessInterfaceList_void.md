# CClusterConnection::ProcessWitnessInterfaceList(void)

- ea: `0x18000f438`
- end: `0x18000faba`
- name: `?ProcessWitnessInterfaceList@CClusterConnection@@QEAAKXZ`
- size: `1666`
- prototype: `__int64 __fastcall(CClusterConnection *this)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x1800310d0`

## callees

- `0x18000d610`
- `0x18000e834`
- `0x18000f33c`
- `0x18000f438`
- `0x18000fac0`
- `0x18000faec`
- `0x18000fb58`
- `0x18000fc08`
- `0x18000fcc4`
- `0x18000fda8`
- `0x18000fe44`
- `0x180022b54`
- `0x180023694`
- `0x1800321c0`
- `0x180032490`
- `0x1800326a8`
- `0x180032760`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f650`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f668`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000f8b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa8e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000fa8e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f465`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000f465`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f70d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f816`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f86e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f92c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f9ba`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f70d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f816`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f86e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f92c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18000f9ba`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f4d8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f53b`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f4d8`
- `RPCRT4!RpcAsyncCompleteCall` at `0x18000f53b`

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
  _QWORD *v37; // r9
  _QWORD *v38; // rax
  _QWORD *v39; // r9
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
      goto LABEL_129;
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
      goto LABEL_129;
    v4 = Reply;
    if ( Reply == 997 )
      goto LABEL_129;
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
        goto LABEL_129;
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
      v37 = (_QWORD *)((char *)this + 24);
      if ( *((_QWORD *)this + 6) > 7u )
        v37 = (_QWORD *)*v37;
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      McTemplateU0zz_EventWriteTransfer(v27, WitnessClientServerSelectionSuccess, v28, v37);
    }
  }
  else
  {
    LOBYTE(v27) = ((unsigned __int8)Microsoft_Windows_SMBWitnessClientEnableBits >> 1) & ((v36 & 2) != 0);
    if ( (_BYTE)v27 )
    {
      v38 = (_QWORD *)((char *)this + 56);
      if ( *((_QWORD *)this + 10) > 7u )
        v38 = (_QWORD *)*v38;
      v39 = (_QWORD *)((char *)this + 24);
      if ( *((_QWORD *)this + 6) > 7u )
        v39 = (_QWORD *)*v39;
      if ( v28[3] > 7u )
        v28 = (_QWORD *)*v28;
      McTemplateU0zzz_EventWriteTransfer(
        v27,
        (unsigned int)WitnessClientServerSelectionSuccess_ShareLevel,
        (_DWORD)v28,
        (_DWORD)v39,
        (__int64)v38);
    }
  }
  CClusterConnection::FreeRpcBinding(this);
  *((_DWORD *)this + 4) = 6;
  v2 = 1;
LABEL_129:
  LeaveCriticalSection(*((LPCRITICAL_SECTION *)this + 54));
  if ( v2 )
    CClusterConnection::IssueRegister(this);
  return 0;
}

```

## disassembly

```asm
0x18000f438  mov     [rsp-28h+arg_8], rbx
0x18000f43d  mov     [rsp-28h+arg_10], rsi
0x18000f442  push    rbp
0x18000f443  push    rdi
0x18000f444  push    r13
0x18000f446  push    r14
0x18000f448  push    r15
0x18000f44a  mov     rbp, rsp
0x18000f44d  sub     rsp, 30h
0x18000f451  mov     rbx, rcx
0x18000f454  mov     [rbp+Reply], 0
0x18000f45b  mov     rcx, [rcx+1B0h]; lpCriticalSection
0x18000f462  xor     r13d, r13d
0x18000f465  call    cs:__imp_EnterCriticalSection
0x18000f46b  lea     r8, [rbx+118h]
0x18000f472  mov     r9d, [r8+28h]
0x18000f476  mov     ecx, r9d
0x18000f479  test    r9d, r9d
0x18000f47c  jz      loc_18000F534
0x18000f482  sub     ecx, 3
0x18000f485  jz      short loc_18000F4D1
0x18000f487  cmp     ecx, 1
0x18000f48a  jz      short loc_18000F4D1
0x18000f48c  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f493  lea     r15, WPP_witness_GLOBAL_Control
0x18000f49a  cmp     rcx, r15
0x18000f49d  jz      loc_18000FA87
0x18000f4a3  lea     edi, [r13+1]
0x18000f4a7  test    [rcx+1Ch], dil
0x18000f4ab  jz      loc_18000FA87
0x18000f4b1  cmp     byte ptr [rcx+19h], 3
0x18000f4b5  jb      loc_18000FA87
0x18000f4bb  mov     rcx, [rcx+10h]
0x18000f4bf  lea     edx, [rdi+1Eh]
0x18000f4c2  mov     [rsp+30h+var_10], rbx
0x18000f4c7  call    WPP_SF_dq
0x18000f4cc  jmp     loc_18000FA87
0x18000f4d1  lea     rdx, [rbp+Reply]; Reply
0x18000f4d5  mov     rcx, r8; pAsync
0x18000f4d8  call    cs:__imp_RpcAsyncCompleteCall
0x18000f4de  mov     esi, eax
0x18000f4e0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f4e7  lea     r15, WPP_witness_GLOBAL_Control
0x18000f4ee  mov     edi, 1
0x18000f4f3  cmp     rcx, r15
0x18000f4f6  jz      short loc_18000F523
0x18000f4f8  test    [rcx+1Ch], dil
0x18000f4fc  jz      short loc_18000F523
0x18000f4fe  cmp     byte ptr [rcx+19h], 3
0x18000f502  jb      short loc_18000F523
0x18000f504  mov     r9d, [rbx+140h]
0x18000f50b  lea     edx, [rdi+1Dh]
0x18000f50e  mov     rcx, [rcx+10h]
0x18000f512  mov     [rsp+30h+var_10], rbx
0x18000f517  call    WPP_SF_dq
0x18000f51c  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f523  test    esi, esi
0x18000f525  jz      short loc_18000F52F
0x18000f527  mov     [rbp+Reply], esi
0x18000f52a  jmp     loc_18000F5AF
0x18000f52f  mov     esi, [rbp+Reply]
0x18000f532  jmp     short loc_18000F5AF
0x18000f534  lea     rdx, [rbp+Reply]; Reply
0x18000f538  mov     rcx, r8; pAsync
0x18000f53b  call    cs:__imp_RpcAsyncCompleteCall
0x18000f541  mov     r14d, eax
0x18000f544  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f54b  lea     r15, WPP_witness_GLOBAL_Control
0x18000f552  mov     edi, 1
0x18000f557  cmp     rcx, r15
0x18000f55a  jz      short loc_18000F58A
0x18000f55c  test    [rcx+1Ch], dil
0x18000f560  jz      short loc_18000F58A
0x18000f562  cmp     byte ptr [rcx+19h], 3
0x18000f566  jb      short loc_18000F58A
0x18000f568  mov     eax, [rbp+Reply]
0x18000f56b  lea     edx, [rdi+1Ch]
0x18000f56e  mov     rcx, [rcx+10h]
0x18000f572  mov     r9d, r14d
0x18000f575  mov     [rsp+30h+var_8], rbx
0x18000f57a  mov     dword ptr [rsp+30h+var_10], eax
0x18000f57e  call    WPP_SF_ddq
0x18000f583  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f58a  mov     eax, 3E5h
0x18000f58f  cmp     r14d, eax
0x18000f592  jz      loc_18000FA87
0x18000f598  mov     esi, [rbp+Reply]
0x18000f59b  cmp     esi, eax
0x18000f59d  jz      loc_18000FA87
0x18000f5a3  test    r14d, r14d
0x18000f5a6  jz      short loc_18000F5AF
0x18000f5a8  mov     esi, r14d
0x18000f5ab  mov     [rbp+Reply], r14d
0x18000f5af  test    esi, esi
0x18000f5b1  jnz     short loc_18000F5EF
0x18000f5b3  cmp     [rbx+190h], r13
0x18000f5ba  jnz     short loc_18000F5EF
0x18000f5bc  cmp     rcx, r15
0x18000f5bf  jz      short loc_18000F5E7
0x18000f5c1  test    [rcx+1Ch], dil
0x18000f5c5  jz      short loc_18000F5E7
0x18000f5c7  cmp     [rcx+19h], dil
0x18000f5cb  jb      short loc_18000F5E7
0x18000f5cd  mov     rcx, [rcx+10h]
0x18000f5d1  lea     edx, [rsi+20h]
0x18000f5d4  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18000f5db  call    WPP_SF_
0x18000f5e0  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f5e7  mov     esi, 57h ; 'W'
0x18000f5ec  mov     [rbp+Reply], esi
0x18000f5ef  mov     r14d, 42Bh
0x18000f5f5  cmp     [rbx+0D0h], r13d
0x18000f5fc  jz      short loc_18000F62B
0x18000f5fe  cmp     rcx, r15
0x18000f601  jz      short loc_18000F624
0x18000f603  test    [rcx+1Ch], dil
0x18000f607  jz      short loc_18000F624
0x18000f609  cmp     [rcx+19h], dil
0x18000f60d  jb      short loc_18000F624
0x18000f60f  mov     rcx, [rcx+10h]
0x18000f613  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18000f61a  mov     edx, 21h ; '!'
0x18000f61f  call    WPP_SF_
0x18000f624  mov     esi, r14d
0x18000f627  mov     [rbp+Reply], r14d
0x18000f62b  mov     rcx, rbx; this
0x18000f62e  test    esi, esi
0x18000f630  jz      loc_18000F880
0x18000f636  call    ?FreeRpcBinding@CClusterConnection@@AEAAXXZ; CClusterConnection::FreeRpcBinding(void)
0x18000f63b  mov     rax, [rbx+190h]
0x18000f642  test    rax, rax
0x18000f645  jz      short loc_18000F675
0x18000f647  mov     rcx, [rax+8]; hMem
0x18000f64b  test    rcx, rcx
0x18000f64e  jz      short loc_18000F661
0x18000f650  call    cs:__imp_LocalFree
0x18000f656  mov     rax, [rbx+190h]
0x18000f65d  mov     [rax+8], r13
0x18000f661  mov     rcx, [rbx+190h]; hMem
0x18000f668  call    cs:__imp_LocalFree
0x18000f66e  mov     [rbx+190h], r13
0x18000f675  mov     r8d, [rbp+Reply]
0x18000f679  cmp     r8d, 5
0x18000f67d  jz      loc_18000F7C6
0x18000f683  cmp     r8d, 4DCh
0x18000f68a  jz      loc_18000F7C6
0x18000f690  cmp     r8d, 57h ; 'W'
0x18000f694  jz      loc_18000F7A7
0x18000f69a  cmp     r8d, 103h
0x18000f6a1  jz      loc_18000F7A7
0x18000f6a7  cmp     r8d, r14d
0x18000f6aa  jz      loc_18000F9D7
0x18000f6b0  cmp     r8d, 71Ah
0x18000f6b7  jz      loc_18000F9D7
0x18000f6bd  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f6c4  cmp     rcx, r15
0x18000f6c7  jz      short loc_18000F6EF
0x18000f6c9  test    [rcx+1Ch], dil
0x18000f6cd  jz      short loc_18000F6EF
0x18000f6cf  cmp     [rcx+19h], dil
0x18000f6d3  jb      short loc_18000F6EF
0x18000f6d5  mov     rcx, [rcx+10h]
0x18000f6d9  mov     edx, 24h ; '$'
0x18000f6de  mov     r9, rbx
0x18000f6e1  mov     dword ptr [rsp+30h+var_10], r8d
0x18000f6e6  call    WPP_SF_qD
0x18000f6eb  mov     r8d, [rbp+Reply]
0x18000f6ef  cmp     dword ptr [rbx+1D8h], 2
0x18000f6f6  jnz     short loc_18000F727
0x18000f6f8  cmp     [rbx+1DCh], r8d
0x18000f6ff  jnz     short loc_18000F727
0x18000f701  mov     rsi, [rbx+1E0h]
0x18000f708  test    rsi, rsi
0x18000f70b  jz      short loc_18000F727
0x18000f70d  call    cs:__imp_GetTickCount64
0x18000f713  lea     rcx, [rsi+2932E00h]
0x18000f71a  cmp     rax, rcx
0x18000f71d  jbe     loc_18000F9D7
0x18000f723  mov     r8d, [rbp+Reply]
0x18000f727  mov     eax, [rbx+1C4h]
0x18000f72d  test    dil, al
0x18000f730  jz      short loc_18000F756
0x18000f732  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, 4
0x18000f739  jz      short loc_18000F798
0x18000f73b  lea     rax, [rbx+18h]
0x18000f73f  cmp     qword ptr [rax+18h], 7
0x18000f744  jbe     short loc_18000F749
0x18000f746  mov     rax, [rax]
0x18000f749  mov     r9d, r8d
0x18000f74c  mov     r8, rax
0x18000f74f  call    McTemplateU0zqq_EventWriteTransfer
0x18000f754  jmp     short loc_18000F794
0x18000f756  test    al, 2
0x18000f758  mov     al, cs:Microsoft_Windows_SMBWitnessClientEnableBits
0x18000f75e  setnz   cl
0x18000f761  shr     al, 2
0x18000f764  and     cl, al
0x18000f766  test    dil, cl
0x18000f769  jz      short loc_18000F798
0x18000f76b  lea     r9, [rbx+38h]
0x18000f76f  cmp     qword ptr [r9+18h], 7
0x18000f774  jbe     short loc_18000F779
0x18000f776  mov     r9, [r9]
0x18000f779  lea     rax, [rbx+18h]
0x18000f77d  cmp     qword ptr [rax+18h], 7
0x18000f782  jbe     short loc_18000F787
0x18000f784  mov     rax, [rax]
0x18000f787  mov     dword ptr [rsp+30h+var_10], r8d
0x18000f78c  mov     r8, rax
0x18000f78f  call    McTemplateU0zzqq_EventWriteTransfer
0x18000f794  mov     r8d, [rbp+Reply]
0x18000f798  mov     dword ptr [rbx+1D8h], 2
0x18000f7a2  jmp     loc_18000F867
0x18000f7a7  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f7ae  cmp     rcx, r15
0x18000f7b1  jz      short loc_18000F7F8
0x18000f7b3  test    [rcx+1Ch], dil
0x18000f7b7  jz      short loc_18000F7F8
0x18000f7b9  cmp     [rcx+19h], dil
0x18000f7bd  jb      short loc_18000F7F8
0x18000f7bf  mov     edx, 23h ; '#'
0x18000f7c4  jmp     short loc_18000F7E3
0x18000f7c6  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f7cd  cmp     rcx, r15
0x18000f7d0  jz      short loc_18000F7F8
0x18000f7d2  test    [rcx+1Ch], dil
0x18000f7d6  jz      short loc_18000F7F8
0x18000f7d8  cmp     [rcx+19h], dil
0x18000f7dc  jb      short loc_18000F7F8
0x18000f7de  mov     edx, 22h ; '"'
0x18000f7e3  mov     rcx, [rcx+10h]
0x18000f7e7  mov     r9, rbx
0x18000f7ea  mov     dword ptr [rsp+30h+var_10], r8d
0x18000f7ef  call    WPP_SF_qD
0x18000f7f4  mov     r8d, [rbp+Reply]
0x18000f7f8  cmp     dword ptr [rbx+1D8h], 3
0x18000f7ff  jnz     short loc_18000F830
0x18000f801  cmp     [rbx+1DCh], r8d
0x18000f808  jnz     short loc_18000F830
0x18000f80a  mov     rsi, [rbx+1E0h]
0x18000f811  test    rsi, rsi
0x18000f814  jz      short loc_18000F830
0x18000f816  call    cs:__imp_GetTickCount64
0x18000f81c  lea     rcx, [rsi+2932E00h]
0x18000f823  cmp     rax, rcx
0x18000f826  jbe     loc_18000F9D7
0x18000f82c  mov     r8d, [rbp+Reply]
0x18000f830  test    cs:Microsoft_Windows_SMBWitnessClientEnableBits, dil
0x18000f837  jz      short loc_18000F85D
0x18000f839  lea     rax, [rbx+58h]
0x18000f83d  cmp     qword ptr [rax+18h], 7
0x18000f842  jbe     short loc_18000F847
0x18000f844  mov     rax, [rax]
0x18000f847  mov     r9d, r8d
0x18000f84a  lea     rdx, WitnessClientRequestWitnessServerListFailed
0x18000f851  mov     r8, rax
0x18000f854  call    McTemplateU0zq_EventWriteTransfer
0x18000f859  mov     r8d, [rbp+Reply]
0x18000f85d  mov     dword ptr [rbx+1D8h], 3
0x18000f867  mov     [rbx+1DCh], r8d
0x18000f86e  call    cs:__imp_GetTickCount64
0x18000f874  mov     [rbx+1E0h], rax
0x18000f87b  jmp     loc_18000F9D7
0x18000f880  mov     dword ptr [rbx+10h], 5
0x18000f887  call    ?ParseWitnessInterfaceList@CClusterConnection@@AEAAXXZ; CClusterConnection::ParseWitnessInterfaceList(void)
0x18000f88c  mov     rax, [rbx+190h]
0x18000f893  mov     rcx, [rax+8]; hMem
0x18000f897  test    rcx, rcx
0x18000f89a  jz      short loc_18000F8AD
0x18000f89c  call    cs:__imp_LocalFree
0x18000f8a2  mov     rax, [rbx+190h]
0x18000f8a9  mov     [rax+8], r13
0x18000f8ad  mov     rcx, [rbx+190h]; hMem
0x18000f8b4  call    cs:__imp_LocalFree
0x18000f8ba  mov     rcx, rbx; this
0x18000f8bd  mov     [rbx+190h], r13
0x18000f8c4  call    ?SelectWitnessNode@CClusterConnection@@AEAAPEAVCWitnessServer@@XZ; CClusterConnection::SelectWitnessNode(void)
0x18000f8c9  mov     r8, [rbx+108h]
0x18000f8d0  test    r8, r8
0x18000f8d3  jnz     loc_18000F9F0
0x18000f8d9  mov     rcx, cs:WPP_witness_GLOBAL_Control
0x18000f8e0  cmp     rcx, r15
0x18000f8e3  jz      short loc_18000F908
0x18000f8e5  test    [rcx+1Ch], dil
0x18000f8e9  jz      short loc_18000F908
0x18000f8eb  cmp     [rcx+19h], dil
0x18000f8ef  jb      short loc_18000F908
0x18000f8f1  mov     rcx, [rcx+10h]
0x18000f8f5  lea     edx, [r8+25h]
0x18000f8f9  lea     r8, WPP_05a199c97cb13ffb21b1b8c24cf946fe_Traceguids
0x18000f900  mov     r9, rbx
0x18000f903  call    WPP_SF_q
0x18000f908  cmp     dword ptr [rbx+1D8h], 2
0x18000f90f  mov     r14d, 490h
0x18000f915  jnz     short loc_18000F942
0x18000f917  cmp     [rbx+1DCh], r14d
0x18000f91e  jnz     short loc_18000F942
0x18000f920  mov     rsi, [rbx+1E0h]
0x18000f927  test    rsi, rsi
0x18000f92a  jz      short loc_18000F942
  ... truncated ...
```
