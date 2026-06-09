# DavrIsValidShare

- ea: `0x18000a770`
- end: `0x18000b048`
- name: `DavrIsValidShare`
- size: `2264`
- prototype: ``
- caller_count: `0`
- callee_count: `18`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002bac`
- `0x18000591c`
- `0x180005a38`
- `0x180005d38`
- `0x180006618`
- `0x18000a770`
- `0x18000b060`
- `0x18000b4f0`
- `0x18000b728`
- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b93c`
- `0x18000b99c`
- `0x18000ba14`
- `0x18000fce0`
- `0x180028440`
- `0x18002cf62`
- `0x18002cfa0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18000a924`
- `msvcrt!_wcsicmp` at `0x18000abe1`
- `msvcrt!_wcsicmp` at `0x18000a924`
- `msvcrt!_wcsicmp` at `0x18000abe1`
- `ntdll!NtCreateFile` at `0x18000aebe`
- `ntdll!NtCreateFile` at `0x18000aebe`
- `ntdll!RtlNtStatusToDosError` at `0x18000af31`
- `ntdll!RtlNtStatusToDosError` at `0x18000af31`
- `ntdll!NtClose` at `0x18000aecf`
- `ntdll!NtClose` at `0x18000aecf`
- `ntdll!RtlInitUnicodeString` at `0x18000ae48`
- `ntdll!RtlInitUnicodeString` at `0x18000ae48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a810`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a864`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac97`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad1b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000aa92`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ac19`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000ad1b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aade`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aa7b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000aade`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18000a976`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18000a976`
- `KERNEL32!LocalFree` at `0x18000b016`
- `KERNEL32!LocalFree` at `0x18000b016`
- `KERNEL32!LocalAlloc` at `0x18000a802`
- `KERNEL32!LocalAlloc` at `0x18000ac82`
- `KERNEL32!LocalAlloc` at `0x18000a802`
- `KERNEL32!LocalAlloc` at `0x18000ac82`

## pseudocode

```c
__int64 __fastcall DavrIsValidShare(__int64 a1, void *a2, const wchar_t *a3, const wchar_t *a4, __int16 a5, char *a6)
{
  char v8; // di
  char *EaBuffer; // r12
  unsigned int v10; // eax
  wchar_t *v11; // rsi
  DWORD LastError; // ebx
  _QWORD *v13; // rcx
  int v14; // r13d
  HRESULT v15; // eax
  __int64 v16; // rdx
  _QWORD *v17; // rcx
  __int64 v18; // rdx
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  __int64 result; // rax
  int v22; // ebx
  _QWORD *v23; // rdi
  _QWORD *v24; // rcx
  __int64 v25; // rbx
  __int64 v26; // rdx
  __int64 v27; // r8
  void *v28; // rcx
  const wchar_t *v29; // rdi
  size_t v30; // rbx
  __int64 v31; // rax
  const char *v32; // r8
  __int64 v33; // rdx
  _BYTE *v34; // rcx
  _BYTE *v35; // rax
  int v36; // r11d
  HRESULT v37; // eax
  int v38; // eax
  char v39; // di
  STRSAFE_LPCWSTR v40; // rax
  unsigned int v41; // eax
  int v42; // [rsp+60h] [rbp-A0h]
  void *FileHandle; // [rsp+68h] [rbp-98h] BYREF
  ULONG EaLength[2]; // [rsp+70h] [rbp-90h]
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-88h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+90h] [rbp-70h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+98h] [rbp-68h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+C8h] [rbp-38h] BYREF
  wchar_t pszDest[520]; // [rsp+E0h] [rbp-20h] BYREF

  *(_QWORD *)&DestinationString.Length = a2;
  v47 = a1;
  v42 = 0;
  pszSrc = a4;
  memset_0(pszDest, 0, sizeof(pszDest));
  v8 = *a6;
  FileHandle = 0;
  EaLength[0] = 0;
  EaBuffer = 0;
  *a6 = 0;
  v10 = DavConvertIDNToPunyCode(a2);
  if ( !v10 )
  {
    v11 = (wchar_t *)a2;
    goto LABEL_14;
  }
  v11 = (wchar_t *)LocalAlloc(0x40u, 2LL * v10);
  if ( !v11 )
  {
    LastError = GetLastError();
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 140, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    goto LABEL_108;
  }
  DavConvertIDNToPunyCode(a2);
  LastError = GetLastError();
  if ( LastError )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 141, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
    goto LABEL_113;
  }
  v13 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
    {
LABEL_15:
      if ( v13 != &WPP_GLOBAL_Control && (*((_BYTE *)v13 + 28) & 2) != 0 )
        WPP_SF_SS(v13[2], 143, (unsigned int)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, (_DWORD)v11, (__int64)a3);
      goto LABEL_18;
    }
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 142, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v11);
LABEL_14:
    v13 = WPP_GLOBAL_Control;
    goto LABEL_15;
  }
LABEL_18:
  v14 = _wcsicmp(L"DavWWWRoot", a3);
  v15 = StringCchPrintfW(pszDest, 0x104u, L"%s\\%s", v11, a3);
  if ( v15 < 0 )
  {
    v17 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_33;
    v18 = 144;
LABEL_32:
    WPP_SF_d(v17[2], v18, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, (unsigned int)v15);
LABEL_33:
    result = 2140;
LABEL_45:
    *a6 = 0;
    return result;
  }
  DavRemoveDummyShareFromFileName(pszDest, v16);
  if ( v14 )
  {
    if ( (unsigned int)DavIsConnectedByThisUser(pszDest) )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
        goto LABEL_39;
      v20 = 145;
LABEL_38:
      WPP_SF_(v19[2], v20, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
LABEL_39:
      *a6 = 1;
      return 0;
    }
    if ( v8 )
    {
      memset_0(pszDest, 0, 0x208u);
      v15 = StringCchPrintfW(pszDest, 0x104u, L"%s\\", v11);
      if ( v15 < 0 )
      {
        v17 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_33;
        v18 = 146;
        goto LABEL_32;
      }
      if ( (unsigned int)DavIsConnectedByThisUser(pszDest) )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
          goto LABEL_39;
        v20 = 147;
        goto LABEL_38;
      }
    }
  }
  memset_0(pszDest, 0, 0x208u);
  EnterCriticalSection(&NonDAVServerListLock);
  v22 = DavCheckTheNonDAVServerList(v11);
  LeaveCriticalSection(&NonDAVServerListLock);
  if ( v22 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 148, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v11);
    result = 0;
    goto LABEL_45;
  }
  EnterCriticalSection(&ServerShareTableLock);
  v23 = FileHandle;
  LastError = 0;
  if ( !(unsigned int)DavIsServerInServerShareTable(v11) )
    goto LABEL_52;
  v24 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 149, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v24 = WPP_GLOBAL_Control;
  }
  if ( *((_QWORD *)FileHandle + 1) )
  {
    DavFinalizeFileAttributesList(*((char **)FileHandle + 1), 1);
    *((_QWORD *)FileHandle + 1) = 0;
LABEL_52:
    v24 = WPP_GLOBAL_Control;
  }
  if ( !v14 || !v23 || !v23[1] )
  {
LABEL_68:
    *a6 = 0;
    LeaveCriticalSection(&ServerShareTableLock);
    if ( *a6 )
      return LastError;
    v28 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 153, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v29 = pszSrc;
    if ( pszSrc )
    {
      v30 = (unsigned __int16)(2 * a5);
      *(_QWORD *)EaLength = ((_DWORD)v30 + 19) & 0xFFFFFFFC;
      EaBuffer = (char *)LocalAlloc(0x40u, *(SIZE_T *)EaLength);
      if ( !EaBuffer )
      {
        LastError = GetLastError();
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 154, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
        goto LABEL_108;
      }
      v31 = 2147483646;
      v32 = "Cookie:";
      v33 = 8;
      v34 = EaBuffer + 8;
      do
      {
        if ( !v31 )
          break;
        if ( !*v32 )
          break;
        *v34++ = *v32++;
        --v31;
        --v33;
      }
      while ( v33 );
      v35 = v34 - 1;
      if ( v33 )
        v35 = v34;
      *v35 = 0;
      EaBuffer[5] = 7;
      StringCbCopyW((STRSAFE_LPWSTR)EaBuffer + 8, v30, v29);
      *((_WORD *)EaBuffer + 3) = v30;
      *(_DWORD *)EaBuffer = v36;
      EaBuffer[4] = v36;
    }
    LastError = DavImpersonateClient(v28, v26, v27);
    if ( LastError )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 155, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, LastError);
      goto LABEL_113;
    }
    v42 = 1;
    FileHandle = 0;
    memset(&ObjectAttributes, 0, 44);
    IoStatusBlock = 0;
    if ( v14 )
      v37 = StringCchPrintfW(
              pszDest,
              0x208u,
              L"\\Device\\WebDavRedirector\\%s\\DavWWWRoot\\%s",
              *(_QWORD *)&DestinationString.Length,
              a3);
    else
      v37 = StringCchPrintfW(
              pszDest,
              0x208u,
              L"\\Device\\WebDavRedirector\\%s\\DavWWWRoot",
              *(_QWORD *)&DestinationString.Length);
    if ( v37 < 0 )
    {
      LastError = 87;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 158, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a3);
      goto LABEL_113;
    }
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, pszDest);
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v38 = NtCreateFile(
            &FileHandle,
            0x100001u,
            &ObjectAttributes,
            &IoStatusBlock,
            0,
            0x80u,
            7u,
            1u,
            0x21u,
            EaBuffer,
            EaLength[0]);
    v39 = v38;
    if ( v38 >= 0 )
    {
      NtClose(FileHandle);
      v40 = pszSrc;
      *a6 = 1;
      if ( v40 )
        DavrSetCookie(v47, v11, v40);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 156, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a3);
      goto LABEL_115;
    }
    LastError = RtlNtStatusToDosError(v38);
    *a6 = 0;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        157,
        (unsigned int)WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids,
        (_DWORD)a3,
        v39);
    if ( LastError == 67 )
    {
      if ( !v14 )
      {
        LastError = 53;
        goto LABEL_108;
      }
LABEL_113:
      *a6 = 0;
LABEL_114:
      if ( !v42 )
      {
LABEL_119:
        if ( EaBuffer )
        {
          memset_0(EaBuffer, 0, EaLength[0]);
          LocalFree(EaBuffer);
        }
        return LastError;
      }
LABEL_115:
      v41 = DavRevertToSelf();
      if ( v41
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 159, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, v41);
      }
      goto LABEL_119;
    }
LABEL_108:
    if ( !LastError )
      goto LABEL_114;
    goto LABEL_113;
  }
  if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
  {
    WPP_SF_(v24[2], 150, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids);
    v24 = WPP_GLOBAL_Control;
  }
  v25 = v23[1] + 64LL;
  while ( 1 )
  {
    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 28) & 2) != 0 )
    {
      WPP_SF_S(v24[2], 151, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, *(_QWORD *)(v25 + 32));
      v24 = WPP_GLOBAL_Control;
    }
    if ( !*(_BYTE *)(v25 + 20) )
      goto LABEL_66;
    if ( !_wcsicmp(*(const wchar_t **)(v25 + 32), a3) )
      break;
    v24 = WPP_GLOBAL_Control;
LABEL_66:
    v25 = *(_QWORD *)v25;
    if ( v25 == v23[1] + 64LL )
    {
      LastError = 0;
      goto LABEL_68;
    }
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 152, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids, a3);
  LastError = 0;
  *a6 = 1;
  LeaveCriticalSection(&ServerShareTableLock);
  return LastError;
}

```

## disassembly

```asm
0x18000a770  mov     [rsp-8+arg_0], rbx
0x18000a775  push    rbp
0x18000a776  push    rsi
0x18000a777  push    rdi
0x18000a778  push    r12
0x18000a77a  push    r13
0x18000a77c  push    r14
0x18000a77e  push    r15
0x18000a780  lea     rbp, [rsp-400h]
0x18000a788  sub     rsp, 500h
0x18000a78f  mov     rax, cs:__security_cookie
0x18000a796  xor     rax, rsp
0x18000a799  mov     [rbp+430h+var_40], rax
0x18000a7a0  mov     r14, [rbp+430h+arg_28]
0x18000a7a7  mov     r15, r8
0x18000a7aa  mov     r13, rdx
0x18000a7ad  mov     qword ptr [rsp+530h+DestinationString.Length], rdx
0x18000a7b2  mov     [rbp+430h+var_4A0], rcx
0x18000a7b6  xor     esi, esi
0x18000a7b8  xor     edx, edx; Val
0x18000a7ba  mov     [rsp+530h+var_4D0], esi
0x18000a7be  mov     r8d, 410h; Size
0x18000a7c4  mov     [rbp+430h+pszSrc], r9
0x18000a7c8  lea     rcx, [rbp+430h+pszDest]; void *
0x18000a7cc  call    memset_0
0x18000a7d1  mov     dil, [r14]
0x18000a7d4  xor     r8d, r8d
0x18000a7d7  xor     edx, edx
0x18000a7d9  mov     [rsp+530h+FileHandle], rsi
0x18000a7de  mov     rcx, r13; hMem
0x18000a7e1  mov     [rsp+530h+var_4C0], esi
0x18000a7e5  mov     r12d, esi
0x18000a7e8  mov     [r14], sil
0x18000a7eb  call    DavConvertIDNToPunyCode
0x18000a7f0  mov     ebx, eax
0x18000a7f2  test    eax, eax
0x18000a7f4  jz      loc_18000A8E1
0x18000a7fa  mov     edx, ebx
0x18000a7fc  lea     ecx, [rsi+40h]; uFlags
0x18000a7ff  add     rdx, rdx; uBytes
0x18000a802  call    cs:__imp_LocalAlloc
0x18000a808  mov     rsi, rax
0x18000a80b  test    rax, rax
0x18000a80e  jnz     short loc_18000A856
0x18000a810  call    cs:__imp_GetLastError
0x18000a816  mov     ebx, eax
0x18000a818  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a81f  lea     rax, WPP_GLOBAL_Control
0x18000a826  cmp     rcx, rax
0x18000a829  jz      loc_18000AF80
0x18000a82f  test    byte ptr [rcx+1Ch], 1
0x18000a833  jz      loc_18000AF80
0x18000a839  mov     rcx, [rcx+10h]
0x18000a83d  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a844  mov     edx, 8Ch
0x18000a849  mov     r9d, ebx
0x18000a84c  call    WPP_SF_d
0x18000a851  jmp     loc_18000AF80
0x18000a856  mov     r8d, ebx
0x18000a859  mov     rdx, rsi
0x18000a85c  mov     rcx, r13; hMem
0x18000a85f  call    DavConvertIDNToPunyCode
0x18000a864  call    cs:__imp_GetLastError
0x18000a86a  mov     ebx, eax
0x18000a86c  test    eax, eax
0x18000a86e  jz      short loc_18000A8AE
0x18000a870  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a877  lea     rax, WPP_GLOBAL_Control
0x18000a87e  cmp     rcx, rax
0x18000a881  jz      loc_18000AFBA
0x18000a887  test    byte ptr [rcx+1Ch], 1
0x18000a88b  jz      loc_18000AFBA
0x18000a891  mov     rcx, [rcx+10h]
0x18000a895  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a89c  mov     edx, 8Dh
0x18000a8a1  mov     r9d, ebx
0x18000a8a4  call    WPP_SF_d
0x18000a8a9  jmp     loc_18000AFBA
0x18000a8ae  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8b5  lea     rbx, WPP_GLOBAL_Control
0x18000a8bc  cmp     rcx, rbx
0x18000a8bf  jz      short loc_18000A91A
0x18000a8c1  test    byte ptr [rcx+1Ch], 2
0x18000a8c5  jz      short loc_18000A8F2
0x18000a8c7  mov     rcx, [rcx+10h]
0x18000a8cb  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a8d2  mov     edx, 8Eh
0x18000a8d7  mov     r9, rsi
0x18000a8da  call    WPP_SF_S
0x18000a8df  jmp     short loc_18000A8EB
0x18000a8e1  mov     rsi, r13
0x18000a8e4  lea     rbx, WPP_GLOBAL_Control
0x18000a8eb  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a8f2  cmp     rcx, rbx
0x18000a8f5  jz      short loc_18000A91A
0x18000a8f7  test    byte ptr [rcx+1Ch], 2
0x18000a8fb  jz      short loc_18000A91A
0x18000a8fd  mov     rcx, [rcx+10h]
0x18000a901  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000a908  mov     edx, 8Fh
0x18000a90d  mov     [rsp+530h+AllocationSize], r15
0x18000a912  mov     r9, rsi
0x18000a915  call    WPP_SF_SS
0x18000a91a  mov     rdx, r15; String2
0x18000a91d  lea     rcx, aDavwwwroot; "DavWWWRoot"
0x18000a924  call    cs:__imp__wcsicmp
0x18000a92a  mov     r9, rsi
0x18000a92d  mov     [rsp+530h+AllocationSize], r15
0x18000a932  lea     r8, aSS; "%s\\%s"
0x18000a939  mov     edx, 104h; cchDest
0x18000a93e  lea     rcx, [rbp+430h+pszDest]; pszDest
0x18000a942  mov     r13d, eax
0x18000a945  call    StringCchPrintfW
0x18000a94a  test    eax, eax
0x18000a94c  jns     short loc_18000A972
0x18000a94e  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a955  cmp     rcx, rbx
0x18000a958  jz      loc_18000AA18
0x18000a95e  test    byte ptr [rcx+1Ch], 1
0x18000a962  jz      loc_18000AA18
0x18000a968  mov     edx, 90h
0x18000a96d  jmp     loc_18000AA05
0x18000a972  lea     rcx, [rbp+430h+pszDest]
0x18000a976  call    cs:__imp_DavRemoveDummyShareFromFileName
0x18000a97c  test    r13d, r13d
0x18000a97f  jz      loc_18000AA63
0x18000a985  mov     dl, 1
0x18000a987  lea     rcx, [rbp+430h+pszDest]; String2
0x18000a98b  call    DavIsConnectedByThisUser
0x18000a990  test    eax, eax
0x18000a992  jz      short loc_18000A9B8
0x18000a994  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a99b  cmp     rcx, rbx
0x18000a99e  jz      loc_18000AA58
0x18000a9a4  test    byte ptr [rcx+1Ch], 2
0x18000a9a8  jz      loc_18000AA58
0x18000a9ae  mov     edx, 91h
0x18000a9b3  jmp     loc_18000AA48
0x18000a9b8  test    dil, dil
0x18000a9bb  jz      loc_18000AA63
0x18000a9c1  xor     edx, edx; Val
0x18000a9c3  lea     rcx, [rbp+430h+pszDest]; void *
0x18000a9c7  mov     r8d, 208h; Size
0x18000a9cd  call    memset_0
0x18000a9d2  mov     r9, rsi
0x18000a9d5  lea     r8, aS; "%s\\"
0x18000a9dc  mov     edx, 104h; cchDest
0x18000a9e1  lea     rcx, [rbp+430h+pszDest]; pszDest
0x18000a9e5  call    StringCchPrintfW
0x18000a9ea  test    eax, eax
0x18000a9ec  jns     short loc_18000AA22
0x18000a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18000a9f5  cmp     rcx, rbx
0x18000a9f8  jz      short loc_18000AA18
0x18000a9fa  test    byte ptr [rcx+1Ch], 1
0x18000a9fe  jz      short loc_18000AA18
0x18000aa00  mov     edx, 92h
0x18000aa05  mov     rcx, [rcx+10h]
0x18000aa09  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000aa10  mov     r9d, eax
0x18000aa13  call    WPP_SF_d
0x18000aa18  mov     eax, 85Ch
0x18000aa1d  jmp     loc_18000AACF
0x18000aa22  mov     dl, 1
0x18000aa24  lea     rcx, [rbp+430h+pszDest]; String2
0x18000aa28  call    DavIsConnectedByThisUser
0x18000aa2d  test    eax, eax
0x18000aa2f  jz      short loc_18000AA63
0x18000aa31  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aa38  cmp     rcx, rbx
0x18000aa3b  jz      short loc_18000AA58
0x18000aa3d  test    byte ptr [rcx+1Ch], 2
0x18000aa41  jz      short loc_18000AA58
0x18000aa43  mov     edx, 93h
0x18000aa48  mov     rcx, [rcx+10h]
0x18000aa4c  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000aa53  call    WPP_SF_
0x18000aa58  mov     byte ptr [r14], 1
0x18000aa5c  xor     eax, eax
0x18000aa5e  jmp     loc_18000B01E
0x18000aa63  xor     edx, edx; Val
0x18000aa65  lea     rcx, [rbp+430h+pszDest]; void *
0x18000aa69  mov     r8d, 208h; Size
0x18000aa6f  call    memset_0
0x18000aa74  lea     rcx, NonDAVServerListLock; lpCriticalSection
0x18000aa7b  call    cs:__imp_EnterCriticalSection
0x18000aa81  mov     rcx, rsi; String1
0x18000aa84  call    DavCheckTheNonDAVServerList
0x18000aa89  lea     rcx, NonDAVServerListLock; lpCriticalSection
0x18000aa90  mov     ebx, eax
0x18000aa92  call    cs:__imp_LeaveCriticalSection
0x18000aa98  test    ebx, ebx
0x18000aa9a  jz      short loc_18000AAD7
0x18000aa9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18000aaa3  lea     rax, WPP_GLOBAL_Control
0x18000aaaa  cmp     rcx, rax
0x18000aaad  jz      short loc_18000AACD
0x18000aaaf  test    byte ptr [rcx+1Ch], 2
0x18000aab3  jz      short loc_18000AACD
0x18000aab5  mov     rcx, [rcx+10h]
0x18000aab9  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000aac0  mov     edx, 94h
0x18000aac5  mov     r9, rsi
0x18000aac8  call    WPP_SF_S
0x18000aacd  xor     eax, eax
0x18000aacf  mov     [r14], r12b
0x18000aad2  jmp     loc_18000B01E
0x18000aad7  lea     rcx, ServerShareTableLock; lpCriticalSection
0x18000aade  call    cs:__imp_EnterCriticalSection
0x18000aae4  lea     rdx, [rsp+530h+FileHandle]
0x18000aae9  mov     rcx, rsi; String1
0x18000aaec  call    DavIsServerInServerShareTable
0x18000aaf1  mov     rdi, [rsp+530h+FileHandle]
0x18000aaf6  xor     ebx, ebx
0x18000aaf8  test    eax, eax
0x18000aafa  jz      short loc_18000AB49
0x18000aafc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab03  lea     rax, WPP_GLOBAL_Control
0x18000ab0a  cmp     rcx, rax
0x18000ab0d  jz      short loc_18000AB31
0x18000ab0f  test    byte ptr [rcx+1Ch], 2
0x18000ab13  jz      short loc_18000AB31
0x18000ab15  mov     rcx, [rcx+10h]
0x18000ab19  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000ab20  mov     edx, 95h
0x18000ab25  call    WPP_SF_
0x18000ab2a  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab31  cmp     [rdi+8], rbx
0x18000ab35  jz      short loc_18000AB50
0x18000ab37  mov     rcx, [rdi+8]; hMem
0x18000ab3b  mov     edx, 1
0x18000ab40  call    DavFinalizeFileAttributesList
0x18000ab45  mov     [rdi+8], rbx
0x18000ab49  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab50  test    r13d, r13d
0x18000ab53  jz      loc_18000AC0F
0x18000ab59  test    rdi, rdi
0x18000ab5c  jz      loc_18000AC0F
0x18000ab62  cmp     [rdi+8], rbx
0x18000ab66  jz      loc_18000AC0F
0x18000ab6c  lea     rax, WPP_GLOBAL_Control
0x18000ab73  cmp     rcx, rax
0x18000ab76  jz      short loc_18000ABA1
0x18000ab78  test    byte ptr [rcx+1Ch], 2
0x18000ab7c  jz      short loc_18000ABA1
0x18000ab7e  mov     rcx, [rcx+10h]
0x18000ab82  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000ab89  mov     edx, 96h
0x18000ab8e  call    WPP_SF_
0x18000ab93  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ab9a  lea     rax, WPP_GLOBAL_Control
0x18000aba1  mov     rbx, [rdi+8]
0x18000aba5  add     rbx, 40h ; '@'
0x18000aba9  cmp     rcx, rax
0x18000abac  jz      short loc_18000ABD4
0x18000abae  test    byte ptr [rcx+1Ch], 2
0x18000abb2  jz      short loc_18000ABD4
0x18000abb4  mov     r9, [rbx+20h]
0x18000abb8  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000abbf  mov     rcx, [rcx+10h]
0x18000abc3  mov     edx, 97h
0x18000abc8  call    WPP_SF_S
0x18000abcd  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abd4  cmp     [rbx+14h], r12b
0x18000abd8  jz      short loc_18000ABF6
0x18000abda  mov     rcx, [rbx+20h]; String1
0x18000abde  mov     rdx, r15; String2
0x18000abe1  call    cs:__imp__wcsicmp
0x18000abe7  test    eax, eax
0x18000abe9  jz      loc_18000ACDD
0x18000abef  mov     rcx, cs:WPP_GLOBAL_Control
0x18000abf6  mov     rax, [rdi+8]
0x18000abfa  mov     rbx, [rbx]
0x18000abfd  add     rax, 40h ; '@'
0x18000ac01  cmp     rbx, rax
0x18000ac04  lea     rax, WPP_GLOBAL_Control
0x18000ac0b  jnz     short loc_18000ABA9
0x18000ac0d  xor     ebx, ebx
0x18000ac0f  lea     rcx, ServerShareTableLock; lpCriticalSection
0x18000ac16  mov     [r14], r12b
0x18000ac19  call    cs:__imp_LeaveCriticalSection
0x18000ac1f  cmp     [r14], r12b
0x18000ac22  jnz     loc_18000B01C
0x18000ac28  mov     rcx, cs:WPP_GLOBAL_Control
0x18000ac2f  lea     rax, WPP_GLOBAL_Control
0x18000ac36  cmp     rcx, rax
0x18000ac39  jz      short loc_18000AC56
0x18000ac3b  test    byte ptr [rcx+1Ch], 2
0x18000ac3f  jz      short loc_18000AC56
0x18000ac41  mov     rcx, [rcx+10h]
0x18000ac45  lea     r8, WPP_213bafaee9dd3d0e10589223cbfc7563_Traceguids
0x18000ac4c  mov     edx, 99h
0x18000ac51  call    WPP_SF_
0x18000ac56  mov     rdi, [rbp+430h+pszSrc]
0x18000ac5a  test    rdi, rdi
0x18000ac5d  jz      loc_18000AD8E
0x18000ac63  movzx   eax, [rbp+430h+arg_20]
0x18000ac6a  mov     ecx, 40h ; '@'; uFlags
0x18000ac6f  add     ax, ax
0x18000ac72  movzx   ebx, ax
  ... truncated ...
```
