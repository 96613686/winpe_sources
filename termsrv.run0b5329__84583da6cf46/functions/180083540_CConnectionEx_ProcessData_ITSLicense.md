# CConnectionEx::ProcessData(ITSLicense *)

- ea: `0x180083540`
- end: `0x180083d0b`
- name: `?ProcessData@CConnectionEx@@UEAAJPEAVITSLicense@@@Z`
- size: `1995`
- prototype: `__int64 __fastcall(CConnectionEx *__hidden this, struct ITSLicense *)`
- caller_count: `0`
- callee_count: `15`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180001284`
- `0x180001688`
- `0x18000c2f0`
- `0x180013150`
- `0x180013a18`
- `0x180013d00`
- `0x1800148f0`
- `0x1800241f0`
- `0x1800321f0`
- `0x1800330c4`
- `0x180080250`
- `0x180080460`
- `0x180083540`
- `0x180084670`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800838b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800838b9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800838d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b60`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800838d4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083a17`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180083b60`

## string_xrefs

- `0x180083c4f`: `Task completed successfully`
- `0x1800835bd`: `Processing license for new incoming connection`
- `0x180083639`: `this->ptrIWRdsProtocolConnection->GetLicenseConnection`
- `0x1800836fa`: `GetDeviceIdFromProtocolContext failed, using null (Bug 15139482)`
- `0x18008376f`: `Licensing State: Licensing protocol completed`
- `0x1800837c9`: `ProtocolComplete`
- `0x180083bc4`: `FAILED to save protocol context in connection object`

## pseudocode

```c
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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    v35 = (struct IRemoteConnectionManager *)"Processing license for new incoming connection";
    v34 = "CConnectionEx::ProcessData";
    v36 = "Licensing";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      (unsigned int)"CConnectionEx::ProcessData",
      (unsigned int)byte_18010E97D,
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
        if ( (unsigned int)dword_180128170 <= 3 )
          goto LABEL_68;
        v19 = "ProcessData";
        v33 = "ProcessData";
        v11 = (__int16 *)byte_18010E90D;
        goto LABEL_66;
      }
      v43 = 261;
      v12 = (*(__int64 (__fastcall **)(struct ITSLicense *, char *, int *))(*(_QWORD *)a2 + 48LL))(
              a2,
              (char *)this + 17344,
              &v43);
      if ( v12 < 0 )
      {
        if ( (unsigned int)dword_180128170 > 4 )
        {
          LODWORD(v34) = v12;
          v33 = "GetDeviceIdFromProtocolContext failed, using null (Bug 15139482)";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            dword_180128170,
            (unsigned int)word_18010E8EA,
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
          if ( (unsigned int)dword_180128170 > 4 )
          {
            v33 = "Licensing State: Licensing protocol completed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v16,
              (unsigned int)word_18010E792,
              v7,
              v8,
              (__int64)&v33);
          }
          v6 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v41 + 48LL))(v41, *(unsigned int *)v40);
          if ( v6 < 0 )
          {
            if ( (unsigned int)dword_180128170 <= 3 )
              goto LABEL_68;
            v33 = "ProcessData";
            v19 = "ProtocolComplete";
            v11 = word_18010E75A;
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
          if ( (unsigned int)dword_180128170 > 4 )
          {
            v33 = "Licensing State: Send client license";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
              v16,
              (unsigned int)&word_18010E83E,
              v7,
              v8,
              (__int64)&v33);
          }
          v6 = (*(__int64 (__fastcall **)(__int64, LPVOID, _QWORD))(*(_QWORD *)v41 + 32LL))(v41, v40, HIDWORD(cb));
          if ( v6 < 0 )
          {
            if ( (unsigned int)dword_180128170 <= 3 )
              goto LABEL_68;
            v33 = "ProcessData";
            v19 = "SendClientLicense";
            v11 = &word_18010E806;
            goto LABEL_66;
          }
        }
      }
      else
      {
        if ( (unsigned int)dword_180128170 > 4 )
        {
          v33 = "Licensing State: Request client license";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v16,
            (unsigned int)qword_18010E7E8,
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
          if ( (unsigned int)dword_180128170 <= 3 )
            goto LABEL_68;
          v33 = "ProcessData";
          v19 = "RequestClientLicense";
          v11 = (__int16 *)qword_18010E7B0;
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
        if ( (unsigned int)dword_180128170 > 2 )
        {
          LODWORD(v34) = v39;
          v33 = "TLS Licensing error, reject connection";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            v22,
            (unsigned int)byte_18010E731,
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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v33 = "Licensing State: Query Client Licensing capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v16,
        (unsigned int)&dword_18010E8CC,
        v7,
        v8,
        (__int64)&v33);
    }
    memset_0(v45, 0, 0x40u);
    v47 = 42;
    v6 = (*(__int64 (__fastcall **)(__int64, _DWORD *, int *))(*(_QWORD *)v41 + 24LL))(v41, v45, &v44);
    if ( v6 < 0 )
    {
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_68;
      v33 = "ProcessData";
      v19 = "RequestLicensingCapabilities";
      v11 = (__int16 *)&dword_18010E894;
      goto LABEL_66;
    }
    v9 = (char *)pv;
    if ( !pv )
    {
      v6 = -2147024809;
      if ( (unsigned int)dword_180128170 <= 3 )
        goto LABEL_68;
      v33 = "ProcessData";
      v19 = "CWTSConvert::WTSConvertLicenseCapabilities";
      v11 = (__int16 *)&dword_18010E85C;
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
  LODWORD(v9) = dword_180128170;
  if ( (unsigned int)dword_180128170 > 3 )
  {
    v36 = "ProcessData";
    v35 = (struct IRemoteConnectionManager *)"this->ptrIWRdsProtocolConnection->GetLicenseConnection";
    v33 = "Warning HResult failed";
    v32 = &v36;
    v31 = &v35;
    v10 = (struct IRemoteConnectionManager **)&v33;
    v11 = (__int16 *)byte_18010E945;
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
    if ( (unsigned int)dword_180128170 > 2 )
    {
      LODWORD(v34) = v6;
      v33 = "CConnectionEx::ProcessData";
      v36 = "Licensing";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&dword_18010E6BC,
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
      && (unsigned int)dword_180128170 > 3 )
    {
      v33 = "FAILED to save protocol context in connection object";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_18010E713,
        v25,
        v26,
        (__int64)&v33);
    }
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v33 = "Delay_User_Authentication: NotifyUserAuthenticated NOT called here";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v24,
        (unsigned int)byte_18010E6F5,
        v25,
        v26,
        (__int64)&v33);
    }
    SmartPtr<ITerminal>::operator=((char *)this + 17304, a2);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v34);
    SmartPtr<CConnectionHandlerItem>::~SmartPtr<CConnectionHandlerItem>(&v35);
    if ( (unsigned int)dword_180128170 > 5 )
    {
      LODWORD(v34) = v6;
      v33 = "CConnectionEx::ProcessData";
      v36 = "Task completed successfully";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v27,
        (unsigned int)byte_18010E68B,
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
0x180083540  mov     [rsp-8+arg_10], rbx
0x180083545  push    rbp
0x180083546  push    rsi
0x180083547  push    rdi
0x180083548  push    r13
0x18008354a  push    r14
0x18008354c  lea     rbp, [rsp-37h]
0x180083551  sub     rsp, 0E0h
0x180083558  mov     rax, cs:__security_cookie
0x18008355f  xor     rax, rsp
0x180083562  mov     [rbp+57h+var_30], rax
0x180083566  mov     rsi, rdx
0x180083569  mov     rdi, rcx
0x18008356c  xor     r14d, r14d
0x18008356f  mov     [rbp+57h+var_A0], r14d
0x180083573  mov     dword ptr [rbp+57h+cb+4], r14d
0x180083577  mov     dword ptr [rbp+57h+cb], r14d
0x18008357b  mov     [rbp+57h+var_94], 106h
0x180083582  mov     [rbp+57h+var_90], r14
0x180083586  mov     [rbp+57h+pv], r14
0x18008358a  mov     [rbp+57h+var_78], r14d
0x18008358e  lea     r13d, [r14+40h]
0x180083592  mov     r8d, r13d; Size
0x180083595  xor     edx, edx; Val
0x180083597  lea     rcx, [rbp+57h+var_70]; void *
0x18008359b  call    memset_0
0x1800835a0  mov     [rbp+57h+var_74], r13d
0x1800835a4  mov     eax, cs:dword_180128170
0x1800835aa  lea     rcx, aCconnectionexP; "CConnectionEx::ProcessData"
0x1800835b1  lea     rdx, aLicensing; "Licensing"
0x1800835b8  cmp     eax, 4
0x1800835bb  jbe     short loc_1800835F7
0x1800835bd  lea     rax, aProcessingLice; "Processing license for new incoming con"...
0x1800835c4  mov     [rbp+57h+var_B0], rax
0x1800835c8  mov     [rbp+57h+var_B8], rcx
0x1800835cc  mov     [rbp+57h+var_A8], rdx
0x1800835d0  lea     rax, [rbp+57h+var_B0]
0x1800835d4  mov     [rsp+100h+var_D0], rax
0x1800835d9  lea     rax, [rbp+57h+var_B8]
0x1800835dd  mov     [rsp+100h+var_D8], rax
0x1800835e2  lea     rax, [rbp+57h+var_A8]
0x1800835e6  mov     [rsp+100h+var_E0], rax
0x1800835eb  lea     rdx, byte_18010E97D
0x1800835f2  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800835f7  mov     [rbp+57h+var_A0], 1
0x1800835fe  mov     [rbp+57h+var_88], r14
0x180083602  mov     rcx, [rdi+638h]
0x180083609  mov     rax, [rcx]
0x18008360c  lea     rdx, [rbp+57h+var_88]
0x180083610  mov     rax, [rax+40h]
0x180083614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083619  mov     ebx, eax
0x18008361b  test    eax, eax
0x18008361d  jns     short loc_18008367A
0x18008361f  mov     ecx, cs:dword_180128170
0x180083625  cmp     ecx, 3
0x180083628  jbe     loc_180083B48
0x18008362e  lea     rax, aProcessdata; "ProcessData"
0x180083635  mov     [rbp+57h+var_A8], rax
0x180083639  lea     rax, aThisPtriwrdspr_9; "this->ptrIWRdsProtocolConnection->GetLi"...
0x180083640  mov     [rbp+57h+var_B0], rax
0x180083644  lea     rax, aWarningHresult; "Warning HResult failed"
0x18008364b  mov     [rbp+57h+var_C0], rax
0x18008364f  lea     rax, [rbp+57h+var_A8]
0x180083653  mov     [rsp+100h+var_C8], rax
0x180083658  lea     rax, [rbp+57h+var_B8]
0x18008365c  mov     [rsp+100h+var_D0], rax
0x180083661  lea     rax, [rbp+57h+var_B0]
0x180083665  mov     [rsp+100h+var_D8], rax
0x18008366a  lea     rax, [rbp+57h+var_C0]
0x18008366e  lea     rdx, byte_18010E945
0x180083675  jmp     loc_180083B3B
0x18008367a  cmp     [rbp+57h+var_A0], 8
0x18008367e  jz      loc_180083B48
0x180083684  mov     rax, [rsi]
0x180083687  lea     rcx, [rbp+57h+var_94]
0x18008368b  mov     [rsp+100h+var_D0], rcx
0x180083690  lea     rcx, [rbp+57h+var_A0]
0x180083694  mov     [rsp+100h+var_D8], rcx
0x180083699  lea     rcx, [rbp+57h+cb+4]
0x18008369d  mov     [rsp+100h+var_E0], rcx
0x1800836a2  lea     r9, [rbp+57h+var_90]
0x1800836a6  lea     r8, [rbp+57h+cb]
0x1800836aa  lea     rdx, [rbp+57h+pv]
0x1800836ae  mov     rcx, rsi
0x1800836b1  mov     rax, [rax+18h]
0x1800836b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836ba  mov     ebx, eax
0x1800836bc  test    eax, eax
0x1800836be  js      loc_180083AF0
0x1800836c4  mov     [rbp+57h+var_78], 105h
0x1800836cb  lea     rbx, [rdi+43C0h]
0x1800836d2  mov     rax, [rsi]
0x1800836d5  lea     r8, [rbp+57h+var_78]
0x1800836d9  mov     rdx, rbx
0x1800836dc  mov     rcx, rsi
0x1800836df  mov     rax, [rax+30h]
0x1800836e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800836e8  test    eax, eax
0x1800836ea  jns     short loc_180083733
0x1800836ec  mov     ecx, cs:dword_180128170
0x1800836f2  cmp     ecx, 4
0x1800836f5  jbe     short loc_180083723
0x1800836f7  mov     dword ptr [rbp+57h+var_B8], eax
0x1800836fa  lea     rax, aGetdeviceidfro; "GetDeviceIdFromProtocolContext failed, "...
0x180083701  mov     [rbp+57h+var_C0], rax
0x180083705  lea     rax, [rbp+57h+var_B8]
0x180083709  mov     [rsp+100h+var_D8], rax
0x18008370e  lea     rax, [rbp+57h+var_C0]
0x180083712  mov     [rsp+100h+var_E0], rax
0x180083717  lea     rdx, word_18010E8EA
0x18008371e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180083723  xor     edx, edx; Val
0x180083725  mov     r8d, 20Ah; Size
0x18008372b  mov     rcx, rbx; void *
0x18008372e  call    memset_0
0x180083733  mov     edx, [rbp+57h+var_A0]
0x180083736  mov     rcx, rdi
0x180083739  call    ?GetIoctlCode@CConnectionEx@@UEAAKW4TSLicenseState@@@Z; CConnectionEx::GetIoctlCode(TSLicenseState)
0x18008373e  sub     eax, 380117h
0x180083743  jz      loc_180083939
0x180083749  sub     eax, 4
0x18008374c  jz      loc_180083856
0x180083752  sub     eax, 4
0x180083755  jz      loc_1800837DC
0x18008375b  cmp     eax, 4
0x18008375e  jnz     loc_180083A43
0x180083764  mov     eax, cs:dword_180128170
0x18008376a  cmp     eax, 4
0x18008376d  jbe     short loc_18008378F
0x18008376f  lea     rax, aLicensingState_2; "Licensing State: Licensing protocol com"...
0x180083776  mov     [rbp+57h+var_C0], rax
0x18008377a  lea     rax, [rbp+57h+var_C0]
0x18008377e  mov     [rsp+100h+var_E0], rax
0x180083783  lea     rdx, word_18010E792
0x18008378a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18008378f  mov     rcx, [rbp+57h+var_88]
0x180083793  mov     rax, [rcx]
0x180083796  mov     rdx, [rbp+57h+var_90]
0x18008379a  mov     edx, [rdx]
0x18008379c  mov     rax, [rax+30h]
0x1800837a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800837a5  mov     ebx, eax
0x1800837a7  test    eax, eax
0x1800837a9  jns     loc_180083A0E
0x1800837af  mov     eax, cs:dword_180128170
0x1800837b5  cmp     eax, 3
0x1800837b8  jbe     loc_180083B48
0x1800837be  lea     rax, aProcessdata; "ProcessData"
0x1800837c5  mov     [rbp+57h+var_C0], rax
0x1800837c9  lea     rax, aProtocolcomple; "ProtocolComplete"
0x1800837d0  lea     rdx, word_18010E75A
0x1800837d7  jmp     loc_180083B0D
0x1800837dc  mov     eax, cs:dword_180128170
0x1800837e2  cmp     eax, 4
0x1800837e5  jbe     short loc_180083807
0x1800837e7  lea     rax, aLicensingState_1; "Licensing State: Send client license"
0x1800837ee  mov     [rbp+57h+var_C0], rax
0x1800837f2  lea     rax, [rbp+57h+var_C0]
0x1800837f6  mov     [rsp+100h+var_E0], rax
0x1800837fb  lea     rdx, word_18010E83E
0x180083802  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180083807  mov     rcx, [rbp+57h+var_88]
0x18008380b  mov     rax, [rcx]
0x18008380e  mov     r8d, dword ptr [rbp+57h+cb+4]
0x180083812  mov     rdx, [rbp+57h+var_90]
0x180083816  mov     rax, [rax+20h]
0x18008381a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008381f  mov     ebx, eax
0x180083821  test    eax, eax
0x180083823  jns     loc_180083A0E
0x180083829  mov     eax, cs:dword_180128170
0x18008382f  cmp     eax, 3
0x180083832  jbe     loc_180083B48
0x180083838  lea     rax, aProcessdata; "ProcessData"
0x18008383f  mov     [rbp+57h+var_C0], rax
0x180083843  lea     rax, aSendclientlice; "SendClientLicense"
0x18008384a  lea     rdx, word_18010E806
0x180083851  jmp     loc_180083B0D
0x180083856  mov     eax, cs:dword_180128170
0x18008385c  cmp     eax, 4
0x18008385f  jbe     short loc_180083881
0x180083861  lea     rax, aLicensingState_0; "Licensing State: Request client license"
0x180083868  mov     [rbp+57h+var_C0], rax
0x18008386c  lea     rax, [rbp+57h+var_C0]
0x180083870  mov     [rsp+100h+var_E0], rax
0x180083875  lea     rdx, qword_18010E7E8
0x18008387c  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180083881  mov     rcx, [rbp+57h+var_88]
0x180083885  mov     rax, [rcx]
0x180083888  lea     rdx, [rbp+57h+cb]
0x18008388c  mov     [rsp+100h+var_E0], rdx
0x180083891  mov     r9, [rbp+57h+pv]
0x180083895  mov     r8d, dword ptr [rbp+57h+cb+4]
0x180083899  mov     rdx, [rbp+57h+var_90]
0x18008389d  mov     rax, [rax+28h]
0x1800838a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800838a6  mov     ebx, eax
0x1800838a8  cmp     eax, 0D0000023h
0x1800838ad  jz      short loc_1800838B6
0x1800838af  cmp     eax, 8007007Ah
0x1800838b4  jnz     short loc_180083904
0x1800838b6  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1800838b9  call    cs:__imp_CoTaskMemAlloc
0x1800838bf  mov     rbx, rax
0x1800838c2  test    rax, rax
0x1800838c5  jz      loc_180083A4D
0x1800838cb  mov     rcx, [rbp+57h+pv]; pv
0x1800838cf  test    rcx, rcx
0x1800838d2  jz      short loc_1800838DA
0x1800838d4  call    cs:__imp_CoTaskMemFree
0x1800838da  mov     [rbp+57h+pv], rbx
0x1800838de  mov     rcx, [rbp+57h+var_88]
0x1800838e2  mov     rax, [rcx]
0x1800838e5  lea     rdx, [rbp+57h+cb]
0x1800838e9  mov     [rsp+100h+var_E0], rdx
0x1800838ee  mov     r9, rbx
0x1800838f1  mov     r8d, dword ptr [rbp+57h+cb+4]
0x1800838f5  mov     rdx, [rbp+57h+var_90]
0x1800838f9  mov     rax, [rax+28h]
0x1800838fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083902  mov     ebx, eax
0x180083904  test    ebx, ebx
0x180083906  jns     loc_180083A0E
0x18008390c  mov     eax, cs:dword_180128170
0x180083912  cmp     eax, 3
0x180083915  jbe     loc_180083B48
0x18008391b  lea     rax, aProcessdata; "ProcessData"
0x180083922  mov     [rbp+57h+var_C0], rax
0x180083926  lea     rax, aRequestclientl; "RequestClientLicense"
0x18008392d  lea     rdx, qword_18010E7B0
0x180083934  jmp     loc_180083B0D
0x180083939  mov     eax, cs:dword_180128170
0x18008393f  cmp     eax, 4
0x180083942  jbe     short loc_180083964
0x180083944  lea     rax, aLicensingState; "Licensing State: Query Client Licensing"...
0x18008394b  mov     [rbp+57h+var_C0], rax
0x18008394f  lea     rax, [rbp+57h+var_C0]
0x180083953  mov     [rsp+100h+var_E0], rax
0x180083958  lea     rdx, dword_18010E8CC
0x18008395f  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180083964  mov     r8, r13; Size
0x180083967  xor     edx, edx; Val
0x180083969  lea     rcx, [rbp+57h+var_70]; void *
0x18008396d  call    memset_0
0x180083972  mov     [rbp+57h+var_60], 2Ah ; '*'
0x180083979  mov     rcx, [rbp+57h+var_88]
0x18008397d  mov     rax, [rcx]
0x180083980  lea     r8, [rbp+57h+var_74]
0x180083984  lea     rdx, [rbp+57h+var_70]
0x180083988  mov     rax, [rax+18h]
0x18008398c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083991  mov     ebx, eax
0x180083993  test    eax, eax
0x180083995  js      loc_180083ACA
0x18008399b  mov     rcx, [rbp+57h+pv]
0x18008399f  test    rcx, rcx
0x1800839a2  jz      loc_180083A9B
0x1800839a8  mov     eax, [rbp+57h+var_70]
0x1800839ab  mov     [rcx], eax
0x1800839ad  mov     eax, [rbp+57h+var_6C]
0x1800839b0  mov     [rcx+4], eax
0x1800839b3  mov     eax, [rbp+57h+var_68]
0x1800839b6  mov     [rcx+8], eax
0x1800839b9  mov     edx, [rbp+57h+var_64]
0x1800839bc  test    edx, edx
0x1800839be  jz      short loc_1800839DC
0x1800839c0  sub     edx, 1
0x1800839c3  jz      short loc_1800839D3
0x1800839c5  cmp     edx, 1
0x1800839c8  jnz     short loc_1800839DC
0x1800839ca  mov     dword ptr [rcx+0Ch], 2
0x1800839d1  jmp     short loc_1800839E0
0x1800839d3  mov     dword ptr [rcx+0Ch], 1
0x1800839da  jmp     short loc_1800839E0
0x1800839dc  mov     [rcx+0Ch], r14d
0x1800839e0  lea     rax, [rcx+14h]
0x1800839e4  test    rax, rax
0x1800839e7  jz      short loc_180083A07
0x1800839e9  mov     dword ptr [rcx+10h], 2Ah ; '*'
0x1800839f0  movups  xmm0, [rbp+57h+var_5C]
0x1800839f4  movups  xmmword ptr [rax], xmm0
0x1800839f7  movups  xmm1, xmmword ptr [rbp+57h+var_4C]
0x1800839fb  movups  xmmword ptr [rax+10h], xmm1
0x1800839ff  movups  xmm0, xmmword ptr [rbp+57h+var_4C+0Ah]
0x180083a03  movups  xmmword ptr [rax+1Ah], xmm0
0x180083a07  mov     dword ptr [rbp+57h+cb], r13d
0x180083a0b  mov     ebx, r14d
0x180083a0e  mov     rcx, [rbp+57h+var_90]; pv
0x180083a12  test    rcx, rcx
0x180083a15  jz      short loc_180083A21
0x180083a17  call    cs:__imp_CoTaskMemFree
0x180083a1d  mov     [rbp+57h+var_90], r14
0x180083a21  cmp     [rbp+57h+var_94], r14d
0x180083a25  jnz     short loc_180083A57
0x180083a27  mov     edx, [rbp+57h+var_A0]
0x180083a2a  mov     rcx, rdi
0x180083a2d  call    ?GetNextProtocolState@CConnectionEx@@UEAA?AW4TSLicenseState@@W42@@Z; CConnectionEx::GetNextProtocolState(TSLicenseState)
0x180083a32  mov     [rbp+57h+var_A0], eax
0x180083a35  cmp     eax, 8
  ... truncated ...
```
