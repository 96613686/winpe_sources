# CUxpDllWrapper::GetWlidUxModulePath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18003b7f8`
- end: `0x18003b95b`
- name: `?GetWlidUxModulePath@CUxpDllWrapper@@SAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `355`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x180031560`
- `0x18003b964`

## callees

- `0x18000a870`
- `0x18000a914`
- `0x18000b8a4`
- `0x18000ba8c`
- `0x18000bd2c`
- `0x18000bea0`
- `0x18000cc9c`
- `0x18000e870`
- `0x18000edbc`
- `0x18003b7f8`
- `0x180053890`
- `0x1800550f4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b90f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b90f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18003b904`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathCombineW` at `0x18003b904`

## string_xrefs

- `0x18003b810`: `CUxpDllWrapper::GetWlidUxModulePath`
- `0x18003b85e`: `SharedPath`
- `0x18003b86f`: `software\microsoft\windows live\common`
- `0x18003b8c4`: `hr = Reg_QueryString(HKEY_LOCAL_MACHINE, PPCRL_REG_WLID_UX_PATH, PPCRL_REG_WLID_UX_VALUE, wstrDirPath, TRUE )`
- `0x18003b8f7`: `wlidux.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CUxpDllWrapper::GetWlidUxModulePath(const unsigned __int16 **a1)
{
  __int64 v2; // rcx
  int v3; // esi
  const WCHAR *v4; // rbx
  WCHAR *v5; // rax
  signed int LastError; // eax
  unsigned int v7; // eax
  unsigned int v8; // edi
  char *v10; // [rsp+20h] [rbp-40h]
  LPCWSTR pszDir; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v12[5]; // [rsp+38h] [rbp-28h] BYREF
  int v13; // [rsp+98h] [rbp+38h] BYREF
  __int64 v14; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v15; // [rsp+A8h] [rbp+48h] BYREF

  v13 = 0;
  v12[0] = "CUxpDllWrapper::GetWlidUxModulePath";
  v12[1] = &v13;
  v12[2] = 0;
  v12[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
    "CUxpDllWrapper::GetWlidUxModulePath",
    (const char *)0x76,
    0,
    (const unsigned __int16 *)v10);
  ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>((__int64)&pszDir);
  ATL::CSimpleStringT<unsigned short,0>::Truncate(a1, 0);
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v15,
    (__int64)L"SharedPath");
  ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
    (__int64)&v14,
    (__int64)L"software\\microsoft\\windows live\\common");
  v3 = Reg_QueryString(v2, &v14, &v15, 513, &pszDir);
  v13 = v3;
  ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
  ATL::CStringData::Release((ATL::CStringData *)(v15 - 24));
  v4 = pszDir;
  if ( v3 >= 0 )
  {
    v5 = (WCHAR *)ATL::CSimpleStringT<unsigned short,0>::PrepareWrite(a1, 260);
    if ( PathCombineW(v5, v4, L"wlidux.dll") )
    {
      v7 = ocslen(*a1);
      ATL::CSimpleStringT<unsigned short,0>::SetLength(a1, v7);
    }
    else
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v13 = LastError;
    }
  }
  else
  {
    Telemetry::IfFailExit(
      "clientcore\\ds\\ext\\live\\identity\\api\\classic\\uxpuiwrapper.cpp",
      "CUxpDllWrapper::GetWlidUxModulePath",
      0x80u,
      v3,
      "hr = Reg_QueryString(HKEY_LOCAL_MACHINE, PPCRL_REG_WLID_UX_PATH, PPCRL_REG_WLID_UX_VALUE, wstrDirPath, TRUE )");
  }
  v8 = v13;
  ATL::CStringData::Release((ATL::CStringData *)(v4 - 12));
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v12);
  return v8;
}

```

## disassembly

```asm
0x18003b7f8  push    rbp
0x18003b7fa  push    rbx
0x18003b7fb  push    rsi
0x18003b7fc  push    rdi
0x18003b7fd  push    r15
0x18003b7ff  mov     rbp, rsp
0x18003b802  sub     rsp, 60h
0x18003b806  mov     rdi, rcx
0x18003b809  mov     [rbp+arg_8], 0
0x18003b810  lea     r15, aCuxpdllwrapper_0; "CUxpDllWrapper::GetWlidUxModulePath"
0x18003b817  mov     [rbp+var_28], r15
0x18003b81b  lea     rax, [rbp+arg_8]
0x18003b81f  mov     [rbp+var_20], rax
0x18003b823  mov     [rbp+var_18], 0
0x18003b82b  mov     [rbp+var_10], 0
0x18003b833  xor     r9d, r9d; unsigned int
0x18003b836  lea     r8d, [r9+76h]; char *
0x18003b83a  mov     rdx, r15; char *
0x18003b83d  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003b844  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18003b849  nop
0x18003b84a  lea     rcx, [rbp+pszDir]
0x18003b84e  call    ??0?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAA@XZ; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>(void)
0x18003b853  nop
0x18003b854  xor     edx, edx
0x18003b856  mov     rcx, rdi
0x18003b859  call    ?Truncate@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::Truncate(int)
0x18003b85e  lea     rdx, aSharedpath; "SharedPath"
0x18003b865  lea     rcx, [rbp+arg_18]
0x18003b869  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003b86e  nop
0x18003b86f  lea     rdx, aSoftwareMicros_1; "software\\microsoft\\windows live\\comm"...
0x18003b876  lea     rcx, [rbp+arg_10]
0x18003b87a  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x18003b87f  nop
0x18003b880  lea     rax, [rbp+pszDir]
0x18003b884  mov     [rsp+60h+var_40], rax
0x18003b889  mov     r9d, 201h
0x18003b88f  lea     r8, [rbp+arg_18]
0x18003b893  lea     rdx, [rbp+arg_10]
0x18003b897  call    ?Reg_QueryString@@YAJPEAUHKEY__@@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@1KAEAV23@@Z; Reg_QueryString(HKEY__ *,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ulong,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)
0x18003b89c  mov     esi, eax
0x18003b89e  mov     [rbp+arg_8], eax
0x18003b8a1  mov     rcx, [rbp+arg_10]
0x18003b8a5  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003b8a9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b8ae  nop
0x18003b8af  mov     rcx, [rbp+arg_18]
0x18003b8b3  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x18003b8b7  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b8bc  mov     rbx, [rbp+pszDir]
0x18003b8c0  test    esi, esi
0x18003b8c2  jns     short loc_18003B8EA
0x18003b8c4  lea     rax, aHrRegQuerystri; "hr = Reg_QueryString(HKEY_LOCAL_MACHINE"...
0x18003b8cb  mov     [rsp+60h+var_40], rax; char *
0x18003b8d0  mov     r9d, esi; int
0x18003b8d3  mov     r8d, 80h; unsigned int
0x18003b8d9  mov     rdx, r15; char *
0x18003b8dc  lea     rcx, aClientcoreDsEx_7; "clientcore\\ds\\ext\\live\\identity\\ap"...
0x18003b8e3  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18003b8e8  jmp     short loc_18003B938
0x18003b8ea  mov     edx, 104h
0x18003b8ef  mov     rcx, rdi
0x18003b8f2  call    ?PrepareWrite@?$CSimpleStringT@G$0A@@ATL@@AEAAPEAGH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite(int)
0x18003b8f7  lea     r8, pszFile; "wlidux.dll"
0x18003b8fe  mov     rdx, rbx; pszDir
0x18003b901  mov     rcx, rax; pszDest
0x18003b904  call    cs:__imp_PathCombineW
0x18003b90a  test    rax, rax
0x18003b90d  jnz     short loc_18003B926
0x18003b90f  call    cs:__imp_GetLastError
0x18003b915  test    eax, eax
0x18003b917  jle     short loc_18003B921
0x18003b919  movzx   eax, ax
0x18003b91c  or      eax, 80070000h
0x18003b921  mov     [rbp+arg_8], eax
0x18003b924  jmp     short loc_18003B938
0x18003b926  mov     rcx, [rdi]; unsigned __int16 *
0x18003b929  call    ?ocslen@@YAHPEBG@Z; ocslen(ushort const *)
0x18003b92e  mov     edx, eax
0x18003b930  mov     rcx, rdi
0x18003b933  call    ?SetLength@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::SetLength(int)
0x18003b938  mov     edi, [rbp+arg_8]
0x18003b93b  lea     rcx, [rbx-18h]; this
0x18003b93f  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x18003b944  nop
0x18003b945  lea     rcx, [rbp+var_28]
0x18003b949  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x18003b94e  mov     eax, edi
0x18003b950  add     rsp, 60h
0x18003b954  pop     r15
0x18003b956  pop     rdi
0x18003b957  pop     rsi
0x18003b958  pop     rbx
0x18003b959  pop     rbp
0x18003b95a  retn
```
