# FileSystemUtility::Initialize(void)

- ea: `0x180076554`
- end: `0x180076706`
- name: `?Initialize@FileSystemUtility@@IEAAJXZ`
- size: `434`
- prototype: `__int64 __fastcall(FileSystemUtility *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180075ebc`

## callees

- `0x180074e6c`
- `0x180076554`
- `0x180076ae8`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800765ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076610`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076655`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800765ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076610`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180076655`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076571`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800766a7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180076571`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800766a7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007661f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076580`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800765c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007661f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180076664`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800766bb`

## string_xrefs

- `0x180076562`: `FMIFS.DLL`
- `0x1800766e6`: `LoadLibraryEx`

## pseudocode

```c
__int64 __fastcall FileSystemUtility::Initialize(FileSystemUtility *this)
{
  HMODULE Library; // rax
  signed int LastError; // eax
  int v4; // edx
  int v5; // ecx
  unsigned int v6; // ebx
  FARPROC ProcAddress; // rax
  signed int v8; // eax
  int v9; // edx
  int v10; // ecx
  int v11; // r8d
  int v12; // r9d
  FARPROC v13; // rax
  signed int v14; // eax
  FARPROC v15; // rax
  signed int v16; // eax
  __int64 i; // rsi
  HMODULE v18; // rax
  signed int v19; // eax
  int v20; // edx

  Library = LoadLibraryExW(L"FMIFS.DLL", 0, 0);
  *((_QWORD *)this + 1) = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
      McTemplateU0zzzq_EventWriteTransfer(
        v5,
        v4,
        (unsigned int)L"FileSystemUtility::Initialize",
        (unsigned int)L"LoadLibraryEx",
        (__int64)L"FMIFS.DLL",
        v6);
    return v6;
  }
  ProcAddress = GetProcAddress(Library, "FormatEx2");
  *((_QWORD *)this + 5) = ProcAddress;
  if ( ProcAddress )
  {
    v13 = GetProcAddress(*((HMODULE *)this + 1), "ChkdskEx");
    *((_QWORD *)this + 6) = v13;
    if ( v13 )
    {
      v15 = GetProcAddress(*((HMODULE *)this + 1), "GetDefaultFileSystem");
      *((_QWORD *)this + 7) = v15;
      if ( v15 )
      {
        v6 = 0;
        for ( i = 0; (unsigned int)i < 3; i = (unsigned int)(i + 1) )
        {
          v18 = LoadLibraryExW((LPCWSTR)(&modulesToCache)[i], 0, 0);
          *((_QWORD *)this + i + 2) = v18;
          if ( !v18 )
          {
            v19 = GetLastError();
            v6 = v19;
            if ( v19 > 0 )
              v6 = (unsigned __int16)v19 | 0x80070000;
            if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
              McTemplateU0zzzq_EventWriteTransfer(
                (unsigned int)(&modulesToCache)[i],
                v20,
                (unsigned int)L"FileSystemUtility::Initialize",
                (unsigned int)L"LoadLibraryEx",
                (__int64)(&modulesToCache)[i],
                v6);
            return v6;
          }
        }
      }
      else
      {
        v16 = GetLastError();
        v6 = v16;
        if ( v16 > 0 )
          v6 = (unsigned __int16)v16 | 0x80070000;
        if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
          goto LABEL_10;
      }
    }
    else
    {
      v14 = GetLastError();
      v6 = v14;
      if ( v14 > 0 )
        v6 = (unsigned __int16)v14 | 0x80070000;
      if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
        goto LABEL_10;
    }
  }
  else
  {
    v8 = GetLastError();
    v6 = v8;
    if ( v8 > 0 )
      v6 = (unsigned __int16)v8 | 0x80070000;
    if ( (Microsoft_WindowsPhone_StorageHelperEnableBits & 4) != 0 )
LABEL_10:
      McTemplateU0zzzzq_EventWriteTransfer(v10, v9, v11, v12);
  }
  return v6;
}

```

## disassembly

```asm
0x180076554  push    rbx
0x180076556  push    rbp
0x180076557  push    rsi
0x180076558  push    rdi
0x180076559  push    r14
0x18007655b  sub     rsp, 40h
0x18007655f  mov     rdi, rcx
0x180076562  lea     rsi, aFmifsDll; "FMIFS.DLL"
0x180076569  mov     rcx, rsi; lpLibFileName
0x18007656c  xor     r8d, r8d; dwFlags
0x18007656f  xor     edx, edx; hFile
0x180076571  call    cs:__imp_LoadLibraryExW
0x180076577  mov     [rdi+8], rax
0x18007657b  test    rax, rax
0x18007657e  jnz     short loc_1800765B0
0x180076580  call    cs:__imp_GetLastError
0x180076586  mov     ebx, eax
0x180076588  test    eax, eax
0x18007658a  jle     short loc_180076595
0x18007658c  movzx   ebx, ax
0x18007658f  or      ebx, 80070000h
0x180076595  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18007659c  jz      loc_1800766F9
0x1800765a2  mov     dword ptr [rsp+68h+var_40], ebx
0x1800765a6  mov     [rsp+68h+var_48], rsi
0x1800765ab  jmp     loc_1800766E6
0x1800765b0  lea     rdx, aFormatex2_0; "FormatEx2"
0x1800765b7  mov     rcx, rax; hModule
0x1800765ba  call    cs:__imp_GetProcAddress
0x1800765c0  mov     [rdi+28h], rax
0x1800765c4  test    rax, rax
0x1800765c7  jnz     short loc_180076605
0x1800765c9  call    cs:__imp_GetLastError
0x1800765cf  mov     ebx, eax
0x1800765d1  test    eax, eax
0x1800765d3  jle     short loc_1800765DE
0x1800765d5  movzx   ebx, ax
0x1800765d8  or      ebx, 80070000h
0x1800765de  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800765e5  jz      loc_1800766F9
0x1800765eb  lea     rax, aFormatex2; "FormatEx2"
0x1800765f2  mov     [rsp+68h+var_38], ebx
0x1800765f6  mov     [rsp+68h+var_40], rax
0x1800765fb  call    McTemplateU0zzzzq_EventWriteTransfer
0x180076600  jmp     loc_1800766F9
0x180076605  mov     rcx, [rdi+8]; hModule
0x180076609  lea     rdx, aChkdskex; "ChkdskEx"
0x180076610  call    cs:__imp_GetProcAddress
0x180076616  mov     [rdi+30h], rax
0x18007661a  test    rax, rax
0x18007661d  jnz     short loc_18007664A
0x18007661f  call    cs:__imp_GetLastError
0x180076625  mov     ebx, eax
0x180076627  test    eax, eax
0x180076629  jle     short loc_180076634
0x18007662b  movzx   ebx, ax
0x18007662e  or      ebx, 80070000h
0x180076634  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x18007663b  jz      loc_1800766F9
0x180076641  lea     rax, aChkdskex_0; "ChkdskEx"
0x180076648  jmp     short loc_1800765F2
0x18007664a  mov     rcx, [rdi+8]; hModule
0x18007664e  lea     rdx, aGetdefaultfile_0; "GetDefaultFileSystem"
0x180076655  call    cs:__imp_GetProcAddress
0x18007665b  mov     [rdi+38h], rax
0x18007665f  test    rax, rax
0x180076662  jnz     short loc_18007668E
0x180076664  call    cs:__imp_GetLastError
0x18007666a  mov     ebx, eax
0x18007666c  test    eax, eax
0x18007666e  jle     short loc_180076679
0x180076670  movzx   ebx, ax
0x180076673  or      ebx, 80070000h
0x180076679  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x180076680  jz      short loc_1800766F9
0x180076682  lea     rax, aGetdefaultfile; "GetDefaultFileSystem"
0x180076689  jmp     loc_1800765F2
0x18007668e  xor     ebx, ebx
0x180076690  xor     esi, esi
0x180076692  cmp     esi, 3
0x180076695  jnb     short loc_1800766F9
0x180076697  lea     r14, ?modulesToCache@@3PAPEB_WA; wchar_t const * near * modulesToCache
0x18007669e  xor     r8d, r8d; dwFlags
0x1800766a1  mov     rcx, [r14+rsi*8]; lpLibFileName
0x1800766a5  xor     edx, edx; hFile
0x1800766a7  call    cs:__imp_LoadLibraryExW
0x1800766ad  mov     [rdi+rsi*8+10h], rax
0x1800766b2  test    rax, rax
0x1800766b5  jz      short loc_1800766BB
0x1800766b7  inc     esi
0x1800766b9  jmp     short loc_180076692
0x1800766bb  call    cs:__imp_GetLastError
0x1800766c1  mov     ebx, eax
0x1800766c3  test    eax, eax
0x1800766c5  jle     short loc_1800766D0
0x1800766c7  movzx   ebx, ax
0x1800766ca  or      ebx, 80070000h
0x1800766d0  test    cs:Microsoft_WindowsPhone_StorageHelperEnableBits, 4
0x1800766d7  jz      short loc_1800766F9
0x1800766d9  mov     rcx, [r14+rsi*8]
0x1800766dd  mov     dword ptr [rsp+68h+var_40], ebx
0x1800766e1  mov     [rsp+68h+var_48], rcx
0x1800766e6  lea     r9, aLoadlibraryex; "LoadLibraryEx"
0x1800766ed  lea     r8, aFilesystemutil_1; "FileSystemUtility::Initialize"
0x1800766f4  call    McTemplateU0zzzq_EventWriteTransfer
0x1800766f9  mov     eax, ebx
0x1800766fb  add     rsp, 40h
0x1800766ff  pop     r14
0x180076701  pop     rdi
0x180076702  pop     rsi
0x180076703  pop     rbp
0x180076704  pop     rbx
0x180076705  retn
```
