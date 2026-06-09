# LOG_WRITER::CreateLogDirectory(ushort const *,int)

- ea: `0x1800031d0`
- end: `0x180003710`
- name: `?CreateLogDirectory@LOG_WRITER@@AEAAJPEBGH@Z`
- size: `1344`
- prototype: `__int64 __fastcall(LOG_WRITER *this, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180004878`

## callees

- `0x1800031d0`
- `0x18000e97a`
- `0x18000e9a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800036da`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800036cc`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800036cc`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000330d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000331d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000332d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000330d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000331d`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x18000332d`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800032b2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800033f6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000349c`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800032b2`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x1800033f6`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x18000349c`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180003666`
- `api-ms-win-security-base-l1-1-0!InitializeSecurityDescriptor` at `0x180003666`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180003680`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorDacl` at `0x180003680`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800036a8`
- `api-ms-win-security-base-l1-1-0!SetSecurityDescriptorOwner` at `0x1800036a8`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000364a`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000364a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000333c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000334a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000333c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000334a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800032df`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800032df`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800032ef`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800032fe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800032ef`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800032fe`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800035d0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaLookupNames2` at `0x1800035d0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000357a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x18000357a`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180003636`
- `api-ms-win-security-provider-l1-1-0!SetEntriesInAclW` at `0x180003636`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003355`
- `iisutil!??1STRU@@QEAA@XZ` at `0x180003355`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003277`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x180003277`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003451`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003451`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800034e9`
- `iisutil!?Append@STRU@@QEAAJPEBG@Z` at `0x1800034e9`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000351d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000353a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180003559`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000351d`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x18000353a`
- `iisutil!?Append@STRU@@QEAAJPEBGK@Z` at `0x180003559`

## pseudocode

```c
__int64 __fastcall LOG_WRITER::CreateLogDirectory(LOG_WRITER *this, const unsigned __int16 *a2, int a3)
{
  void *v6; // rdi
  signed int LastError; // eax
  signed int v8; // ebx
  ULONG v10; // esi
  PSID v11; // rax
  const unsigned __int16 *v12; // rdx
  HLOCAL v13; // rax
  PSID v14; // rdx
  PVOID Buffer; // [rsp+60h] [rbp-A0h] BYREF
  PSID v16; // [rsp+68h] [rbp-98h] BYREF
  PSID v17; // [rsp+70h] [rbp-90h] BYREF
  LSA_HANDLE ObjectHandle; // [rsp+78h] [rbp-88h] BYREF
  PSID pSid; // [rsp+80h] [rbp-80h] BYREF
  HLOCAL hMem; // [rsp+88h] [rbp-78h] BYREF
  PVOID v21; // [rsp+90h] [rbp-70h] BYREF
  struct _LSA_UNICODE_STRING Names; // [rsp+98h] [rbp-68h] BYREF
  _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+A8h] [rbp-58h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+C0h] [rbp-40h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+F0h] [rbp-10h] BYREF
  _BYTE v26[32]; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR *v27; // [rsp+118h] [rbp+18h]
  int v28; // [rsp+128h] [rbp+28h]
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+130h] [rbp+30h] BYREF
  int v30; // [rsp+160h] [rbp+60h]
  int v31; // [rsp+164h] [rbp+64h]
  int v32; // [rsp+168h] [rbp+68h]
  int v33; // [rsp+17Ch] [rbp+7Ch]
  int v34; // [rsp+180h] [rbp+80h]
  PSID v35; // [rsp+188h] [rbp+88h]
  int v36; // [rsp+190h] [rbp+90h]
  int v37; // [rsp+194h] [rbp+94h]
  int v38; // [rsp+198h] [rbp+98h]
  int v39; // [rsp+1ACh] [rbp+ACh]
  int v40; // [rsp+1B0h] [rbp+B0h]
  PSID v41; // [rsp+1B8h] [rbp+B8h]
  unsigned __int16 v42[128]; // [rsp+1C0h] [rbp+C0h] BYREF

  v16 = 0;
  pSid = 0;
  v17 = 0;
  hMem = 0;
  v6 = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  memset(&SecurityAttributes, 0, sizeof(SecurityAttributes));
  ObjectHandle = 0;
  v21 = 0;
  Buffer = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  memset_0(v42, 0, sizeof(v42));
  STRU::STRU((STRU *)v26, v42, 0x80u);
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSid) )
    goto LABEL_2;
  memset_0(&pListOfExplicitEntries, 0, 0x60u);
  pListOfExplicitEntries.grfAccessPermissions = 0x1FFFFF;
  pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
  v10 = 3;
  pListOfExplicitEntries.grfInheritance = 3;
  pListOfExplicitEntries.Trustee.TrusteeForm = TRUSTEE_IS_SID;
  pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)pSid;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &v16) )
    goto LABEL_2;
  v30 = 0x1FFFFF;
  v31 = 2;
  v32 = 3;
  v33 = 0;
  v34 = 2;
  v35 = v16;
  if ( a3 )
  {
    memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
    v8 = STRU::Copy((STRU *)v26, *((const unsigned __int16 **)g_pLogSvcAdmin + 216));
    if ( v8 < 0 )
      goto LABEL_4;
    if ( !v28 )
    {
      if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 7u, 0, 0, 0, 0, 0, 0, 0, &v17) )
        goto LABEL_2;
      v36 = 0x1FFFFF;
      v37 = 2;
      v38 = 3;
      v39 = 0;
      v40 = 5;
      v11 = v17;
      goto LABEL_40;
    }
    v8 = STRU::Append((STRU *)v26, L"\\");
    if ( v8 < 0 )
      goto LABEL_4;
    v12 = (const unsigned __int16 *)*((_QWORD *)g_pLogSvcAdmin + 227);
    if ( v12 && *v12 )
    {
      v8 = STRU::Append((STRU *)v26, v12, *((_DWORD *)g_pLogSvcAdmin + 458));
      if ( v8 >= 0 )
      {
        v8 = STRU::Append((STRU *)v26, L"$", 1u);
        if ( v8 >= 0 )
        {
LABEL_35:
          if ( LsaOpenPolicy(0, &ObjectAttributes, 0x800u, &ObjectHandle)
            || (Names.Length = 2 * v28,
                Names.MaximumLength = 2 * v28 + 2,
                Names.Buffer = v27,
                LsaLookupNames2(
                  ObjectHandle,
                  0x80000000,
                  1u,
                  &Names,
                  (PLSA_REFERENCED_DOMAIN_LIST *)&v21,
                  (PLSA_TRANSLATED_SID2 *)&Buffer))
            || (unsigned int)(*(_DWORD *)Buffer - 7) <= 1 )
          {
            v8 = -2147467259;
            goto LABEL_4;
          }
          v36 = 0x1FFFFF;
          v37 = 2;
          v38 = 3;
          v39 = 0;
          v40 = 8;
          v11 = (PSID)*((_QWORD *)Buffer + 1);
LABEL_40:
          v41 = v11;
          goto LABEL_42;
        }
      }
    }
    else
    {
      v8 = STRU::Append((STRU *)v26, L"- ", 2u);
    }
    if ( v8 < 0 )
      goto LABEL_4;
    goto LABEL_35;
  }
  v8 = 0;
  v10 = 2;
LABEL_42:
  if ( SetEntriesInAclW(v10, &pListOfExplicitEntries, 0, (PACL *)&hMem)
    || (v13 = LocalAlloc(0x40u, 0x28u), (v6 = v13) == 0)
    || !InitializeSecurityDescriptor(v13, 1u)
    || !SetSecurityDescriptorDacl(v6, 1, (PACL)hMem, 0)
    || (!a3 ? (v14 = v16) : !v28 ? (v14 = v17) : (v14 = (PSID)*((_QWORD *)Buffer + 1)),
        !SetSecurityDescriptorOwner(v6, v14, 0)) )
  {
LABEL_2:
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError <= 0 )
      goto LABEL_4;
    goto LABEL_3;
  }
  SecurityAttributes.nLength = 24;
  SecurityAttributes.lpSecurityDescriptor = v6;
  SecurityAttributes.bInheritHandle = 0;
  if ( !CreateDirectoryW(a2, &SecurityAttributes) )
  {
    LastError = GetLastError();
    if ( LastError != 183 )
    {
      *((_DWORD *)this + 169) = 1;
      if ( LastError <= 0 )
      {
        v8 = LastError;
        goto LABEL_4;
      }
LABEL_3:
      v8 = (unsigned __int16)LastError | 0x80070000;
    }
  }
LABEL_4:
  if ( ObjectHandle )
    LsaClose(ObjectHandle);
  if ( Buffer )
    LsaFreeMemory(Buffer);
  if ( v21 )
    LsaFreeMemory(v21);
  if ( pSid )
    FreeSid(pSid);
  if ( v16 )
    FreeSid(v16);
  if ( v17 )
    FreeSid(v17);
  if ( hMem )
    LocalFree(hMem);
  if ( v6 )
    LocalFree(v6);
  STRU::~STRU((STRU *)v26);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800031d0  mov     [rsp-8+arg_10], rbx
0x1800031d5  push    rbp
0x1800031d6  push    rsi
0x1800031d7  push    rdi
0x1800031d8  push    r12
0x1800031da  push    r13
0x1800031dc  push    r14
0x1800031de  push    r15
0x1800031e0  lea     rbp, [rsp-1D0h]
0x1800031e8  sub     rsp, 2D0h
0x1800031ef  mov     rax, cs:__security_cookie
0x1800031f6  xor     rax, rsp
0x1800031f9  mov     [rbp+200h+var_40], rax
0x180003200  mov     r14d, r8d
0x180003203  mov     r12, rdx
0x180003206  mov     r15, rcx
0x180003209  xor     r13d, r13d
0x18000320c  mov     [rsp+300h+var_298], r13
0x180003211  mov     [rbp+200h+var_280], r13
0x180003215  mov     [rsp+300h+var_290], r13
0x18000321a  mov     [rbp+200h+hMem], r13
0x18000321e  mov     edi, r13d
0x180003221  mov     dword ptr [rbp+200h+pIdentifierAuthority.Value], r13d
0x180003225  mov     word ptr [rbp+200h+pIdentifierAuthority.Value+4], 500h
0x18000322b  xorps   xmm0, xmm0
0x18000322e  xor     eax, eax
0x180003230  movups  xmmword ptr [rbp+200h+SecurityAttributes.nLength], xmm0
0x180003234  mov     qword ptr [rbp+200h+SecurityAttributes.bInheritHandle], rax
0x180003238  mov     [rsp+300h+ObjectHandle], r13
0x18000323d  mov     [rbp+200h+var_270], r13
0x180003241  mov     [rsp+300h+Buffer], r13
0x180003246  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x18000324a  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x18000324e  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x180003252  xor     edx, edx; Val
0x180003254  mov     r8d, 100h; Size
0x18000325a  lea     rcx, [rbp+200h+var_140]; void *
0x180003261  call    memset_0
0x180003266  mov     r8d, 80h
0x18000326c  lea     rdx, [rbp+200h+var_140]
0x180003273  lea     rcx, [rbp+200h+var_208]
0x180003277  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000327d  nop
0x18000327e  lea     rax, [rbp+200h+var_280]
0x180003282  mov     [rsp+300h+pSid], rax; pSid
0x180003287  mov     [rsp+300h+nSubAuthority7], r13d; nSubAuthority7
0x18000328c  mov     [rsp+300h+nSubAuthority6], r13d; nSubAuthority6
0x180003291  mov     [rsp+300h+nSubAuthority5], r13d; nSubAuthority5
0x180003296  mov     [rsp+300h+nSubAuthority4], r13d; nSubAuthority4
0x18000329b  mov     [rsp+300h+nSubAuthority3], r13d; nSubAuthority3
0x1800032a0  mov     [rsp+300h+nSubAuthority2], r13d; nSubAuthority2
0x1800032a5  xor     r9d, r9d; nSubAuthority1
0x1800032a8  lea     r8d, [r13+12h]; nSubAuthority0
0x1800032ac  mov     dl, 1; nSubAuthorityCount
0x1800032ae  lea     rcx, [rbp+200h+pIdentifierAuthority]; pIdentifierAuthority
0x1800032b2  call    cs:__imp_AllocateAndInitializeSid
0x1800032b8  test    eax, eax
0x1800032ba  jnz     loc_180003387
0x1800032c0  call    cs:__imp_GetLastError
0x1800032c6  mov     ebx, eax
0x1800032c8  test    eax, eax
0x1800032ca  jle     short loc_1800032D5
0x1800032cc  movzx   ebx, ax
0x1800032cf  or      ebx, 80070000h
0x1800032d5  mov     rcx, [rsp+300h+ObjectHandle]; ObjectHandle
0x1800032da  test    rcx, rcx
0x1800032dd  jz      short loc_1800032E5
0x1800032df  call    cs:__imp_LsaClose
0x1800032e5  mov     rcx, [rsp+300h+Buffer]; Buffer
0x1800032ea  test    rcx, rcx
0x1800032ed  jz      short loc_1800032F5
0x1800032ef  call    cs:__imp_LsaFreeMemory
0x1800032f5  mov     rcx, [rbp+200h+var_270]; Buffer
0x1800032f9  test    rcx, rcx
0x1800032fc  jz      short loc_180003304
0x1800032fe  call    cs:__imp_LsaFreeMemory
0x180003304  mov     rcx, [rbp+200h+var_280]; pSid
0x180003308  test    rcx, rcx
0x18000330b  jz      short loc_180003313
0x18000330d  call    cs:__imp_FreeSid
0x180003313  mov     rcx, [rsp+300h+var_298]; pSid
0x180003318  test    rcx, rcx
0x18000331b  jz      short loc_180003323
0x18000331d  call    cs:__imp_FreeSid
0x180003323  mov     rcx, [rsp+300h+var_290]; pSid
0x180003328  test    rcx, rcx
0x18000332b  jz      short loc_180003333
0x18000332d  call    cs:__imp_FreeSid
0x180003333  mov     rcx, [rbp+200h+hMem]; hMem
0x180003337  test    rcx, rcx
0x18000333a  jz      short loc_180003342
0x18000333c  call    cs:__imp_LocalFree
0x180003342  test    rdi, rdi
0x180003345  jz      short loc_180003351
0x180003347  mov     rcx, rdi; hMem
0x18000334a  call    cs:__imp_LocalFree
0x180003350  nop
0x180003351  lea     rcx, [rbp+200h+var_208]
0x180003355  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000335b  mov     eax, ebx
0x18000335d  mov     rcx, [rbp+200h+var_40]
0x180003364  xor     rcx, rsp; StackCookie
0x180003367  call    __security_check_cookie
0x18000336c  mov     rbx, [rsp+300h+arg_10]
0x180003374  add     rsp, 2D0h
0x18000337b  pop     r15
0x18000337d  pop     r14
0x18000337f  pop     r13
0x180003381  pop     r12
0x180003383  pop     rdi
0x180003384  pop     rsi
0x180003385  pop     rbp
0x180003386  retn
0x180003387  xor     edx, edx; Val
0x180003389  lea     r8d, [rdx+60h]; Size
0x18000338d  lea     rcx, [rbp+200h+pListOfExplicitEntries]; void *
0x180003391  call    memset_0
0x180003396  mov     [rbp+200h+pListOfExplicitEntries.grfAccessPermissions], 1FFFFFh
0x18000339d  mov     ebx, 2
0x1800033a2  mov     [rbp+200h+pListOfExplicitEntries.grfAccessMode], ebx
0x1800033a5  lea     esi, [rbx+1]
0x1800033a8  mov     [rbp+200h+pListOfExplicitEntries.grfInheritance], esi
0x1800033ab  mov     [rbp+200h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x1800033af  mov     [rbp+200h+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800033b6  mov     rax, [rbp+200h+var_280]
0x1800033ba  mov     [rbp+200h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x1800033be  lea     rax, [rsp+300h+var_298]
0x1800033c3  mov     [rsp+300h+pSid], rax; pSid
0x1800033c8  mov     [rsp+300h+nSubAuthority7], r13d; nSubAuthority7
0x1800033cd  mov     [rsp+300h+nSubAuthority6], r13d; nSubAuthority6
0x1800033d2  mov     [rsp+300h+nSubAuthority5], r13d; nSubAuthority5
0x1800033d7  mov     [rsp+300h+nSubAuthority4], r13d; nSubAuthority4
0x1800033dc  mov     [rsp+300h+nSubAuthority3], r13d; nSubAuthority3
0x1800033e1  mov     [rsp+300h+nSubAuthority2], r13d; nSubAuthority2
0x1800033e6  mov     r9d, 220h; nSubAuthority1
0x1800033ec  lea     r8d, [rbx+1Eh]; nSubAuthority0
0x1800033f0  mov     dl, bl; nSubAuthorityCount
0x1800033f2  lea     rcx, [rbp+200h+pIdentifierAuthority]; pIdentifierAuthority
0x1800033f6  call    cs:__imp_AllocateAndInitializeSid
0x1800033fc  test    eax, eax
0x1800033fe  jz      loc_1800032C0
0x180003404  mov     [rbp+200h+var_1A0], 1FFFFFh
0x18000340b  mov     [rbp+200h+var_19C], ebx
0x18000340e  mov     [rbp+200h+var_198], esi
0x180003411  mov     [rbp+200h+var_184], r13d
0x180003415  mov     [rbp+200h+var_180], ebx
0x18000341b  mov     rax, [rsp+300h+var_298]
0x180003420  mov     [rbp+200h+var_178], rax
0x180003427  test    r14d, r14d
0x18000342a  jz      loc_180003621
0x180003430  xorps   xmm0, xmm0
0x180003433  movups  xmmword ptr [rbp+200h+ObjectAttributes.Length], xmm0
0x180003437  movups  xmmword ptr [rbp+200h+ObjectAttributes.ObjectName], xmm0
0x18000343b  movups  xmmword ptr [rbp+200h+ObjectAttributes.SecurityDescriptor], xmm0
0x18000343f  mov     rdx, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180003446  mov     rdx, [rdx+6C0h]
0x18000344d  lea     rcx, [rbp+200h+var_208]
0x180003451  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003457  mov     ebx, eax
0x180003459  test    eax, eax
0x18000345b  js      loc_1800032D5
0x180003461  cmp     [rbp+200h+var_1D8], r13d
0x180003465  jnz     short loc_1800034DE
0x180003467  lea     rax, [rsp+300h+var_290]
0x18000346c  mov     [rsp+300h+pSid], rax; pSid
0x180003471  mov     [rsp+300h+nSubAuthority7], r13d; nSubAuthority7
0x180003476  mov     [rsp+300h+nSubAuthority6], r13d; nSubAuthority6
0x18000347b  mov     [rsp+300h+nSubAuthority5], r13d; nSubAuthority5
0x180003480  mov     [rsp+300h+nSubAuthority4], r13d; nSubAuthority4
0x180003485  mov     [rsp+300h+nSubAuthority3], r13d; nSubAuthority3
0x18000348a  mov     [rsp+300h+nSubAuthority2], r13d; nSubAuthority2
0x18000348f  xor     r9d, r9d; nSubAuthority1
0x180003492  lea     r8d, [rsi+4]; nSubAuthority0
0x180003496  mov     dl, 1; nSubAuthorityCount
0x180003498  lea     rcx, [rbp+200h+pIdentifierAuthority]; pIdentifierAuthority
0x18000349c  call    cs:__imp_AllocateAndInitializeSid
0x1800034a2  test    eax, eax
0x1800034a4  jz      loc_1800032C0
0x1800034aa  mov     [rbp+200h+var_170], 1FFFFFh
0x1800034b4  lea     ecx, [rsi-1]
0x1800034b7  mov     [rbp+200h+var_16C], ecx
0x1800034bd  mov     [rbp+200h+var_168], esi
0x1800034c3  mov     [rbp+200h+var_154], r13d
0x1800034ca  mov     [rbp+200h+var_150], 5
0x1800034d4  mov     rax, [rsp+300h+var_290]
0x1800034d9  jmp     loc_180003618
0x1800034de  lea     rdx, asc_180011C30; "\\"
0x1800034e5  lea     rcx, [rbp+200h+var_208]
0x1800034e9  call    cs:__imp_?Append@STRU@@QEAAJPEBG@Z; STRU::Append(ushort const *)
0x1800034ef  mov     ebx, eax
0x1800034f1  test    eax, eax
0x1800034f3  js      loc_1800032D5
0x1800034f9  mov     r8, cs:?g_pLogSvcAdmin@@3PEAVLOG_SVC_ADMIN@@EA; LOG_SVC_ADMIN * g_pLogSvcAdmin
0x180003500  mov     rdx, [r8+718h]
0x180003507  test    rdx, rdx
0x18000350a  jz      short loc_180003548
0x18000350c  cmp     [rdx], r13w
0x180003510  jz      short loc_180003548
0x180003512  mov     r8d, [r8+728h]
0x180003519  lea     rcx, [rbp+200h+var_208]
0x18000351d  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180003523  mov     ebx, eax
0x180003525  test    eax, eax
0x180003527  js      short loc_180003561
0x180003529  mov     r8d, 1
0x18000352f  lea     rdx, asc_1800120CC; "$"
0x180003536  lea     rcx, [rbp+200h+var_208]
0x18000353a  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x180003540  mov     ebx, eax
0x180003542  test    eax, eax
0x180003544  js      short loc_180003561
0x180003546  jmp     short loc_180003569
0x180003548  mov     r8d, 2
0x18000354e  lea     rdx, asc_180012130; "- "
0x180003555  lea     rcx, [rbp+200h+var_208]
0x180003559  call    cs:__imp_?Append@STRU@@QEAAJPEBGK@Z; STRU::Append(ushort const *,ulong)
0x18000355f  mov     ebx, eax
0x180003561  test    ebx, ebx
0x180003563  js      loc_1800032D5
0x180003569  lea     r9, [rsp+300h+ObjectHandle]; PolicyHandle
0x18000356e  mov     r8d, 800h; DesiredAccess
0x180003574  lea     rdx, [rbp+200h+ObjectAttributes]; ObjectAttributes
0x180003578  xor     ecx, ecx; SystemName
0x18000357a  call    cs:__imp_LsaOpenPolicy
0x180003580  test    eax, eax
0x180003582  jz      short loc_18000358E
0x180003584  mov     ebx, 80004005h
0x180003589  jmp     loc_1800032D5
0x18000358e  movzx   eax, word ptr [rbp+200h+var_1D8]
0x180003592  add     ax, ax
0x180003595  mov     [rbp+200h+Names.Length], ax
0x180003599  add     ax, 2
0x18000359d  mov     [rbp+200h+Names.MaximumLength], ax
0x1800035a1  mov     rax, [rbp+200h+var_1E8]
0x1800035a5  mov     [rbp+200h+Names.Buffer], rax
0x1800035a9  lea     rax, [rsp+300h+Buffer]
0x1800035ae  mov     qword ptr [rsp+300h+nSubAuthority3], rax; Sids
0x1800035b3  lea     rax, [rbp+200h+var_270]
0x1800035b7  mov     qword ptr [rsp+300h+nSubAuthority2], rax; ReferencedDomains
0x1800035bc  lea     r9, [rbp+200h+Names]; Names
0x1800035c0  mov     edx, 80000000h; Flags
0x1800035c5  mov     r8d, 1; Count
0x1800035cb  mov     rcx, [rsp+300h+ObjectHandle]; PolicyHandle
0x1800035d0  call    cs:__imp_LsaLookupNames2
0x1800035d6  test    eax, eax
0x1800035d8  jnz     short loc_180003584
0x1800035da  mov     rcx, [rsp+300h+Buffer]
0x1800035df  mov     eax, [rcx]
0x1800035e1  sub     eax, 7
0x1800035e4  cmp     eax, 1
0x1800035e7  jbe     short loc_180003584
0x1800035e9  mov     [rbp+200h+var_170], 1FFFFFh
0x1800035f3  mov     [rbp+200h+var_16C], 2
0x1800035fd  mov     [rbp+200h+var_168], esi
0x180003603  mov     [rbp+200h+var_154], r13d
0x18000360a  mov     [rbp+200h+var_150], 8
0x180003614  mov     rax, [rcx+8]
0x180003618  mov     [rbp+200h+var_148], rax
0x18000361f  jmp     short loc_180003629
0x180003621  mov     ebx, r13d
0x180003624  mov     esi, 2
0x180003629  lea     r9, [rbp+200h+hMem]; NewAcl
0x18000362d  xor     r8d, r8d; OldAcl
0x180003630  lea     rdx, [rbp+200h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180003634  mov     ecx, esi; cCountOfExplicitEntries
0x180003636  call    cs:__imp_SetEntriesInAclW
0x18000363c  test    eax, eax
0x18000363e  jnz     loc_1800032C0
0x180003644  lea     edx, [rax+28h]; uBytes
0x180003647  lea     ecx, [rax+40h]; uFlags
0x18000364a  call    cs:__imp_LocalAlloc
0x180003650  mov     rdi, rax
0x180003653  test    rax, rax
0x180003656  jz      loc_1800032C0
0x18000365c  mov     esi, 1
0x180003661  mov     edx, esi; dwRevision
0x180003663  mov     rcx, rax; pSecurityDescriptor
0x180003666  call    cs:__imp_InitializeSecurityDescriptor
0x18000366c  test    eax, eax
0x18000366e  jz      loc_1800032C0
0x180003674  xor     r9d, r9d; bDaclDefaulted
0x180003677  mov     r8, [rbp+200h+hMem]; pDacl
0x18000367b  mov     edx, esi; bDaclPresent
0x18000367d  mov     rcx, rdi; pSecurityDescriptor
0x180003680  call    cs:__imp_SetSecurityDescriptorDacl
0x180003686  test    eax, eax
0x180003688  jz      loc_1800032C0
0x18000368e  xor     r8d, r8d; bOwnerDefaulted
0x180003691  mov     rcx, rdi; pSecurityDescriptor
0x180003694  test    r14d, r14d
0x180003697  jz      short loc_180003708
0x180003699  cmp     [rbp+200h+var_1D8], r13d
0x18000369d  jbe     short loc_180003701
0x18000369f  mov     rdx, [rsp+300h+Buffer]
0x1800036a4  mov     rdx, [rdx+8]; pOwner
0x1800036a8  call    cs:__imp_SetSecurityDescriptorOwner
0x1800036ae  test    eax, eax
0x1800036b0  jz      loc_1800032C0
0x1800036b6  mov     [rbp+200h+SecurityAttributes.nLength], 18h
0x1800036bd  mov     [rbp+200h+SecurityAttributes.lpSecurityDescriptor], rdi
  ... truncated ...
```
