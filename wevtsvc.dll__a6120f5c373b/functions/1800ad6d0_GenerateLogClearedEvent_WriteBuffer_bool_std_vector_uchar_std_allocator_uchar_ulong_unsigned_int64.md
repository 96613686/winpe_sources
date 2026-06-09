# GenerateLogClearedEvent(WriteBuffer &,bool,std::vector<uchar,std::allocator<uchar>> &,ulong &,unsigned __int64 &)

- ea: `0x1800ad6d0`
- end: `0x1800add78`
- name: `?GenerateLogClearedEvent@@YAXAEAVWriteBuffer@@_NAEAV?$vector@EV?$allocator@E@std@@@std@@AEAKAEA_K@Z`
- size: `1704`
- prototype: `__int64 __usercall@<rax>(WriteBuffer *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180063238`

## callees

- `0x180006fb0`
- `0x180016250`
- `0x1800248c0`
- `0x18003617c`
- `0x18006be5c`
- `0x180070418`
- `0x180076220`
- `0x180092008`
- `0x18009aee0`
- `0x18009bb88`
- `0x1800ad5b4`
- `0x1800ad6d0`
- `0x1800d3370`

## import_xrefs

- `ntdll!NtQueryInformationProcess` at `0x1800ad779`
- `ntdll!NtQueryInformationProcess` at `0x1800ad779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad92a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad80e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad8a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad92a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad9ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800adb15`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad79f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800ad79f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ada36`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ada36`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad7f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad870`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800adaeb`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad7f9`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800ad870`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800adaeb`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800adbd9`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x1800adbd9`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ad754`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1800ad754`
- `RPCRT4!RpcImpersonateClient` at `0x1800ad727`
- `RPCRT4!RpcImpersonateClient` at `0x1800ad727`
- `RPCRT4!RpcRevertToSelf` at `0x1800add4b`
- `RPCRT4!RpcRevertToSelf` at `0x1800add4b`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800ad91c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800ad987`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800ad91c`
- `api-ms-win-security-lsalookup-l1-1-0!LookupAccountSidLocalW` at `0x1800ad987`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
RPC_STATUS __fastcall GenerateLogClearedEvent(WriteBuffer *this, char a2, void **a3, DWORD *a4, unsigned __int64 *a5)
{
  char v9; // r15
  DWORD RpcClientPid; // eax
  HANDLE v11; // rax
  void *v12; // rbx
  unsigned __int64 v13; // rcx
  DWORD v14; // ebx
  PSID *v15; // rax
  PSID *p_TokenInformation; // rsi
  DWORD LastError; // eax
  __int64 v18; // rdx
  WCHAR *v19; // r9
  WCHAR *v20; // rdx
  WCHAR *v21; // r9
  WCHAR *v22; // rdx
  LPWSTR *v23; // rcx
  LPWSTR *v24; // rcx
  DWORD LengthSid; // eax
  size_t v26; // r14
  _BYTE *v27; // rdx
  unsigned __int64 v28; // rcx
  unsigned __int64 v29; // rbx
  DWORD v30; // eax
  char *v31; // r9
  char *v32; // rdx
  char *v33; // rbx
  BOOL WellKnownSid; // eax
  char *v35; // rdx
  char *v36; // r14
  unsigned __int64 v37; // rcx
  char *v38; // rax
  size_t v39; // rbx
  char *v40; // rax
  unsigned __int64 v41; // rsi
  LPWSTR *v42; // rdx
  LPWSTR *v43; // rdx
  unsigned int v44; // r8d
  LPWSTR *v45; // rdx
  LPWSTR *v46; // rdx
  RPC_STATUS result; // eax
  DWORD cbSid[2]; // [rsp+30h] [rbp-A1h] BYREF
  DWORD TokenInformationLength; // [rsp+38h] [rbp-99h] BYREF
  DWORD cchName; // [rsp+3Ch] [rbp-95h] BYREF
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-91h] BYREF
  char v52; // [rsp+45h] [rbp-8Ch]
  unsigned __int64 ProcessInformation; // [rsp+48h] [rbp-89h] BYREF
  PSID *v54; // [rsp+50h] [rbp-81h] BYREF
  __int64 v55; // [rsp+58h] [rbp-79h] BYREF
  __int128 TokenInformation; // [rsp+60h] [rbp-71h] BYREF
  LPWSTR ReferencedDomainName[2]; // [rsp+70h] [rbp-61h] BYREF
  __int64 v58; // [rsp+80h] [rbp-51h]
  unsigned __int64 v59; // [rsp+88h] [rbp-49h]
  LPWSTR Name[2]; // [rsp+90h] [rbp-41h] BYREF
  __int64 v61; // [rsp+A0h] [rbp-31h]
  unsigned __int64 v62; // [rsp+A8h] [rbp-29h]
  _OWORD v63[3]; // [rsp+B0h] [rbp-21h] BYREF
  __int64 v64; // [rsp+E0h] [rbp+Fh]

  ProcessInformation = 0;
  *a4 = 0;
  *a5 = 0;
  if ( *a3 != a3[1] )
    a3[1] = *a3;
  v9 = 1;
  v52 = 1;
  if ( RpcImpersonateClient(0) )
  {
    v9 = 0;
    v52 = 0;
  }
  else
  {
    RpcClientPid = GetRpcClientPid();
    *a4 = RpcClientPid;
    v11 = OpenProcess(0x1000u, 0, RpcClientPid);
    v12 = v11;
    if ( v11 )
    {
      if ( NtQueryInformationProcess(v11, ProcessLUIDDeviceMapsEnabled|0x40, &ProcessInformation, 8u, 0) >= 0 )
      {
        v13 = ProcessInformation;
        *a5 = ProcessInformation;
        *a5 = v13 | ((unsigned __int64)MEMORY[0x7FFE02C4] << 48);
      }
      CloseHandle(v12);
    }
  }
  *(_OWORD *)Name = 0;
  v61 = 0;
  v62 = 7;
  LOWORD(Name[0]) = 0;
  *(_OWORD *)ReferencedDomainName = 0;
  v58 = 0;
  v59 = 7;
  LOWORD(ReferencedDomainName[0]) = 0;
  TokenInformation = 0;
  TokenInformationLength = 16;
  v54 = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenUser, &TokenInformation, 0x10u, &TokenInformationLength) )
  {
    p_TokenInformation = (PSID *)&TokenInformation;
  }
  else
  {
    if ( GetLastError() != 122 )
      goto LABEL_17;
    v14 = TokenInformationLength;
    v15 = (PSID *)operator new(TokenInformationLength);
    p_TokenInformation = v15;
    if ( v15 )
      memset_0(v15, 0, v14);
    else
      p_TokenInformation = 0;
    *(_QWORD *)cbSid = 0;
    v54 = p_TokenInformation;
    utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(cbSid);
    if ( !GetTokenInformation(
            (HANDLE)0xFFFFFFFFFFFFFFFALL,
            TokenUser,
            p_TokenInformation,
            TokenInformationLength,
            &TokenInformationLength) )
    {
LABEL_17:
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LastError = GetLastError();
        v18 = 11;
LABEL_39:
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, WPP_cb99b26e88863fa57470e86087f74cae_Traceguids, LastError);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
  }
  cchName = 64;
  std::wstring::resize(Name, 64);
  cchReferencedDomainName = 64;
  std::wstring::resize(ReferencedDomainName, 64);
  cbSid[0] = 0;
  v19 = (WCHAR *)ReferencedDomainName;
  if ( v59 > 7 )
    v19 = ReferencedDomainName[0];
  v20 = (WCHAR *)Name;
  if ( v62 > 7 )
    v20 = Name[0];
  if ( LookupAccountSidLocalW(*p_TokenInformation, v20, &cchName, v19, &cchReferencedDomainName, (PSID_NAME_USE)cbSid) )
    goto LABEL_40;
  if ( GetLastError() != 122 )
    goto LABEL_31;
  std::wstring::resize(Name, cchName);
  std::wstring::resize(ReferencedDomainName, cchReferencedDomainName);
  v21 = (WCHAR *)ReferencedDomainName;
  if ( v59 > 7 )
    v21 = ReferencedDomainName[0];
  v22 = (WCHAR *)Name;
  if ( v62 > 7 )
    v22 = Name[0];
  if ( LookupAccountSidLocalW(*p_TokenInformation, v22, &cchName, v21, &cchReferencedDomainName, (PSID_NAME_USE)cbSid) )
  {
LABEL_40:
    std::wstring::resize(Name, cchName);
    std::wstring::resize(ReferencedDomainName, cchReferencedDomainName);
    LengthSid = GetLengthSid(*p_TokenInformation);
    v26 = LengthSid;
    v27 = *a3;
    v28 = (_BYTE *)a3[1] - (_BYTE *)*a3;
    if ( LengthSid >= v28 )
    {
      if ( LengthSid > v28 )
      {
        if ( LengthSid <= (unsigned __int64)((_BYTE *)a3[2] - v27) )
        {
          v29 = (unsigned __int64)a3[1] + LengthSid - v28;
          memset_0(a3[1], 0, LengthSid - v28);
          a3[1] = (void *)v29;
        }
        else
        {
          std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, LengthSid);
        }
      }
    }
    else
    {
      a3[1] = &v27[LengthSid];
    }
    memcpy_0(*a3, *p_TokenInformation, v26);
  }
  else
  {
LABEL_31:
    v61 = 0;
    v23 = Name;
    if ( v62 > 7 )
      v23 = (LPWSTR *)Name[0];
    *(_WORD *)v23 = 0;
    v58 = 0;
    v24 = ReferencedDomainName;
    if ( v59 > 7 )
      v24 = (LPWSTR *)ReferencedDomainName[0];
    *(_WORD *)v24 = 0;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      v18 = 10;
      goto LABEL_39;
    }
  }
LABEL_47:
  utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(&v54);
  v55 = 0;
  memset(v63, 0, sizeof(v63));
  v64 = 0;
  cbSid[0] = 56;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFALL, TokenStatistics, v63, 0x38u, cbSid) )
  {
    v55 = DWORD2(v63[0]) + ((__int64)SHIDWORD(v63[0]) << 32);
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
         && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0
         && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 3u )
  {
    v30 = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_cb99b26e88863fa57470e86087f74cae_Traceguids, v30);
  }
  if ( !v61 )
    std::wstring::push_back(Name);
  if ( !v58 )
    std::wstring::push_back(ReferencedDomainName);
  v31 = (char *)a3[1];
  v32 = (char *)*a3;
  if ( *a3 != v31 )
    goto LABEL_80;
  if ( (unsigned __int64)(v31 - v32) <= 0x44 )
  {
    if ( (unsigned __int64)(v31 - v32) < 0x44 )
    {
      if ( (unsigned __int64)((_BYTE *)a3[2] - v32) >= 0x44 )
      {
        v33 = v32 + 68;
        memset_0(a3[1], 0, 68 - (v31 - v32));
        a3[1] = v33;
      }
      else
      {
        std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, 68);
      }
    }
  }
  else
  {
    a3[1] = v32 + 68;
  }
  cbSid[0] = *((_DWORD *)a3 + 2) - *(_DWORD *)a3;
  WellKnownSid = CreateWellKnownSid(WinNullSid, 0, *a3, cbSid);
  v35 = (char *)*a3;
  v36 = (char *)a3[1];
  v37 = v36 - (_BYTE *)*a3;
  if ( !WellKnownSid )
  {
    if ( v37 > 0xC )
    {
      v40 = v35 + 12;
LABEL_78:
      a3[1] = v40;
      goto LABEL_79;
    }
    if ( v37 < 0xC )
    {
      if ( (unsigned __int64)((_BYTE *)a3[2] - v35) >= 0xC )
      {
        v41 = 12 - v37;
        memset_0(a3[1], 0, 12 - v37);
        v40 = &v36[v41];
        goto LABEL_78;
      }
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, 12);
    }
LABEL_79:
    memcpy_0(*a3, qword_1800F1118, (_BYTE *)a3[1] - (_BYTE *)*a3);
    goto LABEL_80;
  }
  if ( cbSid[0] >= v37 )
  {
    if ( cbSid[0] <= v37 )
      goto LABEL_80;
    if ( cbSid[0] > (unsigned __int64)((_BYTE *)a3[2] - v35) )
    {
      std::vector<unsigned char>::_Resize_reallocate<std::_Value_init_tag>(a3, cbSid[0]);
      goto LABEL_80;
    }
    v39 = cbSid[0] - v37;
    memset_0(a3[1], 0, v39);
    v38 = &v36[v39];
  }
  else
  {
    v38 = &v35[cbSid[0]];
  }
  a3[1] = v38;
LABEL_80:
  if ( a2 )
  {
    WriteBuffer::Write(this, *a3, *((_DWORD *)a3 + 2) - *(_DWORD *)a3);
    v42 = Name;
    if ( v62 > 7 )
      v42 = (LPWSTR *)Name[0];
    WriteBuffer::Write(this, v42, 2 * v61 + 2);
    v43 = ReferencedDomainName;
    if ( v59 > 7 )
      v43 = (LPWSTR *)ReferencedDomainName[0];
    WriteBuffer::Write(this, v43, 2 * v58 + 2);
    v44 = 8;
    v45 = (LPWSTR *)&v55;
  }
  else
  {
    v46 = Name;
    if ( v62 > 7 )
      v46 = (LPWSTR *)Name[0];
    WriteBuffer::Write(this, v46, 2 * v61 + 2);
    v44 = 2 * v58 + 2;
    v45 = ReferencedDomainName;
    if ( v59 > 7 )
      v45 = (LPWSTR *)ReferencedDomainName[0];
  }
  WriteBuffer::Write(this, v45, v44);
  std::wstring::~wstring(ReferencedDomainName);
  result = std::wstring::~wstring(Name);
  if ( v9 )
    return RpcRevertToSelf();
  return result;
}

```

## disassembly

```asm
0x1800ad6d0  mov     [rsp-8+arg_8], rbx
0x1800ad6d5  push    rbp
0x1800ad6d6  push    rsi
0x1800ad6d7  push    rdi
0x1800ad6d8  push    r12
0x1800ad6da  push    r13
0x1800ad6dc  push    r14
0x1800ad6de  push    r15
0x1800ad6e0  lea     rbp, [rsp-1Fh]
0x1800ad6e5  sub     rsp, 0F0h
0x1800ad6ec  mov     rax, cs:__security_cookie
0x1800ad6f3  xor     rax, rsp
0x1800ad6f6  mov     [rbp+4Fh+var_38], rax
0x1800ad6fa  mov     rbx, r9
0x1800ad6fd  mov     rdi, r8
0x1800ad700  mov     r13b, dl
0x1800ad703  mov     r12, rcx
0x1800ad706  mov     rsi, [rbp+4Fh+arg_20]
0x1800ad70a  xor     r14d, r14d
0x1800ad70d  mov     [rsp+120h+ProcessInformation], r14
0x1800ad712  mov     [r9], r14d
0x1800ad715  mov     [rsi], r14
0x1800ad718  mov     rax, [r8]
0x1800ad71b  cmp     rax, [r8+8]
0x1800ad71f  jz      short loc_1800AD725
0x1800ad721  mov     [r8+8], rax
0x1800ad725  xor     ecx, ecx; BindingHandle
0x1800ad727  call    cs:__imp_RpcImpersonateClient
0x1800ad72d  mov     r15b, 1
0x1800ad730  mov     [rsp+120h+var_DB], r15b
0x1800ad735  test    eax, eax
0x1800ad737  jz      short loc_1800AD743
0x1800ad739  mov     r15b, r14b
0x1800ad73c  mov     [rsp+120h+var_DB], r14b
0x1800ad741  jmp     short loc_1800AD7A5
0x1800ad743  call    ?GetRpcClientPid@@YAKXZ; GetRpcClientPid(void)
0x1800ad748  mov     [rbx], eax
0x1800ad74a  mov     r8d, eax; dwProcessId
0x1800ad74d  xor     edx, edx; bInheritHandle
0x1800ad74f  mov     ecx, 1000h; dwDesiredAccess
0x1800ad754  call    cs:__imp_OpenProcess
0x1800ad75a  mov     rbx, rax
0x1800ad75d  test    rax, rax
0x1800ad760  jz      short loc_1800AD7A5
0x1800ad762  mov     [rsp+120h+ReturnLength], r14; ReturnLength
0x1800ad767  mov     r9d, 8; ProcessInformationLength
0x1800ad76d  lea     r8, [rsp+120h+ProcessInformation]; ProcessInformation
0x1800ad772  lea     edx, [r9+54h]; ProcessInformationClass
0x1800ad776  mov     rcx, rax; ProcessHandle
0x1800ad779  call    cs:__imp_NtQueryInformationProcess
0x1800ad77f  test    eax, eax
0x1800ad781  js      short loc_1800AD79C
0x1800ad783  mov     rcx, [rsp+120h+ProcessInformation]
0x1800ad788  mov     [rsi], rcx
0x1800ad78b  mov     eax, ds:7FFE02C4h
0x1800ad792  shl     rax, 30h
0x1800ad796  or      rax, rcx
0x1800ad799  mov     [rsi], rax
0x1800ad79c  mov     rcx, rbx; hObject
0x1800ad79f  call    cs:__imp_CloseHandle
0x1800ad7a5  xorps   xmm0, xmm0
0x1800ad7a8  movups  xmmword ptr [rbp+4Fh+Name], xmm0
0x1800ad7ac  mov     [rbp+4Fh+var_80], r14
0x1800ad7b0  mov     ecx, 7
0x1800ad7b5  mov     [rbp+4Fh+var_78], rcx
0x1800ad7b9  mov     word ptr [rbp+4Fh+Name], r14w
0x1800ad7be  movups  xmmword ptr [rbp+4Fh+ReferencedDomainName], xmm0
0x1800ad7c2  mov     [rbp+4Fh+var_A0], r14
0x1800ad7c6  mov     [rbp+4Fh+var_98], rcx
0x1800ad7ca  mov     word ptr [rbp+4Fh+ReferencedDomainName], r14w
0x1800ad7cf  movups  [rbp+4Fh+TokenInformation], xmm0
0x1800ad7d3  lea     r9d, [rcx+9]; TokenInformationLength
0x1800ad7d7  mov     [rsp+120h+TokenInformationLength], r9d
0x1800ad7dc  mov     [rsp+120h+var_D0], r14
0x1800ad7e1  lea     rax, [rsp+120h+TokenInformationLength]
0x1800ad7e6  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800ad7eb  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x1800ad7ef  lea     edx, [rcx-6]; TokenInformationClass
0x1800ad7f2  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800ad7f9  call    cs:__imp_GetTokenInformation
0x1800ad7ff  lea     rbx, WPP_GLOBAL_Control
0x1800ad806  test    eax, eax
0x1800ad808  jnz     loc_1800AD8B8
0x1800ad80e  call    cs:__imp_GetLastError
0x1800ad814  cmp     eax, 7Ah ; 'z'
0x1800ad817  jnz     short loc_1800AD881
0x1800ad819  mov     ebx, [rsp+120h+TokenInformationLength]
0x1800ad81d  mov     ecx, ebx; dwBytes
0x1800ad81f  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad824  mov     rsi, rax
0x1800ad827  test    rax, rax
0x1800ad82a  jz      short loc_1800AD83B
0x1800ad82c  mov     r8d, ebx; Size
0x1800ad82f  xor     edx, edx; Val
0x1800ad831  mov     rcx, rax; void *
0x1800ad834  call    memset_0
0x1800ad839  jmp     short loc_1800AD83E
0x1800ad83b  mov     rsi, r14
0x1800ad83e  mov     qword ptr [rsp+120h+cbSid], r14
0x1800ad843  mov     [rsp+120h+var_D0], rsi
0x1800ad848  lea     rcx, [rsp+120h+cbSid]
0x1800ad84d  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800ad852  lea     rax, [rsp+120h+TokenInformationLength]
0x1800ad857  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800ad85c  mov     r9d, [rsp+120h+TokenInformationLength]; TokenInformationLength
0x1800ad861  mov     r8, rsi; TokenInformation
0x1800ad864  mov     edx, 1; TokenInformationClass
0x1800ad869  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800ad870  call    cs:__imp_GetTokenInformation
0x1800ad876  test    eax, eax
0x1800ad878  jnz     short loc_1800AD8BC
0x1800ad87a  lea     rbx, WPP_GLOBAL_Control
0x1800ad881  mov     rax, cs:WPP_GLOBAL_Control
0x1800ad888  cmp     rax, rbx
0x1800ad88b  jz      loc_1800ADAA6
0x1800ad891  test    dword ptr [rax+1Ch], 800h
0x1800ad898  jz      loc_1800ADAA6
0x1800ad89e  cmp     byte ptr [rax+19h], 2
0x1800ad8a2  jb      loc_1800ADAA6
0x1800ad8a8  call    cs:__imp_GetLastError
0x1800ad8ae  mov     edx, 0Bh
0x1800ad8b3  jmp     loc_1800AD9FA
0x1800ad8b8  lea     rsi, [rbp+4Fh+TokenInformation]
0x1800ad8bc  mov     ebx, 40h ; '@'
0x1800ad8c1  mov     [rsp+120h+cchName], ebx
0x1800ad8c5  mov     edx, ebx
0x1800ad8c7  lea     rcx, [rbp+4Fh+Name]
0x1800ad8cb  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ad8d0  mov     [rsp+120h+cchReferencedDomainName], ebx
0x1800ad8d4  mov     edx, ebx
0x1800ad8d6  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x1800ad8da  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ad8df  mov     [rsp+120h+cbSid], r14d
0x1800ad8e4  lea     r9, [rbp+4Fh+ReferencedDomainName]
0x1800ad8e8  cmp     [rbp+4Fh+var_98], 7
0x1800ad8ed  cmova   r9, [rbp+4Fh+ReferencedDomainName]; ReferencedDomainName
0x1800ad8f2  lea     rdx, [rbp+4Fh+Name]
0x1800ad8f6  cmp     [rbp+4Fh+var_78], 7
0x1800ad8fb  cmova   rdx, [rbp+4Fh+Name]; Name
0x1800ad900  lea     rax, [rsp+120h+cbSid]
0x1800ad905  mov     [rsp+120h+peUse], rax; peUse
0x1800ad90a  lea     rax, [rsp+120h+cchReferencedDomainName]
0x1800ad90f  mov     [rsp+120h+ReturnLength], rax; cchReferencedDomainName
0x1800ad914  lea     r8, [rsp+120h+cchName]; cchName
0x1800ad919  mov     rcx, [rsi]; Sid
0x1800ad91c  call    cs:__imp_LookupAccountSidLocalW
0x1800ad922  test    eax, eax
0x1800ad924  jnz     loc_1800ADA19
0x1800ad92a  call    cs:__imp_GetLastError
0x1800ad930  cmp     eax, 7Ah ; 'z'
0x1800ad933  jnz     short loc_1800AD995
0x1800ad935  mov     edx, [rsp+120h+cchName]
0x1800ad939  lea     rcx, [rbp+4Fh+Name]
0x1800ad93d  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ad942  mov     edx, [rsp+120h+cchReferencedDomainName]
0x1800ad946  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x1800ad94a  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ad94f  lea     r9, [rbp+4Fh+ReferencedDomainName]
0x1800ad953  cmp     [rbp+4Fh+var_98], 7
0x1800ad958  cmova   r9, [rbp+4Fh+ReferencedDomainName]; ReferencedDomainName
0x1800ad95d  lea     rdx, [rbp+4Fh+Name]
0x1800ad961  cmp     [rbp+4Fh+var_78], 7
0x1800ad966  cmova   rdx, [rbp+4Fh+Name]; Name
0x1800ad96b  lea     rax, [rsp+120h+cbSid]
0x1800ad970  mov     [rsp+120h+peUse], rax; peUse
0x1800ad975  lea     rax, [rsp+120h+cchReferencedDomainName]
0x1800ad97a  mov     [rsp+120h+ReturnLength], rax; cchReferencedDomainName
0x1800ad97f  lea     r8, [rsp+120h+cchName]; cchName
0x1800ad984  mov     rcx, [rsi]; Sid
0x1800ad987  call    cs:__imp_LookupAccountSidLocalW
0x1800ad98d  test    eax, eax
0x1800ad98f  jnz     loc_1800ADA19
0x1800ad995  mov     [rbp+4Fh+var_80], r14
0x1800ad999  lea     rcx, [rbp+4Fh+Name]
0x1800ad99d  cmp     [rbp+4Fh+var_78], 7
0x1800ad9a2  cmova   rcx, [rbp+4Fh+Name]
0x1800ad9a7  mov     [rcx], r14w
0x1800ad9ab  mov     [rbp+4Fh+var_A0], r14
0x1800ad9af  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x1800ad9b3  cmp     [rbp+4Fh+var_98], 7
0x1800ad9b8  cmova   rcx, [rbp+4Fh+ReferencedDomainName]
0x1800ad9bd  mov     [rcx], r14w
0x1800ad9c1  mov     rax, cs:WPP_GLOBAL_Control
0x1800ad9c8  lea     rbx, WPP_GLOBAL_Control
0x1800ad9cf  cmp     rax, rbx
0x1800ad9d2  jz      loc_1800ADAA6
0x1800ad9d8  test    dword ptr [rax+1Ch], 800h
0x1800ad9df  jz      loc_1800ADAA6
0x1800ad9e5  cmp     byte ptr [rax+19h], 2
0x1800ad9e9  jb      loc_1800ADAA6
0x1800ad9ef  call    cs:__imp_GetLastError
0x1800ad9f5  mov     edx, 0Ah
0x1800ad9fa  mov     r9d, eax
0x1800ad9fd  lea     r8, WPP_cb99b26e88863fa57470e86087f74cae_Traceguids
0x1800ada04  mov     rcx, cs:WPP_GLOBAL_Control
0x1800ada0b  mov     rcx, [rcx+10h]
0x1800ada0f  call    WPP_SF_d
0x1800ada14  jmp     loc_1800ADAA6
0x1800ada19  mov     edx, [rsp+120h+cchName]
0x1800ada1d  lea     rcx, [rbp+4Fh+Name]
0x1800ada21  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ada26  mov     edx, [rsp+120h+cchReferencedDomainName]
0x1800ada2a  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x1800ada2e  call    ?resize@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K_W@Z; std::wstring::resize(unsigned __int64,wchar_t)
0x1800ada33  mov     rcx, [rsi]; pSid
0x1800ada36  call    cs:__imp_GetLengthSid
0x1800ada3c  mov     r14d, eax
0x1800ada3f  mov     rdx, [rdi]
0x1800ada42  mov     r9, [rdi+8]
0x1800ada46  mov     rcx, r9
0x1800ada49  sub     rcx, rdx
0x1800ada4c  cmp     r14, rcx
0x1800ada4f  jnb     short loc_1800ADA5B
0x1800ada51  lea     rax, [r14+rdx]
0x1800ada55  mov     [rdi+8], rax
0x1800ada59  jmp     short loc_1800ADA8E
0x1800ada5b  jbe     short loc_1800ADA8E
0x1800ada5d  mov     rax, [rdi+10h]
0x1800ada61  sub     rax, rdx
0x1800ada64  cmp     r14, rax
0x1800ada67  jbe     short loc_1800ADA76
0x1800ada69  mov     rdx, r14
0x1800ada6c  mov     rcx, rdi
0x1800ada6f  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<uchar>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x1800ada74  jmp     short loc_1800ADA8E
0x1800ada76  mov     r8, r14
0x1800ada79  sub     r8, rcx; Size
0x1800ada7c  lea     rbx, [r8+r9]
0x1800ada80  xor     edx, edx; Val
0x1800ada82  mov     rcx, r9; void *
0x1800ada85  call    memset_0
0x1800ada8a  mov     [rdi+8], rbx
0x1800ada8e  mov     r8, r14; Size
0x1800ada91  mov     rdx, [rsi]; Src
0x1800ada94  mov     rcx, [rdi]; void *
0x1800ada97  call    memcpy_0
0x1800ada9c  xor     r14d, r14d
0x1800ada9f  lea     rbx, WPP_GLOBAL_Control
0x1800adaa6  lea     rcx, [rsp+120h+var_D0]
0x1800adaab  call    ??1?$unique_ptr@$$BY0A@PEAXU?$default_delete@$$BY0A@PEAX@utl@@@utl@@QEAA@XZ; utl::unique_ptr<void * [0],utl::default_delete<void * [0]>>::~unique_ptr<void * [0],utl::default_delete<void * [0]>>(void)
0x1800adab0  mov     [rbp+4Fh+var_C8], r14
0x1800adab4  xorps   xmm0, xmm0
0x1800adab7  xor     eax, eax
0x1800adab9  movups  [rbp+4Fh+var_70], xmm0
0x1800adabd  movups  [rbp+4Fh+var_60], xmm0
0x1800adac1  movups  [rbp+4Fh+var_50], xmm0
0x1800adac5  mov     [rbp+4Fh+var_40], rax
0x1800adac9  lea     r9d, [rax+38h]; TokenInformationLength
0x1800adacd  mov     [rsp+120h+cbSid], r9d
0x1800adad2  lea     rax, [rsp+120h+cbSid]
0x1800adad7  mov     [rsp+120h+ReturnLength], rax; ReturnLength
0x1800adadc  lea     r8, [rbp+4Fh+var_70]; TokenInformation
0x1800adae0  lea     edx, [r9-2Eh]; TokenInformationClass
0x1800adae4  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x1800adaeb  call    cs:__imp_GetTokenInformation
0x1800adaf1  mov     esi, 0Ch
0x1800adaf6  test    eax, eax
0x1800adaf8  jnz     short loc_1800ADB39
0x1800adafa  mov     rax, cs:WPP_GLOBAL_Control
0x1800adb01  cmp     rax, rbx
0x1800adb04  jz      short loc_1800ADB4B
0x1800adb06  test    dword ptr [rax+1Ch], 800h
0x1800adb0d  jz      short loc_1800ADB4B
0x1800adb0f  cmp     byte ptr [rax+19h], 3
0x1800adb13  jb      short loc_1800ADB4B
0x1800adb15  call    cs:__imp_GetLastError
0x1800adb1b  mov     edx, esi
0x1800adb1d  mov     r9d, eax
0x1800adb20  lea     r8, WPP_cb99b26e88863fa57470e86087f74cae_Traceguids
0x1800adb27  mov     rcx, cs:WPP_GLOBAL_Control
0x1800adb2e  mov     rcx, [rcx+10h]
0x1800adb32  call    WPP_SF_d
0x1800adb37  jmp     short loc_1800ADB4B
0x1800adb39  movsxd  rcx, dword ptr [rbp+4Fh+var_70+0Ch]
0x1800adb3d  shl     rcx, 20h
0x1800adb41  mov     eax, dword ptr [rbp+4Fh+var_70+8]
0x1800adb44  add     rcx, rax
0x1800adb47  mov     [rbp+4Fh+var_C8], rcx
0x1800adb4b  cmp     [rbp+4Fh+var_80], r14
0x1800adb4f  jnz     short loc_1800ADB5A
0x1800adb51  lea     rcx, [rbp+4Fh+Name]
0x1800adb55  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x1800adb5a  cmp     [rbp+4Fh+var_A0], r14
0x1800adb5e  jnz     short loc_1800ADB69
0x1800adb60  lea     rcx, [rbp+4Fh+ReferencedDomainName]
0x1800adb64  call    ?push_back@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_W@Z; std::wstring::push_back(wchar_t)
0x1800adb69  mov     r9, [rdi+8]
0x1800adb6d  mov     rdx, [rdi]
0x1800adb70  cmp     rdx, r9
0x1800adb73  jnz     loc_1800ADC8C
0x1800adb79  mov     rcx, r9
0x1800adb7c  sub     rcx, rdx
0x1800adb7f  mov     r8d, 44h ; 'D'
0x1800adb85  cmp     rcx, r8
0x1800adb88  jbe     short loc_1800ADB94
0x1800adb8a  lea     rax, [rdx+44h]
0x1800adb8e  mov     [rdi+8], rax
0x1800adb92  jmp     short loc_1800ADBC4
0x1800adb94  jnb     short loc_1800ADBC4
0x1800adb96  mov     rax, [rdi+10h]
  ... truncated ...
```
