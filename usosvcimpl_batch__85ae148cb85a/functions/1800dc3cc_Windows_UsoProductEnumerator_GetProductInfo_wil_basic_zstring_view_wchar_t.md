# Windows::UsoProductEnumerator::GetProductInfo(wil::basic_zstring_view<wchar_t>)

- ea: `0x1800dc3cc`
- end: `0x1800dccf4`
- name: `?GetProductInfo@UsoProductEnumerator@Windows@@QEAA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$basic_zstring_view@_W@wil@@@Z`
- size: `2344`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x18008ec70`

## callees

- `0x18000f3a8`
- `0x1800108b4`
- `0x1800112d0`
- `0x18001151c`
- `0x180011680`
- `0x18001171c`
- `0x18001bdc0`
- `0x18001c6b4`
- `0x18002b918`
- `0x18002e698`
- `0x18008f6cc`
- `0x1800b0948`
- `0x1800dc3cc`
- `0x1800dccfc`
- `0x1800dd930`
- `0x1800e4630`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc4fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc812`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800dc88b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc50d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc89e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc50d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc825`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800dc89e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc81d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc896`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcaec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcaff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcbe5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc505`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc5d5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc81d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dc896`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcaec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcaff`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800dcbe5`

## string_xrefs

- `0x1800dcc49`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcc5e`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcc73`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcc88`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcc9d`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dccb2`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcccd`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`
- `0x1800dcce2`: `C:\__w\1\s\src\orchestrator\system\windows\common\ProductEnumeratorHelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=31
_QWORD *__fastcall Windows::UsoProductEnumerator::GetProductInfo(_DWORD *a1, _QWORD *a2, __int64 *a3)
{
  _DWORD *v4; // rax
  int v5; // edi
  __int64 v6; // rdx
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // eax
  __int64 v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  __int64 v13; // r15
  _QWORD *v14; // rsi
  void *v15; // r14
  DWORD LastError; // ebx
  __int64 v17; // rax
  int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  __int64 v21; // rax
  __int64 v22; // rax
  int v23; // eax
  __int64 v24; // r8
  int v25; // ebx
  bool v26; // bl
  LPVOID v27; // rbx
  int v28; // edi
  unsigned int v29; // r12d
  __int64 v30; // rax
  int v31; // eax
  __int64 v32; // rcx
  __int64 v33; // rax
  int v34; // eax
  wchar_t *v35; // r15
  wchar_t *v36; // rsi
  void *v37; // r14
  DWORD v38; // ebx
  __int64 v39; // rax
  int v40; // eax
  wchar_t *v41; // r15
  wchar_t *v42; // rsi
  void *v43; // r14
  DWORD v44; // ebx
  __int64 *v45; // rsi
  __int64 v46; // r8
  const wchar_t *v47; // rcx
  char v48; // bl
  __int64 v49; // rdx
  __int64 v50; // r8
  __int64 v51; // rcx
  __int64 v52; // rcx
  __int64 v53; // rcx
  int v55; // [rsp+20h] [rbp-E0h]
  bool v56; // [rsp+40h] [rbp-C0h]
  wchar_t *S1[2]; // [rsp+48h] [rbp-B8h] BYREF
  size_t N[2]; // [rsp+58h] [rbp-A8h]
  int v59; // [rsp+68h] [rbp-98h]
  __int64 *v60; // [rsp+70h] [rbp-90h]
  _DWORD *v61; // [rsp+78h] [rbp-88h]
  _QWORD v62[2]; // [rsp+80h] [rbp-80h] BYREF
  __int128 v63; // [rsp+90h] [rbp-70h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  _QWORD *v65; // [rsp+A8h] [rbp-58h]
  _QWORD v66[4]; // [rsp+B0h] [rbp-50h] BYREF
  _QWORD v67[2]; // [rsp+D0h] [rbp-30h] BYREF
  _QWORD v68[5]; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v69[32]; // [rsp+108h] [rbp+8h] BYREF
  _BYTE v70[40]; // [rsp+128h] [rbp+28h] BYREF
  __int128 v71; // [rsp+150h] [rbp+50h] BYREF
  char v72; // [rsp+160h] [rbp+60h]
  unsigned int v73; // [rsp+170h] [rbp+70h] BYREF
  __int64 *v74; // [rsp+178h] [rbp+78h] BYREF
  __int64 *v75; // [rsp+180h] [rbp+80h] BYREF
  LPVOID v76; // [rsp+188h] [rbp+88h] BYREF
  LPVOID v77; // [rsp+190h] [rbp+90h] BYREF
  LPVOID v78; // [rsp+198h] [rbp+98h] BYREF
  LPVOID pv; // [rsp+1A0h] [rbp+A0h] BYREF
  __int64 v80[2]; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v81; // [rsp+1B8h] [rbp+B8h]
  wil::details::in1diag3 *retaddr; // [rsp+208h] [rbp+108h]

  v60 = a3;
  v4 = a1;
  v61 = a1;
  v68[4] = a2;
  *(_OWORD *)a2 = 0;
  a2[2] = 0;
  a2[3] = 7;
  *(_WORD *)a2 = 0;
  v5 = 1;
  v6 = 0;
  v59 = 0;
  if ( *a1 )
  {
    while ( 1 )
    {
      v74 = 0;
      v7 = (__int64 *)*((_QWORD *)v4 + 3);
      v8 = *v7;
      *(_QWORD *)&v71 = &v74;
      *((_QWORD *)&v71 + 1) = 0;
      v72 = 1;
      v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, char *))(v8 + 32))(v7, v6, (char *)&v71 + 8);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA3,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v9,
          v55);
      if ( v72 )
      {
        v10 = *(_QWORD *)v71;
        *(_QWORD *)v71 = *((_QWORD *)&v71 + 1);
        if ( v10 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      }
      pv = 0;
      v11 = *v74;
      *(_QWORD *)&v71 = &pv;
      *((_QWORD *)&v71 + 1) = 0;
      v72 = 1;
      v12 = (*(__int64 (__fastcall **)(__int64 *, char *))(v11 + 24))(v74, (char *)&v71 + 8);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v12,
          v55);
      if ( v72 )
      {
        v13 = *((_QWORD *)&v71 + 1);
        v14 = (_QWORD *)v71;
        v15 = *(void **)v71;
        if ( *(_QWORD *)v71 )
        {
          LastError = GetLastError();
          CoTaskMemFree(v15);
          SetLastError(LastError);
        }
        *v14 = v13;
      }
      v75 = 0;
      v17 = *v74;
      *(_QWORD *)&v71 = &v75;
      *((_QWORD *)&v71 + 1) = 0;
      v72 = 1;
      v18 = (*(__int64 (__fastcall **)(__int64 *, char *))(v17 + 32))(v74, (char *)&v71 + 8);
      if ( v18 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA9,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v18,
          v55);
      if ( v72 )
      {
        v19 = *(_QWORD *)v71;
        *(_QWORD *)v71 = *((_QWORD *)&v71 + 1);
        if ( v19 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      }
      v73 = 0;
      v20 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v75 + 24))(v75, &v73);
      if ( v20 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xAC,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v20,
          v55);
      if ( v73 )
        break;
      if ( v75 )
        (*(void (__fastcall **)(__int64 *))(*v75 + 16))(v75);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v74 )
        (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
LABEL_89:
      v6 = (unsigned int)(v59 + 1);
      v59 = v6;
      v4 = v61;
      if ( (unsigned int)v6 >= *v61 )
        return a2;
    }
    v56 = 0;
    *(_QWORD *)&v71 = 0;
    v21 = *v74;
    *(_QWORD *)&v71 = 0;
    if ( (*(int (__fastcall **)(__int64 *, const wchar_t *, __int128 *))(v21 + 40))(v74, L"PrimaryOSProduct", &v71) >= 0 )
    {
      v76 = 0;
      v22 = *(_QWORD *)v71;
      v76 = 0;
      v23 = (*(__int64 (__fastcall **)(_QWORD, LPVOID *))(v22 + 32))(v71, &v76);
      if ( v23 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB6,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v23,
          v55);
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v24 = -1;
      do
        ++v24;
      while ( *((_WORD *)v76 + v24) );
      std::wstring::_Construct<1,wchar_t const *>(S1, v76);
      v25 = std::stoi((wchar_t *)S1);
      std::wstring::~wstring(S1);
      v26 = v25 == 1;
      v56 = v26;
      if ( v76 )
      {
        CoTaskMemFree(v76);
        v56 = v26;
      }
    }
    if ( (_QWORD)v71 )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v71 + 16LL))(v71);
    v27 = pv;
    std::_Format_arg_index::_Format_arg_index((std::_Format_arg_index *)v62);
    v62[1] = v27;
    v62[0] = 0xB000000000000000uLL;
    *(_QWORD *)&v63 = L"PN={}";
    *((_QWORD *)&v63 + 1) = 5;
    v64 = 1;
    v65 = v62;
    v71 = v63;
    std::vformat<0>(v80);
    v28 = v5 | 0x20;
    v29 = 0;
    if ( !v73 )
    {
LABEL_82:
      if ( v81 == 0x7FFFFFFFFFFFFFFELL )
        std::_Xlen_string();
      std::wstring::wstring(S1, v81, L";", 1);
      v5 = v28 | 0x10;
      std::wstring::append(a2);
      std::wstring::~wstring(S1);
      std::wstring::~wstring(v80);
      if ( v75 )
        (*(void (__fastcall **)(__int64 *))(*v75 + 16))(v75);
      if ( pv )
        CoTaskMemFree(pv);
      if ( v74 )
        (*(void (__fastcall **)(__int64 *))(*v74 + 16))(v74);
      goto LABEL_89;
    }
    while ( 1 )
    {
      *(_QWORD *)&v71 = 0;
      v30 = *v75;
      S1[0] = (wchar_t *)&v71;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v31 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, wchar_t **))(v30 + 32))(v75, v29, &S1[1]);
      if ( v31 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC2,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v31,
          v55);
      if ( LOBYTE(N[0]) )
      {
        v32 = *(_QWORD *)S1[0];
        *(_QWORD *)S1[0] = S1[1];
        if ( v32 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v32 + 16LL))(v32);
      }
      v78 = 0;
      v33 = *(_QWORD *)v71;
      S1[0] = (wchar_t *)&v78;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v34 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(v33 + 24))(v71, &S1[1]);
      if ( v34 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC5,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v34,
          v55);
      if ( LOBYTE(N[0]) )
      {
        v35 = S1[1];
        v36 = S1[0];
        v37 = *(void **)S1[0];
        if ( *(_QWORD *)S1[0] )
        {
          v38 = GetLastError();
          CoTaskMemFree(v37);
          SetLastError(v38);
        }
        *(_QWORD *)v36 = v35;
      }
      v77 = 0;
      v39 = *(_QWORD *)v71;
      S1[0] = (wchar_t *)&v77;
      S1[1] = 0;
      LOBYTE(N[0]) = 1;
      v40 = (*(__int64 (__fastcall **)(_QWORD, wchar_t **))(v39 + 32))(v71, &S1[1]);
      if ( v40 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC8,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\ProductEnumeratorHelper.cpp",
          (const char *)(unsigned int)v40,
          v55);
      if ( LOBYTE(N[0]) )
      {
        v41 = S1[1];
        v42 = S1[0];
        v43 = *(void **)S1[0];
        if ( *(_QWORD *)S1[0] )
        {
          v44 = GetLastError();
          CoTaskMemFree(v43);
          SetLastError(v44);
        }
        *(_QWORD *)v42 = v41;
      }
      v45 = v60;
      if ( !v60[1] )
        goto LABEL_54;
      *(_OWORD *)S1 = 0;
      *(_OWORD *)N = 0;
      v46 = -1;
      do
        ++v46;
      while ( *((_WORD *)v78 + v46) );
      std::wstring::_Construct<1,wchar_t const *>(S1, v78);
      v28 |= 2u;
      v47 = (const wchar_t *)S1;
      if ( N[1] > 7 )
        v47 = S1[0];
      if ( N[0] != 7 || (v48 = 1, wmemcmp(v47, L"Version", 7u)) )
LABEL_54:
        v48 = 0;
      if ( (v28 & 2) != 0 )
      {
        v28 &= ~2u;
        std::wstring::~wstring(S1);
      }
      if ( v48 )
      {
        if ( v56 )
        {
          v49 = *v45;
          *(_OWORD *)S1 = 0;
          *(_OWORD *)N = 0;
          v50 = -1;
          do
            ++v50;
          while ( *(_WORD *)(v49 + 2 * v50) );
          std::wstring::_Construct<1,wchar_t const *>(S1, v49);
          v28 |= 4u;
        }
        else
        {
          v51 = -1;
          do
            ++v51;
          while ( *((_WORD *)v77 + v51) );
          v66[0] = v77;
          v66[1] = v51;
          Windows::UsoProductEnumerator::EscapeProductString(v51, v70, v66);
          v28 |= 8u;
        }
        v66[2] = L"&V={}";
        v66[3] = 5;
        std::format<std::wstring>(v69);
        std::wstring::append(v80);
        std::wstring::~wstring(v69);
        if ( (v28 & 8) != 0 )
        {
          v28 &= ~8u;
          std::wstring::~wstring(v70);
        }
        if ( (v28 & 4) == 0 )
          goto LABEL_75;
        v28 &= ~4u;
      }
      else
      {
        v52 = -1;
        do
          ++v52;
        while ( *((_WORD *)v77 + v52) );
        v67[0] = v77;
        v67[1] = v52;
        Windows::UsoProductEnumerator::EscapeProductString(v52, S1, v67);
        v53 = -1;
        do
          ++v53;
        while ( *((_WORD *)v78 + v53) );
        v68[0] = v78;
        v68[1] = v53;
        Windows::UsoProductEnumerator::EscapeProductString(v53, v69, v68);
        v68[2] = L"&{}={}";
        v68[3] = 6;
        std::format<std::wstring,std::wstring>(v70);
        std::wstring::append(v80);
        std::wstring::~wstring(v70);
        std::wstring::~wstring(v69);
      }
      std::wstring::~wstring(S1);
LABEL_75:
      if ( v77 )
        CoTaskMemFree(v77);
      if ( v78 )
        CoTaskMemFree(v78);
      if ( (_QWORD)v71 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v71 + 16LL))(v71);
      if ( ++v29 >= v73 )
        goto LABEL_82;
    }
  }
  return a2;
}

```

## disassembly

```asm
0x1800dc3cc  mov     [rsp-8+arg_18], rbx
0x1800dc3d1  push    rbp
0x1800dc3d2  push    rsi
0x1800dc3d3  push    rdi
0x1800dc3d4  push    r12
0x1800dc3d6  push    r13
0x1800dc3d8  push    r14
0x1800dc3da  push    r15
0x1800dc3dc  lea     rbp, [rsp-0D0h]
0x1800dc3e4  sub     rsp, 1D0h
0x1800dc3eb  mov     rax, cs:__security_cookie
0x1800dc3f2  xor     rax, rsp
0x1800dc3f5  mov     [rbp+100h+var_38], rax
0x1800dc3fc  mov     [rsp+200h+var_190], r8
0x1800dc401  mov     r13, rdx
0x1800dc404  mov     rax, rcx
0x1800dc407  mov     [rsp+200h+var_188], rcx
0x1800dc40c  mov     [rbp+100h+var_100], rdx
0x1800dc410  xor     r14d, r14d
0x1800dc413  mov     [rsp+200h+var_1BC], r14d
0x1800dc418  xorps   xmm0, xmm0
0x1800dc41b  movups  xmmword ptr [rdx], xmm0
0x1800dc41e  mov     [rdx+10h], r14
0x1800dc422  mov     qword ptr [rdx+18h], 7
0x1800dc42a  mov     [rdx], r14w
0x1800dc42e  lea     edi, [r14+1]
0x1800dc432  mov     [rsp+200h+var_1BC], edi
0x1800dc436  mov     edx, r14d
0x1800dc439  mov     [rsp+200h+var_198], edx
0x1800dc43d  cmp     [rcx], r14d
0x1800dc440  jbe     loc_1800DCC19
0x1800dc446  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800dc44a  mov     [rbp+100h+var_88], r14
0x1800dc44e  mov     rcx, [rax+18h]
0x1800dc452  mov     rax, [rcx]
0x1800dc455  lea     r8, [rbp+100h+var_88]
0x1800dc459  mov     qword ptr [rbp+100h+var_B0], r8
0x1800dc45d  mov     qword ptr [rbp+100h+var_B0+8], r14
0x1800dc461  mov     [rbp+100h+var_A0], 1
0x1800dc465  lea     r8, [rbp+100h+var_B0+8]
0x1800dc469  mov     rax, [rax+20h]
0x1800dc46d  call    _guard_dispatch_icall
0x1800dc472  mov     rcx, [rbp+108h]; this
0x1800dc479  test    eax, eax
0x1800dc47b  js      loc_1800DCC5B
0x1800dc481  cmp     [rbp+100h+var_A0], r14b
0x1800dc485  jz      short loc_1800DC4A7
0x1800dc487  mov     rdx, qword ptr [rbp+100h+var_B0]
0x1800dc48b  mov     rcx, [rdx]
0x1800dc48e  mov     rax, qword ptr [rbp+100h+var_B0+8]
0x1800dc492  mov     [rdx], rax
0x1800dc495  test    rcx, rcx
0x1800dc498  jz      short loc_1800DC4A7
0x1800dc49a  mov     rax, [rcx]
0x1800dc49d  mov     rax, [rax+10h]
0x1800dc4a1  call    _guard_dispatch_icall
0x1800dc4a6  nop
0x1800dc4a7  mov     [rbp+100h+pv], r14
0x1800dc4ae  mov     rcx, [rbp+100h+var_88]
0x1800dc4b2  mov     rax, [rcx]
0x1800dc4b5  lea     rdx, [rbp+100h+pv]
0x1800dc4bc  mov     qword ptr [rbp+100h+var_B0], rdx
0x1800dc4c0  mov     qword ptr [rbp+100h+var_B0+8], r14
0x1800dc4c4  mov     [rbp+100h+var_A0], 1
0x1800dc4c8  lea     rdx, [rbp+100h+var_B0+8]
0x1800dc4cc  mov     rax, [rax+18h]
0x1800dc4d0  call    _guard_dispatch_icall
0x1800dc4d5  mov     rcx, [rbp+108h]; this
0x1800dc4dc  test    eax, eax
0x1800dc4de  js      loc_1800DCC46
0x1800dc4e4  cmp     [rbp+100h+var_A0], r14b
0x1800dc4e8  jz      short loc_1800DC51D
0x1800dc4ea  mov     r15, qword ptr [rbp+100h+var_B0+8]
0x1800dc4ee  mov     rsi, qword ptr [rbp+100h+var_B0]
0x1800dc4f2  mov     r14, [rsi]
0x1800dc4f5  test    r14, r14
0x1800dc4f8  jz      short loc_1800DC513
0x1800dc4fa  call    cs:__imp_GetLastError
0x1800dc500  mov     ebx, eax
0x1800dc502  mov     rcx, r14; pv
0x1800dc505  call    cs:__imp_CoTaskMemFree
0x1800dc50b  mov     ecx, ebx; dwErrCode
0x1800dc50d  call    cs:__imp_SetLastError
0x1800dc513  mov     [rsi], r15
0x1800dc516  xor     r14d, r14d
0x1800dc519  or      r15, 0FFFFFFFFFFFFFFFFh
0x1800dc51d  mov     [rbp+100h+var_80], r14
0x1800dc524  mov     rcx, [rbp+100h+var_88]
0x1800dc528  mov     rax, [rcx]
0x1800dc52b  lea     rdx, [rbp+100h+var_80]
0x1800dc532  mov     qword ptr [rbp+100h+var_B0], rdx
0x1800dc536  mov     qword ptr [rbp+100h+var_B0+8], r14
0x1800dc53a  mov     [rbp+100h+var_A0], 1
0x1800dc53e  lea     rdx, [rbp+100h+var_B0+8]
0x1800dc542  mov     rax, [rax+20h]
0x1800dc546  call    _guard_dispatch_icall
0x1800dc54b  mov     rcx, [rbp+108h]; this
0x1800dc552  test    eax, eax
0x1800dc554  js      loc_1800DCCDF
0x1800dc55a  cmp     [rbp+100h+var_A0], r14b
0x1800dc55e  jz      short loc_1800DC580
0x1800dc560  mov     rdx, qword ptr [rbp+100h+var_B0]
0x1800dc564  mov     rcx, [rdx]
0x1800dc567  mov     rax, qword ptr [rbp+100h+var_B0+8]
0x1800dc56b  mov     [rdx], rax
0x1800dc56e  test    rcx, rcx
0x1800dc571  jz      short loc_1800DC580
0x1800dc573  mov     rax, [rcx]
0x1800dc576  mov     rax, [rax+10h]
0x1800dc57a  call    _guard_dispatch_icall
0x1800dc57f  nop
0x1800dc580  mov     [rbp+100h+var_90], r14d
0x1800dc584  mov     rcx, [rbp+100h+var_80]
0x1800dc58b  mov     rax, [rcx]
0x1800dc58e  lea     rdx, [rbp+100h+var_90]
0x1800dc592  mov     rax, [rax+18h]
0x1800dc596  call    _guard_dispatch_icall
0x1800dc59b  mov     rcx, [rbp+108h]; this
0x1800dc5a2  test    eax, eax
0x1800dc5a4  js      loc_1800DCCCA
0x1800dc5aa  cmp     [rbp+100h+var_90], r14d
0x1800dc5ae  jnz     short loc_1800DC5F7
0x1800dc5b0  mov     rcx, [rbp+100h+var_80]
0x1800dc5b7  test    rcx, rcx
0x1800dc5ba  jz      short loc_1800DC5C9
0x1800dc5bc  mov     rax, [rcx]
0x1800dc5bf  mov     rax, [rax+10h]
0x1800dc5c3  call    _guard_dispatch_icall
0x1800dc5c8  nop
0x1800dc5c9  mov     rcx, [rbp+100h+pv]; pv
0x1800dc5d0  test    rcx, rcx
0x1800dc5d3  jz      short loc_1800DC5DC
0x1800dc5d5  call    cs:__imp_CoTaskMemFree
0x1800dc5db  nop
0x1800dc5dc  mov     rcx, [rbp+100h+var_88]
0x1800dc5e0  test    rcx, rcx
0x1800dc5e3  jz      short loc_1800DC5F2
0x1800dc5e5  mov     rax, [rcx]
0x1800dc5e8  mov     rax, [rax+10h]
0x1800dc5ec  call    _guard_dispatch_icall
0x1800dc5f1  nop
0x1800dc5f2  jmp     loc_1800DCC02
0x1800dc5f7  mov     [rsp+200h+var_1C0], r14b
0x1800dc5fc  mov     qword ptr [rbp+100h+var_B0], r14
0x1800dc600  mov     rcx, [rbp+100h+var_88]
0x1800dc604  mov     rax, [rcx]
0x1800dc607  mov     qword ptr [rbp+100h+var_B0], r14
0x1800dc60b  lea     r8, [rbp+100h+var_B0]
0x1800dc60f  lea     rdx, aPrimaryosprodu; "PrimaryOSProduct"
0x1800dc616  mov     rax, [rax+28h]
0x1800dc61a  call    _guard_dispatch_icall
0x1800dc61f  test    eax, eax
0x1800dc621  js      loc_1800DC6C2
0x1800dc627  mov     [rbp+100h+var_78], r14
0x1800dc62e  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1800dc632  mov     rax, [rcx]
0x1800dc635  mov     [rbp+100h+var_78], r14
0x1800dc63c  lea     rdx, [rbp+100h+var_78]
0x1800dc643  mov     rax, [rax+20h]
0x1800dc647  call    _guard_dispatch_icall
0x1800dc64c  mov     rcx, [rbp+108h]; this
0x1800dc653  test    eax, eax
0x1800dc655  js      loc_1800DCC70
0x1800dc65b  xorps   xmm0, xmm0
0x1800dc65e  movups  xmmword ptr [rsp+200h+S1], xmm0
0x1800dc663  xorps   xmm1, xmm1
0x1800dc666  movdqu  xmmword ptr [rsp+200h+N], xmm1
0x1800dc66c  mov     rdx, [rbp+100h+var_78]
0x1800dc673  mov     r8, r15
0x1800dc676  inc     r8
0x1800dc679  cmp     [rdx+r8*2], r14w
0x1800dc67e  jnz     short loc_1800DC676
0x1800dc680  lea     rcx, [rsp+200h+S1]
0x1800dc685  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800dc68a  nop
0x1800dc68b  lea     rcx, [rsp+200h+S1]; String
0x1800dc690  call    ?stoi@std@@YAHAEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@PEA_KH@Z; std::stoi(std::wstring const &,unsigned __int64 *,int)
0x1800dc695  mov     ebx, eax
0x1800dc697  lea     rcx, [rsp+200h+S1]; void *
0x1800dc69c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1800dc6a1  nop
0x1800dc6a2  cmp     ebx, 1
0x1800dc6a5  setz    bl
0x1800dc6a8  mov     [rsp+200h+var_1C0], bl
0x1800dc6ac  mov     rcx, [rbp+100h+var_78]; pv
0x1800dc6b3  test    rcx, rcx
0x1800dc6b6  jz      short loc_1800DC6C2
0x1800dc6b8  call    cs:__imp_CoTaskMemFree
0x1800dc6be  mov     [rsp+200h+var_1C0], bl
0x1800dc6c2  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1800dc6c6  test    rcx, rcx
0x1800dc6c9  jz      short loc_1800DC6D8
0x1800dc6cb  mov     rax, [rcx]
0x1800dc6ce  mov     rax, [rax+10h]
0x1800dc6d2  call    _guard_dispatch_icall
0x1800dc6d7  nop
0x1800dc6d8  mov     rbx, [rbp+100h+pv]
0x1800dc6df  lea     rcx, [rbp+100h+var_180]; this
0x1800dc6e3  call    ??0_Format_arg_index@std@@QEAA@XZ; std::_Format_arg_index::_Format_arg_index(void)
0x1800dc6e8  mov     [rbp+100h+var_178], rbx
0x1800dc6ec  mov     rax, 0B000000000000000h
0x1800dc6f6  mov     [rbp+100h+var_180], rax
0x1800dc6fa  lea     rax, aPn; "PN={}"
0x1800dc701  mov     qword ptr [rbp+100h+var_170], rax
0x1800dc705  mov     qword ptr [rbp+100h+var_170+8], 5
0x1800dc70d  mov     [rbp+100h+var_160], 1
0x1800dc715  lea     rax, [rbp+100h+var_180]
0x1800dc719  mov     [rbp+100h+var_158], rax
0x1800dc71d  movaps  xmm0, [rbp+100h+var_170]
0x1800dc721  movdqa  [rbp+100h+var_B0], xmm0
0x1800dc726  lea     r8, [rbp+100h+var_160]
0x1800dc72a  lea     rdx, [rbp+100h+var_B0]
0x1800dc72e  lea     rcx, [rbp+100h+var_58]; Src
0x1800dc735  call    ??$vformat@$0A@@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@V?$basic_string_view@_WU?$char_traits@_W@std@@@0@V?$basic_format_args@V?$basic_format_context@V?$back_insert_iterator@V?$_Fmt_buffer@_W@std@@@std@@_W@std@@@0@@Z; std::vformat<0>(std::wstring_view,std::basic_format_args<std::basic_format_context<std::back_insert_iterator<std::_Fmt_buffer<wchar_t>>,wchar_t>>)
0x1800dc73a  or      edi, 20h
0x1800dc73d  mov     [rsp+200h+var_1BC], edi
0x1800dc741  mov     r12d, r14d
0x1800dc744  cmp     [rbp+100h+var_90], r14d
0x1800dc748  jbe     loc_1800DCB29
0x1800dc74e  mov     qword ptr [rbp+100h+var_B0], r14
0x1800dc752  mov     rcx, [rbp+100h+var_80]
0x1800dc759  mov     rax, [rcx]
0x1800dc75c  lea     rdx, [rbp+100h+var_B0]
0x1800dc760  mov     [rsp+200h+S1], rdx
0x1800dc765  mov     [rsp+200h+S1+8], r14
0x1800dc76a  mov     byte ptr [rsp+200h+N], 1
0x1800dc76f  lea     r8, [rsp+200h+S1+8]
0x1800dc774  mov     edx, r12d
0x1800dc777  mov     rax, [rax+20h]
0x1800dc77b  call    _guard_dispatch_icall
0x1800dc780  mov     rcx, [rbp+108h]; this
0x1800dc787  test    eax, eax
0x1800dc789  js      loc_1800DCCAF
0x1800dc78f  cmp     byte ptr [rsp+200h+N], r14b
0x1800dc794  jz      short loc_1800DC7B8
0x1800dc796  mov     rdx, [rsp+200h+S1]
0x1800dc79b  mov     rcx, [rdx]
0x1800dc79e  mov     rax, [rsp+200h+S1+8]
0x1800dc7a3  mov     [rdx], rax
0x1800dc7a6  test    rcx, rcx
0x1800dc7a9  jz      short loc_1800DC7B8
0x1800dc7ab  mov     rax, [rcx]
0x1800dc7ae  mov     rax, [rax+10h]
0x1800dc7b2  call    _guard_dispatch_icall
0x1800dc7b7  nop
0x1800dc7b8  mov     [rbp+100h+var_68], r14
0x1800dc7bf  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1800dc7c3  mov     rax, [rcx]
0x1800dc7c6  lea     rdx, [rbp+100h+var_68]
0x1800dc7cd  mov     [rsp+200h+S1], rdx
0x1800dc7d2  mov     [rsp+200h+S1+8], r14
0x1800dc7d7  mov     byte ptr [rsp+200h+N], 1
0x1800dc7dc  lea     rdx, [rsp+200h+S1+8]
0x1800dc7e1  mov     rax, [rax+18h]
0x1800dc7e5  call    _guard_dispatch_icall
0x1800dc7ea  mov     rcx, [rbp+108h]; this
0x1800dc7f1  test    eax, eax
0x1800dc7f3  js      loc_1800DCC9A
0x1800dc7f9  cmp     byte ptr [rsp+200h+N], r14b
0x1800dc7fe  jz      short loc_1800DC831
0x1800dc800  mov     r15, [rsp+200h+S1+8]
0x1800dc805  mov     rsi, [rsp+200h+S1]
0x1800dc80a  mov     r14, [rsi]
0x1800dc80d  test    r14, r14
0x1800dc810  jz      short loc_1800DC82B
0x1800dc812  call    cs:__imp_GetLastError
0x1800dc818  mov     ebx, eax
0x1800dc81a  mov     rcx, r14; pv
0x1800dc81d  call    cs:__imp_CoTaskMemFree
0x1800dc823  mov     ecx, ebx; dwErrCode
0x1800dc825  call    cs:__imp_SetLastError
0x1800dc82b  mov     [rsi], r15
0x1800dc82e  xor     r14d, r14d
0x1800dc831  mov     [rbp+100h+var_70], r14
0x1800dc838  mov     rcx, qword ptr [rbp+100h+var_B0]
0x1800dc83c  mov     rax, [rcx]
0x1800dc83f  lea     rdx, [rbp+100h+var_70]
0x1800dc846  mov     [rsp+200h+S1], rdx
0x1800dc84b  mov     [rsp+200h+S1+8], r14
0x1800dc850  mov     byte ptr [rsp+200h+N], 1
0x1800dc855  lea     rdx, [rsp+200h+S1+8]
0x1800dc85a  mov     rax, [rax+20h]
0x1800dc85e  call    _guard_dispatch_icall
0x1800dc863  mov     rcx, [rbp+108h]; this
0x1800dc86a  test    eax, eax
0x1800dc86c  js      loc_1800DCC85
0x1800dc872  cmp     byte ptr [rsp+200h+N], r14b
0x1800dc877  jz      short loc_1800DC8AA
0x1800dc879  mov     r15, [rsp+200h+S1+8]
0x1800dc87e  mov     rsi, [rsp+200h+S1]
0x1800dc883  mov     r14, [rsi]
0x1800dc886  test    r14, r14
0x1800dc889  jz      short loc_1800DC8A4
0x1800dc88b  call    cs:__imp_GetLastError
0x1800dc891  mov     ebx, eax
0x1800dc893  mov     rcx, r14; pv
0x1800dc896  call    cs:__imp_CoTaskMemFree
0x1800dc89c  mov     ecx, ebx; dwErrCode
0x1800dc89e  call    cs:__imp_SetLastError
0x1800dc8a4  mov     [rsi], r15
  ... truncated ...
```
