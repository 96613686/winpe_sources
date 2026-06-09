# VltOpenVault

- ea: `0x180026a80`
- end: `0x180027330`
- name: `VltOpenVault`
- size: `2224`
- prototype: `__int64 __fastcall(__int64, const struct _GUID *, int, WCHAR **)`
- caller_count: `0`
- callee_count: `19`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003140`
- `0x180006610`
- `0x180011110`
- `0x180012210`
- `0x180013390`
- `0x180015568`
- `0x18001eda0`
- `0x180020a24`
- `0x180021b70`
- `0x180026a80`
- `0x18003a580`
- `0x18003b7b0`
- `0x18003b7d8`
- `0x18003b9ac`
- `0x18003be38`
- `0x18003d780`
- `0x180048c64`
- `0x180048ccc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c5c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180026c5c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026ba0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026ba0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027300`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026e60`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026ed0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180026f50`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027010`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027080`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027100`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180027300`
- `RPCRT4!RpcRevertToSelf` at `0x180026bf7`
- `RPCRT4!RpcRevertToSelf` at `0x180026bf7`
- `SspiCli!GetUserNameExW` at `0x18002711c`
- `SspiCli!GetUserNameExW` at `0x18002711c`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026e3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026eab`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026f28`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026fe7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002705b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800270d8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800272d9`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026e3a`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026eab`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026f28`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x180026fe7`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x18002705b`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800270d8`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalSize` at `0x1800272d9`
- `ntdll!NtSetInformationThread` at `0x180026c23`
- `ntdll!NtSetInformationThread` at `0x180026c23`

## string_xrefs

- `0x180026afd`: `VltOpenVault`

## pseudocode

```c
__int64 __fastcall VltOpenVault(__int64 a1, const struct _GUID *a2, int a3, WCHAR **a4)
{
  __int64 v7; // rax
  const char *v8; // r8
  __int64 v9; // rdx
  char *v10; // rcx
  char v11; // r9
  char *v12; // rax
  PVOID *v13; // rcx
  char *v14; // rax
  CVaultMgr *v15; // rcx
  int v16; // r8d
  WCHAR *v17; // rdi
  NTSTATUS v18; // eax
  _DWORD *v20; // rsi
  unsigned int UserVaultManager; // eax
  int v22; // edx
  int v23; // r8d
  unsigned int v24; // ebx
  PVOID *v25; // r10
  __int64 v26; // rdx
  HLOCAL v27; // rcx
  _BYTE *v28; // rax
  _BYTE *v29; // rbx
  unsigned int Vault; // eax
  int v31; // edx
  int v32; // r8d
  unsigned int v33; // esi
  PVOID *v34; // r10
  SIZE_T v35; // rax
  WCHAR *v36; // rcx
  __int64 v37; // rcx
  _BYTE *v38; // rax
  SIZE_T v39; // rax
  _BYTE *v40; // rcx
  HLOCAL v41; // rbx
  __int64 v42; // rcx
  _BYTE *v43; // rax
  SIZE_T v44; // rax
  _BYTE *v45; // rdx
  unsigned int v46; // eax
  int v47; // edx
  int v48; // r8d
  unsigned int v49; // esi
  PVOID *v50; // r10
  SIZE_T v51; // rax
  WCHAR *v52; // rcx
  __int64 v53; // rcx
  _BYTE *v54; // rax
  SIZE_T v55; // rax
  _BYTE *v56; // rcx
  HLOCAL v57; // rbx
  __int64 v58; // rcx
  _BYTE *v59; // rax
  SIZE_T v60; // rax
  _BYTE *v61; // rdx
  HLOCAL v62; // rsi
  __int64 v63; // rax
  int v64; // edx
  int v65; // r8d
  unsigned int v66; // ebx
  PVOID *v67; // r10
  unsigned int v68; // edi
  __int64 v69; // rcx
  _BYTE *v70; // rax
  SIZE_T v71; // rax
  _BYTE *v72; // rcx
  int v73; // [rsp+40h] [rbp-C0h] BYREF
  char v74[8]; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE ThreadInformation; // [rsp+50h] [rbp-B0h] BYREF
  int v76; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall *v77)(); // [rsp+60h] [rbp-A0h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v79; // [rsp+70h] [rbp-90h]
  ULONG nSize; // [rsp+78h] [rbp-88h] BYREF
  __int64 (__fastcall *v81)(); // [rsp+80h] [rbp-80h] BYREF
  HLOCAL v82; // [rsp+88h] [rbp-78h] BYREF
  unsigned int v83; // [rsp+90h] [rbp-70h]
  _QWORD v84[2]; // [rsp+98h] [rbp-68h] BYREF
  int v85; // [rsp+A8h] [rbp-58h]
  _BYTE v86[64]; // [rsp+B0h] [rbp-50h] BYREF
  int *v87; // [rsp+F0h] [rbp-10h]

  v73 = 0;
  v81 = AutoDereference<IVaultKeyManager>;
  v82 = 0;
  v83 = 0;
  v77 = AutoDereference<IVaultKeyManager>;
  hMem = 0;
  v79 = 0;
  v85 = 0;
  v84[0] = 0;
  v74[0] = 0;
  ThreadInformation = 0;
  nSize = 257;
  v7 = 2147483646;
  v8 = "VltOpenVault";
  v9 = 64;
  v10 = v86;
  do
  {
    if ( !v7 )
      break;
    v11 = *v8;
    if ( !*v8 )
      break;
    ++v8;
    *v10++ = v11;
    --v7;
    --v9;
  }
  while ( v9 );
  v12 = v10 - 1;
  if ( v9 )
    v12 = v10;
  *v12 = 0;
  v87 = &v73;
  v13 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, v8, v86);
      v13 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 8) != 0 )
      WPP_SF__guid_(v13[2], 111, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, a2);
  }
  v14 = (char *)LocalAlloc(0x40u, 0x258u);
  v17 = (WCHAR *)v14;
  v84[1] = v14;
  if ( v14 )
  {
    v20 = v14 + 76;
    UserVaultManager = CVaultMgr::GetUserVaultManager(
                         v15,
                         1u,
                         (struct CUserVaultMgr **)&hMem,
                         (unsigned __int8 *const)v14 + 8,
                         (struct _LUID *)(v14 + 76));
    v24 = UserVaultManager;
    v73 = UserVaultManager;
    if ( UserVaultManager )
    {
      v25 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
      {
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            112,
            &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
            UserVaultManager);
          v24 = v73;
          v25 = (PVOID *)WPP_GLOBAL_Control;
        }
        if ( v25 != &WPP_GLOBAL_Control && (*((_BYTE *)v25 + 28) & 8) != 0 )
          WPP_SF_sD((unsigned int)v25[2], v22, v23, (unsigned int)v86, *v87);
      }
      CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v74);
      VaultFreeInternal(v17);
      v27 = hMem;
      if ( hMem )
      {
        if ( v79 )
        {
          v26 = v79;
          v28 = hMem;
          do
          {
            *v28++ = 0;
            --v26;
          }
          while ( v26 );
        }
        if ( v77 )
          ((void (__fastcall *)(HLOCAL, __int64))v77)(v27, v26);
        else
          VaultFreeInternal(v27);
      }
      return v24;
    }
    else
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          113,
          &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
          *((unsigned int *)v17 + 20),
          *v20);
      v29 = hMem;
      Vault = CUserVaultMgr::GetVault((CUserVaultMgr *)hMem, a2, (struct CUserVault **)&v82);
      v33 = Vault;
      v73 = Vault;
      if ( Vault )
      {
        v34 = (PVOID *)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
        {
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 114, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, Vault);
            v33 = v73;
            v34 = (PVOID *)WPP_GLOBAL_Control;
          }
          if ( v34 != &WPP_GLOBAL_Control && (*((_BYTE *)v34 + 28) & 8) != 0 )
            WPP_SF_sD((unsigned int)v34[2], v31, v32, (unsigned int)v86, *v87);
        }
        CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v74);
        if ( v17 )
        {
          v35 = LocalSize(v17);
          if ( v35 )
          {
            v36 = v17;
            do
            {
              *(_BYTE *)v36 = 0;
              v36 = (WCHAR *)((char *)v36 + 1);
              --v35;
            }
            while ( v35 );
          }
          LocalFree(v17);
        }
        if ( v29 )
        {
          if ( v79 )
          {
            v37 = v79;
            v38 = v29;
            do
            {
              *v38++ = 0;
              --v37;
            }
            while ( v37 );
          }
          if ( v77 )
          {
            ((void (__fastcall *)(_BYTE *))v77)(v29);
          }
          else
          {
            v39 = LocalSize(v29);
            if ( v39 )
            {
              v40 = v29;
              do
              {
                *v40++ = 0;
                --v39;
              }
              while ( v39 );
            }
            LocalFree(v29);
          }
        }
        v41 = v82;
        if ( v82 )
        {
          if ( v83 )
          {
            v42 = v83;
            v43 = v82;
            do
            {
              *v43++ = 0;
              --v42;
            }
            while ( v42 );
          }
          if ( v81 )
          {
            ((void (__fastcall *)(HLOCAL))v81)(v41);
          }
          else if ( v41 )
          {
            v44 = LocalSize(v41);
            if ( v44 )
            {
              v45 = v41;
              do
              {
                *v45++ = 0;
                --v44;
              }
              while ( v44 );
            }
            LocalFree(v41);
          }
        }
        return v33;
      }
      else
      {
        v46 = CVaultRpcImpersonate::Impersonate((CVaultRpcImpersonate *)v74, 1);
        v49 = v46;
        v73 = v46;
        if ( v46 )
        {
          v50 = (PVOID *)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
          {
            if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 115, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids, v46);
              v49 = v73;
              v50 = (PVOID *)WPP_GLOBAL_Control;
            }
            if ( v50 != &WPP_GLOBAL_Control && (*((_BYTE *)v50 + 28) & 8) != 0 )
              WPP_SF_sD((unsigned int)v50[2], v47, v48, (unsigned int)v86, *v87);
          }
          CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v74);
          if ( v17 )
          {
            v51 = LocalSize(v17);
            if ( v51 )
            {
              v52 = v17;
              do
              {
                *(_BYTE *)v52 = 0;
                v52 = (WCHAR *)((char *)v52 + 1);
                --v51;
              }
              while ( v51 );
            }
            LocalFree(v17);
          }
          if ( v29 )
          {
            if ( v79 )
            {
              v53 = v79;
              v54 = v29;
              do
              {
                *v54++ = 0;
                --v53;
              }
              while ( v53 );
            }
            if ( v77 )
            {
              ((void (__fastcall *)(_BYTE *))v77)(v29);
            }
            else
            {
              v55 = LocalSize(v29);
              if ( v55 )
              {
                v56 = v29;
                do
                {
                  *v56++ = 0;
                  --v55;
                }
                while ( v55 );
              }
              LocalFree(v29);
            }
          }
          v57 = v82;
          if ( v82 )
          {
            if ( v83 )
            {
              v58 = v83;
              v59 = v82;
              do
              {
                *v59++ = 0;
                --v58;
              }
              while ( v58 );
            }
            if ( v81 )
            {
              ((void (__fastcall *)(HLOCAL))v81)(v57);
            }
            else if ( v57 )
            {
              v60 = LocalSize(v57);
              if ( v60 )
              {
                v61 = v57;
                do
                {
                  *v61++ = 0;
                  --v60;
                }
                while ( v60 );
              }
              LocalFree(v57);
            }
          }
          return v49;
        }
        else
        {
          GetUserNameExW(NameSamCompatible, v17 + 43, &nSize);
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
            WPP_SF_S(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              116,
              &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
              v17 + 43);
          v76 = 0;
          v62 = v82;
          v63 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)v82 + 1) + 216LL))(*((_QWORD *)v82 + 1));
          if ( (unsigned int)VaultAccessCheck(0, v63, &v76) )
          {
            *((_BYTE *)v17 + 85) = v76;
            if ( (a3 & 0x10000000) != 0 )
            {
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 118, &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids);
              *((_BYTE *)v17 + 84) = 1;
            }
            *(_QWORD *)v17 = v62;
            *a4 = v17;
            v68 = v73;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
              WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), *v87, v65, (unsigned int)v86, *v87);
            CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v74);
            if ( v29 )
            {
              if ( v79 )
              {
                v69 = v79;
                v70 = v29;
                do
                {
                  *v70++ = 0;
                  --v69;
                }
                while ( v69 );
              }
              if ( v77 )
              {
                ((void (__fastcall *)(_BYTE *))v77)(v29);
              }
              else
              {
                v71 = LocalSize(v29);
                if ( v71 )
                {
                  v72 = v29;
                  do
                  {
                    *v72++ = 0;
                    --v71;
                  }
                  while ( v71 );
                }
                LocalFree(v29);
              }
            }
            return v68;
          }
          else
          {
            v66 = 1168;
            v73 = 1168;
            v67 = (PVOID *)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_d(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  117,
                  &WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids,
                  1168);
                v66 = v73;
                v67 = (PVOID *)WPP_GLOBAL_Control;
              }
              if ( v67 != &WPP_GLOBAL_Control && (*((_BYTE *)v67 + 28) & 8) != 0 )
                WPP_SF_sD((unsigned int)v67[2], v64, v65, (unsigned int)v86, *v87);
            }
            CVaultRpcImpersonate::~CVaultRpcImpersonate((CVaultRpcImpersonate *)v74);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(v84);
            CVaultAutoPtr<HKEY__ *,long,HKEY__ *,0>::Delete(&v77);
            CVaultAutoPtr<CUserVault *,void,CUserVault *,0>::Delete(&v81);
            return v66;
          }
        }
      }
    }
  }
  else
  {
    v73 = 14;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_sD(*((_QWORD *)WPP_GLOBAL_Control + 2), *v87, v16, (unsigned int)v86, *v87);
    CVaultIntegrityLevel::~CVaultIntegrityLevel(&ThreadInformation);
    if ( v74[0] )
    {
      RpcRevertToSelf();
      v74[0] = 0;
    }
    if ( ThreadInformation )
    {
      v18 = NtSetInformationThread((HANDLE)0xFFFFFFFFFFFFFFFELL, ThreadImpersonationToken, &ThreadInformation, 8u);
      if ( v18 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids,
          (unsigned int)v18);
      CloseHandle(ThreadInformation);
      ThreadInformation = 0;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids);
    }
    return 14;
  }
}

```

## disassembly

```asm
0x180026a80  mov     [rsp-8+arg_0], rbx
0x180026a85  push    rbp
0x180026a86  push    rsi
0x180026a87  push    rdi
0x180026a88  push    r12
0x180026a8a  push    r13
0x180026a8c  push    r14
0x180026a8e  push    r15
0x180026a90  lea     rbp, [rsp-10h]
0x180026a95  sub     rsp, 110h
0x180026a9c  mov     rax, cs:__security_cookie
0x180026aa3  xor     rax, rsp
0x180026aa6  mov     [rbp+40h+var_40], rax
0x180026aaa  mov     r12, r9
0x180026aad  mov     r15d, r8d
0x180026ab0  mov     r14, rdx
0x180026ab3  xor     ebx, ebx
0x180026ab5  mov     [rsp+140h+var_100], ebx
0x180026ab9  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180026ac0  mov     [rbp+40h+var_C0], rax
0x180026ac4  mov     [rbp+40h+var_B8], rbx
0x180026ac8  mov     [rbp+40h+var_B0], ebx
0x180026acb  lea     rax, ??$AutoDereference@UIVaultKeyManager@@@@YAXPEAUIVaultKeyManager@@@Z; AutoDereference<IVaultKeyManager>(IVaultKeyManager *)
0x180026ad2  mov     [rsp+140h+var_E0], rax
0x180026ad7  mov     [rsp+140h+hMem], rbx
0x180026adc  mov     [rsp+140h+var_D0], ebx
0x180026ae0  mov     [rbp+40h+var_98], ebx
0x180026ae3  mov     [rbp+40h+var_A8], rbx
0x180026ae7  mov     [rsp+140h+var_F8], bl
0x180026aeb  mov     [rsp+140h+ThreadInformation], rbx
0x180026af0  mov     [rsp+140h+nSize], 101h
0x180026af8  mov     eax, 7FFFFFFEh
0x180026afd  lea     r8, aVltopenvault; "VltOpenVault"
0x180026b04  mov     edx, 40h ; '@'
0x180026b09  lea     rcx, [rbp+40h+var_90]
0x180026b0d  nop     dword ptr [rax]
0x180026b10  test    rax, rax
0x180026b13  jz      short loc_180026B30
0x180026b15  movzx   r9d, byte ptr [r8]
0x180026b19  test    r9b, r9b
0x180026b1c  jz      short loc_180026B30
0x180026b1e  inc     r8
0x180026b21  mov     [rcx], r9b
0x180026b24  inc     rcx
0x180026b27  dec     rax
0x180026b2a  sub     rdx, 1
0x180026b2e  jnz     short loc_180026B10
0x180026b30  lea     rax, [rcx-1]
0x180026b34  test    rdx, rdx
0x180026b37  cmovnz  rax, rcx
0x180026b3b  mov     [rax], bl
0x180026b3d  lea     rax, [rsp+140h+var_100]
0x180026b42  mov     [rbp+40h+var_50], rax
0x180026b46  lea     r13, WPP_GLOBAL_Control
0x180026b4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b54  cmp     rcx, r13
0x180026b57  jz      short loc_180026B96
0x180026b59  test    byte ptr [rcx+1Ch], 8
0x180026b5d  jz      short loc_180026B73
0x180026b5f  lea     r9, [rbp+40h+var_90]
0x180026b63  mov     rcx, [rcx+10h]
0x180026b67  call    WPP_SF_s
0x180026b6c  mov     rcx, cs:WPP_GLOBAL_Control
0x180026b73  cmp     rcx, r13
0x180026b76  jz      short loc_180026B96
0x180026b78  test    byte ptr [rcx+1Ch], 8
0x180026b7c  jz      short loc_180026B96
0x180026b7e  mov     edx, 6Fh ; 'o'
0x180026b83  mov     r9, r14
0x180026b86  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180026b8d  mov     rcx, [rcx+10h]
0x180026b91  call    WPP_SF__guid_
0x180026b96  mov     edx, 258h; uBytes
0x180026b9b  mov     ecx, 40h ; '@'; uFlags
0x180026ba0  call    cs:__imp_LocalAlloc
0x180026ba6  mov     rdi, rax
0x180026ba9  mov     [rbp+40h+var_A0], rax
0x180026bad  test    rax, rax
0x180026bb0  jnz     loc_180026C99
0x180026bb6  mov     [rsp+140h+var_100], 0Eh
0x180026bbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180026bc5  cmp     rcx, r13
0x180026bc8  jz      short loc_180026BE7
0x180026bca  test    byte ptr [rcx+1Ch], 8
0x180026bce  jz      short loc_180026BE7
0x180026bd0  mov     rax, [rbp+40h+var_50]
0x180026bd4  mov     edx, [rax]
0x180026bd6  mov     dword ptr [rsp+140h+var_120], edx
0x180026bda  lea     r9, [rbp+40h+var_90]
0x180026bde  mov     rcx, [rcx+10h]
0x180026be2  call    WPP_SF_sD
0x180026be7  lea     rcx, [rsp+140h+ThreadInformation]; ThreadInformation
0x180026bec  call    ??1CVaultIntegrityLevel@@QEAA@XZ; CVaultIntegrityLevel::~CVaultIntegrityLevel(void)
0x180026bf1  cmp     [rsp+140h+var_F8], bl
0x180026bf5  jz      short loc_180026C01
0x180026bf7  call    cs:__imp_RpcRevertToSelf
0x180026bfd  mov     [rsp+140h+var_F8], bl
0x180026c01  cmp     [rsp+140h+ThreadInformation], rbx
0x180026c06  jz      loc_180026C8F
0x180026c0c  mov     r9d, 8; ThreadInformationLength
0x180026c12  lea     r8, [rsp+140h+ThreadInformation]; ThreadInformation
0x180026c17  mov     edx, 5; ThreadInformationClass
0x180026c1c  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x180026c23  call    cs:__imp_NtSetInformationThread
0x180026c29  test    eax, eax
0x180026c2b  jns     short loc_180026C57
0x180026c2d  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c34  cmp     rcx, r13
0x180026c37  jz      short loc_180026C57
0x180026c39  test    byte ptr [rcx+1Ch], 2
0x180026c3d  jz      short loc_180026C57
0x180026c3f  mov     edx, 0Ah
0x180026c44  mov     r9d, eax
0x180026c47  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x180026c4e  mov     rcx, [rcx+10h]
0x180026c52  call    WPP_SF_d
0x180026c57  mov     rcx, [rsp+140h+ThreadInformation]; hObject
0x180026c5c  call    cs:__imp_CloseHandle
0x180026c62  mov     [rsp+140h+ThreadInformation], rbx
0x180026c67  mov     rcx, cs:WPP_GLOBAL_Control
0x180026c6e  cmp     rcx, r13
0x180026c71  jz      short loc_180026C8F
0x180026c73  test    byte ptr [rcx+1Ch], 8
0x180026c77  jz      short loc_180026C8F
0x180026c79  mov     edx, 0Bh
0x180026c7e  lea     r8, WPP_fc1af33029303d26f917cfed6bc21a33_Traceguids
0x180026c85  mov     rcx, [rcx+10h]
0x180026c89  call    WPP_SF_
0x180026c8e  nop
0x180026c8f  mov     eax, 0Eh
0x180026c94  jmp     loc_180027309
0x180026c99  lea     rsi, [rax+4Ch]
0x180026c9d  lea     r9, [rax+8]; unsigned __int8 *
0x180026ca1  mov     [rsp+140h+var_120], rsi; struct _LUID *
0x180026ca6  lea     r8, [rsp+140h+hMem]; struct CUserVaultMgr **
0x180026cab  mov     dl, 1; unsigned __int8
0x180026cad  call    ?GetUserVaultManager@CVaultMgr@@QEAAKEPEAPEAVCUserVaultMgr@@QEAEPEAU_LUID@@PEAKPEAPEAX@Z; CVaultMgr::GetUserVaultManager(uchar,CUserVaultMgr * *,uchar * const,_LUID *,ulong *,void * *)
0x180026cb2  mov     ebx, eax
0x180026cb4  mov     [rsp+140h+var_100], eax
0x180026cb8  test    eax, eax
0x180026cba  jz      loc_180026D7B
0x180026cc0  mov     r10, cs:WPP_GLOBAL_Control
0x180026cc7  cmp     r10, r13
0x180026cca  jz      short loc_180026D19
0x180026ccc  test    byte ptr [r10+1Ch], 2
0x180026cd1  jz      short loc_180026CF6
0x180026cd3  mov     edx, 70h ; 'p'
0x180026cd8  mov     r9d, eax
0x180026cdb  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180026ce2  mov     rcx, [r10+10h]
0x180026ce6  call    WPP_SF_d
0x180026ceb  mov     ebx, [rsp+140h+var_100]
0x180026cef  mov     r10, cs:WPP_GLOBAL_Control
0x180026cf6  cmp     r10, r13
0x180026cf9  jz      short loc_180026D19
0x180026cfb  test    byte ptr [r10+1Ch], 8
0x180026d00  jz      short loc_180026D19
0x180026d02  mov     rax, [rbp+40h+var_50]
0x180026d06  mov     ecx, [rax]
0x180026d08  mov     dword ptr [rsp+140h+var_120], ecx
0x180026d0c  lea     r9, [rbp+40h+var_90]
0x180026d10  mov     rcx, [r10+10h]
0x180026d14  call    WPP_SF_sD
0x180026d19  lea     rcx, [rsp+140h+var_F8]; this
0x180026d1e  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180026d23  nop
0x180026d24  mov     rcx, rdi; hMem
0x180026d27  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180026d2c  nop
0x180026d2d  mov     rcx, [rsp+140h+hMem]; hMem
0x180026d32  test    rcx, rcx
0x180026d35  jz      short loc_180026D74
0x180026d37  mov     eax, [rsp+140h+var_D0]
0x180026d3b  test    eax, eax
0x180026d3d  jz      short loc_180026D5D
0x180026d3f  test    rcx, rcx
0x180026d42  jz      short loc_180026D5D
0x180026d44  mov     edx, eax
0x180026d46  test    eax, eax
0x180026d48  jz      short loc_180026D5D
0x180026d4a  mov     rax, rcx
0x180026d4d  nop     dword ptr [rax]
0x180026d50  mov     byte ptr [rax], 0
0x180026d53  lea     rax, [rax+1]
0x180026d57  sub     rdx, 1
0x180026d5b  jnz     short loc_180026D50
0x180026d5d  mov     rax, [rsp+140h+var_E0]
0x180026d62  test    rax, rax
0x180026d65  jz      short loc_180026D6E
0x180026d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d6c  jmp     short loc_180026D74
0x180026d6e  call    ?VaultFreeInternal@@YAXPEAE@Z; VaultFreeInternal(uchar *)
0x180026d73  nop
0x180026d74  mov     eax, ebx
0x180026d76  jmp     loc_180027309
0x180026d7b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026d82  cmp     rcx, r13
0x180026d85  jz      short loc_180026DAC
0x180026d87  test    byte ptr [rcx+1Ch], 8
0x180026d8b  jz      short loc_180026DAC
0x180026d8d  mov     edx, 71h ; 'q'
0x180026d92  mov     eax, [rsi]
0x180026d94  mov     dword ptr [rsp+140h+var_120], eax
0x180026d98  mov     r9d, [rdi+50h]
0x180026d9c  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180026da3  mov     rcx, [rcx+10h]
0x180026da7  call    WPP_SF_dd
0x180026dac  lea     r8, [rbp+40h+var_B8]; struct CUserVault **
0x180026db0  mov     rdx, r14; struct _GUID *
0x180026db3  mov     rbx, [rsp+140h+hMem]
0x180026db8  mov     rcx, rbx; this
0x180026dbb  call    ?GetVault@CUserVaultMgr@@QEAAKPEBU_GUID@@PEAPEAVCUserVault@@@Z; CUserVaultMgr::GetVault(_GUID const *,CUserVault * *)
0x180026dc0  mov     esi, eax
0x180026dc2  mov     [rsp+140h+var_100], eax
0x180026dc6  test    eax, eax
0x180026dc8  jz      loc_180026F5E
0x180026dce  mov     r10, cs:WPP_GLOBAL_Control
0x180026dd5  cmp     r10, r13
0x180026dd8  jz      short loc_180026E27
0x180026dda  test    byte ptr [r10+1Ch], 2
0x180026ddf  jz      short loc_180026E04
0x180026de1  mov     edx, 72h ; 'r'
0x180026de6  mov     r9d, eax
0x180026de9  lea     r8, WPP_e7da9ea8097432d4a0cb57857dcd9c1c_Traceguids
0x180026df0  mov     rcx, [r10+10h]
0x180026df4  call    WPP_SF_d
0x180026df9  mov     esi, [rsp+140h+var_100]
0x180026dfd  mov     r10, cs:WPP_GLOBAL_Control
0x180026e04  cmp     r10, r13
0x180026e07  jz      short loc_180026E27
0x180026e09  test    byte ptr [r10+1Ch], 8
0x180026e0e  jz      short loc_180026E27
0x180026e10  mov     rax, [rbp+40h+var_50]
0x180026e14  mov     ecx, [rax]
0x180026e16  mov     dword ptr [rsp+140h+var_120], ecx
0x180026e1a  lea     r9, [rbp+40h+var_90]
0x180026e1e  mov     rcx, [r10+10h]
0x180026e22  call    WPP_SF_sD
0x180026e27  lea     rcx, [rsp+140h+var_F8]; this
0x180026e2c  call    ??1CVaultRpcImpersonate@@QEAA@XZ; CVaultRpcImpersonate::~CVaultRpcImpersonate(void)
0x180026e31  nop
0x180026e32  test    rdi, rdi
0x180026e35  jz      short loc_180026E67
0x180026e37  mov     rcx, rdi; hMem
0x180026e3a  call    cs:__imp_LocalSize
0x180026e40  test    rax, rax
0x180026e43  jz      short loc_180026E5D
0x180026e45  mov     rcx, rdi
0x180026e48  nop     dword ptr [rax+rax+00000000h]
0x180026e50  mov     byte ptr [rcx], 0
0x180026e53  lea     rcx, [rcx+1]
0x180026e57  sub     rax, 1
0x180026e5b  jnz     short loc_180026E50
0x180026e5d  mov     rcx, rdi; hMem
0x180026e60  call    cs:__imp_LocalFree
0x180026e66  nop
0x180026e67  test    rbx, rbx
0x180026e6a  jz      short loc_180026ED7
0x180026e6c  mov     eax, [rsp+140h+var_D0]
0x180026e70  test    eax, eax
0x180026e72  jz      short loc_180026E8F
0x180026e74  test    rbx, rbx
0x180026e77  jz      short loc_180026E8F
0x180026e79  mov     ecx, eax
0x180026e7b  test    eax, eax
0x180026e7d  jz      short loc_180026E8F
0x180026e7f  mov     rax, rbx
0x180026e82  mov     byte ptr [rax], 0
0x180026e85  lea     rax, [rax+1]
0x180026e89  sub     rcx, 1
0x180026e8d  jnz     short loc_180026E82
0x180026e8f  mov     rax, [rsp+140h+var_E0]
0x180026e94  test    rax, rax
0x180026e97  jz      short loc_180026EA3
0x180026e99  mov     rcx, rbx
0x180026e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ea1  jmp     short loc_180026ED7
0x180026ea3  test    rbx, rbx
0x180026ea6  jz      short loc_180026ED7
0x180026ea8  mov     rcx, rbx; hMem
0x180026eab  call    cs:__imp_LocalSize
0x180026eb1  test    rax, rax
0x180026eb4  jz      short loc_180026ECD
0x180026eb6  mov     rcx, rbx
0x180026eb9  nop     dword ptr [rax+00000000h]
0x180026ec0  mov     byte ptr [rcx], 0
0x180026ec3  lea     rcx, [rcx+1]
0x180026ec7  sub     rax, 1
0x180026ecb  jnz     short loc_180026EC0
0x180026ecd  mov     rcx, rbx; hMem
0x180026ed0  call    cs:__imp_LocalFree
0x180026ed6  nop
0x180026ed7  mov     rbx, [rbp+40h+var_B8]
0x180026edb  test    rbx, rbx
0x180026ede  jz      short loc_180026F57
0x180026ee0  mov     eax, [rbp+40h+var_B0]
0x180026ee3  test    eax, eax
0x180026ee5  jz      short loc_180026F0D
0x180026ee7  test    rbx, rbx
0x180026eea  jz      short loc_180026F0D
  ... truncated ...
```
