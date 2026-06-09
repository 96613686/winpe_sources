# CloudAPHelper::CallCloudAP(uchar *,ulong,void * *,ulong *)

- ea: `0x18000f1f8`
- end: `0x18000f624`
- name: `?CallCloudAP@CloudAPHelper@@AEAAJPEAEKPEAPEAXPEAK@Z`
- size: `1068`
- prototype: `int(CloudAPHelper *__hidden this, unsigned __int8 *, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x18000fec0`
- `0x180011310`

## callees

- `0x1800013bc`
- `0x1800014c4`
- `0x180006734`
- `0x180007a64`
- `0x18000f1f8`
- `0x180015582`

## import_xrefs

- `SspiCli!LsaCallAuthenticationPackage` at `0x18000f559`
- `SspiCli!LsaCallAuthenticationPackage` at `0x18000f559`

## string_xrefs

- `0x18000f26a`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000f306`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000f39c`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000f42e`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000f4c8`: `onecore\termsrv\rdp\win\security\cloudaphelper.cpp`
- `0x18000f243`: `Missing paramter pRequestJson`

## pseudocode

```c
__int64 __fastcall CloudAPHelper::CallCloudAP(
        CloudAPHelper *this,
        unsigned __int8 *a2,
        unsigned int a3,
        void **a4,
        PULONG a5)
{
  size_t v5; // rbx
  unsigned int v9; // ebx
  ULONG *ReturnBufferLength; // r14
  ULONG v11; // esi
  char *v12; // rax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  void *v16; // rdi
  int v17; // ecx
  NTSTATUS v18; // ebx
  int v19; // r8d
  int v20; // r9d
  char *v21; // rdx
  const char *v22; // rax
  int v24; // [rsp+50h] [rbp-21h] BYREF
  int v25; // [rsp+54h] [rbp-1Dh] BYREF
  const char *v26; // [rsp+58h] [rbp-19h] BYREF
  const char *v27; // [rsp+60h] [rbp-11h] BYREF
  const char *v28; // [rsp+68h] [rbp-9h] BYREF
  _QWORD v29[10]; // [rsp+70h] [rbp-1h] BYREF
  int ProtocolStatus; // [rsp+D8h] [rbp+67h] BYREF

  v5 = a3;
  ProtocolStatus = 0;
  if ( !a2 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v24 = 441;
      v26 = "Missing paramter pRequestJson";
      v25 = -2147024809;
      v27 = "CallCloudAP";
      v28 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v29[0] = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_18001A13B,
        a3,
        (_DWORD)a4,
        (__int64)v29,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v26);
    }
    return v9;
  }
  if ( !a4 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v25 = 442;
      v29[0] = "Missing paramter ppCloudApResponse";
      v24 = -2147024809;
      v28 = "CallCloudAP";
      v27 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)byte_18001A189,
        a3,
        0,
        (__int64)&v26,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)v29);
    }
    return v9;
  }
  ReturnBufferLength = a5;
  if ( !a5 )
  {
    v9 = -2147024809;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v25 = 443;
      v29[0] = "Missing paramter pcbCloudApResponse";
      v24 = -2147024809;
      v28 = "CallCloudAP";
      v27 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        -2147024809,
        (unsigned int)&byte_18001A09F,
        a3,
        (_DWORD)a4,
        (__int64)&v26,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)v29);
    }
    return v9;
  }
  v11 = a3 + 27;
  if ( a3 + 27 < a3 )
  {
    v9 = -2147467259;
    if ( (unsigned int)dword_18001F000 > 2 )
    {
      v25 = 446;
      v29[0] = "Integer overflow check failed failed";
      v24 = -2147467259;
      v28 = "CallCloudAP";
      v27 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
      v26 = "Error condition failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)this,
        (unsigned int)byte_18001A0ED,
        a3,
        (_DWORD)a4,
        (__int64)&v26,
        (__int64)&v24,
        (__int64)&v27,
        (__int64)&v25,
        (__int64)&v28,
        (__int64)v29);
    }
    return v9;
  }
  v12 = (char *)operator new(v11);
  v16 = v12;
  if ( v12 )
  {
    *(_DWORD *)v12 = 2;
    *((_DWORD *)v12 + 5) = v5;
    *(_OWORD *)(v12 + 4) = xmmword_180018498;
    memcpy_0(v12 + 24, a2, v5);
    v18 = LsaCallAuthenticationPackage(
            *((HANDLE *)this + 7),
            *((_DWORD *)this + 16),
            v16,
            v11,
            a4,
            ReturnBufferLength,
            &ProtocolStatus);
    if ( v18 && (v9 = v18 | 0x10000000, (v9 & 0x80000000) != 0) )
    {
      if ( (unsigned int)dword_18001F000 > 3 )
      {
        v29[0] = "CallCloudAP";
        v21 = byte_180019FD9;
        v22 = "LsaCallAuthenticationPackage failed";
LABEL_21:
        v28 = v22;
        v27 = "Warning HResult failed";
        v25 = v9;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
          v17,
          (_DWORD)v21,
          v19,
          v20,
          (__int64)&v27,
          (__int64)&v28,
          (__int64)&v25,
          (__int64)v29);
      }
    }
    else
    {
      if ( !ProtocolStatus || (v9 = ProtocolStatus | 0x10000000, ProtocolStatus >= 0) )
      {
        v9 = 0;
        goto LABEL_27;
      }
      if ( (unsigned int)dword_18001F000 > 3 )
      {
        v29[0] = "CallCloudAP";
        v21 = byte_18001A015;
        v22 = "CloudAP returned an error";
        goto LABEL_21;
      }
    }
LABEL_27:
    operator delete(v16);
    return v9;
  }
  v9 = -2147024882;
  if ( (unsigned int)dword_18001F000 > 2 )
  {
    v25 = 449;
    v29[0] = "pCloudApRequest allocation failed";
    v24 = -2147024882;
    v28 = "CallCloudAP";
    v27 = "onecore\\termsrv\\rdp\\win\\security\\cloudaphelper.cpp";
    v26 = "Error condition failed";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
      v13,
      (unsigned int)byte_18001A051,
      v14,
      v15,
      (__int64)&v26,
      (__int64)&v24,
      (__int64)&v27,
      (__int64)&v25,
      (__int64)&v28,
      (__int64)v29);
  }
  return v9;
}

```

## disassembly

```asm
0x18000f1f8  push    rbp
0x18000f1fa  push    rbx
0x18000f1fb  push    rsi
0x18000f1fc  push    rdi
0x18000f1fd  push    r12
0x18000f1ff  push    r13
0x18000f201  push    r14
0x18000f203  push    r15
0x18000f205  lea     rbp, [rsp-17h]
0x18000f20a  sub     rsp, 88h
0x18000f211  mov     ebx, r8d
0x18000f214  mov     r15, r9
0x18000f217  mov     [rbp+4Fh+arg_8], 0
0x18000f21e  mov     r12, rdx
0x18000f221  mov     r13, rcx
0x18000f224  test    rdx, rdx
0x18000f227  jnz     loc_18000F2C0
0x18000f22d  mov     eax, cs:dword_18001F000
0x18000f233  mov     ecx, 80070057h
0x18000f238  mov     ebx, ecx
0x18000f23a  cmp     eax, 2
0x18000f23d  jbe     loc_18000F60E
0x18000f243  lea     rax, aMissingParamte_4; "Missing paramter pRequestJson"
0x18000f24a  mov     [rbp+4Fh+var_70], 1B9h
0x18000f251  mov     [rbp+4Fh+var_68], rax
0x18000f255  lea     rdx, byte_18001A13B
0x18000f25c  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f263  mov     [rbp+4Fh+var_6C], ecx
0x18000f266  mov     [rbp+4Fh+var_60], rax
0x18000f26a  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000f271  mov     [rbp+4Fh+var_58], rax
0x18000f275  lea     rax, aErrorCondition; "Error condition failed"
0x18000f27c  mov     [rbp+4Fh+var_50], rax
0x18000f280  lea     rax, [rbp+4Fh+var_68]
0x18000f284  mov     [rsp+0C0h+var_78], rax
0x18000f289  lea     rax, [rbp+4Fh+var_60]
0x18000f28d  mov     [rsp+0C0h+var_80], rax
0x18000f292  lea     rax, [rbp+4Fh+var_70]
0x18000f296  mov     [rsp+0C0h+var_88], rax
0x18000f29b  lea     rax, [rbp+4Fh+var_58]
0x18000f29f  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f2a4  lea     rax, [rbp+4Fh+var_6C]
0x18000f2a8  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f2ad  lea     rax, [rbp+4Fh+var_50]
0x18000f2b1  mov     [rsp+0C0h+ProtocolReturnBuffer], rax
0x18000f2b6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x18000f2bb  jmp     loc_18000F60E
0x18000f2c0  test    r15, r15
0x18000f2c3  jnz     loc_18000F352
0x18000f2c9  mov     eax, cs:dword_18001F000
0x18000f2cf  mov     ecx, 80070057h
0x18000f2d4  mov     ebx, ecx
0x18000f2d6  cmp     eax, 2
0x18000f2d9  jbe     loc_18000F60E
0x18000f2df  lea     rax, aMissingParamte_5; "Missing paramter ppCloudApResponse"
0x18000f2e6  mov     [rbp+4Fh+var_6C], 1BAh
0x18000f2ed  mov     [rbp+4Fh+var_50], rax
0x18000f2f1  lea     rdx, byte_18001A189
0x18000f2f8  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f2ff  mov     [rbp+4Fh+var_70], ecx
0x18000f302  mov     [rbp+4Fh+var_58], rax
0x18000f306  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000f30d  mov     [rbp+4Fh+var_60], rax
0x18000f311  lea     rax, aErrorCondition; "Error condition failed"
0x18000f318  mov     [rbp+4Fh+var_68], rax
0x18000f31c  lea     rax, [rbp+4Fh+var_50]
0x18000f320  mov     [rsp+0C0h+var_78], rax
0x18000f325  lea     rax, [rbp+4Fh+var_58]
0x18000f329  mov     [rsp+0C0h+var_80], rax
0x18000f32e  lea     rax, [rbp+4Fh+var_6C]
0x18000f332  mov     [rsp+0C0h+var_88], rax
0x18000f337  lea     rax, [rbp+4Fh+var_60]
0x18000f33b  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f340  lea     rax, [rbp+4Fh+var_70]
0x18000f344  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f349  lea     rax, [rbp+4Fh+var_68]
0x18000f34d  jmp     loc_18000F2B1
0x18000f352  mov     r14, [rbp+4Fh+arg_20]
0x18000f356  test    r14, r14
0x18000f359  jnz     loc_18000F3E8
0x18000f35f  mov     eax, cs:dword_18001F000
0x18000f365  mov     ecx, 80070057h
0x18000f36a  mov     ebx, ecx
0x18000f36c  cmp     eax, 2
0x18000f36f  jbe     loc_18000F60E
0x18000f375  lea     rax, aMissingParamte_1; "Missing paramter pcbCloudApResponse"
0x18000f37c  mov     [rbp+4Fh+var_6C], 1BBh
0x18000f383  mov     [rbp+4Fh+var_50], rax
0x18000f387  lea     rdx, byte_18001A09F
0x18000f38e  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f395  mov     [rbp+4Fh+var_70], ecx
0x18000f398  mov     [rbp+4Fh+var_58], rax
0x18000f39c  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000f3a3  mov     [rbp+4Fh+var_60], rax
0x18000f3a7  lea     rax, aErrorCondition; "Error condition failed"
0x18000f3ae  mov     [rbp+4Fh+var_68], rax
0x18000f3b2  lea     rax, [rbp+4Fh+var_50]
0x18000f3b6  mov     [rsp+0C0h+var_78], rax
0x18000f3bb  lea     rax, [rbp+4Fh+var_58]
0x18000f3bf  mov     [rsp+0C0h+var_80], rax
0x18000f3c4  lea     rax, [rbp+4Fh+var_6C]
0x18000f3c8  mov     [rsp+0C0h+var_88], rax
0x18000f3cd  lea     rax, [rbp+4Fh+var_60]
0x18000f3d1  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f3d6  lea     rax, [rbp+4Fh+var_70]
0x18000f3da  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f3df  lea     rax, [rbp+4Fh+var_68]
0x18000f3e3  jmp     loc_18000F2B1
0x18000f3e8  lea     esi, [rbx+1Bh]
0x18000f3eb  cmp     esi, ebx
0x18000f3ed  ja      loc_18000F47A
0x18000f3f3  mov     eax, cs:dword_18001F000
0x18000f3f9  mov     ebx, 80004005h
0x18000f3fe  cmp     eax, 2
0x18000f401  jbe     loc_18000F60E
0x18000f407  lea     rax, aIntegerOverflo; "Integer overflow check failed failed"
0x18000f40e  mov     [rbp+4Fh+var_6C], 1BEh
0x18000f415  mov     [rbp+4Fh+var_50], rax
0x18000f419  lea     rdx, byte_18001A0ED
0x18000f420  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f427  mov     [rbp+4Fh+var_70], ebx
0x18000f42a  mov     [rbp+4Fh+var_58], rax
0x18000f42e  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000f435  mov     [rbp+4Fh+var_60], rax
0x18000f439  lea     rax, aErrorCondition; "Error condition failed"
0x18000f440  mov     [rbp+4Fh+var_68], rax
0x18000f444  lea     rax, [rbp+4Fh+var_50]
0x18000f448  mov     [rsp+0C0h+var_78], rax
0x18000f44d  lea     rax, [rbp+4Fh+var_58]
0x18000f451  mov     [rsp+0C0h+var_80], rax
0x18000f456  lea     rax, [rbp+4Fh+var_6C]
0x18000f45a  mov     [rsp+0C0h+var_88], rax
0x18000f45f  lea     rax, [rbp+4Fh+var_60]
0x18000f463  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f468  lea     rax, [rbp+4Fh+var_70]
0x18000f46c  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f471  lea     rax, [rbp+4Fh+var_68]
0x18000f475  jmp     loc_18000F2B1
0x18000f47a  mov     ecx, esi; Size
0x18000f47c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f481  mov     rdi, rax
0x18000f484  test    rax, rax
0x18000f487  jnz     loc_18000F514
0x18000f48d  mov     eax, cs:dword_18001F000
0x18000f493  mov     ebx, 8007000Eh
0x18000f498  cmp     eax, 2
0x18000f49b  jbe     loc_18000F60E
0x18000f4a1  lea     rax, aPcloudapreques; "pCloudApRequest allocation failed"
0x18000f4a8  mov     [rbp+4Fh+var_6C], 1C1h
0x18000f4af  mov     [rbp+4Fh+var_50], rax
0x18000f4b3  lea     rdx, byte_18001A051
0x18000f4ba  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f4c1  mov     [rbp+4Fh+var_70], ebx
0x18000f4c4  mov     [rbp+4Fh+var_58], rax
0x18000f4c8  lea     rax, aOnecoreTermsrv_0; "onecore\\termsrv\\rdp\\win\\security\\c"...
0x18000f4cf  mov     [rbp+4Fh+var_60], rax
0x18000f4d3  lea     rax, aErrorCondition; "Error condition failed"
0x18000f4da  mov     [rbp+4Fh+var_68], rax
0x18000f4de  lea     rax, [rbp+4Fh+var_50]
0x18000f4e2  mov     [rsp+0C0h+var_78], rax
0x18000f4e7  lea     rax, [rbp+4Fh+var_58]
0x18000f4eb  mov     [rsp+0C0h+var_80], rax
0x18000f4f0  lea     rax, [rbp+4Fh+var_6C]
0x18000f4f4  mov     [rsp+0C0h+var_88], rax
0x18000f4f9  lea     rax, [rbp+4Fh+var_60]
0x18000f4fd  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f502  lea     rax, [rbp+4Fh+var_70]
0x18000f506  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f50b  lea     rax, [rbp+4Fh+var_68]
0x18000f50f  jmp     loc_18000F2B1
0x18000f514  movups  xmm0, cs:xmmword_180018498
0x18000f51b  mov     r8, rbx; Size
0x18000f51e  mov     dword ptr [rax], 2
0x18000f524  lea     rcx, [rax+18h]; void *
0x18000f528  mov     [rax+14h], ebx
0x18000f52b  mov     rdx, r12; Src
0x18000f52e  movdqu  xmmword ptr [rax+4], xmm0
0x18000f533  call    memcpy_0
0x18000f538  mov     edx, [r13+40h]; AuthenticationPackage
0x18000f53c  lea     rax, [rbp+4Fh+arg_8]
0x18000f540  mov     rcx, [r13+38h]; LsaHandle
0x18000f544  mov     r9d, esi; SubmitBufferLength
0x18000f547  mov     [rsp+0C0h+ProtocolStatus], rax; ProtocolStatus
0x18000f54c  mov     r8, rdi; ProtocolSubmitBuffer
0x18000f54f  mov     [rsp+0C0h+ReturnBufferLength], r14; ReturnBufferLength
0x18000f554  mov     [rsp+0C0h+ProtocolReturnBuffer], r15; ProtocolReturnBuffer
0x18000f559  call    cs:__imp_LsaCallAuthenticationPackage
0x18000f55f  mov     ebx, eax
0x18000f561  mov     eax, 10000000h
0x18000f566  test    ebx, ebx
0x18000f568  jz      short loc_18000F5D3
0x18000f56a  or      ebx, eax
0x18000f56c  jge     short loc_18000F5D3
0x18000f56e  mov     eax, cs:dword_18001F000
0x18000f574  cmp     eax, 3
0x18000f577  jbe     loc_18000F606
0x18000f57d  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f584  mov     [rbp+4Fh+var_50], rax
0x18000f588  lea     rdx, byte_180019FD9
0x18000f58f  lea     rax, aLsacallauthent; "LsaCallAuthenticationPackage failed"
0x18000f596  mov     [rbp+4Fh+var_58], rax
0x18000f59a  lea     rax, aWarningHresult; "Warning HResult failed"
0x18000f5a1  mov     [rbp+4Fh+var_60], rax
0x18000f5a5  lea     rax, [rbp+4Fh+var_50]
0x18000f5a9  mov     [rsp+0C0h+var_88], rax
0x18000f5ae  lea     rax, [rbp+4Fh+var_6C]
0x18000f5b2  mov     [rsp+0C0h+ProtocolStatus], rax
0x18000f5b7  lea     rax, [rbp+4Fh+var_58]
0x18000f5bb  mov     [rsp+0C0h+ReturnBufferLength], rax
0x18000f5c0  lea     rax, [rbp+4Fh+var_60]
0x18000f5c4  mov     [rsp+0C0h+ProtocolReturnBuffer], rax
0x18000f5c9  mov     [rbp+4Fh+var_6C], ebx
0x18000f5cc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x18000f5d1  jmp     short loc_18000F606
0x18000f5d3  mov     ebx, [rbp+4Fh+arg_8]
0x18000f5d6  test    ebx, ebx
0x18000f5d8  jz      short loc_18000F604
0x18000f5da  or      ebx, eax
0x18000f5dc  jge     short loc_18000F604
0x18000f5de  mov     eax, cs:dword_18001F000
0x18000f5e4  cmp     eax, 3
0x18000f5e7  jbe     short loc_18000F606
0x18000f5e9  lea     rax, aCallcloudap; "CallCloudAP"
0x18000f5f0  mov     [rbp+4Fh+var_50], rax
0x18000f5f4  lea     rdx, byte_18001A015
0x18000f5fb  lea     rax, aCloudapReturne_0; "CloudAP returned an error"
0x18000f602  jmp     short loc_18000F596
0x18000f604  xor     ebx, ebx
0x18000f606  mov     rcx, rdi; Block
0x18000f609  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000f60e  mov     eax, ebx
0x18000f610  add     rsp, 88h
0x18000f617  pop     r15
0x18000f619  pop     r14
0x18000f61b  pop     r13
0x18000f61d  pop     r12
0x18000f61f  pop     rdi
0x18000f620  pop     rsi
0x18000f621  pop     rbx
0x18000f622  pop     rbp
0x18000f623  retn
```
