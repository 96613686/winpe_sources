# Windows::UsoProductEnumerator::TryGetPrimaryOsInfo(void)

- ea: `0x1800dbecc`
- end: `0x1800dc3c6`
- name: `?TryGetPrimaryOsInfo@UsoProductEnumerator@Windows@@QEAA?AU?$pair@V?$optional@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@V12@@std@@XZ`
- size: `1274`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18008db50`

## callees

- `0x1800108b4`
- `0x1800112d0`
- `0x180011680`
- `0x18002e064`
- `0x18002e168`
- `0x1800b0948`
- `0x1800dbecc`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc152`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc0d4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc152`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc165`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc0e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc165`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc07e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc1b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc36f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc37f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc00e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc07e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc0df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc15d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc1b6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc36f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc37f`

## string_xrefs

- `0x1800dbf27`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int128 *__fastcall Windows::UsoProductEnumerator::TryGetPrimaryOsInfo(__int64 a1)
{
  unsigned int v2; // edi
  __int64 v3; // r14
  __int64 *v4; // rcx
  __int64 v5; // rax
  int v6; // eax
  __int64 v7; // rax
  unsigned int v8; // eax
  __int64 v9; // rax
  int v10; // eax
  __int64 v11; // r8
  int v12; // ebx
  __int64 *v13; // rbx
  __int64 (__fastcall *v14)(__int64 *, LPVOID *); // r15
  void *v15; // rsi
  DWORD LastError; // edi
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  wil::details::in1diag3 *v20; // rcx
  __int64 v21; // rdx
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, LPVOID *); // r15
  void *v24; // rsi
  DWORD v25; // edi
  __int64 v26; // r8
  _BYTE *v27; // rdi
  char v28; // bl
  wchar_t *v29; // rax
  char v30; // bl
  char v31; // bl
  int v33; // [rsp+28h] [rbp-E0h]
  wchar_t String_8[8]; // [rsp+40h] [rbp-C8h] BYREF
  __int128 v35; // [rsp+50h] [rbp-B8h]
  _BYTE v36[40]; // [rsp+60h] [rbp-A8h] BYREF
  char v37; // [rsp+88h] [rbp-80h]
  _BYTE v38[32]; // [rsp+90h] [rbp-78h] BYREF
  char v39; // [rsp+B0h] [rbp-58h]
  _BYTE v40[32]; // [rsp+B8h] [rbp-50h] BYREF
  char v41; // [rsp+D8h] [rbp-30h]
  __int64 *v42; // [rsp+E0h] [rbp-28h] BYREF
  __int64 *v43; // [rsp+E8h] [rbp-20h] BYREF
  __int64 v44; // [rsp+F8h] [rbp-10h] BYREF
  LPVOID pv; // [rsp+108h] [rbp+0h] BYREF
  LPVOID v46; // [rsp+110h] [rbp+8h] BYREF
  LPVOID v47; // [rsp+118h] [rbp+10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+150h] [rbp+48h]

  v47 = 0;
  v46 = 0;
  v2 = 0;
  v3 = -1;
  if ( !*(_DWORD *)a1 )
    goto LABEL_47;
  while ( 1 )
  {
    v42 = 0;
    v4 = *(__int64 **)(a1 + 24);
    v5 = *v4;
    v42 = 0;
    v6 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 **))(v5 + 32))(v4, v2, &v42);
    if ( v6 >= 0 )
      break;
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x75,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v6,
      v33);
LABEL_21:
    if ( v42 )
      (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
    if ( ++v2 >= *(_DWORD *)a1 )
      goto LABEL_43;
  }
  v43 = 0;
  v7 = *v42;
  v43 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 **))(v7 + 40))(v42, L"PrimaryOSProduct", &v43);
  if ( (int)wil::details::in1diag3::Log_IfFailedWithExpected(
              retaddr,
              (void *)0x7C,
              (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
              (const char *)v8,
              1,
              2) < 0 )
  {
    if ( v43 )
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    goto LABEL_21;
  }
  pv = 0;
  v9 = *v43;
  pv = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v9 + 32))(v43, &pv);
  if ( v10 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x82,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v10,
      v33);
    if ( pv )
      CoTaskMemFree(pv);
    if ( v43 )
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    goto LABEL_21;
  }
  *(_OWORD *)String_8 = 0;
  v35 = 0;
  v11 = -1;
  do
    ++v11;
  while ( *((_WORD *)pv + v11) );
  std::wstring::_Construct<1,wchar_t const *>(String_8, pv, v11);
  v12 = std::stoi(String_8);
  std::wstring::~wstring(String_8);
  if ( v12 != 1 )
  {
    if ( pv )
      CoTaskMemFree(pv);
    if ( v43 )
      (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
    goto LABEL_21;
  }
  v13 = v42;
  v14 = *(__int64 (__fastcall **)(__int64 *, LPVOID *))(*v42 + 24);
  v15 = v47;
  if ( v47 )
  {
    LastError = GetLastError();
    CoTaskMemFree(v15);
    SetLastError(LastError);
  }
  v47 = 0;
  v17 = v14(v13, &v47);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v17,
      v33);
  v44 = 0;
  v18 = *v42;
  v44 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64 *, const wchar_t *, __int64 *))(v18 + 40))(v42, L"Version", &v44);
  v20 = retaddr;
  if ( v19 < 0 )
  {
    v21 = 140;
    goto LABEL_34;
  }
  v22 = v44;
  v23 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v44 + 32LL);
  v24 = v46;
  if ( v46 )
  {
    v25 = GetLastError();
    CoTaskMemFree(v24);
    SetLastError(v25);
  }
  v46 = 0;
  v19 = v23(v22, &v46);
  v20 = retaddr;
  if ( v19 < 0 )
  {
    v21 = 142;
LABEL_34:
    wil::details::in1diag3::_Log_Hr(
      v20,
      (void *)v21,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
      (const char *)(unsigned int)v19,
      v33);
  }
  if ( v44 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v44 + 16LL))(v44);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v43 )
    (*(void (__fastcall **)(__int64 *))(*v43 + 16))(v43);
  if ( v42 )
    (*(void (__fastcall **)(__int64 *))(*v42 + 16))(v42);
LABEL_43:
  if ( v47 )
  {
    memset(&v36[8], 0, 32);
    v26 = -1;
    do
      ++v26;
    while ( *((_WORD *)v47 + v26) );
    std::wstring::_Construct<1,wchar_t const *>(&v36[8], v47, v26);
    v37 = 1;
    v27 = &v36[8];
    v28 = 65;
    goto LABEL_48;
  }
LABEL_47:
  v41 = 0;
  v27 = v40;
  v28 = 2;
LABEL_48:
  if ( v46 )
  {
    *(_OWORD *)String_8 = 0;
    v35 = 0;
    do
      ++v3;
    while ( *((_WORD *)v46 + v3) );
    std::wstring::_Construct<1,wchar_t const *>(String_8, v46, v3);
    v36[0] = 1;
    v29 = String_8;
    v30 = v28 | 0x24;
  }
  else
  {
    v39 = 0;
    v29 = (wchar_t *)v38;
    v30 = v28 | 8;
  }
  byte_180150E90 = 0;
  if ( v27[32] )
  {
    xmmword_180150E70 = *(_OWORD *)v27;
    xmmword_180150E80 = *((_OWORD *)v27 + 1);
    *(_WORD *)v27 = 0;
    *((_QWORD *)v27 + 2) = 0;
    *((_QWORD *)v27 + 3) = 7;
    byte_180150E90 = 1;
  }
  byte_180150EB8 = 0;
  if ( *((_BYTE *)v29 + 32) )
  {
    xmmword_180150E98 = *(_OWORD *)v29;
    xmmword_180150EA8 = *((_OWORD *)v29 + 1);
    *v29 = 0;
    *((_QWORD *)v29 + 2) = 0;
    *((_QWORD *)v29 + 3) = 7;
    byte_180150EB8 = 1;
  }
  v31 = v30 | 0x10;
  if ( (v31 & 8) != 0 )
  {
    v31 &= ~8u;
    if ( v39 )
      std::wstring::~wstring(v38);
  }
  if ( (v31 & 4) != 0 )
  {
    v31 &= ~4u;
    if ( v36[0] )
      std::wstring::~wstring(String_8);
  }
  if ( (v31 & 2) != 0 )
  {
    v31 &= ~2u;
    if ( v41 )
      std::wstring::~wstring(v40);
  }
  if ( (v31 & 1) != 0 && v37 )
    std::wstring::~wstring(&v36[8]);
  if ( v46 )
    CoTaskMemFree(v46);
  if ( v47 )
    CoTaskMemFree(v47);
  return &xmmword_180150E70;
}

```

## disassembly

```asm
0x1800dbecc  mov     rax, rsp
0x1800dbecf  mov     [rax+10h], rbx
0x1800dbed3  mov     [rax+18h], rsi
0x1800dbed7  mov     [rax+20h], rdi
0x1800dbedb  push    rbp
0x1800dbedc  push    r12
0x1800dbede  push    r13
0x1800dbee0  push    r14
0x1800dbee2  push    r15
0x1800dbee4  lea     rbp, [rax-48h]
0x1800dbee8  sub     rsp, 120h
0x1800dbeef  mov     rax, cs:__security_cookie
0x1800dbef6  xor     rax, rsp
0x1800dbef9  mov     [rbp+40h+var_28], rax
0x1800dbefd  mov     rsi, rcx
0x1800dbf00  xor     r12d, r12d
0x1800dbf03  mov     dword ptr [rsp+140h+String], r12d
0x1800dbf08  lea     r15, xmmword_180150E70
0x1800dbf0f  mov     [rbp+40h+var_30], r12
0x1800dbf13  mov     [rbp+40h+var_38], r12
0x1800dbf17  mov     edi, r12d
0x1800dbf1a  or      r14, 0FFFFFFFFFFFFFFFFh
0x1800dbf1e  cmp     [rcx], r12d
0x1800dbf21  jbe     loc_1800DC235
0x1800dbf27  lea     r13, aCW1SSrcOrchest_37; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1800dbf2e  mov     [rbp+40h+var_68], r12
0x1800dbf32  mov     rcx, [rsi+18h]
0x1800dbf36  mov     rax, [rcx]
0x1800dbf39  mov     [rbp+40h+var_68], r12
0x1800dbf3d  lea     r8, [rbp+40h+var_68]
0x1800dbf41  mov     edx, edi
0x1800dbf43  mov     rax, [rax+20h]
0x1800dbf47  call    _guard_dispatch_icall
0x1800dbf4c  mov     rcx, [rbp+48h]; this
0x1800dbf50  test    eax, eax
0x1800dbf52  jns     short loc_1800DBF6A
0x1800dbf54  mov     r9d, eax; char *
0x1800dbf57  mov     r8, r13; unsigned int
0x1800dbf5a  mov     edx, 75h ; 'u'; void *
0x1800dbf5f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dbf64  nop
0x1800dbf65  jmp     loc_1800DC09B
0x1800dbf6a  mov     [rbp+40h+var_60], r12
0x1800dbf6e  mov     rcx, [rbp+40h+var_68]
0x1800dbf72  mov     rax, [rcx]
0x1800dbf75  mov     [rbp+40h+var_60], r12
0x1800dbf79  lea     r8, [rbp+40h+var_60]
0x1800dbf7d  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x1800dbf84  mov     rax, [rax+28h]
0x1800dbf88  call    _guard_dispatch_icall
0x1800dbf8d  mov     rcx, [rbp+48h]; this
0x1800dbf91  mov     dword ptr [rsp+140h+var_118], 80070002h; char
0x1800dbf99  mov     [rsp+140h+var_120], 1; int
0x1800dbfa1  mov     r9d, eax; char *
0x1800dbfa4  mov     r8, r13; unsigned int
0x1800dbfa7  mov     edx, 7Ch ; '|'; void *
0x1800dbfac  call    ?Log_IfFailedWithExpected@in1diag3@details@wil@@YAJPEAXIPEBDJIZZ; wil::details::in1diag3::Log_IfFailedWithExpected(void *,uint,char const *,long,uint,...)
0x1800dbfb1  test    eax, eax
0x1800dbfb3  jns     short loc_1800DBFD0
0x1800dbfb5  mov     rcx, [rbp+40h+var_60]
0x1800dbfb9  test    rcx, rcx
0x1800dbfbc  jz      short loc_1800DBFCB
0x1800dbfbe  mov     rax, [rcx]
0x1800dbfc1  mov     rax, [rax+10h]
0x1800dbfc5  call    _guard_dispatch_icall
0x1800dbfca  nop
0x1800dbfcb  jmp     loc_1800DC09B
0x1800dbfd0  mov     [rbp+40h+pv], r12
0x1800dbfd4  mov     rcx, [rbp+40h+var_60]
0x1800dbfd8  mov     rax, [rcx]
0x1800dbfdb  mov     [rbp+40h+pv], r12
0x1800dbfdf  lea     rdx, [rbp+40h+pv]
0x1800dbfe3  mov     rax, [rax+20h]
0x1800dbfe7  call    _guard_dispatch_icall
0x1800dbfec  mov     rcx, [rbp+48h]; this
0x1800dbff0  test    eax, eax
0x1800dbff2  jns     short loc_1800DC02D
0x1800dbff4  mov     r9d, eax; char *
0x1800dbff7  mov     r8, r13; unsigned int
0x1800dbffa  mov     edx, 82h; void *
0x1800dbfff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dc004  nop
0x1800dc005  mov     rcx, [rbp+40h+pv]; pv
0x1800dc009  test    rcx, rcx
0x1800dc00c  jz      short loc_1800DC015
0x1800dc00e  call    cs:__imp_CoTaskMemFree
0x1800dc014  nop
0x1800dc015  mov     rcx, [rbp+40h+var_60]
0x1800dc019  test    rcx, rcx
0x1800dc01c  jz      short loc_1800DC02B
0x1800dc01e  mov     rax, [rcx]
0x1800dc021  mov     rax, [rax+10h]
0x1800dc025  call    _guard_dispatch_icall
0x1800dc02a  nop
0x1800dc02b  jmp     short loc_1800DC09B
0x1800dc02d  xorps   xmm0, xmm0
0x1800dc030  movups  xmmword ptr [rsp+140h+String+8], xmm0
0x1800dc035  xorps   xmm1, xmm1
0x1800dc038  movdqu  xmmword ptr [rsp+140h+var_100+8], xmm1
0x1800dc03e  mov     rdx, [rbp+40h+pv]
0x1800dc042  mov     r8, r14
0x1800dc045  inc     r8
0x1800dc048  cmp     [rdx+r8*2], r12w
0x1800dc04d  jnz     short loc_1800DC045
0x1800dc04f  lea     rcx, [rsp+140h+String+8]
0x1800dc054  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dc059  nop
0x1800dc05a  lea     rcx, [rsp+140h+String+8]; String
0x1800dc05f  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x1800dc064  mov     ebx, eax
0x1800dc066  lea     rcx, [rsp+140h+String+8]; void *
0x1800dc06b  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dc070  cmp     ebx, 1
0x1800dc073  jz      short loc_1800DC0C0
0x1800dc075  mov     rcx, [rbp+40h+pv]; pv
0x1800dc079  test    rcx, rcx
0x1800dc07c  jz      short loc_1800DC085
0x1800dc07e  call    cs:__imp_CoTaskMemFree
0x1800dc084  nop
0x1800dc085  mov     rcx, [rbp+40h+var_60]
0x1800dc089  test    rcx, rcx
0x1800dc08c  jz      short loc_1800DC09B
0x1800dc08e  mov     rax, [rcx]
0x1800dc091  mov     rax, [rax+10h]
0x1800dc095  call    _guard_dispatch_icall
0x1800dc09a  nop
0x1800dc09b  mov     rcx, [rbp+40h+var_68]
0x1800dc09f  test    rcx, rcx
0x1800dc0a2  jz      short loc_1800DC0B1
0x1800dc0a4  mov     rax, [rcx]
0x1800dc0a7  mov     rax, [rax+10h]
0x1800dc0ab  call    _guard_dispatch_icall
0x1800dc0b0  nop
0x1800dc0b1  inc     edi
0x1800dc0b3  cmp     edi, [rsi]
0x1800dc0b5  jb      loc_1800DBF2E
0x1800dc0bb  jmp     loc_1800DC1F0
0x1800dc0c0  mov     rbx, [rbp+40h+var_68]
0x1800dc0c4  mov     rax, [rbx]
0x1800dc0c7  mov     r15, [rax+18h]
0x1800dc0cb  mov     rsi, [rbp+40h+var_30]
0x1800dc0cf  test    rsi, rsi
0x1800dc0d2  jz      short loc_1800DC0ED
0x1800dc0d4  call    cs:__imp_GetLastError
0x1800dc0da  mov     edi, eax
0x1800dc0dc  mov     rcx, rsi; pv
0x1800dc0df  call    cs:__imp_CoTaskMemFree
0x1800dc0e5  mov     ecx, edi; dwErrCode
0x1800dc0e7  call    cs:__imp_SetLastError
0x1800dc0ed  mov     [rbp+40h+var_30], r12
0x1800dc0f1  lea     rdx, [rbp+40h+var_30]
0x1800dc0f5  mov     rcx, rbx
0x1800dc0f8  mov     rax, r15
0x1800dc0fb  call    _guard_dispatch_icall
0x1800dc100  mov     rcx, [rbp+48h]; this
0x1800dc104  test    eax, eax
0x1800dc106  js      loc_1800DC3B5
0x1800dc10c  mov     [rbp+40h+var_50], r12
0x1800dc110  mov     rcx, [rbp+40h+var_68]
0x1800dc114  mov     rax, [rcx]
0x1800dc117  mov     [rbp+40h+var_50], r12
0x1800dc11b  lea     r8, [rbp+40h+var_50]
0x1800dc11f  lea     rdx, aVersion_0; "Version"
0x1800dc126  mov     rax, [rax+28h]
0x1800dc12a  call    _guard_dispatch_icall
0x1800dc12f  mov     rcx, [rbp+48h]
0x1800dc133  test    eax, eax
0x1800dc135  jns     short loc_1800DC13E
0x1800dc137  mov     edx, 8Ch
0x1800dc13c  jmp     short loc_1800DC18B
0x1800dc13e  mov     rbx, [rbp+40h+var_50]
0x1800dc142  mov     rax, [rbx]
0x1800dc145  mov     r15, [rax+20h]
0x1800dc149  mov     rsi, [rbp+40h+var_38]
0x1800dc14d  test    rsi, rsi
0x1800dc150  jz      short loc_1800DC16B
0x1800dc152  call    cs:__imp_GetLastError
0x1800dc158  mov     edi, eax
0x1800dc15a  mov     rcx, rsi; pv
0x1800dc15d  call    cs:__imp_CoTaskMemFree
0x1800dc163  mov     ecx, edi; dwErrCode
0x1800dc165  call    cs:__imp_SetLastError
0x1800dc16b  mov     [rbp+40h+var_38], r12
0x1800dc16f  lea     rdx, [rbp+40h+var_38]
0x1800dc173  mov     rcx, rbx
0x1800dc176  mov     rax, r15
0x1800dc179  call    _guard_dispatch_icall
0x1800dc17e  mov     rcx, [rbp+48h]; this
0x1800dc182  test    eax, eax
0x1800dc184  jns     short loc_1800DC197
0x1800dc186  mov     edx, 8Eh; void *
0x1800dc18b  mov     r9d, eax; char *
0x1800dc18e  mov     r8, r13; unsigned int
0x1800dc191  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800dc196  nop
0x1800dc197  mov     rcx, [rbp+40h+var_50]
0x1800dc19b  test    rcx, rcx
0x1800dc19e  jz      short loc_1800DC1AD
0x1800dc1a0  mov     rax, [rcx]
0x1800dc1a3  mov     rax, [rax+10h]
0x1800dc1a7  call    _guard_dispatch_icall
0x1800dc1ac  nop
0x1800dc1ad  mov     rcx, [rbp+40h+pv]; pv
0x1800dc1b1  test    rcx, rcx
0x1800dc1b4  jz      short loc_1800DC1BD
0x1800dc1b6  call    cs:__imp_CoTaskMemFree
0x1800dc1bc  nop
0x1800dc1bd  mov     rcx, [rbp+40h+var_60]
0x1800dc1c1  test    rcx, rcx
0x1800dc1c4  jz      short loc_1800DC1D3
0x1800dc1c6  mov     rax, [rcx]
0x1800dc1c9  mov     rax, [rax+10h]
0x1800dc1cd  call    _guard_dispatch_icall
0x1800dc1d2  nop
0x1800dc1d3  mov     rcx, [rbp+40h+var_68]
0x1800dc1d7  test    rcx, rcx
0x1800dc1da  jz      short loc_1800DC1E9
0x1800dc1dc  mov     rax, [rcx]
0x1800dc1df  mov     rax, [rax+10h]
0x1800dc1e3  call    _guard_dispatch_icall
0x1800dc1e8  nop
0x1800dc1e9  lea     r15, xmmword_180150E70
0x1800dc1f0  mov     rcx, [rbp+40h+var_30]
0x1800dc1f4  test    rcx, rcx
0x1800dc1f7  jz      short loc_1800DC235
0x1800dc1f9  xorps   xmm0, xmm0
0x1800dc1fc  movups  [rsp+140h+var_E8+8], xmm0
0x1800dc201  xorps   xmm1, xmm1
0x1800dc204  movdqu  [rsp+140h+var_D8+8], xmm1
0x1800dc20a  mov     r8, r14
0x1800dc20d  inc     r8
0x1800dc210  cmp     [rcx+r8*2], r12w
0x1800dc215  jnz     short loc_1800DC20D
0x1800dc217  mov     rdx, [rbp+40h+var_30]
0x1800dc21b  lea     rcx, [rsp+140h+var_E8+8]
0x1800dc220  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dc225  mov     [rbp+40h+var_C0], 1
0x1800dc229  lea     rdi, [rsp+140h+var_E8+8]
0x1800dc22e  mov     ebx, 41h ; 'A'
0x1800dc233  jmp     short loc_1800DC242
0x1800dc235  mov     [rbp+40h+var_70], r12b
0x1800dc239  lea     rdi, [rbp+40h+var_90]
0x1800dc23d  mov     ebx, 2
0x1800dc242  mov     dword ptr [rsp+140h+String], ebx
0x1800dc246  mov     rcx, [rbp+40h+var_38]
0x1800dc24a  test    rcx, rcx
0x1800dc24d  jz      short loc_1800DC28A
0x1800dc24f  xorps   xmm0, xmm0
0x1800dc252  movups  xmmword ptr [rsp+140h+String+8], xmm0
0x1800dc257  xorps   xmm1, xmm1
0x1800dc25a  movdqu  xmmword ptr [rsp+140h+var_100+8], xmm1
0x1800dc260  inc     r14
0x1800dc263  cmp     [rcx+r14*2], r12w
0x1800dc268  jnz     short loc_1800DC260
0x1800dc26a  mov     r8, r14
0x1800dc26d  mov     rdx, [rbp+40h+var_38]
0x1800dc271  lea     rcx, [rsp+140h+String+8]
0x1800dc276  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dc27b  mov     byte ptr [rsp+140h+var_E8], 1
0x1800dc280  lea     rax, [rsp+140h+String+8]
0x1800dc285  or      ebx, 24h
0x1800dc288  jmp     short loc_1800DC295
0x1800dc28a  mov     [rbp+40h+var_98], r12b
0x1800dc28e  lea     rax, [rbp+40h+var_B8]
0x1800dc292  or      ebx, 8
0x1800dc295  mov     cs:byte_180150E90, r12b
0x1800dc29c  mov     ecx, 7
0x1800dc2a1  cmp     [rdi+20h], r12b
0x1800dc2a5  jz      short loc_1800DC2CF
0x1800dc2a7  movups  xmm1, xmmword ptr [rdi]
0x1800dc2aa  movaps  cs:xmmword_180150E70, xmm1
0x1800dc2b1  movups  xmm0, xmmword ptr [rdi+10h]
0x1800dc2b5  movaps  cs:xmmword_180150E80, xmm0
0x1800dc2bc  mov     [rdi], r12w
0x1800dc2c0  mov     [rdi+10h], r12
0x1800dc2c4  mov     [rdi+18h], rcx
0x1800dc2c8  mov     cs:byte_180150E90, 1
0x1800dc2cf  mov     cs:byte_180150EB8, r12b
0x1800dc2d6  cmp     [rax+20h], r12b
0x1800dc2da  jz      short loc_1800DC304
0x1800dc2dc  movups  xmm1, xmmword ptr [rax]
0x1800dc2df  movups  cs:xmmword_180150E98, xmm1
0x1800dc2e6  movups  xmm0, xmmword ptr [rax+10h]
0x1800dc2ea  movups  cs:xmmword_180150EA8, xmm0
0x1800dc2f1  mov     [rax], r12w
0x1800dc2f5  mov     [rax+10h], r12
0x1800dc2f9  mov     [rax+18h], rcx
0x1800dc2fd  mov     cs:byte_180150EB8, 1
0x1800dc304  or      ebx, 10h
0x1800dc307  test    bl, 8
0x1800dc30a  jz      short loc_1800DC31E
0x1800dc30c  and     ebx, 0FFFFFFF7h
0x1800dc30f  cmp     [rbp+40h+var_98], r12b
0x1800dc313  jz      short loc_1800DC31E
0x1800dc315  lea     rcx, [rbp+40h+var_B8]; void *
0x1800dc319  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dc31e  test    bl, 4
0x1800dc321  jz      short loc_1800DC338
0x1800dc323  and     ebx, 0FFFFFFFBh
0x1800dc326  cmp     byte ptr [rsp+140h+var_E8], r12b
  ... truncated ...
```
