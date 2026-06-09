# PfSvRecreateScenarioBasedDb

- ea: `0x18003623c`
- end: `0x1800367d6`
- name: `PfSvRecreateScenarioBasedDb`
- size: `1434`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `service_task`

## callers

- `0x180036030`

## callees

- `0x180004948`
- `0x180006574`
- `0x18000832c`
- `0x180021e0c`
- `0x180031b10`
- `0x180031b64`
- `0x180031e50`
- `0x180035dd4`
- `0x180035f58`
- `0x18003623c`
- `0x180038414`
- `0x18003af4c`
- `0x18003b0a8`
- `0x180054874`
- `0x180063c68`
- `0x1800810ec`
- `0x180081440`
- `0x18008b394`
- `0x1800b645a`
- `0x1800b64c0`
- `0x1800b6580`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800366ef`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800366ef`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003670a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18003670a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036700`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036700`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800363f9`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1800363f9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800363d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036796`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800363d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180036796`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800363e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800367a4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800363e5`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800367a4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036787`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180036787`

## pseudocode

```c
__int64 __fastcall PfSvRecreateScenarioBasedDb(
        __int64 a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        _BYTE *a6,
        __int64 a7)
{
  _BYTE *v9; // rdi
  void *v10; // r14
  HANDLE CurrentThread; // rax
  BOOL v12; // eax
  int v13; // r13d
  DWORD fixed; // ebx
  unsigned int v15; // ecx
  unsigned int v16; // r9d
  int v17; // r8d
  unsigned int v18; // eax
  DWORD v19; // edx
  int v20; // eax
  __int64 v21; // rdx
  int i; // esi
  DWORD v23; // eax
  DWORD v24; // eax
  unsigned int v25; // edi
  DWORD v26; // eax
  DWORD v27; // ecx
  DWORD v28; // eax
  HANDLE v29; // rax
  int v31; // [rsp+20h] [rbp-E0h]
  int v32; // [rsp+28h] [rbp-D8h]
  int v33; // [rsp+40h] [rbp-C0h] BYREF
  int v34; // [rsp+44h] [rbp-BCh]
  void *v35; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v36; // [rsp+50h] [rbp-B0h]
  __int64 v37; // [rsp+60h] [rbp-A0h]
  __int64 v38; // [rsp+68h] [rbp-98h]
  __int64 v39; // [rsp+70h] [rbp-90h]
  _DWORD v40[3]; // [rsp+78h] [rbp-88h] BYREF
  __m128i si128; // [rsp+84h] [rbp-7Ch]
  int v42; // [rsp+94h] [rbp-6Ch]
  _BYTE v43[12]; // [rsp+98h] [rbp-68h] BYREF
  _BYTE v44[4]; // [rsp+B0h] [rbp-50h] BYREF
  int v45; // [rsp+B4h] [rbp-4Ch]
  int v46; // [rsp+DCh] [rbp-24h]
  struct _FILETIME SystemTimeAsFileTime[2]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v48[624]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v49[624]; // [rsp+380h] [rbp+280h] BYREF
  _BYTE v50[624]; // [rsp+5F0h] [rbp+4F0h] BYREF
  _BYTE v51[944]; // [rsp+860h] [rbp+760h] BYREF
  _BYTE v52[944]; // [rsp+C10h] [rbp+B10h] BYREF
  wchar_t v53[264]; // [rsp+FC0h] [rbp+EC0h] BYREF
  wchar_t pszDest[264]; // [rsp+11D0h] [rbp+10D0h] BYREF

  v9 = a6;
  v38 = a7;
  v39 = a2;
  SystemTimeAsFileTime[1].dwLowDateTime = 0;
  SystemTimeAsFileTime[0] = 0;
  v34 = a4;
  v36 = 0;
  v37 = 0;
  memset_0(v50, 0, sizeof(v50));
  memset_0(v49, 0, sizeof(v49));
  memset_0(v52, 0, sizeof(v52));
  memset_0(v48, 0, sizeof(v48));
  memset_0(v51, 0, sizeof(v51));
  v46 = 0;
  memset_0(v44, 0, 0x44u);
  v10 = 0;
  v40[2] = 88;
  memset(v43, 0, sizeof(v43));
  v42 = 0;
  v40[0] = 72;
  v40[1] = 72;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  v35 = 0;
  si128.m128i_i32[0] = 24;
  PfDbDatabaseInitialize(v50, v40);
  if ( a6 )
    PfDbDatabaseInitialize(a6, v40);
  else
    v9 = v50;
  PfDbDatabaseInitialize(v48, 0);
  PfDbDatabaseInitialize(v49, 0);
  BtDbParametersSetDefault(v44);
  v45 = 64;
  BtDbDatabaseInitialize(v51);
  BtDbDatabaseInitialize(v52);
  CurrentThread = GetCurrentThread();
  v12 = SetThreadPriority(CurrentThread, 0x10000);
  *(_OWORD *)&SystemTimeAsFileTime[0].dwLowDateTime = 0;
  v13 = v12;
  GetSystemTimeAsFileTime(&SystemTimeAsFileTime[1]);
  fixed = PfsEnumeratePrefetchDirectory((STRSAFE_LPCWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL), 1, -1);
  if ( !fixed )
  {
    v15 = 0;
    HIDWORD(v37) = 0;
    v16 = 0;
    v17 = 7;
    do
    {
      if ( !v17 )
        break;
      v18 = v15;
      v19 = SystemTimeAsFileTime[0].dwLowDateTime & (1 << v15);
      if ( !v19 )
        v18 = v16;
      ++v15;
      v16 = v18;
      v20 = v17 - 1;
      if ( !v19 )
        v20 = v17;
      v17 = v20;
    }
    while ( v15 < 0x20 );
    *(_QWORD *)&v36 = v9;
    LODWORD(v37) = a3;
    *((_QWORD *)&v36 + 1) = *(_QWORD *)&SystemTimeAsFileTime[1] - 864000000000LL * (v16 + 1);
    fixed = PfsEnumeratePrefetchDirectory((STRSAFE_LPCWSTR)(*(_QWORD *)&PfSvcGlobals + 888LL), 1, -1);
    if ( !fixed )
    {
      for ( i = 0; i < 2; ++i )
      {
        if ( !(unsigned int)PfSvResPriGetStaticDbPath(v53, v21, i) )
        {
          v23 = PfSvResPriStaticDbReadEx(v51, v53, 0);
          fixed = v23;
          if ( v23 != 2 )
          {
            if ( v23 )
              goto LABEL_43;
            fixed = BtDbConvertToPfDb(v51, v48);
            if ( fixed )
              goto LABEL_43;
            BtDbDatabaseCleanup(v51);
            BtDbDatabaseInitialize(v51);
            fixed = PfDbDatabaseFixPaths(v48);
            if ( fixed )
              goto LABEL_43;
            fixed = PfDbDatabaseSubtract(v9, v48);
            if ( fixed )
              goto LABEL_43;
            PfDbDatabaseCleanup(v48);
            PfDbDatabaseInitialize(v48, 0);
          }
        }
      }
      if ( !a5 || (fixed = PfDbDatabaseSubtract(v9, a5)) == 0 )
      {
        fixed = PfXpTaskCheckContinue(a1);
        if ( !fixed )
        {
          v33 = 0;
          v24 = PfSvDynPriDbBoostAndSortDb(v9, &v35, &v33);
          v10 = v35;
          fixed = v24;
          if ( !v24 )
          {
            fixed = PfSvDynPriDbConvertToPrefetchDb((unsigned int)v49, (_DWORD)v9, (_DWORD)v35, v33, v31, v32, v34, v38);
            if ( !fixed )
            {
              PfDbDatabaseCleanup(v50);
              PfDbDatabaseInitialize(v50, 0);
              if ( StringCchPrintfW(pszDest, 0x104u, L"%s\\%s", *(_QWORD *)&PfSvcGlobals + 888LL, v39) >= 0 )
              {
                fixed = BtDbConvertFromPfDb(v49, v52);
                if ( !fixed )
                {
                  PfDbDatabaseCleanup(v49);
                  PfDbDatabaseInitialize(v49, 0);
                  v25 = 0;
                  while ( v25 < 5 )
                  {
                    v26 = BtDbDatabaseWrite(v52, pszDest);
                    fixed = v26;
                    if ( !v26 )
                      goto LABEL_42;
                    if ( v26 != 32 )
                      goto LABEL_43;
                    ++v25;
                    v27 = 1000 * v25;
                    if ( *(_QWORD *)(*(_QWORD *)&PfSvcGlobals + 880LL) )
                    {
                      v28 = WaitForSingleObject(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 880LL), v27);
                      if ( !v28 )
                      {
                        fixed = 1237;
                        goto LABEL_43;
                      }
                      if ( v28 != 258 )
                      {
                        fixed = GetLastError();
                        goto LABEL_43;
                      }
                    }
                    else
                    {
                      Sleep(v27);
                    }
                  }
                  if ( fixed )
                    goto LABEL_43;
LABEL_42:
                  BtDbDatabaseCleanup(v52);
                  BtDbDatabaseInitialize(v52);
                  fixed = 0;
                }
              }
              else
              {
                fixed = 111;
              }
            }
          }
        }
      }
    }
  }
LABEL_43:
  PfDbDatabaseCleanup(v50);
  PfDbDatabaseCleanup(v49);
  PfDbDatabaseCleanup(v48);
  BtDbDatabaseCleanup(v51);
  BtDbDatabaseCleanup(v52);
  if ( v10 )
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v10);
  if ( v13 != 400 )
  {
    v29 = GetCurrentThread();
    SetThreadPriority(v29, 0x20000);
  }
  return fixed;
}

```

## disassembly

```asm
0x18003623c  mov     [rsp-8+arg_18], rbx
0x180036241  push    rbp
0x180036242  push    rsi
0x180036243  push    rdi
0x180036244  push    r12
0x180036246  push    r13
0x180036248  push    r14
0x18003624a  push    r15
0x18003624c  lea     rbp, [rsp-12F0h]
0x180036254  mov     eax, 13F0h
0x180036259  call    _alloca_probe
0x18003625e  sub     rsp, rax
0x180036261  mov     rax, cs:__security_cookie
0x180036268  xor     rax, rsp
0x18003626b  mov     [rbp+1320h+var_40], rax
0x180036272  mov     rax, [rbp+1320h+arg_30]
0x180036279  mov     esi, r8d
0x18003627c  mov     r12, [rbp+1320h+arg_20]
0x180036283  mov     r15, rcx
0x180036286  mov     rdi, [rbp+1320h+arg_28]
0x18003628d  lea     rcx, [rbp+1320h+var_E30]; void *
0x180036294  mov     [rsp+1420h+var_13B8], rax
0x180036299  xorps   xmm0, xmm0
0x18003629c  xor     eax, eax
0x18003629e  mov     [rsp+1420h+var_13B0], rdx
0x1800362a3  mov     qword ptr [rbp+1320h+SystemTimeAsFileTime.dwHighDateTime], rax
0x1800362a7  mov     r14d, 270h
0x1800362ad  mov     r8d, r14d; Size
0x1800362b0  mov     qword ptr [rbp+1320h+SystemTimeAsFileTime.dwLowDateTime], rax
0x1800362b4  xor     edx, edx; Val
0x1800362b6  mov     [rsp+1420h+var_13DC], r9d
0x1800362bb  movups  [rsp+1420h+var_13D0], xmm0
0x1800362c0  mov     [rsp+1420h+var_13C0], rax
0x1800362c5  call    memset_0
0x1800362ca  mov     r8d, r14d; Size
0x1800362cd  lea     rcx, [rbp+1320h+var_10A0]; void *
0x1800362d4  xor     edx, edx; Val
0x1800362d6  call    memset_0
0x1800362db  mov     ebx, 3B0h
0x1800362e0  lea     rcx, [rbp+1320h+var_810]; void *
0x1800362e7  mov     r8d, ebx; Size
0x1800362ea  xor     edx, edx; Val
0x1800362ec  call    memset_0
0x1800362f1  mov     r8d, r14d; Size
0x1800362f4  lea     rcx, [rbp+1320h+var_1310]; void *
0x1800362f8  xor     edx, edx; Val
0x1800362fa  call    memset_0
0x1800362ff  mov     r8d, ebx; Size
0x180036302  lea     rcx, [rbp+1320h+var_BC0]; void *
0x180036309  xor     edx, edx; Val
0x18003630b  call    memset_0
0x180036310  xor     eax, eax
0x180036312  lea     rcx, [rbp+1320h+var_1370]; void *
0x180036316  xor     edx, edx; Val
0x180036318  mov     [rbp+1320h+var_1344], eax
0x18003631b  lea     r8d, [rax+44h]; Size
0x18003631f  call    memset_0
0x180036324  xor     r14d, r14d
0x180036327  mov     [rbp+1320h+var_13A0], 58h ; 'X'
0x18003632e  xorps   xmm0, xmm0
0x180036331  mov     qword ptr [rbp+1320h+var_1388], r14
0x180036335  movdqu  [rbp+1320h+var_139C+4], xmm0
0x18003633a  lea     rdx, [rsp+1420h+var_13A8]
0x18003633f  xor     eax, eax
0x180036341  movdqa  xmm0, cs:__xmm@00000010000000100000001000000010
0x180036349  lea     ecx, [r14+48h]
0x18003634d  mov     [rsp+1420h+var_13A8], ecx
0x180036351  mov     [rsp+1420h+var_13A4], ecx
0x180036355  lea     rcx, [rbp+1320h+var_E30]
0x18003635c  movups  [rbp+1320h+var_139C], xmm0
0x180036360  mov     [rsp+1420h+var_13D8], r14
0x180036365  mov     qword ptr [rbp+1320h+var_1388+4], rax
0x180036369  mov     dword ptr [rbp+1320h+var_139C], 18h
0x180036370  call    PfDbDatabaseInitialize
0x180036375  test    rdi, rdi
0x180036378  jz      short loc_180036389
0x18003637a  lea     rdx, [rsp+1420h+var_13A8]
0x18003637f  mov     rcx, rdi
0x180036382  call    PfDbDatabaseInitialize
0x180036387  jmp     short loc_180036390
0x180036389  lea     rdi, [rbp+1320h+var_E30]
0x180036390  xor     edx, edx
0x180036392  lea     rcx, [rbp+1320h+var_1310]
0x180036396  call    PfDbDatabaseInitialize
0x18003639b  xor     edx, edx
0x18003639d  lea     rcx, [rbp+1320h+var_10A0]
0x1800363a4  call    PfDbDatabaseInitialize
0x1800363a9  lea     rcx, [rbp+1320h+var_1370]
0x1800363ad  call    BtDbParametersSetDefault
0x1800363b2  lea     rdx, [rbp+1320h+var_1370]
0x1800363b6  mov     [rbp+1320h+var_136C], 40h ; '@'
0x1800363bd  lea     rcx, [rbp+1320h+var_BC0]; void *
0x1800363c4  call    BtDbDatabaseInitialize
0x1800363c9  xor     edx, edx
0x1800363cb  lea     rcx, [rbp+1320h+var_810]; void *
0x1800363d2  call    BtDbDatabaseInitialize
0x1800363d7  call    cs:__imp_GetCurrentThread
0x1800363dd  mov     rcx, rax; hThread
0x1800363e0  mov     edx, 10000h; nPriority
0x1800363e5  call    cs:__imp_SetThreadPriority
0x1800363eb  xorps   xmm0, xmm0
0x1800363ee  lea     rcx, [rbp+1320h+SystemTimeAsFileTime.dwLowDateTime+8]; lpSystemTimeAsFileTime
0x1800363f2  movups  xmmword ptr [rbp+1320h+SystemTimeAsFileTime.dwLowDateTime], xmm0
0x1800363f6  mov     r13d, eax
0x1800363f9  call    cs:__imp_GetSystemTimeAsFileTime
0x1800363ff  mov     rcx, cs:PfSvcGlobals
0x180036406  lea     r8, [rbp+1320h+SystemTimeAsFileTime]
0x18003640a  add     rcx, 378h; pszSrc
0x180036411  mov     [rsp+1420h+var_13F8], 0FFFFFFFFh; int
0x180036419  mov     r9, r15
0x18003641c  mov     [rsp+1420h+var_1400], 1; int
0x180036424  lea     rdx, PfSvDynPriDbSelectActiveDays
0x18003642b  call    PfsEnumeratePrefetchDirectory
0x180036430  mov     ebx, eax
0x180036432  test    eax, eax
0x180036434  jnz     loc_180036739
0x18003643a  xor     ecx, ecx
0x18003643c  mov     dword ptr [rsp+1420h+var_13C0+4], r14d
0x180036441  xor     r9d, r9d
0x180036444  lea     r8d, [rax+7]
0x180036448  lea     r10d, [rax+1]
0x18003644c  test    r8d, r8d
0x18003644f  jz      short loc_180036477
0x180036451  mov     eax, ecx
0x180036453  mov     edx, r10d
0x180036456  shl     edx, cl
0x180036458  and     edx, [rbp+1320h+SystemTimeAsFileTime.dwLowDateTime]
0x18003645b  cmovz   eax, r9d
0x18003645f  add     ecx, r10d
0x180036462  test    edx, edx
0x180036464  mov     r9d, eax
0x180036467  lea     eax, [r8-1]
0x18003646b  cmovz   eax, r8d
0x18003646f  mov     r8d, eax
0x180036472  cmp     ecx, 20h ; ' '
0x180036475  jb      short loc_18003644C
0x180036477  lea     ecx, [r9+1]
0x18003647b  mov     [rsp+1420h+var_13F8], 0FFFFFFFFh; int
0x180036483  mov     rax, 0C92A69C000h
0x18003648d  mov     qword ptr [rsp+1420h+var_13D0], rdi
0x180036492  imul    rcx, rax
0x180036496  mov     rax, qword ptr [rbp+1320h+SystemTimeAsFileTime.dwLowDateTime+8]
0x18003649a  lea     r8, [rsp+1420h+var_13D0]
0x18003649f  sub     rax, rcx
0x1800364a2  mov     dword ptr [rsp+1420h+var_13C0], esi
0x1800364a6  mov     rcx, cs:PfSvcGlobals
0x1800364ad  lea     rdx, PfSvDynPriDbPopulateDbFromPfFiles
0x1800364b4  add     rcx, 378h; pszSrc
0x1800364bb  mov     qword ptr [rsp+1420h+var_13D0+8], rax
0x1800364c0  mov     r9, r15
0x1800364c3  mov     [rsp+1420h+var_1400], r10d; int
0x1800364c8  call    PfsEnumeratePrefetchDirectory
0x1800364cd  mov     ebx, eax
0x1800364cf  test    eax, eax
0x1800364d1  jnz     loc_180036739
0x1800364d7  xor     esi, esi
0x1800364d9  cmp     esi, 2
0x1800364dc  jge     loc_180036596
0x1800364e2  mov     r8d, esi
0x1800364e5  lea     rcx, [rbp+1320h+var_460]
0x1800364ec  call    PfSvResPriGetStaticDbPath
0x1800364f1  test    eax, eax
0x1800364f3  jnz     loc_18003658F
0x1800364f9  xor     r8d, r8d
0x1800364fc  lea     rdx, [rbp+1320h+var_460]
0x180036503  lea     rcx, [rbp+1320h+var_BC0]
0x18003650a  call    PfSvResPriStaticDbReadEx
0x18003650f  mov     ebx, eax
0x180036511  cmp     eax, 2
0x180036514  jz      short loc_18003658F
0x180036516  test    eax, eax
0x180036518  jnz     loc_180036739
0x18003651e  lea     rdx, [rbp+1320h+var_1310]
0x180036522  lea     rcx, [rbp+1320h+var_BC0]
0x180036529  call    BtDbConvertToPfDb
0x18003652e  mov     ebx, eax
0x180036530  test    eax, eax
0x180036532  jnz     loc_180036739
0x180036538  lea     rcx, [rbp+1320h+var_BC0]
0x18003653f  call    BtDbDatabaseCleanup
0x180036544  xor     edx, edx
0x180036546  lea     rcx, [rbp+1320h+var_BC0]; void *
0x18003654d  call    BtDbDatabaseInitialize
0x180036552  lea     rcx, [rbp+1320h+var_1310]
0x180036556  call    PfDbDatabaseFixPaths
0x18003655b  mov     ebx, eax
0x18003655d  test    eax, eax
0x18003655f  jnz     loc_180036739
0x180036565  lea     rdx, [rbp+1320h+var_1310]
0x180036569  mov     rcx, rdi
0x18003656c  call    PfDbDatabaseSubtract
0x180036571  mov     ebx, eax
0x180036573  test    eax, eax
0x180036575  jnz     loc_180036739
0x18003657b  lea     rcx, [rbp+1320h+var_1310]
0x18003657f  call    PfDbDatabaseCleanup
0x180036584  xor     edx, edx
0x180036586  lea     rcx, [rbp+1320h+var_1310]
0x18003658a  call    PfDbDatabaseInitialize
0x18003658f  inc     esi
0x180036591  jmp     loc_1800364D9
0x180036596  test    r12, r12
0x180036599  jz      short loc_1800365B0
0x18003659b  mov     rdx, r12
0x18003659e  mov     rcx, rdi
0x1800365a1  call    PfDbDatabaseSubtract
0x1800365a6  mov     ebx, eax
0x1800365a8  test    eax, eax
0x1800365aa  jnz     loc_180036739
0x1800365b0  mov     rcx, r15
0x1800365b3  call    PfXpTaskCheckContinue
0x1800365b8  mov     ebx, eax
0x1800365ba  test    eax, eax
0x1800365bc  jnz     loc_180036739
0x1800365c2  lea     r8, [rsp+1420h+var_13E0]
0x1800365c7  mov     [rsp+1420h+var_13E0], r14d
0x1800365cc  lea     rdx, [rsp+1420h+var_13D8]
0x1800365d1  mov     rcx, rdi
0x1800365d4  call    PfSvDynPriDbBoostAndSortDb
0x1800365d9  mov     r14, [rsp+1420h+var_13D8]
0x1800365de  mov     ebx, eax
0x1800365e0  test    eax, eax
0x1800365e2  jnz     loc_180036739
0x1800365e8  mov     rax, [rsp+1420h+var_13B8]
0x1800365ed  lea     rcx, [rbp+1320h+var_10A0]
0x1800365f4  mov     r9d, [rsp+1420h+var_13E0]
0x1800365f9  mov     r8, r14
0x1800365fc  mov     [rsp+1420h+var_13E8], rax
0x180036601  mov     rdx, rdi
0x180036604  mov     eax, [rsp+1420h+var_13DC]
0x180036608  mov     [rsp+1420h+var_13F0], eax
0x18003660c  call    PfSvDynPriDbConvertToPrefetchDb
0x180036611  mov     ebx, eax
0x180036613  test    eax, eax
0x180036615  jnz     loc_180036739
0x18003661b  lea     rcx, [rbp+1320h+var_E30]
0x180036622  call    PfDbDatabaseCleanup
0x180036627  xor     edx, edx
0x180036629  lea     rcx, [rbp+1320h+var_E30]
0x180036630  call    PfDbDatabaseInitialize
0x180036635  mov     r9, cs:PfSvcGlobals
0x18003663c  lea     r8, aSS; "%s\\%s"
0x180036643  mov     rax, [rsp+1420h+var_13B0]
0x180036648  lea     rcx, [rbp+1320h+pszDest]; pszDest
0x18003664f  add     r9, 378h
0x180036656  mov     qword ptr [rsp+1420h+var_1400], rax
0x18003665b  mov     edx, 104h; cchDest
0x180036660  call    StringCchPrintfW
0x180036665  test    eax, eax
0x180036667  jns     short loc_180036673
0x180036669  mov     ebx, 6Fh ; 'o'
0x18003666e  jmp     loc_180036739
0x180036673  lea     rdx, [rbp+1320h+var_810]
0x18003667a  lea     rcx, [rbp+1320h+var_10A0]
0x180036681  call    BtDbConvertFromPfDb
0x180036686  mov     ebx, eax
0x180036688  test    eax, eax
0x18003668a  jnz     loc_180036739
0x180036690  lea     rcx, [rbp+1320h+var_10A0]
0x180036697  call    PfDbDatabaseCleanup
0x18003669c  xor     edx, edx
0x18003669e  lea     rcx, [rbp+1320h+var_10A0]
0x1800366a5  call    PfDbDatabaseInitialize
0x1800366aa  xor     edi, edi
0x1800366ac  cmp     edi, 5
0x1800366af  jnb     short loc_180036719
0x1800366b1  lea     rdx, [rbp+1320h+pszDest]
0x1800366b8  lea     rcx, [rbp+1320h+var_810]
0x1800366bf  call    BtDbDatabaseWrite
0x1800366c4  mov     ebx, eax
0x1800366c6  test    eax, eax
0x1800366c8  jz      short loc_18003671D
0x1800366ca  cmp     eax, 20h ; ' '
0x1800366cd  jnz     short loc_180036739
0x1800366cf  mov     rax, cs:PfSvcGlobals
0x1800366d6  inc     edi
0x1800366d8  imul    ecx, edi, 3E8h; dwMilliseconds
0x1800366de  mov     r8, [rax+370h]
0x1800366e5  test    r8, r8
0x1800366e8  jz      short loc_18003670A
0x1800366ea  mov     edx, ecx; dwMilliseconds
0x1800366ec  mov     rcx, r8; hHandle
0x1800366ef  call    cs:__imp_WaitForSingleObject
0x1800366f5  test    eax, eax
0x1800366f7  jz      short loc_180036712
0x1800366f9  cmp     eax, 102h
0x1800366fe  jz      short loc_1800366AC
0x180036700  call    cs:__imp_GetLastError
0x180036706  mov     ebx, eax
0x180036708  jmp     short loc_180036739
0x18003670a  call    cs:__imp_Sleep
0x180036710  jmp     short loc_1800366AC
0x180036712  mov     ebx, 4D5h
0x180036717  jmp     short loc_180036739
0x180036719  test    ebx, ebx
0x18003671b  jnz     short loc_180036739
0x18003671d  lea     rcx, [rbp+1320h+var_810]
0x180036724  call    BtDbDatabaseCleanup
0x180036729  xor     edx, edx
0x18003672b  lea     rcx, [rbp+1320h+var_810]; void *
  ... truncated ...
```
