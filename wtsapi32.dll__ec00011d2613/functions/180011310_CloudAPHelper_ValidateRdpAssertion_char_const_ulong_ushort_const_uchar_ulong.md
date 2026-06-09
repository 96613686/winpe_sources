# CloudAPHelper::ValidateRdpAssertion(char const *,ulong,ushort const *,uchar * *,ulong *)

- ea: `0x180011310`
- end: `0x180011e68`
- name: `?ValidateRdpAssertion@CloudAPHelper@@UEAAJPEBDKPEBGPEAPEAEPEAK@Z`
- size: `2904`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, const char *, unsigned int, const unsigned __int16 *, unsigned __int8 **, unsigned int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800010b0`
- `0x1800014c4`
- `0x180006734`
- `0x18000f1f8`
- `0x180011210`
- `0x180011310`
- `0x180012a78`
- `0x180015050`
- `0x180016010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x180011e32`
- `SspiCli!LsaFreeReturnBuffer` at `0x180011e32`

## string_xrefs

- `0x18001139b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011438`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800114cb`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011560`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18001160e`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800116b3`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011756`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011809`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800118b7`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18001195f`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011a09`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011aac`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011b55`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011c0a`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011cb0`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011d4d`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011dc2`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180011539`: `GetInstanceOfJsonHelper failed`
- `0x1800117e2`: `GetInstanceOfJsonHelper failed`
- `0x180011890`: `spJsonHelper->SetValue(call) failed`
- `0x1800119e2`: `spJsonHelper->SetValue(correlationId) failed`
- `0x18001172f`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x180011a85`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x1800115e7`: `spJsonHelper->SetJsonString failed`
- `0x180011be3`: `spJsonHelper->SetJsonString failed`
- `0x18001168c`: `spJsonHelper->SetValue(rdp_resourceid) failed`
- `0x180011938`: `spJsonHelper->SetValue(payload) failed`
- `0x180011c89`: `spJsonHelper->GetValue failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::ValidateRdpAssertion(
        CloudAPHelper *this,
        const char *a2,
        unsigned int a3,
        const unsigned __int16 *a4,
        unsigned __int8 **a5,
        unsigned int *a6)
{
  unsigned int v7; // r15d
  const char *v8; // rsi
  int InstanceOfJsonHelper; // ebx
  int v10; // r8d
  int v11; // r9d
  struct IJsonHelper *v12; // rdi
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  int v16; // ecx
  int v17; // r8d
  int v18; // r9d
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  struct IJsonHelper *v25; // rdi
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  int v29; // ecx
  int v30; // r8d
  int v31; // r9d
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  unsigned int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int v42; // r8d
  int v43; // r9d
  int v44; // ecx
  int v45; // r8d
  int v46; // r9d
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v51; // [rsp+50h] [rbp-39h] BYREF
  int v52; // [rsp+54h] [rbp-35h] BYREF
  const char *v53; // [rsp+58h] [rbp-31h] BYREF
  const char *v54; // [rsp+60h] [rbp-29h] BYREF
  const char *v55; // [rsp+68h] [rbp-21h] BYREF
  const char *v56; // [rsp+70h] [rbp-19h] BYREF
  struct IJsonHelper *v57; // [rsp+78h] [rbp-11h] BYREF
  unsigned int v58; // [rsp+80h] [rbp-9h] BYREF
  unsigned int v59; // [rsp+84h] [rbp-5h] BYREF
  void *Block; // [rsp+88h] [rbp-1h] BYREF
  unsigned __int16 *v61; // [rsp+90h] [rbp+7h] BYREF
  PVOID Buffer; // [rsp+98h] [rbp+Fh] BYREF
  unsigned __int8 *v63; // [rsp+A0h] [rbp+17h] BYREF
  unsigned int v65; // [rsp+E8h] [rbp+5Fh] BYREF

  v57 = 0;
  v7 = a3;
  Block = 0;
  v8 = a2;
  v65 = 0;
  v63 = 0;
  v58 = 0;
  Buffer = 0;
  v59 = 0;
  v61 = 0;
  if ( !a2 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v51 = 243;
      v56 = "Missing paramter pRdpAssertion";
      v52 = -2147024809;
      v53 = "ValidateRdpAssertion";
      v54 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v55 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)qword_18001A7E0,
        a3,
        (_DWORD)a4,
        (__int64)&v55,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v56);
    }
    goto LABEL_57;
  }
  if ( !a5 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 244;
      v55 = "Missing paramter ppAuthBlob";
      v51 = -2147024809;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)&dword_18001A744,
        a3,
        (_DWORD)a4,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( !a6 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 245;
      v55 = "Missing paramter pcbAuthBlob";
      v51 = -2147024809;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)word_18001A792,
        a3,
        (_DWORD)a4,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v57);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 253;
      v55 = "GetInstanceOfJsonHelper failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        dword_18001F000,
        (unsigned int)qword_18001A6A8,
        v10,
        v11,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( !a4 )
    goto LABEL_29;
  v12 = v57;
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const char *, _QWORD))(*(_QWORD *)v57 + 56LL))(
                           v57,
                           v8,
                           v7);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 258;
      v55 = "spJsonHelper->SetJsonString failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v13,
        (unsigned int)&word_18001A6F6,
        v14,
        v15,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, const unsigned __int16 *))(*(_QWORD *)v12 + 120LL))(
                           v12,
                           L"rdp_resourceid",
                           a4);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 261;
      v55 = "spJsonHelper->SetValue(rdp_resourceid) failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v16,
        (unsigned int)&dword_18001A60C,
        v17,
        v18,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, void **, unsigned int *))(*(_QWORD *)v12 + 48LL))(
                           v12,
                           &Block,
                           &v65);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 264;
      v55 = "spJsonHelper->GetJsonStringAsByteArray failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v19,
        (unsigned int)word_18001A65A,
        v20,
        v21,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
    goto LABEL_57;
  }
  if ( v12 )
  {
    TCntPtr<ValuesArray>::SafeRelease(&v57);
    v57 = 0;
  }
  v8 = (const char *)Block;
  v7 = v65;
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v57);
  if ( InstanceOfJsonHelper < 0 )
  {
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 270;
      v55 = "GetInstanceOfJsonHelper failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v22,
        (unsigned int)qword_18001A570,
        v23,
        v24,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
  }
  else
  {
LABEL_29:
    v25 = v57;
    InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *))(*(_QWORD *)v57 + 104LL))(
                             v57,
                             L"call");
    if ( InstanceOfJsonHelper >= 0 )
    {
      InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, const char *, _QWORD))(*(_QWORD *)v25 + 112LL))(
                               v25,
                               L"payload",
                               v8,
                               v7);
      if ( InstanceOfJsonHelper >= 0 )
      {
        InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, char *))(*(_QWORD *)v25 + 120LL))(
                                 v25,
                                 L"correlationId",
                                 (char *)this + 72);
        if ( InstanceOfJsonHelper >= 0 )
        {
          InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, unsigned __int8 **, unsigned int *))(*(_QWORD *)v25 + 48LL))(
                                   v25,
                                   &v63,
                                   &v58);
          if ( InstanceOfJsonHelper >= 0 )
          {
            InstanceOfJsonHelper = CloudAPHelper::CallCloudAP(this, v63, v58, &Buffer, &v59);
            if ( InstanceOfJsonHelper >= 0 )
            {
              if ( Buffer && (v39 = v59) != 0 )
              {
                InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v25 + 56LL))(v25);
                if ( InstanceOfJsonHelper >= 0 )
                {
                  InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v25 + 88LL))(
                                           v25,
                                           L"authbuffer",
                                           &v61);
                  if ( InstanceOfJsonHelper >= 0 )
                  {
                    InstanceOfJsonHelper = CTSCryptUtils::UrlEncodedStringToBinaryW(v61, a5, a6);
                    if ( InstanceOfJsonHelper < 0 && (unsigned int)dword_18001F000 > 2 )
                    {
                      v52 = 311;
                      v55 = "CTSCryptUtils::UrlEncodedStringToBinaryW failed";
                      v51 = InstanceOfJsonHelper;
                      v54 = "ValidateRdpAssertion";
                      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                      v56 = "Error HResult failed";
                      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                        v47,
                        (unsigned int)qword_18001A308,
                        v48,
                        v49,
                        (__int64)&v56,
                        (__int64)&v51,
                        (__int64)&v53,
                        (__int64)&v52,
                        (__int64)&v54,
                        (__int64)&v55);
                    }
                  }
                  else if ( (unsigned int)dword_18001F000 > 2 )
                  {
                    v52 = 304;
                    v55 = "spJsonHelper->GetValue failed";
                    v51 = InstanceOfJsonHelper;
                    v54 = "ValidateRdpAssertion";
                    v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                    v56 = "Error HResult failed";
                    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                      v44,
                      (unsigned int)&word_18001A356,
                      v45,
                      v46,
                      (__int64)&v56,
                      (__int64)&v51,
                      (__int64)&v53,
                      (__int64)&v52,
                      (__int64)&v54,
                      (__int64)&v55);
                  }
                }
                else if ( (unsigned int)dword_18001F000 > 2 )
                {
                  v52 = 301;
                  v55 = "spJsonHelper->SetJsonString failed";
                  v51 = InstanceOfJsonHelper;
                  v54 = "ValidateRdpAssertion";
                  v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v56 = "Error HResult failed";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                    v41,
                    (unsigned int)word_18001A3EA,
                    v42,
                    v43,
                    (__int64)&v56,
                    (__int64)&v51,
                    (__int64)&v53,
                    (__int64)&v52,
                    (__int64)&v54,
                    (__int64)&v55);
                }
              }
              else
              {
                InstanceOfJsonHelper = -2147467259;
                if ( (unsigned int)dword_18001F000 > 2 )
                {
                  v52 = 291;
                  v55 = "ValidateRdpAssertion";
                  v51 = -2147467259;
                  v54 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v53 = "CloudAP returned an empty responce to the RDP assertion validation request";
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                    v38,
                    (unsigned int)&dword_18001A3A4,
                    v39,
                    v40,
                    (__int64)&v53,
                    (__int64)&v51,
                    (__int64)&v54,
                    (__int64)&v52,
                    (__int64)&v55);
                }
              }
            }
            else if ( (unsigned int)dword_18001F000 > 2 )
            {
              v52 = 286;
              v55 = "CallCloudAP failed";
              v51 = InstanceOfJsonHelper;
              v54 = "ValidateRdpAssertion";
              v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
              v56 = "Error HResult failed";
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
                v38,
                (unsigned int)&word_18001A486,
                v39,
                v40,
                (__int64)&v56,
                (__int64)&v51,
                (__int64)&v53,
                (__int64)&v52,
                (__int64)&v54,
                (__int64)&v55);
            }
          }
          else if ( (unsigned int)dword_18001F000 > 2 )
          {
            v52 = 283;
            v55 = "spJsonHelper->GetJsonStringAsByteArray failed";
            v51 = InstanceOfJsonHelper;
            v54 = "ValidateRdpAssertion";
            v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
            v56 = "Error HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
              v35,
              (unsigned int)qword_18001A438,
              v36,
              v37,
              (__int64)&v56,
              (__int64)&v51,
              (__int64)&v53,
              (__int64)&v52,
              (__int64)&v54,
              (__int64)&v55);
          }
        }
        else if ( (unsigned int)dword_18001F000 > 2 )
        {
          v52 = 280;
          v55 = "spJsonHelper->SetValue(correlationId) failed";
          v51 = InstanceOfJsonHelper;
          v54 = "ValidateRdpAssertion";
          v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v56 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v32,
            (unsigned int)word_18001A522,
            v33,
            v34,
            (__int64)&v56,
            (__int64)&v51,
            (__int64)&v53,
            (__int64)&v52,
            (__int64)&v54,
            (__int64)&v55);
        }
      }
      else if ( (unsigned int)dword_18001F000 > 2 )
      {
        v52 = 277;
        v55 = "spJsonHelper->SetValue(payload) failed";
        v51 = InstanceOfJsonHelper;
        v54 = "ValidateRdpAssertion";
        v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v56 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v29,
          (unsigned int)&dword_18001A4D4,
          v30,
          v31,
          (__int64)&v56,
          (__int64)&v51,
          (__int64)&v53,
          (__int64)&v52,
          (__int64)&v54,
          (__int64)&v55);
      }
    }
    else if ( (unsigned int)dword_18001F000 > 2 )
    {
      v52 = 274;
      v55 = "spJsonHelper->SetValue(call) failed";
      v51 = InstanceOfJsonHelper;
      v54 = "ValidateRdpAssertion";
      v53 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v56 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v26,
        (unsigned int)&word_18001A5BE,
        v27,
        v28,
        (__int64)&v56,
        (__int64)&v51,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v55);
    }
  }
LABEL_57:
  if ( Block )
    operator delete(Block);
  if ( v61 )
    operator delete(v61);
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( v63 )
    operator delete(v63);
  TCntPtr<ValuesArray>::SafeRelease(&v57);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x180011310  mov     [rsp-8+arg_10], rbx
0x180011315  mov     [rsp-8+arg_0], rcx
0x18001131a  push    rbp
0x18001131b  push    rsi
0x18001131c  push    rdi
0x18001131d  push    r14
0x18001131f  push    r15
0x180011321  lea     rbp, [rsp-27h]
0x180011326  sub     rsp, 0B0h
0x18001132d  xor     eax, eax
0x18001132f  mov     r14, r9
0x180011332  mov     [rbp+47h+var_58], rax
0x180011336  mov     r15d, r8d
0x180011339  mov     [rbp+47h+Block], rax
0x18001133d  mov     rsi, rdx
0x180011340  mov     [rbp+47h+arg_8], eax
0x180011343  mov     [rbp+47h+var_30], rax
0x180011347  mov     [rbp+47h+var_50], eax
0x18001134a  mov     [rbp+47h+Buffer], rax
0x18001134e  mov     [rbp+47h+var_4C], eax
0x180011351  mov     [rbp+47h+var_40], rax
0x180011355  test    rdx, rdx
0x180011358  jnz     loc_1800113F1
0x18001135e  mov     eax, cs:dword_18001F000
0x180011364  mov     ecx, 80070057h
0x180011369  mov     ebx, ecx
0x18001136b  cmp     eax, 2
0x18001136e  jbe     loc_180011E0D
0x180011374  lea     rax, aMissingParamte_3; "Missing paramter pRdpAssertion"
0x18001137b  mov     [rbp+47h+var_80], 0F3h
0x180011382  mov     [rbp+47h+var_60], rax
0x180011386  lea     rdx, qword_18001A7E0
0x18001138d  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x180011394  mov     [rbp+47h+var_7C], ecx
0x180011397  mov     [rbp+47h+var_78], rax
0x18001139b  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800113a2  mov     [rbp+47h+var_70], rax
0x1800113a6  lea     rax, aErrorCondition; "Error condition failed"
0x1800113ad  mov     [rbp+47h+var_68], rax
0x1800113b1  lea     rax, [rbp+47h+var_60]
0x1800113b5  mov     [rsp+0D0h+var_88], rax
0x1800113ba  lea     rax, [rbp+47h+var_78]
0x1800113be  mov     [rsp+0D0h+var_90], rax
0x1800113c3  lea     rax, [rbp+47h+var_80]
0x1800113c7  mov     [rsp+0D0h+var_98], rax
0x1800113cc  lea     rax, [rbp+47h+var_70]
0x1800113d0  mov     [rsp+0D0h+var_A0], rax
0x1800113d5  lea     rax, [rbp+47h+var_7C]
0x1800113d9  mov     [rsp+0D0h+var_A8], rax
0x1800113de  lea     rax, [rbp+47h+var_68]
0x1800113e2  mov     [rsp+0D0h+var_B0], rax
0x1800113e7  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800113ec  jmp     loc_180011E0D
0x1800113f1  cmp     [rbp+47h+arg_20], rax
0x1800113f5  jnz     loc_180011484
0x1800113fb  mov     eax, cs:dword_18001F000
0x180011401  mov     ecx, 80070057h
0x180011406  mov     ebx, ecx
0x180011408  cmp     eax, 2
0x18001140b  jbe     loc_180011E0D
0x180011411  lea     rax, aMissingParamte_7; "Missing paramter ppAuthBlob"
0x180011418  mov     [rbp+47h+var_7C], 0F4h
0x18001141f  mov     [rbp+47h+var_68], rax
0x180011423  lea     rdx, dword_18001A744
0x18001142a  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x180011431  mov     [rbp+47h+var_80], ecx
0x180011434  mov     [rbp+47h+var_70], rax
0x180011438  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18001143f  mov     [rbp+47h+var_78], rax
0x180011443  lea     rax, aErrorCondition; "Error condition failed"
0x18001144a  mov     [rbp+47h+var_60], rax
0x18001144e  lea     rax, [rbp+47h+var_68]
0x180011452  mov     [rsp+0D0h+var_88], rax
0x180011457  lea     rax, [rbp+47h+var_70]
0x18001145b  mov     [rsp+0D0h+var_90], rax
0x180011460  lea     rax, [rbp+47h+var_7C]
0x180011464  mov     [rsp+0D0h+var_98], rax
0x180011469  lea     rax, [rbp+47h+var_78]
0x18001146d  mov     [rsp+0D0h+var_A0], rax
0x180011472  lea     rax, [rbp+47h+var_80]
0x180011476  mov     [rsp+0D0h+var_A8], rax
0x18001147b  lea     rax, [rbp+47h+var_60]
0x18001147f  jmp     loc_1800113E2
0x180011484  cmp     [rbp+47h+arg_28], rax
0x180011488  jnz     loc_180011517
0x18001148e  mov     eax, cs:dword_18001F000
0x180011494  mov     ecx, 80070057h
0x180011499  mov     ebx, ecx
0x18001149b  cmp     eax, 2
0x18001149e  jbe     loc_180011E0D
0x1800114a4  lea     rax, aMissingParamte_6; "Missing paramter pcbAuthBlob"
0x1800114ab  mov     [rbp+47h+var_7C], 0F5h
0x1800114b2  mov     [rbp+47h+var_68], rax
0x1800114b6  lea     rdx, word_18001A792
0x1800114bd  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x1800114c4  mov     [rbp+47h+var_80], ecx
0x1800114c7  mov     [rbp+47h+var_70], rax
0x1800114cb  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800114d2  mov     [rbp+47h+var_78], rax
0x1800114d6  lea     rax, aErrorCondition; "Error condition failed"
0x1800114dd  mov     [rbp+47h+var_60], rax
0x1800114e1  lea     rax, [rbp+47h+var_68]
0x1800114e5  mov     [rsp+0D0h+var_88], rax
0x1800114ea  lea     rax, [rbp+47h+var_70]
0x1800114ee  mov     [rsp+0D0h+var_90], rax
0x1800114f3  lea     rax, [rbp+47h+var_7C]
0x1800114f7  mov     [rsp+0D0h+var_98], rax
0x1800114fc  lea     rax, [rbp+47h+var_78]
0x180011500  mov     [rsp+0D0h+var_A0], rax
0x180011505  lea     rax, [rbp+47h+var_80]
0x180011509  mov     [rsp+0D0h+var_A8], rax
0x18001150e  lea     rax, [rbp+47h+var_60]
0x180011512  jmp     loc_1800113E2
0x180011517  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x18001151b  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x180011520  mov     ebx, eax
0x180011522  test    eax, eax
0x180011524  jns     loc_1800115AC
0x18001152a  mov     ecx, cs:dword_18001F000
0x180011530  cmp     ecx, 2
0x180011533  jbe     loc_180011E0D
0x180011539  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x180011540  mov     [rbp+47h+var_7C], 0FDh
0x180011547  mov     [rbp+47h+var_68], rax
0x18001154b  lea     rdx, qword_18001A6A8
0x180011552  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x180011559  mov     [rbp+47h+var_80], ebx
0x18001155c  mov     [rbp+47h+var_70], rax
0x180011560  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180011567  mov     [rbp+47h+var_78], rax
0x18001156b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180011572  mov     [rbp+47h+var_60], rax
0x180011576  lea     rax, [rbp+47h+var_68]
0x18001157a  mov     [rsp+0D0h+var_88], rax
0x18001157f  lea     rax, [rbp+47h+var_70]
0x180011583  mov     [rsp+0D0h+var_90], rax
0x180011588  lea     rax, [rbp+47h+var_7C]
0x18001158c  mov     [rsp+0D0h+var_98], rax
0x180011591  lea     rax, [rbp+47h+var_78]
0x180011595  mov     [rsp+0D0h+var_A0], rax
0x18001159a  lea     rax, [rbp+47h+var_80]
0x18001159e  mov     [rsp+0D0h+var_A8], rax
0x1800115a3  lea     rax, [rbp+47h+var_60]
0x1800115a7  jmp     loc_1800113E2
0x1800115ac  test    r14, r14
0x1800115af  jz      loc_180011855
0x1800115b5  mov     rdi, [rbp+47h+var_58]
0x1800115b9  mov     r8d, r15d
0x1800115bc  mov     rdx, rsi
0x1800115bf  mov     rcx, rdi
0x1800115c2  mov     rax, [rdi]
0x1800115c5  mov     rax, [rax+38h]
0x1800115c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800115ce  mov     ebx, eax
0x1800115d0  test    eax, eax
0x1800115d2  jns     loc_18001165A
0x1800115d8  mov     eax, cs:dword_18001F000
0x1800115de  cmp     eax, 2
0x1800115e1  jbe     loc_180011E0D
0x1800115e7  lea     rax, aSpjsonhelperSe_1; "spJsonHelper->SetJsonString failed"
0x1800115ee  mov     [rbp+47h+var_7C], 102h
0x1800115f5  mov     [rbp+47h+var_68], rax
0x1800115f9  lea     rdx, word_18001A6F6
0x180011600  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x180011607  mov     [rbp+47h+var_80], ebx
0x18001160a  mov     [rbp+47h+var_70], rax
0x18001160e  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180011615  mov     [rbp+47h+var_78], rax
0x180011619  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180011620  mov     [rbp+47h+var_60], rax
0x180011624  lea     rax, [rbp+47h+var_68]
0x180011628  mov     [rsp+0D0h+var_88], rax
0x18001162d  lea     rax, [rbp+47h+var_70]
0x180011631  mov     [rsp+0D0h+var_90], rax
0x180011636  lea     rax, [rbp+47h+var_7C]
0x18001163a  mov     [rsp+0D0h+var_98], rax
0x18001163f  lea     rax, [rbp+47h+var_78]
0x180011643  mov     [rsp+0D0h+var_A0], rax
0x180011648  lea     rax, [rbp+47h+var_80]
0x18001164c  mov     [rsp+0D0h+var_A8], rax
0x180011651  lea     rax, [rbp+47h+var_60]
0x180011655  jmp     loc_1800113E2
0x18001165a  mov     rax, [rdi]
0x18001165d  lea     rdx, aRdpResourceid; "rdp_resourceid"
0x180011664  mov     r8, r14
0x180011667  mov     rcx, rdi
0x18001166a  mov     rax, [rax+78h]
0x18001166e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011673  mov     ebx, eax
0x180011675  test    eax, eax
0x180011677  jns     loc_1800116FF
0x18001167d  mov     eax, cs:dword_18001F000
0x180011683  cmp     eax, 2
0x180011686  jbe     loc_180011E0D
0x18001168c  lea     rax, aSpjsonhelperSe_2; "spJsonHelper->SetValue(rdp_resourceid) "...
0x180011693  mov     [rbp+47h+var_7C], 105h
0x18001169a  mov     [rbp+47h+var_68], rax
0x18001169e  lea     rdx, dword_18001A60C
0x1800116a5  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x1800116ac  mov     [rbp+47h+var_80], ebx
0x1800116af  mov     [rbp+47h+var_70], rax
0x1800116b3  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800116ba  mov     [rbp+47h+var_78], rax
0x1800116be  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800116c5  mov     [rbp+47h+var_60], rax
0x1800116c9  lea     rax, [rbp+47h+var_68]
0x1800116cd  mov     [rsp+0D0h+var_88], rax
0x1800116d2  lea     rax, [rbp+47h+var_70]
0x1800116d6  mov     [rsp+0D0h+var_90], rax
0x1800116db  lea     rax, [rbp+47h+var_7C]
0x1800116df  mov     [rsp+0D0h+var_98], rax
0x1800116e4  lea     rax, [rbp+47h+var_78]
0x1800116e8  mov     [rsp+0D0h+var_A0], rax
0x1800116ed  lea     rax, [rbp+47h+var_80]
0x1800116f1  mov     [rsp+0D0h+var_A8], rax
0x1800116f6  lea     rax, [rbp+47h+var_60]
0x1800116fa  jmp     loc_1800113E2
0x1800116ff  mov     rax, [rdi]
0x180011702  lea     r8, [rbp+47h+arg_8]
0x180011706  lea     rdx, [rbp+47h+Block]
0x18001170a  mov     rcx, rdi
0x18001170d  mov     rax, [rax+30h]
0x180011711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011716  mov     ebx, eax
0x180011718  test    eax, eax
0x18001171a  jns     loc_1800117A2
0x180011720  mov     eax, cs:dword_18001F000
0x180011726  cmp     eax, 2
0x180011729  jbe     loc_180011E0D
0x18001172f  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x180011736  mov     [rbp+47h+var_7C], 108h
0x18001173d  mov     [rbp+47h+var_68], rax
0x180011741  lea     rdx, word_18001A65A
0x180011748  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x18001174f  mov     [rbp+47h+var_80], ebx
0x180011752  mov     [rbp+47h+var_70], rax
0x180011756  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18001175d  mov     [rbp+47h+var_78], rax
0x180011761  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180011768  mov     [rbp+47h+var_60], rax
0x18001176c  lea     rax, [rbp+47h+var_68]
0x180011770  mov     [rsp+0D0h+var_88], rax
0x180011775  lea     rax, [rbp+47h+var_70]
0x180011779  mov     [rsp+0D0h+var_90], rax
0x18001177e  lea     rax, [rbp+47h+var_7C]
0x180011782  mov     [rsp+0D0h+var_98], rax
0x180011787  lea     rax, [rbp+47h+var_78]
0x18001178b  mov     [rsp+0D0h+var_A0], rax
0x180011790  lea     rax, [rbp+47h+var_80]
0x180011794  mov     [rsp+0D0h+var_A8], rax
0x180011799  lea     rax, [rbp+47h+var_60]
0x18001179d  jmp     loc_1800113E2
0x1800117a2  test    rdi, rdi
0x1800117a5  jz      short loc_1800117B8
0x1800117a7  lea     rcx, [rbp+47h+var_58]
0x1800117ab  call    ?SafeRelease@?$TCntPtr@VValuesArray@@@@AEAAXXZ; TCntPtr<ValuesArray>::SafeRelease(void)
0x1800117b0  mov     [rbp+47h+var_58], 0
0x1800117b8  mov     rsi, [rbp+47h+Block]
0x1800117bc  lea     rcx, [rbp+47h+var_58]; struct IJsonHelper **
0x1800117c0  mov     r15d, [rbp+47h+arg_8]
0x1800117c4  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x1800117c9  mov     ebx, eax
0x1800117cb  test    eax, eax
0x1800117cd  jns     loc_180011855
0x1800117d3  mov     eax, cs:dword_18001F000
0x1800117d9  cmp     eax, 2
0x1800117dc  jbe     loc_180011E0D
0x1800117e2  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x1800117e9  mov     [rbp+47h+var_7C], 10Eh
0x1800117f0  mov     [rbp+47h+var_68], rax
0x1800117f4  lea     rdx, qword_18001A570
0x1800117fb  lea     rax, aValidaterdpass; "ValidateRdpAssertion"
0x180011802  mov     [rbp+47h+var_80], ebx
0x180011805  mov     [rbp+47h+var_70], rax
0x180011809  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180011810  mov     [rbp+47h+var_78], rax
0x180011814  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18001181b  mov     [rbp+47h+var_60], rax
0x18001181f  lea     rax, [rbp+47h+var_68]
0x180011823  mov     [rsp+0D0h+var_88], rax
0x180011828  lea     rax, [rbp+47h+var_70]
0x18001182c  mov     [rsp+0D0h+var_90], rax
0x180011831  lea     rax, [rbp+47h+var_7C]
0x180011835  mov     [rsp+0D0h+var_98], rax
0x18001183a  lea     rax, [rbp+47h+var_78]
0x18001183e  mov     [rsp+0D0h+var_A0], rax
0x180011843  lea     rax, [rbp+47h+var_80]
0x180011847  mov     [rsp+0D0h+var_A8], rax
0x18001184c  lea     rax, [rbp+47h+var_60]
0x180011850  jmp     loc_1800113E2
0x180011855  mov     rdi, [rbp+47h+var_58]
0x180011859  lea     rdx, aCall; "call"
0x180011860  movsd   xmm2, cs:__real@4024000000000000
0x180011868  mov     rcx, rdi
0x18001186b  mov     rax, [rdi]
0x18001186e  mov     rax, [rax+68h]
0x180011872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011877  mov     ebx, eax
0x180011879  test    eax, eax
0x18001187b  jns     loc_180011903
  ... truncated ...
```
