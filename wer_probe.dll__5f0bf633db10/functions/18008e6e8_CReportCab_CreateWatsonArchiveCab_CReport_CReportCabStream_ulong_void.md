# CReportCab::CreateWatsonArchiveCab(CReport *,CReportCabStream *,ulong,void *)

- ea: `0x18008e6e8`
- end: `0x18008eb5e`
- name: `?CreateWatsonArchiveCab@CReportCab@@QEAAJPEAVCReport@@PEAVCReportCabStream@@KPEAX@Z`
- size: `1142`
- prototype: `__int64 __fastcall(CReportCab *this, struct CReport *, struct CReportCabStream *, int, HANDLE hHandle)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18007d2a8`

## callees

- `0x180004bb4`
- `0x180013730`
- `0x18001f9dc`
- `0x18001fe24`
- `0x180026498`
- `0x18002dbac`
- `0x18003bf14`
- `0x180043d28`
- `0x180045bb4`
- `0x180048cd0`
- `0x180048d10`
- `0x18008e6e8`
- `0x1800ad010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008eafd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e725`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008e798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008eafd`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008e7a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008eb09`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008e7a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008eb09`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008e72e`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008e72e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e745`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008e7ae`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e814`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18008e814`

## pseudocode

```c
__int64 __fastcall CReportCab::CreateWatsonArchiveCab(
        CReportCab *this,
        struct CReport *a2,
        struct CReportCabStream *a3,
        int a4,
        HANDLE hHandle)
{
  HANDLE CurrentThread; // rax
  int v9; // r12d
  signed int LastError; // eax
  unsigned int v11; // ebx
  wchar_t *v12; // rcx
  __int64 v13; // rdx
  __int64 v14; // r9
  HANDLE v15; // rax
  signed int v16; // eax
  _QWORD *v17; // r15
  __int64 v18; // rax
  int v19; // eax
  struct CReportFile *v20; // rbx
  __int64 v21; // r13
  struct CReportFile *v22; // rbp
  unsigned int v23; // r15d
  int FileByIndex; // eax
  __int64 v25; // rdx
  __int64 v26; // rcx
  __int64 v27; // r9
  wchar_t *v28; // rcx
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  HANDLE v33; // rax
  struct CReportFile *v35; // [rsp+30h] [rbp-48h] BYREF
  struct CReportFile *v36; // [rsp+38h] [rbp-40h] BYREF
  int ThreadPriority; // [rsp+88h] [rbp+10h]

  v36 = 0;
  if ( !a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids);
    return 2147942487LL;
  }
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v9 = ThreadPriority;
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    LastError = GetLastError();
    v11 = LastError;
    if ( LastError > 0 )
      v11 = (unsigned __int16)LastError | 0x80070000;
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 28;
      v14 = v11;
      goto LABEL_9;
    }
    goto LABEL_75;
  }
  v15 = GetCurrentThread();
  if ( !SetThreadPriority(v15, -1) )
  {
    v16 = GetLastError();
    v11 = v16;
    if ( v16 > 0 )
      v11 = (unsigned __int16)v16 | 0x80070000;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v11);
    v9 = 0x7FFFFFFF;
    goto LABEL_75;
  }
  if ( hHandle )
  {
    *(_QWORD *)this = hHandle;
    if ( !WaitForSingleObject(hHandle, 0) )
    {
      v11 = -2145681407;
      goto LABEL_75;
    }
  }
  v17 = (_QWORD *)((char *)this + 40);
  if ( *((_DWORD *)a3 + 4) )
    v18 = utl::make_unique<CZipArchiveFile,,0>(&v35);
  else
    v18 = utl::make_unique<CCabArchiveFile,,0>(&v35);
  utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(
    (char *)this + 40,
    v18);
  utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(&v35);
  if ( !*v17 )
  {
    v11 = -2147024882;
    goto LABEL_75;
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD, struct CReportCabStream *, _QWORD, _QWORD, HANDLE))(*(_QWORD *)*v17 + 8LL))(
          *v17,
          a3,
          0,
          0,
          hHandle);
  v11 = v19;
  if ( v19 < 0 )
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 30;
      goto LABEL_28;
    }
    goto LABEL_75;
  }
  v20 = 0;
  v21 = (__int64)(*((_QWORD *)a2 + 728) - *((_QWORD *)a2 + 727)) >> 3;
  v22 = 0;
  v23 = 0;
  v35 = 0;
  if ( !(_DWORD)v21 )
    goto LABEL_58;
  do
  {
    FileByIndex = CReport::GetFileByIndex(a2, v23, &v36);
    if ( FileByIndex < 0 || (v20 = v36) == 0 )
    {
      v28 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v29 = 31;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v28 + 2), v29, &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, (unsigned int)FileByIndex);
      }
LABEL_55:
      v20 = v35;
      goto LABEL_56;
    }
    if ( (a4 & *((_DWORD *)v36 + 1)) != a4 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v27 = *((_QWORD *)v36 + 10);
        if ( v27 == *((_QWORD *)v36 + 11) )
          v27 = *((_QWORD *)v36 + 14);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v27);
      }
      goto LABEL_55;
    }
    if ( *((_DWORD *)a2 + 1468) != 4 )
      goto LABEL_47;
    if ( *(_DWORD *)v36 != 2 )
    {
      if ( *(_DWORD *)v36 == 3 )
      {
        if ( v22 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25);
        v22 = v20;
        goto LABEL_55;
      }
LABEL_47:
      FileByIndex = CReportCab::AddReportFileToCab(this, a2, v36);
      if ( FileByIndex < 0 )
      {
        v28 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v29 = 33;
          goto LABEL_54;
        }
      }
      goto LABEL_55;
    }
    if ( v35 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25);
    v35 = v20;
LABEL_56:
    ++v23;
  }
  while ( v23 < (unsigned int)v21 );
  v9 = ThreadPriority;
LABEL_58:
  if ( *((_DWORD *)a2 + 1468) == 4 )
  {
    if ( !v22 )
      goto LABEL_64;
    v30 = CReportCab::AddReportFileToCab(this, a2, v22);
    if ( v30 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
          (unsigned int)v30);
LABEL_64:
      if ( v20 )
      {
        v31 = CReportCab::AddReportFileToCab(this, a2, v20);
        if ( v31 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
            (unsigned int)v31);
      }
    }
  }
  v19 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 5) + 40LL))(*((_QWORD *)this + 5));
  v11 = v19;
  if ( v19 >= 0 )
  {
    v11 = 0;
  }
  else
  {
    v12 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    {
      v13 = 36;
LABEL_28:
      v14 = (unsigned int)v19;
LABEL_9:
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, &WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v14);
    }
  }
LABEL_75:
  v32 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v32 )
    utl::default_delete<ITpCommand>::operator()();
  if ( v9 != 0x7FFFFFFF )
  {
    v33 = GetCurrentThread();
    SetThreadPriority(v33, v9);
  }
  return v11;
}

```

## disassembly

```asm
0x18008e6e8  mov     [rsp+arg_0], rbx
0x18008e6ed  mov     [rsp+arg_18], r9d
0x18008e6f2  push    rbp
0x18008e6f3  push    rsi
0x18008e6f4  push    rdi
0x18008e6f5  push    r12
0x18008e6f7  push    r13
0x18008e6f9  push    r14
0x18008e6fb  push    r15
0x18008e6fd  sub     rsp, 40h
0x18008e701  mov     [rsp+78h+var_40], 0
0x18008e70a  mov     rdi, r8
0x18008e70d  mov     rsi, rdx
0x18008e710  mov     r14, rcx
0x18008e713  test    rdx, rdx
0x18008e716  jz      loc_18008EB13
0x18008e71c  test    r8, r8
0x18008e71f  jz      loc_18008EB13
0x18008e725  call    cs:__imp_GetCurrentThread
0x18008e72b  mov     rcx, rax; hThread
0x18008e72e  call    cs:__imp_GetThreadPriority
0x18008e734  mov     [rsp+78h+arg_8], eax
0x18008e73b  mov     r12d, eax
0x18008e73e  cmp     eax, 7FFFFFFFh
0x18008e743  jnz     short loc_18008E798
0x18008e745  call    cs:__imp_GetLastError
0x18008e74b  mov     ebx, eax
0x18008e74d  test    eax, eax
0x18008e74f  jle     short loc_18008E75A
0x18008e751  movzx   ebx, ax
0x18008e754  or      ebx, 80070000h
0x18008e75a  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e761  lea     rdi, WPP_GLOBAL_Control
0x18008e768  cmp     rcx, rdi
0x18008e76b  jz      loc_18008EADE
0x18008e771  test    byte ptr [rcx+1Ch], 1
0x18008e775  jz      loc_18008EADE
0x18008e77b  mov     edx, 1Ch
0x18008e780  mov     r9d, ebx
0x18008e783  mov     rcx, [rcx+10h]
0x18008e787  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e78e  call    WPP_SF_d
0x18008e793  jmp     loc_18008EADE
0x18008e798  call    cs:__imp_GetCurrentThread
0x18008e79e  mov     rcx, rax; hThread
0x18008e7a1  or      edx, 0FFFFFFFFh; nPriority
0x18008e7a4  call    cs:__imp_SetThreadPriority
0x18008e7aa  test    eax, eax
0x18008e7ac  jnz     short loc_18008E7FF
0x18008e7ae  call    cs:__imp_GetLastError
0x18008e7b4  mov     ebx, eax
0x18008e7b6  test    eax, eax
0x18008e7b8  jle     short loc_18008E7C3
0x18008e7ba  movzx   ebx, ax
0x18008e7bd  or      ebx, 80070000h
0x18008e7c3  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e7ca  lea     rdi, WPP_GLOBAL_Control
0x18008e7d1  cmp     rcx, rdi
0x18008e7d4  jz      short loc_18008E7F4
0x18008e7d6  test    byte ptr [rcx+1Ch], 1
0x18008e7da  jz      short loc_18008E7F4
0x18008e7dc  mov     rcx, [rcx+10h]
0x18008e7e0  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e7e7  mov     edx, 1Dh
0x18008e7ec  mov     r9d, ebx
0x18008e7ef  call    WPP_SF_d
0x18008e7f4  mov     r12d, 7FFFFFFFh
0x18008e7fa  jmp     loc_18008EADE
0x18008e7ff  mov     rbx, [rsp+78h+hHandle]
0x18008e807  test    rbx, rbx
0x18008e80a  jz      short loc_18008E828
0x18008e80c  xor     edx, edx; dwMilliseconds
0x18008e80e  mov     [r14], rbx
0x18008e811  mov     rcx, rbx; hHandle
0x18008e814  call    cs:__imp_WaitForSingleObject
0x18008e81a  test    eax, eax
0x18008e81c  jnz     short loc_18008E828
0x18008e81e  mov     ebx, 801B8001h
0x18008e823  jmp     loc_18008EADE
0x18008e828  cmp     dword ptr [rdi+10h], 0
0x18008e82c  lea     r15, [r14+28h]
0x18008e830  lea     rcx, [rsp+78h+var_48]
0x18008e835  jz      short loc_18008E853
0x18008e837  call    ??$make_unique@VCZipArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@0@XZ; utl::make_unique<CZipArchiveFile,,0>(void)
0x18008e83c  mov     rdx, rax
0x18008e83f  mov     rcx, r15
0x18008e842  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x18008e847  lea     rcx, [rsp+78h+var_48]
0x18008e84c  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x18008e851  jmp     short loc_18008E86D
0x18008e853  call    ??$make_unique@VCCabArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCCabArchiveFile@@U?$default_delete@VCCabArchiveFile@@@utl@@@0@XZ; utl::make_unique<CCabArchiveFile,,0>(void)
0x18008e858  mov     rdx, rax
0x18008e85b  mov     rcx, r15
0x18008e85e  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x18008e863  lea     rcx, [rsp+78h+var_48]
0x18008e868  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x18008e86d  mov     rcx, [r15]
0x18008e870  test    rcx, rcx
0x18008e873  jz      loc_18008EAD9
0x18008e879  mov     rax, [rcx]
0x18008e87c  xor     r9d, r9d
0x18008e87f  xor     r8d, r8d
0x18008e882  mov     [rsp+78h+var_58], rbx
0x18008e887  mov     rdx, rdi
0x18008e88a  mov     rax, [rax+8]
0x18008e88e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008e893  mov     ebx, eax
0x18008e895  test    eax, eax
0x18008e897  jns     short loc_18008E8C7
0x18008e899  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e8a0  lea     rdi, WPP_GLOBAL_Control
0x18008e8a7  cmp     rcx, rdi
0x18008e8aa  jz      loc_18008EADE
0x18008e8b0  test    byte ptr [rcx+1Ch], 1
0x18008e8b4  jz      loc_18008EADE
0x18008e8ba  mov     edx, 1Eh
0x18008e8bf  mov     r9d, eax
0x18008e8c2  jmp     loc_18008E783
0x18008e8c7  mov     r13, [rsi+16C0h]
0x18008e8ce  lea     rdi, WPP_GLOBAL_Control
0x18008e8d5  sub     r13, [rsi+16B8h]
0x18008e8dc  xor     ebx, ebx
0x18008e8de  sar     r13, 3
0x18008e8e2  xor     ebp, ebp
0x18008e8e4  xor     r15d, r15d
0x18008e8e7  mov     [rsp+78h+var_48], rbx
0x18008e8ec  test    r13d, r13d
0x18008e8ef  jz      loc_18008EA14
0x18008e8f5  mov     r12d, [rsp+78h+arg_18]
0x18008e8fd  lea     r8, [rsp+78h+var_40]; struct CReportFile **
0x18008e902  mov     edx, r15d; unsigned int
0x18008e905  mov     rcx, rsi; this
0x18008e908  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x18008e90d  test    eax, eax
0x18008e90f  js      loc_18008E9D1
0x18008e915  mov     rbx, [rsp+78h+var_40]
0x18008e91a  test    rbx, rbx
0x18008e91d  jz      loc_18008E9D1
0x18008e923  mov     eax, [rbx+4]
0x18008e926  and     eax, r12d
0x18008e929  cmp     eax, r12d
0x18008e92c  jz      short loc_18008E970
0x18008e92e  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e935  cmp     rcx, rdi
0x18008e938  jz      loc_18008E9FB
0x18008e93e  test    byte ptr [rcx+1Ch], 4
0x18008e942  jz      loc_18008E9FB
0x18008e948  mov     r9, [rbx+50h]
0x18008e94c  cmp     r9, [rbx+58h]
0x18008e950  jnz     short loc_18008E956
0x18008e952  mov     r9, [rbx+70h]
0x18008e956  mov     rcx, [rcx+10h]
0x18008e95a  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e961  mov     edx, 20h ; ' '
0x18008e966  call    WPP_SF_S
0x18008e96b  jmp     loc_18008E9FB
0x18008e970  cmp     dword ptr [rsi+16F0h], 4
0x18008e977  jnz     short loc_18008E9A6
0x18008e979  cmp     dword ptr [rbx], 2
0x18008e97c  jnz     short loc_18008E992
0x18008e97e  cmp     [rsp+78h+var_48], 0
0x18008e984  jz      short loc_18008E98B
0x18008e986  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e98b  mov     [rsp+78h+var_48], rbx
0x18008e990  jmp     short loc_18008EA00
0x18008e992  cmp     dword ptr [rbx], 3
0x18008e995  jnz     short loc_18008E9A6
0x18008e997  test    rbp, rbp
0x18008e99a  jz      short loc_18008E9A1
0x18008e99c  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18008e9a1  mov     rbp, rbx
0x18008e9a4  jmp     short loc_18008E9FB
0x18008e9a6  mov     r8, rbx; struct CReportFile *
0x18008e9a9  mov     rdx, rsi; struct CReport *
0x18008e9ac  mov     rcx, r14; this
0x18008e9af  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008e9b4  test    eax, eax
0x18008e9b6  jns     short loc_18008E9FB
0x18008e9b8  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9bf  cmp     rcx, rdi
0x18008e9c2  jz      short loc_18008E9FB
0x18008e9c4  test    byte ptr [rcx+1Ch], 2
0x18008e9c8  jz      short loc_18008E9FB
0x18008e9ca  mov     edx, 21h ; '!'
0x18008e9cf  jmp     short loc_18008E9E8
0x18008e9d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18008e9d8  cmp     rcx, rdi
0x18008e9db  jz      short loc_18008E9FB
0x18008e9dd  test    byte ptr [rcx+1Ch], 2
0x18008e9e1  jz      short loc_18008E9FB
0x18008e9e3  mov     edx, 1Fh
0x18008e9e8  mov     rcx, [rcx+10h]
0x18008e9ec  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008e9f3  mov     r9d, eax
0x18008e9f6  call    WPP_SF_d
0x18008e9fb  mov     rbx, [rsp+78h+var_48]
0x18008ea00  inc     r15d
0x18008ea03  cmp     r15d, r13d
0x18008ea06  jb      loc_18008E8FD
0x18008ea0c  mov     r12d, [rsp+78h+arg_8]
0x18008ea14  cmp     dword ptr [rsi+16F0h], 4
0x18008ea1b  jnz     loc_18008EAA3
0x18008ea21  test    rbp, rbp
0x18008ea24  jz      short loc_18008EA62
0x18008ea26  mov     r8, rbp; struct CReportFile *
0x18008ea29  mov     rdx, rsi; struct CReport *
0x18008ea2c  mov     rcx, r14; this
0x18008ea2f  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008ea34  test    eax, eax
0x18008ea36  jns     short loc_18008EAA3
0x18008ea38  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea3f  cmp     rcx, rdi
0x18008ea42  jz      short loc_18008EA62
0x18008ea44  test    byte ptr [rcx+1Ch], 2
0x18008ea48  jz      short loc_18008EA62
0x18008ea4a  mov     rcx, [rcx+10h]
0x18008ea4e  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008ea55  mov     edx, 22h ; '"'
0x18008ea5a  mov     r9d, eax
0x18008ea5d  call    WPP_SF_d
0x18008ea62  test    rbx, rbx
0x18008ea65  jz      short loc_18008EAA3
0x18008ea67  mov     r8, rbx; struct CReportFile *
0x18008ea6a  mov     rdx, rsi; struct CReport *
0x18008ea6d  mov     rcx, r14; this
0x18008ea70  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x18008ea75  test    eax, eax
0x18008ea77  jns     short loc_18008EAA3
0x18008ea79  mov     rcx, cs:WPP_GLOBAL_Control
0x18008ea80  cmp     rcx, rdi
0x18008ea83  jz      short loc_18008EAA3
0x18008ea85  test    byte ptr [rcx+1Ch], 2
0x18008ea89  jz      short loc_18008EAA3
0x18008ea8b  mov     rcx, [rcx+10h]
0x18008ea8f  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008ea96  mov     edx, 23h ; '#'
0x18008ea9b  mov     r9d, eax
0x18008ea9e  call    WPP_SF_d
0x18008eaa3  mov     rcx, [r14+28h]
0x18008eaa7  mov     rax, [rcx]
0x18008eaaa  mov     rax, [rax+28h]
0x18008eaae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008eab3  mov     ebx, eax
0x18008eab5  test    eax, eax
0x18008eab7  jns     short loc_18008EAD5
0x18008eab9  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eac0  cmp     rcx, rdi
0x18008eac3  jz      short loc_18008EADE
0x18008eac5  test    byte ptr [rcx+1Ch], 1
0x18008eac9  jz      short loc_18008EADE
0x18008eacb  mov     edx, 24h ; '$'
0x18008ead0  jmp     loc_18008E8BF
0x18008ead5  xor     ebx, ebx
0x18008ead7  jmp     short loc_18008EADE
0x18008ead9  mov     ebx, 8007000Eh
0x18008eade  mov     rdx, [r14+28h]
0x18008eae2  mov     qword ptr [r14+28h], 0
0x18008eaea  test    rdx, rdx
0x18008eaed  jz      short loc_18008EAF4
0x18008eaef  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x18008eaf4  cmp     r12d, 7FFFFFFFh
0x18008eafb  jz      short loc_18008EB0F
0x18008eafd  call    cs:__imp_GetCurrentThread
0x18008eb03  mov     rcx, rax; hThread
0x18008eb06  mov     edx, r12d; nPriority
0x18008eb09  call    cs:__imp_SetThreadPriority
0x18008eb0f  mov     eax, ebx
0x18008eb11  jmp     short loc_18008EB46
0x18008eb13  mov     rcx, cs:WPP_GLOBAL_Control
0x18008eb1a  lea     rdi, WPP_GLOBAL_Control
0x18008eb21  cmp     rcx, rdi
0x18008eb24  jz      short loc_18008EB41
0x18008eb26  test    byte ptr [rcx+1Ch], 1
0x18008eb2a  jz      short loc_18008EB41
0x18008eb2c  mov     rcx, [rcx+10h]
0x18008eb30  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x18008eb37  mov     edx, 1Bh
0x18008eb3c  call    WPP_SF_
0x18008eb41  mov     eax, 80070057h
0x18008eb46  mov     rbx, [rsp+78h+arg_0]
0x18008eb4e  add     rsp, 40h
0x18008eb52  pop     r15
0x18008eb54  pop     r14
0x18008eb56  pop     r13
0x18008eb58  pop     r12
0x18008eb5a  pop     rdi
0x18008eb5b  pop     rsi
0x18008eb5c  pop     rbp
0x18008eb5d  retn
```
