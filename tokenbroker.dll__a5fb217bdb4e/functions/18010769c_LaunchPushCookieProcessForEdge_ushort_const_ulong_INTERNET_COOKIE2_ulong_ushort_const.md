# LaunchPushCookieProcessForEdge(ushort const *,ulong,INTERNET_COOKIE2 *,ulong,ushort const *)

- ea: `0x18010769c`
- end: `0x180107b08`
- name: `?LaunchPushCookieProcessForEdge@@YAKPEBGKPEAUINTERNET_COOKIE2@@K0@Z`
- size: `1132`
- prototype: `unsigned int(const unsigned __int16 *, unsigned int, struct INTERNET_COOKIE2 *, unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `11`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180106908`
- `0x180106b44`

## callees

- `0x18001a510`
- `0x18002ea84`
- `0x1800348cc`
- `0x18004e850`
- `0x180055498`
- `0x18005d6c0`
- `0x180063fc4`
- `0x18009168c`
- `0x180106d10`
- `0x1801072f4`
- `0x18010769c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801078fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010791e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107993`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801078fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010791e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107993`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010797a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107a52`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18010797a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180107a52`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010781c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18010781c`
- `ntdll!RtlSetEnvironmentVar` at `0x1801077ef`
- `ntdll!RtlSetEnvironmentVar` at `0x1801077ef`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180107704`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x180107704`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107951`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180107951`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180107743`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180107743`
- `USERENV!CreateEnvironmentBlock` at `0x18010779c`
- `USERENV!CreateEnvironmentBlock` at `0x18010779c`
- `USERENV!GetAppContainerFolderPath` at `0x1801077b7`
- `USERENV!GetAppContainerFolderPath` at `0x1801077b7`
- `USERENV!DestroyEnvironmentBlock` at `0x180107964`
- `USERENV!DestroyEnvironmentBlock` at `0x180107964`
- `ext-ms-win-security-tokenbrokerui-l1-1-0!TokenBrokerGetEdgeSids` at `0x18010770a`
- `ext-ms-win-security-tokenbrokerui-l1-1-0!TokenBrokerGetEdgeSids` at `0x18010770a`

## string_xrefs

- `0x180107a7a`: `Completed`
- `0x1801076ef`: `IsTokenBrokerGetEdgeSidsPresentFailed`
- `0x18010771b`: `TokenBrokerGetEdgeSidsReturnsNullSid`

## pseudocode

```c
__int64 __fastcall LaunchPushCookieProcessForEdge(
        const unsigned __int16 *a1,
        __int64 a2,
        struct INTERNET_COOKIE2 *a3,
        unsigned int a4,
        unsigned __int16 *a5)
{
  struct INTERNET_COOKIE2 *v6; // r15
  char EdgeSidsPresent; // al
  const unsigned __int16 *v8; // r12
  unsigned int v9; // ebx
  _QWORD *EdgeSids; // rbx
  unsigned int v11; // r14d
  struct _SID_AND_ATTRIBUTES *v12; // rsi
  unsigned int v13; // r8d
  __int64 v14; // rdi
  void *v15; // rdx
  BOOL v16; // eax
  WCHAR *v17; // r15
  __int64 v18; // rax
  void *v19; // rdx
  unsigned int v20; // edx
  unsigned int v21; // r8d
  int v22; // eax
  int v23; // r8d
  int v24; // r9d
  char *v25; // rdx
  DWORD *v26; // rax
  int v27; // r9d
  int v28; // r8d
  const unsigned __int16 *v29; // r8
  HLOCAL hMem; // [rsp+48h] [rbp-31h] BYREF
  DWORD LastError; // [rsp+50h] [rbp-29h] BYREF
  LPVOID Environment; // [rsp+58h] [rbp-21h] BYREF
  const unsigned __int16 *v34; // [rsp+60h] [rbp-19h]
  const unsigned __int16 *v35; // [rsp+68h] [rbp-11h]
  LPVOID pv; // [rsp+70h] [rbp-9h] BYREF
  PSID Sid; // [rsp+78h] [rbp-1h] BYREF
  DWORD v38; // [rsp+80h] [rbp+7h] BYREF
  DWORD v39; // [rsp+84h] [rbp+Bh] BYREF
  void *TokenHandle; // [rsp+88h] [rbp+Fh] BYREF
  char v41; // [rsp+90h] [rbp+17h]
  int v43; // [rsp+E0h] [rbp+67h] BYREF
  struct INTERNET_COOKIE2 *v44; // [rsp+E8h] [rbp+6Fh]

  v44 = a3;
  hMem = 0;
  v6 = a3;
  Environment = 0;
  pv = 0;
  v43 = 0;
  Sid = 0;
  EdgeSidsPresent = IsTokenBrokerGetEdgeSidsPresent();
  v8 = a5;
  if ( EdgeSidsPresent )
  {
    RtlGetDeviceFamilyInfoEnum(0, &v43, 0);
    EdgeSids = (_QWORD *)TokenBrokerGetEdgeSids();
    if ( !EdgeSids )
    {
      v9 = 50;
      goto LABEL_42;
    }
    v11 = 0;
    v12 = 0;
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &Sid,
      0);
    ConvertStringSidToSidW(
      L"S-1-15-3-1024-2440306377-3304611049-1494399071-1161926223-163912384-1437065773-1456820560-2390158196",
      &Sid);
    if ( !*EdgeSids )
    {
LABEL_41:
      v9 = 0;
      goto LABEL_42;
    }
    while ( 1 )
    {
      v14 = 4LL * v11;
      if ( !BuildPushCookieCommandLine(
              (const unsigned __int16 *)EdgeSids[v14 + 3],
              a1,
              v13,
              v6,
              a4,
              (unsigned __int16 **)&hMem,
              v8) )
        break;
LABEL_40:
      if ( !EdgeSids[4 * ++v11] )
        goto LABEL_41;
    }
    v15 = (void *)EdgeSids[v14 + 2];
    if ( !v15 )
    {
      if ( (unsigned int)dword_180175038 > 2 )
      {
        LastError = GetLastError();
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175038,
          (unsigned int)word_180156E3A,
          0,
          v27,
          (__int64)&LastError);
      }
      v17 = (WCHAR *)hMem;
      if ( LaunchPushCookieProcess(0, (LPWSTR)hMem, (void *)EdgeSids[v14], 0, 0, 0, 0)
        && (unsigned int)dword_180175038 > 2
        && (unsigned __int8)tlgKeywordOn(&dword_180175038, 0x400000000000LL) )
      {
        v34 = (const unsigned __int16 *)EdgeSids[v14 + 3];
        LODWORD(hMem) = v28;
        v35 = v8;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
          &dword_180175038,
          byte_180156F4B,
          0);
      }
      goto LABEL_39;
    }
    v16 = CreateEnvironmentBlock(&Environment, v15, 0);
    v17 = (WCHAR *)hMem;
    if ( v16 )
    {
      if ( (int)GetAppContainerFolderPath(EdgeSids[v14 + 1], &pv) >= 0 )
      {
        v18 = -1;
        do
          ++v18;
        while ( *((_WORD *)pv + v18) );
        RtlSetEnvironmentVar(&Environment, L"LOCALAPPDATA", 12, pv, v18);
        v19 = (void *)EdgeSids[v14 + 2];
        TokenHandle = 0;
        v41 = 0;
        if ( (int)Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(&TokenHandle, v19) >= 0 )
        {
          v12 = (struct _SID_AND_ATTRIBUTES *)LocalAlloc(0x40u, 0x10u);
          v20 = 0;
          if ( v12 && Sid )
          {
            v12->Sid = Sid;
            v20 = 1;
            v12->Attributes = 4;
          }
          v21 = LaunchPushCookieProcess((HANDLE)EdgeSids[v14 + 2], v17, (void *)EdgeSids[v14], v12, v20, Environment, 1);
          if ( v21 > 0x1F || (v22 = -2147483643, !_bittest(&v22, v21)) )
          {
            if ( (unsigned int)dword_180175038 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180175038, 0x400000000000LL) )
            {
              v35 = (const unsigned __int16 *)EdgeSids[v14 + 3];
              LODWORD(hMem) = v23;
              v34 = v8;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
                &dword_180175038,
                byte_180156EB9,
                0);
            }
          }
        }
        Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope((Windows::Internal::Security::Authentication::Web::ThreadTokenScope *)&TokenHandle);
        goto LABEL_27;
      }
      if ( (unsigned int)dword_180175038 > 2 )
      {
        v38 = GetLastError();
        v25 = (char *)&unk_180156F10;
        v26 = &v38;
LABEL_26:
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
          (unsigned int)&dword_180175038,
          (_DWORD)v25,
          0,
          v24,
          (__int64)v26);
      }
    }
    else if ( (unsigned int)dword_180175038 > 2 )
    {
      v39 = GetLastError();
      v25 = byte_180157001;
      v26 = &v39;
      goto LABEL_26;
    }
LABEL_27:
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( Environment )
    {
      DestroyEnvironmentBlock(Environment);
      Environment = 0;
    }
    if ( v12 )
    {
      LocalFree(v12);
      v12 = 0;
    }
LABEL_39:
    LocalFree(v17);
    v6 = v44;
    hMem = 0;
    goto LABEL_40;
  }
  v9 = 50;
LABEL_42:
  if ( (unsigned int)dword_180175038 > 4 && (unsigned __int8)tlgKeywordOn(&dword_180175038, 0x400000000000LL) )
  {
    v34 = v29;
    v35 = v8;
    LastError = v9;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      &dword_180175038,
      &byte_180156E67,
      0);
  }
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&Sid);
  return v9;
}

```

## disassembly

```asm
0x18010769c  mov     rax, rsp
0x18010769f  mov     [rax+20h], rbx
0x1801076a3  mov     [rax+18h], r8
0x1801076a7  mov     [rax+10h], edx
0x1801076aa  mov     [rax+8], rcx
0x1801076ae  push    rbp
0x1801076af  push    rsi
0x1801076b0  push    rdi
0x1801076b1  push    r12
0x1801076b3  push    r13
0x1801076b5  push    r14
0x1801076b7  push    r15
0x1801076b9  lea     rbp, [rax-57h]
0x1801076bd  sub     rsp, 90h
0x1801076c4  xor     edi, edi
0x1801076c6  mov     r13d, r9d
0x1801076c9  mov     [rbp+4Fh+hMem], rdi
0x1801076cd  mov     r15, r8
0x1801076d0  mov     [rbp+4Fh+Environment], rdi
0x1801076d4  mov     [rbp+4Fh+pv], rdi
0x1801076d8  mov     [rbp+4Fh+arg_8], edi
0x1801076db  mov     [rbp+4Fh+Sid], rdi
0x1801076df  call    IsTokenBrokerGetEdgeSidsPresent
0x1801076e4  mov     r12, [rbp+4Fh+arg_20]
0x1801076e8  test    al, al
0x1801076ea  jnz     short loc_1801076FB
0x1801076ec  lea     ebx, [rdi+32h]
0x1801076ef  lea     r8, aIstokenbrokerg; "IsTokenBrokerGetEdgeSidsPresentFailed"
0x1801076f6  jmp     loc_180107A81
0x1801076fb  xor     r8d, r8d
0x1801076fe  lea     rdx, [rbp+4Fh+arg_8]
0x180107702  xor     ecx, ecx
0x180107704  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x18010770a  call    cs:__imp_TokenBrokerGetEdgeSids
0x180107710  mov     rbx, rax
0x180107713  test    rax, rax
0x180107716  jnz     short loc_180107727
0x180107718  lea     ebx, [rax+32h]
0x18010771b  lea     r8, aTokenbrokerget_1; "TokenBrokerGetEdgeSidsReturnsNullSid"
0x180107722  jmp     loc_180107A81
0x180107727  xor     edx, edx
0x180107729  lea     rcx, [rbp+4Fh+Sid]
0x18010772d  mov     r14d, edi
0x180107730  mov     rsi, rdi
0x180107733  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180107738  lea     rdx, [rbp+4Fh+Sid]; Sid
0x18010773c  lea     rcx, StringSid; "S-1-15-3-1024-2440306377-3304611049-149"...
0x180107743  call    cs:__imp_ConvertStringSidToSidW
0x180107749  cmp     [rbx], rdi
0x18010774c  jz      loc_180107A78
0x180107752  mov     rdx, [rbp+4Fh+arg_0]; unsigned __int16 *
0x180107756  lea     rax, [rbp+4Fh+hMem]
0x18010775a  mov     [rsp+30h], r12; unsigned __int16 *
0x18010775f  mov     r9, r15; struct INTERNET_COOKIE2 *
0x180107762  mov     [rsp+0C0h+var_98], rax; unsigned __int16 **
0x180107767  mov     edi, r14d
0x18010776a  shl     rdi, 5
0x18010776e  mov     [rsp+0C0h+var_A0], r13d; unsigned int
0x180107773  mov     rcx, [rdi+rbx+18h]; unsigned __int16 *
0x180107778  call    ?BuildPushCookieCommandLine@@YAKPEBG0KPEAUINTERNET_COOKIE2@@KPEAPEAG0@Z; BuildPushCookieCommandLine(ushort const *,ushort const *,ulong,INTERNET_COOKIE2 *,ulong,ushort * *,ushort const *)
0x18010777d  xor     ecx, ecx
0x18010777f  test    eax, eax
0x180107781  jnz     loc_180107A62
0x180107787  mov     rdx, [rdi+rbx+10h]; hToken
0x18010778c  test    rdx, rdx
0x18010778f  jz      loc_180107988
0x180107795  xor     r8d, r8d; bInherit
0x180107798  lea     rcx, [rbp+4Fh+Environment]; lpEnvironment
0x18010779c  call    cs:__imp_CreateEnvironmentBlock
0x1801077a2  mov     r15, [rbp+4Fh+hMem]
0x1801077a6  test    eax, eax
0x1801077a8  jz      loc_180107913
0x1801077ae  mov     rcx, [rdi+rbx+8]
0x1801077b3  lea     rdx, [rbp+4Fh+pv]
0x1801077b7  call    cs:__imp_GetAppContainerFolderPath
0x1801077bd  xor     ecx, ecx
0x1801077bf  test    eax, eax
0x1801077c1  js      loc_1801078F2
0x1801077c7  mov     r9, [rbp+4Fh+pv]
0x1801077cb  or      rax, 0FFFFFFFFFFFFFFFFh
0x1801077cf  inc     rax
0x1801077d2  cmp     [r9+rax*2], cx
0x1801077d7  jnz     short loc_1801077CF
0x1801077d9  mov     r8d, 0Ch
0x1801077df  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1801077e4  lea     rdx, aLocalappdata_0; "LOCALAPPDATA"
0x1801077eb  lea     rcx, [rbp+4Fh+Environment]
0x1801077ef  call    cs:__imp_RtlSetEnvironmentVar
0x1801077f5  mov     rdx, [rdi+rbx+10h]; hToken
0x1801077fa  lea     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x1801077fe  xor     eax, eax
0x180107800  mov     [rbp+4Fh+TokenHandle], rax
0x180107804  mov     [rbp+4Fh+var_38], al
0x180107807  call    ?Impersonate@ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAAJPEAX@Z; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::Impersonate(void *)
0x18010780c  test    eax, eax
0x18010780e  js      loc_1801078E7
0x180107814  mov     edx, 10h; uBytes
0x180107819  lea     ecx, [rdx+30h]; uFlags
0x18010781c  call    cs:__imp_LocalAlloc
0x180107822  mov     rsi, rax
0x180107825  xor     eax, eax
0x180107827  mov     edx, eax
0x180107829  test    rsi, rsi
0x18010782c  jz      short loc_180107844
0x18010782e  mov     rcx, [rbp+4Fh+Sid]
0x180107832  test    rcx, rcx
0x180107835  jz      short loc_180107844
0x180107837  mov     [rsi], rcx
0x18010783a  lea     edx, [rax+1]
0x18010783d  mov     dword ptr [rsi+8], 4
0x180107844  mov     rax, [rbp+4Fh+Environment]
0x180107848  mov     r9, rsi; struct _SID_AND_ATTRIBUTES *
0x18010784b  mov     r8, [rdi+rbx]; void *
0x18010784f  mov     rcx, [rdi+rbx+10h]; hToken
0x180107854  mov     dword ptr [rsp+30h], 1; int
0x18010785c  mov     [rsp+0C0h+var_98], rax; void *
0x180107861  mov     [rsp+0C0h+var_A0], edx; unsigned int
0x180107865  mov     rdx, r15; lpCommandLine
0x180107868  call    ?LaunchPushCookieProcess@@YAKPEAXPEAG0QEAU_SID_AND_ATTRIBUTES@@K0H@Z; LaunchPushCookieProcess(void *,ushort *,void *,_SID_AND_ATTRIBUTES * const,ulong,void *,int)
0x18010786d  mov     r8d, eax
0x180107870  cmp     eax, 1Fh
0x180107873  ja      short loc_180107880
0x180107875  mov     eax, 80000005h
0x18010787a  bt      eax, r8d
0x18010787e  jb      short loc_1801078E7
0x180107880  mov     ecx, cs:dword_180175038
0x180107886  cmp     ecx, 2
0x180107889  jbe     short loc_1801078E7
0x18010788b  mov     rdx, 400000000000h
0x180107895  lea     rcx, dword_180175038
0x18010789c  call    _tlgKeywordOn
0x1801078a1  test    al, al
0x1801078a3  jz      short loc_1801078E7
0x1801078a5  mov     rax, [rdi+rbx+18h]
0x1801078aa  lea     rdx, byte_180156EB9
0x1801078b1  mov     [rbp+4Fh+var_60], rax
0x1801078b5  lea     rcx, dword_180175038
0x1801078bc  lea     rax, [rbp+4Fh+var_68]
0x1801078c0  mov     dword ptr [rbp+4Fh+hMem], r8d
0x1801078c4  mov     [rsp+30h], rax
0x1801078c9  xor     r8d, r8d
0x1801078cc  lea     rax, [rbp+4Fh+var_60]
0x1801078d0  mov     [rbp+4Fh+var_68], r12
0x1801078d4  mov     [rsp+0C0h+var_98], rax
0x1801078d9  lea     rax, [rbp+4Fh+hMem]
0x1801078dd  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1801078e2  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1801078e7  lea     rcx, [rbp+4Fh+TokenHandle]; this
0x1801078eb  call    ??1ThreadTokenScope@Web@Authentication@Security@Internal@Windows@@QEAA@XZ; Windows::Internal::Security::Authentication::Web::ThreadTokenScope::~ThreadTokenScope(void)
0x1801078f0  jmp     short loc_180107946
0x1801078f2  mov     eax, cs:dword_180175038
0x1801078f8  cmp     eax, 2
0x1801078fb  jbe     short loc_180107946
0x1801078fd  call    cs:__imp_GetLastError
0x180107903  mov     [rbp+4Fh+var_48], eax
0x180107906  lea     rdx, unk_180156F10
0x18010790d  lea     rax, [rbp+4Fh+var_48]
0x180107911  jmp     short loc_180107932
0x180107913  mov     eax, cs:dword_180175038
0x180107919  cmp     eax, 2
0x18010791c  jbe     short loc_180107946
0x18010791e  call    cs:__imp_GetLastError
0x180107924  mov     [rbp+4Fh+var_44], eax
0x180107927  lea     rdx, byte_180157001
0x18010792e  lea     rax, [rbp+4Fh+var_44]
0x180107932  xor     r8d, r8d
0x180107935  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18010793a  lea     rcx, dword_180175038
0x180107941  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180107946  mov     rcx, [rbp+4Fh+pv]; pv
0x18010794a  xor     edi, edi
0x18010794c  test    rcx, rcx
0x18010794f  jz      short loc_18010795B
0x180107951  call    cs:__imp_CoTaskMemFree
0x180107957  mov     [rbp+4Fh+pv], rdi
0x18010795b  mov     rcx, [rbp+4Fh+Environment]; lpEnvironment
0x18010795f  test    rcx, rcx
0x180107962  jz      short loc_18010796E
0x180107964  call    cs:__imp_DestroyEnvironmentBlock
0x18010796a  mov     [rbp+4Fh+Environment], rdi
0x18010796e  test    rsi, rsi
0x180107971  jz      loc_180107A4F
0x180107977  mov     rcx, rsi; hMem
0x18010797a  call    cs:__imp_LocalFree
0x180107980  mov     rsi, rdi
0x180107983  jmp     loc_180107A4F
0x180107988  mov     eax, cs:dword_180175038
0x18010798e  cmp     eax, 2
0x180107991  jbe     short loc_1801079BD
0x180107993  call    cs:__imp_GetLastError
0x180107999  mov     [rbp+4Fh+var_78], eax
0x18010799c  xor     r8d, r8d
0x18010799f  lea     rdx, word_180156E3A
0x1801079a6  lea     rax, [rbp+4Fh+var_78]
0x1801079aa  lea     rcx, dword_180175038
0x1801079b1  mov     qword ptr [rsp+0C0h+var_A0], rax
0x1801079b6  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x1801079bb  xor     ecx, ecx
0x1801079bd  mov     r15, [rbp+4Fh+hMem]
0x1801079c1  xor     r9d, r9d; struct _SID_AND_ATTRIBUTES *
0x1801079c4  mov     r8, [rdi+rbx]; void *
0x1801079c8  mov     rdx, r15; lpCommandLine
0x1801079cb  mov     [rsp+30h], ecx; int
0x1801079cf  mov     [rsp+0C0h+var_98], rcx; void *
0x1801079d4  mov     [rsp+0C0h+var_A0], ecx; unsigned int
0x1801079d8  xor     ecx, ecx; hToken
0x1801079da  call    ?LaunchPushCookieProcess@@YAKPEAXPEAG0QEAU_SID_AND_ATTRIBUTES@@K0H@Z; LaunchPushCookieProcess(void *,ushort *,void *,_SID_AND_ATTRIBUTES * const,ulong,void *,int)
0x1801079df  mov     r8d, eax
0x1801079e2  test    eax, eax
0x1801079e4  jz      short loc_180107A4D
0x1801079e6  mov     ecx, cs:dword_180175038
0x1801079ec  cmp     ecx, 2
0x1801079ef  jbe     short loc_180107A4D
0x1801079f1  mov     rdx, 400000000000h
0x1801079fb  lea     rcx, dword_180175038
0x180107a02  call    _tlgKeywordOn
0x180107a07  test    al, al
0x180107a09  jz      short loc_180107A4D
0x180107a0b  mov     rax, [rdi+rbx+18h]
0x180107a10  lea     rdx, byte_180156F4B
0x180107a17  mov     [rbp+4Fh+var_68], rax
0x180107a1b  lea     rcx, dword_180175038
0x180107a22  lea     rax, [rbp+4Fh+var_60]
0x180107a26  mov     dword ptr [rbp+4Fh+hMem], r8d
0x180107a2a  mov     [rsp+30h], rax
0x180107a2f  xor     r8d, r8d
0x180107a32  lea     rax, [rbp+4Fh+var_68]
0x180107a36  mov     [rbp+4Fh+var_60], r12
0x180107a3a  mov     [rsp+0C0h+var_98], rax
0x180107a3f  lea     rax, [rbp+4Fh+hMem]
0x180107a43  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180107a48  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180107a4d  xor     edi, edi
0x180107a4f  mov     rcx, r15; hMem
0x180107a52  call    cs:__imp_LocalFree
0x180107a58  mov     r15, [rbp+4Fh+arg_10]
0x180107a5c  mov     [rbp+4Fh+hMem], rdi
0x180107a60  jmp     short loc_180107A64
0x180107a62  xor     edi, edi
0x180107a64  inc     r14d
0x180107a67  mov     eax, r14d
0x180107a6a  shl     rax, 5
0x180107a6e  cmp     [rax+rbx], rdi
0x180107a72  jnz     loc_180107752
0x180107a78  mov     ebx, edi
0x180107a7a  lea     r8, aCompleted_0; "Completed"
0x180107a81  mov     eax, cs:dword_180175038
0x180107a87  cmp     eax, 4
0x180107a8a  jbe     short loc_180107AE2
0x180107a8c  mov     rdx, 400000000000h
0x180107a96  lea     rcx, dword_180175038
0x180107a9d  call    _tlgKeywordOn
0x180107aa2  test    al, al
0x180107aa4  jz      short loc_180107AE2
0x180107aa6  lea     rax, [rbp+4Fh+var_60]
0x180107aaa  mov     [rbp+4Fh+var_68], r8
0x180107aae  mov     [rsp+30h], rax
0x180107ab3  lea     rdx, byte_180156E67
0x180107aba  lea     rax, [rbp+4Fh+var_68]
0x180107abe  mov     [rbp+4Fh+var_60], r12
0x180107ac2  mov     [rsp+0C0h+var_98], rax
0x180107ac7  lea     rcx, dword_180175038
0x180107ace  lea     rax, [rbp+4Fh+var_78]
0x180107ad2  mov     [rbp+4Fh+var_78], ebx
0x180107ad5  xor     r8d, r8d
0x180107ad8  mov     qword ptr [rsp+0C0h+var_A0], rax
0x180107add  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x180107ae2  lea     rcx, [rbp+4Fh+Sid]
0x180107ae6  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x180107aeb  mov     eax, ebx
0x180107aed  mov     rbx, [rsp+0C0h+arg_18]
0x180107af5  add     rsp, 90h
0x180107afc  pop     r15
0x180107afe  pop     r14
0x180107b00  pop     r13
0x180107b02  pop     r12
0x180107b04  pop     rdi
0x180107b05  pop     rsi
0x180107b06  pop     rbp
0x180107b07  retn
```
