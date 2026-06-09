# RestoreDumpSettings(void)

- ea: `0x14000964c`
- end: `0x140009c2d`
- name: `?RestoreDumpSettings@@YAJXZ`
- size: `1505`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, registry_config`

## callers

- `0x140009c34`

## callees

- `0x14000162c`
- `0x140003200`
- `0x140003224`
- `0x14000470c`
- `0x140007c50`
- `0x140008220`
- `0x140008c40`
- `0x14000964c`
- `0x14000a098`
- `0x14000e340`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x140009886`
- `api-ms-win-crt-private-l1-1-0!_o__wcstoi64` at `0x140009886`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009780`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009800`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009907`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009780`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009800`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x140009907`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140009ae3`
- `api-ms-win-crt-private-l1-1-0!wcschr` at `0x140009ae3`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009bbb`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140009bbb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009b12`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140009b12`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b61`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b31`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b4a`
- `api-ms-win-core-registry-l1-1-0!RegDeleteValueW` at `0x140009b61`
- `wer!WerpReinitializeKernelCrashDump` at `0x14000997e`
- `wer!WerpReinitializeKernelCrashDump` at `0x14000997e`

## string_xrefs

- `0x1400098b6`: `Initialize failed for CRASH_CONTROL_KEY_PATH`

## pseudocode

```c
__int64 RestoreDumpSettings(void)
{
  int v0; // r14d
  __int64 v1; // r15
  int v2; // edi
  const char *v3; // rax
  __int64 v4; // rdx
  int v5; // eax
  int v6; // ebx
  HKEY v7; // rdx
  unsigned int v8; // r9d
  wchar_t **v9; // r9
  unsigned __int64 v10; // r11
  void **v11; // rbx
  __int64 v12; // r10
  int v13; // ecx
  int v14; // r8d
  int v15; // edx
  int v16; // ecx
  HKEY v17; // rsi
  wchar_t *v18; // rbx
  const WCHAR *v19; // rdx
  wil::details *phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  HKEY *phkResulta; // [rsp+20h] [rbp-E0h]
  char *v24; // [rsp+30h] [rbp-D0h]
  char *v25; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v27[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+54h] [rbp-ACh]
  wchar_t *String; // [rsp+58h] [rbp-A8h]
  __m128i si128; // [rsp+60h] [rbp-A0h]
  void *v31; // [rsp+70h] [rbp-90h]
  _WORD *v32; // [rsp+78h] [rbp-88h]
  _WORD v33[8]; // [rsp+80h] [rbp-80h] BYREF
  void *v34; // [rsp+90h] [rbp-70h]
  _WORD *v35; // [rsp+98h] [rbp-68h]
  _WORD v36[8]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v37; // [rsp+B0h] [rbp-50h]
  int v38; // [rsp+C0h] [rbp-40h] BYREF
  int v39; // [rsp+C4h] [rbp-3Ch] BYREF
  int v40; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v41; // [rsp+D0h] [rbp-30h] BYREF
  char v42[32]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 *v43; // [rsp+100h] [rbp+0h]
  __int64 v44; // [rsp+108h] [rbp+8h]
  int *v45; // [rsp+110h] [rbp+10h]
  __int64 v46; // [rsp+118h] [rbp+18h]
  int *v47; // [rsp+120h] [rbp+20h]
  __int64 v48; // [rsp+128h] [rbp+28h]
  const wchar_t *v49; // [rsp+130h] [rbp+30h]
  __int64 v50; // [rsp+138h] [rbp+38h]
  int *v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]
  wil::details::in1diag4 *retaddr; // [rsp+1A8h] [rbp+A8h]

  v31 = v33;
  v27[0] = 0;
  v32 = v33;
  v28 = 0;
  v34 = v36;
  String = (wchar_t *)-1LL;
  v35 = v36;
  si128 = _mm_load_si128((const __m128i *)&_xmm_ffffffffffffffffffffffffffffffff);
  v33[0] = 0;
  v36[0] = 0;
  v0 = 0;
  v37 = 0;
  v1 = 0;
  LODWORD(v25) = 0;
  hKey = 0;
  v2 = CRegSetting::Initialize(v27, 0, L"System\\CurrentControlSet\\Control\\CrashControl", L"CrashDumpEnabled.New", 0);
  if ( v2 >= 0 )
  {
    if ( CRegSetting::Load((CRegSetting *)v27, HKEY_LOCAL_MACHINE, 0) < 0 )
      goto LABEL_47;
    if ( LOBYTE(v27[0]) )
    {
      if ( !v28 )
      {
        v0 = *(_DWORD *)String;
LABEL_11:
        v2 = CRegSetting::Initialize(
               v27,
               0,
               L"System\\CurrentControlSet\\Control\\CrashControl",
               L"CrashDumpEnabled.Old",
               0);
        if ( v2 < 0 )
        {
          v3 = "Initialize failed for CRASH_DUMP_ENABLED_OLD";
          v4 = 2311;
          goto LABEL_3;
        }
        if ( CRegSetting::Load((CRegSetting *)v27, HKEY_LOCAL_MACHINE, 0) < 0 )
          goto LABEL_47;
        if ( !LOBYTE(v27[0]) )
          goto LABEL_19;
        if ( !v28 )
        {
          v5 = *(_DWORD *)String;
          goto LABEL_20;
        }
        if ( v28 == 1 )
          v5 = wcstol(String, 0, 10);
        else
LABEL_19:
          v5 = v37;
LABEL_20:
        LODWORD(v25) = v5;
        v2 = CRegSetting::Initialize(
               v27,
               7,
               L"System\\CurrentControlSet\\Control\\CrashControl",
               L"CrashDumpEnabled.Time",
               0);
        if ( v2 < 0 )
        {
          v3 = "Initialize failed for CRASH_DUMP_ENABLED_TIME";
          v4 = 2337;
          goto LABEL_3;
        }
        if ( CRegSetting::Load((CRegSetting *)v27, HKEY_LOCAL_MACHINE, 0) >= 0 )
        {
          if ( !LOBYTE(v27[0]) )
            goto LABEL_28;
          if ( v28 == 7 )
          {
            v1 = *(_QWORD *)String;
            goto LABEL_29;
          }
          if ( v28 == 1 )
            v1 = _wcstoi64(String, 0, 10);
          else
LABEL_28:
            v1 = v37;
        }
LABEL_29:
        v2 = CRegSetting::Initialize(
               v27,
               0,
               L"System\\CurrentControlSet\\Control\\CrashControl",
               L"CrashDumpEnabled",
               0);
        if ( v2 < 0 )
        {
          v3 = "Initialize failed for CRASH_CONTROL_KEY_PATH";
          v4 = 2364;
          goto LABEL_3;
        }
        if ( CRegSetting::Load((CRegSetting *)v27, HKEY_LOCAL_MACHINE, 0) >= 0 )
        {
          if ( !LOBYTE(v27[0]) )
            goto LABEL_37;
          if ( !v28 )
          {
            v6 = *(_DWORD *)String;
            goto LABEL_38;
          }
          if ( v28 == 1 )
            v6 = wcstol(String, 0, 10);
          else
LABEL_37:
            v6 = v37;
LABEL_38:
          if ( v6 == v0 )
          {
            LODWORD(v24) = (_DWORD)v25;
            LODWORD(phkResult) = 0x80000000;
            wil::details::in1diag4::Log_HrMsg(
              retaddr,
              (void *)0x954,
              (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
              "RestoreDumpSettings",
              phkResult,
              (int)"RestoreDumpSettings: Restoring CrashDumpEnabled to %u",
              v24);
            v2 = CRegSetting::Save((CRegSetting *)v27, v7, &v25, v8, phkResultb);
            if ( v2 < 0 )
            {
              v3 = "Failed to save the settings";
              v4 = 2396;
              goto LABEL_3;
            }
            v2 = WerpReinitializeKernelCrashDump();
            if ( (unsigned int)dword_14002C000 > 5
              && (qword_14002C010 & 0x400000000000LL) != 0
              && (qword_14002C018 & 0x400000000000LL) == qword_14002C018 )
            {
              v39 = (int)v25;
              v38 = v2;
              v51 = &v38;
              v40 = v6;
              v49 = L"Restore";
              v41 = 0x1000000;
              v47 = &v39;
              v45 = &v40;
              v43 = &v41;
              v52 = 4;
              v50 = 16;
              v48 = 4;
              v46 = 4;
              v44 = 8;
              tlgWriteTransfer_EventWriteTransfer(&dword_14002C000, &unk_140025DC3, 0, 0, 7, v42);
            }
            if ( v2 < 0 )
            {
              v3 = "Failed to reinitialize crashdump.";
              v4 = 2412;
              goto LABEL_3;
            }
          }
        }
LABEL_47:
        v2 = 0;
        goto LABEL_48;
      }
      if ( v28 == 1 )
      {
        v0 = wcstol(String, 0, 10);
        goto LABEL_11;
      }
    }
    v0 = v37;
    goto LABEL_11;
  }
  v3 = "Initialize failed for CRASH_DUMP_ENABLED_NEW";
  v4 = 2286;
LABEL_3:
  LODWORD(phkResult) = v2;
  wil::details::in1diag4::Log_HrMsg(
    retaddr,
    (void *)v4,
    (unsigned int)"onecore\\windows\\feedback\\core\\wermgr\\lib\\wermgr.cpp",
    "RestoreDumpSettings",
    phkResult,
    (int)v3,
    v24);
LABEL_48:
  v9 = &off_14002C190;
  while ( 1 )
  {
    v10 = (unsigned __int64)v9[1];
    if ( v10 <= 0x40 )
      break;
LABEL_68:
    v9 += 3;
    if ( v9 == (wchar_t **)&std::bad_array_new_length `RTTI Type Descriptor' )
      goto LABEL_69;
  }
  v11 = (void **)*v9;
  if ( *v9 != L"HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Control\\CrashControl" )
  {
    v12 = 0;
    if ( v10 )
    {
      do
      {
        v13 = aHkeyLocalMachi_0[v12];
        v14 = *((unsigned __int16 *)v11 + v12);
        v15 = v13 - 32;
        if ( (unsigned int)(v13 - 97) >= 0x1A )
          v15 = aHkeyLocalMachi_0[v12];
        v16 = v14 - 32;
        if ( (unsigned int)(v14 - 97) >= 0x1A )
          v16 = *((unsigned __int16 *)v11 + v12);
        if ( v16 != v15 )
          goto LABEL_68;
      }
      while ( ++v12 != v10 );
    }
  }
  v17 = (HKEY)v9[2];
  if ( v17 )
  {
    v18 = wcschr(L"HKEY_LOCAL_MACHINE\\System\\CurrentControlSet\\Control\\CrashControl", 0x5Cu);
    phkResulta = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    v19 = v18 + 1;
    if ( !v18 )
      v19 = 0;
    if ( !RegOpenKeyExW(v17, v19, 0, 2u, phkResulta) )
    {
      if ( v0 )
        RegDeleteValueW(hKey, L"CrashDumpEnabled.New");
      if ( (_DWORD)v25 )
        RegDeleteValueW(hKey, L"CrashDumpEnabled.Old");
      if ( v1 )
        RegDeleteValueW(hKey, L"CrashDumpEnabled.Time");
    }
    goto LABEL_72;
  }
LABEL_69:
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_4a1f9762a44538069b93a1cd96af1873_Traceguids, 2147500037LL);
LABEL_72:
  if ( hKey )
    RegCloseKey(hKey);
  if ( v34 != v36 )
    operator delete(v34, (const struct std::nothrow_t *)&std::nothrow);
  if ( v31 != v33 )
    operator delete(v31, (const struct std::nothrow_t *)&std::nothrow);
  if ( String != (wchar_t *)-1LL )
  {
    si128.m128i_i64[0] = (__int64)String;
    operator delete(String, (const struct std::nothrow_t *)&std::nothrow);
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x14000964c  push    rbp
0x14000964e  push    rbx
0x14000964f  push    rsi
0x140009650  push    rdi
0x140009651  push    r12
0x140009653  push    r13
0x140009655  push    r14
0x140009657  push    r15
0x140009659  lea     rbp, [rsp-68h]
0x14000965e  sub     rsp, 168h
0x140009665  mov     rax, cs:__security_cookie
0x14000966c  xor     rax, rsp
0x14000966f  mov     [rbp+0A0h+var_50], rax
0x140009673  movdqa  xmm0, cs:__xmm@ffffffffffffffffffffffffffffffff
0x14000967b  lea     rax, [rbp+0A0h+var_120]
0x14000967f  xor     r12d, r12d
0x140009682  mov     [rsp+1A0h+var_130], rax
0x140009687  lea     rax, [rbp+0A0h+var_120]
0x14000968b  mov     [rsp+1A0h+var_150], r12w
0x140009691  mov     [rsp+1A0h+var_128], rax
0x140009696  lea     rsi, aSystemCurrentc_0; "System\\CurrentControlSet\\Control\\Cra"...
0x14000969d  lea     rax, [rbp+0A0h+var_100]
0x1400096a1  mov     [rsp+1A0h+var_14C], r12d
0x1400096a6  mov     [rbp+0A0h+var_110], rax
0x1400096aa  lea     r9, aCrashdumpenabl_0; "CrashDumpEnabled.New"
0x1400096b1  lea     rax, [rbp+0A0h+var_100]
0x1400096b5  mov     [rsp+1A0h+String], 0FFFFFFFFFFFFFFFFh
0x1400096be  mov     r8, rsi
0x1400096c1  mov     [rbp+0A0h+var_108], rax
0x1400096c5  xor     edx, edx
0x1400096c7  movdqa  [rsp+1A0h+var_140], xmm0
0x1400096cd  lea     rcx, [rsp+1A0h+var_150]
0x1400096d2  mov     [rbp+0A0h+var_120], r12w
0x1400096d7  mov     [rbp+0A0h+var_100], r12w
0x1400096dc  mov     r14d, r12d
0x1400096df  mov     [rbp+0A0h+var_F0], r12
0x1400096e3  mov     r15d, r12d
0x1400096e6  mov     dword ptr [rsp+1A0h+var_160], r12d
0x1400096eb  mov     [rsp+1A0h+hKey], r12
0x1400096f0  mov     [rsp+1A0h+phkResult], r12
0x1400096f5  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x1400096fa  lea     r13d, [r12+0Ah]
0x1400096ff  mov     edi, eax
0x140009701  test    eax, eax
0x140009703  jns     short loc_140009739
0x140009705  lea     rax, aInitializeFail_2; "Initialize failed for CRASH_DUMP_ENABLE"...
0x14000970c  mov     edx, 8EEh; void *
0x140009711  mov     rcx, [rbp+0A8h]; this
0x140009718  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x14000971f  mov     qword ptr [rsp+1A0h+var_178], rax; int
0x140009724  lea     r9, aRestoredumpset_0; "RestoreDumpSettings"
0x14000972b  mov     dword ptr [rsp+1A0h+phkResult], edi; wil::details *
0x14000972f  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140009734  jmp     loc_140009A6C
0x140009739  mov     rbx, 0FFFFFFFF80000002h
0x140009740  lea     rcx, [rsp+1A0h+var_150]; this
0x140009745  mov     rdx, rbx; HKEY
0x140009748  xor     r8d, r8d; unsigned int
0x14000974b  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140009750  test    eax, eax
0x140009752  js      loc_140009A69
0x140009758  cmp     byte ptr [rsp+1A0h+var_150], r12b
0x14000975d  jz      short loc_14000978B
0x14000975f  mov     eax, [rsp+1A0h+var_14C]
0x140009763  test    eax, eax
0x140009765  jnz     short loc_140009771
0x140009767  mov     rax, [rsp+1A0h+String]
0x14000976c  mov     r14d, [rax]
0x14000976f  jmp     short loc_14000978F
0x140009771  cmp     eax, 1
0x140009774  jnz     short loc_14000978B
0x140009776  mov     rcx, [rsp+1A0h+String]; String
0x14000977b  mov     r8d, r13d; Radix
0x14000977e  xor     edx, edx; EndPtr
0x140009780  call    cs:__imp_wcstol
0x140009786  mov     r14d, eax
0x140009789  jmp     short loc_14000978F
0x14000978b  mov     r14d, dword ptr [rbp+0A0h+var_F0]
0x14000978f  lea     r9, aCrashdumpenabl_2; "CrashDumpEnabled.Old"
0x140009796  mov     [rsp+1A0h+phkResult], r12
0x14000979b  mov     r8, rsi
0x14000979e  lea     rcx, [rsp+1A0h+var_150]
0x1400097a3  xor     edx, edx
0x1400097a5  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x1400097aa  mov     edi, eax
0x1400097ac  test    eax, eax
0x1400097ae  jns     short loc_1400097C1
0x1400097b0  lea     rax, aInitializeFail; "Initialize failed for CRASH_DUMP_ENABLE"...
0x1400097b7  mov     edx, 907h
0x1400097bc  jmp     loc_140009711
0x1400097c1  xor     r8d, r8d; unsigned int
0x1400097c4  lea     rcx, [rsp+1A0h+var_150]; this
0x1400097c9  mov     rdx, rbx; HKEY
0x1400097cc  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400097d1  test    eax, eax
0x1400097d3  js      loc_140009A69
0x1400097d9  cmp     byte ptr [rsp+1A0h+var_150], r12b
0x1400097de  jz      short loc_140009808
0x1400097e0  mov     eax, [rsp+1A0h+var_14C]
0x1400097e4  test    eax, eax
0x1400097e6  jnz     short loc_1400097F1
0x1400097e8  mov     rax, [rsp+1A0h+String]
0x1400097ed  mov     eax, [rax]
0x1400097ef  jmp     short loc_14000980B
0x1400097f1  cmp     eax, 1
0x1400097f4  jnz     short loc_140009808
0x1400097f6  mov     rcx, [rsp+1A0h+String]; String
0x1400097fb  mov     r8d, r13d; Radix
0x1400097fe  xor     edx, edx; EndPtr
0x140009800  call    cs:__imp_wcstol
0x140009806  jmp     short loc_14000980B
0x140009808  mov     eax, dword ptr [rbp+0A0h+var_F0]
0x14000980b  mov     r13d, 7
0x140009811  mov     dword ptr [rsp+1A0h+var_160], eax
0x140009815  mov     edx, r13d
0x140009818  mov     [rsp+1A0h+phkResult], r12
0x14000981d  lea     r9, aCrashdumpenabl_1; "CrashDumpEnabled.Time"
0x140009824  mov     r8, rsi
0x140009827  lea     rcx, [rsp+1A0h+var_150]
0x14000982c  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x140009831  mov     edi, eax
0x140009833  test    eax, eax
0x140009835  jns     short loc_140009848
0x140009837  lea     rax, aInitializeFail_1; "Initialize failed for CRASH_DUMP_ENABLE"...
0x14000983e  mov     edx, 921h
0x140009843  jmp     loc_140009711
0x140009848  xor     r8d, r8d; unsigned int
0x14000984b  lea     rcx, [rsp+1A0h+var_150]; this
0x140009850  mov     rdx, rbx; HKEY
0x140009853  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x140009858  test    eax, eax
0x14000985a  js      short loc_140009895
0x14000985c  cmp     byte ptr [rsp+1A0h+var_150], r12b
0x140009861  jz      short loc_140009891
0x140009863  cmp     [rsp+1A0h+var_14C], r13d
0x140009868  jnz     short loc_140009874
0x14000986a  mov     rax, [rsp+1A0h+String]
0x14000986f  mov     r15, [rax]
0x140009872  jmp     short loc_140009895
0x140009874  cmp     [rsp+1A0h+var_14C], 1
0x140009879  jnz     short loc_140009891
0x14000987b  mov     rcx, [rsp+1A0h+String]; String
0x140009880  xor     edx, edx; EndPtr
0x140009882  lea     r8d, [rdx+0Ah]; Radix
0x140009886  call    cs:__imp__wcstoi64
0x14000988c  mov     r15, rax
0x14000988f  jmp     short loc_140009895
0x140009891  mov     r15, [rbp+0A0h+var_F0]
0x140009895  lea     r9, aCrashdumpenabl; "CrashDumpEnabled"
0x14000989c  mov     [rsp+1A0h+phkResult], r12
0x1400098a1  mov     r8, rsi
0x1400098a4  lea     rcx, [rsp+1A0h+var_150]
0x1400098a9  xor     edx, edx
0x1400098ab  call    ?Initialize@CRegSetting@@QEAAJW4_DataType@@PEB_W1_K@Z; CRegSetting::Initialize(_DataType,wchar_t const *,wchar_t const *,unsigned __int64)
0x1400098b0  mov     edi, eax
0x1400098b2  test    eax, eax
0x1400098b4  jns     short loc_1400098C7
0x1400098b6  lea     rax, aInitializeFail_0; "Initialize failed for CRASH_CONTROL_KEY"...
0x1400098bd  mov     edx, 93Ch
0x1400098c2  jmp     loc_140009711
0x1400098c7  xor     r8d, r8d; unsigned int
0x1400098ca  lea     rcx, [rsp+1A0h+var_150]; this
0x1400098cf  mov     rdx, rbx; HKEY
0x1400098d2  call    ?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z; CRegSetting::Load(HKEY__ *,ulong)
0x1400098d7  test    eax, eax
0x1400098d9  js      loc_140009A69
0x1400098df  cmp     byte ptr [rsp+1A0h+var_150], r12b
0x1400098e4  jz      short loc_140009911
0x1400098e6  mov     eax, [rsp+1A0h+var_14C]
0x1400098ea  test    eax, eax
0x1400098ec  jnz     short loc_1400098F7
0x1400098ee  mov     rax, [rsp+1A0h+String]
0x1400098f3  mov     ebx, [rax]
0x1400098f5  jmp     short loc_140009914
0x1400098f7  cmp     eax, 1
0x1400098fa  jnz     short loc_140009911
0x1400098fc  mov     rcx, [rsp+1A0h+String]; String
0x140009901  lea     r8d, [rax+9]; Radix
0x140009905  xor     edx, edx; EndPtr
0x140009907  call    cs:__imp_wcstol
0x14000990d  mov     ebx, eax
0x14000990f  jmp     short loc_140009914
0x140009911  mov     ebx, dword ptr [rbp+0A0h+var_F0]
0x140009914  cmp     ebx, r14d
0x140009917  jnz     loc_140009A69
0x14000991d  mov     eax, dword ptr [rsp+1A0h+var_160]
0x140009921  lea     r9, aRestoredumpset_0; "RestoreDumpSettings"
0x140009928  mov     rcx, [rbp+0A8h]; this
0x14000992f  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\wermg"...
0x140009936  mov     dword ptr [rsp+1A0h+var_170], eax; char *
0x14000993a  mov     edx, 954h; void *
0x14000993f  lea     rax, aRestoredumpset; "RestoreDumpSettings: Restoring CrashDum"...
0x140009946  mov     qword ptr [rsp+1A0h+var_178], rax; int
0x14000994b  mov     dword ptr [rsp+1A0h+phkResult], 80000000h; unsigned int
0x140009953  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140009958  lea     r8, [rsp+1A0h+var_160]; void *
0x14000995d  lea     rcx, [rsp+1A0h+var_150]; this
0x140009962  call    ?Save@CRegSetting@@QEAAJPEAUHKEY__@@PEAXKK@Z; CRegSetting::Save(HKEY__ *,void *,ulong,ulong)
0x140009967  mov     edi, eax
0x140009969  test    eax, eax
0x14000996b  jns     short loc_14000997E
0x14000996d  lea     rax, aFailedToSaveTh; "Failed to save the settings"
0x140009974  mov     edx, 95Ch
0x140009979  jmp     loc_140009711
0x14000997e  call    cs:__imp_WerpReinitializeKernelCrashDump
0x140009984  mov     edi, eax
0x140009986  mov     eax, cs:dword_14002C000
0x14000998c  cmp     eax, 5
0x14000998f  jbe     loc_140009A54
0x140009995  mov     rcx, cs:qword_14002C018
0x14000999c  mov     rdx, 400000000000h
0x1400099a6  mov     rax, cs:qword_14002C010
0x1400099ad  test    rdx, rax
0x1400099b0  jz      loc_140009A54
0x1400099b6  mov     rax, rcx
0x1400099b9  and     rax, rdx
0x1400099bc  cmp     rax, rcx
0x1400099bf  jnz     loc_140009A54
0x1400099c5  mov     eax, dword ptr [rsp+1A0h+var_160]
0x1400099c9  lea     rdx, unk_140025DC3
0x1400099d0  mov     [rbp+0A0h+var_DC], eax
0x1400099d3  lea     rcx, dword_14002C000
0x1400099da  lea     rax, [rbp+0A0h+var_E0]
0x1400099de  mov     [rbp+0A0h+var_E0], edi
0x1400099e1  mov     [rbp+0A0h+var_60], rax
0x1400099e5  xor     r9d, r9d
0x1400099e8  lea     rax, aRestore; "Restore"
0x1400099ef  mov     [rbp+0A0h+var_D8], ebx
0x1400099f2  mov     [rbp+0A0h+var_70], rax
0x1400099f6  xor     r8d, r8d
0x1400099f9  lea     rax, [rbp+0A0h+var_DC]
0x1400099fd  mov     [rbp+0A0h+var_D0], 1000000h
0x140009a05  mov     [rbp+0A0h+var_80], rax
0x140009a09  lea     rax, [rbp+0A0h+var_D8]
0x140009a0d  mov     [rbp+0A0h+var_90], rax
0x140009a11  lea     rax, [rbp+0A0h+var_D0]
0x140009a15  mov     [rbp+0A0h+var_A0], rax
0x140009a19  lea     rax, [rbp+0A0h+var_C0]
0x140009a1d  mov     qword ptr [rsp+1A0h+var_178], rax
0x140009a22  mov     dword ptr [rsp+1A0h+phkResult], r13d
0x140009a27  mov     [rbp+0A0h+var_58], 4
0x140009a2f  mov     [rbp+0A0h+var_68], 10h
0x140009a37  mov     [rbp+0A0h+var_78], 4
0x140009a3f  mov     [rbp+0A0h+var_88], 4
0x140009a47  mov     [rbp+0A0h+var_98], 8
0x140009a4f  call    _tlgWriteTransfer_EventWriteTransfer
0x140009a54  test    edi, edi
0x140009a56  jns     short loc_140009A69
0x140009a58  lea     rax, aFailedToReinit; "Failed to reinitialize crashdump."
0x140009a5f  mov     edx, 96Ch
0x140009a64  jmp     loc_140009711
0x140009a69  mov     edi, r12d
0x140009a6c  lea     r9, off_14002C190; "HKCU\\"
0x140009a73  lea     r13, aHkeyLocalMachi_0; "HKEY_LOCAL_MACHINE\\System\\CurrentCont"...
0x140009a7a  mov     r11, [r9+8]
0x140009a7e  cmp     r11, 40h ; '@'
0x140009a82  ja      loc_140009B69
0x140009a88  mov     rbx, [r9]
0x140009a8b  cmp     rbx, r13
0x140009a8e  jz      short loc_140009ACE
0x140009a90  mov     r10, r12
0x140009a93  test    r11, r11
0x140009a96  jz      short loc_140009ACE
0x140009a98  movzx   ecx, word ptr [r13+r10*2+0]
0x140009a9e  movzx   r8d, word ptr [rbx+r10*2]
0x140009aa3  lea     eax, [rcx-61h]
0x140009aa6  cmp     eax, 1Ah
0x140009aa9  lea     edx, [rcx-20h]
0x140009aac  lea     eax, [r8-61h]
0x140009ab0  cmovnb  edx, ecx
0x140009ab3  cmp     eax, 1Ah
0x140009ab6  lea     ecx, [r8-20h]
0x140009aba  cmovnb  ecx, r8d
0x140009abe  cmp     ecx, edx
0x140009ac0  jnz     loc_140009B69
0x140009ac6  inc     r10
0x140009ac9  cmp     r10, r11
0x140009acc  jnz     short loc_140009A98
0x140009ace  mov     rsi, [r9+10h]
0x140009ad2  test    rsi, rsi
0x140009ad5  jz      loc_140009B7D
0x140009adb  mov     edx, 5Ch ; '\'; Ch
0x140009ae0  mov     rcx, r13; Str
0x140009ae3  call    cs:__imp_wcschr
0x140009ae9  lea     rcx, [rsp+1A0h+hKey]
0x140009aee  mov     rbx, rax
0x140009af1  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x140009af6  test    rbx, rbx
0x140009af9  mov     [rsp+1A0h+phkResult], rax; phkResult
0x140009afe  lea     rdx, [rbx+2]
0x140009b02  mov     r9d, 2; samDesired
0x140009b08  cmovz   rdx, rbx; lpSubKey
0x140009b0c  mov     rcx, rsi; hKey
0x140009b0f  xor     r8d, r8d; ulOptions
0x140009b12  call    cs:__imp_RegOpenKeyExW
0x140009b18  test    eax, eax
0x140009b1a  jnz     loc_140009BB1
0x140009b20  test    r14d, r14d
0x140009b23  jz      short loc_140009B37
0x140009b25  mov     rcx, [rsp+1A0h+hKey]; hKey
  ... truncated ...
```
