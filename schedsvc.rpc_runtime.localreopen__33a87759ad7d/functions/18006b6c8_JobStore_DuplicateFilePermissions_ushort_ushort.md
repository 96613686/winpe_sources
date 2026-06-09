# JobStore::DuplicateFilePermissions(ushort *,ushort *)

- ea: `0x18006b6c8`
- end: `0x18006b938`
- name: `?DuplicateFilePermissions@JobStore@@QEBAJPEAG0@Z`
- size: `624`
- prototype: `__int64 __fastcall(JobStore *this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006b204`
- `0x18006b2f0`

## callees

- `0x180001520`
- `0x180001694`
- `0x180040c14`
- `0x180052584`
- `0x18006b6c8`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006b82d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006b82d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b918`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006b918`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006b7ab`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006b7ab`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006b8b4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006b8b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall JobStore::DuplicateFilePermissions(JobStore *this, unsigned __int16 *a2, unsigned __int16 *a3)
{
  __int64 v5; // rcx
  unsigned int LastHrError; // ebx
  int v7; // ecx
  int v8; // r8d
  int v9; // r9d
  int v10; // edx
  tsched *v11; // rcx
  int v12; // ecx
  int v13; // r8d
  int v14; // r9d
  HANDLE FileW; // rax
  int v16; // edx
  tsched *v17; // rcx
  void *v18; // r14
  __int64 v19; // rcx
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  int v23; // edx
  tsched *v24; // rcx
  __int64 v25; // rcx
  int v26; // ecx
  int v27; // r8d
  int v28; // r9d
  PACL pDacl; // [rsp+40h] [rbp-9h] BYREF
  PSID psidGroup; // [rsp+48h] [rbp-1h] BYREF
  PSID ppsidOwner; // [rsp+50h] [rbp+7h] BYREF
  unsigned __int16 *v33; // [rsp+58h] [rbp+Fh] BYREF
  unsigned __int16 *v34; // [rsp+60h] [rbp+17h] BYREF
  PSECURITY_DESCRIPTOR ppSecurityDescriptor[2]; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v36; // [rsp+78h] [rbp+2Fh]
  __int64 v37; // [rsp+88h] [rbp+3Fh]
  int v38; // [rsp+C8h] [rbp+7Fh] BYREF

  v37 = 0;
  ppsidOwner = 0;
  *(_OWORD *)ppSecurityDescriptor = 0;
  psidGroup = 0;
  v36 = 0;
  pDacl = 0;
  if ( JobStore::RealPathIsValid(this, a3) )
  {
    if ( GetNamedSecurityInfoW(a2, SE_FILE_OBJECT, 7u, &ppsidOwner, &psidGroup, &pDacl, 0, ppSecurityDescriptor) )
    {
      LastHrError = tsched::GetLastHrError(v11, v10);
      if ( (unsigned int)dword_1800BC358 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800BC358, 0x400000000001LL) )
      {
        v34 = a3;
        v33 = a2;
        v38 = LastHrError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)byte_1800AD769,
          v13,
          v14,
          (__int64)&v38,
          (__int64)&v33,
          (__int64)&v34);
      }
    }
    else
    {
      FileW = CreateFileW(a3, 0xE0000u, 0, 0, 3u, 0x2200000u, 0);
      v18 = FileW;
      if ( FileW == (HANDLE)-1LL )
      {
        LastHrError = tsched::GetLastHrError(v17, v16);
        if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v19, 0x400000000001LL) )
        {
          v34 = a3;
          v33 = a2;
          v38 = LastHrError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v20,
            (unsigned int)word_1800AD9AA,
            v21,
            v22,
            (__int64)&v38,
            (__int64)&v33,
            (__int64)&v34);
        }
      }
      else
      {
        LastHrError = 0;
        if ( SetSecurityInfo(FileW, SE_FILE_OBJECT, 7u, ppsidOwner, psidGroup, pDacl, 0) )
        {
          LastHrError = tsched::GetLastHrError(v24, v23);
          if ( (unsigned int)dword_1800BC358 > 4 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v25, 0x400000000001LL) )
            {
              v34 = a3;
              v33 = a2;
              v38 = LastHrError;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v26,
                (unsigned int)word_1800AD6C2,
                v27,
                v28,
                (__int64)&v38,
                (__int64)&v33,
                (__int64)&v34);
            }
          }
        }
        CloseHandle(v18);
      }
    }
  }
  else
  {
    LastHrError = -2147024891;
    if ( (unsigned int)dword_1800BC358 > 4 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000001LL) )
    {
      v33 = a3;
      v34 = a2;
      v38 = -2147024891;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&unk_1800ADA28,
        v8,
        v9,
        (__int64)&v38,
        (__int64)&v34,
        (__int64)&v33);
    }
  }
  return LastHrError;
}

```

## disassembly

```asm
0x18006b6c8  mov     [rsp-8+arg_0], rbx
0x18006b6cd  mov     [rsp-8+arg_8], rsi
0x18006b6d2  push    rbp
0x18006b6d3  push    rdi
0x18006b6d4  push    r14
0x18006b6d6  lea     rbp, [rsp-47h]
0x18006b6db  sub     rsp, 90h
0x18006b6e2  xor     eax, eax
0x18006b6e4  xorps   xmm0, xmm0
0x18006b6e7  mov     rsi, rdx
0x18006b6ea  mov     [rbp+57h+var_18], rax
0x18006b6ee  mov     rdx, r8; unsigned __int16 *
0x18006b6f1  mov     [rbp+57h+ppsidOwner], rax
0x18006b6f5  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18006b6f9  mov     [rbp+57h+psidGroup], rax
0x18006b6fd  mov     rdi, r8
0x18006b700  movups  [rbp+57h+var_28], xmm0
0x18006b704  mov     [rbp+57h+pDacl], rax
0x18006b708  call    ?RealPathIsValid@JobStore@@AEBA_NPEBG@Z; JobStore::RealPathIsValid(ushort const *)
0x18006b70d  test    al, al
0x18006b70f  jnz     short loc_18006B777
0x18006b711  mov     eax, cs:dword_1800BC358
0x18006b717  mov     ebx, 80070005h
0x18006b71c  cmp     eax, 4
0x18006b71f  jbe     loc_18006B91E
0x18006b725  mov     rdx, 400000000001h
0x18006b72f  call    _tlgKeywordOn
0x18006b734  test    al, al
0x18006b736  jz      loc_18006B91E
0x18006b73c  lea     rax, [rbp+57h+var_48]
0x18006b740  mov     [rbp+57h+var_48], rdi
0x18006b744  mov     [rsp+0A0h+ppSacl], rax
0x18006b749  lea     rdx, unk_1800ADA28
0x18006b750  lea     rax, [rbp+57h+var_40]
0x18006b754  mov     [rbp+57h+var_40], rsi
0x18006b758  mov     [rbp+57h+arg_18], 80070005h
0x18006b75f  mov     [rsp+0A0h+ppDacl], rax
0x18006b764  lea     rax, [rbp+57h+arg_18]
0x18006b768  mov     [rsp+0A0h+ppsidGroup], rax
0x18006b76d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006b772  jmp     loc_18006B91E
0x18006b777  lea     rax, [rbp+57h+var_38]
0x18006b77b  mov     edx, 1; ObjectType
0x18006b780  mov     [rsp+0A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18006b785  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18006b789  lea     rax, [rbp+57h+pDacl]
0x18006b78d  mov     [rsp+0A0h+ppSacl], 0; ppSacl
0x18006b796  mov     [rsp+0A0h+ppDacl], rax; ppDacl
0x18006b79b  mov     rcx, rsi; pObjectName
0x18006b79e  lea     rax, [rbp+57h+psidGroup]
0x18006b7a2  lea     r8d, [rdx+6]; SecurityInfo
0x18006b7a6  mov     [rsp+0A0h+ppsidGroup], rax; ppsidGroup
0x18006b7ab  call    cs:__imp_GetNamedSecurityInfoW
0x18006b7b1  test    eax, eax
0x18006b7b3  jz      short loc_18006B806
0x18006b7b5  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006b7ba  mov     ecx, cs:dword_1800BC358
0x18006b7c0  mov     ebx, eax
0x18006b7c2  cmp     ecx, 4
0x18006b7c5  jbe     loc_18006B91E
0x18006b7cb  mov     rdx, 400000000001h
0x18006b7d5  call    _tlgKeywordOn
0x18006b7da  test    al, al
0x18006b7dc  jz      loc_18006B91E
0x18006b7e2  lea     rax, [rbp+57h+var_40]
0x18006b7e6  mov     [rbp+57h+var_40], rdi
0x18006b7ea  mov     [rsp+0A0h+ppSacl], rax
0x18006b7ef  lea     rdx, byte_1800AD769
0x18006b7f6  lea     rax, [rbp+57h+var_48]
0x18006b7fa  mov     [rbp+57h+var_48], rsi
0x18006b7fe  mov     [rbp+57h+arg_18], ebx
0x18006b801  jmp     loc_18006B75F
0x18006b806  mov     [rsp+0A0h+ppSacl], 0; hTemplateFile
0x18006b80f  xor     r9d, r9d; lpSecurityAttributes
0x18006b812  mov     dword ptr [rsp+0A0h+ppDacl], 2200000h; dwFlagsAndAttributes
0x18006b81a  xor     r8d, r8d; dwShareMode
0x18006b81d  mov     edx, 0E0000h; dwDesiredAccess
0x18006b822  mov     dword ptr [rsp+0A0h+ppsidGroup], 3; dwCreationDisposition
0x18006b82a  mov     rcx, rdi; lpFileName
0x18006b82d  call    cs:__imp_CreateFileW
0x18006b833  mov     r14, rax
0x18006b836  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006b83a  jnz     short loc_18006B88D
0x18006b83c  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006b841  mov     ebx, eax
0x18006b843  mov     eax, cs:dword_1800BC358
0x18006b849  cmp     eax, 4
0x18006b84c  jbe     loc_18006B91E
0x18006b852  mov     rdx, 400000000001h
0x18006b85c  call    _tlgKeywordOn
0x18006b861  test    al, al
0x18006b863  jz      loc_18006B91E
0x18006b869  lea     rax, [rbp+57h+var_40]
0x18006b86d  mov     [rbp+57h+var_40], rdi
0x18006b871  mov     [rsp+0A0h+ppSacl], rax
0x18006b876  lea     rdx, word_1800AD9AA
0x18006b87d  lea     rax, [rbp+57h+var_48]
0x18006b881  mov     [rbp+57h+var_48], rsi
0x18006b885  mov     [rbp+57h+arg_18], ebx
0x18006b888  jmp     loc_18006B75F
0x18006b88d  mov     rax, [rbp+57h+pDacl]
0x18006b891  xor     ebx, ebx
0x18006b893  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x18006b897  mov     rcx, r14; handle
0x18006b89a  mov     [rsp+0A0h+ppSacl], rbx; pSacl
0x18006b89f  mov     [rsp+0A0h+ppDacl], rax; pDacl
0x18006b8a4  mov     rax, [rbp+57h+psidGroup]
0x18006b8a8  lea     edx, [rbx+1]; ObjectType
0x18006b8ab  lea     r8d, [rbx+7]; SecurityInfo
0x18006b8af  mov     [rsp+0A0h+ppsidGroup], rax; psidGroup
0x18006b8b4  call    cs:__imp_SetSecurityInfo
0x18006b8ba  test    eax, eax
0x18006b8bc  jz      short loc_18006B915
0x18006b8be  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006b8c3  mov     ebx, eax
0x18006b8c5  mov     eax, cs:dword_1800BC358
0x18006b8cb  cmp     eax, 4
0x18006b8ce  jbe     short loc_18006B915
0x18006b8d0  mov     rdx, 400000000001h
0x18006b8da  call    _tlgKeywordOn
0x18006b8df  test    al, al
0x18006b8e1  jz      short loc_18006B915
0x18006b8e3  lea     rax, [rbp+57h+var_40]
0x18006b8e7  mov     [rbp+57h+var_40], rdi
0x18006b8eb  mov     [rsp+0A0h+ppSacl], rax
0x18006b8f0  lea     rdx, word_1800AD6C2
0x18006b8f7  lea     rax, [rbp+57h+var_48]
0x18006b8fb  mov     [rbp+57h+var_48], rsi
0x18006b8ff  mov     [rsp+0A0h+ppDacl], rax
0x18006b904  lea     rax, [rbp+57h+arg_18]
0x18006b908  mov     [rsp+0A0h+ppsidGroup], rax
0x18006b90d  mov     [rbp+57h+arg_18], ebx
0x18006b910  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006b915  mov     rcx, r14; hObject
0x18006b918  call    cs:__imp_CloseHandle
0x18006b91e  lea     r11, [rsp+0A0h+var_10]
0x18006b926  mov     eax, ebx
0x18006b928  mov     rbx, [r11+20h]
0x18006b92c  mov     rsi, [r11+28h]
0x18006b930  mov     rsp, r11
0x18006b933  pop     r14
0x18006b935  pop     rdi
0x18006b936  pop     rbp
0x18006b937  retn
```
