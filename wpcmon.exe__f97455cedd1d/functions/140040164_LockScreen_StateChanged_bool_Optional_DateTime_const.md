# LockScreen::StateChanged(bool,Optional<DateTime> const &)

- ea: `0x140040164`
- end: `0x140040976`
- name: `?StateChanged@LockScreen@@QEAAX_NAEBV?$Optional@VDateTime@@@@@Z`
- size: `2066`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x14002f160`

## callees

- `0x140005530`
- `0x140006338`
- `0x140009858`
- `0x14000ccac`
- `0x1400251c4`
- `0x14002a754`
- `0x14003d594`
- `0x14003d77c`
- `0x14003d918`
- `0x14003e348`
- `0x14003e8e8`
- `0x140040164`
- `0x140060f58`
- `0x140065b3c`
- `0x140067fe8`
- `0x140068dbc`
- `0x140090810`
- `0x140090f4c`
- `0x1400a8010`

## import_xrefs

- `KERNEL32!CompareFileTime` at `0x1400406d8`
- `KERNEL32!CompareFileTime` at `0x1400406ec`
- `KERNEL32!CompareFileTime` at `0x1400406d8`
- `KERNEL32!CompareFileTime` at `0x1400406ec`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400404bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400405cb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400404bb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x1400405cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall LockScreen::StateChanged(__int64 a1, char a2, __int64 a3)
{
  bool v6; // zf
  unsigned __int64 v7; // rbx
  __int64 v8; // rdx
  char v9; // r12
  UiThread *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  unsigned __int64 v13; // rsi
  _DWORD *v14; // rax
  _DWORD *v15; // rcx
  double v16; // xmm0_8
  unsigned __int64 v17; // rax
  __int64 v18; // r14
  __int64 v19; // rcx
  int v20; // eax
  unsigned int v21; // r8d
  unsigned int v22; // r9d
  double v23; // xmm0_8
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // rdx
  __int64 v26; // rsi
  __int64 v27; // rcx
  int v28; // edx
  char *v29; // rcx
  __int64 v30; // rax
  __int64 v31; // rcx
  volatile signed __int32 *v32; // rsi
  __int64 v33; // rsi
  __int64 v34; // rcx
  int v35; // edx
  char *v36; // rcx
  __int64 v37; // rax
  __int64 v38; // rcx
  volatile signed __int32 *v39; // rdi
  const FILETIME *v40; // rsi
  const FILETIME *v41; // r14
  int v42; // ecx
  __int64 v43; // rcx
  int v44; // edx
  _BYTE *v45; // rcx
  _QWORD *v46; // rbx
  UiThread *v47; // rcx
  UiThread *v48; // rcx
  unsigned __int64 v49; // rdx
  __int64 v50; // rax
  unsigned __int64 v51; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v52; // [rsp+38h] [rbp-C8h] BYREF
  unsigned __int64 v53; // [rsp+40h] [rbp-C0h]
  __int64 v54; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v55[12]; // [rsp+50h] [rbp-B0h] BYREF
  int v56; // [rsp+5Ch] [rbp-A4h]
  _BYTE *v57; // [rsp+60h] [rbp-A0h]
  __int128 v58; // [rsp+70h] [rbp-90h] BYREF
  _OWORD pExceptionObject[3]; // [rsp+80h] [rbp-80h] BYREF
  _OWORD v60[3]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v61[64]; // [rsp+E0h] [rbp-20h] BYREF
  int v62; // [rsp+120h] [rbp+20h]

  (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)(*(_QWORD *)a1 + 80LL) + 48LL))(*(_QWORD *)a1 + 80LL, &v52);
  v6 = a2 == 0;
  v7 = v53;
  if ( v6 )
  {
    v8 = v53 + 80;
    if ( *(_QWORD *)(((v53 + 80) & -(__int64)(v53 != -81)) + 0x18) )
    {
      v9 = 1;
      memset(v60, 0, 32);
      std::wstring::_Construct<1,unsigned short const *>((char **)v60, L"Dismissing lock window", 0x16u);
      wpc::UI::Logging::MonitorUILogger::LogMessage(v60);
      std::wstring::~wstring((char **)v60);
      v7 = v53;
    }
    else
    {
      v9 = 0;
    }
    v10 = *(UiThread **)(v7 + 104);
    if ( v10 )
    {
      UiThread::~UiThread(v10);
      *(_QWORD *)(v7 + 104) = 0;
      v7 = v53;
    }
    if ( *(_QWORD *)((a3 & -(__int64)(a3 != -1)) + 0x10) )
    {
      v11 = *(_QWORD *)(a3 + 16);
      if ( !v11 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v60, -2147467261);
        throw (ErrorCodeException *)v60;
      }
      v54 = 9000000000LL;
      DateTime::operator-(v11, &v58, &v54);
      v12 = *(_QWORD *)(a3 + 16);
      if ( !v12 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v60, -2147467261);
        throw (ErrorCodeException *)v60;
      }
      v54 = 1200000000;
      DateTime::operator-(v12, pExceptionObject, &v54);
      v13 = v53;
      v8 = 0x8000000000000000uLL;
      if ( !*(_QWORD *)((v53 & -(__int64)(v53 != -1)) + 0x48) )
        goto LABEL_17;
      v14 = *(_DWORD **)(v53 + 72);
      if ( !v14 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v60, -2147467261);
        throw (ErrorCodeException *)v60;
      }
      v15 = *(_DWORD **)(a3 + 16);
      if ( !v15 )
      {
        ErrorCodeException::ErrorCodeException((ErrorCodeException *)v60, -2147467261);
        throw (ErrorCodeException *)v60;
      }
      *(_QWORD *)&v16 = COERCE_UNSIGNED_INT64((double)(*v14 - *v15)) & _xmm;
      v17 = 0;
      if ( v16 >= 9.223372036854776e18 )
      {
        v16 = v16 - 9.223372036854776e18;
        if ( v16 < 9.223372036854776e18 )
          v17 = 0x8000000000000000uLL;
      }
      if ( v17 + (unsigned int)(int)v16 > TimeSpan::Minute )
      {
LABEL_17:
        v18 = *(_QWORD *)(a3 + 16);
        if ( !v18 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)v60, -2147467261);
          throw (ErrorCodeException *)v60;
        }
        v19 = *(_QWORD *)(v53 + 72);
        if ( v19 )
        {
          anonymous_namespace_::LockScreenImpl::LockWarnings::_LockWarnings(v19, 0x8000000000000000uLL);
          *(_QWORD *)(v13 + 72) = 0;
        }
        v20 = *(_DWORD *)(v18 + 8);
        *(_QWORD *)(v13 + 8) = *(_QWORD *)v18;
        *(_DWORD *)(v13 + 16) = v20;
        Threadpool::Threadpool((Threadpool *)(v13 + 24), v8, 1);
        *(_QWORD *)(v13 + 40) = 0;
        *(_QWORD *)(v13 + 48) = 0;
        *(_QWORD *)(v13 + 56) = 0;
        *(_QWORD *)(v13 + 64) = 0;
        *(_QWORD *)(v13 + 72) = v13 + 8;
        DateTime::GetCurrent(&v54);
        v21 = HIDWORD(v54);
        v22 = v54;
        if ( !v9 )
          goto LABEL_25;
        v51 = v58;
        *(_QWORD *)&v23 = COERCE_UNSIGNED_INT64((double)((int)v58 - (int)v54)) & _xmm;
        v24 = 0;
        if ( v23 >= 9.223372036854776e18 )
        {
          v23 = v23 - 9.223372036854776e18;
          if ( v23 < 9.223372036854776e18 )
            v24 = 0x8000000000000000uLL;
        }
        if ( v24 + (unsigned int)(int)v23 >= TimeSpan::Minute )
        {
LABEL_25:
          v54 = *(_QWORD *)&pExceptionObject[0];
          v51 = __PAIR64__(v21, v22);
          v25 = *(_QWORD *)&pExceptionObject[0] - __PAIR64__(v21, v22);
          if ( (__int64)(*(_QWORD *)&pExceptionObject[0] - __PAIR64__(v21, v22)) < 0 )
            v25 = 0;
          if ( v25 > TimeSpan::Minute )
          {
            memset(v60, 0, 32);
            std::wstring::_Construct<1,unsigned short const *>((char **)v60, L"Set 15 min warning timer", 0x18u);
            wpc::UI::Logging::MonitorUILogger::LogMessage(v60);
            std::wstring::~wstring((char **)v60);
            v26 = *(_QWORD *)(v53 + 72);
            if ( !v26 )
            {
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
              throw (ErrorCodeException *)pExceptionObject;
            }
            *(_QWORD *)&v60[0] = a1;
            v27 = *(_QWORD *)(a3 + 16);
            if ( v27 )
            {
              v28 = 0;
              *(_QWORD *)((char *)v60 + 12) = *(_QWORD *)v27;
              DWORD1(v60[1]) = *(_DWORD *)(v27 + 8);
            }
            else
            {
              v28 = -1;
            }
            v29 = (char *)v60 + 12;
            if ( v28 == -1 )
              v29 = 0;
            *((_QWORD *)&v60[1] + 1) = v29;
            v62 = 0;
            _o_wcscpy_s(v61, 32, L"TimeWarning");
            v30 = Threadpool::QueueDelayedWorkItem__lambda_f00b0fc701dfedcc755a4c28b6159184___(
                    (int)v26 + 16,
                    (unsigned int)&v54,
                    (unsigned int)v61,
                    (unsigned int)v60,
                    (__int64)&v58);
            v31 = *(_QWORD *)(v53 + 72);
            if ( !v31 )
            {
              ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
              throw (ErrorCodeException *)pExceptionObject;
            }
            std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=(v31 + 32, v30);
            v32 = *(volatile signed __int32 **)v55;
            if ( *(_QWORD *)v55 )
            {
              if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)v55 + 8LL), 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v32)(v32);
                if ( _InterlockedExchangeAdd(v32 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v32 + 8LL))(v32);
              }
            }
          }
        }
        memset(v60, 0, 32);
        std::wstring::_Construct<1,unsigned short const *>((char **)v60, L"Set 2 min warning timer", 0x17u);
        wpc::UI::Logging::MonitorUILogger::LogMessage(v60);
        std::wstring::~wstring((char **)v60);
        v33 = *(_QWORD *)(v53 + 72);
        if ( !v33 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        *(_QWORD *)&v60[0] = a1;
        v34 = *(_QWORD *)(a3 + 16);
        if ( v34 )
        {
          v35 = 0;
          *(_QWORD *)((char *)v60 + 12) = *(_QWORD *)v34;
          DWORD1(v60[1]) = *(_DWORD *)(v34 + 8);
        }
        else
        {
          v35 = -1;
        }
        v36 = (char *)v60 + 12;
        if ( v35 == -1 )
          v36 = 0;
        *((_QWORD *)&v60[1] + 1) = v36;
        v62 = 0;
        _o_wcscpy_s(v61, 32, L"TimeWarning");
        v37 = Threadpool::QueueDelayedWorkItem__lambda_a3590754413f215dfd6baebbd98dd29f___(
                (int)v33 + 16,
                (unsigned int)&v58,
                (unsigned int)v61,
                (unsigned int)v60,
                (__int64)pExceptionObject);
        v38 = *(_QWORD *)(v53 + 72);
        if ( !v38 )
        {
          ErrorCodeException::ErrorCodeException((ErrorCodeException *)pExceptionObject, -2147467261);
          throw (ErrorCodeException *)pExceptionObject;
        }
        std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=(v38 + 48, v37);
        v39 = (volatile signed __int32 *)*((_QWORD *)&v58 + 1);
        if ( *((_QWORD *)&v58 + 1) )
        {
          if ( !_InterlockedDecrement((volatile signed __int32 *)(*((_QWORD *)&v58 + 1) + 8LL)) )
          {
            (**(void (__fastcall ***)(volatile signed __int32 *))v39)(v39);
            if ( !_InterlockedDecrement(v39 + 3) )
              (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v39 + 8LL))(v39);
          }
        }
      }
    }
    else if ( *(_QWORD *)(v7 + 72) )
    {
      ((void (*)(void))anonymous_namespace_::LockScreenImpl::LockWarnings::_LockWarnings)();
      *(_QWORD *)(v7 + 72) = 0;
    }
    goto LABEL_78;
  }
  if ( *(_QWORD *)(v53 + 72) )
  {
    ((void (*)(void))anonymous_namespace_::LockScreenImpl::LockWarnings::_LockWarnings)();
    *(_QWORD *)(v7 + 72) = 0;
    v7 = v53;
  }
  if ( *(_QWORD *)(((v7 + 80) & -(__int64)(v7 != -81)) + 0x18) )
  {
    v8 = v7 + 112;
    v40 = *(const FILETIME **)(a3 + 16);
    v41 = *(const FILETIME **)(((v7 + 112) & -(__int64)(v7 != -113)) + 0x10);
    if ( v41 == v40 )
      goto LABEL_78;
    if ( !v41 )
    {
      v42 = -(v40 != 0);
      goto LABEL_63;
    }
    if ( v40 )
    {
      if ( CompareFileTime(v41, *(const FILETIME **)(a3 + 16)) >= 0 )
        v42 = CompareFileTime(v41, v40) > 0;
      else
        v42 = -1;
LABEL_63:
      if ( !v42 )
        goto LABEL_78;
    }
  }
  LODWORD(v51) = 1;
  UiThread::UiThread((UiThread *)&v58, (const enum UiThread::Type *)&v51);
  v54 = a1;
  v43 = *(_QWORD *)(a3 + 16);
  if ( v43 )
  {
    v44 = 0;
    *(_QWORD *)&v55[4] = *(_QWORD *)v43;
    v56 = *(_DWORD *)(v43 + 8);
  }
  else
  {
    v44 = -1;
  }
  v45 = &v55[4];
  if ( v44 == -1 )
    v45 = 0;
  v57 = v45;
  UiThread::Post__lambda_8e16763c156ca1ff978d2f8f9d588af6___(&v58, pExceptionObject, &v54);
  Future<void>::~Future<void>(pExceptionObject);
  v46 = (_QWORD *)v53;
  v47 = *(UiThread **)(v53 + 104);
  if ( v47 )
  {
    UiThread::~UiThread(v47);
    v46[13] = 0;
    v46 = (_QWORD *)v53;
  }
  pExceptionObject[0] = v58;
  v58 = 0;
  v48 = (UiThread *)v46[13];
  if ( v48 )
  {
    UiThread::~UiThread(v48);
    v46[13] = 0;
  }
  v46[11] = 0;
  v46[12] = 0;
  *(_OWORD *)(v46 + 11) = pExceptionObject[0];
  pExceptionObject[0] = 0;
  v46[13] = v46 + 11;
  UiThread::~UiThread((UiThread *)pExceptionObject);
  v49 = v53;
  if ( *(_QWORD *)(v53 + 128) )
    *(_QWORD *)(v53 + 128) = 0;
  v50 = *(_QWORD *)(a3 + 16);
  if ( v50 )
  {
    *(_QWORD *)(v49 + 116) = *(_QWORD *)v50;
    *(_DWORD *)(v49 + 124) = *(_DWORD *)(v50 + 8);
    *(_QWORD *)(v49 + 128) = v49 + 116;
  }
  UiThread::~UiThread((UiThread *)&v58);
LABEL_78:
  if ( v52 )
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 24LL))(v52, v8);
}

```

## disassembly

```asm
0x140040164  mov     rax, rsp
0x140040167  mov     [rax+10h], rbx
0x14004016b  push    rbp
0x14004016c  push    rsi
0x14004016d  push    rdi
0x14004016e  push    r12
0x140040170  push    r13
0x140040172  push    r14
0x140040174  push    r15
0x140040176  lea     rbp, [rsp-50h]
0x14004017b  sub     rsp, 150h
0x140040182  movaps  xmmword ptr [rax-48h], xmm6
0x140040186  mov     rax, cs:__security_cookie
0x14004018d  xor     rax, rsp
0x140040190  mov     [rbp+80h+var_50], rax
0x140040194  mov     rdi, r8
0x140040197  mov     bl, dl
0x140040199  mov     r15, rcx
0x14004019c  xor     r13d, r13d
0x14004019f  mov     rcx, [rcx]
0x1400401a2  add     rcx, 50h ; 'P'
0x1400401a6  mov     rax, [rcx]
0x1400401a9  lea     rdx, [rsp+180h+var_148]
0x1400401ae  mov     rax, [rax+30h]
0x1400401b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400401b7  nop
0x1400401b8  test    bl, bl
0x1400401ba  mov     rbx, [rsp+180h+var_140]
0x1400401bf  jnz     loc_14004066E
0x1400401c5  lea     rdx, [rbx+50h]
0x1400401c9  lea     rax, [rdx+1]
0x1400401cd  neg     rax
0x1400401d0  sbb     rcx, rcx
0x1400401d3  and     rcx, rdx
0x1400401d6  cmp     [rcx+18h], r13
0x1400401da  jz      short loc_14004021D
0x1400401dc  mov     r12b, 1
0x1400401df  xorps   xmm0, xmm0
0x1400401e2  movups  [rbp+80h+var_D0], xmm0
0x1400401e6  xorps   xmm1, xmm1
0x1400401e9  movdqu  [rbp+80h+var_C0], xmm1
0x1400401ee  lea     r8d, [r13+16h]
0x1400401f2  lea     rdx, aDismissingLock; "Dismissing lock window"
0x1400401f9  lea     rcx, [rbp+80h+var_D0]
0x1400401fd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140040202  nop
0x140040203  lea     rcx, [rbp+80h+var_D0]
0x140040207  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x14004020c  nop
0x14004020d  lea     rcx, [rbp+80h+var_D0]
0x140040211  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040216  mov     rbx, [rsp+180h+var_140]
0x14004021b  jmp     short loc_140040220
0x14004021d  mov     r12b, r13b
0x140040220  mov     rcx, [rbx+68h]; this
0x140040224  test    rcx, rcx
0x140040227  jz      short loc_140040237
0x140040229  call    ??1UiThread@@QEAA@XZ; UiThread::~UiThread(void)
0x14004022e  mov     [rbx+68h], r13
0x140040232  mov     rbx, [rsp+180h+var_140]
0x140040237  lea     rax, [rdi+1]
0x14004023b  neg     rax
0x14004023e  sbb     rcx, rcx
0x140040241  and     rcx, rdi
0x140040244  cmp     [rcx+10h], r13
0x140040248  jz      loc_140040653
0x14004024e  mov     rcx, [rdi+10h]
0x140040252  test    rcx, rcx
0x140040255  jz      loc_14004087E
0x14004025b  mov     rax, 218711A00h
0x140040265  mov     [rsp+180h+var_138], rax
0x14004026a  lea     r8, [rsp+180h+var_138]
0x14004026f  lea     rdx, [rsp+180h+var_110]
0x140040274  call    ??GDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator-(TimeSpan const &)
0x140040279  mov     rcx, [rdi+10h]
0x14004027d  test    rcx, rcx
0x140040280  jz      loc_14004089D
0x140040286  mov     [rsp+180h+var_138], 47868C00h
0x14004028f  lea     r8, [rsp+180h+var_138]
0x140040294  lea     rdx, [rbp+80h+pExceptionObject]
0x140040298  call    ??GDateTime@@QEBA?AV0@AEBVTimeSpan@@@Z; DateTime::operator-(TimeSpan const &)
0x14004029d  mov     rsi, [rsp+180h+var_140]
0x1400402a2  lea     rax, [rsi+1]
0x1400402a6  neg     rax
0x1400402a9  sbb     rcx, rcx
0x1400402ac  and     rcx, rsi
0x1400402af  mov     rdx, 8000000000000000h
0x1400402b9  movsd   xmm6, cs:__real@43e0000000000000
0x1400402c1  cmp     [rcx+48h], r13
0x1400402c5  jz      short loc_140040320
0x1400402c7  mov     rax, [rsi+48h]
0x1400402cb  test    rax, rax
0x1400402ce  jz      loc_1400408BC
0x1400402d4  mov     rcx, [rdi+10h]
0x1400402d8  test    rcx, rcx
0x1400402db  jz      loc_1400408DB
0x1400402e1  mov     rax, [rax]
0x1400402e4  sub     rax, [rcx]
0x1400402e7  xorps   xmm0, xmm0
0x1400402ea  cvtsi2sd xmm0, rax
0x1400402ef  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1400402f6  xor     eax, eax
0x1400402f8  comisd  xmm0, xmm6
0x1400402fc  jb      short loc_14004030B
0x1400402fe  subsd   xmm0, xmm6
0x140040302  comisd  xmm0, xmm6
0x140040306  jnb     short loc_14004030B
0x140040308  mov     rax, rdx
0x14004030b  cvttsd2si rcx, xmm0
0x140040310  add     rcx, rax
0x140040313  cmp     rcx, cs:?Minute@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Minute
0x14004031a  jbe     loc_14004081C
0x140040320  mov     r14, [rdi+10h]
0x140040324  test    r14, r14
0x140040327  jz      loc_1400408FA
0x14004032d  mov     rcx, [rsi+48h]
0x140040331  test    rcx, rcx
0x140040334  jz      short loc_14004033F
0x140040336  call    _anonymous_namespace___LockScreenImpl__LockWarnings___LockWarnings
0x14004033b  mov     [rsi+48h], r13
0x14004033f  lea     rbx, [rsi+8]
0x140040343  movsd   xmm0, qword ptr [r14]
0x140040348  mov     eax, [r14+8]
0x14004034c  movsd   qword ptr [rbx], xmm0
0x140040350  mov     [rbx+8], eax
0x140040353  lea     rcx, [rbx+10h]; this
0x140040357  mov     r8d, 1; unsigned int
0x14004035d  call    ??0Threadpool@@QEAA@II@Z; Threadpool::Threadpool(uint,uint)
0x140040362  mov     [rbx+20h], r13
0x140040366  mov     [rbx+28h], r13
0x14004036a  mov     [rbx+30h], r13
0x14004036e  mov     [rbx+38h], r13
0x140040372  mov     [rsi+48h], rbx
0x140040376  lea     rcx, [rsp+180h+var_138]
0x14004037b  call    ?GetCurrent@DateTime@@SA?AV1@XZ; DateTime::GetCurrent(void)
0x140040380  or      ebx, 0FFFFFFFFh
0x140040383  lea     r14d, [rbx+21h]
0x140040387  mov     r8, [rsp+180h+var_138+4]
0x14004038c  mov     r9d, dword ptr [rsp+180h+var_138]
0x140040391  mov     rax, cs:?Minute@TimeSpan@@2V1@B; TimeSpan const TimeSpan::Minute
0x140040398  test    r12b, r12b
0x14004039b  jz      short loc_140040400
0x14004039d  mov     ecx, dword ptr [rsp+180h+var_110]
0x1400403a1  mov     dword ptr [rsp+180h+var_150], ecx
0x1400403a5  mov     ecx, dword ptr [rsp+180h+var_110+4]
0x1400403a9  mov     dword ptr [rsp+180h+var_150+4], ecx
0x1400403ad  mov     dword ptr [rsp+180h+var_138], r9d
0x1400403b2  mov     dword ptr [rsp+180h+var_138+4], r8d
0x1400403b7  mov     rcx, [rsp+180h+var_150]
0x1400403bc  sub     rcx, [rsp+180h+var_138]
0x1400403c1  xorps   xmm0, xmm0
0x1400403c4  cvtsi2sd xmm0, rcx
0x1400403c9  andps   xmm0, cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1400403d0  xor     edx, edx
0x1400403d2  comisd  xmm0, xmm6
0x1400403d6  jb      short loc_1400403EF
0x1400403d8  subsd   xmm0, xmm6
0x1400403dc  comisd  xmm0, xmm6
0x1400403e0  jnb     short loc_1400403EF
0x1400403e2  mov     rcx, 8000000000000000h
0x1400403ec  mov     rdx, rcx
0x1400403ef  cvttsd2si rcx, xmm0
0x1400403f4  add     rcx, rdx
0x1400403f7  cmp     rcx, rax
0x1400403fa  jb      loc_14004053F
0x140040400  mov     ecx, dword ptr [rbp+80h+pExceptionObject]
0x140040403  mov     dword ptr [rsp+180h+var_138], ecx
0x140040407  mov     ecx, dword ptr [rbp+80h+pExceptionObject+4]
0x14004040a  mov     dword ptr [rsp+180h+var_138+4], ecx
0x14004040e  mov     dword ptr [rsp+180h+var_150], r9d
0x140040413  mov     dword ptr [rsp+180h+var_150+4], r8d
0x140040418  mov     rdx, [rsp+180h+var_138]
0x14004041d  sub     rdx, [rsp+180h+var_150]
0x140040422  cmovs   rdx, r13
0x140040426  cmp     rdx, rax
0x140040429  jbe     loc_14004053F
0x14004042f  xorps   xmm0, xmm0
0x140040432  movups  [rbp+80h+var_D0], xmm0
0x140040436  xorps   xmm1, xmm1
0x140040439  movdqu  [rbp+80h+var_C0], xmm1
0x14004043e  mov     r8d, 18h
0x140040444  lea     rdx, aSet15MinWarnin; "Set 15 min warning timer"
0x14004044b  lea     rcx, [rbp+80h+var_D0]
0x14004044f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140040454  nop
0x140040455  lea     rcx, [rbp+80h+var_D0]
0x140040459  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x14004045e  nop
0x14004045f  lea     rcx, [rbp+80h+var_D0]
0x140040463  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040468  mov     rax, [rsp+180h+var_140]
0x14004046d  mov     rsi, [rax+48h]
0x140040471  test    rsi, rsi
0x140040474  jz      loc_140040919
0x14004047a  mov     qword ptr [rbp+80h+var_D0], r15
0x14004047e  mov     rcx, [rdi+10h]
0x140040482  test    rcx, rcx
0x140040485  jz      short loc_140040499
0x140040487  mov     edx, r13d
0x14004048a  mov     rax, [rcx]
0x14004048d  mov     qword ptr [rbp+80h+var_D0+0Ch], rax
0x140040491  mov     eax, [rcx+8]
0x140040494  mov     dword ptr [rbp+80h+var_C0+4], eax
0x140040497  jmp     short loc_14004049B
0x140040499  mov     edx, ebx
0x14004049b  lea     rcx, [rbp+80h+var_D0+0Ch]
0x14004049f  cmp     edx, ebx
0x1400404a1  cmovz   rcx, r13
0x1400404a5  mov     qword ptr [rbp+80h+var_C0+8], rcx
0x1400404a9  mov     [rbp+80h+var_60], r13d
0x1400404ad  lea     r8, aTimewarning; "TimeWarning"
0x1400404b4  mov     rdx, r14
0x1400404b7  lea     rcx, [rbp+80h+var_A0]
0x1400404bb  call    cs:__imp__o_wcscpy_s
0x1400404c1  lea     rcx, [rsi+10h]
0x1400404c5  lea     rax, [rsp+180h+var_110]
0x1400404ca  mov     [rsp+180h+var_160], rax
0x1400404cf  lea     r9, [rbp+80h+var_D0]
0x1400404d3  lea     r8, [rbp+80h+var_A0]
0x1400404d7  lea     rdx, [rsp+180h+var_138]
0x1400404dc  call    Threadpool__QueueDelayedWorkItem__lambda_f00b0fc701dfedcc755a4c28b6159184___
0x1400404e1  nop
0x1400404e2  mov     rcx, [rsp+180h+var_140]
0x1400404e7  mov     rcx, [rcx+48h]
0x1400404eb  test    rcx, rcx
0x1400404ee  jz      loc_140040938
0x1400404f4  add     rcx, 20h ; ' '
0x1400404f8  mov     rdx, rax
0x1400404fb  call    ??4?$shared_ptr@V?$Signal@$$A6A?AV?$Optional@_J@@_K_J@Z@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>>::operator=(std::shared_ptr<Signal<Optional<__int64> (unsigned __int64,__int64)>> &&)
0x140040500  nop
0x140040501  mov     rsi, qword ptr [rsp+180h+var_130]
0x140040506  test    rsi, rsi
0x140040509  jz      short loc_14004053F
0x14004050b  mov     eax, ebx
0x14004050d  lock xadd [rsi+8], eax
0x140040512  add     eax, ebx
0x140040514  jnz     short loc_14004053F
0x140040516  mov     rax, [rsi]
0x140040519  mov     rcx, rsi
0x14004051c  mov     rax, [rax]
0x14004051f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040524  mov     eax, ebx
0x140040526  lock xadd [rsi+0Ch], eax
0x14004052b  add     eax, ebx
0x14004052d  jnz     short loc_14004053F
0x14004052f  mov     rax, [rsi]
0x140040532  mov     rcx, rsi
0x140040535  mov     rax, [rax+8]
0x140040539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004053e  nop
0x14004053f  xorps   xmm0, xmm0
0x140040542  movups  [rbp+80h+var_D0], xmm0
0x140040546  xorps   xmm1, xmm1
0x140040549  movdqu  [rbp+80h+var_C0], xmm1
0x14004054e  mov     r8d, 17h
0x140040554  lea     rdx, aSet2MinWarning; "Set 2 min warning timer"
0x14004055b  lea     rcx, [rbp+80h+var_D0]
0x14004055f  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x140040564  nop
0x140040565  lea     rcx, [rbp+80h+var_D0]
0x140040569  call    ?LogMessage@MonitorUILogger@Logging@UI@wpc@@SAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; wpc::UI::Logging::MonitorUILogger::LogMessage(std::wstring const &)
0x14004056e  nop
0x14004056f  lea     rcx, [rbp+80h+var_D0]
0x140040573  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140040578  mov     rax, [rsp+180h+var_140]
0x14004057d  mov     rsi, [rax+48h]
0x140040581  test    rsi, rsi
0x140040584  jz      loc_140040957
0x14004058a  mov     qword ptr [rbp+80h+var_D0], r15
0x14004058e  mov     rcx, [rdi+10h]
0x140040592  test    rcx, rcx
0x140040595  jz      short loc_1400405A9
0x140040597  mov     edx, r13d
0x14004059a  mov     rax, [rcx]
0x14004059d  mov     qword ptr [rbp+80h+var_D0+0Ch], rax
0x1400405a1  mov     eax, [rcx+8]
0x1400405a4  mov     dword ptr [rbp+80h+var_C0+4], eax
0x1400405a7  jmp     short loc_1400405AB
0x1400405a9  mov     edx, ebx
0x1400405ab  lea     rcx, [rbp+80h+var_D0+0Ch]
0x1400405af  cmp     edx, ebx
0x1400405b1  cmovz   rcx, r13
0x1400405b5  mov     qword ptr [rbp+80h+var_C0+8], rcx
0x1400405b9  mov     [rbp+80h+var_60], r13d
0x1400405bd  lea     r8, aTimewarning; "TimeWarning"
0x1400405c4  mov     rdx, r14
0x1400405c7  lea     rcx, [rbp+80h+var_A0]
0x1400405cb  call    cs:__imp__o_wcscpy_s
0x1400405d1  lea     rcx, [rsi+10h]
0x1400405d5  lea     rax, [rbp+80h+pExceptionObject]
0x1400405d9  mov     [rsp+180h+var_160], rax
0x1400405de  lea     r9, [rbp+80h+var_D0]
0x1400405e2  lea     r8, [rbp+80h+var_A0]
0x1400405e6  lea     rdx, [rsp+180h+var_110]
0x1400405eb  call    Threadpool__QueueDelayedWorkItem__lambda_a3590754413f215dfd6baebbd98dd29f___
0x1400405f0  nop
0x1400405f1  mov     rcx, [rsp+180h+var_140]
0x1400405f6  mov     rcx, [rcx+48h]
0x1400405fa  test    rcx, rcx
0x1400405fd  jz      loc_14004085F
  ... truncated ...
```
