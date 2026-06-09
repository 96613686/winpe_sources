# WIMSetFileShortName

- ea: `0x180020cc8`
- end: `0x18002118b`
- name: `WIMSetFileShortName`
- size: `1219`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180014454`

## callees

- `0x18000fd58`
- `0x18001180c`
- `0x180020a08`
- `0x180020cc8`
- `0x1800219c4`
- `0x180060cfa`

## import_xrefs

- `msvcrt!wcsncmp` at `0x180020fd6`
- `msvcrt!wcsncmp` at `0x180020fd6`
- `KERNEL32!HeapFree` at `0x180020fff`
- `KERNEL32!HeapFree` at `0x18002103b`
- `KERNEL32!HeapFree` at `0x18002115b`
- `KERNEL32!HeapFree` at `0x180020fff`
- `KERNEL32!HeapFree` at `0x18002103b`
- `KERNEL32!HeapFree` at `0x18002115b`
- `KERNEL32!HeapAlloc` at `0x180020f89`
- `KERNEL32!HeapAlloc` at `0x180021094`
- `KERNEL32!HeapAlloc` at `0x180020f89`
- `KERNEL32!HeapAlloc` at `0x180021094`
- `KERNEL32!GetLastError` at `0x1800210ab`
- `KERNEL32!GetLastError` at `0x1800210cc`
- `KERNEL32!GetLastError` at `0x1800210ab`
- `KERNEL32!GetLastError` at `0x1800210cc`
- `KERNEL32!GetProcessHeap` at `0x180020f74`
- `KERNEL32!GetProcessHeap` at `0x180020feb`
- `KERNEL32!GetProcessHeap` at `0x180021027`
- `KERNEL32!GetProcessHeap` at `0x18002107d`
- `KERNEL32!GetProcessHeap` at `0x180021147`
- `KERNEL32!GetProcessHeap` at `0x180020f74`
- `KERNEL32!GetProcessHeap` at `0x180020feb`
- `KERNEL32!GetProcessHeap` at `0x180021027`
- `KERNEL32!GetProcessHeap` at `0x18002107d`
- `KERNEL32!GetProcessHeap` at `0x180021147`
- `ntdll!NtCreateFile` at `0x180020f60`
- `ntdll!NtCreateFile` at `0x180020f60`
- `ntdll!NtSetInformationFile` at `0x180021131`
- `ntdll!NtSetInformationFile` at `0x180021131`
- `ntdll!NtQueryInformationFile` at `0x180020fb1`
- `ntdll!NtQueryInformationFile` at `0x180020fb1`
- `ntdll!NtClose` at `0x18002100f`
- `ntdll!NtClose` at `0x18002104b`
- `ntdll!NtClose` at `0x18002100f`
- `ntdll!NtClose` at `0x18002104b`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180020eda`
- `ntdll!RtlDosPathNameToNtPathName_U` at `0x180020eda`

## string_xrefs

- `0x180020e85`: `WIMSetFileShortName`

## pseudocode

```c
__int64 __fastcall WIMSetFileShortName(__int64 a1, void *a2, const WCHAR *a3, const wchar_t *a4)
{
  const wchar_t *v4; // r15
  unsigned int v5; // r14d
  WCHAR v7; // ax
  char *v8; // rsi
  const wchar_t *v9; // rdi
  int v10; // ebx
  char *v11; // rsi
  const wchar_t *v12; // rdi
  int v13; // ebx
  __int64 v14; // rcx
  __int64 v15; // rax
  _QWORD *v16; // rax
  int v18; // eax
  __int64 v19; // rdx
  __int64 v20; // rax
  HANDLE ProcessHeap; // rax
  wchar_t *v22; // rbx
  size_t v23; // r8
  HANDLE v24; // rax
  HANDLE v26; // rax
  __int64 v27; // rax
  ULONG v28; // esi
  HANDLE v29; // rax
  unsigned __int16 *v30; // rdi
  int v31; // ebx
  signed int LastError; // eax
  signed int v33; // ecx
  signed int v34; // eax
  NTSTATUS v35; // eax
  HANDLE v36; // rax
  void *FileHandle; // [rsp+68h] [rbp-39h] BYREF
  _UNICODE_STRING NtPathName; // [rsp+70h] [rbp-31h] BYREF
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+80h] [rbp-21h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+90h] [rbp-11h] BYREF

  v4 = a4;
  v5 = 0;
  FileHandle = 0;
  if ( a2 == (void *)-1LL || !a3 )
    return 2147942487LL;
  v7 = *a3;
  v8 = (char *)a3;
  if ( *a3 )
  {
    while ( 1 )
    {
      v9 = L"\\Windows\\WinSxS\\";
      if ( v7 )
      {
        do
        {
          if ( !*v9 )
            break;
          v10 = towupper_0(*(const wchar_t *)((char *)v9 + v8 - (char *)L"\\Windows\\WinSxS\\"));
          if ( v10 != towupper_0(*v9) )
            break;
          ++v9;
        }
        while ( *(const wchar_t *)((char *)v9 + v8 - (char *)L"\\Windows\\WinSxS\\") );
        v5 = (unsigned int)FileHandle;
        v4 = a4;
      }
      if ( !*v9 )
        return 0;
      v8 += 2;
      v7 = *(_WORD *)v8;
      if ( !*(_WORD *)v8 )
      {
        v7 = *a3;
        break;
      }
    }
  }
  v11 = (char *)a3;
  if ( v7 )
  {
    do
    {
      v12 = L"\\Program Files\\WindowsApps\\";
      if ( v7 )
      {
        do
        {
          if ( !*v12 )
            break;
          v13 = towupper_0(*v12);
          if ( towupper_0(*(const wchar_t *)((char *)v12 + v11 - (char *)L"\\Program Files\\WindowsApps\\")) != v13 )
            break;
          ++v12;
        }
        while ( *(const wchar_t *)((char *)v12 + v11 - (char *)L"\\Program Files\\WindowsApps\\") );
        v5 = (unsigned int)FileHandle;
        v4 = a4;
      }
      if ( !*v12 )
        return 0;
      v11 += 2;
      v7 = *(_WORD *)v11;
    }
    while ( *(_WORD *)v11 );
  }
  if ( a1 )
  {
    v14 = *(_QWORD *)(a1 + 64);
    v15 = a1;
    if ( v14 )
      v15 = *(_QWORD *)(a1 + 64);
    if ( (*(_DWORD *)(v15 + 36) & 0x40000000) == 0 )
    {
      v16 = v14 ? *(_QWORD **)(v14 + 176) : *(_QWORD **)(a1 + 176);
      if ( v16 ? *v16 : 0LL )
      {
        if ( !v4 )
          goto LABEL_55;
        if ( *v4 )
        {
          v18 = EnableShortnamesOnApplyTarget();
          if ( v18 < 0 )
            UtilReportError(L"WIMSetFileShortName", v19, 615, (unsigned int)v18);
          v20 = a1;
          if ( *(_QWORD *)(a1 + 64) )
            v20 = *(_QWORD *)(a1 + 64);
          LODWORD(FileHandle) = *(_DWORD *)(v20 + 36) | 0x40000000;
          SetImageFlags(a1, &FileHandle, 0);
        }
      }
    }
  }
  if ( v4 )
  {
    *(_QWORD *)&NtPathName.Length = 0;
    NtPathName.Buffer = 0;
    if ( RtlDosPathNameToNtPathName_U(a3, &NtPathName, 0, 0) )
    {
      IoStatusBlock.Pointer = 0;
      IoStatusBlock.Information = 0;
      FileHandle = 0;
      *(_QWORD *)&ObjectAttributes.Length = 48;
      *(_QWORD *)&ObjectAttributes.Attributes = 64;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.ObjectName = &NtPathName;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( NtCreateFile(&FileHandle, 0x100080u, &ObjectAttributes, &IoStatusBlock, 0, 0x80u, 7u, 1u, 0x4020u, 0, 0) >= 0 )
      {
        ProcessHeap = GetProcessHeap();
        v22 = (wchar_t *)HeapAlloc(ProcessHeap, 0, 0x28u);
        if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, v22, 0x28u, FileAlternateNameInformation) >= 0 )
        {
          v23 = -1;
          do
            ++v23;
          while ( v4[v23] );
          if ( !wcsncmp(v4, v22 + 2, v23) )
          {
            if ( v22 )
            {
              v24 = GetProcessHeap();
              HeapFree(v24, 0, v22);
            }
            NtClose(FileHandle);
            return 0;
          }
        }
        if ( v22 )
        {
          v26 = GetProcessHeap();
          HeapFree(v26, 0, v22);
        }
        NtClose(FileHandle);
      }
    }
    v27 = -1;
    do
      ++v27;
    while ( v4[v27] );
    v5 = 2 * v27;
    v28 = 2 * v27 + 10;
    goto LABEL_56;
  }
LABEL_55:
  v4 = (const wchar_t *)&qword_180068440;
  v28 = 8;
LABEL_56:
  v29 = GetProcessHeap();
  v30 = (unsigned __int16 *)HeapAlloc(v29, 8u, v28);
  v31 = 0;
  if ( v30 )
    goto LABEL_65;
  LastError = GetLastError();
  v33 = (unsigned __int16)LastError | 0x80070000;
  if ( LastError <= 0 )
    v33 = LastError;
  if ( v33 >= 0 )
  {
    v31 = -2147467259;
  }
  else
  {
    v34 = GetLastError();
    v31 = (unsigned __int16)v34 | 0x80070000;
    if ( v34 <= 0 )
      v31 = v34;
  }
  if ( v31 >= 0 )
  {
LABEL_65:
    *(_DWORD *)v30 = v5;
    if ( v5 )
      v31 = StringCchCopyW(v30 + 2, ((unsigned __int64)v5 >> 1) + 1, v4);
    if ( v31 >= 0 )
    {
      IoStatusBlock.Pointer = 0;
      IoStatusBlock.Information = 0;
      v35 = NtSetInformationFile(a2, &IoStatusBlock, v30, v28, FileShortNameInformation);
      if ( v35 < 0 )
        v31 = v35 | 0x10000000;
    }
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v30);
  }
  return (unsigned int)v31;
}

```

## disassembly

```asm
0x180020cc8  mov     rax, rsp
0x180020ccb  mov     [rax+18h], rbx
0x180020ccf  mov     [rax+20h], r9
0x180020cd3  mov     [rax+10h], rdx
0x180020cd7  mov     [rax+8], rcx
0x180020cdb  push    rbp
0x180020cdc  push    rsi
0x180020cdd  push    rdi
0x180020cde  push    r12
0x180020ce0  push    r13
0x180020ce2  push    r14
0x180020ce4  push    r15
0x180020ce6  lea     rbp, [rax-5Fh]
0x180020cea  sub     rsp, 0C0h
0x180020cf1  xor     r13d, r13d
0x180020cf4  mov     r15, r9
0x180020cf7  mov     r14d, r13d
0x180020cfa  mov     r12, r8
0x180020cfd  mov     [rbp+57h+FileHandle], r14
0x180020d01  mov     rax, rdx
0x180020d04  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x180020d08  jz      loc_18002116B
0x180020d0e  test    r8, r8
0x180020d11  jz      loc_18002116B
0x180020d17  movzx   eax, word ptr [r8]
0x180020d1b  mov     rsi, r8
0x180020d1e  cmp     r13w, ax
0x180020d22  jz      short loc_180020D9F
0x180020d24  lea     rcx, aWindowsWinsxs; "\\Windows\\WinSxS\\"
0x180020d2b  mov     rdi, rcx
0x180020d2e  cmp     r13w, ax
0x180020d32  jz      short loc_180020D83
0x180020d34  xor     r15d, r15d
0x180020d37  lea     r14, aWindowsWinsxs; "\\Windows\\WinSxS\\"
0x180020d3e  cmp     r15w, [rdi]
0x180020d42  jz      short loc_180020D71
0x180020d44  mov     r13, rsi
0x180020d47  sub     r13, r14
0x180020d4a  movzx   ecx, word ptr [rdi+r13]; C
0x180020d4f  call    towupper_0
0x180020d54  movzx   ecx, word ptr [rdi]; C
0x180020d57  movzx   ebx, ax
0x180020d5a  call    towupper_0
0x180020d5f  movzx   eax, ax
0x180020d62  cmp     ebx, eax
0x180020d64  jnz     short loc_180020D71
0x180020d66  add     rdi, 2
0x180020d6a  cmp     r15w, [rdi+r13]
0x180020d6f  jnz     short loc_180020D3E
0x180020d71  mov     r14, [rbp+57h+FileHandle]
0x180020d75  lea     rcx, aWindowsWinsxs; "\\Windows\\WinSxS\\"
0x180020d7c  mov     r15, [rbp+57h+arg_18]
0x180020d80  xor     r13d, r13d
0x180020d83  cmp     r13w, [rdi]
0x180020d87  jz      loc_18002101B
0x180020d8d  add     rsi, 2
0x180020d91  movzx   eax, word ptr [rsi]
0x180020d94  cmp     r13w, ax
0x180020d98  jnz     short loc_180020D2B
0x180020d9a  movzx   eax, word ptr [r12]
0x180020d9f  mov     rsi, r12
0x180020da2  cmp     r13w, ax
0x180020da6  jz      short loc_180020E1E
0x180020da8  lea     rcx, aProgramFilesWi; "\\Program Files\\WindowsApps\\"
0x180020daf  mov     rdi, rcx
0x180020db2  cmp     r13w, ax
0x180020db6  jz      short loc_180020E07
0x180020db8  xor     r15d, r15d
0x180020dbb  lea     r14, aProgramFilesWi; "\\Program Files\\WindowsApps\\"
0x180020dc2  movzx   ecx, word ptr [rdi]; C
0x180020dc5  cmp     r15w, cx
0x180020dc9  jz      short loc_180020DF5
0x180020dcb  call    towupper_0
0x180020dd0  mov     r13, rsi
0x180020dd3  movzx   ebx, ax
0x180020dd6  sub     r13, r14
0x180020dd9  movzx   ecx, word ptr [rdi+r13]; C
0x180020dde  call    towupper_0
0x180020de3  movzx   eax, ax
0x180020de6  sub     eax, ebx
0x180020de8  jnz     short loc_180020DF5
0x180020dea  add     rdi, 2
0x180020dee  cmp     r15w, [rdi+r13]
0x180020df3  jnz     short loc_180020DC2
0x180020df5  mov     r14, [rbp+57h+FileHandle]
0x180020df9  lea     rcx, aProgramFilesWi; "\\Program Files\\WindowsApps\\"
0x180020e00  mov     r15, [rbp+57h+arg_18]
0x180020e04  xor     r13d, r13d
0x180020e07  cmp     r13w, [rdi]
0x180020e0b  jz      loc_18002101B
0x180020e11  add     rsi, 2
0x180020e15  movzx   eax, word ptr [rsi]
0x180020e18  cmp     r13w, ax
0x180020e1c  jnz     short loc_180020DAF
0x180020e1e  mov     rbx, [rbp+57h+arg_0]
0x180020e22  test    rbx, rbx
0x180020e25  jz      loc_180020EBA
0x180020e2b  mov     rcx, [rbx+40h]
0x180020e2f  mov     rax, rbx
0x180020e32  test    rcx, rcx
0x180020e35  mov     edi, 40000000h
0x180020e3a  cmovnz  rax, rcx
0x180020e3e  test    [rax+24h], edi
0x180020e41  jnz     short loc_180020EBA
0x180020e43  test    rcx, rcx
0x180020e46  jz      short loc_180020E51
0x180020e48  mov     rax, [rcx+0B0h]
0x180020e4f  jmp     short loc_180020E58
0x180020e51  mov     rax, [rbx+0B0h]
0x180020e58  test    rax, rax
0x180020e5b  jz      short loc_180020E62
0x180020e5d  mov     rdx, [rax]
0x180020e60  jmp     short loc_180020E65
0x180020e62  mov     rdx, r13
0x180020e65  test    rdx, rdx
0x180020e68  jz      short loc_180020EBA
0x180020e6a  test    r15, r15
0x180020e6d  jz      loc_180021071
0x180020e73  cmp     [r15], r13w
0x180020e77  jz      short loc_180020EBA
0x180020e79  call    EnableShortnamesOnApplyTarget
0x180020e7e  test    eax, eax
0x180020e80  jns     short loc_180020E97
0x180020e82  mov     r9d, eax
0x180020e85  lea     rcx, aWimsetfileshor; "WIMSetFileShortName"
0x180020e8c  mov     r8d, 267h
0x180020e92  call    UtilReportError
0x180020e97  cmp     [rbx+40h], r13
0x180020e9b  lea     rdx, [rbp+57h+FileHandle]
0x180020e9f  mov     rax, rbx
0x180020ea2  mov     rcx, rbx
0x180020ea5  cmovnz  rax, [rbx+40h]
0x180020eaa  xor     r8d, r8d
0x180020ead  mov     eax, [rax+24h]
0x180020eb0  or      eax, edi
0x180020eb2  mov     dword ptr [rbp+57h+FileHandle], eax
0x180020eb5  call    SetImageFlags
0x180020eba  test    r15, r15
0x180020ebd  jz      loc_180021071
0x180020ec3  xor     eax, eax
0x180020ec5  lea     rdx, [rbp+57h+NtPathName]; NtPathName
0x180020ec9  xor     r9d, r9d; DirectoryInfo
0x180020ecc  mov     qword ptr [rbp+57h+NtPathName.Length], rax
0x180020ed0  xor     r8d, r8d; NtFileNamePart
0x180020ed3  mov     [rbp+57h+NtPathName.Buffer], rax
0x180020ed7  mov     rcx, r12; DosPathName
0x180020eda  call    cs:__imp_RtlDosPathNameToNtPathName_U
0x180020ee1  nop     dword ptr [rax+rax+00h]
0x180020ee6  test    al, al
0x180020ee8  jz      loc_180021057
0x180020eee  mov     [rsp+50h], r13d; EaLength
0x180020ef3  lea     r9, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180020ef7  mov     [rsp+0F0h+EaBuffer], r13; EaBuffer
0x180020efc  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x180020f00  xor     eax, eax
0x180020f02  mov     [rsp+0F0h+CreateOptions], 4020h; CreateOptions
0x180020f0a  mov     [rsp+0F0h+CreateDisposition], 1; CreateDisposition
0x180020f12  lea     rcx, [rbp+57h+FileHandle]; FileHandle
0x180020f16  mov     qword ptr [rbp+57h+IoStatusBlock], rax
0x180020f1a  xorps   xmm0, xmm0
0x180020f1d  mov     [rbp+57h+IoStatusBlock.Information], rax
0x180020f21  mov     edx, 100080h; DesiredAccess
0x180020f26  mov     [rsp+0F0h+ShareAccess], 7; ShareAccess
0x180020f2e  lea     rax, [rbp+57h+NtPathName]
0x180020f32  mov     [rsp+0F0h+FileAttributes], 80h; FileAttributes
0x180020f3a  mov     [rsp+0F0h+AllocationSize], r13; AllocationSize
0x180020f3f  mov     [rbp+57h+FileHandle], r13
0x180020f43  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x180020f4b  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x180020f53  mov     [rbp+57h+ObjectAttributes.RootDirectory], r13
0x180020f57  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x180020f5b  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x180020f60  call    cs:__imp_NtCreateFile
0x180020f67  nop     dword ptr [rax+rax+00h]
0x180020f6c  test    eax, eax
0x180020f6e  js      loc_180021057
0x180020f74  call    cs:__imp_GetProcessHeap
0x180020f7b  nop     dword ptr [rax+rax+00h]
0x180020f80  xor     edx, edx; dwFlags
0x180020f82  mov     rcx, rax; hHeap
0x180020f85  lea     r8d, [rdx+28h]; dwBytes
0x180020f89  call    cs:__imp_HeapAlloc
0x180020f90  nop     dword ptr [rax+rax+00h]
0x180020f95  mov     rcx, [rbp+57h+FileHandle]; FileHandle
0x180020f99  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180020f9d  mov     r8, rax; FileInformation
0x180020fa0  mov     dword ptr [rsp+0F0h+AllocationSize], 15h; FileInformationClass
0x180020fa8  mov     r9d, 28h ; '('; Length
0x180020fae  mov     rbx, rax
0x180020fb1  call    cs:__imp_NtQueryInformationFile
0x180020fb8  nop     dword ptr [rax+rax+00h]
0x180020fbd  test    eax, eax
0x180020fbf  js      short loc_180021022
0x180020fc1  or      r8, 0FFFFFFFFFFFFFFFFh
0x180020fc5  inc     r8; MaxCount
0x180020fc8  cmp     [r15+r8*2], r13w
0x180020fcd  jnz     short loc_180020FC5
0x180020fcf  lea     rdx, [rbx+4]; String2
0x180020fd3  mov     rcx, r15; String1
0x180020fd6  call    cs:__imp_wcsncmp
0x180020fdd  nop     dword ptr [rax+rax+00h]
0x180020fe2  test    eax, eax
0x180020fe4  jnz     short loc_180021022
0x180020fe6  test    rbx, rbx
0x180020fe9  jz      short loc_18002100B
0x180020feb  call    cs:__imp_GetProcessHeap
0x180020ff2  nop     dword ptr [rax+rax+00h]
0x180020ff7  mov     r8, rbx; lpMem
0x180020ffa  xor     edx, edx; dwFlags
0x180020ffc  mov     rcx, rax; hHeap
0x180020fff  call    cs:__imp_HeapFree
0x180021006  nop     dword ptr [rax+rax+00h]
0x18002100b  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002100f  call    cs:__imp_NtClose
0x180021016  nop     dword ptr [rax+rax+00h]
0x18002101b  xor     eax, eax
0x18002101d  jmp     loc_180021170
0x180021022  test    rbx, rbx
0x180021025  jz      short loc_180021047
0x180021027  call    cs:__imp_GetProcessHeap
0x18002102e  nop     dword ptr [rax+rax+00h]
0x180021033  mov     r8, rbx; lpMem
0x180021036  xor     edx, edx; dwFlags
0x180021038  mov     rcx, rax; hHeap
0x18002103b  call    cs:__imp_HeapFree
0x180021042  nop     dword ptr [rax+rax+00h]
0x180021047  mov     rcx, [rbp+57h+FileHandle]; Handle
0x18002104b  call    cs:__imp_NtClose
0x180021052  nop     dword ptr [rax+rax+00h]
0x180021057  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002105b  inc     rax
0x18002105e  cmp     [r15+rax*2], r13w
0x180021063  jnz     short loc_18002105B
0x180021065  mov     r14, rax
0x180021068  add     r14d, r14d
0x18002106b  lea     esi, [r14+0Ah]
0x18002106f  jmp     short loc_18002107D
0x180021071  lea     r15, qword_180068440
0x180021078  mov     esi, 8
0x18002107d  call    cs:__imp_GetProcessHeap
0x180021084  nop     dword ptr [rax+rax+00h]
0x180021089  mov     r8d, esi; dwBytes
0x18002108c  mov     edx, 8; dwFlags
0x180021091  mov     rcx, rax; hHeap
0x180021094  call    cs:__imp_HeapAlloc
0x18002109b  nop     dword ptr [rax+rax+00h]
0x1800210a0  mov     rdi, rax
0x1800210a3  mov     ebx, r13d
0x1800210a6  test    rax, rax
0x1800210a9  jnz     short loc_1800210EE
0x1800210ab  call    cs:__imp_GetLastError
0x1800210b2  nop     dword ptr [rax+rax+00h]
0x1800210b7  movzx   ecx, ax
0x1800210ba  mov     r12d, 80070000h
0x1800210c0  or      ecx, r12d
0x1800210c3  test    eax, eax
0x1800210c5  cmovle  ecx, eax
0x1800210c8  test    ecx, ecx
0x1800210ca  jns     short loc_1800210E5
0x1800210cc  call    cs:__imp_GetLastError
0x1800210d3  nop     dword ptr [rax+rax+00h]
0x1800210d8  movzx   ebx, ax
0x1800210db  or      ebx, r12d
0x1800210de  test    eax, eax
0x1800210e0  cmovle  ebx, eax
0x1800210e3  jmp     short loc_1800210EA
0x1800210e5  mov     ebx, 80004005h
0x1800210ea  test    ebx, ebx
0x1800210ec  js      short loc_180021167
0x1800210ee  mov     [rdi], r14d
0x1800210f1  test    r14d, r14d
0x1800210f4  jz      short loc_18002110D
0x1800210f6  mov     edx, r14d
0x1800210f9  lea     rcx, [rdi+4]; unsigned __int16 *
0x1800210fd  shr     rdx, 1
0x180021100  mov     r8, r15; unsigned __int16 *
0x180021103  inc     rdx; unsigned __int64
0x180021106  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002110b  mov     ebx, eax
0x18002110d  test    ebx, ebx
0x18002110f  js      short loc_180021147
0x180021111  mov     rcx, [rbp+57h+arg_8]; FileHandle
0x180021115  lea     rdx, [rbp+57h+IoStatusBlock]; IoStatusBlock
0x180021119  xor     eax, eax
0x18002111b  mov     dword ptr [rsp+0F0h+AllocationSize], 28h ; '('; FileInformationClass
0x180021123  mov     r9d, esi; Length
0x180021126  mov     qword ptr [rbp+57h+IoStatusBlock], rax
0x18002112a  mov     r8, rdi; FileInformation
0x18002112d  mov     [rbp+57h+IoStatusBlock.Information], rax
0x180021131  call    cs:__imp_NtSetInformationFile
0x180021138  nop     dword ptr [rax+rax+00h]
0x18002113d  test    eax, eax
0x18002113f  jns     short loc_180021147
0x180021141  mov     ebx, eax
0x180021143  bts     ebx, 1Ch
0x180021147  call    cs:__imp_GetProcessHeap
0x18002114e  nop     dword ptr [rax+rax+00h]
0x180021153  mov     r8, rdi; lpMem
0x180021156  xor     edx, edx; dwFlags
0x180021158  mov     rcx, rax; hHeap
  ... truncated ...
```
