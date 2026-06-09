# ScValidateNotificationParams(_SC_HANDLE_STRUCT *,int,_SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2 *,_USERVICE_NOTIFY_CLIENT_IDENTIFIERS *,ulong *,int *)

- ea: `0x140025d08`
- end: `0x14002631f`
- name: `?ScValidateNotificationParams@@YAKPEAU_SC_HANDLE_STRUCT@@HPEAU_SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2@@PEAT_USERVICE_NOTIFY_CLIENT_IDENTIFIERS@@PEAKPEAH@Z`
- size: `1559`
- prototype: `unsigned int __fastcall(struct _SC_HANDLE_STRUCT *, int, struct _SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2 *, union _USERVICE_NOTIFY_CLIENT_IDENTIFIERS *, unsigned int *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x14007fbc0`

## callees

- `0x140003e54`
- `0x140019014`
- `0x140025d08`
- `0x140032be0`
- `0x140033670`
- `0x140080b04`
- `0x14008131c`
- `0x140092ab0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026176`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400261db`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140026169`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140026169`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1400261d1`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessTimes` at `0x1400261d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400262ff`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400262ff`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140025fc1`
- `RPCRT4!I_RpcBindingIsClientLocal` at `0x140025fc1`

## pseudocode

```c
__int64 __fastcall ScValidateNotificationParams(
        struct _SC_HANDLE_STRUCT *a1,
        int a2,
        struct _SERVICE_NOTIFY_STATUS_CHANGE_PARAMS_2 *a3,
        union _USERVICE_NOTIFY_CLIENT_IDENTIFIERS *a4,
        unsigned int *a5,
        int *a6)
{
  struct CServiceRecord *v6; // rsi
  __int64 v10; // rax
  __int64 v11; // rdx
  unsigned int IsClientLocal; // ebx
  PRPC_ASYNC_STATE v13; // rcx
  const WCHAR *v14; // rax
  int v15; // edx
  int v16; // r8d
  PRPC_ASYNC_STATE v17; // r10
  const WCHAR *v18; // rax
  int v19; // edx
  PRPC_ASYNC_STATE v20; // rcx
  const WCHAR *v21; // rax
  int v22; // edx
  int v23; // r9d
  PRPC_ASYNC_STATE v24; // r10
  const WCHAR *v25; // rax
  int v26; // edx
  unsigned __int64 v27; // rax
  unsigned __int64 v28; // xmm0_8
  PRPC_ASYNC_STATE v29; // r10
  const WCHAR *v30; // rax
  int v31; // edx
  unsigned __int64 v32; // rax
  DWORD ProcessId; // r14d
  int v34; // r8d
  const WCHAR *v35; // rax
  const WCHAR *v36; // rax
  BOOL v37; // ecx
  struct _FILETIME ExitTime; // [rsp+40h] [rbp-10h] BYREF
  _FILETIME CreationTime; // [rsp+48h] [rbp-8h] BYREF
  HANDLE Process; // [rsp+90h] [rbp+40h] BYREF
  unsigned int ClientLocalFlag; // [rsp+98h] [rbp+48h] BYREF
  union _USERVICE_NOTIFY_CLIENT_IDENTIFIERS *v43; // [rsp+A8h] [rbp+58h]

  v43 = a4;
  v6 = g_pNotificationsPlaceholderSR;
  ClientLocalFlag = 0;
  Process = 0;
  if ( !a2 )
    v6 = (struct CServiceRecord *)*((_QWORD *)a1 + 2);
  v10 = *((_QWORD *)a1 + 3);
  if ( v10 )
  {
    v11 = *(_QWORD *)(v10 + 8);
    if ( v11 )
    {
      IsClientLocal = memcmp((char *)a3 + 28, (const void *)(v11 + 52), 0x10u) != 0 ? 1242 : 2014;
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
        return IsClientLocal;
      v14 = L"SCM";
      if ( !a2 )
        v14 = (const WCHAR *)*((_QWORD *)v6 + 7);
      v15 = 42;
      goto LABEL_10;
    }
  }
  v16 = *((_DWORD *)a3 + 2);
  if ( (v16 & 0x3FF) == 0 )
  {
    IsClientLocal = 87;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return IsClientLocal;
    v18 = L"SCM";
    if ( !a2 )
      v18 = (const WCHAR *)*((_QWORD *)v6 + 7);
    v19 = 43;
LABEL_18:
    WPP_SF_LSd(v17->StubInfo, v19, v16, v16, (__int64)v18, 87);
    goto LABEL_115;
  }
  if ( (v16 & 0x27F) != 0 && (v16 & 0x180) != 0 )
  {
    IsClientLocal = 87;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return IsClientLocal;
    v18 = L"SCM";
    if ( !a2 )
      v18 = (const WCHAR *)*((_QWORD *)v6 + 7);
    v19 = 44;
    goto LABEL_18;
  }
  if ( a2 == 1 && (v16 & 0x27F) != 0 || !a2 && (v16 & 0x180) != 0 )
  {
    IsClientLocal = 6;
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return IsClientLocal;
    v21 = L"SCM";
    if ( !a2 )
      v21 = (const WCHAR *)*((_QWORD *)v6 + 7);
    v22 = 45;
    v23 = v16;
    goto LABEL_36;
  }
  if ( (*((_BYTE *)a1 + 4) & 8) != 0 && (v16 & 0x180) == 0 )
  {
    IsClientLocal = 87;
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return IsClientLocal;
    v25 = L"SCM";
    if ( !a2 )
      v25 = (const WCHAR *)*((_QWORD *)v6 + 7);
    v26 = 46;
    goto LABEL_44;
  }
  v27 = *(_QWORD *)((char *)a3 + 28);
  v28 = _mm_srli_si128((__m128i)0LL, 8).m128i_u64[0];
  if ( !v27 )
    v27 = *(_QWORD *)((char *)a3 + 36) - v28;
  if ( !v27 )
  {
    IsClientLocal = 87;
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control || (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) == 0 )
      return IsClientLocal;
    v30 = L"SCM";
    if ( !a2 )
      v30 = (const WCHAR *)*((_QWORD *)v6 + 7);
    v31 = 47;
    goto LABEL_53;
  }
  IsClientLocal = I_RpcBindingIsClientLocal(0, &ClientLocalFlag);
  if ( IsClientLocal )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
    {
      v14 = L"SCM";
      if ( !a2 )
        v14 = (const WCHAR *)*((_QWORD *)v6 + 7);
      v15 = 48;
LABEL_10:
      WPP_SF_Sd(
        v13->StubInfo,
        v15,
        (unsigned int)WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids,
        (_DWORD)v14,
        IsClientLocal);
    }
  }
  else
  {
    v16 = *((_DWORD *)a1 + 1);
    if ( (v16 & 4) != 0 && !ClientLocalFlag || (v16 & 2) != 0 && ClientLocalFlag )
    {
      IsClientLocal = 87;
      v24 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      {
        v25 = L"SCM";
        if ( !a2 )
          v25 = (const WCHAR *)*((_QWORD *)v6 + 7);
        v26 = 49;
LABEL_44:
        WPP_SF_SLd(
          v24->StubInfo,
          v26,
          (unsigned int)WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids,
          (_DWORD)v25,
          v16,
          87);
      }
    }
    else
    {
      IsClientLocal = 0;
      if ( !ClientLocalFlag )
        goto LABEL_115;
      CreationTime = 0;
      ExitTime = 0;
      if ( s_pfnI_RpcOpenClientProcess )
      {
        v32 = *(_QWORD *)((char *)a3 + 12);
        if ( !v32 )
          v32 = *(_QWORD *)((char *)a3 + 20) - v28;
        if ( v32 )
        {
          IsClientLocal = ((__int64 (__fastcall *)(_QWORD, __int64, HANDLE *))s_pfnI_RpcOpenClientProcess)(
                            0,
                            1024,
                            &Process);
          if ( IsClientLocal )
          {
            v13 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
              && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
            {
              v14 = L"SCM";
              if ( !a2 )
                v14 = (const WCHAR *)*((_QWORD *)v6 + 7);
              v15 = 52;
              goto LABEL_10;
            }
          }
          else
          {
            ProcessId = GetProcessId(Process);
            if ( ProcessId )
            {
              if ( !GetProcessTimes(Process, &CreationTime, &ExitTime, &ExitTime, &ExitTime) )
              {
                IsClientLocal = GetLastError();
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  v35 = L"SCM";
                  if ( !a2 )
                    v35 = (const WCHAR *)*((_QWORD *)v6 + 7);
                  WPP_SF_dSd(
                    WPP_GLOBAL_Control->StubInfo,
                    54,
                    (unsigned int)WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids,
                    ProcessId,
                    (__int64)v35,
                    IsClientLocal);
                }
                goto LABEL_115;
              }
              if ( CreationTime != *(_QWORD *)v43 )
              {
                IsClientLocal = 1067;
                if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                  && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
                {
                  v36 = L"SCM";
                  if ( !a2 )
                    v36 = (const WCHAR *)*((_QWORD *)v6 + 7);
                  WPP_SF_iidSd(
                    WPP_GLOBAL_Control->StubInfo,
                    *(_QWORD *)v43,
                    v34,
                    CreationTime.dwLowDateTime,
                    *(_QWORD *)v43,
                    ProcessId,
                    (__int64)v36);
                }
                goto LABEL_115;
              }
              IsClientLocal = ScCheckClientThreadId(ProcessId, *(_QWORD *)a3, 0);
              if ( !IsClientLocal )
              {
                v37 = ClientLocalFlag != 0;
                *a5 = ProcessId;
                *a6 = v37;
                goto LABEL_115;
              }
              v20 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v21 = L"SCM";
                if ( !a2 )
                  v21 = (const WCHAR *)*((_QWORD *)v6 + 7);
                v23 = *(_DWORD *)a3;
                v22 = 56;
LABEL_36:
                WPP_SF_LSd(v20->StubInfo, v22, v16, v23, (__int64)v21, IsClientLocal);
              }
            }
            else
            {
              IsClientLocal = GetLastError();
              v13 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
                && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
              {
                v14 = L"SCM";
                if ( !a2 )
                  v14 = (const WCHAR *)*((_QWORD *)v6 + 7);
                v15 = 53;
                goto LABEL_10;
              }
            }
          }
        }
        else
        {
          IsClientLocal = 87;
          v29 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            v30 = L"SCM";
            if ( !a2 )
              v30 = (const WCHAR *)*((_QWORD *)v6 + 7);
            v31 = 51;
LABEL_53:
            WPP_SF_Sd(
              v29->StubInfo,
              v31,
              (unsigned int)WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids,
              (_DWORD)v30,
              87);
          }
        }
      }
      else
      {
        IsClientLocal = 50;
        v13 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          v14 = L"SCM";
          if ( !a2 )
            v14 = (const WCHAR *)*((_QWORD *)v6 + 7);
          v15 = 50;
          goto LABEL_10;
        }
      }
    }
  }
LABEL_115:
  if ( Process )
    CloseHandle(Process);
  return IsClientLocal;
}

```

## disassembly

```asm
0x140025d08  mov     [rsp-38h+arg_10], rbx
0x140025d0d  mov     [rsp-38h+arg_18], r9
0x140025d12  push    rbp
0x140025d13  push    rsi
0x140025d14  push    rdi
0x140025d15  push    r12
0x140025d17  push    r13
0x140025d19  push    r14
0x140025d1b  push    r15
0x140025d1d  mov     rbp, rsp
0x140025d20  sub     rsp, 50h
0x140025d24  mov     rsi, cs:?g_pNotificationsPlaceholderSR@@3PEAVCServiceRecord@@EA; CServiceRecord * g_pNotificationsPlaceholderSR
0x140025d2b  mov     r15, r8
0x140025d2e  mov     [rbp+ClientLocalFlag], 0
0x140025d35  mov     edi, edx
0x140025d37  mov     [rbp+Process], 0
0x140025d3f  mov     r14, rcx
0x140025d42  test    edx, edx
0x140025d44  jnz     short loc_140025D4A
0x140025d46  mov     rsi, [rcx+10h]
0x140025d4a  mov     rax, [rcx+18h]
0x140025d4e  xorps   xmm0, xmm0
0x140025d51  test    rax, rax
0x140025d54  jz      short loc_140025DD3
0x140025d56  mov     rdx, [rax+8]
0x140025d5a  test    rdx, rdx
0x140025d5d  jz      short loc_140025DD3
0x140025d5f  lea     rcx, [r8+1Ch]; Buf1
0x140025d63  add     rdx, 34h ; '4'; Buf2
0x140025d67  mov     r8d, 10h; Size
0x140025d6d  call    memcmp
0x140025d72  neg     eax
0x140025d74  sbb     ebx, ebx
0x140025d76  and     ebx, 0FFFFFCFCh
0x140025d7c  add     ebx, 7DEh
0x140025d82  mov     rcx, cs:WPP_GLOBAL_Control
0x140025d89  lea     rax, WPP_GLOBAL_Control
0x140025d90  cmp     rcx, rax
0x140025d93  jz      loc_140026305
0x140025d99  test    byte ptr [rcx+1Ch], 1
0x140025d9d  jz      loc_140026305
0x140025da3  lea     rax, InstanceName; "SCM"
0x140025daa  test    edi, edi
0x140025dac  jnz     short loc_140025DB2
0x140025dae  mov     rax, [rsi+38h]
0x140025db2  mov     edx, 2Ah ; '*'
0x140025db7  mov     rcx, [rcx+10h]
0x140025dbb  mov     dword ptr [rsp+50h+lpUserTime], ebx
0x140025dbf  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x140025dc6  mov     r9, rax
0x140025dc9  call    WPP_SF_Sd
0x140025dce  jmp     loc_1400262F6
0x140025dd3  mov     r8d, [r8+8]
0x140025dd7  test    r8d, 3FFh
0x140025dde  jnz     short loc_140025E37
0x140025de0  mov     ecx, 57h ; 'W'
0x140025de5  mov     ebx, ecx
0x140025de7  mov     r10, cs:WPP_GLOBAL_Control
0x140025dee  lea     rax, WPP_GLOBAL_Control
0x140025df5  cmp     r10, rax
0x140025df8  jz      loc_140026305
0x140025dfe  test    byte ptr [r10+1Ch], 1
0x140025e03  jz      loc_140026305
0x140025e09  lea     rax, InstanceName; "SCM"
0x140025e10  test    edi, edi
0x140025e12  jnz     short loc_140025E18
0x140025e14  mov     rax, [rsi+38h]
0x140025e18  mov     edx, 2Bh ; '+'
0x140025e1d  mov     [rsp+50h+var_28], ecx
0x140025e21  mov     r9d, r8d
0x140025e24  mov     rcx, [r10+10h]
0x140025e28  mov     [rsp+50h+lpUserTime], rax
0x140025e2d  call    WPP_SF_LSd
0x140025e32  jmp     loc_1400262F6
0x140025e37  mov     eax, r8d
0x140025e3a  mov     ecx, r8d
0x140025e3d  and     eax, 180h
0x140025e42  and     ecx, 27Fh
0x140025e48  jz      short loc_140025E8D
0x140025e4a  test    eax, eax
0x140025e4c  jz      short loc_140025E8D
0x140025e4e  mov     ecx, 57h ; 'W'
0x140025e53  mov     ebx, ecx
0x140025e55  mov     r10, cs:WPP_GLOBAL_Control
0x140025e5c  lea     rax, WPP_GLOBAL_Control
0x140025e63  cmp     r10, rax
0x140025e66  jz      loc_140026305
0x140025e6c  test    byte ptr [r10+1Ch], 1
0x140025e71  jz      loc_140026305
0x140025e77  lea     rax, InstanceName; "SCM"
0x140025e7e  test    edi, edi
0x140025e80  jnz     short loc_140025E86
0x140025e82  mov     rax, [rsi+38h]
0x140025e86  mov     edx, 2Ch ; ','
0x140025e8b  jmp     short loc_140025E1D
0x140025e8d  cmp     edi, 1
0x140025e90  jnz     short loc_140025E96
0x140025e92  test    ecx, ecx
0x140025e94  jnz     short loc_140025E9E
0x140025e96  test    edi, edi
0x140025e98  jnz     short loc_140025EE8
0x140025e9a  test    eax, eax
0x140025e9c  jz      short loc_140025EE8
0x140025e9e  mov     ebx, 6
0x140025ea3  mov     rcx, cs:WPP_GLOBAL_Control
0x140025eaa  lea     rax, WPP_GLOBAL_Control
0x140025eb1  cmp     rcx, rax
0x140025eb4  jz      loc_140026305
0x140025eba  test    byte ptr [rcx+1Ch], 1
0x140025ebe  jz      loc_140026305
0x140025ec4  lea     rax, InstanceName; "SCM"
0x140025ecb  test    edi, edi
0x140025ecd  jnz     short loc_140025ED3
0x140025ecf  mov     rax, [rsi+38h]
0x140025ed3  mov     edx, 2Dh ; '-'
0x140025ed8  mov     r9d, r8d
0x140025edb  mov     rcx, [rcx+10h]
0x140025edf  mov     [rsp+50h+var_28], ebx
0x140025ee3  jmp     loc_140025E28
0x140025ee8  test    byte ptr [r14+4], 8
0x140025eed  jz      short loc_140025F4F
0x140025eef  test    eax, eax
0x140025ef1  jnz     short loc_140025F4F
0x140025ef3  lea     ecx, [rax+57h]
0x140025ef6  mov     ebx, ecx
0x140025ef8  mov     r10, cs:WPP_GLOBAL_Control
0x140025eff  lea     rax, WPP_GLOBAL_Control
0x140025f06  cmp     r10, rax
0x140025f09  jz      loc_140026305
0x140025f0f  test    byte ptr [r10+1Ch], 1
0x140025f14  jz      loc_140026305
0x140025f1a  lea     rax, InstanceName; "SCM"
0x140025f21  test    edi, edi
0x140025f23  jnz     short loc_140025F29
0x140025f25  mov     rax, [rsi+38h]
0x140025f29  mov     edx, 2Eh ; '.'
0x140025f2e  mov     [rsp+50h+var_28], ecx
0x140025f32  mov     r9, rax
0x140025f35  mov     rcx, [r10+10h]
0x140025f39  mov     dword ptr [rsp+50h+lpUserTime], r8d
0x140025f3e  lea     r8, WPP_1d352e7a0bd43dd98d3d0c2932bfa1b0_Traceguids
0x140025f45  call    WPP_SF_SLd
0x140025f4a  jmp     loc_1400262F6
0x140025f4f  mov     rax, [r15+1Ch]
0x140025f53  movq    r13, xmm0
0x140025f58  psrldq  xmm0, 8
0x140025f5d  movq    r12, xmm0
0x140025f62  sub     rax, r13
0x140025f65  jnz     short loc_140025F6E
0x140025f67  mov     rax, [r15+24h]
0x140025f6b  sub     rax, r12
0x140025f6e  test    rax, rax
0x140025f71  jnz     short loc_140025FBB
0x140025f73  lea     ecx, [rax+57h]
0x140025f76  mov     ebx, ecx
0x140025f78  mov     r10, cs:WPP_GLOBAL_Control
0x140025f7f  lea     rax, WPP_GLOBAL_Control
0x140025f86  cmp     r10, rax
0x140025f89  jz      loc_140026305
0x140025f8f  test    byte ptr [r10+1Ch], 1
0x140025f94  jz      loc_140026305
0x140025f9a  lea     rax, InstanceName; "SCM"
0x140025fa1  test    edi, edi
0x140025fa3  jnz     short loc_140025FA9
0x140025fa5  mov     rax, [rsi+38h]
0x140025fa9  mov     edx, 2Fh ; '/'
0x140025fae  mov     dword ptr [rsp+50h+lpUserTime], ecx
0x140025fb2  mov     rcx, [r10+10h]
0x140025fb6  jmp     loc_140025DBF
0x140025fbb  lea     rdx, [rbp+ClientLocalFlag]; ClientLocalFlag
0x140025fbf  xor     ecx, ecx; BindingHandle
0x140025fc1  call    cs:__imp_I_RpcBindingIsClientLocal
0x140025fc7  mov     ebx, eax
0x140025fc9  test    eax, eax
0x140025fcb  jz      short loc_140026007
0x140025fcd  mov     rcx, cs:WPP_GLOBAL_Control
0x140025fd4  lea     rax, WPP_GLOBAL_Control
0x140025fdb  cmp     rcx, rax
0x140025fde  jz      loc_1400262F6
0x140025fe4  test    byte ptr [rcx+1Ch], 1
0x140025fe8  jz      loc_1400262F6
0x140025fee  lea     rax, InstanceName; "SCM"
0x140025ff5  test    edi, edi
0x140025ff7  jnz     short loc_140025FFD
0x140025ff9  mov     rax, [rsi+38h]
0x140025ffd  mov     edx, 30h ; '0'
0x140026002  jmp     loc_140025DB7
0x140026007  mov     r8d, [r14+4]
0x14002600b  mov     eax, [rbp+ClientLocalFlag]
0x14002600e  test    r8b, 4
0x140026012  jz      short loc_140026018
0x140026014  test    eax, eax
0x140026016  jz      short loc_140026022
0x140026018  test    r8b, 2
0x14002601c  jz      short loc_140026064
0x14002601e  test    eax, eax
0x140026020  jz      short loc_140026064
0x140026022  mov     ecx, 57h ; 'W'
0x140026027  mov     ebx, ecx
0x140026029  mov     r10, cs:WPP_GLOBAL_Control
0x140026030  lea     rax, WPP_GLOBAL_Control
0x140026037  cmp     r10, rax
0x14002603a  jz      loc_1400262F6
0x140026040  test    byte ptr [r10+1Ch], 1
0x140026045  jz      loc_1400262F6
0x14002604b  lea     rax, InstanceName; "SCM"
0x140026052  test    edi, edi
0x140026054  jnz     short loc_14002605A
0x140026056  mov     rax, [rsi+38h]
0x14002605a  mov     edx, 31h ; '1'
0x14002605f  jmp     loc_140025F2E
0x140026064  xor     ebx, ebx
0x140026066  test    eax, eax
0x140026068  jz      loc_1400262F6
0x14002606e  mov     r9, cs:?s_pfnI_RpcOpenClientProcess@@3P6AJPEAXKPEAPEAX@ZEA; long (*s_pfnI_RpcOpenClientProcess)(void *,ulong,void * *)
0x140026075  mov     qword ptr [rbp+CreationTime.dwLowDateTime], rbx
0x140026079  mov     qword ptr [rbp+ExitTime.dwLowDateTime], rbx
0x14002607d  test    r9, r9
0x140026080  jnz     short loc_1400260BD
0x140026082  lea     ebx, [r9+32h]
0x140026086  mov     rcx, cs:WPP_GLOBAL_Control
0x14002608d  lea     rax, WPP_GLOBAL_Control
0x140026094  cmp     rcx, rax
0x140026097  jz      loc_1400262F6
0x14002609d  test    byte ptr [rcx+1Ch], 1
0x1400260a1  jz      loc_1400262F6
0x1400260a7  lea     rax, InstanceName; "SCM"
0x1400260ae  test    edi, edi
0x1400260b0  jnz     short loc_1400260B6
0x1400260b2  mov     rax, [rsi+38h]
0x1400260b6  mov     edx, ebx
0x1400260b8  jmp     loc_140025DB7
0x1400260bd  mov     rax, [r15+0Ch]
0x1400260c1  sub     rax, r13
0x1400260c4  jnz     short loc_1400260CD
0x1400260c6  mov     rax, [r15+14h]
0x1400260ca  sub     rax, r12
0x1400260cd  test    rax, rax
0x1400260d0  jnz     short loc_140026112
0x1400260d2  lea     ecx, [rax+57h]
0x1400260d5  mov     ebx, ecx
0x1400260d7  mov     r10, cs:WPP_GLOBAL_Control
0x1400260de  lea     rax, WPP_GLOBAL_Control
0x1400260e5  cmp     r10, rax
0x1400260e8  jz      loc_1400262F6
0x1400260ee  test    byte ptr [r10+1Ch], 1
0x1400260f3  jz      loc_1400262F6
0x1400260f9  lea     rax, InstanceName; "SCM"
0x140026100  test    edi, edi
0x140026102  jnz     short loc_140026108
0x140026104  mov     rax, [rsi+38h]
0x140026108  mov     edx, 33h ; '3'
0x14002610d  jmp     loc_140025FAE
0x140026112  lea     r8, [rbp+Process]
0x140026116  mov     edx, 400h
0x14002611b  xor     ecx, ecx
0x14002611d  mov     rax, r9
0x140026120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140026125  mov     ebx, eax
0x140026127  test    eax, eax
0x140026129  jz      short loc_140026165
0x14002612b  mov     rcx, cs:WPP_GLOBAL_Control
0x140026132  lea     rax, WPP_GLOBAL_Control
0x140026139  cmp     rcx, rax
0x14002613c  jz      loc_1400262F6
0x140026142  test    byte ptr [rcx+1Ch], 1
0x140026146  jz      loc_1400262F6
0x14002614c  lea     rax, InstanceName; "SCM"
0x140026153  test    edi, edi
0x140026155  jnz     short loc_14002615B
0x140026157  mov     rax, [rsi+38h]
0x14002615b  mov     edx, 34h ; '4'
0x140026160  jmp     loc_140025DB7
0x140026165  mov     rcx, [rbp+Process]; Process
0x140026169  call    cs:__imp_GetProcessId
0x14002616f  mov     r14d, eax
0x140026172  test    eax, eax
0x140026174  jnz     short loc_1400261B8
0x140026176  call    cs:__imp_GetLastError
0x14002617c  mov     ebx, eax
0x14002617e  mov     rcx, cs:WPP_GLOBAL_Control
0x140026185  lea     rax, WPP_GLOBAL_Control
0x14002618c  cmp     rcx, rax
0x14002618f  jz      loc_1400262F6
0x140026195  test    byte ptr [rcx+1Ch], 1
0x140026199  jz      loc_1400262F6
0x14002619f  lea     rax, InstanceName; "SCM"
0x1400261a6  test    edi, edi
0x1400261a8  jnz     short loc_1400261AE
0x1400261aa  mov     rax, [rsi+38h]
0x1400261ae  mov     edx, 35h ; '5'
0x1400261b3  jmp     loc_140025DB7
0x1400261b8  mov     rcx, [rbp+Process]; hProcess
0x1400261bc  lea     rax, [rbp+ExitTime]
0x1400261c0  lea     r9, [rbp+ExitTime]; lpKernelTime
0x1400261c4  mov     [rsp+50h+lpUserTime], rax; lpUserTime
0x1400261c9  lea     r8, [rbp+ExitTime]; lpExitTime
0x1400261cd  lea     rdx, [rbp+CreationTime]; lpCreationTime
0x1400261d1  call    cs:__imp_GetProcessTimes
0x1400261d7  test    eax, eax
  ... truncated ...
```
