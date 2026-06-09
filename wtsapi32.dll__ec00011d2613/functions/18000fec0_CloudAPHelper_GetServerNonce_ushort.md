# CloudAPHelper::GetServerNonce(ushort * *)

- ea: `0x18000fec0`
- end: `0x18001048c`
- name: `?GetServerNonce@CloudAPHelper@@UEAAJPEAPEAG@Z`
- size: `1484`
- prototype: `__int64 __fastcall(CloudAPHelper *__hidden this, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x1800010b0`
- `0x1800013bc`
- `0x1800014c4`
- `0x180006734`
- `0x18000f1f8`
- `0x18000fec0`
- `0x180011210`
- `0x180012a78`
- `0x180016010`

## import_xrefs

- `SspiCli!LsaFreeReturnBuffer` at `0x18001045f`
- `SspiCli!LsaFreeReturnBuffer` at `0x18001045f`

## string_xrefs

- `0x18000ff41`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000ffd9`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180010080`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18001011f`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800101bb`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x1800102f4`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x180010396`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18001040b`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000ffb5`: `GetInstanceOfJsonHelper failed`
- `0x18001005c`: `spJsonHelper->SetValue(call) failed`
- `0x1800100fb`: `spJsonHelper->SetValue(correlationId) failed`
- `0x180010197`: `spJsonHelper->GetJsonStringAsByteArray failed`
- `0x1800102d0`: `spJsonHelper->SetJsonString failed`
- `0x180010372`: `spJsonHelper->GetValue(ts_nonce) failed`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::GetServerNonce(CloudAPHelper *this, unsigned __int16 **a2, int a3, int a4)
{
  CloudAPHelper *v5; // r14
  int InstanceOfJsonHelper; // ebx
  __int16 *v7; // rdx
  const char **v8; // rax
  struct IJsonHelper *v9; // rdi
  int v10; // ecx
  unsigned int v11; // r8d
  int v12; // r9d
  const char **v14; // [rsp+38h] [rbp-29h]
  const char **v15; // [rsp+48h] [rbp-19h]
  const char **v16; // [rsp+50h] [rbp-11h]
  int v17; // [rsp+58h] [rbp-9h] BYREF
  PVOID Buffer; // [rsp+60h] [rbp-1h] BYREF
  void *Block; // [rsp+68h] [rbp+7h] BYREF
  struct IJsonHelper *v20; // [rsp+70h] [rbp+Fh] BYREF
  const char *v21; // [rsp+78h] [rbp+17h] BYREF
  const char *v22; // [rsp+80h] [rbp+1Fh] BYREF
  const char *v23; // [rsp+88h] [rbp+27h] BYREF
  _QWORD v24[5]; // [rsp+90h] [rbp+2Fh] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+6Fh] BYREF
  unsigned int v26; // [rsp+D8h] [rbp+77h] BYREF
  int v27; // [rsp+E0h] [rbp+7Fh] BYREF

  v20 = 0;
  Block = 0;
  v5 = this;
  v25 = 0;
  Buffer = 0;
  v26 = 0;
  if ( !a2 )
  {
    InstanceOfJsonHelper = -2147024809;
    if ( (unsigned int)dword_18001F000 <= 2 )
      goto LABEL_30;
    v27 = 169;
    v21 = "Missing paramter ppNonce";
    v7 = (__int16 *)&dword_18001AA84;
    v22 = "GetServerNonce";
    v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
    v24[0] = "Error condition failed";
    v16 = &v21;
    v15 = &v22;
    v14 = &v23;
    v8 = (const char **)v24;
    goto LABEL_4;
  }
  InstanceOfJsonHelper = GetInstanceOfJsonHelper(&v20);
  if ( InstanceOfJsonHelper >= 0 )
  {
    v9 = v20;
    InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *))(*(_QWORD *)v20 + 104LL))(
                             v20,
                             L"call");
    if ( InstanceOfJsonHelper >= 0 )
    {
      InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, __int64))(*(_QWORD *)v9 + 120LL))(
                               v9,
                               L"correlationId",
                               (__int64)v5 + 72);
      if ( InstanceOfJsonHelper >= 0 )
      {
        InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, void **, unsigned int *))(*(_QWORD *)v9 + 48LL))(
                                 v9,
                                 &Block,
                                 &v25);
        if ( InstanceOfJsonHelper >= 0 )
        {
          InstanceOfJsonHelper = CloudAPHelper::CallCloudAP(v5, (unsigned __int8 *)Block, v25, &Buffer, &v26);
          if ( InstanceOfJsonHelper >= 0 )
          {
            if ( Buffer && (v11 = v26) != 0 )
            {
              InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *))(*(_QWORD *)v9 + 56LL))(v9);
              if ( InstanceOfJsonHelper >= 0 )
              {
                InstanceOfJsonHelper = (*(__int64 (__fastcall **)(struct IJsonHelper *, const wchar_t *, unsigned __int16 **))(*(_QWORD *)v9 + 88LL))(
                                         v9,
                                         L"ts_nonce",
                                         a2);
                if ( InstanceOfJsonHelper < 0 && (unsigned int)dword_18001F000 > 2 )
                {
                  v27 = 207;
                  v24[0] = "spJsonHelper->GetValue(ts_nonce) failed";
                  v7 = (__int16 *)&dword_18001A87C;
                  v23 = "GetServerNonce";
                  v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                  v21 = "Error HResult failed";
                  v16 = (const char **)v24;
                  v15 = &v23;
                  v14 = &v22;
                  v8 = &v21;
                  goto LABEL_4;
                }
              }
              else if ( (unsigned int)dword_18001F000 > 2 )
              {
                v27 = 204;
                v24[0] = "spJsonHelper->SetJsonString failed";
                v7 = &word_18001A82E;
                v23 = "GetServerNonce";
                v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v21 = "Error HResult failed";
                v16 = (const char **)v24;
                v15 = &v23;
                v14 = &v22;
                v8 = &v21;
                goto LABEL_4;
              }
            }
            else
            {
              InstanceOfJsonHelper = -2147467259;
              if ( (unsigned int)dword_18001F000 > 2 )
              {
                v27 = 194;
                v24[0] = "GetServerNonce";
                v17 = -2147467259;
                v23 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
                v22 = "CloudAP returned an empty responce to the nonce request";
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v10,
                  (unsigned int)word_18001A8CA,
                  v11,
                  v12,
                  (__int64)&v22,
                  (__int64)&v17,
                  (__int64)&v23,
                  (__int64)&v27,
                  (__int64)v24);
              }
            }
          }
          else if ( (unsigned int)dword_18001F000 > 3 )
          {
            v27 = InstanceOfJsonHelper;
            v24[0] = "GetServerNonce";
            v23 = "CallCloudAP failed";
            v22 = "Warning HResult failed";
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              v10,
              (unsigned int)&word_18001A95E,
              v11,
              v12,
              (__int64)&v22,
              (__int64)&v23,
              (__int64)&v27,
              (__int64)v24);
          }
        }
        else if ( (unsigned int)dword_18001F000 > 2 )
        {
          v27 = 186;
          v24[0] = "spJsonHelper->GetJsonStringAsByteArray failed";
          v7 = (__int16 *)qword_18001A910;
          v23 = "GetServerNonce";
          v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
          v21 = "Error HResult failed";
          v16 = (const char **)v24;
          v15 = &v23;
          v14 = &v22;
          v8 = &v21;
          goto LABEL_4;
        }
      }
      else if ( (unsigned int)dword_18001F000 > 2 )
      {
        v27 = 183;
        v24[0] = "spJsonHelper->SetValue(correlationId) failed";
        v7 = word_18001A99A;
        v23 = "GetServerNonce";
        v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
        v21 = "Error HResult failed";
        v16 = (const char **)v24;
        v15 = &v23;
        v14 = &v22;
        v8 = &v21;
        goto LABEL_4;
      }
    }
    else if ( (unsigned int)dword_18001F000 > 2 )
    {
      v27 = 180;
      v24[0] = "spJsonHelper->SetValue(call) failed";
      v7 = &word_18001AA36;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
      goto LABEL_4;
    }
  }
  else
  {
    LODWORD(this) = dword_18001F000;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v27 = 177;
      v24[0] = "GetInstanceOfJsonHelper failed";
      v7 = (__int16 *)qword_18001A9E8;
      v23 = "GetServerNonce";
      v22 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v21 = "Error HResult failed";
      v16 = (const char **)v24;
      v15 = &v23;
      v14 = &v22;
      v8 = &v21;
LABEL_4:
      v17 = InstanceOfJsonHelper;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (_DWORD)v7,
        a3,
        a4,
        (__int64)v8,
        (__int64)&v17,
        (__int64)v14,
        (__int64)&v27,
        (__int64)v15,
        (__int64)v16);
    }
  }
LABEL_30:
  if ( Buffer )
    LsaFreeReturnBuffer(Buffer);
  if ( Block )
    operator delete(Block);
  TCntPtr<ValuesArray>::SafeRelease(&v20);
  return (unsigned int)InstanceOfJsonHelper;
}

```

## disassembly

```asm
0x18000fec0  mov     r11, rsp
0x18000fec3  push    rbp
0x18000fec4  push    rbx
0x18000fec5  push    rsi
0x18000fec6  push    rdi
0x18000fec7  push    r14
0x18000fec9  lea     rbp, [r11-5Fh]
0x18000fecd  sub     rsp, 90h
0x18000fed4  mov     [rbp+57h+var_48], 0
0x18000fedc  mov     rsi, rdx
0x18000fedf  mov     [rbp+57h+Block], 0
0x18000fee7  mov     r14, rcx
0x18000feea  mov     [rbp+57h+arg_8], 0
0x18000fef1  mov     [rbp+57h+Buffer], 0
0x18000fef9  mov     [rbp+57h+arg_10], 0
0x18000ff00  test    rdx, rdx
0x18000ff03  jnz     loc_18000FF97
0x18000ff09  mov     eax, cs:dword_18001F000
0x18000ff0f  mov     ebx, 80070057h
0x18000ff14  cmp     eax, 2
0x18000ff17  jbe     loc_180010456
0x18000ff1d  lea     rax, aMissingParamte; "Missing paramter ppNonce"
0x18000ff24  mov     [rbp+57h+arg_18], 0A9h
0x18000ff2b  mov     [rbp+57h+var_40], rax
0x18000ff2f  lea     rdx, dword_18001AA84
0x18000ff36  lea     rax, aGetservernonce; "GetServerNonce"
0x18000ff3d  mov     [rbp+57h+var_38], rax
0x18000ff41  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000ff48  mov     [rbp+57h+var_30], rax
0x18000ff4c  lea     rax, aErrorCondition; "Error condition failed"
0x18000ff53  mov     [rbp+57h+var_28], rax
0x18000ff57  lea     rax, [rbp+57h+var_40]
0x18000ff5b  mov     [r11-70h], rax
0x18000ff5f  lea     rax, [rbp+57h+var_38]
0x18000ff63  mov     [r11-78h], rax
0x18000ff67  lea     rax, [rbp+57h+arg_18]
0x18000ff6b  mov     [r11-80h], rax
0x18000ff6f  lea     rax, [rbp+57h+var_30]
0x18000ff73  mov     [rsp+0B0h+var_80], rax
0x18000ff78  lea     rax, [rbp+57h+var_60]
0x18000ff7c  mov     [rsp+0B0h+var_88], rax
0x18000ff81  lea     rax, [rbp+57h+var_28]
0x18000ff85  mov     [rbp+57h+var_60], ebx
0x18000ff88  mov     [rsp+0B0h+var_90], rax
0x18000ff8d  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000ff92  jmp     loc_180010456
0x18000ff97  lea     rcx, [rbp+57h+var_48]; struct IJsonHelper **
0x18000ff9b  call    ?GetInstanceOfJsonHelper@@YAJPEAPEAVIJsonHelper@@@Z; GetInstanceOfJsonHelper(IJsonHelper * *)
0x18000ffa0  mov     ebx, eax
0x18000ffa2  test    eax, eax
0x18000ffa4  jns     short loc_180010025
0x18000ffa6  mov     ecx, cs:dword_18001F000
0x18000ffac  cmp     ecx, 2
0x18000ffaf  jbe     loc_180010456
0x18000ffb5  lea     rax, aGetinstanceofj; "GetInstanceOfJsonHelper failed"
0x18000ffbc  mov     [rbp+57h+arg_18], 0B1h
0x18000ffc3  mov     [rbp+57h+var_28], rax
0x18000ffc7  lea     rdx, qword_18001A9E8
0x18000ffce  lea     rax, aGetservernonce; "GetServerNonce"
0x18000ffd5  mov     [rbp+57h+var_30], rax
0x18000ffd9  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000ffe0  mov     [rbp+57h+var_38], rax
0x18000ffe4  lea     rax, aErrorHresultFa; "Error HResult failed"
0x18000ffeb  mov     [rbp+57h+var_40], rax
0x18000ffef  lea     rax, [rbp+57h+var_28]
0x18000fff3  mov     [rsp+48h], rax
0x18000fff8  lea     rax, [rbp+57h+var_30]
0x18000fffc  mov     [rsp+0B0h+var_70], rax
0x180010001  lea     rax, [rbp+57h+arg_18]
0x180010005  mov     [rsp+0B0h+var_78], rax
0x18001000a  lea     rax, [rbp+57h+var_38]
0x18001000e  mov     [rsp+0B0h+var_80], rax
0x180010013  lea     rax, [rbp+57h+var_60]
0x180010017  mov     [rsp+0B0h+var_88], rax
0x18001001c  lea     rax, [rbp+57h+var_40]
0x180010020  jmp     loc_18000FF85
0x180010025  mov     rdi, [rbp+57h+var_48]
0x180010029  lea     rdx, aCall; "call"
0x180010030  movsd   xmm2, cs:__real@4022000000000000
0x180010038  mov     rcx, rdi
0x18001003b  mov     rax, [rdi]
0x18001003e  mov     rax, [rax+68h]
0x180010042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010047  mov     ebx, eax
0x180010049  test    eax, eax
0x18001004b  jns     short loc_1800100CC
0x18001004d  mov     eax, cs:dword_18001F000
0x180010053  cmp     eax, 2
0x180010056  jbe     loc_180010456
0x18001005c  lea     rax, aSpjsonhelperSe_0; "spJsonHelper->SetValue(call) failed"
0x180010063  mov     [rbp+57h+arg_18], 0B4h
0x18001006a  mov     [rbp+57h+var_28], rax
0x18001006e  lea     rdx, word_18001AA36
0x180010075  lea     rax, aGetservernonce; "GetServerNonce"
0x18001007c  mov     [rbp+57h+var_30], rax
0x180010080  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180010087  mov     [rbp+57h+var_38], rax
0x18001008b  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010092  mov     [rbp+57h+var_40], rax
0x180010096  lea     rax, [rbp+57h+var_28]
0x18001009a  mov     [rsp+48h], rax
0x18001009f  lea     rax, [rbp+57h+var_30]
0x1800100a3  mov     [rsp+0B0h+var_70], rax
0x1800100a8  lea     rax, [rbp+57h+arg_18]
0x1800100ac  mov     [rsp+0B0h+var_78], rax
0x1800100b1  lea     rax, [rbp+57h+var_38]
0x1800100b5  mov     [rsp+0B0h+var_80], rax
0x1800100ba  lea     rax, [rbp+57h+var_60]
0x1800100be  mov     [rsp+0B0h+var_88], rax
0x1800100c3  lea     rax, [rbp+57h+var_40]
0x1800100c7  jmp     loc_18000FF85
0x1800100cc  mov     rax, [rdi]
0x1800100cf  lea     r8, [r14+48h]
0x1800100d3  lea     rdx, aCorrelationid; "correlationId"
0x1800100da  mov     rcx, rdi
0x1800100dd  mov     rax, [rax+78h]
0x1800100e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100e6  mov     ebx, eax
0x1800100e8  test    eax, eax
0x1800100ea  jns     short loc_18001016B
0x1800100ec  mov     eax, cs:dword_18001F000
0x1800100f2  cmp     eax, 2
0x1800100f5  jbe     loc_180010456
0x1800100fb  lea     rax, aSpjsonhelperSe_3; "spJsonHelper->SetValue(correlationId) f"...
0x180010102  mov     [rbp+57h+arg_18], 0B7h
0x180010109  mov     [rbp+57h+var_28], rax
0x18001010d  lea     rdx, word_18001A99A
0x180010114  lea     rax, aGetservernonce; "GetServerNonce"
0x18001011b  mov     [rbp+57h+var_30], rax
0x18001011f  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180010126  mov     [rbp+57h+var_38], rax
0x18001012a  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010131  mov     [rbp+57h+var_40], rax
0x180010135  lea     rax, [rbp+57h+var_28]
0x180010139  mov     [rsp+48h], rax
0x18001013e  lea     rax, [rbp+57h+var_30]
0x180010142  mov     [rsp+0B0h+var_70], rax
0x180010147  lea     rax, [rbp+57h+arg_18]
0x18001014b  mov     [rsp+0B0h+var_78], rax
0x180010150  lea     rax, [rbp+57h+var_38]
0x180010154  mov     [rsp+0B0h+var_80], rax
0x180010159  lea     rax, [rbp+57h+var_60]
0x18001015d  mov     [rsp+0B0h+var_88], rax
0x180010162  lea     rax, [rbp+57h+var_40]
0x180010166  jmp     loc_18000FF85
0x18001016b  mov     rax, [rdi]
0x18001016e  lea     r8, [rbp+57h+arg_8]
0x180010172  lea     rdx, [rbp+57h+Block]
0x180010176  mov     rcx, rdi
0x180010179  mov     rax, [rax+30h]
0x18001017d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010182  mov     ebx, eax
0x180010184  test    eax, eax
0x180010186  jns     short loc_180010207
0x180010188  mov     eax, cs:dword_18001F000
0x18001018e  cmp     eax, 2
0x180010191  jbe     loc_180010456
0x180010197  lea     rax, aSpjsonhelperGe_1; "spJsonHelper->GetJsonStringAsByteArray "...
0x18001019e  mov     [rbp+57h+arg_18], 0BAh
0x1800101a5  mov     [rbp+57h+var_28], rax
0x1800101a9  lea     rdx, qword_18001A910
0x1800101b0  lea     rax, aGetservernonce; "GetServerNonce"
0x1800101b7  mov     [rbp+57h+var_30], rax
0x1800101bb  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800101c2  mov     [rbp+57h+var_38], rax
0x1800101c6  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800101cd  mov     [rbp+57h+var_40], rax
0x1800101d1  lea     rax, [rbp+57h+var_28]
0x1800101d5  mov     [rsp+48h], rax
0x1800101da  lea     rax, [rbp+57h+var_30]
0x1800101de  mov     [rsp+0B0h+var_70], rax
0x1800101e3  lea     rax, [rbp+57h+arg_18]
0x1800101e7  mov     [rsp+0B0h+var_78], rax
0x1800101ec  lea     rax, [rbp+57h+var_38]
0x1800101f0  mov     [rsp+0B0h+var_80], rax
0x1800101f5  lea     rax, [rbp+57h+var_60]
0x1800101f9  mov     [rsp+0B0h+var_88], rax
0x1800101fe  lea     rax, [rbp+57h+var_40]
0x180010202  jmp     loc_18000FF85
0x180010207  mov     r8d, [rbp+57h+arg_8]; unsigned int
0x18001020b  lea     rax, [rbp+57h+arg_10]
0x18001020f  mov     rdx, [rbp+57h+Block]; unsigned __int8 *
0x180010213  lea     r9, [rbp+57h+Buffer]; void **
0x180010217  mov     rcx, r14; this
0x18001021a  mov     [rsp+0B0h+var_90], rax; unsigned int *
0x18001021f  call    ?CallCloudAP@CloudAPHelper@@AEAAJPEAEKPEAPEAXPEAK@Z; CloudAPHelper::CallCloudAP(uchar *,ulong,void * *,ulong *)
0x180010224  mov     ebx, eax
0x180010226  test    eax, eax
0x180010228  jns     short loc_180010292
0x18001022a  mov     eax, cs:dword_18001F000
0x180010230  cmp     eax, 3
0x180010233  jbe     loc_180010456
0x180010239  lea     rax, aGetservernonce; "GetServerNonce"
0x180010240  mov     [rbp+57h+arg_18], ebx
0x180010243  mov     [rbp+57h+var_28], rax
0x180010247  lea     rdx, word_18001A95E
0x18001024e  lea     rax, aCallcloudapFai; "CallCloudAP failed"
0x180010255  mov     [rbp+57h+var_30], rax
0x180010259  lea     rax, aWarningHresult; "Warning HResult failed"
0x180010260  mov     [rbp+57h+var_38], rax
0x180010264  lea     rax, [rbp+57h+var_28]
0x180010268  mov     [rsp+0B0h+var_78], rax
0x18001026d  lea     rax, [rbp+57h+arg_18]
0x180010271  mov     [rsp+0B0h+var_80], rax
0x180010276  lea     rax, [rbp+57h+var_30]
0x18001027a  mov     [rsp+0B0h+var_88], rax
0x18001027f  lea     rax, [rbp+57h+var_38]
0x180010283  mov     [rsp+0B0h+var_90], rax
0x180010288  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18001028d  jmp     loc_180010456
0x180010292  mov     rdx, [rbp+57h+Buffer]
0x180010296  test    rdx, rdx
0x180010299  jz      loc_1800103E2
0x18001029f  mov     r8d, [rbp+57h+arg_10]
0x1800102a3  test    r8d, r8d
0x1800102a6  jz      loc_1800103E2
0x1800102ac  mov     rax, [rdi]
0x1800102af  mov     rcx, rdi
0x1800102b2  mov     rax, [rax+38h]
0x1800102b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102bb  mov     ebx, eax
0x1800102bd  test    eax, eax
0x1800102bf  jns     short loc_180010340
0x1800102c1  mov     eax, cs:dword_18001F000
0x1800102c7  cmp     eax, 2
0x1800102ca  jbe     loc_180010456
0x1800102d0  lea     rax, aSpjsonhelperSe_1; "spJsonHelper->SetJsonString failed"
0x1800102d7  mov     [rbp+57h+arg_18], 0CCh
0x1800102de  mov     [rbp+57h+var_28], rax
0x1800102e2  lea     rdx, word_18001A82E
0x1800102e9  lea     rax, aGetservernonce; "GetServerNonce"
0x1800102f0  mov     [rbp+57h+var_30], rax
0x1800102f4  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x1800102fb  mov     [rbp+57h+var_38], rax
0x1800102ff  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180010306  mov     [rbp+57h+var_40], rax
0x18001030a  lea     rax, [rbp+57h+var_28]
0x18001030e  mov     [rsp+48h], rax
0x180010313  lea     rax, [rbp+57h+var_30]
0x180010317  mov     [rsp+0B0h+var_70], rax
0x18001031c  lea     rax, [rbp+57h+arg_18]
0x180010320  mov     [rsp+0B0h+var_78], rax
0x180010325  lea     rax, [rbp+57h+var_38]
0x180010329  mov     [rsp+0B0h+var_80], rax
0x18001032e  lea     rax, [rbp+57h+var_60]
0x180010332  mov     [rsp+0B0h+var_88], rax
0x180010337  lea     rax, [rbp+57h+var_40]
0x18001033b  jmp     loc_18000FF85
0x180010340  mov     rax, [rdi]
0x180010343  lea     rdx, aTsNonce; "ts_nonce"
0x18001034a  mov     r8, rsi
0x18001034d  mov     rcx, rdi
0x180010350  mov     rax, [rax+58h]
0x180010354  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010359  mov     ebx, eax
0x18001035b  test    eax, eax
0x18001035d  jns     loc_180010456
0x180010363  mov     eax, cs:dword_18001F000
0x180010369  cmp     eax, 2
0x18001036c  jbe     loc_180010456
0x180010372  lea     rax, aSpjsonhelperGe_0; "spJsonHelper->GetValue(ts_nonce) failed"
0x180010379  mov     [rbp+57h+arg_18], 0CFh
0x180010380  mov     [rbp+57h+var_28], rax
0x180010384  lea     rdx, dword_18001A87C
0x18001038b  lea     rax, aGetservernonce; "GetServerNonce"
0x180010392  mov     [rbp+57h+var_30], rax
0x180010396  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18001039d  mov     [rbp+57h+var_38], rax
0x1800103a1  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800103a8  mov     [rbp+57h+var_40], rax
0x1800103ac  lea     rax, [rbp+57h+var_28]
0x1800103b0  mov     [rsp+48h], rax
0x1800103b5  lea     rax, [rbp+57h+var_30]
0x1800103b9  mov     [rsp+0B0h+var_70], rax
0x1800103be  lea     rax, [rbp+57h+arg_18]
0x1800103c2  mov     [rsp+0B0h+var_78], rax
0x1800103c7  lea     rax, [rbp+57h+var_38]
0x1800103cb  mov     [rsp+0B0h+var_80], rax
0x1800103d0  lea     rax, [rbp+57h+var_60]
0x1800103d4  mov     [rsp+0B0h+var_88], rax
0x1800103d9  lea     rax, [rbp+57h+var_40]
0x1800103dd  jmp     loc_18000FF85
0x1800103e2  mov     eax, cs:dword_18001F000
0x1800103e8  mov     ebx, 80004005h
0x1800103ed  cmp     eax, 2
0x1800103f0  jbe     short loc_180010456
0x1800103f2  lea     rax, aGetservernonce; "GetServerNonce"
0x1800103f9  mov     [rbp+57h+arg_18], 0C2h
0x180010400  mov     [rbp+57h+var_28], rax
0x180010404  lea     rdx, word_18001A8CA
0x18001040b  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x180010412  mov     [rbp+57h+var_60], ebx
0x180010415  mov     [rbp+57h+var_30], rax
0x180010419  lea     rax, aCloudapReturne_1; "CloudAP returned an empty responce to t"...
0x180010420  mov     [rbp+57h+var_38], rax
0x180010424  lea     rax, [rbp+57h+var_28]
0x180010428  mov     [rsp+0B0h+var_70], rax
0x18001042d  lea     rax, [rbp+57h+arg_18]
0x180010431  mov     [rsp+0B0h+var_78], rax
0x180010436  lea     rax, [rbp+57h+var_30]
  ... truncated ...
```
