# CComClassInfo::InitializeSurrogateInfo(HKEY__ *,tagProcessType,bool,bool,ushort)

- ea: `0x180067d70`
- end: `0x1800685de`
- name: `?InitializeSurrogateInfo@CComClassInfo@@AEAAJPEAUHKEY__@@W4tagProcessType@@_N2G@Z`
- size: `2158`
- prototype: ``
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180063694`

## callees

- `0x1800116bc`
- `0x18001186c`
- `0x180011db0`
- `0x180013b18`
- `0x180034260`
- `0x18004b524`
- `0x18005a664`
- `0x18005ad10`
- `0x180067d70`
- `0x180074d98`
- `0x18007ac30`
- `0x180081158`
- `0x1800855d8`
- `0x180095c0c`
- `0x18009e160`
- `0x1800b7ac0`
- `0x1800b8060`
- `0x1800b8428`
- `0x1800d1de0`
- `0x180114010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068500`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068500`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068161`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180068161`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067e59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006806f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800681c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800683e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006849d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180067e59`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006806f`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800681c6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800683e1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18006849d`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006828b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18006828b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068269`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180068269`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006836c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18006836c`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180068357`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180068357`

## string_xrefs

- `0x1800684ca`: `DllHost.exe`
- `0x180068126`: `onecore\com\combase\catalog\class.cxx`
- `0x1800682e9`: `onecore\com\combase\catalog\class.cxx`
- `0x180068529`: `onecore\com\combase\catalog\class.cxx`
- `0x18006859f`: `onecore\com\combase\catalog\class.cxx`
- `0x180068434`: `DllHost.exe /Processid:`
- `0x18006858a`: `CLSID:%ws %!HRESULT!`
- `0x18006810b`: `CComClassInfo::InitializeSurrogateInfo`
- `0x180068535`: `CComClassInfo::InitializeSurrogateInfo`
- `0x180068583`: `CComClassInfo::InitializeSurrogateInfo`
- `0x18006811f`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Surrogate:%ws %!HRESULT!`
- `0x18006851c`: `CLSID:%ws %!WINERROR!`

## pseudocode

```c
__int64 __fastcall CComClassInfo::InitializeSurrogateInfo(
        __int64 a1,
        HKEY a2,
        int a3,
        char a4,
        char a5,
        unsigned __int16 a6)
{
  __int64 (__fastcall ***v8)(_QWORD, GUID *, __int64 *); // rcx
  signed int ExeArchitectureFromRegString; // edi
  int v10; // r15d
  __int64 v11; // rsi
  unsigned __int64 v12; // rsi
  SIZE_T v13; // rax
  _WORD *v14; // rax
  CComClassInfo *v15; // rcx
  _WORD *v16; // r10
  __int64 v17; // rdi
  unsigned __int16 *v18; // rcx
  __int64 v19; // rax
  unsigned __int64 v20; // rdx
  _WORD *v21; // r8
  __int64 v22; // r9
  __int64 v23; // rcx
  _WORD *v24; // rax
  __int64 v25; // rax
  const wchar_t *v26; // rcx
  unsigned __int64 v27; // rdx
  __int64 v28; // r8
  _WORD *v29; // rax
  __int64 v30; // rcx
  _WORD *v31; // r10
  __int64 v32; // rax
  unsigned __int16 *v33; // rcx
  unsigned __int64 v34; // rdx
  _WORD *v35; // r8
  CComClassInfo *v36; // r9
  _WORD *v37; // rax
  const unsigned __int16 *v38; // rax
  _WORD *v39; // rax
  __int64 v40; // rax
  unsigned __int64 v41; // rdi
  SIZE_T v42; // rax
  unsigned __int64 v43; // kr00_8
  unsigned __int16 *v44; // rax
  const unsigned __int16 near **v45; // r8
  __int64 v46; // rax
  unsigned __int64 v47; // rdi
  SIZE_T v48; // rax
  unsigned __int64 v49; // kr10_8
  unsigned __int16 *v50; // rax
  bool v51; // r9
  LSTATUS v52; // r15d
  BOOL v53; // esi
  const WCHAR *v54; // rcx
  int ModuleArchitecture; // eax
  unsigned int SystemWow64Directory2W; // eax
  UINT SystemDirectoryW; // esi
  __int64 v58; // rcx
  unsigned __int64 v59; // rdi
  SIZE_T v60; // rax
  unsigned __int16 *v61; // rax
  UINT v62; // edi
  SIZE_T v63; // rax
  unsigned __int16 *v64; // rax
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int v67; // [rsp+28h] [rbp-D8h]
  unsigned int v68; // [rsp+28h] [rbp-D8h]
  unsigned int v69; // [rsp+28h] [rbp-D8h]
  __int64 v70; // [rsp+30h] [rbp-D0h]
  DWORD LastError; // [rsp+30h] [rbp-D0h]
  unsigned __int16 *v72; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v73; // [rsp+48h] [rbp-B8h] BYREF
  HKEY hKey; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v75; // [rsp+58h] [rbp-A8h] BYREF
  unsigned __int16 v76[40]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Buffer; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v78[526]; // [rsp+B2h] [rbp-4Eh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  if ( a3 != 3 )
  {
    ExeArchitectureFromRegString = 0;
    if ( a3 != 2 )
      goto LABEL_116;
    if ( !g_bInSCM && !a4 )
      MicrosoftTelemetryAssertTriggeredNoArgs(a1);
    hKey = 0;
    v52 = RegOpenKeyExW(a2, L"InprocServer32", 0, 0x20019u, &hKey);
    v53 = v52 != 2;
    if ( hKey )
      RegCloseKey(hKey);
    if ( v52 != 2 )
    {
      if ( a5 )
      {
        if ( !*(_QWORD *)(a1 + 248) )
          CComClassInfo::InitializeForInprocActivations((CComClassInfo *)a1, g_bInSCM, a2, v51, 0, 0);
        v54 = *(const WCHAR **)(a1 + 248);
        if ( v54 )
        {
          ModuleArchitecture = CoGetModuleArchitecture(v54);
          if ( ModuleArchitecture < 0 )
          {
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x466,
              (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
              (const char *)(unsigned int)ModuleArchitecture,
              phkResult);
            return (unsigned int)ExeArchitectureFromRegString;
          }
        }
        else
        {
          v53 = 0;
        }
      }
      else
      {
        *(_DWORD *)(a1 + 304) = a6;
      }
    }
    if ( !v53 )
      return (unsigned int)ExeArchitectureFromRegString;
    Buffer = 0;
    memset_0(v78, 0, 0x206u);
    if ( *(_DWORD *)(a1 + 304) == GetNativeArchitecture() )
    {
      SystemDirectoryW = GetSystemDirectoryW(&Buffer, 0x103u);
      if ( SystemDirectoryW >= 0x103 )
        goto LABEL_112;
    }
    else
    {
      SystemWow64Directory2W = GetSystemWow64Directory2W(&Buffer, 259, *(unsigned __int16 *)(a1 + 304));
      SystemDirectoryW = SystemWow64Directory2W < 0x103 ? SystemWow64Directory2W : 0;
    }
    if ( SystemDirectoryW )
    {
      if ( *(&Buffer + SystemDirectoryW - 1) != 92 )
      {
        v58 = SystemDirectoryW++;
        *(_WORD *)&v78[2 * v58 - 2] = 92;
        if ( 2 * (unsigned __int64)SystemDirectoryW >= 0x208 )
          _report_rangecheckfailure();
        *(_WORD *)&v78[2 * SystemDirectoryW - 2] = 0;
      }
      v59 = SystemDirectoryW + 62LL;
      v60 = 2 * v59;
      v72 = (unsigned __int16 *)v59;
      if ( !is_mul_ok(v59, 2u) )
        v60 = -1;
      v61 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v60);
      *(_QWORD *)(a1 + 288) = v61;
      if ( !v61 )
        goto LABEL_111;
      v73 = v61;
      StringCchCopyExW(v61, SystemDirectoryW + 62LL, &Buffer, &v73, (unsigned __int64 *)&v72, v67);
      StringCchCopyExW(v73, (unsigned __int64)v72, L"DllHost.exe /Processid:", &v73, (unsigned __int64 *)&v72, v68);
      wStringFromGUID2((const struct _GUID *)(a1 + 80), v76, 39);
      ExeArchitectureFromRegString = StringCchCopyExW(
                                       v73,
                                       (unsigned __int64)v72,
                                       v76,
                                       &v73,
                                       (unsigned __int64 *)&v72,
                                       v69);
      if ( ExeArchitectureFromRegString >= 0 )
      {
        v62 = SystemDirectoryW + 12;
        v63 = 2LL * (SystemDirectoryW + 12);
        if ( !is_mul_ok(SystemDirectoryW + 12, 2u) )
          v63 = -1;
        v64 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v63);
        *(_QWORD *)(a1 + 296) = v64;
        if ( v64 )
        {
          StringCchCopyW(v64, v62, &Buffer);
          ExeArchitectureFromRegString = StringCchCatW(*(unsigned __int16 **)(a1 + 296), v62, L"DllHost.exe");
          goto LABEL_116;
        }
LABEL_111:
        ExeArchitectureFromRegString = -2147024882;
      }
LABEL_116:
      *(_DWORD *)(a1 + 224) |= 4u;
LABEL_117:
      if ( ExeArchitectureFromRegString == -2147024894 )
      {
        return 0;
      }
      else if ( ExeArchitectureFromRegString < 0
             && (dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
      {
        LODWORD(v70) = ExeArchitectureFromRegString;
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeSurrogateInfo",
          1355,
          0,
          (__int64)L"CLSID:%ws %!HRESULT!",
          a1 + 112,
          v70);
      }
      return (unsigned int)ExeArchitectureFromRegString;
    }
LABEL_112:
    if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
    {
      LastError = GetLastError();
      ComTraceMessageT<unsigned __int64,unsigned long>(
        (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
        (unsigned int)"CComClassInfo::InitializeSurrogateInfo",
        1227,
        0,
        (__int64)L"CLSID:%ws %!WINERROR!",
        a1 + 112,
        LastError);
    }
    goto LABEL_116;
  }
  v8 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))(a1 + 104);
  v75 = 0;
  if ( !v8 )
    return (unsigned int)-2147467259;
  ExeArchitectureFromRegString = (**v8)(v8, &GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680, &v75);
  if ( ExeArchitectureFromRegString >= 0 )
  {
    v72 = 0;
    LODWORD(v73) = 0;
    v10 = 1;
    ExeArchitectureFromRegString = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **, unsigned __int16 **))(*(_QWORD *)v75 + 208LL))(
                                     v75,
                                     &v73,
                                     &v72);
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_77;
    if ( (_DWORD)v73 )
    {
      v40 = -1;
      do
        ++v40;
      while ( v72[v40] );
      v41 = v40 + 1;
      v43 = v40 + 1;
      v42 = 2 * (v40 + 1);
      if ( !is_mul_ok(v43, 2u) )
        v42 = -1;
      v44 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v42);
      *(_QWORD *)(a1 + 288) = v44;
      if ( !v44 )
        goto LABEL_76;
      ExeArchitectureFromRegString = StringCchCopyW(v44, v41, v72);
    }
    else
    {
      v11 = -1;
      do
        ++v11;
      while ( v72[v11] );
      v12 = v11 + 51;
      v13 = 2 * v12;
      if ( !is_mul_ok(v12, 2u) )
        v13 = -1;
      v14 = HeapAlloc(g_hHeap, 0, v13);
      *(_QWORD *)(a1 + 288) = v14;
      v16 = v14;
      if ( v14 )
      {
        v17 = 2147483646;
        if ( !v12 )
          goto LABEL_30;
        if ( v12 <= 0x7FFFFFFF )
        {
          v18 = v72;
          v19 = 2147483646;
          v20 = v12;
          v21 = v16;
          v22 = 0;
          do
          {
            if ( !v19 )
              break;
            if ( !*v18 )
              break;
            *v21++ = *v18++;
            --v19;
            ++v22;
            --v20;
          }
          while ( v20 );
          v23 = v22 - 1;
          v24 = v21 - 1;
          if ( v20 )
          {
            v23 = v22;
            v24 = v21;
          }
          v12 -= v23;
          *v24 = 0;
          v16 += v23;
          if ( !v12 )
          {
LABEL_30:
            wStringFromGUID2((const struct _GUID *)(a1 + 64), v76, 39);
            if ( v12 )
            {
              if ( v12 <= 0x7FFFFFFF )
              {
                v32 = 2147483646;
                v33 = v76;
                v34 = v12;
                v35 = v31;
                v36 = 0;
                do
                {
                  if ( !v32 )
                    break;
                  if ( !*v33 )
                    break;
                  *v35++ = *v33++;
                  --v32;
                  v36 = (CComClassInfo *)((char *)v36 + 1);
                  --v34;
                }
                while ( v34 );
                v15 = (CComClassInfo *)((char *)v36 - 1);
                v37 = v35 - 1;
                if ( v34 )
                {
                  v15 = v36;
                  v37 = v35;
                }
                v12 -= (unsigned __int64)v15;
                *v37 = 0;
                v31 += (__int64)v15;
                if ( !v12 )
                  goto LABEL_48;
              }
              else
              {
                *v31 = 0;
              }
              if ( v12 <= 0x7FFFFFFF )
              {
                v38 = L" -Embedding";
                do
                {
                  if ( !v17 )
                    break;
                  v15 = (CComClassInfo *)*v38;
                  if ( !(_WORD)v15 )
                    break;
                  *v31 = (_WORD)v15;
                  ++v38;
                  ++v31;
                  --v17;
                  --v12;
                }
                while ( v12 );
                v39 = v31 - 1;
                if ( v12 )
                  v39 = v31;
                ExeArchitectureFromRegString = v12 == 0 ? 0x8007007A : 0;
                *v39 = 0;
                goto LABEL_57;
              }
            }
LABEL_48:
            ExeArchitectureFromRegString = -2147024809;
            if ( v12 )
              *v31 = 0;
            goto LABEL_57;
          }
        }
        else
        {
          *v14 = 0;
        }
        if ( v12 > 0x7FFFFFFF )
        {
          *v16 = 0;
        }
        else
        {
          v25 = 2147483646;
          v26 = L" ";
          v27 = v12;
          v28 = 0;
          do
          {
            if ( !v25 )
              break;
            if ( !*v26 )
              break;
            *v16++ = *v26++;
            --v25;
            ++v28;
            --v27;
          }
          while ( v27 );
          v29 = v16 - 1;
          v30 = v28 - 1;
          if ( v27 )
          {
            v29 = v16;
            v30 = v28;
          }
          v12 -= v30;
          *v29 = 0;
        }
        goto LABEL_30;
      }
      ExeArchitectureFromRegString = -2147024882;
    }
LABEL_57:
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_77;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(
                                     v15,
                                     *(const unsigned __int16 **)(a1 + 288),
                                     (unsigned int *)(a1 + 304));
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_77;
    if ( !CComClassInfo::IsBinaryArchitectureExpectedForView((CComClassInfo *)a1, a6) )
    {
      ExeArchitectureFromRegString = -2147221164;
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
        ComTraceMessageT<unsigned short *,unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CComClassInfo::InitializeSurrogateInfo",
          1028,
          1,
          (__int64)L"CLSID:%ws Binary architecture doesn't match registry view architecture. Surrogate:%ws %!HRESULT!",
          a1 + 112,
          *(_QWORD *)(a1 + 288),
          -2147221164);
      v45 = *(const unsigned __int16 near ***)(a1 + 288);
      v10 = 0;
      if ( v45 && v45 != &g_wszEmptyString )
        HeapFree(g_hHeap, 0, v45);
      *(_QWORD *)(a1 + 288) = 0;
LABEL_77:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      if ( !v10 )
        goto LABEL_117;
      goto LABEL_116;
    }
    hKey = 0;
    if ( (*(int (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v75 + 216LL))(v75, &hKey) < 0 )
    {
      ExeArchitectureFromRegString = 0;
      goto LABEL_77;
    }
    v46 = -1;
    do
      ++v46;
    while ( *((_WORD *)hKey + v46) );
    v47 = v46 + 1;
    v49 = v46 + 1;
    v48 = 2 * (v46 + 1);
    if ( !is_mul_ok(v49, 2u) )
      v48 = -1;
    v50 = (unsigned __int16 *)HeapAlloc(g_hHeap, 0, v48);
    *(_QWORD *)(a1 + 296) = v50;
    if ( v50 )
    {
      ExeArchitectureFromRegString = StringCchCopyW(v50, v47, (const unsigned __int16 *)hKey);
      goto LABEL_77;
    }
LABEL_76:
    ExeArchitectureFromRegString = -2147024882;
    goto LABEL_77;
  }
  return (unsigned int)ExeArchitectureFromRegString;
}

```

## disassembly

```asm
0x180067d70  mov     [rsp-8+arg_10], rbx
0x180067d75  push    rbp
0x180067d76  push    rsi
0x180067d77  push    rdi
0x180067d78  push    r12
0x180067d7a  push    r13
0x180067d7c  push    r14
0x180067d7e  push    r15
0x180067d80  lea     rbp, [rsp-1D0h]
0x180067d88  sub     rsp, 2D0h
0x180067d8f  mov     rax, cs:__security_cookie
0x180067d96  xor     rax, rsp
0x180067d99  mov     [rbp+200h+var_40], rax
0x180067da0  xor     ebx, ebx
0x180067da2  mov     r13, rdx
0x180067da5  mov     r14, rcx
0x180067da8  cmp     r8d, 3
0x180067dac  jnz     loc_180068224
0x180067db2  mov     rcx, [rcx+68h]
0x180067db6  mov     [rsp+300h+var_2A8], rbx
0x180067dbb  test    rcx, rcx
0x180067dbe  jz      loc_18006821A
0x180067dc4  mov     rax, [rcx]
0x180067dc7  lea     r8, [rsp+300h+var_2A8]
0x180067dcc  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x180067dd3  mov     rax, [rax]
0x180067dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067ddb  mov     edi, eax
0x180067ddd  test    eax, eax
0x180067ddf  js      loc_1800685AB
0x180067de5  mov     rcx, [rsp+300h+var_2A8]
0x180067dea  lea     r8, [rsp+300h+var_2C0]
0x180067def  mov     [rsp+300h+var_2C0], rbx
0x180067df4  lea     rdx, [rsp+300h+var_2B8]
0x180067df9  mov     dword ptr [rsp+300h+var_2B8], ebx
0x180067dfd  lea     r15d, [rbx+1]
0x180067e01  mov     rax, [rcx]
0x180067e04  mov     rax, [rax+0D0h]
0x180067e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180067e10  mov     edi, eax
0x180067e12  test    eax, eax
0x180067e14  js      loc_1800681FB
0x180067e1a  or      r13, 0FFFFFFFFFFFFFFFFh
0x180067e1e  cmp     dword ptr [rsp+300h+var_2B8], ebx
0x180067e22  jnz     loc_18006803E
0x180067e28  mov     rax, [rsp+300h+var_2C0]
0x180067e2d  mov     rsi, r13
0x180067e30  inc     rsi
0x180067e33  cmp     [rax+rsi*2], bx
0x180067e37  jnz     short loc_180067E30
0x180067e39  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180067e40  mov     r12d, 2
0x180067e46  mov     eax, r12d
0x180067e49  add     rsi, 33h ; '3'
0x180067e4d  mul     rsi
0x180067e50  cmovb   rax, r13
0x180067e54  xor     edx, edx; dwFlags
0x180067e56  mov     r8, rax; dwBytes
0x180067e59  call    cs:__imp_HeapAlloc
0x180067e60  nop     dword ptr [rax+rax+00h]
0x180067e65  mov     [r14+120h], rax
0x180067e6c  mov     r10, rax
0x180067e6f  test    rax, rax
0x180067e72  jz      loc_180068037
0x180067e78  mov     edi, 7FFFFFFEh
0x180067e7d  test    rsi, rsi
0x180067e80  jz      loc_180067F58
0x180067e86  cmp     rsi, 7FFFFFFFh
0x180067e8d  jbe     short loc_180067E94
0x180067e8f  mov     [rax], bx
0x180067e92  jmp     short loc_180067EEB
0x180067e94  mov     rcx, [rsp+300h+var_2C0]
0x180067e99  mov     rax, rdi
0x180067e9c  mov     rdx, rsi
0x180067e9f  mov     r8, r10
0x180067ea2  mov     r9, rbx
0x180067ea5  test    rax, rax
0x180067ea8  jz      short loc_180067EC9
0x180067eaa  movzx   r11d, word ptr [rcx]
0x180067eae  test    r11w, r11w
0x180067eb2  jz      short loc_180067EC9
0x180067eb4  mov     [r8], r11w
0x180067eb8  add     rcx, r12
0x180067ebb  add     r8, r12
0x180067ebe  sub     rax, r15
0x180067ec1  add     r9, r15
0x180067ec4  sub     rdx, r15
0x180067ec7  jnz     short loc_180067EA5
0x180067ec9  test    rdx, rdx
0x180067ecc  lea     rcx, [r9-1]
0x180067ed0  lea     rax, [r8-2]
0x180067ed4  cmovnz  rcx, r9
0x180067ed8  cmovnz  rax, r8
0x180067edc  sub     rsi, rcx
0x180067edf  mov     [rax], bx
0x180067ee2  lea     r10, [r10+rcx*2]
0x180067ee6  test    rsi, rsi
0x180067ee9  jz      short loc_180067F58
0x180067eeb  cmp     rsi, 7FFFFFFFh
0x180067ef2  ja      short loc_180067F4F
0x180067ef4  test    rsi, rsi
0x180067ef7  jz      short loc_180067F58
0x180067ef9  mov     rax, rdi
0x180067efc  lea     rcx, asc_18012013C; " "
0x180067f03  mov     rdx, rsi
0x180067f06  mov     r8, rbx
0x180067f09  mov     r11, r10
0x180067f0c  test    rax, rax
0x180067f0f  jz      short loc_180067F30
0x180067f11  movzx   r9d, word ptr [rcx]
0x180067f15  test    r9w, r9w
0x180067f19  jz      short loc_180067F30
0x180067f1b  mov     [r10], r9w
0x180067f1f  add     rcx, r12
0x180067f22  add     r10, r12
0x180067f25  sub     rax, r15
0x180067f28  add     r8, r15
0x180067f2b  sub     rdx, r15
0x180067f2e  jnz     short loc_180067F0C
0x180067f30  test    rdx, rdx
0x180067f33  lea     rax, [r10-2]
0x180067f37  lea     rcx, [r8-1]
0x180067f3b  cmovnz  rax, r10
0x180067f3f  cmovnz  rcx, r8
0x180067f43  sub     rsi, rcx
0x180067f46  mov     [rax], bx
0x180067f49  lea     r10, [r11+rcx*2]
0x180067f4d  jmp     short loc_180067F58
0x180067f4f  test    rsi, rsi
0x180067f52  jz      short loc_180067F58
0x180067f54  mov     [r10], bx
0x180067f58  lea     rcx, [r14+40h]; struct _GUID *
0x180067f5c  mov     r8d, 27h ; '''; int
0x180067f62  lea     rdx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180067f67  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x180067f6c  test    rsi, rsi
0x180067f6f  jz      loc_180068027
0x180067f75  cmp     rsi, 7FFFFFFFh
0x180067f7c  jbe     short loc_180067F84
0x180067f7e  mov     [r10], bx
0x180067f82  jmp     short loc_180067FDB
0x180067f84  mov     rax, rdi
0x180067f87  lea     rcx, [rsp+300h+var_2A0]
0x180067f8c  mov     rdx, rsi
0x180067f8f  mov     r8, r10
0x180067f92  mov     r9, rbx
0x180067f95  test    rax, rax
0x180067f98  jz      short loc_180067FB9
0x180067f9a  movzx   r11d, word ptr [rcx]
0x180067f9e  test    r11w, r11w
0x180067fa2  jz      short loc_180067FB9
0x180067fa4  mov     [r8], r11w
0x180067fa8  add     rcx, r12
0x180067fab  add     r8, r12
0x180067fae  sub     rax, r15
0x180067fb1  add     r9, r15
0x180067fb4  sub     rdx, r15
0x180067fb7  jnz     short loc_180067F95
0x180067fb9  test    rdx, rdx
0x180067fbc  lea     rcx, [r9-1]
0x180067fc0  lea     rax, [r8-2]
0x180067fc4  cmovnz  rcx, r9
0x180067fc8  cmovnz  rax, r8
0x180067fcc  sub     rsi, rcx
0x180067fcf  mov     [rax], bx
0x180067fd2  lea     r10, [r10+rcx*2]
0x180067fd6  test    rsi, rsi
0x180067fd9  jz      short loc_180068027
0x180067fdb  cmp     rsi, 7FFFFFFFh
0x180067fe2  ja      short loc_180068027
0x180067fe4  lea     rax, ?g_wszEmbedding@@3QBGB; " -Embedding"
0x180067feb  test    rdi, rdi
0x180067fee  jz      short loc_18006800A
0x180067ff0  movzx   ecx, word ptr [rax]
0x180067ff3  test    cx, cx
0x180067ff6  jz      short loc_18006800A
0x180067ff8  mov     [r10], cx
0x180067ffc  add     rax, r12
0x180067fff  add     r10, r12
0x180068002  sub     rdi, r15
0x180068005  sub     rsi, r15
0x180068008  jnz     short loc_180067FEB
0x18006800a  test    rsi, rsi
0x18006800d  lea     rax, [r10-2]
0x180068011  cmovnz  rax, r10
0x180068015  neg     rsi
0x180068018  sbb     edi, edi
0x18006801a  not     edi
0x18006801c  and     edi, 8007007Ah
0x180068022  mov     [rax], bx
0x180068025  jmp     short loc_18006809D
0x180068027  mov     edi, 80070057h
0x18006802c  test    rsi, rsi
0x18006802f  jz      short loc_18006809D
0x180068031  mov     [r10], bx
0x180068035  jmp     short loc_18006809D
0x180068037  mov     edi, 8007000Eh
0x18006803c  jmp     short loc_18006809D
0x18006803e  mov     rcx, [rsp+300h+var_2C0]
0x180068043  mov     rax, r13
0x180068046  inc     rax
0x180068049  cmp     [rcx+rax*2], bx
0x18006804d  jnz     short loc_180068046
0x18006804f  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180068056  lea     rdi, [rax+1]
0x18006805a  mov     r12d, 2
0x180068060  mov     eax, r12d
0x180068063  mul     rdi
0x180068066  cmovb   rax, r13
0x18006806a  xor     edx, edx; dwFlags
0x18006806c  mov     r8, rax; dwBytes
0x18006806f  call    cs:__imp_HeapAlloc
0x180068076  nop     dword ptr [rax+rax+00h]
0x18006807b  mov     [r14+120h], rax
0x180068082  test    rax, rax
0x180068085  jz      loc_1800681F6
0x18006808b  mov     r8, [rsp+300h+var_2C0]; unsigned __int16 *
0x180068090  mov     rdx, rdi; unsigned __int64
0x180068093  mov     rcx, rax; unsigned __int16 *
0x180068096  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18006809b  mov     edi, eax
0x18006809d  test    edi, edi
0x18006809f  js      loc_1800681FB
0x1800680a5  mov     rdx, [r14+120h]; unsigned __int16 *
0x1800680ac  lea     r8, [r14+130h]; unsigned int *
0x1800680b3  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x1800680b8  mov     edi, eax
0x1800680ba  test    eax, eax
0x1800680bc  js      loc_1800681FB
0x1800680c2  movzx   edx, [rbp+200h+arg_28]; unsigned int
0x1800680c9  mov     rcx, r14; this
0x1800680cc  call    ?IsBinaryArchitectureExpectedForView@CComClassInfo@@AEBA_NK@Z; CComClassInfo::IsBinaryArchitectureExpectedForView(ulong)
0x1800680d1  test    al, al
0x1800680d3  jnz     loc_180068179
0x1800680d9  mov     eax, cs:dword_1801574B8
0x1800680df  mov     edi, 80040154h
0x1800680e4  test    eax, eax
0x1800680e6  jnz     short loc_1800680FC
0x1800680e8  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x1800680ee  jz      short loc_18006813D
0x1800680f0  mov     ecx, r15d
0x1800680f3  call    IsWppLevelEnabled
0x1800680f8  test    al, al
0x1800680fa  jz      short loc_18006813D
0x1800680fc  mov     rax, [r14+120h]
0x180068103  lea     rcx, [r14+70h]
0x180068107  mov     [rsp+300h+var_2C8], edi
0x18006810b  lea     rdx, aCcomclassinfoI_1; "CComClassInfo::InitializeSurrogateInfo"
0x180068112  mov     [rsp+300h+var_2D0], rax
0x180068117  mov     r9d, r15d
0x18006811a  mov     qword ptr [rsp+300h+var_2D8], rcx
0x18006811f  lea     rax, aClsidWsBinaryA; "CLSID:%ws Binary architecture doesn't m"...
0x180068126  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18006812d  mov     [rsp+300h+phkResult], rax
0x180068132  mov     r8d, 404h
0x180068138  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x18006813d  mov     r8, [r14+120h]; lpMem
0x180068144  mov     r15d, ebx
0x180068147  test    r8, r8
0x18006814a  jz      short loc_18006816D
0x18006814c  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x180068153  cmp     r8, rax
0x180068156  jz      short loc_18006816D
0x180068158  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x18006815f  xor     edx, edx; dwFlags
0x180068161  call    cs:__imp_HeapFree
0x180068168  nop     dword ptr [rax+rax+00h]
0x18006816d  mov     [r14+120h], rbx
0x180068174  jmp     loc_1800681FB
0x180068179  mov     rcx, [rsp+300h+var_2A8]
0x18006817e  lea     rdx, [rsp+300h+hKey]
0x180068183  mov     [rsp+300h+hKey], rbx
0x180068188  mov     rax, [rcx]
0x18006818b  mov     rax, [rax+0D8h]
0x180068192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068197  test    eax, eax
0x180068199  js      short loc_1800681F2
0x18006819b  mov     rcx, [rsp+300h+hKey]
0x1800681a0  mov     rax, r13
0x1800681a3  inc     rax
0x1800681a6  cmp     [rcx+rax*2], bx
0x1800681aa  jnz     short loc_1800681A3
0x1800681ac  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800681b3  lea     rdi, [rax+1]
0x1800681b7  mov     rax, r12
0x1800681ba  mul     rdi
0x1800681bd  cmovb   rax, r13
0x1800681c1  xor     edx, edx; dwFlags
0x1800681c3  mov     r8, rax; dwBytes
0x1800681c6  call    cs:__imp_HeapAlloc
0x1800681cd  nop     dword ptr [rax+rax+00h]
0x1800681d2  mov     [r14+128h], rax
0x1800681d9  test    rax, rax
0x1800681dc  jz      short loc_1800681F6
0x1800681de  mov     r8, [rsp+300h+hKey]; unsigned __int16 *
0x1800681e3  mov     rdx, rdi; unsigned __int64
0x1800681e6  mov     rcx, rax; unsigned __int16 *
0x1800681e9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800681ee  mov     edi, eax
0x1800681f0  jmp     short loc_1800681FB
  ... truncated ...
```
