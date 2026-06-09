# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x180021398`
- end: `0x1800216a9`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `785`
- prototype: `signed int __fastcall(__int64, const void *, DWORD, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800216b0`

## callees

- `0x18001e0a8`
- `0x180021398`
- `0x1800319f0`
- `0x180034010`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18002152b`
- `KERNEL32!GetLastError` at `0x180021585`
- `KERNEL32!GetLastError` at `0x1800215d3`
- `KERNEL32!GetLastError` at `0x18002152b`
- `KERNEL32!GetLastError` at `0x180021585`
- `KERNEL32!GetLastError` at `0x1800215d3`
- `KERNEL32!CloseHandle` at `0x1800215ed`
- `KERNEL32!CloseHandle` at `0x1800215ed`
- `KERNEL32!GetTempFileNameW` at `0x1800214f5`
- `KERNEL32!GetTempFileNameW` at `0x18002151b`
- `KERNEL32!GetTempFileNameW` at `0x1800214f5`
- `KERNEL32!GetTempFileNameW` at `0x18002151b`
- `KERNEL32!WriteFile` at `0x1800215be`
- `KERNEL32!WriteFile` at `0x1800215be`
- `KERNEL32!GetTempPathW` at `0x180021456`
- `KERNEL32!GetTempPathW` at `0x180021456`
- `KERNEL32!CreateFileW` at `0x180021571`
- `KERNEL32!CreateFileW` at `0x180021571`
- `KERNEL32!GetProcAddress` at `0x180021410`
- `KERNEL32!GetProcAddress` at `0x180021410`
- `KERNEL32!LoadLibraryExW` at `0x1800213ea`
- `KERNEL32!LoadLibraryExW` at `0x1800213ea`
- `KERNEL32!DeleteFileW` at `0x18002165b`
- `KERNEL32!DeleteFileW` at `0x18002166f`
- `KERNEL32!DeleteFileW` at `0x18002165b`
- `KERNEL32!DeleteFileW` at `0x18002166f`
- `KERNEL32!FreeLibrary` at `0x180021439`
- `KERNEL32!FreeLibrary` at `0x18002146c`
- `KERNEL32!FreeLibrary` at `0x180021439`
- `KERNEL32!FreeLibrary` at `0x18002146c`

## string_xrefs

- `0x1800213e3`: `kernelbase.dll`
- `0x180021406`: `GetTempPath2W`
- `0x180021610`: `TdhLoadManifest`

## pseudocode

```c
signed int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const void *a2,
        DWORD a3,
        __int64 a4)
{
  HMODULE Library; // rax
  HMODULE v8; // rbx
  FARPROC ProcAddress; // rax
  __int64 v10; // rdi
  DWORD TempPathW; // esi
  __int64 v12; // rax
  const WCHAR *v13; // rdx
  WCHAR *v14; // rcx
  WCHAR v15; // r8
  signed int result; // eax
  WCHAR *v17; // rdx
  HANDLE FileW; // rax
  void *v19; // rsi
  signed int v20; // eax
  signed int v21; // ebx
  signed int LastError; // eax
  __int64 (__fastcall *v23)(WCHAR *); // rax
  int v24; // eax
  DWORD NumberOfBytesWritten[2]; // [rsp+48h] [rbp-C0h] BYREF
  _QWORD v26[3]; // [rsp+50h] [rbp-B8h] BYREF
  __int64 v27; // [rsp+68h] [rbp-A0h]
  __int64 v28; // [rsp+70h] [rbp-98h]
  WCHAR TempFileName[264]; // [rsp+78h] [rbp-90h] BYREF
  WCHAR Buffer[264]; // [rsp+288h] [rbp+180h] BYREF

  v28 = -2;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v8 = Library;
  *(_QWORD *)NumberOfBytesWritten = Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
  {
    v10 = 260;
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
    FreeLibrary(v8);
  }
  else
  {
    v10 = 260;
    TempPathW = GetTempPathW(0x104u, Buffer);
    if ( v8 )
      FreeLibrary(v8);
  }
  if ( TempPathW && TempPathW + 1 <= 0x104 )
    goto LABEL_36;
  v12 = 2147483646;
  v13 = L".";
  v14 = Buffer;
  do
  {
    if ( !v12 )
      break;
    v15 = *v13;
    if ( !*v13 )
      break;
    ++v13;
    *v14++ = v15;
    --v12;
    --v10;
  }
  while ( v10 );
  result = v10 == 0 ? 0x8007007A : 0;
  v17 = v14 - 1;
  if ( v10 )
    v17 = v14;
  *v17 = 0;
  if ( v10 )
  {
LABEL_36:
    if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
    {
      FileW = CreateFileW(TempFileName, 0x40000000u, 0, 0, 2u, 0x80u, 0);
      v19 = FileW;
      if ( FileW )
      {
        v21 = 0;
        NumberOfBytesWritten[0] = 0;
        if ( !WriteFile(FileW, a2, a3, NumberOfBytesWritten, 0) )
        {
          LastError = GetLastError();
          v21 = LastError;
          if ( LastError > 0 )
            v21 = (unsigned __int16)LastError | 0x80070000;
        }
        CloseHandle(v19);
      }
      else
      {
        v20 = GetLastError();
        v21 = v20;
        if ( v20 > 0 )
          v21 = (unsigned __int16)v20 | 0x80070000;
      }
      if ( v21 >= 0 )
      {
        *(_QWORD *)NumberOfBytesWritten = TempFileName;
        v26[0] = a4;
        v26[1] = "TdhLoadManifest";
        v26[2] = 0;
        LOBYTE(v27) = 0;
        if ( !Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v26)
          || (v23 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<unsigned long (*)(unsigned short *),Performance::DelayLoad::CFakeSRWLock>::operator unsigned long (*)(unsigned short *)(v26),
              v24 = v23(TempFileName),
              (v21 = v24) == 0) )
        {
          DeleteFileW(TempFileName);
          return 0;
        }
        if ( v24 > 0 )
          v21 = (unsigned __int16)v24 | 0x80070000;
        DeleteFileW(TempFileName);
      }
      return v21;
    }
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x180021398  mov     rax, rsp
0x18002139b  push    rbp
0x18002139c  push    rsi
0x18002139d  push    rdi
0x18002139e  push    r12
0x1800213a0  push    r13
0x1800213a2  push    r14
0x1800213a4  push    r15
0x1800213a6  lea     rbp, [rax-3D8h]
0x1800213ad  sub     rsp, 4A0h
0x1800213b4  mov     [rsp+4D0h+var_468], 0FFFFFFFFFFFFFFFEh
0x1800213bd  mov     [rax+8], rbx
0x1800213c1  mov     rax, cs:__security_cookie
0x1800213c8  xor     rax, rsp
0x1800213cb  mov     [rbp+3D0h+var_40], rax
0x1800213d2  mov     r12, r9
0x1800213d5  mov     r15d, r8d
0x1800213d8  mov     r14, rdx
0x1800213db  xor     edx, edx; hFile
0x1800213dd  mov     r8d, 800h; dwFlags
0x1800213e3  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x1800213ea  call    cs:__imp_LoadLibraryExW
0x1800213f1  nop     dword ptr [rax+rax+00h]
0x1800213f6  mov     rbx, rax
0x1800213f9  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x1800213fe  xor     r13d, r13d
0x180021401  test    rax, rax
0x180021404  jz      short loc_180021448
0x180021406  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18002140d  mov     rcx, rax; hModule
0x180021410  call    cs:__imp_GetProcAddress
0x180021417  nop     dword ptr [rax+rax+00h]
0x18002141c  test    rax, rax
0x18002141f  jz      short loc_180021448
0x180021421  lea     rdx, [rbp+3D0h+Buffer]
0x180021428  mov     edi, 104h
0x18002142d  mov     ecx, edi
0x18002142f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021434  mov     esi, eax
0x180021436  mov     rcx, rbx; hLibModule
0x180021439  call    cs:__imp_FreeLibrary
0x180021440  nop     dword ptr [rax+rax+00h]
0x180021445  nop
0x180021446  jmp     short loc_180021479
0x180021448  lea     rdx, [rbp+3D0h+Buffer]; lpBuffer
0x18002144f  mov     edi, 104h
0x180021454  mov     ecx, edi; nBufferLength
0x180021456  call    cs:__imp_GetTempPathW
0x18002145d  nop     dword ptr [rax+rax+00h]
0x180021462  mov     esi, eax
0x180021464  test    rbx, rbx
0x180021467  jz      short loc_180021479
0x180021469  mov     rcx, rbx; hLibModule
0x18002146c  call    cs:__imp_FreeLibrary
0x180021473  nop     dword ptr [rax+rax+00h]
0x180021478  nop
0x180021479  test    esi, esi
0x18002147b  jz      short loc_180021484
0x18002147d  lea     eax, [rsi+1]
0x180021480  cmp     eax, edi
0x180021482  jbe     short loc_1800214DF
0x180021484  mov     eax, 7FFFFFFEh
0x180021489  lea     rdx, PathName; "."
0x180021490  lea     rcx, [rbp+3D0h+Buffer]
0x180021497  test    rax, rax
0x18002149a  jz      short loc_1800214BB
0x18002149c  movzx   r8d, word ptr [rdx]
0x1800214a0  test    r8w, r8w
0x1800214a4  jz      short loc_1800214BB
0x1800214a6  add     rdx, 2
0x1800214aa  mov     [rcx], r8w
0x1800214ae  add     rcx, 2
0x1800214b2  dec     rax
0x1800214b5  sub     rdi, 1
0x1800214b9  jnz     short loc_180021497
0x1800214bb  mov     rax, rdi
0x1800214be  neg     rax
0x1800214c1  sbb     eax, eax
0x1800214c3  not     eax
0x1800214c5  and     eax, 8007007Ah
0x1800214ca  lea     rdx, [rcx-2]
0x1800214ce  test    rdi, rdi
0x1800214d1  cmovnz  rdx, rcx
0x1800214d5  mov     [rdx], r13w
0x1800214d9  jz      loc_18002167E
0x1800214df  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x1800214e4  xor     r8d, r8d; uUnique
0x1800214e7  lea     rdx, PrefixString; "xpf"
0x1800214ee  lea     rcx, [rbp+3D0h+Buffer]; lpPathName
0x1800214f5  call    cs:__imp_GetTempFileNameW
0x1800214fc  nop     dword ptr [rax+rax+00h]
0x180021501  test    eax, eax
0x180021503  jnz     short loc_18002154C
0x180021505  lea     r9, [rsp+4D0h+TempFileName]; lpTempFileName
0x18002150a  xor     r8d, r8d; uUnique
0x18002150d  lea     rdx, PrefixString; "xpf"
0x180021514  lea     rcx, PathName; "."
0x18002151b  call    cs:__imp_GetTempFileNameW
0x180021522  nop     dword ptr [rax+rax+00h]
0x180021527  test    eax, eax
0x180021529  jnz     short loc_18002154C
0x18002152b  call    cs:__imp_GetLastError
0x180021532  nop     dword ptr [rax+rax+00h]
0x180021537  test    eax, eax
0x180021539  jle     loc_18002167E
0x18002153f  movzx   eax, ax
0x180021542  or      eax, 80070000h
0x180021547  jmp     loc_18002167E
0x18002154c  mov     [rsp+30h], r13; hTemplateFile
0x180021551  mov     [rsp+4D0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180021559  mov     [rsp+4D0h+dwCreationDisposition], 2; dwCreationDisposition
0x180021561  xor     r9d, r9d; lpSecurityAttributes
0x180021564  xor     r8d, r8d; dwShareMode
0x180021567  mov     edx, 40000000h; dwDesiredAccess
0x18002156c  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x180021571  call    cs:__imp_CreateFileW
0x180021578  nop     dword ptr [rax+rax+00h]
0x18002157d  mov     rsi, rax
0x180021580  test    rax, rax
0x180021583  jnz     short loc_1800215A3
0x180021585  call    cs:__imp_GetLastError
0x18002158c  nop     dword ptr [rax+rax+00h]
0x180021591  mov     ebx, eax
0x180021593  mov     edi, 80070000h
0x180021598  test    eax, eax
0x18002159a  jle     short loc_1800215F9
0x18002159c  movzx   ebx, ax
0x18002159f  or      ebx, edi
0x1800215a1  jmp     short loc_1800215F9
0x1800215a3  mov     ebx, r13d
0x1800215a6  mov     [rsp+4D0h+NumberOfBytesWritten], r13d
0x1800215ab  mov     qword ptr [rsp+4D0h+dwCreationDisposition], r13; lpOverlapped
0x1800215b0  lea     r9, [rsp+4D0h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800215b5  mov     r8d, r15d; nNumberOfBytesToWrite
0x1800215b8  mov     rdx, r14; lpBuffer
0x1800215bb  mov     rcx, rsi; hFile
0x1800215be  call    cs:__imp_WriteFile
0x1800215c5  nop     dword ptr [rax+rax+00h]
0x1800215ca  mov     edi, 80070000h
0x1800215cf  test    eax, eax
0x1800215d1  jnz     short loc_1800215EA
0x1800215d3  call    cs:__imp_GetLastError
0x1800215da  nop     dword ptr [rax+rax+00h]
0x1800215df  mov     ebx, eax
0x1800215e1  test    eax, eax
0x1800215e3  jle     short loc_1800215EA
0x1800215e5  movzx   ebx, ax
0x1800215e8  or      ebx, edi
0x1800215ea  mov     rcx, rsi; hObject
0x1800215ed  call    cs:__imp_CloseHandle
0x1800215f4  nop     dword ptr [rax+rax+00h]
0x1800215f9  test    ebx, ebx
0x1800215fb  jns     short loc_180021601
0x1800215fd  mov     eax, ebx
0x1800215ff  jmp     short loc_18002167E
0x180021601  lea     rax, [rsp+4D0h+TempFileName]
0x180021606  mov     qword ptr [rsp+4D0h+NumberOfBytesWritten], rax
0x18002160b  mov     [rsp+4D0h+var_488], r12
0x180021610  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x180021617  mov     [rsp+4D0h+var_480], rax
0x18002161c  mov     qword ptr [rsp+4D0h+var_478], r13
0x180021621  mov     byte ptr [rsp+4D0h+var_470], r13b
0x180021626  lea     rcx, [rsp+4D0h+var_488]
0x18002162b  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x180021630  test    rax, rax
0x180021633  jz      short loc_18002166A
0x180021635  lea     rcx, [rsp+4D0h+var_488]
0x18002163a  call    ??B?$CDelayLoadedImport@P6AKPEAG@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6AKPEAG@ZXZ; Performance::DelayLoad::CDelayLoadedImport<ulong (*)(ushort *),Performance::DelayLoad::CFakeSRWLock>::operator ulong (*)(ushort *)(void)
0x18002163f  lea     rcx, [rsp+4D0h+TempFileName]
0x180021644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021649  mov     ebx, eax
0x18002164b  test    eax, eax
0x18002164d  jz      short loc_18002166A
0x18002164f  jle     short loc_180021656
0x180021651  movzx   ebx, ax
0x180021654  or      ebx, edi
0x180021656  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002165b  call    cs:__imp_DeleteFileW
0x180021662  nop     dword ptr [rax+rax+00h]
0x180021667  nop
0x180021668  jmp     short loc_1800215FD
0x18002166a  lea     rcx, [rsp+4D0h+TempFileName]; lpFileName
0x18002166f  call    cs:__imp_DeleteFileW
0x180021676  nop     dword ptr [rax+rax+00h]
0x18002167b  nop
0x18002167c  xor     eax, eax
0x18002167e  mov     rcx, [rbp+3D0h+var_40]
0x180021685  xor     rcx, rsp; StackCookie
0x180021688  call    __security_check_cookie
0x18002168d  mov     rbx, [rsp+4D0h+arg_0]
0x180021695  add     rsp, 4A0h
0x18002169c  pop     r15
0x18002169e  pop     r14
0x1800216a0  pop     r13
0x1800216a2  pop     r12
0x1800216a4  pop     rdi
0x1800216a5  pop     rsi
0x1800216a6  pop     rbp
0x1800216a7  retn
```
