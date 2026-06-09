# CFSTransfer::_SameVolumeMoveOrRename(ulong,bool,IShellItem * *)

- ea: `0x18015a37c`
- end: `0x18015a92e`
- name: `?_SameVolumeMoveOrRename@CFSTransfer@@AEAAJK_NPEAPEAUIShellItem@@@Z`
- size: `1458`
- prototype: `__int64 __fastcall(CFSTransfer *__hidden this, unsigned int, bool, struct IShellItem **)`
- caller_count: `1`
- callee_count: `25`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180158c90`

## callees

- `0x18004e06c`
- `0x1800551d0`
- `0x1800693a0`
- `0x1800f8f68`
- `0x1800ff160`
- `0x180114978`
- `0x1801166ac`
- `0x18012ced0`
- `0x18015a37c`
- `0x18015ae38`
- `0x18015b910`
- `0x18015b964`
- `0x18016409c`
- `0x1801720f0`
- `0x180258160`
- `0x1802bc6ec`
- `0x18031aebc`
- `0x1803b1f60`
- `0x1803b1f84`
- `0x1805c4088`
- `0x1805c42e4`
- `0x1805c4a3c`
- `0x1805e599c`
- `0x1805f3f70`
- `0x18067d010`

## import_xrefs

- `ntdll!RtlGetLastNtStatus` at `0x18015a658`
- `ntdll!RtlGetLastNtStatus` at `0x18015a658`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18015a8be`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpICW` at `0x18015a8be`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015a587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015a91d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015a587`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015a91d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18015a693`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18015a6f3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18015a693`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18015a6f3`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18015a643`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x18015a643`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18015a464`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsSameRootW` at `0x18015a464`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18015a3f6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRootW` at `0x18015a3f6`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18015a55d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathMatchSpecW` at `0x18015a55d`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18066cc64`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18066cc64`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18015a797`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x18015a797`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18015a760`
- `api-ms-win-security-provider-l1-1-0!GetNamedSecurityInfoW` at `0x18015a760`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHEncryptFile` at `0x18066cd08`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_SHEncryptFile` at `0x18066cd08`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_EncryptDirectory` at `0x18015a722`
- `ext-ms-win-shell-exports-internal-l1-1-0!SHELL32_EncryptDirectory` at `0x18015a722`

## pseudocode

```c
__int64 __fastcall CFSTransfer::_SameVolumeMoveOrRename(
        CFSTransfer *this,
        unsigned int a2,
        char a3,
        struct IShellItem **a4)
{
  __int64 v5; // rcx
  char v7; // si
  __int64 result; // rax
  int v9; // eax
  const WCHAR *v10; // rdx
  const WCHAR *v11; // rcx
  unsigned int v12; // r15d
  signed int v13; // r14d
  bool v14; // r13
  __int64 v15; // rcx
  int ItemDest; // esi
  int v17; // eax
  __int64 v18; // r8
  unsigned int v19; // ebx
  BOOL v20; // eax
  int v21; // eax
  NTSTATUS LastNtStatus; // ebx
  __int64 v23; // r8
  unsigned int v24; // r9d
  DWORD FileAttributesW; // eax
  DWORD v26; // eax
  __int64 v27; // rcx
  signed int NamedSecurityInfoW; // eax
  void *v29; // rcx
  int v30; // ebx
  int Error; // ebx
  char v32; // [rsp+40h] [rbp-39h]
  int v34; // [rsp+48h] [rbp-31h]
  int v35; // [rsp+4Ch] [rbp-2Dh]
  PACL pAcl; // [rsp+58h] [rbp-21h] BYREF
  HLOCAL hMem; // [rsp+60h] [rbp-19h] BYREF
  WORD pControl[2]; // [rsp+68h] [rbp-11h] BYREF
  DWORD dwRevision; // [rsp+6Ch] [rbp-Dh] BYREF
  __int64 v41; // [rsp+70h] [rbp-9h] BYREF
  int v42; // [rsp+78h] [rbp-1h]
  void *v43; // [rsp+80h] [rbp+7h]
  _BYTE v44[16]; // [rsp+88h] [rbp+Fh] BYREF

  *a4 = 0;
  v5 = *((_QWORD *)this + 9);
  v7 = a2;
  if ( v5 )
  {
    result = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v5 + 24LL))(
               v5,
               0,
               0,
               0,
               0,
               0,
               0);
    if ( (int)result < 0 )
      return result;
  }
  if ( PathIsRootW(*((LPCWSTR *)this + 27)) )
    return 2150039583LL;
  if ( !*((_QWORD *)this + 33) )
    return 2147942417LL;
  v35 = v7 & 4;
  if ( (v7 & 4) == 0 && !SHRestricted(REST_NOENCRYPTONMOVE) )
  {
    v9 = *((_DWORD *)this + 56);
    if ( (v9 & 4) == 0 && (v9 & 0x4000) == 0 )
    {
      FileAttributesW = GetFileAttributesW(*((LPCWSTR *)this + 33));
      if ( FileAttributesW != -1 && (FileAttributesW & 0x4000) != 0 )
      {
        v41 = *((_QWORD *)this + 33);
        v43 = 0;
        v42 = 0;
        if ( CEfsUtil::IsDpapiNgProtectedFile((CEfsUtil *)&v41) )
        {
          operator delete(v43, (const struct std::nothrow_t *)1);
          return 2147942417LL;
        }
        operator delete(v43, (const struct std::nothrow_t *)1);
      }
    }
  }
  v10 = (const WCHAR *)*((_QWORD *)this + 33);
  v11 = (const WCHAR *)*((_QWORD *)this + 27);
  pAcl = 0;
  hMem = 0;
  pControl[0] = 0;
  if ( !PathIsSameRootW(v11, v10) )
    return 2147942417LL;
  v12 = 2;
  v34 = 0;
  v32 = 0;
  if ( *((_DWORD *)this + 42) != 1 )
  {
    v13 = -2147467259;
    goto LABEL_12;
  }
  if ( !CFSTransfer::_IsMoveSecurityAttributesEnabled() && !a3 )
  {
    v32 = 1;
    goto LABEL_79;
  }
  if ( (v7 & 8) != 0 )
  {
LABEL_79:
    v13 = CTLocalAllocPolicy::Alloc(v29, 0x40u, 8u, (void **)&pAcl);
    if ( v13 >= 0 )
    {
      v34 = 1;
      v13 = !InitializeAcl(pAcl, 8u, 2u) ? 0x80004005 : 0;
    }
    goto LABEL_12;
  }
  NamedSecurityInfoW = GetNamedSecurityInfoW(*((LPCWSTR *)this + 27), SE_FILE_OBJECT, 4u, 0, 0, &pAcl, 0, &hMem);
  v13 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v13 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v13 >= 0 )
  {
    dwRevision = 0;
    GetSecurityDescriptorControl(hMem, pControl, &dwRevision);
  }
LABEL_12:
  AvoidCurrentDirectory(*((LPCWCH *)this + 27));
  v14 = IsFolderNotStreamItem(*((struct IShellItem **)this + 26));
  do
  {
    v15 = *((_QWORD *)this + 9);
    if ( v15 )
    {
      ItemDest = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))(*(_QWORD *)v15 + 24LL))(
                   v15,
                   0,
                   0,
                   0,
                   0,
                   0,
                   0);
      if ( ItemDest < 0 )
        break;
    }
    ItemDest = *((_DWORD *)this + 205);
    if ( ItemDest >= 0 )
    {
      if ( *((_DWORD *)this + 42) != 1
        || (*((_DWORD *)this + 56) & 0x4000) != 0
        || (ItemDest = CFSTransfer::_CheckEncryptionDest(this), ItemDest >= 0) )
      {
        v19 = !IsFolderNotStreamItem(*((struct IShellItem **)this + 26)) && (a2 & 2) != 0;
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x400000) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_Shell_Core_Provider_Context,
            Shell32_CopyEngine_CallMoveFile_Start,
            v18,
            1,
            v44);
        if ( *((_DWORD *)this + 46) || CFSTransfer::IsFileAvailableOnlineOnly(this) )
        {
          if ( CFSTransfer::IsFileAvailableOnlineOnly(this) || *((_DWORD *)this + 46) )
            v19 |= 2u;
          v21 = MoveFileWithUsnSourceInfo(
                  *((const unsigned __int16 **)this + 27),
                  *((const unsigned __int16 **)this + 34),
                  v19,
                  *((_DWORD *)this + 46));
        }
        else
        {
          v20 = MoveFileExW(*((LPCWSTR *)this + 27), *((LPCWSTR *)this + 34), v19);
          v21 = ResultFromWin32Bool(v20);
        }
        ItemDest = v21;
        LastNtStatus = RtlGetLastNtStatus();
        if ( (Microsoft_Windows_Shell_CoreEnableBits & 0x400000) != 0 )
          McGenEventWrite_EventWriteTransfer(
            &Microsoft_Windows_Shell_Core_Provider_Context,
            Shell32_CopyEngine_CallMoveFile_Stop,
            v23,
            1,
            &v41);
        if ( ItemDest < 0 )
        {
          if ( LastNtStatus == -1073741638 && ItemDest == -2147024891 )
          {
            ItemDest = -2147024879;
            break;
          }
          if ( v14 && ItemDest == -2147024891 && (unsigned int)CFSTransfer::_HasMoveAccess(this) )
          {
            ItemDest = -2147024864;
            break;
          }
          v30 = ItemDest;
          ItemDest = CFSTransfer::_HandleBaseApiErrors(this, ItemDest, a2, v24, 0);
          if ( ItemDest == 2555907 )
          {
            ItemDest = v30;
            break;
          }
        }
      }
    }
  }
  while ( ItemDest == 2555908 );
  if ( (unsigned int)ShouldProceedWithOperation(ItemDest) )
  {
    if ( IsDesktopPresent() && !v35 && !SHRestricted(REST_NOENCRYPTONMOVE) )
    {
      v17 = *((_DWORD *)this + 56);
      if ( (v17 & 4) == 0 && (v17 & 0x4000) == 0 )
      {
        v26 = GetFileAttributesW(*((LPCWSTR *)this + 33));
        if ( v26 != -1 && (v26 & 0x4000) != 0 )
        {
          v27 = *((_QWORD *)this + 34);
          if ( v14 )
          {
            SHELL32_EncryptDirectory(v27);
          }
          else if ( !(unsigned int)SHELL32_SHEncryptFile(v27, 1, 0, *((_QWORD *)this + 107)) )
          {
            Error = ResultFromKnownLastError();
            SHMoveFile(*((LPCVOID *)this + 34), *((LPCVOID *)this + 27), v14 ? 0x20000 : 1);
            ItemDest = -2147018896;
            if ( Error == -2147023673 )
              ItemDest = -2144927744;
          }
        }
      }
    }
    if ( v13 >= 0 && pAcl )
    {
      if ( !v32 )
        v12 = (a2 & 8) == 0;
      CFSTransfer::_ResetInheritedACL(this, pAcl, pControl[0], v12);
    }
    if ( PathMatchSpecW(*((LPCWSTR *)this + 34), L"*.ini;*.url") )
    {
      SHFlushPrivateProfile(*((_QWORD *)this + 34));
      if ( !StrCmpICW((LPCWSTR)this + 148, L"desktop.ini") )
        SHChangeNotify(0x2000, 5u, *((LPCVOID *)this + 33), 0);
    }
    if ( ItemDest != -2144927744 )
    {
      ItemDest = CFSTransfer::_GetItemDest(this, (const unsigned __int16 *)this + 148, *((_DWORD *)this + 56), a4);
      if ( ItemDest >= 0 )
        ItemDest = 2555912;
    }
  }
  if ( v34 )
    LocalFree(pAcl);
  LocalFree(hMem);
  return (unsigned int)ItemDest;
}

```

## disassembly

```asm
0x18015a37c  mov     [rsp-8+arg_10], rbx
0x18015a381  push    rbp
0x18015a382  push    rsi
0x18015a383  push    rdi
0x18015a384  push    r12
0x18015a386  push    r13
0x18015a388  push    r14
0x18015a38a  push    r15
0x18015a38c  lea     rbp, [rsp-27h]
0x18015a391  sub     rsp, 0A0h
0x18015a398  mov     rax, cs:__security_cookie
0x18015a39f  xor     rax, rsp
0x18015a3a2  mov     [rbp+57h+var_38], rax
0x18015a3a6  xor     r12d, r12d
0x18015a3a9  mov     [rbp+57h+var_80], r9
0x18015a3ad  mov     [r9], r12
0x18015a3b0  mov     rdi, rcx
0x18015a3b3  mov     rcx, [rcx+48h]
0x18015a3b7  mov     bl, r8b
0x18015a3ba  mov     [rbp+57h+var_8C], edx
0x18015a3bd  mov     esi, edx
0x18015a3bf  test    rcx, rcx
0x18015a3c2  jz      short loc_18015A3EF
0x18015a3c4  mov     rax, [rcx]
0x18015a3c7  xor     r9d, r9d
0x18015a3ca  mov     dword ptr [rsp+0D0h+ppSacl], r12d
0x18015a3cf  xor     r8d, r8d
0x18015a3d2  mov     dword ptr [rsp+0D0h+ppDacl], r12d
0x18015a3d7  xor     edx, edx
0x18015a3d9  mov     dword ptr [rsp+0D0h+ppsidGroup], r12d
0x18015a3de  mov     rax, [rax+18h]
0x18015a3e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a3e7  test    eax, eax
0x18015a3e9  js      loc_18015A595
0x18015a3ef  mov     rcx, [rdi+0D8h]; pszPath
0x18015a3f6  call    cs:__imp_PathIsRootW
0x18015a3fd  nop     dword ptr [rax+rax+00h]
0x18015a402  test    eax, eax
0x18015a404  jnz     loc_18015A7A8
0x18015a40a  cmp     [rdi+108h], r12
0x18015a411  jz      loc_18015A6E2
0x18015a417  mov     eax, esi
0x18015a419  mov     r13d, 1
0x18015a41f  and     eax, 4
0x18015a422  mov     [rbp+57h+var_84], eax
0x18015a425  jnz     short loc_18015A449
0x18015a427  mov     ecx, 40000045h; rest
0x18015a42c  call    SHRestricted
0x18015a431  test    eax, eax
0x18015a433  jnz     short loc_18015A449
0x18015a435  mov     eax, [rdi+0E0h]
0x18015a43b  test    al, 4
0x18015a43d  jnz     short loc_18015A449
0x18015a43f  bt      eax, 0Eh
0x18015a443  jnb     loc_18015A68C
0x18015a449  mov     rdx, [rdi+108h]; pszPath2
0x18015a450  mov     rcx, [rdi+0D8h]; pszPath1
0x18015a457  mov     [rbp+57h+pAcl], r12
0x18015a45b  mov     [rbp+57h+hMem], r12
0x18015a45f  mov     [rbp+57h+pControl], r12w
0x18015a464  call    cs:__imp_PathIsSameRootW
0x18015a46b  nop     dword ptr [rax+rax+00h]
0x18015a470  test    eax, eax
0x18015a472  jz      loc_18015A6E2
0x18015a478  mov     r15d, 2
0x18015a47e  mov     [rbp+57h+var_88], r12d
0x18015a482  mov     [rbp+57h+var_90], r12b
0x18015a486  cmp     [rdi+0A8h], r13d
0x18015a48d  jz      loc_18015A7B2
0x18015a493  mov     r14d, 80004005h
0x18015a499  mov     rcx, [rdi+0D8h]; lpString2
0x18015a4a0  call    ?AvoidCurrentDirectory@@YAXPEBG@Z; AvoidCurrentDirectory(ushort const *)
0x18015a4a5  mov     rcx, [rdi+0D0h]; struct IShellItem *
0x18015a4ac  call    ?IsFolderNotStreamItem@@YA_NPEAUIShellItem@@@Z; IsFolderNotStreamItem(IShellItem *)
0x18015a4b1  mov     cl, al
0x18015a4b3  mov     r13b, al
0x18015a4b6  neg     cl
0x18015a4b8  sbb     r12d, r12d
0x18015a4bb  and     r12d, 1FFFFh
0x18015a4c2  mov     rcx, [rdi+48h]
0x18015a4c6  test    rcx, rcx
0x18015a4c9  jz      loc_18015A5BD
0x18015a4cf  mov     rax, [rcx]
0x18015a4d2  xor     r9d, r9d
0x18015a4d5  mov     dword ptr [rsp+0D0h+ppSacl], 0
0x18015a4dd  xor     r8d, r8d
0x18015a4e0  mov     dword ptr [rsp+0D0h+ppDacl], 0
0x18015a4e8  xor     edx, edx
0x18015a4ea  mov     dword ptr [rsp+0D0h+ppsidGroup], 0
0x18015a4f2  mov     rax, [rax+18h]
0x18015a4f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18015a4fb  mov     esi, eax
0x18015a4fd  test    eax, eax
0x18015a4ff  jns     loc_18015A5BD
0x18015a505  mov     ecx, esi; int
0x18015a507  call    ?ShouldProceedWithOperation@@YAHJ@Z; ShouldProceedWithOperation(long)
0x18015a50c  test    eax, eax
0x18015a50e  jz      short loc_18015A579
0x18015a510  call    ?IsDesktopPresent@@YA_NXZ; IsDesktopPresent(void)
0x18015a515  mov     ebx, 80270000h
0x18015a51a  test    al, al
0x18015a51c  jz      short loc_18015A546
0x18015a51e  cmp     [rbp+57h+var_84], 0
0x18015a522  jnz     short loc_18015A546
0x18015a524  mov     ecx, 40000045h; rest
0x18015a529  call    SHRestricted
0x18015a52e  test    eax, eax
0x18015a530  jnz     short loc_18015A546
0x18015a532  mov     eax, [rdi+0E0h]
0x18015a538  test    al, 4
0x18015a53a  jnz     short loc_18015A546
0x18015a53c  bt      eax, 0Eh
0x18015a540  jnb     loc_18015A6EC
0x18015a546  test    r14d, r14d
0x18015a549  jns     loc_18015A876
0x18015a54f  mov     rcx, [rdi+110h]; pszFile
0x18015a556  lea     rdx, pszSpec; "*.ini;*.url"
0x18015a55d  call    cs:__imp_PathMatchSpecW
0x18015a564  nop     dword ptr [rax+rax+00h]
0x18015a569  test    eax, eax
0x18015a56b  jnz     loc_18015A8A4
0x18015a571  cmp     esi, ebx
0x18015a573  jnz     loc_18015A8EE
0x18015a579  cmp     [rbp+57h+var_88], 0
0x18015a57d  jnz     loc_18015A919
0x18015a583  mov     rcx, [rbp+57h+hMem]; hMem
0x18015a587  call    cs:__imp_LocalFree
0x18015a58e  nop     dword ptr [rax+rax+00h]
0x18015a593  mov     eax, esi
0x18015a595  mov     rcx, [rbp+57h+var_38]
0x18015a599  xor     rcx, rsp; StackCookie
0x18015a59c  call    __security_check_cookie
0x18015a5a1  mov     rbx, [rsp+0D0h+arg_10]
0x18015a5a9  add     rsp, 0A0h
0x18015a5b0  pop     r15
0x18015a5b2  pop     r14
0x18015a5b4  pop     r13
0x18015a5b6  pop     r12
0x18015a5b8  pop     rdi
0x18015a5b9  pop     rsi
0x18015a5ba  pop     rbp
0x18015a5bb  retn
0x18015a5bd  mov     esi, [rdi+334h]
0x18015a5c3  test    esi, esi
0x18015a5c5  js      loc_18015A67B
0x18015a5cb  cmp     dword ptr [rdi+0A8h], 1
0x18015a5d2  jnz     short loc_18015A5F2
0x18015a5d4  test    dword ptr [rdi+0E0h], 4000h
0x18015a5de  jnz     short loc_18015A5F2
0x18015a5e0  mov     rcx, rdi; this
0x18015a5e3  call    ?_CheckEncryptionDest@CFSTransfer@@AEAAJXZ; CFSTransfer::_CheckEncryptionDest(void)
0x18015a5e8  mov     esi, eax
0x18015a5ea  test    eax, eax
0x18015a5ec  js      loc_18015A67B
0x18015a5f2  mov     rcx, [rdi+0D0h]; struct IShellItem *
0x18015a5f9  call    ?IsFolderNotStreamItem@@YA_NPEAUIShellItem@@@Z; IsFolderNotStreamItem(IShellItem *)
0x18015a5fe  test    al, al
0x18015a600  jz      loc_18015A7D0
0x18015a606  xor     ebx, ebx
0x18015a608  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 40h
0x18015a60f  jnz     loc_18015A7E4
0x18015a615  cmp     dword ptr [rdi+0B8h], 0
0x18015a61c  jnz     loc_18015A80B
0x18015a622  mov     rcx, rdi; this
0x18015a625  call    ?IsFileAvailableOnlineOnly@CFSTransfer@@AEAA_NXZ; CFSTransfer::IsFileAvailableOnlineOnly(void)
0x18015a62a  test    al, al
0x18015a62c  jnz     loc_18015A80B
0x18015a632  mov     rdx, [rdi+110h]; lpNewFileName
0x18015a639  mov     r8d, ebx; dwFlags
0x18015a63c  mov     rcx, [rdi+0D8h]; lpExistingFileName
0x18015a643  call    cs:__imp_MoveFileExW
0x18015a64a  nop     dword ptr [rax+rax+00h]
0x18015a64f  mov     ecx, eax; int
0x18015a651  call    ?ResultFromWin32Bool@@YAJH@Z; ResultFromWin32Bool(int)
0x18015a656  mov     esi, eax
0x18015a658  call    cs:__imp_RtlGetLastNtStatus
0x18015a65f  nop     dword ptr [rax+rax+00h]
0x18015a664  test    byte ptr cs:Microsoft_Windows_Shell_CoreEnableBits+2, 40h
0x18015a66b  mov     ebx, eax
0x18015a66d  jnz     loc_18015A82D
0x18015a673  test    esi, esi
0x18015a675  js      loc_18015A854
0x18015a67b  cmp     esi, 270004h
0x18015a681  jnz     loc_18015A505
0x18015a687  jmp     loc_18015A4C2
0x18015a68c  mov     rcx, [rdi+108h]; lpFileName
0x18015a693  call    cs:__imp_GetFileAttributesW
0x18015a69a  nop     dword ptr [rax+rax+00h]
0x18015a69f  cmp     eax, 0FFFFFFFFh
0x18015a6a2  jz      loc_18015A449
0x18015a6a8  bt      eax, 0Eh
0x18015a6ac  jnb     loc_18015A449
0x18015a6b2  mov     rax, [rdi+108h]
0x18015a6b9  lea     rcx, [rbp+57h+var_60]; this
0x18015a6bd  mov     [rbp+57h+var_60], rax
0x18015a6c1  mov     [rbp+57h+var_50], r12
0x18015a6c5  mov     [rbp+57h+var_58], r12d
0x18015a6c9  call    ?IsDpapiNgProtectedFile@CEfsUtil@@QEAA_NXZ; CEfsUtil::IsDpapiNgProtectedFile(void)
0x18015a6ce  mov     rcx, [rbp+57h+var_50]; void *
0x18015a6d2  mov     rdx, r13; struct std::nothrow_t *
0x18015a6d5  test    al, al
0x18015a6d7  jz      loc_18066CC22
0x18015a6dd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18015a6e2  mov     eax, 80070011h
0x18015a6e7  jmp     loc_18015A595
0x18015a6ec  mov     rcx, [rdi+108h]; lpFileName
0x18015a6f3  call    cs:__imp_GetFileAttributesW
0x18015a6fa  nop     dword ptr [rax+rax+00h]
0x18015a6ff  cmp     eax, 0FFFFFFFFh
0x18015a702  jz      loc_18015A546
0x18015a708  bt      eax, 0Eh
0x18015a70c  jnb     loc_18015A546
0x18015a712  mov     rcx, [rdi+110h]
0x18015a719  test    r13b, r13b
0x18015a71c  jz      loc_18066CCFA
0x18015a722  call    cs:__imp_SHELL32_EncryptDirectory
0x18015a729  nop     dword ptr [rax+rax+00h]
0x18015a72e  jmp     loc_18015A546
0x18015a733  mov     rcx, [rdi+0D8h]; pObjectName
0x18015a73a  lea     rax, [rbp+57h+hMem]
0x18015a73e  mov     [rsp+0D0h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x18015a743  xor     r9d, r9d; ppsidOwner
0x18015a746  lea     rax, [rbp+57h+pAcl]
0x18015a74a  mov     [rsp+0D0h+ppSacl], r12; ppSacl
0x18015a74f  mov     [rsp+0D0h+ppDacl], rax; ppDacl
0x18015a754  mov     edx, r13d; ObjectType
0x18015a757  mov     [rsp+0D0h+ppsidGroup], r12; ppsidGroup
0x18015a75c  lea     r8d, [r9+4]; SecurityInfo
0x18015a760  call    cs:__imp_GetNamedSecurityInfoW
0x18015a767  nop     dword ptr [rax+rax+00h]
0x18015a76c  mov     r14d, eax
0x18015a76f  test    eax, eax
0x18015a771  jle     short loc_18015A77E
0x18015a773  movzx   r14d, ax
0x18015a777  or      r14d, 80070000h
0x18015a77e  test    r14d, r14d
0x18015a781  js      loc_18015A499
0x18015a787  mov     rcx, [rbp+57h+hMem]; pSecurityDescriptor
0x18015a78b  lea     r8, [rbp+57h+dwRevision]; lpdwRevision
0x18015a78f  lea     rdx, [rbp+57h+pControl]; pControl
0x18015a793  mov     [rbp+57h+dwRevision], r12d
0x18015a797  call    cs:__imp_GetSecurityDescriptorControl
0x18015a79e  nop     dword ptr [rax+rax+00h]
0x18015a7a3  jmp     loc_18015A499
0x18015a7a8  mov     eax, 8027001Fh
0x18015a7ad  jmp     loc_18015A595
0x18015a7b2  call    ?_IsMoveSecurityAttributesEnabled@CFSTransfer@@CA_NXZ; CFSTransfer::_IsMoveSecurityAttributesEnabled(void)
0x18015a7b7  test    al, al
0x18015a7b9  jnz     loc_18066CC2D
0x18015a7bf  test    bl, bl
0x18015a7c1  jnz     loc_18066CC2D
0x18015a7c7  mov     [rbp+57h+var_90], r13b
0x18015a7cb  jmp     loc_18066CC37
0x18015a7d0  test    byte ptr [rbp+57h+var_8C], r15b
0x18015a7d4  jz      loc_18015A606
0x18015a7da  mov     ebx, 1
0x18015a7df  jmp     loc_18015A608
0x18015a7e4  lea     rax, [rbp+57h+var_48]
0x18015a7e8  mov     r9d, 1
0x18015a7ee  lea     rdx, Shell32_CopyEngine_CallMoveFile_Start
0x18015a7f5  mov     [rsp+0D0h+ppsidGroup], rax
0x18015a7fa  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18015a801  call    McGenEventWrite_EventWriteTransfer
0x18015a806  jmp     loc_18015A615
0x18015a80b  mov     rcx, rdi; this
0x18015a80e  call    ?IsFileAvailableOnlineOnly@CFSTransfer@@AEAA_NXZ; CFSTransfer::IsFileAvailableOnlineOnly(void)
0x18015a813  test    al, al
0x18015a815  jnz     loc_18066CC84
0x18015a81b  cmp     dword ptr [rdi+0B8h], 0
0x18015a822  jnz     loc_18066CC84
0x18015a828  jmp     loc_18066CC87
0x18015a82d  lea     rax, [rbp+57h+var_60]
0x18015a831  mov     r9d, 1
0x18015a837  lea     rdx, Shell32_CopyEngine_CallMoveFile_Stop
0x18015a83e  mov     [rsp+0D0h+ppsidGroup], rax
0x18015a843  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x18015a84a  call    McGenEventWrite_EventWriteTransfer
0x18015a84f  jmp     loc_18015A673
0x18015a854  cmp     ebx, 0C00000BAh
0x18015a85a  jnz     loc_18066CCAA
0x18015a860  cmp     esi, 80070005h
0x18015a866  jnz     loc_18066CCAA
0x18015a86c  mov     esi, 80070011h
0x18015a871  jmp     loc_18015A505
0x18015a876  mov     rdx, [rbp+57h+pAcl]; pDacl
0x18015a87a  test    rdx, rdx
0x18015a87d  jz      loc_18015A54F
0x18015a883  cmp     [rbp+57h+var_90], 0
0x18015a887  jnz     loc_18066CD53
0x18015a88d  test    byte ptr [rbp+57h+var_8C], 8
0x18015a891  mov     r15d, 1
0x18015a897  lea     eax, [r15-1]
0x18015a89b  cmovnz  r15d, eax
0x18015a89f  jmp     loc_18066CD53
0x18015a8a4  mov     rcx, [rdi+110h]
0x18015a8ab  call    SHFlushPrivateProfile
0x18015a8b0  lea     rcx, [rdi+128h]; pszStr1
0x18015a8b7  lea     rdx, aDesktopIni_0; "desktop.ini"
0x18015a8be  call    cs:__imp_StrCmpICW
0x18015a8c5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
