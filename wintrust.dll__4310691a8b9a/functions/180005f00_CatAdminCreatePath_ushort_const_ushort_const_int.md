# _CatAdminCreatePath(ushort const *,ushort const *,int)

- ea: `0x180005f00`
- end: `0x1800064a1`
- name: `?_CatAdminCreatePath@@YAPEAGPEBG0H@Z`
- size: `1441`
- prototype: `unsigned __int16 *__fastcall(const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180003920`
- `0x180004380`
- `0x1800213f0`

## callees

- `0x180005d00`
- `0x180005f00`
- `0x1800064a8`
- `0x180028398`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000641a`
- `api-ms-win-core-file-l1-1-0!SetEndOfFile` at `0x18000641a`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800061e1`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800061e1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800061ce`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800061ce`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006200`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006408`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006200`
- `api-ms-win-core-file-l1-1-0!SetFilePointer` at `0x180006408`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006234`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x180006234`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000625f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000643d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006053`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000625f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006432`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000643d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006059`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006059`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006496`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringA` at `0x180006496`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000617b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180005f8d`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000617b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000623d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006251`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000623d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006251`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006246`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180006246`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006164`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000619d`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180006164`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x18000619d`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000607c`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x18000607c`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x1800060a4`
- `api-ms-win-core-datetime-l1-1-0!GetTimeFormatA` at `0x1800060a4`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x1800060e6`
- `api-ms-win-core-datetime-l1-1-0!GetDateFormatA` at `0x1800060e6`

## string_xrefs

- `0x18000615b`: `%SystemRoot%\System32\CatRoot2\dberr.txt`
- `0x180006190`: `%SystemRoot%\System32\CatRoot2\dberr.txt`

## pseudocode

```c
unsigned __int16 *__fastcall _CatAdminCreatePath(const unsigned __int16 *a1, const unsigned __int16 *a2, int a3)
{
  __int64 v3; // rsi
  __int64 v5; // rbx
  const unsigned __int16 *v6; // rdi
  __int64 v8; // rcx
  unsigned int v9; // r14d
  unsigned __int64 v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // r15
  __int64 v13; // rsi
  __int64 v14; // rcx
  const unsigned __int16 *v15; // rdx
  __int64 v16; // r9
  unsigned __int16 *v17; // r8
  unsigned __int16 *v18; // rcx
  const unsigned __int16 *v19; // r11
  unsigned __int16 *v20; // rax
  __int64 v21; // r8
  __int64 v22; // rcx
  __int64 v23; // rax
  int LastError; // r14d
  int TimeFormatA; // eax
  const char *v26; // r8
  DWORD v27; // eax
  DWORD v28; // ebp
  WCHAR *v29; // rax
  WCHAR *v30; // rdi
  __int64 v31; // rbx
  HANDLE FileW; // rax
  unsigned __int16 *result; // rax
  unsigned __int16 *v34; // rdx
  __int64 v35; // rcx
  __int64 i; // r8
  unsigned __int16 *v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  unsigned __int16 *v40; // rcx
  __int64 j; // r10
  unsigned __int16 *v42; // rdx
  __int64 v43; // rcx
  __int64 v44; // rax
  unsigned __int16 *v45; // r9
  __int64 v46; // rcx
  const unsigned __int16 *v47; // rdx
  __int64 v48; // r8
  bool v49; // zf
  unsigned __int16 *v50; // rcx
  unsigned __int16 *v51; // rcx
  int v52; // eax
  int lpTimeStr; // [rsp+20h] [rbp-388h]
  CHAR *lpTimeStra; // [rsp+20h] [rbp-388h]
  int cchTime; // [rsp+28h] [rbp-380h]
  __int64 cchTimea; // [rsp+28h] [rbp-380h]
  int hTemplateFile; // [rsp+30h] [rbp-378h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-368h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+48h] [rbp-360h] BYREF
  CHAR TimeStr[256]; // [rsp+60h] [rbp-348h] BYREF
  CHAR Buffer[512]; // [rsp+160h] [rbp-248h] BYREF

  v3 = -1;
  v5 = -1;
  v6 = a2;
  do
    ++v5;
  while ( a1[v5] );
  v8 = -1;
  do
    ++v8;
  while ( a2[v8] );
  v9 = v5 + v8 + (a3 != 0) + 2;
  v10 = 2LL * v9;
  if ( v10 > 0xFFFFFFFF )
  {
    v12 = 0;
    SetLastError(0x216u);
    SystemTime = 0;
    LastError = GetLastError();
    if ( !g_fErrLogInitialized )
      ErrLog_Initialize();
    GetLocalTime(&SystemTime);
    TimeFormatA = GetTimeFormatA(0x400u, 0, &SystemTime, 0, TimeStr, 256);
    if ( (unsigned int)(TimeFormatA - 1) > 0xFF )
      goto LABEL_41;
    lpTimeStra = &TimeStr[TimeFormatA];
    *(lpTimeStra - 1) = 32;
    GetDateFormatA(0x400u, 1u, &SystemTime, 0, lpTimeStra, 256 - TimeFormatA);
    if ( (LastError & 0x1FFF0000) == 0xE5E0000 )
    {
      v26 = "CatalogDB: %s: %s at line #%u encountered JET error %d\r\n";
      v52 = -(unsigned __int16)LastError;
      if ( LastError >= 0 )
        v52 = (unsigned __int16)LastError;
      hTemplateFile = v52;
    }
    else
    {
      hTemplateFile = LastError;
      v26 = "CatalogDB: %s: %s at line #%u encountered error 0x%.8lx\r\n";
    }
    LODWORD(cchTimea) = 2851;
    StringCchPrintfA(Buffer, 0x200u, v26, TimeStr, "catadnew.cpp", cchTimea, hTemplateFile);
    NumberOfBytesWritten = 0;
    if ( g_fLogErrorsToDebugger )
      OutputDebugStringA(Buffer);
    if ( !g_fLogErrorsToFile )
      goto LABEL_41;
    v27 = ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", 0, 0);
    v28 = v27;
    if ( !v27 )
      goto LABEL_41;
    v29 = (WCHAR *)LocalAlloc(0, 2LL * v27);
    v30 = v29;
    if ( !v29 )
      goto LABEL_41;
    v31 = -1;
    if ( !ExpandEnvironmentStringsW(L"%SystemRoot%\\System32\\CatRoot2\\dberr.txt", v29, v28)
      || (FileW = CreateFileW(v30, 0xC0000000, 0, 0, 4u, 0x80u, 0), v31 = (__int64)FileW, FileW == (HANDLE)-1LL)
      || GetFileSize(FileW, 0) >= 0x30D40 && (SetFilePointer((HANDLE)v31, 0, 0, 0) == -1 || !SetEndOfFile((HANDLE)v31))
      || SetFilePointer((HANDLE)v31, 0, 0, 2u) == -1 )
    {
      LocalFree(v30);
      if ( v31 == -1 )
        goto LABEL_41;
    }
    else
    {
      do
        ++v3;
      while ( Buffer[v3] );
      WriteFile((HANDLE)v31, Buffer, v3, &NumberOfBytesWritten, 0);
      LocalFree(v30);
    }
    CloseHandle((HANDLE)v31);
LABEL_41:
    SetLastError(LastError);
    return v12;
  }
  v11 = (unsigned __int16 *)LocalAlloc(0, (unsigned int)v10);
  v12 = v11;
  if ( !v11 )
  {
    SetLastError(8u);
    SetLastError(8u);
    ErrLog_LogError(v51, 2u, 0xB2Bu, 0, lpTimeStr, cchTime);
    return v12;
  }
  v13 = 2147483646;
  if ( v9 )
  {
    if ( (unsigned __int64)(int)v9 > 0x7FFFFFFF )
    {
      *v11 = 0;
    }
    else
    {
      v14 = 2147483646;
      v15 = a1;
      v16 = (int)v9;
      v17 = v11;
      do
      {
        if ( !v14 )
          break;
        if ( !*v15 )
          break;
        *v17++ = *v15++;
        --v14;
        --v16;
      }
      while ( v16 );
      v18 = v17 - 1;
      if ( v16 )
        v18 = v17;
      *v18 = 0;
    }
  }
  v19 = L"\\";
  if ( a1[(int)v5 - 1] == 92 || !v9 )
    goto LABEL_17;
  if ( (unsigned __int64)(int)v9 > 0x7FFFFFFF )
    goto LABEL_53;
  v43 = (int)v9;
  while ( *v11 )
  {
    ++v11;
    if ( !--v43 )
    {
      v44 = 0;
      goto LABEL_76;
    }
  }
  v44 = (int)v9 - v43;
LABEL_76:
  if ( v43 )
  {
    v45 = &v12[v44];
    v46 = 2147483646;
    v47 = L"\\";
    v48 = (int)v9 - v44;
    if ( v9 != v44 )
    {
      do
      {
        if ( !v46 )
          break;
        if ( !*v47 )
          break;
        *v45++ = *v47++;
        --v46;
        --v48;
      }
      while ( v48 );
    }
    v49 = v48 == 0;
    v50 = v45 - 1;
    v21 = (int)v9;
    if ( !v49 )
      v50 = v45;
    *v50 = 0;
    v20 = v12;
  }
  else
  {
LABEL_17:
    v20 = v12;
    v21 = (int)v9;
    if ( !v9 || (unsigned __int64)(int)v9 > 0x7FFFFFFF )
      goto LABEL_53;
  }
  v22 = (int)v9;
  while ( *v20 )
  {
    ++v20;
    if ( !--v22 )
    {
      v23 = 0;
      goto LABEL_45;
    }
  }
  v23 = v21 - v22;
LABEL_45:
  if ( v22 )
  {
    v34 = &v12[v23];
    v35 = 2147483646;
    for ( i = v21 - v23; i; --i )
    {
      if ( !v35 )
        break;
      if ( !*v6 )
        break;
      *v34++ = *v6++;
      --v35;
    }
    v37 = v34 - 1;
    if ( i )
      v37 = v34;
    *v37 = 0;
  }
LABEL_53:
  if ( !a3 || !v9 )
    return v12;
  result = v12;
  if ( (unsigned __int64)(int)v9 <= 0x7FFFFFFF )
  {
    v38 = (int)v9;
    while ( *result )
    {
      ++result;
      if ( !--v38 )
      {
        v39 = 0;
        goto LABEL_61;
      }
    }
    v39 = (int)v9 - v38;
LABEL_61:
    if ( v38 )
    {
      v40 = &v12[v39];
      for ( j = (int)v9 - v39; j; --j )
      {
        if ( !v13 )
          break;
        if ( !*v19 )
          break;
        *v40++ = *v19++;
        --v13;
      }
      v42 = v40 - 1;
      if ( j )
        v42 = v40;
      *v42 = 0;
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180005f00  push    rbx
0x180005f02  push    rbp
0x180005f03  push    rsi
0x180005f04  push    rdi
0x180005f05  push    r12
0x180005f07  push    r13
0x180005f09  push    r14
0x180005f0b  sub     rsp, 370h
0x180005f12  mov     rax, cs:__security_cookie
0x180005f19  xor     rax, rsp
0x180005f1c  mov     [rsp+3A8h+var_48], rax
0x180005f24  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180005f2b  mov     r12d, r8d
0x180005f2e  mov     rbx, rsi
0x180005f31  mov     rdi, rdx
0x180005f34  mov     rbp, rcx
0x180005f37  nop     word ptr [rax+rax+00000000h]
0x180005f40  inc     rbx
0x180005f43  cmp     word ptr [rcx+rbx*2], 0
0x180005f48  jnz     short loc_180005F40
0x180005f4a  mov     rcx, rsi
0x180005f4d  nop     dword ptr [rax]
0x180005f50  inc     rcx
0x180005f53  cmp     word ptr [rdx+rcx*2], 0
0x180005f58  jnz     short loc_180005F50
0x180005f5a  xor     eax, eax
0x180005f5c  mov     [rsp+3A8h+arg_10], r15
0x180005f64  test    r12d, r12d
0x180005f67  mov     r13d, 0FFFFFFFFh
0x180005f6d  setnz   al
0x180005f70  lea     r14d, [rax+2]
0x180005f74  add     r14d, ecx
0x180005f77  add     r14d, ebx
0x180005f7a  mov     eax, r14d
0x180005f7d  add     rax, rax
0x180005f80  cmp     rax, r13
0x180005f83  ja      loc_18000604B
0x180005f89  mov     edx, eax; uBytes
0x180005f8b  xor     ecx, ecx; uFlags
0x180005f8d  call    cs:__imp_LocalAlloc
0x180005f93  mov     r15, rax
0x180005f96  test    rax, rax
0x180005f99  jz      loc_18000642D
0x180005f9f  movsxd  r10, r14d
0x180005fa2  mov     esi, 7FFFFFFEh
0x180005fa7  test    r14d, r14d
0x180005faa  jz      short loc_180005FF6
0x180005fac  cmp     r10, 7FFFFFFFh
0x180005fb3  ja      loc_18000645B
0x180005fb9  mov     ecx, esi
0x180005fbb  mov     rdx, rbp
0x180005fbe  mov     r9, r10
0x180005fc1  mov     r8, rax
0x180005fc4  test    rcx, rcx
0x180005fc7  jz      short loc_180005FE6
0x180005fc9  movzx   eax, word ptr [rdx]
0x180005fcc  test    ax, ax
0x180005fcf  jz      short loc_180005FE6
0x180005fd1  mov     [r8], ax
0x180005fd5  add     rdx, 2
0x180005fd9  add     r8, 2
0x180005fdd  dec     rcx
0x180005fe0  sub     r9, 1
0x180005fe4  jnz     short loc_180005FC4
0x180005fe6  test    r9, r9
0x180005fe9  lea     rcx, [r8-2]
0x180005fed  cmovnz  rcx, r8
0x180005ff1  xor     eax, eax
0x180005ff3  mov     [rcx], ax
0x180005ff6  movsxd  rax, ebx
0x180005ff9  lea     r11, asc_1800557E4; "\\"
0x180006000  cmp     word ptr [rbp+rax*2-2], 5Ch ; '\'
0x180006006  jnz     loc_180006369
0x18000600c  mov     rax, r15
0x18000600f  mov     r8, r10
0x180006012  test    r14d, r14d
0x180006015  jz      loc_1800062E1
0x18000601b  cmp     r10, 7FFFFFFFh
0x180006022  ja      loc_1800062E1
0x180006028  mov     rcx, r10
0x18000602b  nop     dword ptr [rax+rax+00h]
0x180006030  cmp     word ptr [rax], 0
0x180006034  jz      loc_180006292
0x18000603a  add     rax, 2
0x18000603e  sub     rcx, 1
0x180006042  jnz     short loc_180006030
0x180006044  xor     eax, eax
0x180006046  jmp     loc_180006298
0x18000604b  mov     ecx, 216h; dwErrCode
0x180006050  xor     r15d, r15d
0x180006053  call    cs:__imp_SetLastError
0x180006059  call    cs:__imp_GetLastError
0x18000605f  cmp     cs:?g_fErrLogInitialized@@3HA, r15d; int g_fErrLogInitialized
0x180006066  xorps   xmm0, xmm0
0x180006069  movups  xmmword ptr [rsp+3A8h+SystemTime.wYear], xmm0
0x18000606e  mov     r14d, eax
0x180006071  jz      loc_180006466
0x180006077  lea     rcx, [rsp+3A8h+SystemTime]; lpSystemTime
0x18000607c  call    cs:__imp_GetLocalTime
0x180006082  lea     rax, [rsp+3A8h+TimeStr]
0x180006087  mov     ebx, 100h
0x18000608c  mov     dword ptr [rsp+3A8h+cchTime], ebx; cchTime
0x180006090  lea     r8, [rsp+3A8h+SystemTime]; lpTime
0x180006095  xor     r9d, r9d; lpFormat
0x180006098  mov     [rsp+3A8h+lpTimeStr], rax; lpTimeStr
0x18000609d  xor     edx, edx; dwFlags
0x18000609f  mov     ecx, 400h; Locale
0x1800060a4  call    cs:__imp_GetTimeFormatA
0x1800060aa  lea     edx, [rax-1]
0x1800060ad  cmp     edx, 0FFh
0x1800060b3  ja      loc_18000625C
0x1800060b9  movsxd  rdx, eax
0x1800060bc  lea     r8, [rsp+3A8h+TimeStr]
0x1800060c1  add     r8, rdx
0x1800060c4  sub     ebx, eax
0x1800060c6  mov     dword ptr [rsp+3A8h+cchTime], ebx; cchDate
0x1800060ca  xor     r9d, r9d; lpFormat
0x1800060cd  mov     [rsp+3A8h+lpTimeStr], r8; lpDateStr
0x1800060d2  mov     edx, 1; dwFlags
0x1800060d7  mov     ecx, 400h; Locale
0x1800060dc  mov     byte ptr [r8-1], 20h ; ' '
0x1800060e1  lea     r8, [rsp+3A8h+SystemTime]; lpDate
0x1800060e6  call    cs:__imp_GetDateFormatA
0x1800060ec  mov     eax, r14d
0x1800060ef  lea     r9, [rsp+3A8h+TimeStr]
0x1800060f4  and     eax, 1FFF0000h
0x1800060f9  mov     edx, 200h; unsigned __int64
0x1800060fe  cmp     eax, 0E5E0000h
0x180006103  jz      loc_180006470
0x180006109  mov     [rsp+3A8h+hTemplateFile], r14d
0x18000610e  lea     r8, aCatalogdbSSAtL_0; "CatalogDB: %s: %s at line #%u encounter"...
0x180006115  lea     rax, aCatadnewCpp; "catadnew.cpp"
0x18000611c  mov     dword ptr [rsp+3A8h+cchTime], 0B23h
0x180006124  lea     rcx, [rsp+3A8h+Buffer]; char *
0x18000612c  mov     [rsp+3A8h+lpTimeStr], rax
0x180006131  call    ?StringCchPrintfA@@YAJPEAD_KPEBDZZ; StringCchPrintfA(char *,unsigned __int64,char const *,...)
0x180006136  xor     r12d, r12d
0x180006139  cmp     cs:?g_fLogErrorsToDebugger@@3HA, r12d; int g_fLogErrorsToDebugger
0x180006140  mov     [rsp+3A8h+NumberOfBytesWritten], r12d
0x180006145  jnz     loc_18000648E
0x18000614b  cmp     cs:?g_fLogErrorsToFile@@3HA, r12d; int g_fLogErrorsToFile
0x180006152  jz      loc_18000625C
0x180006158  xor     r8d, r8d; nSize
0x18000615b  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180006162  xor     edx, edx; lpDst
0x180006164  call    cs:__imp_ExpandEnvironmentStringsW
0x18000616a  mov     ebp, eax
0x18000616c  test    eax, eax
0x18000616e  jz      loc_18000625C
0x180006174  mov     edx, ebp
0x180006176  xor     ecx, ecx; uFlags
0x180006178  add     rdx, rdx; uBytes
0x18000617b  call    cs:__imp_LocalAlloc
0x180006181  mov     rdi, rax
0x180006184  test    rax, rax
0x180006187  jz      loc_18000625C
0x18000618d  mov     r8d, ebp; nSize
0x180006190  lea     rcx, Src; "%SystemRoot%\\System32\\CatRoot2\\dberr"...
0x180006197  mov     rdx, rax; lpDst
0x18000619a  mov     rbx, rsi
0x18000619d  call    cs:__imp_ExpandEnvironmentStringsW
0x1800061a3  test    eax, eax
0x1800061a5  jz      loc_18000624E
0x1800061ab  mov     qword ptr [rsp+3A8h+hTemplateFile], r12; hTemplateFile
0x1800061b0  xor     r9d, r9d; lpSecurityAttributes
0x1800061b3  mov     dword ptr [rsp+3A8h+cchTime], 80h; dwFlagsAndAttributes
0x1800061bb  xor     r8d, r8d; dwShareMode
0x1800061be  mov     edx, 0C0000000h; dwDesiredAccess
0x1800061c3  mov     dword ptr [rsp+3A8h+lpTimeStr], 4; dwCreationDisposition
0x1800061cb  mov     rcx, rdi; lpFileName
0x1800061ce  call    cs:__imp_CreateFileW
0x1800061d4  mov     rbx, rax
0x1800061d7  cmp     rax, rsi
0x1800061da  jz      short loc_18000624E
0x1800061dc  xor     edx, edx; lpFileSizeHigh
0x1800061de  mov     rcx, rax; hFile
0x1800061e1  call    cs:__imp_GetFileSize
0x1800061e7  cmp     eax, 30D40h
0x1800061ec  jnb     loc_1800063FD
0x1800061f2  mov     r9d, 2; dwMoveMethod
0x1800061f8  xor     r8d, r8d; lpDistanceToMoveHigh
0x1800061fb  xor     edx, edx; lDistanceToMove
0x1800061fd  mov     rcx, rbx; hFile
0x180006200  call    cs:__imp_SetFilePointer
0x180006206  cmp     eax, r13d
0x180006209  jz      short loc_18000624E
0x18000620b  lea     rax, [rsp+3A8h+Buffer]
0x180006213  inc     rsi
0x180006216  cmp     [rax+rsi], r12b
0x18000621a  jnz     short loc_180006213
0x18000621c  mov     r8d, esi; nNumberOfBytesToWrite
0x18000621f  mov     [rsp+3A8h+lpTimeStr], r12; lpOverlapped
0x180006224  lea     r9, [rsp+3A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x180006229  mov     rcx, rbx; hFile
0x18000622c  lea     rdx, [rsp+3A8h+Buffer]; lpBuffer
0x180006234  call    cs:__imp_WriteFile
0x18000623a  mov     rcx, rdi; hMem
0x18000623d  call    cs:__imp_LocalFree
0x180006243  mov     rcx, rbx; hObject
0x180006246  call    cs:__imp_CloseHandle
0x18000624c  jmp     short loc_18000625C
0x18000624e  mov     rcx, rdi; hMem
0x180006251  call    cs:__imp_LocalFree
0x180006257  cmp     rbx, rsi
0x18000625a  jnz     short loc_180006243
0x18000625c  mov     ecx, r14d; dwErrCode
0x18000625f  call    cs:__imp_SetLastError
0x180006265  mov     rax, r15
0x180006268  mov     r15, [rsp+3A8h+arg_10]
0x180006270  mov     rcx, [rsp+3A8h+var_48]
0x180006278  xor     rcx, rsp; StackCookie
0x18000627b  call    __security_check_cookie
0x180006280  add     rsp, 370h
0x180006287  pop     r14
0x180006289  pop     r13
0x18000628b  pop     r12
0x18000628d  pop     rdi
0x18000628e  pop     rsi
0x18000628f  pop     rbp
0x180006290  pop     rbx
0x180006291  retn
0x180006292  mov     rax, r8
0x180006295  sub     rax, rcx
0x180006298  test    rcx, rcx
0x18000629b  jz      short loc_1800062E1
0x18000629d  lea     rdx, [r15+rax*2]
0x1800062a1  mov     rcx, rsi
0x1800062a4  sub     r8, rax
0x1800062a7  jz      short loc_1800062D1
0x1800062a9  nop     dword ptr [rax+00000000h]
0x1800062b0  test    rcx, rcx
0x1800062b3  jz      short loc_1800062D1
0x1800062b5  movzx   eax, word ptr [rdi]
0x1800062b8  test    ax, ax
0x1800062bb  jz      short loc_1800062D1
0x1800062bd  mov     [rdx], ax
0x1800062c0  add     rdi, 2
0x1800062c4  add     rdx, 2
0x1800062c8  dec     rcx
0x1800062cb  sub     r8, 1
0x1800062cf  jnz     short loc_1800062B0
0x1800062d1  test    r8, r8
0x1800062d4  lea     rcx, [rdx-2]
0x1800062d8  cmovnz  rcx, rdx
0x1800062dc  xor     eax, eax
0x1800062de  mov     [rcx], ax
0x1800062e1  test    r12d, r12d
0x1800062e4  jz      loc_180006265
0x1800062ea  test    r14d, r14d
0x1800062ed  jz      loc_180006265
0x1800062f3  mov     rax, r15
0x1800062f6  cmp     r10, 7FFFFFFFh
0x1800062fd  ja      loc_180006268
0x180006303  mov     rcx, r10
0x180006306  cmp     word ptr [rax], 0
0x18000630a  jz      short loc_18000631A
0x18000630c  add     rax, 2
0x180006310  sub     rcx, 1
0x180006314  jnz     short loc_180006306
0x180006316  xor     eax, eax
0x180006318  jmp     short loc_180006320
0x18000631a  mov     rax, r10
0x18000631d  sub     rax, rcx
0x180006320  test    rcx, rcx
0x180006323  jz      loc_180006265
0x180006329  lea     rcx, [r15+rax*2]
0x18000632d  sub     r10, rax
0x180006330  jz      short loc_180006354
0x180006332  test    rsi, rsi
0x180006335  jz      short loc_180006354
0x180006337  movzx   eax, word ptr [r11]
0x18000633b  test    ax, ax
0x18000633e  jz      short loc_180006354
0x180006340  mov     [rcx], ax
0x180006343  add     r11, 2
0x180006347  add     rcx, 2
0x18000634b  dec     rsi
0x18000634e  sub     r10, 1
0x180006352  jnz     short loc_180006332
0x180006354  test    r10, r10
0x180006357  lea     rdx, [rcx-2]
0x18000635b  cmovnz  rdx, rcx
0x18000635f  xor     ecx, ecx
0x180006361  mov     [rdx], cx
0x180006364  jmp     loc_180006265
0x180006369  test    r14d, r14d
0x18000636c  jz      loc_18000600C
0x180006372  cmp     r10, 7FFFFFFFh
0x180006379  ja      loc_1800062E1
0x18000637f  mov     rcx, r10
0x180006382  mov     rax, r15
0x180006385  cmp     word ptr [rax], 0
0x180006389  jz      short loc_180006399
0x18000638b  add     rax, 2
0x18000638f  sub     rcx, 1
0x180006393  jnz     short loc_180006385
0x180006395  xor     eax, eax
0x180006397  jmp     short loc_18000639F
0x180006399  mov     rax, r10
0x18000639c  sub     rax, rcx
  ... truncated ...
```
