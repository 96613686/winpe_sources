# CEnumFiles::_InitEnumeration(ushort const *,ushort const *,int,tagWIN32_FIND_DATA_EX *)

- ea: `0x1800f3790`
- end: `0x1800f3e68`
- name: `?_InitEnumeration@CEnumFiles@@AEAAJPEBG0HPEAUtagWIN32_FIND_DATA_EX@@@Z`
- size: `1752`
- prototype: `__int64 __usercall@<rax>(CEnumFiles *__hidden this@<rcx>, LPCWSTR lpFileName@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, struct tagWIN32_FIND_DATA_EX *)`
- caller_count: `7`
- callee_count: `15`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800f1bc0`
- `0x1800f1be0`
- `0x1800f3080`
- `0x18025c018`
- `0x1802edc30`
- `0x18036be50`
- `0x18056151c`

## callees

- `0x1800f3790`
- `0x1800f3e70`
- `0x180159af0`
- `0x1801b7444`
- `0x1801c86d0`
- `0x18022e910`
- `0x180236540`
- `0x1802abb90`
- `0x18035fa60`
- `0x18036c080`
- `0x18036db6c`
- `0x18036e290`
- `0x1803b1f60`
- `0x1803b2ac0`
- `0x1803b69c5`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f3b1a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3a49`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f3a49`
- `ntdll!RtlNtStatusToDosError` at `0x180666909`
- `ntdll!RtlNtStatusToDosError` at `0x180666909`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x1800f37e1`
- `ntdll!RtlQueryThreadPlaceholderCompatibilityMode` at `0x1800f37e1`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800f37f7`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800f3a73`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800f37f7`
- `ntdll!RtlSetThreadPlaceholderCompatibilityMode` at `0x1800f3a73`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800f3ab8`
- `ntdll!RtlInitUnicodeStringEx` at `0x1800f3ab8`
- `ntdll!NtQueryDirectoryFile` at `0x1800f3915`
- `ntdll!NtQueryDirectoryFile` at `0x1800f3915`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f3bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f3d84`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f3bb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800f3d84`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f3b7c`
- `api-ms-win-core-path-l1-1-0!PathAllocCombine` at `0x1800f3b7c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f386d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800f386d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f3e4f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1800f3e4f`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f3e15`
- `api-ms-win-core-file-l1-1-0!GetDriveTypeW` at `0x1800f3e15`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800f382d`
- `SHCORE!__imp_SHWindowsPolicy` at `0x1800f382d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CEnumFiles::_InitEnumeration(
        CEnumFiles *this,
        LPCWSTR lpFileName,
        const unsigned __int16 *a3,
        int a4,
        WCHAR *a5)
{
  const WCHAR *v6; // rbx
  PWSTR v8; // r12
  char v9; // di
  __int64 v10; // rcx
  unsigned __int8 v11; // bp
  FILE_INFORMATION_CLASS FileInformationClass; // r12d
  HANDLE FileW; // rcx
  HANDLE *v14; // r14
  int v15; // ebx
  int v16; // edx
  struct _UNICODE_STRING *FileName; // rdx
  NTSTATUS DirectoryFile; // eax
  int DataFromFileInformationByHandle; // ebx
  int v20; // eax
  __int64 v21; // rcx
  __int64 v22; // r13
  PWSTR v23; // r12
  unsigned int v24; // eax
  size_t v25; // r8
  size_t v26; // r8
  int v27; // eax
  void *v28; // rcx
  NTSTATUS inited; // eax
  signed int LastError; // eax
  _DWORD *v32; // r13
  PWSTR v33; // r12
  unsigned int v34; // eax
  size_t v35; // r8
  char v36; // r12
  int v37; // r8d
  __int64 v38; // rdx
  ULONG v39; // eax
  int dwCreationDisposition; // [rsp+20h] [rbp-B8h]
  unsigned __int8 v42; // [rsp+65h] [rbp-73h]
  PWSTR ppszPathOut; // [rsp+70h] [rbp-68h] BYREF
  HLOCAL hMem; // [rsp+78h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+80h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+0h]

  v6 = lpFileName;
  v8 = a5;
  ppszPathOut = a5;
  v9 = 0;
  if ( (unsigned __int8)RtlQueryThreadPlaceholderCompatibilityMode() == 2 )
  {
    v11 = v42;
  }
  else
  {
    LOBYTE(v10) = 2;
    v11 = RtlSetThreadPlaceholderCompatibilityMode(v10);
    v9 = 1;
  }
  DestinationString = 0;
  if ( a3 )
  {
    inited = RtlInitUnicodeStringEx(&DestinationString, a3);
    if ( inited < 0 )
    {
      DataFromFileInformationByHandle = wil::details::in1diag3::Return_NtStatus(
                                          retaddr,
                                          (void *)0x178,
                                          (unsigned int)"onecoreuap\\shell\\windows.storage\\findfile.cpp",
                                          (const char *)(unsigned int)inited,
                                          dwCreationDisposition);
      goto LABEL_34;
    }
  }
  if ( (unsigned int)SHWindowsPolicy(POLID_UseFindFirstFileEnumeration) )
  {
    v14 = (HANDLE *)((char *)this + 48);
LABEL_48:
    CEnumFiles::_FindClose(this);
    if ( a4 )
    {
      ppszPathOut = 0;
      DataFromFileInformationByHandle = PathAllocCombine(v6, a3, 1u, &ppszPathOut);
      if ( DataFromFileInformationByHandle >= 0 )
      {
        DataFromFileInformationByHandle = GetFindDataFromFileInformationByHandle(ppszPathOut);
        if ( DataFromFileInformationByHandle >= 0 )
        {
          hMem = 0;
          if ( SHGetSnapshotTimeFromPath(ppszPathOut, (struct _FILETIME *)&hMem) >= 0 )
            DataFromFileInformationByHandle = CheckTimewarp(ppszPathOut);
        }
      }
      if ( ppszPathOut )
        LocalFree(ppszPathOut);
      v14 = (HANDLE *)((char *)this + 48);
    }
    else
    {
      DataFromFileInformationByHandle = CEnumFiles::_InitByNormalFindFirst(
                                          this,
                                          v6,
                                          a3,
                                          (struct tagWIN32_FIND_DATA_EX *)v8);
    }
    goto LABEL_27;
  }
  FileInformationClass = FileBothDirectoryInformation;
  FileW = CreateFileW(v6, 0x100081u, 7u, 0, 3u, 0x2000000u, 0);
  v14 = (HANDLE *)((char *)this + 48);
  *((_QWORD *)this + 6) = FileW;
  if ( FileW != (HANDLE)-1LL )
  {
    if ( *((_DWORD *)this + 37) || *((_DWORD *)this + 21) == 37 )
    {
      v15 = IsSMBv1(FileW);
      v16 = *((_DWORD *)this + 37);
      FileW = *v14;
    }
    else
    {
      v15 = -2147467259;
      v16 = 0;
    }
    if ( *((_DWORD *)this + 21) == 37 )
    {
      if ( v15 )
        FileInformationClass = FileIdBothDirectoryInformation;
      else
        *((_DWORD *)this + 21) = 3;
    }
    else
    {
      FileInformationClass = *((_DWORD *)this + 21);
    }
    if ( v16 && *((_QWORD *)this + 9) > 0x10000u && v15 >= 0 )
      *((_QWORD *)this + 9) = 0x10000;
    FileName = &DestinationString;
    if ( !a3 )
      FileName = 0;
    DirectoryFile = NtQueryDirectoryFile(
                      FileW,
                      0,
                      0,
                      0,
                      (PIO_STATUS_BLOCK)this + 2,
                      *((PVOID *)this + 8),
                      *((_DWORD *)this + 18),
                      FileInformationClass,
                      a3 != 0,
                      FileName,
                      1u);
    *((_DWORD *)this + 20) = DirectoryFile;
    if ( !DirectoryFile )
    {
      if ( *((_QWORD *)this + 5) )
      {
        DataFromFileInformationByHandle = 0;
        if ( !*((_DWORD *)this + 37)
          || (DataFromFileInformationByHandle = CEnumFiles::_InitializeIndexFromBuffer(this),
              DataFromFileInformationByHandle >= 0) )
        {
          if ( *((_DWORD *)this + 37) )
          {
            *((_DWORD *)this + 36) = 0;
            v37 = *((_DWORD *)this + 21);
            v38 = *((_QWORD *)this + 8) + **((unsigned int **)this + 14);
            if ( v37 == 37 )
            {
              *((_QWORD *)this + 11) = v38;
LABEL_22:
              v22 = *((_QWORD *)this + 11);
              v23 = ppszPathOut;
              memset_0(ppszPathOut, 0, 0x268u);
              *(_DWORD *)ppszPathOut = *(_DWORD *)(v22 + 56);
              *((_DWORD *)v23 + 1) = *(_DWORD *)(v22 + 8);
              *((_DWORD *)v23 + 2) = *(_DWORD *)(v22 + 12);
              *((_DWORD *)v23 + 3) = *(_DWORD *)(v22 + 16);
              *((_DWORD *)v23 + 4) = *(_DWORD *)(v22 + 20);
              *((_DWORD *)v23 + 5) = *(_DWORD *)(v22 + 24);
              *((_DWORD *)v23 + 6) = *(_DWORD *)(v22 + 28);
              *((_DWORD *)v23 + 8) = *(_DWORD *)(v22 + 40);
              *((_DWORD *)v23 + 7) = *(_DWORD *)(v22 + 44);
              *((_DWORD *)v23 + 9) = *(_DWORD *)(v22 + 64);
              *((_QWORD *)v23 + 74) = *(_QWORD *)(v22 + 96);
              v24 = *(_DWORD *)(v22 + 60);
              v25 = 518;
              if ( v24 <= 0x206 )
                v25 = v24;
              memcpy_0(v23 + 22, (const void *)(v22 + 104), v25);
              v26 = *(char *)(v22 + 68);
              if ( v26 > 0x18 )
                v26 = 24;
              memcpy_0(v23 + 282, (const void *)(v22 + 70), v26);
              goto LABEL_27;
            }
            if ( v37 == 2 )
            {
              *((_QWORD *)this + 13) = v38;
              goto LABEL_56;
            }
            *((_QWORD *)this + 12) = v38;
          }
          else
          {
            v20 = *((_DWORD *)this + 21);
            v21 = *((_QWORD *)this + 8);
            if ( v20 == 37 )
            {
              *((_QWORD *)this + 11) = v21;
            }
            else if ( v20 == 2 )
            {
              *((_QWORD *)this + 13) = v21;
            }
            else
            {
              *((_QWORD *)this + 12) = v21;
            }
            if ( v20 == 37 )
              goto LABEL_22;
            if ( v20 == 2 )
            {
LABEL_56:
              v32 = (_DWORD *)*((_QWORD *)this + 13);
              v33 = ppszPathOut;
              memset_0(ppszPathOut, 0, 0x268u);
              *(_DWORD *)ppszPathOut = v32[14];
              *((_DWORD *)v33 + 1) = v32[2];
              *((_DWORD *)v33 + 2) = v32[3];
              *((_DWORD *)v33 + 3) = v32[4];
              *((_DWORD *)v33 + 4) = v32[5];
              *((_DWORD *)v33 + 5) = v32[6];
              *((_DWORD *)v33 + 6) = v32[7];
              *((_DWORD *)v33 + 8) = v32[10];
              *((_DWORD *)v33 + 7) = v32[11];
              *((_DWORD *)v33 + 9) = v32[16];
              v34 = v32[15];
              v35 = 518;
              if ( v34 <= 0x206 )
                v35 = v34;
              memcpy_0(v33 + 22, v32 + 17, v35);
              goto LABEL_27;
            }
          }
          _ConvertBothDirInfoToWFDX(
            *((const struct _FILE_BOTH_DIR_INFORMATION **)this + 12),
            (struct tagWIN32_FIND_DATA_EX *)ppszPathOut);
        }
LABEL_27:
        v27 = a4;
        goto LABEL_28;
      }
      goto LABEL_64;
    }
    if ( DirectoryFile != -1073741809
      && DirectoryFile != -1073741628
      && DirectoryFile != -1073741496
      && DirectoryFile != -1073741637
      && DirectoryFile != -1073741811 )
    {
LABEL_64:
      v36 = 0;
      GetPathRoot(&hMem, lpFileName);
      if ( hMem )
      {
        if ( a4 && GetDriveTypeW((LPCWSTR)hMem) == 5 )
        {
          DataFromFileInformationByHandle = 0;
          v36 = 1;
        }
        else
        {
          v39 = RtlNtStatusToDosError(*((_DWORD *)this + 20));
          DataFromFileInformationByHandle = ResultFromKnownError(v39);
        }
        if ( hMem )
          LocalFree(hMem);
      }
      else
      {
        DataFromFileInformationByHandle = -2147024882;
      }
      if ( !v36 )
        goto LABEL_27;
      goto LABEL_47;
    }
    goto LABEL_47;
  }
  LastError = GetLastError();
  DataFromFileInformationByHandle = LastError;
  if ( LastError > 0 )
    DataFromFileInformationByHandle = (unsigned __int16)LastError | 0x80070000;
  if ( DataFromFileInformationByHandle >= 0 )
  {
    DataFromFileInformationByHandle = -2147467259;
  }
  else if ( DataFromFileInformationByHandle == -2147024894 || DataFromFileInformationByHandle == -2147024893 )
  {
    goto LABEL_47;
  }
  v27 = a4;
  if ( a4 && DataFromFileInformationByHandle == -2147024891 )
  {
LABEL_47:
    v8 = ppszPathOut;
    v6 = lpFileName;
    goto LABEL_48;
  }
LABEL_28:
  if ( a3 || v27 || ((DataFromFileInformationByHandle + 2147024894) & 0xFFFFFFEF) != 0 )
  {
    if ( DataFromFileInformationByHandle < 0 )
    {
      if ( *v14 != (HANDLE)-1LL )
      {
        CloseHandle(*v14);
        *v14 = (HANDLE)-1LL;
      }
      v28 = (void *)*((_QWORD *)this + 7);
      if ( v28 != (void *)-1LL )
      {
        FindClose(v28);
        *((_QWORD *)this + 7) = -1;
      }
    }
  }
  else
  {
    DataFromFileInformationByHandle = 1;
  }
LABEL_34:
  if ( v9 )
    RtlSetThreadPlaceholderCompatibilityMode(v11);
  return (unsigned int)DataFromFileInformationByHandle;
}

```

## disassembly

```asm
0x1800f3790  mov     [rsp+arg_18], rbx
0x1800f3795  push    rbp
0x1800f3796  push    rsi
0x1800f3797  push    rdi
0x1800f3798  push    r12
0x1800f379a  push    r13
0x1800f379c  push    r14
0x1800f379e  push    r15
0x1800f37a0  sub     rsp, 0A0h
0x1800f37a7  mov     rax, cs:__security_cookie
0x1800f37ae  xor     rax, rsp
0x1800f37b1  mov     [rsp+0D8h+var_48], rax
0x1800f37b9  mov     [rsp+0D8h+var_78], r9d
0x1800f37be  mov     r15, r8
0x1800f37c1  mov     rbx, rdx
0x1800f37c4  mov     [rsp+0D8h+pszPathIn], rdx
0x1800f37c9  mov     rsi, rcx
0x1800f37cc  mov     r12, [rsp+0D8h+arg_20]
0x1800f37d4  mov     [rsp+0D8h+ppszPathOut], r12
0x1800f37d9  xor     dil, dil
0x1800f37dc  mov     [rsp+0D8h+var_74], dil
0x1800f37e1  call    cs:__imp_RtlQueryThreadPlaceholderCompatibilityMode
0x1800f37e8  nop     dword ptr [rax+rax+00h]
0x1800f37ed  cmp     al, 2
0x1800f37ef  jz      loc_1800F3D95
0x1800f37f5  mov     cl, 2
0x1800f37f7  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x1800f37fe  nop     dword ptr [rax+rax+00h]
0x1800f3803  movzx   ebp, al
0x1800f3806  mov     [rsp+0D8h+var_73], al
0x1800f380a  mov     dil, 1
0x1800f380d  mov     [rsp+0D8h+var_74], dil
0x1800f3812  xorps   xmm0, xmm0
0x1800f3815  movups  xmmword ptr [rsp+0D8h+DestinationString.Length], xmm0
0x1800f381d  test    r15, r15
0x1800f3820  jnz     loc_1800F3AAD
0x1800f3826  lea     rcx, POLID_UseFindFirstFileEnumeration
0x1800f382d  call    cs:__imp_SHWindowsPolicy
0x1800f3834  nop     dword ptr [rax+rax+00h]
0x1800f3839  xor     r13d, r13d
0x1800f383c  test    eax, eax
0x1800f383e  jnz     loc_1800F3E46
0x1800f3844  mov     [rsp+0D8h+hTemplateFile], r13; hTemplateFile
0x1800f3849  mov     [rsp+0D8h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x1800f3851  mov     r12d, 3
0x1800f3857  mov     [rsp+0D8h+dwCreationDisposition], r12d; dwCreationDisposition
0x1800f385c  xor     r9d, r9d; lpSecurityAttributes
0x1800f385f  mov     edx, 100081h; dwDesiredAccess
0x1800f3864  mov     r8d, 7; dwShareMode
0x1800f386a  mov     rcx, rbx; lpFileName
0x1800f386d  call    cs:__imp_CreateFileW
0x1800f3874  nop     dword ptr [rax+rax+00h]
0x1800f3879  mov     rcx, rax
0x1800f387c  lea     r14, [rsi+30h]
0x1800f3880  mov     [r14], rax
0x1800f3883  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800f3887  jz      loc_1800F3B1A
0x1800f388d  cmp     [rsi+94h], r13d
0x1800f3894  jnz     short loc_1800F38A0
0x1800f3896  cmp     dword ptr [rsi+54h], 25h ; '%'
0x1800f389a  jnz     loc_1800F3BC6
0x1800f38a0  call    IsSMBv1
0x1800f38a5  mov     ebx, eax
0x1800f38a7  mov     edx, [rsi+94h]
0x1800f38ad  mov     rcx, [r14]; FileHandle
0x1800f38b0  mov     eax, [rsi+54h]
0x1800f38b3  cmp     eax, 25h ; '%'
0x1800f38b6  jnz     loc_1800F3B12
0x1800f38bc  test    ebx, ebx
0x1800f38be  jz      loc_1800F3D9F
0x1800f38c4  mov     r12d, eax
0x1800f38c7  test    edx, edx
0x1800f38c9  jnz     loc_1800F3DA8
0x1800f38cf  lea     rdx, [rsp+0D8h+DestinationString]
0x1800f38d7  test    r15, r15
0x1800f38da  cmovz   rdx, r13
0x1800f38de  setnz   al
0x1800f38e1  lea     r8, [rsi+20h]
0x1800f38e5  mov     [rsp+0D8h+RestartScan], 1; RestartScan
0x1800f38ea  mov     [rsp+0D8h+FileName], rdx; FileName
0x1800f38ef  mov     [rsp+0D8h+ReturnSingleEntry], al; ReturnSingleEntry
0x1800f38f3  mov     [rsp+0D8h+FileInformationClass], r12d; FileInformationClass
0x1800f38f8  mov     eax, [rsi+48h]
0x1800f38fb  mov     dword ptr [rsp+0D8h+hTemplateFile], eax; Length
0x1800f38ff  mov     rax, [rsi+40h]
0x1800f3903  mov     qword ptr [rsp+0D8h+dwFlagsAndAttributes], rax; FileInformation
0x1800f3908  mov     qword ptr [rsp+0D8h+dwCreationDisposition], r8; IoStatusBlock
0x1800f390d  xor     r9d, r9d; ApcContext
0x1800f3910  xor     r8d, r8d; ApcRoutine
0x1800f3913  xor     edx, edx; Event
0x1800f3915  call    cs:__imp_NtQueryDirectoryFile
0x1800f391c  nop     dword ptr [rax+rax+00h]
0x1800f3921  mov     [rsi+50h], eax
0x1800f3924  test    eax, eax
0x1800f3926  jnz     loc_1800F3C73
0x1800f392c  cmp     [rsi+28h], r13
0x1800f3930  jz      loc_1800F3CAA
0x1800f3936  mov     ebx, r13d
0x1800f3939  cmp     [rsi+94h], ebx
0x1800f393f  jnz     loc_1800F3DCB
0x1800f3945  cmp     [rsi+94h], r13d
0x1800f394c  jnz     loc_1800F3DE2
0x1800f3952  mov     eax, [rsi+54h]
0x1800f3955  mov     rcx, [rsi+40h]
0x1800f3959  cmp     eax, 25h ; '%'
0x1800f395c  jnz     loc_1800F3CDD
0x1800f3962  mov     [rsi+58h], rcx
0x1800f3966  cmp     eax, 25h ; '%'
0x1800f3969  jnz     loc_1800F3BD3
0x1800f396f  mov     r13, [rsi+58h]
0x1800f3973  xor     edx, edx; Val
0x1800f3975  mov     r8d, 268h; Size
0x1800f397b  mov     r12, [rsp+0D8h+ppszPathOut]
0x1800f3980  mov     rcx, r12; void *
0x1800f3983  call    memset_0
0x1800f3988  mov     eax, [r13+38h]
0x1800f398c  mov     [r12], eax
0x1800f3990  mov     eax, [r13+8]
0x1800f3994  mov     [r12+4], eax
0x1800f3999  mov     eax, [r13+0Ch]
0x1800f399d  mov     [r12+8], eax
0x1800f39a2  mov     eax, [r13+10h]
0x1800f39a6  mov     [r12+0Ch], eax
0x1800f39ab  mov     eax, [r13+14h]
0x1800f39af  mov     [r12+10h], eax
0x1800f39b4  mov     eax, [r13+18h]
0x1800f39b8  mov     [r12+14h], eax
0x1800f39bd  mov     eax, [r13+1Ch]
0x1800f39c1  mov     [r12+18h], eax
0x1800f39c6  mov     eax, [r13+28h]
0x1800f39ca  mov     [r12+20h], eax
0x1800f39cf  mov     eax, [r13+2Ch]
0x1800f39d3  mov     [r12+1Ch], eax
0x1800f39d8  mov     eax, [r13+40h]
0x1800f39dc  mov     [r12+24h], eax
0x1800f39e1  mov     rax, [r13+60h]
0x1800f39e5  mov     [r12+250h], rax
0x1800f39ed  mov     eax, [r13+3Ch]
0x1800f39f1  mov     r8d, 206h
0x1800f39f7  cmp     eax, r8d
0x1800f39fa  ja      short loc_1800F39FF
0x1800f39fc  mov     r8d, eax; Size
0x1800f39ff  lea     rdx, [r13+68h]; Src
0x1800f3a03  lea     rcx, [r12+2Ch]; void *
0x1800f3a08  call    memcpy_0
0x1800f3a0d  movsx   r8, byte ptr [r13+44h]
0x1800f3a12  mov     eax, 18h
0x1800f3a17  cmp     r8, rax
0x1800f3a1a  cmova   r8, rax; Size
0x1800f3a1e  lea     rdx, [r13+46h]; Src
0x1800f3a22  lea     rcx, [r12+234h]; void *
0x1800f3a2a  call    memcpy_0
0x1800f3a2f  mov     eax, [rsp+0D8h+var_78]
0x1800f3a33  test    r15, r15
0x1800f3a36  jz      loc_1800F3AEF
0x1800f3a3c  test    ebx, ebx
0x1800f3a3e  jns     short loc_1800F3A6A
0x1800f3a40  mov     rcx, [r14]; hObject
0x1800f3a43  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f3a47  jz      short loc_1800F3A5C
0x1800f3a49  call    cs:__imp_CloseHandle
0x1800f3a50  nop     dword ptr [rax+rax+00h]
0x1800f3a55  mov     qword ptr [r14], 0FFFFFFFFFFFFFFFFh
0x1800f3a5c  mov     rcx, [rsi+38h]; hFindFile
0x1800f3a60  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f3a64  jnz     loc_1800F3E4F
0x1800f3a6a  test    dil, dil
0x1800f3a6d  jz      short loc_1800F3A7F
0x1800f3a6f  movzx   ecx, bpl
0x1800f3a73  call    cs:__imp_RtlSetThreadPlaceholderCompatibilityMode
0x1800f3a7a  nop     dword ptr [rax+rax+00h]
0x1800f3a7f  mov     eax, ebx
0x1800f3a81  mov     rcx, [rsp+0D8h+var_48]
0x1800f3a89  xor     rcx, rsp; StackCookie
0x1800f3a8c  call    __security_check_cookie
0x1800f3a91  mov     rbx, [rsp+0D8h+arg_18]
0x1800f3a99  add     rsp, 0A0h
0x1800f3aa0  pop     r15
0x1800f3aa2  pop     r14
0x1800f3aa4  pop     r13
0x1800f3aa6  pop     r12
0x1800f3aa8  pop     rdi
0x1800f3aa9  pop     rsi
0x1800f3aaa  pop     rbp
0x1800f3aab  retn
0x1800f3aad  mov     rdx, r15; SourceString
0x1800f3ab0  lea     rcx, [rsp+0D8h+DestinationString]; DestinationString
0x1800f3ab8  call    cs:__imp_RtlInitUnicodeStringEx
0x1800f3abf  nop     dword ptr [rax+rax+00h]
0x1800f3ac4  test    eax, eax
0x1800f3ac6  jns     loc_1800F3826
0x1800f3acc  mov     rcx, [rsp+0D8h]; this
0x1800f3ad4  mov     r9d, eax; char *
0x1800f3ad7  lea     r8, aOnecoreuapShel_93; "onecoreuap\\shell\\windows.storage\\fin"...
0x1800f3ade  mov     edx, 178h; void *
0x1800f3ae3  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800f3ae8  mov     ebx, eax
0x1800f3aea  jmp     loc_1800F3A6A
0x1800f3aef  test    eax, eax
0x1800f3af1  jnz     loc_1800F3A3C
0x1800f3af7  lea     eax, [rbx+7FF8FFFEh]
0x1800f3afd  test    eax, 0FFFFFFEFh
0x1800f3b02  jnz     loc_1800F3A3C
0x1800f3b08  mov     ebx, 1
0x1800f3b0d  jmp     loc_1800F3A6A
0x1800f3b12  mov     r12d, eax
0x1800f3b15  jmp     loc_1800F38C7
0x1800f3b1a  call    cs:__imp_GetLastError
0x1800f3b21  nop     dword ptr [rax+rax+00h]
0x1800f3b26  mov     ebx, eax
0x1800f3b28  test    eax, eax
0x1800f3b2a  jle     short loc_1800F3B35
0x1800f3b2c  movzx   ebx, ax
0x1800f3b2f  or      ebx, 80070000h
0x1800f3b35  test    ebx, ebx
0x1800f3b37  jns     loc_1800F3CEB
0x1800f3b3d  cmp     ebx, 80070002h
0x1800f3b43  jnz     loc_1800F3E35
0x1800f3b49  mov     r12, [rsp+0D8h+ppszPathOut]
0x1800f3b4e  mov     rbx, [rsp+0D8h+pszPathIn]
0x1800f3b53  mov     rcx, rsi; this
0x1800f3b56  call    ?_FindClose@CEnumFiles@@AEAAXXZ; CEnumFiles::_FindClose(void)
0x1800f3b5b  cmp     [rsp+0D8h+var_78], 0
0x1800f3b60  jz      loc_1800F3D42
0x1800f3b66  mov     [rsp+0D8h+ppszPathOut], r13
0x1800f3b6b  lea     r9, [rsp+0D8h+ppszPathOut]; ppszPathOut
0x1800f3b70  mov     r8d, 1; dwFlags
0x1800f3b76  mov     rdx, r15; pszMore
0x1800f3b79  mov     rcx, rbx; pszPathIn
0x1800f3b7c  call    cs:__imp_PathAllocCombine
0x1800f3b83  nop     dword ptr [rax+rax+00h]
0x1800f3b88  mov     ebx, eax
0x1800f3b8a  test    eax, eax
0x1800f3b8c  js      short loc_1800F3BA7
0x1800f3b8e  mov     r8, r12
0x1800f3b91  xor     edx, edx
0x1800f3b93  mov     rcx, [rsp+0D8h+ppszPathOut]; pszPath
0x1800f3b98  call    GetFindDataFromFileInformationByHandle
0x1800f3b9d  mov     ebx, eax
0x1800f3b9f  test    eax, eax
0x1800f3ba1  jns     loc_1800F3D0D
0x1800f3ba7  mov     rcx, [rsp+0D8h+ppszPathOut]; hMem
0x1800f3bac  test    rcx, rcx
0x1800f3baf  jz      short loc_1800F3BBD
0x1800f3bb1  call    cs:__imp_LocalFree
0x1800f3bb8  nop     dword ptr [rax+rax+00h]
0x1800f3bbd  lea     r14, [rsi+30h]
0x1800f3bc1  jmp     loc_1800F3A2F
0x1800f3bc6  mov     ebx, 80004005h
0x1800f3bcb  mov     edx, r13d
0x1800f3bce  jmp     loc_1800F38B0
0x1800f3bd3  cmp     eax, 2
0x1800f3bd6  jnz     loc_1800F3D63
0x1800f3bdc  mov     r13, [rsi+68h]
0x1800f3be0  xor     edx, edx; Val
0x1800f3be2  mov     r8d, 268h; Size
0x1800f3be8  mov     r12, [rsp+0D8h+ppszPathOut]
0x1800f3bed  mov     rcx, r12; void *
0x1800f3bf0  call    memset_0
0x1800f3bf5  mov     eax, [r13+38h]
0x1800f3bf9  mov     [r12], eax
0x1800f3bfd  mov     eax, [r13+8]
0x1800f3c01  mov     [r12+4], eax
0x1800f3c06  mov     eax, [r13+0Ch]
0x1800f3c0a  mov     [r12+8], eax
0x1800f3c0f  mov     eax, [r13+10h]
0x1800f3c13  mov     [r12+0Ch], eax
0x1800f3c18  mov     eax, [r13+14h]
0x1800f3c1c  mov     [r12+10h], eax
0x1800f3c21  mov     eax, [r13+18h]
0x1800f3c25  mov     [r12+14h], eax
0x1800f3c2a  mov     eax, [r13+1Ch]
0x1800f3c2e  mov     [r12+18h], eax
0x1800f3c33  mov     eax, [r13+28h]
0x1800f3c37  mov     [r12+20h], eax
0x1800f3c3c  mov     eax, [r13+2Ch]
0x1800f3c40  mov     [r12+1Ch], eax
0x1800f3c45  mov     eax, [r13+40h]
0x1800f3c49  mov     [r12+24h], eax
0x1800f3c4e  mov     eax, [r13+3Ch]
0x1800f3c52  mov     r8d, 206h
0x1800f3c58  cmp     eax, r8d
0x1800f3c5b  ja      short loc_1800F3C60
0x1800f3c5d  mov     r8d, eax; Size
0x1800f3c60  lea     rdx, [r13+44h]; Src
0x1800f3c64  lea     rcx, [r12+2Ch]; void *
0x1800f3c69  call    memcpy_0
0x1800f3c6e  jmp     loc_1800F3A2F
0x1800f3c73  cmp     eax, 0C000000Fh
0x1800f3c78  jz      loc_1800F3B49
0x1800f3c7e  cmp     eax, 0C00000C4h
0x1800f3c83  jz      loc_1800F3B49
0x1800f3c89  cmp     eax, 0C0000148h
0x1800f3c8e  jz      loc_1800F3B49
0x1800f3c94  cmp     eax, 0C00000BBh
0x1800f3c99  jz      loc_1800F3B49
0x1800f3c9f  cmp     eax, 0C000000Dh
0x1800f3ca4  jz      loc_1800F3B49
0x1800f3caa  xor     r12b, r12b
0x1800f3cad  mov     rdx, [rsp+0D8h+pszPathIn]
  ... truncated ...
```
