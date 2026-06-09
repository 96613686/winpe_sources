# CapabilityHelper::CreateSecurityAttributesForUWPCapability_0

- ea: `0x180276270`
- end: `0x18027679d`
- name: `CapabilityHelper::CreateSecurityAttributesForUWPCapability_0`
- size: `1325`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180649a7c`

## callees

- `0x180051b40`
- `0x18007f488`
- `0x1800c7a60`
- `0x1800c7bc0`
- `0x1800c7c34`
- `0x18027624c`
- `0x180276270`
- `0x1802767a4`
- `0x1802767c8`
- `0x180277a9c`
- `0x180303644`
- `0x180356360`
- `0x180356754`
- `0x1804ae288`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802764d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180276511`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802764d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180276511`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802764f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1802764f0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802764b8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1802764b8`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802764cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x1802764cd`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180276503`
- `api-ms-win-core-processthreads-l1-1-0!OpenProcessToken` at `0x180276503`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18027632b`
- `ntdll!RtlDeriveCapabilitySidsFromName` at `0x18027632b`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18027670d`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18027670d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180276373`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180276583`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180276373`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180276583`

## string_xrefs

- `0x18027630c`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027633f`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x180276384`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x1802763c3`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x1802763f6`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x180276427`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027645a`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027648d`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x180276531`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x180276594`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x1802765cd`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027662a`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027665d`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x180276690`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x1802766c3`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`
- `0x18027671e`: `shellcommon\internal\shell\inc\private\CapabilityHelper.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CapabilityHelper::CreateSecurityAttributesForUWPCapability_0(__int64 a1)
{
  __int64 v2; // rdx
  const wchar_t *v3; // rax
  const char *v4; // r9
  int v5; // eax
  const char *v6; // r9
  int v7; // eax
  int v8; // eax
  int v9; // eax
  int v10; // eax
  int v11; // eax
  HANDLE CurrentThread; // rax
  signed int LastError; // eax
  HANDLE CurrentProcess; // rax
  const char *v15; // r9
  int v16; // eax
  void *v17; // rcx
  int v18; // eax
  int v19; // eax
  int v20; // eax
  int v21; // eax
  const char *v22; // r9
  __int64 v23; // rdx
  int v25[2]; // [rsp+20h] [rbp-E0h] BYREF
  LPWSTR StringSid; // [rsp+28h] [rbp-D8h] BYREF
  char v27; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v28; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int16 *v29; // [rsp+40h] [rbp-C0h] BYREF
  void *Block; // [rsp+48h] [rbp-B8h] BYREF
  int v31[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v32; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v33; // [rsp+60h] [rbp-A0h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int128 v35; // [rsp+78h] [rbp-88h] BYREF
  _BYTE Sid[48]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v37[48]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR StringSecurityDescriptor[1024]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+928h] [rbp+828h]

  v28 = (unsigned __int16 *)a1;
  v35 = 0;
  v2 = 0x7FFF;
  v3 = L"shellExperience";
  do
  {
    if ( !*v3 )
      break;
    ++v3;
    --v2;
  }
  while ( v2 );
  v4 = v2 == 0 ? (const char *)0xC000000DLL : 0LL;
  if ( !v2 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x15,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      v4,
      v25[0]);
  LOWORD(v35) = -2 - 2 * v2;
  WORD1(v35) = -2 * v2;
  *((_QWORD *)&v35 + 1) = L"shellExperience";
  v5 = RtlDeriveCapabilitySidsFromName(&v35, v37, Sid, v4);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_NtStatus(
      retaddr,
      (void *)0x1E,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v5,
      v25[0]);
  v28 = 0;
  *(_QWORD *)v25 = &v28;
  StringSid = 0;
  v27 = 1;
  if ( !ConvertSidToStringSidW(Sid, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x22,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      v6);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v25);
  v7 = StringCchCopyW(StringSecurityDescriptor, 0x400u, L"D:AI");
  if ( v7 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x26,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v7,
      v25[0]);
  v8 = StringCchCatW(StringSecurityDescriptor, 0x400u, L"(A;CI;KA;;;");
  if ( v8 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x28,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v8,
      v25[0]);
  v9 = StringCchCatW(StringSecurityDescriptor, 0x400u, v28);
  if ( v9 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2A,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v9,
      v25[0]);
  v10 = StringCchCatW(StringSecurityDescriptor, 0x400u, L")");
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2B,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v10,
      v25[0]);
  v11 = StringCchCatW(StringSecurityDescriptor, 0x400u, L"(A;OICIID;KA;;;");
  if ( v11 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x2E,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v11,
      v25[0]);
  *(_QWORD *)v31 = 0;
  *(_QWORD *)v25 = v31;
  StringSid = 0;
  v27 = 1;
  CurrentThread = GetCurrentThread();
  if ( OpenThreadToken(CurrentThread, 8u, 0, (PHANDLE)&StringSid) )
    goto LABEL_26;
  LastError = GetLastError();
  if ( LastError > 0 )
    LastError = (unsigned __int16)LastError | 0x80070000;
  if ( LastError == -2147023888 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( OpenProcessToken(CurrentProcess, 8u, (PHANDLE)&StringSid) )
    {
LABEL_26:
      LastError = 0;
      goto LABEL_29;
    }
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_29:
  if ( LastError < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x32,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)LastError,
      v25[0]);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(v25);
  wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(&Block, *(_QWORD *)v31);
  v29 = 0;
  *(_QWORD *)v25 = &v29;
  StringSid = 0;
  v27 = 1;
  if ( !ConvertSidToStringSidW(*(PSID *)Block, &StringSid) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x37,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      v15);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(v25);
  v16 = StringCchCatW(StringSecurityDescriptor, 0x400u, v29);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x39,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v16,
      v25[0]);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
  v17 = Block;
  Block = 0;
  if ( v17 )
    operator delete(v17);
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(v31);
  v18 = StringCchCatW(StringSecurityDescriptor, 0x400u, L")");
  if ( v18 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3C,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v18,
      v25[0]);
  v19 = StringCchCatW(StringSecurityDescriptor, 0x400u, L"(A;OICIID;KA;;;SY)");
  if ( v19 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x3F,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v19,
      v25[0]);
  v20 = StringCchCatW(StringSecurityDescriptor, 0x400u, L"(A;OICIID;KA;;;BA)");
  if ( v20 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x40,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v20,
      v25[0]);
  v21 = StringCchCatW(StringSecurityDescriptor, 0x400u, L"(A;OICIID;KR;;;RC)");
  if ( v21 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x41,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      (const char *)(unsigned int)v21,
      v25[0]);
  v32 = 0;
  v33 = 0;
  v34 = 0;
  *(_QWORD *)v25 = &v32;
  StringSid = 0;
  v27 = 1;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
          StringSecurityDescriptor,
          1u,
          (PSECURITY_DESCRIPTOR *)&StringSid,
          0) )
    wil::details::in1diag3::_Throw_GetLastError(
      retaddr,
      (void *)0x44,
      (unsigned int)"shellcommon\\internal\\shell\\inc\\private\\CapabilityHelper.h",
      v22);
  wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(v25);
  LODWORD(v33) = 24;
  v23 = v32;
  *((_QWORD *)&v33 + 1) = v32;
  *(_QWORD *)a1 = v32;
  v32 = 0;
  *(_DWORD *)(a1 + 8) = 24;
  *(_DWORD *)(a1 + 12) = DWORD1(v33);
  *(_QWORD *)(a1 + 16) = v23;
  *(_QWORD *)(a1 + 24) = v34;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v32);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
  return a1;
}

```

## disassembly

```asm
0x180276270  push    rbp
0x180276272  push    rbx
0x180276273  push    rsi
0x180276274  push    rdi
0x180276275  lea     rbp, [rsp-808h]
0x18027627d  sub     rsp, 908h
0x180276284  mov     rax, cs:__security_cookie
0x18027628b  xor     rax, rsp
0x18027628e  mov     [rbp+820h+var_30], rax
0x180276295  mov     rbx, rcx
0x180276298  mov     [rsp+920h+var_8E8], rcx
0x18027629d  xor     edi, edi
0x18027629f  xorps   xmm0, xmm0
0x1802762a2  movups  [rsp+920h+var_8A8], xmm0
0x1802762a7  mov     edx, 7FFFh
0x1802762ac  lea     r10, aShellexperienc_0; "shellExperience"
0x1802762b3  mov     rax, r10
0x1802762b6  lea     r8d, [rdi+2]
0x1802762ba  cmp     [rax], di
0x1802762bd  jz      short loc_1802762C8
0x1802762bf  add     rax, r8
0x1802762c2  sub     rdx, 1
0x1802762c6  jnz     short loc_1802762BA
0x1802762c8  mov     rax, rdx
0x1802762cb  neg     rax
0x1802762ce  sbb     r9d, r9d
0x1802762d1  not     r9d
0x1802762d4  and     r9d, 0C000000Dh; char *
0x1802762db  test    rdx, rdx
0x1802762de  jz      short loc_180276300
0x1802762e0  movzx   eax, dx
0x1802762e3  add     ax, ax
0x1802762e6  mov     ecx, 0FFFEh
0x1802762eb  sub     cx, ax
0x1802762ee  mov     word ptr [rsp+920h+var_8A8], cx
0x1802762f3  add     cx, r8w
0x1802762f7  mov     word ptr [rsp+920h+var_8A8+2], cx
0x1802762fc  mov     qword ptr [rbp+820h+var_8A8+8], r10
0x180276300  mov     rcx, [rbp+828h]; this
0x180276307  test    rdx, rdx
0x18027630a  jnz     short loc_18027631E
0x18027630c  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276313  mov     edx, 15h; void *
0x180276318  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x18027631e  lea     r8, [rbp+820h+Sid]
0x180276322  lea     rdx, [rbp+820h+var_860]
0x180276326  lea     rcx, [rsp+920h+var_8A8]
0x18027632b  call    cs:__imp_RtlDeriveCapabilitySidsFromName
0x180276331  mov     rcx, [rbp+828h]; this
0x180276338  test    eax, eax
0x18027633a  jns     short loc_180276351
0x18027633c  mov     r9d, eax; char *
0x18027633f  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276346  mov     edx, 1Eh; void *
0x18027634b  call    ?_Throw_NtStatus@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_NtStatus(void *,uint,char const *,long)
0x180276351  mov     [rsp+920h+var_8E8], rdi
0x180276356  lea     rax, [rsp+920h+var_8E8]
0x18027635b  mov     qword ptr [rsp+920h+var_900], rax; int
0x180276360  mov     [rsp+920h+StringSid], rdi
0x180276365  mov     [rsp+920h+var_8F0], 1
0x18027636a  lea     rdx, [rsp+920h+StringSid]; StringSid
0x18027636f  lea     rcx, [rbp+820h+Sid]; Sid
0x180276373  call    cs:__imp_ConvertSidToStringSidW
0x180276379  mov     rcx, [rbp+828h]; this
0x180276380  test    eax, eax
0x180276382  jnz     short loc_180276394
0x180276384  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x18027638b  lea     edx, [rax+22h]; void *
0x18027638e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x180276394  lea     rcx, [rsp+920h+var_900]
0x180276399  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18027639e  lea     r8, aDAi; "D:AI"
0x1802763a5  mov     esi, 400h
0x1802763aa  mov     edx, esi; unsigned __int64
0x1802763ac  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x1802763b0  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1802763b5  mov     rcx, [rbp+828h]; this
0x1802763bc  test    eax, eax
0x1802763be  jns     short loc_1802763D5
0x1802763c0  mov     r9d, eax; char *
0x1802763c3  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x1802763ca  mov     edx, 26h ; '&'; void *
0x1802763cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802763d5  lea     r8, aACiKa; "(A;CI;KA;;;"
0x1802763dc  mov     rdx, rsi; unsigned __int64
0x1802763df  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x1802763e3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802763e8  mov     rcx, [rbp+828h]; this
0x1802763ef  test    eax, eax
0x1802763f1  jns     short loc_180276408
0x1802763f3  mov     r9d, eax; char *
0x1802763f6  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x1802763fd  mov     edx, 28h ; '('; void *
0x180276402  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180276408  mov     r8, [rsp+920h+var_8E8]; unsigned __int16 *
0x18027640d  mov     rdx, rsi; unsigned __int64
0x180276410  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x180276414  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180276419  mov     rcx, [rbp+828h]; this
0x180276420  test    eax, eax
0x180276422  jns     short loc_180276439
0x180276424  mov     r9d, eax; char *
0x180276427  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x18027642e  mov     edx, 2Ah ; '*'; void *
0x180276433  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180276439  lea     r8, asc_1807719AC; ")"
0x180276440  mov     rdx, rsi; unsigned __int64
0x180276443  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x180276447  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18027644c  mov     rcx, [rbp+828h]; this
0x180276453  test    eax, eax
0x180276455  jns     short loc_18027646C
0x180276457  mov     r9d, eax; char *
0x18027645a  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276461  mov     edx, 2Bh ; '+'; void *
0x180276466  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18027646c  lea     r8, aAOiciidKa; "(A;OICIID;KA;;;"
0x180276473  mov     rdx, rsi; unsigned __int64
0x180276476  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x18027647a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18027647f  mov     rcx, [rbp+828h]; this
0x180276486  test    eax, eax
0x180276488  jns     short loc_18027649F
0x18027648a  mov     r9d, eax; char *
0x18027648d  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276494  mov     edx, 2Eh ; '.'; void *
0x180276499  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18027649f  mov     qword ptr [rsp+920h+var_8D0], rdi
0x1802764a4  lea     rax, [rsp+920h+var_8D0]
0x1802764a9  mov     qword ptr [rsp+920h+var_900], rax; int
0x1802764ae  mov     [rsp+920h+StringSid], rdi
0x1802764b3  mov     [rsp+920h+var_8F0], 1
0x1802764b8  call    cs:__imp_GetCurrentThread
0x1802764be  mov     rcx, rax; ThreadHandle
0x1802764c1  lea     r9, [rsp+920h+StringSid]; TokenHandle
0x1802764c6  xor     r8d, r8d; OpenAsSelf
0x1802764c9  lea     edx, [r8+8]; DesiredAccess
0x1802764cd  call    cs:__imp_OpenThreadToken
0x1802764d3  test    eax, eax
0x1802764d5  jnz     short loc_18027650D
0x1802764d7  call    cs:__imp_GetLastError
0x1802764dd  test    eax, eax
0x1802764df  jle     short loc_1802764E9
0x1802764e1  movzx   eax, ax
0x1802764e4  or      eax, 80070000h
0x1802764e9  cmp     eax, 800703F0h
0x1802764ee  jnz     short loc_180276523
0x1802764f0  call    cs:__imp_GetCurrentProcess
0x1802764f6  mov     rcx, rax; ProcessHandle
0x1802764f9  lea     r8, [rsp+920h+StringSid]; TokenHandle
0x1802764fe  mov     edx, 8; DesiredAccess
0x180276503  call    cs:__imp_OpenProcessToken
0x180276509  test    eax, eax
0x18027650b  jz      short loc_180276511
0x18027650d  mov     eax, edi
0x18027650f  jmp     short loc_180276523
0x180276511  call    cs:__imp_GetLastError
0x180276517  test    eax, eax
0x180276519  jle     short loc_180276523
0x18027651b  movzx   eax, ax
0x18027651e  or      eax, 80070000h
0x180276523  mov     rcx, [rbp+828h]; this
0x18027652a  test    eax, eax
0x18027652c  jns     short loc_180276543
0x18027652e  mov     r9d, eax; char *
0x180276531  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276538  mov     edx, 32h ; '2'; void *
0x18027653d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180276543  lea     rcx, [rsp+920h+var_900]
0x180276548  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18027654d  mov     rdx, qword ptr [rsp+920h+var_8D0]
0x180276552  lea     rcx, [rsp+920h+Block]
0x180276557  call    ??$GetTokenInfoWrap@U_TOKEN_USER@@Uerr_exception_policy@wil@@$0A@@details@wil@@YA?AV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::details::GetTokenInfoWrap<_TOKEN_USER,wil::err_exception_policy,0>(void *)
0x18027655c  nop
0x18027655d  mov     [rsp+920h+var_8E0], rdi
0x180276562  lea     rax, [rsp+920h+var_8E0]
0x180276567  mov     qword ptr [rsp+920h+var_900], rax; int
0x18027656c  mov     [rsp+920h+StringSid], rdi
0x180276571  mov     [rsp+920h+var_8F0], 1
0x180276576  lea     rdx, [rsp+920h+StringSid]; StringSid
0x18027657b  mov     rcx, [rsp+920h+Block]
0x180276580  mov     rcx, [rcx]; Sid
0x180276583  call    cs:__imp_ConvertSidToStringSidW
0x180276589  test    eax, eax
0x18027658b  jnz     short loc_1802765A4
0x18027658d  mov     rcx, [rbp+828h]; this
0x180276594  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x18027659b  lea     edx, [rax+37h]; void *
0x18027659e  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x1802765a4  lea     rcx, [rsp+920h+var_900]
0x1802765a9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x1802765ae  mov     r8, [rsp+920h+var_8E0]; unsigned __int16 *
0x1802765b3  mov     rdx, rsi; unsigned __int64
0x1802765b6  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x1802765ba  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802765bf  mov     rcx, [rbp+828h]; this
0x1802765c6  test    eax, eax
0x1802765c8  jns     short loc_1802765DF
0x1802765ca  mov     r9d, eax; char *
0x1802765cd  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x1802765d4  mov     edx, 39h ; '9'; void *
0x1802765d9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802765df  lea     rcx, [rsp+920h+var_8E0]
0x1802765e4  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1802765e9  nop
0x1802765ea  mov     rcx, [rsp+920h+Block]; Block
0x1802765ef  mov     [rsp+920h+Block], rdi
0x1802765f4  test    rcx, rcx
0x1802765f7  jz      short loc_1802765FF
0x1802765f9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1802765fe  nop
0x1802765ff  lea     rcx, [rsp+920h+var_8D0]
0x180276604  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180276609  lea     r8, asc_1807719AC; ")"
0x180276610  mov     rdx, rsi; unsigned __int64
0x180276613  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x180276617  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18027661c  mov     rcx, [rbp+828h]; this
0x180276623  test    eax, eax
0x180276625  jns     short loc_18027663C
0x180276627  mov     r9d, eax; char *
0x18027662a  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276631  mov     edx, 3Ch ; '<'; void *
0x180276636  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18027663c  lea     r8, aAOiciidKaSy; "(A;OICIID;KA;;;SY)"
0x180276643  mov     rdx, rsi; unsigned __int64
0x180276646  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x18027664a  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18027664f  mov     rcx, [rbp+828h]; this
0x180276656  test    eax, eax
0x180276658  jns     short loc_18027666F
0x18027665a  mov     r9d, eax; char *
0x18027665d  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276664  mov     edx, 3Fh ; '?'; void *
0x180276669  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18027666f  lea     r8, aAOiciidKaBa; "(A;OICIID;KA;;;BA)"
0x180276676  mov     rdx, rsi; unsigned __int64
0x180276679  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x18027667d  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180276682  mov     rcx, [rbp+828h]; this
0x180276689  test    eax, eax
0x18027668b  jns     short loc_1802766A2
0x18027668d  mov     r9d, eax; char *
0x180276690  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276697  mov     edx, 40h ; '@'; void *
0x18027669c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802766a2  lea     r8, aAOiciidKrRc; "(A;OICIID;KR;;;RC)"
0x1802766a9  mov     rdx, rsi; unsigned __int64
0x1802766ac  lea     rcx, [rbp+820h+StringSecurityDescriptor]; unsigned __int16 *
0x1802766b0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1802766b5  mov     rcx, [rbp+828h]; this
0x1802766bc  test    eax, eax
0x1802766be  jns     short loc_1802766D5
0x1802766c0  mov     r9d, eax; char *
0x1802766c3  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x1802766ca  mov     edx, 41h ; 'A'; void *
0x1802766cf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802766d5  mov     [rsp+920h+var_8C8], rdi
0x1802766da  xorps   xmm0, xmm0
0x1802766dd  xor     eax, eax
0x1802766df  movups  [rsp+920h+var_8C0], xmm0
0x1802766e4  mov     [rsp+920h+var_8B0], rax
0x1802766e9  lea     rax, [rsp+920h+var_8C8]
0x1802766ee  mov     qword ptr [rsp+920h+var_900], rax
0x1802766f3  mov     [rsp+920h+StringSid], rdi
0x1802766f8  mov     [rsp+920h+var_8F0], 1
0x1802766fd  xor     r9d, r9d; SecurityDescriptorSize
0x180276700  lea     r8, [rsp+920h+StringSid]; SecurityDescriptor
0x180276705  lea     edx, [r9+1]; StringSDRevision
0x180276709  lea     rcx, [rbp+820h+StringSecurityDescriptor]; StringSecurityDescriptor
0x18027670d  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180276713  mov     rcx, [rbp+828h]; this
0x18027671a  test    eax, eax
0x18027671c  jnz     short loc_18027672E
0x18027671e  lea     r8, aShellcommonInt_0; "shellcommon\\internal\\shell\\inc\\priv"...
0x180276725  lea     edx, [rax+44h]; void *
0x180276728  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18027672e  lea     rcx, [rsp+920h+var_900]
0x180276733  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180276738  mov     eax, 18h
0x18027673d  mov     dword ptr [rsp+920h+var_8C0], eax
0x180276741  mov     rdx, [rsp+920h+var_8C8]
0x180276746  mov     qword ptr [rsp+920h+var_8C0+8], rdx
0x18027674b  mov     [rbx], rdx
0x18027674e  mov     [rsp+920h+var_8C8], rdi
0x180276753  mov     [rbx+8], eax
0x180276756  mov     ecx, dword ptr [rsp+920h+var_8C0+4]
0x18027675a  mov     [rbx+0Ch], ecx
0x18027675d  mov     [rbx+10h], rdx
0x180276761  mov     rcx, [rsp+920h+var_8B0]
0x180276766  mov     [rbx+18h], rcx
0x18027676a  lea     rcx, [rsp+920h+var_8C8]
0x18027676f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180276774  nop
0x180276775  lea     rcx, [rsp+920h+var_8E8]
0x18027677a  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18027677f  mov     rax, rbx
0x180276782  mov     rcx, [rbp+820h+var_30]
0x180276789  xor     rcx, rsp; StackCookie
0x18027678c  call    __security_check_cookie
  ... truncated ...
```
