# UnistoreJetMove(TableHandleInfo *,long,ulong)

- ea: `0x180012100`
- end: `0x1800123cb`
- name: `?UnistoreJetMove@@YAJPEAUTableHandleInfo@@JK@Z`
- size: `715`
- prototype: `int(struct TableHandleInfo *, int, unsigned int)`
- caller_count: `17`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180056cf0`
- `0x180058960`
- `0x180058a40`
- `0x1800601c0`
- `0x180061700`
- `0x1800618f0`
- `0x1800621c0`
- `0x180067630`
- `0x180080c18`
- `0x1800ab6c4`
- `0x1800add80`
- `0x1800ae200`
- `0x1800ae420`
- `0x1800ae760`
- `0x1800ae830`
- `0x1800aef30`
- `0x1800af6e4`

## callees

- `0x1800068f0`
- `0x18000f530`
- `0x180010690`
- `0x180012100`
- `0x1800125d0`
- `0x180045990`
- `0x180067c1c`
- `0x18006f180`
- `0x18007d4e4`
- `0x18007d540`
- `0x18007d59c`
- `0x1800c50f0`

## import_xrefs

- `ESENT!JetMove` at `0x180012149`
- `ESENT!JetMove` at `0x180012149`
- `ESENT!JetGetErrorInfoW` at `0x1800121c2`
- `ESENT!JetGetErrorInfoW` at `0x1800121c2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001212e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001220d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001224c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001212e`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001220d`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18001224c`

## string_xrefs

- `0x1800122e3`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x18001231b`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\dbmanager.cpp`
- `0x1800123ad`: `onecoreuap\base\appmodel\userdataaccess\services\unifiedstore\lib\esehelper.cpp`

## pseudocode

```c
__int64 __fastcall UnistoreJetMove(struct TableHandleInfo *a1, int a2)
{
  ULONGLONG TickCount64; // rax
  JET_TABLEID v5; // rdx
  JET_SESID v6; // rcx
  int v7; // esi
  JET_ERR v8; // eax
  int v9; // ebx
  int HresultFromJetError; // ebx
  int v11; // eax
  int v13; // eax
  int v14; // eax
  __int64 v15; // rcx
  unsigned __int32 v16; // edx
  int v17; // eax
  __int64 v18; // r9
  __int64 v19; // rdx
  unsigned __int32 v20; // edx
  int v21; // eax
  int v22; // [rsp+30h] [rbp-89h] BYREF
  JET_ERR v23; // [rsp+38h] [rbp-81h] BYREF
  ULONGLONG v24; // [rsp+40h] [rbp-79h] BYREF
  int v25; // [rsp+48h] [rbp-71h]
  int v26; // [rsp+50h] [rbp-69h] BYREF
  __int128 v27; // [rsp+54h] [rbp-65h]
  __int128 v28; // [rsp+64h] [rbp-55h]
  __int128 v29; // [rsp+74h] [rbp-45h]
  __int128 v30; // [rsp+84h] [rbp-35h]
  __int128 v31; // [rsp+94h] [rbp-25h]
  __int128 v32; // [rsp+A4h] [rbp-15h]
  __int128 v33; // [rsp+B4h] [rbp-5h]
  __int128 v34; // [rsp+C4h] [rbp+Bh]
  __int128 v35; // [rsp+D4h] [rbp+1Bh]
  int v36; // [rsp+E4h] [rbp+2Bh]

  v25 = 20;
  TickCount64 = GetTickCount64();
  v5 = *((_QWORD *)a1 + 2);
  v6 = *((_QWORD *)a1 + 1);
  v7 = TickCount64;
  v24 = TickCount64;
  v8 = JetMove(v6, v5, a2, 0);
  v9 = v8;
  if ( !g_fInProc || dword_18010D924 )
    goto LABEL_6;
  if ( v8 != -1414 )
  {
    v23 = v8;
    if ( v8 >= 0 )
      goto LABEL_8;
    v26 = 152;
    v36 = 0;
    v27 = 0;
    v28 = 0;
    v29 = 0;
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    v35 = 0;
    if ( (int)JetGetErrorInfoW(&v23, &v26, 152, 1, 0) < 0 )
      goto LABEL_6;
    if ( DWORD1(v27) != 10 )
    {
      if ( DWORD1(v27) == 11 )
      {
        v22 = v23;
        UnistoreTelemetry::JetInconsistentError<unsigned long>(&v22);
      }
      else if ( DWORD1(v27) == 12 )
      {
        v22 = v23;
        UnistoreTelemetry::JetFragmentationError<unsigned long>(&v22);
      }
      goto LABEL_6;
    }
    if ( v23 == -1414 )
      goto LABEL_6;
  }
  v14 = RegistrySetDWORD(HKEY_CURRENT_USER, L"Software\\Microsoft\\Unified Store", L"CorruptReason", v9);
  if ( v14 >= 0 )
  {
    v22 = v9;
    UnistoreTelemetry::MarkStoreCorruption<unsigned long>(&v22);
    if ( (unsigned int)IsJetCorruptionError(v9) )
    {
      Log_AssertionEvent(
        v15,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
        109);
      __int2c();
    }
  }
  else
  {
    Log_UnistoreHREvent_0(
      (unsigned int)v14,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\dbmanager.cpp",
      102);
  }
LABEL_6:
  if ( v9 != -1603 )
  {
    if ( v9 < 0 )
    {
      HresultFromJetError = MakeHresultFromJetError(v9);
      if ( HresultFromJetError == -1603 )
      {
LABEL_35:
        PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter((PerfAutoStartStopTimeCounter *)&v24);
        return (unsigned int)HresultFromJetError;
      }
      v18 = 1184;
      v19 = 0;
LABEL_34:
      Log_UnistoreHREvent_0(
        (unsigned int)HresultFromJetError,
        v19,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\unifiedstore\\lib\\esehelper.cpp",
        v18);
      goto LABEL_35;
    }
LABEL_8:
    HresultFromJetError = UnifiedStoreCursorLocation::UpdateToCurrentLocation(
                            (__int64)a1 + 24,
                            *(_DWORD *)a1,
                            *((_DWORD *)a1 + 1) == 0,
                            *((_QWORD *)a1 + 1),
                            *((_QWORD *)a1 + 2));
    if ( HresultFromJetError >= 0 )
    {
      v11 = GetTickCount64();
      if ( g_perfStatEnabled )
      {
        v20 = v11 - v7;
        _InterlockedIncrement(&dword_18010DAF8);
        _InterlockedAdd(&dword_18010DAF0, v11 - v7);
        do
          v21 = dword_18010DAF4;
        while ( dword_18010DAF4 < v20 && v21 != _InterlockedCompareExchange(&dword_18010DAF4, v20, dword_18010DAF4) );
      }
      return 0;
    }
    v18 = 1181;
    v19 = 1;
    goto LABEL_34;
  }
  *((_DWORD *)a1 + 6) = 0;
  v13 = GetTickCount64();
  if ( g_perfStatEnabled )
  {
    v16 = v13 - v7;
    _InterlockedIncrement(&dword_18010DAF8);
    _InterlockedAdd(&dword_18010DAF0, v13 - v7);
    do
      v17 = dword_18010DAF4;
    while ( dword_18010DAF4 < v16 && v17 != _InterlockedCompareExchange(&dword_18010DAF4, v16, dword_18010DAF4) );
  }
  return 2147942425LL;
}

```

## disassembly

```asm
0x180012100  mov     [rsp-8+arg_10], rbx
0x180012105  push    rbp
0x180012106  push    rsi
0x180012107  push    rdi
0x180012108  lea     rbp, [rsp-47h]
0x18001210d  sub     rsp, 100h
0x180012114  mov     rax, cs:__security_cookie
0x18001211b  xor     rax, rsp
0x18001211e  mov     [rbp+57h+var_20], rax
0x180012122  mov     ebx, edx
0x180012124  mov     [rbp+57h+var_C8], 14h
0x18001212b  mov     rdi, rcx
0x18001212e  call    cs:__imp_GetTickCount64
0x180012134  mov     rdx, [rdi+10h]; tableid
0x180012138  xor     r9d, r9d; grbit
0x18001213b  mov     rcx, [rdi+8]; sesid
0x18001213f  mov     r8d, ebx; cRow
0x180012142  mov     rsi, rax
0x180012145  mov     [rbp+57h+var_D0], rax
0x180012149  call    cs:__imp_JetMove
0x18001214f  cmp     cs:?g_fInProc@@3HA, 0; int g_fInProc
0x180012156  mov     ebx, eax
0x180012158  jz      short loc_1800121D0
0x18001215a  cmp     cs:dword_18010D924, 0
0x180012161  jnz     short loc_1800121D0
0x180012163  cmp     eax, 0FFFFFA7Ah
0x180012168  jz      loc_1800122BC
0x18001216e  mov     [rsp+110h+var_D8], eax
0x180012172  test    eax, eax
0x180012174  jns     short loc_1800121E0
0x180012176  xorps   xmm0, xmm0
0x180012179  mov     [rbp+57h+var_C0], 98h
0x180012180  xor     eax, eax
0x180012182  lea     rdx, [rbp+57h+var_C0]
0x180012186  mov     r9d, 1
0x18001218c  mov     [rbp+57h+var_2C], eax
0x18001218f  mov     r8d, 98h
0x180012195  mov     dword ptr [rsp+110h+var_F0], eax
0x180012199  lea     rcx, [rsp+110h+var_D8]
0x18001219e  movups  [rbp+57h+var_BC], xmm0
0x1800121a2  movups  [rbp+57h+var_AC], xmm0
0x1800121a6  movups  [rbp+57h+var_9C], xmm0
0x1800121aa  movups  [rbp+57h+var_8C], xmm0
0x1800121ae  movups  [rbp+57h+var_7C], xmm0
0x1800121b2  movups  [rbp+57h+var_6C], xmm0
0x1800121b6  movups  [rbp+57h+var_5C], xmm0
0x1800121ba  movups  [rbp+57h+var_4C], xmm0
0x1800121be  movups  [rbp+57h+var_3C], xmm0
0x1800121c2  call    cs:__imp_JetGetErrorInfoW
0x1800121c8  test    eax, eax
0x1800121ca  jns     loc_18001226A
0x1800121d0  cmp     ebx, 0FFFFF9BDh
0x1800121d6  jz      short loc_180012245
0x1800121d8  test    ebx, ebx
0x1800121da  js      loc_180012395
0x1800121e0  mov     rax, [rdi+10h]
0x1800121e4  lea     rcx, [rdi+18h]
0x1800121e8  mov     r9, [rdi+8]
0x1800121ec  xor     r8d, r8d
0x1800121ef  cmp     [rdi+4], r8d
0x1800121f3  mov     edx, [rdi]
0x1800121f5  setz    r8b
0x1800121f9  mov     [rsp+110h+var_F0], rax
0x1800121fe  call    ?UpdateToCurrentLocation@UnifiedStoreCursorLocation@@QEAAJW4US_TABLEID@@H_K1@Z; UnifiedStoreCursorLocation::UpdateToCurrentLocation(US_TABLEID,int,unsigned __int64,unsigned __int64)
0x180012203  mov     ebx, eax
0x180012205  test    eax, eax
0x180012207  js      loc_18001235B
0x18001220d  call    cs:__imp_GetTickCount64
0x180012213  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180012219  mov     rdx, rax
0x18001221c  test    ecx, ecx
0x18001221e  jnz     loc_180012368
0x180012224  xor     eax, eax
0x180012226  mov     rcx, [rbp+57h+var_20]
0x18001222a  xor     rcx, rsp; StackCookie
0x18001222d  call    __security_check_cookie
0x180012232  mov     rbx, [rsp+110h+arg_10]
0x18001223a  add     rsp, 100h
0x180012241  pop     rdi
0x180012242  pop     rsi
0x180012243  pop     rbp
0x180012244  retn
0x180012245  mov     dword ptr [rdi+18h], 0
0x18001224c  call    cs:__imp_GetTickCount64
0x180012252  mov     ecx, cs:?g_perfStatEnabled@@3KC; ulong volatile g_perfStatEnabled
0x180012258  mov     rdx, rax
0x18001225b  test    ecx, ecx
0x18001225d  jnz     loc_18001232E
0x180012263  mov     eax, 80070019h
0x180012268  jmp     short loc_180012226
0x18001226a  mov     ecx, dword ptr [rbp+57h+var_BC+4]
0x18001226d  sub     ecx, 0Ah
0x180012270  jz      short loc_1800122AE
0x180012272  sub     ecx, 1
0x180012275  jz      short loc_180012297
0x180012277  cmp     ecx, 1
0x18001227a  jnz     loc_1800121D0
0x180012280  mov     eax, [rsp+110h+var_D8]
0x180012284  lea     rcx, [rsp+110h+var_E0]
0x180012289  mov     [rsp+110h+var_E0], eax
0x18001228d  call    ??$JetFragmentationError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetFragmentationError<ulong>(ulong &&)
0x180012292  jmp     loc_1800121D0
0x180012297  mov     eax, [rsp+110h+var_D8]
0x18001229b  lea     rcx, [rsp+110h+var_E0]
0x1800122a0  mov     [rsp+110h+var_E0], eax
0x1800122a4  call    ??$JetInconsistentError@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::JetInconsistentError<ulong>(ulong &&)
0x1800122a9  jmp     loc_1800121D0
0x1800122ae  cmp     [rsp+110h+var_D8], 0FFFFFA7Ah
0x1800122b6  jz      loc_1800121D0
0x1800122bc  mov     r9d, ebx; unsigned int
0x1800122bf  lea     r8, ?c_wszUnistoreRegistryCorruptAfterMount@@3QBGB; "CorruptReason"
0x1800122c6  lea     rdx, ?c_wszUnistoreRegistryRoot@@3QBGB; "Software\\Microsoft\\Unified Store"
0x1800122cd  mov     rcx, 0FFFFFFFF80000001h; hKey
0x1800122d4  call    ?RegistrySetDWORD@@YAJPEAUHKEY__@@PEBG1K@Z; RegistrySetDWORD(HKEY__ *,ushort const *,ushort const *,ulong)
0x1800122d9  test    eax, eax
0x1800122db  jns     short loc_1800122F8
0x1800122dd  mov     r9d, 66h ; 'f'
0x1800122e3  lea     r8, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800122ea  xor     edx, edx
0x1800122ec  mov     ecx, eax
0x1800122ee  call    Log_UnistoreHREvent_0
0x1800122f3  jmp     loc_1800121D0
0x1800122f8  lea     rcx, [rsp+110h+var_E0]
0x1800122fd  mov     [rsp+110h+var_E0], ebx
0x180012301  call    ??$MarkStoreCorruption@K@UnistoreTelemetry@@SAX$$QEAK@Z; UnistoreTelemetry::MarkStoreCorruption<ulong>(ulong &&)
0x180012306  mov     ecx, ebx; int
0x180012308  call    ?IsJetCorruptionError@@YAHJ@Z; IsJetCorruptionError(long)
0x18001230d  test    eax, eax
0x18001230f  jz      loc_1800121D0
0x180012315  mov     r8d, 6Dh ; 'm'
0x18001231b  lea     rdx, aOnecoreuapBase_18; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180012322  call    Log_AssertionEvent
0x180012327  int     2Ch; Windows NT - assertion failure
0x180012329  jmp     loc_1800121D0
0x18001232e  sub     edx, esi
0x180012330  lock inc cs:dword_18010DAF8
0x180012337  lock add cs:dword_18010DAF0, edx
0x18001233e  mov     eax, cs:dword_18010DAF4
0x180012344  cmp     eax, edx
0x180012346  jnb     loc_180012263
0x18001234c  lock cmpxchg cs:dword_18010DAF4, edx
0x180012354  jnz     short loc_18001233E
0x180012356  jmp     loc_180012263
0x18001235b  mov     r9d, 49Dh
0x180012361  mov     edx, 1
0x180012366  jmp     short loc_1800123AD
0x180012368  sub     edx, esi
0x18001236a  lock inc cs:dword_18010DAF8
0x180012371  lock add cs:dword_18010DAF0, edx
0x180012378  mov     eax, cs:dword_18010DAF4
0x18001237e  cmp     eax, edx
0x180012380  jnb     loc_180012224
0x180012386  lock cmpxchg cs:dword_18010DAF4, edx
0x18001238e  jnz     short loc_180012378
0x180012390  jmp     loc_180012224
0x180012395  mov     ecx, ebx; int
0x180012397  call    ?MakeHresultFromJetError@@YAJJ@Z; MakeHresultFromJetError(long)
0x18001239c  mov     ebx, eax
0x18001239e  cmp     eax, 0FFFFF9BDh
0x1800123a3  jz      short loc_1800123BB
0x1800123a5  mov     r9d, 4A0h
0x1800123ab  xor     edx, edx
0x1800123ad  lea     r8, aOnecoreuapBase_8; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800123b4  mov     ecx, ebx
0x1800123b6  call    Log_UnistoreHREvent_0
0x1800123bb  lea     rcx, [rbp+57h+var_D0]; this
0x1800123bf  call    ??1PerfAutoStartStopTimeCounter@@QEAA@XZ; PerfAutoStartStopTimeCounter::~PerfAutoStartStopTimeCounter(void)
0x1800123c4  mov     eax, ebx
0x1800123c6  jmp     loc_180012226
```
