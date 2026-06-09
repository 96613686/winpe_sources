# DavrCreateConnection

- ea: `0x180006d20`
- end: `0x180007b4a`
- name: `DavrCreateConnection`
- size: `3626`
- prototype: `__int64 __fastcall(void *, __int64, void *, DWORD, void *, int, STRSAFE_LPCWSTR pszSrc, int, int, __int64, __int64, int, unsigned __int8, unsigned __int8, int, void *)`
- caller_count: `0`
- callee_count: `26`
- tags: `reparse_path, authz_impersonation, loader_planting`

## callees

- `0x18000235c`
- `0x1800028c4`
- `0x18000298c`
- `0x180003458`
- `0x18000370c`
- `0x180003a9c`
- `0x180005568`
- `0x1800056f4`
- `0x180005844`
- `0x18000591c`
- `0x180005de4`
- `0x180006618`
- `0x180006d20`
- `0x18000b060`
- `0x18000b35c`
- `0x18000b6b4`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b89c`
- `0x18000b93c`
- `0x18000ba14`
- `0x18000bbec`
- `0x180010028`
- `0x18002cf56`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!wcscspn` at `0x180007108`
- `msvcrt!wcscspn` at `0x1800071a4`
- `msvcrt!wcscspn` at `0x180007108`
- `msvcrt!wcscspn` at `0x1800071a4`
- `ntdll!NtFsControlFile` at `0x18000796d`
- `ntdll!NtFsControlFile` at `0x18000796d`
- `ntdll!NtClose` at `0x1800077c3`
- `ntdll!NtClose` at `0x1800079ac`
- `ntdll!NtClose` at `0x180007a69`
- `ntdll!NtClose` at `0x1800077c3`
- `ntdll!NtClose` at `0x1800079ac`
- `ntdll!NtClose` at `0x180007a69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800070a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800073f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007493`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800075d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800077ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a55`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007a55`
- `KERNEL32!LocalFree` at `0x180007a77`
- `KERNEL32!LocalFree` at `0x180007a86`
- `KERNEL32!LocalFree` at `0x180007a98`
- `KERNEL32!LocalFree` at `0x180007aa6`
- `KERNEL32!LocalFree` at `0x180007ad9`
- `KERNEL32!LocalFree` at `0x180007aff`
- `KERNEL32!LocalFree` at `0x180007b0e`
- `KERNEL32!LocalFree` at `0x180007a77`
- `KERNEL32!LocalFree` at `0x180007a86`
- `KERNEL32!LocalFree` at `0x180007a98`
- `KERNEL32!LocalFree` at `0x180007aa6`
- `KERNEL32!LocalFree` at `0x180007ad9`
- `KERNEL32!LocalFree` at `0x180007aff`
- `KERNEL32!LocalFree` at `0x180007b0e`
- `KERNEL32!LocalAlloc` at `0x180007097`
- `KERNEL32!LocalAlloc` at `0x1800073e3`
- `KERNEL32!LocalAlloc` at `0x18000751f`
- `KERNEL32!LocalAlloc` at `0x1800077e1`
- `KERNEL32!LocalAlloc` at `0x180007097`
- `KERNEL32!LocalAlloc` at `0x1800073e3`
- `KERNEL32!LocalAlloc` at `0x18000751f`
- `KERNEL32!LocalAlloc` at `0x1800077e1`
- `CRYPT32!CryptUnprotectMemory` at `0x180007489`
- `CRYPT32!CryptUnprotectMemory` at `0x1800075c8`
- `CRYPT32!CryptUnprotectMemory` at `0x180007489`
- `CRYPT32!CryptUnprotectMemory` at `0x1800075c8`

## pseudocode

```c
__int64 __fastcall DavrCreateConnection(
        void *a1,
        __int64 a2,
        void *a3,
        DWORD a4,
        void *a5,
        int a6,
        STRSAFE_LPCWSTR pszSrc,
        int a8,
        int a9,
        __int64 a10,
        __int64 a11,
        int a12,
        unsigned __int8 a13,
        unsigned __int8 a14,
        int a15,
        void *a16)
{
  HLOCAL v18; // rdi
  char v19; // r14
  void *v20; // r15
  wchar_t *v21; // rsi
  int v22; // eax
  _UNKNOWN **v23; // r8
  _QWORD *v24; // rcx
  __int64 v25; // rcx
  const wchar_t *v26; // r9
  __int64 v27; // rdx
  DWORD LastError; // ebx
  _QWORD *v29; // rcx
  __int64 v30; // rdx
  __int64 v31; // r9
  int *v32; // rcx
  DWORD v33; // eax
  __int64 v34; // r13
  _QWORD *v35; // rcx
  __int64 v36; // rbx
  wchar_t *v37; // rax
  __int64 v38; // r15
  unsigned int v39; // ecx
  __int64 v40; // rsi
  _QWORD *v41; // rcx
  __int64 v42; // rdx
  unsigned int v43; // ebx
  __int64 v44; // rdi
  __int64 v45; // rbx
  wchar_t *v46; // rcx
  DWORD LogonId; // eax
  HANDLE v48; // r12
  void *v49; // rdi
  size_t v50; // rbx
  HLOCAL v51; // rax
  _QWORD *v52; // rcx
  __int64 v53; // rdx
  void *v54; // rdi
  size_t v55; // rbx
  HLOCAL v56; // rax
  _QWORD *v57; // rcx
  __int64 v58; // rdx
  _WORD *v59; // rdi
  __int64 v60; // rax
  const wchar_t *v61; // rdi
  __int64 v62; // r14
  WCHAR *v63; // rax
  HANDLE v64; // r15
  NTSTATUS Status; // eax
  HLOCAL v66; // rcx
  void *v67; // rdx
  __int64 v68; // rcx
  _BYTE *v69; // rax
  HLOCAL v70; // rcx
  __int64 v71; // rdx
  _BYTE *v72; // rax
  HANDLE hObject; // [rsp+90h] [rbp-80h] BYREF
  char v75; // [rsp+98h] [rbp-78h]
  DWORD Size[3]; // [rsp+9Ch] [rbp-74h] BYREF
  int uBytes; // [rsp+A8h] [rbp-68h]
  DWORD uBytes_4; // [rsp+ACh] [rbp-64h] BYREF
  int InputBuffer; // [rsp+B0h] [rbp-60h] BYREF
  wchar_t *String; // [rsp+B8h] [rbp-58h]
  unsigned int v81; // [rsp+C0h] [rbp-50h] BYREF
  HANDLE FileHandle; // [rsp+C8h] [rbp-48h] BYREF
  LPVOID pDataIn; // [rsp+D0h] [rbp-40h]
  HLOCAL v84; // [rsp+D8h] [rbp-38h]
  HLOCAL v85; // [rsp+E0h] [rbp-30h] BYREF
  HANDLE Handle; // [rsp+E8h] [rbp-28h] BYREF
  HLOCAL hMem[2]; // [rsp+F0h] [rbp-20h] BYREF
  struct _LUID DestinationLuid; // [rsp+100h] [rbp-10h] BYREF
  HLOCAL v89; // [rsp+108h] [rbp-8h] BYREF
  __int64 v90; // [rsp+110h] [rbp+0h]
  __int64 v91; // [rsp+118h] [rbp+8h]
  HLOCAL v92; // [rsp+120h] [rbp+10h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+128h] [rbp+18h] BYREF
  void *Src; // [rsp+138h] [rbp+28h]
  void *v95; // [rsp+140h] [rbp+30h]
  int v96; // [rsp+148h] [rbp+38h] BYREF
  __int16 v97; // [rsp+14Ch] [rbp+3Ch]
  _BYTE v98[528]; // [rsp+150h] [rbp+40h] BYREF

  Src = a5;
  uBytes = a6;
  v18 = a3;
  v91 = a10;
  v90 = a11;
  Size[0] = a15;
  IoStatusBlock.Pointer = a1;
  v95 = a16;
  v19 = 0;
  v81 = 0;
  DestinationLuid = 0;
  v20 = 0;
  FileHandle = (HANDLE)-1LL;
  v21 = 0;
  *(_QWORD *)&Size[1] = 0;
  v89 = 0;
  String = 0;
  hObject = (HANDLE)-1LL;
  pDataIn = 0;
  v84 = 0;
  v85 = 0;
  v96 = 0;
  v97 = 0;
  uBytes_4 = a4;
  v92 = a3;
  *(_OWORD *)hMem = 0;
  v22 = DavConvertIDNToPunyCodeUNC(a3, &v85);
  v23 = &WPP_GLOBAL_Control;
  if ( v22 && v85 )
  {
    v24 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v85);
      v24 = WPP_GLOBAL_Control;
      v23 = &WPP_GLOBAL_Control;
    }
    v18 = v85;
    v92 = v85;
  }
  else
  {
    v24 = WPP_GLOBAL_Control;
  }
  if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
  {
    v25 = v24[2];
    LODWORD(v26) = a2;
    if ( !a2 )
      v26 = L"NULL";
    WPP_SF_SS(v25, 25, (unsigned int)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, (_DWORD)v26, (__int64)v18);
    v24 = WPP_GLOBAL_Control;
    v23 = &WPP_GLOBAL_Control;
  }
  v27 = 0;
  hMem[1] = 0;
  LODWORD(hMem[0]) = 0;
  if ( a4 >= 2 )
  {
    LastError = 87;
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
      WPP_SF_(v24[2], 26, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    goto LABEL_185;
  }
  if ( (uBytes & 0xF) != 0 )
  {
    LastError = 87;
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 1) != 0 )
      WPP_SF_d(v24[2], 27, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, (unsigned int)uBytes);
    goto LABEL_185;
  }
  if ( a2 )
  {
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
      WPP_SF_SS(v24[2], 28, (unsigned int)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a2, (__int64)v18);
    LastError = DavCheckLocalName(a2, &v96, v23);
    if ( LastError )
    {
      v29 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_185;
      v30 = 29;
LABEL_29:
      v31 = LastError;
LABEL_30:
      WPP_SF_d(v29[2], v30, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v31);
      goto LABEL_185;
    }
    InputBuffer = 3;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, &v96);
    v32 = &v96;
  }
  else
  {
    v32 = 0;
    InputBuffer = 0;
  }
  Handle = v32;
  v33 = DavCheckRemoteName(v32, v18, &Size[1]);
  LastError = v33;
  if ( v33 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v33);
    goto LABEL_40;
  }
  v20 = *(void **)&Size[1];
  v34 = -1;
  do
    ++v34;
  while ( *(_WORD *)(*(_QWORD *)&Size[1] + 2 * v34) );
  v35 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_S(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      32,
      WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
      *(_QWORD *)&Size[1]);
    v35 = WPP_GLOBAL_Control;
  }
  if ( pszSrc )
  {
    v36 = -1;
    do
      ++v36;
    while ( pszSrc[v36] );
    v37 = (wchar_t *)LocalAlloc(0x40u, 2LL * (unsigned int)(v36 + 1));
    String = v37;
    v21 = v37;
    if ( !v37 )
    {
      LastError = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
      goto LABEL_185;
    }
    StringCchCopyW(v37, (unsigned int)(v36 + 1), pszSrc);
    v38 = (unsigned int)v36;
    if ( wcscspn(pszSrc, asc_180030FB0) != (unsigned int)v36 )
    {
      v39 = 0;
      if ( !(_DWORD)v36 )
      {
LABEL_58:
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_66;
        v42 = 35;
LABEL_65:
        WPP_SF_(v41[2], v42, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
LABEL_66:
        LastError = 87;
LABEL_40:
        v20 = *(void **)&Size[1];
        goto LABEL_185;
      }
      while ( 1 )
      {
        v27 = v39 + 1;
        v40 = v39;
        if ( pszSrc[v40] == 92 )
          break;
        ++v39;
        if ( (unsigned int)v27 >= (unsigned int)v36 )
        {
          v21 = String;
          goto LABEL_58;
        }
      }
      v43 = v36 - v39;
      v44 = v43;
      v45 = v43 - 1;
      memcpy_0(String, &pszSrc[v27], v45 * 2);
      v46 = &String[v44];
      String[v45] = 64;
      memcpy_0(v46, pszSrc, v40 * 2);
      v21 = String;
      if ( wcscspn(String, asc_180030FB0) != v38 )
      {
        v41 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_66;
        v42 = 34;
        goto LABEL_65;
      }
    }
    v35 = WPP_GLOBAL_Control;
    v20 = *(void **)&Size[1];
  }
  if ( v35 != &WPP_GLOBAL_Control && (*((_BYTE *)v35 + 28) & 2) != 0 )
    WPP_SF_S(v35[2], 36, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v21);
  LogonId = DavImpersonateAndGetLogonId(&DestinationLuid);
  LastError = LogonId;
  if ( LogonId )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v30 = 37;
LABEL_75:
    v31 = LogonId;
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Dd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
      (unsigned int)DestinationLuid.HighPart,
      DestinationLuid.LowPart);
  LogonId = DavImpersonateAndGetSessionId(&v81);
  LastError = LogonId;
  if ( LogonId )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v30 = 39;
    goto LABEL_75;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v81);
  v48 = Handle;
  LastError = DavCreateTreeConnectName(v20, Handle, v81, hMem);
  if ( LastError )
  {
    v29 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_185;
    v30 = 41;
    goto LABEL_29;
  }
  v75 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_Z(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, hMem);
  if ( !v48 )
    goto LABEL_99;
  LastError = DavCreateSymbolicLink(v48, hMem[1], &v89, &hObject);
  if ( !LastError )
  {
    v75 = 1;
LABEL_99:
    v49 = Src;
    if ( Src && uBytes )
    {
      v50 = (unsigned int)uBytes;
      v51 = LocalAlloc(0x40u, (unsigned int)uBytes);
      pDataIn = v51;
      if ( !v51 )
      {
        LastError = GetLastError();
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 44;
        goto LABEL_105;
      }
      memcpy_0(v51, v49, v50);
      LastError = DavImpersonateClient();
      if ( LastError )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 45;
        goto LABEL_105;
      }
      v19 = 1;
      if ( !CryptUnprotectMemory(pDataIn, uBytes, 2u) )
      {
        LastError = GetLastError();
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 46;
        goto LABEL_105;
      }
      LastError = ((__int64 (*)(void))DavRevertToSelf)();
      if ( LastError )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 47;
        goto LABEL_105;
      }
    }
    v54 = v95;
    if ( v95 && Size[0] )
    {
      v55 = Size[0];
      v56 = LocalAlloc(0x40u, Size[0]);
      v84 = v56;
      if ( !v56 )
      {
        LastError = GetLastError();
        v57 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_176;
        v58 = 48;
        goto LABEL_124;
      }
      memcpy_0(v56, v54, v55);
      LastError = DavImpersonateClient();
      if ( LastError )
      {
        v57 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_176;
        v58 = 49;
        goto LABEL_124;
      }
      v59 = v84;
      v19 = 1;
      if ( !CryptUnprotectMemory(v84, Size[0], 2u) )
      {
        LastError = GetLastError();
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 50;
        goto LABEL_105;
      }
      LastError = ((__int64 (*)(void))DavRevertToSelf)();
      if ( LastError )
      {
        v52 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_177;
        v53 = 51;
LABEL_105:
        WPP_SF_d(v52[2], v53, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
LABEL_177:
        v64 = hObject;
LABEL_178:
        if ( v75 && LastError )
          DavDeleteSymbolicLink(v48, (LPCWSTR)hMem[1], (LPCWSTR)v89, v64, 0);
        v20 = *(void **)&Size[1];
        goto LABEL_182;
      }
      v60 = -1;
      do
        ++v60;
      while ( v59[v60] );
      Size[0] = 2 * v60 + 2;
    }
    LastError = DavOpenCreateConnection(
                  hMem,
                  String,
                  pDataIn,
                  v91,
                  a9,
                  v90,
                  a12,
                  v20,
                  0x100000,
                  1,
                  160,
                  uBytes_4,
                  &FileHandle,
                  0,
                  a13,
                  a14,
                  Size[0],
                  v84);
    if ( LastError )
    {
      v21 = String;
    }
    else
    {
      v61 = *(const wchar_t **)&Size[1];
      v21 = String;
      v62 = v90;
      Handle = (HANDLE)-1LL;
      LastError = DavOpenCreateConnection(
                    hMem,
                    String,
                    pDataIn,
                    v91,
                    a9,
                    v90,
                    a12,
                    *(_QWORD *)&Size[1],
                    1048577,
                    1,
                    33,
                    uBytes_4,
                    &Handle,
                    0,
                    a13,
                    a14,
                    Size[0],
                    v84);
      if ( !LastError )
      {
        memset_0(v98, 0, 0x202u);
        if ( v62 && !(unsigned int)GetServerName(v92, v98) )
          DavrSetCookie(IoStatusBlock.Pointer, v98, v62);
        NtClose(Handle);
        if ( !v21 )
        {
          uBytes_4 = 257;
          v63 = (WCHAR *)LocalAlloc(0x40u, 0x204u);
          v21 = v63;
          if ( !v63 )
          {
            LastError = GetLastError();
            v57 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_176;
            v58 = 55;
LABEL_124:
            WPP_SF_d(v57[2], v58, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
            goto LABEL_176;
          }
          LastError = DavImpersonateAndGetUserId(v63, &uBytes_4);
          if ( LastError )
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                56,
                WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
                LastError);
            goto LABEL_176;
          }
        }
        v64 = hObject;
        v19 = 0;
        LastError = DavAddUse(
                      (int)&DestinationLuid,
                      (int)v48,
                      InputBuffer,
                      (int)v21,
                      v61,
                      v34,
                      (__int64)hMem,
                      FileHandle,
                      hObject,
                      (__int64)v89);
        if ( LastError
          && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 57, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        }
        goto LABEL_178;
      }
      InputBuffer = 0;
      IoStatusBlock = 0;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
      Status = NtFsControlFile(FileHandle, 0, 0, 0, &IoStatusBlock, 0x4000020u, &InputBuffer, 4u, 0, 0);
      if ( Status < 0 || (Status = IoStatusBlock.Status, IoStatusBlock.Status < 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            53,
            WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
            (unsigned int)Status);
      }
      NtClose(FileHandle);
      FileHandle = (HANDLE)-1LL;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    switch ( LastError )
    {
      case 2u:
      case 0x7Bu:
        goto LABEL_175;
      case 0x4CDu:
        LastError = 67;
        break;
      case 0x8CAu:
LABEL_175:
        LastError = 53;
        break;
    }
LABEL_176:
    v19 = 0;
    goto LABEL_177;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 43, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
LABEL_182:
  if ( hObject != (HANDLE)-1LL && LastError )
    CloseHandle(hObject);
LABEL_185:
  if ( FileHandle != (HANDLE)-1LL && LastError )
    NtClose(FileHandle);
  if ( v21 )
    LocalFree(v21);
  v66 = hMem[1];
  if ( hMem[1] )
    LocalFree(hMem[1]);
  if ( v89 )
    LocalFree(v89);
  if ( v20 )
    LocalFree(v20);
  if ( v19 )
    DavRevertToSelf(v66, v27, v23);
  v67 = pDataIn;
  if ( pDataIn )
  {
    v68 = (unsigned int)uBytes;
    v69 = pDataIn;
    if ( uBytes )
    {
      do
      {
        *v69++ = 0;
        --v68;
      }
      while ( v68 );
    }
    LocalFree(v67);
  }
  v70 = v84;
  if ( v84 )
  {
    v71 = Size[0];
    v72 = v84;
    if ( Size[0] )
    {
      do
      {
        *v72++ = 0;
        --v71;
      }
      while ( v71 );
    }
    LocalFree(v70);
  }
  if ( v85 )
    LocalFree(v85);
  return LastError;
}

```

## disassembly

```asm
0x180006d20  mov     [rsp-8+arg_0], rbx
0x180006d25  push    rbp
0x180006d26  push    rsi
0x180006d27  push    rdi
0x180006d28  push    r12
0x180006d2a  push    r13
0x180006d2c  push    r14
0x180006d2e  push    r15
0x180006d30  lea     rbp, [rsp-260h]
0x180006d38  sub     rsp, 370h
0x180006d3f  mov     rax, cs:__security_cookie
0x180006d46  xor     rax, rsp
0x180006d49  mov     [rbp+290h+var_40], rax
0x180006d50  mov     rax, [rbp+290h+arg_20]
0x180006d57  mov     rbx, rdx
0x180006d5a  mov     r12, [rbp+290h+pszSrc]
0x180006d61  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180006d65  mov     [rbp+290h+Src], rax
0x180006d69  xorps   xmm0, xmm0
0x180006d6c  mov     eax, [rbp+290h+arg_28]
0x180006d72  mov     r13d, r9d
0x180006d75  mov     dword ptr [rbp+290h+uBytes], eax
0x180006d78  mov     rdi, r8
0x180006d7b  mov     rax, [rbp+290h+arg_48]
0x180006d82  mov     [rbp+290h+var_288], rax
0x180006d86  mov     rax, [rbp+290h+arg_50]
0x180006d8d  mov     [rbp+290h+var_290], rax
0x180006d91  mov     eax, [rbp+290h+arg_70]
0x180006d97  mov     dword ptr [rbp+290h+Size], eax
0x180006d9a  mov     rax, [rbp+290h+arg_78]
0x180006da1  mov     qword ptr [rbp+290h+var_278], rcx
0x180006da5  xor     ecx, ecx
0x180006da7  mov     [rbp+290h+var_260], rax
0x180006dab  mov     r14b, cl
0x180006dae  xor     eax, eax
0x180006db0  mov     [rbp+290h+var_2E0], ecx
0x180006db3  mov     qword ptr [rbp+290h+DestinationLuid.LowPart], rcx
0x180006db7  mov     r15d, ecx
0x180006dba  mov     [rbp+290h+FileHandle], rdx
0x180006dbe  mov     esi, ecx
0x180006dc0  mov     qword ptr [rbp+290h+Size+4], rcx
0x180006dc4  mov     [rbp+290h+var_298], rcx
0x180006dc8  mov     [rbp+290h+String], rcx
0x180006dcc  mov     [rbp+290h+hObject], rdx
0x180006dd0  lea     rdx, [rbp+290h+var_2C0]
0x180006dd4  mov     [rbp+290h+pDataIn], rcx
0x180006dd8  mov     [rbp+290h+var_2C8], rcx
0x180006ddc  mov     [rbp+290h+var_2C0], rcx
0x180006de0  mov     rcx, r8
0x180006de3  mov     [rbp+290h+var_258], eax
0x180006de6  mov     [rbp+290h+var_254], ax
0x180006dea  mov     dword ptr [rbp+290h+uBytes+4], r9d
0x180006dee  mov     [rbp+290h+var_280], r8
0x180006df2  movups  xmmword ptr [rbp+290h+hMem], xmm0
0x180006df6  call    DavConvertIDNToPunyCodeUNC
0x180006dfb  xor     edx, edx
0x180006dfd  lea     r8, WPP_GLOBAL_Control
0x180006e04  test    eax, eax
0x180006e06  jz      short loc_180006E4F
0x180006e08  cmp     [rbp+290h+var_2C0], rdx
0x180006e0c  jz      short loc_180006E4F
0x180006e0e  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e15  cmp     rcx, r8
0x180006e18  jz      short loc_180006E45
0x180006e1a  test    byte ptr [rcx+1Ch], 2
0x180006e1e  jz      short loc_180006E45
0x180006e20  mov     r9, [rbp+290h+var_2C0]
0x180006e24  lea     edx, [rsi+18h]
0x180006e27  mov     rcx, [rcx+10h]
0x180006e2b  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006e32  call    WPP_SF_S
0x180006e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e3e  lea     r8, WPP_GLOBAL_Control
0x180006e45  mov     rdi, [rbp+290h+var_2C0]
0x180006e49  mov     [rbp+290h+var_280], rdi
0x180006e4d  jmp     short loc_180006E56
0x180006e4f  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e56  cmp     rcx, r8
0x180006e59  jz      short loc_180006E9A
0x180006e5b  test    byte ptr [rcx+1Ch], 2
0x180006e5f  jz      short loc_180006E9A
0x180006e61  mov     rcx, [rcx+10h]
0x180006e65  lea     rax, aNull_0; "NULL"
0x180006e6c  test    rbx, rbx
0x180006e6f  mov     [rsp+3A0h+IoStatusBlock], rdi
0x180006e74  mov     r9, rbx
0x180006e77  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006e7e  cmovz   r9, rax
0x180006e82  mov     edx, 19h
0x180006e87  call    WPP_SF_SS
0x180006e8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180006e93  lea     r8, WPP_GLOBAL_Control
0x180006e9a  xor     edx, edx
0x180006e9c  mov     [rbp+290h+hMem+8], rdx
0x180006ea0  mov     dword ptr [rbp+290h+hMem], edx
0x180006ea3  cmp     r13d, 2
0x180006ea7  jb      short loc_180006ED7
0x180006ea9  lea     ebx, [rdx+57h]
0x180006eac  cmp     rcx, r8
0x180006eaf  jz      loc_180007A5B
0x180006eb5  test    byte ptr [rcx+1Ch], 1
0x180006eb9  jz      loc_180007A5B
0x180006ebf  mov     rcx, [rcx+10h]
0x180006ec3  lea     edx, [rbx-3Dh]
0x180006ec6  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006ecd  call    WPP_SF_
0x180006ed2  jmp     loc_180007A5B
0x180006ed7  mov     eax, dword ptr [rbp+290h+uBytes]
0x180006eda  test    al, 0Fh
0x180006edc  jz      short loc_180006F11
0x180006ede  mov     ebx, 57h ; 'W'
0x180006ee3  cmp     rcx, r8
0x180006ee6  jz      loc_180007A5B
0x180006eec  test    byte ptr [rcx+1Ch], 1
0x180006ef0  jz      loc_180007A5B
0x180006ef6  mov     rcx, [rcx+10h]
0x180006efa  lea     edx, [rbx-3Ch]
0x180006efd  mov     r9d, eax
0x180006f00  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006f07  call    WPP_SF_d
0x180006f0c  jmp     loc_180007A5B
0x180006f11  test    rbx, rbx
0x180006f14  jz      loc_180006FD1
0x180006f1a  cmp     rcx, r8
0x180006f1d  jz      short loc_180006F42
0x180006f1f  test    byte ptr [rcx+1Ch], 2
0x180006f23  jz      short loc_180006F42
0x180006f25  mov     rcx, [rcx+10h]
0x180006f29  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006f30  mov     edx, 1Ch
0x180006f35  mov     [rsp+3A0h+IoStatusBlock], rdi
0x180006f3a  mov     r9, rbx
0x180006f3d  call    WPP_SF_SS
0x180006f42  lea     rdx, [rbp+290h+var_258]
0x180006f46  mov     rcx, rbx
0x180006f49  call    DavCheckLocalName
0x180006f4e  mov     ebx, eax
0x180006f50  test    eax, eax
0x180006f52  jz      short loc_180006F92
0x180006f54  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f5b  lea     rax, WPP_GLOBAL_Control
0x180006f62  cmp     rcx, rax
0x180006f65  jz      loc_180007A5B
0x180006f6b  test    byte ptr [rcx+1Ch], 1
0x180006f6f  jz      loc_180007A5B
0x180006f75  mov     edx, 1Dh
0x180006f7a  mov     r9d, ebx
0x180006f7d  mov     rcx, [rcx+10h]
0x180006f81  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006f88  call    WPP_SF_d
0x180006f8d  jmp     loc_180007A5B
0x180006f92  mov     rcx, cs:WPP_GLOBAL_Control
0x180006f99  lea     r15, WPP_GLOBAL_Control
0x180006fa0  mov     [rbp+290h+var_2F0], 3
0x180006fa7  cmp     rcx, r15
0x180006faa  jz      short loc_180006FCB
0x180006fac  test    byte ptr [rcx+1Ch], 2
0x180006fb0  jz      short loc_180006FCB
0x180006fb2  mov     rcx, [rcx+10h]
0x180006fb6  lea     r9, [rbp+290h+var_258]
0x180006fba  mov     edx, 1Eh
0x180006fbf  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180006fc6  call    WPP_SF_S
0x180006fcb  lea     rcx, [rbp+290h+var_258]
0x180006fcf  jmp     short loc_180006FDD
0x180006fd1  xor     ecx, ecx
0x180006fd3  lea     r15, WPP_GLOBAL_Control
0x180006fda  mov     [rbp+290h+var_2F0], ecx
0x180006fdd  lea     r8, [rbp+290h+Size+4]
0x180006fe1  mov     [rbp+290h+Handle], rcx
0x180006fe5  mov     rdx, rdi
0x180006fe8  call    DavCheckRemoteName
0x180006fed  mov     ebx, eax
0x180006fef  test    eax, eax
0x180006ff1  jz      short loc_180007026
0x180006ff3  mov     rcx, cs:WPP_GLOBAL_Control
0x180006ffa  cmp     rcx, r15
0x180006ffd  jz      short loc_18000701D
0x180006fff  test    byte ptr [rcx+1Ch], 1
0x180007003  jz      short loc_18000701D
0x180007005  mov     rcx, [rcx+10h]
0x180007009  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x180007010  mov     edx, 1Fh
0x180007015  mov     r9d, eax
0x180007018  call    WPP_SF_d
0x18000701d  mov     r15, qword ptr [rbp+290h+Size+4]
0x180007021  jmp     loc_180007A5B
0x180007026  mov     r15, qword ptr [rbp+290h+Size+4]
0x18000702a  or      r13, 0FFFFFFFFFFFFFFFFh
0x18000702e  xor     edi, edi
0x180007030  inc     r13
0x180007033  cmp     [r15+r13*2], di
0x180007038  jnz     short loc_180007030
0x18000703a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007041  lea     rax, WPP_GLOBAL_Control
0x180007048  cmp     rcx, rax
0x18000704b  jz      short loc_180007072
0x18000704d  test    byte ptr [rcx+1Ch], 2
0x180007051  jz      short loc_180007072
0x180007053  mov     rcx, [rcx+10h]
0x180007057  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000705e  mov     edx, 20h ; ' '
0x180007063  mov     r9, r15
0x180007066  call    WPP_SF_S
0x18000706b  mov     rcx, cs:WPP_GLOBAL_Control
0x180007072  test    r12, r12
0x180007075  jz      loc_1800071F4
0x18000707b  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000707f  inc     rbx
0x180007082  cmp     [r12+rbx*2], di
0x180007087  jnz     short loc_18000707F
0x180007089  lea     eax, [rbx+1]
0x18000708c  mov     ecx, 40h ; '@'; uFlags
0x180007091  lea     rdx, [rax+rax]; uBytes
0x180007095  mov     edi, eax
0x180007097  call    cs:__imp_LocalAlloc
0x18000709d  mov     [rbp+290h+String], rax
0x1800070a1  mov     rsi, rax
0x1800070a4  test    rax, rax
0x1800070a7  jnz     short loc_1800070ED
0x1800070a9  call    cs:__imp_GetLastError
0x1800070af  mov     ebx, eax
0x1800070b1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800070b8  lea     rax, WPP_GLOBAL_Control
0x1800070bf  cmp     rcx, rax
0x1800070c2  jz      loc_180007A5B
0x1800070c8  test    byte ptr [rcx+1Ch], 1
0x1800070cc  jz      loc_180007A5B
0x1800070d2  mov     rcx, [rcx+10h]
0x1800070d6  lea     edx, [rsi+21h]
0x1800070d9  mov     r9d, ebx
0x1800070dc  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800070e3  call    WPP_SF_d
0x1800070e8  jmp     loc_180007A5B
0x1800070ed  mov     r8, r12; pszSrc
0x1800070f0  mov     rdx, rdi; cchDest
0x1800070f3  mov     rcx, rax; pszDest
0x1800070f6  call    StringCchCopyW
0x1800070fb  lea     rdx, asc_180030FB0; "\"/:|<>?"
0x180007102  mov     r15d, ebx
0x180007105  mov     rcx, r12; String
0x180007108  call    cs:__imp_wcscspn
0x18000710e  cmp     rax, r15
0x180007111  jz      loc_1800071E7
0x180007117  xor     eax, eax
0x180007119  mov     ecx, eax
0x18000711b  test    ebx, ebx
0x18000711d  jz      short loc_18000713A
0x18000711f  mov     eax, ecx
0x180007121  lea     edx, [rcx+1]
0x180007124  lea     rsi, [rax+rax]
0x180007128  cmp     word ptr [r12+rsi], 5Ch ; '\'
0x18000712e  jz      short loc_180007162
0x180007130  mov     ecx, edx
0x180007132  cmp     edx, ebx
0x180007134  jb      short loc_18000711F
0x180007136  mov     rsi, [rbp+290h+String]
0x18000713a  mov     rcx, cs:WPP_GLOBAL_Control
0x180007141  lea     rax, WPP_GLOBAL_Control
0x180007148  cmp     rcx, rax
0x18000714b  jz      loc_1800071DD
0x180007151  test    byte ptr [rcx+1Ch], 1
0x180007155  jz      loc_1800071DD
0x18000715b  mov     edx, 23h ; '#'
0x180007160  jmp     short loc_1800071CD
0x180007162  sub     ebx, ecx
0x180007164  lea     rdx, [r12+rdx*2]; Src
0x180007168  mov     rcx, [rbp+290h+String]; void *
0x18000716c  mov     edi, ebx
0x18000716e  lea     eax, [rbx-1]
0x180007171  lea     rbx, [rax+rax]
0x180007175  mov     r8, rbx; Size
0x180007178  call    memcpy_0
0x18000717d  mov     rax, [rbp+290h+String]
0x180007181  mov     r8, rsi; Size
0x180007184  mov     rdx, r12; Src
0x180007187  lea     rcx, [rax+rdi*2]; void *
0x18000718b  mov     word ptr [rbx+rax], 40h ; '@'
0x180007191  call    memcpy_0
0x180007196  mov     rsi, [rbp+290h+String]
0x18000719a  lea     rdx, asc_180030FB0; "\"/:|<>?"
0x1800071a1  mov     rcx, rsi; String
0x1800071a4  call    cs:__imp_wcscspn
0x1800071aa  cmp     rax, r15
0x1800071ad  jz      short loc_1800071E7
0x1800071af  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071b6  lea     rax, WPP_GLOBAL_Control
0x1800071bd  cmp     rcx, rax
0x1800071c0  jz      short loc_1800071DD
0x1800071c2  test    byte ptr [rcx+1Ch], 1
0x1800071c6  jz      short loc_1800071DD
0x1800071c8  mov     edx, 22h ; '"'
0x1800071cd  mov     rcx, [rcx+10h]
0x1800071d1  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x1800071d8  call    WPP_SF_
0x1800071dd  mov     ebx, 57h ; 'W'
0x1800071e2  jmp     loc_18000701D
0x1800071e7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800071ee  xor     edi, edi
0x1800071f0  mov     r15, qword ptr [rbp+290h+Size+4]
  ... truncated ...
```
