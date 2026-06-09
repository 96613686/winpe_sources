# JobStore::DuplicateFilePermissions(ushort *,ushort *)

- ea: `0x18006ecac`
- end: `0x18006ef35`
- name: `?DuplicateFilePermissions@JobStore@@QEBAJPEAG0@Z`
- size: `649`
- prototype: `int(JobStore *__hidden this, unsigned __int16 *, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18006e72c`
- `0x18006e824`

## callees

- `0x180001544`
- `0x1800016c0`
- `0x180043550`
- `0x180054c80`
- `0x18006ecac`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ee17`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18006ee17`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ef0e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006ef0e`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006ed8f`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18006ed8f`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006eea4`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18006eea4`

## pseudocode

```c
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
      if ( (unsigned int)dword_1800C0358 > 4
        && (unsigned __int8)tlgKeywordOn((unsigned int)dword_1800C0358, 0x400000000001LL) )
      {
        v34 = a3;
        v33 = a2;
        v38 = LastHrError;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)byte_1800B17B1,
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
        if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)tlgKeywordOn(v19, 0x400000000001LL) )
        {
          v34 = a3;
          v33 = a2;
          v38 = LastHrError;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
            v20,
            (unsigned int)word_1800B19F2,
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
          if ( (unsigned int)dword_1800C0358 > 4 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v25, 0x400000000001LL) )
            {
              v34 = a3;
              v33 = a2;
              v38 = LastHrError;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                v26,
                (unsigned int)word_1800B170A,
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
    if ( (unsigned int)dword_1800C0358 > 4 && (unsigned __int8)tlgKeywordOn(v5, 0x400000000001LL) )
    {
      v33 = a3;
      v34 = a2;
      v38 = -2147024891;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
        v7,
        (unsigned int)&unk_1800B1A70,
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
0x18006ecac  mov     [rsp-8+arg_0], rbx
0x18006ecb1  mov     [rsp-8+arg_8], rsi
0x18006ecb6  push    rbp
0x18006ecb7  push    rdi
0x18006ecb8  push    r14
0x18006ecba  lea     rbp, [rsp-47h]
0x18006ecbf  sub     rsp, 90h
0x18006ecc6  xor     eax, eax
0x18006ecc8  xorps   xmm0, xmm0
0x18006eccb  mov     rsi, rdx
0x18006ecce  mov     [rbp+57h+var_18], rax
0x18006ecd2  mov     rdx, r8; unsigned __int16 *
0x18006ecd5  mov     [rbp+57h+ppsidOwner], rax
0x18006ecd9  movups  xmmword ptr [rbp+57h+var_38], xmm0
0x18006ecdd  mov     [rbp+57h+psidGroup], rax
0x18006ece1  mov     rdi, r8
0x18006ece4  movups  [rbp+57h+var_28], xmm0
0x18006ece8  mov     [rbp+57h+pDacl], rax
0x18006ecec  call    ?RealPathIsValid@JobStore@@AEBA_NPEBG@Z; JobStore::RealPathIsValid(ushort const *)
0x18006ecf1  test    al, al
0x18006ecf3  jnz     short loc_18006ED5B
0x18006ecf5  mov     eax, cs:dword_1800C0358
0x18006ecfb  mov     ebx, 80070005h
0x18006ed00  cmp     eax, 4
0x18006ed03  jbe     loc_18006EF1A
0x18006ed09  mov     rdx, 400000000001h
0x18006ed13  call    _tlgKeywordOn
0x18006ed18  test    al, al
0x18006ed1a  jz      loc_18006EF1A
0x18006ed20  lea     rax, [rbp+57h+var_48]
0x18006ed24  mov     [rbp+57h+var_48], rdi
0x18006ed28  mov     [rsp+0A0h+ppSacl], rax
0x18006ed2d  lea     rdx, unk_1800B1A70
0x18006ed34  lea     rax, [rbp+57h+var_40]
0x18006ed38  mov     [rbp+57h+var_40], rsi
0x18006ed3c  mov     [rbp+57h+arg_18], 80070005h
0x18006ed43  mov     [rsp+0A0h+ppDacl], rax
0x18006ed48  lea     rax, [rbp+57h+arg_18]
0x18006ed4c  mov     [rsp+0A0h+ppsidGroup], rax
0x18006ed51  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006ed56  jmp     loc_18006EF1A
0x18006ed5b  lea     rax, [rbp+57h+var_38]
0x18006ed5f  mov     edx, 1; ObjectType
0x18006ed64  mov     [rsp+0A0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18006ed69  lea     r9, [rbp+57h+ppsidOwner]; ppsidOwner
0x18006ed6d  lea     rax, [rbp+57h+pDacl]
0x18006ed71  mov     [rsp+0A0h+ppSacl], 0; ppSacl
0x18006ed7a  mov     [rsp+0A0h+ppDacl], rax; ppDacl
0x18006ed7f  mov     rcx, rsi; pObjectName
0x18006ed82  lea     rax, [rbp+57h+psidGroup]
0x18006ed86  lea     r8d, [rdx+6]; SecurityInfo
0x18006ed8a  mov     [rsp+0A0h+ppsidGroup], rax; ppsidGroup
0x18006ed8f  call    cs:__imp_GetNamedSecurityInfoW
0x18006ed96  nop     dword ptr [rax+rax+00h]
0x18006ed9b  test    eax, eax
0x18006ed9d  jz      short loc_18006EDF0
0x18006ed9f  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006eda4  mov     ecx, cs:dword_1800C0358
0x18006edaa  mov     ebx, eax
0x18006edac  cmp     ecx, 4
0x18006edaf  jbe     loc_18006EF1A
0x18006edb5  mov     rdx, 400000000001h
0x18006edbf  call    _tlgKeywordOn
0x18006edc4  test    al, al
0x18006edc6  jz      loc_18006EF1A
0x18006edcc  lea     rax, [rbp+57h+var_40]
0x18006edd0  mov     [rbp+57h+var_40], rdi
0x18006edd4  mov     [rsp+0A0h+ppSacl], rax
0x18006edd9  lea     rdx, byte_1800B17B1
0x18006ede0  lea     rax, [rbp+57h+var_48]
0x18006ede4  mov     [rbp+57h+var_48], rsi
0x18006ede8  mov     [rbp+57h+arg_18], ebx
0x18006edeb  jmp     loc_18006ED43
0x18006edf0  mov     [rsp+0A0h+ppSacl], 0; hTemplateFile
0x18006edf9  xor     r9d, r9d; lpSecurityAttributes
0x18006edfc  mov     dword ptr [rsp+0A0h+ppDacl], 2200000h; dwFlagsAndAttributes
0x18006ee04  xor     r8d, r8d; dwShareMode
0x18006ee07  mov     edx, 0E0000h; dwDesiredAccess
0x18006ee0c  mov     dword ptr [rsp+0A0h+ppsidGroup], 3; dwCreationDisposition
0x18006ee14  mov     rcx, rdi; lpFileName
0x18006ee17  call    cs:__imp_CreateFileW
0x18006ee1e  nop     dword ptr [rax+rax+00h]
0x18006ee23  mov     r14, rax
0x18006ee26  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18006ee2a  jnz     short loc_18006EE7D
0x18006ee2c  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006ee31  mov     ebx, eax
0x18006ee33  mov     eax, cs:dword_1800C0358
0x18006ee39  cmp     eax, 4
0x18006ee3c  jbe     loc_18006EF1A
0x18006ee42  mov     rdx, 400000000001h
0x18006ee4c  call    _tlgKeywordOn
0x18006ee51  test    al, al
0x18006ee53  jz      loc_18006EF1A
0x18006ee59  lea     rax, [rbp+57h+var_40]
0x18006ee5d  mov     [rbp+57h+var_40], rdi
0x18006ee61  mov     [rsp+0A0h+ppSacl], rax
0x18006ee66  lea     rdx, word_1800B19F2
0x18006ee6d  lea     rax, [rbp+57h+var_48]
0x18006ee71  mov     [rbp+57h+var_48], rsi
0x18006ee75  mov     [rbp+57h+arg_18], ebx
0x18006ee78  jmp     loc_18006ED43
0x18006ee7d  mov     rax, [rbp+57h+pDacl]
0x18006ee81  xor     ebx, ebx
0x18006ee83  mov     r9, [rbp+57h+ppsidOwner]; psidOwner
0x18006ee87  mov     rcx, r14; handle
0x18006ee8a  mov     [rsp+0A0h+ppSacl], rbx; pSacl
0x18006ee8f  mov     [rsp+0A0h+ppDacl], rax; pDacl
0x18006ee94  mov     rax, [rbp+57h+psidGroup]
0x18006ee98  lea     edx, [rbx+1]; ObjectType
0x18006ee9b  lea     r8d, [rbx+7]; SecurityInfo
0x18006ee9f  mov     [rsp+0A0h+ppsidGroup], rax; psidGroup
0x18006eea4  call    cs:__imp_SetSecurityInfo
0x18006eeab  nop     dword ptr [rax+rax+00h]
0x18006eeb0  test    eax, eax
0x18006eeb2  jz      short loc_18006EF0B
0x18006eeb4  call    ?GetLastHrError@tsched@@YAJJ@Z; tsched::GetLastHrError(long)
0x18006eeb9  mov     ebx, eax
0x18006eebb  mov     eax, cs:dword_1800C0358
0x18006eec1  cmp     eax, 4
0x18006eec4  jbe     short loc_18006EF0B
0x18006eec6  mov     rdx, 400000000001h
0x18006eed0  call    _tlgKeywordOn
0x18006eed5  test    al, al
0x18006eed7  jz      short loc_18006EF0B
0x18006eed9  lea     rax, [rbp+57h+var_40]
0x18006eedd  mov     [rbp+57h+var_40], rdi
0x18006eee1  mov     [rsp+0A0h+ppSacl], rax
0x18006eee6  lea     rdx, word_1800B170A
0x18006eeed  lea     rax, [rbp+57h+var_48]
0x18006eef1  mov     [rbp+57h+var_48], rsi
0x18006eef5  mov     [rsp+0A0h+ppDacl], rax
0x18006eefa  lea     rax, [rbp+57h+arg_18]
0x18006eefe  mov     [rsp+0A0h+ppsidGroup], rax
0x18006ef03  mov     [rbp+57h+arg_18], ebx
0x18006ef06  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18006ef0b  mov     rcx, r14; hObject
0x18006ef0e  call    cs:__imp_CloseHandle
0x18006ef15  nop     dword ptr [rax+rax+00h]
0x18006ef1a  lea     r11, [rsp+0A0h+var_10]
0x18006ef22  mov     eax, ebx
0x18006ef24  mov     rbx, [r11+20h]
0x18006ef28  mov     rsi, [r11+28h]
0x18006ef2c  mov     rsp, r11
0x18006ef2f  pop     r14
0x18006ef31  pop     rdi
0x18006ef32  pop     rbp
0x18006ef33  retn
```
