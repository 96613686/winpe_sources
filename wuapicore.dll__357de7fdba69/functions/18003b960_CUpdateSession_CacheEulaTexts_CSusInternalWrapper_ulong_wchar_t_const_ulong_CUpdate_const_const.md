# CUpdateSession::CacheEulaTexts(CSusInternalWrapper *,ulong,wchar_t const *,ulong,CUpdate const * const *)

- ea: `0x18003b960`
- end: `0x18003bbe2`
- name: `?CacheEulaTexts@CUpdateSession@@QEAAJPEAVCSusInternalWrapper@@KPEB_WKPEBQEBVCUpdate@@@Z`
- size: `642`
- prototype: `__int64 __fastcall(CUpdateSession *__hidden this, struct CSusInternalWrapper *, unsigned int, const wchar_t *, unsigned int, const struct CUpdate *const *)`
- caller_count: `3`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800320b0`
- `0x180035880`
- `0x180057148`

## callees

- `0x180006ac4`
- `0x18003b960`
- `0x18003ce5c`
- `0x18003d034`
- `0x180045420`
- `0x180081a38`
- `0x1800826a0`
- `0x180096bb0`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bb57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbd9`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bb57`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18003bbd9`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b9ff`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18003b9ff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb33`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003bb33`
- `OLEAUT32!__imp_SysFreeString` at `0x18003baca`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bb19`
- `OLEAUT32!__imp_SysFreeString` at `0x18003baca`
- `OLEAUT32!__imp_SysFreeString` at `0x18003bb19`

## string_xrefs

- `0x18003b9d2`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003bb69`: `C:\__w\1\s\src\Client\comapi\Session.cpp`
- `0x18003bbbe`: `C:\__w\1\s\src\Client\comapi\Session.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CUpdateSession::CacheEulaTexts(
        CUpdateSession *this,
        struct CSusInternalWrapper *a2,
        unsigned int a3,
        const wchar_t *a4,
        unsigned int a5,
        const struct CUpdate *const *a6)
{
  const struct CUpdate *const *v7; // r13
  __int64 v8; // r14
  int v10; // r15d
  int v11; // eax
  unsigned int ValuePointer; // edi
  void *v13; // rbx
  char *v14; // rsi
  const struct CUpdate *v15; // rcx
  wchar_t **v16; // r13
  int EulaText; // edi
  void *lpMem; // [rsp+28h] [rbp-71h] BYREF
  wchar_t **v20; // [rsp+30h] [rbp-69h] BYREF
  const struct CUpdate *const *v21; // [rsp+38h] [rbp-61h]
  struct _GUID *v22; // [rsp+40h] [rbp-59h]
  CSusInternalWrapper *v23; // [rsp+48h] [rbp-51h]
  __int128 v24; // [rsp+50h] [rbp-49h] BYREF
  unsigned int v25; // [rsp+60h] [rbp-39h]
  int v26; // [rsp+64h] [rbp-35h]
  void *v27; // [rsp+68h] [rbp-31h]
  char *v28; // [rsp+70h] [rbp-29h]
  __int64 v29; // [rsp+78h] [rbp-21h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-19h]
  int v31; // [rsp+88h] [rbp-11h]
  int v32; // [rsp+8Ch] [rbp-Dh]
  LPVOID pv; // [rsp+90h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v23 = a2;
  v7 = a6;
  v21 = a6;
  LODWORD(v8) = a5;
  if ( !a5 )
    return 0;
  v20 = 0;
  v10 = 0;
  lpMem = 0;
  v11 = DuplicateString<wchar_t const *,wchar_t *>(a4, &lpMem);
  ValuePointer = v11;
  if ( v11 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
      (const char *)(unsigned int)v11,
      a3);
    v13 = lpMem;
    goto LABEL_31;
  }
  if ( this )
  {
    v14 = (char *)this + 56;
    if ( this != (CUpdateSession *)-56LL )
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  }
  else
  {
    v14 = 0;
  }
  v28 = v14;
  v13 = lpMem;
  while ( 1 )
  {
    do
    {
      if ( !(_DWORD)v8 )
      {
        if ( v14 )
          LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
        if ( v10 < 0 )
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1ED,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
            (const char *)(unsigned int)v10,
            a3);
        ValuePointer = v10;
        goto LABEL_31;
      }
      v8 = (unsigned int)(v8 - 1);
      v15 = v7[v8];
    }
    while ( !*((_DWORD *)v15 + 105) );
    v22 = (struct _GUID *)((char *)v15 + 656);
    v24 = *((_OWORD *)v15 + 41);
    v25 = a3;
    v26 = 0;
    v27 = v13;
    v29 = 0;
    bstrString = 0;
    v31 = -2145120257;
    v32 = 0;
    ValuePointer = CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::get_ValuePointer(
                     (char *)this + 136,
                     &v24,
                     &v20);
    if ( (int)(ValuePointer + 0x80000000) >= 0 && ValuePointer != -2145124345 )
      break;
    v16 = (wchar_t **)&v29;
    if ( ValuePointer != -2145124345 )
      v16 = v20;
    v20 = v16;
    pv = 0;
    EulaText = CSusInternalWrapper::GetEulaText(v23, v22, a3, (wchar_t **)&pv);
    if ( EulaText >= 0 )
    {
      SysFreeString(v16[1]);
      v16[1] = 0;
      EulaText = SusSysAllocString((const wchar_t *)pv, v16 + 1);
    }
    *((_DWORD *)v16 + 4) = EulaText;
    if ( EulaText < 0 )
      goto LABEL_21;
    if ( &v29 != (__int64 *)v16 )
      goto LABEL_22;
    EulaText = CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::Add(
                 (char *)this + 136,
                 &v24,
                 &v29);
    if ( EulaText < 0 )
    {
      SysFreeString(bstrString);
      bstrString = 0;
LABEL_21:
      v10 = EulaText;
      goto LABEL_22;
    }
    v13 = 0;
    lpMem = 0;
LABEL_22:
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    v7 = v21;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C1,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\comapi\\Session.cpp",
    (const char *)ValuePointer,
    a3);
  if ( v14 )
    LeaveCriticalSection((LPCRITICAL_SECTION)(v14 + 8));
LABEL_31:
  if ( v13 )
    SusFree(v13);
  return ValuePointer;
}

```

## disassembly

```asm
0x18003b960  push    rbp
0x18003b962  push    rbx
0x18003b963  push    rsi
0x18003b964  push    rdi
0x18003b965  push    r12
0x18003b967  push    r13
0x18003b969  push    r14
0x18003b96b  push    r15
0x18003b96d  lea     rbp, [rsp-0Fh]
0x18003b972  sub     rsp, 0A8h
0x18003b979  mov     rax, cs:__security_cookie
0x18003b980  xor     rax, rsp
0x18003b983  mov     [rbp+47h+var_48], rax
0x18003b987  mov     [rbp+47h+var_C0], r8d
0x18003b98b  mov     [rbp+47h+var_98], rdx
0x18003b98f  mov     r12, rcx
0x18003b992  mov     r13, [rbp+47h+arg_28]
0x18003b996  mov     [rbp+47h+var_A8], r13
0x18003b99a  mov     r14d, [rbp+47h+arg_20]
0x18003b99e  test    r14d, r14d
0x18003b9a1  jnz     short loc_18003B9AA
0x18003b9a3  xor     eax, eax
0x18003b9a5  jmp     loc_18003BB8C
0x18003b9aa  mov     [rbp+47h+var_B0], 0
0x18003b9b2  xor     r15d, r15d
0x18003b9b5  mov     [rbp+47h+lpMem], r15
0x18003b9b9  lea     rdx, [rbp+47h+lpMem]
0x18003b9bd  mov     rcx, r9
0x18003b9c0  call    ??$DuplicateString@PEB_WPEA_W@@YAJPEB_WPEAPEA_W@Z; DuplicateString<wchar_t const *,wchar_t *>(wchar_t const *,wchar_t * *)
0x18003b9c5  mov     edi, eax
0x18003b9c7  test    eax, eax
0x18003b9c9  jns     short loc_18003B9EC
0x18003b9cb  mov     rcx, [rbp+4Fh]; this
0x18003b9cf  mov     r9d, eax; char *
0x18003b9d2  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003b9d9  mov     edx, 1AAh; void *
0x18003b9de  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003b9e3  mov     rbx, [rbp+47h+lpMem]
0x18003b9e7  jmp     loc_18003BB7D
0x18003b9ec  test    r12, r12
0x18003b9ef  jz      short loc_18003BA07
0x18003b9f1  lea     rsi, [r12+38h]
0x18003b9f6  test    rsi, rsi
0x18003b9f9  jz      short loc_18003BA09
0x18003b9fb  lea     rcx, [rsi+8]; lpCriticalSection
0x18003b9ff  call    cs:__imp_EnterCriticalSection
0x18003ba05  jmp     short loc_18003BA09
0x18003ba07  xor     esi, esi
0x18003ba09  mov     [rbp+47h+var_70], rsi
0x18003ba0d  mov     rbx, [rbp+47h+lpMem]
0x18003ba11  jmp     loc_18003BB45
0x18003ba16  dec     r14d
0x18003ba19  mov     rcx, [r13+r14*8+0]
0x18003ba1e  cmp     dword ptr [rcx+1A4h], 0
0x18003ba25  jz      loc_18003BB45
0x18003ba2b  lea     rax, [rcx+290h]
0x18003ba32  mov     [rbp+47h+var_A0], rax
0x18003ba36  movups  xmm0, xmmword ptr [rax]
0x18003ba39  movdqu  [rbp+47h+var_90], xmm0
0x18003ba3e  mov     eax, [rbp+47h+var_C0]
0x18003ba41  mov     [rbp+47h+var_80], eax
0x18003ba44  xor     eax, eax
0x18003ba46  mov     [rbp+47h+var_7C], eax
0x18003ba49  mov     [rbp+47h+var_78], rbx
0x18003ba4d  mov     [rbp+47h+var_68], rax
0x18003ba51  mov     [rbp+47h+bstrString], rax
0x18003ba55  mov     [rbp+47h+var_58], 80240FFFh
0x18003ba5c  mov     [rbp+47h+var_54], eax
0x18003ba5f  lea     rcx, [r12+88h]
0x18003ba67  lea     r8, [rbp+47h+var_B0]
0x18003ba6b  lea     rdx, [rbp+47h+var_90]
0x18003ba6f  call    ?get_ValuePointer@?$CSusMap@UtagSEulaInfoKey@CUpdateSession@@UtagSEulaInfo@2@VCSusEulaInfoKeyListOps@2@VCSusArrayListItemOpSEulaInfo@2@@@QEAAJAEBUtagSEulaInfoKey@CUpdateSession@@PEAPEAUtagSEulaInfo@3@@Z; CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::get_ValuePointer(CUpdateSession::tagSEulaInfoKey const &,CUpdateSession::tagSEulaInfo * *)
0x18003ba74  mov     edi, eax
0x18003ba76  mov     ecx, 80000000h
0x18003ba7b  add     eax, ecx
0x18003ba7d  test    ecx, eax
0x18003ba7f  jnz     short loc_18003BA8D
0x18003ba81  cmp     edi, 80240007h
0x18003ba87  jnz     loc_18003BBB7
0x18003ba8d  lea     r13, [rbp+47h+var_68]
0x18003ba91  cmp     edi, 80240007h
0x18003ba97  cmovnz  r13, [rbp+47h+var_B0]
0x18003ba9c  mov     [rbp+47h+var_B0], r13
0x18003baa0  mov     [rbp+47h+pv], 0
0x18003baa8  lea     r9, [rbp+47h+pv]; wchar_t **
0x18003baac  mov     r8d, [rbp+47h+var_C0]; unsigned int
0x18003bab0  mov     rdx, [rbp+47h+var_A0]; struct _GUID *
0x18003bab4  mov     rcx, [rbp+47h+var_98]; this
0x18003bab8  call    ?GetEulaText@CSusInternalWrapper@@QEAAJAEBU_GUID@@KPEAPEA_W@Z; CSusInternalWrapper::GetEulaText(_GUID const &,ulong,wchar_t * *)
0x18003babd  mov     edi, eax
0x18003babf  test    eax, eax
0x18003bac1  js      short loc_18003BAE5
0x18003bac3  lea     rdi, [r13+8]
0x18003bac7  mov     rcx, [rdi]; bstrString
0x18003baca  call    cs:__imp_SysFreeString
0x18003bad0  mov     qword ptr [rdi], 0
0x18003bad7  mov     rdx, rdi; wchar_t **
0x18003bada  mov     rcx, [rbp+47h+pv]; wchar_t *
0x18003bade  call    ?SusSysAllocString@@YAJPEB_WPEAPEA_W@Z; SusSysAllocString(wchar_t const *,wchar_t * *)
0x18003bae3  mov     edi, eax
0x18003bae5  mov     [r13+10h], edi
0x18003bae9  test    edi, edi
0x18003baeb  js      short loc_18003BB27
0x18003baed  lea     rax, [rbp+47h+var_68]
0x18003baf1  cmp     rax, r13
0x18003baf4  jnz     short loc_18003BB2A
0x18003baf6  lea     r8, [rbp+47h+var_68]
0x18003bafa  lea     rdx, [rbp+47h+var_90]
0x18003bafe  lea     rcx, [r12+88h]
0x18003bb06  call    ?Add@?$CSusMap@UtagSEulaInfoKey@CUpdateSession@@UtagSEulaInfo@2@VCSusEulaInfoKeyListOps@2@VCSusArrayListItemOpSEulaInfo@2@@@QEAAJAEBUtagSEulaInfoKey@CUpdateSession@@AEBUtagSEulaInfo@3@@Z; CSusMap<CUpdateSession::tagSEulaInfoKey,CUpdateSession::tagSEulaInfo,CUpdateSession::CSusEulaInfoKeyListOps,CUpdateSession::CSusArrayListItemOpSEulaInfo>::Add(CUpdateSession::tagSEulaInfoKey const &,CUpdateSession::tagSEulaInfo const &)
0x18003bb0b  mov     edi, eax
0x18003bb0d  test    eax, eax
0x18003bb0f  jns     loc_18003BBAC
0x18003bb15  mov     rcx, [rbp+47h+bstrString]; bstrString
0x18003bb19  call    cs:__imp_SysFreeString
0x18003bb1f  mov     [rbp+47h+bstrString], 0
0x18003bb27  mov     r15d, edi
0x18003bb2a  mov     rcx, [rbp+47h+pv]; pv
0x18003bb2e  test    rcx, rcx
0x18003bb31  jz      short loc_18003BB41
0x18003bb33  call    cs:__imp_CoTaskMemFree
0x18003bb39  mov     [rbp+47h+pv], 0
0x18003bb41  mov     r13, [rbp+47h+var_A8]
0x18003bb45  test    r14d, r14d
0x18003bb48  jnz     loc_18003BA16
0x18003bb4e  test    rsi, rsi
0x18003bb51  jz      short loc_18003BB5D
0x18003bb53  lea     rcx, [rsi+8]; lpCriticalSection
0x18003bb57  call    cs:__imp_LeaveCriticalSection
0x18003bb5d  test    r15d, r15d
0x18003bb60  jns     short loc_18003BB7A
0x18003bb62  mov     rcx, [rbp+4Fh]; this
0x18003bb66  mov     r9d, r15d; char *
0x18003bb69  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003bb70  mov     edx, 1EDh; void *
0x18003bb75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bb7a  mov     edi, r15d
0x18003bb7d  test    rbx, rbx
0x18003bb80  jz      short loc_18003BB8A
0x18003bb82  mov     rcx, rbx; lpMem
0x18003bb85  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x18003bb8a  mov     eax, edi
0x18003bb8c  mov     rcx, [rbp+47h+var_48]
0x18003bb90  xor     rcx, rsp; StackCookie
0x18003bb93  call    __security_check_cookie
0x18003bb98  add     rsp, 0A8h
0x18003bb9f  pop     r15
0x18003bba1  pop     r14
0x18003bba3  pop     r13
0x18003bba5  pop     r12
0x18003bba7  pop     rdi
0x18003bba8  pop     rsi
0x18003bba9  pop     rbx
0x18003bbaa  pop     rbp
0x18003bbab  retn
0x18003bbac  xor     ebx, ebx
0x18003bbae  mov     [rbp+47h+lpMem], rbx
0x18003bbb2  jmp     loc_18003BB2A
0x18003bbb7  mov     rcx, [rbp+4Fh]; this
0x18003bbbb  mov     r9d, edi; char *
0x18003bbbe  lea     r8, aCW1SSrcClientC_17; "C:\\__w\\1\\s\\src\\Client\\comapi\\Ses"...
0x18003bbc5  mov     edx, 1C1h; void *
0x18003bbca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003bbcf  nop
0x18003bbd0  test    rsi, rsi
0x18003bbd3  jz      short loc_18003BB7D
0x18003bbd5  lea     rcx, [rsi+8]; lpCriticalSection
0x18003bbd9  call    cs:__imp_LeaveCriticalSection
0x18003bbdf  jmp     short loc_18003BB7D
```
