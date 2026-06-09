# SHGetFileDescriptionW

- ea: `0x180003ec0`
- end: `0x1800044b3`
- name: `SHGetFileDescriptionW`
- size: `1523`
- prototype: `__int64 __usercall@<rax>(LPCWSTR pszPath@<rcx>, unsigned __int16 *@<rdx>, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180003400`
- `0x180003ec0`
- `0x1800044bc`
- `0x180004e64`
- `0x180012550`
- `0x18001bbfc`
- `0x180020e18`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003f43`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003f67`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003f43`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180003f67`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fff`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180003fff`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000407b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040a5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000407b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800040a5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003f4e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180003f4e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000414d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800041b7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800041ec`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180004225`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800042a9`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180004363`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000414d`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800041b7`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800041ec`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180004225`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x1800042a9`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x180004363`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000411e`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoExW` at `0x18000411e`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180003fec`
- `api-ms-win-core-version-l1-1-0!GetFileVersionInfoSizeExW` at `0x180003fec`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180004435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x180004435`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180003fd1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1800042cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180003fd1`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1800042cc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180003fc4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800042bf`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180003fc4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800042bf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRStrIW` at `0x180004238`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrRStrIW` at `0x180004238`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004089`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000424d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000446b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180004089`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000424d`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18000446b`
- `MPR!WNetGetResourceInformationW` at `0x18000431b`
- `MPR!WNetGetResourceInformationW` at `0x18000431b`
- `SHELL32!SHBindToParent` at `0x1800043d1`
- `SHELL32!SHBindToParent` at `0x1800043d1`
- `SHELL32!SHParseDisplayName` at `0x1800043a7`
- `SHELL32!SHParseDisplayName` at `0x1800043a7`
- `SHELL32!__imp_ILFree` at `0x180004411`
- `SHELL32!__imp_ILFree` at `0x180004411`

## pseudocode

```c
__int64 __fastcall SHGetFileDescriptionW(WCHAR *pszPath, ITEMIDLIST *a2, const WCHAR *a3, _WORD *a4, unsigned int *a5)
{
  int v5; // ebx
  UINT v11; // esi
  DWORD FileAttributesW; // eax
  char v13; // r14
  WCHAR *v14; // rax
  void *v15; // rsi
  __int64 v16; // rcx
  WCHAR *v17; // r8
  __int64 v18; // rdx
  struct IUnknown *v19; // rcx
  DWORD FileVersionInfoSize; // eax
  DWORD v21; // ebx
  HLOCAL v22; // rax
  __int64 v23; // r14
  const WCHAR *v24; // rbx
  unsigned int v25; // ecx
  unsigned int v26; // eax
  __int64 v27; // rdx
  LPCWSTR v28; // rax
  _WORD *v29; // rcx
  const wchar_t *v30; // r8
  __int64 v31; // rcx
  WCHAR *v32; // rax
  __int64 v33; // rdx
  WCHAR *v34; // rcx
  PWSTR v35; // rdi
  DWORD ResourceInformationW; // eax
  int v37; // eax
  __int64 v38; // r8
  const unsigned __int16 *FileNameW; // rax
  LPVOID lpData; // [rsp+20h] [rbp-E0h]
  LPCWSTR lpString; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cbBuffer[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR lpSystem; // [rsp+50h] [rbp-B0h] BYREF
  LPITEMIDLIST ppidl; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID lpBuffer; // [rsp+60h] [rbp-A0h] BYREF
  struct _NETRESOURCEW NetResource; // [rsp+68h] [rbp-98h] BYREF
  unsigned int puLen; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwHandle; // [rsp+9Ch] [rbp-64h] BYREF
  WCHAR SubBlock[64]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v51[264]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR wstrFilename[264]; // [rsp+330h] [rbp+230h] BYREF
  _BYTE Buffer[512]; // [rsp+540h] [rbp+440h] BYREF

  v5 = 0;
  puLen = 0;
  lpString = 0;
  lpBuffer = 0;
  if ( !pszPath )
    return 0;
  v11 = SetErrorMode(1u);
  FileAttributesW = GetFileAttributesW(pszPath);
  v13 = FileAttributesW;
  if ( FileAttributesW != -1
    || (PathIsUNCServerW(pszPath) || PathIsUNCServerShareW(pszPath))
    && ((*(_QWORD *)&NetResource.dwScope = 2,
         NetResource.lpRemoteName = pszPath,
         cbBuffer[0] = 512,
         lpSystem = 0,
         *(_OWORD *)&NetResource.dwDisplayType = 0,
         *(_OWORD *)&NetResource.lpComment = 0,
         (ResourceInformationW = WNetGetResourceInformationW(&NetResource, Buffer, cbBuffer, &lpSystem)) == 0)
     || ResourceInformationW == 234) )
  {
    v5 = 1;
  }
  SetErrorMode(v11);
  if ( !v5 )
    return 0;
  v14 = wstrFilename;
  v15 = 0;
  v16 = 2147483646;
  v17 = pszPath;
  v18 = 260;
  do
  {
    if ( !v16 )
      break;
    if ( !*v17 )
      break;
    *v14++ = *v17++;
    --v16;
    --v18;
  }
  while ( v18 );
  v19 = (struct IUnknown *)(v14 - 1);
  if ( v18 )
    v19 = (struct IUnknown *)v14;
  LOWORD(v19->lpVtbl) = 0;
  if ( (v13 & 0x10) != 0
    || PathIsUNCServerW(pszPath)
    || PathIsUNCServerShareW(pszPath)
    || (dwHandle = 0,
        FileVersionInfoSize = GetFileVersionInfoSizeExW(1u, wstrFilename, &dwHandle),
        (v21 = FileVersionInfoSize) == 0)
    || (v22 = LocalAlloc(0x40u, FileVersionInfoSize), (v15 = v22) == 0)
    || !GetFileVersionInfoExW(3u, wstrFilename, dwHandle, v21, v22) )
  {
    a2 = 0;
  }
  else if ( !a2
         || (v37 = StringCchCopyW(SubBlock, 0x3Cu, &a2->mkid.cb), a2 = 0, v37 < 0)
         || !VerQueryValueW(v15, SubBlock, (LPVOID *)&lpString, &puLen) )
  {
    if ( !VerQueryValueW(v15, L"\\VarFileInfo\\Translation", &lpBuffer, &puLen)
      || puLen == (_DWORD)a2
      || (LODWORD(lpData) = *((unsigned __int16 *)lpBuffer + 1),
          (int)StringCchPrintfW(
                 SubBlock,
                 0x3Cu,
                 L"\\StringFileInfo\\%04X%04X\\FileDescription",
                 *(unsigned __int16 *)lpBuffer,
                 lpData) < 0)
      || !VerQueryValueW(v15, SubBlock, (LPVOID *)&lpString, &puLen) )
    {
      v23 = 2147483646;
      v30 = L"\\StringFileInfo\\040904B0\\FileDescription";
      v31 = 2147483646;
      v32 = SubBlock;
      v33 = 60;
      do
      {
        if ( !v31 )
          break;
        if ( !*v30 )
          break;
        *v32++ = *v30++;
        --v31;
        --v33;
      }
      while ( v33 );
      v34 = v32 - 1;
      if ( v33 )
        v34 = v32;
      *v34 = (unsigned __int16)a2;
      if ( (!v33 || !VerQueryValueW(v15, SubBlock, (LPVOID *)&lpString, &puLen))
        && ((int)StringCchCopyW(SubBlock, 0x3Cu, L"\\StringFileInfo\\040904E4\\FileDescription") < 0
         || !VerQueryValueW(v15, SubBlock, (LPVOID *)&lpString, &puLen))
        && (int)StringCchCopyW(SubBlock, 0x3Cu, L"\\StringFileInfo\\04090000\\FileDescription") >= 0 )
      {
        VerQueryValueW(v15, SubBlock, (LPVOID *)&lpString, &puLen);
      }
      goto LABEL_19;
    }
  }
  v23 = 2147483646;
LABEL_19:
  v24 = lpString;
  if ( !lpString || *lpString == (_WORD)a2 )
  {
    hMem = a2;
    if ( (int)SHCreateSkipBindCtx(v19, (struct IBindCtx **)&hMem) >= 0 )
    {
      ppidl = a2;
      if ( SHParseDisplayName(pszPath, (IBindCtx *)hMem, &ppidl, 0, (SFGAOF *)&a2->mkid.cb) >= 0 )
      {
        *(_QWORD *)cbBuffer = a2;
        lpSystem = &a2->mkid.cb;
        if ( SHBindToParent(
               ppidl,
               &GUID_000214e6_0000_0000_c000_000000000046,
               (void **)cbBuffer,
               (LPCITEMIDLIST *)&lpSystem) >= 0 )
        {
          if ( (int)DisplayNameOfW(*(_QWORD *)cbBuffer, lpSystem, v38, v51) >= 0 )
            lpString = v51;
          (*(void (__fastcall **)(_QWORD))(**(_QWORD **)cbBuffer + 16LL))(*(_QWORD *)cbBuffer);
        }
        ILFree(ppidl);
      }
      (*(void (__fastcall **)(HLOCAL))(*(_QWORD *)hMem + 16LL))(hMem);
    }
    v24 = lpString;
  }
  if ( !v24 || *v24 == (_WORD)a2 )
  {
    FileNameW = PathFindFileNameW(pszPath);
    if ( (int)StringCchCopyW(v51, 0x104u, FileNameW) < 0 )
    {
      v24 = lpString;
    }
    else
    {
      v24 = v51;
      lpString = v51;
    }
  }
  if ( v24 && *v24 != (_WORD)a2 )
  {
    hMem = a2;
    if ( !(unsigned int)_AllocValueString((HKEY)v19, (const unsigned __int16 *)v18, v17, (unsigned __int16 **)&hMem) )
      a3 = (const WCHAR *)hMem;
    if ( a3 )
    {
      while ( *a3 != (_WORD)a2 )
      {
        v35 = StrRStrIW(v24, 0, a3);
        if ( v35 && v35[lstrlenW(a3)] == (_WORD)a2 )
        {
          do
            *v35-- = (unsigned __int16)a2;
          while ( v35 >= v24 && *v35 == 32 );
          break;
        }
        a3 += lstrlenW(a3) + 1;
      }
      LocalFree(hMem);
    }
    v24 = lpString;
  }
  v25 = lstrlenW(v24) + 1;
  puLen = v25;
  if ( a4 )
  {
    v26 = *a5;
    if ( *a5 >= v25 )
      v26 = v25;
    v27 = v26;
    *a5 = v26;
    if ( v26 - 1 > 0x7FFFFFFE )
    {
      if ( v26 )
        *a4 = (_WORD)a2;
    }
    else
    {
      v28 = lpString;
      do
      {
        if ( !v23 )
          break;
        if ( !*v28 )
          break;
        *a4++ = *v28++;
        --v23;
        --v27;
      }
      while ( v27 );
      v29 = a4 - 1;
      if ( v27 )
        v29 = a4;
      *v29 = (_WORD)a2;
    }
  }
  else
  {
    *a5 = v25;
  }
  LocalFree(v15);
  return 1;
}

```

## disassembly

```asm
0x180003ec0  push    rbp
0x180003ec2  push    rbx
0x180003ec3  push    rsi
0x180003ec4  push    rdi
0x180003ec5  push    r12
0x180003ec7  push    r13
0x180003ec9  push    r14
0x180003ecb  push    r15
0x180003ecd  lea     rbp, [rsp-658h]
0x180003ed5  sub     rsp, 758h
0x180003edc  mov     rax, cs:__security_cookie
0x180003ee3  xor     rax, rsp
0x180003ee6  mov     [rbp+690h+var_50], rax
0x180003eed  mov     rax, [rbp+690h+arg_20]
0x180003ef4  xor     ebx, ebx
0x180003ef6  mov     [rsp+790h+var_760], rax
0x180003efb  mov     r13, r9
0x180003efe  mov     [rbp+690h+puLen], ebx
0x180003f01  mov     r15, r8
0x180003f04  mov     [rsp+790h+lpString], rbx
0x180003f09  mov     r12, rdx
0x180003f0c  mov     [rsp+790h+lpBuffer], rbx
0x180003f11  mov     rdi, rcx
0x180003f14  test    rcx, rcx
0x180003f17  jnz     short loc_180003F3E
0x180003f19  xor     eax, eax
0x180003f1b  mov     rcx, [rbp+690h+var_50]
0x180003f22  xor     rcx, rsp; StackCookie
0x180003f25  call    __security_check_cookie
0x180003f2a  add     rsp, 758h
0x180003f31  pop     r15
0x180003f33  pop     r14
0x180003f35  pop     r13
0x180003f37  pop     r12
0x180003f39  pop     rdi
0x180003f3a  pop     rsi
0x180003f3b  pop     rbx
0x180003f3c  pop     rbp
0x180003f3d  retn
0x180003f3e  mov     ecx, 1; uMode
0x180003f43  call    cs:__imp_SetErrorMode
0x180003f49  mov     rcx, rdi; lpFileName
0x180003f4c  mov     esi, eax
0x180003f4e  call    cs:__imp_GetFileAttributesW
0x180003f54  mov     r14d, eax
0x180003f57  cmp     eax, 0FFFFFFFFh
0x180003f5a  jz      loc_1800042BC
0x180003f60  mov     ebx, 1
0x180003f65  mov     ecx, esi; uMode
0x180003f67  call    cs:__imp_SetErrorMode
0x180003f6d  test    ebx, ebx
0x180003f6f  jz      short loc_180003F19
0x180003f71  xor     ebx, ebx
0x180003f73  lea     rax, [rbp+690h+wstrFilename]
0x180003f7a  mov     esi, ebx
0x180003f7c  mov     ecx, 7FFFFFFEh
0x180003f81  mov     r8, rdi
0x180003f84  mov     edx, 104h
0x180003f89  test    rcx, rcx
0x180003f8c  jz      short loc_180003FAD
0x180003f8e  movzx   r9d, word ptr [r8]
0x180003f92  test    r9w, r9w
0x180003f96  jz      short loc_180003FAD
0x180003f98  mov     [rax], r9w
0x180003f9c  add     r8, 2
0x180003fa0  add     rax, 2
0x180003fa4  dec     rcx
0x180003fa7  sub     rdx, 1
0x180003fab  jnz     short loc_180003F89
0x180003fad  test    rdx, rdx
0x180003fb0  lea     rcx, [rax-2]
0x180003fb4  cmovnz  rcx, rax
0x180003fb8  mov     [rcx], bx
0x180003fbb  test    r14b, 10h
0x180003fbf  jnz     short loc_180004011
0x180003fc1  mov     rcx, rdi; pszPath
0x180003fc4  call    cs:__imp_PathIsUNCServerW
0x180003fca  test    eax, eax
0x180003fcc  jnz     short loc_180004011
0x180003fce  mov     rcx, rdi; pszPath
0x180003fd1  call    cs:__imp_PathIsUNCServerShareW
0x180003fd7  test    eax, eax
0x180003fd9  jnz     short loc_180004011
0x180003fdb  lea     r8, [rbp+690h+dwHandle]; lpdwHandle
0x180003fdf  mov     [rbp+690h+dwHandle], ebx
0x180003fe2  lea     rdx, [rbp+690h+wstrFilename]; lpwstrFilename
0x180003fe9  lea     ecx, [rax+1]; dwFlags
0x180003fec  call    cs:__imp_GetFileVersionInfoSizeExW
0x180003ff2  mov     ebx, eax
0x180003ff4  test    eax, eax
0x180003ff6  jz      short loc_180004011
0x180003ff8  mov     edx, ebx; uBytes
0x180003ffa  mov     ecx, 40h ; '@'; uFlags
0x180003fff  call    cs:__imp_LocalAlloc
0x180004005  mov     rsi, rax
0x180004008  test    rax, rax
0x18000400b  jnz     loc_180004106
0x180004011  xor     r12d, r12d
0x180004014  mov     r14d, 7FFFFFFEh
0x18000401a  mov     rbx, [rsp+790h+lpString]
0x18000401f  test    rbx, rbx
0x180004022  jz      loc_180004376
0x180004028  cmp     [rbx], r12w
0x18000402c  jz      loc_180004376
0x180004032  test    rbx, rbx
0x180004035  jz      loc_180004432
0x18000403b  cmp     [rbx], r12w
0x18000403f  jz      loc_180004432
0x180004045  test    rbx, rbx
0x180004048  jz      short loc_180004086
0x18000404a  cmp     [rbx], r12w
0x18000404e  jz      short loc_180004086
0x180004050  lea     r9, [rsp+790h+hMem]; unsigned __int16 **
0x180004055  mov     [rsp+790h+hMem], r12
0x18000405a  call    ?_AllocValueString@@YAJPEAUHKEY__@@PEBG1PEAPEAG@Z; _AllocValueString(HKEY__ *,ushort const *,ushort const *,ushort * *)
0x18000405f  test    eax, eax
0x180004061  cmovz   r15, [rsp+790h+hMem]
0x180004067  test    r15, r15
0x18000406a  jz      short loc_180004081
0x18000406c  cmp     [r15], r12w
0x180004070  jnz     loc_180004230
0x180004076  mov     rcx, [rsp+790h+hMem]; hMem
0x18000407b  call    cs:__imp_LocalFree
0x180004081  mov     rbx, [rsp+790h+lpString]
0x180004086  mov     rcx, rbx; lpString
0x180004089  call    cs:__imp_lstrlenW
0x18000408f  mov     r8, [rsp+790h+var_760]
0x180004094  lea     ecx, [rax+1]
0x180004097  mov     [rbp+690h+puLen], ecx
0x18000409a  test    r13, r13
0x18000409d  jnz     short loc_1800040B5
0x18000409f  mov     [r8], ecx
0x1800040a2  mov     rcx, rsi; hMem
0x1800040a5  call    cs:__imp_LocalFree
0x1800040ab  mov     eax, 1
0x1800040b0  jmp     loc_180003F1B
0x1800040b5  mov     eax, [r8]
0x1800040b8  cmp     eax, ecx
0x1800040ba  cmovnb  eax, ecx
0x1800040bd  mov     edx, eax
0x1800040bf  dec     eax
0x1800040c1  mov     [r8], edx
0x1800040c4  cmp     eax, r14d
0x1800040c7  ja      loc_1800044A0
0x1800040cd  mov     rax, [rsp+790h+lpString]
0x1800040d2  test    r14, r14
0x1800040d5  jz      short loc_1800040F5
0x1800040d7  movzx   ecx, word ptr [rax]
0x1800040da  test    cx, cx
0x1800040dd  jz      short loc_1800040F5
0x1800040df  mov     [r13+0], cx
0x1800040e4  add     rax, 2
0x1800040e8  add     r13, 2
0x1800040ec  dec     r14
0x1800040ef  sub     rdx, 1
0x1800040f3  jnz     short loc_1800040D2
0x1800040f5  test    rdx, rdx
0x1800040f8  lea     rcx, [r13-2]
0x1800040fc  cmovnz  rcx, r13
0x180004100  mov     [rcx], r12w
0x180004104  jmp     short loc_1800040A2
0x180004106  mov     r8d, [rbp+690h+dwHandle]; dwHandle
0x18000410a  lea     rdx, [rbp+690h+wstrFilename]; lpwstrFilename
0x180004111  mov     r9d, ebx; dwLen
0x180004114  mov     [rsp+790h+lpData], rsi; lpData
0x180004119  mov     ecx, 3; dwFlags
0x18000411e  call    cs:__imp_GetFileVersionInfoExW
0x180004124  test    eax, eax
0x180004126  jz      loc_180004011
0x18000412c  mov     ebx, 3Ch ; '<'
0x180004131  test    r12, r12
0x180004134  jnz     loc_180004339
0x18000413a  lea     r9, [rbp+690h+puLen]; puLen
0x18000413e  mov     rcx, rsi; pBlock
0x180004141  lea     r8, [rsp+790h+lpBuffer]; lplpBuffer
0x180004146  lea     rdx, SubBlock; "\\VarFileInfo\\Translation"
0x18000414d  call    cs:__imp_VerQueryValueW
0x180004153  test    eax, eax
0x180004155  jnz     loc_180004263
0x18000415b  mov     r14d, 7FFFFFFEh
0x180004161  lea     r8, aStringfileinfo_0; "\\StringFileInfo\\040904B0\\FileDescrip"...
0x180004168  mov     ecx, r14d
0x18000416b  lea     rax, [rbp+690h+SubBlock]
0x18000416f  mov     rdx, rbx
0x180004172  test    rcx, rcx
0x180004175  jz      short loc_180004196
0x180004177  movzx   r9d, word ptr [r8]
0x18000417b  test    r9w, r9w
0x18000417f  jz      short loc_180004196
0x180004181  mov     [rax], r9w
0x180004185  add     r8, 2
0x180004189  add     rax, 2
0x18000418d  dec     rcx
0x180004190  sub     rdx, 1
0x180004194  jnz     short loc_180004172
0x180004196  test    rdx, rdx
0x180004199  lea     rcx, [rax-2]
0x18000419d  cmovnz  rcx, rax
0x1800041a1  mov     [rcx], r12w
0x1800041a5  jz      short loc_1800041C5
0x1800041a7  lea     r9, [rbp+690h+puLen]; puLen
0x1800041ab  mov     rcx, rsi; pBlock
0x1800041ae  lea     r8, [rsp+790h+lpString]; lplpBuffer
0x1800041b3  lea     rdx, [rbp+690h+SubBlock]; lpSubBlock
0x1800041b7  call    cs:__imp_VerQueryValueW
0x1800041bd  test    eax, eax
0x1800041bf  jnz     loc_18000401A
0x1800041c5  lea     r8, aStringfileinfo_5; "\\StringFileInfo\\040904E4\\FileDescrip"...
0x1800041cc  mov     rdx, rbx; unsigned __int64
0x1800041cf  lea     rcx, [rbp+690h+SubBlock]; unsigned __int16 *
0x1800041d3  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800041d8  test    eax, eax
0x1800041da  js      short loc_1800041FA
0x1800041dc  lea     r9, [rbp+690h+puLen]; puLen
0x1800041e0  mov     rcx, rsi; pBlock
0x1800041e3  lea     r8, [rsp+790h+lpString]; lplpBuffer
0x1800041e8  lea     rdx, [rbp+690h+SubBlock]; lpSubBlock
0x1800041ec  call    cs:__imp_VerQueryValueW
0x1800041f2  test    eax, eax
0x1800041f4  jnz     loc_18000401A
0x1800041fa  lea     r8, aStringfileinfo_3; "\\StringFileInfo\\04090000\\FileDescrip"...
0x180004201  mov     rdx, rbx; unsigned __int64
0x180004204  lea     rcx, [rbp+690h+SubBlock]; unsigned __int16 *
0x180004208  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000420d  test    eax, eax
0x18000420f  js      loc_18000401A
0x180004215  lea     r9, [rbp+690h+puLen]; puLen
0x180004219  mov     rcx, rsi; pBlock
0x18000421c  lea     r8, [rsp+790h+lpString]; lplpBuffer
0x180004221  lea     rdx, [rbp+690h+SubBlock]; lpSubBlock
0x180004225  call    cs:__imp_VerQueryValueW
0x18000422b  jmp     loc_18000401A
0x180004230  mov     r8, r15; pszSrch
0x180004233  xor     edx, edx; pszLast
0x180004235  mov     rcx, rbx; pszSource
0x180004238  call    cs:__imp_StrRStrIW
0x18000423e  mov     rdi, rax
0x180004241  test    rax, rax
0x180004244  jnz     loc_180004468
0x18000424a  mov     rcx, r15; lpString
0x18000424d  call    cs:__imp_lstrlenW
0x180004253  movsxd  rcx, eax
0x180004256  lea     r15, [r15+rcx*2]
0x18000425a  add     r15, 2
0x18000425e  jmp     loc_18000406C
0x180004263  cmp     [rbp+690h+puLen], r12d
0x180004267  jz      loc_18000415B
0x18000426d  mov     rax, [rsp+790h+lpBuffer]
0x180004272  lea     r8, aStringfileinfo; "\\StringFileInfo\\%04X%04X\\FileDescrip"...
0x180004279  mov     rdx, rbx; unsigned __int64
0x18000427c  movzx   ecx, word ptr [rax+2]
0x180004280  movzx   r9d, word ptr [rax]
0x180004284  mov     dword ptr [rsp+790h+lpData], ecx
0x180004288  lea     rcx, [rbp+690h+SubBlock]; unsigned __int16 *
0x18000428c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180004291  test    eax, eax
0x180004293  js      loc_18000415B
0x180004299  lea     r9, [rbp+690h+puLen]; puLen
0x18000429d  mov     rcx, rsi; pBlock
0x1800042a0  lea     r8, [rsp+790h+lpString]; lplpBuffer
0x1800042a5  lea     rdx, [rbp+690h+SubBlock]; lpSubBlock
0x1800042a9  call    cs:__imp_VerQueryValueW
0x1800042af  test    eax, eax
0x1800042b1  jnz     loc_180004014
0x1800042b7  jmp     loc_18000415B
0x1800042bc  mov     rcx, rdi; pszPath
0x1800042bf  call    cs:__imp_PathIsUNCServerW
0x1800042c5  test    eax, eax
0x1800042c7  jnz     short loc_1800042DA
0x1800042c9  mov     rcx, rdi; pszPath
0x1800042cc  call    cs:__imp_PathIsUNCServerShareW
0x1800042d2  test    eax, eax
0x1800042d4  jz      loc_180003F65
0x1800042da  xorps   xmm0, xmm0
0x1800042dd  mov     qword ptr [rsp+790h+NetResource.dwScope], 2
0x1800042e6  xorps   xmm1, xmm1
0x1800042e9  mov     [rbp+690h+NetResource.lpRemoteName], rdi
0x1800042ed  lea     r9, [rsp+790h+lpSystem]; lplpSystem
0x1800042f2  mov     [rsp+790h+cbBuffer], 200h
0x1800042fa  lea     r8, [rsp+790h+cbBuffer]; lpcbBuffer
0x1800042ff  mov     [rsp+790h+lpSystem], rbx
0x180004304  lea     rdx, [rbp+690h+Buffer]; lpBuffer
0x18000430b  lea     rcx, [rsp+790h+NetResource]; lpNetResource
0x180004310  movdqu  xmmword ptr [rsp+790h+NetResource.dwDisplayType], xmm0
0x180004316  movdqu  xmmword ptr [rbp+690h+NetResource.lpComment], xmm1
0x18000431b  call    cs:__imp_WNetGetResourceInformationW
0x180004321  test    eax, eax
0x180004323  jz      loc_180003F60
0x180004329  cmp     eax, 0EAh
0x18000432e  jnz     loc_180003F65
0x180004334  jmp     loc_180003F60
0x180004339  mov     r8, r12; unsigned __int16 *
0x18000433c  lea     rcx, [rbp+690h+SubBlock]; unsigned __int16 *
0x180004340  mov     rdx, rbx; unsigned __int64
0x180004343  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180004348  xor     r12d, r12d
0x18000434b  test    eax, eax
0x18000434d  js      loc_18000413A
0x180004353  lea     r9, [rbp+690h+puLen]; puLen
0x180004357  mov     rcx, rsi; pBlock
  ... truncated ...
```
