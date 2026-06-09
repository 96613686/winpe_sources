# GetFileInfo(ushort const *,ulong *,ushort *,ulong,int *,int *)

- ea: `0x180009148`
- end: `0x1800095a6`
- name: `?GetFileInfo@@YAXPEBGPEAKPEAGKPEAH3@Z`
- size: `1118`
- prototype: `void __fastcall(const unsigned __int16 *, unsigned int *, unsigned __int16 *, __int64, int *, int *)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005b00`
- `0x18000a440`

## callees

- `0x180005610`
- `0x180009148`
- `0x180009600`
- `0x180009b58`
- `0x18000ca38`
- `0x18001d33a`
- `0x18001d370`

## import_xrefs

- `SHLWAPI!PathAddBackslashW` at `0x18000926e`
- `SHLWAPI!PathAddBackslashW` at `0x18000926e`
- `SHLWAPI!PathIsUNCW` at `0x1800092ce`
- `SHLWAPI!PathIsUNCW` at `0x1800092f4`
- `SHLWAPI!PathIsUNCW` at `0x180009368`
- `SHLWAPI!PathIsUNCW` at `0x180009400`
- `SHLWAPI!PathIsUNCW` at `0x1800092ce`
- `SHLWAPI!PathIsUNCW` at `0x1800092f4`
- `SHLWAPI!PathIsUNCW` at `0x180009368`
- `SHLWAPI!PathIsUNCW` at `0x180009400`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180009231`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180009260`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180009231`
- `SHLWAPI!PathRemoveFileSpecW` at `0x180009260`
- `SHLWAPI!PathIsRootW` at `0x180009248`
- `SHLWAPI!PathIsRootW` at `0x1800093dc`
- `SHLWAPI!PathIsRootW` at `0x180009248`
- `SHLWAPI!PathIsRootW` at `0x1800093dc`
- `SHLWAPI!PathRemoveBackslashW` at `0x180009256`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800092b2`
- `SHLWAPI!PathRemoveBackslashW` at `0x180009256`
- `SHLWAPI!PathRemoveBackslashW` at `0x1800092b2`
- `SHLWAPI!PathIsUNCServerShareW` at `0x180009375`
- `SHLWAPI!PathIsUNCServerShareW` at `0x180009375`
- `SHLWAPI!StrChrW` at `0x180009416`
- `SHLWAPI!StrChrW` at `0x180009416`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009239`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009239`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009576`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009568`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180009576`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800093ec`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800093ec`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000929a`
- `api-ms-win-core-file-l1-1-0!GetVolumeInformationW` at `0x18000929a`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180009223`
- `api-ms-win-core-file-l1-2-0!GetVolumeNameForVolumeMountPointW` at `0x180009223`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000951e`
- `api-ms-win-core-file-l2-1-0!GetFileInformationByHandleEx` at `0x18000951e`
- `KERNEL32!GetComputerNameW` at `0x180009458`
- `KERNEL32!GetComputerNameW` at `0x180009458`
- `ntdll!RtlFreeUnicodeString` at `0x180009555`
- `ntdll!RtlFreeUnicodeString` at `0x180009555`
- `ntdll!NtOpenFile` at `0x1800094fd`
- `ntdll!NtOpenFile` at `0x1800094fd`
- `ntdll!RtlNtStatusToDosError` at `0x180009505`
- `ntdll!RtlNtStatusToDosError` at `0x180009505`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800094ad`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x1800094ad`
- `ntdll!NtClose` at `0x18000954a`
- `ntdll!NtClose` at `0x18000954a`

## pseudocode

```c
void __fastcall GetFileInfo(
        const unsigned __int16 *a1,
        unsigned int *a2,
        unsigned __int16 *a3,
        __int64 a4,
        int *a5,
        int *a6)
{
  DWORD v8; // edi
  __int64 v9; // r15
  __int64 v10; // rcx
  HLOCAL v11; // r12
  const unsigned __int16 *v12; // r8
  WCHAR *v13; // rax
  __int64 v14; // rdx
  WCHAR *v15; // rcx
  int RemotePath; // eax
  WCHAR *v17; // rcx
  WCHAR *v18; // rax
  __int64 v19; // rdx
  WCHAR *v20; // rcx
  unsigned __int16 *v21; // r14
  PWSTR v22; // rax
  unsigned int v23; // eax
  NTSTATUS v24; // eax
  DWORD FileSystemFlags; // [rsp+40h] [rbp-C0h] BYREF
  DWORD nSize; // [rsp+44h] [rbp-BCh] BYREF
  HLOCAL v27; // [rsp+48h] [rbp-B8h] BYREF
  void *FileHandle; // [rsp+50h] [rbp-B0h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  LPWSTR lpBuffer; // [rsp+60h] [rbp-A0h]
  struct _UNICODE_STRING NtPathName; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-88h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+A8h] [rbp-58h] BYREF
  _BYTE FileInformation[4]; // [rsp+C0h] [rbp-40h] BYREF
  int v35; // [rsp+C4h] [rbp-3Ch]
  unsigned __int16 v36; // [rsp+C8h] [rbp-38h]
  unsigned __int16 v37; // [rsp+CAh] [rbp-36h]
  WCHAR szVolumeMountPoint[264]; // [rsp+140h] [rbp+40h] BYREF
  WCHAR pszPath[2]; // [rsp+350h] [rbp+250h] BYREF
  WCHAR pszStart[262]; // [rsp+354h] [rbp+254h] BYREF
  WCHAR szVolumeName[264]; // [rsp+560h] [rbp+460h] BYREF

  lpBuffer = a3;
  *a3 = 0;
  v8 = 260;
  if ( a5 )
    *a5 = 0;
  v9 = 2147483646;
  hMem = 0;
  v10 = 2147483646;
  v27 = 0;
  v11 = 0;
  FileSystemFlags = 0;
  v12 = a1;
  v13 = szVolumeMountPoint;
  v14 = 260;
  do
  {
    if ( !v10 )
      break;
    if ( !*v12 )
      break;
    *v13++ = *v12++;
    --v10;
    --v14;
  }
  while ( v14 );
  v15 = v13 - 1;
  if ( v14 )
    v15 = v13;
  *v15 = 0;
  if ( v14 )
  {
    if ( (*(_BYTE *)a2 & 1) == 0 || GetVolumeNameForVolumeMountPointW(szVolumeMountPoint, szVolumeName, 0x104u) )
      PathRemoveFileSpecW(szVolumeMountPoint);
    while ( 1 )
    {
      PathAddBackslashW(szVolumeMountPoint);
      if ( GetVolumeInformationW(szVolumeMountPoint, 0, 0, 0, 0, &FileSystemFlags, 0, 0) )
        break;
      if ( GetLastError() == 5 )
      {
        FileSystemFlags = 8;
        break;
      }
      if ( !PathIsRootW(szVolumeMountPoint) )
      {
        PathRemoveBackslashW(szVolumeMountPoint);
        if ( PathRemoveFileSpecW(szVolumeMountPoint) )
          continue;
      }
      break;
    }
    PathRemoveBackslashW(szVolumeMountPoint);
    StringCchCopyW(pszPath, 0x104u, szVolumeMountPoint);
  }
  else
  {
    pszPath[0] = 0;
  }
  if ( !PathIsUNCW(a1) && !(unsigned int)GetRemotePath(a1, (unsigned __int16 **)&hMem) )
    a1 = (const unsigned __int16 *)hMem;
  if ( !PathIsUNCW(pszPath) )
  {
    RemotePath = GetRemotePath(pszPath, (unsigned __int16 **)&v27);
    v11 = v27;
    if ( !RemotePath )
    {
      v17 = (WCHAR *)v27;
      v18 = pszPath;
      v19 = 260;
      do
      {
        if ( !v9 )
          break;
        if ( !*v17 )
          break;
        *v18++ = *v17++;
        --v9;
        --v19;
      }
      while ( v19 );
      v20 = v18 - 1;
      if ( v19 )
        v20 = v18;
      *v20 = 0;
    }
  }
  if ( a6 )
    *a6 = PathIsUNCW(a1);
  if ( PathIsUNCServerShareW(a1) )
  {
    if ( (unsigned int)IsShareRoot(a1) )
    {
      *a2 |= 2u;
      goto LABEL_40;
    }
  }
  else
  {
    if ( !PathIsRootW(a1) )
      goto LABEL_40;
    *a2 |= 2u;
    if ( GetDriveTypeW(a1) != 4 )
      goto LABEL_40;
  }
  if ( a5 )
    *a5 = 1;
LABEL_40:
  v21 = lpBuffer;
  if ( (FileSystemFlags & 8) != 0 )
  {
    *a2 |= 4u;
    if ( (unsigned int)IsDfsPath(pszPath, v21, 0x104u, 0, 0) )
    {
      if ( a6 )
        *a6 = 1;
    }
    else if ( PathIsUNCW(pszPath) )
    {
      v22 = StrChrW(pszStart, 0x5Cu);
      if ( v22 )
      {
        v23 = v22 - pszPath + 1;
        if ( v23 <= 0x104 )
          v8 = v23;
      }
      StringCchCopyW(v21, v8, pszPath);
    }
  }
  nSize = v8;
  if ( !*v21 )
    GetComputerNameW(v21, &nSize);
  FileHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  IoStatusBlock = 0;
  NtPathName = 0;
  memset_0(FileInformation, 0, 0x74u);
  *a2 |= 8u;
  if ( *a6 && RtlDosPathNameToNtPathName_U(a1, &NtPathName, 0, 0) )
  {
    ObjectAttributes.ObjectName = &NtPathName;
    ObjectAttributes.Length = 48;
    ObjectAttributes.RootDirectory = 0;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v24 = NtOpenFile(&FileHandle, 0x80u, &ObjectAttributes, &IoStatusBlock, 3u, 0);
    if ( !RtlNtStatusToDosError(v24) )
    {
      if ( GetFileInformationByHandleEx(FileHandle, FileRemoteProtocolInfo, FileInformation, 0x74u)
        && v35 == 0x20000
        && (v36 < 2u || v36 == 2 && v37 < 2u) )
      {
        *a2 &= ~8u;
      }
      NtClose(FileHandle);
    }
    RtlFreeUnicodeString(&NtPathName);
  }
  if ( hMem )
    LocalFree(hMem);
  if ( v11 )
    LocalFree(v11);
}

```

## disassembly

```asm
0x180009148  mov     [rsp-8+arg_18], rbx
0x18000914d  push    rbp
0x18000914e  push    rsi
0x18000914f  push    rdi
0x180009150  push    r12
0x180009152  push    r13
0x180009154  push    r14
0x180009156  push    r15
0x180009158  lea     rbp, [rsp-680h]
0x180009160  sub     rsp, 780h
0x180009167  mov     rax, cs:__security_cookie
0x18000916e  xor     rax, rsp
0x180009171  mov     [rbp+6B0h+var_40], rax
0x180009178  mov     r14, [rbp+6B0h+arg_20]
0x18000917f  xor     r10d, r10d
0x180009182  mov     r13, [rbp+6B0h+arg_28]
0x180009189  mov     rbx, rdx
0x18000918c  mov     [rsp+7B0h+lpBuffer], r8
0x180009191  mov     rsi, rcx
0x180009194  mov     [r8], r10w
0x180009198  mov     edi, 104h
0x18000919d  test    r14, r14
0x1800091a0  jz      short loc_1800091A5
0x1800091a2  mov     [r14], r10d
0x1800091a5  mov     r15d, 7FFFFFFEh
0x1800091ab  mov     [rsp+7B0h+hMem], r10
0x1800091b0  mov     ecx, r15d
0x1800091b3  mov     [rsp+7B0h+var_768], r10
0x1800091b8  mov     r12, r10
0x1800091bb  mov     [rsp+7B0h+FileSystemFlags], r10d
0x1800091c0  mov     r8, rsi
0x1800091c3  lea     rax, [rbp+6B0h+szVolumeMountPoint]
0x1800091c7  mov     rdx, rdi
0x1800091ca  mov     r11d, 2
0x1800091d0  test    rcx, rcx
0x1800091d3  jz      short loc_1800091F2
0x1800091d5  movzx   r9d, word ptr [r8]
0x1800091d9  test    r9w, r9w
0x1800091dd  jz      short loc_1800091F2
0x1800091df  mov     [rax], r9w
0x1800091e3  add     r8, r11
0x1800091e6  add     rax, r11
0x1800091e9  dec     rcx
0x1800091ec  sub     rdx, 1
0x1800091f0  jnz     short loc_1800091D0
0x1800091f2  test    rdx, rdx
0x1800091f5  lea     rcx, [rax-2]
0x1800091f9  cmovnz  rcx, rax
0x1800091fd  mov     [rcx], r10w
0x180009201  jnz     short loc_180009210
0x180009203  mov     [rbp+6B0h+pszPath], r10w
0x18000920b  jmp     loc_1800092CB
0x180009210  test    byte ptr [rbx], 1
0x180009213  jz      short loc_18000922D
0x180009215  mov     r8d, edi; cchBufferLength
0x180009218  lea     rdx, [rbp+6B0h+szVolumeName]; lpszVolumeName
0x18000921f  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; lpszVolumeMountPoint
0x180009223  call    cs:__imp_GetVolumeNameForVolumeMountPointW
0x180009229  test    eax, eax
0x18000922b  jz      short loc_18000926A
0x18000922d  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x180009231  call    cs:__imp_PathRemoveFileSpecW
0x180009237  jmp     short loc_18000926A
0x180009239  call    cs:__imp_GetLastError
0x18000923f  cmp     eax, 5
0x180009242  jz      short loc_1800092A6
0x180009244  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x180009248  call    cs:__imp_PathIsRootW
0x18000924e  test    eax, eax
0x180009250  jnz     short loc_1800092AE
0x180009252  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x180009256  call    cs:__imp_PathRemoveBackslashW
0x18000925c  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x180009260  call    cs:__imp_PathRemoveFileSpecW
0x180009266  test    eax, eax
0x180009268  jz      short loc_1800092AE
0x18000926a  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x18000926e  call    cs:__imp_PathAddBackslashW
0x180009274  xor     ecx, ecx
0x180009276  lea     rax, [rsp+7B0h+FileSystemFlags]
0x18000927b  mov     [rsp+7B0h+nFileSystemNameSize], ecx; nFileSystemNameSize
0x18000927f  xor     r9d, r9d; lpVolumeSerialNumber
0x180009282  mov     [rsp+7B0h+lpFileSystemNameBuffer], rcx; lpFileSystemNameBuffer
0x180009287  xor     r8d, r8d; nVolumeNameSize
0x18000928a  mov     [rsp+7B0h+lpFileSystemFlags], rax; lpFileSystemFlags
0x18000928f  xor     edx, edx; lpVolumeNameBuffer
0x180009291  mov     [rsp+7B0h+lpMaximumComponentLength], rcx; lpMaximumComponentLength
0x180009296  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; lpRootPathName
0x18000929a  call    cs:__imp_GetVolumeInformationW
0x1800092a0  test    eax, eax
0x1800092a2  jz      short loc_180009239
0x1800092a4  jmp     short loc_1800092AE
0x1800092a6  mov     [rsp+7B0h+FileSystemFlags], 8
0x1800092ae  lea     rcx, [rbp+6B0h+szVolumeMountPoint]; pszPath
0x1800092b2  call    cs:__imp_PathRemoveBackslashW
0x1800092b8  lea     r8, [rbp+6B0h+szVolumeMountPoint]; unsigned __int16 *
0x1800092bc  mov     rdx, rdi; unsigned __int64
0x1800092bf  lea     rcx, [rbp+6B0h+pszPath]; unsigned __int16 *
0x1800092c6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800092cb  mov     rcx, rsi; pszPath
0x1800092ce  call    cs:__imp_PathIsUNCW
0x1800092d4  test    eax, eax
0x1800092d6  jnz     short loc_1800092ED
0x1800092d8  lea     rdx, [rsp+7B0h+hMem]; unsigned __int16 **
0x1800092dd  mov     rcx, rsi; unsigned __int16 *
0x1800092e0  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x1800092e5  test    eax, eax
0x1800092e7  cmovz   rsi, [rsp+7B0h+hMem]
0x1800092ed  lea     rcx, [rbp+6B0h+pszPath]; pszPath
0x1800092f4  call    cs:__imp_PathIsUNCW
0x1800092fa  test    eax, eax
0x1800092fc  jnz     short loc_18000935D
0x1800092fe  lea     rdx, [rsp+7B0h+var_768]; unsigned __int16 **
0x180009303  lea     rcx, [rbp+6B0h+pszPath]; unsigned __int16 *
0x18000930a  call    ?GetRemotePath@@YAJPEBGPEAPEAG@Z; GetRemotePath(ushort const *,ushort * *)
0x18000930f  mov     r12, [rsp+7B0h+var_768]
0x180009314  test    eax, eax
0x180009316  jnz     short loc_18000935D
0x180009318  mov     rcx, r12
0x18000931b  lea     rax, [rbp+6B0h+pszPath]
0x180009322  mov     rdx, rdi
0x180009325  test    r15, r15
0x180009328  jz      short loc_180009349
0x18000932a  movzx   r8d, word ptr [rcx]
0x18000932e  test    r8w, r8w
0x180009332  jz      short loc_180009349
0x180009334  mov     [rax], r8w
0x180009338  add     rcx, 2
0x18000933c  add     rax, 2
0x180009340  dec     r15
0x180009343  sub     rdx, 1
0x180009347  jnz     short loc_180009325
0x180009349  xor     r15d, r15d
0x18000934c  lea     rcx, [rax-2]
0x180009350  test    rdx, rdx
0x180009353  cmovnz  rcx, rax
0x180009357  mov     [rcx], r15w
0x18000935b  jmp     short loc_180009360
0x18000935d  xor     r15d, r15d
0x180009360  test    r13, r13
0x180009363  jz      short loc_180009372
0x180009365  mov     rcx, rsi; pszPath
0x180009368  call    cs:__imp_PathIsUNCW
0x18000936e  mov     [r13+0], eax
0x180009372  mov     rcx, rsi; pszPath
0x180009375  call    cs:__imp_PathIsUNCServerShareW
0x18000937b  mov     rcx, rsi; pszPath
0x18000937e  test    eax, eax
0x180009380  jz      short loc_1800093DC
0x180009382  call    ?IsShareRoot@@YAHPEBG@Z; IsShareRoot(ushort const *)
0x180009387  test    eax, eax
0x180009389  jz      short loc_180009390
0x18000938b  or      dword ptr [rbx], 2
0x18000938e  jmp     short loc_18000939C
0x180009390  test    r14, r14
0x180009393  jz      short loc_18000939C
0x180009395  mov     dword ptr [r14], 1
0x18000939c  test    byte ptr [rsp+7B0h+FileSystemFlags], 8
0x1800093a1  mov     r14, [rsp+7B0h+lpBuffer]
0x1800093a6  jz      loc_180009446
0x1800093ac  or      dword ptr [rbx], 4
0x1800093af  lea     rcx, [rbp+6B0h+pszPath]; unsigned __int16 *
0x1800093b6  xor     r9d, r9d; unsigned __int16 *
0x1800093b9  mov     dword ptr [rsp+7B0h+lpMaximumComponentLength], r15d; unsigned int
0x1800093be  mov     r8d, edi; unsigned int
0x1800093c1  mov     rdx, r14; unsigned __int16 *
0x1800093c4  call    ?IsDfsPath@@YAHPEBGPEAGI1I@Z; IsDfsPath(ushort const *,ushort *,uint,ushort *,uint)
0x1800093c9  test    eax, eax
0x1800093cb  jz      short loc_1800093F9
0x1800093cd  test    r13, r13
0x1800093d0  jz      short loc_180009446
0x1800093d2  mov     dword ptr [r13+0], 1
0x1800093da  jmp     short loc_180009446
0x1800093dc  call    cs:__imp_PathIsRootW
0x1800093e2  test    eax, eax
0x1800093e4  jz      short loc_18000939C
0x1800093e6  or      dword ptr [rbx], 2
0x1800093e9  mov     rcx, rsi; lpRootPathName
0x1800093ec  call    cs:__imp_GetDriveTypeW
0x1800093f2  cmp     eax, 4
0x1800093f5  jnz     short loc_18000939C
0x1800093f7  jmp     short loc_180009390
0x1800093f9  lea     rcx, [rbp+6B0h+pszPath]; pszPath
0x180009400  call    cs:__imp_PathIsUNCW
0x180009406  test    eax, eax
0x180009408  jz      short loc_180009446
0x18000940a  mov     edx, 5Ch ; '\'; wMatch
0x18000940f  lea     rcx, [rbp+6B0h+pszStart]; pszStart
0x180009416  call    cs:__imp_StrChrW
0x18000941c  test    rax, rax
0x18000941f  jz      short loc_180009435
0x180009421  lea     rcx, [rbp+6B0h+pszPath]
0x180009428  sub     rax, rcx
0x18000942b  sar     rax, 1
0x18000942e  inc     eax
0x180009430  cmp     eax, edi
0x180009432  cmovbe  edi, eax
0x180009435  mov     edx, edi; unsigned __int64
0x180009437  lea     r8, [rbp+6B0h+pszPath]; unsigned __int16 *
0x18000943e  mov     rcx, r14; unsigned __int16 *
0x180009441  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180009446  mov     [rsp+7B0h+nSize], edi
0x18000944a  cmp     [r14], r15w
0x18000944e  jnz     short loc_18000945E
0x180009450  lea     rdx, [rsp+7B0h+nSize]; nSize
0x180009455  mov     rcx, r14; lpBuffer
0x180009458  call    cs:__imp_GetComputerNameW
0x18000945e  xorps   xmm0, xmm0
0x180009461  mov     [rsp+7B0h+FileHandle], r15
0x180009466  xorps   xmm1, xmm1
0x180009469  lea     rcx, [rbp+6B0h+FileInformation]; void *
0x18000946d  mov     edi, 74h ; 't'
0x180009472  xor     edx, edx; Val
0x180009474  mov     r8d, edi; Size
0x180009477  movups  xmmword ptr [rsp+7B0h+ObjectAttributes.Length], xmm0
0x18000947c  movups  xmmword ptr [rbp+6B0h+ObjectAttributes.ObjectName], xmm0
0x180009480  movups  xmmword ptr [rbp+6B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180009484  movups  xmmword ptr [rbp+6B0h+IoStatusBlock], xmm0
0x180009488  movups  xmmword ptr [rsp+7B0h+NtPathName.Length], xmm1
0x18000948d  call    memset_0
0x180009492  or      dword ptr [rbx], 8
0x180009495  cmp     [r13+0], r15d
0x180009499  jz      loc_18000955B
0x18000949f  xor     r9d, r9d; DirectoryInfo
0x1800094a2  lea     rdx, [rsp+7B0h+NtPathName]; NtPathName
0x1800094a7  xor     r8d, r8d; NtFileNamePart
0x1800094aa  mov     rcx, rsi; DosPathName
0x1800094ad  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x1800094b3  test    al, al
0x1800094b5  jz      loc_18000955B
0x1800094bb  lea     rax, [rsp+7B0h+NtPathName]
0x1800094c0  mov     dword ptr [rsp+7B0h+lpFileSystemFlags], r15d; OpenOptions
0x1800094c5  xorps   xmm0, xmm0
0x1800094c8  mov     [rbp+6B0h+ObjectAttributes.ObjectName], rax
0x1800094cc  lea     r9, [rbp+6B0h+IoStatusBlock]; IoStatusBlock
0x1800094d0  mov     [rsp+7B0h+ObjectAttributes.Length], 30h ; '0'
0x1800094d8  lea     r8, [rsp+7B0h+ObjectAttributes]; ObjectAttributes
0x1800094dd  mov     [rbp+6B0h+ObjectAttributes.RootDirectory], r15
0x1800094e1  lea     edx, [rdi+0Ch]; DesiredAccess
0x1800094e4  mov     [rbp+6B0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800094eb  lea     rcx, [rsp+7B0h+FileHandle]; FileHandle
0x1800094f0  mov     dword ptr [rsp+7B0h+lpMaximumComponentLength], 3; ShareAccess
0x1800094f8  movdqu  xmmword ptr [rbp+6B0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800094fd  call    cs:__imp_NtOpenFile
0x180009503  mov     ecx, eax; Status
0x180009505  call    cs:__imp_RtlNtStatusToDosError
0x18000950b  test    eax, eax
0x18000950d  jnz     short loc_180009550
0x18000950f  mov     rcx, [rsp+7B0h+FileHandle]; hFile
0x180009514  lea     r8, [rbp+6B0h+FileInformation]; lpFileInformation
0x180009518  mov     r9d, edi; dwBufferSize
0x18000951b  lea     edx, [rdi-67h]; FileInformationClass
0x18000951e  call    cs:__imp_GetFileInformationByHandleEx
0x180009524  test    eax, eax
0x180009526  jz      short loc_180009545
0x180009528  cmp     [rbp+6B0h+var_6EC], 20000h
0x18000952f  jnz     short loc_180009545
0x180009531  lea     eax, [rdi-72h]
0x180009534  cmp     [rbp+6B0h+var_6E8], ax
0x180009538  jb      short loc_180009542
0x18000953a  jnz     short loc_180009545
0x18000953c  cmp     [rbp+6B0h+var_6E6], ax
0x180009540  jnb     short loc_180009545
0x180009542  and     dword ptr [rbx], 0FFFFFFF7h
0x180009545  mov     rcx, [rsp+7B0h+FileHandle]; Handle
0x18000954a  call    cs:__imp_NtClose
0x180009550  lea     rcx, [rsp+7B0h+NtPathName]; UnicodeString
0x180009555  call    cs:__imp_RtlFreeUnicodeString
0x18000955b  mov     rax, [rsp+7B0h+hMem]
0x180009560  test    rax, rax
0x180009563  jz      short loc_18000956E
0x180009565  mov     rcx, rax; hMem
0x180009568  call    cs:__imp_LocalFree
0x18000956e  test    r12, r12
0x180009571  jz      short loc_18000957C
0x180009573  mov     rcx, r12; hMem
0x180009576  call    cs:__imp_LocalFree
0x18000957c  mov     rcx, [rbp+6B0h+var_40]
0x180009583  xor     rcx, rsp; StackCookie
0x180009586  call    __security_check_cookie
0x18000958b  mov     rbx, [rsp+7B0h+arg_18]
0x180009593  add     rsp, 780h
0x18000959a  pop     r15
0x18000959c  pop     r14
0x18000959e  pop     r13
0x1800095a0  pop     r12
0x1800095a2  pop     rdi
0x1800095a3  pop     rsi
0x1800095a4  pop     rbp
0x1800095a5  retn
```
