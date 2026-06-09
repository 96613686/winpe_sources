# COSDownloader::GenerateDownloadRequest(void)

- ea: `0x180020290`
- end: `0x180020928`
- name: `?GenerateDownloadRequest@COSDownloader@@QEAAJXZ`
- size: `1688`
- prototype: `__int64 __fastcall(COSDownloader *__hidden this)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, loader_planting, service_task, installer_update`

## callers

- `0x18001f870`

## callees

- `0x180003950`
- `0x18000956c`
- `0x18000a4f4`
- `0x18001952c`
- `0x18001e570`
- `0x18001f728`
- `0x180020290`
- `0x180020930`
- `0x1800216c8`
- `0x180021730`
- `0x180021d90`
- `0x180024050`
- `0x180024660`
- `0x18003a7c8`
- `0x180042630`
- `0x180042a24`
- `0x1800430f8`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002041d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002072e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800203e6`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002041d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180020703`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002072e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020409`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002063c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020377`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180020409`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002063c`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800204a4`
- `api-ms-win-core-realtime-l1-1-0!QueryUnbiasedInterruptTime` at `0x1800204a4`

## string_xrefs

- `0x180020478`: `Starting to count time for GDR for update %ws`
- `0x180020580`: `AddFullFileToDownloadRequestIfNotDownloaded failed for the service stack file '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall COSDownloader::GenerateDownloadRequest(COSDownloader *this)
{
  unsigned int v2; // r12d
  struct tagDSFile **i; // rbx
  struct ISusHandlerNotification *v5; // rcx
  signed int FilesPerPatchType; // esi
  struct ISusHandlerNotification *v7; // rsi
  CWUPerfTimer *v8; // rax
  ULONGLONG *v9; // rdi
  OSDownloader::details::GDRTimer *v10; // r15
  __int64 v11; // rdx
  struct tagDSFile *v12; // r13
  __int64 v13; // rdx
  int v14; // eax
  struct _RTL_CRITICAL_SECTION *v15; // rsi
  _OWORD *v16; // rcx
  const wchar_t *v17; // r8
  int v18; // eax
  unsigned int v19; // edi
  __int64 v20; // rdx
  const wchar_t *v21; // r8
  int v22; // eax
  int v23; // eax
  unsigned __int64 v24; // r9
  _QWORD *v25; // rcx
  const struct std::nothrow_t *v26; // rdx
  int v27; // [rsp+28h] [rbp-E0h]
  struct tagDSFile ***v28; // [rsp+40h] [rbp-C8h]
  bool v29; // [rsp+48h] [rbp-C0h]
  struct tagDSFile **v30; // [rsp+4Ch] [rbp-BCh] BYREF
  struct tagDSFile **v31; // [rsp+58h] [rbp-B0h] BYREF
  struct tagDSFile *v32; // [rsp+60h] [rbp-A8h] BYREF
  __int64 v33; // [rsp+68h] [rbp-A0h]
  char *v34; // [rsp+70h] [rbp-98h]
  void *v35[2]; // [rsp+78h] [rbp-90h] BYREF
  struct ISusHandlerNotification **v36; // [rsp+88h] [rbp-80h]
  __int64 v37; // [rsp+90h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-70h]
  _BYTE v39[112]; // [rsp+A8h] [rbp-60h] BYREF
  struct ISusHandlerNotification *v40; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v2 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl'::`2'::impl)
    && COSDownloader::IsGDRRunning(this) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x34D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
      (const char *)0x80240009LL,
      v27);
    return 2149842953LL;
  }
  v32 = 0;
  v30 = 0;
  i = 0;
  v31 = 0;
  v35[0] = 0;
  v33 = 0;
  v38 = 0;
  v5 = 0;
  v40 = 0;
  v37 = 1;
  v35[1] = this;
  v36 = &v40;
  if ( !*((_BYTE *)this + 16) )
  {
    v34 = (char *)this + 80;
    if ( this != (COSDownloader *)-80LL )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      v5 = v40;
    }
    v7 = (struct ISusHandlerNotification *)*((_QWORD *)this + 18);
    *((_QWORD *)this + 18) = 0;
    if ( v5 )
      (*(void (__fastcall **)(struct ISusHandlerNotification *))(*(_QWORD *)v5 + 16LL))(v5);
    v40 = v7;
    if ( !v7 )
    {
      FilesPerPatchType = -2145112065;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x38B,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
        (const char *)0x80242FFFLL,
        v27);
      if ( this != (COSDownloader *)-80LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
      goto LABEL_83;
    }
    if ( this != (COSDownloader *)-80LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 88));
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl'::`2'::impl) )
    {
      if ( this != (COSDownloader *)-24LL )
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
      *((_BYTE *)this + 72) = 1;
      if ( this != (COSDownloader *)-24LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
    }
    else
    {
      *((_BYTE *)this + 72) = 1;
    }
    v8 = (CWUPerfTimer *)operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
    v9 = (ULONGLONG *)v8;
    v34 = (char *)v8;
    if ( v8 )
    {
      CWUPerfTimer::CWUPerfTimer(v8);
      v9[5] = (ULONGLONG)this + 308;
      v9[6] = (ULONGLONG)this + 476;
      Trace::UpdateIdToString::UpdateIdToString((Trace::UpdateIdToString *)v39, (COSDownloader *)((char *)this + 308));
      WUTrace(0, 0, 4096, 4);
      v9[3] = 0;
      QueryUnbiasedInterruptTime(v9 + 1);
      v34 = (char *)v9;
      v10 = (OSDownloader::details::GDRTimer *)v9;
      FilesPerPatchType = OSDeploymentHelper::GetFilesPerPatchType(
                            (OSDeploymentHelper *)*((unsigned int *)this + 98),
                            *((_QWORD *)this + 50),
                            (struct tagDSFile *const)&v32,
                            (const struct tagDSFile **)&v30,
                            (unsigned int *)&v31,
                            (struct tagDSFile ***)((char *)&v30 + 4),
                            (unsigned int *)v35,
                            v28);
      if ( FilesPerPatchType < 0 )
      {
        v11 = 930;
LABEL_24:
        i = v31;
        goto LABEL_79;
      }
      if ( !*((_QWORD *)this + 34) )
      {
        FilesPerPatchType = CSusFileRequestList::CreateInstance((struct CSusFileRequestList **)this + 34);
        if ( FilesPerPatchType < 0 )
        {
          v11 = 934;
          goto LABEL_24;
        }
      }
      if ( !*((_QWORD *)this + 54) )
      {
        FilesPerPatchType = CSusFileRequestList::CreateInstance((struct CSusFileRequestList **)this + 54);
        if ( FilesPerPatchType < 0 )
        {
          v11 = 940;
          goto LABEL_24;
        }
      }
      v12 = v32;
      v29 = v32 != 0;
      if ( v32 )
      {
        FilesPerPatchType = AddFullFileToDownloadRequestIfNotDownloaded(
                              *((const wchar_t **)this + 35),
                              v32,
                              *((struct ISusFileRequestList **)this + 34));
        v2 = 0;
        if ( FilesPerPatchType < 0 )
        {
          v27 = FilesPerPatchType;
          WUTrace(0, 0, 4096, 1);
          v11 = 959;
          goto LABEL_24;
        }
        v33 = *((_QWORD *)v12 + 29);
        LOBYTE(v2) = FilesPerPatchType == 0;
      }
      v13 = 0;
      HIDWORD(v30) = 0;
      for ( i = v31; (unsigned int)v13 < (unsigned int)v30; HIDWORD(v30) = v13 )
      {
        if ( v2 < 0x32 )
        {
          v14 = AddFullFileToDownloadRequestIfNotDownloaded(
                  *((const wchar_t **)this + 35),
                  i[v13],
                  *((struct ISusFileRequestList **)this + 34));
          FilesPerPatchType = v14;
          if ( v14 < 0 )
          {
            v27 = v14;
            WUTrace(0, 0, 4096, 1);
            v11 = 988;
            goto LABEL_79;
          }
          LODWORD(v13) = HIDWORD(v30);
          if ( !v14 )
            ++v2;
        }
        v33 += *((_QWORD *)i[(unsigned int)v13] + 29);
        v13 = (unsigned int)(v13 + 1);
      }
      v15 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 216);
      v32 = (COSDownloader *)((char *)this + 216);
      if ( this == (COSDownloader *)-208LL )
        v32 = (struct tagDSFile *)8;
      else
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
      if ( !*((_QWORD *)this + 32) )
      {
        v16 = operator new(0x38u, (const struct std::nothrow_t *)&std::nothrow);
        if ( v16 )
        {
          *v16 = 0;
          v16[1] = 0;
          v16[2] = 0;
          *((_QWORD *)v16 + 6) = 0;
        }
        else
        {
          v16 = 0;
        }
        *((_QWORD *)this + 32) = v16;
        FilesPerPatchType = v16 == 0 ? 0x8007000E : 0;
        if ( !v16 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x3EE,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)(unsigned int)FilesPerPatchType,
            v27);
          if ( this != (COSDownloader *)-208LL )
            LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
          goto LABEL_81;
        }
        *(_BYTE *)v16 = 4;
        *(_QWORD *)(*((_QWORD *)this + 32) + 8LL) = v33;
        v15 = (struct _RTL_CRITICAL_SECTION *)v32;
      }
      if ( this != (COSDownloader *)-208LL )
        LeaveCriticalSection(v15);
      *(_BYTE *)(*((_QWORD *)this + 32) + 52LL) = v2 == 0;
      if ( *(_BYTE *)(*((_QWORD *)this + 32) + 52LL) )
      {
        if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl'::`2'::impl) )
        {
          if ( v29 )
            v17 = (const wchar_t *)*((_QWORD *)v12 + 9);
          else
            v17 = 0;
          v18 = COSDownloader::AddPayloadFileToDownloadRequest(this, v40, v17, (unsigned int)v30, i);
          v19 = v18;
          if ( v18 < 0 )
          {
            if ( v18 == -2145116152 || (unsigned int)(v18 + 2147024894) <= 1 )
              goto LABEL_72;
            v20 = 1031;
LABEL_71:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v20,
              (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
              (const char *)v19,
              v27);
LABEL_72:
            FilesPerPatchType = v19;
            goto LABEL_81;
          }
        }
        else
        {
          if ( v29 )
            v21 = (const wchar_t *)*((_QWORD *)v12 + 9);
          else
            v21 = 0;
          v22 = COSDownloader::AddPayloadFileToDownloadRequest_Legacy(
                  this,
                  v40,
                  v21,
                  (int)v30,
                  i,
                  *((struct OSDownloadProgress **)this + 32));
          v19 = v22;
          if ( v22 < 0 )
          {
            if ( v22 == -2145116152 || (unsigned int)(v22 + 2147024894) <= 1 )
              goto LABEL_72;
            v20 = 1043;
            goto LABEL_71;
          }
        }
        v23 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 34) + 128LL))(
                *((_QWORD *)this + 34),
                *((_QWORD *)this + 32) + 24LL);
        FilesPerPatchType = v23;
        if ( v23 < 0 )
        {
          v24 = (unsigned int)v23;
          v11 = 1046;
LABEL_80:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v11,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Downloader\\OSDownloader.cpp",
            (const char *)v24,
            v27);
LABEL_81:
          if ( v10 )
          {
            OSDownloader::details::GDRTimer::~GDRTimer(v10);
            operator delete(v10, (const struct std::nothrow_t *)0x38);
          }
          goto LABEL_83;
        }
        *(_QWORD *)(*((_QWORD *)this + 32) + 32LL) += *(_QWORD *)(*((_QWORD *)this + 32) + 24LL);
        v25 = (_QWORD *)*((_QWORD *)this + 32);
        if ( !v25[5] )
          v25[2] += v25[3];
      }
      FilesPerPatchType = 0;
      goto LABEL_81;
    }
    v10 = 0;
    FilesPerPatchType = -2147024882;
    v11 = 922;
LABEL_79:
    v24 = (unsigned int)FilesPerPatchType;
    goto LABEL_80;
  }
  FilesPerPatchType = -2145116152;
LABEL_83:
  LOBYTE(v37) = 0;
  lambda_38bf6544e741f00a12d0dd1b6cb1ed53_::operator()(&v35[1]);
  if ( v40 )
  {
    (*(void (__fastcall **)(struct ISusHandlerNotification *))(*(_QWORD *)v40 + 16LL))(v40);
    v40 = 0;
  }
  if ( v35[0] )
    operator delete(v35[0], v26);
  if ( i )
    operator delete(i, v26);
  return (unsigned int)FilesPerPatchType;
}

```

## disassembly

```asm
0x180020290  mov     rax, rsp
0x180020293  mov     [rax+10h], rbx
0x180020297  mov     [rax+18h], rsi
0x18002029b  mov     [rax+20h], rdi
0x18002029f  push    rbp
0x1800202a0  push    r12
0x1800202a2  push    r13
0x1800202a4  push    r14
0x1800202a6  push    r15
0x1800202a8  lea     rbp, [rax-48h]
0x1800202ac  sub     rsp, 120h
0x1800202b3  mov     rax, cs:__security_cookie
0x1800202ba  xor     rax, rsp
0x1800202bd  mov     [rbp+40h+var_28], rax
0x1800202c1  mov     r14, rcx
0x1800202c4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl(void)'::`2'::impl
0x1800202cb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(void)
0x1800202d0  xor     r12d, r12d
0x1800202d3  test    al, al
0x1800202d5  jz      short loc_180020307
0x1800202d7  mov     rcx, r14; this
0x1800202da  call    ?IsGDRRunning@COSDownloader@@QEAA_NXZ; COSDownloader::IsGDRRunning(void)
0x1800202df  test    al, al
0x1800202e1  jz      short loc_180020307
0x1800202e3  mov     rcx, [rbp+48h]; this
0x1800202e7  mov     ebx, 80240009h
0x1800202ec  mov     r9d, ebx; char *
0x1800202ef  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800202f6  mov     edx, 34Dh; void *
0x1800202fb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020300  mov     eax, ebx
0x180020302  jmp     loc_1800208FB
0x180020307  mov     [rsp+140h+var_E8], r12
0x18002030c  mov     dword ptr [rsp+140h+var_FC], r12d
0x180020311  mov     rbx, r12
0x180020314  mov     [rsp+140h+var_F0], rbx
0x180020319  mov     dword ptr [rsp+140h+var_FC+4], r12d
0x18002031e  mov     [rsp+140h+var_D0], r12
0x180020323  mov     [rsp+140h+var_E0], r12
0x180020328  mov     [rbp+40h+var_B0], r12
0x18002032c  mov     rcx, r12
0x18002032f  mov     [rbp+40h+var_30], rcx
0x180020333  xorps   xmm0, xmm0
0x180020336  xor     eax, eax
0x180020338  movups  xmmword ptr [rsp+140h+var_D0+8], xmm0
0x18002033d  mov     [rbp+40h+var_B8], rax
0x180020341  mov     [rsp+140h+var_D0+8], r14
0x180020346  lea     rax, [rbp+40h+var_30]
0x18002034a  mov     [rbp+40h+var_C0], rax
0x18002034e  mov     byte ptr [rbp+40h+var_B8], 1
0x180020352  cmp     [r14+10h], r12b
0x180020356  jz      short loc_180020362
0x180020358  mov     esi, 80242008h
0x18002035d  jmp     loc_1800208B4
0x180020362  lea     rdi, [r14+50h]
0x180020366  mov     [rsp+140h+var_D8], rdi
0x18002036b  lea     r15, [rdi+8]
0x18002036f  test    rdi, rdi
0x180020372  jz      short loc_180020381
0x180020374  mov     rcx, r15; lpCriticalSection
0x180020377  call    cs:__imp_EnterCriticalSection
0x18002037d  mov     rcx, [rbp+40h+var_30]
0x180020381  mov     rsi, [r14+90h]
0x180020388  mov     [r14+90h], r12
0x18002038f  test    rcx, rcx
0x180020392  jz      short loc_1800203A0
0x180020394  mov     rax, [rcx]
0x180020397  mov     rax, [rax+10h]
0x18002039b  call    _guard_dispatch_icall
0x1800203a0  mov     [rbp+40h+var_30], rsi
0x1800203a4  test    rsi, rsi
0x1800203a7  jnz     short loc_1800203DE
0x1800203a9  mov     rcx, [rbp+48h]; this
0x1800203ad  mov     esi, 80242FFFh
0x1800203b2  mov     r9d, esi; char *
0x1800203b5  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800203bc  mov     edx, 38Bh; void *
0x1800203c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800203c6  nop
0x1800203c7  test    rdi, rdi
0x1800203ca  jz      loc_1800208B4
0x1800203d0  mov     rcx, r15; lpCriticalSection
0x1800203d3  call    cs:__imp_LeaveCriticalSection
0x1800203d9  jmp     loc_1800208B4
0x1800203de  test    rdi, rdi
0x1800203e1  jz      short loc_1800203EC
0x1800203e3  mov     rcx, r15; lpCriticalSection
0x1800203e6  call    cs:__imp_LeaveCriticalSection
0x1800203ec  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::GetImpl(void)'::`2'::impl
0x1800203f3  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UUPRemoteProcess_55045381>::__private_IsEnabled(void)
0x1800203f8  test    al, al
0x1800203fa  jz      short loc_180020425
0x1800203fc  lea     rdi, [r14+18h]
0x180020400  test    rdi, rdi
0x180020403  jz      short loc_18002040F
0x180020405  lea     rcx, [rdi+8]; lpCriticalSection
0x180020409  call    cs:__imp_EnterCriticalSection
0x18002040f  mov     byte ptr [r14+48h], 1
0x180020414  test    rdi, rdi
0x180020417  jz      short loc_18002042A
0x180020419  lea     rcx, [rdi+8]; lpCriticalSection
0x18002041d  call    cs:__imp_LeaveCriticalSection
0x180020423  jmp     short loc_18002042A
0x180020425  mov     byte ptr [r14+48h], 1
0x18002042a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020431  mov     ecx, 38h ; '8'; unsigned __int64
0x180020436  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18002043b  mov     rdi, rax
0x18002043e  mov     [rsp+140h+var_D8], rax
0x180020443  test    rax, rax
0x180020446  jz      loc_180020875
0x18002044c  mov     rcx, rax; this
0x18002044f  call    ??0CWUPerfTimer@@QEAA@XZ; CWUPerfTimer::CWUPerfTimer(void)
0x180020454  lea     rdx, [r14+134h]; struct tagDSGlobalUpdateId *
0x18002045b  mov     [rdi+28h], rdx
0x18002045f  lea     rcx, [r14+1DCh]
0x180020466  mov     [rdi+30h], rcx
0x18002046a  lea     rcx, [rbp+40h+var_A0]; this
0x18002046e  call    ??0UpdateIdToString@Trace@@QEAA@AEBUtagDSGlobalUpdateId@@@Z; Trace::UpdateIdToString::UpdateIdToString(tagDSGlobalUpdateId const &)
0x180020473  mov     [rsp+140h+var_110], rax
0x180020478  lea     rax, aStartingToCoun; "Starting to count time for GDR for upda"...
0x18002047f  mov     [rsp+140h+var_118], rax
0x180020484  mov     [rsp+140h+var_120], r12
0x180020489  xor     edx, edx
0x18002048b  xor     ecx, ecx
0x18002048d  lea     r9d, [rdx+4]
0x180020491  mov     r8d, 1000h
0x180020497  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18002049c  mov     [rdi+18h], r12
0x1800204a0  lea     rcx, [rdi+8]; UnbiasedTime
0x1800204a4  call    cs:__imp_QueryUnbiasedInterruptTime
0x1800204aa  mov     [rsp+140h+var_D8], rdi
0x1800204af  mov     r15, rdi
0x1800204b2  test    rdi, rdi
0x1800204b5  jz      loc_180020878
0x1800204bb  lea     rax, [rsp+140h+var_D0]
0x1800204c0  mov     [rsp+140h+var_110], rax; unsigned int *
0x1800204c5  lea     rax, [rsp+140h+var_FC+4]
0x1800204ca  mov     [rsp+140h+var_118], rax; struct tagDSFile ***
0x1800204cf  lea     rax, [rsp+140h+var_F0]
0x1800204d4  mov     [rsp+140h+var_120], rax; int
0x1800204d9  lea     r9, [rsp+140h+var_FC]; struct tagDSFile **
0x1800204de  lea     r8, [rsp+140h+var_E8]; struct tagDSFile *
0x1800204e3  mov     rdx, [r14+190h]; unsigned int
0x1800204ea  mov     ecx, [r14+188h]; this
0x1800204f1  call    ?GetFilesPerPatchType@OSDeploymentHelper@@YAJKQEAUtagDSFile@@PEAPEBU2@PEAKPEAPEAPEAU2@23@Z; OSDeploymentHelper::GetFilesPerPatchType(ulong,tagDSFile * const,tagDSFile const * *,ulong *,tagDSFile * * *,ulong *,tagDSFile * * *)
0x1800204f6  mov     esi, eax
0x1800204f8  test    eax, eax
0x1800204fa  jns     short loc_18002050B
0x1800204fc  mov     edx, 3A2h
0x180020501  mov     rbx, [rsp+140h+var_F0]
0x180020506  jmp     loc_180020882
0x18002050b  lea     rbx, [r14+110h]
0x180020512  cmp     [rbx], r12
0x180020515  jnz     short loc_18002052C
0x180020517  mov     rcx, rbx; struct CSusFileRequestList **
0x18002051a  call    ?CreateInstance@CSusFileRequestList@@SAJPEAPEAV1@@Z; CSusFileRequestList::CreateInstance(CSusFileRequestList * *)
0x18002051f  mov     esi, eax
0x180020521  test    eax, eax
0x180020523  jns     short loc_18002052C
0x180020525  mov     edx, 3A6h
0x18002052a  jmp     short loc_180020501
0x18002052c  lea     rcx, [r14+1B0h]; struct CSusFileRequestList **
0x180020533  cmp     [rcx], r12
0x180020536  jnz     short loc_18002054A
0x180020538  call    ?CreateInstance@CSusFileRequestList@@SAJPEAPEAV1@@Z; CSusFileRequestList::CreateInstance(CSusFileRequestList * *)
0x18002053d  mov     esi, eax
0x18002053f  test    eax, eax
0x180020541  jns     short loc_18002054A
0x180020543  mov     edx, 3ACh
0x180020548  jmp     short loc_180020501
0x18002054a  mov     r13, [rsp+140h+var_E8]
0x18002054f  test    r13, r13
0x180020552  setnz   byte ptr [rsp+140h+var_100]
0x180020557  test    r13, r13
0x18002055a  jz      short loc_1800205C0
0x18002055c  mov     r8, [rbx]; struct ISusFileRequestList *
0x18002055f  mov     rdx, r13; struct tagDSFile *
0x180020562  mov     rcx, [r14+118h]; wchar_t *
0x180020569  call    ?AddFullFileToDownloadRequestIfNotDownloaded@@YAJPEB_WAEBUtagDSFile@@PEAUISusFileRequestList@@@Z; AddFullFileToDownloadRequestIfNotDownloaded(wchar_t const *,tagDSFile const &,ISusFileRequestList *)
0x18002056e  mov     esi, eax
0x180020570  xor     r12d, r12d
0x180020573  test    eax, eax
0x180020575  jns     short loc_1800205AE
0x180020577  mov     rax, [r13+48h]
0x18002057b  mov     [rsp+140h+var_110], rax
0x180020580  lea     rax, aAddfullfiletod_0; "AddFullFileToDownloadRequestIfNotDownlo"...
0x180020587  mov     [rsp+140h+var_118], rax
0x18002058c  mov     dword ptr [rsp+140h+var_120], esi
0x180020590  xor     edx, edx
0x180020592  xor     ecx, ecx
0x180020594  lea     r9d, [r12+1]
0x180020599  mov     r8d, 1000h
0x18002059f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1800205a4  mov     edx, 3BFh
0x1800205a9  jmp     loc_180020501
0x1800205ae  mov     rax, [r13+0E8h]
0x1800205b5  mov     [rsp+140h+var_E0], rax
0x1800205ba  test    esi, esi
0x1800205bc  setz    r12b
0x1800205c0  xor     edx, edx
0x1800205c2  mov     dword ptr [rsp+140h+var_FC+4], edx
0x1800205c6  mov     rbx, [rsp+140h+var_F0]
0x1800205cb  cmp     dword ptr [rsp+140h+var_FC], edx
0x1800205cf  jbe     short loc_180020624
0x1800205d1  cmp     r12d, 32h ; '2'
0x1800205d5  jnb     short loc_180020601
0x1800205d7  mov     edi, edx
0x1800205d9  mov     r8, [r14+110h]; struct ISusFileRequestList *
0x1800205e0  mov     rdx, [rbx+rdx*8]; struct tagDSFile *
0x1800205e4  mov     rcx, [r14+118h]; wchar_t *
0x1800205eb  call    ?AddFullFileToDownloadRequestIfNotDownloaded@@YAJPEB_WAEBUtagDSFile@@PEAUISusFileRequestList@@@Z; AddFullFileToDownloadRequestIfNotDownloaded(wchar_t const *,tagDSFile const &,ISusFileRequestList *)
0x1800205f0  mov     esi, eax
0x1800205f2  test    eax, eax
0x1800205f4  js      short loc_180020644
0x1800205f6  mov     edx, dword ptr [rsp+140h+var_FC+4]
0x1800205fa  test    eax, eax
0x1800205fc  jnz     short loc_180020601
0x1800205fe  inc     r12d
0x180020601  mov     eax, edx
0x180020603  mov     rcx, [rbx+rax*8]
0x180020607  mov     rax, [rsp+140h+var_E0]
0x18002060c  add     rax, [rcx+0E8h]
0x180020613  mov     [rsp+140h+var_E0], rax
0x180020618  inc     edx
0x18002061a  mov     dword ptr [rsp+140h+var_FC+4], edx
0x18002061e  cmp     edx, dword ptr [rsp+140h+var_FC]
0x180020622  jb      short loc_1800205D1
0x180020624  lea     rdi, [r14+0D0h]
0x18002062b  lea     rsi, [rdi+8]
0x18002062f  mov     [rsp+140h+var_E8], rsi
0x180020634  test    rdi, rdi
0x180020637  jz      short loc_18002067E
0x180020639  mov     rcx, rsi; lpCriticalSection
0x18002063c  call    cs:__imp_EnterCriticalSection
0x180020642  jmp     short loc_180020683
0x180020644  mov     rax, [rbx+rdi*8]
0x180020648  mov     rcx, [rax+48h]
0x18002064c  mov     [rsp+140h+var_110], rcx
0x180020651  lea     rax, aAddfullfiletod; "AddFullFileToDownloadRequestIfNotDownlo"...
0x180020658  mov     [rsp+140h+var_118], rax
0x18002065d  mov     dword ptr [rsp+140h+var_120], esi
0x180020661  xor     edx, edx
0x180020663  xor     ecx, ecx
0x180020665  lea     r9d, [rdx+1]
0x180020669  mov     r8d, 1000h
0x18002066f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180020674  mov     edx, 3DCh
0x180020679  jmp     loc_180020882
0x18002067e  mov     [rsp+140h+var_E8], rsi
0x180020683  cmp     qword ptr [r14+100h], 0
0x18002068b  jnz     loc_180020726
0x180020691  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180020698  mov     ecx, 38h ; '8'; unsigned __int64
0x18002069d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800206a2  mov     rcx, rax
0x1800206a5  test    rax, rax
0x1800206a8  jz      short loc_1800206C0
0x1800206aa  xorps   xmm0, xmm0
0x1800206ad  xor     eax, eax
0x1800206af  movups  xmmword ptr [rcx], xmm0
0x1800206b2  movups  xmmword ptr [rcx+10h], xmm0
0x1800206b6  movups  xmmword ptr [rcx+20h], xmm0
0x1800206ba  mov     [rcx+30h], rax
0x1800206be  jmp     short loc_1800206C2
0x1800206c0  xor     ecx, ecx
0x1800206c2  mov     [r14+100h], rcx
0x1800206c9  mov     rax, rcx
0x1800206cc  neg     rax
0x1800206cf  sbb     esi, esi
0x1800206d1  not     esi
0x1800206d3  and     esi, 8007000Eh
0x1800206d9  test    rcx, rcx
0x1800206dc  jnz     short loc_18002070E
0x1800206de  mov     rcx, [rbp+48h]; this
0x1800206e2  mov     r9d, esi; char *
0x1800206e5  lea     r8, aCW1SSrcClientE_3; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x1800206ec  mov     edx, 3EEh; void *
0x1800206f1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206f6  test    rdi, rdi
0x1800206f9  jz      loc_180020896
0x1800206ff  lea     rcx, [rdi+8]; lpCriticalSection
0x180020703  call    cs:__imp_LeaveCriticalSection
0x180020709  jmp     loc_180020896
0x18002070e  mov     byte ptr [rcx], 4
0x180020711  mov     rax, [r14+100h]
0x180020718  mov     rcx, [rsp+140h+var_E0]
0x18002071d  mov     [rax+8], rcx
0x180020721  mov     rsi, [rsp+140h+var_E8]
0x180020726  test    rdi, rdi
0x180020729  jz      short loc_180020734
0x18002072b  mov     rcx, rsi; lpCriticalSection
0x18002072e  call    cs:__imp_LeaveCriticalSection
0x180020734  mov     rdx, [r14+100h]
0x18002073b  test    r12d, r12d
0x18002073e  setz    al
0x180020741  mov     [rdx+34h], al
0x180020744  mov     rax, [r14+100h]
0x18002074b  xor     r12d, r12d
0x18002074e  cmp     [rax+34h], r12b
  ... truncated ...
```
