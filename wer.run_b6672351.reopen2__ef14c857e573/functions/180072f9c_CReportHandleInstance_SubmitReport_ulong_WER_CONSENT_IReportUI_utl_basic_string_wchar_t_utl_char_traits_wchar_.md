# CReportHandleInstance::SubmitReport(ulong,_WER_CONSENT,IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,_WER_SUBMIT_RESULT *,_WERP_SUBMIT_RESULT *)

- ea: `0x180072f9c`
- end: `0x180073444`
- name: `?SubmitReport@CReportHandleInstance@@QEAAJKW4_WER_CONSENT@@PEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAW4_WER_SUBMIT_RESULT@@PEAW4_WERP_SUBMIT_RESULT@@@Z`
- size: `1192`
- prototype: `__int64 __usercall@<rax>(CReportHandleInstance *this@<rcx>, __int64, enum _WER_SUBMIT_RESULT *, enum _WERP_SUBMIT_RESULT *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180063700`
- `0x18006df10`

## callees

- `0x180003a98`
- `0x180004c64`
- `0x18000753c`
- `0x1800094d0`
- `0x18000db80`
- `0x18000ea54`
- `0x180011a3c`
- `0x180018ff0`
- `0x180020680`
- `0x18002d868`
- `0x18002d8f4`
- `0x18002e66c`
- `0x1800304b4`
- `0x180030de4`
- `0x180031cd0`
- `0x180033264`
- `0x180034288`
- `0x1800479ac`
- `0x180068558`
- `0x180072e54`
- `0x180072ec8`
- `0x180072f9c`
- `0x1800754b4`
- `0x18007645c`
- `0x180076de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073236`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180073236`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073195`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180073195`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800731f9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x1800731f9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180073220`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007341a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180073220`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18007341a`

## pseudocode

```c
__int64 CReportHandleInstance::SubmitReport(
        CReportHandleInstance *this,
        enum _WER_FILE_TYPE a2,
        enum _WER_CONSENT a3,
        __int64 a4,
        __int64 a5,
        ...)
{
  enum _WER_SUBMIT_RESULT *v5; // r13
  __int64 v7; // rax
  unsigned int v8; // esi
  enum _WERP_SUBMIT_RESULT *v10; // r12
  int v11; // ebx
  int v12; // r15d
  wchar_t *v13; // rcx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int IsCurrentProcessInteractive; // eax
  unsigned int v17; // ecx
  __int64 v18; // rcx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rcx
  enum _WERP_SUBMIT_RESULT *v22; // rdx
  bool v23; // zf
  __int64 v24; // rdx
  __int64 v25; // r9
  void *v26; // rcx
  __int64 v28; // [rsp+40h] [rbp-40h] BYREF
  __int64 v29; // [rsp+48h] [rbp-38h] BYREF
  __int64 v30; // [rsp+50h] [rbp-30h]
  __int64 v31[2]; // [rsp+58h] [rbp-28h] BYREF
  _WORD v32[12]; // [rsp+68h] [rbp-18h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+C0h] [rbp+40h] BYREF
  int v34; // [rsp+C8h] [rbp+48h]
  __int64 v35; // [rsp+D8h] [rbp+58h]
  enum _WER_SUBMIT_RESULT *v36; // [rsp+E8h] [rbp+68h] BYREF
  va_list va; // [rsp+E8h] [rbp+68h]
  enum _WERP_SUBMIT_RESULT *v38; // [rsp+F0h] [rbp+70h] BYREF
  va_list va1; // [rsp+F0h] [rbp+70h]
  va_list va2; // [rsp+F8h] [rbp+78h] BYREF

  va_start(va2, a5);
  va_start(va1, a5);
  va_start(va, a5);
  v36 = va_arg(va1, enum _WER_SUBMIT_RESULT *);
  va_copy(va2, va1);
  v38 = va_arg(va2, enum _WERP_SUBMIT_RESULT *);
  v35 = a4;
  v5 = v36;
  v7 = *((_QWORD *)this + 1);
  v8 = a2;
  SystemTimeAsFileTime = 0;
  v34 = 0;
  v30 = v7;
  if ( v36 )
    *v36 = WerReportFailed;
  v10 = v38;
  if ( v38 )
    *(_DWORD *)v38 = 2;
  if ( _InterlockedExchange((volatile __int32 *)this + 20, 1) )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
    v11 = -2147019873;
    goto LABEL_51;
  }
  v12 = 0;
  if ( (a2 & 0x200000) == 0 && !(unsigned int)CReport::IsReportLocked(*((CReport **)this + 1)) )
  {
    v11 = CReport::TryReportLock(*((CReport **)this + 1));
    if ( v11 < 0 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 15;
LABEL_49:
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids, (unsigned int)v11);
        goto LABEL_50;
      }
      goto LABEL_50;
    }
    v34 = 1;
  }
  if ( a3 == WerConsentApproved )
  {
    if ( (v8 & 0x20000000) != 0 )
      CReport::MarkFilesAsApprovedByType(*((CReport **)this + 1), a2);
    else
      a3 = WerConsentNotAsked;
  }
  v11 = CReport::ValidateSignatureParams(*((CReport **)this + 1));
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_50;
    v15 = 16;
    goto LABEL_25;
  }
  CReport::SetDefaultDynamicParameters(*((CReport **)this + 1));
  v11 = CReport::SetConsentValue(*((CReport **)this + 1), a3);
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (wchar_t *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[14] & 1) == 0 )
      goto LABEL_50;
    v15 = 17;
LABEL_25:
    WPP_SF_(*((_QWORD *)v13 + 2), v15, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
    goto LABEL_50;
  }
  v11 = CReport::InitializeSettings(*((CReport **)this + 1));
  if ( v11 < 0 )
  {
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v14 = 18;
      goto LABEL_49;
    }
LABEL_50:
    if ( v12 )
      goto LABEL_62;
    goto LABEL_51;
  }
  *(_DWORD *)(*((_QWORD *)this + 1) + 6616LL) = v8;
  if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 46680LL) )
  {
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    CReport::SetFileTime(*((CReport **)this + 1), &SystemTimeAsFileTime);
    if ( !*(_DWORD *)(*((_QWORD *)this + 1) + 5872LL) )
      v8 = v8 & 0x7FFFFFFC | 0x80000000;
    IsCurrentProcessInteractive = UtilIsCurrentProcessInteractive();
    v17 = v8 | 0x80000000;
    if ( IsCurrentProcessInteractive )
      v17 = v8;
    *(_DWORD *)(*((_QWORD *)this + 1) + 6616LL) = v17;
  }
  if ( !*((_QWORD *)this + 4) )
  {
    v11 = CReportHandleInstance::InitiateReportManager(this);
    if ( v11 < 0 )
      goto LABEL_51;
  }
  ResetEvent(*((HANDLE *)this + 7));
  if ( UtilWaitForSingleObject(L"CancelEvent", *((void **)this + 8), 0) )
  {
    *((_DWORD *)this + 10) = GetCurrentThreadId();
    CReportHandleInstance::LogReportSubmitAsimovEvent(this);
    v11 = CReportManager::ReportProblem(*((CReportManager **)this + 4));
    CReportHandleInstance::DoFinalCallback(this, v11);
    if ( v11 >= 0 )
      goto LABEL_62;
    v12 = 1;
    if ( v11 != -2145681407 )
    {
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      {
        v14 = 19;
        goto LABEL_49;
      }
    }
    goto LABEL_50;
  }
  SetEvent(*((HANDLE *)this + 7));
  v11 = -2145681407;
LABEL_51:
  v18 = *((_QWORD *)this + 1);
  v31[0] = (__int64)v32;
  v31[1] = (__int64)v32;
  v32[0] = 0;
  CReport::GetUniqueIdentifier(v18, v31);
  if ( (unsigned int)dword_1800DE000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800DE000, 0x400000000000LL) )
  {
    v21 = *((_QWORD *)this + 1);
    v22 = *(enum _WERP_SUBMIT_RESULT **)(v21 + 5912);
    v23 = v22 == *(enum _WERP_SUBMIT_RESULT **)(v21 + 5920);
    LODWORD(v36) = v11;
    if ( v23 )
      v22 = 0;
    v29 = 0x1000000;
    v28 = v31[0];
    v38 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
      v21,
      (unsigned int)byte_1800CD811,
      v19,
      v20,
      (__int64)&v29,
      (__int64)va,
      (__int64)&v28,
      (__int64)va1);
  }
  if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
  {
    v24 = *((_QWORD *)this + 1);
    v25 = *(_QWORD *)(v24 + 5912);
    if ( v25 == *(_QWORD *)(v24 + 5920) )
      v25 = 0;
    WPP_SF_dSS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      20,
      (unsigned int)WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids,
      v11,
      v31[0],
      v25);
  }
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v31);
LABEL_62:
  if ( v5 )
    CReportHandleInstance::MapSubmitResult(v5, v11, *(enum _WER_SUBMIT_RESULT *)(v30 + 9128));
  if ( v10 )
    CReportHandleInstance::MapInternalSubmitResult((CReportHandleInstance *)v13, v11, v10);
  if ( (int)(v11 + 0x80000000) < 0 || v11 == -2145681407 )
    v11 = 0;
  if ( v34 )
    CReport::ReleaseReportLock(*((CReport **)this + 1));
  v26 = (void *)*((_QWORD *)this + 7);
  if ( (unsigned __int64)v26 + 1 > 1 )
    SetEvent(v26);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180072f9c  mov     [rsp-38h+arg_10], rbx
0x180072fa1  mov     [rsp-38h+arg_18], r9
0x180072fa6  push    rbp
0x180072fa7  push    rsi
0x180072fa8  push    rdi
0x180072fa9  push    r12
0x180072fab  push    r13
0x180072fad  push    r14
0x180072faf  push    r15
0x180072fb1  mov     rbp, rsp
0x180072fb4  sub     rsp, 80h
0x180072fbb  mov     r13, [rbp+arg_28]
0x180072fbf  mov     r14d, r8d
0x180072fc2  mov     rax, [rcx+8]
0x180072fc6  mov     esi, edx
0x180072fc8  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x180072fd0  mov     rdi, rcx
0x180072fd3  mov     [rbp+arg_8], 0
0x180072fda  mov     [rbp+var_30], rax
0x180072fde  test    r13, r13
0x180072fe1  jz      short loc_180072FEB
0x180072fe3  mov     dword ptr [r13+0], 4
0x180072feb  mov     r12, [rbp+arg_30]
0x180072fef  test    r12, r12
0x180072ff2  jz      short loc_180072FFC
0x180072ff4  mov     dword ptr [r12], 2
0x180072ffc  mov     eax, 1
0x180073001  lea     r15, WPP_GLOBAL_Control
0x180073008  xchg    eax, [rcx+50h]
0x18007300b  test    eax, eax
0x18007300d  jz      short loc_180073040
0x18007300f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073016  cmp     rcx, r15
0x180073019  jz      short loc_180073036
0x18007301b  test    byte ptr [rcx+1Ch], 1
0x18007301f  jz      short loc_180073036
0x180073021  mov     rcx, [rcx+10h]
0x180073025  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18007302c  mov     edx, 0Eh
0x180073031  call    WPP_SF_
0x180073036  mov     ebx, 8007139Fh
0x18007303b  jmp     loc_1800732C0
0x180073040  xor     r15d, r15d
0x180073043  bt      esi, 15h
0x180073047  jb      short loc_180073096
0x180073049  mov     rcx, [rcx+8]; this
0x18007304d  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x180073052  test    eax, eax
0x180073054  jnz     short loc_180073096
0x180073056  mov     rcx, [rdi+8]; this
0x18007305a  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x18007305f  mov     ebx, eax
0x180073061  test    eax, eax
0x180073063  jns     short loc_18007308F
0x180073065  mov     rcx, cs:WPP_GLOBAL_Control
0x18007306c  lea     rax, WPP_GLOBAL_Control
0x180073073  cmp     rcx, rax
0x180073076  jz      loc_1800732B0
0x18007307c  test    byte ptr [rcx+1Ch], 1
0x180073080  jz      loc_1800732B0
0x180073086  lea     edx, [r15+0Fh]
0x18007308a  jmp     loc_18007329D
0x18007308f  mov     [rbp+arg_8], 1
0x180073096  cmp     r14d, 2
0x18007309a  jnz     short loc_1800730B3
0x18007309c  bt      esi, 1Dh
0x1800730a0  jnb     short loc_1800730AD
0x1800730a2  mov     rcx, [rdi+8]; this
0x1800730a6  call    ?MarkFilesAsApprovedByType@CReport@@QEAAXW4_WER_FILE_TYPE@@@Z; CReport::MarkFilesAsApprovedByType(_WER_FILE_TYPE)
0x1800730ab  jmp     short loc_1800730B3
0x1800730ad  mov     r14d, 1
0x1800730b3  mov     rcx, [rdi+8]; this
0x1800730b7  call    ?ValidateSignatureParams@CReport@@QEAAJXZ; CReport::ValidateSignatureParams(void)
0x1800730bc  mov     ebx, eax
0x1800730be  test    eax, eax
0x1800730c0  jns     short loc_1800730FD
0x1800730c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800730c9  lea     rax, WPP_GLOBAL_Control
0x1800730d0  cmp     rcx, rax
0x1800730d3  jz      loc_1800732B0
0x1800730d9  test    byte ptr [rcx+1Ch], 1
0x1800730dd  jz      loc_1800732B0
0x1800730e3  mov     edx, 10h
0x1800730e8  mov     rcx, [rcx+10h]
0x1800730ec  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x1800730f3  call    WPP_SF_
0x1800730f8  jmp     loc_1800732B0
0x1800730fd  mov     rcx, [rdi+8]; this
0x180073101  call    ?SetDefaultDynamicParameters@CReport@@QEAAJXZ; CReport::SetDefaultDynamicParameters(void)
0x180073106  mov     rcx, [rdi+8]; this
0x18007310a  mov     edx, r14d; enum _WER_CONSENT
0x18007310d  call    ?SetConsentValue@CReport@@QEAAJW4_WER_CONSENT@@@Z; CReport::SetConsentValue(_WER_CONSENT)
0x180073112  mov     ebx, eax
0x180073114  test    eax, eax
0x180073116  jns     short loc_180073140
0x180073118  mov     rcx, cs:WPP_GLOBAL_Control
0x18007311f  lea     rax, WPP_GLOBAL_Control
0x180073126  cmp     rcx, rax
0x180073129  jz      loc_1800732B0
0x18007312f  test    byte ptr [rcx+1Ch], 1
0x180073133  jz      loc_1800732B0
0x180073139  mov     edx, 11h
0x18007313e  jmp     short loc_1800730E8
0x180073140  mov     rcx, [rdi+8]; this
0x180073144  call    ?InitializeSettings@CReport@@QEAAJXZ; CReport::InitializeSettings(void)
0x180073149  mov     ebx, eax
0x18007314b  test    eax, eax
0x18007314d  jns     short loc_18007317A
0x18007314f  mov     rcx, cs:WPP_GLOBAL_Control
0x180073156  lea     rax, WPP_GLOBAL_Control
0x18007315d  cmp     rcx, rax
0x180073160  jz      loc_1800732B0
0x180073166  test    byte ptr [rcx+1Ch], 1
0x18007316a  jz      loc_1800732B0
0x180073170  mov     edx, 12h
0x180073175  jmp     loc_18007329D
0x18007317a  mov     rax, [rdi+8]
0x18007317e  mov     [rax+19D8h], esi
0x180073184  mov     rax, [rdi+8]
0x180073188  cmp     [rax+0B658h], r15d
0x18007318f  jnz     short loc_1800731DD
0x180073191  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180073195  call    cs:__imp_GetSystemTimeAsFileTime
0x18007319c  nop     dword ptr [rax+rax+00h]
0x1800731a1  mov     rcx, [rdi+8]; this
0x1800731a5  lea     rdx, [rbp+SystemTimeAsFileTime]; struct _FILETIME *
0x1800731a9  call    ?SetFileTime@CReport@@QEAAXPEAU_FILETIME@@@Z; CReport::SetFileTime(_FILETIME *)
0x1800731ae  mov     rax, [rdi+8]
0x1800731b2  mov     ebx, 80000000h
0x1800731b7  cmp     [rax+16F0h], r15d
0x1800731be  jnz     short loc_1800731C5
0x1800731c0  and     esi, 0FFFFFFFCh
0x1800731c3  or      esi, ebx
0x1800731c5  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x1800731ca  mov     ecx, esi
0x1800731cc  or      ecx, ebx
0x1800731ce  test    eax, eax
0x1800731d0  mov     rax, [rdi+8]
0x1800731d4  cmovnz  ecx, esi
0x1800731d7  mov     [rax+19D8h], ecx
0x1800731dd  cmp     [rdi+20h], r15
0x1800731e1  jnz     short loc_1800731F5
0x1800731e3  mov     rcx, rdi; this
0x1800731e6  call    ?InitiateReportManager@CReportHandleInstance@@QEAAJXZ; CReportHandleInstance::InitiateReportManager(void)
0x1800731eb  mov     ebx, eax
0x1800731ed  test    eax, eax
0x1800731ef  js      loc_1800732B9
0x1800731f5  mov     rcx, [rdi+38h]; hEvent
0x1800731f9  call    cs:__imp_ResetEvent
0x180073200  nop     dword ptr [rax+rax+00h]
0x180073205  mov     rdx, [rdi+40h]; void *
0x180073209  lea     rcx, aCancelevent; "CancelEvent"
0x180073210  xor     r8d, r8d; unsigned int
0x180073213  call    ?UtilWaitForSingleObject@@YAKPEB_WPEAXK@Z; UtilWaitForSingleObject(wchar_t const *,void *,ulong)
0x180073218  test    eax, eax
0x18007321a  jnz     short loc_180073236
0x18007321c  mov     rcx, [rdi+38h]; hEvent
0x180073220  call    cs:__imp_SetEvent
0x180073227  nop     dword ptr [rax+rax+00h]
0x18007322c  mov     ebx, 801B8001h
0x180073231  jmp     loc_1800732B9
0x180073236  call    cs:__imp_GetCurrentThreadId
0x18007323d  nop     dword ptr [rax+rax+00h]
0x180073242  mov     rcx, rdi; this
0x180073245  mov     [rdi+28h], eax
0x180073248  call    ?LogReportSubmitAsimovEvent@CReportHandleInstance@@AEAAXXZ; CReportHandleInstance::LogReportSubmitAsimovEvent(void)
0x18007324d  mov     r8, [rbp+arg_20]
0x180073251  mov     rdx, [rbp+arg_18]
0x180073255  mov     rcx, [rdi+20h]; this
0x180073259  call    ?ReportProblem@CReportManager@@QEAAJPEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ReportProblem(IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18007325e  mov     edx, eax; int
0x180073260  mov     rcx, rdi; this
0x180073263  mov     ebx, eax
0x180073265  call    ?DoFinalCallback@CReportHandleInstance@@AEAAJJ@Z; CReportHandleInstance::DoFinalCallback(long)
0x18007326a  test    ebx, ebx
0x18007326c  jns     loc_1800733BE
0x180073272  mov     r15d, 1
0x180073278  cmp     ebx, 801B8001h
0x18007327e  jz      short loc_1800732B0
0x180073280  mov     rcx, cs:WPP_GLOBAL_Control
0x180073287  lea     rax, WPP_GLOBAL_Control
0x18007328e  cmp     rcx, rax
0x180073291  jz      short loc_1800732B0
0x180073293  test    [rcx+1Ch], r15b
0x180073297  jz      short loc_1800732B0
0x180073299  lea     edx, [r15+12h]
0x18007329d  mov     rcx, [rcx+10h]
0x1800732a1  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x1800732a8  mov     r9d, ebx
0x1800732ab  call    WPP_SF_d
0x1800732b0  test    r15d, r15d
0x1800732b3  jnz     loc_1800733BE
0x1800732b9  lea     r15, WPP_GLOBAL_Control
0x1800732c0  mov     rcx, [rdi+8]
0x1800732c4  lea     rax, [rbp+var_18]
0x1800732c8  mov     [rbp+var_28], rax
0x1800732cc  lea     rdx, [rbp+var_28]
0x1800732d0  lea     rax, [rbp+var_18]
0x1800732d4  mov     [rbp+var_20], rax
0x1800732d8  xor     eax, eax
0x1800732da  mov     [rbp+var_18], ax
0x1800732de  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x1800732e3  mov     eax, cs:dword_1800DE000
0x1800732e9  cmp     eax, 5
0x1800732ec  jbe     short loc_180073367
0x1800732ee  mov     rdx, 400000000000h
0x1800732f8  lea     rcx, dword_1800DE000
0x1800732ff  call    _tlgKeywordOn
0x180073304  test    al, al
0x180073306  jz      short loc_180073367
0x180073308  mov     rcx, [rdi+8]
0x18007330c  xor     eax, eax
0x18007330e  mov     rdx, [rcx+1718h]
0x180073315  cmp     rdx, [rcx+1720h]
0x18007331c  mov     dword ptr [rbp+arg_28], ebx
0x18007331f  cmovz   rdx, rax
0x180073323  mov     [rbp+var_38], 1000000h
0x18007332b  mov     rax, [rbp+var_28]
0x18007332f  mov     [rbp+var_40], rax
0x180073333  lea     rax, [rbp+arg_30]
0x180073337  mov     [rsp+80h+var_48], rax
0x18007333c  lea     rax, [rbp+var_40]
0x180073340  mov     [rsp+80h+var_50], rax
0x180073345  lea     rax, [rbp+arg_28]
0x180073349  mov     [rsp+80h+var_58], rax
0x18007334e  lea     rax, [rbp+var_38]
0x180073352  mov     [rbp+arg_30], rdx
0x180073356  lea     rdx, byte_1800CD811
0x18007335d  mov     [rsp+80h+var_60], rax
0x180073362  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180073367  mov     rcx, cs:WPP_GLOBAL_Control
0x18007336e  cmp     rcx, r15
0x180073371  jz      short loc_1800733B5
0x180073373  test    byte ptr [rcx+1Ch], 4
0x180073377  jz      short loc_1800733B5
0x180073379  mov     rdx, [rdi+8]
0x18007337d  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x180073384  mov     rcx, [rcx+10h]
0x180073388  xor     eax, eax
0x18007338a  mov     r9, [rdx+1718h]
0x180073391  cmp     r9, [rdx+1720h]
0x180073398  lea     edx, [rax+14h]
0x18007339b  cmovz   r9, rax
0x18007339f  mov     rax, [rbp+var_28]
0x1800733a3  mov     [rsp+80h+var_58], r9
0x1800733a8  mov     r9d, ebx
0x1800733ab  mov     [rsp+80h+var_60], rax
0x1800733b0  call    WPP_SF_dSS
0x1800733b5  lea     rcx, [rbp+var_28]; void *
0x1800733b9  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x1800733be  test    r13, r13
0x1800733c1  jz      short loc_1800733D8
0x1800733c3  mov     r8, [rbp+var_30]
0x1800733c7  mov     edx, ebx; int
0x1800733c9  mov     rcx, r13; enum _WER_SUBMIT_RESULT *
0x1800733cc  mov     r8d, [r8+23A8h]; enum _WER_SUBMIT_RESULT
0x1800733d3  call    ?MapSubmitResult@CReportHandleInstance@@SAXPEAW4_WER_SUBMIT_RESULT@@JW42@@Z; CReportHandleInstance::MapSubmitResult(_WER_SUBMIT_RESULT *,long,_WER_SUBMIT_RESULT)
0x1800733d8  test    r12, r12
0x1800733db  jz      short loc_1800733E7
0x1800733dd  mov     r8, r12; enum _WERP_SUBMIT_RESULT *
0x1800733e0  mov     edx, ebx; int
0x1800733e2  call    ?MapInternalSubmitResult@CReportHandleInstance@@QEBAJJPEAW4_WERP_SUBMIT_RESULT@@@Z; CReportHandleInstance::MapInternalSubmitResult(long,_WERP_SUBMIT_RESULT *)
0x1800733e7  mov     ecx, 80000000h
0x1800733ec  lea     eax, [rbx+rcx]
0x1800733ef  test    ecx, eax
0x1800733f1  jnz     short loc_1800733FB
0x1800733f3  cmp     ebx, 801B8001h
0x1800733f9  jnz     short loc_1800733FD
0x1800733fb  xor     ebx, ebx
0x1800733fd  cmp     [rbp+arg_8], 0
0x180073401  jz      short loc_18007340C
0x180073403  mov     rcx, [rdi+8]; this
0x180073407  call    ?ReleaseReportLock@CReport@@QEAAJXZ; CReport::ReleaseReportLock(void)
0x18007340c  mov     rcx, [rdi+38h]; hEvent
0x180073410  lea     rax, [rcx+1]
0x180073414  cmp     rax, 1
0x180073418  jbe     short loc_180073426
0x18007341a  call    cs:__imp_SetEvent
0x180073421  nop     dword ptr [rax+rax+00h]
0x180073426  mov     eax, ebx
0x180073428  mov     rbx, [rsp+80h+arg_10]
0x180073430  add     rsp, 80h
0x180073437  pop     r15
0x180073439  pop     r14
0x18007343b  pop     r13
0x18007343d  pop     r12
0x18007343f  pop     rdi
0x180073440  pop     rsi
0x180073441  pop     rbp
0x180073442  retn
```
