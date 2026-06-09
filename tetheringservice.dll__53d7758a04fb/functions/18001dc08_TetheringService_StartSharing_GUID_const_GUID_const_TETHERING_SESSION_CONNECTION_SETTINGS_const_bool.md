# TetheringService::StartSharing(_GUID const *,_GUID const *,_TETHERING_SESSION_CONNECTION_SETTINGS * const,bool)

- ea: `0x18001dc08`
- end: `0x18001e49e`
- name: `?StartSharing@TetheringService@@QEAAJPEBU_GUID@@0QEAU_TETHERING_SESSION_CONNECTION_SETTINGS@@_N@Z`
- size: `2198`
- prototype: `__int64 __usercall@<rax>(TetheringService *__hidden this@<rcx>, const struct _GUID *@<rdx>, const struct _GUID *@<r8>, struct _TETHERING_SESSION_CONNECTION_SETTINGS *const@<r9>, bool)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, authz_impersonation, registry_config, service_task`

## callers

- `0x18000ce60`

## callees

- `0x180002960`
- `0x18000299c`
- `0x180002ffa`
- `0x180003088`
- `0x18000bf4c`
- `0x18000bf74`
- `0x18000ee14`
- `0x180012738`
- `0x180018c00`
- `0x18001aae8`
- `0x18001c0dc`
- `0x18001dc08`
- `0x18001e4a4`
- `0x1800219dc`
- `0x180027130`
- `0x1800272c0`
- `0x180027394`
- `0x180027550`
- `0x180027f34`
- `0x180029d00`
- `0x18002d868`
- `0x180033010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e333`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001e333`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd44`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dd44`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e42d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e300`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e42d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e313`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e313`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001e404`
- `api-ms-win-core-threadpool-l1-2-0!TrySubmitThreadpoolCallback` at `0x18001e404`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e41a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001dd9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e30b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e41a`
- `IPHLPAPI!FreeMibTable` at `0x18001ddad`
- `IPHLPAPI!FreeMibTable` at `0x18001de13`
- `IPHLPAPI!FreeMibTable` at `0x18001ddad`
- `IPHLPAPI!FreeMibTable` at `0x18001de13`
- `IPHLPAPI!GetIfTable2` at `0x18001dde2`
- `IPHLPAPI!GetIfTable2` at `0x18001dde2`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TetheringService::StartSharing(
        TetheringService *this,
        const struct _GUID *a2,
        const struct _GUID *a3,
        struct _GUID *a4,
        bool a5)
{
  struct TetheringSessionTelemetry *v8; // rbx
  bool v9; // si
  WCHAR *v10; // rdi
  signed int started; // r14d
  TetheringServiceTelemetry *v12; // rsi
  TetheringServiceTelemetry *v13; // rcx
  RTL_SRWLOCK *v14; // rbx
  TetheringServiceTelemetry *v15; // rcx
  int Session; // esi
  __int64 v17; // rax
  struct _GUID *v18; // rdx
  TetheringServiceTelemetry *v19; // rcx
  NTSTATUS IfTable2; // eax
  void *v22; // rcx
  __int64 v23; // rdx
  __int64 v24; // r9
  int InterfaceGuidInMibTable; // eax
  __int64 v26; // rcx
  int SimState; // eax
  unsigned __int16 **v28; // rdx
  __int64 v29; // rdx
  int LoggedInUserSID; // eax
  int IsEnabled; // eax
  unsigned int v32; // ebx
  unsigned int v33; // ebx
  unsigned int v34; // ebx
  unsigned int v35; // ebx
  unsigned int v36; // ebx
  struct _GUID *v37; // rsi
  __int64 v38; // rdx
  HLOCAL *Data4; // r15
  const WCHAR *v40; // r12
  DWORD LastError; // ebx
  struct _GUID *v42; // rcx
  signed int v43; // eax
  bool v44; // [rsp+40h] [rbp-91h] BYREF
  bool v45; // [rsp+41h] [rbp-90h] BYREF
  bool v46; // [rsp+42h] [rbp-8Fh] BYREF
  bool v47; // [rsp+43h] [rbp-8Eh] BYREF
  unsigned int v48; // [rsp+44h] [rbp-8Dh] BYREF
  int v49; // [rsp+48h] [rbp-89h]
  int v50; // [rsp+4Ch] [rbp-85h]
  PCNZWCH sourceString; // [rsp+50h] [rbp-81h] BYREF
  PVOID Memory; // [rsp+58h] [rbp-79h] BYREF
  struct _GUID *v53; // [rsp+60h] [rbp-71h]
  PMIB_IF_TABLE2 Table[2]; // [rsp+70h] [rbp-61h] BYREF
  char v55; // [rsp+80h] [rbp-51h]
  _BYTE v56[72]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v57; // [rsp+D8h] [rbp+7h]
  struct TetheringSessionTelemetry *v58; // [rsp+130h] [rbp+5Fh] BYREF

  v58 = this;
  v8 = this;
  v9 = a5;
  if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
  {
    WPP_SF_L_guid__guid_l(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (_DWORD)a2,
      (_DWORD)a3,
      *((_DWORD *)this + 56),
      (__int64)a2,
      (__int64)a3);
  }
  LODWORD(v53) = *((_DWORD *)v8 + 56);
  Memory = 0;
  v49 = 0;
  v50 = 0;
  v10 = 0;
  sourceString = 0;
  TetheringService::ResetInactivityTimerIfNotSharing(v8);
  v44 = 0;
  started = IsTetheringGPAllowedInternal(&v44);
  if ( started < 0 )
    goto LABEL_7;
  if ( v44 )
  {
    Table[0] = (PMIB_IF_TABLE2)&Memory;
    Table[1] = 0;
    v55 = 1;
    IfTable2 = GetIfTable2(&Table[1]);
    started = IfTable2;
    if ( IfTable2 > 0 )
      started = (unsigned __int16)IfTable2 | 0x80070000;
    if ( v55 )
    {
      v22 = *(void **)Table[0];
      *(_QWORD *)Table[0] = Table[1];
      if ( v22 )
        FreeMibTable(v22);
    }
    if ( started < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_8;
      }
      v23 = 145;
LABEL_35:
      v24 = (unsigned int)started;
LABEL_36:
      WPP_SF_d(*((_QWORD *)v12 + 2), v23, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v24);
LABEL_37:
      v12 = WPP_GLOBAL_Control;
      goto LABEL_8;
    }
    v48 = 0;
    InterfaceGuidInMibTable = InterfaceMgr::FindInterfaceGuidInMibTable((struct _MIB_IF_TABLE2 *)Memory, a2, &v48);
    started = InterfaceGuidInMibTable;
    if ( InterfaceGuidInMibTable < 0 )
    {
      v12 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        goto LABEL_8;
      }
      v23 = 146;
      goto LABEL_42;
    }
    v26 = (__int64)Memory;
    v49 = *((_DWORD *)Memory + 338 * v48 + 287);
    if ( *(_QWORD *)&a3->Data1 == *(_QWORD *)&GUID_NULL.Data1 && *(_QWORD *)a3->Data4 == *(_QWORD *)GUID_NULL.Data4 )
    {
      v50 = 10;
    }
    else
    {
      v48 = 0;
      InterfaceGuidInMibTable = InterfaceMgr::FindInterfaceGuidInMibTable((struct _MIB_IF_TABLE2 *)Memory, a3, &v48);
      started = InterfaceGuidInMibTable;
      if ( InterfaceGuidInMibTable < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_8;
        }
        v23 = 147;
LABEL_42:
        v24 = (unsigned int)InterfaceGuidInMibTable;
        goto LABEL_36;
      }
      v26 = 1352LL * v48;
      v50 = *(_DWORD *)((char *)Memory + v26 + 1148);
    }
    if ( v49 == 8 )
    {
      v44 = 0;
      v45 = 0;
      v46 = 0;
      v47 = 0;
      SimState = TetheringService::GetSimState((TetheringService *)v26, a2, &v44, &v45, &v46, &v47);
      if ( SimState < 0 )
      {
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            152,
            &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
            (unsigned int)SimState);
        }
      }
      else
      {
        if ( v44 )
        {
          started = -2095972335;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_8;
          }
          v29 = 148;
          goto LABEL_57;
        }
        if ( !v45 )
        {
          started = -2095972333;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_8;
          }
          v29 = 149;
          goto LABEL_57;
        }
        if ( !v46 )
        {
          started = -2095972332;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_8;
          }
          v29 = 150;
          goto LABEL_57;
        }
        if ( !v47 )
        {
          started = -2095972334;
          v12 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
            goto LABEL_8;
          }
          v29 = 151;
LABEL_57:
          WPP_SF_(*((_QWORD *)v12 + 2), v29, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids);
          goto LABEL_37;
        }
      }
      sourceString = 0;
      LoggedInUserSID = Windows::Internal::Tethering::GetLoggedInUserSID(
                          (Windows::Internal::Tethering *)&sourceString,
                          v28);
      started = LoggedInUserSID;
      if ( LoggedInUserSID < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          v10 = (WCHAR *)sourceString;
          goto LABEL_8;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          153,
          &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
          (unsigned int)LoggedInUserSID);
        v10 = (WCHAR *)sourceString;
        goto LABEL_7;
      }
      v48 = 0;
      *(struct _GUID *)Table = *a2;
      v10 = (WCHAR *)sourceString;
      IsEnabled = TetheringIsEnabled(sourceString, (struct _GUID *)Table, (enum _TETHERING_ENABLEMENT_TYPE *)&v48);
      started = IsEnabled;
      if ( IsEnabled < 0 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_8;
        }
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          154,
          &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids,
          (unsigned int)IsEnabled);
        goto LABEL_7;
      }
      v32 = v48;
      if ( v48 != 1 )
      {
        v12 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, v48);
          v12 = WPP_GLOBAL_Control;
        }
        v33 = v32 - 2;
        if ( v33 )
        {
          v34 = v33 - 1;
          if ( v34 )
          {
            v35 = v34 - 1;
            if ( v35 )
            {
              v36 = v35 - 1;
              if ( v36 )
              {
                if ( v36 == 1 )
                  started = -2095972329;
                else
                  started = -2095972342;
              }
              else
              {
                started = -2095972336;
              }
            }
            else
            {
              started = -2095972340;
            }
          }
          else
          {
            started = -2095972339;
          }
        }
        else
        {
          started = -2095972348;
        }
        goto LABEL_8;
      }
      v8 = v58;
    }
    if ( TetheringService::NeedToChangeState(v26, (int)v53, 2) )
    {
      if ( v9 )
      {
        v37 = (struct _GUID *)operator new(0x100u, (const struct std::nothrow_t *)&std::nothrow);
        v53 = v37;
        if ( !v37 )
        {
          started = -2147024882;
          goto LABEL_7;
        }
        *(unsigned __int16 *)((char *)&v37[15].Data2 + 1) = 0;
        HIBYTE(v37[15].Data3) = 0;
        memset_0(v37, 0, 0xF8u);
        *(_QWORD *)v37[15].Data4 = 0;
        *v37 = *a2;
        v37[1] = *a3;
        LOBYTE(v37[15].Data2) = 0;
        Data4 = (HLOCAL *)v37[15].Data4;
        v40 = *(const WCHAR **)v37[15].Data4;
        *(_QWORD *)v37[15].Data4 = 0;
        if ( v37[15].Data4 != (unsigned __int8 *)&sourceString )
        {
          *Data4 = v10;
          v10 = 0;
        }
        if ( v10 )
        {
          LastError = GetLastError();
          LocalFree(v10);
          SetLastError(LastError);
        }
        v10 = (WCHAR *)v40;
        sourceString = v40;
        if ( a4 )
        {
          v42 = v37 + 2;
          if ( v37 == (struct _GUID *)-32LL )
          {
            *(_DWORD *)_o__errno(v42, v38) = 22;
            invalid_parameter_noinfo();
          }
          else
          {
            *v42 = *a4;
            v37[3] = a4[1];
            v37[4] = a4[2];
            v37[5] = a4[3];
            v37[6] = a4[4];
            v37[7] = a4[5];
            v37[8] = a4[6];
            v37[9] = a4[7];
            v37[10] = a4[8];
            v37[11] = a4[9];
            v37[12] = a4[10];
            v37[13] = a4[11];
            v37[14] = a4[12];
            v37[15].Data1 = a4[13].Data1;
          }
          LOBYTE(v37[15].Data2) = 1;
        }
        if ( !TrySubmitThreadpoolCallback(
                TetheringService::StartSharingWorkerProc,
                v37,
                (PTP_CALLBACK_ENVIRON)((char *)v58 + 1808)) )
        {
          if ( *Data4 )
            LocalFree(*Data4);
          operator delete(v37);
          v43 = GetLastError();
          started = v43;
          if ( v43 > 0 )
            started = (unsigned __int16)v43 | 0x80070000;
          goto LABEL_7;
        }
      }
      else
      {
        started = TetheringService::StartSharingInternal(
                    v8,
                    a2,
                    a3,
                    (struct _TETHERING_SESSION_CONNECTION_SETTINGS *const)a4,
                    1u,
                    v10);
      }
      v12 = WPP_GLOBAL_Control;
      goto LABEL_18;
    }
    if ( !a4 )
      goto LABEL_7;
    started = -2095972328;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (TetheringServiceTelemetry *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
    {
      goto LABEL_8;
    }
    v23 = 156;
    goto LABEL_35;
  }
  started = -2095972348;
LABEL_7:
  v12 = WPP_GLOBAL_Control;
LABEL_8:
  memset_0(v56, 0, 0x50u);
  v14 = 0;
  v58 = 0;
  if ( *(_QWORD *)&g_pTetheringSessionId.Data1 )
  {
    Session = TetheringServiceTelemetry::GetSession(v13, *(struct _GUID **)&g_pTetheringSessionId.Data1, &v58);
    v14 = (RTL_SRWLOCK *)v58;
    if ( (Session < 0 || v58 && TetheringSessionTelemetry::Initialized((RTL_SRWLOCK *)v58)) && Session >= 0 )
    {
      if ( !v14 )
        ATL::AtlThrowImpl(-2147467259);
      TetheringServiceTelemetry::AcquireSessionData(v15, v14, (struct TetheringServiceTelemetry::SESSION_DATA *)v56);
      v17 = v57;
      *(_DWORD *)(v57 + 92) = v49;
      *(_DWORD *)(v17 + 96) = v50;
      *(_DWORD *)(v17 + 28) = started;
      ReleaseSRWLockExclusive(v14 + 2);
      TetheringServiceTelemetry::StopSession(v19, v18);
    }
    v12 = WPP_GLOBAL_Control;
  }
  if ( v14 )
  {
    (*((void (__fastcall **)(RTL_SRWLOCK *))v14->Ptr + 2))(v14);
    v12 = WPP_GLOBAL_Control;
  }
LABEL_18:
  if ( v12 != (TetheringServiceTelemetry *)&WPP_GLOBAL_Control && (*((_BYTE *)v12 + 28) & 8) != 0 )
    WPP_SF_d(*((_QWORD *)v12 + 2), 157, &WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids, (unsigned int)started);
  if ( v10 )
    LocalFree(v10);
  if ( Memory )
    FreeMibTable(Memory);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x18001dc08  mov     [rsp-8+arg_0], rcx
0x18001dc0d  push    rbp
0x18001dc0e  push    rbx
0x18001dc0f  push    rsi
0x18001dc10  push    rdi
0x18001dc11  push    r12
0x18001dc13  push    r13
0x18001dc15  push    r14
0x18001dc17  push    r15
0x18001dc19  lea     rbp, [rsp-17h]
0x18001dc1e  sub     rsp, 0E8h
0x18001dc25  mov     r13, r9
0x18001dc28  mov     r12, r8
0x18001dc2b  mov     r15, rdx
0x18001dc2e  mov     rbx, rcx
0x18001dc31  xor     r14d, r14d
0x18001dc34  lea     rax, WPP_GLOBAL_Control
0x18001dc3b  movzx   esi, [rbp+4Fh+arg_20]
0x18001dc3f  mov     rcx, cs:WPP_GLOBAL_Control
0x18001dc46  cmp     rcx, rax
0x18001dc49  jz      short loc_18001DC6F
0x18001dc4b  test    byte ptr [rcx+1Ch], 8
0x18001dc4f  jz      short loc_18001DC6F
0x18001dc51  mov     rcx, [rcx+10h]
0x18001dc55  mov     [rsp+120h+var_F0], esi
0x18001dc59  mov     [rsp+120h+var_F8], r8
0x18001dc5e  mov     [rsp+120h+var_100], rdx
0x18001dc63  mov     r9d, [rbx+0E0h]
0x18001dc6a  call    WPP_SF_L_guid__guid_l
0x18001dc6f  mov     eax, [rbx+0E0h]
0x18001dc75  mov     dword ptr [rbp+4Fh+var_C0], eax
0x18001dc78  mov     [rbp+4Fh+Memory], r14
0x18001dc7c  mov     [rsp+120h+var_D8], r14d
0x18001dc81  mov     [rsp+120h+var_D4], r14d
0x18001dc86  mov     rdi, r14
0x18001dc89  mov     [rsp+120h+sourceString], r14
0x18001dc8e  mov     rcx, rbx; this
0x18001dc91  call    ?ResetInactivityTimerIfNotSharing@TetheringService@@AEAAXXZ; TetheringService::ResetInactivityTimerIfNotSharing(void)
0x18001dc96  mov     [rsp+120h+var_E0], r14b
0x18001dc9b  lea     rcx, [rsp+120h+var_E0]; bool *
0x18001dca0  call    ?IsTetheringGPAllowedInternal@@YAJPEA_N@Z; IsTetheringGPAllowedInternal(bool *)
0x18001dca5  mov     r14d, eax
0x18001dca8  test    eax, eax
0x18001dcaa  js      short loc_18001DCBD
0x18001dcac  cmp     [rsp+120h+var_E0], 0
0x18001dcb1  jnz     loc_18001DDCA
0x18001dcb7  mov     r14d, 83120004h
0x18001dcbd  mov     rsi, cs:WPP_GLOBAL_Control
0x18001dcc4  lea     r15, WPP_GLOBAL_Control
0x18001dccb  xor     edx, edx; Val
0x18001dccd  lea     r8d, [rdx+50h]; Size
0x18001dcd1  lea     rcx, [rbp+4Fh+var_90]; void *
0x18001dcd5  call    memset_0
0x18001dcda  nop
0x18001dcdb  xor     ebx, ebx
0x18001dcdd  mov     [rbp+4Fh+arg_0], rbx
0x18001dce1  mov     rdx, qword ptr cs:?g_pTetheringSessionId@@3PEAU_GUID@@EA.Data1; struct _GUID *
0x18001dce8  test    rdx, rdx
0x18001dceb  jz      short loc_18001DD56
0x18001dced  lea     r8, [rbp+4Fh+arg_0]; struct TetheringSessionTelemetry **
0x18001dcf1  call    ?GetSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@PEAPEAVTetheringSessionTelemetry@@@Z; TetheringServiceTelemetry::GetSession(_GUID *,TetheringSessionTelemetry * *)
0x18001dcf6  mov     esi, eax
0x18001dcf8  mov     rbx, [rbp+4Fh+arg_0]
0x18001dcfc  test    eax, eax
0x18001dcfe  js      short loc_18001DD11
0x18001dd00  test    rbx, rbx
0x18001dd03  jz      short loc_18001DD4F
0x18001dd05  mov     rcx, rbx; this
0x18001dd08  call    ?Initialized@TetheringSessionTelemetry@@QEAAHXZ; TetheringSessionTelemetry::Initialized(void)
0x18001dd0d  test    eax, eax
0x18001dd0f  jz      short loc_18001DD4F
0x18001dd11  test    esi, esi
0x18001dd13  js      short loc_18001DD4F
0x18001dd15  test    rbx, rbx
0x18001dd18  jz      loc_18001E493
0x18001dd1e  lea     r8, [rbp+4Fh+var_90]; struct TetheringServiceTelemetry::SESSION_DATA *
0x18001dd22  mov     rdx, rbx; struct TetheringSessionTelemetry *
0x18001dd25  call    ?AcquireSessionData@TetheringServiceTelemetry@@QEAAXAEAVTetheringSessionTelemetry@@AEAUSESSION_DATA@1@@Z; TetheringServiceTelemetry::AcquireSessionData(TetheringSessionTelemetry &,TetheringServiceTelemetry::SESSION_DATA &)
0x18001dd2a  mov     rax, [rbp+4Fh+var_48]
0x18001dd2e  mov     ecx, [rsp+120h+var_D8]
0x18001dd32  mov     [rax+5Ch], ecx
0x18001dd35  mov     ecx, [rsp+120h+var_D4]
0x18001dd39  mov     [rax+60h], ecx
0x18001dd3c  mov     [rax+1Ch], r14d
0x18001dd40  lea     rcx, [rbx+10h]; SRWLock
0x18001dd44  call    cs:__imp_ReleaseSRWLockExclusive
0x18001dd4a  call    ?StopSession@TetheringServiceTelemetry@@QEAAJPEAU_GUID@@@Z; TetheringServiceTelemetry::StopSession(_GUID *)
0x18001dd4f  mov     rsi, cs:WPP_GLOBAL_Control
0x18001dd56  test    rbx, rbx
0x18001dd59  jz      short loc_18001DD71
0x18001dd5b  mov     rax, [rbx]
0x18001dd5e  mov     rcx, rbx
0x18001dd61  mov     rax, [rax+10h]
0x18001dd65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dd6a  mov     rsi, cs:WPP_GLOBAL_Control
0x18001dd71  cmp     rsi, r15
0x18001dd74  jz      short loc_18001DD95
0x18001dd76  test    byte ptr [rsi+1Ch], 8
0x18001dd7a  jz      short loc_18001DD95
0x18001dd7c  mov     edx, 9Dh
0x18001dd81  mov     r9d, r14d
0x18001dd84  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001dd8b  mov     rcx, [rsi+10h]
0x18001dd8f  call    WPP_SF_d
0x18001dd94  nop
0x18001dd95  test    rdi, rdi
0x18001dd98  jz      short loc_18001DDA4
0x18001dd9a  mov     rcx, rdi; hMem
0x18001dd9d  call    cs:__imp_LocalFree
0x18001dda3  nop
0x18001dda4  mov     rcx, [rbp+4Fh+Memory]; Memory
0x18001dda8  test    rcx, rcx
0x18001ddab  jz      short loc_18001DDB3
0x18001ddad  call    cs:__imp_FreeMibTable
0x18001ddb3  mov     eax, r14d
0x18001ddb6  add     rsp, 0E8h
0x18001ddbd  pop     r15
0x18001ddbf  pop     r14
0x18001ddc1  pop     r13
0x18001ddc3  pop     r12
0x18001ddc5  pop     rdi
0x18001ddc6  pop     rsi
0x18001ddc7  pop     rbx
0x18001ddc8  pop     rbp
0x18001ddc9  retn
0x18001ddca  lea     rax, [rbp+4Fh+Memory]
0x18001ddce  mov     [rbp+4Fh+Table], rax
0x18001ddd2  mov     [rbp+4Fh+Table+8], 0
0x18001ddda  mov     [rbp+4Fh+var_A0], 1
0x18001ddde  lea     rcx, [rbp+4Fh+Table+8]; Table
0x18001dde2  call    cs:__imp_GetIfTable2
0x18001dde8  mov     r14d, eax
0x18001ddeb  test    eax, eax
0x18001dded  jle     short loc_18001DDFA
0x18001ddef  movzx   r14d, ax
0x18001ddf3  or      r14d, 80070000h
0x18001ddfa  cmp     [rbp+4Fh+var_A0], 0
0x18001ddfe  jz      short loc_18001DE19
0x18001de00  mov     rdx, [rbp+4Fh+Table]
0x18001de04  mov     rcx, [rdx]; Memory
0x18001de07  mov     rax, [rbp+4Fh+Table+8]
0x18001de0b  mov     [rdx], rax
0x18001de0e  test    rcx, rcx
0x18001de11  jz      short loc_18001DE19
0x18001de13  call    cs:__imp_FreeMibTable
0x18001de19  test    r14d, r14d
0x18001de1c  jns     short loc_18001DE63
0x18001de1e  mov     rsi, cs:WPP_GLOBAL_Control
0x18001de25  lea     r15, WPP_GLOBAL_Control
0x18001de2c  cmp     rsi, r15
0x18001de2f  jz      loc_18001DCCB
0x18001de35  test    byte ptr [rsi+1Ch], 1
0x18001de39  jz      loc_18001DCCB
0x18001de3f  mov     edx, 91h
0x18001de44  mov     r9d, r14d
0x18001de47  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001de4e  mov     rcx, [rsi+10h]
0x18001de52  call    WPP_SF_d
0x18001de57  mov     rsi, cs:WPP_GLOBAL_Control
0x18001de5e  jmp     loc_18001DCCB
0x18001de63  mov     [rsp+120h+var_DC], 0
0x18001de6b  lea     r8, [rsp+120h+var_DC]; unsigned int *
0x18001de70  mov     rdx, r15; struct _GUID *
0x18001de73  mov     rcx, [rbp+4Fh+Memory]; struct _MIB_IF_TABLE2 *
0x18001de77  call    ?FindInterfaceGuidInMibTable@InterfaceMgr@@SAJPEAU_MIB_IF_TABLE2@@PEBU_GUID@@PEAK@Z; InterfaceMgr::FindInterfaceGuidInMibTable(_MIB_IF_TABLE2 *,_GUID const *,ulong *)
0x18001de7c  mov     r14d, eax
0x18001de7f  test    eax, eax
0x18001de81  jns     short loc_18001DEAE
0x18001de83  mov     rsi, cs:WPP_GLOBAL_Control
0x18001de8a  lea     r15, WPP_GLOBAL_Control
0x18001de91  cmp     rsi, r15
0x18001de94  jz      loc_18001DCCB
0x18001de9a  test    byte ptr [rsi+1Ch], 1
0x18001de9e  jz      loc_18001DCCB
0x18001dea4  mov     edx, 92h
0x18001dea9  mov     r9d, eax
0x18001deac  jmp     short loc_18001DE47
0x18001deae  mov     eax, [rsp+120h+var_DC]
0x18001deb2  imul    rdx, rax, 548h
0x18001deb9  mov     rcx, [rbp+4Fh+Memory]; struct _MIB_IF_TABLE2 *
0x18001debd  mov     eax, [rdx+rcx+47Ch]
0x18001dec4  mov     [rsp+120h+var_D8], eax
0x18001dec8  mov     rax, [r12]
0x18001decc  cmp     rax, qword ptr cs:GUID_NULL.Data1
0x18001ded3  jnz     short loc_18001DEED
0x18001ded5  mov     rax, [r12+8]
0x18001deda  cmp     rax, qword ptr cs:GUID_NULL.Data4
0x18001dee1  jnz     short loc_18001DEED
0x18001dee3  mov     [rsp+120h+var_D4], 0Ah
0x18001deeb  jmp     short loc_18001DF4E
0x18001deed  mov     [rsp+120h+var_DC], 0
0x18001def5  lea     r8, [rsp+120h+var_DC]; unsigned int *
0x18001defa  mov     rdx, r12; struct _GUID *
0x18001defd  call    ?FindInterfaceGuidInMibTable@InterfaceMgr@@SAJPEAU_MIB_IF_TABLE2@@PEBU_GUID@@PEAK@Z; InterfaceMgr::FindInterfaceGuidInMibTable(_MIB_IF_TABLE2 *,_GUID const *,ulong *)
0x18001df02  mov     r14d, eax
0x18001df05  test    eax, eax
0x18001df07  jns     short loc_18001DF34
0x18001df09  mov     rsi, cs:WPP_GLOBAL_Control
0x18001df10  lea     r15, WPP_GLOBAL_Control
0x18001df17  cmp     rsi, r15
0x18001df1a  jz      loc_18001DCCB
0x18001df20  test    byte ptr [rsi+1Ch], 1
0x18001df24  jz      loc_18001DCCB
0x18001df2a  mov     edx, 93h
0x18001df2f  jmp     loc_18001DEA9
0x18001df34  mov     eax, [rsp+120h+var_DC]
0x18001df38  imul    rcx, rax, 548h; this
0x18001df3f  mov     rax, [rbp+4Fh+Memory]
0x18001df43  mov     eax, [rcx+rax+47Ch]
0x18001df4a  mov     [rsp+120h+var_D4], eax
0x18001df4e  cmp     [rsp+120h+var_D8], 8
0x18001df53  jnz     loc_18001E21F
0x18001df59  xor     r14d, r14d
0x18001df5c  mov     [rsp+120h+var_E0], r14b
0x18001df61  mov     [rsp+120h+var_DF], r14b
0x18001df66  mov     [rsp+120h+var_DE], r14b
0x18001df6b  mov     [rsp+120h+var_DD], r14b
0x18001df70  lea     rax, [rsp+120h+var_DD]
0x18001df75  mov     [rsp+120h+var_F8], rax; bool *
0x18001df7a  lea     rax, [rsp+120h+var_DE]
0x18001df7f  mov     [rsp+120h+var_100], rax; bool *
0x18001df84  lea     r9, [rsp+120h+var_DF]; bool *
0x18001df89  lea     r8, [rsp+120h+var_E0]; bool *
0x18001df8e  mov     rdx, r15; struct _GUID *
0x18001df91  call    ?GetSimState@TetheringService@@AEAAJPEBU_GUID@@PEA_N111@Z; TetheringService::GetSimState(_GUID const *,bool *,bool *,bool *,bool *)
0x18001df96  test    eax, eax
0x18001df98  js      loc_18001E088
0x18001df9e  cmp     [rsp+120h+var_E0], r14b
0x18001dfa3  jz      short loc_18001DFE6
0x18001dfa5  mov     r14d, 83120011h
0x18001dfab  mov     rsi, cs:WPP_GLOBAL_Control
0x18001dfb2  lea     r15, WPP_GLOBAL_Control
0x18001dfb9  cmp     rsi, r15
0x18001dfbc  jz      loc_18001DCCB
0x18001dfc2  test    byte ptr [rsi+1Ch], 1
0x18001dfc6  jz      loc_18001DCCB
0x18001dfcc  mov     edx, 94h
0x18001dfd1  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001dfd8  mov     rcx, [rsi+10h]
0x18001dfdc  call    WPP_SF_
0x18001dfe1  jmp     loc_18001DE57
0x18001dfe6  cmp     [rsp+120h+var_DF], r14b
0x18001dfeb  jnz     short loc_18001E01B
0x18001dfed  mov     r14d, 83120013h
0x18001dff3  mov     rsi, cs:WPP_GLOBAL_Control
0x18001dffa  lea     r15, WPP_GLOBAL_Control
0x18001e001  cmp     rsi, r15
0x18001e004  jz      loc_18001DCCB
0x18001e00a  test    byte ptr [rsi+1Ch], 1
0x18001e00e  jz      loc_18001DCCB
0x18001e014  mov     edx, 95h
0x18001e019  jmp     short loc_18001DFD1
0x18001e01b  cmp     [rsp+120h+var_DE], r14b
0x18001e020  jnz     short loc_18001E050
0x18001e022  mov     r14d, 83120014h
0x18001e028  mov     rsi, cs:WPP_GLOBAL_Control
0x18001e02f  lea     r15, WPP_GLOBAL_Control
0x18001e036  cmp     rsi, r15
0x18001e039  jz      loc_18001DCCB
0x18001e03f  test    byte ptr [rsi+1Ch], 1
0x18001e043  jz      loc_18001DCCB
0x18001e049  mov     edx, 96h
0x18001e04e  jmp     short loc_18001DFD1
0x18001e050  cmp     [rsp+120h+var_DD], r14b
0x18001e055  jnz     short loc_18001E0BB
0x18001e057  mov     r14d, 83120012h
0x18001e05d  mov     rsi, cs:WPP_GLOBAL_Control
0x18001e064  lea     r15, WPP_GLOBAL_Control
0x18001e06b  cmp     rsi, r15
0x18001e06e  jz      loc_18001DCCB
0x18001e074  test    byte ptr [rsi+1Ch], 1
0x18001e078  jz      loc_18001DCCB
0x18001e07e  mov     edx, 97h
0x18001e083  jmp     loc_18001DFD1
0x18001e088  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e08f  lea     rbx, WPP_GLOBAL_Control
0x18001e096  cmp     rcx, rbx
0x18001e099  jz      short loc_18001E0C2
0x18001e09b  test    byte ptr [rcx+1Ch], 2
0x18001e09f  jz      short loc_18001E0C2
0x18001e0a1  mov     edx, 98h
0x18001e0a6  mov     r9d, eax
0x18001e0a9  lea     r8, WPP_ad96878468d9324e80184c9fc08cbc2e_Traceguids
0x18001e0b0  mov     rcx, [rcx+10h]
0x18001e0b4  call    WPP_SF_d
0x18001e0b9  jmp     short loc_18001E0C2
0x18001e0bb  lea     rbx, WPP_GLOBAL_Control
0x18001e0c2  mov     [rsp+120h+sourceString], r14
0x18001e0c7  lea     rcx, [rsp+120h+sourceString]; this
0x18001e0cc  call    ?GetLoggedInUserSID@Tethering@Internal@Windows@@YAJPEAPEAG@Z; Windows::Internal::Tethering::GetLoggedInUserSID(ushort * *)
0x18001e0d1  mov     r14d, eax
0x18001e0d4  test    eax, eax
0x18001e0d6  jns     short loc_18001E116
0x18001e0d8  mov     rsi, cs:WPP_GLOBAL_Control
0x18001e0df  cmp     rsi, rbx
0x18001e0e2  jz      short loc_18001E10C
0x18001e0e4  test    byte ptr [rsi+1Ch], 1
0x18001e0e8  jz      short loc_18001E10C
0x18001e0ea  mov     edx, 99h
0x18001e0ef  mov     r9d, eax
  ... truncated ...
```
