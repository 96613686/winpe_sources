# DavFsClose

- ea: `0x18001f190`
- end: `0x1800203de`
- name: `DavFsClose`
- size: `4686`
- prototype: `__int64 __fastcall(__int64, _UNKNOWN **, __int64)`
- caller_count: `1`
- callee_count: `24`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001f190`

## callees

- `0x18000b7b4`
- `0x18000b7dc`
- `0x18000b81c`
- `0x18000b93c`
- `0x18000bc5c`
- `0x18000bfe0`
- `0x18000d9e4`
- `0x180010478`
- `0x180010770`
- `0x180010ffc`
- `0x180011360`
- `0x180013c08`
- `0x18001befc`
- `0x18001f190`
- `0x1800203e4`
- `0x18002097c`
- `0x180021008`
- `0x180021590`
- `0x1800297e4`
- `0x180029bec`
- `0x18002ae00`
- `0x18002be24`
- `0x18002c6d0`
- `0x18002cfa0`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x180020213`
- `ntdll!RtlFreeHeap` at `0x180020213`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001f7c6`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x18001f7c6`
- `ntdll!NtCreateFile` at `0x18001f86e`
- `ntdll!NtCreateFile` at `0x18001f86e`
- `ntdll!RtlNtStatusToDosError` at `0x18001f880`
- `ntdll!RtlNtStatusToDosError` at `0x18001f880`
- `ntdll!NtClose` at `0x180020354`
- `ntdll!NtClose` at `0x180020354`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002024c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002029e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f34f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f682`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f967`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fc7e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fcf0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fd76`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fe74`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001feed`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002024c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002029e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800202f0`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001f95d`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18001f95d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f345`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001f345`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f52b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200f7`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f52b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001fdb8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800200f7`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd49`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4c0`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001fd49`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f8e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fb5a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020121`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002021e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001f8e2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18001fb5a`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180020121`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18002021e`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001f4b0`
- `DAVHLPR!DavRemoveDummyShareFromFileName` at `0x18001f4b0`
- `KERNEL32!LocalFree` at `0x180020293`
- `KERNEL32!LocalFree` at `0x1800202e5`
- `KERNEL32!LocalFree` at `0x180020293`
- `KERNEL32!LocalFree` at `0x1800202e5`
- `KERNEL32!LocalAlloc` at `0x18001f670`
- `KERNEL32!LocalAlloc` at `0x18001f670`
- `ADVAPI32!ReadEncryptedFileRaw` at `0x18001fb18`
- `ADVAPI32!ReadEncryptedFileRaw` at `0x18001fb18`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x180020337`
- `ADVAPI32!CloseEncryptedFileRaw` at `0x180020337`
- `ADVAPI32!OpenEncryptedFileRawW` at `0x18001fab5`
- `ADVAPI32!OpenEncryptedFileRawW` at `0x18001fab5`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001fd6c`
- `WINHTTP!WinHttpAddRequestHeaders` at `0x18001fd6c`
- `WINHTTP!WinHttpSetOption` at `0x18001fce2`
- `WINHTTP!WinHttpSetOption` at `0x18001fee3`
- `WINHTTP!WinHttpSetOption` at `0x18001fce2`
- `WINHTTP!WinHttpSetOption` at `0x18001fee3`
- `WINHTTP!WinHttpCloseHandle` at `0x180020242`
- `WINHTTP!WinHttpCloseHandle` at `0x1800203b6`
- `WINHTTP!WinHttpCloseHandle` at `0x180020242`
- `WINHTTP!WinHttpCloseHandle` at `0x1800203b6`

## string_xrefs

- `0x18001fb8f`: `DELETE`

## pseudocode

```c
__int64 __fastcall DavFsClose(__int64 a1, _UNKNOWN **a2, __int64 a3)
{
  __int64 v3; // r13
  unsigned int v4; // r15d
  int v6; // r12d
  __int64 v7; // rcx
  DWORD v8; // ebx
  FILETIME *v9; // r14
  int v10; // r15d
  __int64 v11; // r9
  DWORD LastError; // eax
  WCHAR *v13; // rbx
  __int64 v14; // rdx
  unsigned int v15; // edi
  __int64 v16; // r14
  bool v17; // zf
  __int64 v18; // r14
  __int64 *v19; // rax
  __int64 v20; // rdi
  int v21; // eax
  char v22; // al
  int v23; // eax
  char *v24; // rax
  DWORD v25; // eax
  const wchar_t *v26; // r14
  __int64 v27; // rdx
  __int64 v28; // r9
  NTSTATUS v29; // eax
  unsigned int v30; // edi
  DWORD EncryptedFileRaw; // eax
  DWORD v32; // eax
  _QWORD *v33; // rcx
  PVOID v34; // r8
  void *v35; // rbx
  DWORD v36; // eax
  DWORD v37; // eax
  const WCHAR *v38; // rdx
  DWORD v39; // eax
  unsigned int v40; // eax
  HINTERNET v41; // rbx
  DWORD v42; // eax
  __int64 v43; // rdx
  DWORD v44; // eax
  int v45; // edx
  unsigned int v46; // eax
  unsigned int v47; // ebx
  unsigned int v48; // eax
  __int64 v49; // rdx
  unsigned int v50; // eax
  unsigned int v51; // eax
  int v52; // eax
  void *v53; // rcx
  DWORD v54; // eax
  void *v55; // rcx
  DWORD v56; // eax
  void *v57; // rcx
  DWORD v58; // eax
  void *v59; // rcx
  void *v60; // rcx
  DWORD v61; // eax
  int AllocationSize; // [rsp+20h] [rbp-E0h]
  int FileAttributes; // [rsp+28h] [rbp-D8h]
  int ShareAccess; // [rsp+30h] [rbp-D0h]
  int ShareAccessa; // [rsp+30h] [rbp-D0h]
  __int64 v67; // [rsp+70h] [rbp-90h]
  __int64 v68; // [rsp+78h] [rbp-88h]
  int Buffer; // [rsp+80h] [rbp-80h] BYREF
  PVOID pvContext; // [rsp+88h] [rbp-78h] BYREF
  int v71; // [rsp+90h] [rbp-70h]
  void *FileHandle; // [rsp+98h] [rbp-68h] BYREF
  int v73[2]; // [rsp+A0h] [rbp-60h]
  HINTERNET hInternet; // [rsp+A8h] [rbp-58h]
  __int64 v75; // [rsp+B0h] [rbp-50h]
  HINTERNET v76; // [rsp+B8h] [rbp-48h]
  struct _UNICODE_STRING NtPathName; // [rsp+C0h] [rbp-40h] BYREF
  __int64 *v78; // [rsp+D0h] [rbp-30h] BYREF
  HINTERNET v79; // [rsp+D8h] [rbp-28h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+E0h] [rbp-20h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+110h] [rbp+10h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+120h] [rbp+20h] BYREF

  *(_QWORD *)v73 = 0;
  v3 = 0;
  v79 = 0;
  v4 = 0;
  v78 = 0;
  v71 = 0;
  pvContext = 0;
  v6 = 0;
  memset(&FileInformation, 0, sizeof(FileInformation));
  FileHandle = 0;
  v75 = 0;
  Buffer = 0;
  IoStatusBlock = 0;
  v76 = 0;
  NtPathName = 0;
  hInternet = 0;
  memset(&ObjectAttributes, 0, 44);
  v7 = (__int64)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, a1 + 752);
      v7 = (__int64)WPP_GLOBAL_Control;
    }
    if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(v7 + 16), 11, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, *(unsigned int *)(a1 + 692));
      v7 = (__int64)WPP_GLOBAL_Control;
    }
  }
  NtPathName.Buffer = 0;
  *(_DWORD *)&NtPathName.Length = 0;
  if ( !*(_DWORD *)(a1 + 688)
    && (*(_BYTE *)(a1 + 708) || *(_BYTE *)(a1 + 709) || *(_BYTE *)(a1 + 710) || *(_BYTE *)(a1 + 711)) )
  {
    v4 = 1;
    v71 = 1;
  }
  if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(v7 + 16), 12, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v4);
    v7 = (__int64)WPP_GLOBAL_Control;
  }
  if ( !*(_DWORD *)(a1 + 704) )
  {
    v8 = 0;
    if ( !*(_DWORD *)(a1 + 700) )
    {
      v11 = *(_QWORD *)(a1 + 632);
      if ( v11 )
      {
        if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
          WPP_SF_q(*(_QWORD *)(v7 + 16), 13, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v11);
        if ( CloseHandle(*(HANDLE *)(a1 + 632)) )
        {
          *(_QWORD *)(a1 + 640) = 0;
          *(_QWORD *)(a1 + 632) = 0;
          goto LABEL_30;
        }
        LastError = GetLastError();
        v8 = LastError;
        v7 = (__int64)WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, LastError);
LABEL_30:
          v7 = (__int64)WPP_GLOBAL_Control;
        }
      }
    }
    if ( !*(_DWORD *)(a1 + 688) && !*(_DWORD *)(a1 + 692) && !v4 && !*(_QWORD *)(a1 + 680) )
    {
      v10 = 0;
      goto LABEL_95;
    }
LABEL_35:
    v13 = (WCHAR *)(*(_QWORD *)(a1 + 656) + 2LL);
    if ( *(_QWORD *)(a1 + 656) == -2 )
    {
      if ( (_UNKNOWN **)v7 == &WPP_GLOBAL_Control || (*(_BYTE *)(v7 + 28) & 1) == 0 )
        goto LABEL_40;
      v14 = 15;
      goto LABEL_39;
    }
    if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
    {
      WPP_SF_S(*(_QWORD *)(v7 + 16), 16, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v13);
      v7 = (__int64)WPP_GLOBAL_Control;
    }
    v15 = *(_DWORD *)(a1 + 664);
    a2 = &WPP_GLOBAL_Control;
    if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
    {
      WPP_SF_d(*(_QWORD *)(v7 + 16), 17, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v15);
      v7 = (__int64)WPP_GLOBAL_Control;
      a2 = &WPP_GLOBAL_Control;
    }
    v16 = *(_QWORD *)(a1 + 672);
    v17 = v16 == -2;
    v18 = v16 + 2;
    v67 = v18;
    if ( v17 )
    {
      if ( (_UNKNOWN **)v7 == &WPP_GLOBAL_Control || (*(_BYTE *)(v7 + 28) & 1) == 0 )
        goto LABEL_40;
      v14 = 18;
LABEL_39:
      WPP_SF_(*(_QWORD *)(v7 + 16), v14, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
LABEL_40:
      v8 = 87;
      goto LABEL_208;
    }
    if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
      WPP_SF_S(*(_QWORD *)(v7 + 16), 19, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v18);
    v75 = a1;
    DavRemoveDummyShareFromFileName(v18, a2);
    EnterCriticalSection(&HashServerEntryTableLock);
    if ( !(unsigned int)DavDoesUserEntryExist(v13, v15, (_DWORD *)(a1 + 648), &v78, (__int64 **)&pvContext)
      || !pvContext
      || (v19 = v78) == 0 )
    {
      v8 = 1223;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
      LeaveCriticalSection(&HashServerEntryTableLock);
      goto LABEL_208;
    }
    *(_QWORD *)(a1 + 504) = pvContext;
    *(_QWORD *)(a1 + 496) = v19;
    ++*((_DWORD *)v19 + 16);
    v20 = v19[4];
    v68 = v19[5];
    *(_QWORD *)v73 = v20;
    LeaveCriticalSection(&HashServerEntryTableLock);
    v7 = 4;
    v21 = *(_DWORD *)(a1 + 688);
    if ( *(_DWORD *)(a1 + 704) )
    {
      if ( !v21 )
      {
        LODWORD(v26) = 0;
        if ( !v4 )
          goto LABEL_138;
        goto LABEL_134;
      }
    }
    else if ( !v21 )
    {
      if ( *(_DWORD *)(a1 + 692) )
      {
        if ( !v4 || !*(_DWORD *)(*(_QWORD *)(a1 + 504) + 40LL) || *(_DWORD *)(a1 + 572) )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
          *(_DWORD *)(a1 + 572) = 0;
LABEL_81:
          *(_DWORD *)(a1 + 56) = 5;
          *(_QWORD *)(a1 + 552) = 0;
          v26 = L"PUT";
          *(_QWORD *)(a1 + 560) = 0;
          *(_DWORD *)(a1 + 520) = 0;
          if ( (*(_DWORD *)(a1 + 744) & 0x4000) != 0 )
          {
            pvContext = 0;
            v33 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
            {
              if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 29, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
                v33 = WPP_GLOBAL_Control;
              }
              if ( v33 != &WPP_GLOBAL_Control && (*((_BYTE *)v33 + 28) & 2) != 0 )
                WPP_SF_S(v33[2], 30, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, a1 + 752);
            }
            *(_DWORD *)(a1 + 568) = 1;
            EncryptedFileRaw = DavSetAclForEncryptedFile((LPCWSTR)(a1 + 752));
            v8 = EncryptedFileRaw;
            if ( EncryptedFileRaw )
            {
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v27 = 31;
                goto LABEL_103;
              }
LABEL_208:
              if ( *(_DWORD *)(a1 + 572) )
                goto LABEL_230;
              goto LABEL_209;
            }
            EncryptedFileRaw = UMReflectorImpersonate(a1, *(void **)(a1 + 72));
            v8 = EncryptedFileRaw;
            if ( EncryptedFileRaw )
            {
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v27 = 32;
                goto LABEL_103;
              }
              goto LABEL_208;
            }
            v6 = 1;
            v8 = OpenEncryptedFileRawW((LPCWSTR)(a1 + 752), 0, &pvContext);
            if ( v8 )
            {
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_dS(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  33,
                  (unsigned int)WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
                  v8,
                  a1 + 752);
              }
              goto LABEL_208;
            }
            v34 = pvContext;
            *(_DWORD *)(a1 + 520) = 0;
            EncryptedFileRaw = ReadEncryptedFileRaw(DavCalculateSizeRawCallback, (PVOID)a1, v34);
            v8 = EncryptedFileRaw;
            if ( EncryptedFileRaw )
            {
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v27 = 34;
                goto LABEL_103;
              }
              goto LABEL_208;
            }
            *(_QWORD *)(a1 + 560) = pvContext;
            RevertToSelf();
          }
          else
          {
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
            *(_DWORD *)(a1 + 568) = 0;
            if ( !RtlDosPathNameToNtPathName_U((PCWSTR)(a1 + 752), &NtPathName, 0, 0) )
            {
              v8 = 161;
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                v27 = 25;
                v28 = 161;
LABEL_89:
                WPP_SF_d(*(_QWORD *)(v7 + 16), v27, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v28);
                goto LABEL_208;
              }
              goto LABEL_208;
            }
            ObjectAttributes.Length = 48;
            ObjectAttributes.RootDirectory = 0;
            ObjectAttributes.Attributes = 64;
            ObjectAttributes.ObjectName = &NtPathName;
            *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
            v29 = NtCreateFile(&FileHandle, 0x100081u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 3u, 1u, 0x60u, 0, 0);
            v30 = v29;
            if ( v29 )
            {
              v8 = RtlNtStatusToDosError(v29);
              FileHandle = 0;
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v30);
              }
              v3 = v67;
              v10 = v68;
              goto LABEL_95;
            }
            if ( !GetFileInformationByHandle(FileHandle, &FileInformation) )
            {
              v32 = GetLastError();
              v8 = v32;
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v32);
              }
              goto LABEL_75;
            }
            *(_QWORD *)(a1 + 552) = FileHandle;
            *(_DWORD *)(a1 + 520) = FileInformation.nFileSizeLow;
          }
          LODWORD(v20) = v73[0];
LABEL_138:
          EncryptedFileRaw = UMReflectorImpersonate(a1, *(void **)(a1 + 72));
          v8 = EncryptedFileRaw;
          if ( EncryptedFileRaw )
          {
            v7 = (__int64)WPP_GLOBAL_Control;
            v6 = 0;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              v27 = 35;
              goto LABEL_103;
            }
            goto LABEL_208;
          }
          *(_DWORD *)(a1 + 52) = 1;
          v6 = 1;
          if ( *(_DWORD *)(a1 + 704) || *(_DWORD *)(a1 + 688) || !*(_DWORD *)(a1 + 692) )
          {
            v10 = v68;
          }
          else
          {
            v10 = v68;
            if ( !(unsigned int)DavHttpOpenRequestW(
                                  v20,
                                  v68,
                                  (unsigned int)L"HEAD",
                                  v67,
                                  AllocationSize,
                                  FileAttributes,
                                  ShareAccess,
                                  0) )
            {
              v8 = GetLastError();
              v76 = hInternet;
LABEL_147:
              v3 = v67;
              goto LABEL_95;
            }
            v35 = hInternet;
            v76 = hInternet;
            if ( !hInternet )
            {
              v36 = GetLastError();
              v8 = v36;
              if ( v36 == 997 )
                goto LABEL_147;
              v7 = (__int64)WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v36);
              }
              v3 = v67;
LABEL_95:
              if ( v8 )
                goto LABEL_208;
LABEL_96:
              v9 = (FILETIME *)(a1 + 728);
              if ( v6 )
              {
                RevertToSelf();
                v6 = 0;
              }
              goto LABEL_98;
            }
            if ( g_DisableCookies )
            {
              if ( !WinHttpSetOption(hInternet, 0x3Fu, &Buffer, 4u) )
              {
                v37 = GetLastError();
                if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                {
                  WPP_SF_d(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    37,
                    WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
                    v37);
                }
              }
            }
            else if ( *(_DWORD *)(a1 + 48) != 4 )
            {
              EnterCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 496) + 120LL));
              v38 = *(const WCHAR **)(*(_QWORD *)(a1 + 496) + 112LL);
              if ( v38 )
              {
                if ( !WinHttpAddRequestHeaders(v35, v38, 0xFFFFFFFF, 0xA0000000) )
                {
                  v39 = GetLastError();
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      38,
                      WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
                      v39);
                  }
                }
              }
              LeaveCriticalSection((LPCRITICAL_SECTION)(*(_QWORD *)(a1 + 496) + 120LL));
            }
            v40 = DavSendRequest(v35, 0, 0, ShareAccessa, a1);
            if ( v40
              && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v40);
            }
          }
          v3 = v67;
          if ( !(unsigned int)DavHttpOpenRequestW(
                                v20,
                                v10,
                                (_DWORD)v26,
                                v67,
                                AllocationSize,
                                FileAttributes,
                                ShareAccess,
                                0) )
          {
            v8 = GetLastError();
            goto LABEL_95;
          }
          v41 = v79;
          if ( v79 )
          {
            Buffer = 1;
            if ( !g_DisableCookies || WinHttpSetOption(v79, 0x3Fu, &Buffer, 4u) )
            {
              *(_QWORD *)(a1 + 544) = v41;
              v44 = DavAsyncCommonStates((unsigned int *)a1);
              v8 = v44;
              if ( v44 )
              {
                if ( v44 != 997 )
                {
                  v7 = (__int64)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
                  {
                    WPP_SF_d(
                      *((_QWORD *)WPP_GLOBAL_Control + 2),
                      42,
                      WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
                      v44);
                  }
                }
                goto LABEL_208;
              }
              goto LABEL_96;
            }
            v42 = GetLastError();
            v8 = v42;
            v7 = (__int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_95;
            v43 = 41;
          }
          else
          {
            v42 = GetLastError();
            v8 = v42;
            if ( v42 == 997 )
              goto LABEL_95;
            v7 = (__int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
              goto LABEL_95;
            v43 = 40;
          }
          WPP_SF_d(*(_QWORD *)(v7 + 16), v43, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v42);
          goto LABEL_95;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids);
        v22 = *(_BYTE *)(a1 + 711);
        if ( v22 == 1 )
        {
          v23 = *(_DWORD *)(a1 + 744);
          if ( (v23 & 0x7137) != 0 )
            *(_DWORD *)(a1 + 744) = v23 & 0xFFFFFF7F;
        }
        else if ( !v22 )
        {
LABEL_71:
          *(_DWORD *)(a1 + 572) = 1;
          *(_DWORD *)(a1 + 536) = 0;
          *(_QWORD *)(a1 + 528) = 0;
          DavGetProppatchBuffer(
            *(unsigned __int8 *)(a1 + 708),
            *(unsigned __int8 *)(a1 + 709),
            *(unsigned __int8 *)(a1 + 710),
            *(unsigned __int8 *)(a1 + 711),
            (FILETIME *)(a1 + 712),
            (FILETIME *)(a1 + 720),
            (FILETIME *)(a1 + 728),
            *(_DWORD *)(a1 + 744),
            0,
            a1 + 536);
          v24 = (char *)LocalAlloc(0x40u, *(unsigned int *)(a1 + 536) + 32LL);
          *(_QWORD *)(a1 + 528) = v24;
          if ( !v24 )
          {
            v25 = GetLastError();
            v8 = v25;
            v7 = (__int64)WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v25);
LABEL_75:
            v3 = v67;
            v10 = v68;
            goto LABEL_95;
          }
          DavGetProppatchBuffer(
            *(unsigned __int8 *)(a1 + 708),
            *(unsigned __int8 *)(a1 + 709),
            *(unsigned __int8 *)(a1 + 710),
            *(unsigned __int8 *)(a1 + 711),
            (FILETIME *)(a1 + 712),
            (FILETIME *)(a1 + 720),
            (FILETIME *)(a1 + 728),
            *(_DWORD *)(a1 + 744),
            v24 + 16,
            a1 + 536);
          goto LABEL_81;
        }
        v7 = 272;
        if ( (*(_DWORD *)(a1 + 744) & 0x110) == 0x110 )
          goto LABEL_40;
        goto LABEL_71;
      }
LABEL_134:
      v3 = v67;
      v9 = (FILETIME *)(a1 + 728);
      v10 = v68;
      v8 = 0;
      goto LABEL_98;
    }
    *(_DWORD *)(a1 + 56) = 4;
    *(_DWORD *)(a1 + 520) = 0;
    v26 = L"DELETE";
    goto LABEL_138;
  }
  if ( *(_DWORD *)(a1 + 688) || v4 )
    goto LABEL_35;
  v8 = 0;
  v9 = (FILETIME *)(a1 + 728);
  v10 = 0;
LABEL_98:
  ((void (__fastcall *)(_QWORD, _QWORD, _QWORD))TfsSetEntryModifiedTime)(v7, a1 + 1272, *v9);
  if ( v71 )
  {
    EncryptedFileRaw = UMReflectorImpersonate(v75, *(void **)(a1 + 72));
    v8 = EncryptedFileRaw;
    if ( EncryptedFileRaw )
    {
      v7 = (__int64)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v27 = 43;
LABEL_103:
        v28 = EncryptedFileRaw;
        goto LABEL_89;
      }
      goto LABEL_208;
    }
    v6 = 1;
    if ( !*(_DWORD *)(a1 + 572) )
    {
      v45 = v73[0];
      *(_DWORD *)(a1 + 56) = 6;
      v46 = DavSetBasicInformation(
              a1,
              v45,
              v10,
              v3,
              *(unsigned __int8 *)(a1 + 708),
              *(unsigned __int8 *)(a1 + 709),
              *(unsigned __int8 *)(a1 + 710),
              *(unsigned __int8 *)(a1 + 711),
              (FILETIME *)(a1 + 712),
              (FILETIME *)(a1 + 720),
              v9,
              *(_DWORD *)(a1 + 744));
      v47 = v46;
      if ( v46 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v46);
        v48 = DavFormatAndLogError(a1, v47);
        if ( v48 )
        {
          v7 = (__int64)WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          {
LABEL_203:
            v8 = 0;
            goto LABEL_209;
          }
          if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          {
LABEL_200:
            if ( (_UNKNOWN **)v7 != &WPP_GLOBAL_Control && (*(_BYTE *)(v7 + 28) & 2) != 0 )
              WPP_SF_dDS(
                *(_QWORD *)(v7 + 16),
                46,
                (unsigned int)WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids,
                v47,
                *(_DWORD *)(a1 + 744),
                v3);
            goto LABEL_203;
          }
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v48);
        }
      }
      v7 = (__int64)WPP_GLOBAL_Control;
      goto LABEL_200;
    }
  }
LABEL_209:
  if ( !*(_DWORD *)(a1 + 704) && *(_DWORD *)(a1 + 696) )
  {
    if ( v6 )
    {
      RevertToSelf();
      v6 = 0;
    }
    v49 = a1 + 1272;
    if ( (*(_DWORD *)(a1 + 744) & 0x4000) != 0 )
      TfsDeleteEntry(v7, v49);
    else
      TfsReleaseEntry(v7, v49);
  }
  if ( !*(_DWORD *)(a1 + 572) && *(_QWORD *)(a1 + 680) && !*(_DWORD *)(a1 + 688) && *(_QWORD *)(a1 + 496) )
  {
    if ( !v6 )
    {
      v50 = UMReflectorImpersonate(v75, *(void **)(a1 + 72));
      if ( v50 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 47, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v50);
      }
      else
      {
        v6 = 1;
      }
    }
    v51 = DavUnLockTheFileOnTheServer(a1);
    if ( v51 && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 48, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v51);
  }
LABEL_230:
  if ( NtPathName.Buffer )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, NtPathName.Buffer);
  if ( v6 )
    RevertToSelf();
  if ( v8 )
    v52 = DavMapErrorToNtStatus(v8);
  else
    v52 = 0;
  *(_DWORD *)(a1 + 32) = v52;
  v53 = *(void **)(a1 + 544);
  if ( v53 )
  {
    if ( !WinHttpCloseHandle(v53) )
    {
      v54 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v54);
    }
    *(_QWORD *)(a1 + 544) = 0;
  }
  v55 = *(void **)(a1 + 512);
  if ( v55 )
  {
    if ( LocalFree(v55) )
    {
      v56 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v56);
    }
    *(_QWORD *)(a1 + 512) = 0;
  }
  v57 = *(void **)(a1 + 528);
  if ( v57 )
  {
    if ( LocalFree(v57) )
    {
      v58 = GetLastError();
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids, v58);
    }
    *(_QWORD *)(a1 + 528) = 0;
  }
  v59 = *(void **)(a1 + 560);
  if ( v59 )
  {
    CloseEncryptedFileRaw(v59);
    *(_QWORD *)(a1 + 560) = 0;
  }
  v60 = *(void **)(a1 + 552);
  if ( v60 )
  {
    NtClose(v60);
    *(_QWORD *)(a1 + 552) = 0;
  }
  if ( !*(_DWORD *)(a1 + 32) || !*(_DWORD *)(a1 + 572) )
    DavFsFinalizeTheDavCallBackContext(a1);
  if ( *(_QWORD *)(a1 + 496) )
    DavFinalizePerUserEntry((unsigned int **)(a1 + 496), (__int64)a2, a3);
  if ( *(_DWORD *)(a1 + 32) )
  {
    if ( *(_DWORD *)(a1 + 572) )
    {
      v61 = DavFsClose(a1);
      if ( v61 )
        v8 = v61;
    }
  }
  if ( v76 )
    WinHttpCloseHandle(v76);
  return v8;
}

```

## disassembly

```asm
0x18001f190  push    rbp
0x18001f192  push    rbx
0x18001f193  push    rsi
0x18001f194  push    rdi
0x18001f195  push    r12
0x18001f197  push    r13
0x18001f199  push    r14
0x18001f19b  push    r15
0x18001f19d  lea     rbp, [rsp-68h]
0x18001f1a2  sub     rsp, 168h
0x18001f1a9  mov     rax, cs:__security_cookie
0x18001f1b0  xor     rax, rsp
0x18001f1b3  mov     [rbp+0A0h+var_48], rax
0x18001f1b7  xorps   xmm0, xmm0
0x18001f1ba  xor     edi, edi
0x18001f1bc  xor     eax, eax
0x18001f1be  mov     qword ptr [rbp+0A0h+var_100], rdi
0x18001f1c2  xor     r13d, r13d
0x18001f1c5  mov     [rbp+0A0h+var_C8], rdi
0x18001f1c9  xor     r15d, r15d
0x18001f1cc  mov     [rbp+0A0h+var_D0], r13
0x18001f1d0  xorps   xmm1, xmm1
0x18001f1d3  mov     [rbp+0A0h+var_110], r15d
0x18001f1d7  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.ObjectName], xmm0
0x18001f1db  mov     rsi, rcx
0x18001f1de  mov     [rbp+0A0h+pvContext], r13
0x18001f1e2  movups  xmmword ptr [rbp+0A0h+ObjectAttributes+1Ch], xmm0
0x18001f1e6  mov     [rbp+0A0h+FileInformation.nFileIndexLow], eax
0x18001f1e9  xor     r12d, r12d
0x18001f1ec  movups  xmmword ptr [rbp+0A0h+FileInformation.dwFileAttributes], xmm0
0x18001f1f0  mov     [rbp+0A0h+FileHandle], rax
0x18001f1f4  movups  xmmword ptr [rbp+0A0h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18001f1f8  mov     [rbp+0A0h+var_F0], rax
0x18001f1fc  movups  xmmword ptr [rbp+0A0h+FileInformation.nFileSizeHigh], xmm0
0x18001f200  mov     [rbp+0A0h+Buffer], eax
0x18001f203  movups  xmmword ptr [rbp+0A0h+IoStatusBlock], xmm0
0x18001f207  mov     [rbp+0A0h+var_E8], rdi
0x18001f20b  movups  xmmword ptr [rbp+0A0h+NtPathName.Length], xmm1
0x18001f20f  mov     [rbp+0A0h+hInternet], rdi
0x18001f213  movups  xmmword ptr [rbp+0A0h+ObjectAttributes.Length], xmm0
0x18001f217  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f21e  lea     rdi, WPP_GLOBAL_Control
0x18001f225  lea     r14, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18001f22c  mov     bl, 2
0x18001f22e  cmp     rcx, rdi
0x18001f231  jz      short loc_18001F27E
0x18001f233  test    [rcx+1Ch], bl
0x18001f236  jz      short loc_18001F255
0x18001f238  mov     rcx, [rcx+10h]
0x18001f23c  lea     r9, [rsi+2F0h]
0x18001f243  lea     edx, [rax+0Ah]
0x18001f246  mov     r8, r14
0x18001f249  call    WPP_SF_S
0x18001f24e  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f255  cmp     rcx, rdi
0x18001f258  jz      short loc_18001F27E
0x18001f25a  test    [rcx+1Ch], bl
0x18001f25d  jz      short loc_18001F27E
0x18001f25f  mov     r9d, [rsi+2B4h]
0x18001f266  mov     edx, 0Bh
0x18001f26b  mov     rcx, [rcx+10h]
0x18001f26f  mov     r8, r14
0x18001f272  call    WPP_SF_d
0x18001f277  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f27e  xor     eax, eax
0x18001f280  mov     [rbp+0A0h+NtPathName.Buffer], r12
0x18001f284  mov     dword ptr [rbp+0A0h+NtPathName.Length], eax
0x18001f287  cmp     [rsi+2B0h], eax
0x18001f28d  jnz     short loc_18001F2B9
0x18001f28f  cmp     [rsi+2C4h], al
0x18001f295  jnz     short loc_18001F2AF
0x18001f297  cmp     [rsi+2C5h], al
0x18001f29d  jnz     short loc_18001F2AF
0x18001f29f  cmp     [rsi+2C6h], al
0x18001f2a5  jnz     short loc_18001F2AF
0x18001f2a7  cmp     [rsi+2C7h], al
0x18001f2ad  jz      short loc_18001F2B9
0x18001f2af  mov     r15d, 1
0x18001f2b5  mov     [rbp+0A0h+var_110], r15d
0x18001f2b9  cmp     rcx, rdi
0x18001f2bc  jz      short loc_18001F2DE
0x18001f2be  test    [rcx+1Ch], bl
0x18001f2c1  jz      short loc_18001F2DE
0x18001f2c3  mov     rcx, [rcx+10h]
0x18001f2c7  mov     edx, 0Ch
0x18001f2cc  mov     r9d, r15d
0x18001f2cf  mov     r8, r14
0x18001f2d2  call    WPP_SF_d
0x18001f2d7  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f2de  cmp     [rsi+2C0h], r12d
0x18001f2e5  jz      short loc_18001F30E
0x18001f2e7  cmp     [rsi+2B0h], r12d
0x18001f2ee  jnz     loc_18001F3B8
0x18001f2f4  test    r15d, r15d
0x18001f2f7  jnz     loc_18001F3B8
0x18001f2fd  xor     ebx, ebx
0x18001f2ff  lea     r14, [rsi+2D8h]
0x18001f306  mov     r15d, ebx
0x18001f309  jmp     loc_18001F8F2
0x18001f30e  xor     ebx, ebx
0x18001f310  cmp     [rsi+2BCh], ebx
0x18001f316  jnz     short loc_18001F394
0x18001f318  mov     r9, [rsi+278h]
0x18001f31f  test    r9, r9
0x18001f322  jz      short loc_18001F394
0x18001f324  cmp     rcx, rdi
0x18001f327  jz      short loc_18001F33E
0x18001f329  test    byte ptr [rcx+1Ch], 2
0x18001f32d  jz      short loc_18001F33E
0x18001f32f  mov     rcx, [rcx+10h]
0x18001f333  lea     edx, [rbx+0Dh]
0x18001f336  mov     r8, r14
0x18001f339  call    WPP_SF_q
0x18001f33e  mov     rcx, [rsi+278h]; hObject
0x18001f345  call    cs:__imp_CloseHandle
0x18001f34b  test    eax, eax
0x18001f34d  jnz     short loc_18001F37F
0x18001f34f  call    cs:__imp_GetLastError
0x18001f355  mov     ebx, eax
0x18001f357  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f35e  cmp     rcx, rdi
0x18001f361  jz      short loc_18001F394
0x18001f363  test    byte ptr [rcx+1Ch], 1
0x18001f367  jz      short loc_18001F394
0x18001f369  mov     rcx, [rcx+10h]
0x18001f36d  mov     edx, 0Eh
0x18001f372  mov     r9d, eax
0x18001f375  mov     r8, r14
0x18001f378  call    WPP_SF_d
0x18001f37d  jmp     short loc_18001F38D
0x18001f37f  mov     [rsi+280h], rbx
0x18001f386  mov     [rsi+278h], rbx
0x18001f38d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f394  cmp     [rsi+2B0h], r12d
0x18001f39b  jnz     short loc_18001F3B8
0x18001f39d  cmp     [rsi+2B4h], r12d
0x18001f3a4  jnz     short loc_18001F3B8
0x18001f3a6  test    r15d, r15d
0x18001f3a9  jnz     short loc_18001F3B8
0x18001f3ab  cmp     [rsi+2A8h], r12
0x18001f3b2  jz      loc_18001FF1D
0x18001f3b8  mov     rbx, [rsi+290h]
0x18001f3bf  add     rbx, 2
0x18001f3c3  jnz     short loc_18001F3E9
0x18001f3c5  cmp     rcx, rdi
0x18001f3c8  jz      short loc_18001F3DF
0x18001f3ca  test    byte ptr [rcx+1Ch], 1
0x18001f3ce  jz      short loc_18001F3DF
0x18001f3d0  lea     edx, [rbx+0Fh]
0x18001f3d3  mov     r8, r14
0x18001f3d6  mov     rcx, [rcx+10h]
0x18001f3da  call    WPP_SF_
0x18001f3df  mov     ebx, 57h ; 'W'
0x18001f3e4  jmp     loc_1800200FD
0x18001f3e9  cmp     rcx, rdi
0x18001f3ec  jz      short loc_18001F40F
0x18001f3ee  test    byte ptr [rcx+1Ch], 2
0x18001f3f2  jz      short loc_18001F40F
0x18001f3f4  mov     rcx, [rcx+10h]
0x18001f3f8  mov     edx, 10h
0x18001f3fd  mov     r9, rbx
0x18001f400  mov     r8, r14
0x18001f403  call    WPP_SF_S
0x18001f408  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f40f  mov     edi, [rsi+298h]
0x18001f415  lea     rdx, WPP_GLOBAL_Control
0x18001f41c  cmp     rcx, rdx
0x18001f41f  jz      short loc_18001F449
0x18001f421  test    byte ptr [rcx+1Ch], 2
0x18001f425  jz      short loc_18001F449
0x18001f427  mov     rcx, [rcx+10h]
0x18001f42b  mov     edx, 11h
0x18001f430  mov     r9d, edi
0x18001f433  mov     r8, r14
0x18001f436  call    WPP_SF_d
0x18001f43b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f442  lea     rdx, WPP_GLOBAL_Control
0x18001f449  mov     r14, [rsi+2A0h]
0x18001f450  add     r14, 2
0x18001f454  mov     [rsp+1A0h+var_130], r14
0x18001f459  jnz     short loc_18001F486
0x18001f45b  lea     rdi, WPP_GLOBAL_Control
0x18001f462  cmp     rcx, rdi
0x18001f465  jz      loc_18001F3DF
0x18001f46b  test    byte ptr [rcx+1Ch], 1
0x18001f46f  jz      loc_18001F3DF
0x18001f475  mov     edx, 12h
0x18001f47a  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18001f481  jmp     loc_18001F3D6
0x18001f486  cmp     rcx, rdx
0x18001f489  jz      short loc_18001F4A9
0x18001f48b  test    byte ptr [rcx+1Ch], 2
0x18001f48f  jz      short loc_18001F4A9
0x18001f491  mov     rcx, [rcx+10h]
0x18001f495  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18001f49c  mov     edx, 13h
0x18001f4a1  mov     r9, r14
0x18001f4a4  call    WPP_SF_S
0x18001f4a9  mov     rcx, r14
0x18001f4ac  mov     [rbp+0A0h+var_F0], rsi
0x18001f4b0  call    cs:__imp_DavRemoveDummyShareFromFileName
0x18001f4b6  lea     r14, HashServerEntryTableLock
0x18001f4bd  mov     rcx, r14; lpCriticalSection
0x18001f4c0  call    cs:__imp_EnterCriticalSection
0x18001f4c6  lea     rax, [rbp+0A0h+pvContext]
0x18001f4ca  mov     edx, edi
0x18001f4cc  lea     r8, [rsi+288h]
0x18001f4d3  mov     [rsp+1A0h+AllocationSize], rax; __int64
0x18001f4d8  lea     r9, [rbp+0A0h+var_D0]
0x18001f4dc  mov     rcx, rbx; hMem
0x18001f4df  call    DavDoesUserEntryExist
0x18001f4e4  test    eax, eax
0x18001f4e6  jz      loc_1800200C1
0x18001f4ec  mov     r13, [rbp+0A0h+pvContext]
0x18001f4f0  test    r13, r13
0x18001f4f3  jz      loc_1800200C1
0x18001f4f9  mov     rax, [rbp+0A0h+var_D0]
0x18001f4fd  test    rax, rax
0x18001f500  jz      loc_1800200C1
0x18001f506  mov     [rsi+1F8h], r13
0x18001f50d  mov     [rsi+1F0h], rax
0x18001f514  inc     dword ptr [rax+40h]
0x18001f517  mov     rcx, [rax+28h]
0x18001f51b  mov     rdi, [rax+20h]
0x18001f51f  mov     [rsp+1A0h+var_128], rcx
0x18001f524  mov     rcx, r14; lpCriticalSection
0x18001f527  mov     qword ptr [rbp+0A0h+var_100], rdi
0x18001f52b  call    cs:__imp_LeaveCriticalSection
0x18001f531  mov     ecx, 4
0x18001f536  mov     eax, [rsi+2B0h]
0x18001f53c  cmp     [rsi+2C0h], r12d
0x18001f543  jnz     loc_18001FB7E
0x18001f549  test    eax, eax
0x18001f54b  jnz     loc_18001FB82
0x18001f551  cmp     [rsi+2B4h], r12d
0x18001f558  jz      loc_18001FB66
0x18001f55e  test    r15d, r15d
0x18001f561  jz      loc_18001F71D
0x18001f567  mov     rax, [rsi+1F8h]
0x18001f56e  cmp     [rax+28h], r12d
0x18001f572  jz      loc_18001F71D
0x18001f578  cmp     [rsi+23Ch], r12d
0x18001f57f  jnz     loc_18001F71D
0x18001f585  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f58c  lea     rdi, WPP_GLOBAL_Control
0x18001f593  cmp     rcx, rdi
0x18001f596  jz      short loc_18001F5B3
0x18001f598  test    byte ptr [rcx+1Ch], 2
0x18001f59c  jz      short loc_18001F5B3
0x18001f59e  mov     rcx, [rcx+10h]
0x18001f5a2  lea     r8, WPP_d57e13e437c83ba07ee9c2320814043d_Traceguids
0x18001f5a9  mov     edx, 15h
0x18001f5ae  call    WPP_SF_
0x18001f5b3  mov     al, [rsi+2C7h]
0x18001f5b9  cmp     al, 1
0x18001f5bb  jnz     short loc_18001F5D6
0x18001f5bd  mov     eax, [rsi+2E8h]
0x18001f5c3  test    eax, 7137h
0x18001f5c8  jz      short loc_18001F5DA
0x18001f5ca  btr     eax, 7
0x18001f5ce  mov     [rsi+2E8h], eax
0x18001f5d4  jmp     short loc_18001F5DA
0x18001f5d6  test    al, al
0x18001f5d8  jz      short loc_18001F5EF
0x18001f5da  mov     eax, [rsi+2E8h]
0x18001f5e0  mov     ecx, 110h
0x18001f5e5  and     eax, ecx
0x18001f5e7  cmp     eax, ecx
0x18001f5e9  jz      loc_18001F3DF
0x18001f5ef  mov     dword ptr [rsi+23Ch], 1
0x18001f5f9  lea     rbx, [rsi+218h]
0x18001f600  mov     [rbx], r12d
0x18001f603  lea     rdi, [rsi+2D8h]
0x18001f60a  mov     [rsi+210h], r12
0x18001f611  lea     r14, [rsi+2D0h]
0x18001f618  mov     eax, [rsi+2E8h]
0x18001f61e  lea     r15, [rsi+2C8h]
0x18001f625  movzx   r9d, byte ptr [rsi+2C7h]; int
0x18001f62d  movzx   r8d, byte ptr [rsi+2C6h]; int
0x18001f635  movzx   edx, byte ptr [rsi+2C5h]; int
0x18001f63c  movzx   ecx, byte ptr [rsi+2C4h]; int
0x18001f643  mov     [rsp+1A0h+EaBuffer], rbx; __int64
0x18001f648  mov     qword ptr [rsp+1A0h+CreateOptions], r12; void *
0x18001f64d  mov     [rsp+1A0h+CreateDisposition], eax; int
0x18001f651  mov     qword ptr [rsp+1A0h+ShareAccess], rdi; FILETIME *
0x18001f656  mov     qword ptr [rsp+1A0h+FileAttributes], r14; FILETIME *
0x18001f65b  mov     [rsp+1A0h+AllocationSize], r15; FILETIME *
0x18001f660  call    DavGetProppatchBuffer
0x18001f665  mov     edx, [rbx]
0x18001f667  mov     ecx, 40h ; '@'; uFlags
0x18001f66c  add     rdx, 20h ; ' '; uBytes
0x18001f670  call    cs:__imp_LocalAlloc
0x18001f676  mov     [rsi+210h], rax
0x18001f67d  test    rax, rax
0x18001f680  jnz     short loc_18001F6CA
0x18001f682  call    cs:__imp_GetLastError
0x18001f688  mov     ebx, eax
0x18001f68a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001f691  lea     rdi, WPP_GLOBAL_Control
0x18001f698  cmp     rcx, rdi
  ... truncated ...
```
