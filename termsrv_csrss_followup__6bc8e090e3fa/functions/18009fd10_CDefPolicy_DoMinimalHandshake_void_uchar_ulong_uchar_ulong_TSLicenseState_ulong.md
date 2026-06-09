# CDefPolicy::DoMinimalHandshake(void * *,uchar * *,ulong *,uchar * *,ulong *,TSLicenseState *,ulong *)

- ea: `0x18009fd10`
- end: `0x1800a0037`
- name: `?DoMinimalHandshake@CDefPolicy@@UEAAJPEAPEAXPEAPEAEPEAK12PEAW4TSLicenseState@@2@Z`
- size: `807`
- prototype: `__int64 __fastcall(CDefPolicy *__hidden this, void **, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, enum TSLicenseState *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800a0200`

## callees

- `0x18000542c`
- `0x180012210`
- `0x1800978b8`
- `0x18009fd10`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009fdab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009feaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009ff65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009fdab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009feaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009ff65`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ff19`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009ff19`

## string_xrefs

- `0x18009ff37`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_PROTOCOL_BEGIN`
- `0x18009fe46`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_LICENSING_CAPABILITIES_OBTAINED`
- `0x18009fd7f`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_CLIENT_LICENSE_SENT`
- `0x18009fe14`: `TSLTEST: License Protocol Handshake Complete.\n`

## pseudocode

```c
__int64 __fastcall CDefPolicy::DoMinimalHandshake(
        CDefPolicy *this,
        void **a2,
        unsigned __int8 **a3,
        unsigned int *a4,
        unsigned __int8 **a5,
        unsigned int *a6,
        enum TSLicenseState *a7,
        unsigned int *a8)
{
  enum TSLicenseState *v8; // r14
  unsigned int v9; // r12d
  unsigned int v12; // ebx
  const char *v13; // rax
  char *v14; // rdx
  unsigned __int8 *v15; // rax
  _BYTE *v16; // rbx
  unsigned __int8 *v17; // rax
  _DWORD *v18; // rdx
  unsigned __int8 *v19; // rax
  const char *v21; // [rsp+30h] [rbp-18h] BYREF

  v8 = a7;
  v9 = 0;
  if ( *(_DWORD *)a7 == 1 )
  {
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_PROTOCOL_BEGIN";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18012E170,
        (unsigned int)byte_180119AF5,
        0,
        0,
        (__int64)&a7);
    }
    v19 = (unsigned __int8 *)CoTaskMemAlloc(0x40u);
    *a3 = v19;
    if ( !v19 )
    {
      v12 = 1;
      if ( (unsigned int)dword_18012E170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake - ppClientData : Memory Error";
        v14 = byte_180119B13;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    *a4 = 64;
    *((_DWORD *)*a3 + 4) = 42;
    *(_DWORD *)v8 = 2;
    goto LABEL_32;
  }
  if ( *(_DWORD *)a7 == 3 )
  {
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_LICENSING_CAPABILITIES_OBTAINED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18012E170,
        (unsigned int)byte_180119AB9,
        0,
        0,
        (__int64)&a7);
    }
    if ( *a4 != 64 )
    {
      v12 = 15;
      if ( (unsigned int)dword_18012E170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake FAILED - Invalid data for TSLIC_LICENSING_CAPABILITIES_OBTAINED";
        v14 = &byte_180119AD7;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    v16 = *a3;
    WORD1(a7) = 16;
    v17 = (unsigned __int8 *)CoTaskMemAlloc(0x10u);
    *a5 = v17;
    if ( !v17 )
    {
      v12 = 1;
      if ( (unsigned int)dword_18012E170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake - ppResponse : Memory Error";
        v14 = byte_180119A7D;
        goto LABEL_27;
      }
      goto LABEL_28;
    }
    LOBYTE(a7) = -1;
    *a6 = 16;
    v18 = *a5;
    BYTE1(a7) = v16[4];
    *v18 = (_DWORD)a7;
    v18[1] = 7;
    v18[2] = 2;
    v18[3] = 4;
    CoTaskMemFree(v16);
    *a3 = 0;
    *a4 = 0;
    *(_DWORD *)v8 = 4;
LABEL_32:
    v12 = 0;
    goto LABEL_33;
  }
  if ( *(_DWORD *)a7 != 5 )
  {
    v12 = 3;
    if ( (unsigned int)dword_18012E170 > 4 )
    {
      v13 = "CDefPolicy::DoMinimalHandshake - Invalid State";
      v14 = (char *)word_1801199FA;
LABEL_27:
      a7 = (enum TSLicenseState *)v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_18012E170,
        (_DWORD)v14,
        0,
        0,
        (__int64)&a7);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_CLIENT_LICENSE_SENT";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_18012E170,
      (unsigned int)byte_180119A9B,
      0,
      0,
      (__int64)&a7);
  }
  v15 = (unsigned __int8 *)CoTaskMemAlloc(4u);
  *a5 = v15;
  if ( !v15 )
  {
    v12 = 1;
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      v13 = "CDefPolicy::DoMinimalHandshake - ppResponse : Memory Error";
      v14 = byte_180119A41;
      goto LABEL_27;
    }
LABEL_28:
    if ( (unsigned int)dword_18012E170 > 2 )
    {
      LODWORD(a7) = v12;
      v21 = "CDefPolicy::DoMinimalHandshake FAILED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_18012E170,
        (unsigned int)qword_180119A18,
        0,
        0,
        (__int64)&v21,
        (__int64)&a7);
    }
    v9 = -2147467259;
    goto LABEL_33;
  }
  v12 = 0;
  *a6 = 4;
  *(_DWORD *)*a5 = 1;
  *a3 = 0;
  *a4 = 0;
  *(_DWORD *)v8 = 8;
  if ( (unsigned int)dword_18012E170 > 4 )
  {
    a7 = (enum TSLicenseState *)"TSLTEST: License Protocol Handshake Complete.\n";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_18012E170,
      (unsigned int)&byte_180119A5F,
      0,
      0,
      (__int64)&a7);
  }
LABEL_33:
  *a8 = LsStatusToClientError(v12);
  return v9;
}

```

## disassembly

```asm
0x18009fd10  push    rbp
0x18009fd12  push    rbx
0x18009fd13  push    rsi
0x18009fd14  push    rdi
0x18009fd15  push    r12
0x18009fd17  push    r13
0x18009fd19  push    r14
0x18009fd1b  push    r15
0x18009fd1d  mov     rbp, rsp
0x18009fd20  sub     rsp, 48h
0x18009fd24  mov     r14, [rbp+arg_30]
0x18009fd28  lea     r13, dword_18012E170
0x18009fd2f  mov     eax, cs:dword_18012E170
0x18009fd35  xor     r12d, r12d
0x18009fd38  mov     r15, r9
0x18009fd3b  mov     rsi, r8
0x18009fd3e  mov     ecx, [r14]
0x18009fd41  lea     edi, [r12+4]
0x18009fd46  sub     ecx, 1
0x18009fd49  jz      loc_18009FF33
0x18009fd4f  sub     ecx, 2
0x18009fd52  jz      loc_18009FE42
0x18009fd58  cmp     ecx, 2
0x18009fd5b  jz      short loc_18009FD7B
0x18009fd5d  lea     ebx, [rdi-1]
0x18009fd60  cmp     eax, edi
0x18009fd62  jbe     loc_18009FFB0
0x18009fd68  lea     rax, aCdefpolicyDomi_3; "CDefPolicy::DoMinimalHandshake - Invali"...
0x18009fd6f  lea     rdx, word_1801199FA
0x18009fd76  jmp     loc_18009FF95
0x18009fd7b  cmp     eax, edi
0x18009fd7d  jbe     short loc_18009FDA8
0x18009fd7f  lea     rax, aCdefpolicyDomi_5; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009fd86  xor     r9d, r9d
0x18009fd89  mov     [rbp+arg_30], rax
0x18009fd8d  lea     rdx, byte_180119A9B
0x18009fd94  lea     rax, [rbp+arg_30]
0x18009fd98  xor     r8d, r8d
0x18009fd9b  mov     rcx, r13
0x18009fd9e  mov     [rsp+48h+var_28], rax
0x18009fda3  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fda8  mov     rcx, rdi; cb
0x18009fdab  call    cs:__imp_CoTaskMemAlloc
0x18009fdb2  nop     dword ptr [rax+rax+00h]
0x18009fdb7  mov     rcx, [rbp+arg_20]
0x18009fdbb  mov     [rcx], rax
0x18009fdbe  test    rax, rax
0x18009fdc1  jnz     short loc_18009FDE8
0x18009fdc3  lea     ebx, [rax+1]
0x18009fdc6  mov     eax, cs:dword_18012E170
0x18009fdcc  cmp     eax, 2
0x18009fdcf  jbe     loc_18009FFB0
0x18009fdd5  lea     rax, aCdefpolicyDomi_6; "CDefPolicy::DoMinimalHandshake - ppResp"...
0x18009fddc  lea     rdx, byte_180119A41
0x18009fde3  jmp     loc_18009FF95
0x18009fde8  mov     rax, [rbp+arg_28]
0x18009fdec  xor     ebx, ebx
0x18009fdee  mov     [rax], edi
0x18009fdf0  mov     rax, [rcx]
0x18009fdf3  mov     dword ptr [rax], 1
0x18009fdf9  mov     [rsi], r12
0x18009fdfc  mov     [r15], r12d
0x18009fdff  mov     dword ptr [r14], 8
0x18009fe06  mov     eax, cs:dword_18012E170
0x18009fe0c  cmp     eax, edi
0x18009fe0e  jbe     loc_1800A0012
0x18009fe14  lea     rax, aTsltestLicense; "TSLTEST: License Protocol Handshake Com"...
0x18009fe1b  xor     r9d, r9d
0x18009fe1e  mov     [rbp+arg_30], rax
0x18009fe22  lea     rdx, byte_180119A5F
0x18009fe29  lea     rax, [rbp+arg_30]
0x18009fe2d  xor     r8d, r8d
0x18009fe30  mov     rcx, r13
0x18009fe33  mov     [rsp+48h+var_28], rax
0x18009fe38  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fe3d  jmp     loc_1800A0012
0x18009fe42  cmp     eax, edi
0x18009fe44  jbe     short loc_18009FE6F
0x18009fe46  lea     rax, aCdefpolicyDomi_4; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009fe4d  xor     r9d, r9d
0x18009fe50  mov     [rbp+arg_30], rax
0x18009fe54  lea     rdx, byte_180119AB9
0x18009fe5b  lea     rax, [rbp+arg_30]
0x18009fe5f  xor     r8d, r8d
0x18009fe62  mov     rcx, r13
0x18009fe65  mov     [rsp+48h+var_28], rax
0x18009fe6a  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009fe6f  cmp     dword ptr [r15], 40h ; '@'
0x18009fe73  jz      short loc_18009FE9C
0x18009fe75  mov     eax, cs:dword_18012E170
0x18009fe7b  mov     ebx, 0Fh
0x18009fe80  cmp     eax, 2
0x18009fe83  jbe     loc_18009FFB0
0x18009fe89  lea     rax, aCdefpolicyDomi_1; "CDefPolicy::DoMinimalHandshake FAILED -"...
0x18009fe90  lea     rdx, byte_180119AD7
0x18009fe97  jmp     loc_18009FF95
0x18009fe9c  mov     rbx, [rsi]
0x18009fe9f  mov     eax, 10h
0x18009fea4  mov     ecx, eax; cb
0x18009fea6  mov     word ptr [rbp+arg_30+2], ax
0x18009feaa  call    cs:__imp_CoTaskMemAlloc
0x18009feb1  nop     dword ptr [rax+rax+00h]
0x18009feb6  mov     rdx, [rbp+arg_20]
0x18009feba  mov     [rdx], rax
0x18009febd  test    rax, rax
0x18009fec0  jnz     short loc_18009FEE7
0x18009fec2  lea     ebx, [rax+1]
0x18009fec5  mov     eax, cs:dword_18012E170
0x18009fecb  cmp     eax, 2
0x18009fece  jbe     loc_18009FFB0
0x18009fed4  lea     rax, aCdefpolicyDomi_6; "CDefPolicy::DoMinimalHandshake - ppResp"...
0x18009fedb  lea     rdx, byte_180119A7D
0x18009fee2  jmp     loc_18009FF95
0x18009fee7  mov     rax, [rbp+arg_28]
0x18009feeb  mov     rcx, rbx; pv
0x18009feee  mov     byte ptr [rbp+arg_30], 0FFh
0x18009fef2  mov     dword ptr [rax], 10h
0x18009fef8  mov     al, [rbx+4]
0x18009fefb  mov     rdx, [rdx]
0x18009fefe  mov     byte ptr [rbp+arg_30+1], al
0x18009ff01  mov     eax, dword ptr [rbp+arg_30]
0x18009ff04  mov     [rdx], eax
0x18009ff06  mov     dword ptr [rdx+4], 7
0x18009ff0d  mov     dword ptr [rdx+rdi+4], 2
0x18009ff15  mov     [rdx+rdi+8], edi
0x18009ff19  call    cs:__imp_CoTaskMemFree
0x18009ff20  nop     dword ptr [rax+rax+00h]
0x18009ff25  mov     [rsi], r12
0x18009ff28  mov     [r15], r12d
0x18009ff2b  mov     [r14], edi
0x18009ff2e  jmp     loc_1800A0010
0x18009ff33  cmp     eax, edi
0x18009ff35  jbe     short loc_18009FF60
0x18009ff37  lea     rax, aCdefpolicyDomi; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009ff3e  xor     r9d, r9d
0x18009ff41  mov     [rbp+arg_30], rax
0x18009ff45  lea     rdx, byte_180119AF5
0x18009ff4c  lea     rax, [rbp+arg_30]
0x18009ff50  xor     r8d, r8d
0x18009ff53  mov     rcx, r13
0x18009ff56  mov     [rsp+48h+var_28], rax
0x18009ff5b  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ff60  mov     ecx, 40h ; '@'; cb
0x18009ff65  call    cs:__imp_CoTaskMemAlloc
0x18009ff6c  nop     dword ptr [rax+rax+00h]
0x18009ff71  mov     [rsi], rax
0x18009ff74  test    rax, rax
0x18009ff77  jnz     short loc_18009FFF8
0x18009ff79  lea     ebx, [rax+1]
0x18009ff7c  mov     eax, cs:dword_18012E170
0x18009ff82  cmp     eax, 2
0x18009ff85  jbe     short loc_18009FFB0
0x18009ff87  lea     rax, aCdefpolicyDomi_2; "CDefPolicy::DoMinimalHandshake - ppClie"...
0x18009ff8e  lea     rdx, byte_180119B13
0x18009ff95  mov     [rbp+arg_30], rax
0x18009ff99  xor     r9d, r9d
0x18009ff9c  lea     rax, [rbp+arg_30]
0x18009ffa0  xor     r8d, r8d
0x18009ffa3  mov     rcx, r13
0x18009ffa6  mov     [rsp+48h+var_28], rax
0x18009ffab  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009ffb0  mov     eax, cs:dword_18012E170
0x18009ffb6  cmp     eax, 2
0x18009ffb9  jbe     short loc_18009FFF0
0x18009ffbb  lea     rax, aCdefpolicyDomi_0; "CDefPolicy::DoMinimalHandshake FAILED"
0x18009ffc2  mov     dword ptr [rbp+arg_30], ebx
0x18009ffc5  mov     [rbp+var_18], rax
0x18009ffc9  lea     rdx, qword_180119A18
0x18009ffd0  lea     rax, [rbp+arg_30]
0x18009ffd4  xor     r9d, r9d
0x18009ffd7  mov     [rsp+48h+var_20], rax
0x18009ffdc  xor     r8d, r8d
0x18009ffdf  lea     rax, [rbp+var_18]
0x18009ffe3  mov     rcx, r13
0x18009ffe6  mov     [rsp+48h+var_28], rax
0x18009ffeb  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009fff0  mov     r12d, 80004005h
0x18009fff6  jmp     short loc_1800A0012
0x18009fff8  mov     dword ptr [r15], 40h ; '@'
0x18009ffff  mov     rcx, [rsi]
0x1800a0002  mov     dword ptr [rcx+10h], 2Ah ; '*'
0x1800a0009  mov     dword ptr [r14], 2
0x1800a0010  xor     ebx, ebx
0x1800a0012  mov     ecx, ebx; unsigned int
0x1800a0014  call    ?LsStatusToClientError@@YAKK@Z; LsStatusToClientError(ulong)
0x1800a0019  mov     rcx, [rbp+arg_38]
0x1800a0020  mov     [rcx], eax
0x1800a0022  mov     eax, r12d
0x1800a0025  add     rsp, 48h
0x1800a0029  pop     r15
0x1800a002b  pop     r14
0x1800a002d  pop     r13
0x1800a002f  pop     r12
0x1800a0031  pop     rdi
0x1800a0032  pop     rsi
0x1800a0033  pop     rbx
0x1800a0034  pop     rbp
0x1800a0035  retn
```
