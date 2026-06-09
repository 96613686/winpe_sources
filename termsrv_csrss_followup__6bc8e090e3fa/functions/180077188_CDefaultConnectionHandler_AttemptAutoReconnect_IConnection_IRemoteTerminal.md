# CDefaultConnectionHandler::AttemptAutoReconnect(IConnection *,IRemoteTerminal *)

- ea: `0x180077188`
- end: `0x180077a6d`
- name: `?AttemptAutoReconnect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `2277`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *__hidden this, struct IConnection *, struct IRemoteTerminal *)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800799f0`

## callees

- `0x180001398`
- `0x1800016a8`
- `0x180002280`
- `0x180003604`
- `0x180009940`
- `0x18000c2a0`
- `0x180012c90`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x180015310`
- `0x180033f60`
- `0x180034e64`
- `0x180051e44`
- `0x180052b58`
- `0x180077188`
- `0x18007d43c`
- `0x18007d63c`
- `0x18007d734`
- `0x18007dc24`
- `0x1800caed0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077487`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180077487`

## string_xrefs

- `0x1800778cc`: `Task completed successfully`
- `0x180077211`: `Attempting auto reconnect...`
- `0x1800771fe`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x1800776ac`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x180077887`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x180077291`: `AttemptAutoReconnect`
- `0x180077350`: `AttemptAutoReconnect`
- `0x18007739d`: `AttemptAutoReconnect`
- `0x180077407`: `AttemptAutoReconnect`
- `0x1800776d1`: `AttemptAutoReconnect`
- `0x180077718`: `AttemptAutoReconnect`
- `0x180077824`: `AttemptAutoReconnect`
- `0x180077631`: `RDP protocol failed to reset new last input time`
- `0x180077744`: `Attempting to serialize auto reconnect`
- `0x1800777a2`: `Autoreconnect incoming connection to session`
- `0x1800777df`: `Autoreconnect incoming connection failed, probably because of lack of licenses. Return proper error`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CDefaultConnectionHandler::AttemptAutoReconnect(
        CDefaultConnectionHandler *this,
        struct IConnection *a2,
        struct IRemoteTerminal *a3,
        int a4)
{
  int v6; // eax
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int SessionList; // ebx
  unsigned int v11; // edi
  int v12; // esi
  const char *v13; // rax
  char *v14; // rdx
  unsigned int v15; // edx
  unsigned __int64 v16; // rsi
  unsigned __int64 v17; // rbx
  const char *v18; // r13
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rcx
  char *v23; // rax
  int v24; // eax
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  const char *v30; // rax
  __int64 *v31; // rdx
  const char *v32; // rax
  __int16 *v33; // rdx
  int v34; // ecx
  int v35; // r8d
  int v36; // r9d
  __int64 v37; // rdx
  unsigned int v39[2]; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int v40; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  unsigned __int64 v42; // [rsp+68h] [rbp-98h] BYREF
  const char *v43; // [rsp+70h] [rbp-90h] BYREF
  struct ITSSession *v44; // [rsp+78h] [rbp-88h] BYREF
  const char *v45; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v46; // [rsp+88h] [rbp-78h] BYREF
  struct IRemoteConnectionManager *v47; // [rsp+90h] [rbp-70h] BYREF
  __int64 v48; // [rsp+98h] [rbp-68h] BYREF
  struct ISessionList *v49; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v50; // [rsp+A8h] [rbp-58h] BYREF
  __int128 Buf2; // [rsp+B8h] [rbp-48h] BYREF
  struct _GUID v52; // [rsp+C8h] [rbp-38h] BYREF
  _BYTE v53[124]; // [rsp+E0h] [rbp-20h] BYREF
  int v54; // [rsp+15Ch] [rbp+5Ch]
  char v55; // [rsp+1B2h] [rbp+B2h] BYREF
  unsigned __int16 v56[40]; // [rsp+B50h] [rbp+A50h] BYREF

  v40 = 0;
  v44 = 0;
  v49 = 0;
  v52 = 0;
  v39[0] = 0;
  v48 = 0;
  v47 = 0;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v42 = (unsigned __int64)"Attempting auto reconnect...";
    SystemTimeAsFileTime = (struct _FILETIME)"CDefaultConnectionHandler::AttemptAutoReconnect";
    v43 = "Auto Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"Auto Reconnect",
      (unsigned int)&word_1801131A6,
      (_DWORD)a3,
      a4,
      (__int64)&v43,
      (__int64)&SystemTimeAsFileTime,
      (__int64)&v42);
  }
  v6 = (*(__int64 (__fastcall **)(struct IRemoteTerminal *, unsigned int *))(*(_QWORD *)a3 + 376LL))(a3, &v40);
  SessionList = v6;
  v11 = 1;
  if ( v6 < 0 && (v12 = 0, v6 != -2147023652) || (v12 = 1, v6 < 0) )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
    {
LABEL_62:
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_69;
      *(_QWORD *)&v50 = "CDefaultConnectionHandler::AttemptAutoReconnect";
      v32 = "Auto Reconnect";
      v33 = &word_180112E46;
      goto LABEL_68;
    }
    v43 = "AttemptAutoReconnect";
    v13 = "AuthenticateClientToSession";
    v14 = byte_180113169;
LABEL_8:
    v42 = (unsigned __int64)v13;
    SystemTimeAsFileTime = (struct _FILETIME)"Warning HResult failed";
    v39[0] = SessionList;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      v7,
      (_DWORD)v14,
      v8,
      v9,
      (__int64)&SystemTimeAsFileTime,
      (__int64)&v42,
      (__int64)v39,
      (__int64)&v43);
    goto LABEL_62;
  }
  v46 = 0;
  SystemTimeAsFileTime.dwLowDateTime = 0;
  if ( (*(int (__fastcall **)(struct IConnection *, struct _GUID *))(*(_QWORD *)a2 + 368LL))(a2, &v52) < 0 )
    v52 = 0;
  CUtils::ConvertUuidToString(&v52, v15, v56);
  SessionList = CHelper::GetSessionList(&v49);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_62;
    v43 = "AttemptAutoReconnect";
    v13 = "GetSessionList";
    v14 = (char *)&dword_18011312C;
    goto LABEL_8;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, struct ITSSession **))(*(_QWORD *)v49 + 24LL))(
                  v49,
                  v40,
                  &v44);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_18012E170 <= 3 )
      goto LABEL_62;
    v43 = "AttemptAutoReconnect";
    v13 = "FindSessionById";
    v14 = &byte_1801130EF;
    goto LABEL_8;
  }
  if ( (int)CHelper::GetSessionAutoReconnectFlag(v44, (int *)&SystemTimeAsFileTime) >= 0
    && SystemTimeAsFileTime.dwLowDateTime == 1 )
  {
    SessionList = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)v44 + 88LL))(v44, &v46);
    if ( SessionList < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_62;
      v43 = "AttemptAutoReconnect";
      v13 = "getState";
      v14 = (char *)word_1801130B2;
      goto LABEL_8;
    }
    if ( (unsigned int)IsLoggedOnState(v46) )
      (*(void (__fastcall **)(struct ITSSession *, _QWORD, _QWORD))(*(_QWORD *)v44 + 56LL))(v44, 0, 0);
    if ( (unsigned int)CHelper::IsResetLastInputTimeOnAutoReconnect() )
    {
      v42 = 0;
      SystemTimeAsFileTime = 0;
      if ( (int)CHelper::GetCachedLastInputTimeForSession(v40, &v42, v39) >= 0 )
      {
        GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
        v16 = v42;
        v17 = (*(_QWORD *)&SystemTimeAsFileTime - v42) / 0x2710;
        v18 = (const char *)v39[0];
        if ( v17 > (unsigned __int64)v39[0] + 120000 )
        {
          memset_0(v53, 0, 0xA68u);
          if ( (*(int (__fastcall **)(struct IRemoteTerminal *, _BYTE *, __int64))(*(_QWORD *)a3 + 240LL))(
                 a3,
                 v53,
                 2664) >= 0
            && (v54 & 0x2000) != 0 )
          {
            if ( (unsigned int)dword_18012E170 > 4 )
            {
              v43 = "Logging off session due to idle timeout expiration";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v19,
                (unsigned int)&byte_18011308F,
                v20,
                v21,
                (__int64)&v43);
            }
            (*(void (__fastcall **)(struct ITSSession *, __int64))(*(_QWORD *)v44 + 64LL))(v44, 3);
          }
          v22 = 30;
          v23 = &v55;
          do
          {
            *v23++ = 0;
            --v22;
          }
          while ( v22 );
          if ( (unsigned int)dword_18012E170 > 3 )
          {
            v43 = (const char *)v17;
            v42 = v16;
            *(struct _FILETIME *)v39 = SystemTimeAsFileTime;
            v45 = v18;
            *(_QWORD *)&Buf2 = (int)v40;
            *(_QWORD *)&v50 = "Auto-reconnect exceed max idle";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)&word_18011301E,
              v20,
              v21,
              (__int64)&v50,
              (__int64)&Buf2,
              (__int64)&v45,
              (__int64)v39,
              (__int64)&v42,
              (__int64)&v43);
          }
          (*(void (__fastcall **)(struct IConnection *, __int64))(*(_QWORD *)a2 + 304LL))(a2, 3);
          SessionList = -2147023436;
          goto LABEL_61;
        }
        v24 = (*(__int64 (__fastcall **)(struct IConnection *, unsigned __int64))(*(_QWORD *)a2 + 728LL))(a2, v42);
        if ( v24 >= 0 )
        {
          CHelper::DeleteCachedLastInputTimeForSession(v40);
          if ( (unsigned int)dword_18012E170 > 4 )
          {
            *(_QWORD *)&v50 = (int)v40;
            *(_QWORD *)&Buf2 = "Successfully reset last input time succeeded for connection";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              v27,
              (unsigned int)word_180112FBA,
              v28,
              v29,
              (__int64)&Buf2,
              (__int64)&v50);
          }
        }
        else if ( (unsigned int)dword_18012E170 > 3 )
        {
          v39[0] = v24;
          *(_QWORD *)&v50 = (int)v40;
          *(_QWORD *)&Buf2 = "RDP protocol failed to reset new last input time";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            dword_18012E170,
            (unsigned int)qword_180112FE8,
            v25,
            v26,
            (__int64)&Buf2,
            (__int64)&v50,
            (__int64)v39);
        }
      }
    }
    SessionList = GetInstanceOfRemoteConnectionManager(&v47);
    if ( SessionList < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "GetInstanceOfRemoteConnectionManager";
        v31 = (__int64 *)byte_180112F7D;
LABEL_60:
        *(_QWORD *)&Buf2 = v30;
        v45 = "Warning HResult failed";
        v39[0] = SessionList;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v7,
          (_DWORD)v31,
          v8,
          v9,
          (__int64)&v45,
          (__int64)&Buf2,
          (__int64)v39,
          (__int64)&v50);
        goto LABEL_61;
      }
      goto LABEL_61;
    }
    SessionList = (*(__int64 (__fastcall **)(struct IRemoteConnectionManager *, __int64 *))(*(_QWORD *)v47 + 72LL))(
                    v47,
                    &v48);
    if ( SessionList < 0 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "GetInstanceOfEnforcementCore";
        v31 = qword_180112F40;
        goto LABEL_60;
      }
LABEL_61:
      v12 = 1;
      goto LABEL_62;
    }
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      *(_QWORD *)&v50 = (int)v40;
      *(_QWORD *)&Buf2 = "Attempting to serialize auto reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)word_180112F12,
        v8,
        v9,
        (__int64)&Buf2,
        (__int64)&v50);
    }
    SessionList = (*(__int64 (__fastcall **)(__int64, struct ITSSession *, struct IRemoteTerminal *, _QWORD))(*(_QWORD *)v48 + 96LL))(
                    v48,
                    v44,
                    a3,
                    0);
    if ( SessionList >= 0 )
    {
      if ( (unsigned int)dword_18012E170 > 4 )
      {
        *(_QWORD *)&v50 = (int)v40;
        *(_QWORD *)&Buf2 = "Autoreconnect incoming connection to session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v7,
          (unsigned int)&dword_180112EE4,
          v8,
          v9,
          (__int64)&Buf2,
          (__int64)&v50);
      }
      v12 = 1;
      goto LABEL_66;
    }
    if ( SessionList != -804650989 )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "SerializeSessionReconnect";
        v31 = (__int64 *)&dword_180112E84;
        goto LABEL_60;
      }
      goto LABEL_61;
    }
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      *(_QWORD *)&v50 = "Autoreconnect incoming connection failed, probably because of lack of licenses. Return proper error";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)byte_180112EC1,
        v8,
        v9,
        (__int64)&v50);
    }
    (*(void (__fastcall **)(struct IConnection *, __int64))(*(_QWORD *)a2 + 304LL))(a2, 5);
    v12 = 1;
  }
  else
  {
    (*(void (__fastcall **)(struct IConnection *, __int64))(*(_QWORD *)a2 + 304LL))(a2, 5);
  }
  SessionList = 1;
LABEL_66:
  if ( (unsigned int)dword_18012E170 <= 5 )
    goto LABEL_69;
  *(_QWORD *)&v50 = "CDefaultConnectionHandler::AttemptAutoReconnect";
  v32 = "Task completed successfully";
  v33 = (__int16 *)qword_180112E10;
LABEL_68:
  *(_QWORD *)&Buf2 = v32;
  v39[0] = SessionList;
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
    v7,
    (_DWORD)v33,
    v8,
    v9,
    (__int64)&Buf2,
    (__int64)&v50,
    (__int64)v39);
LABEL_69:
  if ( SessionList == -2147024894 || SessionList == -2147023652 )
  {
    Buf2 = 0;
    (*(void (__fastcall **)(struct IConnection *, __int128 *))(*(_QWORD *)a2 + 336LL))(a2, &Buf2);
    if ( !memcmp_0(&TERMINAL_TYPE_RDP_REMOTEAPP, &Buf2, 0x10u) )
    {
      if ( (unsigned int)dword_18012E170 > 3 )
      {
        *(_QWORD *)&v50 = "Autoreconnect session not found or cookie expired for RAIL. Disconnect.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v34,
          (unsigned int)word_180112DEA,
          v35,
          v36,
          (__int64)&v50);
      }
LABEL_81:
      v37 = 3;
      goto LABEL_82;
    }
  }
  if ( SessionList != -2147023531 )
  {
    if ( SessionList != -2147024894 && SessionList != -2147023652
      || (v50 = 0,
          (*(void (__fastcall **)(struct IConnection *, __int128 *))(*(_QWORD *)a2 + 336LL))(a2, &v50),
          memcmp_0(&TERMINAL_TYPE_RDP_REMOTEAPP, &v50, 0x10u)) )
    {
      v11 = SessionList;
      goto LABEL_83;
    }
    _DbgPrintMessage(4, "Autoreconnect session not found or cookie expired for RAIL. Disconnect.");
    goto LABEL_81;
  }
  v37 = 5;
LABEL_82:
  (*(void (__fastcall **)(struct IConnection *, __int64, _QWORD))(*(_QWORD *)a2 + 304LL))(a2, v37, 0);
LABEL_83:
  if ( v12 )
    (*(void (__fastcall **)(struct IConnection *))(*(_QWORD *)a2 + 504LL))(a2);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v47);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v48);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v49);
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v44);
  return v11;
}

```

## disassembly

```asm
0x180077188  mov     [rsp-8+arg_0], rbx
0x18007718d  mov     [rsp-8+arg_18], rsi
0x180077192  push    rbp
0x180077193  push    rdi
0x180077194  push    r13
0x180077196  push    r14
0x180077198  push    r15
0x18007719a  lea     rbp, [rsp-0AB0h]
0x1800771a2  sub     rsp, 0BB0h
0x1800771a9  mov     rax, cs:__security_cookie
0x1800771b0  xor     rax, rsp
0x1800771b3  mov     [rbp+0AD0h+var_30], rax
0x1800771ba  mov     r15, r8
0x1800771bd  mov     r14, rdx
0x1800771c0  mov     [rsp+0BD0h+var_B78], 0
0x1800771c8  mov     [rsp+0BD0h+var_B58], 0
0x1800771d1  mov     [rbp+0AD0h+var_B30], 0
0x1800771d9  xorps   xmm0, xmm0
0x1800771dc  movups  xmmword ptr [rbp+0AD0h+var_B08.Data1], xmm0
0x1800771e0  mov     [rsp+0BD0h+var_B80], 0
0x1800771e8  mov     [rbp+0AD0h+var_B38], 0
0x1800771f0  mov     [rbp+0AD0h+var_B40], 0
0x1800771f8  mov     eax, cs:dword_18012E170
0x1800771fe  lea     r13, aCdefaultconnec; "CDefaultConnectionHandler::AttemptAutoR"...
0x180077205  lea     rcx, aAutoReconnect; "Auto Reconnect"
0x18007720c  cmp     eax, 4
0x18007720f  jbe     short loc_180077251
0x180077211  lea     rax, aAttemptingAuto; "Attempting auto reconnect..."
0x180077218  mov     [rsp+0BD0h+var_B68], rax
0x18007721d  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180077222  mov     [rsp+0BD0h+var_B60], rcx
0x180077227  lea     rax, [rsp+0BD0h+var_B68]
0x18007722c  mov     [rsp+0BD0h+var_BA0], rax
0x180077231  lea     rax, [rsp+0BD0h+SystemTimeAsFileTime]
0x180077236  mov     [rsp+0BD0h+var_BA8], rax
0x18007723b  lea     rax, [rsp+0BD0h+var_B60]
0x180077240  mov     [rsp+0BD0h+var_BB0], rax
0x180077245  lea     rdx, word_1801131A6
0x18007724c  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180077251  mov     rax, [r15]
0x180077254  lea     rdx, [rsp+0BD0h+var_B78]
0x180077259  mov     rcx, r15
0x18007725c  mov     rax, [rax+178h]
0x180077263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077268  mov     ebx, eax
0x18007726a  mov     edi, 1
0x18007726f  test    eax, eax
0x180077271  jns     short loc_18007727C
0x180077273  xor     esi, esi
0x180077275  cmp     eax, 800704DCh
0x18007727a  jnz     short loc_180077282
0x18007727c  mov     esi, edi
0x18007727e  test    ebx, ebx
0x180077280  jns     short loc_1800772F2
0x180077282  mov     eax, cs:dword_18012E170
0x180077288  cmp     eax, 3
0x18007728b  jbe     loc_18007787C
0x180077291  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180077298  mov     [rsp+0BD0h+var_B60], rax
0x18007729d  lea     rax, aAuthenticatecl_0; "AuthenticateClientToSession"
0x1800772a4  lea     rdx, byte_180113169
0x1800772ab  mov     [rsp+0BD0h+var_B68], rax
0x1800772b0  lea     rax, aWarningHresult; "Warning HResult failed"
0x1800772b7  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800772bc  lea     rax, [rsp+0BD0h+var_B60]
0x1800772c1  mov     [rsp+0BD0h+var_B98], rax
0x1800772c6  lea     rax, [rsp+0BD0h+var_B80]
0x1800772cb  mov     [rsp+0BD0h+var_BA0], rax
0x1800772d0  lea     rax, [rsp+0BD0h+var_B68]
0x1800772d5  mov     [rsp+0BD0h+var_BA8], rax
0x1800772da  lea     rax, [rsp+0BD0h+SystemTimeAsFileTime]
0x1800772df  mov     [rsp+0BD0h+var_BB0], rax
0x1800772e4  mov     [rsp+0BD0h+var_B80], ebx
0x1800772e8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800772ed  jmp     loc_18007787C
0x1800772f2  mov     [rbp+0AD0h+var_B48], 0
0x1800772f9  mov     [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180077301  mov     rax, [r14]
0x180077304  lea     rdx, [rbp+0AD0h+var_B08]
0x180077308  mov     rcx, r14
0x18007730b  mov     rax, [rax+170h]
0x180077312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077317  lea     r8, [rbp+0AD0h+var_80]; unsigned __int16 *
0x18007731e  lea     rcx, [rbp+0AD0h+var_B08]; struct _GUID *
0x180077322  test    eax, eax
0x180077324  jns     short loc_18007732D
0x180077326  xorps   xmm0, xmm0
0x180077329  movups  xmmword ptr [rbp+0AD0h+var_B08.Data1], xmm0
0x18007732d  call    ?ConvertUuidToString@CUtils@@SAJPEAU_GUID@@KPEAG@Z; CUtils::ConvertUuidToString(_GUID *,ulong,ushort *)
0x180077332  lea     rcx, [rbp+0AD0h+var_B30]; struct ISessionList **
0x180077336  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x18007733b  mov     ebx, eax
0x18007733d  test    eax, eax
0x18007733f  jns     short loc_18007736F
0x180077341  mov     eax, cs:dword_18012E170
0x180077347  cmp     eax, 3
0x18007734a  jbe     loc_18007787C
0x180077350  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180077357  mov     [rsp+0BD0h+var_B60], rax
0x18007735c  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180077363  lea     rdx, dword_18011312C
0x18007736a  jmp     loc_1800772AB
0x18007736f  mov     rcx, [rbp+0AD0h+var_B30]
0x180077373  mov     rax, [rcx]
0x180077376  lea     r8, [rsp+0BD0h+var_B58]
0x18007737b  mov     edx, [rsp+0BD0h+var_B78]
0x18007737f  mov     rax, [rax+18h]
0x180077383  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077388  mov     ebx, eax
0x18007738a  test    eax, eax
0x18007738c  jns     short loc_1800773BC
0x18007738e  mov     eax, cs:dword_18012E170
0x180077394  cmp     eax, 3
0x180077397  jbe     loc_18007787C
0x18007739d  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x1800773a4  mov     [rsp+0BD0h+var_B60], rax
0x1800773a9  lea     rax, aFindsessionbyi; "FindSessionById"
0x1800773b0  lea     rdx, byte_1801130EF
0x1800773b7  jmp     loc_1800772AB
0x1800773bc  lea     rdx, [rsp+0BD0h+SystemTimeAsFileTime]; int *
0x1800773c1  mov     rcx, [rsp+0BD0h+var_B58]; struct ITSSession *
0x1800773c6  call    ?GetSessionAutoReconnectFlag@CHelper@@SAJPEAUITSSession@@PEAH@Z; CHelper::GetSessionAutoReconnectFlag(ITSSession *,int *)
0x1800773cb  test    eax, eax
0x1800773cd  js      loc_1800778A2
0x1800773d3  cmp     [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], edi
0x1800773d7  jnz     loc_1800778A2
0x1800773dd  mov     rcx, [rsp+0BD0h+var_B58]
0x1800773e2  mov     rax, [rcx]
0x1800773e5  lea     rdx, [rbp+0AD0h+var_B48]
0x1800773e9  mov     rax, [rax+58h]
0x1800773ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800773f2  mov     ebx, eax
0x1800773f4  test    eax, eax
0x1800773f6  jns     short loc_180077426
0x1800773f8  mov     eax, cs:dword_18012E170
0x1800773fe  cmp     eax, 3
0x180077401  jbe     loc_18007787C
0x180077407  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x18007740e  mov     [rsp+0BD0h+var_B60], rax
0x180077413  lea     rax, aGetstate; "getState"
0x18007741a  lea     rdx, word_1801130B2
0x180077421  jmp     loc_1800772AB
0x180077426  mov     ecx, [rbp+0AD0h+var_B48]
0x180077429  call    IsLoggedOnState
0x18007742e  test    eax, eax
0x180077430  jz      short loc_180077448
0x180077432  mov     rcx, [rsp+0BD0h+var_B58]
0x180077437  mov     rax, [rcx]
0x18007743a  xor     r8d, r8d
0x18007743d  xor     edx, edx
0x18007743f  mov     rax, [rax+38h]
0x180077443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077448  call    ?IsResetLastInputTimeOnAutoReconnect@CHelper@@SAHXZ; CHelper::IsResetLastInputTimeOnAutoReconnect(void)
0x18007744d  test    eax, eax
0x18007744f  jz      loc_1800776B3
0x180077455  mov     [rsp+0BD0h+var_B68], 0
0x18007745e  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180077467  lea     r8, [rsp+0BD0h+var_B80]; unsigned int *
0x18007746c  lea     rdx, [rsp+0BD0h+var_B68]; unsigned __int64 *
0x180077471  mov     ecx, [rsp+0BD0h+var_B78]; unsigned int
0x180077475  call    ?GetCachedLastInputTimeForSession@CHelper@@SAJKPEA_KPEAK@Z; CHelper::GetCachedLastInputTimeForSession(ulong,unsigned __int64 *,ulong *)
0x18007747a  test    eax, eax
0x18007747c  js      loc_1800776B3
0x180077482  lea     rcx, [rsp+0BD0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180077487  call    cs:__imp_GetSystemTimeAsFileTime
0x18007748e  nop     dword ptr [rax+rax+00h]
0x180077493  mov     rcx, qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime]
0x180077498  mov     rsi, [rsp+0BD0h+var_B68]
0x18007749d  sub     rcx, rsi
0x1800774a0  mov     rax, 346DC5D63886594Bh
0x1800774aa  mul     rcx
0x1800774ad  mov     rbx, rdx
0x1800774b0  shr     rbx, 0Bh
0x1800774b4  mov     r13d, [rsp+0BD0h+var_B80]
0x1800774b9  lea     rax, [r13+1D4C0h]
0x1800774c0  cmp     rbx, rax
0x1800774c3  jbe     loc_1800775FC
0x1800774c9  xor     edx, edx; Val
0x1800774cb  mov     r8d, 0A68h; Size
0x1800774d1  lea     rcx, [rbp+0AD0h+var_AF0]; void *
0x1800774d5  call    memset_0
0x1800774da  mov     rax, [r15]
0x1800774dd  mov     r8d, 0A68h
0x1800774e3  lea     rdx, [rbp+0AD0h+var_AF0]
0x1800774e7  mov     rcx, r15
0x1800774ea  mov     rax, [rax+0F0h]
0x1800774f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800774f6  test    eax, eax
0x1800774f8  js      short loc_180077546
0x1800774fa  test    [rbp+0AD0h+var_A74], 2000h
0x180077501  jz      short loc_180077546
0x180077503  mov     eax, cs:dword_18012E170
0x180077509  cmp     eax, 4
0x18007750c  jbe     short loc_180077530
0x18007750e  lea     rax, aLoggingOffSess; "Logging off session due to idle timeout"...
0x180077515  mov     [rsp+0BD0h+var_B60], rax
0x18007751a  lea     rax, [rsp+0BD0h+var_B60]
0x18007751f  mov     [rsp+0BD0h+var_BB0], rax
0x180077524  lea     rdx, byte_18011308F
0x18007752b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180077530  mov     rcx, [rsp+0BD0h+var_B58]
0x180077535  mov     rax, [rcx]
0x180077538  mov     edx, 3
0x18007753d  mov     rax, [rax+40h]
0x180077541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077546  mov     ecx, 1Eh
0x18007754b  lea     rax, [rbp+0AD0h+var_A1E]
0x180077552  mov     byte ptr [rax], 0
0x180077555  add     rax, rdi
0x180077558  sub     rcx, rdi
0x18007755b  jnz     short loc_180077552
0x18007755d  mov     eax, cs:dword_18012E170
0x180077563  cmp     eax, 3
0x180077566  jbe     short loc_1800775D9
0x180077568  mov     [rsp+0BD0h+var_B60], rbx
0x18007756d  mov     [rsp+0BD0h+var_B68], rsi
0x180077572  mov     rax, qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime]
0x180077577  mov     qword ptr [rsp+0BD0h+var_B80], rax
0x18007757c  mov     [rbp+0AD0h+var_B50], r13
0x180077580  movsxd  rax, [rsp+0BD0h+var_B78]
0x180077585  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x180077589  lea     rax, aAutoReconnectE; "Auto-reconnect exceed max idle"
0x180077590  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x180077594  lea     rax, [rsp+0BD0h+var_B60]
0x180077599  mov     [rsp+0BD0h+var_B88], rax
0x18007759e  lea     rax, [rsp+0BD0h+var_B68]
0x1800775a3  mov     [rsp+0BD0h+var_B90], rax
0x1800775a8  lea     rax, [rsp+0BD0h+var_B80]
0x1800775ad  mov     [rsp+0BD0h+var_B98], rax
0x1800775b2  lea     rax, [rbp+0AD0h+var_B50]
0x1800775b6  mov     [rsp+0BD0h+var_BA0], rax
0x1800775bb  lea     rax, [rbp+0AD0h+Buf2]
0x1800775bf  mov     [rsp+0BD0h+var_BA8], rax
0x1800775c4  lea     rax, [rbp+0AD0h+var_B28]
0x1800775c8  mov     [rsp+0BD0h+var_BB0], rax
0x1800775cd  lea     rdx, word_18011301E
0x1800775d4  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x1800775d9  mov     rax, [r14]
0x1800775dc  xor     r8d, r8d
0x1800775df  lea     edx, [r8+3]
0x1800775e3  mov     rcx, r14
0x1800775e6  mov     rax, [rax+130h]
0x1800775ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800775f2  mov     ebx, 800705B4h
0x1800775f7  jmp     loc_18007787A
0x1800775fc  mov     rax, [r14]
0x1800775ff  mov     rdx, rsi
0x180077602  mov     rcx, r14
0x180077605  mov     rax, [rax+2D8h]
0x18007760c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077611  test    eax, eax
0x180077613  jns     short loc_180077666
0x180077615  mov     ecx, cs:dword_18012E170
0x18007761b  cmp     ecx, 3
0x18007761e  jbe     loc_1800776AC
0x180077624  mov     [rsp+0BD0h+var_B80], eax
0x180077628  movsxd  rax, [rsp+0BD0h+var_B78]
0x18007762d  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x180077631  lea     rax, aRdpProtocolFai; "RDP protocol failed to reset new last i"...
0x180077638  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x18007763c  lea     rax, [rsp+0BD0h+var_B80]
0x180077641  mov     [rsp+0BD0h+var_BA0], rax
0x180077646  lea     rax, [rbp+0AD0h+var_B28]
0x18007764a  mov     [rsp+0BD0h+var_BA8], rax
0x18007764f  lea     rax, [rbp+0AD0h+Buf2]
0x180077653  mov     [rsp+0BD0h+var_BB0], rax
0x180077658  lea     rdx, qword_180112FE8
0x18007765f  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x180077664  jmp     short loc_1800776AC
0x180077666  mov     ecx, [rsp+0BD0h+var_B78]; unsigned int
0x18007766a  call    ?DeleteCachedLastInputTimeForSession@CHelper@@SAJK@Z; CHelper::DeleteCachedLastInputTimeForSession(ulong)
0x18007766f  mov     eax, cs:dword_18012E170
0x180077675  cmp     eax, 4
0x180077678  jbe     short loc_1800776AC
0x18007767a  movsxd  rax, [rsp+0BD0h+var_B78]
0x18007767f  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x180077683  lea     rax, aSuccessfullyRe; "Successfully reset last input time succ"...
0x18007768a  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x18007768e  lea     rax, [rbp+0AD0h+var_B28]
0x180077692  mov     [rsp+0BD0h+var_BA8], rax
0x180077697  lea     rax, [rbp+0AD0h+Buf2]
0x18007769b  mov     [rsp+0BD0h+var_BB0], rax
0x1800776a0  lea     rdx, word_180112FBA
0x1800776a7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x1800776ac  lea     r13, aCdefaultconnec; "CDefaultConnectionHandler::AttemptAutoR"...
0x1800776b3  lea     rcx, [rbp+0AD0h+var_B40]; struct IRemoteConnectionManager **
0x1800776b7  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x1800776bc  mov     ebx, eax
0x1800776be  test    eax, eax
0x1800776c0  jns     short loc_1800776EF
0x1800776c2  mov     eax, cs:dword_18012E170
0x1800776c8  cmp     eax, 3
0x1800776cb  jbe     loc_18007787A
0x1800776d1  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x1800776d8  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x1800776dc  lea     rax, aGetinstanceofr_2; "GetInstanceOfRemoteConnectionManager"
0x1800776e3  lea     rdx, byte_180112F7D
0x1800776ea  jmp     loc_18007783D
0x1800776ef  mov     rcx, [rbp+0AD0h+var_B40]
0x1800776f3  mov     rax, [rcx]
  ... truncated ...
```
