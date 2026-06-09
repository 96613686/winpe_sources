# CSdController::_AddUserLibraryPathsToEngine(ISdBackup2 *,int,_UserProfileData *,_SD_BACKUP_USER_DATA *)

- ea: `0x180010c80`
- end: `0x18001121b`
- name: `?_AddUserLibraryPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@HPEAU_UserProfileData@@PEAU_SD_BACKUP_USER_DATA@@@Z`
- size: `1435`
- prototype: `__int64 __fastcall(CSdController *this, struct ISdBackup2 *, int, const unsigned __int16 **, struct _SD_BACKUP_USER_DATA *)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800106f4`

## callees

- `0x180010b4c`
- `0x180010c80`
- `0x180014f70`
- `0x18001507c`
- `0x18001586c`
- `0x180015974`
- `0x18001fcc0`
- `0x180020488`
- `0x18002170a`
- `0x180021740`
- `0x180022010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180010df1`
- `msvcrt!_wcsicmp` at `0x180010df1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110ed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800110ed`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800111d7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800111d7`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800110bc`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800110bc`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010d8b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180010d8b`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180010e58`
- `api-ms-win-shell-shellcom-l1-1-0!SHCoCreateInstance` at `0x180010e58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011150`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180010fa3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180011150`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180010e83`
- `api-ms-win-shell-namespace-l1-1-0!SHCreateItemFromParsingName` at `0x180010e83`

## string_xrefs

- `0x180010ccd`: `CSdController::_AddUserLibraryPathsToEngine`

## pseudocode

```c
__int64 __fastcall CSdController::_AddUserLibraryPathsToEngine(
        CSdController *this,
        struct ISdBackup2 *a2,
        int a3,
        const unsigned __int16 **a4,
        struct _SD_BACKUP_USER_DATA *a5)
{
  __int64 FirstFileW; // rbx
  const unsigned __int16 *v9; // r9
  __int16 v10; // ax
  const unsigned __int16 *v11; // r9
  int v12; // edx
  __int64 v13; // rdi
  int v14; // esi
  int v15; // eax
  int v16; // eax
  __int64 v17; // rcx
  CSdController *v18; // rcx
  unsigned int v19; // edi
  void **ppv; // [rsp+20h] [rbp-E0h]
  void **ppva; // [rsp+20h] [rbp-E0h]
  const unsigned __int16 *v23; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v24; // [rsp+28h] [rbp-D8h]
  const unsigned __int16 *v25; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v26; // [rsp+30h] [rbp-D0h]
  const unsigned __int16 *v27; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v28; // [rsp+38h] [rbp-C8h]
  const unsigned __int16 *v29; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v30; // [rsp+40h] [rbp-C0h]
  const unsigned __int16 *v31; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v32; // [rsp+48h] [rbp-B8h]
  const unsigned __int16 *v33; // [rsp+50h] [rbp-B0h]
  const unsigned __int16 *v34; // [rsp+50h] [rbp-B0h]
  __int64 v35; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  __int64 v37; // [rsp+70h] [rbp-90h] BYREF
  void *v38; // [rsp+78h] [rbp-88h] BYREF
  int v39; // [rsp+80h] [rbp-80h] BYREF
  __int16 v40; // [rsp+84h] [rbp-7Ch]
  __int16 v41; // [rsp+86h] [rbp-7Ah]
  __int64 v42; // [rsp+B8h] [rbp-48h] BYREF
  void *v43; // [rsp+C0h] [rbp-40h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+C8h] [rbp-38h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+E0h] [rbp-20h] BYREF

  CSxFunctionTracer::CSxFunctionTracer((CSxFunctionTracer *)&v39, "CSdController::_AddUserLibraryPathsToEngine", 712, 0);
  lpFileName[0] = (LPCWSTR)qword_180028260;
  lpFileName[1] = 0;
  v43 = 0;
  FirstFileW = -1;
  v35 = 0;
  v38 = 0;
  v42 = 0;
  v37 = 0;
  pv = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v10 = 727;
  if ( !a2 || (v40 = 727, v10 = 728, !a4) )
  {
    v39 = -2147024809;
    goto LABEL_3;
  }
  v39 = 0;
  v40 = 728;
  if ( a5 && *((_DWORD *)a5 + 7) )
  {
    v10 = 732;
LABEL_56:
    v40 = v10;
    goto LABEL_57;
  }
  v39 = CBsString::SetPath(
          (CBsString *)lpFileName,
          a4[5],
          L"*.library-ms",
          v9,
          (const unsigned __int16 *)ppv,
          v23,
          v25,
          v27,
          v29,
          v31,
          v33);
  v10 = 735;
  if ( v39 < 0 )
    goto LABEL_3;
  v40 = 735;
  FirstFileW = (__int64)FindFirstFileW(lpFileName[0], &FindFileData);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
  {
    while ( 1 )
    {
      if ( !a5 )
        goto LABEL_16;
      v12 = *((_DWORD *)a5 + 2);
      if ( (v12 != 0) != (*((_QWORD *)a5 + 2) != 0) )
      {
        v39 = -2147024809;
        v41 = 757;
        goto LABEL_57;
      }
      v13 = 0;
      v39 = 0;
      v14 = *((_DWORD *)a5 + 7);
      v40 = 757;
      if ( v12 )
      {
        while ( _wcsicmp(*(const wchar_t **)(*((_QWORD *)a5 + 2) + 8 * v13), FindFileData.cFileName) )
        {
          v13 = (unsigned int)(v13 + 1);
          if ( (unsigned int)v13 >= *((_DWORD *)a5 + 2) )
            goto LABEL_15;
        }
        goto LABEL_45;
      }
LABEL_15:
      if ( !v14 )
      {
LABEL_16:
        v39 = CBsString::SetPath(
                (CBsString *)lpFileName,
                a4[5],
                FindFileData.cFileName,
                v11,
                (const unsigned __int16 *)ppva,
                v24,
                v26,
                v28,
                v30,
                v32,
                v34);
        v10 = 774;
        if ( v39 < 0 )
          goto LABEL_3;
        v40 = 774;
        v39 = SHCoCreateInstance(0, &CLSID_ShellLibrary, 0, &GUID_11a66efa_382e_451a_9234_1e0e12ef3085, &v38);
        v10 = 776;
        if ( v39 < 0 )
          goto LABEL_3;
        v40 = 776;
        v39 = SHCreateItemFromParsingName(lpFileName[0], 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v43);
        v10 = 779;
        if ( v39 < 0 )
          goto LABEL_3;
        v40 = 779;
        v15 = (*(__int64 (__fastcall **)(void *, void *, _QWORD))(*(_QWORD *)v38 + 24LL))(v38, v43, 0);
        v39 = v15;
        if ( v15 < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              12,
              (unsigned int)WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids,
              lpFileName[0],
              v15);
          }
          v39 = 0;
        }
        else
        {
          if ( (*(int (__fastcall **)(void *, __int64, GUID *, __int64 *))(*(_QWORD *)v38 + 56LL))(
                 v38,
                 1,
                 &GUID_b63ea76d_1f85_456f_a19c_48159efa858b,
                 &v42) >= 0
            && (*(int (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v42 + 72LL))(v42, &v37) >= 0 )
          {
            v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v37 + 24LL))(v37, 1, &v35);
            v39 = v16;
            if ( v16 < 0 )
            {
              v10 = 790;
              goto LABEL_3;
            }
            v40 = 790;
            while ( v16 != 1 )
            {
              v39 = (*(__int64 (__fastcall **)(__int64, __int64, LPVOID *))(*(_QWORD *)v35 + 40LL))(
                      v35,
                      2147844096LL,
                      &pv);
              v10 = 793;
              if ( v39 < 0 )
                goto LABEL_3;
              v40 = 793;
              v39 = (*(__int64 (__fastcall **)(struct ISdBackup2 *, LPVOID, __int64))(*(_QWORD *)a2 + 32LL))(
                      a2,
                      pv,
                      3221225839LL);
              v10 = 796;
              if ( v39 < 0 )
                goto LABEL_3;
              v40 = 796;
              CoTaskMemFree(pv);
              v17 = v35;
              pv = 0;
              if ( v35 )
              {
                v35 = 0;
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
              }
              v16 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v37 + 24LL))(v37, 1, &v35);
              v39 = v16;
              if ( v16 < 0 )
              {
                v41 = 800;
                goto LABEL_57;
              }
              v40 = 800;
            }
          }
          if ( v35 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
            v35 = 0;
          }
          if ( v37 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
            v37 = 0;
          }
          if ( v42 )
          {
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
            v42 = 0;
          }
        }
        if ( v38 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
          v38 = 0;
        }
        if ( v43 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
          v43 = 0;
        }
      }
LABEL_45:
      if ( !FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
        goto LABEL_57;
    }
  }
  if ( GetLastError() == 3 && a3 )
  {
    v18 = (CSdController *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids, a4[5]);
    v39 = CSdController::_AddDefaultUserLibraryPathsToEngine(v18, a2, (struct _UserProfileData *)a4);
    v10 = 747;
    if ( v39 < 0 )
    {
LABEL_3:
      v41 = v10;
      goto LABEL_57;
    }
    goto LABEL_56;
  }
LABEL_57:
  CoTaskMemFree(pv);
  pv = 0;
  v19 = v39;
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v38 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v35 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
  if ( v43 )
    (*(void (__fastcall **)(void *))(*(_QWORD *)v43 + 16LL))(v43);
  if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    FindClose((HANDLE)FirstFileW);
  CBsString::_Release((CBsString *)lpFileName);
  CSxFunctionTracer::~CSxFunctionTracer((CSxFunctionTracer *)&v39);
  return v19;
}

```

## disassembly

```asm
0x180010c80  mov     [rsp-8+arg_0], rbx
0x180010c85  push    rbp
0x180010c86  push    rsi
0x180010c87  push    rdi
0x180010c88  push    r12
0x180010c8a  push    r13
0x180010c8c  push    r14
0x180010c8e  push    r15
0x180010c90  lea     rbp, [rsp-240h]
0x180010c98  sub     rsp, 340h
0x180010c9f  mov     rax, cs:__security_cookie
0x180010ca6  xor     rax, rsp
0x180010ca9  mov     [rbp+270h+var_40], rax
0x180010cb0  mov     r14, [rbp+270h+arg_20]
0x180010cb7  lea     rcx, [rbp+270h+var_2F0]; this
0x180010cbb  mov     r15, r9
0x180010cbe  mov     edi, r8d
0x180010cc1  mov     r13, rdx
0x180010cc4  xor     r9d, r9d; unsigned __int16
0x180010cc7  mov     r8d, 2C8h; unsigned __int16
0x180010ccd  lea     rdx, aCsdcontrollerA_0; "CSdController::_AddUserLibraryPathsToEn"...
0x180010cd4  call    ??0CSxFunctionTracer@@QEAA@PEBDGG@Z; CSxFunctionTracer::CSxFunctionTracer(char const *,ushort,ushort)
0x180010cd9  xor     esi, esi
0x180010cdb  lea     rax, qword_180028260
0x180010ce2  xor     edx, edx; Val
0x180010ce4  mov     [rbp+270h+lpFileName], rax
0x180010ce8  mov     r8d, 250h; Size
0x180010cee  mov     [rbp+270h+var_2A0], rsi
0x180010cf2  lea     rcx, [rbp+270h+FindFileData]; void *
0x180010cf6  mov     [rbp+270h+var_2B0], rsi
0x180010cfa  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180010cfe  mov     [rsp+370h+var_310], rsi
0x180010d03  mov     [rsp+370h+var_2F8], rsi
0x180010d08  mov     [rbp+270h+var_2B8], rsi
0x180010d0c  mov     [rsp+370h+var_300], rsi
0x180010d11  mov     [rsp+370h+pv], rsi
0x180010d16  call    memset_0
0x180010d1b  mov     eax, 2D7h
0x180010d20  test    r13, r13
0x180010d23  jnz     short loc_180010D35
0x180010d25  mov     [rbp+270h+var_2F0], 80070057h
0x180010d2c  mov     [rbp+270h+var_2EA], ax
0x180010d30  jmp     loc_18001114B
0x180010d35  mov     [rbp+270h+var_2EC], ax
0x180010d39  mov     eax, 2D8h
0x180010d3e  test    r15, r15
0x180010d41  jz      short loc_180010D25
0x180010d43  mov     [rbp+270h+var_2F0], esi
0x180010d46  mov     [rbp+270h+var_2EC], ax
0x180010d4a  test    r14, r14
0x180010d4d  jz      short loc_180010D5F
0x180010d4f  cmp     [r14+1Ch], esi
0x180010d53  jz      short loc_180010D5F
0x180010d55  mov     eax, 2DCh
0x180010d5a  jmp     loc_180011147
0x180010d5f  mov     rdx, [r15+28h]; unsigned __int16 *
0x180010d63  lea     r8, aLibraryMs; "*.library-ms"
0x180010d6a  lea     rcx, [rbp+270h+lpFileName]; this
0x180010d6e  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180010d73  mov     [rbp+270h+var_2F0], eax
0x180010d76  test    eax, eax
0x180010d78  mov     eax, 2DFh
0x180010d7d  js      short loc_180010D2C
0x180010d7f  mov     rcx, [rbp+270h+lpFileName]; lpFileName
0x180010d83  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x180010d87  mov     [rbp+270h+var_2EC], ax
0x180010d8b  call    cs:__imp_FindFirstFileW
0x180010d91  mov     rbx, rax
0x180010d94  dec     rax
0x180010d97  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180010d9b  ja      loc_1800110ED
0x180010da1  lea     r12, WPP_GLOBAL_Control
0x180010da8  mov     r8d, 2F5h
0x180010dae  lea     edi, [r8+2Bh]
0x180010db2  test    r14, r14
0x180010db5  jz      short loc_180010E16
0x180010db7  mov     edx, [r14+8]
0x180010dbb  mov     ecx, esi
0x180010dbd  test    edx, edx
0x180010dbf  mov     eax, esi
0x180010dc1  setnz   cl
0x180010dc4  cmp     [r14+10h], rsi
0x180010dc8  setnz   al
0x180010dcb  cmp     ecx, eax
0x180010dcd  jnz     loc_1800110CF
0x180010dd3  xor     edi, edi
0x180010dd5  mov     [rbp+270h+var_2F0], esi
0x180010dd8  mov     esi, [r14+1Ch]
0x180010ddc  mov     [rbp+270h+var_2EC], r8w
0x180010de1  test    edx, edx
0x180010de3  jz      short loc_180010E07
0x180010de5  mov     rcx, [r14+10h]
0x180010de9  lea     rdx, [rbp+270h+FindFileData.cFileName]; String2
0x180010ded  mov     rcx, [rcx+rdi*8]; String1
0x180010df1  call    cs:__imp__wcsicmp
0x180010df7  test    eax, eax
0x180010df9  jz      loc_1800110B3
0x180010dff  inc     edi
0x180010e01  cmp     edi, [r14+8]
0x180010e05  jb      short loc_180010DE5
0x180010e07  test    esi, esi
0x180010e09  jnz     loc_1800110B3
0x180010e0f  xor     esi, esi
0x180010e11  mov     edi, 320h
0x180010e16  mov     rdx, [r15+28h]; unsigned __int16 *
0x180010e1a  lea     r8, [rbp+270h+FindFileData.cFileName]; unsigned __int16 *
0x180010e1e  lea     rcx, [rbp+270h+lpFileName]; this
0x180010e22  call    ?SetPath@CBsString@@QEAAJPEBG000000000@Z; CBsString::SetPath(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180010e27  mov     [rbp+270h+var_2F0], eax
0x180010e2a  test    eax, eax
0x180010e2c  mov     eax, 306h
0x180010e31  js      loc_180010D2C
0x180010e37  mov     [rbp+270h+var_2EC], ax
0x180010e3b  lea     r9, _GUID_11a66efa_382e_451a_9234_1e0e12ef3085; riid
0x180010e42  lea     rax, [rsp+370h+var_2F8]
0x180010e47  xor     r8d, r8d; pUnkOuter
0x180010e4a  lea     rdx, CLSID_ShellLibrary; pclsid
0x180010e51  mov     [rsp+370h+ppv], rax; ppv
0x180010e56  xor     ecx, ecx; pszCLSID
0x180010e58  call    cs:__imp_SHCoCreateInstance
0x180010e5e  mov     [rbp+270h+var_2F0], eax
0x180010e61  test    eax, eax
0x180010e63  mov     eax, 308h
0x180010e68  js      loc_180010D2C
0x180010e6e  mov     rcx, [rbp+270h+lpFileName]; pszPath
0x180010e72  lea     r9, [rbp+270h+var_2B0]; ppv
0x180010e76  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180010e7d  mov     [rbp+270h+var_2EC], ax
0x180010e81  xor     edx, edx; pbc
0x180010e83  call    cs:__imp_SHCreateItemFromParsingName
0x180010e89  mov     [rbp+270h+var_2F0], eax
0x180010e8c  test    eax, eax
0x180010e8e  mov     eax, 30Bh
0x180010e93  js      loc_180010D2C
0x180010e99  mov     rcx, [rsp+370h+var_2F8]
0x180010e9e  xor     r8d, r8d
0x180010ea1  mov     rdx, [rbp+270h+var_2B0]
0x180010ea5  mov     [rbp+270h+var_2EC], ax
0x180010ea9  mov     rax, [rcx]
0x180010eac  mov     rax, [rax+18h]
0x180010eb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eb5  mov     [rbp+270h+var_2F0], eax
0x180010eb8  test    eax, eax
0x180010eba  js      loc_18001104B
0x180010ec0  mov     rcx, [rsp+370h+var_2F8]
0x180010ec5  lea     r9, [rbp+270h+var_2B8]
0x180010ec9  lea     r8, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b
0x180010ed0  mov     edx, 1
0x180010ed5  mov     rax, [rcx]
0x180010ed8  mov     rax, [rax+38h]
0x180010edc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee1  test    eax, eax
0x180010ee3  js      loc_180010FFA
0x180010ee9  mov     rcx, [rbp+270h+var_2B8]
0x180010eed  lea     rdx, [rsp+370h+var_300]
0x180010ef2  mov     rax, [rcx]
0x180010ef5  mov     rax, [rax+48h]
0x180010ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010efe  test    eax, eax
0x180010f00  js      loc_180010FFA
0x180010f06  mov     rcx, [rsp+370h+var_300]
0x180010f0b  lea     r8, [rsp+370h+var_310]
0x180010f10  xor     r9d, r9d
0x180010f13  mov     rax, [rcx]
0x180010f16  lea     edx, [r9+1]
0x180010f1a  mov     rax, [rax+18h]
0x180010f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f23  mov     [rbp+270h+var_2F0], eax
0x180010f26  test    eax, eax
0x180010f28  js      loc_1800110E3
0x180010f2e  mov     ecx, 316h
0x180010f33  mov     [rbp+270h+var_2EC], cx
0x180010f37  cmp     eax, 1
0x180010f3a  jz      loc_180010FFA
0x180010f40  mov     rcx, [rsp+370h+var_310]
0x180010f45  lea     r8, [rsp+370h+pv]
0x180010f4a  mov     edx, 80058000h
0x180010f4f  mov     rax, [rcx]
0x180010f52  mov     rax, [rax+28h]
0x180010f56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5b  mov     [rbp+270h+var_2F0], eax
0x180010f5e  test    eax, eax
0x180010f60  mov     eax, 319h
0x180010f65  js      loc_180010D2C
0x180010f6b  mov     rdx, [rsp+370h+pv]
0x180010f70  mov     r8d, 0C000016Fh
0x180010f76  mov     [rbp+270h+var_2EC], ax
0x180010f7a  mov     rcx, r13
0x180010f7d  mov     rax, [r13+0]
0x180010f81  mov     rax, [rax+20h]
0x180010f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8a  mov     [rbp+270h+var_2F0], eax
0x180010f8d  test    eax, eax
0x180010f8f  mov     eax, 31Ch
0x180010f94  js      loc_180010D2C
0x180010f9a  mov     rcx, [rsp+370h+pv]; pv
0x180010f9f  mov     [rbp+270h+var_2EC], ax
0x180010fa3  call    cs:__imp_CoTaskMemFree
0x180010fa9  mov     rcx, [rsp+370h+var_310]
0x180010fae  mov     [rsp+370h+pv], rsi
0x180010fb3  test    rcx, rcx
0x180010fb6  jz      short loc_180010FC9
0x180010fb8  mov     [rsp+370h+var_310], rsi
0x180010fbd  mov     rax, [rcx]
0x180010fc0  mov     rax, [rax+10h]
0x180010fc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fc9  mov     rcx, [rsp+370h+var_300]
0x180010fce  lea     r8, [rsp+370h+var_310]
0x180010fd3  xor     r9d, r9d
0x180010fd6  mov     rax, [rcx]
0x180010fd9  lea     edx, [r9+1]
0x180010fdd  mov     rax, [rax+18h]
0x180010fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fe6  mov     [rbp+270h+var_2F0], eax
0x180010fe9  test    eax, eax
0x180010feb  js      loc_1800110DD
0x180010ff1  mov     [rbp+270h+var_2EC], di
0x180010ff5  jmp     loc_180010F37
0x180010ffa  mov     rcx, [rsp+370h+var_310]
0x180010fff  test    rcx, rcx
0x180011002  jz      short loc_180011015
0x180011004  mov     rax, [rcx]
0x180011007  mov     rax, [rax+10h]
0x18001100b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011010  mov     [rsp+370h+var_310], rsi
0x180011015  mov     rcx, [rsp+370h+var_300]
0x18001101a  test    rcx, rcx
0x18001101d  jz      short loc_180011030
0x18001101f  mov     rax, [rcx]
0x180011022  mov     rax, [rax+10h]
0x180011026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001102b  mov     [rsp+370h+var_300], rsi
0x180011030  mov     rcx, [rbp+270h+var_2B8]
0x180011034  test    rcx, rcx
0x180011037  jz      short loc_18001107D
0x180011039  mov     rax, [rcx]
0x18001103c  mov     rax, [rax+10h]
0x180011040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011045  mov     [rbp+270h+var_2B8], rsi
0x180011049  jmp     short loc_18001107D
0x18001104b  mov     rcx, cs:WPP_GLOBAL_Control
0x180011052  cmp     rcx, r12
0x180011055  jz      short loc_18001107A
0x180011057  test    byte ptr [rcx+1Ch], 40h
0x18001105b  jz      short loc_18001107A
0x18001105d  mov     r9, [rbp+270h+lpFileName]
0x180011061  lea     r8, WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids
0x180011068  mov     rcx, [rcx+10h]
0x18001106c  mov     edx, 0Ch
0x180011071  mov     dword ptr [rsp+370h+ppv], eax
0x180011075  call    WPP_SF_Sd
0x18001107a  mov     [rbp+270h+var_2F0], esi
0x18001107d  mov     rcx, [rsp+370h+var_2F8]
0x180011082  test    rcx, rcx
0x180011085  jz      short loc_180011098
0x180011087  mov     rax, [rcx]
0x18001108a  mov     rax, [rax+10h]
0x18001108e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011093  mov     [rsp+370h+var_2F8], rsi
0x180011098  mov     rcx, [rbp+270h+var_2B0]
0x18001109c  test    rcx, rcx
0x18001109f  jz      short loc_1800110B5
0x1800110a1  mov     rax, [rcx]
0x1800110a4  mov     rax, [rax+10h]
0x1800110a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800110ad  mov     [rbp+270h+var_2B0], rsi
0x1800110b1  jmp     short loc_1800110B5
0x1800110b3  xor     esi, esi
0x1800110b5  lea     rdx, [rbp+270h+FindFileData]; lpFindFileData
0x1800110b9  mov     rcx, rbx; hFindFile
0x1800110bc  call    cs:__imp_FindNextFileW
0x1800110c2  test    eax, eax
0x1800110c4  jz      loc_18001114B
0x1800110ca  jmp     loc_180010DA8
0x1800110cf  mov     [rbp+270h+var_2F0], 80070057h
0x1800110d6  mov     [rbp+270h+var_2EA], r8w
0x1800110db  jmp     short loc_18001114B
0x1800110dd  mov     [rbp+270h+var_2EA], di
0x1800110e1  jmp     short loc_18001114B
0x1800110e3  mov     eax, 316h
0x1800110e8  jmp     loc_180010D2C
0x1800110ed  call    cs:__imp_GetLastError
0x1800110f3  cmp     eax, 3
0x1800110f6  jnz     short loc_18001114B
0x1800110f8  test    edi, edi
0x1800110fa  jz      short loc_18001114B
0x1800110fc  mov     rcx, cs:WPP_GLOBAL_Control
0x180011103  lea     r12, WPP_GLOBAL_Control
0x18001110a  cmp     rcx, r12
0x18001110d  jz      short loc_18001112C
0x18001110f  test    byte ptr [rcx+1Ch], 40h
0x180011113  jz      short loc_18001112C
0x180011115  mov     r9, [r15+28h]
0x180011119  lea     edx, [rax+8]
0x18001111c  mov     rcx, [rcx+10h]
0x180011120  lea     r8, WPP_54dd5ff1959335a765c661c9f9542d64_Traceguids
0x180011127  call    WPP_SF_S
0x18001112c  mov     r8, r15; struct _UserProfileData *
0x18001112f  mov     rdx, r13; struct ISdBackup2 *
0x180011132  call    ?_AddDefaultUserLibraryPathsToEngine@CSdController@@AEAAJPEAUISdBackup2@@PEAU_UserProfileData@@@Z; CSdController::_AddDefaultUserLibraryPathsToEngine(ISdBackup2 *,_UserProfileData *)
  ... truncated ...
```
