# DBSession::GetTableHandle(US_TABLEID,ulong,TableHandleInfo * *)

- ea: `0x18000e8b0`
- end: `0x18000ee08`
- name: `?GetTableHandle@DBSession@@UEAAJW4US_TABLEID@@KPEAPEAUTableHandleInfo@@@Z`
- size: `1368`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callees

- `0x1800068f0`
- `0x18000e8b0`
- `0x180012ed0`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x180078a40`
- `0x180079030`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000e8eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec71`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000e953`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000eb76`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ec71`
- `ESENT!JetSetIndexRange` at `0x18000e974`
- `ESENT!JetSetIndexRange` at `0x18000e974`
- `ESENT!JetGetErrorInfoW` at `0x18000e9f6`
- `ESENT!JetGetErrorInfoW` at `0x18000e9f6`

## string_xrefs

- `0x18000ed29`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000ed61`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18000eb02`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x18000e939`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000eb40`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000eb5c`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000ecb9`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbsession.cpp`
- `0x18000eacc`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000eae6`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000ebab`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`
- `0x18000ed82`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\jetinterophelper.h`

## pseudocode

```c
__int64 __fastcall DBSession::GetTableHandle(__int64 a1, unsigned int a2, unsigned int a3, _QWORD *a4)
{
  _QWORD *i; // rbx
  __int64 v8; // rcx
  int v9; // eax
  unsigned int v10; // ebx
  JET_ERR v12; // eax
  int v13; // esi
  __int64 v14; // rcx
  __int64 v15; // r8
  unsigned int v16; // esi
  __int64 v17; // rsi
  _QWORD *v18; // rax
  _QWORD *v19; // r9
  _QWORD *v20; // rcx
  unsigned int v21; // ecx
  _QWORD *v22; // rcx
  _QWORD *v23; // rax
  unsigned int v24; // ecx
  int v25; // eax
  __int64 v26; // rcx
  int v27; // eax
  int v28; // eax
  int v29; // [rsp+30h] [rbp-D0h] BYREF
  JET_ERR v30; // [rsp+38h] [rbp-C8h] BYREF
  _QWORD *v31; // [rsp+40h] [rbp-C0h]
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v33; // [rsp+54h] [rbp-ACh]
  __int128 v34; // [rsp+64h] [rbp-9Ch]
  __int128 v35; // [rsp+74h] [rbp-8Ch]
  __int128 v36; // [rsp+84h] [rbp-7Ch]
  __int128 v37; // [rsp+94h] [rbp-6Ch]
  __int128 v38; // [rsp+A4h] [rbp-5Ch]
  __int128 v39; // [rsp+B4h] [rbp-4Ch]
  __int128 v40; // [rsp+C4h] [rbp-3Ch]
  __int128 v41; // [rsp+D4h] [rbp-2Ch]
  int v42; // [rsp+E4h] [rbp-1Ch]

  v31 = a4;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
  for ( i = *(_QWORD **)(a1 + 256); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(a1 + 256) )
      goto LABEL_5;
    v8 = i[2];
    if ( a2 == *(_DWORD *)v8 && a3 == *(_DWORD *)(v8 + 4) )
      break;
  }
  v12 = JetSetIndexRange(*(_QWORD *)(v8 + 8), *(_QWORD *)(v8 + 16), 8u);
  v13 = v12;
  if ( !g_fInProc || dword_18010D924 )
    goto LABEL_13;
  if ( v12 == -1414 )
  {
LABEL_55:
    v25 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v13);
    if ( v25 >= 0 )
    {
      v29 = v13;
      UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v29);
      if ( (unsigned int)IsJetCorruptionError(v13) )
      {
        Log_AssertionEvent(
          v26,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
          109);
        __int2c();
      }
    }
    else
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v25,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        102);
    }
    goto LABEL_13;
  }
  v30 = v12;
  if ( v12 >= 0 )
    goto LABEL_35;
  v32 = 152;
  v42 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v41 = 0;
  if ( (int)JetGetErrorInfoW(&v30, &v32, 152, 1, 0) >= 0 )
  {
    if ( DWORD1(v33) != 10 )
    {
      if ( DWORD1(v33) == 11 )
      {
        v29 = v30;
        UnistoreTelemetry::JetInconsistentError<unsigned long>(&v29);
      }
      else if ( DWORD1(v33) == 12 )
      {
        v29 = v30;
        UnistoreTelemetry::JetFragmentationError<unsigned long>(&v29);
      }
      goto LABEL_13;
    }
    if ( v30 == -1414 )
      goto LABEL_13;
    goto LABEL_55;
  }
LABEL_13:
  v14 = 0x80000000LL;
  if ( (int)(v13 + 0x80000000) < 0 || v13 == -1906 )
    goto LABEL_35;
  if ( g_breakOnJetError && g_breakOnJetError == v13 )
    Log_AssertionEvent(
      0x80000000LL,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
      25);
  switch ( v13 )
  {
    case -1811:
      v16 = -2147024894;
      break;
    case -1601:
    case -1603:
    case -1017:
      v16 = -2147024871;
      break;
    case -1605:
    case -1525:
      v16 = -2147024713;
      break;
    case -346:
      v16 = -2147024872;
      break;
    case -529:
    case -1808:
    case -510:
      v16 = -2147024784;
      break;
    default:
      if ( v13 < 0 )
      {
        switch ( v13 )
        {
          case -1102:
            Log_AssertionEvent(
              v14,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
              62);
            goto LABEL_33;
          case -1054:
            Log_AssertionEvent(
              v14,
              "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
              59);
            break;
          case -1069:
            v15 = 65;
            goto LABEL_32;
        }
        if ( v13 != -1086 )
        {
LABEL_33:
          v16 = -v13 | 0x80C80000;
          break;
        }
        v15 = 71;
LABEL_32:
        Log_AssertionEvent(
          v14,
          "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\jetinterophelper.h",
          v15);
        __int2c();
        goto LABEL_33;
      }
      v16 = v13 | 0xC80000;
      break;
  }
  Log_UnistoreHREvent_0(
    v16,
    0,
    "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
    1461);
  if ( (v16 & 0x80000000) != 0 )
  {
    Log_UnistoreHREvent_0(
      v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1402);
    if ( v16 != -2147023728 )
      goto LABEL_37;
LABEL_5:
    v9 = DBSession::_OpenTable(a1, a2, a3, v31);
    v10 = v9;
    if ( v9 < 0 )
    {
      Log_UnistoreHREvent_0(
        (unsigned int)v9,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
        1427);
      LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
      return v10;
    }
    goto LABEL_45;
  }
LABEL_35:
  v17 = *(_QWORD *)(a1 + 232);
  v18 = operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v18 )
  {
    v16 = -2147024882;
    Log_UnistoreHREvent_0(
      2147942414LL,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1404);
LABEL_37:
    Log_UnistoreHREvent_0(
      v16,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbsession.cpp",
      1431);
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
    return v16;
  }
  v19 = v31;
  v18[2] = i[2];
  v20 = *(_QWORD **)(v17 + 8);
  v18[1] = v20;
  *v18 = v17;
  *v20 = v18;
  *(_QWORD *)(v17 + 8) = v18;
  ++*(_QWORD *)(a1 + 248);
  *v19 = i[2];
  v21 = *(_DWORD *)(a1 + 248);
  if ( g_perfStatEnabled )
  {
    _InterlockedIncrement(&dword_18010DB34);
    _InterlockedAdd(&dword_18010DB2C, v21);
    do
      v27 = dword_18010DB30;
    while ( dword_18010DB30 < v21 && v27 != _InterlockedCompareExchange(&dword_18010DB30, v21, dword_18010DB30) );
  }
  v22 = (_QWORD *)i[1];
  v23 = (_QWORD *)*i;
  *v22 = *i;
  v23[1] = v22;
  operator delete(i);
  --*(_QWORD *)(a1 + 272);
  v24 = *(_DWORD *)(a1 + 272);
  if ( g_perfStatEnabled )
  {
    _InterlockedIncrement(&dword_18010DB40);
    _InterlockedAdd(&dword_18010DB38, v24);
    do
      v28 = dword_18010DB3C;
    while ( dword_18010DB3C < v24 && v28 != _InterlockedCompareExchange(&dword_18010DB3C, v24, dword_18010DB3C) );
  }
LABEL_45:
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 280));
  return 0;
}

```

## disassembly

```asm
0x18000e8b0  push    rbp
0x18000e8b2  push    rbx
0x18000e8b3  push    rdi
0x18000e8b4  push    r12
0x18000e8b6  push    r13
0x18000e8b8  push    r14
0x18000e8ba  push    r15
0x18000e8bc  lea     rbp, [rsp-10h]
0x18000e8c1  sub     rsp, 110h
0x18000e8c8  mov     rax, cs:__security_cookie
0x18000e8cf  xor     rax, rsp
0x18000e8d2  mov     [rbp+40h+var_50], rax
0x18000e8d6  mov     r14, rcx
0x18000e8d9  mov     [rsp+140h+var_100], r9
0x18000e8de  add     rcx, 118h; lpCriticalSection
0x18000e8e5  mov     r13d, r8d
0x18000e8e8  mov     r12d, edx
0x18000e8eb  call    cs:__imp_EnterCriticalSection
0x18000e8f1  lea     r15, [r14+100h]
0x18000e8f8  mov     [rsp+140h+var_38], rsi
0x18000e900  mov     rbx, [r15]
0x18000e903  cmp     rbx, r15
0x18000e906  jz      short loc_18000E916
0x18000e908  mov     rcx, [rbx+10h]
0x18000e90c  cmp     r12d, [rcx]
0x18000e90f  jz      short loc_18000E960
0x18000e911  mov     rbx, [rbx]
0x18000e914  jmp     short loc_18000E903
0x18000e916  mov     r9, [rsp+140h+var_100]
0x18000e91b  mov     r8d, r13d
0x18000e91e  mov     edx, r12d
0x18000e921  mov     rcx, r14
0x18000e924  call    ?_OpenTable@DBSession@@IEAAJW4US_TABLEID@@KPEAPEAUTableHandleInfo@@@Z; DBSession::_OpenTable(US_TABLEID,ulong,TableHandleInfo * *)
0x18000e929  mov     ebx, eax
0x18000e92b  test    eax, eax
0x18000e92d  jns     loc_18000EC6A
0x18000e933  mov     r9d, 593h
0x18000e939  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000e940  mov     edx, 1
0x18000e945  mov     ecx, eax
0x18000e947  call    Log_UnistoreHREvent_0
0x18000e94c  lea     rcx, [r14+118h]; lpCriticalSection
0x18000e953  call    cs:__imp_LeaveCriticalSection
0x18000e959  mov     eax, ebx
0x18000e95b  jmp     loc_18000EB7E
0x18000e960  cmp     r13d, [rcx+4]
0x18000e964  jnz     short loc_18000E911
0x18000e966  mov     rdx, [rcx+10h]; tableidSrc
0x18000e96a  mov     r8d, 8; grbit
0x18000e970  mov     rcx, [rcx+8]; sesid
0x18000e974  call    cs:__imp_JetSetIndexRange
0x18000e97a  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x18000e981  mov     esi, eax
0x18000e983  jz      short loc_18000EA04
0x18000e985  cmp     cs:dword_18010D924, 0
0x18000e98c  jnz     short loc_18000EA04
0x18000e98e  cmp     eax, 0FFFFFA7Ah
0x18000e993  jz      loc_18000ED02
0x18000e999  mov     [rsp+140h+var_108], eax
0x18000e99d  test    eax, eax
0x18000e99f  jns     loc_18000EB1A
0x18000e9a5  xorps   xmm0, xmm0
0x18000e9a8  mov     [rsp+140h+var_F0], 98h
0x18000e9b0  xor     eax, eax
0x18000e9b2  lea     rdx, [rsp+140h+var_F0]
0x18000e9b7  mov     r9d, 1
0x18000e9bd  mov     [rbp+40h+var_5C], eax
0x18000e9c0  mov     r8d, 98h
0x18000e9c6  mov     [rsp+140h+var_120], eax
0x18000e9ca  lea     rcx, [rsp+140h+var_108]
0x18000e9cf  movups  [rsp+140h+var_EC], xmm0
0x18000e9d4  movups  [rsp+140h+var_DC], xmm0
0x18000e9d9  movups  [rsp+140h+var_CC], xmm0
0x18000e9de  movups  [rbp+40h+var_BC], xmm0
0x18000e9e2  movups  [rbp+40h+var_AC], xmm0
0x18000e9e6  movups  [rbp+40h+var_9C], xmm0
0x18000e9ea  movups  [rbp+40h+var_8C], xmm0
0x18000e9ee  movups  [rbp+40h+var_7C], xmm0
0x18000e9f2  movups  [rbp+40h+var_6C], xmm0
0x18000e9f6  call    cs:__imp_JetGetErrorInfoW
0x18000e9fc  test    eax, eax
0x18000e9fe  jns     loc_18000EBBC
0x18000ea04  mov     ecx, 80000000h
0x18000ea09  lea     eax, [rsi+rcx]
0x18000ea0c  test    ecx, eax
0x18000ea0e  jnz     loc_18000EB1A
0x18000ea14  cmp     esi, 0FFFFF88Eh
0x18000ea1a  jz      loc_18000EB1A
0x18000ea20  mov     eax, cs:?g_breakOnJetError@@3JA; long g_breakOnJetError
0x18000ea26  test    eax, eax
0x18000ea28  jnz     loc_18000ED74
0x18000ea2e  cmp     esi, 0FFFFF8EDh
0x18000ea34  jz      loc_18000EC92
0x18000ea3a  cmp     esi, 0FFFFF9BFh
0x18000ea40  jz      loc_18000EC88
0x18000ea46  cmp     esi, 0FFFFF9BDh
0x18000ea4c  jz      loc_18000EC88
0x18000ea52  cmp     esi, 0FFFFFC07h
0x18000ea58  jz      loc_18000EC88
0x18000ea5e  cmp     esi, 0FFFFF9BBh
0x18000ea64  jz      loc_18000EDA8
0x18000ea6a  cmp     esi, 0FFFFFA0Bh
0x18000ea70  jz      loc_18000EDA8
0x18000ea76  cmp     esi, 0FFFFFEA6h
0x18000ea7c  jz      loc_18000EC7E
0x18000ea82  cmp     esi, 0FFFFFDEFh
0x18000ea88  jz      loc_18000ED9E
0x18000ea8e  cmp     esi, 0FFFFF8F0h
0x18000ea94  jz      loc_18000ED9E
0x18000ea9a  cmp     esi, 0FFFFFE02h
0x18000eaa0  jz      loc_18000ED9E
0x18000eaa6  test    esi, esi
0x18000eaa8  jns     loc_18000ED93
0x18000eaae  cmp     esi, 0FFFFFBB2h
0x18000eab4  jz      loc_18000EBA5
0x18000eaba  cmp     esi, 0FFFFFBE2h
0x18000eac0  jnz     loc_18000EC9C
0x18000eac6  mov     r8d, 3Bh ; ';'
0x18000eacc  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ead3  call    Log_AssertionEvent
0x18000ead8  cmp     esi, 0FFFFFBC2h
0x18000eade  jnz     short loc_18000EAF4
0x18000eae0  mov     r8d, 47h ; 'G'
0x18000eae6  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000eaed  call    Log_AssertionEvent
0x18000eaf2  int     2Ch; Windows NT - assertion failure
0x18000eaf4  neg     esi
0x18000eaf6  or      esi, 80C80000h
0x18000eafc  mov     r9d, 5B5h
0x18000eb02  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000eb09  xor     edx, edx
0x18000eb0b  mov     ecx, esi
0x18000eb0d  call    Log_UnistoreHREvent_0
0x18000eb12  test    esi, esi
0x18000eb14  js      loc_18000ECB3
0x18000eb1a  mov     rsi, [r14+0E8h]
0x18000eb21  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000eb28  mov     ecx, 18h; unsigned __int64
0x18000eb2d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000eb32  test    rax, rax
0x18000eb35  jnz     loc_18000EBF2
0x18000eb3b  mov     esi, 8007000Eh
0x18000eb40  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000eb47  mov     ecx, esi
0x18000eb49  mov     r9d, 57Ch
0x18000eb4f  xor     edx, edx
0x18000eb51  call    Log_UnistoreHREvent_0
0x18000eb56  mov     r9d, 597h
0x18000eb5c  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000eb63  mov     edx, 1
0x18000eb68  mov     ecx, esi
0x18000eb6a  call    Log_UnistoreHREvent_0
0x18000eb6f  lea     rcx, [r14+118h]; lpCriticalSection
0x18000eb76  call    cs:__imp_LeaveCriticalSection
0x18000eb7c  mov     eax, esi
0x18000eb7e  mov     rsi, [rsp+140h+var_38]
0x18000eb86  mov     rcx, [rbp+40h+var_50]
0x18000eb8a  xor     rcx, rsp; StackCookie
0x18000eb8d  call    __security_check_cookie
0x18000eb92  add     rsp, 110h
0x18000eb99  pop     r15
0x18000eb9b  pop     r14
0x18000eb9d  pop     r13
0x18000eb9f  pop     r12
0x18000eba1  pop     rdi
0x18000eba2  pop     rbx
0x18000eba3  pop     rbp
0x18000eba4  retn
0x18000eba5  mov     r8d, 3Eh ; '>'
0x18000ebab  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ebb2  call    Log_AssertionEvent
0x18000ebb7  jmp     loc_18000EAF4
0x18000ebbc  mov     ecx, dword ptr [rsp+140h+var_EC+4]
0x18000ebc0  sub     ecx, 0Ah
0x18000ebc3  jz      loc_18000ECF4
0x18000ebc9  sub     ecx, 1
0x18000ebcc  jz      loc_18000ECDD
0x18000ebd2  cmp     ecx, 1
0x18000ebd5  jnz     loc_18000EA04
0x18000ebdb  mov     eax, [rsp+140h+var_108]
0x18000ebdf  lea     rcx, [rsp+140h+var_110]
0x18000ebe4  mov     [rsp+140h+var_110], eax
0x18000ebe8  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x18000ebed  jmp     loc_18000EA04
0x18000ebf2  mov     rcx, [rbx+10h]
0x18000ebf6  mov     r9, [rsp+140h+var_100]
0x18000ebfb  mov     [rax+10h], rcx
0x18000ebff  mov     rcx, [rsi+8]
0x18000ec03  mov     [rax+8], rcx
0x18000ec07  mov     [rax], rsi
0x18000ec0a  mov     [rcx], rax
0x18000ec0d  mov     [rsi+8], rax
0x18000ec11  inc     qword ptr [r14+0F8h]
0x18000ec18  mov     rax, [rbx+10h]
0x18000ec1c  mov     [r9], rax
0x18000ec1f  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x18000ec25  mov     ecx, [r14+0F8h]
0x18000ec2c  test    eax, eax
0x18000ec2e  jnz     loc_18000EDB2
0x18000ec34  mov     rcx, [rbx+8]
0x18000ec38  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; std::nothrow_t const std::nothrow
0x18000ec3f  mov     rax, [rbx]
0x18000ec42  mov     [rcx], rax
0x18000ec45  mov     [rax+8], rcx
0x18000ec49  mov     rcx, rbx; Block
0x18000ec4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ec51  dec     qword ptr [r15+10h]
0x18000ec55  mov     eax, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x18000ec5b  mov     ecx, [r14+110h]
0x18000ec62  test    eax, eax
0x18000ec64  jnz     loc_18000EDDD
0x18000ec6a  lea     rcx, [r14+118h]; lpCriticalSection
0x18000ec71  call    cs:__imp_LeaveCriticalSection
0x18000ec77  xor     eax, eax
0x18000ec79  jmp     loc_18000EB7E
0x18000ec7e  mov     esi, 80070018h
0x18000ec83  jmp     loc_18000EAFC
0x18000ec88  mov     esi, 80070019h
0x18000ec8d  jmp     loc_18000EAFC
0x18000ec92  mov     esi, 80070002h
0x18000ec97  jmp     loc_18000EAFC
0x18000ec9c  cmp     esi, 0FFFFFBD3h
0x18000eca2  jnz     loc_18000EAD8
0x18000eca8  mov     r8d, 41h ; 'A'
0x18000ecae  jmp     loc_18000EAE6
0x18000ecb3  mov     r9d, 57Ah
0x18000ecb9  lea     r8, aOnecoreuapBase_29; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ecc0  mov     edx, 1
0x18000ecc5  mov     ecx, esi
0x18000ecc7  call    Log_UnistoreHREvent_0
0x18000eccc  cmp     esi, 80070490h
0x18000ecd2  jnz     loc_18000EB56
0x18000ecd8  jmp     loc_18000E916
0x18000ecdd  mov     eax, [rsp+140h+var_108]
0x18000ece1  lea     rcx, [rsp+140h+var_110]
0x18000ece6  mov     [rsp+140h+var_110], eax
0x18000ecea  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x18000ecef  jmp     loc_18000EA04
0x18000ecf4  cmp     [rsp+140h+var_108], 0FFFFFA7Ah
0x18000ecfc  jz      loc_18000EA04
0x18000ed02  mov     r9d, esi; unsigned int
0x18000ed05  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x18000ed0c  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x18000ed13  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18000ed1a  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x18000ed1f  test    eax, eax
0x18000ed21  jns     short loc_18000ED3E
0x18000ed23  mov     r9d, 66h ; 'f'
0x18000ed29  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ed30  xor     edx, edx
0x18000ed32  mov     ecx, eax
0x18000ed34  call    Log_UnistoreHREvent_0
0x18000ed39  jmp     loc_18000EA04
0x18000ed3e  lea     rcx, [rsp+140h+var_110]
0x18000ed43  mov     [rsp+140h+var_110], esi
0x18000ed47  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x18000ed4c  mov     ecx, esi; int
0x18000ed4e  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18000ed53  test    eax, eax
0x18000ed55  jz      loc_18000EA04
0x18000ed5b  mov     r8d, 6Dh ; 'm'
0x18000ed61  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ed68  call    Log_AssertionEvent
0x18000ed6d  int     2Ch; Windows NT - assertion failure
0x18000ed6f  jmp     loc_18000EA04
0x18000ed74  cmp     eax, esi
0x18000ed76  jnz     loc_18000EA2E
0x18000ed7c  mov     r8d, 19h
0x18000ed82  lea     rdx, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000ed89  call    Log_AssertionEvent
0x18000ed8e  jmp     loc_18000EA2E
0x18000ed93  or      esi, 0C80000h
0x18000ed99  jmp     loc_18000EAFC
0x18000ed9e  mov     esi, 80070070h
0x18000eda3  jmp     loc_18000EAFC
0x18000eda8  mov     esi, 800700B7h
0x18000edad  jmp     loc_18000EAFC
0x18000edb2  lock inc cs:dword_18010DB34
0x18000edb9  lock add cs:dword_18010DB2C, ecx
0x18000edc0  mov     eax, cs:dword_18010DB30
0x18000edc6  cmp     eax, ecx
0x18000edc8  jnb     loc_18000EC34
0x18000edce  lock cmpxchg cs:dword_18010DB30, ecx
0x18000edd6  jnz     short loc_18000EDC0
0x18000edd8  jmp     loc_18000EC34
0x18000eddd  lock inc cs:dword_18010DB40
0x18000ede4  lock add cs:dword_18010DB38, ecx
0x18000edeb  mov     eax, cs:dword_18010DB3C
0x18000edf1  cmp     eax, ecx
0x18000edf3  jnb     loc_18000EC6A
0x18000edf9  lock cmpxchg cs:dword_18010DB3C, ecx
0x18000ee01  jnz     short loc_18000EDEB
0x18000ee03  jmp     loc_18000EC6A
```
