# Windows::Internal::Security::Authentication::TokenBroker::GetVailCallerIdentity(IUnknown *,Windows::Internal::Security::Authentication::TokenBroker::VailCallerIdentity *)

- ea: `0x1800f03a4`
- end: `0x1800f0727`
- name: `?GetVailCallerIdentity@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAUVailCallerIdentity@12345@@Z`
- size: `899`
- prototype: `__int64 __fastcall(Windows::Internal::Security::Authentication::TokenBroker *__hidden this, struct IUnknown *, struct Windows::Internal::Security::Authentication::TokenBroker::VailCallerIdentity *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18008d0b0`

## callees

- `0x180005304`
- `0x18000bd40`
- `0x18000ee40`
- `0x18000f0b0`
- `0x180024000`
- `0x180040b40`
- `0x18007c220`
- `0x1800af930`
- `0x1800f03a4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f04ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0542`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f04ae`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800f0542`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04b8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f04b8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f066b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f06bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0711`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0580`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f066b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f06bf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800f0711`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f06a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0566`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f0651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f06a5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f0516`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800f0516`
- `ntdll!RtlCompareUnicodeString` at `0x1800f05dd`
- `ntdll!RtlCompareUnicodeString` at `0x1800f05dd`

## string_xrefs

- `0x1800f03ca`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f046e`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f04ce`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f04f4`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f0550`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f0691`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f06d8`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f06f6`: `onecore\ds\security\tokenbroker\api\lib\utils.cpp`
- `0x1800f0598`: `WIN://ContainerTokenIntegrityLevel`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall Windows::Internal::Security::Authentication::TokenBroker::GetVailCallerIdentity(
        Windows::Internal::Security::Authentication::TokenBroker *this,
        struct IUnknown *a2,
        struct Windows::Internal::Security::Authentication::TokenBroker::VailCallerIdentity *a3)
{
  __int64 v5; // rdx
  unsigned int v6; // ebx
  void *v7; // r9
  int CallingAppPackageFamilyName; // eax
  char v9; // al
  int ImpersonationTokenForClientOfObject_nothrow; // eax
  DWORD LastError; // eax
  struct IUnknownVtbl *v12; // rbx
  const char *v13; // r9
  unsigned int v14; // edi
  char v16; // r14
  __int64 v17; // rsi
  ULONG (__stdcall *AddRef)(IUnknown *); // rax
  struct IUnknownVtbl *v19; // rcx
  int v20; // r8d
  int v21; // r9d
  __int64 v22; // rdx
  int ReturnLength; // [rsp+20h] [rbp-60h]
  unsigned int ReturnLengtha; // [rsp+20h] [rbp-60h]
  int ReturnLengthb; // [rsp+20h] [rbp-60h]
  HSTRING string; // [rsp+30h] [rbp-50h] BYREF
  struct IUnknownVtbl *lpVtbl; // [rsp+38h] [rbp-48h] BYREF
  UNICODE_STRING String1; // [rsp+40h] [rbp-40h] BYREF
  UNICODE_STRING String2; // [rsp+50h] [rbp-30h] BYREF
  __int128 v30; // [rsp+60h] [rbp-20h]
  struct IUnknownVtbl **v31; // [rsp+70h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  struct IUnknown v33; // [rsp+B0h] [rbp+30h] BYREF
  DWORD TokenInformationLength; // [rsp+C0h] [rbp+40h] BYREF
  HANDLE TokenHandle; // [rsp+C8h] [rbp+48h] BYREF

  if ( !this )
  {
    v5 = 1714;
LABEL_3:
    v6 = -2147024809;
LABEL_4:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v5,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)v6,
      ReturnLength);
    return v6;
  }
  if ( !a2 )
  {
    v5 = 1715;
    goto LABEL_3;
  }
  LOBYTE(v33.lpVtbl) = 0;
  v6 = Windows::Internal::Security::Authentication::TokenBroker::IsCallFromVailContainer(this, &v33, (bool *)a3);
  if ( (v6 & 0x80000000) != 0 )
  {
    v5 = 1718;
    goto LABEL_4;
  }
  if ( !LOBYTE(v33.lpVtbl) )
  {
    v5 = 1720;
    goto LABEL_3;
  }
  string = 0;
  CallingAppPackageFamilyName = Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(
                                  this,
                                  (struct IUnknown *)&string,
                                  0,
                                  v7);
  v6 = CallingAppPackageFamilyName;
  if ( CallingAppPackageFamilyName == -2147009196 )
  {
    v9 = 0;
  }
  else
  {
    if ( CallingAppPackageFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6C8,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)(unsigned int)CallingAppPackageFamilyName,
        ReturnLength);
LABEL_50:
      if ( string )
        WindowsDeleteString(string);
      return v6;
    }
    v9 = 1;
  }
  LOBYTE(a2->lpVtbl) = v9;
  TokenHandle = 0;
  ImpersonationTokenForClientOfObject_nothrow = wil::GetImpersonationTokenForClientOfObject_nothrow(
                                                  this,
                                                  131080,
                                                  &TokenHandle);
  v6 = ImpersonationTokenForClientOfObject_nothrow;
  if ( ImpersonationTokenForClientOfObject_nothrow < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6CD,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)(unsigned int)ImpersonationTokenForClientOfObject_nothrow,
      ReturnLength);
LABEL_17:
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    goto LABEL_50;
  }
  TokenInformationLength = 0;
  if ( !GetTokenInformation(TokenHandle, TokenSecurityAttributes, 0, 0, &TokenInformationLength) )
  {
    LastError = GetLastError();
    if ( LastError != 122 )
    {
      if ( LastError )
      {
        v6 = wil::details::in1diag3::Return_Win32(
               retaddr,
               (void *)0x6DA,
               (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
               (const char *)LastError,
               ReturnLengtha);
        goto LABEL_17;
      }
    }
  }
  if ( !TokenInformationLength )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6DE,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x8000FFFFLL,
      ReturnLengtha);
LABEL_45:
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    if ( string )
      WindowsDeleteString(string);
    return 2147549183LL;
  }
  v12 = (struct IUnknownVtbl *)LocalAlloc(0x40u, 16LL * TokenInformationLength);
  v33.lpVtbl = v12;
  if ( !v12 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6E2,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
      (const char *)0x8007000ELL,
      ReturnLengtha);
    goto LABEL_17;
  }
  if ( GetTokenInformation(TokenHandle, TokenSecurityAttributes, v12, TokenInformationLength, &TokenInformationLength) )
  {
    v16 = 0;
    *(_QWORD *)&String1.Length = 4587588;
    String1.Buffer = L"WIN://ContainerTokenIntegrityLevel";
    v17 = 0;
    if ( !HIDWORD(v12->QueryInterface) )
    {
LABEL_43:
      v22 = 1790;
LABEL_44:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v22,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
        (const char *)0x8000FFFFLL,
        ReturnLengthb);
      LocalFree(v12);
      goto LABEL_45;
    }
    do
    {
      AddRef = v12->AddRef;
      String2 = *(UNICODE_STRING *)((char *)AddRef + 40 * v17);
      v30 = *(_OWORD *)((char *)AddRef + 40 * v17 + 16);
      v31 = (struct IUnknownVtbl **)*((_QWORD *)AddRef + 5 * v17 + 4);
      if ( !RtlCompareUnicodeString(&String1, &String2, 1u) )
      {
        if ( (_WORD)v30 != 2 )
        {
          v22 = 1782;
          goto LABEL_44;
        }
        if ( DWORD2(v30) != 1 )
        {
          v22 = 1783;
          goto LABEL_44;
        }
        v19 = *v31;
        a2[1].lpVtbl = *v31;
        v16 = 1;
      }
      v17 = (unsigned int)(v17 + 1);
    }
    while ( (unsigned int)v17 < HIDWORD(v12->QueryInterface) );
    if ( !v16 )
      goto LABEL_43;
    if ( (unsigned int)dword_180175000 > 4 )
    {
      lpVtbl = a2[1].lpVtbl;
      LODWORD(v33.lpVtbl) = LOBYTE(a2->lpVtbl);
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        (_DWORD)v19,
        (unsigned int)&dword_1801533E4,
        v20,
        v21,
        (__int64)&v33,
        (__int64)&lpVtbl);
    }
    LocalFree(v12);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    if ( string )
      WindowsDeleteString(string);
    return 0;
  }
  else
  {
    v14 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x6E9,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\api\\lib\\utils.cpp",
            v13);
    LocalFree(v12);
    Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator((Windows::Internal::Security::Authentication::Web::AsyncImpersonator *)&TokenHandle);
    if ( string )
      WindowsDeleteString(string);
    return v14;
  }
}

```

## disassembly

```asm
0x1800f03a4  push    rbp
0x1800f03a6  push    rbx
0x1800f03a7  push    rsi
0x1800f03a8  push    rdi
0x1800f03a9  push    r14
0x1800f03ab  mov     rbp, rsp
0x1800f03ae  sub     rsp, 80h
0x1800f03b5  mov     rdi, rdx
0x1800f03b8  mov     rsi, rcx
0x1800f03bb  test    rcx, rcx
0x1800f03be  jnz     short loc_1800F03E2
0x1800f03c0  mov     edx, 6B2h; void *
0x1800f03c5  mov     ebx, 80070057h
0x1800f03ca  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f03d1  mov     r9d, ebx; char *
0x1800f03d4  mov     rcx, [rbp+28h]; this
0x1800f03d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f03dd  jmp     loc_1800F0717
0x1800f03e2  test    rdi, rdi
0x1800f03e5  jnz     short loc_1800F03EE
0x1800f03e7  mov     edx, 6B3h
0x1800f03ec  jmp     short loc_1800F03C5
0x1800f03ee  mov     byte ptr [rbp+arg_0.lpVtbl], 0
0x1800f03f2  lea     rdx, [rbp+arg_0]; struct IUnknown *
0x1800f03f6  call    ?IsCallFromVailContainer@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEA_N@Z; Windows::Internal::Security::Authentication::TokenBroker::IsCallFromVailContainer(IUnknown *,bool *)
0x1800f03fb  mov     ebx, eax
0x1800f03fd  test    eax, eax
0x1800f03ff  jns     short loc_1800F0408
0x1800f0401  mov     edx, 6B6h
0x1800f0406  jmp     short loc_1800F03CA
0x1800f0408  cmp     byte ptr [rbp+arg_0.lpVtbl], 0
0x1800f040c  jnz     short loc_1800F0415
0x1800f040e  mov     edx, 6B8h
0x1800f0413  jmp     short loc_1800F03C5
0x1800f0415  mov     [rbp+string], 0
0x1800f041d  xor     r8d, r8d; HSTRING *
0x1800f0420  lea     rdx, [rbp+string]; struct IUnknown *
0x1800f0424  mov     rcx, rsi; this
0x1800f0427  call    ?GetCallingAppPackageFamilyName@TokenBroker@Authentication@Security@Internal@Windows@@YAJPEAUIUnknown@@PEAPEAUHSTRING__@@PEAX@Z; Windows::Internal::Security::Authentication::TokenBroker::GetCallingAppPackageFamilyName(IUnknown *,HSTRING__ * *,void *)
0x1800f042c  mov     ebx, eax
0x1800f042e  cmp     eax, 80073D54h
0x1800f0433  jnz     short loc_1800F0439
0x1800f0435  xor     al, al
0x1800f0437  jmp     short loc_1800F0443
0x1800f0439  test    ebx, ebx
0x1800f043b  js      loc_1800F06EF
0x1800f0441  mov     al, 1
0x1800f0443  mov     rcx, rdi
0x1800f0446  mov     [rcx], al
0x1800f0448  mov     [rbp+TokenHandle], 0
0x1800f0450  lea     r8, [rbp+TokenHandle]
0x1800f0454  mov     edx, 20008h
0x1800f0459  mov     rcx, rsi
0x1800f045c  call    ?GetImpersonationTokenForClientOfObject_nothrow@wil@@YAJPEAUIUnknown@@KAEAV?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@1@@Z; wil::GetImpersonationTokenForClientOfObject_nothrow(IUnknown *,ulong,wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>> &)
0x1800f0461  mov     ebx, eax
0x1800f0463  test    eax, eax
0x1800f0465  jns     short loc_1800F048E
0x1800f0467  mov     rcx, [rbp+28h]; this
0x1800f046b  mov     r9d, eax; char *
0x1800f046e  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f0475  mov     edx, 6CDh; void *
0x1800f047a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f047f  nop
0x1800f0480  lea     rcx, [rbp+TokenHandle]; this
0x1800f0484  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f0489  jmp     loc_1800F0708
0x1800f048e  mov     [rbp+TokenInformationLength], 0
0x1800f0495  lea     rax, [rbp+TokenInformationLength]
0x1800f0499  mov     [rsp+80h+ReturnLength], rax; int
0x1800f049e  xor     r9d, r9d; TokenInformationLength
0x1800f04a1  xor     r8d, r8d; TokenInformation
0x1800f04a4  lea     esi, [r9+27h]
0x1800f04a8  mov     edx, esi; TokenInformationClass
0x1800f04aa  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800f04ae  call    cs:__imp_GetTokenInformation
0x1800f04b4  test    eax, eax
0x1800f04b6  jnz     short loc_1800F04E3
0x1800f04b8  call    cs:__imp_GetLastError
0x1800f04be  cmp     eax, 7Ah ; 'z'
0x1800f04c1  jz      short loc_1800F04E3
0x1800f04c3  test    eax, eax
0x1800f04c5  jz      short loc_1800F04E3
0x1800f04c7  mov     rcx, [rbp+28h]; this
0x1800f04cb  mov     r9d, eax; char *
0x1800f04ce  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f04d5  mov     edx, 6DAh; void *
0x1800f04da  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800f04df  mov     ebx, eax
0x1800f04e1  jmp     short loc_1800F0480
0x1800f04e3  mov     eax, [rbp+TokenInformationLength]
0x1800f04e6  test    eax, eax
0x1800f04e8  jnz     short loc_1800F050A
0x1800f04ea  mov     rcx, [rbp+28h]; this
0x1800f04ee  mov     r9d, 8000FFFFh; char *
0x1800f04f4  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f04fb  mov     edx, 6DEh; void *
0x1800f0500  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0505  jmp     loc_1800F06AC
0x1800f050a  mov     rdx, rax
0x1800f050d  shl     rdx, 4; uBytes
0x1800f0511  mov     ecx, 40h ; '@'; uFlags
0x1800f0516  call    cs:__imp_LocalAlloc
0x1800f051c  mov     rbx, rax
0x1800f051f  mov     [rbp+arg_0.lpVtbl], rax
0x1800f0523  test    rax, rax
0x1800f0526  jz      loc_1800F06CC
0x1800f052c  lea     rax, [rbp+TokenInformationLength]
0x1800f0530  mov     [rsp+80h+ReturnLength], rax; int
0x1800f0535  mov     r9d, [rbp+TokenInformationLength]; TokenInformationLength
0x1800f0539  mov     r8, rbx; TokenInformation
0x1800f053c  mov     edx, esi; TokenInformationClass
0x1800f053e  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x1800f0542  call    cs:__imp_GetTokenInformation
0x1800f0548  test    eax, eax
0x1800f054a  jnz     short loc_1800F058D
0x1800f054c  mov     rcx, [rbp+28h]; this
0x1800f0550  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f0557  mov     edx, 6E9h; void *
0x1800f055c  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800f0561  mov     edi, eax
0x1800f0563  mov     rcx, rbx; hMem
0x1800f0566  call    cs:__imp_LocalFree
0x1800f056c  nop
0x1800f056d  lea     rcx, [rbp+TokenHandle]; this
0x1800f0571  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f0576  nop
0x1800f0577  mov     rcx, [rbp+string]; string
0x1800f057b  test    rcx, rcx
0x1800f057e  jz      short loc_1800F0586
0x1800f0580  call    cs:__imp_WindowsDeleteString
0x1800f0586  mov     eax, edi
0x1800f0588  jmp     loc_1800F0719
0x1800f058d  xor     r14b, r14b
0x1800f0590  mov     qword ptr [rbp+String1.Length], 460044h
0x1800f0598  lea     rax, aWinContainerto; "WIN://ContainerTokenIntegrityLevel"
0x1800f059f  mov     [rbp+String1.Buffer], rax
0x1800f05a3  xor     esi, esi
0x1800f05a5  cmp     [rbx+4], esi
0x1800f05a8  jbe     loc_1800F0686
0x1800f05ae  lea     rcx, [rsi+rsi*4]
0x1800f05b2  mov     rax, [rbx+8]
0x1800f05b6  movups  xmm0, xmmword ptr [rax+rcx*8]
0x1800f05ba  movups  xmmword ptr [rbp+String2.Length], xmm0
0x1800f05be  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x1800f05c3  movups  [rbp+var_20], xmm1
0x1800f05c7  movsd   xmm0, qword ptr [rax+rcx*8+20h]
0x1800f05cd  movsd   [rbp+var_10], xmm0
0x1800f05d2  mov     r8b, 1; CaseInsensitive
0x1800f05d5  lea     rdx, [rbp+String2]; String2
0x1800f05d9  lea     rcx, [rbp+String1]; String1
0x1800f05dd  call    cs:__imp_RtlCompareUnicodeString
0x1800f05e3  test    eax, eax
0x1800f05e5  jnz     short loc_1800F060A
0x1800f05e7  mov     eax, 2
0x1800f05ec  cmp     ax, word ptr [rbp+var_20]
0x1800f05f0  jnz     loc_1800F067F
0x1800f05f6  cmp     dword ptr [rbp+var_20+8], 1
0x1800f05fa  jnz     short loc_1800F0678
0x1800f05fc  mov     rax, [rbp+var_10]
0x1800f0600  mov     rcx, [rax]
0x1800f0603  mov     [rdi+8], rcx
0x1800f0607  mov     r14b, 1
0x1800f060a  inc     esi
0x1800f060c  cmp     esi, [rbx+4]
0x1800f060f  jb      short loc_1800F05AE
0x1800f0611  test    r14b, r14b
0x1800f0614  jz      short loc_1800F0686
0x1800f0616  mov     eax, cs:dword_180175000
0x1800f061c  cmp     eax, 4
0x1800f061f  jbe     short loc_1800F064E
0x1800f0621  mov     rax, [rdi+8]
0x1800f0625  mov     [rbp+var_48], rax
0x1800f0629  movzx   eax, byte ptr [rdi]
0x1800f062c  mov     dword ptr [rbp+arg_0.lpVtbl], eax
0x1800f062f  lea     rax, [rbp+var_48]
0x1800f0633  mov     [rsp+80h+var_58], rax
0x1800f0638  lea     rax, [rbp+arg_0]
0x1800f063c  mov     [rsp+80h+ReturnLength], rax
0x1800f0641  lea     rdx, dword_1801533E4
0x1800f0648  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800f064d  nop
0x1800f064e  mov     rcx, rbx; hMem
0x1800f0651  call    cs:__imp_LocalFree
0x1800f0657  nop
0x1800f0658  lea     rcx, [rbp+TokenHandle]; this
0x1800f065c  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f0661  nop
0x1800f0662  mov     rcx, [rbp+string]; string
0x1800f0666  test    rcx, rcx
0x1800f0669  jz      short loc_1800F0671
0x1800f066b  call    cs:__imp_WindowsDeleteString
0x1800f0671  xor     eax, eax
0x1800f0673  jmp     loc_1800F0719
0x1800f0678  mov     edx, 6F7h
0x1800f067d  jmp     short loc_1800F068B
0x1800f067f  mov     edx, 6F6h
0x1800f0684  jmp     short loc_1800F068B
0x1800f0686  mov     edx, 6FEh; void *
0x1800f068b  mov     r9d, 8000FFFFh; char *
0x1800f0691  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f0698  mov     rcx, [rbp+28h]; this
0x1800f069c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f06a1  nop
0x1800f06a2  mov     rcx, rbx; hMem
0x1800f06a5  call    cs:__imp_LocalFree
0x1800f06ab  nop
0x1800f06ac  lea     rcx, [rbp+TokenHandle]; this
0x1800f06b0  call    ??1AsyncImpersonator@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::AsyncImpersonator::~AsyncImpersonator(void)
0x1800f06b5  nop
0x1800f06b6  mov     rcx, [rbp+string]; string
0x1800f06ba  test    rcx, rcx
0x1800f06bd  jz      short loc_1800F06C5
0x1800f06bf  call    cs:__imp_WindowsDeleteString
0x1800f06c5  mov     eax, 8000FFFFh
0x1800f06ca  jmp     short loc_1800F0719
0x1800f06cc  mov     rcx, [rbp+28h]; this
0x1800f06d0  mov     ebx, 8007000Eh
0x1800f06d5  mov     r9d, ebx; char *
0x1800f06d8  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f06df  mov     edx, 6E2h; void *
0x1800f06e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f06e9  nop
0x1800f06ea  jmp     loc_1800F0480
0x1800f06ef  mov     rcx, [rbp+28h]; this
0x1800f06f3  mov     r9d, ebx; char *
0x1800f06f6  lea     r8, aOnecoreDsSecur_1; "onecore\\ds\\security\\tokenbroker\\api"...
0x1800f06fd  mov     edx, 6C8h; void *
0x1800f0702  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800f0707  nop
0x1800f0708  mov     rcx, [rbp+string]; string
0x1800f070c  test    rcx, rcx
0x1800f070f  jz      short loc_1800F0717
0x1800f0711  call    cs:__imp_WindowsDeleteString
0x1800f0717  mov     eax, ebx
0x1800f0719  add     rsp, 80h
0x1800f0720  pop     r14
0x1800f0722  pop     rdi
0x1800f0723  pop     rsi
0x1800f0724  pop     rbx
0x1800f0725  pop     rbp
0x1800f0726  retn
```
