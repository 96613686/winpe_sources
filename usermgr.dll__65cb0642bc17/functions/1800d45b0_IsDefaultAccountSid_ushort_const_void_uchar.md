# IsDefaultAccountSid(ushort const *,void *,uchar *)

- ea: `0x1800d45b0`
- end: `0x1800d47d3`
- name: `?IsDefaultAccountSid@@YAJPEBGPEAXPEAE@Z`
- size: `547`
- prototype: `int(const unsigned __int16 *, void *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800d47dc`

## callees

- `0x1800088e8`
- `0x180014e7c`
- `0x180034454`
- `0x1800344b8`
- `0x180061e1c`
- `0x1800c5b04`
- `0x1800d3f1c`
- `0x1800d3f3c`
- `0x1800d45b0`
- `0x1800de450`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d4703`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800d4703`
- `ntdll!RtlEqualSid` at `0x1800d474a`
- `ntdll!RtlEqualSid` at `0x1800d474a`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800d4629`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupOpenLocalPolicy` at `0x1800d4629`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800d46a8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupGetDomainInfo` at `0x1800d46a8`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800d4684`
- `api-ms-win-security-lsalookup-l1-1-0!LsaLookupFreeMemory` at `0x1800d4684`

## string_xrefs

- `0x1800d463a`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x1800d46b9`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x1800d4711`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`
- `0x1800d4784`: `onecore\ds\security\umstartup\aulogon\aulogon.cxx`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall IsDefaultAccountSid(const unsigned __int16 *a1, void *a2, unsigned __int8 *a3)
{
  NTSTATUS v5; // eax
  unsigned int LastError; // ebx
  NTSTATUS DomainInfo; // eax
  const char *v8; // r9
  PVOID Buffer; // [rsp+20h] [rbp-79h] BYREF
  PVOID PolicyHandle; // [rsp+28h] [rbp-71h] BYREF
  __int64 v12; // [rsp+30h] [rbp-69h] BYREF
  DWORD cbSid; // [rsp+38h] [rbp-61h] BYREF
  _BYTE v14[8]; // [rsp+40h] [rbp-59h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-51h] BYREF
  _BYTE pSid[80]; // [rsp+80h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]

  cbSid = 68;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v12 = 0;
  PolicyHandle = 0;
  Buffer = 0;
  if ( !a2 || !a3 )
  {
    LastError = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x126,
      (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
      (const char *)0x80070057LL,
      (int)Buffer);
    wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v12);
    return LastError;
  }
  *a3 = 0;
  v5 = LsaLookupOpenLocalPolicy(&ObjectAttributes, 1u, &PolicyHandle);
  if ( v5 < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x131,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                  (const char *)(unsigned int)v5,
                  (int)Buffer);
    wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v12);
    return LastError;
  }
  if ( Buffer )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)v14);
    LsaLookupFreeMemory(Buffer);
    wil::last_error_context::~last_error_context((wil::last_error_context *)v14);
  }
  Buffer = 0;
  DomainInfo = LsaLookupGetDomainInfo(PolicyHandle, AccountDomainInformation, &Buffer);
  if ( DomainInfo < 0 )
  {
    LastError = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x132,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                  (const char *)(unsigned int)DomainInfo,
                  (int)Buffer);
    wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v12);
    return LastError;
  }
  if ( !CreateWellKnownSid(WinLocalAccountAndAdministratorSid|WinCreatorGroupSid, *((PSID *)Buffer + 2), pSid, &cbSid) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x133,
                  (unsigned int)"onecore\\ds\\security\\umstartup\\aulogon\\aulogon.cxx",
                  v8);
    wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
    wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v12);
    return LastError;
  }
  if ( RtlEqualSid(a2, pSid) )
    *a3 = 1;
  wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&long LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(&Buffer);
  wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&long LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&PolicyHandle);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,long (*)(void *),&long CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&v12);
  return 0;
}

```

## disassembly

```asm
0x1800d45b0  mov     [rsp-8+arg_0], rbx
0x1800d45b5  push    rbp
0x1800d45b6  push    rsi
0x1800d45b7  push    rdi
0x1800d45b8  lea     rbp, [rsp-47h]
0x1800d45bd  sub     rsp, 0E0h
0x1800d45c4  mov     rax, cs:__security_cookie
0x1800d45cb  xor     rax, rsp
0x1800d45ce  mov     [rbp+57h+var_20], rax
0x1800d45d2  mov     rbx, r8
0x1800d45d5  mov     rsi, rdx
0x1800d45d8  mov     [rbp+57h+cbSid], 44h ; 'D'
0x1800d45df  xorps   xmm0, xmm0
0x1800d45e2  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x1800d45e6  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x1800d45ea  movups  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800d45ee  mov     [rbp+57h+var_C0], 0
0x1800d45f6  mov     [rbp+57h+PolicyHandle], 0
0x1800d45fe  mov     [rbp+57h+Buffer], 0
0x1800d4606  test    rdx, rdx
0x1800d4609  jz      loc_1800D4778
0x1800d460f  test    rbx, rbx
0x1800d4612  jz      loc_1800D4778
0x1800d4618  mov     byte ptr [r8], 0
0x1800d461c  lea     r8, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800d4620  mov     edx, 1; AccessMask
0x1800d4625  lea     rcx, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800d4629  call    cs:__imp_LsaLookupOpenLocalPolicy
0x1800d462f  test    eax, eax
0x1800d4631  jns     short loc_1800D466F
0x1800d4633  mov     rcx, [rbp+5Fh]; this
0x1800d4637  mov     r9d, eax; char *
0x1800d463a  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d4641  mov     edx, 131h; void *
0x1800d4646  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d464b  mov     ebx, eax
0x1800d464d  lea     rcx, [rbp+57h+Buffer]
0x1800d4651  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800d4656  lea     rcx, [rbp+57h+PolicyHandle]
0x1800d465a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d465f  nop
0x1800d4660  lea     rcx, [rbp+57h+var_C0]
0x1800d4664  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800d4669  nop
0x1800d466a  jmp     loc_1800D47B2
0x1800d466f  mov     rdi, [rbp+57h+Buffer]
0x1800d4673  test    rdi, rdi
0x1800d4676  jz      short loc_1800D4693
0x1800d4678  lea     rcx, [rbp+57h+var_B0]; this
0x1800d467c  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800d4681  mov     rcx, rdi; Buffer
0x1800d4684  call    cs:__imp_LsaLookupFreeMemory
0x1800d468a  lea     rcx, [rbp+57h+var_B0]; this
0x1800d468e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1800d4693  mov     [rbp+57h+Buffer], 0
0x1800d469b  lea     r8, [rbp+57h+Buffer]; DomainInfo
0x1800d469f  mov     edx, 5; DomainInfoClass
0x1800d46a4  mov     rcx, [rbp+57h+PolicyHandle]; PolicyHandle
0x1800d46a8  call    cs:__imp_LsaLookupGetDomainInfo
0x1800d46ae  test    eax, eax
0x1800d46b0  jns     short loc_1800D46EE
0x1800d46b2  mov     rcx, [rbp+5Fh]; this
0x1800d46b6  mov     r9d, eax; char *
0x1800d46b9  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d46c0  mov     edx, 132h; void *
0x1800d46c5  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800d46ca  mov     ebx, eax
0x1800d46cc  lea     rcx, [rbp+57h+Buffer]
0x1800d46d0  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800d46d5  lea     rcx, [rbp+57h+PolicyHandle]
0x1800d46d9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d46de  nop
0x1800d46df  lea     rcx, [rbp+57h+var_C0]
0x1800d46e3  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800d46e8  nop
0x1800d46e9  jmp     loc_1800D47B2
0x1800d46ee  lea     r9, [rbp+57h+cbSid]; cbSid
0x1800d46f2  lea     r8, [rbp+57h+pSid]; pSid
0x1800d46f6  mov     rdx, [rbp+57h+Buffer]
0x1800d46fa  mov     rdx, [rdx+10h]; DomainSid
0x1800d46fe  mov     ecx, 6Eh ; 'n'; WellKnownSidType
0x1800d4703  call    cs:__imp_CreateWellKnownSid
0x1800d4709  test    eax, eax
0x1800d470b  jnz     short loc_1800D4743
0x1800d470d  mov     rcx, [rbp+5Fh]; this
0x1800d4711  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d4718  mov     edx, 133h; void *
0x1800d471d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800d4722  mov     ebx, eax
0x1800d4724  lea     rcx, [rbp+57h+Buffer]
0x1800d4728  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800d472d  lea     rcx, [rbp+57h+PolicyHandle]
0x1800d4731  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d4736  nop
0x1800d4737  lea     rcx, [rbp+57h+var_C0]
0x1800d473b  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800d4740  nop
0x1800d4741  jmp     short loc_1800D47B2
0x1800d4743  lea     rdx, [rbp+57h+pSid]; Sid2
0x1800d4747  mov     rcx, rsi; Sid1
0x1800d474a  call    cs:__imp_RtlEqualSid
0x1800d4750  test    al, al
0x1800d4752  jz      short loc_1800D4757
0x1800d4754  mov     byte ptr [rbx], 1
0x1800d4757  lea     rcx, [rbp+57h+Buffer]
0x1800d475b  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800d4760  lea     rcx, [rbp+57h+PolicyHandle]
0x1800d4764  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d4769  nop
0x1800d476a  lea     rcx, [rbp+57h+var_C0]
0x1800d476e  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800d4773  nop
0x1800d4774  xor     eax, eax
0x1800d4776  jmp     short loc_1800D47B4
0x1800d4778  mov     rcx, [rbp+5Fh]; this
0x1800d477c  mov     ebx, 80070057h
0x1800d4781  mov     r9d, ebx; char *
0x1800d4784  lea     r8, aOnecoreDsSecur_79; "onecore\\ds\\security\\umstartup\\aulog"...
0x1800d478b  mov     edx, 126h; void *
0x1800d4790  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d4795  lea     rcx, [rbp+57h+Buffer]
0x1800d4799  call    ??1?$unique_storage@U?$resource_policy@PEAU_POLICY_ACCOUNT_DOMAIN_INFO@@P6AJPEAX@Z$1?LsaLookupFreeMemory@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_POLICY_ACCOUNT_DOMAIN_INFO *,long (*)(void *),&LsaLookupFreeMemory(void *),wistd::integral_constant<unsigned __int64,0>,_POLICY_ACCOUNT_DOMAIN_INFO *,_POLICY_ACCOUNT_DOMAIN_INFO *,0,std::nullptr_t>>(void)
0x1800d479e  lea     rcx, [rbp+57h+PolicyHandle]
0x1800d47a2  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AJPEAX@Z$1?LsaLookupClose@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,long (*)(void *),&LsaLookupClose(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800d47a7  nop
0x1800d47a8  lea     rcx, [rbp+57h+var_C0]
0x1800d47ac  call    ??1?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AJPEAX@Z$1?CamFreeBuffer@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAA@XZ; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,long (*)(void *),&CamFreeBuffer(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>(void)
0x1800d47b1  nop
0x1800d47b2  mov     eax, ebx
0x1800d47b4  mov     rcx, [rbp+57h+var_20]
0x1800d47b8  xor     rcx, rsp; StackCookie
0x1800d47bb  call    __security_check_cookie
0x1800d47c0  mov     rbx, [rsp+0F0h+arg_0]
0x1800d47c8  add     rsp, 0E0h
0x1800d47cf  pop     rdi
0x1800d47d0  pop     rsi
0x1800d47d1  pop     rbp
0x1800d47d2  retn
```
