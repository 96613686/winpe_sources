# ConnectToSubscriber(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,int,ulong *,int *,_NOTIFICATION_COMPONENT * *)

- ea: `0x140025d50`
- end: `0x140026581`
- name: `?ConnectToSubscriber@@YAKPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@HPEAKPEAHPEAPEAU2@@Z`
- size: `2097`
- prototype: `unsigned int __usercall@<eax>(struct _NOTIFICATION_CLIENT_DEF *@<rcx>, struct _NOTIFICATION_COMPONENT *@<rdx>, int@<r8d>, unsigned int *@<r9>, int *, struct _NOTIFICATION_COMPONENT **)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1400403d8`

## callees

- `0x1400057f4`
- `0x14000fb30`
- `0x140025d50`
- `0x140026590`
- `0x140026970`
- `0x1400269f0`
- `0x140026b80`
- `0x140041c34`
- `0x14004df08`
- `0x140053720`
- `0x14005f43c`
- `0x140092088`
- `0x1400927b0`
- `0x140092a10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140025e4d`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140025e4d`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140026255`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x140026255`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026341`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140026341`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140026209`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x140026209`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002621b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14002621b`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400261d5`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1400261d5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140025e36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140025f95`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140025e36`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x140025f95`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140025fca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140025fca`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140026235`
- `api-ms-win-service-management-l1-1-0!OpenSCManagerW` at `0x140026235`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140026180`
- `api-ms-win-service-management-l1-1-0!CloseServiceHandle` at `0x140026180`
- `ntdll!NtOpenThreadToken` at `0x1400261b9`
- `ntdll!NtOpenThreadToken` at `0x1400261b9`
- `ntdll!EtwEventEnabled` at `0x140025df0`
- `ntdll!EtwEventEnabled` at `0x140025ebc`
- `ntdll!EtwEventEnabled` at `0x140025df0`
- `ntdll!EtwEventEnabled` at `0x140025ebc`
- `ntdll!EtwEventWrite` at `0x140025e30`
- `ntdll!EtwEventWrite` at `0x140025f05`
- `ntdll!EtwEventWrite` at `0x140025e30`
- `ntdll!EtwEventWrite` at `0x140025f05`
- `ntdll!RtlNtStatusToDosError` at `0x1400261c5`
- `ntdll!RtlNtStatusToDosError` at `0x1400261c5`

## string_xrefs

- `0x140025e43`: `TrustedInstaller`

## pseudocode

```c
__int64 __fastcall ConnectToSubscriber(
        struct _NOTIFICATION_CLIENT_DEF *a1,
        struct _NOTIFICATION_COMPONENT *a2,
        int a3,
        unsigned int *a4,
        int *a5,
        struct _NOTIFICATION_COMPONENT **a6)
{
  int *v6; // rsi
  int v7; // r12d
  DWORD v9; // edi
  __int64 v11; // rbx
  __int64 v12; // rax
  bool v13; // zf
  ULONGLONG TickCount64; // r15
  __int64 v15; // rdx
  unsigned int v16; // eax
  CUser *v17; // rcx
  SC_HANDLE v18; // rcx
  int v20; // edi
  unsigned int v21; // eax
  unsigned int v22; // eax
  int v23; // edi
  __int64 v24; // rdx
  unsigned __int16 v25; // ax
  int v26; // r8d
  CUser *v27; // r10
  unsigned int *v28; // rdi
  __int64 v29; // r9
  const WCHAR *v30; // rdi
  int v31; // eax
  SC_HANDLE v32; // rax
  DWORD LastError; // eax
  struct _NOTIFICATION_CLIENT_DEF *v34; // rcx
  unsigned int v35; // eax
  __int64 v36; // rdx
  const wchar_t *v37; // rcx
  unsigned int v38; // [rsp+30h] [rbp-49h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-41h] BYREF
  unsigned int v40; // [rsp+40h] [rbp-39h]
  int v41; // [rsp+44h] [rbp-35h]
  int v42; // [rsp+48h] [rbp-31h] BYREF
  unsigned int v43[2]; // [rsp+50h] [rbp-29h]
  int v44; // [rsp+58h] [rbp-21h]
  int v45; // [rsp+5Ch] [rbp-1Dh]
  unsigned int *v46; // [rsp+60h] [rbp-19h]
  struct _NOTIFICATION_COMPONENT **v47; // [rsp+68h] [rbp-11h]
  int *v48; // [rsp+70h] [rbp-9h]
  int *v49; // [rsp+78h] [rbp-1h] BYREF
  int v50; // [rsp+80h] [rbp+7h]
  int v51; // [rsp+84h] [rbp+Bh]

  v6 = &dword_1400ABAAC;
  v48 = a5;
  v7 = 1;
  v46 = a4;
  v45 = a3;
  if ( a2 )
    v6 = (int *)a2;
  v47 = a6;
  v9 = 50;
  v38 = 0;
  v40 = -1;
  v11 = -1;
  LODWORD(TokenHandle) = 1;
  v41 = 50;
  v42 = 1;
  *(_QWORD *)v43 = 60000;
  v44 = 1;
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_ConnectToSubscriber_Start) )
  {
    v49 = v6;
    v12 = -1;
    do
      v13 = *((_WORD *)v6 + ++v12) == 0;
    while ( !v13 );
    v50 = 2 * v12 + 2;
    v51 = 0;
    EtwEventWrite(g_TraceRegHandle, WLEvt_ConnectToSubscriber_Start, 1, &v49);
  }
  TickCount64 = GetTickCount64();
  if ( (unsigned int)_o__wcsicmp(*((_QWORD *)a2 + 72), L"TrustedInstaller") )
  {
    LODWORD(v15) = 60000;
  }
  else
  {
    v40 = IsServiceExpectedToStart(a1, a2, (int *)&TokenHandle, &v42);
    v7 = (int)TokenHandle;
    v15 = 60000;
    if ( v40 == 1 )
      v15 = 600000;
    *(_QWORD *)v43 = v15;
  }
  if ( *((_DWORD *)a2 + 150) )
  {
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        55,
        WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
        *((_QWORD *)a2 + 72));
      LODWORD(v15) = v43[0];
    }
    v30 = (const WCHAR *)*((_QWORD *)a2 + 72);
    TokenHandle = 0;
    if ( NtCurrentTeb()->IsImpersonating )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids);
      }
      v31 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 0xCu, 1u, &TokenHandle);
      if ( v31 >= 0 )
      {
        RevertToSelf();
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids);
        }
        WaitForDesiredService(v30, v43[0], 1);
        if ( !SetThreadToken(0, TokenHandle) )
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              WPP_dee1fec175ed3bc1a62ebb36f32fb4e0_Traceguids,
              LastError);
          }
        }
        CloseHandle(TokenHandle);
        v9 = 50;
      }
      else
      {
        RtlNtStatusToDosError(v31);
        v9 = 50;
      }
    }
    else
    {
      WaitForDesiredService(v30, v15, 1);
      v9 = 50;
    }
  }
  while ( 1 )
  {
    v16 = BuildRpcBinding((LPCWCH)a2);
    v38 = v16;
    if ( !v16 )
      break;
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_Sl(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        56,
        (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
        (_DWORD)a2,
        v16);
      v17 = WPP_GLOBAL_Control;
    }
    if ( !v45 )
      goto LABEL_13;
    v7 = 0;
    LODWORD(TokenHandle) = 0;
    if ( v38 != 1753 )
      goto LABEL_13;
    if ( GetTickCount64() - TickCount64 >= *(_QWORD *)v43 )
      break;
    if ( *((_QWORD *)a1 + 4) || (v32 = OpenSCManagerW(0, 0, 1u), (*((_QWORD *)a1 + 4) = v32) != 0) )
    {
      if ( v40 == -1 || v40 == 1 && (v20 = *((_DWORD *)a2 + 148), v21 = GetTickCount() - v20, v9 = v41, v21 > 0x1388) )
      {
        v22 = IsServiceExpectedToStart(a1, a2, (int *)&TokenHandle, &v42);
        v7 = (int)TokenHandle;
        v40 = v22;
      }
    }
    if ( !*((_QWORD *)a1 + 4) )
      goto LABEL_68;
    if ( !v40 )
    {
      v7 = 1;
      break;
    }
    if ( v44 )
    {
      v44 = 0;
      v34 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_SS(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          57,
          (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          (_DWORD)a2,
          *((_QWORD *)a2 + 72));
      }
      v35 = WaitForServiceToStart(v34, a2, v43[0]);
      if ( v35 && v35 != 1053 )
      {
        if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 58, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, v35);
        }
        goto LABEL_68;
      }
    }
    else
    {
LABEL_68:
      Sleep(v9);
      if ( v9 < 0xFA )
      {
        v9 += 50;
        v41 = v9;
      }
    }
  }
  v17 = WPP_GLOBAL_Control;
LABEL_13:
  if ( v38 )
  {
    if ( !v42 )
    {
      if ( v17 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v17 + 28) & 1) != 0 && *((_BYTE *)v17 + 25) >= 4u )
        WPP_SF_SS(
          *((_QWORD *)v17 + 2),
          59,
          (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          (_DWORD)a2,
          *((_QWORD *)a2 + 72));
      goto LABEL_14;
    }
    v23 = v45;
    v24 = 2147489651LL;
    if ( !v45 )
      v24 = 2147489648LL;
    v25 = 2;
    if ( !*((_DWORD *)a2 + 149) )
      v25 = 4;
    NotifyReportEvent(v25, v24, 4, &v38, 1, a2);
    if ( !v23 )
    {
      if ( WPP_GLOBAL_Control != (CUser *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_Sl(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          64,
          (unsigned int)WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids,
          (_DWORD)a2,
          v38);
      }
LABEL_41:
      *v48 = v7;
      goto LABEL_14;
    }
    if ( v7 )
    {
      if ( *((_DWORD *)a2 + 149) )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_45;
        }
        v36 = 60;
      }
      else
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 3u )
        {
          goto LABEL_45;
        }
        v36 = 61;
      }
      WPP_SF_S(*((_QWORD *)v27 + 2), v36, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, a2);
    }
    else
    {
      v27 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CUser *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_45;
      }
      v37 = L"Non-admin";
      if ( v38 != 1753 )
        v37 = L"All";
      WPP_SF_SlS(*((_QWORD *)WPP_GLOBAL_Control + 2), (unsigned int)L"All", v26, (_DWORD)a2, v38, (__int64)v37);
    }
    v27 = WPP_GLOBAL_Control;
LABEL_45:
    if ( *((_DWORD *)a2 + 149) || !v7 )
    {
      v28 = v46;
      v29 = *v46;
      if ( !(_DWORD)v29 || (_DWORD)v29 == 1753 )
      {
        if ( v27 != (CUser *)&WPP_GLOBAL_Control && (*((_BYTE *)v27 + 28) & 1) != 0 && *((_BYTE *)v27 + 25) >= 4u )
          WPP_SF_DD(*((_QWORD *)v27 + 2), 63, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids, v29);
        *v28 = v38;
        *v47 = a2;
      }
    }
    goto LABEL_41;
  }
LABEL_14:
  v18 = (SC_HANDLE)*((_QWORD *)a2 + 73);
  if ( v18 )
  {
    CloseServiceHandle(v18);
    *((_QWORD *)a2 + 73) = 0;
  }
  if ( g_TraceRegHandle && (unsigned __int8)EtwEventEnabled(g_TraceRegHandle, WLEvt_ConnectToSubscriber_Stop) )
  {
    v49 = v6;
    do
      v13 = *((_WORD *)v6 + ++v11) == 0;
    while ( !v13 );
    v50 = 2 * v11 + 2;
    v51 = 0;
    EtwEventWrite(g_TraceRegHandle, WLEvt_ConnectToSubscriber_Stop, 1, &v49);
  }
  return v38;
}

```

## disassembly

```asm
0x140025d50  mov     [rsp-8+arg_10], rbx
0x140025d55  push    rbp
0x140025d56  push    rsi
0x140025d57  push    rdi
0x140025d58  push    r12
0x140025d5a  push    r13
0x140025d5c  push    r14
0x140025d5e  push    r15
0x140025d60  lea     rbp, [rsp-17h]
0x140025d65  sub     rsp, 90h
0x140025d6c  mov     rax, cs:__security_cookie
0x140025d73  xor     rax, rsp
0x140025d76  mov     [rbp+47h+var_38], rax
0x140025d7a  mov     rax, [rbp+47h+arg_20]
0x140025d7e  lea     rsi, dword_1400ABAAC
0x140025d85  xor     r15d, r15d
0x140025d88  mov     [rbp+47h+var_50], rax
0x140025d8c  mov     rax, [rbp+47h+arg_28]
0x140025d90  mov     r12d, 1
0x140025d96  test    rdx, rdx
0x140025d99  mov     [rbp+47h+var_60], r9
0x140025d9d  mov     r13, rcx
0x140025da0  mov     [rbp+47h+var_64], r8d
0x140025da4  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140025dab  cmovnz  rsi, rdx
0x140025daf  mov     [rbp+47h+var_58], rax
0x140025db3  mov     edi, 32h ; '2'
0x140025db8  mov     [rbp+47h+var_90], r15d
0x140025dbc  mov     r14, rdx
0x140025dbf  mov     [rbp+47h+var_80], 0FFFFFFFFh
0x140025dc6  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140025dcd  mov     dword ptr [rbp+47h+TokenHandle], r12d
0x140025dd1  mov     [rbp+47h+var_7C], edi
0x140025dd4  mov     [rbp+47h+var_78], r12d
0x140025dd8  mov     qword ptr [rbp+47h+var_70], 0EA60h
0x140025de0  mov     [rbp+47h+var_68], r12d
0x140025de4  test    rcx, rcx
0x140025de7  jz      short loc_140025E36
0x140025de9  lea     rdx, WLEvt_ConnectToSubscriber_Start
0x140025df0  call    cs:__imp_EtwEventEnabled
0x140025df6  test    al, al
0x140025df8  jz      short loc_140025E36
0x140025dfa  mov     [rbp+47h+var_48], rsi
0x140025dfe  mov     rax, rbx
0x140025e01  cmp     [rsi+rax*2+2], r15w
0x140025e07  lea     rax, [rax+1]
0x140025e0b  jnz     short loc_140025E01
0x140025e0d  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140025e14  lea     eax, ds:2[rax*2]
0x140025e1b  lea     r9, [rbp+47h+var_48]
0x140025e1f  mov     [rbp+47h+var_40], eax
0x140025e22  mov     r8d, r12d
0x140025e25  mov     [rbp+47h+var_3C], r15d
0x140025e29  lea     rdx, WLEvt_ConnectToSubscriber_Start
0x140025e30  call    cs:__imp_EtwEventWrite
0x140025e36  call    cs:__imp_GetTickCount64
0x140025e3c  mov     rcx, [r14+240h]
0x140025e43  lea     rdx, aTrustedinstall; "TrustedInstaller"
0x140025e4a  mov     r15, rax
0x140025e4d  call    cs:__imp__o__wcsicmp
0x140025e53  test    eax, eax
0x140025e55  jz      loc_140026272
0x140025e5b  mov     edx, 0EA60h
0x140025e60  cmp     dword ptr [r14+258h], 0
0x140025e68  lea     r8, WPP_GLOBAL_Control
0x140025e6f  jnz     loc_14002613D
0x140025e75  mov     rcx, r14; lpWideCharStr
0x140025e78  call    ?BuildRpcBinding@@YAKPEAU_NOTIFICATION_COMPONENT@@@Z; BuildRpcBinding(_NOTIFICATION_COMPONENT *)
0x140025e7d  mov     [rbp+47h+var_90], eax
0x140025e80  test    eax, eax
0x140025e82  jnz     loc_140025F35
0x140025e88  mov     rcx, cs:WPP_GLOBAL_Control
0x140025e8f  cmp     [rbp+47h+var_90], 0
0x140025e93  jnz     loc_140025FFF
0x140025e99  mov     rcx, [r14+248h]; hSCObject
0x140025ea0  test    rcx, rcx
0x140025ea3  jnz     loc_140026180
0x140025ea9  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140025eb0  test    rcx, rcx
0x140025eb3  jz      short loc_140025F0B
0x140025eb5  lea     rdx, WLEvt_ConnectToSubscriber_Stop
0x140025ebc  call    cs:__imp_EtwEventEnabled
0x140025ec2  test    al, al
0x140025ec4  jz      short loc_140025F0B
0x140025ec6  mov     [rbp+47h+var_48], rsi
0x140025eca  nop     word ptr [rax+rax+00h]
0x140025ed0  cmp     word ptr [rsi+rbx*2+2], 0
0x140025ed6  lea     rbx, [rbx+1]
0x140025eda  jnz     short loc_140025ED0
0x140025edc  mov     rcx, cs:?g_TraceRegHandle@@3_KA; unsigned __int64 g_TraceRegHandle
0x140025ee3  lea     ebx, ds:2[rbx*2]
0x140025eea  lea     r9, [rbp+47h+var_48]
0x140025eee  mov     [rbp+47h+var_40], ebx
0x140025ef1  mov     r8d, 1
0x140025ef7  mov     [rbp+47h+var_3C], 0
0x140025efe  lea     rdx, WLEvt_ConnectToSubscriber_Stop
0x140025f05  call    cs:__imp_EtwEventWrite
0x140025f0b  mov     eax, [rbp+47h+var_90]
0x140025f0e  mov     rcx, [rbp+47h+var_38]
0x140025f12  xor     rcx, rsp; StackCookie
0x140025f15  call    __security_check_cookie
0x140025f1a  mov     rbx, [rsp+0C0h+arg_10]
0x140025f22  add     rsp, 90h
0x140025f29  pop     r15
0x140025f2b  pop     r14
0x140025f2d  pop     r13
0x140025f2f  pop     r12
0x140025f31  pop     rdi
0x140025f32  pop     rsi
0x140025f33  pop     rbp
0x140025f34  retn
0x140025f35  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f3c  lea     rdx, WPP_GLOBAL_Control
0x140025f43  cmp     rcx, rdx
0x140025f46  jz      short loc_140025F77
0x140025f48  test    byte ptr [rcx+1Ch], 1
0x140025f4c  jz      short loc_140025F77
0x140025f4e  cmp     byte ptr [rcx+19h], 2
0x140025f52  jb      short loc_140025F77
0x140025f54  mov     rcx, [rcx+10h]
0x140025f58  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140025f5f  mov     edx, 38h ; '8'
0x140025f64  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140025f68  mov     r9, r14
0x140025f6b  call    WPP_SF_Sl
0x140025f70  mov     rcx, cs:WPP_GLOBAL_Control
0x140025f77  cmp     [rbp+47h+var_64], 0
0x140025f7b  jz      loc_140025E8F
0x140025f81  xor     r12d, r12d
0x140025f84  cmp     [rbp+47h+var_90], 6D9h
0x140025f8b  mov     dword ptr [rbp+47h+TokenHandle], r12d
0x140025f8f  jnz     loc_140025E8F
0x140025f95  call    cs:__imp_GetTickCount64
0x140025f9b  sub     rax, r15
0x140025f9e  cmp     rax, qword ptr [rbp+47h+var_70]
0x140025fa2  jnb     loc_140025E88
0x140025fa8  cmp     [r13+20h], r12
0x140025fac  jz      loc_14002622B
0x140025fb2  mov     eax, [rbp+47h+var_80]
0x140025fb5  cmp     eax, 0FFFFFFFFh
0x140025fb8  jz      short loc_140025FE0
0x140025fba  cmp     eax, 1
0x140025fbd  jnz     loc_140026248
0x140025fc3  mov     edi, [r14+250h]
0x140025fca  call    cs:__imp_GetTickCount
0x140025fd0  sub     eax, edi
0x140025fd2  mov     edi, [rbp+47h+var_7C]
0x140025fd5  cmp     eax, 1388h
0x140025fda  jbe     loc_140026248
0x140025fe0  lea     r9, [rbp+47h+var_78]; int *
0x140025fe4  mov     rdx, r14; struct _NOTIFICATION_COMPONENT *
0x140025fe7  lea     r8, [rbp+47h+TokenHandle]; int *
0x140025feb  mov     rcx, r13; struct _NOTIFICATION_CLIENT_DEF *
0x140025fee  call    ?IsServiceExpectedToStart@@YAKPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@PEAH2@Z; IsServiceExpectedToStart(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,int *,int *)
0x140025ff3  mov     r12d, dword ptr [rbp+47h+TokenHandle]
0x140025ff7  mov     [rbp+47h+var_80], eax
0x140025ffa  jmp     loc_140026248
0x140025fff  cmp     [rbp+47h+var_78], 0
0x140026003  jz      loc_14002645F
0x140026009  mov     edi, [rbp+47h+var_64]
0x14002600c  lea     r9, [rbp+47h+var_90]
0x140026010  mov     eax, 80001770h
0x140026015  mov     [rsp+0C0h+var_98], r14
0x14002601a  test    edi, edi
0x14002601c  mov     dword ptr [rsp+0C0h+var_A0], 1
0x140026024  mov     edx, 80001773h
0x140026029  mov     r8d, 4
0x14002602f  cmovz   edx, eax
0x140026032  cmp     dword ptr [r14+254h], 0
0x14002603a  mov     eax, 2
0x14002603f  cmovz   ax, r8w
0x140026044  movzx   ecx, ax
0x140026047  call    NotifyReportEvent
0x14002604c  test    edi, edi
0x14002604e  jnz     short loc_140026073
0x140026050  mov     rcx, cs:WPP_GLOBAL_Control
0x140026057  lea     rax, WPP_GLOBAL_Control
0x14002605e  cmp     rcx, rax
0x140026061  jnz     loc_140026105
0x140026067  mov     rax, [rbp+47h+var_50]
0x14002606b  mov     [rax], r12d
0x14002606e  jmp     loc_140025E99
0x140026073  test    r12d, r12d
0x140026076  jz      loc_140026512
0x14002607c  cmp     dword ptr [r14+254h], 0
0x140026084  jnz     loc_1400264AC
0x14002608a  mov     r10, cs:WPP_GLOBAL_Control
0x140026091  lea     rax, WPP_GLOBAL_Control
0x140026098  cmp     r10, rax
0x14002609b  jnz     loc_1400264FA
0x1400260a1  cmp     dword ptr [r14+254h], 0
0x1400260a9  jnz     short loc_1400260B0
0x1400260ab  test    r12d, r12d
0x1400260ae  jnz     short loc_140026067
0x1400260b0  mov     rdi, [rbp+47h+var_60]
0x1400260b4  mov     r9d, [rdi]
0x1400260b7  test    r9d, r9d
0x1400260ba  jz      short loc_1400260C5
0x1400260bc  cmp     r9d, 6D9h
0x1400260c3  jnz     short loc_140026067
0x1400260c5  cmp     r10, rax
0x1400260c8  jz      short loc_1400260F4
0x1400260ca  test    byte ptr [r10+1Ch], 1
0x1400260cf  jz      short loc_1400260F4
0x1400260d1  cmp     byte ptr [r10+19h], 4
0x1400260d6  jb      short loc_1400260F4
0x1400260d8  mov     eax, [rbp+47h+var_90]
0x1400260db  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x1400260e2  mov     rcx, [r10+10h]
0x1400260e6  mov     edx, 3Fh ; '?'
0x1400260eb  mov     dword ptr [rsp+0C0h+var_A0], eax
0x1400260ef  call    WPP_SF_DD
0x1400260f4  mov     eax, [rbp+47h+var_90]
0x1400260f7  mov     [rdi], eax
0x1400260f9  mov     rax, [rbp+47h+var_58]
0x1400260fd  mov     [rax], r14
0x140026100  jmp     loc_140026067
0x140026105  test    byte ptr [rcx+1Ch], 1
0x140026109  jz      loc_140026067
0x14002610f  cmp     byte ptr [rcx+19h], 2
0x140026113  jb      loc_140026067
0x140026119  mov     eax, [rbp+47h+var_90]
0x14002611c  lea     r8, WPP_c4e026e548883477c15208e9f0c6fcb8_Traceguids
0x140026123  mov     rcx, [rcx+10h]
0x140026127  mov     edx, 40h ; '@'
0x14002612c  mov     r9, r14
0x14002612f  mov     dword ptr [rsp+0C0h+var_A0], eax
0x140026133  call    WPP_SF_Sl
0x140026138  jmp     loc_140026067
0x14002613d  mov     rcx, cs:WPP_GLOBAL_Control
0x140026144  cmp     rcx, r8
0x140026147  jnz     loc_1400262A5
0x14002614d  mov     rdi, [r14+240h]
0x140026154  mov     [rbp+47h+TokenHandle], 0
0x14002615c  mov     eax, gs:179Ch
0x140026164  test    eax, eax
0x140026166  jnz     short loc_140026196
0x140026168  mov     r8d, 1
0x14002616e  mov     rcx, rdi; lpServiceName
0x140026171  call    WaitForDesiredService
0x140026176  mov     edi, 32h ; '2'
0x14002617b  jmp     loc_140025E75
0x140026180  call    cs:__imp_CloseServiceHandle
0x140026186  mov     qword ptr [r14+248h], 0
0x140026191  jmp     loc_140025EA9
0x140026196  mov     rcx, cs:WPP_GLOBAL_Control
0x14002619d  cmp     rcx, r8
0x1400261a0  jnz     loc_1400262E5
0x1400261a6  lea     r9, [rbp+47h+TokenHandle]; TokenHandle
0x1400261aa  mov     r8b, 1; OpenAsSelf
0x1400261ad  mov     edx, 0Ch; DesiredAccess
0x1400261b2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x1400261b9  call    cs:__imp_NtOpenThreadToken
0x1400261bf  test    eax, eax
0x1400261c1  jns     short loc_1400261D5
0x1400261c3  mov     ecx, eax; Status
0x1400261c5  call    cs:__imp_RtlNtStatusToDosError
0x1400261cb  mov     edi, 32h ; '2'
0x1400261d0  jmp     loc_140025E75
0x1400261d5  call    cs:__imp_RevertToSelf
0x1400261db  mov     rcx, cs:WPP_GLOBAL_Control
0x1400261e2  lea     rax, WPP_GLOBAL_Control
0x1400261e9  cmp     rcx, rax
0x1400261ec  jnz     loc_140026313
0x1400261f2  mov     r8d, 1
0x1400261f8  mov     edx, [rbp+47h+var_70]
0x1400261fb  mov     rcx, rdi; lpServiceName
0x1400261fe  call    WaitForDesiredService
0x140026203  mov     rdx, [rbp+47h+TokenHandle]; Token
0x140026207  xor     ecx, ecx; Thread
0x140026209  call    cs:__imp_SetThreadToken
0x14002620f  test    eax, eax
0x140026211  jz      loc_140026341
0x140026217  mov     rcx, [rbp+47h+TokenHandle]; hObject
0x14002621b  call    cs:__imp_CloseHandle
0x140026221  mov     edi, 32h ; '2'
0x140026226  jmp     loc_140025E75
0x14002622b  xor     edx, edx; lpDatabaseName
0x14002622d  xor     ecx, ecx; lpMachineName
0x14002622f  mov     r8d, 1; dwDesiredAccess
0x140026235  call    cs:__imp_OpenSCManagerW
0x14002623b  mov     [r13+20h], rax
0x14002623f  test    rax, rax
0x140026242  jnz     loc_140025FB2
0x140026248  cmp     qword ptr [r13+20h], 0
0x14002624d  jnz     loc_14002638F
0x140026253  mov     ecx, edi; dwMilliseconds
0x140026255  call    cs:__imp_Sleep
0x14002625b  cmp     edi, 0FAh
0x140026261  jnb     loc_140025E75
0x140026267  add     edi, 32h ; '2'
0x14002626a  mov     [rbp+47h+var_7C], edi
0x14002626d  jmp     loc_140025E75
0x140026272  lea     r9, [rbp+47h+var_78]; int *
0x140026276  mov     rdx, r14; struct _NOTIFICATION_COMPONENT *
0x140026279  lea     r8, [rbp+47h+TokenHandle]; int *
0x14002627d  mov     rcx, r13; struct _NOTIFICATION_CLIENT_DEF *
0x140026280  call    ?IsServiceExpectedToStart@@YAKPEAU_NOTIFICATION_CLIENT_DEF@@PEAU_NOTIFICATION_COMPONENT@@PEAH2@Z; IsServiceExpectedToStart(_NOTIFICATION_CLIENT_DEF *,_NOTIFICATION_COMPONENT *,int *,int *)
0x140026285  cmp     eax, r12d
0x140026288  mov     [rbp+47h+var_80], eax
  ... truncated ...
```
