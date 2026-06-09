# CConnectionEx::ProcessData(ITSLicense *)

- ea: `0x180086d90`
- end: `0x18008757a`
- name: `?ProcessData@CConnectionEx@@UEAAJPEAVITSLicense@@@Z`
- size: `2026`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct ITSLicense *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001294`
- `0x1800016a8`
- `0x18000c2a0`
- `0x1800139c0`
- `0x1800143e4`
- `0x1800146c8`
- `0x180015310`
- `0x18002558c`
- `0x180033f60`
- `0x180034e64`
- `0x180083a00`
- `0x180083c20`
- `0x180086d90`
- `0x180087ef0`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180087109`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008712a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008712a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180087273`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800873c8`

## string_xrefs

- `0x1800874bd`: `Task completed successfully`
- `0x180086e0d`: `Processing license for new incoming connection`
- `0x180086e89`: `this->ptrIWRdsProtocolConnection->GetLicenseConnection`
- `0x180086f4a`: `GetDeviceIdFromProtocolContext failed, using null (Bug 15139482)`
- `0x180086fbf`: `Licensing State: Licensing protocol completed`
- `0x180087019`: `ProtocolComplete`
- `0x180087432`: `FAILED to save protocol context in connection object`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CConnectionEx::ProcessData(CConnectionEx *this, struct ITSLicense *a2)
{
  int v4; // r8d
  int v5; // r9d
  int v6; // ebx
  int v7; // r8d
  int v8; // r9d
  char *v9; // rcx
  struct IRemoteConnectionManager **v10; // rax
  __int16 *v11; // rdx
  int v12; // eax
  int v13; // r8d
  int v14; // r9d
  int v15; // eax
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  const char *v19; // rax
  int v20; // eax
  void *v21; // rbx
  int v22; // ecx
  int v23; // ecx
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  struct IRemoteConnectionManager **v31; // [rsp+28h] [rbp-81h]
  const char **v32; // [rsp+38h] [rbp-71h]
  const char *v33; // [rsp+40h] [rbp-69h] BYREF
  const char *v34; // [rsp+48h] [rbp-61h] BYREF
  struct IRemoteConnectionManager *v35; // [rsp+50h] [rbp-59h] BYREF
  const char *v36; // [rsp+58h] [rbp-51h] BYREF
  unsigned int NextProtocolState; // [rsp+60h] [rbp-49h] BYREF
  SIZE_T cb; // [rsp+64h] [rbp-45h] BYREF
  unsigned int v39; // [rsp+6Ch] [rbp-3Dh] BYREF
  LPVOID v40; // [rsp+70h] [rbp-39h] BYREF
  __int64 v41; // [rsp+78h] [rbp-31h] BYREF
  LPVOID pv; // [rsp+80h] [rbp-29h] BYREF
  int v43; // [rsp+88h] [rbp-21h] BYREF
  int v44; // [rsp+8Ch] [rbp-1Dh] BYREF
  _DWORD v45[3]; // [rsp+90h] [rbp-19h] BYREF
  int v46; // [rsp+9Ch] [rbp-Dh]
  int v47; // [rsp+A0h] [rbp-9h]
  __int128 v48; // [rsp+A4h] [rbp-5h]
  _BYTE v49[26]; // [rsp+B4h] [rbp+Bh]

  NextProtocolState = 0;
  cb = 0;
  v39 = 262;
  v40 = 0;
  pv = 0;
  v43 = 0;
  memset_0(v45, 0, 0x40u);
  v44 = 64;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    v35 = (struct IRemoteConnectionManager *)"Processing license for new incoming connection";
    v34 = "CConnectionEx::ProcessData";
    v36 = "Licensing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CConnectionEx::ProcessData",
      (unsigned int)byte_1801149FD,
      v4,
      v5,
      (__int64)&v36,
      (__int64)&v34,
      (__int64)&v35);
  }
  NextProtocolState = 1;
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(**((_QWORD **)this + 199) + 64LL))(*((_QWORD *)this + 199), &v41);
  if ( v6 >= 0 )
  {
    if ( NextProtocolState == 8 )
      goto LABEL_68;
    while ( 1 )
    {
      v6 = (*(__int64 (__fastcall **)(struct ITSLicense *, LPVOID *, SIZE_T *, LPVOID *, char *, unsigned int *, unsigned int *))(*(_QWORD *)a2 + 24LL))(
             a2,
             &pv,
             &cb,
             &v40,
             (char *)&cb + 4,
             &NextProtocolState,
             &v39);
      if ( v6 < 0 )
      {
        if ( (unsigned int)dword_18012E170 <= 3 )
          goto LABEL_68;
        v19 = "ProcessData";
        v33 = "ProcessData";
        v11 = (__int16 *)byte_18011498D;
        goto LABEL_66;
      }
      v43 = 261;
      v12 = (*(__int64 (__fastcall **)(struct ITSLicense *, char *, int *))(*(_QWORD *)a2 + 48LL))(
              a2,
              (char *)this + 17344,
              &v43);
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_18012E170 > 4 )
        {
          LODWORD(v34) = v12;
          v33 = "GetDeviceIdFromProtocolContext failed, using null (Bug 15139482)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_18012E170,
            (unsigned int)word_18011496A,
            v13,
            v14,
            (__int64)&v33,
            (__int64)&v34);
        }
        memset_0((char *)this + 17344, 0, 0x20Au);
      }
      v15 = CConnectionEx::GetIoctlCode(this, NextProtocolState) - 3670295;
      if ( !v15 )
        break;
      v17 = v15 - 4;
      if ( v17 )
      {
        v18 = v17 - 4;
        if ( v18 )
        {
          if ( v18 != 4 )
          {
            v6 = -2147467263;
            goto LABEL_68;
          }
          if ( (unsigned int)dword_18012E170 > 4 )
          {
            v33 = "Licensing State: Licensing protocol completed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v16,
              (unsigned int)word_180114812,
              v7,
              v8,
              (__int64)&v33);
          }
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 48LL))(v41, *(unsigned int *)v40);
          if ( v6 < 0 )
          {
            if ( (unsigned int)dword_18012E170 <= 3 )
              goto LABEL_68;
            v33 = "ProcessData";
            v19 = "ProtocolComplete";
            v11 = word_1801147DA;
LABEL_66:
            v36 = v19;
            v35 = (struct IRemoteConnectionManager *)"Warning HResult failed";
            v32 = &v33;
            v31 = (struct IRemoteConnectionManager **)&v36;
            v10 = &v35;
            goto LABEL_67;
          }
        }
        else
        {
          if ( (unsigned int)dword_18012E170 > 4 )
          {
            v33 = "Licensing State: Send client license";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v16,
              (unsigned int)&word_1801148BE,
              v7,
              v8,
              (__int64)&v33);
          }
          v6 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD))(*(_QWORD *)v41 + 32LL))(v41, v40, HIDWORD(cb));
          if ( v6 < 0 )
          {
            if ( (unsigned int)dword_18012E170 <= 3 )
              goto LABEL_68;
            v33 = "ProcessData";
            v19 = "SendClientLicense";
            v11 = &word_180114886;
            goto LABEL_66;
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_18012E170 > 4 )
        {
          v33 = "Licensing State: Request client license";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v16,
            (unsigned int)qword_180114868,
            v7,
            v8,
            (__int64)&v33);
        }
        v20 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, LPVOID, SIZE_T *))(*(_QWORD *)v41 + 40LL))(
                v41,
                v40,
                HIDWORD(cb),
                pv,
                &cb);
        v6 = v20;
        if ( v20 == -805306333 || v20 == -2147024774 )
        {
          v21 = CoTaskMemAlloc((unsigned int)cb);
          if ( !v21 )
          {
            v6 = -2147024882;
            goto LABEL_68;
          }
          if ( pv )
            CoTaskMemFree(pv);
          pv = v21;
          v6 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD, void *, SIZE_T *))(*(_QWORD *)v41 + 40LL))(
                 v41,
                 v40,
                 HIDWORD(cb),
                 v21,
                 &cb);
        }
        if ( v6 < 0 )
        {
          if ( (unsigned int)dword_18012E170 <= 3 )
            goto LABEL_68;
          v33 = "ProcessData";
          v19 = "RequestClientLicense";
          v11 = (__int16 *)qword_180114830;
          goto LABEL_66;
        }
      }
LABEL_50:
      v22 = (int)v40;
      if ( v40 )
      {
        CoTaskMemFree(v40);
        v40 = 0;
      }
      if ( v39 )
      {
        if ( (unsigned int)dword_18012E170 > 2 )
        {
          LODWORD(v34) = v39;
          v33 = "TLS Licensing error, reject connection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_1801147B1,
            v7,
            v8,
            (__int64)&v33,
            (__int64)&v34);
        }
        v6 = -2147467260;
        goto LABEL_68;
      }
      NextProtocolState = CConnectionEx::GetNextProtocolState(this, NextProtocolState);
      if ( NextProtocolState == 8 )
        goto LABEL_68;
    }
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v33 = "Licensing State: Query Client Licensing capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)&dword_18011494C,
        v7,
        v8,
        (__int64)&v33);
    }
    memset_0(v45, 0, 0x40u);
    v47 = 42;
    v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *, int *))(*(_QWORD *)v41 + 24LL))(v41, v45, &v44);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_68;
      v33 = "ProcessData";
      v19 = "RequestLicensingCapabilities";
      v11 = (__int16 *)&dword_180114914;
      goto LABEL_66;
    }
    v9 = (char *)pv;
    if ( !pv )
    {
      v6 = -2147024809;
      if ( (unsigned int)dword_18012E170 <= 3 )
        goto LABEL_68;
      v33 = "ProcessData";
      v19 = "CWTSConvert::WTSConvertLicenseCapabilities";
      v11 = (__int16 *)&dword_1801148DC;
      goto LABEL_66;
    }
    *(_DWORD *)pv = v45[0];
    *((_DWORD *)v9 + 1) = v45[1];
    *((_DWORD *)v9 + 2) = v45[2];
    if ( v46 )
    {
      if ( v46 == 1 )
      {
        *((_DWORD *)v9 + 3) = 1;
        goto LABEL_47;
      }
      if ( v46 == 2 )
      {
        *((_DWORD *)v9 + 3) = 2;
LABEL_47:
        if ( v9 != (char *)-20LL )
        {
          *((_DWORD *)v9 + 4) = 42;
          *(_OWORD *)(v9 + 20) = v48;
          *(_OWORD *)(v9 + 36) = *(_OWORD *)v49;
          *(_OWORD *)(v9 + 46) = *(_OWORD *)&v49[10];
        }
        LODWORD(cb) = 64;
        v6 = 0;
        goto LABEL_50;
      }
    }
    *((_DWORD *)v9 + 3) = 0;
    goto LABEL_47;
  }
  LODWORD(v9) = dword_18012E170;
  if ( (unsigned int)dword_18012E170 > 3 )
  {
    v36 = "ProcessData";
    v35 = (struct IRemoteConnectionManager *)"this->ptrIWRdsProtocolConnection->GetLicenseConnection";
    v33 = "Warning HResult failed";
    v32 = &v36;
    v31 = &v35;
    v10 = (struct IRemoteConnectionManager **)&v33;
    v11 = (__int16 *)byte_1801149C5;
LABEL_67:
    LODWORD(v34) = v6;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
      (_DWORD)v9,
      (_DWORD)v11,
      v7,
      v8,
      (__int64)v10,
      (__int64)v31,
      (__int64)&v34,
      (__int64)v32);
  }
LABEL_68:
  if ( pv )
    CoTaskMemFree(pv);
  v23 = (int)v40;
  if ( v40 )
    CoTaskMemFree(v40);
  if ( v6 < 0 )
  {
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      LODWORD(v34) = v6;
      v33 = "CConnectionEx::ProcessData";
      v36 = "Licensing";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&dword_18011473C,
        v7,
        v8,
        (__int64)&v36,
        (__int64)&v33,
        (__int64)&v34);
    }
    CConnectionEx::SetErrorInfo(this, v39, 0);
  }
  else
  {
    v35 = 0;
    v34 = 0;
    if ( ((int)GetInstanceOfRemoteConnectionManager(&v35) < 0
       || (*(int (__fastcall **)(struct IRemoteConnectionManager *, const char **))(*(_QWORD *)v35 + 72LL))(v35, &v34) < 0
       || (*(int (__fastcall **)(const char *, struct ITSLicense *, char *))(*(_QWORD *)v34 + 72LL))(
            v34,
            a2,
            (char *)this + 17336) < 0)
      && (unsigned int)dword_18012E170 > 3 )
    {
      v33 = "FAILED to save protocol context in connection object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_180114793,
        v25,
        v26,
        (__int64)&v33);
    }
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v33 = "Delay_User_Authentication: NotifyUserAuthenticated NOT called here";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_180114775,
        v25,
        v26,
        (__int64)&v33);
    }
    SmartPtr<ITerminal>::operator=((char *)this + 17304, a2);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v34);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v35);
    if ( (unsigned int)dword_18012E170 > 5 )
    {
      LODWORD(v34) = v6;
      v33 = "CConnectionEx::ProcessData";
      v36 = "Task completed successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)byte_18011470B,
        v28,
        v29,
        (__int64)&v36,
        (__int64)&v33,
        (__int64)&v34);
    }
  }
  SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v41);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180086d90  mov     [rsp-8+arg_10], rbx
0x180086d95  push    rbp
0x180086d96  push    rsi
0x180086d97  push    rdi
0x180086d98  push    r13
0x180086d9a  push    r14
0x180086d9c  lea     rbp, [rsp-37h]
0x180086da1  sub     rsp, 0E0h
0x180086da8  mov     rax, cs:__security_cookie
0x180086daf  xor     rax, rsp
0x180086db2  mov     [rbp+57h+var_30], rax
0x180086db6  mov     rsi, rdx
0x180086db9  mov     rdi, rcx
0x180086dbc  xor     r14d, r14d
0x180086dbf  mov     [rbp+57h+var_A0], r14d
0x180086dc3  mov     dword ptr [rbp+57h+cb+4], r14d
0x180086dc7  mov     dword ptr [rbp+57h+cb], r14d
0x180086dcb  mov     [rbp+57h+var_94], 106h
0x180086dd2  mov     [rbp+57h+var_90], r14
0x180086dd6  mov     [rbp+57h+pv], r14
0x180086dda  mov     [rbp+57h+var_78], r14d
0x180086dde  lea     r13d, [r14+40h]
0x180086de2  mov     r8d, r13d; Size
0x180086de5  xor     edx, edx; Val
0x180086de7  lea     rcx, [rbp+57h+var_70]; void *
0x180086deb  call    memset_0
0x180086df0  mov     [rbp+57h+var_74], r13d
0x180086df4  mov     eax, cs:dword_18012E170
0x180086dfa  lea     rcx, aCconnectionexP; "CConnectionEx::ProcessData"
0x180086e01  lea     rdx, aLicensing; "Licensing"
0x180086e08  cmp     eax, 4
0x180086e0b  jbe     short loc_180086E47
0x180086e0d  lea     rax, aProcessingLice; "Processing license for new incoming con"...
0x180086e14  mov     [rbp+57h+var_B0], rax
0x180086e18  mov     [rbp+57h+var_B8], rcx
0x180086e1c  mov     [rbp+57h+var_A8], rdx
0x180086e20  lea     rax, [rbp+57h+var_B0]
0x180086e24  mov     [rsp+100h+var_D0], rax
0x180086e29  lea     rax, [rbp+57h+var_B8]
0x180086e2d  mov     [rsp+100h+var_D8], rax
0x180086e32  lea     rax, [rbp+57h+var_A8]
0x180086e36  mov     [rsp+100h+var_E0], rax
0x180086e3b  lea     rdx, byte_1801149FD
0x180086e42  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180086e47  mov     [rbp+57h+var_A0], 1
0x180086e4e  mov     [rbp+57h+var_88], r14
0x180086e52  mov     rcx, [rdi+638h]
0x180086e59  mov     rax, [rcx]
0x180086e5c  lea     rdx, [rbp+57h+var_88]
0x180086e60  mov     rax, [rax+40h]
0x180086e64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086e69  mov     ebx, eax
0x180086e6b  test    eax, eax
0x180086e6d  jns     short loc_180086ECA
0x180086e6f  mov     ecx, cs:dword_18012E170
0x180086e75  cmp     ecx, 3
0x180086e78  jbe     loc_1800873AA
0x180086e7e  lea     rax, aProcessdata; "ProcessData"
0x180086e85  mov     [rbp+57h+var_A8], rax
0x180086e89  lea     rax, aThisPtriwrdspr_9; "this->ptrIWRdsProtocolConnection->GetLi"...
0x180086e90  mov     [rbp+57h+var_B0], rax
0x180086e94  lea     rax, aWarningHresult; "Warning HResult failed"
0x180086e9b  mov     [rbp+57h+var_C0], rax
0x180086e9f  lea     rax, [rbp+57h+var_A8]
0x180086ea3  mov     [rsp+100h+var_C8], rax
0x180086ea8  lea     rax, [rbp+57h+var_B8]
0x180086eac  mov     [rsp+100h+var_D0], rax
0x180086eb1  lea     rax, [rbp+57h+var_B0]
0x180086eb5  mov     [rsp+100h+var_D8], rax
0x180086eba  lea     rax, [rbp+57h+var_C0]
0x180086ebe  lea     rdx, byte_1801149C5
0x180086ec5  jmp     loc_18008739D
0x180086eca  cmp     [rbp+57h+var_A0], 8
0x180086ece  jz      loc_1800873AA
0x180086ed4  mov     rax, [rsi]
0x180086ed7  lea     rcx, [rbp+57h+var_94]
0x180086edb  mov     [rsp+100h+var_D0], rcx
0x180086ee0  lea     rcx, [rbp+57h+var_A0]
0x180086ee4  mov     [rsp+100h+var_D8], rcx
0x180086ee9  lea     rcx, [rbp+57h+cb+4]
0x180086eed  mov     [rsp+100h+var_E0], rcx
0x180086ef2  lea     r9, [rbp+57h+var_90]
0x180086ef6  lea     r8, [rbp+57h+cb]
0x180086efa  lea     rdx, [rbp+57h+pv]
0x180086efe  mov     rcx, rsi
0x180086f01  mov     rax, [rax+18h]
0x180086f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f0a  mov     ebx, eax
0x180086f0c  test    eax, eax
0x180086f0e  js      loc_180087352
0x180086f14  mov     [rbp+57h+var_78], 105h
0x180086f1b  lea     rbx, [rdi+43C0h]
0x180086f22  mov     rax, [rsi]
0x180086f25  lea     r8, [rbp+57h+var_78]
0x180086f29  mov     rdx, rbx
0x180086f2c  mov     rcx, rsi
0x180086f2f  mov     rax, [rax+30h]
0x180086f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086f38  test    eax, eax
0x180086f3a  jns     short loc_180086F83
0x180086f3c  mov     ecx, cs:dword_18012E170
0x180086f42  cmp     ecx, 4
0x180086f45  jbe     short loc_180086F73
0x180086f47  mov     dword ptr [rbp+57h+var_B8], eax
0x180086f4a  lea     rax, aGetdeviceidfro; "GetDeviceIdFromProtocolContext failed, "...
0x180086f51  mov     [rbp+57h+var_C0], rax
0x180086f55  lea     rax, [rbp+57h+var_B8]
0x180086f59  mov     [rsp+100h+var_D8], rax
0x180086f5e  lea     rax, [rbp+57h+var_C0]
0x180086f62  mov     [rsp+100h+var_E0], rax
0x180086f67  lea     rdx, word_18011496A
0x180086f6e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180086f73  xor     edx, edx; Val
0x180086f75  mov     r8d, 20Ah; Size
0x180086f7b  mov     rcx, rbx; void *
0x180086f7e  call    memset_0
0x180086f83  mov     edx, [rbp+57h+var_A0]
0x180086f86  mov     rcx, rdi
0x180086f89  call    ?GetIoctlCode@CConnectionEx@@UEAAKW4TSLicenseState@@@Z; CConnectionEx::GetIoctlCode(TSLicenseState)
0x180086f8e  sub     eax, 380117h
0x180086f93  jz      loc_180087195
0x180086f99  sub     eax, 4
0x180086f9c  jz      loc_1800870A6
0x180086fa2  sub     eax, 4
0x180086fa5  jz      loc_18008702C
0x180086fab  cmp     eax, 4
0x180086fae  jnz     loc_1800872A5
0x180086fb4  mov     eax, cs:dword_18012E170
0x180086fba  cmp     eax, 4
0x180086fbd  jbe     short loc_180086FDF
0x180086fbf  lea     rax, aLicensingState_2; "Licensing State: Licensing protocol com"...
0x180086fc6  mov     [rbp+57h+var_C0], rax
0x180086fca  lea     rax, [rbp+57h+var_C0]
0x180086fce  mov     [rsp+100h+var_E0], rax
0x180086fd3  lea     rdx, word_180114812
0x180086fda  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180086fdf  mov     rcx, [rbp+57h+var_88]
0x180086fe3  mov     rax, [rcx]
0x180086fe6  mov     rdx, [rbp+57h+var_90]
0x180086fea  mov     edx, [rdx]
0x180086fec  mov     rax, [rax+30h]
0x180086ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180086ff5  mov     ebx, eax
0x180086ff7  test    eax, eax
0x180086ff9  jns     loc_18008726A
0x180086fff  mov     eax, cs:dword_18012E170
0x180087005  cmp     eax, 3
0x180087008  jbe     loc_1800873AA
0x18008700e  lea     rax, aProcessdata; "ProcessData"
0x180087015  mov     [rbp+57h+var_C0], rax
0x180087019  lea     rax, aProtocolcomple; "ProtocolComplete"
0x180087020  lea     rdx, word_1801147DA
0x180087027  jmp     loc_18008736F
0x18008702c  mov     eax, cs:dword_18012E170
0x180087032  cmp     eax, 4
0x180087035  jbe     short loc_180087057
0x180087037  lea     rax, aLicensingState_1; "Licensing State: Send client license"
0x18008703e  mov     [rbp+57h+var_C0], rax
0x180087042  lea     rax, [rbp+57h+var_C0]
0x180087046  mov     [rsp+100h+var_E0], rax
0x18008704b  lea     rdx, word_1801148BE
0x180087052  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180087057  mov     rcx, [rbp+57h+var_88]
0x18008705b  mov     rax, [rcx]
0x18008705e  mov     r8d, dword ptr [rbp+57h+cb+4]
0x180087062  mov     rdx, [rbp+57h+var_90]
0x180087066  mov     rax, [rax+20h]
0x18008706a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008706f  mov     ebx, eax
0x180087071  test    eax, eax
0x180087073  jns     loc_18008726A
0x180087079  mov     eax, cs:dword_18012E170
0x18008707f  cmp     eax, 3
0x180087082  jbe     loc_1800873AA
0x180087088  lea     rax, aProcessdata; "ProcessData"
0x18008708f  mov     [rbp+57h+var_C0], rax
0x180087093  lea     rax, aSendclientlice; "SendClientLicense"
0x18008709a  lea     rdx, word_180114886
0x1800870a1  jmp     loc_18008736F
0x1800870a6  mov     eax, cs:dword_18012E170
0x1800870ac  cmp     eax, 4
0x1800870af  jbe     short loc_1800870D1
0x1800870b1  lea     rax, aLicensingState_0; "Licensing State: Request client license"
0x1800870b8  mov     [rbp+57h+var_C0], rax
0x1800870bc  lea     rax, [rbp+57h+var_C0]
0x1800870c0  mov     [rsp+100h+var_E0], rax
0x1800870c5  lea     rdx, qword_180114868
0x1800870cc  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800870d1  mov     rcx, [rbp+57h+var_88]
0x1800870d5  mov     rax, [rcx]
0x1800870d8  lea     rdx, [rbp+57h+cb]
0x1800870dc  mov     [rsp+100h+var_E0], rdx
0x1800870e1  mov     r9, [rbp+57h+pv]
0x1800870e5  mov     r8d, dword ptr [rbp+57h+cb+4]
0x1800870e9  mov     rdx, [rbp+57h+var_90]
0x1800870ed  mov     rax, [rax+28h]
0x1800870f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800870f6  mov     ebx, eax
0x1800870f8  cmp     eax, 0D0000023h
0x1800870fd  jz      short loc_180087106
0x1800870ff  cmp     eax, 8007007Ah
0x180087104  jnz     short loc_180087160
0x180087106  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x180087109  call    cs:__imp_CoTaskMemAlloc
0x180087110  nop     dword ptr [rax+rax+00h]
0x180087115  mov     rbx, rax
0x180087118  test    rax, rax
0x18008711b  jz      loc_1800872AF
0x180087121  mov     rcx, [rbp+57h+pv]; pv
0x180087125  test    rcx, rcx
0x180087128  jz      short loc_180087136
0x18008712a  call    cs:__imp_CoTaskMemFree
0x180087131  nop     dword ptr [rax+rax+00h]
0x180087136  mov     [rbp+57h+pv], rbx
0x18008713a  mov     rcx, [rbp+57h+var_88]
0x18008713e  mov     rax, [rcx]
0x180087141  lea     rdx, [rbp+57h+cb]
0x180087145  mov     [rsp+100h+var_E0], rdx
0x18008714a  mov     r9, rbx
0x18008714d  mov     r8d, dword ptr [rbp+57h+cb+4]
0x180087151  mov     rdx, [rbp+57h+var_90]
0x180087155  mov     rax, [rax+28h]
0x180087159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008715e  mov     ebx, eax
0x180087160  test    ebx, ebx
0x180087162  jns     loc_18008726A
0x180087168  mov     eax, cs:dword_18012E170
0x18008716e  cmp     eax, 3
0x180087171  jbe     loc_1800873AA
0x180087177  lea     rax, aProcessdata; "ProcessData"
0x18008717e  mov     [rbp+57h+var_C0], rax
0x180087182  lea     rax, aRequestclientl; "RequestClientLicense"
0x180087189  lea     rdx, qword_180114830
0x180087190  jmp     loc_18008736F
0x180087195  mov     eax, cs:dword_18012E170
0x18008719b  cmp     eax, 4
0x18008719e  jbe     short loc_1800871C0
0x1800871a0  lea     rax, aLicensingState; "Licensing State: Query Client Licensing"...
0x1800871a7  mov     [rbp+57h+var_C0], rax
0x1800871ab  lea     rax, [rbp+57h+var_C0]
0x1800871af  mov     [rsp+100h+var_E0], rax
0x1800871b4  lea     rdx, dword_18011494C
0x1800871bb  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x1800871c0  mov     r8, r13; Size
0x1800871c3  xor     edx, edx; Val
0x1800871c5  lea     rcx, [rbp+57h+var_70]; void *
0x1800871c9  call    memset_0
0x1800871ce  mov     [rbp+57h+var_60], 2Ah ; '*'
0x1800871d5  mov     rcx, [rbp+57h+var_88]
0x1800871d9  mov     rax, [rcx]
0x1800871dc  lea     r8, [rbp+57h+var_74]
0x1800871e0  lea     rdx, [rbp+57h+var_70]
0x1800871e4  mov     rax, [rax+18h]
0x1800871e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800871ed  mov     ebx, eax
0x1800871ef  test    eax, eax
0x1800871f1  js      loc_18008732C
0x1800871f7  mov     rcx, [rbp+57h+pv]
0x1800871fb  test    rcx, rcx
0x1800871fe  jz      loc_1800872FD
0x180087204  mov     eax, [rbp+57h+var_70]
0x180087207  mov     [rcx], eax
0x180087209  mov     eax, [rbp+57h+var_6C]
0x18008720c  mov     [rcx+4], eax
0x18008720f  mov     eax, [rbp+57h+var_68]
0x180087212  mov     [rcx+8], eax
0x180087215  mov     edx, [rbp+57h+var_64]
0x180087218  test    edx, edx
0x18008721a  jz      short loc_180087238
0x18008721c  sub     edx, 1
0x18008721f  jz      short loc_18008722F
0x180087221  cmp     edx, 1
0x180087224  jnz     short loc_180087238
0x180087226  mov     dword ptr [rcx+0Ch], 2
0x18008722d  jmp     short loc_18008723C
0x18008722f  mov     dword ptr [rcx+0Ch], 1
0x180087236  jmp     short loc_18008723C
0x180087238  mov     [rcx+0Ch], r14d
0x18008723c  lea     rax, [rcx+14h]
0x180087240  test    rax, rax
0x180087243  jz      short loc_180087263
0x180087245  mov     dword ptr [rcx+10h], 2Ah ; '*'
0x18008724c  movups  xmm0, [rbp+57h+var_5C]
0x180087250  movups  xmmword ptr [rax], xmm0
0x180087253  movups  xmm1, xmmword ptr [rbp+57h+var_4C]
0x180087257  movups  xmmword ptr [rax+10h], xmm1
0x18008725b  movups  xmm0, xmmword ptr [rbp+57h+var_4C+0Ah]
0x18008725f  movups  xmmword ptr [rax+1Ah], xmm0
0x180087263  mov     dword ptr [rbp+57h+cb], r13d
0x180087267  mov     ebx, r14d
0x18008726a  mov     rcx, [rbp+57h+var_90]; pv
0x18008726e  test    rcx, rcx
0x180087271  jz      short loc_180087283
0x180087273  call    cs:__imp_CoTaskMemFree
0x18008727a  nop     dword ptr [rax+rax+00h]
0x18008727f  mov     [rbp+57h+var_90], r14
0x180087283  cmp     [rbp+57h+var_94], r14d
0x180087287  jnz     short loc_1800872B9
0x180087289  mov     edx, [rbp+57h+var_A0]
0x18008728c  mov     rcx, rdi
  ... truncated ...
```
