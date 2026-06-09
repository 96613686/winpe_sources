# SusDeleteDirectoryWorker

- ea: `0x18011452c`
- end: `0x18011494a`
- name: `SusDeleteDirectoryWorker`
- size: `1054`
- prototype: `__int64 __fastcall(PCNZWCH *, unsigned __int64 *, int, int, int, LPWIN32_FIND_DATAW lpFindFileData, int, int, unsigned int, void *)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, reparse_path`

## callers

- `0x18011452c`
- `0x180114950`

## callees

- `0x1800548fc`
- `0x1801140a0`
- `0x18011452c`
- `0x18011511c`
- `0x180115324`
- `0x180115f58`
- `0x1801162c0`
- `0x18012b618`
- `0x180238960`
- `0x180240d40`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801145de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114829`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801145de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114647`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180114829`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114902`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180114902`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180114638`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180114638`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18011481f`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x18011481f`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801148a6`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x1801148a6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801145b7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1801145b7`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801148c6`
- `api-ms-win-core-file-l1-1-0!SetFileInformationByHandle` at `0x1801148c6`

## string_xrefs

- `0x1801146d0`: `Final path verification failed for %ws`
- `0x18011468e`: `Found reparse point at: %ws`
- `0x1801148d0`: `SusDeleteDirectoryWorker failed`
- `0x180114937`: `Found mount point while trying to delete %ls. Exiting.`

## pseudocode

```c
__int64 __fastcall SusDeleteDirectoryWorker(
        PCNZWCH *a1,
        unsigned __int64 *a2,
        int a3,
        int a4,
        int a5,
        LPWIN32_FIND_DATAW lpFindFileData,
        int a7,
        int a8,
        unsigned int a9,
        void *a10)
{
  __int64 v13; // r15
  const WCHAR *v14; // rcx
  __int64 v15; // rax
  HANDLE FileW; // rbx
  int v17; // edi
  signed int LastError; // eax
  signed int v19; // eax
  unsigned __int64 v20; // r9
  int FirstFile; // eax
  unsigned __int64 v22; // r9
  int v23; // eax
  signed int v24; // eax
  int NextFile; // eax
  HANDLE hTemplateFile; // [rsp+30h] [rbp-A1h]
  int v28; // [rsp+54h] [rbp-7Dh]
  HANDLE hFindFile; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int64 *v31; // [rsp+68h] [rbp-69h]
  void *v32; // [rsp+70h] [rbp-61h]
  __int64 v33; // [rsp+78h] [rbp-59h]
  HANDLE v34; // [rsp+80h] [rbp-51h]
  char v35[8]; // [rsp+88h] [rbp-49h] BYREF
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+90h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+118h] [rbp+47h]

  v31 = a2;
  v32 = a10;
  v13 = -1;
  hFindFile = (HANDLE)-1LL;
  v28 = 0;
  v14 = *a1;
  v15 = -1;
  do
    ++v15;
  while ( v14[v15] );
  v33 = v15;
  FileW = CreateFileW(v14, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
  v34 = FileW;
  if ( FileW == (HANDLE)-1LL )
  {
    if ( !a4 )
    {
      LastError = GetLastError();
      v17 = (unsigned __int16)LastError | 0x80070000;
      if ( LastError <= 0 )
        v17 = LastError;
      if ( v17 < 0 )
      {
        if ( v17 == -2147024893 || v17 == -2147024894 )
          v17 = 0;
      }
      else
      {
        v17 = -2147418113;
      }
      goto LABEL_54;
    }
    goto LABEL_5;
  }
  memset(&FileInformation, 0, sizeof(FileInformation));
  if ( !GetFileInformationByHandle(FileW, &FileInformation) )
  {
    if ( !a4 )
    {
      v19 = GetLastError();
      v17 = (unsigned __int16)v19 | 0x80070000;
      if ( v19 <= 0 )
        v17 = v19;
      if ( v17 >= 0 )
        v17 = -2147418113;
      goto LABEL_54;
    }
LABEL_5:
    v17 = 1;
    goto LABEL_54;
  }
  if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
  {
    v17 = a4 != 0 ? 1 : -2147020501;
    WUTrace(0, 0, 32, 2, v17, L"Found reparse point at: %ws", *a1);
    goto LABEL_54;
  }
  v17 = VerifyFinalFilePath(FileW, *a1);
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x1DF,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\util\\fileutil.cpp",
      (const char *)(unsigned int)v17,
      (int)"Final path verification failed for %ws",
      (const char *)*a1);
    goto LABEL_60;
  }
  v17 = WUAppendPathReAlloc((wchar_t **)a1, a2, L"*", v20);
  if ( v17 < 0 )
    goto LABEL_54;
  memset(lpFindFileData, 0, sizeof(struct _WIN32_FIND_DATAW));
  FirstFile = SusFindFirstFile(*a1, lpFindFileData, &hFindFile);
  v17 = FirstFile;
  if ( FirstFile < 0 )
  {
    if ( ((FirstFile + 2147024894) & 0xFFFFFFEE) == 0 && FirstFile != -2147024877 )
      v17 = 0;
    v13 = (__int64)hFindFile;
    goto LABEL_54;
  }
  v13 = (__int64)hFindFile;
  do
  {
    if ( (lpFindFileData->dwFileAttributes & 0x10) != 0 && !a3 )
      goto LABEL_51;
    (*a1)[v33] = 0;
    v17 = WUAppendPathReAlloc((wchar_t **)a1, v31, lpFindFileData->cFileName, v22);
    if ( v17 < 0 )
      goto LABEL_50;
    if ( (lpFindFileData->dwFileAttributes & 0x10) == 0 )
    {
      if ( (lpFindFileData->dwFileAttributes & 1) == 0 || SetFileAttributesW(*a1, 0x80u) )
      {
        v17 = SusDeleteFileRetryIfSharingViolation(*a1, a9, v32);
        if ( v17 >= 0 )
          goto LABEL_51;
      }
      else
      {
        v24 = GetLastError();
        v17 = (unsigned __int16)v24 | 0x80070000;
        if ( v24 <= 0 )
          v17 = v24;
        if ( v17 >= 0 )
          v17 = -2147418113;
      }
LABEL_50:
      v28 = 1;
      if ( !a4 )
        goto LABEL_54;
      goto LABEL_51;
    }
    if ( (lpFindFileData->dwFileAttributes & 0x400) != 0 && lpFindFileData->dwReserved0 == -1610612733 )
    {
      if ( !a4 )
      {
        v17 = -2147024891;
        WUTrace(0, 0, 32, 1, -2147024891, L"Found mount point while trying to delete %ls. Exiting.", *a1);
        goto LABEL_54;
      }
LABEL_38:
      v28 = 1;
      goto LABEL_51;
    }
    v23 = SusDeleteDirectoryWorker((int)a1, (int)v31, a3, a4, 0, lpFindFileData, 0, 0, a9, (__int64)v32);
    v17 = v23;
    if ( v23 < 0 )
      goto LABEL_50;
    if ( v23 == 1 )
      goto LABEL_38;
LABEL_51:
    NextFile = SusFindNextFile((HANDLE)v13, lpFindFileData);
    v17 = NextFile;
  }
  while ( NextFile >= 0 );
  if ( NextFile == -2147024878 )
    v17 = v28 != 0;
LABEL_54:
  (*a1)[v33] = 0;
  if ( v13 != -1 )
    FindClose((HANDLE)v13);
  if ( !a7 )
  {
    v35[0] = 1;
    SetFileInformationByHandle(FileW, FileDispositionInfo, v35, 1u);
  }
  if ( v17 < 0 )
    WUTrace(0, 0, 32, 1, v17, L"SusDeleteDirectoryWorker failed", hTemplateFile);
LABEL_60:
  if ( FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return (unsigned int)v17;
}

```

## disassembly

```asm
0x18011452c  push    rbp
0x18011452e  push    rbx
0x18011452f  push    rsi
0x180114530  push    rdi
0x180114531  push    r12
0x180114533  push    r13
0x180114535  push    r14
0x180114537  push    r15
0x180114539  lea     rbp, [rsp-7]
0x18011453e  sub     rsp, 0D8h
0x180114545  mov     rax, cs:__security_cookie
0x18011454c  xor     rax, rsp
0x18011454f  mov     [rbp+3Fh+var_48], rax
0x180114553  mov     r14d, r9d
0x180114556  mov     [rbp+3Fh+var_B8], r8d
0x18011455a  mov     r12, rdx
0x18011455d  mov     [rbp+3Fh+var_A8], rdx
0x180114561  mov     rsi, rcx
0x180114564  mov     r13, [rbp+3Fh+lpFindFileData]
0x180114568  mov     rax, [rbp+3Fh+arg_48]
0x18011456f  mov     [rbp+3Fh+var_A0], rax
0x180114573  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180114577  mov     r15, rdx
0x18011457a  mov     [rbp+3Fh+hFindFile], rdx
0x18011457e  xor     edi, edi
0x180114580  mov     [rbp+3Fh+var_BC], edi
0x180114583  mov     rcx, [rcx]; lpFileName
0x180114586  mov     rax, rdx
0x180114589  inc     rax
0x18011458c  cmp     [rcx+rax*2], di
0x180114590  jnz     short loc_180114589
0x180114592  mov     [rbp+3Fh+var_98], rax
0x180114596  mov     [rsp+110h+hTemplateFile], rdi; hTemplateFile
0x18011459b  mov     [rsp+110h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x1801145a3  mov     [rsp+110h+dwCreationDisposition], 3; dwCreationDisposition
0x1801145ab  xor     r9d, r9d; lpSecurityAttributes
0x1801145ae  mov     edx, 80010000h; dwDesiredAccess
0x1801145b3  lea     r8d, [r9+1]; dwShareMode
0x1801145b7  call    cs:__imp_CreateFileW
0x1801145bd  mov     rbx, rax
0x1801145c0  mov     [rbp+3Fh+var_90], rax
0x1801145c4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1801145c8  setz    [rsp+110h+var_C0]
0x1801145cd  jnz     short loc_18011461D
0x1801145cf  test    r14d, r14d
0x1801145d2  jz      short loc_1801145DE
0x1801145d4  mov     edi, 1
0x1801145d9  jmp     loc_180114890
0x1801145de  call    cs:__imp_GetLastError
0x1801145e4  movzx   edi, ax
0x1801145e7  or      edi, 80070000h
0x1801145ed  xor     ecx, ecx
0x1801145ef  test    eax, eax
0x1801145f1  cmovle  edi, eax
0x1801145f4  test    edi, edi
0x1801145f6  js      short loc_180114602
0x1801145f8  mov     edi, 8000FFFFh
0x1801145fd  jmp     loc_180114890
0x180114602  cmp     edi, 80070003h
0x180114608  jz      short loc_180114616
0x18011460a  cmp     edi, 80070002h
0x180114610  jnz     loc_180114890
0x180114616  mov     edi, ecx
0x180114618  jmp     loc_180114890
0x18011461d  xorps   xmm0, xmm0
0x180114620  xor     eax, eax
0x180114622  movups  xmmword ptr [rbp+3Fh+FileInformation.dwFileAttributes], xmm0
0x180114626  movups  xmmword ptr [rbp+3Fh+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18011462a  movups  xmmword ptr [rbp+3Fh+FileInformation.nFileSizeHigh], xmm0
0x18011462e  mov     [rbp+3Fh+FileInformation.nFileIndexLow], eax
0x180114631  lea     rdx, [rbp+3Fh+FileInformation]; lpFileInformation
0x180114635  mov     rcx, rbx; hFile
0x180114638  call    cs:__imp_GetFileInformationByHandle
0x18011463e  test    eax, eax
0x180114640  jnz     short loc_18011466C
0x180114642  test    r14d, r14d
0x180114645  jnz     short loc_1801145D4
0x180114647  call    cs:__imp_GetLastError
0x18011464d  movzx   edi, ax
0x180114650  or      edi, 80070000h
0x180114656  test    eax, eax
0x180114658  cmovle  edi, eax
0x18011465b  mov     r12d, 8000FFFFh
0x180114661  test    edi, edi
0x180114663  cmovns  edi, r12d
0x180114667  jmp     loc_180114890
0x18011466c  mov     rdx, [rsi]; lpString1
0x18011466f  test    [rbp+3Fh+FileInformation.dwFileAttributes], 400h
0x180114676  jz      short loc_1801146B6
0x180114678  neg     r14d
0x18011467b  sbb     edi, edi
0x18011467d  and     edi, 7FF8EED6h
0x180114683  add     edi, 8007112Bh
0x180114689  mov     [rsp+110h+hTemplateFile], rdx
0x18011468e  lea     rax, aFoundReparsePo; "Found reparse point at: %ws"
0x180114695  xor     edx, edx
0x180114697  xor     ecx, ecx
0x180114699  lea     r9d, [rdx+2]
0x18011469d  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x1801146a2  mov     [rsp+110h+dwCreationDisposition], edi
0x1801146a6  mov     r8d, 20h ; ' '
0x1801146ac  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801146b1  jmp     loc_180114890
0x1801146b6  mov     rcx, rbx; hFile
0x1801146b9  call    ?VerifyFinalFilePath@@YAJPEAXPEB_W@Z; VerifyFinalFilePath(void *,wchar_t const *)
0x1801146be  mov     edi, eax
0x1801146c0  test    eax, eax
0x1801146c2  jns     short loc_1801146F7
0x1801146c4  mov     rcx, [rbp+47h]; this
0x1801146c8  mov     rax, [rsi]
0x1801146cb  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax; char *
0x1801146d0  lea     rax, aFinalPathVerif; "Final path verification failed for %ws"
0x1801146d7  mov     qword ptr [rsp+110h+dwCreationDisposition], rax; int
0x1801146dc  mov     r9d, edi; char *
0x1801146df  lea     r8, aCW1SSrcClientL_66; "C:\\__w\\1\\s\\src\\Client\\lib\\util\\"...
0x1801146e6  mov     edx, 1DFh; void *
0x1801146eb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1801146f0  xor     esi, esi
0x1801146f2  jmp     loc_1801148F2
0x1801146f7  lea     r8, asc_1802783E0; "*"
0x1801146fe  mov     rdx, r12; unsigned __int64 *
0x180114701  mov     rcx, rsi; wchar_t **
0x180114704  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180114709  mov     edi, eax
0x18011470b  test    eax, eax
0x18011470d  js      loc_180114890
0x180114713  xor     edx, edx; Val
0x180114715  mov     r8d, 250h; Size
0x18011471b  mov     rcx, r13; void *
0x18011471e  call    memset
0x180114723  lea     r8, [rbp+3Fh+hFindFile]; void **
0x180114727  mov     rdx, r13; struct _WIN32_FIND_DATAW *
0x18011472a  mov     rcx, [rsi]; wchar_t *
0x18011472d  call    ?SusFindFirstFile@@YAJPEB_WPEAU_WIN32_FIND_DATAW@@PEAPEAX@Z; SusFindFirstFile(wchar_t const *,_WIN32_FIND_DATAW *,void * *)
0x180114732  mov     edi, eax
0x180114734  xor     ecx, ecx
0x180114736  test    eax, eax
0x180114738  jns     short loc_180114759
0x18011473a  add     eax, 7FF8FFFEh
0x18011473f  test    eax, 0FFFFFFEEh
0x180114744  jnz     short loc_180114750
0x180114746  cmp     edi, 80070013h
0x18011474c  jz      short loc_180114750
0x18011474e  mov     edi, ecx
0x180114750  mov     r15, [rbp+3Fh+hFindFile]
0x180114754  jmp     loc_180114890
0x180114759  mov     r12d, 8000FFFFh
0x18011475f  mov     r15, [rbp+3Fh+hFindFile]
0x180114763  test    byte ptr [r13+0], 10h
0x180114768  jz      short loc_180114773
0x18011476a  cmp     [rbp+3Fh+var_B8], ecx
0x18011476d  jz      loc_180114869
0x180114773  mov     rax, [rsi]
0x180114776  mov     rcx, [rbp+3Fh+var_98]
0x18011477a  xor     edx, edx
0x18011477c  mov     [rax+rcx*2], dx
0x180114780  lea     r8, [r13+2Ch]; wchar_t *
0x180114784  mov     rdx, [rbp+3Fh+var_A8]; unsigned __int64 *
0x180114788  mov     rcx, rsi; wchar_t **
0x18011478b  call    ?WUAppendPathReAlloc@@YAJPEAPEA_WPEA_KPEB_W_K@Z; WUAppendPathReAlloc(wchar_t * *,unsigned __int64 *,wchar_t const *,unsigned __int64)
0x180114790  mov     edi, eax
0x180114792  xor     ecx, ecx
0x180114794  test    eax, eax
0x180114796  js      loc_18011485D
0x18011479c  test    byte ptr [r13+0], 10h
0x1801147a1  jz      short loc_180114810
0x1801147a3  test    dword ptr [r13+0], 400h
0x1801147ab  jz      short loc_1801147CC
0x1801147ad  cmp     dword ptr [r13+24h], 0A0000003h
0x1801147b5  jnz     short loc_1801147CC
0x1801147b7  test    r14d, r14d
0x1801147ba  jz      loc_18011492A
0x1801147c0  mov     [rbp+3Fh+var_BC], 1
0x1801147c7  jmp     loc_180114869
0x1801147cc  mov     rax, [rbp+3Fh+var_A0]
0x1801147d0  mov     [rsp+110h+var_C8], rax; __int64
0x1801147d5  mov     eax, [rbp+3Fh+arg_40]
0x1801147db  mov     [rsp+110h+var_D0], eax; int
0x1801147df  mov     [rsp+110h+var_D8], ecx; int
0x1801147e3  mov     dword ptr [rsp+110h+hTemplateFile], ecx; int
0x1801147e7  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], r13; lpFindFileData
0x1801147ec  mov     [rsp+110h+dwCreationDisposition], ecx; int
0x1801147f0  mov     r9d, r14d; int
0x1801147f3  mov     r8d, [rbp+3Fh+var_B8]; int
0x1801147f7  mov     rdx, [rbp+3Fh+var_A8]; int
0x1801147fb  mov     rcx, rsi; int
0x1801147fe  call    SusDeleteDirectoryWorker
0x180114803  mov     edi, eax
0x180114805  test    eax, eax
0x180114807  js      short loc_18011485D
0x180114809  cmp     eax, 1
0x18011480c  jnz     short loc_180114869
0x18011480e  jmp     short loc_1801147C0
0x180114810  test    byte ptr [r13+0], 1
0x180114815  jz      short loc_180114845
0x180114817  mov     edx, 80h; dwFileAttributes
0x18011481c  mov     rcx, [rsi]; lpFileName
0x18011481f  call    cs:__imp_SetFileAttributesW
0x180114825  test    eax, eax
0x180114827  jnz     short loc_180114845
0x180114829  call    cs:__imp_GetLastError
0x18011482f  movzx   edi, ax
0x180114832  or      edi, 80070000h
0x180114838  test    eax, eax
0x18011483a  cmovle  edi, eax
0x18011483d  test    edi, edi
0x18011483f  cmovns  edi, r12d
0x180114843  jmp     short loc_18011485D
0x180114845  mov     r8, [rbp+3Fh+var_A0]; void *
0x180114849  mov     edx, [rbp+3Fh+arg_40]; unsigned int
0x18011484f  mov     rcx, [rsi]; lpString1
0x180114852  call    ?SusDeleteFileRetryIfSharingViolation@@YAJPEB_WKPEAX@Z; SusDeleteFileRetryIfSharingViolation(wchar_t const *,ulong,void *)
0x180114857  mov     edi, eax
0x180114859  test    eax, eax
0x18011485b  jns     short loc_180114869
0x18011485d  mov     [rbp+3Fh+var_BC], 1
0x180114864  test    r14d, r14d
0x180114867  jz      short loc_180114890
0x180114869  mov     rdx, r13; lpFindFileData
0x18011486c  mov     rcx, r15; hFindFile
0x18011486f  call    ?SusFindNextFile@@YAJPEAXPEAU_WIN32_FIND_DATAW@@@Z; SusFindNextFile(void *,_WIN32_FIND_DATAW *)
0x180114874  mov     edi, eax
0x180114876  xor     ecx, ecx
0x180114878  test    eax, eax
0x18011487a  jns     loc_180114763
0x180114880  cmp     eax, 80070012h
0x180114885  jnz     short loc_180114890
0x180114887  mov     edi, ecx
0x180114889  cmp     [rbp+3Fh+var_BC], ecx
0x18011488c  setnz   dil
0x180114890  mov     rax, [rsi]
0x180114893  mov     rcx, [rbp+3Fh+var_98]
0x180114897  xor     esi, esi
0x180114899  mov     [rax+rcx*2], si
0x18011489d  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1801148a1  jz      short loc_1801148AC
0x1801148a3  mov     rcx, r15; hFindFile
0x1801148a6  call    cs:__imp_FindClose
0x1801148ac  cmp     [rbp+3Fh+arg_30], esi
0x1801148af  jnz     short loc_1801148CC
0x1801148b1  mov     [rbp+3Fh+var_88], 1
0x1801148b5  mov     r9d, 1; dwBufferSize
0x1801148bb  lea     r8, [rbp+3Fh+var_88]; lpFileInformation
0x1801148bf  lea     edx, [r9+3]; FileInformationClass
0x1801148c3  mov     rcx, rbx; hFile
0x1801148c6  call    cs:__imp_SetFileInformationByHandle
0x1801148cc  test    edi, edi
0x1801148ce  jns     short loc_1801148F2
0x1801148d0  lea     rax, aSusdeletedirec_0; "SusDeleteDirectoryWorker failed"
0x1801148d7  mov     qword ptr [rsp+110h+dwFlagsAndAttributes], rax
0x1801148dc  mov     [rsp+110h+dwCreationDisposition], edi
0x1801148e0  xor     edx, edx
0x1801148e2  xor     ecx, ecx
0x1801148e4  lea     r9d, [rdx+1]
0x1801148e8  lea     r8d, [rdx+20h]
0x1801148ec  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1801148f1  nop
0x1801148f2  cmp     [rsp+110h+var_C0], sil
0x1801148f7  jnz     short loc_180114908
0x1801148f9  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1801148fd  jz      short loc_180114908
0x1801148ff  mov     rcx, rbx; hObject
0x180114902  call    cs:__imp_CloseHandle
0x180114908  mov     eax, edi
0x18011490a  mov     rcx, [rbp+3Fh+var_48]
0x18011490e  xor     rcx, rsp; StackCookie
0x180114911  call    __security_check_cookie
0x180114916  add     rsp, 0D8h
0x18011491d  pop     r15
0x18011491f  pop     r14
0x180114921  pop     r13
0x180114923  pop     r12
0x180114925  pop     rdi
0x180114926  pop     rsi
0x180114927  pop     rbx
0x180114928  pop     rbp
0x180114929  retn
0x18011492a  mov     edi, 80070005h
0x18011492f  mov     rax, [rsi]
0x180114932  mov     [rsp+110h+hTemplateFile], rax
0x180114937  lea     rax, aFoundMountPoin; "Found mount point while trying to delet"...
0x18011493e  xor     edx, edx
0x180114940  lea     r9d, [rdx+1]
0x180114944  jmp     loc_18011469D
```
