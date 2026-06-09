# RpcQueryVhdOfflineInformation

- ea: `0x180017e40`
- end: `0x180018648`
- name: `RpcQueryVhdOfflineInformation`
- size: `2056`
- prototype: `__int64 __fastcall(__int64, const wchar_t *, _QWORD *)`
- caller_count: `0`
- callee_count: `23`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180003f30`
- `0x180004db0`
- `0x180012b90`
- `0x180012c40`
- `0x180017e40`
- `0x180019b38`
- `0x18001a280`
- `0x18001a2a4`
- `0x18001a2c8`
- `0x18001a2ec`
- `0x18001ace4`
- `0x18001ad5c`
- `0x180035bcc`
- `0x180035d40`
- `0x180035db4`
- `0x180035e20`
- `0x180036560`
- `0x180036dd4`
- `0x180036ef8`
- `0x18004a7a4`
- `0x18004ad48`
- `0x18005a1cc`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185c4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800185c4`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800182a3`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800182a3`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180018562`
- `api-ms-win-core-registry-l1-1-0!RegUnLoadKeyW` at `0x180018562`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018374`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018460`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018374`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800183fb`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180018460`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184e7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800184e7`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800181ef`
- `api-ms-win-core-registry-l1-1-0!RegLoadKeyW` at `0x1800181ef`

## string_xrefs

- `0x1800184a8`: `\SYSTEM32\VMRDVCORE.dll`
- `0x180018235`: `\SYSTEM32\KERNEL32.dll`
- `0x180018303`: `InstallationType`
- `0x180017f45`: `CheckAccessToRpcMethod failed: 0x%x in %s`
- `0x1800180df`: `Failed to build target path failed: 0x%x in %s`
- `0x180017fb6`: `%s failed 0x%x: Failed to mount VHD %S `
- `0x1800180c2`: `Failed to build windows path failed: 0x%x in %s`
- `0x18001809a`: `RDV: RpcQueryVhdOfflineInformation, strTargetFilePath:%ws, strWindowsRootPath: %ws.`
- `0x180018176`: `SetPrivilege failed: 0x%x in %s`
- `0x180018224`: `Failed to build software path failed: 0x%x in %s`
- `0x180018395`: `RDV: RpcQueryVhdOfflineInformation, Failed to query %S registry value [0x%x].`
- `0x180018418`: `RDV: RpcQueryVhdOfflineInformation, Failed to query IMAGE_STATE registry value [0x%x].`
- `0x180018479`: `RDV: RpcQueryVhdOfflineInformation, Failed to query SYSPREP_MODE registry value [0x%x].`
- `0x1800184f7`: `RDV: RpcQueryVhdOfflineInformation, Failed to query Registry key [%S] [0x%x].`

## pseudocode

```c
__int64 __fastcall RpcQueryVhdOfflineInformation(__int64 a1, const wchar_t *a2, _QWORD *a3)
{
  int v5; // r14d
  void (__fastcall ***v6)(_QWORD, __int64); // r12
  char *v7; // rsi
  int v8; // edx
  signed int v9; // ebx
  int v10; // eax
  _QWORD *v11; // rax
  __int64 v12; // r8
  int v13; // eax
  int v14; // r14d
  unsigned int i; // edi
  int v16; // eax
  const unsigned __int16 *v17; // rax
  const unsigned __int16 *v18; // rax
  int v19; // eax
  __int64 v20; // rax
  __int64 v21; // r10
  char *v22; // rax
  const unsigned __int16 *v23; // rcx
  int v24; // eax
  unsigned int j; // edi
  const unsigned __int16 *v26; // rax
  const unsigned __int16 *v27; // r10
  int v28; // eax
  const WCHAR *v29; // rax
  LSTATUS KeyW; // eax
  const unsigned __int16 *v31; // rax
  const WCHAR *v32; // rax
  unsigned int k; // r14d
  __int64 v34; // rdi
  void *pvData; // rbx
  LSTATUS ValueW; // eax
  LSTATUS v37; // eax
  LSTATUS v38; // eax
  const unsigned __int16 *v39; // rax
  const unsigned __int16 *v40; // rax
  __int64 m; // rdi
  const struct std::nothrow_t *v42; // rdx
  int v43; // r15d
  const unsigned __int16 *v44; // rax
  RdVhd::Util::CVhdHelper *v45; // rcx
  const unsigned __int16 *v46; // rcx
  unsigned int v48; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbData; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pdwType; // [rsp+48h] [rbp-B8h] BYREF
  int v51; // [rsp+4Ch] [rbp-B4h]
  HKEY hkey; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  void **v54; // [rsp+60h] [rbp-A0h] BYREF
  int v55; // [rsp+68h] [rbp-98h]
  __int64 v56; // [rsp+6Ch] [rbp-94h]
  int v57; // [rsp+74h] [rbp-8Ch]
  __int64 v58; // [rsp+78h] [rbp-88h]
  int v59; // [rsp+80h] [rbp-80h]
  void **v60; // [rsp+88h] [rbp-78h] BYREF
  int v61; // [rsp+90h] [rbp-70h]
  __int64 v62; // [rsp+94h] [rbp-6Ch]
  int v63; // [rsp+9Ch] [rbp-64h]
  __int64 v64; // [rsp+A0h] [rbp-60h]
  int v65; // [rsp+A8h] [rbp-58h]
  _QWORD *v66; // [rsp+B0h] [rbp-50h]
  _QWORD v67[10]; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v68[592]; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v69[40]; // [rsp+360h] [rbp+260h] BYREF

  v66 = a3;
  hObject = (HANDLE)-1LL;
  `vector constructor iterator'(v69, 0x28u, 8u, (void *(*)(void *))CPathString::CPathString);
  v62 = 128;
  v64 = 0;
  v60 = &CPathString::`vftable';
  v63 = 0;
  v65 = 0x8000000;
  v61 = 0;
  `vector constructor iterator'(v67, 0x28u, 2u, (void *(*)(void *))CPathString::CPathString);
  v48 = 8;
  v51 = 0;
  v5 = 8;
  v6 = 0;
  v7 = 0;
  CRpcCallTrace::CRpcCallTrace((CRpcCallTrace *)v68, v8, "RpcQueryVhdOfflineInformation");
  if ( !a2 || !a3 )
  {
    v9 = -2147024809;
    _DbgPrintMessage(8, "Invalid input parameters failed: 0x%x in %s", 2147942487LL, "RpcQueryVhdOfflineInformation");
    goto LABEL_73;
  }
  v10 = CSessEnvRpc::CheckAccessToRpcMethod(L"O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899010-3337817248-2959896732-3640118089-1866760602)");
  v9 = v10;
  if ( v10 < 0 )
  {
    _DbgPrintMessage(8, "CheckAccessToRpcMethod failed: 0x%x in %s", (unsigned int)v10, "RpcQueryVhdOfflineInformation");
    goto LABEL_73;
  }
  *a3 = 0;
  v11 = operator new(8u, (const struct std::nothrow_t *)std::nothrow);
  v6 = (void (__fastcall ***)(_QWORD, __int64))v11;
  if ( !v11 )
  {
    v9 = -2147024882;
    _DbgPrintMessage(
      8,
      "Failed to allocate CVhdHelper failed: 0x%x in %s",
      -2147024882,
      "RpcQueryVhdOfflineInformation");
    v6 = 0;
    goto LABEL_73;
  }
  *v11 = &RdVhd::Util::CVhdHelper::`vftable';
  v13 = RdVhd::Util::CVhdHelper::MountVhdVolume(v11, a2, v12, v69, &v48, &hObject);
  v9 = v13;
  if ( v13 < 0 )
  {
    _DbgPrintMessage(8, "%s failed 0x%x: Failed to mount VHD %S ", "RpcQueryVhdOfflineInformation", v13, a2);
    goto LABEL_9;
  }
  v14 = 0;
  for ( i = 0; i < v48; ++i )
  {
    v58 = 0;
    v57 = 0;
    v55 = 0;
    v54 = &CPathString::`vftable';
    v56 = 128;
    v59 = 0x8000000;
    v16 = CPathString::BuildPath((CPathString *)&v54, (const struct CPathString *)&v69[5 * i], L"\\WINDOWS");
    v9 = v16;
    if ( v16 < 0 )
    {
      _DbgPrintMessage(
        8,
        "Failed to build target path failed: 0x%x in %s",
        (unsigned int)v16,
        "RpcQueryVhdOfflineInformation");
      goto LABEL_21;
    }
    v17 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v54);
    if ( (unsigned int)CSessEnvRpc::DoesFileExist(v17, 1) )
    {
      if ( v14 )
      {
        CPathString::~CPathString((CPathString *)&v54);
        v9 = -2012020204;
        goto LABEL_9;
      }
      v18 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v69[5 * i]);
      v19 = CPathString::BuildPath((CPathString *)&v60, v18, L"\\WINDOWS");
      v9 = v19;
      if ( v19 < 0 )
      {
        _DbgPrintMessage(
          8,
          "Failed to build windows path failed: 0x%x in %s",
          (unsigned int)v19,
          "RpcQueryVhdOfflineInformation");
LABEL_21:
        CPathString::~CPathString((CPathString *)&v54);
        goto LABEL_9;
      }
      v14 = 1;
      CBaseStringT<unsigned short>::PContents(&v60);
      v20 = CBaseStringT<unsigned short>::PContents(&v54);
      _DbgPrintMessage(
        1,
        "RDV: RpcQueryVhdOfflineInformation, strTargetFilePath:%ws, strWindowsRootPath: %ws.",
        v20,
        v21);
    }
    CPathString::~CPathString((CPathString *)&v54);
  }
  v22 = (char *)operator new[](0xC0Cu, (const struct std::nothrow_t *)std::nothrow);
  v7 = v22;
  if ( !v22 )
  {
    v9 = -2147024882;
    _DbgPrintMessage(8, "Failed to allocate memory failed: 0x%x in %s", 2147942414LL, "RpcQueryVhdOfflineInformation");
    goto LABEL_9;
  }
  memset_0(v22, 0, 0xC04u);
  *(_QWORD *)(v7 + 3076) = 0;
  v24 = CSessEnvRpc::SetPrivilege(v23, 1);
  v9 = v24;
  if ( v24 < 0 )
  {
    _DbgPrintMessage(8, "SetPrivilege failed: 0x%x in %s", (unsigned int)v24, "RpcQueryVhdOfflineInformation");
    goto LABEL_9;
  }
  v51 = 1;
  for ( j = 0; j < 2; ++j )
  {
    v26 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v60);
    v28 = CPathString::BuildPath((CPathString *)&v67[5 * j], v26, v27);
    v9 = v28;
    if ( v28 < 0 )
      goto LABEL_34;
    v29 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(&v67[5 * j]);
    KeyW = RegLoadKeyW(HKEY_LOCAL_MACHINE, off_18005F1F0[j], v29);
    v9 = KeyW;
    if ( KeyW > 0 )
      v9 = (unsigned __int16)KeyW | 0x80070000;
    if ( v9 < 0 )
    {
      _DbgPrintMessage(8, "Failed in RegLoadKey failed: 0x%x in %s", (unsigned int)v9, "RpcQueryVhdOfflineInformation");
      goto LABEL_9;
    }
  }
  v31 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v60);
  v28 = CPathString::BuildPath((CPathString *)v67, v31, L"\\SYSTEM32\\KERNEL32.dll");
  v9 = v28;
  if ( v28 < 0 )
  {
LABEL_34:
    _DbgPrintMessage(
      8,
      "Failed to build software path failed: 0x%x in %s",
      (unsigned int)v28,
      "RpcQueryVhdOfflineInformation");
    goto LABEL_9;
  }
  v32 = (const WCHAR *)CBaseStringT<unsigned short>::PContents(v67);
  *((_DWORD *)v7 + 768) = CSessEnvRpc::SessEnvGetBinaryType(v32);
  for ( k = 0; k < 4; ++k )
  {
    hkey = 0;
    pcbData = 0;
    pdwType = 0;
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, off_18005F1D0[k], 0, 0x20019u, &hkey) )
    {
      _DbgPrintMessage(
        4,
        "RDV: RpcQueryVhdOfflineInformation, Failed to query Registry key [%S] [0x%x].",
        off_18005F1D0[k],
        v9);
    }
    else
    {
      switch ( k )
      {
        case 0u:
          v34 = 0;
          while ( wcsicmp(off_18005F1B0[v34], L"CurrentVersion") )
          {
            if ( !wcsicmp(off_18005F1B0[v34], L"CurrentBuild") )
            {
              pvData = v7;
              goto LABEL_48;
            }
            if ( !wcsicmp(off_18005F1B0[v34], L"InstallationType") )
            {
              pvData = v7 + 1024;
              goto LABEL_48;
            }
            pvData = 0;
            if ( !wcsicmp(off_18005F1B0[v34], L"EditionId") )
            {
              pvData = v7 + 1536;
              goto LABEL_48;
            }
LABEL_49:
            ValueW = RegGetValueW(hkey, 0, off_18005F1B0[v34], 2u, &pdwType, pvData, &pcbData);
            v9 = ValueW;
            if ( ValueW > 0 )
              v9 = (unsigned __int16)ValueW | 0x80070000;
            if ( v9 < 0 )
              _DbgPrintMessage(
                4,
                "RDV: RpcQueryVhdOfflineInformation, Failed to query %S registry value [0x%x].",
                off_18005F1B0[v34],
                v9);
            if ( ++v34 == 4 )
              goto LABEL_68;
          }
          pvData = v7 + 512;
LABEL_48:
          pcbData = 512;
          goto LABEL_49;
        case 1u:
          pcbData = 512;
          v37 = RegGetValueW(hkey, 0, L"ImageState", 2u, &pdwType, v7 + 2048, &pcbData);
          v9 = v37;
          if ( v37 > 0 )
            v9 = (unsigned __int16)v37 | 0x80070000;
          if ( v9 < 0 )
            _DbgPrintMessage(
              4,
              "RDV: RpcQueryVhdOfflineInformation, Failed to query IMAGE_STATE registry value [0x%x].",
              (unsigned int)v9);
          break;
        case 2u:
          pcbData = 512;
          v38 = RegGetValueW(hkey, 0, L"SysprepMode", 2u, &pdwType, v7 + 2560, &pcbData);
          v9 = v38;
          if ( v38 > 0 )
            v9 = (unsigned __int16)v38 | 0x80070000;
          if ( v9 < 0 )
            _DbgPrintMessage(
              4,
              "RDV: RpcQueryVhdOfflineInformation, Failed to query SYSPREP_MODE registry value [0x%x].",
              (unsigned int)v9);
          break;
        default:
          *((_DWORD *)v7 + 769) = 1;
          v39 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(&v60);
          v9 = CPathString::BuildPath((CPathString *)v67, v39, L"\\SYSTEM32\\VMRDVCORE.dll");
          if ( v9 >= 0 )
          {
            v40 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(v67);
            if ( (unsigned int)CSessEnvRpc::DoesFileExist(v40, 0) )
              *((_DWORD *)v7 + 770) = 1;
          }
          break;
      }
LABEL_68:
      RegCloseKey(hkey);
    }
  }
  v9 = 0;
  *v66 = v7;
LABEL_9:
  v5 = v48;
LABEL_73:
  for ( m = 0; m != 2; ++m )
    RegUnLoadKeyW(HKEY_LOCAL_MACHINE, off_18005F1F0[m]);
  v43 = v51;
  if ( v9 < 0 && v7 )
    operator delete(v7, v42);
  if ( v6 )
  {
    if ( v5 )
    {
      v44 = (const unsigned __int16 *)CBaseStringT<unsigned short>::PContents(v69);
      RdVhd::Util::CVhdHelper::SetVolumeOffline(v45, v44);
    }
    (**v6)(v6, 1);
  }
  v46 = (const unsigned __int16 *)hObject;
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  if ( v43 )
    CSessEnvRpc::SetPrivilege(v46, 0);
  CRpcCallTrace::~CRpcCallTrace((CRpcCallTrace *)v68);
  `vector destructor iterator'(v67, 0x28u, 2u, (void (*)(void *))CPathString::~CPathString);
  CPathString::~CPathString((CPathString *)&v60);
  `vector destructor iterator'(v69, 0x28u, 8u, (void (*)(void *))CPathString::~CPathString);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180017e40  mov     [rsp-8+arg_0], rbx
0x180017e45  push    rbp
0x180017e46  push    rsi
0x180017e47  push    rdi
0x180017e48  push    r12
0x180017e4a  push    r13
0x180017e4c  push    r14
0x180017e4e  push    r15
0x180017e50  lea     rbp, [rsp-3B0h]
0x180017e58  sub     rsp, 4B0h
0x180017e5f  mov     rax, cs:__security_cookie
0x180017e66  xor     rax, rsp
0x180017e69  mov     [rbp+3E0h+var_40], rax
0x180017e70  mov     esi, 8
0x180017e75  mov     [rbp+3E0h+var_430], r8
0x180017e79  mov     r13, r8
0x180017e7c  mov     [rsp+4E0h+hObject], 0FFFFFFFFFFFFFFFFh
0x180017e85  mov     rdi, rdx
0x180017e88  lea     r9, ??0CPathString@@QEAA@XZ; void *(*)(void *)
0x180017e8f  mov     r8d, esi; unsigned __int64
0x180017e92  lea     rcx, [rbp+3E0h+var_180]; void *
0x180017e99  lea     r14d, [rsi+20h]
0x180017e9d  mov     edx, r14d; unsigned __int64
0x180017ea0  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180017ea5  xor     ebx, ebx
0x180017ea7  mov     [rbp+3E0h+var_44C], 80h
0x180017eaf  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180017eb6  mov     [rbp+3E0h+var_440], rbx
0x180017eba  lea     r9, ??0CPathString@@QEAA@XZ; void *(*)(void *)
0x180017ec1  mov     [rbp+3E0h+var_458], rax
0x180017ec5  lea     r8d, [rsi-6]; unsigned __int64
0x180017ec9  mov     [rbp+3E0h+var_444], ebx
0x180017ecc  mov     edx, r14d; unsigned __int64
0x180017ecf  mov     [rbp+3E0h+var_438], 8000000h
0x180017ed6  lea     rcx, [rbp+3E0h+var_420]; void *
0x180017eda  mov     [rbp+3E0h+var_450], ebx
0x180017edd  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x180017ee2  lea     r8, aRpcqueryvhdoff; "RpcQueryVhdOfflineInformation"
0x180017ee9  mov     [rsp+4E0h+var_4A0], esi
0x180017eed  lea     rcx, [rbp+3E0h+var_3D0]; this
0x180017ef1  mov     [rsp+4E0h+var_494], ebx
0x180017ef5  mov     r14d, esi
0x180017ef8  mov     r12d, ebx
0x180017efb  mov     esi, ebx
0x180017efd  call    ??0CRpcCallTrace@@QEAA@HPEBD@Z; CRpcCallTrace::CRpcCallTrace(int,char const *)
0x180017f02  test    rdi, rdi
0x180017f05  jnz     short loc_180017F2B
0x180017f07  mov     r8d, 80070057h
0x180017f0d  lea     rdx, aInvalidInputPa; "Invalid input parameters failed: 0x%x i"...
0x180017f14  mov     ebx, r8d
0x180017f17  lea     r9, aRpcqueryvhdoff; "RpcQueryVhdOfflineInformation"
0x180017f1e  mov     ecx, r14d; int
0x180017f21  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017f26  jmp     loc_18001854A
0x180017f2b  test    r13, r13
0x180017f2e  jz      short loc_180017F07
0x180017f30  lea     rcx, aOSygSydA0x0001_0; "O:SYG:SYD:(A;;0x0001;;;S-1-5-80-4130899"...
0x180017f37  call    ?CheckAccessToRpcMethod@CSessEnvRpc@@SAJPEBG@Z; CSessEnvRpc::CheckAccessToRpcMethod(ushort const *)
0x180017f3c  mov     ebx, eax
0x180017f3e  test    eax, eax
0x180017f40  jns     short loc_180017F4E
0x180017f42  mov     r8d, eax
0x180017f45  lea     rdx, aCheckaccesstor; "CheckAccessToRpcMethod failed: 0x%x in "...
0x180017f4c  jmp     short loc_180017F17
0x180017f4e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180017f55  mov     [r13+0], rsi
0x180017f59  mov     rcx, r14; unsigned __int64
0x180017f5c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180017f61  mov     r12, rax
0x180017f64  test    rax, rax
0x180017f67  jz      loc_180018528
0x180017f6d  lea     rax, ??_7CVhdHelper@Util@RdVhd@@6B@; const RdVhd::Util::CVhdHelper::`vftable'
0x180017f74  mov     rdx, rdi
0x180017f77  mov     [r12], rax
0x180017f7b  lea     r9, [rbp+3E0h+var_180]
0x180017f82  lea     rax, [rsp+4E0h+hObject]
0x180017f87  mov     rcx, r12
0x180017f8a  mov     [rsp+4E0h+pvData], rax
0x180017f8f  lea     rax, [rsp+4E0h+var_4A0]
0x180017f94  mov     [rsp+4E0h+phkResult], rax
0x180017f99  call    ?MountVhdVolume@CVhdHelper@Util@RdVhd@@QEBAJPEBGW4Lifetime@AttachLifetime@123@QEAVCPathString@@PEAKPEAPEAXPEAV6@@Z; RdVhd::Util::CVhdHelper::MountVhdVolume(ushort const *,RdVhd::Util::CVhdHelper::AttachLifetime::Lifetime,CPathString * const,ulong *,void * *,CPathString *)
0x180017f9e  mov     ebx, eax
0x180017fa0  test    eax, eax
0x180017fa2  jns     short loc_180017FCC
0x180017fa4  mov     r9d, eax
0x180017fa7  mov     [rsp+4E0h+phkResult], rdi
0x180017fac  lea     r8, aRpcqueryvhdoff; "RpcQueryVhdOfflineInformation"
0x180017fb3  mov     ecx, r14d; int
0x180017fb6  lea     rdx, aSFailed0xXFail; "%s failed 0x%x: Failed to mount VHD %S "
0x180017fbd  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180017fc2  mov     r14d, [rsp+4E0h+var_4A0]
0x180017fc7  jmp     loc_18001854A
0x180017fcc  xor     r15d, r15d
0x180017fcf  mov     r14d, r15d
0x180017fd2  mov     edi, r15d
0x180017fd5  cmp     edi, [rsp+4E0h+var_4A0]
0x180017fd9  jnb     loc_180018109
0x180017fdf  mov     [rsp+4E0h+var_468], r15
0x180017fe4  lea     rax, ??_7CPathString@@6B@; const CPathString::`vftable'
0x180017feb  mov     [rsp+4E0h+var_46C], r15d
0x180017ff0  lea     r8, aWindows_0; "\\WINDOWS"
0x180017ff7  mov     [rsp+4E0h+var_478], r15d
0x180017ffc  lea     r15, [rbp+3E0h+var_180]
0x180018003  mov     [rsp+4E0h+var_480], rax
0x180018008  mov     eax, edi
0x18001800a  mov     [rsp+4E0h+var_474], 80h
0x180018013  mov     [rbp+3E0h+var_460], 8000000h
0x18001801a  lea     rcx, [rax+rax*4]
0x18001801e  lea     r15, [r15+rcx*8]
0x180018022  mov     rdx, r15; struct CPathString *
0x180018025  lea     rcx, [rsp+4E0h+var_480]; this
0x18001802a  call    ?BuildPath@CPathString@@QEAAJAEBV1@PEBG@Z; CPathString::BuildPath(CPathString const &,ushort const *)
0x18001802f  mov     ebx, eax
0x180018031  test    eax, eax
0x180018033  js      loc_1800180DF
0x180018039  lea     rcx, [rsp+4E0h+var_480]
0x18001803e  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018043  mov     rcx, rax; unsigned __int16 *
0x180018046  mov     edx, 1; int
0x18001804b  call    ?DoesFileExist@CSessEnvRpc@@SAHPEBGH@Z; CSessEnvRpc::DoesFileExist(ushort const *,int)
0x180018050  test    eax, eax
0x180018052  jz      short loc_1800180AE
0x180018054  test    r14d, r14d
0x180018057  jnz     short loc_1800180CB
0x180018059  mov     rcx, r15
0x18001805c  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018061  lea     r8, aWindows_0; "\\WINDOWS"
0x180018068  mov     rdx, rax; unsigned __int16 *
0x18001806b  lea     rcx, [rbp+3E0h+var_458]; this
0x18001806f  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180018074  xor     r15d, r15d
0x180018077  mov     ebx, eax
0x180018079  test    eax, eax
0x18001807b  js      short loc_1800180C2
0x18001807d  lea     rcx, [rbp+3E0h+var_458]
0x180018081  lea     r14d, [r15+1]
0x180018085  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x18001808a  lea     rcx, [rsp+4E0h+var_480]
0x18001808f  mov     r10, rax
0x180018092  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018097  mov     r9, r10
0x18001809a  lea     rdx, aRdvRpcqueryvhd_1; "RDV: RpcQueryVhdOfflineInformation, str"...
0x1800180a1  mov     r8, rax
0x1800180a4  mov     ecx, r14d; int
0x1800180a7  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800180ac  jmp     short loc_1800180B1
0x1800180ae  xor     r15d, r15d
0x1800180b1  lea     rcx, [rsp+4E0h+var_480]; this
0x1800180b6  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800180bb  inc     edi
0x1800180bd  jmp     loc_180017FD5
0x1800180c2  lea     rdx, aFailedToBuildW; "Failed to build windows path failed: 0x"...
0x1800180c9  jmp     short loc_1800180E6
0x1800180cb  lea     rcx, [rsp+4E0h+var_480]; this
0x1800180d0  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x1800180d5  mov     ebx, 88130214h
0x1800180da  jmp     loc_180017FC2
0x1800180df  lea     rdx, aFailedToBuildT; "Failed to build target path failed: 0x%"...
0x1800180e6  mov     r8d, eax
0x1800180e9  lea     r9, aRpcqueryvhdoff; "RpcQueryVhdOfflineInformation"
0x1800180f0  mov     ecx, 8; int
0x1800180f5  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x1800180fa  lea     rcx, [rsp+4E0h+var_480]; this
0x1800180ff  call    ??1CPathString@@QEAA@XZ; CPathString::~CPathString(void)
0x180018104  jmp     loc_180017FC2
0x180018109  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180018110  mov     ecx, 0C0Ch; unsigned __int64
0x180018115  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001811a  mov     rsi, rax
0x18001811d  test    rax, rax
0x180018120  jnz     short loc_180018148
0x180018122  mov     r8d, 8007000Eh
0x180018128  lea     rdx, aFailedToAlloca_1; "Failed to allocate memory failed: 0x%x "...
0x18001812f  mov     ebx, r8d
0x180018132  lea     r9, aRpcqueryvhdoff; "RpcQueryVhdOfflineInformation"
0x180018139  mov     ecx, 8; int
0x18001813e  call    ?_DbgPrintMessage@@YAXHPEBDZZ; _DbgPrintMessage(int,char const *,...)
0x180018143  jmp     loc_180017FC2
0x180018148  xor     edx, edx; Val
0x18001814a  mov     r8d, 0C04h; Size
0x180018150  mov     rcx, rsi; void *
0x180018153  call    memset_0
0x180018158  mov     edx, 1; int
0x18001815d  mov     qword ptr [rsi+0C04h], 0
0x180018168  call    ?SetPrivilege@CSessEnvRpc@@SAJPEBGH@Z; CSessEnvRpc::SetPrivilege(ushort const *,int)
0x18001816d  mov     ebx, eax
0x18001816f  test    eax, eax
0x180018171  jns     short loc_18001817F
0x180018173  mov     r8d, eax
0x180018176  lea     rdx, aSetprivilegeFa; "SetPrivilege failed: 0x%x in %s"
0x18001817d  jmp     short loc_180018132
0x18001817f  mov     [rsp+4E0h+var_494], 1
0x180018187  mov     edi, r15d
0x18001818a  lea     rcx, [rbp+3E0h+var_458]
0x18001818e  cmp     edi, 2
0x180018191  jnb     loc_180018230
0x180018197  mov     r14d, edi
0x18001819a  lea     r10, __ImageBase
0x1800181a1  mov     r10, ds:rva off_18005F200[r10+r14*8]; "\\SYSTEM32\\CONFIG\\SOFTWARE" ...
0x1800181a9  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800181ae  lea     rcx, [r14+r14*4]
0x1800181b2  mov     r8, r10; unsigned __int16 *
0x1800181b5  lea     r15, [rbp+3E0h+var_420]
0x1800181b9  mov     rdx, rax; unsigned __int16 *
0x1800181bc  lea     r15, [r15+rcx*8]
0x1800181c0  mov     rcx, r15; this
0x1800181c3  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x1800181c8  mov     ebx, eax
0x1800181ca  test    eax, eax
0x1800181cc  js      short loc_180018221
0x1800181ce  mov     rcx, r15
0x1800181d1  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x1800181d6  mov     r8, rax; lpFile
0x1800181d9  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800181e0  lea     rax, __ImageBase
0x1800181e7  mov     rdx, ds:rva off_18005F1F0[rax+r14*8]; lpSubKey
0x1800181ef  call    cs:__imp_RegLoadKeyW
0x1800181f5  xor     r15d, r15d
0x1800181f8  mov     ebx, eax
0x1800181fa  test    eax, eax
0x1800181fc  jle     short loc_180018207
0x1800181fe  movzx   ebx, ax
0x180018201  or      ebx, 80070000h
0x180018207  test    ebx, ebx
0x180018209  js      short loc_180018212
0x18001820b  inc     edi
0x18001820d  jmp     loc_18001818A
0x180018212  mov     r8d, ebx
0x180018215  lea     rdx, aFailedInRegloa; "Failed in RegLoadKey failed: 0x%x in %s"
0x18001821c  jmp     loc_180018132
0x180018221  mov     r8d, eax
0x180018224  lea     rdx, aFailedToBuildS_0; "Failed to build software path failed: 0"...
0x18001822b  jmp     loc_180018132
0x180018230  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018235  lea     r8, aSystem32Kernel; "\\SYSTEM32\\KERNEL32.dll"
0x18001823c  mov     rdx, rax; unsigned __int16 *
0x18001823f  lea     rcx, [rbp+3E0h+var_420]; this
0x180018243  call    ?BuildPath@CPathString@@QEAAJPEBG0@Z; CPathString::BuildPath(ushort const *,ushort const *)
0x180018248  mov     ebx, eax
0x18001824a  test    eax, eax
0x18001824c  js      short loc_180018221
0x18001824e  lea     rcx, [rbp+3E0h+var_420]
0x180018252  call    ?PContents@?$CBaseStringT@G@@QEBAPEBGXZ; CBaseStringT<ushort>::PContents(void)
0x180018257  mov     rcx, rax; lpFileName
0x18001825a  call    ?SessEnvGetBinaryType@CSessEnvRpc@@SAKPEBG@Z; CSessEnvRpc::SessEnvGetBinaryType(ushort const *)
0x18001825f  mov     [rsi+0C00h], eax
0x180018265  lea     r13, __ImageBase
0x18001826c  mov     r14d, r15d
0x18001826f  lea     rax, [rsp+4E0h+hkey]
0x180018274  mov     edi, r14d
0x180018277  mov     r9d, 20019h; samDesired
0x18001827d  mov     [rsp+4E0h+hkey], r15
0x180018282  xor     r8d, r8d; ulOptions
0x180018285  mov     [rsp+4E0h+var_49C], r15d
0x18001828a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180018291  mov     [rsp+4E0h+pdwType], r15d
0x180018296  mov     rdx, ds:rva off_18005F1D0[r13+rdi*8]; lpSubKey
0x18001829e  mov     [rsp+4E0h+phkResult], rax; phkResult
0x1800182a3  call    cs:__imp_RegOpenKeyExW
0x1800182a9  test    eax, eax
0x1800182ab  jnz     loc_1800184EF
0x1800182b1  test    r14d, r14d
0x1800182b4  jnz     loc_1800183BB
0x1800182ba  mov     rdi, r15
0x1800182bd  mov     rcx, ds:rva off_18005F1B0[r13+rdi*8]; String1
0x1800182c5  lea     rdx, aCurrentversion; "CurrentVersion"
0x1800182cc  call    _wcsicmp
0x1800182d1  test    eax, eax
0x1800182d3  jnz     short loc_1800182DE
0x1800182d5  lea     rbx, [rsi+200h]
0x1800182dc  jmp     short loc_18001833E
0x1800182de  mov     rcx, ds:rva off_18005F1B0[r13+rdi*8]; String1
0x1800182e6  lea     rdx, aCurrentbuild; "CurrentBuild"
0x1800182ed  call    _wcsicmp
0x1800182f2  test    eax, eax
0x1800182f4  jnz     short loc_1800182FB
0x1800182f6  mov     rbx, rsi
0x1800182f9  jmp     short loc_18001833E
0x1800182fb  mov     rcx, ds:rva off_18005F1B0[r13+rdi*8]; String1
0x180018303  lea     rdx, aInstallationty; "InstallationType"
0x18001830a  call    _wcsicmp
0x18001830f  test    eax, eax
0x180018311  jnz     short loc_18001831C
0x180018313  lea     rbx, [rsi+400h]
0x18001831a  jmp     short loc_18001833E
0x18001831c  mov     rcx, ds:rva off_18005F1B0[r13+rdi*8]; String1
0x180018324  lea     rdx, aEditionid; "EditionId"
0x18001832b  mov     rbx, r15
0x18001832e  call    _wcsicmp
0x180018333  test    eax, eax
0x180018335  jnz     short loc_180018346
0x180018337  lea     rbx, [rsi+600h]
0x18001833e  mov     [rsp+4E0h+var_49C], 200h
0x180018346  mov     r8, ds:rva off_18005F1B0[r13+rdi*8]; lpValue
0x18001834e  lea     rax, [rsp+4E0h+var_49C]
0x180018353  mov     rcx, [rsp+4E0h+hkey]; hkey
0x180018358  mov     r9d, 2; dwFlags
0x18001835e  mov     [rsp+4E0h+pcbData], rax; pcbData
0x180018363  xor     edx, edx; lpSubKey
0x180018365  lea     rax, [rsp+4E0h+pdwType]
  ... truncated ...
```
