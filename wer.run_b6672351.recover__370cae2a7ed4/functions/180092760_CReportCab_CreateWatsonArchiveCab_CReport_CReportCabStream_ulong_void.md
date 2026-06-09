# CReportCab::CreateWatsonArchiveCab(CReport *,CReportCabStream *,ulong,void *)

- ea: `0x180092760`
- end: `0x180092c0d`
- name: `?CreateWatsonArchiveCab@CReportCab@@QEAAJPEAVCReport@@PEAVCReportCabStream@@KPEAX@Z`
- size: `1197`
- prototype: `__int64 __usercall@<rax>(CReportCab *__hidden this@<rcx>, struct CReport *@<rdx>, struct CReportCabStream *@<r8>, unsigned int@<r9d>, void *)`
- caller_count: `1`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x180080bc0`

## callees

- `0x180004c64`
- `0x1800170b0`
- `0x180020224`
- `0x180020680`
- `0x180025848`
- `0x18002f680`
- `0x18003de9c`
- `0x1800456c8`
- `0x180047984`
- `0x18004af20`
- `0x18004af64`
- `0x180092760`
- `0x1800b2010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009279d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092b9f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18009279d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092822`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180092b9f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180092834`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180092bb1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180092834`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180092bb1`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800927ac`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x1800927ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092844`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800927c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180092844`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800928b0`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800928b0`

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
  __int64 v27; // r8
  __int64 v28; // r9
  wchar_t *v29; // rcx
  __int64 v30; // rdx
  int v31; // eax
  int v32; // eax
  __int64 v33; // rdx
  HANDLE v34; // rax
  struct CReportFile *v36; // [rsp+30h] [rbp-48h] BYREF
  struct CReportFile *v37; // [rsp+38h] [rbp-40h] BYREF
  int ThreadPriority; // [rsp+88h] [rbp+10h]

  v37 = 0;
  if ( !a2 || !a3 )
  {
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids);
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
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v11);
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
    v18 = utl::make_unique<CZipArchiveFile,,0>(&v36);
  else
    v18 = utl::make_unique<CCabArchiveFile,,0>(&v36);
  utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(
    (char *)this + 40,
    v18);
  utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(&v36);
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
  v36 = 0;
  if ( !(_DWORD)v21 )
    goto LABEL_58;
  do
  {
    FileByIndex = CReport::GetFileByIndex(a2, v23, &v37);
    if ( FileByIndex < 0 || (v20 = v37) == 0 )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        v30 = 31;
LABEL_54:
        WPP_SF_d(*((_QWORD *)v29 + 2), v30, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, (unsigned int)FileByIndex);
      }
LABEL_55:
      v20 = v36;
      goto LABEL_56;
    }
    if ( (a4 & *((_DWORD *)v37 + 1)) != a4 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      {
        v28 = *((_QWORD *)v37 + 10);
        if ( v28 == *((_QWORD *)v37 + 11) )
          v28 = *((_QWORD *)v37 + 14);
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v28);
      }
      goto LABEL_55;
    }
    if ( *((_DWORD *)a2 + 1468) != 4 )
      goto LABEL_47;
    if ( *(_DWORD *)v37 != 2 )
    {
      if ( *(_DWORD *)v37 == 3 )
      {
        if ( v22 )
          MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25, v27);
        v22 = v20;
        goto LABEL_55;
      }
LABEL_47:
      FileByIndex = CReportCab::AddReportFileToCab(this, a2, v37);
      if ( FileByIndex < 0 )
      {
        v29 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        {
          v30 = 33;
          goto LABEL_54;
        }
      }
      goto LABEL_55;
    }
    if ( v36 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v26, v25, v27);
    v36 = v20;
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
    v31 = CReportCab::AddReportFileToCab(this, a2, v22);
    if ( v31 < 0 )
    {
      if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          34,
          WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
          (unsigned int)v31);
LABEL_64:
      if ( v20 )
      {
        v32 = CReportCab::AddReportFileToCab(this, a2, v20);
        if ( v32 < 0 && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 2) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            35,
            WPP_c38227086b7a3e3189713f6d19847d71_Traceguids,
            (unsigned int)v32);
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
      WPP_SF_d(*((_QWORD *)v12 + 2), v13, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids, v14);
    }
  }
LABEL_75:
  v33 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v33 )
    utl::default_delete<ITpCommand>::operator()();
  if ( v9 != 0x7FFFFFFF )
  {
    v34 = GetCurrentThread();
    SetThreadPriority(v34, v9);
  }
  return v11;
}

```

## disassembly

```asm
0x180092760  mov     [rsp+arg_0], rbx
0x180092765  mov     [rsp+arg_18], r9d
0x18009276a  push    rbp
0x18009276b  push    rsi
0x18009276c  push    rdi
0x18009276d  push    r12
0x18009276f  push    r13
0x180092771  push    r14
0x180092773  push    r15
0x180092775  sub     rsp, 40h
0x180092779  mov     [rsp+78h+var_40], 0
0x180092782  mov     rdi, r8
0x180092785  mov     rsi, rdx
0x180092788  mov     r14, rcx
0x18009278b  test    rdx, rdx
0x18009278e  jz      loc_180092BC1
0x180092794  test    r8, r8
0x180092797  jz      loc_180092BC1
0x18009279d  call    cs:__imp_GetCurrentThread
0x1800927a4  nop     dword ptr [rax+rax+00h]
0x1800927a9  mov     rcx, rax; hThread
0x1800927ac  call    cs:__imp_GetThreadPriority
0x1800927b3  nop     dword ptr [rax+rax+00h]
0x1800927b8  mov     [rsp+78h+arg_8], eax
0x1800927bf  mov     r12d, eax
0x1800927c2  cmp     eax, 7FFFFFFFh
0x1800927c7  jnz     short loc_180092822
0x1800927c9  call    cs:__imp_GetLastError
0x1800927d0  nop     dword ptr [rax+rax+00h]
0x1800927d5  mov     ebx, eax
0x1800927d7  test    eax, eax
0x1800927d9  jle     short loc_1800927E4
0x1800927db  movzx   ebx, ax
0x1800927de  or      ebx, 80070000h
0x1800927e4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800927eb  lea     rdi, WPP_GLOBAL_Control
0x1800927f2  cmp     rcx, rdi
0x1800927f5  jz      loc_180092B80
0x1800927fb  test    byte ptr [rcx+1Ch], 1
0x1800927ff  jz      loc_180092B80
0x180092805  mov     edx, 1Ch
0x18009280a  mov     r9d, ebx
0x18009280d  mov     rcx, [rcx+10h]
0x180092811  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092818  call    WPP_SF_d
0x18009281d  jmp     loc_180092B80
0x180092822  call    cs:__imp_GetCurrentThread
0x180092829  nop     dword ptr [rax+rax+00h]
0x18009282e  mov     rcx, rax; hThread
0x180092831  or      edx, 0FFFFFFFFh; nPriority
0x180092834  call    cs:__imp_SetThreadPriority
0x18009283b  nop     dword ptr [rax+rax+00h]
0x180092840  test    eax, eax
0x180092842  jnz     short loc_18009289B
0x180092844  call    cs:__imp_GetLastError
0x18009284b  nop     dword ptr [rax+rax+00h]
0x180092850  mov     ebx, eax
0x180092852  test    eax, eax
0x180092854  jle     short loc_18009285F
0x180092856  movzx   ebx, ax
0x180092859  or      ebx, 80070000h
0x18009285f  mov     rcx, cs:WPP_GLOBAL_Control
0x180092866  lea     rdi, WPP_GLOBAL_Control
0x18009286d  cmp     rcx, rdi
0x180092870  jz      short loc_180092890
0x180092872  test    byte ptr [rcx+1Ch], 1
0x180092876  jz      short loc_180092890
0x180092878  mov     rcx, [rcx+10h]
0x18009287c  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092883  mov     edx, 1Dh
0x180092888  mov     r9d, ebx
0x18009288b  call    WPP_SF_d
0x180092890  mov     r12d, 7FFFFFFFh
0x180092896  jmp     loc_180092B80
0x18009289b  mov     rbx, [rsp+78h+hHandle]
0x1800928a3  test    rbx, rbx
0x1800928a6  jz      short loc_1800928CA
0x1800928a8  xor     edx, edx; dwMilliseconds
0x1800928aa  mov     [r14], rbx
0x1800928ad  mov     rcx, rbx; hHandle
0x1800928b0  call    cs:__imp_WaitForSingleObject
0x1800928b7  nop     dword ptr [rax+rax+00h]
0x1800928bc  test    eax, eax
0x1800928be  jnz     short loc_1800928CA
0x1800928c0  mov     ebx, 801B8001h
0x1800928c5  jmp     loc_180092B80
0x1800928ca  cmp     dword ptr [rdi+10h], 0
0x1800928ce  lea     r15, [r14+28h]
0x1800928d2  lea     rcx, [rsp+78h+var_48]
0x1800928d7  jz      short loc_1800928F5
0x1800928d9  call    ??$make_unique@VCZipArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@0@XZ; utl::make_unique<CZipArchiveFile,,0>(void)
0x1800928de  mov     rdx, rax
0x1800928e1  mov     rcx, r15
0x1800928e4  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x1800928e9  lea     rcx, [rsp+78h+var_48]
0x1800928ee  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x1800928f3  jmp     short loc_18009290F
0x1800928f5  call    ??$make_unique@VCCabArchiveFile@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCCabArchiveFile@@U?$default_delete@VCCabArchiveFile@@@utl@@@0@XZ; utl::make_unique<CCabArchiveFile,,0>(void)
0x1800928fa  mov     rdx, rax
0x1800928fd  mov     rcx, r15
0x180092900  call    ??$?4VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@$0A@@?$unique_ptr@VCArchiveFile@@U?$default_delete@VCArchiveFile@@@utl@@@utl@@QEAAAEAV01@$$QEAV?$unique_ptr@VCZipArchiveFile@@U?$default_delete@VCZipArchiveFile@@@utl@@@1@@Z; utl::unique_ptr<CArchiveFile,utl::default_delete<CArchiveFile>>::operator=<CZipArchiveFile,utl::default_delete<CZipArchiveFile>,0>(utl::unique_ptr<CZipArchiveFile,utl::default_delete<CZipArchiveFile>> &&)
0x180092905  lea     rcx, [rsp+78h+var_48]
0x18009290a  call    ??1?$unique_ptr@VCTpGenericCommand@@U?$default_delete@VCTpGenericCommand@@@utl@@@utl@@QEAA@XZ; utl::unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>::~unique_ptr<CTpGenericCommand,utl::default_delete<CTpGenericCommand>>(void)
0x18009290f  mov     rcx, [r15]
0x180092912  test    rcx, rcx
0x180092915  jz      loc_180092B7B
0x18009291b  mov     rax, [rcx]
0x18009291e  xor     r9d, r9d
0x180092921  xor     r8d, r8d
0x180092924  mov     [rsp+78h+var_58], rbx
0x180092929  mov     rdx, rdi
0x18009292c  mov     rax, [rax+8]
0x180092930  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092935  mov     ebx, eax
0x180092937  test    eax, eax
0x180092939  jns     short loc_180092969
0x18009293b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092942  lea     rdi, WPP_GLOBAL_Control
0x180092949  cmp     rcx, rdi
0x18009294c  jz      loc_180092B80
0x180092952  test    byte ptr [rcx+1Ch], 1
0x180092956  jz      loc_180092B80
0x18009295c  mov     edx, 1Eh
0x180092961  mov     r9d, eax
0x180092964  jmp     loc_18009280D
0x180092969  mov     r13, [rsi+16C0h]
0x180092970  lea     rdi, WPP_GLOBAL_Control
0x180092977  sub     r13, [rsi+16B8h]
0x18009297e  xor     ebx, ebx
0x180092980  sar     r13, 3
0x180092984  xor     ebp, ebp
0x180092986  xor     r15d, r15d
0x180092989  mov     [rsp+78h+var_48], rbx
0x18009298e  test    r13d, r13d
0x180092991  jz      loc_180092AB6
0x180092997  mov     r12d, [rsp+78h+arg_18]
0x18009299f  lea     r8, [rsp+78h+var_40]; struct CReportFile **
0x1800929a4  mov     edx, r15d; unsigned int
0x1800929a7  mov     rcx, rsi; this
0x1800929aa  call    ?GetFileByIndex@CReport@@QEAAJKPEAPEAVCReportFile@@@Z; CReport::GetFileByIndex(ulong,CReportFile * *)
0x1800929af  test    eax, eax
0x1800929b1  js      loc_180092A73
0x1800929b7  mov     rbx, [rsp+78h+var_40]
0x1800929bc  test    rbx, rbx
0x1800929bf  jz      loc_180092A73
0x1800929c5  mov     eax, [rbx+4]
0x1800929c8  and     eax, r12d
0x1800929cb  cmp     eax, r12d
0x1800929ce  jz      short loc_180092A12
0x1800929d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800929d7  cmp     rcx, rdi
0x1800929da  jz      loc_180092A9D
0x1800929e0  test    byte ptr [rcx+1Ch], 4
0x1800929e4  jz      loc_180092A9D
0x1800929ea  mov     r9, [rbx+50h]
0x1800929ee  cmp     r9, [rbx+58h]
0x1800929f2  jnz     short loc_1800929F8
0x1800929f4  mov     r9, [rbx+70h]
0x1800929f8  mov     rcx, [rcx+10h]
0x1800929fc  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092a03  mov     edx, 20h ; ' '
0x180092a08  call    WPP_SF_S
0x180092a0d  jmp     loc_180092A9D
0x180092a12  cmp     dword ptr [rsi+16F0h], 4
0x180092a19  jnz     short loc_180092A48
0x180092a1b  cmp     dword ptr [rbx], 2
0x180092a1e  jnz     short loc_180092A34
0x180092a20  cmp     [rsp+78h+var_48], 0
0x180092a26  jz      short loc_180092A2D
0x180092a28  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180092a2d  mov     [rsp+78h+var_48], rbx
0x180092a32  jmp     short loc_180092AA2
0x180092a34  cmp     dword ptr [rbx], 3
0x180092a37  jnz     short loc_180092A48
0x180092a39  test    rbp, rbp
0x180092a3c  jz      short loc_180092A43
0x180092a3e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180092a43  mov     rbp, rbx
0x180092a46  jmp     short loc_180092A9D
0x180092a48  mov     r8, rbx; struct CReportFile *
0x180092a4b  mov     rdx, rsi; struct CReport *
0x180092a4e  mov     rcx, r14; this
0x180092a51  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x180092a56  test    eax, eax
0x180092a58  jns     short loc_180092A9D
0x180092a5a  mov     rcx, cs:WPP_GLOBAL_Control
0x180092a61  cmp     rcx, rdi
0x180092a64  jz      short loc_180092A9D
0x180092a66  test    byte ptr [rcx+1Ch], 2
0x180092a6a  jz      short loc_180092A9D
0x180092a6c  mov     edx, 21h ; '!'
0x180092a71  jmp     short loc_180092A8A
0x180092a73  mov     rcx, cs:WPP_GLOBAL_Control
0x180092a7a  cmp     rcx, rdi
0x180092a7d  jz      short loc_180092A9D
0x180092a7f  test    byte ptr [rcx+1Ch], 2
0x180092a83  jz      short loc_180092A9D
0x180092a85  mov     edx, 1Fh
0x180092a8a  mov     rcx, [rcx+10h]
0x180092a8e  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092a95  mov     r9d, eax
0x180092a98  call    WPP_SF_d
0x180092a9d  mov     rbx, [rsp+78h+var_48]
0x180092aa2  inc     r15d
0x180092aa5  cmp     r15d, r13d
0x180092aa8  jb      loc_18009299F
0x180092aae  mov     r12d, [rsp+78h+arg_8]
0x180092ab6  cmp     dword ptr [rsi+16F0h], 4
0x180092abd  jnz     loc_180092B45
0x180092ac3  test    rbp, rbp
0x180092ac6  jz      short loc_180092B04
0x180092ac8  mov     r8, rbp; struct CReportFile *
0x180092acb  mov     rdx, rsi; struct CReport *
0x180092ace  mov     rcx, r14; this
0x180092ad1  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x180092ad6  test    eax, eax
0x180092ad8  jns     short loc_180092B45
0x180092ada  mov     rcx, cs:WPP_GLOBAL_Control
0x180092ae1  cmp     rcx, rdi
0x180092ae4  jz      short loc_180092B04
0x180092ae6  test    byte ptr [rcx+1Ch], 2
0x180092aea  jz      short loc_180092B04
0x180092aec  mov     rcx, [rcx+10h]
0x180092af0  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092af7  mov     edx, 22h ; '"'
0x180092afc  mov     r9d, eax
0x180092aff  call    WPP_SF_d
0x180092b04  test    rbx, rbx
0x180092b07  jz      short loc_180092B45
0x180092b09  mov     r8, rbx; struct CReportFile *
0x180092b0c  mov     rdx, rsi; struct CReport *
0x180092b0f  mov     rcx, r14; this
0x180092b12  call    ?AddReportFileToCab@CReportCab@@IEAAJPEAVCReport@@PEAVCReportFile@@@Z; CReportCab::AddReportFileToCab(CReport *,CReportFile *)
0x180092b17  test    eax, eax
0x180092b19  jns     short loc_180092B45
0x180092b1b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092b22  cmp     rcx, rdi
0x180092b25  jz      short loc_180092B45
0x180092b27  test    byte ptr [rcx+1Ch], 2
0x180092b2b  jz      short loc_180092B45
0x180092b2d  mov     rcx, [rcx+10h]
0x180092b31  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092b38  mov     edx, 23h ; '#'
0x180092b3d  mov     r9d, eax
0x180092b40  call    WPP_SF_d
0x180092b45  mov     rcx, [r14+28h]
0x180092b49  mov     rax, [rcx]
0x180092b4c  mov     rax, [rax+28h]
0x180092b50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180092b55  mov     ebx, eax
0x180092b57  test    eax, eax
0x180092b59  jns     short loc_180092B77
0x180092b5b  mov     rcx, cs:WPP_GLOBAL_Control
0x180092b62  cmp     rcx, rdi
0x180092b65  jz      short loc_180092B80
0x180092b67  test    byte ptr [rcx+1Ch], 1
0x180092b6b  jz      short loc_180092B80
0x180092b6d  mov     edx, 24h ; '$'
0x180092b72  jmp     loc_180092961
0x180092b77  xor     ebx, ebx
0x180092b79  jmp     short loc_180092B80
0x180092b7b  mov     ebx, 8007000Eh
0x180092b80  mov     rdx, [r14+28h]
0x180092b84  mov     qword ptr [r14+28h], 0
0x180092b8c  test    rdx, rdx
0x180092b8f  jz      short loc_180092B96
0x180092b91  call    ??R?$default_delete@VITpCommand@@@utl@@QEBAXPEAVITpCommand@@@Z; utl::default_delete<ITpCommand>::operator()(ITpCommand *)
0x180092b96  cmp     r12d, 7FFFFFFFh
0x180092b9d  jz      short loc_180092BBD
0x180092b9f  call    cs:__imp_GetCurrentThread
0x180092ba6  nop     dword ptr [rax+rax+00h]
0x180092bab  mov     rcx, rax; hThread
0x180092bae  mov     edx, r12d; nPriority
0x180092bb1  call    cs:__imp_SetThreadPriority
0x180092bb8  nop     dword ptr [rax+rax+00h]
0x180092bbd  mov     eax, ebx
0x180092bbf  jmp     short loc_180092BF4
0x180092bc1  mov     rcx, cs:WPP_GLOBAL_Control
0x180092bc8  lea     rdi, WPP_GLOBAL_Control
0x180092bcf  cmp     rcx, rdi
0x180092bd2  jz      short loc_180092BEF
0x180092bd4  test    byte ptr [rcx+1Ch], 1
0x180092bd8  jz      short loc_180092BEF
0x180092bda  mov     rcx, [rcx+10h]
0x180092bde  lea     r8, WPP_c38227086b7a3e3189713f6d19847d71_Traceguids
0x180092be5  mov     edx, 1Bh
0x180092bea  call    WPP_SF_
0x180092bef  mov     eax, 80070057h
0x180092bf4  mov     rbx, [rsp+78h+arg_0]
0x180092bfc  add     rsp, 40h
0x180092c00  pop     r15
0x180092c02  pop     r14
0x180092c04  pop     r13
0x180092c06  pop     r12
0x180092c08  pop     rdi
0x180092c09  pop     rsi
0x180092c0a  pop     rbp
0x180092c0b  retn
```
