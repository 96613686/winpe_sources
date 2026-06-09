# DBIndexedRestrictionFilter::MoveNext(TableHandleInfo *)

- ea: `0x180012bb0`
- end: `0x180012eca`
- name: `?MoveNext@DBIndexedRestrictionFilter@@UEAAJPEAUTableHandleInfo@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(DBIndexedRestrictionFilter *__hidden this, struct TableHandleInfo *)`
- caller_count: `0`
- callee_count: `13`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x180004464`
- `0x1800068f0`
- `0x18000f530`
- `0x180010690`
- `0x180011ed0`
- `0x1800125d0`
- `0x180012bb0`
- `0x18001abf4`
- `0x18002d548`
- `0x1800448a0`
- `0x180054754`
- `0x1800af3f4`
- `0x1800c6010`

## import_xrefs

- `ESENT!JetMove` at `0x180012c12`
- `ESENT!JetMove` at `0x180012c12`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012bf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012c63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012cc7`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012bf3`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012c63`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012cc7`

## string_xrefs

- `0x180012d67`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x180012da8`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall DBIndexedRestrictionFilter::MoveNext(DBIndexedRestrictionFilter *this, struct TableHandleInfo *a2)
{
  __int64 v3; // rax
  unsigned int v5; // ebx
  __int64 v6; // r8
  ULONGLONG TickCount64; // rax
  JET_TABLEID v8; // rdx
  JET_SESID v9; // rcx
  int v10; // r15d
  JET_ERR v11; // ebx
  int v12; // eax
  ULONGLONG v13; // rax
  ULONGLONG v14; // rdx
  int v15; // eax
  int v17; // eax
  __int64 v18; // r9
  unsigned __int32 v19; // edx
  int v20; // eax
  unsigned int HresultFromJetError; // eax
  int CurrentKeys; // eax
  __int64 v23; // r8
  __int64 v24; // r9
  ULONGLONG v25; // [rsp+40h] [rbp-28h] BYREF
  __int64 v26; // [rsp+48h] [rbp-20h]
  int v27; // [rsp+A0h] [rbp+38h] BYREF

  v3 = *(_QWORD *)this;
  if ( *((_DWORD *)this + 14) )
  {
    v5 = (*(__int64 (__fastcall **)(DBIndexedRestrictionFilter *, struct TableHandleInfo *, _QWORD))(v3 + 144))(
           this,
           a2,
           0);
    if ( (v5 & 0x80000000) != 0 )
    {
      if ( v5 == -2147024871 )
        return v5;
      v18 = 2491;
LABEL_20:
      Log_UnistoreHREvent_1(v5, 1, v6, v18);
      return v5;
    }
    LODWORD(v26) = 20;
    TickCount64 = GetTickCount64();
    v8 = *((_QWORD *)a2 + 2);
    v9 = *((_QWORD *)a2 + 1);
    v10 = TickCount64;
    v25 = TickCount64;
    v11 = JetMove(v9, v8, 1, 0);
    CheckCorruption(v11);
    if ( v11 == -1603 )
    {
      *((_DWORD *)a2 + 6) = 0;
      v17 = GetTickCount64();
      if ( g_perfStatEnabled )
      {
        v19 = v17 - v10;
        _InterlockedAdd(&dword_18010DAF8, 1u);
        _InterlockedAdd(&dword_18010DAF0, v17 - v10);
        do
          v20 = dword_18010DAF4;
        while ( dword_18010DAF4 < v19 && v20 != _InterlockedCompareExchange(&dword_18010DAF4, v19, dword_18010DAF4) );
      }
      return (unsigned int)-2147024871;
    }
    if ( v11 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v11);
      v5 = HresultFromJetError;
      if ( HresultFromJetError != -1603 )
        Log_UnistoreHREvent_0(
          HresultFromJetError,
          0,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
          1184);
      PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&v25);
      if ( (v5 & 0x80000000) == 0 )
      {
LABEL_12:
        if ( (*((_DWORD *)this + 2) & 0x10000000) == 0 )
          return 0;
        utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&void * LocalFree(void *),0>>>(
          &v25,
          v14,
          v6);
        CurrentKeys = DBFilter::_GetCurrentKeys(a2, 0, &v25);
        v5 = CurrentKeys;
        if ( CurrentKeys < 0 )
        {
          if ( CurrentKeys != -2147024871 )
          {
            v24 = 2869;
LABEL_46:
            Log_UnistoreHREvent_1((unsigned int)CurrentKeys, 1, v23, v24);
            goto LABEL_47;
          }
          goto LABEL_47;
        }
        if ( v26 - v25 == 1000 || *((_DWORD *)this + 16) && (*((_DWORD *)this + 15) & 0xFFFFFFFD) == 0 )
        {
          v27 = 0;
          CurrentKeys = DBRestrictionFilter::IsRelevantRow(this, a2, &v27);
          v5 = CurrentKeys;
          if ( CurrentKeys < 0 )
          {
            if ( CurrentKeys != -2147024871 )
            {
              v24 = 2879;
              goto LABEL_46;
            }
LABEL_47:
            utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v25);
            if ( v5 == -2147024871 )
              return v5;
            v18 = 2497;
            goto LABEL_20;
          }
          if ( !v27 )
          {
            CurrentKeys = (*(__int64 (__fastcall **)(DBIndexedRestrictionFilter *, struct TableHandleInfo *, _QWORD))(*(_QWORD *)this + 144LL))(
                            this,
                            a2,
                            0);
            v5 = CurrentKeys;
            if ( CurrentKeys < 0 )
            {
              if ( CurrentKeys != -2147024871 )
              {
                v24 = 2883;
                goto LABEL_46;
              }
              goto LABEL_47;
            }
            CurrentKeys = DBRestrictionFilter::MoveNext(this, a2);
            v5 = CurrentKeys;
            if ( CurrentKeys < 0 )
            {
              if ( CurrentKeys != -2147024871 )
              {
                v24 = 2884;
                goto LABEL_46;
              }
              goto LABEL_47;
            }
          }
        }
        utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(&v25);
        return 0;
      }
    }
    else
    {
      v12 = UnifiedStoreCursorLocation::UpdateToCurrentLocation(
              (__int64)a2 + 24,
              *(_DWORD *)a2,
              *((_DWORD *)a2 + 1) == 0,
              *((_QWORD *)a2 + 1),
              *((_QWORD *)a2 + 2));
      v5 = v12;
      if ( v12 >= 0 )
      {
        v13 = GetTickCount64();
        v14 = v13;
        if ( g_perfStatEnabled )
        {
          v14 = (unsigned int)(v13 - v10);
          _InterlockedAdd(&dword_18010DAF8, 1u);
          _InterlockedAdd(&dword_18010DAF0, v14);
          do
            v15 = dword_18010DAF4;
          while ( dword_18010DAF4 < (unsigned int)v14
               && v15 != _InterlockedCompareExchange(&dword_18010DAF4, v14, dword_18010DAF4) );
        }
        goto LABEL_12;
      }
      Log_UnistoreHREvent_0(
        (unsigned int)v12,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1181);
      PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&v25);
    }
    if ( v5 == -2147024871 )
      return v5;
    v18 = 2494;
    goto LABEL_20;
  }
  return (*(__int64 (__fastcall **)(DBIndexedRestrictionFilter *, struct TableHandleInfo *, __int64))(v3 + 32))(
           this,
           a2,
           4);
}

```

## disassembly

```asm
0x180012bb0  push    rbp
0x180012bb2  push    rbx
0x180012bb3  push    rsi
0x180012bb4  push    rdi
0x180012bb5  push    r14
0x180012bb7  push    r15
0x180012bb9  mov     rbp, rsp
0x180012bbc  sub     rsp, 68h
0x180012bc0  cmp     dword ptr [rcx+38h], 0
0x180012bc4  mov     r14, rdx
0x180012bc7  mov     rax, [rcx]
0x180012bca  mov     rsi, rcx
0x180012bcd  jz      loc_180012D03
0x180012bd3  mov     rax, [rax+90h]
0x180012bda  xor     r8d, r8d
0x180012bdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012be2  mov     ebx, eax
0x180012be4  test    eax, eax
0x180012be6  js      loc_180012CEE
0x180012bec  mov     dword ptr [rbp+var_20], 14h
0x180012bf3  call    cs:__imp_GetTickCount64
0x180012bf9  mov     rdx, [r14+10h]; tableid
0x180012bfd  xor     r9d, r9d; grbit
0x180012c00  mov     rcx, [r14+8]; sesid
0x180012c04  mov     r15, rax
0x180012c07  mov     [rbp+var_28], rax
0x180012c0b  lea     edi, [r9+1]
0x180012c0f  mov     r8d, edi; cRow
0x180012c12  call    cs:__imp_JetMove
0x180012c18  mov     ecx, eax; int
0x180012c1a  mov     ebx, eax
0x180012c1c  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x180012c21  cmp     ebx, 0FFFFF9BDh
0x180012c27  jz      loc_180012CBF
0x180012c2d  test    ebx, ebx
0x180012c2f  js      loc_180012D8E
0x180012c35  mov     rax, [r14+10h]
0x180012c39  lea     rcx, [r14+18h]
0x180012c3d  mov     r9, [r14+8]
0x180012c41  xor     r8d, r8d
0x180012c44  cmp     [r14+4], r8d
0x180012c48  mov     edx, [r14]
0x180012c4b  setz    r8b
0x180012c4f  mov     [rsp+68h+var_48], rax
0x180012c54  call    ?UpdateToCurrentLocation@UnifiedStoreCursorLocation@@QEAAJW4US_TABLEID@@H_K1@Z; UnifiedStoreCursorLocation::UpdateToCurrentLocation(US_TABLEID,int,unsigned __int64,unsigned __int64)
0x180012c59  mov     ebx, eax
0x180012c5b  test    eax, eax
0x180012c5d  js      loc_180012D61
0x180012c63  call    cs:__imp_GetTickCount64
0x180012c69  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180012c6f  mov     rdx, rax
0x180012c72  test    ecx, ecx
0x180012c74  jz      short loc_180012CAE
0x180012c76  sub     edx, r15d
0x180012c79  lock add cs:dword_18010DAF8, edi
0x180012c80  lock add cs:dword_18010DAF0, edx
0x180012c87  mov     eax, cs:dword_18010DAF4
0x180012c8d  cmp     eax, edx
0x180012c8f  jnb     short loc_180012CAE
0x180012c91  lock cmpxchg cs:dword_18010DAF4, edx
0x180012c99  jnz     short loc_180012C87
0x180012c9b  jmp     short loc_180012CAE
0x180012c9d  lea     rcx, [rbp+var_28]; this
0x180012ca1  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x180012ca6  test    ebx, ebx
0x180012ca8  js      loc_180012D80
0x180012cae  test    dword ptr [rsi+8], 10000000h
0x180012cb5  jnz     loc_180012DBD
0x180012cbb  xor     eax, eax
0x180012cbd  jmp     short loc_180012CE1
0x180012cbf  mov     dword ptr [r14+18h], 0
0x180012cc7  call    cs:__imp_GetTickCount64
0x180012ccd  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180012cd3  mov     rdx, rax
0x180012cd6  test    ecx, ecx
0x180012cd8  jnz     short loc_180012D37
0x180012cda  mov     ebx, 80070019h
0x180012cdf  mov     eax, ebx
0x180012ce1  add     rsp, 68h
0x180012ce5  pop     r15
0x180012ce7  pop     r14
0x180012ce9  pop     rdi
0x180012cea  pop     rsi
0x180012ceb  pop     rbx
0x180012cec  pop     rbp
0x180012ced  retn
0x180012cee  cmp     ebx, 80070019h
0x180012cf4  jz      short loc_180012CDF
0x180012cf6  mov     edx, 1
0x180012cfb  mov     r9d, 9BBh
0x180012d01  jmp     short loc_180012D2E
0x180012d03  mov     rax, [rax+20h]
0x180012d07  xor     r9d, r9d
0x180012d0a  mov     [rsp+68h+var_40], 0
0x180012d13  mov     dword ptr [rsp+68h+var_48], 0
0x180012d1b  lea     r8d, [r9+4]
0x180012d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d24  jmp     short loc_180012CE1
0x180012d26  mov     r9d, 9BEh
0x180012d2c  mov     edx, edi
0x180012d2e  mov     ecx, ebx
0x180012d30  call    Log_UnistoreHREvent_1
0x180012d35  jmp     short loc_180012CDF
0x180012d37  sub     edx, r15d
0x180012d3a  lock add cs:dword_18010DAF8, edi
0x180012d41  lock add cs:dword_18010DAF0, edx
0x180012d48  mov     eax, cs:dword_18010DAF4
0x180012d4e  cmp     eax, edx
0x180012d50  jnb     short loc_180012CDA
0x180012d52  lock cmpxchg cs:dword_18010DAF4, edx
0x180012d5a  jnz     short loc_180012D48
0x180012d5c  jmp     loc_180012CDA
0x180012d61  mov     r9d, 49Dh
0x180012d67  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012d6e  mov     edx, edi
0x180012d70  mov     ecx, eax
0x180012d72  call    Log_UnistoreHREvent_0
0x180012d77  lea     rcx, [rbp+var_28]; this
0x180012d7b  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x180012d80  cmp     ebx, 80070019h
0x180012d86  jz      loc_180012CDF
0x180012d8c  jmp     short loc_180012D26
0x180012d8e  mov     ecx, ebx; int
0x180012d90  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180012d95  mov     ebx, eax
0x180012d97  cmp     eax, 0FFFFF9BDh
0x180012d9c  jz      loc_180012C9D
0x180012da2  mov     r9d, 4A0h
0x180012da8  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012daf  xor     edx, edx
0x180012db1  mov     ecx, eax
0x180012db3  call    Log_UnistoreHREvent_0
0x180012db8  jmp     loc_180012C9D
0x180012dbd  lea     rcx, [rbp+var_28]
0x180012dc1  call    ??0?$vector@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@V?$allocator@V?$auto_xxx@PEAU_USPROPVAL@@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z$0A@@tlx@@@utl@@@utl@@QEAA@XZ; utl::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>::vector<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>,utl::allocator<tlx::auto_xxx<_USPROPVAL *,void * (*)(void *),&LocalFree(void *),0>>>(void)
0x180012dc6  lea     r8, [rbp+var_28]
0x180012dca  xor     edx, edx
0x180012dcc  mov     rcx, r14
0x180012dcf  call    ?_GetCurrentKeys@DBFilter@@KAJPEAUTableHandleInfo@@PEBVUnifiedStoreCursorLocation@@AEAV?$vector@EV?$allocator@E@utl@@@utl@@@Z; DBFilter::_GetCurrentKeys(TableHandleInfo *,UnifiedStoreCursorLocation const *,utl::vector<uchar,utl::allocator<uchar>> &)
0x180012dd4  mov     ebx, eax
0x180012dd6  test    eax, eax
0x180012dd8  jns     short loc_180012DF0
0x180012dda  cmp     eax, 80070019h
0x180012ddf  jz      loc_180012E9C
0x180012de5  mov     r9d, 0B35h
0x180012deb  jmp     loc_180012E93
0x180012df0  mov     rax, [rbp+var_20]
0x180012df4  sub     rax, [rbp+var_28]
0x180012df8  cmp     rax, 3E8h
0x180012dfe  jz      short loc_180012E17
0x180012e00  cmp     dword ptr [rsi+40h], 0
0x180012e04  jz      loc_180012EBC
0x180012e0a  test    dword ptr [rsi+3Ch], 0FFFFFFFDh
0x180012e11  jnz     loc_180012EBC
0x180012e17  lea     r8, [rbp+arg_0]; int *
0x180012e1b  mov     [rbp+arg_0], 0
0x180012e22  mov     rdx, r14; struct TableHandleInfo *
0x180012e25  mov     rcx, rsi; this
0x180012e28  call    ?IsRelevantRow@DBRestrictionFilter@@IEBAJPEAUTableHandleInfo@@PEAH@Z; DBRestrictionFilter::IsRelevantRow(TableHandleInfo *,int *)
0x180012e2d  mov     ebx, eax
0x180012e2f  test    eax, eax
0x180012e31  jns     short loc_180012E42
0x180012e33  cmp     eax, 80070019h
0x180012e38  jz      short loc_180012E9C
0x180012e3a  mov     r9d, 0B3Fh
0x180012e40  jmp     short loc_180012E93
0x180012e42  cmp     [rbp+arg_0], 0
0x180012e46  jnz     short loc_180012EBC
0x180012e48  mov     rax, [rsi]
0x180012e4b  xor     r8d, r8d
0x180012e4e  mov     rdx, r14
0x180012e51  mov     rcx, rsi
0x180012e54  mov     rax, [rax+90h]
0x180012e5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e60  mov     ebx, eax
0x180012e62  test    eax, eax
0x180012e64  jns     short loc_180012E75
0x180012e66  cmp     eax, 80070019h
0x180012e6b  jz      short loc_180012E9C
0x180012e6d  mov     r9d, 0B43h
0x180012e73  jmp     short loc_180012E93
0x180012e75  mov     rdx, r14; struct TableHandleInfo *
0x180012e78  mov     rcx, rsi; this
0x180012e7b  call    ?MoveNext@DBRestrictionFilter@@UEAAJPEAUTableHandleInfo@@@Z; DBRestrictionFilter::MoveNext(TableHandleInfo *)
0x180012e80  mov     ebx, eax
0x180012e82  test    eax, eax
0x180012e84  jns     short loc_180012EBC
0x180012e86  cmp     eax, 80070019h
0x180012e8b  jz      short loc_180012E9C
0x180012e8d  mov     r9d, 0B44h
0x180012e93  mov     edx, edi
0x180012e95  mov     ecx, eax
0x180012e97  call    Log_UnistoreHREvent_1
0x180012e9c  lea     rcx, [rbp+var_28]
0x180012ea0  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180012ea5  cmp     ebx, 80070019h
0x180012eab  jz      loc_180012CDF
0x180012eb1  mov     r9d, 9C1h
0x180012eb7  jmp     loc_180012D2C
0x180012ebc  lea     rcx, [rbp+var_28]
0x180012ec0  call    ?_Uninit@?$vector@UAppRevisionRecord@@V?$allocator@UAppRevisionRecord@@@utl@@@utl@@AEAAXXZ; utl::vector<AppRevisionRecord,utl::allocator<AppRevisionRecord>>::_Uninit(void)
0x180012ec5  jmp     loc_180012CBB
```
