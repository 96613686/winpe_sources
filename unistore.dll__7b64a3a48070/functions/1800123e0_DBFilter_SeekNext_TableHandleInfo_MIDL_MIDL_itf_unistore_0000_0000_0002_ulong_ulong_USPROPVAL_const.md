# DBFilter::SeekNext(TableHandleInfo *,__MIDL___MIDL_itf_unistore_0000_0000_0002,ulong,ulong,_USPROPVAL const *)

- ea: `0x1800123e0`
- end: `0x1800125bf`
- name: `?SeekNext@DBFilter@@UEAAJPEAUTableHandleInfo@@W4__MIDL___MIDL_itf_unistore_0000_0000_0002@@KKPEBU_USPROPVAL@@@Z`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180010690`
- `0x180011ed0`
- `0x1800123e0`
- `0x1800125d0`
- `0x18002d548`
- `0x18007432c`

## import_xrefs

- `ESENT!JetMove` at `0x18001244e`
- `ESENT!JetMove` at `0x18001244e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012431`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001249e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012516`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012431`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001249e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180012516`

## string_xrefs

- `0x180012571`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`
- `0x1800125aa`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall DBFilter::SeekNext(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5)
{
  int v5; // edi
  ULONGLONG TickCount64; // rax
  JET_TABLEID v8; // rdx
  JET_SESID v9; // rcx
  int v10; // esi
  JET_ERR v11; // edi
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  unsigned __int32 v15; // edx
  int v16; // eax
  __int64 v18; // rdx
  __int64 v19; // r9
  int v20; // eax
  unsigned __int32 v21; // edx
  int v22; // eax
  unsigned int HresultFromJetError; // eax
  ULONGLONG v24; // [rsp+30h] [rbp-18h] BYREF
  int v25; // [rsp+38h] [rbp-10h]

  v5 = a3;
  if ( a5 )
    Log_AssertionEvent_10(a1, a2, 712);
  if ( v5 != 4 )
    Log_AssertionEvent_10(a1, a2, 713);
  if ( a5 || v5 != 4 )
  {
    v18 = 0;
    v13 = -2147024846;
    v19 = 714;
LABEL_18:
    Log_UnistoreHREvent_1(v13, v18, a3, v19);
    return v13;
  }
  v25 = 20;
  TickCount64 = GetTickCount64();
  v8 = *(_QWORD *)(a2 + 16);
  v9 = *(_QWORD *)(a2 + 8);
  v10 = TickCount64;
  v24 = TickCount64;
  v11 = JetMove(v9, v8, 1, 0);
  CheckCorruption(v11);
  if ( v11 == -1603 )
  {
    *(_DWORD *)(a2 + 24) = 0;
    v20 = GetTickCount64();
    if ( g_perfStatEnabled )
    {
      v21 = v20 - v10;
      _InterlockedIncrement(&dword_18010DAF8);
      _InterlockedAdd(&dword_18010DAF0, v20 - v10);
      do
        v22 = dword_18010DAF4;
      while ( dword_18010DAF4 < v21 && v22 != _InterlockedCompareExchange(&dword_18010DAF4, v21, dword_18010DAF4) );
    }
    return (unsigned int)-2147024871;
  }
  if ( v11 < 0 )
  {
    HresultFromJetError = MakeHresultFromJetError(v11);
    v13 = HresultFromJetError;
    if ( HresultFromJetError != -1603 )
      Log_UnistoreHREvent_0(
        HresultFromJetError,
        0,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        1184);
    PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&v24);
    if ( (v13 & 0x80000000) == 0 )
      return 0;
  }
  else
  {
    v12 = UnifiedStoreCursorLocation::UpdateToCurrentLocation(
            a2 + 24,
            *(_DWORD *)a2,
            *(_DWORD *)(a2 + 4) == 0,
            *(_QWORD *)(a2 + 8),
            *(_QWORD *)(a2 + 16));
    v13 = v12;
    if ( v12 >= 0 )
    {
      v14 = GetTickCount64();
      if ( g_perfStatEnabled )
      {
        v15 = v14 - v10;
        _InterlockedIncrement(&dword_18010DAF8);
        _InterlockedAdd(&dword_18010DAF0, v14 - v10);
        do
          v16 = dword_18010DAF4;
        while ( dword_18010DAF4 < v15 && v16 != _InterlockedCompareExchange(&dword_18010DAF4, v15, dword_18010DAF4) );
      }
      return 0;
    }
    Log_UnistoreHREvent_0(
      (unsigned int)v12,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
      1181);
    PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&v24);
  }
  if ( v13 != -2147024871 )
  {
    v18 = 1;
    v19 = 717;
    goto LABEL_18;
  }
  return v13;
}

```

## disassembly

```asm
0x1800123e0  mov     [rsp+arg_0], rbx
0x1800123e5  mov     [rsp+arg_8], rsi
0x1800123ea  push    rdi
0x1800123eb  sub     rsp, 40h
0x1800123ef  mov     esi, [rsp+48h+arg_20]
0x1800123f3  mov     edi, r8d
0x1800123f6  mov     rbx, rdx
0x1800123f9  test    esi, esi
0x1800123fb  jz      short loc_180012408
0x1800123fd  mov     r8d, 2C8h
0x180012403  call    Log_AssertionEvent_10
0x180012408  cmp     edi, 4
0x18001240b  jz      short loc_180012418
0x18001240d  mov     r8d, 2C9h
0x180012413  call    Log_AssertionEvent_10
0x180012418  test    esi, esi
0x18001241a  jnz     loc_1800124F7
0x180012420  cmp     edi, 4
0x180012423  jnz     loc_1800124F7
0x180012429  mov     [rsp+48h+var_10], 14h
0x180012431  call    cs:__imp_GetTickCount64
0x180012437  mov     rdx, [rbx+10h]; tableid
0x18001243b  lea     r8d, [rdi-3]; cRow
0x18001243f  mov     rcx, [rbx+8]; sesid
0x180012443  xor     r9d, r9d; grbit
0x180012446  mov     rsi, rax
0x180012449  mov     [rsp+48h+var_18], rax
0x18001244e  call    cs:__imp_JetMove
0x180012454  mov     ecx, eax; int
0x180012456  mov     edi, eax
0x180012458  call    ?CheckCorruption@@YAXJ@Z; CheckCorruption(long)
0x18001245d  cmp     edi, 0FFFFF9BDh
0x180012463  jz      loc_18001250F
0x180012469  test    edi, edi
0x18001246b  js      loc_180012590
0x180012471  mov     rax, [rbx+10h]
0x180012475  lea     rcx, [rbx+18h]
0x180012479  mov     r9, [rbx+8]
0x18001247d  xor     r8d, r8d
0x180012480  cmp     [rbx+4], r8d
0x180012484  mov     edx, [rbx]
0x180012486  setz    r8b
0x18001248a  mov     [rsp+48h+var_28], rax
0x18001248f  call    ?UpdateToCurrentLocation@UnifiedStoreCursorLocation@@QEAAJW4US_TABLEID@@H_K1@Z; UnifiedStoreCursorLocation::UpdateToCurrentLocation(US_TABLEID,int,unsigned __int64,unsigned __int64)
0x180012494  mov     ebx, eax
0x180012496  test    eax, eax
0x180012498  js      loc_18001256B
0x18001249e  call    cs:__imp_GetTickCount64
0x1800124a4  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x1800124aa  mov     rdx, rax
0x1800124ad  test    ecx, ecx
0x1800124af  jz      short loc_1800124E5
0x1800124b1  sub     edx, esi
0x1800124b3  lock inc cs:dword_18010DAF8
0x1800124ba  lock add cs:dword_18010DAF0, edx
0x1800124c1  mov     eax, cs:dword_18010DAF4
0x1800124c7  cmp     eax, edx
0x1800124c9  jnb     short loc_1800124E5
0x1800124cb  lock cmpxchg cs:dword_18010DAF4, edx
0x1800124d3  jnz     short loc_1800124C1
0x1800124d5  jmp     short loc_1800124E5
0x1800124d7  lea     rcx, [rsp+48h+var_18]; this
0x1800124dc  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x1800124e1  test    ebx, ebx
0x1800124e3  js      short loc_180012530
0x1800124e5  xor     eax, eax
0x1800124e7  mov     rbx, [rsp+48h+arg_0]
0x1800124ec  mov     rsi, [rsp+48h+arg_8]
0x1800124f1  add     rsp, 40h
0x1800124f5  pop     rdi
0x1800124f6  retn
0x1800124f7  xor     edx, edx
0x1800124f9  mov     ebx, 80070032h
0x1800124fe  mov     r9d, 2CAh
0x180012504  mov     ecx, ebx
0x180012506  call    Log_UnistoreHREvent_1
0x18001250b  mov     eax, ebx
0x18001250d  jmp     short loc_1800124E7
0x18001250f  mov     dword ptr [rbx+18h], 0
0x180012516  call    cs:__imp_GetTickCount64
0x18001251c  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180012522  mov     rdx, rax
0x180012525  test    ecx, ecx
0x180012527  jnz     short loc_180012545
0x180012529  mov     ebx, 80070019h
0x18001252e  jmp     short loc_18001250B
0x180012530  cmp     ebx, 80070019h
0x180012536  jz      short loc_18001250B
0x180012538  mov     edx, 1
0x18001253d  mov     r9d, 2CDh
0x180012543  jmp     short loc_180012504
0x180012545  sub     edx, esi
0x180012547  lock inc cs:dword_18010DAF8
0x18001254e  lock add cs:dword_18010DAF0, edx
0x180012555  mov     eax, cs:dword_18010DAF4
0x18001255b  cmp     eax, edx
0x18001255d  jnb     short loc_180012529
0x18001255f  lock cmpxchg cs:dword_18010DAF4, edx
0x180012567  jnz     short loc_180012555
0x180012569  jmp     short loc_180012529
0x18001256b  mov     r9d, 49Dh
0x180012571  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012578  mov     edx, 1
0x18001257d  mov     ecx, eax
0x18001257f  call    Log_UnistoreHREvent_0
0x180012584  lea     rcx, [rsp+48h+var_18]; this
0x180012589  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x18001258e  jmp     short loc_180012530
0x180012590  mov     ecx, edi; int
0x180012592  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x180012597  mov     ebx, eax
0x180012599  cmp     eax, 0FFFFF9BDh
0x18001259e  jz      loc_1800124D7
0x1800125a4  mov     r9d, 4A0h
0x1800125aa  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800125b1  xor     edx, edx
0x1800125b3  mov     ecx, eax
0x1800125b5  call    Log_UnistoreHREvent_0
0x1800125ba  jmp     loc_1800124D7
```
