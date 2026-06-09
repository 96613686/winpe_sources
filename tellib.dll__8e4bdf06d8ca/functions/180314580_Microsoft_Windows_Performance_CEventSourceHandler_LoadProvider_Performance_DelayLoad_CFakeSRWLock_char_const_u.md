# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x180314580`
- end: `0x180314779`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `505`
- prototype: `signed int __fastcall(__int64, const char *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180314780`

## callees

- `0x18008b3c8`
- `0x18008daf0`
- `0x18012de40`
- `0x180314580`
- `0x180314bcc`
- `0x180315978`
- `0x180346010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1803145e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1803145e6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1803145c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1803145c6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803146a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1803146a8`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180314672`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180314698`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180314672`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x180314698`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180314743`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180314743`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180314616`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x180314616`

## string_xrefs

- `0x1803145bf`: `kernelbase.dll`
- `0x1803146ec`: `TdhLoadManifest`
- `0x1803145dc`: `GetTempPath2W`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const char *a2,
        DWORD a3,
        __int64 a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  DWORD v10; // ebx
  signed int result; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *v12; // rcx
  __int64 (__fastcall *v13)(WCHAR *); // rax
  int v14; // eax
  unsigned int v15; // ebx
  WCHAR *v16; // [rsp+20h] [rbp-E0h] BYREF
  _QWORD v17[3]; // [rsp+28h] [rbp-D8h] BYREF
  char v18; // [rsp+40h] [rbp-C0h]
  WCHAR TempFileName[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v16 = (WCHAR *)Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
  else
    TempPathW = GetTempPathW(0x104u, Buffer);
  v10 = TempPathW;
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v16);
  if ( v10 && v10 + 1 <= 0x104 || (result = StringCchCopyW(Buffer, 0x104u, L"."), result >= 0) )
  {
    if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
    {
      result = Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(v12, TempFileName, a2, a3);
      if ( result >= 0 )
      {
        v16 = TempFileName;
        v17[0] = a4;
        v17[1] = "TdhLoadManifest";
        v17[2] = 0;
        v18 = 0;
        if ( Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(wchar_t *)(v17)
          && (v13 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(wchar_t *)(v17),
              v14 = v13(TempFileName),
              (v15 = v14) != 0) )
        {
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v15 = 0;
        }
        DeleteFileW(TempFileName);
        return v15;
      }
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180314580  mov     [rsp-8+arg_0], rbx
0x180314585  mov     [rsp-8+arg_18], rsi
0x18031458a  push    rbp
0x18031458b  push    rdi
0x18031458c  push    r14
0x18031458e  lea     rbp, [rsp-380h]
0x180314596  sub     rsp, 480h
0x18031459d  mov     rax, cs:__security_cookie
0x1803145a4  xor     rax, rsp
0x1803145a7  mov     [rbp+390h+var_20], rax
0x1803145ae  mov     rdi, r9
0x1803145b1  mov     r14d, r8d
0x1803145b4  mov     rsi, rdx
0x1803145b7  xor     edx, edx; hFile
0x1803145b9  mov     r8d, 800h; dwFlags
0x1803145bf  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1803145c6  call    cs:__imp_LoadLibraryExW
0x1803145cd  nop     dword ptr [rax+rax+00h]
0x1803145d2  mov     [rsp+490h+var_470], rax
0x1803145d7  test    rax, rax
0x1803145da  jz      short loc_18031460A
0x1803145dc  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x1803145e3  mov     rcx, rax; hModule
0x1803145e6  call    cs:__imp_GetProcAddress
0x1803145ed  nop     dword ptr [rax+rax+00h]
0x1803145f2  test    rax, rax
0x1803145f5  jz      short loc_18031460A
0x1803145f7  lea     rdx, [rbp+390h+Buffer]
0x1803145fe  mov     ecx, 104h
0x180314603  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180314608  jmp     short loc_180314622
0x18031460a  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x180314611  mov     ecx, 104h; nBufferLength
0x180314616  call    cs:__imp_GetTempPathW
0x18031461d  nop     dword ptr [rax+rax+00h]
0x180314622  mov     ebx, eax
0x180314624  lea     rcx, [rsp+490h+var_470]
0x180314629  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18031462e  test    ebx, ebx
0x180314630  jz      short loc_18031463C
0x180314632  lea     eax, [rbx+1]
0x180314635  cmp     eax, 104h
0x18031463a  jbe     short loc_18031465C
0x18031463c  lea     r8, PathName; "."
0x180314643  mov     edx, 104h; unsigned __int64
0x180314648  lea     rcx, [rbp+390h+Buffer]; wchar_t *
0x18031464f  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x180314654  test    eax, eax
0x180314656  js      loc_180314751
0x18031465c  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x180314661  xor     r8d, r8d; uUnique
0x180314664  lea     rdx, PrefixString; "xpf"
0x18031466b  lea     rcx, [rbp+390h+Buffer]; lpPathName
0x180314672  call    cs:__imp_GetTempFileNameW
0x180314679  nop     dword ptr [rax+rax+00h]
0x18031467e  test    eax, eax
0x180314680  jnz     short loc_1803146C9
0x180314682  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x180314687  xor     r8d, r8d; uUnique
0x18031468a  lea     rdx, PrefixString; "xpf"
0x180314691  lea     rcx, PathName; "."
0x180314698  call    cs:__imp_GetTempFileNameW
0x18031469f  nop     dword ptr [rax+rax+00h]
0x1803146a4  test    eax, eax
0x1803146a6  jnz     short loc_1803146C9
0x1803146a8  call    cs:__imp_GetLastError
0x1803146af  nop     dword ptr [rax+rax+00h]
0x1803146b4  test    eax, eax
0x1803146b6  jle     loc_180314751
0x1803146bc  movzx   eax, ax
0x1803146bf  or      eax, 80070000h
0x1803146c4  jmp     loc_180314751
0x1803146c9  mov     r9d, r14d; unsigned int
0x1803146cc  mov     r8, rsi; char *
0x1803146cf  lea     rdx, [rsp+490h+TempFileName]; wchar_t *
0x1803146d4  call    ?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEB_WPEBDK@Z; Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(wchar_t const *,char const *,ulong)
0x1803146d9  test    eax, eax
0x1803146db  js      short loc_180314751
0x1803146dd  lea     rax, [rsp+490h+TempFileName]
0x1803146e2  mov     [rsp+490h+var_470], rax
0x1803146e7  mov     [rsp+490h+var_468], rdi
0x1803146ec  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x1803146f3  mov     [rsp+490h+var_460], rax
0x1803146f8  mov     [rsp+490h+var_458], 0
0x180314701  mov     [rsp+490h+var_450], 0
0x180314706  lea     rcx, [rsp+490h+var_468]
0x18031470b  call    ??B?$CDelayLoadedImport@P6AKPEA_W@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEA_W@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(wchar_t *)(void)
0x180314710  test    rax, rax
0x180314713  jz      short loc_18031473C
0x180314715  lea     rcx, [rsp+490h+var_468]
0x18031471a  call    ??B?$CDelayLoadedImport@P6AKPEA_W@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEA_W@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(wchar_t *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(wchar_t *)(void)
0x18031471f  lea     rcx, [rsp+490h+TempFileName]
0x180314724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180314729  mov     ebx, eax
0x18031472b  test    eax, eax
0x18031472d  jz      short loc_18031473C
0x18031472f  jle     short loc_18031473E
0x180314731  movzx   ebx, ax
0x180314734  or      ebx, 80070000h
0x18031473a  jmp     short loc_18031473E
0x18031473c  xor     ebx, ebx
0x18031473e  lea     rcx, [rsp+490h+TempFileName]; lpFileName
0x180314743  call    cs:__imp_DeleteFileW
0x18031474a  nop     dword ptr [rax+rax+00h]
0x18031474f  mov     eax, ebx
0x180314751  mov     rcx, [rbp+390h+var_20]
0x180314758  xor     rcx, rsp; StackCookie
0x18031475b  call    __security_check_cookie
0x180314760  lea     r11, [rsp+490h+var_10]
0x180314768  mov     rbx, [r11+20h]
0x18031476c  mov     rsi, [r11+38h]
0x180314770  mov     rsp, r11
0x180314773  pop     r14
0x180314775  pop     rdi
0x180314776  pop     rbp
0x180314777  retn
```
