# CAgentDownloadManager::HandleDownloadJobError(_GUID const &,tagDownloadJobError const *)

- ea: `0x1800a08e8`
- end: `0x1800a0ff2`
- name: `?HandleDownloadJobError@CAgentDownloadManager@@QEAAXAEBU_GUID@@PEBUtagDownloadJobError@@@Z`
- size: `1802`
- prototype: `void __fastcall(CAgentDownloadManager *__hidden this, const struct _GUID *, const struct tagDownloadJobError *)`
- caller_count: `1`
- callee_count: `24`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f45e0`

## callees

- `0x1800802e8`
- `0x18008e10c`
- `0x1800941cc`
- `0x180095788`
- `0x1800a08e8`
- `0x1800a1254`
- `0x1800a4c84`
- `0x1800a9464`
- `0x1800a9584`
- `0x1800a96b4`
- `0x1800e6358`
- `0x1800e6bdc`
- `0x1800e6e34`
- `0x1800e6ec4`
- `0x1800ea068`
- `0x1800ea0b4`
- `0x1800ebdfc`
- `0x1800ebf2c`
- `0x180113ae8`
- `0x18012b618`
- `0x18012bed4`
- `0x18012bf80`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0966`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0aa1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0966`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800a0aa1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0ecb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0f79`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0aba`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0ada`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0ecb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800a0f79`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a0eec`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800a0eec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f31`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800a0f31`

## string_xrefs

- `0x1800a0a36`: `Spurious 403 for %ws job{%ws}, updateId = %ws; update is already pending TLU refresh; ignoring...`
- `0x1800a0ba3`: `All available CDNs for the update %ws are tried but the download job %ws still failed.`
- `0x1800a0be8`: `HandleDownloadJobError: will retry with different CDN for update %ws error 0x%x`
- `0x1800a0cb5`: `%ws job {%ws}, updateId = %ws, is using the distribution server's URL and to replace with the original URL`
- `0x1800a0d50`: `%ws job {%ws} 403'd, updateId = %ws, hr = 0x%08lX, BG_ERROR_CONTEXT = %d`
- `0x1800a0de5`: `403'd %ws job {%ws}, updateId = %ws, %ws`
- `0x1800a0e84`: `%ws job {%ws}, updateId = %ws failed on HTTP 403 error after retries`
- `0x1800a0f07`: `Caller SID for retrying failed download job: %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CAgentDownloadManager::HandleDownloadJobError(
        CAgentDownloadManager *this,
        struct _GUID *a2,
        const struct tagDownloadJobError *a3)
{
  struct CUpdateDownloadJob *DownloadJobByJobID; // rax
  struct CUpdateDownloadJob *v7; // r15
  WCHAR *JobTypeAsString; // rdi
  bool v9; // zf
  __int64 updated; // rbx
  __int64 v11; // rax
  int v12; // ebx
  int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // edi
  _WORD *v16; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  int v20; // ebx
  __int64 v21; // rax
  bool v22; // zf
  __int64 v23; // rbx
  __int64 v24; // rax
  int v25; // edi
  int v26; // esi
  __int64 v27; // rbx
  __int64 v28; // rax
  __int64 v29; // rbx
  __int64 v30; // rax
  const wchar_t *v31; // rcx
  __int64 v32; // rax
  unsigned int TLUExpirationMaximumRetryCount; // eax
  __int64 v34; // rbx
  __int64 v35; // rax
  struct CCallerIdentity *v36; // rbx
  const struct tagDownloadJobError *v37; // r9
  int v38; // [rsp+20h] [rbp-E0h]
  unsigned int *v39; // [rsp+38h] [rbp-C8h]
  __int64 v40; // [rsp+40h] [rbp-C0h]
  char v41; // [rsp+60h] [rbp-A0h]
  bool v42; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v43; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned int v44; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v45; // [rsp+74h] [rbp-8Ch]
  struct _GUID v46; // [rsp+78h] [rbp-88h] BYREF
  int v47; // [rsp+88h] [rbp-78h]
  struct CCallerIdentity *v48; // [rsp+90h] [rbp-70h] BYREF
  struct _GUID v49; // [rsp+98h] [rbp-68h] BYREF
  struct _GUID v50; // [rsp+A8h] [rbp-58h] BYREF
  int v51; // [rsp+B8h] [rbp-48h]
  struct _GUID v52; // [rsp+BCh] [rbp-44h]
  void *lpMem; // [rsp+D0h] [rbp-30h]
  _BYTE v54[80]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v55[112]; // [rsp+130h] [rbp+30h] BYREF
  LPWSTR StringSid; // [rsp+1A0h] [rbp+A0h] BYREF
  __int128 v57; // [rsp+1A8h] [rbp+A8h] BYREF
  char v58[144]; // [rsp+1C0h] [rbp+C0h] BYREF

  v48 = 0;
  lpMem = 0;
  v50 = 0;
  v51 = 0;
  v52 = c_idSrvNone;
  v57 = 0;
  v41 = 1;
  if ( !a3 )
  {
    v12 = 0;
    goto LABEL_62;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  DownloadJobByJobID = CAgentDownloadManager::FindDownloadJobByJobID(this, a2);
  v7 = DownloadJobByJobID;
  if ( !DownloadJobByJobID )
  {
    v12 = 0;
    goto LABEL_59;
  }
  DownloadManagerUpdateID::operator=(&v50, (char *)DownloadJobByJobID + 8);
  v49 = v52;
  v46 = v50;
  v47 = v51;
  v43 = 0;
  CDownloadRegulator::IsUpdateSuspended(*((CDownloadRegulator **)this + 259), &v46, &v43);
  JobTypeAsString = (WCHAR *)CUpdateDownloadJob::GetJobTypeAsString(v7);
  StringSid = JobTypeAsString;
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( *((_DWORD *)a3 + 1) != 5 )
      goto LABEL_13;
    v9 = *((_DWORD *)a3 + 2) == -2145844845;
  }
  else
  {
    if ( *(_DWORD *)a3 != 2 )
      goto LABEL_13;
    v9 = *((_DWORD *)a3 + 1) == 403;
  }
  if ( v9 && (v43 & 0x40000) != 0 )
  {
    updated = Trace::UpdateIdToString::UpdateIdToString(
                (Trace::UpdateIdToString *)v55,
                (const struct tagDSGlobalUpdateId *)&v46);
    v11 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
    WUTrace(
      0,
      0,
      2,
      3,
      0,
      L"Spurious 403 for %ws job{%ws}, updateId = %ws; update is already pending TLU refresh; ignoring...",
      JobTypeAsString,
      v11,
      updated);
LABEL_11:
    v41 = 0;
LABEL_12:
    v12 = 0;
    goto LABEL_59;
  }
LABEL_13:
  v42 = 0;
  v44 = 0;
  memset(v58, 0, 129);
  v43 = 0;
  if ( v7 != (struct CUpdateDownloadJob *)-376LL )
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 384));
  v13 = *((_DWORD *)v7 + 111);
  if ( v13 )
  {
    v14 = *(_DWORD *)(*((_QWORD *)v7 + 54) + 4LL * (unsigned int)(v13 - 1));
    if ( v7 != (struct CUpdateDownloadJob *)-376LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 384));
  }
  else
  {
    if ( v7 != (struct CUpdateDownloadJob *)-376LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)v7 + 384));
    v14 = -1;
  }
  CAgentDownloadManager::GetMatchingCallProperties(
    this,
    (const struct DownloadManagerUpdateID *)&v50,
    v14,
    &v42,
    (enum tagNetworkCostPolicy *)&v44,
    v58,
    &v48,
    &v43);
  v15 = v44;
  if ( *((_BYTE *)v7 + 561) )
    v15 = 4;
  v45 = v15;
  if ( CAgentDownloadManager::CanRetryWithDifferentCDNForError(this, &v49, *((_DWORD *)a3 + 2)) )
  {
    if ( *((_BYTE *)v7 + 577) || *((_BYTE *)v7 + 576) && (v16 = (_WORD *)*((_QWORD *)v7 + 23)) != 0 && *v16 )
    {
      v18 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
      v19 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v55,
              (const struct tagDSGlobalUpdateId *)&v46);
      WUTrace(
        0,
        0,
        2,
        1,
        *((_DWORD *)a3 + 2),
        L"All available CDNs for the update %ws are tried but the download job %ws still failed.",
        v19,
        v18);
    }
    else
    {
      v20 = *((_DWORD *)a3 + 2);
      v21 = Trace::UpdateIdToString::UpdateIdToString(
              (Trace::UpdateIdToString *)v55,
              (const struct tagDSGlobalUpdateId *)&v46);
      LODWORD(v39) = v20;
      WUTrace(
        0,
        0,
        2,
        4,
        0,
        L"HandleDownloadJobError: will retry with different CDN for update %ws error 0x%x",
        v21,
        v39);
      v41 = 0;
      LOBYTE(v38) = v42;
      CAgentDownloadManager::QueueUpdateForCDNListRefresh(this, v7, *((unsigned int *)a3 + 2), v15, v38, v58, v43);
    }
    goto LABEL_12;
  }
  if ( *(_DWORD *)a3 == 1 )
  {
    if ( *((_DWORD *)a3 + 1) != 5 )
      goto LABEL_12;
    v22 = *((_DWORD *)a3 + 2) == -2145844845;
  }
  else
  {
    if ( *(_DWORD *)a3 != 2 )
      goto LABEL_12;
    v22 = *((_DWORD *)a3 + 1) == 403;
  }
  if ( !v22 )
    goto LABEL_12;
  if ( CUpdateDownloadJob::ShouldRetryWithOriginalURL(v7) )
  {
    v23 = Trace::UpdateIdToString::UpdateIdToString(
            (Trace::UpdateIdToString *)v55,
            (const struct tagDSGlobalUpdateId *)&v46);
    v24 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
    WUTrace(
      0,
      0,
      2,
      4,
      0,
      L"%ws job {%ws}, updateId = %ws, is using the distribution server's URL and to replace with the original URL",
      StringSid,
      v24,
      v23);
    *((_BYTE *)v7 + 226) = 1;
    v49 = *(struct _GUID *)((char *)v7 + 28);
    CAgentDownloadManager::QueueCheckAllDownloadJobStatesWorkItem(this, &v49, 0);
    goto LABEL_11;
  }
  if ( CUpdateDownloadJob::ShouldRetryWithFullFile(v7) )
    goto LABEL_12;
  v25 = *((_DWORD *)a3 + 1);
  v26 = *((_DWORD *)a3 + 2);
  v27 = Trace::UpdateIdToString::UpdateIdToString(
          (Trace::UpdateIdToString *)v55,
          (const struct tagDSGlobalUpdateId *)&v46);
  v28 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
  v40 = v27;
  v12 = 0;
  WUTrace(
    0,
    0,
    2,
    4,
    0,
    L"%ws job {%ws} 403'd, updateId = %ws, hr = 0x%08lX, BG_ERROR_CONTEXT = %d",
    StringSid,
    v28,
    v40,
    v26,
    v25);
  v44 = 0;
  if ( (int)CAgentDownloadManager::DoesUpdateRequireDynamicData(
              this,
              (const struct DownloadManagerUpdateID *)&v50,
              &v44) < 0 )
  {
LABEL_59:
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
    if ( !v41 )
      goto LABEL_65;
    goto LABEL_62;
  }
  v29 = Trace::UpdateIdToString::UpdateIdToString(
          (Trace::UpdateIdToString *)v55,
          (const struct tagDSGlobalUpdateId *)&v46);
  v30 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
  v31 = L"does not use dynamic data, failing job";
  if ( (v44 & 1) != 0 )
    v31 = L"uses dynamic data";
  WUTrace(0, 0, 2, 4, 0, L"403'd %ws job {%ws}, updateId = %ws, %ws", StringSid, v30, v29, v31);
  if ( (v44 & 1) == 0 )
  {
    v12 = 0;
    goto LABEL_59;
  }
  v32 = *((_QWORD *)a3 + 2);
  if ( !v32 )
  {
    BYTE8(v57) = 1;
    v32 = *((_QWORD *)a3 + 5);
  }
  *(_QWORD *)&v57 = v32;
  TLUExpirationMaximumRetryCount = CAgentDownloadManager::GetTLUExpirationMaximumRetryCount(this, &v49);
  if ( !CUpdateDownloadJob::ShouldRefreshTLU(v7, TLUExpirationMaximumRetryCount, (const struct PathOrFileId *)&v57) )
  {
    v34 = Trace::UpdateIdToString::UpdateIdToString(
            (Trace::UpdateIdToString *)v55,
            (const struct tagDSGlobalUpdateId *)&v46);
    v35 = Trace::GuidToString::GuidToString((Trace::GuidToString *)v54, a2);
    WUTrace(0, 0, 2, 2, 0, L"%ws job {%ws}, updateId = %ws failed on HTTP 403 error after retries", StringSid, v35, v34);
    v12 = *((_DWORD *)v7 + 122);
    goto LABEL_59;
  }
  CDownloadRegulator::SuspendUpdate(*((CDownloadRegulator **)this + 259), &v46, 0x40000u);
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 624));
  v36 = v48;
  if ( v48 )
  {
    StringSid = 0;
    if ( ConvertSidToStringSidW(*((PSID *)v48 + 2), &StringSid) )
    {
      if ( StringSid )
      {
        WUTrace(0, 0, 2, 4, 0, L"Caller SID for retrying failed download job: %ws", StringSid);
        LocalFree(StringSid);
      }
    }
  }
  if ( (int)CAgentDownloadManager::QueueUpdateForDynamicRefresh(this, &v50, v36, v58, v45, v43) < 0 )
  {
    v12 = 0;
LABEL_62:
    v37 = 0;
    if ( !v12 )
      v37 = a3;
    CAgentDownloadManager::HandleDownloadJobCompletion(this, a2, v12, v37, 0, 1);
  }
LABEL_65:
  DownloadManagerUpdateID::Clear((DownloadManagerUpdateID *)&v50);
  if ( lpMem )
    SusFree(lpMem);
}

```

## disassembly

```asm
0x1800a08e8  mov     [rsp-8+arg_18], rbx
0x1800a08ed  push    rbp
0x1800a08ee  push    rsi
0x1800a08ef  push    rdi
0x1800a08f0  push    r12
0x1800a08f2  push    r13
0x1800a08f4  push    r14
0x1800a08f6  push    r15
0x1800a08f8  lea     rbp, [rsp-160h]
0x1800a0900  sub     rsp, 260h
0x1800a0907  mov     rax, cs:__security_cookie
0x1800a090e  xor     rax, rsp
0x1800a0911  mov     [rbp+190h+var_40], rax
0x1800a0918  mov     r14, r8
0x1800a091b  mov     r12, rdx
0x1800a091e  mov     r13, rcx
0x1800a0921  xor     esi, esi
0x1800a0923  mov     [rbp+190h+var_200], rsi
0x1800a0927  mov     [rsp+290h+var_22C], esi
0x1800a092b  mov     [rbp+190h+lpMem], rsi
0x1800a092f  xorps   xmm0, xmm0
0x1800a0932  xor     eax, eax
0x1800a0934  movups  [rbp+190h+var_1E8], xmm0
0x1800a0938  mov     [rbp+190h+var_1D8], eax
0x1800a093b  movups  xmm0, xmmword ptr cs:c_idSrvNone.Data1
0x1800a0942  movdqu  [rbp+190h+var_1D4], xmm0
0x1800a0947  xorps   xmm0, xmm0
0x1800a094a  movups  [rbp+190h+var_E8], xmm0
0x1800a0951  mov     [rsp+290h+var_230], 1
0x1800a0956  test    r8, r8
0x1800a0959  jz      loc_1800A0F88
0x1800a095f  add     rcx, 270h; lpCriticalSection
0x1800a0966  call    cs:__imp_EnterCriticalSection
0x1800a096c  mov     rdx, r12; struct _GUID *
0x1800a096f  mov     rcx, r13; this
0x1800a0972  call    ?FindDownloadJobByJobID@CAgentDownloadManager@@AEAAPEAVCUpdateDownloadJob@@AEBU_GUID@@@Z; CAgentDownloadManager::FindDownloadJobByJobID(_GUID const &)
0x1800a0977  mov     r15, rax
0x1800a097a  test    rax, rax
0x1800a097d  jz      loc_1800A0F6E
0x1800a0983  lea     rdx, [rax+8]
0x1800a0987  lea     rcx, [rbp+190h+var_1E8]
0x1800a098b  call    ??4DownloadManagerUpdateID@@QEAAXAEBU0@@Z; DownloadManagerUpdateID::operator=(DownloadManagerUpdateID const &)
0x1800a0990  movups  xmm0, [rbp+190h+var_1D4]
0x1800a0994  movdqu  xmmword ptr [rbp+190h+var_1F8.Data1], xmm0
0x1800a0999  movups  xmm1, [rbp+190h+var_1E8]
0x1800a099d  movups  xmmword ptr [rsp+290h+var_218.Data1], xmm1
0x1800a09a2  mov     ecx, [rbp+190h+var_1D8]
0x1800a09a5  mov     [rbp+190h+var_208], ecx
0x1800a09a8  mov     [rsp+290h+var_224], esi
0x1800a09ac  lea     r8, [rsp+290h+var_224]; unsigned int *
0x1800a09b1  lea     rdx, [rsp+290h+var_218]; struct _GUID *
0x1800a09b6  mov     rcx, [r13+818h]; this
0x1800a09bd  call    ?IsUpdateSuspended@CDownloadRegulator@@QEAAHAEBU_GUID@@PEAK@Z; CDownloadRegulator::IsUpdateSuspended(_GUID const &,ulong *)
0x1800a09c2  mov     rcx, r15; this
0x1800a09c5  call    ?GetJobTypeAsString@CUpdateDownloadJob@@QEBAPEB_WXZ; CUpdateDownloadJob::GetJobTypeAsString(void)
0x1800a09ca  mov     rdi, rax
0x1800a09cd  mov     [rbp+190h+StringSid], rax
0x1800a09d4  mov     edx, [r14]
0x1800a09d7  sub     edx, 1
0x1800a09da  jz      short loc_1800A09EF
0x1800a09dc  cmp     edx, 1
0x1800a09df  jnz     loc_1800A0A66
0x1800a09e5  cmp     dword ptr [r14+4], 193h
0x1800a09ed  jmp     short loc_1800A09FE
0x1800a09ef  cmp     dword ptr [r14+4], 5
0x1800a09f4  jnz     short loc_1800A0A66
0x1800a09f6  cmp     dword ptr [r14+8], 80190193h
0x1800a09fe  jnz     short loc_1800A0A66
0x1800a0a00  test    [rsp+290h+var_224], 40000h
0x1800a0a08  jz      short loc_1800A0A66
0x1800a0a0a  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0a0f  lea     rcx, [rbp+190h+var_160]; this
0x1800a0a13  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0a18  mov     rbx, rax
0x1800a0a1b  mov     rdx, r12; struct _GUID *
0x1800a0a1e  lea     rcx, [rbp+190h+var_1B0]; this
0x1800a0a22  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a0a27  mov     [rsp+290h+var_250], rbx
0x1800a0a2c  mov     [rsp+290h+var_258], rax
0x1800a0a31  mov     [rsp+290h+var_260], rdi
0x1800a0a36  lea     rax, aSpurious403For; "Spurious 403 for %ws job{%ws}, updateId"...
0x1800a0a3d  mov     [rsp+290h+var_268], rax
0x1800a0a42  mov     [rsp+290h+var_270], rsi
0x1800a0a47  xor     edx, edx
0x1800a0a49  xor     ecx, ecx
0x1800a0a4b  lea     r9d, [rdx+3]
0x1800a0a4f  lea     r8d, [rdx+2]
0x1800a0a53  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a0a58  xor     esi, esi
0x1800a0a5a  mov     [rsp+290h+var_230], sil
0x1800a0a5f  mov     ebx, esi
0x1800a0a61  jmp     loc_1800A0F72
0x1800a0a66  mov     [rsp+290h+var_228], sil
0x1800a0a6b  mov     [rsp+290h+var_220], esi
0x1800a0a6f  mov     [rbp+190h+var_D0], sil
0x1800a0a76  xor     edx, edx; Val
0x1800a0a78  mov     r8d, 80h; Size
0x1800a0a7e  lea     rcx, [rbp+190h+var_CF]; void *
0x1800a0a85  call    memset
0x1800a0a8a  mov     [rsp+290h+var_224], esi
0x1800a0a8e  lea     rbx, [r15+178h]
0x1800a0a95  lea     rdi, [rbx+8]
0x1800a0a99  test    rbx, rbx
0x1800a0a9c  jz      short loc_1800A0AA7
0x1800a0a9e  mov     rcx, rdi; lpCriticalSection
0x1800a0aa1  call    cs:__imp_EnterCriticalSection
0x1800a0aa7  mov     eax, [r15+1BCh]
0x1800a0aae  test    eax, eax
0x1800a0ab0  jnz     short loc_1800A0AC5
0x1800a0ab2  test    rbx, rbx
0x1800a0ab5  jz      short loc_1800A0AC0
0x1800a0ab7  mov     rcx, rdi; lpCriticalSection
0x1800a0aba  call    cs:__imp_LeaveCriticalSection
0x1800a0ac0  or      esi, 0FFFFFFFFh
0x1800a0ac3  jmp     short loc_1800A0AE0
0x1800a0ac5  lea     ecx, [rax-1]
0x1800a0ac8  mov     rax, [r15+1B0h]
0x1800a0acf  mov     esi, [rax+rcx*4]
0x1800a0ad2  test    rbx, rbx
0x1800a0ad5  jz      short loc_1800A0AE0
0x1800a0ad7  mov     rcx, rdi; lpCriticalSection
0x1800a0ada  call    cs:__imp_LeaveCriticalSection
0x1800a0ae0  lea     rax, [rsp+290h+var_224]
0x1800a0ae5  mov     [rsp+290h+var_258], rax; unsigned int *
0x1800a0aea  lea     rax, [rbp+190h+var_200]
0x1800a0aee  mov     [rsp+290h+var_260], rax; struct CCallerIdentity **
0x1800a0af3  lea     rax, [rbp+190h+var_D0]
0x1800a0afa  mov     [rsp+290h+var_268], rax; char *
0x1800a0aff  lea     rax, [rsp+290h+var_220]
0x1800a0b04  mov     [rsp+290h+var_270], rax; enum tagNetworkCostPolicy *
0x1800a0b09  lea     r9, [rsp+290h+var_228]; bool *
0x1800a0b0e  mov     r8d, esi; unsigned int
0x1800a0b11  lea     rdx, [rbp+190h+var_1E8]; struct DownloadManagerUpdateID *
0x1800a0b15  mov     rcx, r13; this
0x1800a0b18  call    ?GetMatchingCallProperties@CAgentDownloadManager@@AEAAXAEBUDownloadManagerUpdateID@@KPEA_NPEAW4tagNetworkCostPolicy@@PEADPEAPEBVCCallerIdentity@@PEAK@Z; CAgentDownloadManager::GetMatchingCallProperties(DownloadManagerUpdateID const &,ulong,bool *,tagNetworkCostPolicy *,char *,CCallerIdentity const * *,ulong *)
0x1800a0b1d  mov     edi, [rsp+290h+var_220]
0x1800a0b21  mov     eax, 4
0x1800a0b26  xor     esi, esi
0x1800a0b28  cmp     [r15+231h], sil
0x1800a0b2f  cmovnz  edi, eax
0x1800a0b32  mov     [rsp+290h+var_21C], edi
0x1800a0b36  mov     r8d, [r14+8]; int
0x1800a0b3a  lea     rdx, [rbp+190h+var_1F8]; struct _GUID *
0x1800a0b3e  mov     rcx, r13; this
0x1800a0b41  call    ?CanRetryWithDifferentCDNForError@CAgentDownloadManager@@AEBA_NAEBU_GUID@@J@Z; CAgentDownloadManager::CanRetryWithDifferentCDNForError(_GUID const &,long)
0x1800a0b46  test    al, al
0x1800a0b48  jz      loc_1800A0C42
0x1800a0b4e  cmp     [r15+241h], sil
0x1800a0b55  jnz     short loc_1800A0B76
0x1800a0b57  cmp     [r15+240h], sil
0x1800a0b5e  jz      short loc_1800A0B71
0x1800a0b60  mov     rax, [r15+0B8h]
0x1800a0b67  test    rax, rax
0x1800a0b6a  jz      short loc_1800A0B71
0x1800a0b6c  cmp     [rax], si
0x1800a0b6f  jnz     short loc_1800A0B76
0x1800a0b71  mov     al, sil
0x1800a0b74  jmp     short loc_1800A0B78
0x1800a0b76  mov     al, 1
0x1800a0b78  test    al, al
0x1800a0b7a  jz      short loc_1800A0BCD
0x1800a0b7c  mov     rdx, r12; struct _GUID *
0x1800a0b7f  lea     rcx, [rbp+190h+var_1B0]; this
0x1800a0b83  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a0b88  mov     rbx, rax
0x1800a0b8b  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0b90  lea     rcx, [rbp+190h+var_160]; this
0x1800a0b94  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0b99  mov     [rsp+290h+var_258], rbx
0x1800a0b9e  mov     [rsp+290h+var_260], rax
0x1800a0ba3  lea     rax, aAllAvailableCd; "All available CDNs for the update %ws a"...
0x1800a0baa  mov     [rsp+290h+var_268], rax
0x1800a0baf  mov     eax, [r14+8]
0x1800a0bb3  mov     dword ptr [rsp+290h+var_270], eax
0x1800a0bb7  xor     edx, edx
0x1800a0bb9  xor     ecx, ecx
0x1800a0bbb  lea     r9d, [rdx+1]
0x1800a0bbf  lea     r8d, [rdx+2]
0x1800a0bc3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a0bc8  jmp     loc_1800A0A5F
0x1800a0bcd  mov     ebx, [r14+8]
0x1800a0bd1  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0bd6  lea     rcx, [rbp+190h+var_160]; this
0x1800a0bda  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0bdf  mov     dword ptr [rsp+290h+var_258], ebx
0x1800a0be3  mov     [rsp+290h+var_260], rax
0x1800a0be8  lea     rax, aHandledownload_1; "HandleDownloadJobError: will retry with"...
0x1800a0bef  mov     [rsp+290h+var_268], rax
0x1800a0bf4  mov     [rsp+290h+var_270], rsi
0x1800a0bf9  xor     edx, edx
0x1800a0bfb  xor     ecx, ecx
0x1800a0bfd  lea     r9d, [rdx+4]
0x1800a0c01  lea     r8d, [rdx+2]
0x1800a0c05  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a0c0a  mov     [rsp+290h+var_230], sil
0x1800a0c0f  mov     eax, [rsp+290h+var_224]
0x1800a0c13  mov     dword ptr [rsp+290h+var_260], eax
0x1800a0c17  lea     rax, [rbp+190h+var_D0]
0x1800a0c1e  mov     [rsp+290h+var_268], rax
0x1800a0c23  mov     al, [rsp+290h+var_228]
0x1800a0c27  mov     byte ptr [rsp+290h+var_270], al
0x1800a0c2b  mov     r9d, edi
0x1800a0c2e  mov     r8d, [r14+8]
0x1800a0c32  mov     rdx, r15
0x1800a0c35  mov     rcx, r13
0x1800a0c38  call    ?QueueUpdateForCDNListRefresh@CAgentDownloadManager@@AEAAJPEAVCUpdateDownloadJob@@JW4tagNetworkCostPolicy@@_NPEBDK@Z; CAgentDownloadManager::QueueUpdateForCDNListRefresh(CUpdateDownloadJob *,long,tagNetworkCostPolicy,bool,char const *,ulong)
0x1800a0c3d  jmp     loc_1800A0A5F
0x1800a0c42  mov     ecx, [r14]
0x1800a0c45  sub     ecx, 1
0x1800a0c48  jz      short loc_1800A0C5D
0x1800a0c4a  cmp     ecx, 1
0x1800a0c4d  jnz     loc_1800A0A5F
0x1800a0c53  cmp     dword ptr [r14+4], 193h
0x1800a0c5b  jmp     short loc_1800A0C70
0x1800a0c5d  cmp     dword ptr [r14+4], 5
0x1800a0c62  jnz     loc_1800A0A5F
0x1800a0c68  cmp     dword ptr [r14+8], 80190193h
0x1800a0c70  jnz     loc_1800A0A5F
0x1800a0c76  mov     rcx, r15; this
0x1800a0c79  call    ?ShouldRetryWithOriginalURL@CUpdateDownloadJob@@QEAA_NXZ; CUpdateDownloadJob::ShouldRetryWithOriginalURL(void)
0x1800a0c7e  test    al, al
0x1800a0c80  jz      short loc_1800A0CFD
0x1800a0c82  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0c87  lea     rcx, [rbp+190h+var_160]; this
0x1800a0c8b  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0c90  mov     rbx, rax
0x1800a0c93  mov     rdx, r12; struct _GUID *
0x1800a0c96  lea     rcx, [rbp+190h+var_1B0]; this
0x1800a0c9a  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a0c9f  mov     [rsp+290h+var_250], rbx
0x1800a0ca4  mov     [rsp+290h+var_258], rax
0x1800a0ca9  mov     rax, [rbp+190h+StringSid]
0x1800a0cb0  mov     [rsp+290h+var_260], rax
0x1800a0cb5  lea     rax, aWsJobWsUpdatei; "%ws job {%ws}, updateId = %ws, is using"...
0x1800a0cbc  mov     [rsp+290h+var_268], rax
0x1800a0cc1  mov     [rsp+290h+var_270], rsi
0x1800a0cc6  xor     edx, edx
0x1800a0cc8  xor     ecx, ecx
0x1800a0cca  lea     r9d, [rdx+4]
0x1800a0cce  lea     r8d, [rdx+2]
0x1800a0cd2  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a0cd7  mov     byte ptr [r15+0E2h], 1
0x1800a0cdf  movups  xmm0, xmmword ptr [r15+1Ch]
0x1800a0ce4  movdqu  xmmword ptr [rbp+190h+var_1F8.Data1], xmm0
0x1800a0ce9  xor     r8d, r8d; unsigned int
0x1800a0cec  lea     rdx, [rbp+190h+var_1F8]; struct _GUID *
0x1800a0cf0  mov     rcx, r13; this
0x1800a0cf3  call    ?QueueCheckAllDownloadJobStatesWorkItem@CAgentDownloadManager@@AEAAXAEBU_GUID@@K@Z; CAgentDownloadManager::QueueCheckAllDownloadJobStatesWorkItem(_GUID const &,ulong)
0x1800a0cf8  jmp     loc_1800A0A5A
0x1800a0cfd  mov     rcx, r15; this
0x1800a0d00  call    ?ShouldRetryWithFullFile@CUpdateDownloadJob@@QEAA_NXZ; CUpdateDownloadJob::ShouldRetryWithFullFile(void)
0x1800a0d05  test    al, al
0x1800a0d07  jnz     loc_1800A0A5F
0x1800a0d0d  mov     edi, [r14+4]
0x1800a0d11  mov     esi, [r14+8]
0x1800a0d15  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0d1a  lea     rcx, [rbp+190h+var_160]; this
0x1800a0d1e  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0d23  mov     rbx, rax
0x1800a0d26  mov     rdx, r12; struct _GUID *
0x1800a0d29  lea     rcx, [rbp+190h+var_1B0]; this
0x1800a0d2d  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a0d32  mov     [rsp+290h+var_240], edi
0x1800a0d36  mov     dword ptr [rsp+290h+var_248], esi
0x1800a0d3a  mov     [rsp+290h+var_250], rbx
0x1800a0d3f  mov     [rsp+290h+var_258], rax
0x1800a0d44  mov     rax, [rbp+190h+StringSid]
0x1800a0d4b  mov     [rsp+290h+var_260], rax
0x1800a0d50  lea     rax, aWsJobWs403DUpd; "%ws job {%ws} 403'd, updateId = %ws, hr"...
0x1800a0d57  mov     [rsp+290h+var_268], rax
0x1800a0d5c  xor     ebx, ebx
0x1800a0d5e  mov     [rsp+290h+var_270], rbx
0x1800a0d63  lea     esi, [rbx+2]
0x1800a0d66  lea     r9d, [rbx+4]
0x1800a0d6a  mov     r8d, esi
0x1800a0d6d  xor     edx, edx
0x1800a0d6f  xor     ecx, ecx
0x1800a0d71  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800a0d76  mov     [rsp+290h+var_220], ebx
0x1800a0d7a  lea     r8, [rsp+290h+var_220]; unsigned int *
0x1800a0d7f  lea     rdx, [rbp+190h+var_1E8]; struct DownloadManagerUpdateID *
0x1800a0d83  mov     rcx, r13; this
0x1800a0d86  call    ?DoesUpdateRequireDynamicData@CAgentDownloadManager@@AEAAJAEBUDownloadManagerUpdateID@@PEAK@Z; CAgentDownloadManager::DoesUpdateRequireDynamicData(DownloadManagerUpdateID const &,ulong *)
0x1800a0d8b  test    eax, eax
0x1800a0d8d  js      loc_1800A0EAB
0x1800a0d93  lea     rdx, [rsp+290h+var_218]; struct tagDSGlobalUpdateId *
0x1800a0d98  lea     rcx, [rbp+190h+var_160]; this
0x1800a0d9c  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x1800a0da1  mov     rbx, rax
0x1800a0da4  mov     rdx, r12; struct _GUID *
0x1800a0da7  lea     rcx, [rbp+190h+var_1B0]; this
0x1800a0dab  call    ??0GuidToString@Trace@@QEAA@AEBU_GUID@@@Z; Trace::GuidToString::GuidToString(_GUID const &)
0x1800a0db0  lea     rdx, aUsesDynamicDat; "uses dynamic data"
0x1800a0db7  lea     rcx, aDoesNotUseDyna; "does not use dynamic data, failing job"
0x1800a0dbe  xor     r8d, r8d
0x1800a0dc1  test    byte ptr [rsp+290h+var_220], 1
0x1800a0dc6  cmovnz  rcx, rdx
0x1800a0dca  mov     [rsp+290h+var_248], rcx
0x1800a0dcf  mov     [rsp+290h+var_250], rbx
0x1800a0dd4  mov     [rsp+290h+var_258], rax
  ... truncated ...
```
