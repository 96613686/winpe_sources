# CDefaultConnectionHandler::AttemptAutoReconnect(IConnection *,IRemoteTerminal *)

- ea: `0x180073c08`
- end: `0x1800744e6`
- name: `?AttemptAutoReconnect@CDefaultConnectionHandler@@QEAAJPEAVIConnection@@PEAVIRemoteTerminal@@@Z`
- size: `2270`
- prototype: `__int64 __fastcall(CDefaultConnectionHandler *this, struct IConnection *, struct IRemoteTerminal *, int)`
- caller_count: `1`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180076420`

## callees

- `0x180001380`
- `0x180001688`
- `0x18000225c`
- `0x1800035d0`
- `0x18000a210`
- `0x18000c2f0`
- `0x180012480`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800148f0`
- `0x1800321f0`
- `0x1800330c4`
- `0x18004f7a4`
- `0x180050490`
- `0x180073c08`
- `0x180079d94`
- `0x180079f94`
- `0x18007a088`
- `0x18007a570`
- `0x1800c4e00`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073f07`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073f07`

## string_xrefs

- `0x180074346`: `Task completed successfully`
- `0x180073c91`: `Attempting auto reconnect...`
- `0x180073c7e`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x180074126`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x180074301`: `CDefaultConnectionHandler::AttemptAutoReconnect`
- `0x180073d11`: `AttemptAutoReconnect`
- `0x180073dd0`: `AttemptAutoReconnect`
- `0x180073e1d`: `AttemptAutoReconnect`
- `0x180073e87`: `AttemptAutoReconnect`
- `0x18007414b`: `AttemptAutoReconnect`
- `0x180074192`: `AttemptAutoReconnect`
- `0x18007429e`: `AttemptAutoReconnect`
- `0x1800740ab`: `RDP protocol failed to reset new last input time`
- `0x1800741be`: `Attempting to serialize auto reconnect`
- `0x18007421c`: `Autoreconnect incoming connection to session`
- `0x180074259`: `Autoreconnect incoming connection failed, probably because of lack of licenses. Return proper error`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v42 = (unsigned __int64)"Attempting auto reconnect...";
    SystemTimeAsFileTime = (struct _FILETIME)"CDefaultConnectionHandler::AttemptAutoReconnect";
    v43 = "Auto Reconnect";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"Auto Reconnect",
      (unsigned int)&word_18010D126,
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
    if ( (unsigned int)dword_180128170 <= 3 )
    {
LABEL_62:
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_69;
      *(_QWORD *)&v50 = "CDefaultConnectionHandler::AttemptAutoReconnect";
      v32 = "Auto Reconnect";
      v33 = &word_18010CDC6;
      goto LABEL_68;
    }
    v43 = "AttemptAutoReconnect";
    v13 = "AuthenticateClientToSession";
    v14 = byte_18010D0E9;
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
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_62;
    v43 = "AttemptAutoReconnect";
    v13 = "GetSessionList";
    v14 = (char *)&dword_18010D0AC;
    goto LABEL_8;
  }
  SessionList = (*(__int64 (__fastcall **)(struct ISessionList *, _QWORD, struct ITSSession **))(*(_QWORD *)v49 + 24LL))(
                  v49,
                  v40,
                  &v44);
  if ( SessionList < 0 )
  {
    if ( (unsigned int)dword_180128170 <= 3 )
      goto LABEL_62;
    v43 = "AttemptAutoReconnect";
    v13 = "FindSessionById";
    v14 = &byte_18010D06F;
    goto LABEL_8;
  }
  if ( (int)CHelper::GetSessionAutoReconnectFlag(v44, (int *)&SystemTimeAsFileTime) >= 0
    && SystemTimeAsFileTime.dwLowDateTime == 1 )
  {
    SessionList = (*(__int64 (__fastcall **)(struct ITSSession *, unsigned int *))(*(_QWORD *)v44 + 88LL))(v44, &v46);
    if ( SessionList < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_62;
      v43 = "AttemptAutoReconnect";
      v13 = "getState";
      v14 = (char *)word_18010D032;
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
            if ( (unsigned int)dword_180128170 > 4 )
            {
              v43 = "Logging off session due to idle timeout expiration";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
                v19,
                (unsigned int)&byte_18010D00F,
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
          if ( (unsigned int)dword_180128170 > 3 )
          {
            v43 = (const char *)v17;
            v42 = v16;
            *(struct _FILETIME *)v39 = SystemTimeAsFileTime;
            v45 = v18;
            *(_QWORD *)&Buf2 = (int)v40;
            *(_QWORD *)&v50 = "Auto-reconnect exceed max idle";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(
              0,
              (unsigned int)&word_18010CF9E,
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
          if ( (unsigned int)dword_180128170 > 4 )
          {
            *(_QWORD *)&v50 = (int)v40;
            *(_QWORD *)&Buf2 = "Successfully reset last input time succeeded for connection";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
              v27,
              (unsigned int)word_18010CF3A,
              v28,
              v29,
              (__int64)&Buf2,
              (__int64)&v50);
          }
        }
        else if ( (unsigned int)dword_180128170 > 3 )
        {
          v39[0] = v24;
          *(_QWORD *)&v50 = (int)v40;
          *(_QWORD *)&Buf2 = "RDP protocol failed to reset new last input time";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
            dword_180128170,
            (unsigned int)qword_18010CF68,
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "GetInstanceOfRemoteConnectionManager";
        v31 = (__int64 *)byte_18010CEFD;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "GetInstanceOfEnforcementCore";
        v31 = qword_18010CEC0;
        goto LABEL_60;
      }
LABEL_61:
      v12 = 1;
      goto LABEL_62;
    }
    if ( (unsigned int)dword_180128170 > 4 )
    {
      *(_QWORD *)&v50 = (int)v40;
      *(_QWORD *)&Buf2 = "Attempting to serialize auto reconnect";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
        v7,
        (unsigned int)word_18010CE92,
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
      if ( (unsigned int)dword_180128170 > 4 )
      {
        *(_QWORD *)&v50 = (int)v40;
        *(_QWORD *)&Buf2 = "Autoreconnect incoming connection to session";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(
          v7,
          (unsigned int)&dword_18010CE64,
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        *(_QWORD *)&v50 = "AttemptAutoReconnect";
        v30 = "SerializeSessionReconnect";
        v31 = (__int64 *)&dword_18010CE04;
        goto LABEL_60;
      }
      goto LABEL_61;
    }
    if ( (unsigned int)dword_180128170 > 4 )
    {
      *(_QWORD *)&v50 = "Autoreconnect incoming connection failed, probably because of lack of licenses. Return proper error";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v7,
        (unsigned int)byte_18010CE41,
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
  if ( (unsigned int)dword_180128170 <= 5 )
    goto LABEL_69;
  *(_QWORD *)&v50 = "CDefaultConnectionHandler::AttemptAutoReconnect";
  v32 = "Task completed successfully";
  v33 = (__int16 *)qword_18010CD90;
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
      if ( (unsigned int)dword_180128170 > 3 )
      {
        *(_QWORD *)&v50 = "Autoreconnect session not found or cookie expired for RAIL. Disconnect.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v34,
          (unsigned int)word_18010CD6A,
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
0x180073c08  mov     [rsp-8+arg_0], rbx
0x180073c0d  mov     [rsp-8+arg_18], rsi
0x180073c12  push    rbp
0x180073c13  push    rdi
0x180073c14  push    r13
0x180073c16  push    r14
0x180073c18  push    r15
0x180073c1a  lea     rbp, [rsp-0AB0h]
0x180073c22  sub     rsp, 0BB0h
0x180073c29  mov     rax, cs:__security_cookie
0x180073c30  xor     rax, rsp
0x180073c33  mov     [rbp+0AD0h+var_30], rax
0x180073c3a  mov     r15, r8
0x180073c3d  mov     r14, rdx
0x180073c40  mov     [rsp+0BD0h+var_B78], 0
0x180073c48  mov     [rsp+0BD0h+var_B58], 0
0x180073c51  mov     [rbp+0AD0h+var_B30], 0
0x180073c59  xorps   xmm0, xmm0
0x180073c5c  movups  xmmword ptr [rbp+0AD0h+var_B08.Data1], xmm0
0x180073c60  mov     [rsp+0BD0h+var_B80], 0
0x180073c68  mov     [rbp+0AD0h+var_B38], 0
0x180073c70  mov     [rbp+0AD0h+var_B40], 0
0x180073c78  mov     eax, cs:dword_180128170
0x180073c7e  lea     r13, aCdefaultconnec; "CDefaultConnectionHandler::AttemptAutoR"...
0x180073c85  lea     rcx, aAutoReconnect; "Auto Reconnect"
0x180073c8c  cmp     eax, 4
0x180073c8f  jbe     short loc_180073CD1
0x180073c91  lea     rax, aAttemptingAuto; "Attempting auto reconnect..."
0x180073c98  mov     [rsp+0BD0h+var_B68], rax
0x180073c9d  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180073ca2  mov     [rsp+0BD0h+var_B60], rcx
0x180073ca7  lea     rax, [rsp+0BD0h+var_B68]
0x180073cac  mov     [rsp+0BD0h+var_BA0], rax
0x180073cb1  lea     rax, [rsp+0BD0h+SystemTimeAsFileTime]
0x180073cb6  mov     [rsp+0BD0h+var_BA8], rax
0x180073cbb  lea     rax, [rsp+0BD0h+var_B60]
0x180073cc0  mov     [rsp+0BD0h+var_BB0], rax
0x180073cc5  lea     rdx, word_18010D126
0x180073ccc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180073cd1  mov     rax, [r15]
0x180073cd4  lea     rdx, [rsp+0BD0h+var_B78]
0x180073cd9  mov     rcx, r15
0x180073cdc  mov     rax, [rax+178h]
0x180073ce3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ce8  mov     ebx, eax
0x180073cea  mov     edi, 1
0x180073cef  test    eax, eax
0x180073cf1  jns     short loc_180073CFC
0x180073cf3  xor     esi, esi
0x180073cf5  cmp     eax, 800704DCh
0x180073cfa  jnz     short loc_180073D02
0x180073cfc  mov     esi, edi
0x180073cfe  test    ebx, ebx
0x180073d00  jns     short loc_180073D72
0x180073d02  mov     eax, cs:dword_180128170
0x180073d08  cmp     eax, 3
0x180073d0b  jbe     loc_1800742F6
0x180073d11  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180073d18  mov     [rsp+0BD0h+var_B60], rax
0x180073d1d  lea     rax, aAuthenticatecl_0; "AuthenticateClientToSession"
0x180073d24  lea     rdx, byte_18010D0E9
0x180073d2b  mov     [rsp+0BD0h+var_B68], rax
0x180073d30  lea     rax, aWarningHresult; "Warning HResult failed"
0x180073d37  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], rax
0x180073d3c  lea     rax, [rsp+0BD0h+var_B60]
0x180073d41  mov     [rsp+0BD0h+var_B98], rax
0x180073d46  lea     rax, [rsp+0BD0h+var_B80]
0x180073d4b  mov     [rsp+0BD0h+var_BA0], rax
0x180073d50  lea     rax, [rsp+0BD0h+var_B68]
0x180073d55  mov     [rsp+0BD0h+var_BA8], rax
0x180073d5a  lea     rax, [rsp+0BD0h+SystemTimeAsFileTime]
0x180073d5f  mov     [rsp+0BD0h+var_BB0], rax
0x180073d64  mov     [rsp+0BD0h+var_B80], ebx
0x180073d68  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180073d6d  jmp     loc_1800742F6
0x180073d72  mov     [rbp+0AD0h+var_B48], 0
0x180073d79  mov     [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180073d81  mov     rax, [r14]
0x180073d84  lea     rdx, [rbp+0AD0h+var_B08]
0x180073d88  mov     rcx, r14
0x180073d8b  mov     rax, [rax+170h]
0x180073d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073d97  lea     r8, [rbp+0AD0h+var_80]; unsigned __int16 *
0x180073d9e  lea     rcx, [rbp+0AD0h+var_B08]; struct _GUID *
0x180073da2  test    eax, eax
0x180073da4  jns     short loc_180073DAD
0x180073da6  xorps   xmm0, xmm0
0x180073da9  movups  xmmword ptr [rbp+0AD0h+var_B08.Data1], xmm0
0x180073dad  call    ?ConvertUuidToString@CUtils@@SAJPEAU_GUID@@KPEAG@Z; CUtils::ConvertUuidToString(_GUID *,ulong,ushort *)
0x180073db2  lea     rcx, [rbp+0AD0h+var_B30]; struct ISessionList **
0x180073db6  call    ?GetSessionList@CHelper@@SAJPEAPEAUISessionList@@@Z; CHelper::GetSessionList(ISessionList * *)
0x180073dbb  mov     ebx, eax
0x180073dbd  test    eax, eax
0x180073dbf  jns     short loc_180073DEF
0x180073dc1  mov     eax, cs:dword_180128170
0x180073dc7  cmp     eax, 3
0x180073dca  jbe     loc_1800742F6
0x180073dd0  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180073dd7  mov     [rsp+0BD0h+var_B60], rax
0x180073ddc  lea     rax, aGetsessionlist_1; "GetSessionList"
0x180073de3  lea     rdx, dword_18010D0AC
0x180073dea  jmp     loc_180073D2B
0x180073def  mov     rcx, [rbp+0AD0h+var_B30]
0x180073df3  mov     rax, [rcx]
0x180073df6  lea     r8, [rsp+0BD0h+var_B58]
0x180073dfb  mov     edx, [rsp+0BD0h+var_B78]
0x180073dff  mov     rax, [rax+18h]
0x180073e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e08  mov     ebx, eax
0x180073e0a  test    eax, eax
0x180073e0c  jns     short loc_180073E3C
0x180073e0e  mov     eax, cs:dword_180128170
0x180073e14  cmp     eax, 3
0x180073e17  jbe     loc_1800742F6
0x180073e1d  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180073e24  mov     [rsp+0BD0h+var_B60], rax
0x180073e29  lea     rax, aFindsessionbyi; "FindSessionById"
0x180073e30  lea     rdx, byte_18010D06F
0x180073e37  jmp     loc_180073D2B
0x180073e3c  lea     rdx, [rsp+0BD0h+SystemTimeAsFileTime]; int *
0x180073e41  mov     rcx, [rsp+0BD0h+var_B58]; struct ITSSession *
0x180073e46  call    ?GetSessionAutoReconnectFlag@CHelper@@SAJPEAUITSSession@@PEAH@Z; CHelper::GetSessionAutoReconnectFlag(ITSSession *,int *)
0x180073e4b  test    eax, eax
0x180073e4d  js      loc_18007431C
0x180073e53  cmp     [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], edi
0x180073e57  jnz     loc_18007431C
0x180073e5d  mov     rcx, [rsp+0BD0h+var_B58]
0x180073e62  mov     rax, [rcx]
0x180073e65  lea     rdx, [rbp+0AD0h+var_B48]
0x180073e69  mov     rax, [rax+58h]
0x180073e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073e72  mov     ebx, eax
0x180073e74  test    eax, eax
0x180073e76  jns     short loc_180073EA6
0x180073e78  mov     eax, cs:dword_180128170
0x180073e7e  cmp     eax, 3
0x180073e81  jbe     loc_1800742F6
0x180073e87  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180073e8e  mov     [rsp+0BD0h+var_B60], rax
0x180073e93  lea     rax, aGetstate; "getState"
0x180073e9a  lea     rdx, word_18010D032
0x180073ea1  jmp     loc_180073D2B
0x180073ea6  mov     ecx, [rbp+0AD0h+var_B48]
0x180073ea9  call    IsLoggedOnState
0x180073eae  test    eax, eax
0x180073eb0  jz      short loc_180073EC8
0x180073eb2  mov     rcx, [rsp+0BD0h+var_B58]
0x180073eb7  mov     rax, [rcx]
0x180073eba  xor     r8d, r8d
0x180073ebd  xor     edx, edx
0x180073ebf  mov     rax, [rax+38h]
0x180073ec3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073ec8  call    ?IsResetLastInputTimeOnAutoReconnect@CHelper@@SAHXZ; CHelper::IsResetLastInputTimeOnAutoReconnect(void)
0x180073ecd  test    eax, eax
0x180073ecf  jz      loc_18007412D
0x180073ed5  mov     [rsp+0BD0h+var_B68], 0
0x180073ede  mov     qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime], 0
0x180073ee7  lea     r8, [rsp+0BD0h+var_B80]; unsigned int *
0x180073eec  lea     rdx, [rsp+0BD0h+var_B68]; unsigned __int64 *
0x180073ef1  mov     ecx, [rsp+0BD0h+var_B78]; unsigned int
0x180073ef5  call    ?GetCachedLastInputTimeForSession@CHelper@@SAJKPEA_KPEAK@Z; CHelper::GetCachedLastInputTimeForSession(ulong,unsigned __int64 *,ulong *)
0x180073efa  test    eax, eax
0x180073efc  js      loc_18007412D
0x180073f02  lea     rcx, [rsp+0BD0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073f07  call    cs:__imp_GetSystemTimeAsFileTime
0x180073f0d  mov     rcx, qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime]
0x180073f12  mov     rsi, [rsp+0BD0h+var_B68]
0x180073f17  sub     rcx, rsi
0x180073f1a  mov     rax, 346DC5D63886594Bh
0x180073f24  mul     rcx
0x180073f27  mov     rbx, rdx
0x180073f2a  shr     rbx, 0Bh
0x180073f2e  mov     r13d, [rsp+0BD0h+var_B80]
0x180073f33  lea     rax, [r13+1D4C0h]
0x180073f3a  cmp     rbx, rax
0x180073f3d  jbe     loc_180074076
0x180073f43  xor     edx, edx; Val
0x180073f45  mov     r8d, 0A68h; Size
0x180073f4b  lea     rcx, [rbp+0AD0h+var_AF0]; void *
0x180073f4f  call    memset_0
0x180073f54  mov     rax, [r15]
0x180073f57  mov     r8d, 0A68h
0x180073f5d  lea     rdx, [rbp+0AD0h+var_AF0]
0x180073f61  mov     rcx, r15
0x180073f64  mov     rax, [rax+0F0h]
0x180073f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073f70  test    eax, eax
0x180073f72  js      short loc_180073FC0
0x180073f74  test    [rbp+0AD0h+var_A74], 2000h
0x180073f7b  jz      short loc_180073FC0
0x180073f7d  mov     eax, cs:dword_180128170
0x180073f83  cmp     eax, 4
0x180073f86  jbe     short loc_180073FAA
0x180073f88  lea     rax, aLoggingOffSess; "Logging off session due to idle timeout"...
0x180073f8f  mov     [rsp+0BD0h+var_B60], rax
0x180073f94  lea     rax, [rsp+0BD0h+var_B60]
0x180073f99  mov     [rsp+0BD0h+var_BB0], rax
0x180073f9e  lea     rdx, byte_18010D00F
0x180073fa5  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180073faa  mov     rcx, [rsp+0BD0h+var_B58]
0x180073faf  mov     rax, [rcx]
0x180073fb2  mov     edx, 3
0x180073fb7  mov     rax, [rax+40h]
0x180073fbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180073fc0  mov     ecx, 1Eh
0x180073fc5  lea     rax, [rbp+0AD0h+var_A1E]
0x180073fcc  mov     byte ptr [rax], 0
0x180073fcf  add     rax, rdi
0x180073fd2  sub     rcx, rdi
0x180073fd5  jnz     short loc_180073FCC
0x180073fd7  mov     eax, cs:dword_180128170
0x180073fdd  cmp     eax, 3
0x180073fe0  jbe     short loc_180074053
0x180073fe2  mov     [rsp+0BD0h+var_B60], rbx
0x180073fe7  mov     [rsp+0BD0h+var_B68], rsi
0x180073fec  mov     rax, qword ptr [rsp+0BD0h+SystemTimeAsFileTime.dwLowDateTime]
0x180073ff1  mov     qword ptr [rsp+0BD0h+var_B80], rax
0x180073ff6  mov     [rbp+0AD0h+var_B50], r13
0x180073ffa  movsxd  rax, [rsp+0BD0h+var_B78]
0x180073fff  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x180074003  lea     rax, aAutoReconnectE; "Auto-reconnect exceed max idle"
0x18007400a  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x18007400e  lea     rax, [rsp+0BD0h+var_B60]
0x180074013  mov     [rsp+0BD0h+var_B88], rax
0x180074018  lea     rax, [rsp+0BD0h+var_B68]
0x18007401d  mov     [rsp+0BD0h+var_B90], rax
0x180074022  lea     rax, [rsp+0BD0h+var_B80]
0x180074027  mov     [rsp+0BD0h+var_B98], rax
0x18007402c  lea     rax, [rbp+0AD0h+var_B50]
0x180074030  mov     [rsp+0BD0h+var_BA0], rax
0x180074035  lea     rax, [rbp+0AD0h+Buf2]
0x180074039  mov     [rsp+0BD0h+var_BA8], rax
0x18007403e  lea     rax, [rbp+0AD0h+var_B28]
0x180074042  mov     [rsp+0BD0h+var_BB0], rax
0x180074047  lea     rdx, word_18010CF9E
0x18007404e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@4444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &)
0x180074053  mov     rax, [r14]
0x180074056  xor     r8d, r8d
0x180074059  lea     edx, [r8+3]
0x18007405d  mov     rcx, r14
0x180074060  mov     rax, [rax+130h]
0x180074067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007406c  mov     ebx, 800705B4h
0x180074071  jmp     loc_1800742F4
0x180074076  mov     rax, [r14]
0x180074079  mov     rdx, rsi
0x18007407c  mov     rcx, r14
0x18007407f  mov     rax, [rax+2D8h]
0x180074086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007408b  test    eax, eax
0x18007408d  jns     short loc_1800740E0
0x18007408f  mov     ecx, cs:dword_180128170
0x180074095  cmp     ecx, 3
0x180074098  jbe     loc_180074126
0x18007409e  mov     [rsp+0BD0h+var_B80], eax
0x1800740a2  movsxd  rax, [rsp+0BD0h+var_B78]
0x1800740a7  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x1800740ab  lea     rax, aRdpProtocolFai; "RDP protocol failed to reset new last i"...
0x1800740b2  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x1800740b6  lea     rax, [rsp+0BD0h+var_B80]
0x1800740bb  mov     [rsp+0BD0h+var_BA0], rax
0x1800740c0  lea     rax, [rbp+0AD0h+var_B28]
0x1800740c4  mov     [rsp+0BD0h+var_BA8], rax
0x1800740c9  lea     rax, [rbp+0AD0h+Buf2]
0x1800740cd  mov     [rsp+0BD0h+var_BB0], rax
0x1800740d2  lea     rdx, qword_18010CF68
0x1800740d9  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1800740de  jmp     short loc_180074126
0x1800740e0  mov     ecx, [rsp+0BD0h+var_B78]; unsigned int
0x1800740e4  call    ?DeleteCachedLastInputTimeForSession@CHelper@@SAJK@Z; CHelper::DeleteCachedLastInputTimeForSession(ulong)
0x1800740e9  mov     eax, cs:dword_180128170
0x1800740ef  cmp     eax, 4
0x1800740f2  jbe     short loc_180074126
0x1800740f4  movsxd  rax, [rsp+0BD0h+var_B78]
0x1800740f9  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x1800740fd  lea     rax, aSuccessfullyRe; "Successfully reset last input time succ"...
0x180074104  mov     qword ptr [rbp+0AD0h+Buf2], rax
0x180074108  lea     rax, [rbp+0AD0h+var_B28]
0x18007410c  mov     [rsp+0BD0h+var_BA8], rax
0x180074111  lea     rax, [rbp+0AD0h+Buf2]
0x180074115  mov     [rsp+0BD0h+var_BB0], rax
0x18007411a  lea     rdx, word_18010CF3A
0x180074121  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &)
0x180074126  lea     r13, aCdefaultconnec; "CDefaultConnectionHandler::AttemptAutoR"...
0x18007412d  lea     rcx, [rbp+0AD0h+var_B40]; struct IRemoteConnectionManager **
0x180074131  call    ?GetInstanceOfRemoteConnectionManager@@YAJPEAPEAVIRemoteConnectionManager@@@Z; GetInstanceOfRemoteConnectionManager(IRemoteConnectionManager * *)
0x180074136  mov     ebx, eax
0x180074138  test    eax, eax
0x18007413a  jns     short loc_180074169
0x18007413c  mov     eax, cs:dword_180128170
0x180074142  cmp     eax, 3
0x180074145  jbe     loc_1800742F4
0x18007414b  lea     rax, aAttemptautorec; "AttemptAutoReconnect"
0x180074152  mov     qword ptr [rbp+0AD0h+var_B28], rax
0x180074156  lea     rax, aGetinstanceofr_2; "GetInstanceOfRemoteConnectionManager"
0x18007415d  lea     rdx, byte_18010CEFD
0x180074164  jmp     loc_1800742B7
0x180074169  mov     rcx, [rbp+0AD0h+var_B40]
0x18007416d  mov     rax, [rcx]
0x180074170  lea     rdx, [rbp+0AD0h+var_B38]
  ... truncated ...
```
