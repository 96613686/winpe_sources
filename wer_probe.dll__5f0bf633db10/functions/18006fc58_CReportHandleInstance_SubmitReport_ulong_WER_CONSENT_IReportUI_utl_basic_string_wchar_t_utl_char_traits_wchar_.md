# CReportHandleInstance::SubmitReport(ulong,_WER_CONSENT,IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,_WER_SUBMIT_RESULT *,_WERP_SUBMIT_RESULT *)

- ea: `0x18006fc58`
- end: `0x1800700de`
- name: `?SubmitReport@CReportHandleInstance@@QEAAJKW4_WER_CONSENT@@PEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAW4_WER_SUBMIT_RESULT@@PEAW4_WERP_SUBMIT_RESULT@@@Z`
- size: `1158`
- prototype: `__int64(CReportHandleInstance *this, enum _WER_FILE_TYPE, enum _WER_CONSENT, __int64, __int64, ...)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180060ea0`
- `0x18006ad60`

## callees

- `0x180003a68`
- `0x180004bb4`
- `0x180006c34`
- `0x1800083c8`
- `0x18000d2c0`
- `0x18000dad0`
- `0x180010c3c`
- `0x18001565c`
- `0x18001fe24`
- `0x18002bba0`
- `0x18002c198`
- `0x18002cd50`
- `0x18002ece8`
- `0x18002f34c`
- `0x1800303dc`
- `0x1800318f4`
- `0x18003285c`
- `0x180045bdc`
- `0x180065510`
- `0x18006fb14`
- `0x18006fb84`
- `0x18006fc58`
- `0x180072164`
- `0x180073084`
- `0x1800739c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fedd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006fedd`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006fe51`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x18006fe51`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006feaf`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18006feaf`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fed0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800700bb`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18006fed0`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800700bb`

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
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
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
        WPP_SF_d(*((_QWORD *)v13 + 2), v14, &WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids, (unsigned int)v11);
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
    WPP_SF_(*((_QWORD *)v13 + 2), v15, &WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids);
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
  if ( (unsigned int)dword_1800D9000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D9000, 0x400000000000LL) )
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
      (unsigned int)&unk_1800C8761,
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
      (unsigned int)&WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids,
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
0x18006fc58  mov     [rsp-38h+arg_10], rbx
0x18006fc5d  mov     [rsp-38h+arg_18], r9
0x18006fc62  push    rbp
0x18006fc63  push    rsi
0x18006fc64  push    rdi
0x18006fc65  push    r12
0x18006fc67  push    r13
0x18006fc69  push    r14
0x18006fc6b  push    r15
0x18006fc6d  mov     rbp, rsp
0x18006fc70  sub     rsp, 80h
0x18006fc77  mov     r13, [rbp+arg_28]
0x18006fc7b  mov     r14d, r8d
0x18006fc7e  mov     rax, [rcx+8]
0x18006fc82  mov     esi, edx
0x18006fc84  mov     qword ptr [rbp+SystemTimeAsFileTime.dwLowDateTime], 0
0x18006fc8c  mov     rdi, rcx
0x18006fc8f  mov     [rbp+arg_8], 0
0x18006fc96  mov     [rbp+var_30], rax
0x18006fc9a  test    r13, r13
0x18006fc9d  jz      short loc_18006FCA7
0x18006fc9f  mov     dword ptr [r13+0], 4
0x18006fca7  mov     r12, [rbp+arg_30]
0x18006fcab  test    r12, r12
0x18006fcae  jz      short loc_18006FCB8
0x18006fcb0  mov     dword ptr [r12], 2
0x18006fcb8  mov     eax, 1
0x18006fcbd  lea     r15, WPP_GLOBAL_Control
0x18006fcc4  xchg    eax, [rcx+50h]
0x18006fcc7  test    eax, eax
0x18006fcc9  jz      short loc_18006FCFC
0x18006fccb  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fcd2  cmp     rcx, r15
0x18006fcd5  jz      short loc_18006FCF2
0x18006fcd7  test    byte ptr [rcx+1Ch], 1
0x18006fcdb  jz      short loc_18006FCF2
0x18006fcdd  mov     rcx, [rcx+10h]
0x18006fce1  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006fce8  mov     edx, 0Eh
0x18006fced  call    WPP_SF_
0x18006fcf2  mov     ebx, 8007139Fh
0x18006fcf7  jmp     loc_18006FF61
0x18006fcfc  xor     r15d, r15d
0x18006fcff  bt      esi, 15h
0x18006fd03  jb      short loc_18006FD52
0x18006fd05  mov     rcx, [rcx+8]; this
0x18006fd09  call    ?IsReportLocked@CReport@@QEAAHXZ; CReport::IsReportLocked(void)
0x18006fd0e  test    eax, eax
0x18006fd10  jnz     short loc_18006FD52
0x18006fd12  mov     rcx, [rdi+8]; this
0x18006fd16  call    ?TryReportLock@CReport@@QEAAJXZ; CReport::TryReportLock(void)
0x18006fd1b  mov     ebx, eax
0x18006fd1d  test    eax, eax
0x18006fd1f  jns     short loc_18006FD4B
0x18006fd21  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd28  lea     rax, WPP_GLOBAL_Control
0x18006fd2f  cmp     rcx, rax
0x18006fd32  jz      loc_18006FF51
0x18006fd38  test    byte ptr [rcx+1Ch], 1
0x18006fd3c  jz      loc_18006FF51
0x18006fd42  lea     edx, [r15+0Fh]
0x18006fd46  jmp     loc_18006FF3E
0x18006fd4b  mov     [rbp+arg_8], 1
0x18006fd52  cmp     r14d, 2
0x18006fd56  jnz     short loc_18006FD6F
0x18006fd58  bt      esi, 1Dh
0x18006fd5c  jnb     short loc_18006FD69
0x18006fd5e  mov     rcx, [rdi+8]; this
0x18006fd62  call    ?MarkFilesAsApprovedByType@CReport@@QEAAXW4_WER_FILE_TYPE@@@Z; CReport::MarkFilesAsApprovedByType(_WER_FILE_TYPE)
0x18006fd67  jmp     short loc_18006FD6F
0x18006fd69  mov     r14d, 1
0x18006fd6f  mov     rcx, [rdi+8]; this
0x18006fd73  call    ?ValidateSignatureParams@CReport@@QEAAJXZ; CReport::ValidateSignatureParams(void)
0x18006fd78  mov     ebx, eax
0x18006fd7a  test    eax, eax
0x18006fd7c  jns     short loc_18006FDB9
0x18006fd7e  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fd85  lea     rax, WPP_GLOBAL_Control
0x18006fd8c  cmp     rcx, rax
0x18006fd8f  jz      loc_18006FF51
0x18006fd95  test    byte ptr [rcx+1Ch], 1
0x18006fd99  jz      loc_18006FF51
0x18006fd9f  mov     edx, 10h
0x18006fda4  mov     rcx, [rcx+10h]
0x18006fda8  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006fdaf  call    WPP_SF_
0x18006fdb4  jmp     loc_18006FF51
0x18006fdb9  mov     rcx, [rdi+8]; this
0x18006fdbd  call    ?SetDefaultDynamicParameters@CReport@@QEAAJXZ; CReport::SetDefaultDynamicParameters(void)
0x18006fdc2  mov     rcx, [rdi+8]; this
0x18006fdc6  mov     edx, r14d; enum _WER_CONSENT
0x18006fdc9  call    ?SetConsentValue@CReport@@QEAAJW4_WER_CONSENT@@@Z; CReport::SetConsentValue(_WER_CONSENT)
0x18006fdce  mov     ebx, eax
0x18006fdd0  test    eax, eax
0x18006fdd2  jns     short loc_18006FDFC
0x18006fdd4  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fddb  lea     rax, WPP_GLOBAL_Control
0x18006fde2  cmp     rcx, rax
0x18006fde5  jz      loc_18006FF51
0x18006fdeb  test    byte ptr [rcx+1Ch], 1
0x18006fdef  jz      loc_18006FF51
0x18006fdf5  mov     edx, 11h
0x18006fdfa  jmp     short loc_18006FDA4
0x18006fdfc  mov     rcx, [rdi+8]; this
0x18006fe00  call    ?InitializeSettings@CReport@@QEAAJXZ; CReport::InitializeSettings(void)
0x18006fe05  mov     ebx, eax
0x18006fe07  test    eax, eax
0x18006fe09  jns     short loc_18006FE36
0x18006fe0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18006fe12  lea     rax, WPP_GLOBAL_Control
0x18006fe19  cmp     rcx, rax
0x18006fe1c  jz      loc_18006FF51
0x18006fe22  test    byte ptr [rcx+1Ch], 1
0x18006fe26  jz      loc_18006FF51
0x18006fe2c  mov     edx, 12h
0x18006fe31  jmp     loc_18006FF3E
0x18006fe36  mov     rax, [rdi+8]
0x18006fe3a  mov     [rax+19D8h], esi
0x18006fe40  mov     rax, [rdi+8]
0x18006fe44  cmp     [rax+0B658h], r15d
0x18006fe4b  jnz     short loc_18006FE93
0x18006fe4d  lea     rcx, [rbp+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x18006fe51  call    cs:__imp_GetSystemTimeAsFileTime
0x18006fe57  mov     rcx, [rdi+8]; this
0x18006fe5b  lea     rdx, [rbp+SystemTimeAsFileTime]; struct _FILETIME *
0x18006fe5f  call    ?SetFileTime@CReport@@QEAAXPEAU_FILETIME@@@Z; CReport::SetFileTime(_FILETIME *)
0x18006fe64  mov     rax, [rdi+8]
0x18006fe68  mov     ebx, 80000000h
0x18006fe6d  cmp     [rax+16F0h], r15d
0x18006fe74  jnz     short loc_18006FE7B
0x18006fe76  and     esi, 0FFFFFFFCh
0x18006fe79  or      esi, ebx
0x18006fe7b  call    ?UtilIsCurrentProcessInteractive@@YAHXZ; UtilIsCurrentProcessInteractive(void)
0x18006fe80  mov     ecx, esi
0x18006fe82  or      ecx, ebx
0x18006fe84  test    eax, eax
0x18006fe86  mov     rax, [rdi+8]
0x18006fe8a  cmovnz  ecx, esi
0x18006fe8d  mov     [rax+19D8h], ecx
0x18006fe93  cmp     [rdi+20h], r15
0x18006fe97  jnz     short loc_18006FEAB
0x18006fe99  mov     rcx, rdi; this
0x18006fe9c  call    ?InitiateReportManager@CReportHandleInstance@@QEAAJXZ; CReportHandleInstance::InitiateReportManager(void)
0x18006fea1  mov     ebx, eax
0x18006fea3  test    eax, eax
0x18006fea5  js      loc_18006FF5A
0x18006feab  mov     rcx, [rdi+38h]; hEvent
0x18006feaf  call    cs:__imp_ResetEvent
0x18006feb5  mov     rdx, [rdi+40h]; void *
0x18006feb9  lea     rcx, aCancelevent; "CancelEvent"
0x18006fec0  xor     r8d, r8d; unsigned int
0x18006fec3  call    ?UtilWaitForSingleObject@@YAKPEB_WPEAXK@Z; UtilWaitForSingleObject(wchar_t const *,void *,ulong)
0x18006fec8  test    eax, eax
0x18006feca  jnz     short loc_18006FEDD
0x18006fecc  mov     rcx, [rdi+38h]; hEvent
0x18006fed0  call    cs:__imp_SetEvent
0x18006fed6  mov     ebx, 801B8001h
0x18006fedb  jmp     short loc_18006FF5A
0x18006fedd  call    cs:__imp_GetCurrentThreadId
0x18006fee3  mov     rcx, rdi; this
0x18006fee6  mov     [rdi+28h], eax
0x18006fee9  call    ?LogReportSubmitAsimovEvent@CReportHandleInstance@@AEAAXXZ; CReportHandleInstance::LogReportSubmitAsimovEvent(void)
0x18006feee  mov     r8, [rbp+arg_20]
0x18006fef2  mov     rdx, [rbp+arg_18]
0x18006fef6  mov     rcx, [rdi+20h]; this
0x18006fefa  call    ?ReportProblem@CReportManager@@QEAAJPEAVIReportUI@@PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReportManager::ReportProblem(IReportUI *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18006feff  mov     edx, eax; int
0x18006ff01  mov     rcx, rdi; this
0x18006ff04  mov     ebx, eax
0x18006ff06  call    ?DoFinalCallback@CReportHandleInstance@@AEAAJJ@Z; CReportHandleInstance::DoFinalCallback(long)
0x18006ff0b  test    ebx, ebx
0x18006ff0d  jns     loc_18007005F
0x18006ff13  mov     r15d, 1
0x18006ff19  cmp     ebx, 801B8001h
0x18006ff1f  jz      short loc_18006FF51
0x18006ff21  mov     rcx, cs:WPP_GLOBAL_Control
0x18006ff28  lea     rax, WPP_GLOBAL_Control
0x18006ff2f  cmp     rcx, rax
0x18006ff32  jz      short loc_18006FF51
0x18006ff34  test    [rcx+1Ch], r15b
0x18006ff38  jz      short loc_18006FF51
0x18006ff3a  lea     edx, [r15+12h]
0x18006ff3e  mov     rcx, [rcx+10h]
0x18006ff42  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x18006ff49  mov     r9d, ebx
0x18006ff4c  call    WPP_SF_d
0x18006ff51  test    r15d, r15d
0x18006ff54  jnz     loc_18007005F
0x18006ff5a  lea     r15, WPP_GLOBAL_Control
0x18006ff61  mov     rcx, [rdi+8]
0x18006ff65  lea     rax, [rbp+var_18]
0x18006ff69  mov     [rbp+var_28], rax
0x18006ff6d  lea     rdx, [rbp+var_28]
0x18006ff71  lea     rax, [rbp+var_18]
0x18006ff75  mov     [rbp+var_20], rax
0x18006ff79  xor     eax, eax
0x18006ff7b  mov     [rbp+var_18], ax
0x18006ff7f  call    ?GetUniqueIdentifier@CReport@@QEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; CReport::GetUniqueIdentifier(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x18006ff84  mov     eax, cs:dword_1800D9000
0x18006ff8a  cmp     eax, 5
0x18006ff8d  jbe     short loc_180070008
0x18006ff8f  mov     rdx, 400000000000h
0x18006ff99  lea     rcx, dword_1800D9000
0x18006ffa0  call    _tlgKeywordOn
0x18006ffa5  test    al, al
0x18006ffa7  jz      short loc_180070008
0x18006ffa9  mov     rcx, [rdi+8]
0x18006ffad  xor     eax, eax
0x18006ffaf  mov     rdx, [rcx+1718h]
0x18006ffb6  cmp     rdx, [rcx+1720h]
0x18006ffbd  mov     dword ptr [rbp+arg_28], ebx
0x18006ffc0  cmovz   rdx, rax
0x18006ffc4  mov     [rbp+var_38], 1000000h
0x18006ffcc  mov     rax, [rbp+var_28]
0x18006ffd0  mov     [rbp+var_40], rax
0x18006ffd4  lea     rax, [rbp+arg_30]
0x18006ffd8  mov     [rsp+80h+var_48], rax
0x18006ffdd  lea     rax, [rbp+var_40]
0x18006ffe1  mov     [rsp+80h+var_50], rax
0x18006ffe6  lea     rax, [rbp+arg_28]
0x18006ffea  mov     [rsp+80h+var_58], rax
0x18006ffef  lea     rax, [rbp+var_38]
0x18006fff3  mov     [rbp+arg_30], rdx
0x18006fff7  lea     rdx, unk_1800C8761
0x18006fffe  mov     [rsp+80h+var_60], rax
0x180070003  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@_W@@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@_W@@5@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180070008  mov     rcx, cs:WPP_GLOBAL_Control
0x18007000f  cmp     rcx, r15
0x180070012  jz      short loc_180070056
0x180070014  test    byte ptr [rcx+1Ch], 4
0x180070018  jz      short loc_180070056
0x18007001a  mov     rdx, [rdi+8]
0x18007001e  lea     r8, WPP_a389fed9ae6c36c3061e2ddfdaf79977_Traceguids
0x180070025  mov     rcx, [rcx+10h]
0x180070029  xor     eax, eax
0x18007002b  mov     r9, [rdx+1718h]
0x180070032  cmp     r9, [rdx+1720h]
0x180070039  lea     edx, [rax+14h]
0x18007003c  cmovz   r9, rax
0x180070040  mov     rax, [rbp+var_28]
0x180070044  mov     [rsp+80h+var_58], r9
0x180070049  mov     r9d, ebx
0x18007004c  mov     [rsp+80h+var_60], rax
0x180070051  call    WPP_SF_dSS
0x180070056  lea     rcx, [rbp+var_28]; void *
0x18007005a  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x18007005f  test    r13, r13
0x180070062  jz      short loc_180070079
0x180070064  mov     r8, [rbp+var_30]
0x180070068  mov     edx, ebx; int
0x18007006a  mov     rcx, r13; enum _WER_SUBMIT_RESULT *
0x18007006d  mov     r8d, [r8+23A8h]; enum _WER_SUBMIT_RESULT
0x180070074  call    ?MapSubmitResult@CReportHandleInstance@@SAXPEAW4_WER_SUBMIT_RESULT@@JW42@@Z; CReportHandleInstance::MapSubmitResult(_WER_SUBMIT_RESULT *,long,_WER_SUBMIT_RESULT)
0x180070079  test    r12, r12
0x18007007c  jz      short loc_180070088
0x18007007e  mov     r8, r12; enum _WERP_SUBMIT_RESULT *
0x180070081  mov     edx, ebx; int
0x180070083  call    ?MapInternalSubmitResult@CReportHandleInstance@@QEBAJJPEAW4_WERP_SUBMIT_RESULT@@@Z; CReportHandleInstance::MapInternalSubmitResult(long,_WERP_SUBMIT_RESULT *)
0x180070088  mov     ecx, 80000000h
0x18007008d  lea     eax, [rbx+rcx]
0x180070090  test    ecx, eax
0x180070092  jnz     short loc_18007009C
0x180070094  cmp     ebx, 801B8001h
0x18007009a  jnz     short loc_18007009E
0x18007009c  xor     ebx, ebx
0x18007009e  cmp     [rbp+arg_8], 0
0x1800700a2  jz      short loc_1800700AD
0x1800700a4  mov     rcx, [rdi+8]; this
0x1800700a8  call    ?ReleaseReportLock@CReport@@QEAAJXZ; CReport::ReleaseReportLock(void)
0x1800700ad  mov     rcx, [rdi+38h]; hEvent
0x1800700b1  lea     rax, [rcx+1]
0x1800700b5  cmp     rax, 1
0x1800700b9  jbe     short loc_1800700C1
0x1800700bb  call    cs:__imp_SetEvent
0x1800700c1  mov     eax, ebx
0x1800700c3  mov     rbx, [rsp+80h+arg_10]
0x1800700cb  add     rsp, 80h
0x1800700d2  pop     r15
0x1800700d4  pop     r14
0x1800700d6  pop     r13
0x1800700d8  pop     r12
0x1800700da  pop     rdi
0x1800700db  pop     rsi
0x1800700dc  pop     rbp
0x1800700dd  retn
```
