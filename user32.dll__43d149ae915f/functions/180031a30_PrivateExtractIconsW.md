# PrivateExtractIconsW

- ea: `0x180031a30`
- end: `0x180031dc8`
- name: `PrivateExtractIconsW`
- size: `920`
- prototype: `UINT __stdcall(LPCWSTR szFileName, int nIconIndex, int cxIcon, int cyIcon, HICON *phicon, UINT *piconid, UINT nIcons, UINT flags)`
- caller_count: `2`
- callee_count: `7`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180031580`
- `0x18007ee60`

## callees

- `0x18002cd24`
- `0x180031a30`
- `0x180031dd0`
- `0x18004ed44`
- `0x18007ebb4`
- `0x180096dc5`
- `0x180096e00`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031bd5`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180031bd5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031b63`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180031b63`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceNamesExW` at `0x180031bcc`
- `api-ms-win-core-libraryloader-l1-2-0!EnumResourceNamesExW` at `0x180031bcc`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c79`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180031c79`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180031b0e`
- `api-ms-win-core-processenvironment-l1-1-0!ExpandEnvironmentStringsW` at `0x180031b0e`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180031b4b`
- `api-ms-win-core-processenvironment-l1-1-0!SearchPathW` at `0x180031b4b`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180031c23`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180031c23`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031cfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031d35`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031cfa`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180031d35`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180031bff`
- `api-ms-win-core-file-l1-1-0!SetFileTime` at `0x180031bff`

## pseudocode

```c
UINT __stdcall PrivateExtractIconsW(
        LPCWSTR szFileName,
        int nIconIndex,
        int cxIcon,
        int cyIcon,
        HICON *phicon,
        UINT *piconid,
        UINT nIcons,
        UINT flags)
{
  UINT v11; // ebx
  int v12; // eax
  HMODULE Library; // rdi
  UINT v14; // eax
  unsigned int IconFromICO; // eax
  UINT i; // eax
  HANDLE FileW; // rax
  HANDLE v19; // rdi
  DWORD NumberOfBytesRead; // [rsp+44h] [rbp-BCh] BYREF
  FILETIME LastAccessTime; // [rsp+48h] [rbp-B8h] BYREF
  _DWORD lParam[4]; // [rsp+50h] [rbp-B0h] BYREF
  HICON *v24; // [rsp+60h] [rbp-A0h]
  UINT *v25; // [rsp+68h] [rbp-98h]
  UINT v26; // [rsp+70h] [rbp-90h]
  UINT v27; // [rsp+74h] [rbp-8Ch]
  __int64 v28; // [rsp+78h] [rbp-88h]
  __int16 v29; // [rsp+80h] [rbp-80h] BYREF
  __int16 v30; // [rsp+82h] [rbp-7Eh]
  __int16 v31; // [rsp+88h] [rbp-78h]
  __int16 v32; // [rsp+8Ah] [rbp-76h]
  WCHAR Buffer[264]; // [rsp+90h] [rbp-70h] BYREF
  WCHAR Dst[264]; // [rsp+2A0h] [rbp+1A0h] BYREF

  v11 = 0;
  memset_0(Buffer, 0, 0x208u);
  memset_0(Dst, 0, 0x208u);
  NumberOfBytesRead = 0;
  if ( __PAIR128__((unsigned __int64)piconid, (unsigned __int64)phicon) != 0 )
  {
    for ( i = 0; i < nIcons; ++i )
    {
      if ( phicon )
        phicon[i] = 0;
      if ( piconid )
        piconid[i] = -1;
    }
  }
  v12 = HasExtension((unsigned __int16 *)szFileName);
  if ( v12 != 1802398766 && v12 != 1684890414 && v12 != 1718186030 && v12 != 1836016430 && v12 != 1952539182 )
  {
    ExpandEnvironmentStringsW(szFileName, Dst, 0x104u);
    Dst[259] = 0;
    if ( Dst[0] == 92 && Dst[1] == 92 )
    {
      StringCchCopyW(Buffer, 0x104u, Dst);
    }
    else if ( !SearchPathW(0, Dst, 0, 0x104u, Buffer, 0) )
    {
      return -(phicon != 0);
    }
    Library = LoadLibraryExW(Buffer, 0, 0x22u);
    if ( Library )
    {
      lParam[2] = cyIcon;
      lParam[3] = 0;
      v28 = 0;
      lParam[0] = nIconIndex;
      lParam[1] = cxIcon;
      v24 = phicon;
      v25 = piconid;
      v26 = nIcons;
      v27 = flags;
      EnumResourceNamesExW(Library, (LPCWSTR)0xE, PrivateEnumProc, (LONG_PTR)lParam, 0xBu, 0);
      FreeLibrary(Library);
      v11 = HIDWORD(v28);
      if ( !phicon )
        return v28;
      return v11;
    }
    FileW = CreateFileW(Buffer, 0x80000100, 3u, 0, 3u, 0x10000080u, 0);
    v19 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      v19 = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0x10000080u, 0);
      if ( v19 == (HANDLE)-1LL )
        return -(phicon != 0);
    }
    else
    {
      LastAccessTime = (FILETIME)-1LL;
      SetFileTime(FileW, 0, &LastAccessTime, 0);
    }
    ReadFile(v19, &v29, 0xCu, &NumberOfBytesRead, 0);
    if ( NumberOfBytesRead != 12 )
    {
LABEL_21:
      CloseHandle(v19);
      return v11;
    }
    if ( !v29 )
    {
      if ( (unsigned __int16)(v30 - 1) > 1u )
        goto LABEL_20;
      v14 = flags;
      goto LABEL_18;
    }
    if ( v29 == 18770 )
    {
      v14 = flags;
      if ( (flags & 0x10000) == 0 && v30 == 17990 && v31 == 17217 && v32 == 20047 )
      {
LABEL_18:
        IconFromICO = ExtractIconFromICO(Buffer, nIconIndex, cxIcon, cyIcon, phicon, v14);
LABEL_19:
        v11 = IconFromICO;
      }
    }
    else if ( v29 == 19778 && (flags & 0x10000) == 0 )
    {
      IconFromICO = ExtractIconFromBMP(Buffer, nIconIndex, cxIcon, cyIcon, phicon, flags);
      goto LABEL_19;
    }
LABEL_20:
    if ( v19 == (HANDLE)-1LL )
      return v11;
    goto LABEL_21;
  }
  return v11;
}

```

## disassembly

```asm
0x180031a30  push    rbp
0x180031a32  push    rbx
0x180031a33  push    rsi
0x180031a34  push    rdi
0x180031a35  push    r12
0x180031a37  push    r13
0x180031a39  push    r14
0x180031a3b  push    r15
0x180031a3d  lea     rbp, [rsp-3C8h]
0x180031a45  sub     rsp, 4C8h
0x180031a4c  mov     rax, cs:__security_cookie
0x180031a53  xor     rax, rsp
0x180031a56  mov     [rbp+400h+var_50], rax
0x180031a5d  mov     rsi, [rbp+400h+phicon]
0x180031a64  mov     r13d, r8d
0x180031a67  mov     r14, [rbp+400h+piconid]
0x180031a6e  mov     r12d, edx
0x180031a71  mov     rdi, rcx
0x180031a74  mov     [rsp+500h+var_4C0], r9d
0x180031a79  mov     r15d, 208h
0x180031a7f  lea     rcx, [rbp+400h+Buffer]; void *
0x180031a83  mov     r8d, r15d; Size
0x180031a86  xor     edx, edx; Val
0x180031a88  xor     ebx, ebx
0x180031a8a  call    memset_0
0x180031a8f  mov     r8d, r15d; Size
0x180031a92  lea     rcx, [rbp+400h+Dst]; void *
0x180031a99  xor     edx, edx; Val
0x180031a9b  call    memset_0
0x180031aa0  mov     r15d, [rbp+400h+nIcons]
0x180031aa7  xor     edx, edx
0x180031aa9  mov     [rsp+500h+NumberOfBytesRead], edx
0x180031aad  test    rsi, rsi
0x180031ab0  jnz     loc_180031CA4
0x180031ab6  test    r14, r14
0x180031ab9  jnz     loc_180031CA4
0x180031abf  mov     rcx, rdi; unsigned __int16 *
0x180031ac2  call    ?HasExtension@@YAKPEAG@Z; HasExtension(ushort *)
0x180031ac7  cmp     eax, 6B6E6C2Eh
0x180031acc  jz      loc_180031C7F
0x180031ad2  cmp     eax, 646D632Eh
0x180031ad7  jz      loc_180031C7F
0x180031add  cmp     eax, 6669702Eh
0x180031ae2  jz      loc_180031C7F
0x180031ae8  cmp     eax, 6D6F632Eh
0x180031aed  jz      loc_180031C7F
0x180031af3  cmp     eax, 7461622Eh
0x180031af8  jz      loc_180031C7F
0x180031afe  mov     r8d, 104h; nSize
0x180031b04  lea     rdx, [rbp+400h+Dst]; lpDst
0x180031b0b  mov     rcx, rdi; lpSrc
0x180031b0e  call    cs:__imp_ExpandEnvironmentStringsW
0x180031b14  xor     edi, edi
0x180031b16  cmp     [rbp+400h+Dst], 5Ch ; '\'
0x180031b1e  mov     [rbp+400h+var_5A], di
0x180031b25  jz      loc_180031D52
0x180031b2b  lea     rax, [rbp+400h+Buffer]
0x180031b2f  mov     [rsp+500h+lpFilePart], rdi; lpFilePart
0x180031b34  mov     r9d, 104h; nBufferLength
0x180031b3a  mov     [rsp+500h+lpBuffer], rax; lpBuffer
0x180031b3f  xor     r8d, r8d; lpExtension
0x180031b42  lea     rdx, [rbp+400h+Dst]; lpFileName
0x180031b49  xor     ecx, ecx; lpPath
0x180031b4b  call    cs:__imp_SearchPathW
0x180031b51  test    eax, eax
0x180031b53  jz      loc_180031D48
0x180031b59  xor     edx, edx; hFile
0x180031b5b  lea     rcx, [rbp+400h+Buffer]; lpLibFileName
0x180031b5f  lea     r8d, [rdx+22h]; dwFlags
0x180031b63  call    cs:__imp_LoadLibraryExW
0x180031b69  xor     ecx, ecx
0x180031b6b  mov     rdi, rax
0x180031b6e  test    rax, rax
0x180031b71  jz      loc_180031CD3
0x180031b77  mov     r9d, [rsp+500h+var_4C0]
0x180031b7c  lea     edx, [rcx+0Eh]; lpType
0x180031b7f  mov     eax, [rbp+400h+flags]
0x180031b85  lea     r8, ?PrivateEnumProc@@YAHPEAUHINSTANCE__@@PEBG1_J@Z; lpEnumFunc
0x180031b8c  mov     word ptr [rsp+500h+lpFilePart], cx; LangId
0x180031b91  mov     [rsp+500h+var_4A8], r9d
0x180031b96  lea     r9, [rsp+500h+lParam]; lParam
0x180031b9b  mov     [rsp+500h+var_4A4], ecx
0x180031b9f  mov     [rsp+500h+var_488], rcx
0x180031ba4  mov     rcx, rdi; hModule
0x180031ba7  mov     dword ptr [rsp+500h+lParam], r12d
0x180031bac  mov     dword ptr [rsp+500h+lParam+4], r13d
0x180031bb1  mov     [rsp+500h+var_4A0], rsi
0x180031bb6  mov     [rsp+500h+var_498], r14
0x180031bbb  mov     [rsp+500h+var_490], r15d
0x180031bc0  mov     [rsp+500h+var_48C], eax
0x180031bc4  mov     dword ptr [rsp+500h+lpBuffer], 0Bh; dwFlags
0x180031bcc  call    cs:__imp_EnumResourceNamesExW
0x180031bd2  mov     rcx, rdi; hLibModule
0x180031bd5  call    cs:__imp_FreeLibrary
0x180031bdb  mov     ebx, dword ptr [rsp+500h+var_488+4]
0x180031bdf  test    rsi, rsi
0x180031be2  cmovz   ebx, dword ptr [rsp+500h+var_488]
0x180031be7  jmp     loc_180031C7F
0x180031bec  lea     r8, [rsp+500h+LastAccessTime]; lpLastAccessTime
0x180031bf1  mov     qword ptr [rsp+500h+LastAccessTime.dwLowDateTime], 0FFFFFFFFFFFFFFFFh
0x180031bfa  xor     edx, edx; lpCreationTime
0x180031bfc  mov     rcx, rax; hFile
0x180031bff  call    cs:__imp_SetFileTime
0x180031c05  xor     r14d, r14d
0x180031c08  lea     r15d, [r14+1]
0x180031c0c  lea     r9, [rsp+500h+NumberOfBytesRead]; lpNumberOfBytesRead
0x180031c11  mov     [rsp+500h+lpBuffer], r14; lpOverlapped
0x180031c16  mov     r8d, 0Ch; nNumberOfBytesToRead
0x180031c1c  lea     rdx, [rbp+400h+var_480]; lpBuffer
0x180031c20  mov     rcx, rdi; hFile
0x180031c23  call    cs:__imp_ReadFile
0x180031c29  cmp     [rsp+500h+NumberOfBytesRead], 0Ch
0x180031c2e  jnz     short loc_180031C76
0x180031c30  movzx   eax, [rbp+400h+var_480]
0x180031c34  test    ax, ax
0x180031c37  jnz     loc_180031D7A
0x180031c3d  movzx   eax, [rbp+400h+var_47E]
0x180031c41  sub     ax, r15w
0x180031c45  cmp     ax, r15w
0x180031c49  ja      short loc_180031C70
0x180031c4b  mov     eax, [rbp+400h+flags]
0x180031c51  mov     r9d, [rsp+500h+var_4C0]; int
0x180031c56  lea     rcx, [rbp+400h+Buffer]; SourceString
0x180031c5a  mov     dword ptr [rsp+500h+lpFilePart], eax; unsigned int
0x180031c5e  mov     r8d, r13d; int
0x180031c61  mov     edx, r12d; int
0x180031c64  mov     [rsp+500h+lpBuffer], rsi; HICON *
0x180031c69  call    ?ExtractIconFromICO@@YAIPEAGHHHPEAPEAUHICON__@@I@Z; ExtractIconFromICO(ushort *,int,int,int,HICON__ * *,uint)
0x180031c6e  mov     ebx, eax
0x180031c70  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180031c74  jz      short loc_180031C7F
0x180031c76  mov     rcx, rdi; hObject
0x180031c79  call    cs:__imp_CloseHandle
0x180031c7f  mov     eax, ebx
0x180031c81  mov     rcx, [rbp+400h+var_50]
0x180031c88  xor     rcx, rsp; StackCookie
0x180031c8b  call    __security_check_cookie
0x180031c90  add     rsp, 4C8h
0x180031c97  pop     r15
0x180031c99  pop     r14
0x180031c9b  pop     r13
0x180031c9d  pop     r12
0x180031c9f  pop     rdi
0x180031ca0  pop     rsi
0x180031ca1  pop     rbx
0x180031ca2  pop     rbp
0x180031ca3  retn
0x180031ca4  mov     eax, edx
0x180031ca6  test    r15d, r15d
0x180031ca9  jz      loc_180031ABF
0x180031caf  mov     ecx, eax
0x180031cb1  test    rsi, rsi
0x180031cb4  jz      short loc_180031CBA
0x180031cb6  mov     [rsi+rcx*8], rdx
0x180031cba  test    r14, r14
0x180031cbd  jz      short loc_180031CC7
0x180031cbf  mov     dword ptr [r14+rcx*4], 0FFFFFFFFh
0x180031cc7  inc     eax
0x180031cc9  cmp     eax, r15d
0x180031ccc  jb      short loc_180031CAF
0x180031cce  jmp     loc_180031ABF
0x180031cd3  mov     [rsp+500h+hTemplateFile], rcx; hTemplateFile
0x180031cd8  mov     r15d, 3
0x180031cde  mov     r8d, r15d; dwShareMode
0x180031ce1  mov     dword ptr [rsp+500h+lpFilePart], 10000080h; dwFlagsAndAttributes
0x180031ce9  xor     r9d, r9d; lpSecurityAttributes
0x180031cec  mov     dword ptr [rsp+500h+lpBuffer], r15d; dwCreationDisposition
0x180031cf1  mov     edx, 80000100h; dwDesiredAccess
0x180031cf6  lea     rcx, [rbp+400h+Buffer]; lpFileName
0x180031cfa  call    cs:__imp_CreateFileW
0x180031d00  xor     r9d, r9d; lpSecurityAttributes
0x180031d03  mov     rdi, rax
0x180031d06  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031d0a  jnz     loc_180031BEC
0x180031d10  xor     r14d, r14d
0x180031d13  lea     rcx, [rbp+400h+Buffer]; lpFileName
0x180031d17  mov     [rsp+500h+hTemplateFile], r14; hTemplateFile
0x180031d1c  mov     edx, 80000000h; dwDesiredAccess
0x180031d21  mov     dword ptr [rsp+500h+lpFilePart], 10000080h; dwFlagsAndAttributes
0x180031d29  mov     dword ptr [rsp+500h+lpBuffer], r15d; dwCreationDisposition
0x180031d2e  lea     r15d, [rax+2]
0x180031d32  mov     r8d, r15d; dwShareMode
0x180031d35  call    cs:__imp_CreateFileW
0x180031d3b  mov     rdi, rax
0x180031d3e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180031d42  jnz     loc_180031C0C
0x180031d48  neg     rsi
0x180031d4b  sbb     ebx, ebx
0x180031d4d  jmp     loc_180031C7F
0x180031d52  cmp     [rbp+400h+var_25E], 5Ch ; '\'
0x180031d5a  jnz     loc_180031B2B
0x180031d60  lea     r8, [rbp+400h+Dst]; unsigned __int16 *
0x180031d67  mov     edx, 104h; unsigned __int64
0x180031d6c  lea     rcx, [rbp+400h+Buffer]; unsigned __int16 *
0x180031d70  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031d75  jmp     loc_180031B59
0x180031d7a  mov     ecx, 4952h
0x180031d7f  cmp     ax, cx
0x180031d82  jz      loc_18009AD94
0x180031d88  mov     ecx, 4D42h
0x180031d8d  cmp     ax, cx
0x180031d90  jnz     loc_180031C70
0x180031d96  mov     eax, [rbp+400h+flags]
0x180031d9c  bt      eax, 10h
0x180031da0  jb      loc_180031C70
0x180031da6  mov     r9d, [rsp+500h+var_4C0]; int
0x180031dab  lea     rcx, [rbp+400h+Buffer]; SourceString
0x180031daf  mov     dword ptr [rsp+500h+lpFilePart], eax; unsigned int
0x180031db3  mov     r8d, r13d; int
0x180031db6  mov     edx, r12d; int
0x180031db9  mov     [rsp+500h+lpBuffer], rsi; HICON *
0x180031dbe  call    ?ExtractIconFromBMP@@YAIPEAGHHHPEAPEAUHICON__@@I@Z; ExtractIconFromBMP(ushort *,int,int,int,HICON__ * *,uint)
0x180031dc3  jmp     loc_180031C6E
0x18009ad94  mov     eax, [rbp+400h+flags]
0x18009ad9a  bt      eax, 10h
0x18009ad9e  jb      loc_180031C70
0x18009ada4  mov     ecx, 4646h
0x18009ada9  cmp     [rbp+400h+var_47E], cx
0x18009adad  jnz     loc_180031C70
0x18009adb3  mov     ecx, 4341h
0x18009adb8  cmp     [rbp+400h+var_478], cx
0x18009adbc  jnz     loc_180031C70
0x18009adc2  mov     ecx, 4E4Fh
0x18009adc7  cmp     [rbp+400h+var_476], cx
0x18009adcb  jnz     loc_180031C70
0x18009add1  jmp     loc_180031C51
```
