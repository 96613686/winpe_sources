# WinBioCredMgrSrvSetCredential

- ea: `0x1800bcd80`
- end: `0x1800bd3bf`
- name: `WinBioCredMgrSrvSetCredential`
- size: `1599`
- prototype: `__int64 __fastcall(void *, int, void *, DWORD, int)`
- caller_count: `0`
- callee_count: `29`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x18000367c`
- `0x180004808`
- `0x1800048c8`
- `0x1800058ec`
- `0x180011d24`
- `0x180025d94`
- `0x1800275b4`
- `0x18003ecc8`
- `0x1800401b8`
- `0x180040600`
- `0x180059038`
- `0x180060dc8`
- `0x180063c6c`
- `0x180068f60`
- `0x180069cc8`
- `0x18006fde0`
- `0x1800bb468`
- `0x1800bbb1c`
- `0x1800bbb84`
- `0x1800bbcec`
- `0x1800bbe9c`
- `0x1800bc048`
- `0x1800bc0c4`
- `0x1800bc144`
- `0x1800bcd80`
- `0x1800bd3f8`
- `0x1800bd7d8`
- `0x1800bd970`
- `0x1800bf0dc`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd373`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800bd373`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bcfca`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800bcfca`
- `RPCRT4!RpcRevertToSelf` at `0x1800bd32f`
- `RPCRT4!RpcRevertToSelf` at `0x1800bd32f`
- `RPCRT4!RpcImpersonateClient` at `0x1800bd18b`
- `RPCRT4!RpcImpersonateClient` at `0x1800bd18b`
- `CRYPT32!CryptUnprotectMemory` at `0x1800bcee6`
- `CRYPT32!CryptUnprotectMemory` at `0x1800bcee6`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bd051`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800bd051`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WinBioCredMgrSrvSetCredential(void *a1, int a2, void *a3, DWORD a4, int a5)
{
  __int64 v7; // rcx
  DWORD v8; // r8d
  DWORD v9; // edx
  CUserContext *v10; // rcx
  DWORD LengthSid; // eax
  CUserContext *v12; // rcx
  unsigned __int64 v13; // rdx
  __int64 v14; // r9
  RPC_STATUS v15; // ebx
  unsigned int v16; // r8d
  unsigned int v17; // r8d
  __int64 v18; // rcx
  unsigned int v19; // r8d
  unsigned int v20; // r8d
  unsigned int v21; // ebx
  int cchReferencedDomainName; // [rsp+20h] [rbp-838h]
  int v24; // [rsp+30h] [rbp-828h] BYREF
  DWORD cbDataIn; // [rsp+38h] [rbp-820h] BYREF
  PSID pSid; // [rsp+40h] [rbp-818h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-810h] BYREF
  WCHAR *v28; // [rsp+50h] [rbp-808h] BYREF
  WCHAR *v29; // [rsp+58h] [rbp-800h] BYREF
  LPVOID pDataIn; // [rsp+60h] [rbp-7F8h] BYREF
  _OWORD v31[2]; // [rsp+68h] [rbp-7F0h] BYREF
  DWORD v32; // [rsp+88h] [rbp-7D0h] BYREF
  DWORD cchName; // [rsp+8Ch] [rbp-7CCh] BYREF
  __int128 v34; // [rsp+90h] [rbp-7C8h] BYREF
  int v35; // [rsp+A0h] [rbp-7B8h]
  _QWORD v36[3]; // [rsp+A8h] [rbp-7B0h] BYREF
  _QWORD v37[2]; // [rsp+C0h] [rbp-798h] BYREF
  _BYTE v38[24]; // [rsp+D0h] [rbp-788h] BYREF
  PSID *p_pSid; // [rsp+E8h] [rbp-770h]
  _BYTE v40[32]; // [rsp+F0h] [rbp-768h] BYREF
  unsigned __int16 v41[128]; // [rsp+110h] [rbp-748h] BYREF
  WCHAR pszPassword[264]; // [rsp+210h] [rbp-648h] BYREF
  WCHAR ReferencedDomainName[256]; // [rsp+420h] [rbp-438h] BYREF
  WCHAR Name[268]; // [rsp+620h] [rbp-238h] BYREF

  pDataIn = a3;
  cbDataIn = a4;
  v24 = -2147467259;
  pSid = 0;
  v34 = 0;
  v35 = 0;
  peUse = 0;
  memset_0(Name, 0, 0x202u);
  cchName = 257;
  memset_0(ReferencedDomainName, 0, sizeof(ReferencedDomainName));
  v32 = 256;
  CCredProvVault::CCredProvVault((CCredProvVault *)v40);
  CActivityMonitor::NotifyClientArrival(0xC0FFFFFF);
  p_pSid = &pSid;
  v37[0] = &pDataIn;
  v37[1] = &cbDataIn;
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v38);
  std::vector<unsigned char,wil::secure_allocator<unsigned char>>::vector<unsigned char,wil::secure_allocator<unsigned char>>(v36);
  if ( !a1 )
    goto LABEL_41;
  if ( CUserContext::OpenContext((CUserContext *)&v34, a1) < 0 )
    goto LABEL_40;
  if ( a2 != 1 || a5 != 1 || cbDataIn < 8 || (cbDataIn & 7) != 0 )
    goto LABEL_41;
  v24 = CUserContext::Impersonate((CUserContext *)&v34);
  if ( v24 < 0 )
  {
    v9 = cbDataIn;
  }
  else
  {
    if ( !CryptUnprotectMemory(pDataIn, cbDataIn, 2u) )
    {
      v24 = -2147024809;
      CUserContext::RevertToSelf((CUserContext *)&v34);
      goto LABEL_42;
    }
    CUserContext::RevertToSelf((CUserContext *)&v34);
    v7 = cbDataIn - 1;
    v8 = *((unsigned __int8 *)pDataIn + v7);
    if ( !*((_BYTE *)pDataIn + v7) || v8 > cbDataIn || v8 > 0x10 )
      goto LABEL_41;
    v9 = cbDataIn - v8;
    cbDataIn -= v8;
  }
  if ( (v9 & 1) != 0 )
  {
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    v9 = cbDataIn;
  }
  if ( (v9 & 0xFFFFFFFE) > 0x202 )
  {
LABEL_41:
    v24 = -2147024809;
    goto LABEL_42;
  }
  if ( (int)CUserContext::GetUserSid((HANDLE *)&v34, &pSid) < 0 )
    goto LABEL_40;
  if ( !CUserContext::IsCredProvEnabled(v10, pSid) )
  {
LABEL_39:
    v24 = -2146861008;
    goto LABEL_42;
  }
  if ( (unsigned int)CUserContext::IsLowIntegrity((CUserContext *)&v34)
    || (unsigned int)CUserContext::IsAppContainer((CUserContext *)&v34) )
  {
    goto LABEL_38;
  }
  if ( __eh34_try(-1, 0) )
  {
    __eh34_scope_strut(0);
    LengthSid = GetLengthSid(pSid);
    std::vector<unsigned char>::_Assign_counted_range<unsigned char *>(v38, pSid, LengthSid);
  }
  if ( __eh34_catch(0) )
  {
    if ( __eh34_catch_type(0, &std::bad_alloc `RTTI Type Descriptor', 0) )
    {
      v24 = -2147024882;
      __eh34_try_continuation(0, &std::bad_alloc `RTTI Type Descriptor', &loc_1800BD15F);
      goto LABEL_42;
    }
  }
  if ( (int)NgcUtils::NgcCredProvEnumLogonKeys(v38, v36) < 0 )
  {
LABEL_40:
    v24 = -2146861053;
    goto LABEL_42;
  }
  if ( v36[0] != v36[1] )
    goto LABEL_39;
  if ( !LookupAccountSidLocalW(pSid, Name, &cchName, ReferencedDomainName, &v32, &peUse) )
    goto LABEL_40;
  if ( peUse != SidTypeUser )
  {
LABEL_38:
    v24 = -2147024891;
    goto LABEL_42;
  }
  if ( ((int (__stdcall *)(CUserContext *, void *))CUserContext::IsProhibitedAccount)(v12, pSid) )
    goto LABEL_40;
  memset_0(pszPassword, 0, 0x202u);
  v29 = pszPassword;
  LODWORD(v28) = 514;
  *(_QWORD *)&v31[0] = &v29;
  *((_QWORD *)&v31[0] + 1) = &v28;
  if ( StringCchCopyNW(pszPassword, v13, (const unsigned __int16 *)pDataIn, (unsigned __int64)cbDataIn >> 1) >= 0 )
  {
    v24 = CheckPassword(Name, ReferencedDomainName, pszPassword);
    if ( v24 >= 0 )
    {
      v14 = -1;
      do
        ++v14;
      while ( pszPassword[v14] );
      if ( CCredProvVault::AddCredential(
             (CCredProvVault *)v40,
             pSid,
             (unsigned __int8 *)pszPassword,
             2 * v14 + 2,
             cchReferencedDomainName) )
      {
        v24 = -2147024891;
      }
    }
    else
    {
      v24 = -2146893044;
    }
  }
  else
  {
    v24 = -2147024809;
  }
  ScopedSecureZero<unsigned long>::~ScopedSecureZero<unsigned long>(v31);
LABEL_42:
  v15 = RpcImpersonateClient(0);
  if ( v24 < 0 )
  {
    if ( v24 == -2147024891 || v24 == -2146893044 )
    {
      memset_0(v41, 0, sizeof(v41));
      v29 = v41;
      memset_0(pszPassword, 0, 0x200u);
      v28 = pszPassword;
      if ( pSid )
      {
        ((void (__fastcall *)(PSID, unsigned __int16 *, unsigned int))GetTextSid)(pSid, v41, v19);
        GetSIDUserName(pSid, pszPassword, v20);
      }
      *(_QWORD *)&v31[0] = &v29;
      *((_QWORD *)&v31[0] + 1) = &v28;
      *(_QWORD *)&v31[1] = &v24;
      *((_QWORD *)&v31[1] + 1) = 0;
      v18 = 1501;
    }
    else if ( v24 == -2146861008 )
    {
      memset(v31, 0, sizeof(v31));
      v18 = 1502;
    }
    else
    {
      *(_QWORD *)&v31[0] = &v24;
      memset((char *)v31 + 8, 0, 24);
      v18 = 1503;
    }
  }
  else
  {
    memset_0(v41, 0, sizeof(v41));
    v29 = v41;
    memset_0(pszPassword, 0, 0x200u);
    v28 = pszPassword;
    ((void (__fastcall *)(PSID, unsigned __int16 *, unsigned int))GetTextSid)(pSid, v41, v16);
    GetSIDUserName(pSid, pszPassword, v17);
    *(_QWORD *)&v31[0] = &v29;
    *((_QWORD *)&v31[0] + 1) = &v28;
    v31[1] = 0;
    v18 = 1500;
  }
  _LogEvent(v18, v31);
  if ( !v15 )
    RpcRevertToSelf();
  v21 = v24;
  std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(v36);
  std::vector<unsigned char>::_Tidy(v38);
  CActivityMonitor::NotifyClientDeparture(0xC0FFFFFF);
  ScopedSecureZero<unsigned long>::~ScopedSecureZero<unsigned long>(v37);
  LocalFree(pSid);
  pSid = 0;
  CBioKeyVault::~CBioKeyVault((CBioKeyVault *)v40);
  CUserContext::~CUserContext((CUserContext *)&v34);
  return v21;
}

```

## disassembly

```asm
0x1800bcd80  mov     [rsp+arg_8], rbx
0x1800bcd85  push    rsi
0x1800bcd86  push    rdi
0x1800bcd87  push    r15
0x1800bcd89  sub     rsp, 840h
0x1800bcd90  mov     rax, cs:__security_cookie
0x1800bcd97  xor     rax, rsp
0x1800bcd9a  mov     [rsp+858h+var_20], rax
0x1800bcda2  mov     esi, edx
0x1800bcda4  mov     rbx, rcx
0x1800bcda7  mov     [rsp+858h+pDataIn], r8
0x1800bcdac  mov     [rsp+858h+cbDataIn], r9d
0x1800bcdb1  mov     [rsp+858h+var_828], 80004005h
0x1800bcdb9  xor     edi, edi
0x1800bcdbb  mov     [rsp+858h+pSid], rdi
0x1800bcdc0  xorps   xmm0, xmm0
0x1800bcdc3  movdqu  [rsp+858h+var_7C8], xmm0
0x1800bcdcc  mov     [rsp+858h+var_7B8], edi
0x1800bcdd3  mov     [rsp+858h+var_810], edi
0x1800bcdd7  mov     r15d, 202h
0x1800bcddd  mov     r8d, r15d; Size
0x1800bcde0  xor     edx, edx; Val
0x1800bcde2  lea     rcx, [rsp+858h+Name]; void *
0x1800bcdea  call    memset_0
0x1800bcdef  mov     [rsp+858h+cchName], 101h
0x1800bcdfa  xor     edx, edx; Val
0x1800bcdfc  lea     r8d, [r15-2]; Size
0x1800bce00  lea     rcx, [rsp+858h+ReferencedDomainName]; void *
0x1800bce08  call    memset_0
0x1800bce0d  mov     [rsp+858h+var_7D0], 100h
0x1800bce18  lea     rcx, [rsp+858h+var_768]; this
0x1800bce20  call    ??0CCredProvVault@@QEAA@XZ; CCredProvVault::CCredProvVault(void)
0x1800bce25  nop
0x1800bce26  mov     ecx, 0C0FFFFFFh; unsigned int
0x1800bce2b  call    ?NotifyClientArrival@CActivityMonitor@@SAXI@Z; CActivityMonitor::NotifyClientArrival(uint)
0x1800bce30  lea     rax, [rsp+858h+pSid]
0x1800bce35  mov     [rsp+858h+var_770], rax
0x1800bce3d  lea     rax, [rsp+858h+pDataIn]
0x1800bce42  mov     [rsp+858h+var_798], rax
0x1800bce4a  lea     rax, [rsp+858h+cbDataIn]
0x1800bce4f  mov     [rsp+858h+var_790], rax
0x1800bce57  lea     rcx, [rsp+858h+var_788]
0x1800bce5f  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800bce64  nop
0x1800bce65  lea     rcx, [rsp+858h+var_7B0]
0x1800bce6d  call    ??0?$vector@EU?$secure_allocator@E@wil@@@std@@QEAA@XZ; std::vector<uchar,wil::secure_allocator<uchar>>::vector<uchar,wil::secure_allocator<uchar>>(void)
0x1800bce72  nop
0x1800bce73  test    rbx, rbx
0x1800bce76  jz      loc_1800BD181
0x1800bce7c  mov     rdx, rbx; void *
0x1800bce7f  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bce87  call    ?OpenContext@CUserContext@@QEAAJPEAX@Z; CUserContext::OpenContext(void *)
0x1800bce8c  mov     [rsp+858h+var_828], eax
0x1800bce90  test    eax, eax
0x1800bce92  js      loc_1800BD177
0x1800bce98  cmp     esi, 1
0x1800bce9b  jnz     loc_1800BD181
0x1800bcea1  cmp     [rsp+858h+arg_20], esi
0x1800bcea8  jnz     loc_1800BD181
0x1800bceae  cmp     [rsp+858h+cbDataIn], 8
0x1800bceb3  jb      loc_1800BD181
0x1800bceb9  test    byte ptr [rsp+858h+cbDataIn], 7
0x1800bcebe  jnz     loc_1800BD181
0x1800bcec4  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bcecc  call    ?Impersonate@CUserContext@@QEAAJXZ; CUserContext::Impersonate(void)
0x1800bced1  mov     [rsp+858h+var_828], eax
0x1800bced5  test    eax, eax
0x1800bced7  js      short loc_1800BCF4D
0x1800bced9  lea     r8d, [rdi+2]; dwFlags
0x1800bcedd  mov     edx, [rsp+858h+cbDataIn]; cbDataIn
0x1800bcee1  mov     rcx, [rsp+858h+pDataIn]; pDataIn
0x1800bcee6  call    cs:__imp_CryptUnprotectMemory
0x1800bceec  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bcef4  test    eax, eax
0x1800bcef6  jnz     short loc_1800BCF0A
0x1800bcef8  mov     [rsp+858h+var_828], 80070057h
0x1800bcf00  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x1800bcf05  jmp     loc_1800BD189
0x1800bcf0a  call    ?RevertToSelf@CUserContext@@QEAAJXZ; CUserContext::RevertToSelf(void)
0x1800bcf0f  mov     eax, [rsp+858h+var_828]
0x1800bcf13  test    eax, eax
0x1800bcf15  js      short loc_1800BCF4D
0x1800bcf17  mov     edx, [rsp+858h+cbDataIn]
0x1800bcf1b  lea     ecx, [rdx-1]
0x1800bcf1e  mov     rax, [rsp+858h+pDataIn]
0x1800bcf23  movzx   r8d, byte ptr [rcx+rax]
0x1800bcf28  test    r8d, r8d
0x1800bcf2b  jz      loc_1800BD181
0x1800bcf31  cmp     r8d, edx
0x1800bcf34  ja      loc_1800BD181
0x1800bcf3a  cmp     r8d, 10h
0x1800bcf3e  ja      loc_1800BD181
0x1800bcf44  sub     edx, r8d
0x1800bcf47  mov     [rsp+858h+cbDataIn], edx
0x1800bcf4b  jmp     short loc_1800BCF51
0x1800bcf4d  mov     edx, [rsp+858h+cbDataIn]
0x1800bcf51  test    dl, 1
0x1800bcf54  jz      short loc_1800BCF5F
0x1800bcf56  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800bcf5b  mov     edx, [rsp+858h+cbDataIn]
0x1800bcf5f  and     edx, 0FFFFFFFEh
0x1800bcf62  cmp     edx, r15d
0x1800bcf65  ja      loc_1800BD181
0x1800bcf6b  lea     rdx, [rsp+858h+pSid]; void **
0x1800bcf70  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bcf78  call    ?GetUserSid@CUserContext@@QEBAJPEAPEAX@Z; CUserContext::GetUserSid(void * *)
0x1800bcf7d  mov     [rsp+858h+var_828], eax
0x1800bcf81  test    eax, eax
0x1800bcf83  js      loc_1800BD177
0x1800bcf89  mov     rdx, [rsp+858h+pSid]; void *
0x1800bcf8e  call    ?IsCredProvEnabled@CUserContext@@QEBAHPEAX@Z; CUserContext::IsCredProvEnabled(void *)
0x1800bcf93  test    eax, eax
0x1800bcf95  jz      loc_1800BD16D
0x1800bcf9b  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bcfa3  call    ?IsLowIntegrity@CUserContext@@QEBAHXZ; CUserContext::IsLowIntegrity(void)
0x1800bcfa8  test    eax, eax
0x1800bcfaa  jnz     loc_1800BD163
0x1800bcfb0  lea     rcx, [rsp+858h+var_7C8]; this
0x1800bcfb8  call    ?IsAppContainer@CUserContext@@QEBAHXZ; CUserContext::IsAppContainer(void)
0x1800bcfbd  test    eax, eax
0x1800bcfbf  jnz     loc_1800BD163
0x1800bcfc5  mov     rcx, [rsp+858h+pSid]; pSid
0x1800bcfca  call    cs:__imp_GetLengthSid
0x1800bcfd0  mov     r8d, eax
0x1800bcfd3  mov     rdx, [rsp+858h+pSid]
0x1800bcfd8  lea     rcx, [rsp+858h+var_788]
0x1800bcfe0  call    ??$_Assign_counted_range@PEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAXPEAE_K@Z; std::vector<uchar>::_Assign_counted_range<uchar *>(uchar *,unsigned __int64)
0x1800bcfe5  nop
0x1800bcfe6  lea     rdx, [rsp+858h+var_7B0]
0x1800bcfee  lea     rcx, [rsp+858h+var_788]
0x1800bcff6  call    ?NgcCredProvEnumLogonKeys@NgcUtils@@YAJAEBV?$vector@EV?$allocator@E@std@@@std@@PEAV?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@3@@Z; NgcUtils::NgcCredProvEnumLogonKeys(std::vector<uchar> const &,std::vector<std::shared_ptr<KeyEnumInfo>> *)
0x1800bcffb  mov     [rsp+858h+var_828], eax
0x1800bcfff  test    eax, eax
0x1800bd001  js      loc_1800BD177
0x1800bd007  mov     rax, [rsp+858h+var_7A8]
0x1800bd00f  cmp     [rsp+858h+var_7B0], rax
0x1800bd017  jnz     loc_1800BD16D
0x1800bd01d  lea     rax, [rsp+858h+var_810]
0x1800bd022  mov     [rsp+858h+peUse], rax; peUse
0x1800bd027  lea     rax, [rsp+858h+var_7D0]
0x1800bd02f  mov     [rsp+858h+cchReferencedDomainName], rax; int
0x1800bd034  lea     r9, [rsp+858h+ReferencedDomainName]; ReferencedDomainName
0x1800bd03c  lea     r8, [rsp+858h+cchName]; cchName
0x1800bd044  lea     rdx, [rsp+858h+Name]; Name
0x1800bd04c  mov     rcx, [rsp+858h+pSid]; Sid
0x1800bd051  call    cs:__imp_LookupAccountSidLocalW
0x1800bd057  test    eax, eax
0x1800bd059  jz      loc_1800BD177
0x1800bd05f  cmp     [rsp+858h+var_810], 1
0x1800bd064  jnz     loc_1800BD163
0x1800bd06a  mov     rdx, [rsp+858h+pSid]; void *
0x1800bd06f  call    ?IsProhibitedAccount@CUserContext@@QEBAHPEAX@Z; CUserContext::IsProhibitedAccount(void *)
0x1800bd074  test    eax, eax
0x1800bd076  jnz     loc_1800BD177
0x1800bd07c  mov     r8, r15; Size
0x1800bd07f  xor     edx, edx; Val
0x1800bd081  lea     rcx, [rsp+858h+pszPassword]; void *
0x1800bd089  call    memset_0
0x1800bd08e  lea     rax, [rsp+858h+pszPassword]
0x1800bd096  mov     [rsp+858h+var_800], rax
0x1800bd09b  mov     dword ptr [rsp+858h+var_808], r15d
0x1800bd0a0  lea     rax, [rsp+858h+var_800]
0x1800bd0a5  mov     qword ptr [rsp+858h+var_7F0], rax
0x1800bd0aa  lea     rax, [rsp+858h+var_808]
0x1800bd0af  mov     qword ptr [rsp+858h+var_7F0+8], rax
0x1800bd0b4  mov     r9d, [rsp+858h+cbDataIn]
0x1800bd0b9  shr     r9, 1; unsigned __int64
0x1800bd0bc  mov     r8, [rsp+858h+pDataIn]; unsigned __int16 *
0x1800bd0c1  lea     rcx, [rsp+858h+pszPassword]; unsigned __int16 *
0x1800bd0c9  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x1800bd0ce  mov     [rsp+858h+var_828], eax
0x1800bd0d2  test    eax, eax
0x1800bd0d4  jns     short loc_1800BD0E0
0x1800bd0d6  mov     [rsp+858h+var_828], 80070057h
0x1800bd0de  jmp     short loc_1800BD153
0x1800bd0e0  lea     r8, [rsp+858h+pszPassword]; pszPassword
0x1800bd0e8  lea     rdx, [rsp+858h+ReferencedDomainName]; unsigned __int16 *
0x1800bd0f0  lea     rcx, [rsp+858h+Name]; unsigned __int16 *
0x1800bd0f8  call    _CheckPassword
0x1800bd0fd  mov     [rsp+858h+var_828], eax
0x1800bd101  test    eax, eax
0x1800bd103  jns     short loc_1800BD10F
0x1800bd105  mov     [rsp+858h+var_828], 8009030Ch
0x1800bd10d  jmp     short loc_1800BD153
0x1800bd10f  lea     rax, [rsp+858h+pszPassword]
0x1800bd117  or      r9, 0FFFFFFFFFFFFFFFFh
0x1800bd11b  inc     r9
0x1800bd11e  cmp     [rax+r9*2], di
0x1800bd123  jnz     short loc_1800BD11B
0x1800bd125  lea     r9d, ds:2[r9*2]; unsigned int
0x1800bd12d  lea     r8, [rsp+858h+pszPassword]; unsigned __int8 *
0x1800bd135  mov     rdx, [rsp+858h+pSid]; void *
0x1800bd13a  lea     rcx, [rsp+858h+var_768]; this
0x1800bd142  call    ?AddCredential@CCredProvVault@@QEAAKPEAXPEAEKH@Z; CCredProvVault::AddCredential(void *,uchar *,ulong,int)
0x1800bd147  test    eax, eax
0x1800bd149  jz      short loc_1800BD153
0x1800bd14b  mov     [rsp+858h+var_828], 80070005h
0x1800bd153  lea     rcx, [rsp+858h+var_7F0]
0x1800bd158  call    ??1?$ScopedSecureZero@K@@QEAA@XZ; ScopedSecureZero<ulong>::~ScopedSecureZero<ulong>(void)
0x1800bd15d  jmp     short loc_1800BD189
0x1800bd15f  xor     edi, edi
0x1800bd161  jmp     short loc_1800BD189
0x1800bd163  mov     [rsp+858h+var_828], 80070005h
0x1800bd16b  jmp     short loc_1800BD189
0x1800bd16d  mov     [rsp+858h+var_828], 80098030h
0x1800bd175  jmp     short loc_1800BD189
0x1800bd177  mov     [rsp+858h+var_828], 80098003h
0x1800bd17f  jmp     short loc_1800BD189
0x1800bd181  mov     [rsp+858h+var_828], 80070057h
0x1800bd189  xor     ecx, ecx; BindingHandle
0x1800bd18b  call    cs:__imp_RpcImpersonateClient
0x1800bd191  mov     ebx, eax
0x1800bd193  mov     ecx, [rsp+858h+var_828]
0x1800bd197  test    ecx, ecx
0x1800bd199  js      loc_1800BD22E
0x1800bd19f  xor     edx, edx; Val
0x1800bd1a1  mov     r8d, 100h; Size
0x1800bd1a7  lea     rcx, [rsp+858h+var_748]; void *
0x1800bd1af  call    memset_0
0x1800bd1b4  lea     rax, [rsp+858h+var_748]
0x1800bd1bc  mov     [rsp+858h+var_800], rax
0x1800bd1c1  xor     edx, edx; Val
0x1800bd1c3  mov     r8d, 200h; Size
0x1800bd1c9  lea     rcx, [rsp+858h+pszPassword]; void *
0x1800bd1d1  call    memset_0
0x1800bd1d6  lea     rax, [rsp+858h+pszPassword]
0x1800bd1de  mov     [rsp+858h+var_808], rax
0x1800bd1e3  lea     rdx, [rsp+858h+var_748]; unsigned __int16 *
0x1800bd1eb  mov     rcx, [rsp+858h+pSid]; pSid
0x1800bd1f0  call    ?GetTextSid@@YAJPEAXPEAGK@Z; GetTextSid(void *,ushort *,ulong)
0x1800bd1f5  lea     rdx, [rsp+858h+pszPassword]; unsigned __int16 *
0x1800bd1fd  mov     rcx, [rsp+858h+pSid]; void *
0x1800bd202  call    ?GetSIDUserName@@YAJPEAXPEAGK@Z; GetSIDUserName(void *,ushort *,ulong)
0x1800bd207  lea     rax, [rsp+858h+var_800]
0x1800bd20c  mov     qword ptr [rsp+858h+var_7F0], rax
0x1800bd211  lea     rax, [rsp+858h+var_808]
0x1800bd216  mov     qword ptr [rsp+858h+var_7F0+8], rax
0x1800bd21b  xorps   xmm0, xmm0
0x1800bd21e  movdqu  [rsp+858h+var_7E0], xmm0
0x1800bd224  mov     ecx, 5DCh
0x1800bd229  jmp     loc_1800BD321
0x1800bd22e  cmp     ecx, 80070005h
0x1800bd234  jz      short loc_1800BD289
0x1800bd236  cmp     ecx, 8009030Ch
0x1800bd23c  jz      short loc_1800BD289
0x1800bd23e  xorps   xmm0, xmm0
0x1800bd241  lea     rdx, [rsp+858h+var_7F0]
0x1800bd246  cmp     ecx, 80098030h
0x1800bd24c  jnz     short loc_1800BD267
0x1800bd24e  movdqu  [rsp+858h+var_7F0], xmm0
0x1800bd254  xorps   xmm1, xmm1
0x1800bd257  movdqu  [rsp+858h+var_7E0], xmm1
0x1800bd25d  mov     ecx, 5DEh
0x1800bd262  jmp     loc_1800BD326
0x1800bd267  lea     rax, [rsp+858h+var_828]
0x1800bd26c  mov     qword ptr [rsp+858h+var_7F0], rax
0x1800bd271  movdqu  [rsp+858h+var_7F0+8], xmm0
0x1800bd277  mov     qword ptr [rsp+858h+var_7E0+8], rdi
0x1800bd27f  mov     ecx, 5DFh
0x1800bd284  jmp     loc_1800BD326
0x1800bd289  xor     edx, edx; Val
0x1800bd28b  mov     r8d, 100h; Size
0x1800bd291  lea     rcx, [rsp+858h+var_748]; void *
0x1800bd299  call    memset_0
0x1800bd29e  lea     rax, [rsp+858h+var_748]
0x1800bd2a6  mov     [rsp+858h+var_800], rax
0x1800bd2ab  xor     edx, edx; Val
0x1800bd2ad  mov     r8d, 200h; Size
0x1800bd2b3  lea     rcx, [rsp+858h+pszPassword]; void *
0x1800bd2bb  call    memset_0
0x1800bd2c0  lea     rax, [rsp+858h+pszPassword]
0x1800bd2c8  mov     [rsp+858h+var_808], rax
0x1800bd2cd  mov     rcx, [rsp+858h+pSid]; pSid
0x1800bd2d2  test    rcx, rcx
0x1800bd2d5  jz      short loc_1800BD2F6
0x1800bd2d7  lea     rdx, [rsp+858h+var_748]; unsigned __int16 *
0x1800bd2df  call    ?GetTextSid@@YAJPEAXPEAGK@Z; GetTextSid(void *,ushort *,ulong)
0x1800bd2e4  lea     rdx, [rsp+858h+pszPassword]; unsigned __int16 *
0x1800bd2ec  mov     rcx, [rsp+858h+pSid]; void *
0x1800bd2f1  call    ?GetSIDUserName@@YAJPEAXPEAGK@Z; GetSIDUserName(void *,ushort *,ulong)
0x1800bd2f6  lea     rax, [rsp+858h+var_800]
0x1800bd2fb  mov     qword ptr [rsp+858h+var_7F0], rax
0x1800bd300  lea     rax, [rsp+858h+var_808]
0x1800bd305  mov     qword ptr [rsp+858h+var_7F0+8], rax
0x1800bd30a  lea     rax, [rsp+858h+var_828]
0x1800bd30f  mov     qword ptr [rsp+858h+var_7E0], rax
0x1800bd314  mov     qword ptr [rsp+858h+var_7E0+8], rdi
0x1800bd31c  mov     ecx, 5DDh
0x1800bd321  lea     rdx, [rsp+858h+var_7F0]
0x1800bd326  call    ?_LogEvent@@YAJKPEAPEAXKW4WBioEventLevel@@@Z; _LogEvent(ulong,void * *,ulong,WBioEventLevel)
0x1800bd32b  test    ebx, ebx
0x1800bd32d  jnz     short loc_1800BD335
0x1800bd32f  call    cs:__imp_RpcRevertToSelf
0x1800bd335  mov     ebx, [rsp+858h+var_828]
0x1800bd339  lea     rcx, [rsp+858h+var_7B0]
0x1800bd341  call    ?_Tidy@?$vector@V?$shared_ptr@UKeyEnumInfo@@@std@@V?$allocator@V?$shared_ptr@UKeyEnumInfo@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<KeyEnumInfo>>::_Tidy(void)
0x1800bd346  nop
0x1800bd347  lea     rcx, [rsp+858h+var_788]
0x1800bd34f  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800bd354  nop
  ... truncated ...
```
