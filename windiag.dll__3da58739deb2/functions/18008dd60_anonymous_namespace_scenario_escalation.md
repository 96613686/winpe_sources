# _anonymous_namespace_::scenario_escalation

- ea: `0x18008dd60`
- end: `0x18008e4bf`
- name: `_anonymous_namespace_::scenario_escalation`
- size: `1887`
- prototype: `__int64 __fastcall(struct lua_State *)`
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180002fdc`
- `0x180004510`
- `0x1800054e4`
- `0x180005508`
- `0x180005520`
- `0x180006690`
- `0x180006b00`
- `0x180006c50`
- `0x180006d00`
- `0x180006d40`
- `0x180008430`
- `0x180037e84`
- `0x18003af08`
- `0x18003b0bc`
- `0x18003d720`
- `0x18003d738`
- `0x180040f94`
- `0x180041564`
- `0x1800416a0`
- `0x180044a38`
- `0x18004a1b4`
- `0x18004faec`
- `0x180052740`
- `0x1800571a4`
- `0x1800673c8`
- `0x180080944`
- `0x18008447c`
- `0x18008d254`
- `0x18008d4cc`
- `0x18008d894`
- `0x18008dd60`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008df4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e272`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008dea0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008df4d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18008e272`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008de6f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18008de6f`
- `RPCRT4!UuidFromStringA` at `0x18008ddd9`
- `RPCRT4!UuidFromStringA` at `0x18008ddd9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008e38b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008e3d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008e38b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18008e3d8`

## string_xrefs

- `0x18008de68`: `utcapi.dll`
- `0x18008de96`: `UtcCreateSessionHandle`
- `0x18008dff2`: `%TEMP%`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall anonymous_namespace_::scenario_escalation(struct lua_State *a1)
{
  unsigned __int8 *v2; // rsi
  __int64 v3; // r8
  _WORD *v4; // rbx
  HMODULE Library; // rax
  const char *v6; // r9
  __int64 v7; // rdx
  int LastError; // eax
  FARPROC ProcAddress; // rax
  __int64 v10; // rbx
  FARPROC v11; // rax
  const char *v12; // r9
  __int64 v13; // rax
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 v16; // r8
  __int128 *v17; // r9
  __int64 v18; // rax
  __int64 v19; // rax
  __int128 *v20; // rdx
  __int128 *v21; // rcx
  __int64 v22; // rax
  unsigned __int64 *v23; // r9
  __int128 *v24; // rdx
  __int128 *v25; // rcx
  const wchar_t *v26; // rax
  __int128 *v27; // rbx
  _QWORD *v28; // rsi
  FARPROC v29; // r10
  const char *v30; // r9
  int v31; // eax
  int *v32; // rbx
  const char *v33; // rdx
  int v35; // [rsp+60h] [rbp-A0h] BYREF
  int v36; // [rsp+64h] [rbp-9Ch]
  void ***v37; // [rsp+68h] [rbp-98h]
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v39; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v40[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h] BYREF
  HMODULE hModule; // [rsp+98h] [rbp-68h]
  __int64 v43; // [rsp+A0h] [rbp-60h]
  __int64 v44; // [rsp+A8h] [rbp-58h]
  __int64 v45; // [rsp+B0h] [rbp-50h]
  __int64 v46; // [rsp+B8h] [rbp-48h]
  __int64 v47; // [rsp+C0h] [rbp-40h]
  INT_PTR (__stdcall *v48)(); // [rsp+C8h] [rbp-38h]
  INT_PTR (__stdcall *v49)(); // [rsp+D0h] [rbp-30h]
  __int64 v50; // [rsp+D8h] [rbp-28h]
  __int64 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+E8h] [rbp-18h]
  __int64 v53; // [rsp+F0h] [rbp-10h]
  __int64 v54; // [rsp+F8h] [rbp-8h]
  _QWORD v55[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v56; // [rsp+110h] [rbp+10h] BYREF
  __int64 v57; // [rsp+120h] [rbp+20h]
  unsigned __int64 v58; // [rsp+128h] [rbp+28h]
  __int128 v59; // [rsp+130h] [rbp+30h] BYREF
  __int128 v60; // [rsp+140h] [rbp+40h]
  void *v61[2]; // [rsp+150h] [rbp+50h] BYREF
  __int64 v62; // [rsp+160h] [rbp+60h]
  unsigned __int64 v63; // [rsp+168h] [rbp+68h]
  bool v64[4]; // [rsp+170h] [rbp+70h] BYREF
  int v65; // [rsp+174h] [rbp+74h]
  int v66; // [rsp+178h] [rbp+78h]
  char v67; // [rsp+17Ch] [rbp+7Ch]
  __int128 v68; // [rsp+180h] [rbp+80h] BYREF
  __int64 v69; // [rsp+190h] [rbp+90h]
  unsigned __int64 v70; // [rsp+198h] [rbp+98h]
  char v71; // [rsp+1A0h] [rbp+A0h]
  UUID Uuid; // [rsp+1A8h] [rbp+A8h] BYREF
  char *v73[4]; // [rsp+1C8h] [rbp+C8h] BYREF
  char v74; // [rsp+1E8h] [rbp+E8h]
  _QWORD v75[4]; // [rsp+1F0h] [rbp+F0h] BYREF
  _BYTE v76[32]; // [rsp+210h] [rbp+110h] BYREF
  _BYTE pExceptionObject[1072]; // [rsp+230h] [rbp+130h] BYREF
  _BYTE v78[128]; // [rsp+660h] [rbp+560h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+728h] [rbp+628h]

  v2 = (unsigned __int8 *)luaL_checklstring(a1, 1, 0);
  *(_OWORD *)v61 = 0;
  v62 = 0;
  v63 = 0;
  std::wstring::_Construct<1,unsigned short const *>(v61, L"StableId\\");
  Uuid = 0;
  if ( !UuidFromStringA(v2, &Uuid) )
  {
    if ( v63 < 0xB )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        v61,
        11,
        v3,
        L"ScenarioId\\");
    }
    else
    {
      v4 = v61[0];
      v62 = 11;
      memmove_0(v61[0], L"ScenarioId\\", 0x16u);
      v4[11] = 0;
    }
  }
  v41 = 0;
  v43 = 0;
  v44 = 0;
  v45 = 0;
  v46 = 0;
  v47 = 0;
  v48 = 0;
  v49 = 0;
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v54 = 0;
  Library = LoadLibraryExW(L"utcapi.dll", 0, 0x800u);
  hModule = Library;
  if ( !Library )
  {
    v7 = 88;
LABEL_7:
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v7,
                  (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
                  v6);
    goto LABEL_11;
  }
  ProcAddress = GetProcAddress(Library, "UtcCreateSessionHandle");
  if ( !ProcAddress )
  {
    v7 = 91;
    goto LABEL_7;
  }
  LastError = ((__int64 (__fastcall *)(__int64 *))ProcAddress)(&v41);
LABEL_11:
  if ( LastError < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      LastError,
      0,
      "[%s:%d] failed; ",
      "scenario_escalation",
      128);
    throw (windiag::system_exception *)pExceptionObject;
  }
  v64[0] = (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl'::`2'::impl) == 0;
  v65 = 1;
  v66 = 60;
  v67 = 0;
  v68 = 0;
  v10 = 0;
  v69 = 0;
  v70 = 7;
  LOWORD(v68) = 0;
  v71 = 1;
  if ( (int)lua_gettop(a1) <= 1 || (anonymous_namespace_::escalation_options::parse(v64, a1), v10 = v69, v71) )
  {
    v11 = v49;
    if ( v49 || (v11 = GetProcAddress(hModule, "UtcDownloadLatestSettingsForNamespaceEx"), (v49 = v11) != 0) )
      ((void (__fastcall *)(__int64, const wchar_t *, const wchar_t *, __int64, _DWORD, int, int))v11)(
        v41,
        L"windows",
        L"diag_ondemand",
        1,
        0,
        1,
        30000);
    else
      wil::details::in1diag3::Return_GetLastError(
        retaddr,
        (void *)0xC7,
        (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
        v12);
  }
  v13 = windiag::char_to_wstring(&v56, v2);
  std::operator+<unsigned short>(v75, v61, v13);
  std::wstring::~wstring(&v56);
  v35 = 0;
  v37 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
  v59 = 0;
  v60 = 0;
  std::wstring::_Construct<1,unsigned short const *>(&v59, L"%TEMP%", 6);
  if ( v10 )
  {
    v15 = windiag::char_to_wstring(v73, v2);
    if ( (unsigned __int64)(0x7FFFFFFFFFFFFFFELL - v10) < 2 )
      std::_Xlen_string();
    v17 = &v68;
    if ( v70 > 7 )
      v17 = (__int128 *)v68;
    std::wstring::wstring(&v56, v14, v16, v17, v10, L"\\{", 2);
    v18 = std::operator+<unsigned short>(v76, &v56, v15);
    v19 = std::operator+<unsigned short>(&Uuid, v18, 125);
    std::wstring::operator=(&v59, v19);
    std::wstring::~wstring(&Uuid);
    std::wstring::~wstring(v76);
    std::wstring::~wstring(&v56);
    std::wstring::~wstring(v73);
    v20 = &v59;
    if ( *((_QWORD *)&v60 + 1) > 7u )
      v20 = (__int128 *)v59;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v56, v20, (_QWORD)v60);
    v35 = 0;
    v37 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    v21 = &v56;
    if ( v58 > 7 )
      v21 = (__int128 *)v56;
    v22 = _std_fs_remove(v21);
    *(_QWORD *)&Uuid.Data1 = (unsigned __int8)v22;
    v35 = HIDWORD(v22);
    v36 = HIDWORD(v40[0]);
    v37 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    if ( HIDWORD(v22) == 145 )
      std::filesystem::_Remove_all_dir(
        (std::filesystem *)&v56,
        (const struct std::filesystem::path *)&v35,
        (struct std::error_code *)&Uuid,
        v23);
    std::wstring::~wstring(&v56);
    v24 = &v59;
    if ( *((_QWORD *)&v60 + 1) > 7u )
      v24 = (__int128 *)v59;
    v56 = 0;
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,unsigned short const *>(&v56, v24, (_QWORD)v60);
    v25 = &v56;
    if ( v58 > 7 )
      v25 = (__int128 *)v56;
    v35 = (unsigned __int64)_std_fs_remove(v25) >> 32;
    v36 = HIDWORD(v40[0]);
    v37 = &`std::_Immortalize_memcpy_image<std::_System_error_category>'::`2'::_Static;
    std::wstring::~wstring(&v56);
  }
  memset_0(v78, 0, sizeof(v78));
  _snwprintf_s<64>(v78, -1, L"%d", (unsigned int)(1000 * v66));
  v40[0] = L"_mutextimeout";
  v40[1] = L"_collectweretwlogs";
  v55[0] = v78;
  v26 = L"true";
  if ( !v67 )
    v26 = L"false";
  v55[1] = v26;
  pv = 0;
  v39 = 0;
  v27 = &v59;
  if ( *((_QWORD *)&v60 + 1) > 7u )
    v27 = (__int128 *)v59;
  v28 = v75;
  if ( v75[3] > 7u )
    v28 = (_QWORD *)v75[0];
  v29 = v48;
  if ( v48 || (v29 = GetProcAddress(hModule, "UtcEscalateScenarioEx"), (v48 = v29) != 0) )
    v31 = ((__int64 (__fastcall *)(__int64, _QWORD *, __int128 *, _QWORD, bool, int, int, _QWORD *, _QWORD *, LPVOID *, int *))v29)(
            v41,
            v28,
            v27,
            0,
            v64[0],
            v65,
            2,
            v40,
            v55,
            &pv,
            &v39);
  else
    v31 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0xB2,
            (unsigned int)"OneCore\\Internal\\Base\\inc\\utcapiwrapperex.h",
            v30);
  if ( v31 < 0 )
  {
    windiag::system_exception::system_exception(
      (windiag::system_exception *)pExceptionObject,
      v31,
      0,
      "[%s:%d] failed; ",
      "scenario_escalation",
      167);
    throw (windiag::system_exception *)pExceptionObject;
  }
  if ( v39 )
  {
    v32 = (int *)pv;
    lua_pushboolean(a1, *((_DWORD *)pv + 8) >= 0);
    if ( v32[8] >= 0 )
    {
      windiag::guid_to_string(v73, v32 + 4);
      if ( v74 )
      {
        v33 = (const char *)v73;
        if ( v73[3] > (char *)0xF )
          v33 = v73[0];
        lua_pushstring(a1, v33);
      }
      else
      {
        lua_pushnil(a1);
      }
      if ( v74 )
        std::string::~string(v73);
    }
    else
    {
      lua_pushinteger(a1, v32[8]);
    }
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(&v59);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(&v68);
    Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)&v41);
    std::wstring::~wstring(v61);
    return 2;
  }
  else
  {
    if ( pv )
      CoTaskMemFree(pv);
    std::wstring::~wstring(&v59);
    std::wstring::~wstring(v75);
    std::wstring::~wstring(&v68);
    Microsoft::Diagnostics::UtcApiWrapper::~UtcApiWrapper((Microsoft::Diagnostics::UtcApiWrapper *)&v41);
    std::wstring::~wstring(v61);
    return 0;
  }
}

```

## disassembly

```asm
0x18008dd60  push    rbp
0x18008dd62  push    rbx
0x18008dd63  push    rsi
0x18008dd64  push    rdi
0x18008dd65  push    r14
0x18008dd67  push    r15
0x18008dd69  lea     rbp, [rsp-5F8h]
0x18008dd71  sub     rsp, 6F8h
0x18008dd78  mov     rax, cs:__security_cookie
0x18008dd7f  xor     rax, rsp
0x18008dd82  mov     [rbp+620h+var_40], rax
0x18008dd89  mov     rdi, rcx
0x18008dd8c  xor     r14d, r14d
0x18008dd8f  xor     r8d, r8d; unsigned __int64 *
0x18008dd92  lea     r15d, [r14+1]
0x18008dd96  mov     edx, r15d; int
0x18008dd99  call    ?luaL_checklstring@@YAPEBDPEAUlua_State@@HPEA_K@Z; luaL_checklstring(lua_State *,int,unsigned __int64 *)
0x18008dd9e  mov     rsi, rax
0x18008dda1  xorps   xmm0, xmm0
0x18008dda4  movups  xmmword ptr [rbp+620h+var_5D0], xmm0
0x18008dda8  mov     [rbp+620h+var_5C0], r14
0x18008ddac  mov     [rbp+620h+var_5B8], r14
0x18008ddb0  lea     r8d, [r14+9]
0x18008ddb4  lea     rdx, aStableid; "StableId\\"
0x18008ddbb  lea     rcx, [rbp+620h+var_5D0]
0x18008ddbf  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008ddc4  nop
0x18008ddc5  xorps   xmm0, xmm0
0x18008ddc8  movups  xmmword ptr [rbp+620h+Uuid.Data1], xmm0
0x18008ddcf  lea     rdx, [rbp+620h+Uuid]; Uuid
0x18008ddd6  mov     rcx, rsi; StringUuid
0x18008ddd9  call    cs:__imp_UuidFromStringA
0x18008dddf  test    eax, eax
0x18008dde1  jnz     short loc_18008DE28
0x18008dde3  lea     edx, [rax+0Bh]
0x18008dde6  cmp     [rbp+620h+var_5B8], rdx
0x18008ddea  jb      short loc_18008DE18
0x18008ddec  lea     rbx, [rbp+620h+var_5D0]
0x18008ddf0  cmp     [rbp+620h+var_5B8], 7
0x18008ddf5  cmova   rbx, [rbp+620h+var_5D0]
0x18008ddfa  mov     [rbp+620h+var_5C0], rdx
0x18008ddfe  lea     r8d, [r14+16h]; Size
0x18008de02  lea     rdx, aScenarioid; "ScenarioId\\"
0x18008de09  mov     rcx, rbx; void *
0x18008de0c  call    memmove_0
0x18008de11  mov     [rbx+16h], r14w
0x18008de16  jmp     short loc_18008DE28
0x18008de18  lea     r9, aScenarioid; "ScenarioId\\"
0x18008de1f  lea     rcx, [rbp+620h+var_5D0]
0x18008de23  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x18008de28  mov     [rbp+620h+var_690], r14
0x18008de2c  mov     [rbp+620h+hModule], r14
0x18008de30  mov     [rbp+620h+var_680], r14
0x18008de34  mov     [rbp+620h+var_678], r14
0x18008de38  mov     [rbp+620h+var_670], r14
0x18008de3c  mov     [rbp+620h+var_668], r14
0x18008de40  mov     [rbp+620h+var_660], r14
0x18008de44  mov     [rbp+620h+var_658], r14
0x18008de48  mov     [rbp+620h+var_650], r14
0x18008de4c  mov     [rbp+620h+var_648], r14
0x18008de50  mov     [rbp+620h+var_640], r14
0x18008de54  mov     [rbp+620h+var_638], r14
0x18008de58  mov     [rbp+620h+var_630], r14
0x18008de5c  mov     [rbp+620h+var_628], r14
0x18008de60  xor     edx, edx; hFile
0x18008de62  mov     r8d, 800h; dwFlags
0x18008de68  lea     rcx, aUtcapiDll; "utcapi.dll"
0x18008de6f  call    cs:__imp_LoadLibraryExW
0x18008de75  mov     [rbp+620h+hModule], rax
0x18008de79  test    rax, rax
0x18008de7c  jnz     short loc_18008DE96
0x18008de7e  lea     edx, [rax+58h]; void *
0x18008de81  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008de88  mov     rcx, [rbp+628h]; this
0x18008de8f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008de94  jmp     short loc_18008DEB9
0x18008de96  lea     rdx, aUtccreatesessi; "UtcCreateSessionHandle"
0x18008de9d  mov     rcx, rax; hModule
0x18008dea0  call    cs:__imp_GetProcAddress
0x18008dea6  test    rax, rax
0x18008dea9  jnz     short loc_18008DEB0
0x18008deab  lea     edx, [rax+5Bh]
0x18008deae  jmp     short loc_18008DE81
0x18008deb0  lea     rcx, [rbp+620h+var_690]
0x18008deb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008deb9  test    eax, eax
0x18008debb  js      loc_18008E478
0x18008dec1  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_BugFixes4D@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D> `wil::Feature<__WilFeatureTraits_Feature_BugFixes4D>::GetImpl(void)'::`2'::impl
0x18008dec8  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_BugFixes4D@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_BugFixes4D>::__private_IsEnabled(void)
0x18008decd  test    al, al
0x18008decf  setz    [rbp+620h+var_5B0]
0x18008ded3  mov     [rbp+620h+var_5AC], r15d
0x18008ded7  mov     [rbp+620h+var_5A8], 3Ch ; '<'
0x18008dede  mov     [rbp+620h+var_5A4], r14b
0x18008dee2  xorps   xmm0, xmm0
0x18008dee5  movups  [rbp+620h+var_5A0], xmm0
0x18008deec  mov     rbx, r14
0x18008deef  mov     [rbp+620h+var_590], rbx
0x18008def6  mov     [rbp+620h+var_588], 7
0x18008df01  mov     word ptr [rbp+620h+var_5A0], r14w
0x18008df09  mov     [rbp+620h+var_580], r15b
0x18008df10  mov     rcx, rdi; struct lua_State *
0x18008df13  call    ?lua_gettop@@YAHPEAUlua_State@@@Z; lua_gettop(lua_State *)
0x18008df18  cmp     eax, r15d
0x18008df1b  jle     short loc_18008DF39
0x18008df1d  mov     rdx, rdi
0x18008df20  lea     rcx, [rbp+620h+var_5B0]
0x18008df24  call    _anonymous_namespace___escalation_options__parse
0x18008df29  mov     rbx, [rbp+620h+var_590]
0x18008df30  cmp     [rbp+620h+var_580], r14b
0x18008df37  jz      short loc_18008DFA2
0x18008df39  mov     rax, [rbp+620h+var_650]
0x18008df3d  test    rax, rax
0x18008df40  jnz     short loc_18008DF76
0x18008df42  lea     rdx, aUtcdownloadlat; "UtcDownloadLatestSettingsForNamespaceEx"
0x18008df49  mov     rcx, [rbp+620h+hModule]; hModule
0x18008df4d  call    cs:__imp_GetProcAddress
0x18008df53  mov     [rbp+620h+var_650], rax
0x18008df57  test    rax, rax
0x18008df5a  jnz     short loc_18008DF76
0x18008df5c  mov     rcx, [rbp+628h]; this
0x18008df63  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008df6a  mov     edx, 0C7h; void *
0x18008df6f  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008df74  jmp     short loc_18008DFA2
0x18008df76  mov     dword ptr [rsp+720h+var_6F0], 7530h
0x18008df7e  mov     dword ptr [rsp+720h+var_6F8], r15d
0x18008df83  mov     dword ptr [rsp+720h+var_700], r14d
0x18008df88  mov     r9d, r15d
0x18008df8b  lea     r8, aDiagOndemand; "diag_ondemand"
0x18008df92  lea     rdx, aWindows; "windows"
0x18008df99  mov     rcx, [rbp+620h+var_690]
0x18008df9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008dfa2  mov     rdx, rsi
0x18008dfa5  lea     rcx, [rbp+620h+var_610]
0x18008dfa9  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008dfae  nop
0x18008dfaf  mov     r8, rax
0x18008dfb2  lea     rdx, [rbp+620h+var_5D0]
0x18008dfb6  lea     rcx, [rbp+620h+var_530]
0x18008dfbd  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@AEBV10@$$QEAV10@@Z; std::operator+<ushort>(std::wstring const &,std::wstring &&)
0x18008dfc2  nop
0x18008dfc3  lea     rcx, [rbp+620h+var_610]
0x18008dfc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008dfcc  mov     [rsp+720h+var_6C0], r14d
0x18008dfd1  lea     rax, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18008dfd8  mov     [rsp+720h+var_6B8], rax
0x18008dfdd  xorps   xmm0, xmm0
0x18008dfe0  movups  [rbp+620h+var_5F0], xmm0
0x18008dfe4  xorps   xmm1, xmm1
0x18008dfe7  movdqu  [rbp+620h+var_5E0], xmm1
0x18008dfec  mov     r8d, 6
0x18008dff2  lea     rdx, aTemp; "%TEMP%"
0x18008dff9  lea     rcx, [rbp+620h+var_5F0]
0x18008dffd  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008e002  nop
0x18008e003  mov     r15d, 2
0x18008e009  test    rbx, rbx
0x18008e00c  jz      loc_18008E1C1
0x18008e012  mov     rdx, rsi
0x18008e015  lea     rcx, [rbp+620h+var_558]
0x18008e01c  call    ?char_to_wstring@windiag@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBD@Z; windiag::char_to_wstring(char const *)
0x18008e021  mov     rsi, rax
0x18008e024  mov     rcx, 7FFFFFFFFFFFFFFEh
0x18008e02e  sub     rcx, rbx
0x18008e031  cmp     rcx, r15
0x18008e034  jb      loc_18008E4B9
0x18008e03a  lea     r9, [rbp+620h+var_5A0]
0x18008e041  cmp     [rbp+620h+var_588], 7
0x18008e049  cmova   r9, qword ptr [rbp+620h+var_5A0]
0x18008e051  mov     [rsp+720h+var_6F0], r15
0x18008e056  lea     rax, asc_1800A87E8; "\\{"
0x18008e05d  mov     [rsp+720h+var_6F8], rax
0x18008e062  mov     [rsp+720h+var_700], rbx
0x18008e067  lea     rcx, [rbp+620h+var_610]
0x18008e06b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@U_String_constructor_concat_tag@1@AEBV01@QEBG_K23@Z; std::wstring::wstring(std::_String_constructor_concat_tag,std::wstring const &,ushort const * const,unsigned __int64,ushort const * const,unsigned __int64)
0x18008e070  nop
0x18008e071  mov     r8, rsi
0x18008e074  lea     rdx, [rbp+620h+var_610]
0x18008e078  lea     rcx, [rbp+620h+var_510]
0x18008e07f  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@0@Z; std::operator+<ushort>(std::wstring &&,std::wstring &&)
0x18008e084  nop
0x18008e085  lea     r8d, [r15+7Bh]
0x18008e089  mov     rdx, rax
0x18008e08c  lea     rcx, [rbp+620h+Uuid]
0x18008e093  call    ??$?HGU?$char_traits@G@std@@V?$allocator@G@1@@std@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAV10@G@Z; std::operator+<ushort>(std::wstring &&,ushort)
0x18008e098  mov     rdx, rax
0x18008e09b  lea     rcx, [rbp+620h+var_5F0]
0x18008e09f  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18008e0a4  lea     rcx, [rbp+620h+Uuid]
0x18008e0ab  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e0b0  nop
0x18008e0b1  lea     rcx, [rbp+620h+var_510]
0x18008e0b8  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e0bd  nop
0x18008e0be  lea     rcx, [rbp+620h+var_610]
0x18008e0c2  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e0c7  nop
0x18008e0c8  lea     rcx, [rbp+620h+var_558]
0x18008e0cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e0d4  lea     rdx, [rbp+620h+var_5F0]
0x18008e0d8  cmp     qword ptr [rbp+620h+var_5E0+8], 7
0x18008e0dd  cmova   rdx, qword ptr [rbp+620h+var_5F0]
0x18008e0e2  xorps   xmm0, xmm0
0x18008e0e5  movups  [rbp+620h+var_610], xmm0
0x18008e0e9  mov     [rbp+620h+var_600], r14
0x18008e0ed  mov     [rbp+620h+var_5F8], r14
0x18008e0f1  mov     r8, qword ptr [rbp+620h+var_5E0]
0x18008e0f5  lea     rcx, [rbp+620h+var_610]
0x18008e0f9  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008e0fe  nop
0x18008e0ff  mov     [rsp+720h+var_6C0], r14d
0x18008e104  lea     rbx, ?_Static@?1???$_Immortalize_memcpy_image@V_System_error_category@std@@@std@@YAAEBV_System_error_category@1@XZ@4U?$_Constexpr_immortalize_impl@V_System_error_category@std@@@1@A; std::_Constexpr_immortalize_impl<std::_System_error_category> `std::_Immortalize_memcpy_image<std::_System_error_category>(void)'::`2'::_Static
0x18008e10b  mov     [rsp+720h+var_6B8], rbx
0x18008e110  lea     rcx, [rbp+620h+var_610]
0x18008e114  cmp     [rbp+620h+var_5F8], 7
0x18008e119  cmova   rcx, qword ptr [rbp+620h+var_610]
0x18008e11e  call    __std_fs_remove
0x18008e123  movzx   ecx, al
0x18008e126  mov     qword ptr [rbp+620h+Uuid.Data1], rcx
0x18008e12d  shr     rax, 20h
0x18008e131  mov     [rsp+720h+var_6C0], eax
0x18008e135  mov     ecx, [rbp+620h+var_69C]
0x18008e138  mov     [rsp+720h+var_6BC], ecx
0x18008e13c  mov     [rsp+720h+var_6B8], rbx
0x18008e141  cmp     eax, 91h
0x18008e146  jnz     short loc_18008E15E
0x18008e148  lea     r8, [rbp+620h+Uuid]; struct std::error_code *
0x18008e14f  lea     rdx, [rsp+720h+var_6C0]; struct std::filesystem::path *
0x18008e154  lea     rcx, [rbp+620h+var_610]; this
0x18008e158  call    ?_Remove_all_dir@filesystem@std@@YAXAEBVpath@12@AEAVerror_code@2@AEA_K@Z; std::filesystem::_Remove_all_dir(std::filesystem::path const &,std::error_code &,unsigned __int64 &)
0x18008e15d  nop
0x18008e15e  lea     rcx, [rbp+620h+var_610]
0x18008e162  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e167  lea     rdx, [rbp+620h+var_5F0]
0x18008e16b  cmp     qword ptr [rbp+620h+var_5E0+8], 7
0x18008e170  cmova   rdx, qword ptr [rbp+620h+var_5F0]
0x18008e175  xorps   xmm0, xmm0
0x18008e178  movups  [rbp+620h+var_610], xmm0
0x18008e17c  mov     [rbp+620h+var_600], r14
0x18008e180  mov     [rbp+620h+var_5F8], r14
0x18008e184  mov     r8, qword ptr [rbp+620h+var_5E0]
0x18008e188  lea     rcx, [rbp+620h+var_610]
0x18008e18c  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x18008e191  lea     rcx, [rbp+620h+var_610]
0x18008e195  cmp     [rbp+620h+var_5F8], 7
0x18008e19a  cmova   rcx, qword ptr [rbp+620h+var_610]
0x18008e19f  call    __std_fs_remove
0x18008e1a4  shr     rax, 20h
0x18008e1a8  mov     [rsp+720h+var_6C0], eax
0x18008e1ac  mov     eax, [rbp+620h+var_69C]
0x18008e1af  mov     [rsp+720h+var_6BC], eax
0x18008e1b3  mov     [rsp+720h+var_6B8], rbx
0x18008e1b8  lea     rcx, [rbp+620h+var_610]
0x18008e1bc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18008e1c1  xor     edx, edx; Val
0x18008e1c3  mov     r8d, 80h; Size
0x18008e1c9  lea     rcx, [rbp+620h+var_C0]; void *
0x18008e1d0  call    memset_0
0x18008e1d5  imul    r9d, [rbp+620h+var_5A8], 3E8h
0x18008e1dd  lea     r8, aD; "%d"
0x18008e1e4  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18008e1e8  lea     rcx, [rbp+620h+var_C0]
0x18008e1ef  call    ??$_snwprintf_s@$0EA@@@YAHAEAY0EA@G_KPEBGZZ; _snwprintf_s<64>(ushort (&)[64],unsigned __int64,ushort const *,...)
0x18008e1f4  lea     rax, aMutextimeout; "_mutextimeout"
0x18008e1fb  mov     [rbp-80h], rax
0x18008e1ff  lea     rax, aCollectweretwl; "_collectweretwlogs"
0x18008e206  mov     [rbp+620h+var_698], rax
0x18008e20a  lea     rax, [rbp+620h+var_C0]
0x18008e211  mov     [rbp+620h+var_620], rax
0x18008e215  lea     rax, aTrue; "true"
0x18008e21c  lea     rcx, aFalse_0; "false"
0x18008e223  cmp     [rbp+620h+var_5A4], r14b
0x18008e227  cmovz   rax, rcx
0x18008e22b  mov     [rbp+620h+var_618], rax
0x18008e22f  mov     [rsp+720h+pv], r14
0x18008e234  mov     [rsp+720h+var_6A8], r14d
0x18008e239  lea     rbx, [rbp+620h+var_5F0]
0x18008e23d  cmp     qword ptr [rbp+620h+var_5E0+8], 7
0x18008e242  cmova   rbx, qword ptr [rbp+620h+var_5F0]
0x18008e247  lea     rsi, [rbp+620h+var_530]
0x18008e24e  cmp     [rbp+620h+var_518], 7
0x18008e256  cmova   rsi, [rbp+620h+var_530]
0x18008e25e  mov     r10, [rbp+620h+var_658]
0x18008e262  test    r10, r10
0x18008e265  jnz     short loc_18008E29E
0x18008e267  lea     rdx, aUtcescalatesce; "UtcEscalateScenarioEx"
0x18008e26e  mov     rcx, [rbp+620h+hModule]; hModule
0x18008e272  call    cs:__imp_GetProcAddress
0x18008e278  mov     r10, rax
0x18008e27b  mov     [rbp+620h+var_658], rax
0x18008e27f  test    rax, rax
0x18008e282  jnz     short loc_18008E29E
0x18008e284  mov     rcx, [rbp+628h]; this
0x18008e28b  lea     r8, aOnecoreInterna_1; "OneCore\\Internal\\Base\\inc\\utcapiwra"...
0x18008e292  mov     edx, 0B2h; void *
0x18008e297  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18008e29c  jmp     short loc_18008E2ED
0x18008e29e  movzx   ecx, [rbp+620h+var_5B0]
0x18008e2a2  lea     rax, [rsp+720h+var_6A8]
  ... truncated ...
```
