# CoGetModuleArchitecture

- ea: `0x18001186c`
- end: `0x180011da0`
- name: `CoGetModuleArchitecture`
- size: `1332`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `4`
- callee_count: `6`
- tags: `file_ops, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800116bc`
- `0x180012430`
- `0x180067d70`
- `0x1800e6708`

## callees

- `0x18001186c`
- `0x180034260`
- `0x18004a3f4`
- `0x180074d98`
- `0x1800b7ac0`
- `0x180114010`

## import_xrefs

- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x180011c71`
- `ntdll!RtlWow64GetEquivalentMachineCHPE` at `0x180011c71`
- `ntdll!RtlImageNtHeaderEx` at `0x180011c54`
- `ntdll!RtlImageNtHeaderEx` at `0x180011c54`
- `ntdll!RtlNtStatusToDosError` at `0x180011c8f`
- `ntdll!RtlNtStatusToDosError` at `0x180011c8f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bce`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800118fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a0d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a55`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ae2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011b5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011bce`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180011ad2`
- `api-ms-win-core-file-l1-1-0!GetFileSizeEx` at `0x180011ad2`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800118df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800119f0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800118df`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800119f0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d37`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180011d50`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180011d23`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x180011d23`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180011bb9`
- `api-ms-win-core-memory-l1-1-0!MapViewOfFile` at `0x180011bb9`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011b42`
- `api-ms-win-core-memory-l1-1-0!CreateFileMappingW` at `0x180011b42`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800119b7`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x1800119b7`

## string_xrefs

- `0x180011aba`: `onecore\com\combase\catalog\class.cxx`
- `0x180011c2b`: `onecore\com\combase\catalog\class.cxx`
- `0x180011cef`: `onecore\com\combase\catalog\class.cxx`

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
    if ( (unsigned int)VerifyStackAvailable(g_ulAdditionalProbeSize + 530, 522) )
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
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
    if ( !dword_1801574B8 && (!gfEnableTracing || !(unsigned __int8)IsWppLevelEnabled(0)) )
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
        if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
      if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
  if ( dword_1801574B8 || gfEnableTracing && (unsigned __int8)IsWppLevelEnabled(0) )
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
0x18001186c  push    rbp
0x18001186e  push    rbx
0x18001186f  push    rsi
0x180011870  push    rdi
0x180011871  push    r12
0x180011873  push    r13
0x180011875  push    r14
0x180011877  push    r15
0x180011879  sub     rsp, 98h
0x180011880  lea     rbp, [rsp+40h]
0x180011885  mov     rax, cs:__security_cookie
0x18001188c  xor     rax, rbp
0x18001188f  mov     [rbp+90h+var_50], rax
0x180011893  mov     r12, rdx
0x180011896  mov     r14, rcx
0x180011899  xor     ebx, ebx
0x18001189b  mov     qword ptr [rbp+90h+FileSize], rbx
0x18001189f  mov     [rdx], ebx
0x1800118a1  test    rcx, rcx
0x1800118a4  jz      loc_180011D7D
0x1800118aa  cmp     word ptr [rcx], 22h ; '"'
0x1800118ae  jz      loc_180011D7D
0x1800118b4  mov     r13d, ebx
0x1800118b7  mov     esi, ebx
0x1800118b9  mov     [rbp+90h+var_68], rbx
0x1800118bd  mov     [rsp+0D0h+hTemplateFile], rbx; hTemplateFile
0x1800118c2  mov     edi, 8000000h
0x1800118c7  mov     [rsp+0D0h+dwFlagsAndAttributes], edi; dwFlagsAndAttributes
0x1800118cb  mov     [rsp+0D0h+dwCreationDisposition], 3; dwCreationDisposition
0x1800118d3  xor     r9d, r9d; lpSecurityAttributes
0x1800118d6  mov     edx, 80000000h; dwDesiredAccess
0x1800118db  lea     r8d, [rbx+1]; dwShareMode
0x1800118df  call    cs:__imp_CreateFileW
0x1800118e6  nop     dword ptr [rax+rax+00h]
0x1800118eb  mov     r15, rax
0x1800118ee  mov     [rbp+90h+var_70], rax
0x1800118f2  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800118f6  jnz     loc_180011A03
0x1800118fc  call    cs:__imp_GetLastError
0x180011903  nop     dword ptr [rax+rax+00h]
0x180011908  cmp     eax, 2
0x18001190b  jnz     loc_180011A03
0x180011911  mov     [rbp+90h+FilePart], rbx
0x180011915  mov     edx, 20Ah
0x18001191a  cmp     cs:g_ulMaxStackAllocSize, rdx
0x180011921  jb      short loc_180011960
0x180011923  mov     rcx, cs:g_ulAdditionalProbeSize
0x18001192a  add     rcx, 212h
0x180011931  cmp     rcx, rdx
0x180011934  jb      short loc_180011960
0x180011936  call    VerifyStackAvailable
0x18001193b  test    eax, eax
0x18001193d  jz      short loc_180011951
0x18001193f  mov     eax, [rsp+0D0h+var_D0]
0x180011942  mov     eax, 220h
0x180011947  sub     rsp, rax
0x18001194a  lea     rsi, [rsp+2F0h+var_2B0]
0x18001194f  mov     eax, [rsi]
0x180011951  test    rsi, rsi
0x180011954  jz      short loc_180011965
0x180011956  mov     dword ptr [rsi], 6B637453h
0x18001195c  add     rsi, 8
0x180011960  test    rsi, rsi
0x180011963  jnz     short loc_180011988
0x180011965  mov     ecx, 212h
0x18001196a  mov     rax, cs:g_pfnAllocate
0x180011971  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011976  mov     rsi, rax
0x180011979  test    rax, rax
0x18001197c  jz      short loc_180011988
0x18001197e  mov     dword ptr [rax], 70616548h
0x180011984  add     rsi, 8
0x180011988  mov     [rbp+90h+var_68], rsi
0x18001198c  test    rsi, rsi
0x18001198f  jnz     short loc_18001199B
0x180011991  mov     edi, 8007000Eh
0x180011996  jmp     loc_180011D1B
0x18001199b  lea     rax, [rbp+90h+FilePart]
0x18001199f  mov     [rsp+2F0h+lpFilePart], rax; lpFilePart
0x1800119a4  mov     [rsp+2F0h+lpBuffer], rsi; lpBuffer
0x1800119a9  mov     r9d, 104h; nBufferLength
0x1800119af  xor     r8d, r8d; lpExtension
0x1800119b2  mov     rdx, r14; lpFileName
0x1800119b5  xor     ecx, ecx; lpPath
0x1800119b7  call    cs:__imp_SearchPathW
0x1800119be  nop     dword ptr [rax+rax+00h]
0x1800119c3  dec     eax
0x1800119c5  cmp     eax, 103h
0x1800119ca  ja      loc_180011A55
0x1800119d0  mov     [rsp+2F0h+var_2C0], rbx; hTemplateFile
0x1800119d5  mov     dword ptr [rsp+2F0h+lpFilePart], edi; dwFlagsAndAttributes
0x1800119d9  mov     dword ptr [rsp+2F0h+lpBuffer], 3; dwCreationDisposition
0x1800119e1  xor     r9d, r9d; lpSecurityAttributes
0x1800119e4  mov     edx, 80000000h; dwDesiredAccess
0x1800119e9  lea     r8d, [r9+1]; dwShareMode
0x1800119ed  mov     rcx, rsi; lpFileName
0x1800119f0  call    cs:__imp_CreateFileW
0x1800119f7  nop     dword ptr [rax+rax+00h]
0x1800119fc  mov     r15, rax
0x1800119ff  mov     [rbp+90h+var_70], rax
0x180011a03  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180011a07  jnz     loc_180011ACB
0x180011a0d  call    cs:__imp_GetLastError
0x180011a14  nop     dword ptr [rax+rax+00h]
0x180011a19  mov     edi, eax
0x180011a1b  test    eax, eax
0x180011a1d  jle     short loc_180011A28
0x180011a1f  movzx   edi, ax
0x180011a22  or      edi, 80070000h
0x180011a28  mov     eax, cs:dword_1801574B8
0x180011a2e  test    eax, eax
0x180011a30  jnz     short loc_180011A4D
0x180011a32  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011a38  jz      loc_180011D1B
0x180011a3e  xor     ecx, ecx
0x180011a40  call    IsWppLevelEnabled
0x180011a45  test    al, al
0x180011a47  jz      loc_180011D1B
0x180011a4d  mov     r8d, 8E8h
0x180011a53  jmp     short loc_180011A9B
0x180011a55  call    cs:__imp_GetLastError
0x180011a5c  nop     dword ptr [rax+rax+00h]
0x180011a61  mov     edi, eax
0x180011a63  test    eax, eax
0x180011a65  jle     short loc_180011A70
0x180011a67  movzx   edi, ax
0x180011a6a  or      edi, 80070000h
0x180011a70  mov     eax, cs:dword_1801574B8
0x180011a76  test    eax, eax
0x180011a78  jnz     short loc_180011A95
0x180011a7a  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011a80  jz      loc_180011D1B
0x180011a86  xor     ecx, ecx
0x180011a88  call    IsWppLevelEnabled
0x180011a8d  test    al, al
0x180011a8f  jz      loc_180011D1B
0x180011a95  mov     r8d, 8D6h
0x180011a9b  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x180011a9f  mov     [rsp+2F0h+lpFilePart], r14
0x180011aa4  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180011aab  xor     r9d, r9d
0x180011aae  mov     [rsp+2F0h+lpBuffer], rax
0x180011ab3  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x180011aba  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180011ac1  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180011ac6  jmp     loc_180011D1B
0x180011acb  lea     rdx, [rbp+90h+FileSize]; lpFileSize
0x180011acf  mov     rcx, r15; hFile
0x180011ad2  call    cs:__imp_GetFileSizeEx
0x180011ad9  nop     dword ptr [rax+rax+00h]
0x180011ade  test    eax, eax
0x180011ae0  jnz     short loc_180011B2D
0x180011ae2  call    cs:__imp_GetLastError
0x180011ae9  nop     dword ptr [rax+rax+00h]
0x180011aee  mov     edi, eax
0x180011af0  test    eax, eax
0x180011af2  jle     short loc_180011AFD
0x180011af4  movzx   edi, ax
0x180011af7  or      edi, 80070000h
0x180011afd  mov     eax, cs:dword_1801574B8
0x180011b03  test    eax, eax
0x180011b05  jnz     short loc_180011B22
0x180011b07  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011b0d  jz      loc_180011D1B
0x180011b13  xor     ecx, ecx
0x180011b15  call    IsWppLevelEnabled
0x180011b1a  test    al, al
0x180011b1c  jz      loc_180011D1B
0x180011b22  mov     r8d, 8EEh
0x180011b28  jmp     loc_180011A9B
0x180011b2d  mov     [rsp+2F0h+lpFilePart], rbx; lpName
0x180011b32  mov     dword ptr [rsp+2F0h+lpBuffer], ebx; dwMaximumSizeLow
0x180011b36  xor     r9d, r9d; dwMaximumSizeHigh
0x180011b39  xor     edx, edx; lpFileMappingAttributes
0x180011b3b  lea     r8d, [r9+2]; flProtect
0x180011b3f  mov     rcx, r15; hFile
0x180011b42  call    cs:__imp_CreateFileMappingW
0x180011b49  nop     dword ptr [rax+rax+00h]
0x180011b4e  mov     r13, rax
0x180011b51  mov     [rbp+90h+var_58], rax
0x180011b55  test    rax, rax
0x180011b58  jnz     short loc_180011BA5
0x180011b5a  call    cs:__imp_GetLastError
0x180011b61  nop     dword ptr [rax+rax+00h]
0x180011b66  mov     edi, eax
0x180011b68  test    eax, eax
0x180011b6a  jle     short loc_180011B75
0x180011b6c  movzx   edi, ax
0x180011b6f  or      edi, 80070000h
0x180011b75  mov     eax, cs:dword_1801574B8
0x180011b7b  test    eax, eax
0x180011b7d  jnz     short loc_180011B9A
0x180011b7f  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011b85  jz      loc_180011D1B
0x180011b8b  xor     ecx, ecx
0x180011b8d  call    IsWppLevelEnabled
0x180011b92  test    al, al
0x180011b94  jz      loc_180011D1B
0x180011b9a  mov     r8d, 8FEh
0x180011ba0  jmp     loc_180011A9B
0x180011ba5  mov     edi, ebx
0x180011ba7  mov     [rsp+2F0h+lpBuffer], rbx; dwNumberOfBytesToMap
0x180011bac  xor     r9d, r9d; dwFileOffsetLow
0x180011baf  xor     r8d, r8d; dwFileOffsetHigh
0x180011bb2  lea     edx, [r9+4]; dwDesiredAccess
0x180011bb6  mov     rcx, rax; hFileMappingObject
0x180011bb9  call    cs:__imp_MapViewOfFile
0x180011bc0  nop     dword ptr [rax+rax+00h]
0x180011bc5  mov     [rbp+90h+var_90], rax
0x180011bc9  test    rax, rax
0x180011bcc  jnz     short loc_180011C40
0x180011bce  call    cs:__imp_GetLastError
0x180011bd5  nop     dword ptr [rax+rax+00h]
0x180011bda  mov     edi, eax
0x180011bdc  test    eax, eax
0x180011bde  jle     short loc_180011BE9
0x180011be0  movzx   edi, ax
0x180011be3  or      edi, 80070000h
0x180011be9  mov     eax, cs:dword_1801574B8
0x180011bef  test    eax, eax
0x180011bf1  jnz     short loc_180011C06
0x180011bf3  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011bf9  jz      short loc_180011C37
0x180011bfb  xor     ecx, ecx
0x180011bfd  call    IsWppLevelEnabled
0x180011c02  test    al, al
0x180011c04  jz      short loc_180011C37
0x180011c06  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x180011c0a  mov     [rsp+2F0h+lpFilePart], r14
0x180011c0f  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180011c16  mov     [rsp+2F0h+lpBuffer], rax
0x180011c1b  xor     r9d, r9d
0x180011c1e  mov     r8d, 906h
0x180011c24  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x180011c2b  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180011c32  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180011c37  mov     rcx, [rbp+90h+var_90]
0x180011c3b  jmp     loc_180011D1E
0x180011c40  mov     [rbp+90h+NtHeader], rbx
0x180011c44  lea     r9, [rbp+90h+NtHeader]; NtHeader
0x180011c48  mov     r8, qword ptr [rbp+90h+FileSize]; Size
0x180011c4c  mov     rdx, rax; BaseAddress
0x180011c4f  mov     ecx, 2; Flags
0x180011c54  call    cs:__imp_RtlImageNtHeaderEx
0x180011c5b  nop     dword ptr [rax+rax+00h]
0x180011c60  test    eax, eax
0x180011c62  js      short loc_180011C8D
0x180011c64  mov     rcx, [rbp+90h+NtHeader]
0x180011c68  test    rcx, rcx
0x180011c6b  jz      short loc_180011C8D
0x180011c6d  movzx   ecx, word ptr [rcx+4]
0x180011c71  call    cs:__imp_RtlWow64GetEquivalentMachineCHPE
0x180011c78  nop     dword ptr [rax+rax+00h]
0x180011c7d  movzx   eax, ax
0x180011c80  mov     [r12], eax
0x180011c84  mov     rcx, [rbp+90h+var_90]
0x180011c88  jmp     loc_180011D1E
0x180011c8d  mov     ecx, eax; Status
0x180011c8f  call    cs:__imp_RtlNtStatusToDosError
0x180011c96  nop     dword ptr [rax+rax+00h]
0x180011c9b  mov     edi, eax
0x180011c9d  test    eax, eax
0x180011c9f  jle     short loc_180011CAA
0x180011ca1  movzx   edi, ax
0x180011ca4  or      edi, 80070000h
0x180011caa  mov     [rbp+90h+var_84], edi
0x180011cad  mov     eax, cs:dword_1801574B8
0x180011cb3  test    eax, eax
0x180011cb5  jnz     short loc_180011CCA
0x180011cb7  cmp     cs:?gfEnableTracing@@3HA, ebx; int gfEnableTracing
0x180011cbd  jz      short loc_180011CFB
0x180011cbf  xor     ecx, ecx
0x180011cc1  call    IsWppLevelEnabled
0x180011cc6  test    al, al
0x180011cc8  jz      short loc_180011CFB
0x180011cca  mov     dword ptr [rsp+2F0h+var_2C0], edi
0x180011cce  mov     [rsp+2F0h+lpFilePart], r14
0x180011cd3  lea     rax, aModuleWsHresul; "Module:%ws %!HRESULT!"
0x180011cda  mov     [rsp+2F0h+lpBuffer], rax
0x180011cdf  xor     r9d, r9d
0x180011ce2  mov     r8d, 911h
0x180011ce8  lea     rdx, aCogetmodulearc; "CoGetModuleArchitecture"
0x180011cef  lea     rcx, aOnecoreComComb_80; "onecore\\com\\combase\\catalog\\class.c"...
0x180011cf6  call    ??$ComTraceMessageT@PEAGJ@@YAXPEBD0HW4TraceLevel@@PEBGPEAGJ@Z; ComTraceMessageT<ushort *,long>(char const *,char const *,int,TraceLevel,ushort const *,ushort *,long)
0x180011cfb  mov     rcx, [rbp+90h+var_90]
0x180011cff  jmp     short loc_180011D1E
0x180011d01  mov     edi, 800703E7h
0x180011d06  mov     [rbp+90h+var_84], edi
0x180011d09  mov     r15, [rbp+90h+var_70]
0x180011d0d  mov     r13, [rbp+90h+var_58]
0x180011d11  mov     rsi, [rbp+90h+var_68]
0x180011d15  mov     rcx, [rbp+90h+var_90]
0x180011d19  jmp     short loc_180011D1E
0x180011d1b  mov     rcx, rbx; lpBaseAddress
0x180011d1e  test    rcx, rcx
0x180011d21  jz      short loc_180011D2F
0x180011d23  call    cs:__imp_UnmapViewOfFile
0x180011d2a  nop     dword ptr [rax+rax+00h]
0x180011d2f  test    r13, r13
0x180011d32  jz      short loc_180011D43
  ... truncated ...
```
