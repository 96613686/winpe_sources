# CDefPolicy::DoMinimalHandshake(void * *,uchar * *,ulong *,uchar * *,ulong *,TSLicenseState *,ulong *)

- ea: `0x18009bae0`
- end: `0x18009bdee`
- name: `?DoMinimalHandshake@CDefPolicy@@UEAAJPEAPEAXPEAPEAEPEAK12PEAW4TSLicenseState@@2@Z`
- size: `782`
- prototype: `__int64 __fastcall(CDefPolicy *__hidden this, void **, unsigned __int8 **, unsigned int *, unsigned __int8 **, unsigned int *, enum TSLicenseState *, unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18009bfc0`

## callees

- `0x1800053e4`
- `0x180011a80`
- `0x1800938b8`
- `0x18009bae0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bc74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bb7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bc74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18009bd23`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bcdd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18009bcdd`

## string_xrefs

- `0x18009bcf5`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_PROTOCOL_BEGIN`
- `0x18009bc10`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_LICENSING_CAPABILITIES_OBTAINED`
- `0x18009bbde`: `TSLTEST: License Protocol Handshake Complete.\n`
- `0x18009bb4f`: `CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_CLIENT_LICENSE_SENT`

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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_PROTOCOL_BEGIN";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_180128170,
        (unsigned int)byte_180113A93,
        0,
        0,
        (__int64)&a7);
    }
    v19 = (unsigned __int8 *)CoTaskMemAlloc(0x40u);
    *a3 = v19;
    if ( !v19 )
    {
      v12 = 1;
      if ( (unsigned int)dword_180128170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake - ppClientData : Memory Error";
        v14 = &byte_180113A57;
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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_LICENSING_CAPABILITIES_OBTAINED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_180128170,
        (unsigned int)byte_180113A75,
        0,
        0,
        (__int64)&a7);
    }
    if ( *a4 != 64 )
    {
      v12 = 15;
      if ( (unsigned int)dword_180128170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake FAILED - Invalid data for TSLIC_LICENSING_CAPABILITIES_OBTAINED";
        v14 = byte_180113A1B;
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
      if ( (unsigned int)dword_180128170 > 2 )
      {
        v13 = "CDefPolicy::DoMinimalHandshake - ppResponse : Memory Error";
        v14 = byte_180113A39;
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
    if ( (unsigned int)dword_180128170 > 4 )
    {
      v13 = "CDefPolicy::DoMinimalHandshake - Invalid State";
      v14 = byte_1801139C1;
LABEL_27:
      a7 = (enum TSLicenseState *)v13;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        (unsigned int)&dword_180128170,
        (_DWORD)v14,
        0,
        0,
        (__int64)&a7);
      goto LABEL_28;
    }
    goto LABEL_28;
  }
  if ( (unsigned int)dword_180128170 > 4 )
  {
    a7 = (enum TSLicenseState *)"CDefPolicy::DoMinimalHandshake - Protocol State : TSLIC_CLIENT_LICENSE_SENT";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180128170,
      (unsigned int)&byte_1801139DF,
      0,
      0,
      (__int64)&a7);
  }
  v15 = (unsigned __int8 *)CoTaskMemAlloc(4u);
  *a5 = v15;
  if ( !v15 )
  {
    v12 = 1;
    if ( (unsigned int)dword_180128170 > 2 )
    {
      v13 = "CDefPolicy::DoMinimalHandshake - ppResponse : Memory Error";
      v14 = byte_1801139FD;
      goto LABEL_27;
    }
LABEL_28:
    if ( (unsigned int)dword_180128170 > 2 )
    {
      LODWORD(a7) = v12;
      v21 = "CDefPolicy::DoMinimalHandshake FAILED";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (unsigned int)&dword_180128170,
        (unsigned int)word_18011397A,
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
  if ( (unsigned int)dword_180128170 > 4 )
  {
    a7 = (enum TSLicenseState *)"TSLTEST: License Protocol Handshake Complete.\n";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
      (unsigned int)&dword_180128170,
      (unsigned int)byte_1801139A3,
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
0x18009bae0  push    rbp
0x18009bae2  push    rbx
0x18009bae3  push    rsi
0x18009bae4  push    rdi
0x18009bae5  push    r12
0x18009bae7  push    r13
0x18009bae9  push    r14
0x18009baeb  push    r15
0x18009baed  mov     rbp, rsp
0x18009baf0  sub     rsp, 48h
0x18009baf4  mov     r14, [rbp+arg_30]
0x18009baf8  lea     r13, dword_180128170
0x18009baff  mov     eax, cs:dword_180128170
0x18009bb05  xor     r12d, r12d
0x18009bb08  mov     r15, r9
0x18009bb0b  mov     rsi, r8
0x18009bb0e  mov     ecx, [r14]
0x18009bb11  lea     edi, [r12+4]
0x18009bb16  sub     ecx, 1
0x18009bb19  jz      loc_18009BCF1
0x18009bb1f  sub     ecx, 2
0x18009bb22  jz      loc_18009BC0C
0x18009bb28  cmp     ecx, 2
0x18009bb2b  jz      short loc_18009BB4B
0x18009bb2d  lea     ebx, [rdi-1]
0x18009bb30  cmp     eax, edi
0x18009bb32  jbe     loc_18009BD68
0x18009bb38  lea     rax, aCdefpolicyDomi_3; "CDefPolicy::DoMinimalHandshake - Invali"...
0x18009bb3f  lea     rdx, byte_1801139C1
0x18009bb46  jmp     loc_18009BD4D
0x18009bb4b  cmp     eax, edi
0x18009bb4d  jbe     short loc_18009BB78
0x18009bb4f  lea     rax, aCdefpolicyDomi_5; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009bb56  xor     r9d, r9d
0x18009bb59  mov     [rbp+arg_30], rax
0x18009bb5d  lea     rdx, byte_1801139DF
0x18009bb64  lea     rax, [rbp+arg_30]
0x18009bb68  xor     r8d, r8d
0x18009bb6b  mov     rcx, r13
0x18009bb6e  mov     [rsp+48h+var_28], rax
0x18009bb73  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009bb78  mov     rcx, rdi; cb
0x18009bb7b  call    cs:__imp_CoTaskMemAlloc
0x18009bb81  mov     rcx, [rbp+arg_20]
0x18009bb85  mov     [rcx], rax
0x18009bb88  test    rax, rax
0x18009bb8b  jnz     short loc_18009BBB2
0x18009bb8d  lea     ebx, [rax+1]
0x18009bb90  mov     eax, cs:dword_180128170
0x18009bb96  cmp     eax, 2
0x18009bb99  jbe     loc_18009BD68
0x18009bb9f  lea     rax, aCdefpolicyDomi_6; "CDefPolicy::DoMinimalHandshake - ppResp"...
0x18009bba6  lea     rdx, byte_1801139FD
0x18009bbad  jmp     loc_18009BD4D
0x18009bbb2  mov     rax, [rbp+arg_28]
0x18009bbb6  xor     ebx, ebx
0x18009bbb8  mov     [rax], edi
0x18009bbba  mov     rax, [rcx]
0x18009bbbd  mov     dword ptr [rax], 1
0x18009bbc3  mov     [rsi], r12
0x18009bbc6  mov     [r15], r12d
0x18009bbc9  mov     dword ptr [r14], 8
0x18009bbd0  mov     eax, cs:dword_180128170
0x18009bbd6  cmp     eax, edi
0x18009bbd8  jbe     loc_18009BDCA
0x18009bbde  lea     rax, aTsltestLicense; "TSLTEST: License Protocol Handshake Com"...
0x18009bbe5  xor     r9d, r9d
0x18009bbe8  mov     [rbp+arg_30], rax
0x18009bbec  lea     rdx, byte_1801139A3
0x18009bbf3  lea     rax, [rbp+arg_30]
0x18009bbf7  xor     r8d, r8d
0x18009bbfa  mov     rcx, r13
0x18009bbfd  mov     [rsp+48h+var_28], rax
0x18009bc02  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009bc07  jmp     loc_18009BDCA
0x18009bc0c  cmp     eax, edi
0x18009bc0e  jbe     short loc_18009BC39
0x18009bc10  lea     rax, aCdefpolicyDomi_4; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009bc17  xor     r9d, r9d
0x18009bc1a  mov     [rbp+arg_30], rax
0x18009bc1e  lea     rdx, byte_180113A75
0x18009bc25  lea     rax, [rbp+arg_30]
0x18009bc29  xor     r8d, r8d
0x18009bc2c  mov     rcx, r13
0x18009bc2f  mov     [rsp+48h+var_28], rax
0x18009bc34  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009bc39  cmp     dword ptr [r15], 40h ; '@'
0x18009bc3d  jz      short loc_18009BC66
0x18009bc3f  mov     eax, cs:dword_180128170
0x18009bc45  mov     ebx, 0Fh
0x18009bc4a  cmp     eax, 2
0x18009bc4d  jbe     loc_18009BD68
0x18009bc53  lea     rax, aCdefpolicyDomi_1; "CDefPolicy::DoMinimalHandshake FAILED -"...
0x18009bc5a  lea     rdx, byte_180113A1B
0x18009bc61  jmp     loc_18009BD4D
0x18009bc66  mov     rbx, [rsi]
0x18009bc69  mov     eax, 10h
0x18009bc6e  mov     ecx, eax; cb
0x18009bc70  mov     word ptr [rbp+arg_30+2], ax
0x18009bc74  call    cs:__imp_CoTaskMemAlloc
0x18009bc7a  mov     rdx, [rbp+arg_20]
0x18009bc7e  mov     [rdx], rax
0x18009bc81  test    rax, rax
0x18009bc84  jnz     short loc_18009BCAB
0x18009bc86  lea     ebx, [rax+1]
0x18009bc89  mov     eax, cs:dword_180128170
0x18009bc8f  cmp     eax, 2
0x18009bc92  jbe     loc_18009BD68
0x18009bc98  lea     rax, aCdefpolicyDomi_6; "CDefPolicy::DoMinimalHandshake - ppResp"...
0x18009bc9f  lea     rdx, byte_180113A39
0x18009bca6  jmp     loc_18009BD4D
0x18009bcab  mov     rax, [rbp+arg_28]
0x18009bcaf  mov     rcx, rbx; pv
0x18009bcb2  mov     byte ptr [rbp+arg_30], 0FFh
0x18009bcb6  mov     dword ptr [rax], 10h
0x18009bcbc  mov     al, [rbx+4]
0x18009bcbf  mov     rdx, [rdx]
0x18009bcc2  mov     byte ptr [rbp+arg_30+1], al
0x18009bcc5  mov     eax, dword ptr [rbp+arg_30]
0x18009bcc8  mov     [rdx], eax
0x18009bcca  mov     dword ptr [rdx+4], 7
0x18009bcd1  mov     dword ptr [rdx+rdi+4], 2
0x18009bcd9  mov     [rdx+rdi+8], edi
0x18009bcdd  call    cs:__imp_CoTaskMemFree
0x18009bce3  mov     [rsi], r12
0x18009bce6  mov     [r15], r12d
0x18009bce9  mov     [r14], edi
0x18009bcec  jmp     loc_18009BDC8
0x18009bcf1  cmp     eax, edi
0x18009bcf3  jbe     short loc_18009BD1E
0x18009bcf5  lea     rax, aCdefpolicyDomi; "CDefPolicy::DoMinimalHandshake - Protoc"...
0x18009bcfc  xor     r9d, r9d
0x18009bcff  mov     [rbp+arg_30], rax
0x18009bd03  lea     rdx, byte_180113A93
0x18009bd0a  lea     rax, [rbp+arg_30]
0x18009bd0e  xor     r8d, r8d
0x18009bd11  mov     rcx, r13
0x18009bd14  mov     [rsp+48h+var_28], rax
0x18009bd19  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009bd1e  mov     ecx, 40h ; '@'; cb
0x18009bd23  call    cs:__imp_CoTaskMemAlloc
0x18009bd29  mov     [rsi], rax
0x18009bd2c  test    rax, rax
0x18009bd2f  jnz     short loc_18009BDB0
0x18009bd31  lea     ebx, [rax+1]
0x18009bd34  mov     eax, cs:dword_180128170
0x18009bd3a  cmp     eax, 2
0x18009bd3d  jbe     short loc_18009BD68
0x18009bd3f  lea     rax, aCdefpolicyDomi_2; "CDefPolicy::DoMinimalHandshake - ppClie"...
0x18009bd46  lea     rdx, byte_180113A57
0x18009bd4d  mov     [rbp+arg_30], rax
0x18009bd51  xor     r9d, r9d
0x18009bd54  lea     rax, [rbp+arg_30]
0x18009bd58  xor     r8d, r8d
0x18009bd5b  mov     rcx, r13
0x18009bd5e  mov     [rsp+48h+var_28], rax
0x18009bd63  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x18009bd68  mov     eax, cs:dword_180128170
0x18009bd6e  cmp     eax, 2
0x18009bd71  jbe     short loc_18009BDA8
0x18009bd73  lea     rax, aCdefpolicyDomi_0; "CDefPolicy::DoMinimalHandshake FAILED"
0x18009bd7a  mov     dword ptr [rbp+arg_30], ebx
0x18009bd7d  mov     [rbp+var_18], rax
0x18009bd81  lea     rdx, word_18011397A
0x18009bd88  lea     rax, [rbp+arg_30]
0x18009bd8c  xor     r9d, r9d
0x18009bd8f  mov     [rsp+48h+var_20], rax
0x18009bd94  xor     r8d, r8d
0x18009bd97  lea     rax, [rbp+var_18]
0x18009bd9b  mov     rcx, r13
0x18009bd9e  mov     [rsp+48h+var_28], rax
0x18009bda3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18009bda8  mov     r12d, 80004005h
0x18009bdae  jmp     short loc_18009BDCA
0x18009bdb0  mov     dword ptr [r15], 40h ; '@'
0x18009bdb7  mov     rcx, [rsi]
0x18009bdba  mov     dword ptr [rcx+10h], 2Ah ; '*'
0x18009bdc1  mov     dword ptr [r14], 2
0x18009bdc8  xor     ebx, ebx
0x18009bdca  mov     ecx, ebx; unsigned int
0x18009bdcc  call    ?LsStatusToClientError@@YAKK@Z; LsStatusToClientError(ulong)
0x18009bdd1  mov     rcx, [rbp+arg_38]
0x18009bdd8  mov     [rcx], eax
0x18009bdda  mov     eax, r12d
0x18009bddd  add     rsp, 48h
0x18009bde1  pop     r15
0x18009bde3  pop     r14
0x18009bde5  pop     r13
0x18009bde7  pop     r12
0x18009bde9  pop     rdi
0x18009bdea  pop     rsi
0x18009bdeb  pop     rbx
0x18009bdec  pop     rbp
0x18009bded  retn
```
