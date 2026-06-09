# SearchForScrEntries(uint,ushort const *)

- ea: `0x1800478f4`
- end: `0x180047bb5`
- name: `?SearchForScrEntries@@YAXIPEBG@Z`
- size: `705`
- prototype: `void(unsigned int, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0x180021470`
- `0x180047cb8`

## callees

- `0x18000ab10`
- `0x1800358c0`
- `0x18003633c`
- `0x180046980`
- `0x180046a70`
- `0x1800478f4`
- `0x180047bbc`

## import_xrefs

- `SHELL32!ExtractIconW` at `0x180047b23`
- `SHELL32!ExtractIconW` at `0x180047b23`
- `SHLWAPI!StrDupW` at `0x180047afe`
- `SHLWAPI!StrDupW` at `0x180047afe`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004798e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18004798e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b68`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047b68`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180047a10`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180047a10`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800479f3`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x1800479f3`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180047a6f`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180047a6f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180047b90`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180047b90`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180047b76`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180047b76`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800479c1`
- `api-ms-win-core-wow64-l1-1-1!GetSystemWow64DirectoryW` at `0x1800479c1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180047a2c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180047ae9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180047a2c`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x180047ae9`

## pseudocode

```c
void __fastcall SearchForScrEntries(int a1, const unsigned __int16 *a2)
{
  unsigned int v4; // edx
  int v5; // ebx
  int v6; // ebx
  UINT SystemDirectoryW; // eax
  HANDLE FirstFileW; // rsi
  unsigned int v9; // edx
  WCHAR *v10; // rdi
  __int64 i; // rbx
  unsigned __int16 **v12; // rbx
  HICON *IconW; // rax
  __int64 v14; // rdx
  _WIN32_FIND_DATAW FindFileData; // [rsp+20h] [rbp-E0h] BYREF
  WCHAR Buffer[264]; // [rsp+270h] [rbp+170h] BYREF
  WCHAR Filename[264]; // [rsp+480h] [rbp+380h] BYREF

  memset_0(Filename, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  if ( g_wNumMethods >= 0x64 || g_fScanSystemDirOnly && a1 )
    return;
  GetModuleFileNameW(g_hinst, Filename, 0x104u);
  StripPathName(Filename);
  if ( !a1 )
  {
    SystemDirectoryW = GetSystemDirectoryW(Buffer, 0x104u);
LABEL_13:
    if ( !SystemDirectoryW )
      return;
    goto LABEL_14;
  }
  v5 = a1 - 2;
  if ( !v5 )
  {
    if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
      Buffer[0] = 0;
    goto LABEL_14;
  }
  v6 = v5 - 1;
  if ( !v6 )
  {
    StringCchCopyW(Buffer, 0x104u, a2);
    StripPathName(Buffer);
LABEL_14:
    if ( !lstrcmpiW(Filename, Buffer) )
      return;
    StringCchCopyW(Filename, 0x104u, Buffer);
    goto LABEL_16;
  }
  if ( v6 == 1 )
  {
    SystemDirectoryW = GetSystemWow64DirectoryW(Buffer, 0x104u);
    goto LABEL_13;
  }
LABEL_16:
  AppendPath(Filename, v4, L"*.scr");
  FirstFileW = FindFirstFileW(Filename, &FindFileData);
  if ( FirstFileW != (HANDLE)-1LL )
  {
    StripPathName(Filename);
    do
    {
      StringCchCopyW(Buffer, 0x104u, Filename);
      AppendPath(Buffer, v9, FindFileData.cFileName);
      v10 = CheckFileAndGetDisplayName(Buffer);
      if ( v10 )
      {
        for ( i = 0; (unsigned int)i < g_wNumMethods; i = (unsigned int)(i + 1) )
        {
          if ( !lstrcmpiW(v10, (LPCWSTR)(&g_aszMethods)[i]) )
            goto LABEL_28;
        }
        v12 = (unsigned __int16 **)StrDupW(Buffer);
        if ( v12 )
        {
          if ( *v10 == 80 )
          {
            v14 = g_wNumMethods;
            (&g_hIcons)[g_wNumMethods] = 0;
          }
          else
          {
            IconW = (HICON *)ExtractIconW(g_hinst, Buffer, 0);
            v14 = g_wNumMethods;
            (&g_hIcons)[g_wNumMethods] = IconW;
          }
          (&g_aszMethods)[v14] = (unsigned __int16 * near *)v10;
          (&g_aszFiles)[v14] = v12;
          g_wNumMethods = v14 + 1;
          v10 = 0;
        }
LABEL_28:
        LocalFree(v10);
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) && g_wNumMethods < 0x64 );
    FindClose(FirstFileW);
  }
}

```

## disassembly

```asm
0x1800478f4  push    rbp
0x1800478f6  push    rbx
0x1800478f7  push    rsi
0x1800478f8  push    rdi
0x1800478f9  push    r14
0x1800478fb  push    r15
0x1800478fd  lea     rbp, [rsp-5A8h]
0x180047905  sub     rsp, 6A8h
0x18004790c  mov     rax, cs:__security_cookie
0x180047913  xor     rax, rsp
0x180047916  mov     [rbp+5D0h+var_40], rax
0x18004791d  mov     rdi, rdx
0x180047920  mov     ebx, ecx
0x180047922  mov     esi, 208h
0x180047927  lea     rcx, [rbp+5D0h+Filename]; void *
0x18004792e  mov     r8d, esi; Size
0x180047931  xor     edx, edx; Val
0x180047933  call    memset_0
0x180047938  mov     r8d, esi; Size
0x18004793b  lea     rcx, [rbp+5D0h+Buffer]; void *
0x180047942  xor     edx, edx; Val
0x180047944  call    memset_0
0x180047949  xor     edx, edx; Val
0x18004794b  lea     r8d, [rsi+48h]; Size
0x18004794f  lea     rcx, [rsp+6D0h+FindFileData]; void *
0x180047954  call    memset_0
0x180047959  cmp     cs:?g_wNumMethods@@3IA, 64h ; 'd'; uint g_wNumMethods
0x180047960  jnb     loc_180047B96
0x180047966  cmp     cs:?g_fScanSystemDirOnly@@3HA, 0; int g_fScanSystemDirOnly
0x18004796d  jz      short loc_180047977
0x18004796f  test    ebx, ebx
0x180047971  jnz     loc_180047B96
0x180047977  mov     rcx, cs:g_hinst; hModule
0x18004797e  lea     rdx, [rbp+5D0h+Filename]; lpFilename
0x180047985  mov     r14d, 104h
0x18004798b  mov     r8d, r14d; nSize
0x18004798e  call    cs:__imp_GetModuleFileNameW
0x180047994  lea     rcx, [rbp+5D0h+Filename]; unsigned __int16 *
0x18004799b  call    ?StripPathName@@YAPEAGPEAG@Z; StripPathName(ushort *)
0x1800479a0  test    ebx, ebx
0x1800479a2  jz      short loc_180047A06
0x1800479a4  sub     ebx, 2
0x1800479a7  jz      short loc_1800479E9
0x1800479a9  sub     ebx, 1
0x1800479ac  jz      short loc_1800479C9
0x1800479ae  cmp     ebx, 1
0x1800479b1  jnz     loc_180047A50
0x1800479b7  mov     edx, r14d; uSize
0x1800479ba  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x1800479c1  call    cs:__imp_GetSystemWow64DirectoryW
0x1800479c7  jmp     short loc_180047A16
0x1800479c9  mov     r8, rdi; unsigned __int16 *
0x1800479cc  lea     rcx, [rbp+5D0h+Buffer]; unsigned __int16 *
0x1800479d3  mov     rdx, r14; unsigned __int64
0x1800479d6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800479db  lea     rcx, [rbp+5D0h+Buffer]; unsigned __int16 *
0x1800479e2  call    ?StripPathName@@YAPEAGPEAG@Z; StripPathName(ushort *)
0x1800479e7  jmp     short loc_180047A1E
0x1800479e9  mov     edx, r14d; uSize
0x1800479ec  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x1800479f3  call    cs:__imp_GetWindowsDirectoryW
0x1800479f9  test    eax, eax
0x1800479fb  jnz     short loc_180047A1E
0x1800479fd  mov     [rbp+5D0h+Buffer], ax
0x180047a04  jmp     short loc_180047A1E
0x180047a06  mov     edx, r14d; uSize
0x180047a09  lea     rcx, [rbp+5D0h+Buffer]; lpBuffer
0x180047a10  call    cs:__imp_GetSystemDirectoryW
0x180047a16  test    eax, eax
0x180047a18  jz      loc_180047B96
0x180047a1e  lea     rdx, [rbp+5D0h+Buffer]; lpString2
0x180047a25  lea     rcx, [rbp+5D0h+Filename]; lpString1
0x180047a2c  call    cs:__imp_lstrcmpiW
0x180047a32  test    eax, eax
0x180047a34  jz      loc_180047B96
0x180047a3a  lea     r8, [rbp+5D0h+Buffer]; unsigned __int16 *
0x180047a41  mov     rdx, r14; unsigned __int64
0x180047a44  lea     rcx, [rbp+5D0h+Filename]; unsigned __int16 *
0x180047a4b  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047a50  lea     r8, aScr; "*.scr"
0x180047a57  lea     rcx, [rbp+5D0h+Filename]; unsigned __int16 *
0x180047a5e  call    ?AppendPath@@YAXPEAGKPEBG@Z; AppendPath(ushort *,ulong,ushort const *)
0x180047a63  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x180047a68  lea     rcx, [rbp+5D0h+Filename]; lpFileName
0x180047a6f  call    cs:__imp_FindFirstFileW
0x180047a75  mov     rsi, rax
0x180047a78  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180047a7c  jz      loc_180047B96
0x180047a82  lea     rcx, [rbp+5D0h+Filename]; unsigned __int16 *
0x180047a89  call    ?StripPathName@@YAPEAGPEAG@Z; StripPathName(ushort *)
0x180047a8e  lea     r15, __ImageBase
0x180047a95  lea     r8, [rbp+5D0h+Filename]; unsigned __int16 *
0x180047a9c  mov     rdx, r14; unsigned __int64
0x180047a9f  lea     rcx, [rbp+5D0h+Buffer]; unsigned __int16 *
0x180047aa6  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180047aab  lea     r8, [rsp+6D0h+FindFileData.cFileName]; unsigned __int16 *
0x180047ab0  lea     rcx, [rbp+5D0h+Buffer]; unsigned __int16 *
0x180047ab7  call    ?AppendPath@@YAXPEAGKPEBG@Z; AppendPath(ushort *,ulong,ushort const *)
0x180047abc  lea     rcx, [rbp+5D0h+Buffer]; unsigned __int16 *
0x180047ac3  call    ?CheckFileAndGetDisplayName@@YAPEAGPEBG@Z; CheckFileAndGetDisplayName(ushort const *)
0x180047ac8  mov     rdi, rax
0x180047acb  test    rax, rax
0x180047ace  jz      loc_180047B6E
0x180047ad4  xor     ebx, ebx
0x180047ad6  cmp     ebx, cs:?g_wNumMethods@@3IA; uint g_wNumMethods
0x180047adc  jnb     short loc_180047AF7
0x180047ade  mov     rdx, rva ?g_aszMethods@@3PAPEAGA[r15+rbx*8]; lpString2
0x180047ae6  mov     rcx, rdi; lpString1
0x180047ae9  call    cs:__imp_lstrcmpiW
0x180047aef  test    eax, eax
0x180047af1  jz      short loc_180047B65
0x180047af3  inc     ebx
0x180047af5  jmp     short loc_180047AD6
0x180047af7  lea     rcx, [rbp+5D0h+Buffer]; pszSrch
0x180047afe  call    cs:__imp_StrDupW
0x180047b04  mov     rbx, rax
0x180047b07  test    rax, rax
0x180047b0a  jz      short loc_180047B65
0x180047b0c  cmp     word ptr [rdi], 50h ; 'P'
0x180047b10  jz      short loc_180047B39
0x180047b12  mov     rcx, cs:g_hinst; hInst
0x180047b19  lea     rdx, [rbp+5D0h+Buffer]; pszExeFileName
0x180047b20  xor     r8d, r8d; nIconIndex
0x180047b23  call    cs:__imp_ExtractIconW
0x180047b29  mov     edx, cs:?g_wNumMethods@@3IA; uint g_wNumMethods
0x180047b2f  mov     rva ?g_hIcons@@3PAPEAUHICON__@@A[r15+rdx*8], rax; HICON__ * near * g_hIcons ...
0x180047b37  jmp     short loc_180047B4B
0x180047b39  mov     edx, cs:?g_wNumMethods@@3IA; uint g_wNumMethods
0x180047b3f  mov     rva ?g_hIcons@@3PAPEAUHICON__@@A[r15+rdx*8], 0; HICON__ * near * g_hIcons ...
0x180047b4b  mov     rva ?g_aszMethods@@3PAPEAGA[r15+rdx*8], rdi; ushort * near * g_aszMethods ...
0x180047b53  mov     rva ?g_aszFiles@@3PAPEAGA[r15+rdx*8], rbx; ushort * near * g_aszFiles ...
0x180047b5b  inc     edx
0x180047b5d  mov     cs:?g_wNumMethods@@3IA, edx; uint g_wNumMethods
0x180047b63  xor     edi, edi
0x180047b65  mov     rcx, rdi; hMem
0x180047b68  call    cs:__imp_LocalFree
0x180047b6e  lea     rdx, [rsp+6D0h+FindFileData]; lpFindFileData
0x180047b73  mov     rcx, rsi; hFindFile
0x180047b76  call    cs:__imp_FindNextFileW
0x180047b7c  test    eax, eax
0x180047b7e  jz      short loc_180047B8D
0x180047b80  cmp     cs:?g_wNumMethods@@3IA, 64h ; 'd'; uint g_wNumMethods
0x180047b87  jb      loc_180047A95
0x180047b8d  mov     rcx, rsi; hFindFile
0x180047b90  call    cs:__imp_FindClose
0x180047b96  mov     rcx, [rbp+5D0h+var_40]
0x180047b9d  xor     rcx, rsp; StackCookie
0x180047ba0  call    __security_check_cookie
0x180047ba5  add     rsp, 6A8h
0x180047bac  pop     r15
0x180047bae  pop     r14
0x180047bb0  pop     rdi
0x180047bb1  pop     rsi
0x180047bb2  pop     rbx
0x180047bb3  pop     rbp
0x180047bb4  retn
```
