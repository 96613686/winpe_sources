# CComClassInfo::InitializeSurrogateInfo(HKEY__ *,tagProcessType,bool,bool,ushort)

- ea: `0x180062934`
- end: `0x180063164`
- name: `?InitializeSurrogateInfo@CComClassInfo@@AEAAJPEAUHKEY__@@W4tagProcessType@@_N2G@Z`
- size: `2096`
- prototype: `int __high(HKEY, enum tagProcessType, bool, bool, unsigned __int16)`
- caller_count: `1`
- callee_count: `19`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18005e598`

## callees

- `0x18000acac`
- `0x18000ae40`
- `0x18000b310`
- `0x18000f1b8`
- `0x180034540`
- `0x1800418c0`
- `0x1800545e4`
- `0x180054b7c`
- `0x180062934`
- `0x180070740`
- `0x18007ced0`
- `0x180081210`
- `0x18008e98c`
- `0x180098b54`
- `0x1800b27e0`
- `0x1800b2d80`
- `0x1800b3128`
- `0x1800cbc2c`
- `0x18010b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006308d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006308d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062d21`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180062d21`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062a1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062d7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062f7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063030`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062a1d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062c2d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062d7d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180062f7a`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180063030`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062e36`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180062e36`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062e1a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180062e1a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180062f0b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180062f0b`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180062efc`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64Directory2W` at `0x180062efc`

## string_xrefs

- `0x180063057`: `DllHost.exe`
- `0x180062ce6`: `onecore\com\combase\catalog\class.cxx`
- `0x180062e8e`: `onecore\com\combase\catalog\class.cxx`
- `0x1800630b0`: `onecore\com\combase\catalog\class.cxx`
- `0x180063126`: `onecore\com\combase\catalog\class.cxx`
- `0x180062fc7`: `DllHost.exe /Processid:`
- `0x180063111`: `CLSID:%ws %!HRESULT!`
- `0x180062cdf`: `CLSID:%ws Binary architecture doesn't match registry view architecture. Surrogate:%ws %!HRESULT!`
- `0x1800630a3`: `CLSID:%ws %!WINERROR!`
- `0x180062ccb`: `CComClassInfo::InitializeSurrogateInfo`
- `0x1800630bc`: `CComClassInfo::InitializeSurrogateInfo`
- `0x18006310a`: `CComClassInfo::InitializeSurrogateInfo`

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
  int v10; // r12d
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
  LSTATUS v52; // r12d
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
      goto LABEL_117;
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
          ModuleArchitecture = CoGetModuleArchitecture(v54, (_DWORD *)(a1 + 304));
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
        goto LABEL_113;
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
          _report_rangecheckfailure(v58);
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
        goto LABEL_112;
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
          goto LABEL_117;
        }
LABEL_112:
        ExeArchitectureFromRegString = -2147024882;
      }
LABEL_117:
      *(_DWORD *)(a1 + 224) |= 4u;
LABEL_118:
      if ( ExeArchitectureFromRegString == -2147024894 )
      {
        return 0;
      }
      else if ( ExeArchitectureFromRegString < 0
             && (dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0)) )
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
LABEL_113:
    if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
    goto LABEL_117;
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
      goto LABEL_78;
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
        goto LABEL_77;
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
      goto LABEL_78;
    ExeArchitectureFromRegString = CComClassInfo::GetExeArchitectureFromRegString(
                                     v15,
                                     *(const unsigned __int16 **)(a1 + 288),
                                     (unsigned int *)(a1 + 304));
    if ( ExeArchitectureFromRegString < 0 )
      goto LABEL_78;
    if ( a6 && *(_DWORD *)(a1 + 304) != a6 )
    {
      ExeArchitectureFromRegString = -2147221164;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(1) )
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
LABEL_78:
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
      if ( !v10 )
        goto LABEL_118;
      goto LABEL_117;
    }
    hKey = 0;
    if ( (*(int (__fastcall **)(__int64, HKEY *))(*(_QWORD *)v75 + 216LL))(v75, &hKey) < 0 )
    {
      ExeArchitectureFromRegString = 0;
      goto LABEL_78;
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
      goto LABEL_78;
    }
LABEL_77:
    ExeArchitectureFromRegString = -2147024882;
    goto LABEL_78;
  }
  return (unsigned int)ExeArchitectureFromRegString;
}

```

## disassembly

```asm
0x180062934  mov     [rsp-8+arg_10], rbx
0x180062939  push    rbp
0x18006293a  push    rsi
0x18006293b  push    rdi
0x18006293c  push    r12
0x18006293e  push    r13
0x180062940  push    r14
0x180062942  push    r15
0x180062944  lea     rbp, [rsp-1D0h]
0x18006294c  sub     rsp, 2D0h
0x180062953  mov     rax, cs:__security_cookie
0x18006295a  xor     rax, rsp
0x18006295d  mov     [rbp+200h+var_40], rax
0x180062964  xor     ebx, ebx
0x180062966  mov     r13, rdx
0x180062969  mov     r14, rcx
0x18006296c  cmp     r8d, 3
0x180062970  jnz     loc_180062DD5
0x180062976  mov     rcx, [rcx+68h]
0x18006297a  mov     [rsp+300h+var_2A8], rbx
0x18006297f  test    rcx, rcx
0x180062982  jz      loc_180062DCB
0x180062988  mov     rax, [rcx]
0x18006298b  lea     r8, [rsp+300h+var_2A8]
0x180062990  lea     rdx, _GUID_5b0300bc_3a64_4bfe_9a06_ee2bcce72680
0x180062997  mov     rax, [rax]
0x18006299a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006299f  mov     edi, eax
0x1800629a1  test    eax, eax
0x1800629a3  js      loc_180063132
0x1800629a9  mov     rcx, [rsp+300h+var_2A8]
0x1800629ae  lea     r8, [rsp+300h+var_2C0]
0x1800629b3  mov     [rsp+300h+var_2C0], rbx
0x1800629b8  lea     rdx, [rsp+300h+var_2B8]
0x1800629bd  mov     dword ptr [rsp+300h+var_2B8], ebx
0x1800629c1  lea     r12d, [rbx+1]
0x1800629c5  mov     rax, [rcx]
0x1800629c8  mov     rax, [rax+0D0h]
0x1800629cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800629d4  mov     edi, eax
0x1800629d6  test    eax, eax
0x1800629d8  js      loc_180062DAC
0x1800629de  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800629e2  cmp     dword ptr [rsp+300h+var_2B8], ebx
0x1800629e6  jnz     loc_180062BFC
0x1800629ec  mov     rax, [rsp+300h+var_2C0]
0x1800629f1  mov     rsi, r13
0x1800629f4  inc     rsi
0x1800629f7  cmp     [rax+rsi*2], bx
0x1800629fb  jnz     short loc_1800629F4
0x1800629fd  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062a04  mov     r15d, 2
0x180062a0a  mov     eax, r15d
0x180062a0d  add     rsi, 33h ; '3'
0x180062a11  mul     rsi
0x180062a14  cmovb   rax, r13
0x180062a18  xor     edx, edx; dwFlags
0x180062a1a  mov     r8, rax; dwBytes
0x180062a1d  call    cs:__imp_HeapAlloc
0x180062a23  mov     [r14+120h], rax
0x180062a2a  mov     r10, rax
0x180062a2d  test    rax, rax
0x180062a30  jz      loc_180062BF5
0x180062a36  mov     edi, 7FFFFFFEh
0x180062a3b  test    rsi, rsi
0x180062a3e  jz      loc_180062B16
0x180062a44  cmp     rsi, 7FFFFFFFh
0x180062a4b  jbe     short loc_180062A52
0x180062a4d  mov     [rax], bx
0x180062a50  jmp     short loc_180062AA9
0x180062a52  mov     rcx, [rsp+300h+var_2C0]
0x180062a57  mov     rax, rdi
0x180062a5a  mov     rdx, rsi
0x180062a5d  mov     r8, r10
0x180062a60  mov     r9, rbx
0x180062a63  test    rax, rax
0x180062a66  jz      short loc_180062A87
0x180062a68  movzx   r11d, word ptr [rcx]
0x180062a6c  test    r11w, r11w
0x180062a70  jz      short loc_180062A87
0x180062a72  mov     [r8], r11w
0x180062a76  add     rcx, r15
0x180062a79  add     r8, r15
0x180062a7c  sub     rax, r12
0x180062a7f  add     r9, r12
0x180062a82  sub     rdx, r12
0x180062a85  jnz     short loc_180062A63
0x180062a87  test    rdx, rdx
0x180062a8a  lea     rcx, [r9-1]
0x180062a8e  lea     rax, [r8-2]
0x180062a92  cmovnz  rcx, r9
0x180062a96  cmovnz  rax, r8
0x180062a9a  sub     rsi, rcx
0x180062a9d  mov     [rax], bx
0x180062aa0  lea     r10, [r10+rcx*2]
0x180062aa4  test    rsi, rsi
0x180062aa7  jz      short loc_180062B16
0x180062aa9  cmp     rsi, 7FFFFFFFh
0x180062ab0  ja      short loc_180062B0D
0x180062ab2  test    rsi, rsi
0x180062ab5  jz      short loc_180062B16
0x180062ab7  mov     rax, rdi
0x180062aba  lea     rcx, SubStr; " "
0x180062ac1  mov     rdx, rsi
0x180062ac4  mov     r8, rbx
0x180062ac7  mov     r11, r10
0x180062aca  test    rax, rax
0x180062acd  jz      short loc_180062AEE
0x180062acf  movzx   r9d, word ptr [rcx]
0x180062ad3  test    r9w, r9w
0x180062ad7  jz      short loc_180062AEE
0x180062ad9  mov     [r10], r9w
0x180062add  add     rcx, r15
0x180062ae0  add     r10, r15
0x180062ae3  sub     rax, r12
0x180062ae6  add     r8, r12
0x180062ae9  sub     rdx, r12
0x180062aec  jnz     short loc_180062ACA
0x180062aee  test    rdx, rdx
0x180062af1  lea     rax, [r10-2]
0x180062af5  lea     rcx, [r8-1]
0x180062af9  cmovnz  rax, r10
0x180062afd  cmovnz  rcx, r8
0x180062b01  sub     rsi, rcx
0x180062b04  mov     [rax], bx
0x180062b07  lea     r10, [r11+rcx*2]
0x180062b0b  jmp     short loc_180062B16
0x180062b0d  test    rsi, rsi
0x180062b10  jz      short loc_180062B16
0x180062b12  mov     [r10], bx
0x180062b16  lea     rcx, [r14+40h]; struct _GUID *
0x180062b1a  mov     r8d, 27h ; '''; int
0x180062b20  lea     rdx, [rsp+300h+var_2A0]; unsigned __int16 *
0x180062b25  call    ?wStringFromGUID2@@YAHAEBU_GUID@@PEAGH@Z; wStringFromGUID2(_GUID const &,ushort *,int)
0x180062b2a  test    rsi, rsi
0x180062b2d  jz      loc_180062BE5
0x180062b33  cmp     rsi, 7FFFFFFFh
0x180062b3a  jbe     short loc_180062B42
0x180062b3c  mov     [r10], bx
0x180062b40  jmp     short loc_180062B99
0x180062b42  mov     rax, rdi
0x180062b45  lea     rcx, [rsp+300h+var_2A0]
0x180062b4a  mov     rdx, rsi
0x180062b4d  mov     r8, r10
0x180062b50  mov     r9, rbx
0x180062b53  test    rax, rax
0x180062b56  jz      short loc_180062B77
0x180062b58  movzx   r11d, word ptr [rcx]
0x180062b5c  test    r11w, r11w
0x180062b60  jz      short loc_180062B77
0x180062b62  mov     [r8], r11w
0x180062b66  add     rcx, r15
0x180062b69  add     r8, r15
0x180062b6c  sub     rax, r12
0x180062b6f  add     r9, r12
0x180062b72  sub     rdx, r12
0x180062b75  jnz     short loc_180062B53
0x180062b77  test    rdx, rdx
0x180062b7a  lea     rcx, [r9-1]
0x180062b7e  lea     rax, [r8-2]
0x180062b82  cmovnz  rcx, r9
0x180062b86  cmovnz  rax, r8
0x180062b8a  sub     rsi, rcx
0x180062b8d  mov     [rax], bx
0x180062b90  lea     r10, [r10+rcx*2]
0x180062b94  test    rsi, rsi
0x180062b97  jz      short loc_180062BE5
0x180062b99  cmp     rsi, 7FFFFFFFh
0x180062ba0  ja      short loc_180062BE5
0x180062ba2  lea     rax, ?g_wszEmbedding@@3QBGB; " -Embedding"
0x180062ba9  test    rdi, rdi
0x180062bac  jz      short loc_180062BC8
0x180062bae  movzx   ecx, word ptr [rax]
0x180062bb1  test    cx, cx
0x180062bb4  jz      short loc_180062BC8
0x180062bb6  mov     [r10], cx
0x180062bba  add     rax, r15
0x180062bbd  add     r10, r15
0x180062bc0  sub     rdi, r12
0x180062bc3  sub     rsi, r12
0x180062bc6  jnz     short loc_180062BA9
0x180062bc8  test    rsi, rsi
0x180062bcb  lea     rax, [r10-2]
0x180062bcf  cmovnz  rax, r10
0x180062bd3  neg     rsi
0x180062bd6  sbb     edi, edi
0x180062bd8  not     edi
0x180062bda  and     edi, 8007007Ah
0x180062be0  mov     [rax], bx
0x180062be3  jmp     short loc_180062C55
0x180062be5  mov     edi, 80070057h
0x180062bea  test    rsi, rsi
0x180062bed  jz      short loc_180062C55
0x180062bef  mov     [r10], bx
0x180062bf3  jmp     short loc_180062C55
0x180062bf5  mov     edi, 8007000Eh
0x180062bfa  jmp     short loc_180062C55
0x180062bfc  mov     rcx, [rsp+300h+var_2C0]
0x180062c01  mov     rax, r13
0x180062c04  inc     rax
0x180062c07  cmp     [rcx+rax*2], bx
0x180062c0b  jnz     short loc_180062C04
0x180062c0d  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062c14  lea     rdi, [rax+1]
0x180062c18  mov     r15d, 2
0x180062c1e  mov     eax, r15d
0x180062c21  mul     rdi
0x180062c24  cmovb   rax, r13
0x180062c28  xor     edx, edx; dwFlags
0x180062c2a  mov     r8, rax; dwBytes
0x180062c2d  call    cs:__imp_HeapAlloc
0x180062c33  mov     [r14+120h], rax
0x180062c3a  test    rax, rax
0x180062c3d  jz      loc_180062DA7
0x180062c43  mov     r8, [rsp+300h+var_2C0]; unsigned __int16 *
0x180062c48  mov     rdx, rdi; unsigned __int64
0x180062c4b  mov     rcx, rax; unsigned __int16 *
0x180062c4e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062c53  mov     edi, eax
0x180062c55  test    edi, edi
0x180062c57  js      loc_180062DAC
0x180062c5d  mov     rdx, [r14+120h]; unsigned __int16 *
0x180062c64  lea     rsi, [r14+130h]
0x180062c6b  mov     r8, rsi; unsigned int *
0x180062c6e  call    ?GetExeArchitectureFromRegString@CComClassInfo@@AEAAJPEBGPEAK@Z; CComClassInfo::GetExeArchitectureFromRegString(ushort const *,ulong *)
0x180062c73  mov     edi, eax
0x180062c75  test    eax, eax
0x180062c77  js      loc_180062DAC
0x180062c7d  cmp     [rbp+200h+arg_28], bx
0x180062c84  jz      loc_180062D30
0x180062c8a  movzx   eax, [rbp+200h+arg_28]
0x180062c91  cmp     [rsi], eax
0x180062c93  jz      loc_180062D30
0x180062c99  mov     eax, cs:dword_18014E4B8
0x180062c9f  mov     edi, 80040154h
0x180062ca4  test    eax, eax
0x180062ca6  jnz     short loc_180062CBC
0x180062ca8  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180062cae  jz      short loc_180062CFD
0x180062cb0  mov     ecx, r12d
0x180062cb3  call    IsWppLevelEnabled
0x180062cb8  test    al, al
0x180062cba  jz      short loc_180062CFD
0x180062cbc  mov     rax, [r14+120h]
0x180062cc3  lea     rcx, [r14+70h]
0x180062cc7  mov     [rsp+300h+var_2C8], edi
0x180062ccb  lea     rdx, aCcomclassinfoI_1; "CComClassInfo::InitializeSurrogateInfo"
0x180062cd2  mov     [rsp+300h+var_2D0], rax
0x180062cd7  mov     r9d, r12d
0x180062cda  mov     qword ptr [rsp+300h+var_2D8], rcx
0x180062cdf  lea     rax, aClsidWsBinaryA; "CLSID:%ws Binary architecture doesn't m"...
0x180062ce6  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180062ced  mov     [rsp+300h+phkResult], rax
0x180062cf2  mov     r8d, 404h
0x180062cf8  call    ??$ComTraceMessageT@PEAGPEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAG3J@Z; ComTraceMessageT<ushort *,ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,ushort *,long)
0x180062cfd  mov     r8, [r14+120h]; lpMem
0x180062d04  mov     r12d, ebx
0x180062d07  test    r8, r8
0x180062d0a  jz      short loc_180062D27
0x180062d0c  lea     rax, ?g_wszEmptyString@@3QBGB; ushort const near * const g_wszEmptyString
0x180062d13  cmp     r8, rax
0x180062d16  jz      short loc_180062D27
0x180062d18  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062d1f  xor     edx, edx; dwFlags
0x180062d21  call    cs:__imp_HeapFree
0x180062d27  mov     [r14+120h], rbx
0x180062d2e  jmp     short loc_180062DAC
0x180062d30  mov     rcx, [rsp+300h+var_2A8]
0x180062d35  lea     rdx, [rsp+300h+hKey]
0x180062d3a  mov     [rsp+300h+hKey], rbx
0x180062d3f  mov     rax, [rcx]
0x180062d42  mov     rax, [rax+0D8h]
0x180062d49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180062d4e  test    eax, eax
0x180062d50  js      short loc_180062DA3
0x180062d52  mov     rcx, [rsp+300h+hKey]
0x180062d57  mov     rax, r13
0x180062d5a  inc     rax
0x180062d5d  cmp     [rcx+rax*2], bx
0x180062d61  jnz     short loc_180062D5A
0x180062d63  mov     rcx, cs:?g_hHeap@@3QEAXEA; hHeap
0x180062d6a  lea     rdi, [rax+1]
0x180062d6e  mov     rax, r15
0x180062d71  mul     rdi
0x180062d74  cmovb   rax, r13
0x180062d78  xor     edx, edx; dwFlags
0x180062d7a  mov     r8, rax; dwBytes
0x180062d7d  call    cs:__imp_HeapAlloc
0x180062d83  mov     [r14+128h], rax
0x180062d8a  test    rax, rax
0x180062d8d  jz      short loc_180062DA7
0x180062d8f  mov     r8, [rsp+300h+hKey]; unsigned __int16 *
0x180062d94  mov     rdx, rdi; unsigned __int64
0x180062d97  mov     rcx, rax; unsigned __int16 *
0x180062d9a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180062d9f  mov     edi, eax
0x180062da1  jmp     short loc_180062DAC
0x180062da3  mov     edi, ebx
0x180062da5  jmp     short loc_180062DAC
0x180062da7  mov     edi, 8007000Eh
  ... truncated ...
```
