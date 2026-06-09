# CoGetModuleArchitecture

- ea: `0x18000ae40`
- end: `0x18000b303`
- name: `CoGetModuleArchitecture`
- size: `1219`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, _DWORD *)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000acac`
- `0x18000c674`
- `0x180062934`
- `0x1800df5f0`

## callees

- `0x18000ae40`
- `0x180034540`
- `0x180040918`
- `0x180070740`
- `0x1800b27e0`
- `0x18010b010`

## import_xrefs

- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x18000b1f3`
- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x18000b1f3`
- `ntdll!RtlImageNtHeaderEx` at `0x18000b1dc`
- `ntdll!RtlImageNtHeaderEx` at `0x18000b1dc`
- `ntdll!RtlNtStatusToDosError` at `0x18000b20b`
- `ntdll!RtlNtStatusToDosError` at `0x18000b20b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b15c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000aeca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000afc5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b007`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b088`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0f4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b15c`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000b07e`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x18000b07e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aeb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000afae`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000aeb3`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000afae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2ba`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2a7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000b2ba`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000b299`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x18000b299`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b14d`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x18000b14d`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b0e2`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x18000b0e2`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000af7f`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x18000af7f`

## string_xrefs

- `0x18000b066`: `onecore\com\combase\catalog\class.cxx`
- `0x18000b1b3`: `onecore\com\combase\catalog\class.cxx`
- `0x18000b265`: `onecore\com\combase\catalog\class.cxx`

## pseudocode

```c
__int64 __fastcall CoGetModuleArchitecture(LPCWSTR lpFileName, _DWORD *a2)
{
  WCHAR *v4; // r13
  WCHAR *lpBuffer; // rsi
  char *FileW; // r15
  void *v7; // rsp
  WCHAR *v8; // rax
  unsigned int v9; // edi
  signed int v10; // eax
  int v11; // r8d
  signed int LastError; // eax
  signed int v13; // eax
  WCHAR *FileMappingW; // rax
  signed int v15; // eax
  void *v16; // rax
  signed int v17; // eax
  const void *v18; // rcx
  int v19; // eax
  signed int v20; // eax
  HANDLE v22; // [rsp+10h] [rbp-230h]
  char v23; // [rsp+20h] [rbp-220h] BYREF
  const void *v24; // [rsp+240h] [rbp+0h]
  unsigned int v25; // [rsp+24Ch] [rbp+Ch]
  _LARGE_INTEGER FileSize; // [rsp+250h] [rbp+10h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+258h] [rbp+18h] BYREF
  char *v28; // [rsp+260h] [rbp+20h]
  WCHAR *v29; // [rsp+268h] [rbp+28h]
  LPWSTR FilePart[2]; // [rsp+270h] [rbp+30h] BYREF

  FileSize.QuadPart = 0;
  *a2 = 0;
  if ( !lpFileName || *lpFileName == 34 )
    return 2147942487LL;
  v4 = 0;
  lpBuffer = 0;
  v29 = 0;
  FileW = (char *)CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v28 = FileW;
  if ( FileW != (char *)-1LL || GetLastError() != 2 )
    goto LABEL_18;
  FilePart[0] = 0;
  if ( (unsigned __int64)g_ulMaxStackAllocSize >= 0x20A && (unsigned __int64)(g_ulAdditionalProbeSize + 530) >= 0x20A )
  {
    if ( (unsigned int)VerifyStackAvailable() )
    {
      v7 = alloca(544);
      lpBuffer = (WCHAR *)&v23;
    }
    if ( !lpBuffer )
      goto LABEL_12;
    *(_DWORD *)lpBuffer = 1801679955;
    lpBuffer += 4;
  }
  if ( !lpBuffer )
  {
LABEL_12:
    v8 = (WCHAR *)((__int64 (__fastcall *)(__int64))g_pfnAllocate)(530);
    lpBuffer = v8;
    if ( v8 )
    {
      *(_DWORD *)v8 = 1885431112;
      lpBuffer = v8 + 4;
    }
  }
  v29 = lpBuffer;
  if ( !lpBuffer )
  {
    v9 = -2147024882;
    goto LABEL_64;
  }
  if ( SearchPathW(0, lpFileName, 0, 0x104u, lpBuffer, FilePart) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_64;
    v11 = 2262;
    goto LABEL_31;
  }
  FileW = (char *)CreateFileW(lpBuffer, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  v28 = FileW;
LABEL_18:
  if ( FileW == (char *)-1LL )
  {
    v10 = GetLastError();
    v9 = v10;
    if ( v10 > 0 )
      v9 = (unsigned __int16)v10 | 0x80070000;
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_64;
    v11 = 2280;
    goto LABEL_31;
  }
  if ( !GetFileSizeEx(FileW, &FileSize) )
  {
    v13 = GetLastError();
    v9 = v13;
    if ( v13 > 0 )
      v9 = (unsigned __int16)v13 | 0x80070000;
    if ( !dword_18014E4B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
      goto LABEL_64;
    v11 = 2286;
    goto LABEL_31;
  }
  FileMappingW = (WCHAR *)CreateFileMappingW(FileW, 0, 2u, 0, 0, 0);
  v4 = FileMappingW;
  FilePart[1] = FileMappingW;
  if ( FileMappingW )
  {
    v9 = 0;
    v16 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
    v24 = v16;
    if ( v16 )
    {
      NtHeader = 0;
      v19 = RtlImageNtHeaderEx(2u, v16, FileSize.QuadPart, &NtHeader);
      if ( v19 >= 0 && NtHeader )
      {
        *a2 = (unsigned __int16)RtlWow64GetEquivalentMachineCHPE(NtHeader->FileHeader.Machine);
        v18 = v24;
      }
      else
      {
        v20 = RtlNtStatusToDosError(v19);
        v9 = v20;
        if ( v20 > 0 )
          v9 = (unsigned __int16)v20 | 0x80070000;
        v25 = v9;
        if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
        {
          LODWORD(v22) = v9;
          ComTraceMessageT<unsigned short *,long>(
            (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
            (unsigned int)"CoGetModuleArchitecture",
            2321,
            0,
            (__int64)L"Module:%ws %!HRESULT!",
            lpFileName,
            v22);
        }
        v18 = v24;
      }
    }
    else
    {
      v17 = GetLastError();
      v9 = v17;
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
      if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
      {
        LODWORD(v22) = v9;
        ComTraceMessageT<unsigned short *,long>(
          (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
          (unsigned int)"CoGetModuleArchitecture",
          2310,
          0,
          (__int64)L"Module:%ws %!HRESULT!",
          lpFileName,
          v22);
      }
      v18 = v24;
    }
    goto LABEL_65;
  }
  v15 = GetLastError();
  v9 = v15;
  if ( v15 > 0 )
    v9 = (unsigned __int16)v15 | 0x80070000;
  if ( dword_18014E4B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
  {
    v11 = 2302;
LABEL_31:
    LODWORD(v22) = v9;
    ComTraceMessageT<unsigned short *,long>(
      (unsigned int)"onecore\\com\\combase\\catalog\\class.cxx",
      (unsigned int)"CoGetModuleArchitecture",
      v11,
      0,
      (__int64)L"Module:%ws %!HRESULT!",
      lpFileName,
      v22);
  }
LABEL_64:
  v18 = 0;
LABEL_65:
  if ( v18 )
    UnmapViewOfFile(v18);
  if ( v4 )
    CloseHandle(v4);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  if ( lpBuffer )
  {
    if ( *((_DWORD *)lpBuffer - 2) == 1885431112 )
      ((void (*)(void))g_pfnFree)();
  }
  return v9;
}

```

## disassembly

```asm
0x18000ae40  push    rbp
0x18000ae42  push    rbx
0x18000ae43  push    rsi
0x18000ae44  push    rdi
0x18000ae45  push    r12
0x18000ae47  push    r13
0x18000ae49  push    r14
0x18000ae4b  push    r15
0x18000ae4d  sub     rsp, 98h
0x18000ae54  lea     rbp, [rsp+40h]
0x18000ae59  mov     rax, cs:__security_cookie
0x18000ae60  xor     rax, rbp
0x18000ae63  mov     [rbp+90h+var_50], rax
0x18000ae67  mov     r12, rdx
0x18000ae6a  mov     r14, rcx
0x18000ae6d  xor     ebx, ebx
0x18000ae6f  mov     qword ptr [rbp+90h+FileSize], rbx
0x18000ae73  mov     [rdx], ebx
0x18000ae75  test    rcx, rcx
0x18000ae78  jz      loc_18000B2E1
0x18000ae7e  cmp     word ptr [rcx], 22h ; '"'
0x18000ae82  jz      loc_18000B2E1
0x18000ae88  mov     r13d, ebx
0x18000ae8b  mov     esi, ebx
0x18000ae8d  mov     [rbp+90h+var_68], rbx
0x18000ae91  mov     [rsp+0D0h+hTemplateFile], rbx; hTemplateFile
0x18000ae96  mov     edi, 8000000h
0x18000ae9b  mov     [rsp+0D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x18000ae9f  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000aea7  xor     r9d, r9d; lpSecurityAttributes
0x18000aeaa  mov     edx, 80000000h; dwDesiredAccess
0x18000aeaf  lea     r8d, [rbx+1]; dwShareMode
0x18000aeb3  call    cs:__imp_CreateFileW
0x18000aeb9  mov     r15, rax
0x18000aebc  mov     [rbp+90h+var_70], rax
0x18000aec0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000aec4  jnz     loc_18000AFBB
0x18000aeca  call    cs:__imp_GetLastError
0x18000aed0  cmp     eax, 2
0x18000aed3  jnz     loc_18000AFBB
0x18000aed9  mov     [rbp+90h+FilePart], rbx
0x18000aedd  mov     edx, 20Ah
0x18000aee2  cmp     cs:g_ulMaxStackAllocSize, rdx
0x18000aee9  jb      short loc_18000AF28
0x18000aeeb  mov     rcx, cs:g_ulAdditionalProbeSize
0x18000aef2  add     rcx, 212h
0x18000aef9  cmp     rcx, rdx
0x18000aefc  jb      short loc_18000AF28
0x18000aefe  call    VerifyStackAvailable
0x18000af03  test    eax, eax
0x18000af05  jz      short loc_18000AF19
0x18000af07  mov     eax, [rsp+0D0h+var_D0]
0x18000af0a  mov     eax, 220h
0x18000af0f  sub     rsp, rax
0x18000af12  lea     rsi, [rsp+2F0h+var_2B0]
0x18000af17  mov     eax, [rsi]
0x18000af19  test    rsi, rsi
0x18000af1c  jz      short loc_18000AF2D
0x18000af1e  mov     dword ptr [rsi], 6B637453h
0x18000af24  add     rsi, 8
0x18000af28  test    rsi, rsi
0x18000af2b  jnz     short loc_18000AF50
0x18000af2d  mov     ecx, 212h
0x18000af32  mov     rax, cs:g_pfnAllocate
0x18000af39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af3e  mov     rsi, rax
0x18000af41  test    rax, rax
0x18000af44  jz      short loc_18000AF50
0x18000af46  mov     dword ptr [rax], 70616548h
0x18000af4c  add     rsi, 8
0x18000af50  mov     [rbp+90h+var_68], rsi
0x18000af54  test    rsi, rsi
0x18000af57  jnz     short loc_18000AF63
0x18000af59  mov     edi, 8007000Eh
0x18000af5e  jmp     loc_18000B291
0x18000af63  lea     rax, [rbp+90h+FilePart]
0x18000af67  mov     [rsp+2F0h+lpFilePart], rax; lpFilePart
0x18000af6c  mov     [rsp+2F0h+lpBuffer], rsi; lpBuffer
0x18000af71  mov     r9d, 104h; nBufferLength
0x18000af77  xor     r8d, r8d; lpExtension
0x18000af7a  mov     rdx, r14; lpFileName
0x18000af7d  xor     ecx, ecx; lpPath
0x18000af7f  call    cs:__imp_SearchPathW
0x18000af85  dec     eax
0x18000af87  cmp     eax, 103h
0x18000af8c  ja      short loc_18000B007
0x18000af8e  mov     [rsp+2F0h+var_2C0], rbx; hTemplateFile
0x18000af93  mov     dword ptr [rsp+2F0h+lpFilePart], edi; dwFlagsAndAttributes
0x18000af97  mov     dword ptr [rsp+2F0h+lpBuffer], 3; dwCreationDisposition
0x18000af9f  xor     r9d, r9d; lpSecurityAttributes
0x18000afa2  mov     edx, 80000000h; dwDesiredAccess
0x18000afa7  lea     r8d, [r9+1]; dwShareMode
0x18000afab  mov     rcx, rsi; lpFileName
0x18000afae  call    cs:__imp_CreateFileW
0x18000afb4  mov     r15, rax
0x18000afb7  mov     [rbp+90h+var_70], rax
0x18000afbb  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x18000afbf  jnz     loc_18000B077
0x18000afc5  call    cs:__imp_GetLastError
0x18000afcb  mov     edi, eax
0x18000afcd  test    eax, eax
0x18000afcf  jle     short loc_18000AFDA
0x18000afd1  movzx   edi, ax
0x18000afd4  or      edi, 80070000h
0x18000afda  mov     eax, cs:dword_18014E4B8
0x18000afe0  test    eax, eax
0x18000afe2  jnz     short loc_18000AFFF
0x18000afe4  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000afea  jz      loc_18000B291
0x18000aff0  xor     ecx, ecx
0x18000aff2  call    IsWppLevelEnabled
0x18000aff7  test    al, al
0x18000aff9  jz      loc_18000B291
0x18000afff  mov     r8d, 8E8h
0x18000b005  jmp     short loc_18000B047
0x18000b007  call    cs:__imp_GetLastError
0x18000b00d  mov     edi, eax
0x18000b00f  test    eax, eax
0x18000b011  jle     short loc_18000B01C
0x18000b013  movzx   edi, ax
0x18000b016  or      edi, 80070000h
0x18000b01c  mov     eax, cs:dword_18014E4B8
0x18000b022  test    eax, eax
0x18000b024  jnz     short loc_18000B041
0x18000b026  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000b02c  jz      loc_18000B291
0x18000b032  xor     ecx, ecx
0x18000b034  call    IsWppLevelEnabled
0x18000b039  test    al, al
0x18000b03b  jz      loc_18000B291
0x18000b041  mov     r8d, 8D6h
0x18000b047  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x18000b04b  mov     [rsp+2F0h+lpFilePart], r14
0x18000b050  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x18000b057  xor     r9d, r9d
0x18000b05a  mov     [rsp+2F0h+lpBuffer], rax
0x18000b05f  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x18000b066  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18000b06d  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18000b072  jmp     loc_18000B291
0x18000b077  lea     rdx, [rbp+90h+FileSize]; lpFileSize
0x18000b07b  mov     rcx, r15; hFile
0x18000b07e  call    cs:__imp_GetFileSizeEx
0x18000b084  test    eax, eax
0x18000b086  jnz     short loc_18000B0CD
0x18000b088  call    cs:__imp_GetLastError
0x18000b08e  mov     edi, eax
0x18000b090  test    eax, eax
0x18000b092  jle     short loc_18000B09D
0x18000b094  movzx   edi, ax
0x18000b097  or      edi, 80070000h
0x18000b09d  mov     eax, cs:dword_18014E4B8
0x18000b0a3  test    eax, eax
0x18000b0a5  jnz     short loc_18000B0C2
0x18000b0a7  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000b0ad  jz      loc_18000B291
0x18000b0b3  xor     ecx, ecx
0x18000b0b5  call    IsWppLevelEnabled
0x18000b0ba  test    al, al
0x18000b0bc  jz      loc_18000B291
0x18000b0c2  mov     r8d, 8EEh
0x18000b0c8  jmp     loc_18000B047
0x18000b0cd  mov     [rsp+2F0h+lpFilePart], rbx; lpName
0x18000b0d2  mov     dword ptr [rsp+2F0h+lpBuffer], ebx; dwMaximumSizeLow
0x18000b0d6  xor     r9d, r9d; dwMaximumSizeHigh
0x18000b0d9  xor     edx, edx; lpFileMappingAttributes
0x18000b0db  lea     r8d, [r9+2]; flProtect
0x18000b0df  mov     rcx, r15; hFile
0x18000b0e2  call    cs:__imp_CreateFileMappingW
0x18000b0e8  mov     r13, rax
0x18000b0eb  mov     [rbp+90h+var_58], rax
0x18000b0ef  test    rax, rax
0x18000b0f2  jnz     short loc_18000B139
0x18000b0f4  call    cs:__imp_GetLastError
0x18000b0fa  mov     edi, eax
0x18000b0fc  test    eax, eax
0x18000b0fe  jle     short loc_18000B109
0x18000b100  movzx   edi, ax
0x18000b103  or      edi, 80070000h
0x18000b109  mov     eax, cs:dword_18014E4B8
0x18000b10f  test    eax, eax
0x18000b111  jnz     short loc_18000B12E
0x18000b113  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000b119  jz      loc_18000B291
0x18000b11f  xor     ecx, ecx
0x18000b121  call    IsWppLevelEnabled
0x18000b126  test    al, al
0x18000b128  jz      loc_18000B291
0x18000b12e  mov     r8d, 8FEh
0x18000b134  jmp     loc_18000B047
0x18000b139  mov     edi, ebx
0x18000b13b  mov     [rsp+2F0h+lpBuffer], rbx; dwNumberOfBytesToMap
0x18000b140  xor     r9d, r9d; dwFileOffsetLow
0x18000b143  xor     r8d, r8d; dwFileOffsetHigh
0x18000b146  lea     edx, [r9+4]; dwDesiredAccess
0x18000b14a  mov     rcx, rax; hFileMappingObject
0x18000b14d  call    cs:__imp_MapViewOfFile
0x18000b153  mov     [rbp+90h+var_90], rax
0x18000b157  test    rax, rax
0x18000b15a  jnz     short loc_18000B1C8
0x18000b15c  call    cs:__imp_GetLastError
0x18000b162  mov     edi, eax
0x18000b164  test    eax, eax
0x18000b166  jle     short loc_18000B171
0x18000b168  movzx   edi, ax
0x18000b16b  or      edi, 80070000h
0x18000b171  mov     eax, cs:dword_18014E4B8
0x18000b177  test    eax, eax
0x18000b179  jnz     short loc_18000B18E
0x18000b17b  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000b181  jz      short loc_18000B1BF
0x18000b183  xor     ecx, ecx
0x18000b185  call    IsWppLevelEnabled
0x18000b18a  test    al, al
0x18000b18c  jz      short loc_18000B1BF
0x18000b18e  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x18000b192  mov     [rsp+2F0h+lpFilePart], r14
0x18000b197  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x18000b19e  mov     [rsp+2F0h+lpBuffer], rax
0x18000b1a3  xor     r9d, r9d
0x18000b1a6  mov     r8d, 906h
0x18000b1ac  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x18000b1b3  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18000b1ba  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18000b1bf  mov     rcx, [rbp+90h+var_90]
0x18000b1c3  jmp     loc_18000B294
0x18000b1c8  mov     [rbp+90h+NtHeader], rbx
0x18000b1cc  lea     r9, [rbp+90h+NtHeader]; NtHeader
0x18000b1d0  mov     r8, qword ptr [rbp+90h+FileSize]; Size
0x18000b1d4  mov     rdx, rax; BaseAddress
0x18000b1d7  mov     ecx, 2; Flags
0x18000b1dc  call    cs:__imp_RtlImageNtHeaderEx
0x18000b1e2  test    eax, eax
0x18000b1e4  js      short loc_18000B209
0x18000b1e6  mov     rcx, [rbp+90h+NtHeader]
0x18000b1ea  test    rcx, rcx
0x18000b1ed  jz      short loc_18000B209
0x18000b1ef  movzx   ecx, word ptr [rcx+4]
0x18000b1f3  call    cs:__imp_RtlWow64GetEquivalentMachineCHPE
0x18000b1f9  movzx   eax, ax
0x18000b1fc  mov     [r12], eax
0x18000b200  mov     rcx, [rbp+90h+var_90]
0x18000b204  jmp     loc_18000B294
0x18000b209  mov     ecx, eax; Status
0x18000b20b  call    cs:__imp_RtlNtStatusToDosError
0x18000b211  mov     edi, eax
0x18000b213  test    eax, eax
0x18000b215  jle     short loc_18000B220
0x18000b217  movzx   edi, ax
0x18000b21a  or      edi, 80070000h
0x18000b220  mov     [rbp+90h+var_84], edi
0x18000b223  mov     eax, cs:dword_18014E4B8
0x18000b229  test    eax, eax
0x18000b22b  jnz     short loc_18000B240
0x18000b22d  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x18000b233  jz      short loc_18000B271
0x18000b235  xor     ecx, ecx
0x18000b237  call    IsWppLevelEnabled
0x18000b23c  test    al, al
0x18000b23e  jz      short loc_18000B271
0x18000b240  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x18000b244  mov     [rsp+2F0h+lpFilePart], r14
0x18000b249  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x18000b250  mov     [rsp+2F0h+lpBuffer], rax
0x18000b255  xor     r9d, r9d
0x18000b258  mov     r8d, 911h
0x18000b25e  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x18000b265  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x18000b26c  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x18000b271  mov     rcx, [rbp+90h+var_90]
0x18000b275  jmp     short loc_18000B294
0x18000b277  mov     edi, 800703E7h
0x18000b27c  mov     [rbp+90h+var_84], edi
0x18000b27f  mov     r15, [rbp+90h+var_70]
0x18000b283  mov     r13, [rbp+90h+var_58]
0x18000b287  mov     rsi, [rbp+90h+var_68]
0x18000b28b  mov     rcx, [rbp+90h+var_90]
0x18000b28f  jmp     short loc_18000B294
0x18000b291  mov     rcx, rbx; lpBaseAddress
0x18000b294  test    rcx, rcx
0x18000b297  jz      short loc_18000B29F
0x18000b299  call    cs:__imp_UnmapViewOfFile
0x18000b29f  test    r13, r13
0x18000b2a2  jz      short loc_18000B2AD
0x18000b2a4  mov     rcx, r13; hObject
0x18000b2a7  call    cs:__imp_CloseHandle
0x18000b2ad  lea     rax, [r15-1]
0x18000b2b1  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b2b5  ja      short loc_18000B2C0
0x18000b2b7  mov     rcx, r15; hObject
0x18000b2ba  call    cs:__imp_CloseHandle
0x18000b2c0  test    rsi, rsi
0x18000b2c3  jz      short loc_18000B2DD
0x18000b2c5  lea     rcx, [rsi-8]
0x18000b2c9  cmp     dword ptr [rcx], 70616548h
0x18000b2cf  jnz     short loc_18000B2DD
0x18000b2d1  mov     rax, cs:g_pfnFree
0x18000b2d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2dd  mov     eax, edi
0x18000b2df  jmp     short loc_18000B2E6
  ... truncated ...
```
