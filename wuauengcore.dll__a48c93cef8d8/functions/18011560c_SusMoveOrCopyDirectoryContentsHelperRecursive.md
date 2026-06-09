# SusMoveOrCopyDirectoryContentsHelperRecursive

- ea: `0x18011560c`
- end: `0x180115a0b`
- name: `SusMoveOrCopyDirectoryContentsHelperRecursive`
- size: `1023`
- prototype: `__int64 __fastcall(wchar_t **, unsigned __int64 *, wchar_t **, unsigned __int64 *, LPWIN32_FIND_DATAW lpFindFileData, int, BOOL bFailIfExists, int, int, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops`

## callers

- `0x18011560c`
- `0x180115a14`

## callees

- `0x18000def4`
- `0x18000df20`
- `0x1801140a0`
- `0x18011511c`
- `0x180115324`
- `0x18011560c`
- `0x180115d38`
- `0x180115e40`
- `0x18012b618`
- `0x180238960`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011570f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115868`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18011570f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115723`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180115868`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801158ba`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1801158ba`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801159e3`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801159e3`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180115853`
- `api-ms-win-core-file-l1-1-0!RemoveDirectoryW` at `0x180115853`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180115705`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180115705`

## string_xrefs

- `0x180115748`: `CreateDirectory() failed to create %ws`
- `0x180115887`: `RemoveDirectory() failed to remove %ws`

## pseudocode

```c
// Hidden C++ exception states: #wind=48
__int64 __fastcall SusMoveOrCopyDirectoryContentsHelperRecursive(
        wchar_t **a1,
        unsigned __int64 *a2,
        wchar_t **a3,
        unsigned __int64 *a4,
        LPWIN32_FIND_DATAW lpFindFileData,
        int a6,
        BOOL bFailIfExists,
        int a8,
        int a9,
        void *a10)
{
  __int64 v10; // rax
  __int64 v11; // rax
  int FirstFile; // eax
  unsigned int v13; // ebx
  __int64 v14; // rdx
  unsigned __int64 v15; // r9
  wchar_t *v16; // rbx
  signed int LastError; // eax
  signed int v18; // ecx
  const char *v19; // r9
  unsigned __int64 v20; // r9
  __int64 v21; // r9
  wchar_t *v22; // rbx
  signed int v23; // eax
  signed int v24; // ecx
  wchar_t *v25; // rdx
  wchar_t *v26; // rcx
  unsigned int v27; // eax
  unsigned __int64 v28; // r9
  const wchar_t *v29; // rdx
  int v31; // [rsp+20h] [rbp-A1h]
  HANDLE hFindFile; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int64 *v33; // [rsp+58h] [rbp-69h]
  unsigned __int64 *v34; // [rsp+60h] [rbp-61h]
  wchar_t ***v35; // [rsp+68h] [rbp-59h]
  __int64 *v36; // [rsp+70h] [rbp-51h]
  wchar_t ***v37; // [rsp+78h] [rbp-49h]
  __int64 *v38; // [rsp+80h] [rbp-41h]
  char v39; // [rsp+88h] [rbp-39h]
  wchar_t **v40; // [rsp+90h] [rbp-31h] BYREF
  wchar_t **v41; // [rsp+98h] [rbp-29h] BYREF
  __int64 v42; // [rsp+A0h] [rbp-21h] BYREF
  __int64 v43; // [rsp+A8h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v33 = a4;
  v34 = a2;
  v40 = a1;
  v41 = a3;
  hFindFile = (HANDLE)-1LL;
  v10 = -1;
  do
    ++v10;
  while ( (*a1)[v10] );
  v42 = v10;
  v11 = -1;
  do
    ++v11;
  while ( (*a3)[v11] );
  v43 = v11;
  v35 = &v40;
  v36 = &v42;
  v37 = &v41;
  v38 = &v43;
  v39 = 1;
  FirstFile = WUAppendPathReAlloc(a1, a2, L"*", (unsigned __int64)a2);
  v13 = FirstFile;
  if ( FirstFile < 0 )
  {
    v14 = 1221;
LABEL_45:
    v28 = (unsigned int)FirstFile;
    goto LABEL_46;
  }
  FirstFile = SusFindFirstFile(*v40, lpFindFileData, &hFindFile);
  v13 = FirstFile;
  if ( FirstFile == -2147024878 )
  {
    v13 = 0;
    goto LABEL_47;
  }
  if ( FirstFile < 0 )
  {
    v14 = 1227;
    goto LABEL_45;
  }
  if ( !CreateDirectoryW(*v41, 0) && GetLastError() != 183 )
  {
    v16 = *v41;
    LastError = GetLastError();
    v18 = (unsigned __int16)LastError | 0x80070000;
    if ( LastError <= 0 )
      v18 = LastError;
    if ( v18 >= 0 )
      v18 = -2147418113;
    WUTrace(0, 0, 32, 2, v18, L"CreateDirectory() failed to create %ws", v16);
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x4D7,
            (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
            v19);
    goto LABEL_47;
  }
  while ( 1 )
  {
    (*v40)[v42] = 0;
    (*v41)[v43] = 0;
    FirstFile = WUAppendPathReAlloc(v40, v34, lpFindFileData->cFileName, v15);
    v13 = FirstFile;
    if ( FirstFile < 0 )
    {
      v14 = 1249;
      goto LABEL_45;
    }
    v13 = WUAppendPathReAlloc(v41, v33, lpFindFileData->cFileName, v20);
    if ( (v13 & 0x80000000) != 0 )
    {
      v28 = v13;
      v14 = 1252;
      goto LABEL_46;
    }
    if ( (lpFindFileData->dwFileAttributes & 0x10) == 0 )
      break;
    v13 = SusMoveOrCopyDirectoryContentsHelperRecursive(
            (int)v40,
            (int)v34,
            (int)v41,
            (int)v33,
            lpFindFileData,
            1,
            bFailIfExists,
            a8,
            10,
            a10);
    if ( (int)(v13 + 0x80000000) >= 0 && v13 != -2147024893 )
    {
      v28 = v13;
      v14 = 1271;
      goto LABEL_46;
    }
    if ( !a8 && !RemoveDirectoryW(*v40) )
    {
      v22 = *v40;
      v23 = GetLastError();
      v24 = (unsigned __int16)v23 | 0x80070000;
      if ( v23 <= 0 )
        v24 = v23;
      if ( v24 >= 0 )
        v24 = -2147418113;
      WUTrace(0, 0, 32, 4, v24, L"RemoveDirectory() failed to remove %ws", v22);
    }
LABEL_37:
    if ( (int)SusFindNextFile(hFindFile, lpFindFileData) < 0 )
    {
      v13 = 0;
      goto LABEL_47;
    }
  }
  if ( !bFailIfExists )
    SetFileAttributesW(*v41, 0x80u);
  v25 = *v41;
  v26 = *v40;
  if ( a8 )
    v27 = SusCopyFileRetryIfSharingViolation(v26, v25, bFailIfExists, 10, a10);
  else
    v27 = SusMoveFileRetryIfSharingViolation(v26, v25, !bFailIfExists, v21, a10);
  v13 = v27;
  if ( (int)(v27 + 0x80000000) < 0 || v27 == -2147024894 )
    goto LABEL_37;
  v29 = L"move";
  if ( a8 )
    v29 = L"copy";
  WUTrace(0, 0, 32, 4, v27, L"Failed to %ws file from %ws to %ws", v29, *v40, *v41);
  v28 = v13;
  v14 = 1325;
LABEL_46:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v14,
    (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
    (const char *)v28,
    v31);
LABEL_47:
  (*v40)[v42] = 0;
  (*v41)[v43] = 0;
  if ( hFindFile != (HANDLE)-1LL )
    FindClose(hFindFile);
  return v13;
}

```

## disassembly

```asm
0x18011560c  push    rbp
0x18011560e  push    rbx
0x18011560f  push    rsi
0x180115610  push    rdi
0x180115611  push    r12
0x180115613  push    r13
0x180115615  push    r14
0x180115617  push    r15
0x180115619  lea     rbp, [rsp-7]
0x18011561e  sub     rsp, 0C8h
0x180115625  mov     rax, cs:__security_cookie
0x18011562c  xor     rax, rsp
0x18011562f  mov     [rbp+3Fh+var_50], rax
0x180115633  mov     [rbp+3Fh+var_A8], r9
0x180115637  mov     r9, rdx; unsigned __int64
0x18011563a  mov     [rbp+3Fh+var_A0], rdx
0x18011563e  mov     rdi, [rbp+3Fh+lpFindFileData]
0x180115642  mov     [rbp+3Fh+var_70], rcx
0x180115646  mov     [rbp+3Fh+var_68], r8
0x18011564a  mov     r14d, [rbp+3Fh+arg_38]
0x180115651  mov     r13, [rbp+3Fh+arg_48]
0x180115658  or      r10, 0FFFFFFFFFFFFFFFFh
0x18011565c  mov     [rbp+3Fh+hFindFile], r10
0x180115660  mov     rdx, [rcx]
0x180115663  mov     rax, r10
0x180115666  xor     esi, esi
0x180115668  inc     rax
0x18011566b  cmp     [rdx+rax*2], si
0x18011566f  jnz     short loc_180115668
0x180115671  mov     [rbp+3Fh+var_60], rax
0x180115675  mov     rdx, [r8]
0x180115678  mov     rax, r10
0x18011567b  inc     rax
0x18011567e  cmp     [rdx+rax*2], si
0x180115682  jnz     short loc_18011567B
0x180115684  mov     [rbp+3Fh+var_58], rax
0x180115688  lea     rax, [rbp+3Fh+var_70]
0x18011568c  mov     [rbp+3Fh+var_98], rax
0x180115690  lea     rax, [rbp+3Fh+var_60]
0x180115694  mov     [rbp+3Fh+var_90], rax
0x180115698  lea     rax, [rbp+3Fh+var_68]
0x18011569c  mov     [rbp+3Fh+var_88], rax
0x1801156a0  lea     rax, [rbp+3Fh+var_58]
0x1801156a4  mov     [rbp+3Fh+var_80], rax
0x1801156a8  mov     [rbp+3Fh+var_78], 1
0x1801156ac  lea     r8, asc_1802783E0; "*"
0x1801156b3  mov     rdx, r9; unsigned __int64 *
0x1801156b6  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x1801156bb  mov     ebx, eax
0x1801156bd  test    eax, eax
0x1801156bf  jns     short loc_1801156CB
0x1801156c1  mov     edx, 4C5h
0x1801156c6  jmp     loc_1801159A3
0x1801156cb  lea     r8, [rbp+3Fh+hFindFile]; void **
0x1801156cf  mov     rdx, rdi; struct _WIN32_FIND_DATAW *
0x1801156d2  mov     rcx, [rbp+3Fh+var_70]
0x1801156d6  mov     rcx, [rcx]; wchar_t *
0x1801156d9  call    ?SusFindFirstFile@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; SusFindFirstFile(wchar_t const *,_WIN32_FIND_DATAW *,void * *)
0x1801156de  mov     ebx, eax
0x1801156e0  cmp     eax, 80070012h
0x1801156e5  jnz     short loc_1801156EE
0x1801156e7  mov     ebx, esi
0x1801156e9  jmp     loc_1801159B6
0x1801156ee  test    eax, eax
0x1801156f0  jns     short loc_1801156FC
0x1801156f2  mov     edx, 4CBh
0x1801156f7  jmp     loc_1801159A3
0x1801156fc  xor     edx, edx; lpSecurityAttributes
0x1801156fe  mov     rcx, [rbp+3Fh+var_68]
0x180115702  mov     rcx, [rcx]; lpPathName
0x180115705  call    cs:__imp_CreateDirectoryW
0x18011570b  test    eax, eax
0x18011570d  jnz     short loc_180115785
0x18011570f  call    cs:__imp_GetLastError
0x180115715  cmp     eax, 0B7h
0x18011571a  jz      short loc_180115785
0x18011571c  mov     rax, [rbp+3Fh+var_68]
0x180115720  mov     rbx, [rax]
0x180115723  call    cs:__imp_GetLastError
0x180115729  movzx   ecx, ax
0x18011572c  or      ecx, 80070000h
0x180115732  test    eax, eax
0x180115734  cmovle  ecx, eax
0x180115737  mov     r12d, 8000FFFFh
0x18011573d  test    ecx, ecx
0x18011573f  cmovns  ecx, r12d
0x180115743  mov     qword ptr [rsp+100h+var_D0], rbx
0x180115748  lea     rax, aCreatedirector; "CreateDirectory() failed to create %ws"
0x18011574f  mov     qword ptr [rsp+100h+var_D8], rax
0x180115754  mov     dword ptr [rsp+100h+var_E0], ecx
0x180115758  xor     edx, edx
0x18011575a  xor     ecx, ecx
0x18011575c  lea     r9d, [rdx+2]
0x180115760  lea     r8d, [rdx+20h]
0x180115764  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x180115769  mov     rcx, [rbp+47h]; this
0x18011576d  lea     r8, aCW1SSrcClientL_66; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x180115774  mov     edx, 4D7h; void *
0x180115779  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18011577e  mov     ebx, eax
0x180115780  jmp     loc_1801159B6
0x180115785  mov     r12d, 8000FFFFh
0x18011578b  mov     esi, [rbp+3Fh+bFailIfExists]
0x18011578e  xor     r8d, r8d
0x180115791  mov     rax, [rbp+3Fh+var_70]
0x180115795  mov     rcx, [rax]
0x180115798  mov     rax, [rbp+3Fh+var_60]
0x18011579c  mov     [rcx+rax*2], r8w
0x1801157a1  mov     rax, [rbp+3Fh+var_68]
0x1801157a5  mov     rcx, [rax]
0x1801157a8  mov     rax, [rbp+3Fh+var_58]
0x1801157ac  mov     [rcx+rax*2], r8w
0x1801157b1  lea     r8, [rdi+2Ch]; wchar_t *
0x1801157b5  mov     rdx, [rbp+3Fh+var_A0]; unsigned __int64 *
0x1801157b9  mov     rcx, [rbp+3Fh+var_70]; wchar_t **
0x1801157bd  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x1801157c2  mov     ebx, eax
0x1801157c4  test    eax, eax
0x1801157c6  js      loc_18011599E
0x1801157cc  lea     r8, [rdi+2Ch]; wchar_t *
0x1801157d0  mov     rdx, [rbp+3Fh+var_A8]; unsigned __int64 *
0x1801157d4  mov     rcx, [rbp+3Fh+var_68]; wchar_t **
0x1801157d8  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x1801157dd  mov     ebx, eax
0x1801157df  xor     eax, eax
0x1801157e1  test    ebx, ebx
0x1801157e3  js      loc_180115994
0x1801157e9  test    byte ptr [rdi], 10h
0x1801157ec  jz      loc_1801158AA
0x1801157f2  mov     [rsp+100h+var_B8], r13; void *
0x1801157f7  mov     [rsp+100h+var_C0], 0Ah; int
0x1801157ff  mov     [rsp+100h+var_C8], r14d; int
0x180115804  mov     [rsp+100h+var_D0], esi; bFailIfExists
0x180115808  mov     [rsp+100h+var_D8], 1; int
0x180115810  mov     [rsp+100h+var_E0], rdi; int
0x180115815  mov     r9, [rbp+3Fh+var_A8]; int
0x180115819  mov     r8, [rbp+3Fh+var_68]; int
0x18011581d  mov     rdx, [rbp+3Fh+var_A0]; int
0x180115821  mov     rcx, [rbp+3Fh+var_70]; int
0x180115825  call    SusMoveOrCopyDirectoryContentsHelperRecursive
0x18011582a  mov     ebx, eax
0x18011582c  mov     ecx, 80000000h
0x180115831  add     eax, ecx
0x180115833  test    ecx, eax
0x180115835  jnz     short loc_180115843
0x180115837  cmp     ebx, 80070003h
0x18011583d  jnz     loc_18011592D
0x180115843  test    r14d, r14d
0x180115846  jnz     loc_18011590E
0x18011584c  mov     rcx, [rbp+3Fh+var_70]
0x180115850  mov     rcx, [rcx]; lpPathName
0x180115853  call    cs:__imp_RemoveDirectoryW
0x180115859  test    eax, eax
0x18011585b  jnz     loc_18011590E
0x180115861  mov     rax, [rbp+3Fh+var_70]
0x180115865  mov     rbx, [rax]
0x180115868  call    cs:__imp_GetLastError
0x18011586e  movzx   ecx, ax
0x180115871  or      ecx, 80070000h
0x180115877  test    eax, eax
0x180115879  cmovle  ecx, eax
0x18011587c  test    ecx, ecx
0x18011587e  cmovns  ecx, r12d
0x180115882  mov     qword ptr [rsp+100h+var_D0], rbx
0x180115887  lea     rax, aRemovedirector; "RemoveDirectory() failed to remove %ws"
0x18011588e  mov     qword ptr [rsp+100h+var_D8], rax
0x180115893  mov     dword ptr [rsp+100h+var_E0], ecx
0x180115897  xor     edx, edx
0x180115899  xor     ecx, ecx
0x18011589b  lea     r9d, [r14+4]
0x18011589f  lea     r8d, [r14+20h]
0x1801158a3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801158a8  jmp     short loc_18011590E
0x1801158aa  test    esi, esi
0x1801158ac  jnz     short loc_1801158C2
0x1801158ae  mov     edx, 80h; dwFileAttributes
0x1801158b3  mov     rcx, [rbp+3Fh+var_68]
0x1801158b7  mov     rcx, [rcx]; lpFileName
0x1801158ba  call    cs:__imp_SetFileAttributesW
0x1801158c0  xor     eax, eax
0x1801158c2  mov     [rsp+100h+var_E0], r13; void *
0x1801158c7  mov     rdx, [rbp+3Fh+var_68]
0x1801158cb  mov     rcx, [rbp+3Fh+var_70]
0x1801158cf  mov     rdx, [rdx]; lpNewFileName
0x1801158d2  mov     rcx, [rcx]; lpExistingFileName
0x1801158d5  test    r14d, r14d
0x1801158d8  jz      short loc_1801158EA
0x1801158da  mov     r9d, 0Ah; unsigned int
0x1801158e0  mov     r8d, esi; bFailIfExists
0x1801158e3  call    ?SusCopyFileRetryIfSharingViolation@@YAJPEB_W0HKPEAX@Z; SusCopyFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,int,ulong,void *)
0x1801158e8  jmp     short loc_1801158F8
0x1801158ea  mov     r8d, eax
0x1801158ed  test    esi, esi
0x1801158ef  setz    r8b; dwFlags
0x1801158f3  call    ?SusMoveFileRetryIfSharingViolation@@YAJPEB_W0KKPEAX@Z; SusMoveFileRetryIfSharingViolation(wchar_t const *,wchar_t const *,ulong,ulong,void *)
0x1801158f8  mov     ebx, eax
0x1801158fa  mov     ecx, 80000000h
0x1801158ff  lea     eax, [rax+rcx]
0x180115902  test    ecx, eax
0x180115904  jnz     short loc_18011590E
0x180115906  cmp     ebx, 80070002h
0x18011590c  jnz     short loc_180115937
0x18011590e  mov     rdx, rdi; lpFindFileData
0x180115911  mov     rcx, [rbp+3Fh+hFindFile]; hFindFile
0x180115915  call    ?SusFindNextFile@@YAJPEAXPEAU_WIN32_FIND_DATAW@@@Z; SusFindNextFile(void *,_WIN32_FIND_DATAW *)
0x18011591a  xor     r8d, r8d
0x18011591d  test    eax, eax
0x18011591f  jns     loc_180115791
0x180115925  mov     ebx, r8d
0x180115928  jmp     loc_1801159B9
0x18011592d  mov     r9d, ebx
0x180115930  mov     edx, 4F7h
0x180115935  jmp     short loc_1801159A6
0x180115937  lea     rax, aCopy_0; "copy"
0x18011593e  lea     rdx, aMove; "move"
0x180115945  test    r14d, r14d
0x180115948  cmovnz  rdx, rax
0x18011594c  mov     rax, [rbp+3Fh+var_68]
0x180115950  mov     rcx, [rax]
0x180115953  mov     qword ptr [rsp+100h+var_C0], rcx
0x180115958  mov     rax, [rbp+3Fh+var_70]
0x18011595c  mov     rcx, [rax]
0x18011595f  mov     qword ptr [rsp+100h+var_C8], rcx
0x180115964  mov     qword ptr [rsp+100h+var_D0], rdx
0x180115969  lea     rax, aFailedToWsFile; "Failed to %ws file from %ws to %ws"
0x180115970  mov     qword ptr [rsp+100h+var_D8], rax
0x180115975  mov     dword ptr [rsp+100h+var_E0], ebx
0x180115979  xor     edx, edx
0x18011597b  xor     ecx, ecx
0x18011597d  lea     r9d, [rdx+4]
0x180115981  lea     r8d, [rdx+20h]
0x180115985  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x18011598a  mov     r9d, ebx
0x18011598d  mov     edx, 52Dh
0x180115992  jmp     short loc_1801159A6
0x180115994  mov     r9d, ebx
0x180115997  mov     edx, 4E4h
0x18011599c  jmp     short loc_1801159A6
0x18011599e  mov     edx, 4E1h; void *
0x1801159a3  mov     r9d, eax; char *
0x1801159a6  lea     r8, aCW1SSrcClientL_66; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801159ad  mov     rcx, [rbp+47h]; this
0x1801159b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801159b6  xor     r8d, r8d
0x1801159b9  mov     rax, [rbp+3Fh+var_70]
0x1801159bd  mov     rcx, [rax]
0x1801159c0  mov     rax, [rbp+3Fh+var_60]
0x1801159c4  mov     [rcx+rax*2], r8w
0x1801159c9  mov     rcx, [rbp+3Fh+var_68]
0x1801159cd  mov     rdx, [rcx]
0x1801159d0  mov     rcx, [rbp+3Fh+var_58]
0x1801159d4  mov     [rdx+rcx*2], r8w
0x1801159d9  mov     rcx, [rbp+3Fh+hFindFile]; hFindFile
0x1801159dd  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1801159e1  jz      short loc_1801159E9
0x1801159e3  call    cs:__imp_FindClose
0x1801159e9  mov     eax, ebx
0x1801159eb  mov     rcx, [rbp+3Fh+var_50]
0x1801159ef  xor     rcx, rsp; StackCookie
0x1801159f2  call    __security_check_cookie
0x1801159f7  add     rsp, 0C8h
0x1801159fe  pop     r15
0x180115a00  pop     r14
0x180115a02  pop     r13
0x180115a04  pop     r12
0x180115a06  pop     rdi
0x180115a07  pop     rsi
0x180115a08  pop     rbx
0x180115a09  pop     rbp
0x180115a0a  retn
```
