# ComputeService::Storage::OpenVsmbRootShare(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,void *,Schema::VirtualMachines::Resources::Storage::VirtualSmbShareOptions const &,Schema::Common::Resources::CacheMode,void *)

- ea: `0x140044280`
- end: `0x1400446c7`
- name: `?OpenVsmbRootShare@Storage@ComputeService@@YA?AV?$unique_any_t@V?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAXAEBUVirtualSmbShareOptions@1Resources@VirtualMachines@Schema@@W4CacheMode@8Common@Schema@@1@Z`
- size: `1095`
- prototype: ``
- caller_count: `12`
- callee_count: `20`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1400250ac`
- `0x140098ed0`
- `0x14009baf0`
- `0x1400aa668`
- `0x1400b55dc`
- `0x14012cea0`
- `0x140130c54`
- `0x14019b2cc`
- `0x14019b3b8`
- `0x14019b4a4`
- `0x14019b590`
- `0x140287cc0`

## callees

- `0x140017040`
- `0x140017840`
- `0x140018d54`
- `0x14001d4d0`
- `0x140024030`
- `0x140042468`
- `0x140044280`
- `0x140044974`
- `0x140080180`
- `0x14009d7f0`
- `0x1400a4e28`
- `0x1400a4ed0`
- `0x1400ee910`
- `0x1401050dc`
- `0x140106fa4`
- `0x14012d504`
- `0x1401332f0`
- `0x140142dac`
- `0x140232f58`
- `0x140233160`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140044497`
- `api-ms-win-security-base-l1-1-0!DuplicateTokenEx` at `0x140044497`
- `ntdll!RtlReleasePrivilege` at `0x140044686`
- `ntdll!RtlReleasePrivilege` at `0x140044686`
- `ntdll!RtlAcquirePrivilege` at `0x140044414`
- `ntdll!RtlAcquirePrivilege` at `0x140044414`
- `ntdll!NtDeviceIoControlFile` at `0x140044626`
- `ntdll!NtDeviceIoControlFile` at `0x140044626`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004453f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14004453f`

## string_xrefs

- `0x14004442b`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x1400444ab`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x140044570`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x14004463d`: `onecore\vm\compute\shared\storage\storageutilities.cpp`
- `0x14004465c`: `onecore\vm\compute\shared\storage\storageutilities.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
_QWORD *__fastcall ComputeService::Storage::OpenVsmbRootShare(
        _QWORD *a1,
        const wchar_t *a2,
        __int64 a3,
        _BYTE *a4,
        int a5,
        HANDLE hExistingToken)
{
  HANDLE v9; // r15
  __int64 v10; // rdx
  const wchar_t *v11; // rcx
  void *v12; // rax
  void *v13; // rax
  void *v14; // rax
  DWORD v15; // edi
  int v16; // esi
  NTSTATUS v17; // eax
  __int64 v18; // rbx
  void **phNewToken; // rax
  const char *v20; // r9
  __int64 *v21; // r15
  const WCHAR *v22; // rcx
  const char *v23; // r9
  HANDLE FileW; // r10
  int v25; // ecx
  int v26; // eax
  NTSTATUS v27; // eax
  void *v28; // rdx
  int TokenType; // [rsp+20h] [rbp-E0h]
  int TokenTypea; // [rsp+20h] [rbp-E0h]
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+60h] [rbp-A0h]
  _BYTE v34[8]; // [rsp+68h] [rbp-98h] BYREF
  _OWORD Src[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v36[32]; // [rsp+90h] [rbp-70h] BYREF
  _QWORD *v37; // [rsp+B0h] [rbp-50h]
  __int128 InputBuffer; // [rsp+B8h] [rbp-48h] BYREF
  ULONG Privilege[2]; // [rsp+C8h] [rbp-38h] BYREF
  PVOID ReturnedState; // [rsp+D0h] [rbp-30h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+D8h] [rbp-28h] BYREF
  __int128 v42; // [rsp+E8h] [rbp-18h]
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+F8h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  v33 = a3;
  v37 = a1;
  v9 = hExistingToken;
  *(_OWORD *)lpFileName = 0;
  v42 = 0;
  std::wstring::_Construct_empty(lpFileName);
  if ( *(_QWORD *)(v10 + 24) <= 7u )
    v11 = a2;
  else
    v11 = *(const wchar_t **)v10;
  if ( *(_QWORD *)(v10 + 16) == 3 && !wmemcmp(v11, L"\\\\?", 3u) )
  {
    memset(Src, 0, sizeof(Src));
    std::wstring::_Construct<1,unsigned short const *>(Src, L"\\??");
    v12 = (void *)std::wstring::_Insert<unsigned short>(Src);
    std::wstring::wstring(v36, v12);
    std::wstring::operator=(lpFileName, v36);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v36);
  }
  else
  {
    if ( *((_QWORD *)a2 + 3) > 7u )
      a2 = *(const wchar_t **)a2;
    v13 = (void *)Vml::DosToNtPath(Src, a2);
    v14 = (void *)std::wstring::_Insert<unsigned short>(v13);
    std::wstring::wstring(v36, v14);
    std::wstring::operator=(lpFileName, v36);
    Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)v36);
  }
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)Src);
  v15 = *a4 != 0 ? 4 : 0;
  ReturnedState = 0;
  v16 = 1;
  if ( a4[4] )
  {
    Privilege[0] = 17;
    ReturnedState = 0;
    v17 = RtlAcquirePrivilege(Privilege, 1u, 0, &ReturnedState);
    if ( v17 < 0 )
      wil::details::in1diag3::Throw_NtStatus(
        retaddr,
        (void *)0x527,
        (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
        (const char *)(unsigned int)v17,
        TokenType);
    v15 |= 1u;
  }
  v18 = -1;
  v32 = -1;
  if ( a4[5] )
  {
    *(_QWORD *)Privilege = 0;
    if ( (unsigned int)wil::details::GetTokenInfoWrap<enum _TOKEN_TYPE,wil::err_exception_policy,0>(hExistingToken) == 1
      || (int)wil::details::GetTokenInfoWrap<enum _SECURITY_IMPERSONATION_LEVEL,wil::err_exception_policy,0>(hExistingToken) < 2 )
    {
      phNewToken = (void **)wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>::put(Privilege);
      if ( !DuplicateTokenEx(hExistingToken, 0xCu, 0, SecurityImpersonation, TokenImpersonation, phNewToken) )
        wil::details::in1diag3::Throw_GetLastError(
          retaddr,
          (void *)0x538,
          (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
          v20);
      v9 = *(HANDLE *)Privilege;
    }
    v21 = (__int64 *)wil::impersonate_token(v34, v9);
    if ( &v32 != v21 )
    {
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(
        &v32,
        *v21);
      *v21 = -1;
      v18 = v32;
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(v34);
    v15 |= 2u;
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(Privilege);
  }
  *a1 = 0;
  v22 = (const WCHAR *)lpFileName;
  if ( *((_QWORD *)&v42 + 1) > 7u )
    v22 = lpFileName[0];
  FileW = CreateFileW(v22, v15, 3u, 0, 3u, 0x42000010u, 0);
  *a1 = FileW;
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x54F,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      v23);
  InputBuffer = 0;
  LODWORD(InputBuffer) = 2;
  if ( a5 == 4 )
  {
    DWORD1(InputBuffer) = 1;
  }
  else
  {
    v16 = 0;
    if ( a5 != 3 )
      goto LABEL_32;
    DWORD1(InputBuffer) = 3;
    v16 = 3;
  }
  *((_QWORD *)&InputBuffer + 1) = v33;
LABEL_32:
  v25 = v16 | 8;
  if ( a4[13] )
    DWORD1(InputBuffer) = v16 | 8;
  else
    v25 = v16;
  v26 = v25 | 4;
  if ( a4[17] )
    DWORD1(InputBuffer) = v25 | 4;
  else
    v26 = v25;
  if ( a4[22] )
    DWORD1(InputBuffer) = v26 | 0x10;
  IoStatusBlock = 0;
  v27 = NtDeviceIoControlFile(FileW, 0, 0, 0, &IoStatusBlock, 0x240328u, &InputBuffer, 0x10u, 0, 0);
  if ( v27 < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x583,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      (const char *)(unsigned int)v27,
      TokenTypea);
  if ( IoStatusBlock.Status < 0 )
    wil::details::in1diag3::Throw_NtStatus(
      retaddr,
      (void *)0x584,
      (unsigned int)"onecore\\vm\\compute\\shared\\storage\\storageutilities.cpp",
      (const char *)(unsigned int)IoStatusBlock.Status,
      TokenTypea);
  if ( v18 != -1 )
    wil::details::RevertImpersonateToken((HANDLE)v18, v28);
  if ( ReturnedState )
    RtlReleasePrivilege(ReturnedState);
  Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump((Schema::Responses::System::CrashReportProcessDump *)lpFileName);
  return a1;
}

```

## disassembly

```asm
0x140044280  mov     [rsp-8+arg_18], rbx
0x140044285  push    rbp
0x140044286  push    rsi
0x140044287  push    rdi
0x140044288  push    r12
0x14004428a  push    r13
0x14004428c  push    r14
0x14004428e  push    r15
0x140044290  lea     rbp, [rsp-10h]
0x140044295  sub     rsp, 110h
0x14004429c  mov     rax, cs:__security_cookie
0x1400442a3  xor     rax, rsp
0x1400442a6  mov     [rbp+40h+var_38], rax
0x1400442aa  mov     r14, r9
0x1400442ad  mov     [rsp+140h+var_E0], r8
0x1400442b2  mov     rbx, rdx
0x1400442b5  mov     r12, rcx
0x1400442b8  mov     [rbp+40h+var_90], rcx
0x1400442bc  mov     r15, [rbp+40h+hExistingToken]
0x1400442c0  mov     [rsp+140h+var_F0], 0
0x1400442c8  xorps   xmm0, xmm0
0x1400442cb  movups  xmmword ptr [rbp+40h+lpFileName], xmm0
0x1400442cf  xorps   xmm1, xmm1
0x1400442d2  movdqu  [rbp+40h+var_58], xmm1
0x1400442d7  lea     rcx, [rbp+40h+lpFileName]
0x1400442db  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x1400442e0  nop
0x1400442e1  cmp     qword ptr [rdx+18h], 7
0x1400442e6  jbe     short loc_1400442ED
0x1400442e8  mov     rcx, [rdx]
0x1400442eb  jmp     short loc_1400442F0
0x1400442ed  mov     rcx, rbx; S1
0x1400442f0  mov     r8d, 3; N
0x1400442f6  cmp     [rdx+10h], r8
0x1400442fa  jnz     short loc_140044375
0x1400442fc  lea     rdx, S2; "\\\\?"
0x140044303  call    wmemcmp
0x140044308  test    eax, eax
0x14004430a  jnz     short loc_140044375
0x14004430c  xorps   xmm0, xmm0
0x14004430f  movups  [rsp+140h+Src], xmm0
0x140044314  xorps   xmm1, xmm1
0x140044317  movdqu  [rbp+40h+var_C0], xmm1
0x14004431c  lea     rdx, asc_140326EF8; "\\??"
0x140044323  lea     rcx, [rsp+140h+Src]
0x140044328  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x14004432d  nop
0x14004432e  mov     r9d, 11h
0x140044334  lea     r8, aStorvspVsmb; "\\\\.\\STORVSP\\VSMB\\"
0x14004433b  lea     rcx, [rsp+140h+Src]; Src
0x140044340  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x140044345  mov     rdx, rax; void *
0x140044348  lea     rcx, [rbp+40h+var_B0]; void *
0x14004434c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x140044351  mov     r13d, 2
0x140044357  mov     [rsp+140h+var_F0], r13d
0x14004435c  lea     rdx, [rbp+40h+var_B0]
0x140044360  lea     rcx, [rbp+40h+lpFileName]
0x140044364  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x140044369  lea     rcx, [rbp+40h+var_B0]; this
0x14004436d  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x140044372  nop
0x140044373  jmp     short loc_1400443D0
0x140044375  cmp     qword ptr [rbx+18h], 7
0x14004437a  jbe     short loc_14004437F
0x14004437c  mov     rbx, [rbx]
0x14004437f  mov     rdx, rbx
0x140044382  lea     rcx, [rsp+140h+Src]
0x140044387  call    ?DosToNtPath@Vml@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; Vml::DosToNtPath(ushort const *)
0x14004438c  nop
0x14004438d  mov     r9d, 11h
0x140044393  lea     r8, aStorvspVsmb; "\\\\.\\STORVSP\\VSMB\\"
0x14004439a  mov     rcx, rax; Src
0x14004439d  call    ??$_Insert@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KQEBG0@Z; std::wstring::_Insert<ushort>(unsigned __int64,ushort const * const,unsigned __int64)
0x1400443a2  mov     rdx, rax; void *
0x1400443a5  lea     rcx, [rbp+40h+var_B0]; void *
0x1400443a9  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x1400443ae  mov     r13d, 4
0x1400443b4  mov     [rsp+140h+var_F0], r13d
0x1400443b9  lea     rdx, [rbp+40h+var_B0]
0x1400443bd  lea     rcx, [rbp+40h+lpFileName]
0x1400443c1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1400443c6  lea     rcx, [rbp+40h+var_B0]; this
0x1400443ca  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400443cf  nop
0x1400443d0  lea     rcx, [rsp+140h+Src]; this
0x1400443d5  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x1400443da  mov     al, [r14]
0x1400443dd  neg     al
0x1400443df  sbb     edi, edi
0x1400443e1  and     edi, 4
0x1400443e4  mov     [rbp+40h+ReturnedState], 0
0x1400443ec  mov     esi, 1
0x1400443f1  cmp     byte ptr [r14+4], 0
0x1400443f6  jz      short loc_14004443F
0x1400443f8  mov     [rbp+40h+Privilege], 11h
0x1400443ff  mov     [rbp+40h+ReturnedState], 0
0x140044407  lea     r9, [rbp+40h+ReturnedState]; ReturnedState
0x14004440b  xor     r8d, r8d; Flags
0x14004440e  mov     edx, esi; NumPriv
0x140044410  lea     rcx, [rbp+40h+Privilege]; Privilege
0x140044414  call    cs:__imp_RtlAcquirePrivilege
0x14004441b  nop     dword ptr [rax+rax+00h]
0x140044420  mov     rcx, [rbp+48h]; this
0x140044424  test    eax, eax
0x140044426  jns     short loc_14004443D
0x140044428  mov     r9d, eax; char *
0x14004442b  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140044432  mov     edx, 527h; void *
0x140044437  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14004443d  or      edi, esi
0x14004443f  or      rbx, 0FFFFFFFFFFFFFFFFh
0x140044443  mov     [rsp+140h+var_E8], rbx
0x140044448  cmp     byte ptr [r14+5], 0
0x14004444d  jz      loc_14004450A
0x140044453  mov     qword ptr [rbp+40h+Privilege], 0
0x14004445b  mov     rcx, r15
0x14004445e  call    ??$GetTokenInfoWrap@W4_TOKEN_TYPE@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AW4_TOKEN_TYPE@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_TYPE,wil::err_exception_policy,0>(void *)
0x140044463  cmp     eax, esi
0x140044465  jz      short loc_140044474
0x140044467  mov     rcx, r15
0x14004446a  call    ??$GetTokenInfoWrap@W4_SECURITY_IMPERSONATION_LEVEL@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AW4_SECURITY_IMPERSONATION_LEVEL@@PEAX@Z; wil::details::GetTokenInfoWrap<_SECURITY_IMPERSONATION_LEVEL,wil::err_exception_policy,0>(void *)
0x14004446f  cmp     eax, 2
0x140044472  jge     short loc_1400444C1
0x140044474  lea     rcx, [rbp+40h+Privilege]
0x140044478  call    ?put@?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@QEAAPEAPEAXXZ; wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>::put(void)
0x14004447d  mov     [rsp+140h+phNewToken], rax; phNewToken
0x140044482  mov     eax, 2
0x140044487  mov     [rsp+140h+TokenType], eax; TokenType
0x14004448b  mov     r9d, eax; ImpersonationLevel
0x14004448e  xor     r8d, r8d; lpTokenAttributes
0x140044491  lea     edx, [rax+0Ah]; dwDesiredAccess
0x140044494  mov     rcx, r15; hExistingToken
0x140044497  call    cs:__imp_DuplicateTokenEx
0x14004449e  nop     dword ptr [rax+rax+00h]
0x1400444a3  mov     rcx, [rbp+48h]; this
0x1400444a7  test    eax, eax
0x1400444a9  jnz     short loc_1400444BD
0x1400444ab  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x1400444b2  mov     edx, 538h; void *
0x1400444b7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1400444bd  mov     r15, qword ptr [rbp+40h+Privilege]
0x1400444c1  mov     rdx, r15
0x1400444c4  lea     rcx, [rsp+140h+var_D8]
0x1400444c9  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x1400444ce  mov     r15, rax
0x1400444d1  lea     rax, [rsp+140h+var_E8]
0x1400444d6  cmp     rax, r15
0x1400444d9  jz      short loc_1400444F4
0x1400444db  mov     rdx, [r15]
0x1400444de  lea     rcx, [rsp+140h+var_E8]
0x1400444e3  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::reset(void *)
0x1400444e8  mov     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1400444ef  mov     rbx, [rsp+140h+var_E8]
0x1400444f4  lea     rcx, [rsp+140h+var_D8]
0x1400444f9  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x1400444fe  or      edi, 2
0x140044501  lea     rcx, [rbp+40h+Privilege]; void *
0x140044505  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x14004450a  xor     eax, eax
0x14004450c  mov     [r12], rax
0x140044510  lea     rcx, [rbp+40h+lpFileName]
0x140044514  cmp     qword ptr [rbp+40h+var_58+8], 7
0x140044519  cmova   rcx, [rbp+40h+lpFileName]; lpFileName
0x14004451e  xor     r15d, r15d
0x140044521  mov     [rsp+140h+hTemplateFile], r15; hTemplateFile
0x140044526  mov     dword ptr [rsp+140h+phNewToken], 42000010h; dwFlagsAndAttributes
0x14004452e  mov     [rsp+140h+TokenType], 3; dwCreationDisposition
0x140044536  xor     r9d, r9d; lpSecurityAttributes
0x140044539  lea     r8d, [rax+3]; dwShareMode
0x14004453d  mov     edx, edi; dwDesiredAccess
0x14004453f  call    cs:__imp_CreateFileW
0x140044546  nop     dword ptr [rax+rax+00h]
0x14004454b  mov     r10, rax
0x14004454e  mov     [r12], rax
0x140044552  or      r13d, esi
0x140044555  mov     [rsp+140h+var_F0], r13d
0x14004455a  lea     rcx, [rax+1]
0x14004455e  test    rcx, 0FFFFFFFFFFFFFFFEh
0x140044565  setz    dl
0x140044568  mov     rcx, [rbp+48h]; this
0x14004456c  test    dl, dl
0x14004456e  jz      short loc_140044582
0x140044570  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140044577  mov     edx, 54Fh; void *
0x14004457c  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x140044582  xorps   xmm0, xmm0
0x140044585  movups  [rbp+40h+InputBuffer], xmm0
0x140044589  mov     dword ptr [rbp+40h+InputBuffer], 2
0x140044590  cmp     [rbp+40h+arg_20], 4
0x140044594  jnz     short loc_14004459B
0x140044596  mov     dword ptr [rbp+40h+InputBuffer+4], esi
0x140044599  jmp     short loc_1400445B0
0x14004459b  mov     esi, r15d
0x14004459e  cmp     [rbp+40h+arg_20], 3
0x1400445a2  jnz     short loc_1400445B9
0x1400445a4  mov     dword ptr [rbp+40h+InputBuffer+4], 3
0x1400445ab  mov     esi, 3
0x1400445b0  mov     rax, [rsp+140h+var_E0]
0x1400445b5  mov     qword ptr [rbp+40h+InputBuffer+8], rax
0x1400445b9  mov     al, [r14+0Dh]
0x1400445bd  mov     ecx, esi
0x1400445bf  or      ecx, 8
0x1400445c2  test    al, al
0x1400445c4  jz      short loc_1400445C9
0x1400445c6  mov     dword ptr [rbp+40h+InputBuffer+4], ecx
0x1400445c9  cmovz   ecx, esi
0x1400445cc  mov     dl, [r14+11h]
0x1400445d0  mov     eax, ecx
0x1400445d2  or      eax, 4
0x1400445d5  test    dl, dl
0x1400445d7  jz      short loc_1400445DC
0x1400445d9  mov     dword ptr [rbp+40h+InputBuffer+4], eax
0x1400445dc  cmovz   eax, ecx
0x1400445df  cmp     [r14+16h], r15b
0x1400445e3  jz      short loc_1400445EB
0x1400445e5  or      eax, 10h
0x1400445e8  mov     dword ptr [rbp+40h+InputBuffer+4], eax
0x1400445eb  movups  xmmword ptr [rbp+40h+IoStatusBlock], xmm0
0x1400445ef  mov     [rsp+140h+OutputBufferLength], r15d; OutputBufferLength
0x1400445f4  mov     [rsp+140h+OutputBuffer], r15; OutputBuffer
0x1400445f9  mov     [rsp+140h+InputBufferLength], 10h; InputBufferLength
0x140044601  lea     rax, [rbp+40h+InputBuffer]
0x140044605  mov     [rsp+140h+hTemplateFile], rax; InputBuffer
0x14004460a  mov     dword ptr [rsp+140h+phNewToken], 240328h; IoControlCode
0x140044612  lea     rax, [rbp+40h+IoStatusBlock]
0x140044616  mov     qword ptr [rsp+140h+TokenType], rax; int
0x14004461b  xor     r9d, r9d; ApcContext
0x14004461e  xor     r8d, r8d; ApcRoutine
0x140044621  xor     edx, edx; Event
0x140044623  mov     rcx, r10; FileHandle
0x140044626  call    cs:__imp_NtDeviceIoControlFile
0x14004462d  nop     dword ptr [rax+rax+00h]
0x140044632  mov     rcx, [rbp+48h]; this
0x140044636  test    eax, eax
0x140044638  jns     short loc_14004464F
0x14004463a  mov     r9d, eax; char *
0x14004463d  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140044644  mov     edx, 583h; void *
0x140044649  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14004464f  mov     r9d, dword ptr [rbp+40h+IoStatusBlock]; char *
0x140044653  mov     rcx, [rbp+48h]; this
0x140044657  test    r9d, r9d
0x14004465a  jns     short loc_14004466E
0x14004465c  lea     r8, aOnecoreVmCompu_46; "onecore\\vm\\compute\\shared\\storage\\"...
0x140044663  mov     edx, 584h; void *
0x140044668  call    ?Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_NtStatus(void *,uint,char const *,long)
0x14004466e  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x140044672  jz      short loc_14004467D
0x140044674  mov     rcx, rbx; hObject
0x140044677  call    ?RevertImpersonateToken@details@wil@@YAXPEAX@Z; wil::details::RevertImpersonateToken(void *)
0x14004467c  nop
0x14004467d  mov     rcx, [rbp+40h+ReturnedState]; ReturnedState
0x140044681  test    rcx, rcx
0x140044684  jz      short loc_140044693
0x140044686  call    cs:__imp_RtlReleasePrivilege
0x14004468d  nop     dword ptr [rax+rax+00h]
0x140044692  nop
0x140044693  lea     rcx, [rbp+40h+lpFileName]; this
0x140044697  call    ??1CrashReportProcessDump@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReportProcessDump::~CrashReportProcessDump(void)
0x14004469c  mov     rax, r12
0x14004469f  mov     rcx, [rbp+40h+var_38]
0x1400446a3  xor     rcx, rsp; StackCookie
0x1400446a6  call    __security_check_cookie
0x1400446ab  mov     rbx, [rsp+140h+arg_18]
0x1400446b3  add     rsp, 110h
0x1400446ba  pop     r15
0x1400446bc  pop     r14
0x1400446be  pop     r13
0x1400446c0  pop     r12
0x1400446c2  pop     rdi
0x1400446c3  pop     rsi
0x1400446c4  pop     rbp
0x1400446c5  retn
```
