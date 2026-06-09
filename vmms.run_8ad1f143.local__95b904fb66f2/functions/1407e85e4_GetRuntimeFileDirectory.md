# GetRuntimeFileDirectory

- ea: `0x1407e85e4`
- end: `0x1407e8a6e`
- name: `GetRuntimeFileDirectory`
- size: `1162`
- prototype: ``
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140100f5c`

## callees

- `0x14001a024`
- `0x140022640`
- `0x1400341d8`
- `0x14004bf10`
- `0x14007ee00`
- `0x14007ee50`
- `0x14007ee88`
- `0x14008108c`
- `0x1400b2bdc`
- `0x1400e1338`
- `0x14017902c`
- `0x140188e18`
- `0x1404828e0`
- `0x1407e85e4`
- `0x1408aa010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407e86e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407e88e6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407e86e5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1407e88e6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1407e8983`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1407e89cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1407e8983`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathAppendW` at `0x1407e89cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e8648`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e8662`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e86a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e8648`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e8662`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathRemoveFileSpecW` at `0x1407e86a3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1407e867c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1407e86bd`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1407e867c`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathStripPathW` at `0x1407e86bd`

## string_xrefs

- `0x1407e8724`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e8751`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e87bc`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e8817`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e886a`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e8941`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e896e`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e899d`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e89e6`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e8a24`: `onecore\vm\vmms\common\vmmsvalidation.cpp`
- `0x1407e884c`: `/configuration/global_settings/data_root`
- `0x1407e891f`: `/configuration/global_settings/data_root`
- `0x1407e8953`: `/configuration/global_settings/data_root`
- `0x1407e882f`: `/configuration/global_settings/snapshots/data_root`
- `0x1407e8906`: `/configuration/global_settings/snapshots/data_root`
- `0x1407e8612`: `/configuration/import/runtime_file_dir`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall GetRuntimeFileDirectory(__int64 a1, __int64 a2, _QWORD *a3)
{
  int v6; // eax
  WCHAR *v7; // rcx
  WCHAR *v8; // rcx
  WCHAR *v9; // rcx
  WCHAR *v10; // rcx
  WCHAR *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rsi
  int v17; // eax
  const WCHAR *v18; // rdx
  WCHAR *v19; // rcx
  LPWSTR *v20; // rcx
  bool v21; // zf
  __int64 (__fastcall *v22)(__int64, const unsigned __int16 *, _QWORD *); // rax
  int v23; // eax
  int v24; // eax
  const WCHAR *v25; // rdx
  WCHAR *v26; // rcx
  _QWORD *v27; // rax
  __int64 v28; // rdx
  __int64 v30; // [rsp+20h] [rbp-49h] BYREF
  __int64 v31; // [rsp+28h] [rbp-41h] BYREF
  __int64 v32; // [rsp+30h] [rbp-39h] BYREF
  char *v33[2]; // [rsp+38h] [rbp-31h] BYREF
  LPWSTR pszPath[3]; // [rsp+48h] [rbp-21h] BYREF
  unsigned __int64 v35; // [rsp+60h] [rbp-9h]
  LPWSTR v36[3]; // [rsp+68h] [rbp-1h] BYREF
  unsigned __int64 v37; // [rsp+80h] [rbp+17h]
  __int128 v38; // [rsp+90h] [rbp+27h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  v6 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *))(*(_QWORD *)a1 + 104LL))(
         a1,
         L"/configuration/import/runtime_file_dir");
  if ( v6 == -2147024894 )
  {
    std::wstring::wstring(pszPath, a2);
    v7 = (WCHAR *)pszPath;
    if ( v35 > 7 )
      v7 = pszPath[0];
    PathRemoveFileSpecW(v7);
    v8 = (WCHAR *)pszPath;
    if ( v35 > 7 )
      v8 = pszPath[0];
    PathRemoveFileSpecW(v8);
    v9 = (WCHAR *)pszPath;
    if ( v35 > 7 )
      v9 = pszPath[0];
    PathStripPathW(v9);
    std::wstring::wstring(v36, a2);
    v10 = (WCHAR *)v36;
    if ( v37 > 7 )
      v10 = v36[0];
    PathRemoveFileSpecW(v10);
    v11 = (WCHAR *)v36;
    if ( v37 > 7 )
      v11 = v36[0];
    PathStripPathW(v11);
    v12 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 328LL))(a1);
    if ( (unsigned int)_o__wcsicmp(v12, L"Planned Snapshots") )
    {
      v20 = pszPath;
      if ( v35 > 7 )
        v20 = (LPWSTR *)pszPath[0];
      v21 = (unsigned int)_o__wcsicmp(v20, L"Snapshots") == 0;
      v22 = *(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)a1 + 104LL);
      if ( v21 )
      {
        v23 = v22(a1, L"/configuration/global_settings/snapshots/data_root", a3);
        if ( v23 == -2147024894 )
          v23 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)a1 + 104LL))(
                  a1,
                  L"/configuration/global_settings/data_root",
                  a3);
        if ( v23 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xC4,
            (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
            (const char *)(unsigned int)v23,
            v30);
      }
      else
      {
        v24 = v22(a1, L"/configuration/global_settings/data_root", a3);
        if ( v24 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xCD,
            (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
            (const char *)(unsigned int)v24,
            v30);
      }
    }
    else
    {
      v38 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a1 + 304LL))(a1, &v38);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x8E,
          (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
          (const char *)(unsigned int)v13,
          v30);
      v32 = 0;
      if ( !(unsigned __int8)Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::TryOpenShared(&v32) )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x91,
          (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
          (const char *)0x8000FFFFLL,
          v30);
      v31 = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64))(*(_QWORD *)v32 + 152LL))(v32, &v38, 3);
      if ( v14 )
        v15 = v14 + *(int *)(*(_QWORD *)(v14 + 8) + 12LL) + 8LL;
      else
        v15 = 0;
      Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(
        &v31,
        0);
      v31 = v15;
      if ( !v15 )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x9B,
          (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
          (const char *)0xD,
          v30);
      v30 = 0;
      v16 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 120LL))(v15);
      Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>::Reset(&v30, 0);
      v30 = v16;
      *(_OWORD *)v33 = 0;
      VmRepositoryAutoLock::VmRepositoryAutoLock(v33, v16, 0);
      if ( SLODWORD(v33[1]) < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xA4,
          (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
          (const char *)LODWORD(v33[1]),
          v30);
      if ( (*(int (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)v16 + 104LL))(
             v16,
             L"/configuration/global_settings/snapshots/data_root",
             a3) < 0 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, const unsigned __int16 *, _QWORD *))(*(_QWORD *)v16 + 104LL))(
                v16,
                L"/configuration/global_settings/data_root",
                a3);
        if ( v17 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0xAD,
            (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
            (const char *)(unsigned int)v17,
            v30);
      }
      VmRepositoryAutoLock::~VmRepositoryAutoLock((VmRepositoryAutoLock *)v33);
      Vml::VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>(&v30);
      Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v31);
      Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(&v32);
    }
    std::wstring::resize(a3);
    v18 = (const WCHAR *)pszPath;
    if ( v35 > 7 )
      v18 = pszPath[0];
    if ( a3[3] <= 7u )
      v19 = (WCHAR *)a3;
    else
      v19 = (WCHAR *)*a3;
    if ( !PathAppendW(v19, v18) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD4,
        (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
        (const char *)0x80010135LL,
        v30);
    v25 = (const WCHAR *)v36;
    if ( v37 > 7 )
      v25 = v36[0];
    if ( a3[3] <= 7u )
      v26 = (WCHAR *)a3;
    else
      v26 = (WCHAR *)*a3;
    if ( !PathAppendW(v26, v25) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD9,
        (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
        (const char *)0x80010135LL,
        v30);
    std::wstring::_Tidy_deallocate(v36);
    std::wstring::_Tidy_deallocate(pszPath);
  }
  else if ( v6 < 0 )
  {
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xDE,
      (unsigned int)"onecore\\vm\\vmms\\common\\vmmsvalidation.cpp",
      (const char *)(unsigned int)v6,
      v30);
  }
  if ( a3[3] <= 7u )
    v27 = a3;
  else
    v27 = (_QWORD *)*a3;
  v28 = -1;
  do
    ++v28;
  while ( *((_WORD *)v27 + v28) );
  return std::wstring::resize(a3);
}

```

## disassembly

```asm
0x1407e85e4  mov     [rsp-8+arg_18], rbx
0x1407e85e9  push    rbp
0x1407e85ea  push    rsi
0x1407e85eb  push    rdi
0x1407e85ec  lea     rbp, [rsp-47h]
0x1407e85f1  sub     rsp, 0B0h
0x1407e85f8  mov     rax, cs:__security_cookie
0x1407e85ff  xor     rax, rsp
0x1407e8602  mov     [rbp+57h+var_20], rax
0x1407e8606  mov     rdi, r8
0x1407e8609  mov     rbx, rdx
0x1407e860c  mov     rsi, rcx
0x1407e860f  mov     rax, [rcx]
0x1407e8612  lea     rdx, ?VIRTUAL_MACHINE_IMPORT_RUNTIME_FILE_DIRECTORY@@3QBGB; "/configuration/import/runtime_file_dir"
0x1407e8619  mov     rax, [rax+68h]
0x1407e861d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8622  cmp     eax, 80070002h
0x1407e8627  jnz     loc_1407E8A17
0x1407e862d  mov     rdx, rbx
0x1407e8630  lea     rcx, [rbp+57h+pszPath]
0x1407e8634  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1407e8639  nop
0x1407e863a  lea     rcx, [rbp+57h+pszPath]
0x1407e863e  cmp     [rbp+57h+var_60], 7
0x1407e8643  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x1407e8648  call    cs:__imp_PathRemoveFileSpecW
0x1407e864f  nop     dword ptr [rax+rax+00h]
0x1407e8654  lea     rcx, [rbp+57h+pszPath]
0x1407e8658  cmp     [rbp+57h+var_60], 7
0x1407e865d  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x1407e8662  call    cs:__imp_PathRemoveFileSpecW
0x1407e8669  nop     dword ptr [rax+rax+00h]
0x1407e866e  lea     rcx, [rbp+57h+pszPath]
0x1407e8672  cmp     [rbp+57h+var_60], 7
0x1407e8677  cmova   rcx, [rbp+57h+pszPath]; pszPath
0x1407e867c  call    cs:__imp_PathStripPathW
0x1407e8683  nop     dword ptr [rax+rax+00h]
0x1407e8688  mov     rdx, rbx
0x1407e868b  lea     rcx, [rbp+57h+var_58]
0x1407e868f  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1407e8694  nop
0x1407e8695  lea     rcx, [rbp+57h+var_58]
0x1407e8699  cmp     [rbp+57h+var_40], 7
0x1407e869e  cmova   rcx, [rbp+57h+var_58]; pszPath
0x1407e86a3  call    cs:__imp_PathRemoveFileSpecW
0x1407e86aa  nop     dword ptr [rax+rax+00h]
0x1407e86af  lea     rcx, [rbp+57h+var_58]
0x1407e86b3  cmp     [rbp+57h+var_40], 7
0x1407e86b8  cmova   rcx, [rbp+57h+var_58]; pszPath
0x1407e86bd  call    cs:__imp_PathStripPathW
0x1407e86c4  nop     dword ptr [rax+rax+00h]
0x1407e86c9  mov     rax, [rsi]
0x1407e86cc  mov     rcx, rsi
0x1407e86cf  mov     rax, [rax+148h]
0x1407e86d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e86db  mov     rcx, rax
0x1407e86de  lea     rdx, aPlannedSnapsho_0; "Planned Snapshots"
0x1407e86e5  call    cs:__imp__o__wcsicmp
0x1407e86ec  nop     dword ptr [rax+rax+00h]
0x1407e86f1  xor     ebx, ebx
0x1407e86f3  test    eax, eax
0x1407e86f5  jnz     loc_1407E88D1
0x1407e86fb  xorps   xmm0, xmm0
0x1407e86fe  movdqa  [rbp+57h+var_30], xmm0
0x1407e8703  mov     rax, [rsi]
0x1407e8706  lea     rdx, [rbp+57h+var_30]
0x1407e870a  mov     rcx, rsi
0x1407e870d  mov     rax, [rax+130h]
0x1407e8714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8719  mov     rcx, [rbp+5Fh]; this
0x1407e871d  test    eax, eax
0x1407e871f  jns     short loc_1407E8736
0x1407e8721  mov     r9d, eax; char *
0x1407e8724  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e872b  mov     edx, 8Eh; void *
0x1407e8730  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8736  mov     [rbp+57h+var_90], rbx
0x1407e873a  lea     rcx, [rbp+57h+var_90]
0x1407e873e  call    ?TryOpenShared@?$VmSingletonObject@VVmmsVirtualMachineManager@@UIVmmsVirtualMachineManager@@@Vml@@SA_NPEAPEAUIVmmsVirtualMachineManager@@@Z; Vml::VmSingletonObject<VmmsVirtualMachineManager,IVmmsVirtualMachineManager>::TryOpenShared(IVmmsVirtualMachineManager * *)
0x1407e8743  mov     rcx, [rbp+5Fh]; this
0x1407e8747  test    al, al
0x1407e8749  jnz     short loc_1407E8763
0x1407e874b  mov     r9d, 8000FFFFh; char *
0x1407e8751  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e8758  mov     edx, 91h; void *
0x1407e875d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8763  mov     [rbp+57h+var_98], rbx
0x1407e8767  mov     rcx, [rbp+57h+var_90]
0x1407e876b  mov     rax, [rcx]
0x1407e876e  mov     r8d, 3
0x1407e8774  lea     rdx, [rbp+57h+var_30]
0x1407e8778  mov     rax, [rax+98h]
0x1407e877f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8784  mov     rdx, rax
0x1407e8787  test    rax, rax
0x1407e878a  jnz     short loc_1407E8791
0x1407e878c  mov     rsi, rbx
0x1407e878f  jmp     short loc_1407E87A0
0x1407e8791  mov     rax, [rax+8]
0x1407e8795  movsxd  rsi, dword ptr [rax+0Ch]
0x1407e8799  add     rsi, 8
0x1407e879d  add     rsi, rdx
0x1407e87a0  xor     edx, edx
0x1407e87a2  lea     rcx, [rbp+57h+var_98]
0x1407e87a6  call    ?Reset@?$VmReferencePtr@VFrManagerMigrationEvents@VmmsFailoverReplicationManager@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVFrManagerMigrationEvents@VmmsFailoverReplicationManager@@@Z; Vml::VmReferencePtr<VmmsFailoverReplicationManager::FrManagerMigrationEvents,Vml::VmUserReferenceTraits>::Reset(VmmsFailoverReplicationManager::FrManagerMigrationEvents *)
0x1407e87ab  mov     [rbp+57h+var_98], rsi
0x1407e87af  test    rsi, rsi
0x1407e87b2  jnz     short loc_1407E87CE
0x1407e87b4  mov     rcx, [rbp+5Fh]; this
0x1407e87b8  lea     r9d, [rsi+0Dh]; char *
0x1407e87bc  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e87c3  mov     edx, 9Bh; void *
0x1407e87c8  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x1407e87ce  mov     [rbp+57h+var_A0], rbx
0x1407e87d2  mov     rax, [rsi]
0x1407e87d5  mov     rcx, rsi
0x1407e87d8  mov     rax, [rax+78h]
0x1407e87dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e87e1  mov     rsi, rax
0x1407e87e4  xor     edx, edx
0x1407e87e6  lea     rcx, [rbp+57h+var_A0]
0x1407e87ea  call    ?Reset@?$VmReferencePtr@VSavedStateRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAAXPEAVSavedStateRepository@@@Z; Vml::VmReferencePtr<SavedStateRepository,Vml::VmUserReferenceTraits>::Reset(SavedStateRepository *)
0x1407e87ef  mov     [rbp+57h+var_A0], rsi
0x1407e87f3  xorps   xmm0, xmm0
0x1407e87f6  movups  xmmword ptr [rbp+57h+var_88], xmm0
0x1407e87fa  xor     r8d, r8d
0x1407e87fd  mov     rdx, rsi
0x1407e8800  lea     rcx, [rbp+57h+var_88]
0x1407e8804  call    ??0VmRepositoryAutoLock@@QEAA@PEAVVmRepository@@W4VmRepositoryLockFlags@@@Z; VmRepositoryAutoLock::VmRepositoryAutoLock(VmRepository *,VmRepositoryLockFlags)
0x1407e8809  nop
0x1407e880a  mov     r9d, dword ptr [rbp+57h+var_88+8]; char *
0x1407e880e  mov     rcx, [rbp+5Fh]; this
0x1407e8812  test    r9d, r9d
0x1407e8815  jns     short loc_1407E8829
0x1407e8817  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e881e  mov     edx, 0A4h; void *
0x1407e8823  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8829  mov     rax, [rsi]
0x1407e882c  mov     r8, rdi
0x1407e882f  lea     rdx, ?VIRTUAL_MACHINE_SNAPSHOT_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/snapshot"...
0x1407e8836  mov     rcx, rsi
0x1407e8839  mov     rax, [rax+68h]
0x1407e883d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8842  test    eax, eax
0x1407e8844  jns     short loc_1407E887C
0x1407e8846  mov     rax, [rsi]
0x1407e8849  mov     r8, rdi
0x1407e884c  lea     rdx, ?VIRTUAL_MACHINE_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/data_roo"...
0x1407e8853  mov     rcx, rsi
0x1407e8856  mov     rax, [rax+68h]
0x1407e885a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e885f  mov     rcx, [rbp+5Fh]; this
0x1407e8863  test    eax, eax
0x1407e8865  jns     short loc_1407E887C
0x1407e8867  mov     r9d, eax; char *
0x1407e886a  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e8871  mov     edx, 0ADh; void *
0x1407e8876  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e887c  lea     rcx, [rbp+57h+var_88]; this
0x1407e8880  call    ??1VmRepositoryAutoLock@@QEAA@XZ; VmRepositoryAutoLock::~VmRepositoryAutoLock(void)
0x1407e8885  nop
0x1407e8886  lea     rcx, [rbp+57h+var_A0]
0x1407e888a  call    ??1?$VmReferencePtr@VSnapshotRepository@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>::~VmReferencePtr<SnapshotRepository,Vml::VmUserReferenceTraits>(void)
0x1407e888f  nop
0x1407e8890  lea     rcx, [rbp+57h+var_98]
0x1407e8894  call    ??1?$VmReferencePtr@UIVmmsPlannedVirtualMachine@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(void)
0x1407e8899  nop
0x1407e889a  lea     rcx, [rbp+57h+var_90]
0x1407e889e  call    ??1?$VmReferencePtr@UIVmmsPlannedVirtualMachine@@VVmUserReferenceTraits@Vml@@@Vml@@QEAA@XZ; Vml::VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>::~VmReferencePtr<IVmmsPlannedVirtualMachine,Vml::VmUserReferenceTraits>(void)
0x1407e88a3  mov     edx, 104h
0x1407e88a8  mov     rcx, rdi; Src
0x1407e88ab  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1407e88b0  lea     rdx, [rbp+57h+pszPath]
0x1407e88b4  cmp     [rbp+57h+var_60], 7
0x1407e88b9  cmova   rdx, [rbp+57h+pszPath]; pszMore
0x1407e88be  cmp     qword ptr [rdi+18h], 7
0x1407e88c3  jbe     loc_1407E8980
0x1407e88c9  mov     rcx, [rdi]
0x1407e88cc  jmp     loc_1407E8983
0x1407e88d1  lea     rcx, [rbp+57h+pszPath]
0x1407e88d5  cmp     [rbp+57h+var_60], 7
0x1407e88da  cmova   rcx, [rbp+57h+pszPath]
0x1407e88df  lea     rdx, aSnapshots; "Snapshots"
0x1407e88e6  call    cs:__imp__o__wcsicmp
0x1407e88ed  nop     dword ptr [rax+rax+00h]
0x1407e88f2  mov     rcx, [rsi]
0x1407e88f5  mov     r9, [rcx+68h]
0x1407e88f9  mov     r8, rdi
0x1407e88fc  mov     rcx, rsi
0x1407e88ff  test    eax, eax
0x1407e8901  mov     rax, r9
0x1407e8904  jnz     short loc_1407E8953
0x1407e8906  lea     rdx, ?VIRTUAL_MACHINE_SNAPSHOT_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/snapshot"...
0x1407e890d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8912  cmp     eax, 80070002h
0x1407e8917  jnz     short loc_1407E8932
0x1407e8919  mov     rax, [rsi]
0x1407e891c  mov     r8, rdi
0x1407e891f  lea     rdx, ?VIRTUAL_MACHINE_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/data_roo"...
0x1407e8926  mov     rcx, rsi
0x1407e8929  mov     rax, [rax+68h]
0x1407e892d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e8932  test    eax, eax
0x1407e8934  jns     loc_1407E88A3
0x1407e893a  mov     rcx, [rbp+5Fh]; this
0x1407e893e  mov     r9d, eax; char *
0x1407e8941  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e8948  mov     edx, 0C4h; void *
0x1407e894d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8953  lea     rdx, ?VIRTUAL_MACHINE_DATA_ROOT_XPATH@@3QBGB; "/configuration/global_settings/data_roo"...
0x1407e895a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1407e895f  mov     rcx, [rbp+5Fh]; this
0x1407e8963  test    eax, eax
0x1407e8965  jns     loc_1407E88A3
0x1407e896b  mov     r9d, eax; char *
0x1407e896e  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e8975  mov     edx, 0CDh; void *
0x1407e897a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8980  mov     rcx, rdi; pszPath
0x1407e8983  call    cs:__imp_PathAppendW
0x1407e898a  nop     dword ptr [rax+rax+00h]
0x1407e898f  test    eax, eax
0x1407e8991  jnz     short loc_1407E89AF
0x1407e8993  mov     rcx, [rbp+5Fh]; this
0x1407e8997  mov     r9d, 80010135h; char *
0x1407e899d  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e89a4  mov     edx, 0D4h; void *
0x1407e89a9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e89af  lea     rdx, [rbp+57h+var_58]
0x1407e89b3  cmp     [rbp+57h+var_40], 7
0x1407e89b8  cmova   rdx, [rbp+57h+var_58]; pszMore
0x1407e89bd  cmp     qword ptr [rdi+18h], 7
0x1407e89c2  jbe     short loc_1407E89C9
0x1407e89c4  mov     rcx, [rdi]
0x1407e89c7  jmp     short loc_1407E89CC
0x1407e89c9  mov     rcx, rdi; pszPath
0x1407e89cc  call    cs:__imp_PathAppendW
0x1407e89d3  nop     dword ptr [rax+rax+00h]
0x1407e89d8  test    eax, eax
0x1407e89da  jnz     short loc_1407E89F8
0x1407e89dc  mov     rcx, [rbp+5Fh]; this
0x1407e89e0  mov     r9d, 80010135h; char *
0x1407e89e6  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e89ed  mov     edx, 0D9h; void *
0x1407e89f2  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e89f8  lea     rcx, [rbp+57h+var_58]
0x1407e89fc  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1407e8a01  nop
0x1407e8a02  lea     rcx, [rbp+57h+pszPath]
0x1407e8a06  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1407e8a0b  cmp     qword ptr [rdi+18h], 7
0x1407e8a10  jbe     short loc_1407E8A36
0x1407e8a12  mov     rax, [rdi]
0x1407e8a15  jmp     short loc_1407E8A39
0x1407e8a17  xor     ebx, ebx
0x1407e8a19  test    eax, eax
0x1407e8a1b  jns     short loc_1407E8A0B
0x1407e8a1d  mov     rcx, [rbp+5Fh]; this
0x1407e8a21  mov     r9d, eax; char *
0x1407e8a24  lea     r8, aOnecoreVmVmmsC_13; "onecore\\vm\\vmms\\common\\vmmsvalidati"...
0x1407e8a2b  mov     edx, 0DEh; void *
0x1407e8a30  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1407e8a36  mov     rax, rdi
0x1407e8a39  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1407e8a3d  inc     rdx
0x1407e8a40  cmp     [rax+rdx*2], bx
0x1407e8a44  jnz     short loc_1407E8A3D
0x1407e8a46  mov     rcx, rdi; Src
0x1407e8a49  call    ?resize@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_KG@Z; std::wstring::resize(unsigned __int64,ushort)
0x1407e8a4e  mov     rcx, [rbp+57h+var_20]
0x1407e8a52  xor     rcx, rsp; StackCookie
0x1407e8a55  call    __security_check_cookie
0x1407e8a5a  mov     rbx, [rsp+0C0h+arg_18]
0x1407e8a62  add     rsp, 0B0h
0x1407e8a69  pop     rdi
0x1407e8a6a  pop     rsi
0x1407e8a6b  pop     rbp
0x1407e8a6c  retn
```
