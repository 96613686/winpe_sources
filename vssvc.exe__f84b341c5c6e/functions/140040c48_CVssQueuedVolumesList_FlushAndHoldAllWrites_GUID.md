# CVssQueuedVolumesList::FlushAndHoldAllWrites(_GUID)

- ea: `0x140040c48`
- end: `0x140041a08`
- name: `?FlushAndHoldAllWrites@CVssQueuedVolumesList@@QEAAJU_GUID@@@Z`
- size: `3520`
- prototype: `__int64 __fastcall(CVssQueuedVolumesList *__hidden this, struct _GUID *__struct_ptr)`
- caller_count: `1`
- callee_count: `19`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400a5c18`

## callees

- `0x140006020`
- `0x140006270`
- `0x1400137c0`
- `0x140013b00`
- `0x140015e38`
- `0x1400326c0`
- `0x140032990`
- `0x140032fcc`
- `0x1400330fc`
- `0x140040c48`
- `0x140041a10`
- `0x140041b3c`
- `0x140049ec4`
- `0x14004f138`
- `0x14005632c`
- `0x14006c934`
- `0x140091584`
- `0x1400919a0`
- `0x1400921dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14004114b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140041592`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x14004114b`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x140041592`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140040e79`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x140040e79`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140040de9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x140040de9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040dfc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040dfc`

## string_xrefs

- `0x140040c6d`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040cf9`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040d6d`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040e16`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040efa`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040fca`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x1400410b9`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x1400411b5`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140041241`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x14004131d`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x14004138b`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x1400415fe`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x14004168a`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x14004176e`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140041916`: `CVssQueuedVolumesList::FlushAndHoldAllWrites`
- `0x140040e5d`: `CreateEvent( NULL, TRUE, FALSE, NULL )`
- `0x14004120c`: `It took longer than %d seconds to open %d handles`
- `0x1400414ed`: `Lovelace failed to hold writes at volume %d - '%s'`
- `0x1400418eb`: `Lovelace failed to hold writes at volume %d - '%s'`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CVssQueuedVolumesList::FlushAndHoldAllWrites(CVssQueuedVolumesList *this, struct _GUID *a2)
{
  int v4; // esi
  void *v5; // rcx
  HANDLE EventW; // rax
  signed int LastError; // eax
  unsigned int v8; // edi
  char v9; // r13
  int i; // edx
  unsigned __int64 v11; // rax
  HANDLE *v12; // rsi
  unsigned int v13; // r14d
  int v14; // r15d
  struct _GUID v15; // xmm0
  __int64 v16; // rcx
  int v17; // edx
  DWORD j; // r14d
  DWORD v19; // ecx
  int started; // r15d
  DWORD v21; // r14d
  unsigned int k; // r15d
  __int64 v23; // r14
  struct CVssDebugInfo *v24; // rax
  struct CVssDebugInfo *v25; // rax
  struct CVssDebugInfo *v26; // rax
  struct CVssDebugInfo *v27; // rax
  struct CVssDebugInfo *v28; // rax
  CVssDebugInfo *v29; // rax
  DWORD v30; // r14d
  unsigned int m; // r15d
  __int64 v32; // r14
  int v33; // esi
  struct CVssDebugInfo *v34; // rax
  struct CVssDebugInfo *v35; // rax
  struct CVssDebugInfo *v36; // rax
  struct CVssDebugInfo *v37; // rax
  struct CVssDebugInfo *v38; // rax
  CVssDebugInfo *v39; // rax
  unsigned int v40; // edi
  __int64 bAlertable; // [rsp+20h] [rbp-598h]
  __int64 bAlertablea; // [rsp+20h] [rbp-598h]
  __int64 bAlertableb; // [rsp+20h] [rbp-598h]
  struct _GUID *v45; // [rsp+28h] [rbp-590h]
  struct _GUID *v46; // [rsp+28h] [rbp-590h]
  struct _GUID *v47; // [rsp+28h] [rbp-590h]
  const unsigned __int16 *v48; // [rsp+40h] [rbp-578h] BYREF
  const unsigned __int16 *v49; // [rsp+48h] [rbp-570h]
  const unsigned __int16 *v50; // [rsp+50h] [rbp-568h]
  int v51; // [rsp+58h] [rbp-560h]
  int v52; // [rsp+5Ch] [rbp-55Ch]
  int v53; // [rsp+60h] [rbp-558h]
  _BYTE v54[120]; // [rsp+68h] [rbp-550h] BYREF
  int v55; // [rsp+E0h] [rbp-4D8h]
  struct _GUID v56; // [rsp+F0h] [rbp-4C8h] BYREF
  LPVOID v57; // [rsp+100h] [rbp-4B8h] BYREF
  int v58; // [rsp+108h] [rbp-4B0h]
  unsigned int v59; // [rsp+124h] [rbp-494h]
  int v60; // [rsp+170h] [rbp-448h] BYREF
  _com_error *v61; // [rsp+178h] [rbp-440h] BYREF
  const std::exception *v62; // [rsp+180h] [rbp-438h] BYREF
  _BYTE v63[168]; // [rsp+188h] [rbp-430h] BYREF
  _BYTE v64[168]; // [rsp+230h] [rbp-388h] BYREF
  _BYTE v65[168]; // [rsp+2D8h] [rbp-2E0h] BYREF
  _BYTE v66[168]; // [rsp+380h] [rbp-238h] BYREF
  _BYTE v67[168]; // [rsp+428h] [rbp-190h] BYREF
  _BYTE v68[232]; // [rsp+4D0h] [rbp-E8h] BYREF
  char v69; // [rsp+5C0h] [rbp+8h]
  HANDLE *v70; // [rsp+5D0h] [rbp+18h]
  _DWORD *v71; // [rsp+5D8h] [rbp+20h]

  v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
  v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
  v50 = L"CORLOVLC";
  v51 = 782;
  v52 = 1;
  v53 = 255;
  v55 = 0x1000000;
  memset_0(v54, 0, sizeof(v54));
  CVssFunctionTracer::CVssFunctionTracer((__int64)&v57, (__int64)&v48, 0);
  try
  {
    v71 = (_DWORD *)((char *)this + 880);
    v4 = *((_DWORD *)this + 220);
    if ( v4 != 1 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 793;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      CVssFunctionTracer::TranslateGenericError(&v57, &v48, 2147549183LL, L"Bad state %d.", v4);
    }
    if ( !*((_DWORD *)this + 4) )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 799;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      CVssFunctionTracer::TranslateGenericError(&v57, &v48, 2147549183LL, L"Improper array size.");
    }
    v5 = (void *)*((_QWORD *)this + 3);
    if ( v5 )
    {
      ResetEvent(v5);
    }
    else
    {
      EventW = CreateEventW(0, 1, 0, 0);
      *((_QWORD *)this + 3) = EventW;
      if ( !EventW )
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 806;
        v52 = 1;
        v53 = 255;
        v55 = 0x1000000;
        memset_0(v54, 0, sizeof(v54));
        CVssFunctionTracer::TranslateGenericError(&v57, &v48, v8, L"CreateEvent( NULL, TRUE, FALSE, NULL )");
      }
    }
    v9 = 0;
    v69 = 0;
    for ( i = 1; (unsigned int)i < *((_DWORD *)this + 4); ++i )
    {
      if ( *(_DWORD *)(**((_QWORD **)this + 1) + 120LL) != *(_DWORD *)(*(_QWORD *)(*((_QWORD *)this + 1) + 8LL * i)
                                                                     + 120LL) )
      {
        v9 = 1;
        v69 = 1;
        break;
      }
    }
    v11 = 8LL * *((unsigned int *)this + 4);
    if ( !is_mul_ok(*((unsigned int *)this + 4), 8u) )
      v11 = -1;
    v12 = (HANDLE *)operator new[](v11, (const struct std::nothrow_t *)&std::nothrow);
    v70 = v12;
    if ( !v12 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 829;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      CVssFunctionTracer::Throw(&v57, &v48, 2147942414LL, L"Memory allocation error.");
    }
    v13 = 0;
    v14 = v58;
    while ( 1 )
    {
      v15 = *a2;
      if ( v13 >= *((_DWORD *)this + 4) )
        break;
      v16 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (int)v13);
      v12[v13] = *(HANDLE *)(v16 + 64);
      v17 = *((_DWORD *)this + 4);
      *(_QWORD *)(v16 + 48) = *((_QWORD *)this + 3);
      *(struct _GUID *)(v16 + 96) = v15;
      *(_DWORD *)(v16 + 112) = v17;
      *(_BYTE *)(v16 + 127) = v9;
      v14 = CVssWorkerThread::PrepareJob((CVssWorkerThread *)v16);
      v58 = v14;
      if ( v14 < 0 )
      {
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 853;
        v52 = 1;
        v53 = 255;
        v55 = 0x1000000;
        memset_0(v54, 0, sizeof(v54));
        CVssFunctionTracer::Throw(&v57, &v48, 2147942414LL, L"Error preparing the job %d [0x%08lx]. ", v13, v14);
      }
      ++v13;
    }
    v56 = *a2;
    CVssDiag::RecordGenericEvent((CVssQueuedVolumesList *)((char *)this + 32), 0x3FDu, 1, 0, v14, &v56);
    for ( j = 0; ; ++j )
    {
      v19 = *((_DWORD *)this + 4);
      if ( j >= v19 )
        break;
      started = CVssWorkerThread::StartJob(*(CVssWorkerThread **)(*((_QWORD *)this + 1) + 8LL * (int)j));
      v58 = started;
      if ( started < 0 )
      {
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 873;
        v52 = 1;
        v53 = 255;
        v55 = 0x1000000;
        memset_0(v54, 0, sizeof(v54));
        LODWORD(v45) = started;
        LODWORD(bAlertable) = j;
        CVssFunctionTracer::Throw(&v57, &v48, 2147942414LL, L"Error starting the job %d [0x%08lx]. ", bAlertable, v45);
      }
    }
    v21 = WaitForMultipleObjectsEx(v19, v12, 1, 0x1D4C0u, 0);
    CVssFunctionTracer::InterpretWaitForMultipleObjects((CVssFunctionTracer *)&v57, v21);
    v56 = *a2;
    CVssDiag::RecordGenericEvent((CVssQueuedVolumesList *)((char *)this + 32), 0x3FDu, 0, v21, v58, &v56);
    if ( v21 == 258 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 887;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      LODWORD(v46) = *((_DWORD *)this + 4);
      LODWORD(bAlertablea) = 120;
      CVssFunctionTracer::Throw(
        &v57,
        &v48,
        2147754771LL,
        L"It took longer than %d seconds to open %d handles",
        bAlertablea,
        v46);
    }
    if ( v21 == -1 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 892;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      LODWORD(bAlertablea) = *((_DWORD *)this + 4);
      CVssFunctionTracer::TranslateGenericError(
        &v57,
        &v48,
        (unsigned int)v58,
        L"WaitForMultipleObjects(%d,%p,1,%d) == 0x%08lx",
        bAlertablea,
        v12,
        120000,
        -1);
    }
    for ( k = 0; k < *((_DWORD *)this + 4); ++k )
    {
      v23 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (int)k);
      if ( !*(_BYTE *)(v23 + 124) )
      {
        v53 = 255;
        v55 = 0x1000000;
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        if ( *(_DWORD *)(v23 + 128) == -2147024882 )
        {
          v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
          v50 = L"CORLOVLC";
          v51 = 908;
          v52 = 1;
          memset_0(v54, 0, sizeof(v54));
          LODWORD(v46) = *(_DWORD *)(v23 + 132);
          LODWORD(bAlertablea) = -2147024882;
          CVssFunctionTracer::Throw(
            &v57,
            &v48,
            2147942414LL,
            L"Memory allocation error. [0x%08lx,0x%08lx,0x%08lx,0x%08lx]",
            bAlertablea,
            v46,
            *(_DWORD *)(v23 + 136),
            *(_DWORD *)(v23 + 140));
        }
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 915;
        v52 = 1;
        memset_0(v54, 0, sizeof(v54));
        v24 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v48, (CVssDebugInfo *)v68, *(_WORD **)(v23 + 80));
        v25 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v24, (CVssDebugInfo *)v67);
        v26 = CVssDebugInfo::operator<<(v25, (CVssDebugInfo *)v66, *(_DWORD *)(v23 + 128));
        v27 = CVssDebugInfo::operator<<(v26, (CVssDebugInfo *)v65, *(_DWORD *)(v23 + 132));
        v28 = CVssDebugInfo::operator<<(v27, (CVssDebugInfo *)v64, *(_DWORD *)(v23 + 136));
        v29 = CVssDebugInfo::operator<<(v28, (CVssDebugInfo *)v63, *(_DWORD *)(v23 + 140));
        CVssFunctionTracer::LogError((__int64)&v57, 0x3009u, (__int64)v29, 1u);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v64);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v65);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v66);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v67);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v68);
        CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v48);
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 918;
        v52 = 1;
        v53 = 255;
        v55 = 0x1000000;
        memset_0(v54, 0, sizeof(v54));
        LODWORD(bAlertablea) = k;
        CVssFunctionTracer::Throw(
          &v57,
          &v48,
          2147754771LL,
          L"Lovelace failed to hold writes at volume %d - '%s'",
          bAlertablea,
          *(_QWORD *)(v23 + 80));
      }
    }
    v56 = *a2;
    CVssDiag::RecordGenericEvent((CVssQueuedVolumesList *)((char *)this + 32), 0x3FEu, 1, 0, v58, &v56);
    if ( v69 )
    {
      v56 = *a2;
      CVssQueuedVolumesList::ProcessFlushLevels(this, &v56);
    }
    else
    {
      CVssQueuedVolumesList::ProcessAllVolumes(this);
    }
    v30 = WaitForMultipleObjectsEx(*((_DWORD *)this + 4), v12, 1, 0x1D4C0u, 0);
    CVssFunctionTracer::InterpretWaitForMultipleObjects((CVssFunctionTracer *)&v57, v30);
    v56 = *a2;
    CVssDiag::RecordGenericEvent((CVssQueuedVolumesList *)((char *)this + 32), 0x3FEu, 0, v30, v58, &v56);
    if ( v30 == 258 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 952;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      LODWORD(v47) = *((_DWORD *)this + 4);
      LODWORD(bAlertableb) = 120;
      CVssFunctionTracer::Throw(
        &v57,
        &v48,
        2147754771LL,
        L"It took longer than %d seconds to  flush %d volumes",
        bAlertableb,
        v47);
    }
    if ( v30 == -1 )
    {
      v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
      v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
      v50 = L"CORLOVLC";
      v51 = 958;
      v52 = 1;
      v53 = 255;
      v55 = 0x1000000;
      memset_0(v54, 0, sizeof(v54));
      LODWORD(bAlertableb) = *((_DWORD *)this + 4);
      CVssFunctionTracer::TranslateGenericError(
        &v57,
        &v48,
        (unsigned int)v58,
        L"WaitForMultipleObjects(%d,%p,1,%d) == 0x%08lx",
        bAlertableb,
        v12,
        120000,
        -1);
    }
    for ( m = 0; m < *((_DWORD *)this + 4); ++m )
    {
      v32 = *(_QWORD *)(*((_QWORD *)this + 1) + 8LL * (int)m);
      if ( !*(_BYTE *)(v32 + 125) )
      {
        v33 = *(_DWORD *)(v32 + 128);
        if ( v33 != -2147024882 && *(_DWORD *)(v32 + 132) != -2147024882 && *(_DWORD *)(v32 + 140) != -2147024882 )
        {
          v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
          v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
          v50 = L"CORLOVLC";
          v51 = 984;
          v52 = 1;
          v53 = 255;
          v55 = 0x1000000;
          memset_0(v54, 0, sizeof(v54));
          v34 = CVssDebugInfo::operator<<((struct CVssDebugInfo *)&v48, (CVssDebugInfo *)v63, *(_WORD **)(v32 + 80));
          v35 = (struct CVssDebugInfo *)CVssDebugInfo::operator<<(v34, (CVssDebugInfo *)v64);
          v36 = CVssDebugInfo::operator<<(v35, (CVssDebugInfo *)v65, *(_DWORD *)(v32 + 128));
          v37 = CVssDebugInfo::operator<<(v36, (CVssDebugInfo *)v66, *(_DWORD *)(v32 + 132));
          v38 = CVssDebugInfo::operator<<(v37, (CVssDebugInfo *)v67, *(_DWORD *)(v32 + 136));
          v39 = CVssDebugInfo::operator<<(v38, (CVssDebugInfo *)v68, *(_DWORD *)(v32 + 140));
          CVssFunctionTracer::LogError((__int64)&v57, 0x3009u, (__int64)v39, 1u);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v67);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v66);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v65);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v64);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)v63);
          CVssDebugInfo::~CVssDebugInfo((CVssDebugInfo *)&v48);
          v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
          v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
          v50 = L"CORLOVLC";
          v51 = 987;
          v52 = 1;
          v53 = 255;
          v55 = 0x1000000;
          memset_0(v54, 0, sizeof(v54));
          LODWORD(bAlertableb) = m;
          CVssFunctionTracer::Throw(
            &v57,
            &v48,
            2147754771LL,
            L"Lovelace failed to hold writes at volume %d - '%s'",
            bAlertableb,
            *(_QWORD *)(v32 + 80));
        }
        v48 = L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx";
        v49 = L"CVssQueuedVolumesList::FlushAndHoldAllWrites";
        v50 = L"CORLOVLC";
        v51 = 977;
        v52 = 1;
        v53 = 255;
        v55 = 0x1000000;
        memset_0(v54, 0, sizeof(v54));
        LODWORD(v47) = *(_DWORD *)(v32 + 132);
        LODWORD(bAlertableb) = v33;
        CVssFunctionTracer::Throw(
          &v57,
          &v48,
          2147942414LL,
          L"Memory allocation error. [0x%08lx,0x%08lx,0x%08lx,0x%08lx]",
          bAlertableb,
          v47,
          *(_DWORD *)(v32 + 136),
          *(_DWORD *)(v32 + 140));
      }
    }
    *v71 = 2;
  }
  catch ( long v60 )
  {
    CVssFunctionTracer::HandleHresultException(
      (CVssFunctionTracer *)&v57,
      v60,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolumesList::FlushAndHoldAllWrites",
      0x3E3u,
      v59);
    v12 = v70;
  }
  catch ( _com_error *v61 )
  {
    CVssFunctionTracer::HandleComException(
      (CVssFunctionTracer *)&v57,
      v61,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolumesList::FlushAndHoldAllWrites",
      0x3E3u,
      v59);
  }
  catch ( std::bad_alloc )
  {
    CVssFunctionTracer::HandleStdBadAllocException(
      (CVssFunctionTracer *)&v57,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolumesList::FlushAndHoldAllWrites",
      0x3E3u,
      v59);
    v12 = v70;
  }
  catch ( const std::exception *v62 )
  {
    CVssFunctionTracer::HandleStdGenericException(
      (CVssFunctionTracer *)&v57,
      v62,
      L"base\\stor\\vss\\modules\\coord\\src\\lovelace.cxx",
      L"CORLOVLC",
      L"CVssQueuedVolumesList::FlushAndHoldAllWrites",
      0x3E3u,
      v59);
  }
  operator delete(v12);
  v40 = v58;
  if ( v58 < 0 )
    *v71 = 4;
  CVssFunctionTracer::~CVssFunctionTracer(&v57);
  return v40;
}

```

## disassembly

```asm
0x140040c48  push    rbx
0x140040c4a  push    rsi
0x140040c4b  push    rdi
0x140040c4c  push    r12
0x140040c4e  push    r13
0x140040c50  push    r14
0x140040c52  push    r15
0x140040c54  sub     rsp, 580h
0x140040c5b  mov     r12, rdx
0x140040c5e  mov     rdi, rcx
0x140040c61  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x140040c68  mov     [rsp+5B8h+var_578], r13
0x140040c6d  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040c74  mov     [rsp+5B8h+var_570], rax
0x140040c79  lea     rax, aCorlovlc; "CORLOVLC"
0x140040c80  mov     [rsp+5B8h+var_568], rax
0x140040c85  mov     [rsp+5B8h+var_560], 30Eh
0x140040c8d  mov     r14d, 1
0x140040c93  mov     [rsp+5B8h+var_55C], r14d
0x140040c98  mov     [rsp+5B8h+var_558], 0FFh
0x140040ca0  xor     ebx, ebx
0x140040ca2  mov     [rsp+5B8h+var_4D8], 1000000h
0x140040cad  lea     r15d, [r14+77h]
0x140040cb1  mov     r8d, r15d; Size
0x140040cb4  xor     edx, edx; Val
0x140040cb6  lea     rcx, [rsp+5B8h+var_550]; void *
0x140040cbb  call    memset_0
0x140040cc0  xor     r8d, r8d
0x140040cc3  lea     rdx, [rsp+5B8h+var_578]
0x140040cc8  lea     rcx, [rsp+5B8h+var_4B8]
0x140040cd0  call    ??0CVssFunctionTracer@@QEAA@UCVssDebugInfo@@QEAG@Z; CVssFunctionTracer::CVssFunctionTracer(CVssDebugInfo,ushort * const)
0x140040cd5  nop
0x140040cd6  mov     [rsp+5B8h+arg_10], rbx
0x140040cde  lea     rax, [rdi+370h]
0x140040ce5  mov     [rsp+5B8h+arg_18], rax
0x140040ced  mov     esi, [rax]
0x140040cef  cmp     esi, r14d
0x140040cf2  jz      short loc_140040D63
0x140040cf4  mov     [rsp+5B8h+var_578], r13
0x140040cf9  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040d00  mov     [rsp+5B8h+var_570], rax
0x140040d05  lea     rax, aCorlovlc; "CORLOVLC"
0x140040d0c  mov     [rsp+5B8h+var_568], rax
0x140040d11  mov     [rsp+5B8h+var_560], 319h
0x140040d19  mov     [rsp+5B8h+var_55C], r14d
0x140040d1e  mov     [rsp+5B8h+var_558], 0FFh
0x140040d26  mov     [rsp+5B8h+var_4D8], 1000000h
0x140040d31  mov     r8d, r15d; Size
0x140040d34  xor     edx, edx; Val
0x140040d36  lea     rcx, [rsp+5B8h+var_550]; void *
0x140040d3b  call    memset_0
0x140040d40  mov     dword ptr [rsp+5B8h+bAlertable], esi
0x140040d44  lea     r9, aBadStateD_0; "Bad state %d."
0x140040d4b  mov     r8d, 8000FFFFh
0x140040d51  lea     rdx, [rsp+5B8h+var_578]
0x140040d56  lea     rcx, [rsp+5B8h+var_4B8]
0x140040d5e  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140040d63  cmp     [rdi+10h], ebx
0x140040d66  ja      short loc_140040DD3
0x140040d68  mov     [rsp+5B8h+var_578], r13
0x140040d6d  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040d74  mov     [rsp+5B8h+var_570], rax
0x140040d79  lea     rax, aCorlovlc; "CORLOVLC"
0x140040d80  mov     [rsp+5B8h+var_568], rax
0x140040d85  mov     [rsp+5B8h+var_560], 31Fh
0x140040d8d  mov     [rsp+5B8h+var_55C], r14d
0x140040d92  mov     [rsp+5B8h+var_558], 0FFh
0x140040d9a  mov     [rsp+5B8h+var_4D8], 1000000h
0x140040da5  mov     r8, r15; Size
0x140040da8  xor     edx, edx; Val
0x140040daa  lea     rcx, [rsp+5B8h+var_550]; void *
0x140040daf  call    memset_0
0x140040db4  lea     r9, aImproperArrayS; "Improper array size."
0x140040dbb  mov     r8d, 8000FFFFh
0x140040dc1  lea     rdx, [rsp+5B8h+var_578]
0x140040dc6  lea     rcx, [rsp+5B8h+var_4B8]
0x140040dce  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140040dd3  mov     rcx, [rdi+18h]; hEvent
0x140040dd7  test    rcx, rcx
0x140040dda  jnz     loc_140040E79
0x140040de0  xor     r9d, r9d; lpName
0x140040de3  xor     r8d, r8d; bInitialState
0x140040de6  mov     edx, r14d; bManualReset
0x140040de9  call    cs:__imp_CreateEventW
0x140040def  mov     [rdi+18h], rax
0x140040df3  test    rax, rax
0x140040df6  jnz     loc_140040E7F
0x140040dfc  call    cs:__imp_GetLastError
0x140040e02  mov     edi, eax
0x140040e04  test    eax, eax
0x140040e06  jle     short loc_140040E11
0x140040e08  movzx   edi, ax
0x140040e0b  or      edi, 80070000h
0x140040e11  mov     [rsp+5B8h+var_578], r13
0x140040e16  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040e1d  mov     [rsp+5B8h+var_570], rax
0x140040e22  lea     rax, aCorlovlc; "CORLOVLC"
0x140040e29  mov     [rsp+5B8h+var_568], rax
0x140040e2e  mov     [rsp+5B8h+var_560], 326h
0x140040e36  mov     [rsp+5B8h+var_55C], r14d
0x140040e3b  mov     [rsp+5B8h+var_558], 0FFh
0x140040e43  mov     [rsp+5B8h+var_4D8], 1000000h
0x140040e4e  mov     r8, r15; Size
0x140040e51  xor     edx, edx; Val
0x140040e53  lea     rcx, [rsp+5B8h+var_550]; void *
0x140040e58  call    memset_0
0x140040e5d  lea     r9, aCreateeventNul_0; "CreateEvent( NULL, TRUE, FALSE, NULL )"
0x140040e64  mov     r8d, edi
0x140040e67  lea     rdx, [rsp+5B8h+var_578]
0x140040e6c  lea     rcx, [rsp+5B8h+var_4B8]
0x140040e74  call    ?TranslateGenericError@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JPEBGZZ; CVssFunctionTracer::TranslateGenericError(CVssDebugInfo,long,ushort const *,...)
0x140040e79  call    cs:__imp_ResetEvent
0x140040e7f  mov     r13b, bl
0x140040e82  mov     [rsp+5B8h+arg_0], bl
0x140040e89  mov     r8, [rdi+8]
0x140040e8d  mov     rax, [r8]
0x140040e90  mov     r9d, [rax+78h]
0x140040e94  mov     edx, r14d
0x140040e97  cmp     edx, [rdi+10h]
0x140040e9a  jnb     short loc_140040EB9
0x140040e9c  movsxd  rax, edx
0x140040e9f  mov     rcx, [r8+rax*8]
0x140040ea3  cmp     r9d, [rcx+78h]
0x140040ea7  jnz     short loc_140040EAE
0x140040ea9  add     edx, r14d
0x140040eac  jmp     short loc_140040E97
0x140040eae  mov     r13b, r14b
0x140040eb1  mov     [rsp+5B8h+arg_0], r14b
0x140040eb9  mov     ecx, [rdi+10h]
0x140040ebc  mov     eax, 8
0x140040ec1  mul     rcx
0x140040ec4  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140040ecb  cmovb   rax, rcx
0x140040ecf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140040ed6  mov     rcx, rax; unsigned __int64
0x140040ed9  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x140040ede  mov     rsi, rax
0x140040ee1  mov     [rsp+5B8h+arg_10], rax
0x140040ee9  test    rax, rax
0x140040eec  jnz     short loc_140040F60
0x140040eee  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x140040ef5  mov     [rsp+5B8h+var_578], r13
0x140040efa  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040f01  mov     [rsp+5B8h+var_570], rax
0x140040f06  lea     rax, aCorlovlc; "CORLOVLC"
0x140040f0d  mov     [rsp+5B8h+var_568], rax
0x140040f12  mov     [rsp+5B8h+var_560], 33Dh
0x140040f1a  mov     [rsp+5B8h+var_55C], r14d
0x140040f1f  mov     [rsp+5B8h+var_558], 0FFh
0x140040f27  mov     [rsp+5B8h+var_4D8], 1000000h
0x140040f32  mov     r8, r15; Size
0x140040f35  xor     edx, edx; Val
0x140040f37  lea     rcx, [rsp+5B8h+var_550]; void *
0x140040f3c  call    memset_0
0x140040f41  lea     r9, aMemoryAllocati_2; "Memory allocation error."
0x140040f48  mov     r8d, 8007000Eh
0x140040f4e  lea     rdx, [rsp+5B8h+var_578]
0x140040f53  lea     rcx, [rsp+5B8h+var_4B8]
0x140040f5b  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x140040f60  mov     r14d, ebx
0x140040f63  mov     r15d, [rsp+5B8h+var_4B0]
0x140040f6b  movaps  xmm0, xmmword ptr [r12]
0x140040f70  cmp     r14d, [rdi+10h]
0x140040f74  jnb     loc_140041046
0x140040f7a  movsxd  rcx, r14d
0x140040f7d  mov     rax, [rdi+8]
0x140040f81  mov     rcx, [rax+rcx*8]; this
0x140040f85  mov     edx, r14d
0x140040f88  mov     rax, [rcx+40h]
0x140040f8c  mov     [rsi+rdx*8], rax
0x140040f90  mov     edx, [rdi+10h]
0x140040f93  mov     rax, [rdi+18h]
0x140040f97  mov     [rcx+30h], rax
0x140040f9b  movdqu  xmmword ptr [rcx+60h], xmm0
0x140040fa0  mov     [rcx+70h], edx
0x140040fa3  mov     [rcx+7Fh], r13b
0x140040fa7  call    ?PrepareJob@CVssWorkerThread@@QEAAJXZ; CVssWorkerThread::PrepareJob(void)
0x140040fac  mov     r15d, eax
0x140040faf  mov     [rsp+5B8h+var_4B0], eax
0x140040fb6  test    eax, eax
0x140040fb8  jns     loc_14004103E
0x140040fbe  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x140040fc5  mov     [rsp+5B8h+var_578], r13
0x140040fca  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x140040fd1  mov     [rsp+5B8h+var_570], rax
0x140040fd6  lea     rax, aCorlovlc; "CORLOVLC"
0x140040fdd  mov     [rsp+5B8h+var_568], rax
0x140040fe2  mov     [rsp+5B8h+var_560], 355h
0x140040fea  mov     [rsp+5B8h+var_55C], 1
0x140040ff2  mov     [rsp+5B8h+var_558], 0FFh
0x140040ffa  mov     [rsp+5B8h+var_4D8], 1000000h
0x140041005  xor     edx, edx; Val
0x140041007  lea     r8d, [rdx+78h]; Size
0x14004100b  lea     rcx, [rsp+5B8h+var_550]; void *
0x140041010  call    memset_0
0x140041015  mov     dword ptr [rsp+5B8h+var_590], r15d
0x14004101a  mov     dword ptr [rsp+5B8h+bAlertable], r14d
0x14004101f  lea     r9, aErrorPreparing; "Error preparing the job %d [0x%08lx]. "
0x140041026  mov     r8d, 8007000Eh
0x14004102c  lea     rdx, [rsp+5B8h+var_578]
0x140041031  lea     rcx, [rsp+5B8h+var_4B8]
0x140041039  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004103e  inc     r14d
0x140041041  jmp     loc_140040F6B
0x140041046  lea     r13, [rdi+20h]
0x14004104a  movdqa  xmmword ptr [rsp+5B8h+var_4C8.Data1], xmm0
0x140041053  lea     rax, [rsp+5B8h+var_4C8]
0x14004105b  mov     [rsp+5B8h+var_590], rax; struct _GUID *
0x140041060  mov     dword ptr [rsp+5B8h+bAlertable], r15d; int
0x140041065  xor     r9d, r9d; unsigned int
0x140041068  lea     r15d, [r9+1]
0x14004106c  mov     r8d, r15d; unsigned int
0x14004106f  mov     edx, 3FDh; unsigned int
0x140041074  mov     rcx, r13; this
0x140041077  call    ?RecordGenericEvent@CVssDiag@@QEAAXKKKJU_GUID@@@Z; CVssDiag::RecordGenericEvent(ulong,ulong,ulong,long,_GUID)
0x14004107c  mov     r14d, ebx
0x14004107f  mov     ecx, [rdi+10h]; nCount
0x140041082  cmp     r14d, ecx
0x140041085  jnb     loc_14004113B
0x14004108b  movsxd  rax, r14d
0x14004108e  mov     rcx, [rdi+8]
0x140041092  mov     rcx, [rcx+rax*8]; this
0x140041096  call    ?StartJob@CVssWorkerThread@@QEAAJXZ; CVssWorkerThread::StartJob(void)
0x14004109b  mov     r15d, eax
0x14004109e  mov     [rsp+5B8h+var_4B0], eax
0x1400410a5  test    eax, eax
0x1400410a7  jns     loc_14004112D
0x1400410ad  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x1400410b4  mov     [rsp+5B8h+var_578], r13
0x1400410b9  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x1400410c0  mov     [rsp+5B8h+var_570], rax
0x1400410c5  lea     rax, aCorlovlc; "CORLOVLC"
0x1400410cc  mov     [rsp+5B8h+var_568], rax
0x1400410d1  mov     [rsp+5B8h+var_560], 369h
0x1400410d9  mov     [rsp+5B8h+var_55C], 1
0x1400410e1  mov     [rsp+5B8h+var_558], 0FFh
0x1400410e9  mov     [rsp+5B8h+var_4D8], 1000000h
0x1400410f4  xor     edx, edx; Val
0x1400410f6  lea     r8d, [rdx+78h]; Size
0x1400410fa  lea     rcx, [rsp+5B8h+var_550]; void *
0x1400410ff  call    memset_0
0x140041104  mov     dword ptr [rsp+5B8h+var_590], r15d
0x140041109  mov     dword ptr [rsp+5B8h+bAlertable], r14d
0x14004110e  lea     r9, aErrorStartingT_0; "Error starting the job %d [0x%08lx]. "
0x140041115  mov     r8d, 8007000Eh
0x14004111b  lea     rdx, [rsp+5B8h+var_578]
0x140041120  lea     rcx, [rsp+5B8h+var_4B8]
0x140041128  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004112d  mov     r15d, 1
0x140041133  add     r14d, r15d
0x140041136  jmp     loc_14004107F
0x14004113b  mov     dword ptr [rsp+5B8h+bAlertable], ebx; bAlertable
0x14004113f  mov     r9d, 1D4C0h; dwMilliseconds
0x140041145  mov     r8d, r15d; bWaitAll
0x140041148  mov     rdx, rsi; lpHandles
0x14004114b  call    cs:__imp_WaitForMultipleObjectsEx
0x140041151  mov     r14d, eax
0x140041154  mov     edx, eax; unsigned int
0x140041156  lea     rcx, [rsp+5B8h+var_4B8]; this
0x14004115e  call    ?InterpretWaitForMultipleObjects@CVssFunctionTracer@@QEAAXK@Z; CVssFunctionTracer::InterpretWaitForMultipleObjects(ulong)
0x140041163  movaps  xmm0, xmmword ptr [r12]
0x140041168  movdqa  xmmword ptr [rsp+5B8h+var_4C8.Data1], xmm0
0x140041171  lea     rax, [rsp+5B8h+var_4C8]
0x140041179  mov     [rsp+5B8h+var_590], rax; struct _GUID *
0x14004117e  mov     ecx, [rsp+5B8h+var_4B0]
0x140041185  mov     dword ptr [rsp+5B8h+bAlertable], ecx; int
0x140041189  mov     r9d, r14d; unsigned int
0x14004118c  xor     r8d, r8d; unsigned int
0x14004118f  mov     edx, 3FDh; unsigned int
0x140041194  mov     rcx, r13; this
0x140041197  call    ?RecordGenericEvent@CVssDiag@@QEAAXKKKJU_GUID@@@Z; CVssDiag::RecordGenericEvent(ulong,ulong,ulong,long,_GUID)
0x14004119c  cmp     r14d, 102h
0x1400411a3  jnz     loc_14004122B
0x1400411a9  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x1400411b0  mov     [rsp+5B8h+var_578], r13
0x1400411b5  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
0x1400411bc  mov     [rsp+5B8h+var_570], rax
0x1400411c1  lea     rax, aCorlovlc; "CORLOVLC"
0x1400411c8  mov     [rsp+5B8h+var_568], rax
0x1400411cd  mov     [rsp+5B8h+var_560], 377h
0x1400411d5  mov     [rsp+5B8h+var_55C], r15d
0x1400411da  mov     [rsp+5B8h+var_558], 0FFh
0x1400411e2  mov     [rsp+5B8h+var_4D8], 1000000h
0x1400411ed  xor     edx, edx; Val
0x1400411ef  lea     r8d, [rdx+78h]; Size
0x1400411f3  lea     rcx, [rsp+5B8h+var_550]; void *
0x1400411f8  call    memset_0
0x1400411fd  mov     eax, [rdi+10h]
0x140041200  mov     dword ptr [rsp+5B8h+var_590], eax
0x140041204  mov     dword ptr [rsp+5B8h+bAlertable], 78h ; 'x'
0x14004120c  lea     r9, aItTookLongerTh; "It took longer than %d seconds to open "...
0x140041213  mov     r8d, 80042313h
0x140041219  lea     rdx, [rsp+5B8h+var_578]
0x14004121e  lea     rcx, [rsp+5B8h+var_4B8]
0x140041226  call    ?Throw@CVssFunctionTracer@@QEAAXUCVssDebugInfo@@JQEAGZZ; CVssFunctionTracer::Throw(CVssDebugInfo,long,ushort * const,...)
0x14004122b  cmp     r14d, 0FFFFFFFFh
0x14004122f  jnz     loc_1400412C3
0x140041235  lea     r13, aBaseStorVssMod_3; "base\\stor\\vss\\modules\\coord\\src\\l"...
0x14004123c  mov     [rsp+5B8h+var_578], r13
0x140041241  lea     rax, aCvssqueuedvolu_8; "CVssQueuedVolumesList::FlushAndHoldAllW"...
  ... truncated ...
```
