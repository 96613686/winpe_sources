# BuildDeviceInfoList

- ea: `0x180030218`
- end: `0x180030f37`
- name: `BuildDeviceInfoList`
- size: `3359`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, service_task`

## callers

- `0x18002d6d0`
- `0x1800312ec`

## callees

- `0x180001600`
- `0x18001c740`
- `0x18001c7c0`
- `0x18001c854`
- `0x18001f918`
- `0x18002a064`
- `0x18002c8d4`
- `0x180030218`
- `0x1800319fc`
- `0x180031d80`
- `0x18003dc84`
- `0x18003fb7c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003085e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030961`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030a4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030a71`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x18003085e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030961`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030a4a`
- `api-ms-win-crt-private-l1-1-0!_o__wcsnicmp` at `0x180030a71`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180030ae5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180030b2f`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180030ae5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x180030b2f`
- `KERNEL32!MapViewOfFile` at `0x1800305f5`
- `KERNEL32!MapViewOfFile` at `0x1800305f5`
- `KERNEL32!CreateFileMappingW` at `0x1800305d0`
- `KERNEL32!CreateFileMappingW` at `0x1800305d0`
- `KERNEL32!GetFileSize` at `0x1800305a6`
- `KERNEL32!GetFileSize` at `0x1800305a6`
- `KERNEL32!GetCurrentDirectoryW` at `0x18003050e`
- `KERNEL32!GetCurrentDirectoryW` at `0x18003050e`
- `KERNEL32!IsDBCSLeadByte` at `0x180030702`
- `KERNEL32!IsDBCSLeadByte` at `0x180030702`
- `KERNEL32!UnmapViewOfFile` at `0x180030ef4`
- `KERNEL32!UnmapViewOfFile` at `0x180030ef4`
- `KERNEL32!HeapAlloc` at `0x180030305`
- `KERNEL32!HeapAlloc` at `0x18003032d`
- `KERNEL32!HeapAlloc` at `0x180030356`
- `KERNEL32!HeapAlloc` at `0x180030382`
- `KERNEL32!HeapAlloc` at `0x1800303a7`
- `KERNEL32!HeapAlloc` at `0x1800303c9`
- `KERNEL32!HeapAlloc` at `0x180030403`
- `KERNEL32!HeapAlloc` at `0x18003069a`
- `KERNEL32!HeapAlloc` at `0x1800307b6`
- `KERNEL32!HeapAlloc` at `0x1800308bb`
- `KERNEL32!HeapAlloc` at `0x1800309fa`
- `KERNEL32!HeapAlloc` at `0x180030c1b`
- `KERNEL32!HeapAlloc` at `0x180030cdd`
- `KERNEL32!HeapAlloc` at `0x180030305`
- `KERNEL32!HeapAlloc` at `0x18003032d`
- `KERNEL32!HeapAlloc` at `0x180030356`
- `KERNEL32!HeapAlloc` at `0x180030382`
- `KERNEL32!HeapAlloc` at `0x1800303a7`
- `KERNEL32!HeapAlloc` at `0x1800303c9`
- `KERNEL32!HeapAlloc` at `0x180030403`
- `KERNEL32!HeapAlloc` at `0x18003069a`
- `KERNEL32!HeapAlloc` at `0x1800307b6`
- `KERNEL32!HeapAlloc` at `0x1800308bb`
- `KERNEL32!HeapAlloc` at `0x1800309fa`
- `KERNEL32!HeapAlloc` at `0x180030c1b`
- `KERNEL32!HeapAlloc` at `0x180030cdd`
- `KERNEL32!CreateFileW` at `0x180030573`
- `KERNEL32!CreateFileW` at `0x180030573`
- `KERNEL32!CloseHandle` at `0x180030efd`
- `KERNEL32!CloseHandle` at `0x180030f0c`
- `KERNEL32!CloseHandle` at `0x180030efd`
- `KERNEL32!CloseHandle` at `0x180030f0c`
- `KERNEL32!GetLastError` at `0x180030586`
- `KERNEL32!GetLastError` at `0x180030586`
- `KERNEL32!MultiByteToWideChar` at `0x1800307f7`
- `KERNEL32!MultiByteToWideChar` at `0x1800307f7`
- `KERNEL32!GetCurrentThreadId` at `0x180030280`
- `KERNEL32!GetCurrentThreadId` at `0x1800302be`
- `KERNEL32!GetCurrentThreadId` at `0x180030280`
- `KERNEL32!GetCurrentThreadId` at `0x1800302be`
- `KERNEL32!WaitForSingleObject` at `0x180030498`
- `KERNEL32!WaitForSingleObject` at `0x180030640`
- `KERNEL32!WaitForSingleObject` at `0x180030498`
- `KERNEL32!WaitForSingleObject` at `0x180030640`
- `KERNEL32!LeaveCriticalSection` at `0x1800302e4`
- `KERNEL32!LeaveCriticalSection` at `0x1800302e4`
- `KERNEL32!EnterCriticalSection` at `0x180030270`
- `KERNEL32!EnterCriticalSection` at `0x180030270`

## pseudocode

```c
__int64 __fastcall BuildDeviceInfoList(unsigned int a1)
{
  _QWORD *v2; // r12
  size_t v3; // rdx
  unsigned int v4; // r14d
  size_t v5; // rdx
  _DWORD *v6; // r13
  unsigned int inserted; // edi
  _QWORD *v8; // rsi
  unsigned int v9; // ebx
  wchar_t *v10; // rax
  unsigned int v11; // eax
  DWORD v12; // eax
  int v13; // r8d
  HANDLE FileW; // rax
  void *v15; // rbx
  DWORD v16; // r14d
  HANDLE FileMappingW; // rax
  unsigned int v18; // ebx
  DWORD v19; // ecx
  int v20; // r15d
  __int16 v21; // cx
  unsigned int v22; // r12d
  DWORD v23; // edx
  int v24; // r14d
  void *v25; // rax
  void *v26; // rbx
  __int64 v27; // rax
  __int16 v28; // bx
  __int16 v29; // dx
  const CHAR *v30; // rbx
  WCHAR *v31; // r15
  unsigned int v32; // eax
  WCHAR *v33; // rbx
  WCHAR i; // ax
  wchar_t *v35; // rbx
  STRSAFE_LPCWSTR v36; // rdx
  unsigned int v37; // r15d
  wchar_t *v38; // rax
  const wchar_t *v39; // r14
  wchar_t v40; // ax
  __int64 v41; // rcx
  bool v42; // zf
  WCHAR v43; // ax
  const wchar_t *v44; // r14
  __int64 v45; // rcx
  unsigned int v46; // r15d
  __int64 v47; // rax
  unsigned int v48; // ebx
  wchar_t *v49; // rax
  __int64 v50; // rdx
  int v51; // eax
  WCHAR v52; // ax
  __int16 *v53; // rbx
  int v54; // eax
  __int64 v55; // rdx
  int v56; // r15d
  __int16 v57; // cx
  int v58; // eax
  __int16 v59; // cx
  int v60; // r14d
  unsigned int DeviceIDFromPermanentID; // eax
  unsigned int v62; // ecx
  unsigned int v63; // r15d
  __int64 v64; // r12
  char *v65; // rax
  char *v66; // r14
  __int64 v67; // r11
  __int64 v68; // r8
  _QWORD *v69; // rax
  __int64 v70; // r12
  STRSAFE_LPWSTR v71; // r14
  unsigned int v72; // r15d
  __int64 v73; // r12
  char *v74; // rax
  char *v75; // r14
  unsigned int j; // ebx
  int v77; // eax
  void *v78; // r14
  void *v79; // r15
  unsigned int v80; // r15d
  unsigned int k; // r14d
  HANDLE v82; // rbx
  DWORD v84; // [rsp+40h] [rbp-C0h]
  DWORD FileSize; // [rsp+44h] [rbp-BCh]
  int v86; // [rsp+50h] [rbp-B0h]
  unsigned int v88; // [rsp+5Ch] [rbp-A4h]
  _DWORD *v89; // [rsp+60h] [rbp-A0h] BYREF
  STRSAFE_LPCWSTR pszSrc; // [rsp+68h] [rbp-98h]
  void *Src; // [rsp+70h] [rbp-90h]
  STRSAFE_LPWSTR pszDest; // [rsp+78h] [rbp-88h]
  unsigned int v93; // [rsp+80h] [rbp-80h]
  size_t Size; // [rsp+88h] [rbp-78h]
  void *v95; // [rsp+90h] [rbp-70h]
  LPCVOID lpBaseAddress; // [rsp+98h] [rbp-68h]
  unsigned int v97; // [rsp+A0h] [rbp-60h]
  size_t v98; // [rsp+A4h] [rbp-5Ch] BYREF
  unsigned int v99; // [rsp+ACh] [rbp-54h]
  LPVOID lpMem; // [rsp+B0h] [rbp-50h]
  HANDLE v101; // [rsp+B8h] [rbp-48h]
  size_t cbDest; // [rsp+C0h] [rbp-40h]
  HANDLE hObject; // [rsp+C8h] [rbp-38h]
  void *v104; // [rsp+D0h] [rbp-30h]
  __int64 v105; // [rsp+D8h] [rbp-28h]
  __int64 v106; // [rsp+E0h] [rbp-20h]
  wchar_t *v107; // [rsp+E8h] [rbp-18h]
  WCHAR Buffer[280]; // [rsp+F0h] [rbp-10h] BYREF

  v98 = 0;
  v2 = 0;
  pszDest = 0;
  Src = 0;
  lpMem = 0;
  pszSrc = 0;
  EnterCriticalSection(&CriticalSection);
  dword_1800519E0 = 1594;
  dword_1800519E4 = GetCurrentThreadId();
  StringCbCopyA(::pszDest, v3, "erver\\tapimmc.c");
  v4 = dword_18005192C;
  dword_1800519F8 = 1596;
  if ( a1 )
    v4 = dword_18005191C;
  v99 = v4;
  dword_1800519FC = GetCurrentThreadId();
  StringCbCopyA(byte_1800519E8, v5, "erver\\tapimmc.c");
  LeaveCriticalSection(&CriticalSection);
  v89 = HeapAlloc(ghTapisrvHeap, 8u, 200 * v4 + 24);
  v6 = v89;
  if ( v89
    && (v2 = HeapAlloc(ghTapisrvHeap, 8u, 16 * v4)) != 0
    && (cbDest = 128, (pszDest = (STRSAFE_LPWSTR)HeapAlloc(ghTapisrvHeap, 8u, 0x80u)) != 0)
    && (v86 = 512, (Src = HeapAlloc(ghTapisrvHeap, 8u, 0x200u)) != 0)
    && (lpMem = HeapAlloc(ghTapisrvHeap, 8u, 0x200u)) != 0
    && (pszSrc = (STRSAFE_LPCWSTR)HeapAlloc(ghTapisrvHeap, 8u, 0x80u)) != 0 )
  {
    v101 = 0;
    hObject = 0;
    lpBaseAddress = 0;
    v95 = 0;
    if ( a1 )
    {
      v95 = HeapAlloc(ghTapisrvHeap, 8u, 4 * v4);
      if ( !v95 )
      {
        inserted = -2147483580;
        v8 = v2;
        goto LABEL_151;
      }
    }
    *v89 = 200 * v4 + 24;
    v9 = 0;
    v6[2] = 40 * v4 + 24;
    v6[4] = 40 * v4;
    v10 = gszLines;
    v6[5] = 24;
    inserted = 0;
    v8 = v2;
    if ( !a1 )
      v10 = gszPhones;
    v107 = v10;
    TRACELogPrint(262146, "GetDeviceInfo: getting names (addrs) for %ld %ws", v4, v10);
    v11 = 0;
    v88 = 0;
    while ( v9 < v4 )
    {
      v12 = WaitForSingleObject(ghEventService, 0);
      v13 = 0;
      if ( !v12 )
      {
        inserted = -2147483576;
LABEL_24:
        v6 = v89;
        goto LABEL_151;
      }
      if ( a1 )
        v13 = (_DWORD)v95 + 4 * v9;
      inserted = InsertDevNameAddrInfo(a1, (unsigned int)&v89, v13, v9, v88);
      if ( inserted )
      {
        inserted = 0;
        v11 = v88;
      }
      else
      {
        v11 = ++v88;
      }
      ++v9;
    }
    v6 = v89;
    v99 = v11;
    v89[3] = v11;
    if ( !GetCurrentDirectoryW(0x104u, Buffer) )
    {
LABEL_26:
      inserted = -2147483576;
      goto LABEL_151;
    }
    StringCbCatW(Buffer, 0x228u, L"\\");
    StringCbCatW(Buffer, 0x228u, gszFileName);
    FileW = CreateFileW(Buffer, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    v101 = FileW;
    v15 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      if ( GetLastError() - 2 > 1 )
        goto LABEL_26;
      v16 = 0;
      FileSize = 0;
    }
    else
    {
      FileSize = GetFileSize(FileW, 0);
      v16 = FileSize;
      if ( FileSize )
      {
        FileMappingW = CreateFileMappingW(v15, 0, 2u, 0, 0, 0);
        hObject = FileMappingW;
        if ( !FileMappingW )
          goto LABEL_26;
        lpBaseAddress = MapViewOfFile(FileMappingW, 4u, 0, 0, 0);
        if ( !lpBaseAddress )
          goto LABEL_26;
      }
      else
      {
        FileSize = 0;
      }
    }
    v18 = 512;
    v97 = 128;
    v19 = 0;
    v93 = 512;
    v84 = 0;
    while ( v19 < v16 )
    {
      if ( !WaitForSingleObject(ghEventService, 0) )
        goto LABEL_26;
      v20 = 0;
      LODWORD(Size) = 0;
      v21 = 0;
      v22 = 0;
      while ( v21 != 10 )
      {
        if ( v21 == 13 )
          goto LABEL_52;
        v23 = v84;
        if ( v84 >= v16 )
          goto LABEL_56;
        if ( v22 >= v18 )
        {
          v24 = v18 + 256;
          v25 = HeapAlloc(ghTapisrvHeap, 8u, v18 + 256);
          v26 = v25;
          if ( !v25 )
            goto LABEL_59;
          memcpy_0(v25, Src, v22);
          ServerFree(Src);
          v23 = v84;
          v86 = v24;
          v16 = FileSize;
          Src = v26;
        }
        v84 = v23 + 1;
        v27 = v22++;
        v28 = *((char *)lpBaseAddress + v23);
        LODWORD(Size) = v22;
        *((_BYTE *)Src + v27) = v28;
        if ( IsDBCSLeadByte(v28) )
        {
          v29 = *((char *)lpBaseAddress + v84++);
          *((_BYTE *)Src + v22) = v29;
          v21 = v29 + (v28 << 8);
          LODWORD(Size) = ++v22;
        }
        else
        {
          v21 = v28;
        }
        v18 = v86;
        ++v20;
      }
      FileSize = v16;
LABEL_52:
      v30 = (const CHAR *)Src;
      *((_BYTE *)Src + v22 - 1) = 0;
      if ( v84 < v16 )
      {
        if ( *((_BYTE *)lpBaseAddress + v84) == 10 || *((_BYTE *)lpBaseAddress + v84) == 13 )
          ++v84;
LABEL_56:
        v30 = (const CHAR *)Src;
      }
      if ( v93 > 2 * (unsigned __int64)(unsigned int)(v20 + 1) )
      {
        v31 = (WCHAR *)lpMem;
      }
      else
      {
        ServerFree(lpMem);
        v93 = 2 * v20 + 512;
        lpMem = HeapAlloc(ghTapisrvHeap, 8u, v93);
        v31 = (WCHAR *)lpMem;
        if ( !lpMem )
          goto LABEL_59;
      }
      v32 = MultiByteToWideChar(0, 1u, v30, v22, v31, v93 >> 1);
      if ( !v32 )
      {
        inserted = -2147483576;
        v2 = v8;
        goto LABEL_151;
      }
      v33 = v31;
      v31[v32] = 0;
      for ( i = *v31; *v33; i = *v33 )
      {
        if ( i != 32 && i != 9 )
          break;
        ++v33;
      }
      if ( *v33 != 91 )
      {
        v19 = v84;
        v2 = v8;
        if ( *pszSrc )
        {
          if ( (unsigned int)_o__wcsnicmp(v33, gszFriendlyUserName, 16) )
          {
            if ( !(unsigned int)_o__wcsnicmp(v33, gszLines, 5) && a1
              || (v51 = _o__wcsnicmp(v33, gszPhones, 6), v19 = v84, v2 = v8, !v51) && !a1 )
            {
              v52 = *v33;
              v2 = v8;
              v19 = v84;
              Size = 0;
              if ( v52 )
              {
                do
                {
                  if ( v52 == 61 )
                    break;
                  v52 = *++v33;
                }
                while ( *v33 );
                v2 = v8;
                if ( *v33 )
                {
                  v53 = (__int16 *)(v33 + 1);
LABEL_103:
                  v2 = v8;
LABEL_104:
                  while ( 1 )
                  {
                    v16 = FileSize;
                    v19 = v84;
                    if ( !*v53 )
                      break;
                    v54 = _o__wtol(v53, v50, 0);
                    v19 = v84;
                    LODWORD(Size) = v54;
                    v56 = v54;
                    if ( !v54 )
                      break;
                    v57 = *v53;
                    if ( !*v53 )
                      goto LABEL_36;
                    do
                    {
                      if ( v57 == 44 )
                        break;
                      v57 = *++v53;
                    }
                    while ( *v53 );
                    if ( !*v53 )
                      goto LABEL_36;
                    v58 = _o__wtol(++v53, v55, 0);
                    v59 = *v53;
                    v60 = v58;
                    HIDWORD(Size) = v58;
                    if ( v59 == 44 )
                      goto LABEL_164;
                    do
                    {
                      if ( !v59 )
                        break;
                      v59 = *++v53;
                    }
                    while ( *v53 != 44 );
                    if ( *v53 == 44 )
                    {
LABEL_164:
                      if ( v53[1] )
                        ++v53;
                      else
                        *v53 = 0;
                    }
                    DeviceIDFromPermanentID = GetDeviceIDFromPermanentID(Size, a1);
                    v50 = DeviceIDFromPermanentID;
                    if ( DeviceIDFromPermanentID != -1 )
                    {
                      v62 = dword_18005192C;
                      if ( a1 )
                        v62 = dword_18005191C;
                      if ( v88 < v62 )
                      {
                        while ( v6[10 * (unsigned int)v50 + 6] != v60 || v6[10 * (unsigned int)v50 + 7] != v56 )
                        {
                          if ( !(_DWORD)v50 )
                            goto LABEL_104;
                          v50 = (unsigned int)(v50 - 1);
                        }
                      }
                      v63 = v6[10 * (unsigned int)v50 + 13];
                      v105 = 5LL * (unsigned int)v50;
                      v106 = 16LL * (unsigned int)v50;
                      v104 = (void *)v8[(unsigned __int64)v106 / 8];
                      if ( (int)WstrToBufSize(pszSrc, &v98, 0) < 0 )
                        goto LABEL_139;
                      v64 = (unsigned int)v98;
                      if ( v63 + (unsigned int)v98 < v63
                        || (v65 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v63 + (unsigned int)v98), (v66 = v65) == 0) )
                      {
                        v2 = v8;
                        goto LABEL_139;
                      }
                      memcpy_0(v65, pszSrc, (unsigned int)v64);
                      if ( v63 )
                      {
                        memcpy_0(&v66[v64], v104, v63);
                        ServerFree(v104);
                      }
                      v67 = v105;
                      v68 = 0;
                      v6 = v89;
                      v69 = v8;
                      v89[2 * v105 + 13] += v64;
                      v70 = v106;
                      v8[(unsigned __int64)v106 / 8] = v66;
                      v71 = pszDest;
                      if ( !*pszDest )
                      {
                        StringCbCopyW(pszDest, (unsigned int)cbDest, pszSrc);
                        v69 = v8;
                      }
                      v72 = v6[2 * v67 + 15];
                      v104 = *(void **)((char *)v69 + v70 + 8);
                      if ( (int)WstrToBufSize(v71, (char *)&v98 + 4, v68) >= 0 )
                      {
                        v73 = HIDWORD(v98);
                        if ( v72 + HIDWORD(v98) >= v72 )
                        {
                          v74 = (char *)HeapAlloc(ghTapisrvHeap, 8u, v72 + HIDWORD(v98));
                          v75 = v74;
                          if ( v74 )
                          {
                            memcpy_0(v74, pszDest, (unsigned int)v73);
                            if ( v72 )
                            {
                              memcpy_0(&v75[v73], v104, v72);
                              ServerFree(v104);
                            }
                            v6 = v89;
                            v89[2 * v105 + 15] += v73;
                            v8[(unsigned __int64)v106 / 8 + 1] = v75;
                            goto LABEL_103;
                          }
                        }
                      }
                      goto LABEL_59;
                    }
                  }
                }
              }
            }
          }
          else
          {
            v43 = *v33;
            v19 = v84;
            if ( *v33 )
            {
              do
              {
                if ( v43 == 61 )
                  break;
                v43 = *++v33;
              }
              while ( *v33 );
              v2 = v8;
              if ( *v33 )
              {
                v44 = v33 + 1;
                v45 = -1;
                do
                  ++v45;
                while ( v44[v45] );
                v46 = cbDest;
                if ( (unsigned int)cbDest >= (unsigned __int64)(2 * v45 + 2) )
                {
                  v49 = pszDest;
                }
                else
                {
                  ServerFree(pszDest);
                  v47 = -1;
                  do
                    ++v47;
                  while ( v44[v47] );
                  v48 = 2 * v47 + 128;
                  v49 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, v48);
                  pszDest = v49;
                  if ( !v49 )
                  {
LABEL_59:
                    inserted = -2147483580;
                    v2 = v8;
                    goto LABEL_151;
                  }
                  v46 = v48;
                  cbDest = v48;
                }
                StringCbCopyW(v49, v46, v44);
                v16 = FileSize;
                v2 = v8;
LABEL_36:
                v19 = v84;
              }
            }
          }
        }
LABEL_37:
        v18 = v86;
        continue;
      }
      v35 = v33 + 1;
      *pszDest = 0;
      if ( !(unsigned int)_o__wcsnicmp(v35, gszTapiAdministrators, 18) && v35[18] == 93 )
      {
        *pszSrc = 0;
        v2 = v8;
        goto LABEL_36;
      }
      v36 = pszSrc;
      v37 = 0;
      while ( *v35 && *v35 != 93 )
      {
        if ( 2 * (unsigned __int64)(v37 + 1) >= v97 )
        {
          v97 += 128;
          v38 = (wchar_t *)HeapAlloc(ghTapisrvHeap, 8u, v97);
          v39 = v38;
          if ( !v38 )
            goto LABEL_59;
          memcpy_0(v38, pszSrc, (unsigned int)Size);
          ServerFree((LPVOID)pszSrc);
          v36 = v39;
          pszSrc = v39;
        }
        v40 = *v35++;
        v41 = v37++;
        v36[v41] = v40;
      }
      v16 = FileSize;
      v36[v37] = 0;
      v42 = *v35 == 0;
      v2 = v8;
      v18 = v86;
      v19 = v84;
      if ( v42 )
      {
        *v36 = 0;
        goto LABEL_37;
      }
    }
    TRACELogPrint(262146, "GetDeviceInfo: matching users to %ws", v107);
    for ( j = 0; j < v88; ++j )
    {
      if ( (unsigned int)InsertInfoListString(&v89, j, 24, v2[2 * j], v6[10 * j + 13], 1) )
      {
        inserted = -2147483580;
        goto LABEL_24;
      }
      v77 = InsertInfoListString(&v89, j, 32, v2[2 * j + 1], v89[10 * j + 15], 1);
      v6 = v89;
      if ( v77 )
      {
LABEL_139:
        inserted = -2147483580;
        goto LABEL_151;
      }
    }
    v6[1] = v6[2];
    if ( a1 )
    {
      gpLineDevFlags = v95;
      gpLineInfoList = v6;
      gdwNumFlags = v88;
    }
    else
    {
      gpPhoneInfoList = v6;
    }
LABEL_151:
    v80 = v99;
    for ( k = 0; k < v80; ++k )
    {
      ServerFree((LPVOID)v8[2 * k]);
      ServerFree((LPVOID)v8[2 * k + 1]);
    }
    v79 = v95;
    v78 = v101;
  }
  else
  {
    v101 = 0;
    v8 = v2;
    hObject = 0;
    inserted = -2147483580;
    lpBaseAddress = 0;
    v78 = 0;
    v95 = 0;
    v79 = 0;
    if ( v2 )
      goto LABEL_151;
  }
  ServerFree((LPVOID)pszSrc);
  ServerFree(Src);
  ServerFree(lpMem);
  ServerFree(pszDest);
  ServerFree(v2);
  if ( inserted )
  {
    ServerFree(v6);
    if ( a1 )
    {
      ServerFree(v79);
      gdwNumFlags = 0;
    }
  }
  v82 = hObject;
  if ( hObject )
  {
    UnmapViewOfFile(lpBaseAddress);
    CloseHandle(v82);
  }
  if ( v78 != (void *)-1LL )
    CloseHandle(v78);
  return inserted;
}

```

## disassembly

```asm
0x180030218  push    rbp
0x18003021a  push    rbx
0x18003021b  push    rsi
0x18003021c  push    rdi
0x18003021d  push    r12
0x18003021f  push    r13
0x180030221  push    r14
0x180030223  push    r15
0x180030225  lea     rbp, [rsp-238h]
0x18003022d  sub     rsp, 338h
0x180030234  mov     rax, cs:__security_cookie
0x18003023b  xor     rax, rsp
0x18003023e  mov     [rbp+270h+var_50], rax
0x180030245  xor     esi, esi
0x180030247  mov     [rsp+370h+var_318], ecx
0x18003024b  mov     edi, ecx
0x18003024d  mov     dword ptr [rbp+270h+var_2CC], esi
0x180030250  lea     rcx, CriticalSection; lpCriticalSection
0x180030257  mov     dword ptr [rbp+270h+var_2CC+4], esi
0x18003025a  mov     r12d, esi
0x18003025d  mov     [rsp+370h+pszDest], rsi
0x180030262  mov     [rsp+370h+Src], rsi
0x180030267  mov     [rbp+270h+lpMem], rsi
0x18003026b  mov     [rsp+370h+pszSrc], rsi
0x180030270  call    cs:__imp_EnterCriticalSection
0x180030276  mov     cs:dword_1800519E0, 63Ah
0x180030280  call    cs:__imp_GetCurrentThreadId
0x180030286  lea     r8, aPrintscanTapiS_1+10h; pszSrc
0x18003028d  mov     cs:dword_1800519E4, eax
0x180030293  lea     rcx, pszDest; pszDest
0x18003029a  call    StringCbCopyA
0x18003029f  mov     r14d, cs:dword_18005192C
0x1800302a6  test    edi, edi
0x1800302a8  mov     cs:dword_1800519F8, 63Ch
0x1800302b2  cmovnz  r14d, cs:dword_18005191C
0x1800302ba  mov     [rbp+270h+var_2C4], r14d
0x1800302be  call    cs:__imp_GetCurrentThreadId
0x1800302c4  lea     r8, aPrintscanTapiS_1+10h; pszSrc
0x1800302cb  mov     cs:dword_1800519FC, eax
0x1800302d1  lea     rcx, byte_1800519E8; pszDest
0x1800302d8  call    StringCbCopyA
0x1800302dd  lea     rcx, CriticalSection; lpCriticalSection
0x1800302e4  call    cs:__imp_LeaveCriticalSection
0x1800302ea  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800302f1  lea     r15d, [rsi+8]
0x1800302f5  imul    ebx, r14d, 0C8h
0x1800302fc  mov     edx, r15d; dwFlags
0x1800302ff  add     ebx, 18h
0x180030302  mov     r8d, ebx; dwBytes
0x180030305  call    cs:__imp_HeapAlloc
0x18003030b  mov     [rsp+370h+var_310], rax
0x180030310  mov     r13, rax
0x180030313  test    rax, rax
0x180030316  jz      loc_180030E3B
0x18003031c  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180030323  mov     r8d, r14d
0x180030326  shl     r8d, 4; dwBytes
0x18003032a  mov     edx, r15d; dwFlags
0x18003032d  call    cs:__imp_HeapAlloc
0x180030333  mov     r12, rax
0x180030336  test    rax, rax
0x180030339  jz      loc_180030E3B
0x18003033f  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180030346  lea     edx, [rsi+8]; dwFlags
0x180030349  mov     r15d, 80h
0x18003034f  mov     r8d, r15d; dwBytes
0x180030352  mov     [rbp+270h+cbDest], r15
0x180030356  call    cs:__imp_HeapAlloc
0x18003035c  mov     [rsp+370h+pszDest], rax
0x180030361  test    rax, rax
0x180030364  jz      loc_180030E3B
0x18003036a  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180030371  lea     edx, [r15-78h]; dwFlags
0x180030375  mov     esi, 200h
0x18003037a  mov     r8d, esi; dwBytes
0x18003037d  mov     [rsp+370h+var_320], rsi
0x180030382  call    cs:__imp_HeapAlloc
0x180030388  xor     r8d, r8d
0x18003038b  mov     [rsp+370h+Src], rax
0x180030390  test    rax, rax
0x180030393  jz      loc_180030E3E
0x180030399  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800303a0  lea     edx, [r15-78h]; dwFlags
0x1800303a4  mov     r8d, esi; dwBytes
0x1800303a7  call    cs:__imp_HeapAlloc
0x1800303ad  xor     esi, esi
0x1800303af  mov     [rbp+270h+lpMem], rax
0x1800303b3  test    rax, rax
0x1800303b6  jz      loc_180030E3B
0x1800303bc  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800303c3  lea     edx, [rsi+8]; dwFlags
0x1800303c6  mov     r8d, r15d; dwBytes
0x1800303c9  call    cs:__imp_HeapAlloc
0x1800303cf  mov     [rsp+370h+pszSrc], rax
0x1800303d4  test    rax, rax
0x1800303d7  jz      loc_180030E3B
0x1800303dd  mov     [rbp+270h+var_2B8], rsi
0x1800303e1  mov     [rbp+270h+hObject], rsi
0x1800303e5  mov     [rbp+270h+lpBaseAddress], rsi
0x1800303e9  mov     [rbp+270h+var_2E0], rsi
0x1800303ed  test    edi, edi
0x1800303ef  jz      short loc_180030422
0x1800303f1  mov     rcx, cs:ghTapisrvHeap; hHeap
0x1800303f8  lea     r8d, ds:0[r14*4]; dwBytes
0x180030400  lea     edx, [rsi+8]; dwFlags
0x180030403  call    cs:__imp_HeapAlloc
0x180030409  mov     [rbp+270h+var_2E0], rax
0x18003040d  test    rax, rax
0x180030410  jnz     short loc_180030422
0x180030412  mov     edi, 80000044h
0x180030417  mov     rsi, r12
0x18003041a  xor     r8d, r8d
0x18003041d  jmp     loc_180030E61
0x180030422  mov     [r13+0], ebx
0x180030426  lea     eax, [r14+r14*4]
0x18003042a  lea     ecx, ds:0[rax*8]
0x180030431  xor     r8d, r8d
0x180030434  lea     eax, [rcx+18h]
0x180030437  xor     ebx, ebx
0x180030439  mov     [r13+8], eax
0x18003043d  lea     rdx, aGetdeviceinfoG; "GetDeviceInfo: getting names (addrs) fo"...
0x180030444  mov     [r13+10h], ecx
0x180030448  lea     rax, gszLines; "Lines"
0x18003044f  lea     rcx, gszPhones; "Phones"
0x180030456  mov     dword ptr [r13+14h], 18h
0x18003045e  mov     r13d, [rsp+370h+var_318]
0x180030463  mov     edi, r8d
0x180030466  test    r13d, r13d
0x180030469  mov     r8d, r14d
0x18003046c  mov     rsi, r12
0x18003046f  cmovz   rax, rcx
0x180030473  mov     ecx, 40002h
0x180030478  mov     r9, rax
0x18003047b  mov     [rbp+270h+var_288], rax
0x18003047f  call    TRACELogPrint
0x180030484  mov     eax, ebx
0x180030486  mov     [rsp+370h+var_314], ebx
0x18003048a  cmp     ebx, r14d
0x18003048d  jnb     short loc_1800304F9
0x18003048f  mov     rcx, cs:ghEventService; hHandle
0x180030496  xor     edx, edx; dwMilliseconds
0x180030498  call    cs:__imp_WaitForSingleObject
0x18003049e  xor     r8d, r8d
0x1800304a1  test    eax, eax
0x1800304a3  jz      short loc_1800304EA
0x1800304a5  test    r13d, r13d
0x1800304a8  jz      short loc_1800304B4
0x1800304aa  mov     rcx, [rbp+270h+var_2E0]
0x1800304ae  mov     eax, ebx
0x1800304b0  lea     r8, [rcx+rax*4]
0x1800304b4  mov     eax, [rsp+370h+var_314]
0x1800304b8  lea     rdx, [rsp+370h+var_310]
0x1800304bd  mov     r9d, ebx
0x1800304c0  mov     [rsp+370h+dwCreationDisposition], eax
0x1800304c4  mov     ecx, r13d
0x1800304c7  call    InsertDevNameAddrInfo
0x1800304cc  mov     edi, eax
0x1800304ce  xor     eax, eax
0x1800304d0  test    edi, edi
0x1800304d2  jz      short loc_1800304DC
0x1800304d4  mov     edi, eax
0x1800304d6  mov     eax, [rsp+370h+var_314]
0x1800304da  jmp     short loc_1800304E6
0x1800304dc  mov     eax, [rsp+370h+var_314]
0x1800304e0  inc     eax
0x1800304e2  mov     [rsp+370h+var_314], eax
0x1800304e6  inc     ebx
0x1800304e8  jmp     short loc_18003048A
0x1800304ea  mov     edi, 80000048h
0x1800304ef  mov     r13, [rsp+370h+var_310]
0x1800304f4  jmp     loc_180030E61
0x1800304f9  mov     r13, [rsp+370h+var_310]
0x1800304fe  lea     rdx, [rbp+270h+Buffer]; lpBuffer
0x180030502  mov     ecx, 104h; nBufferLength
0x180030507  mov     [rbp+270h+var_2C4], eax
0x18003050a  mov     [r13+0Ch], eax
0x18003050e  call    cs:__imp_GetCurrentDirectoryW
0x180030514  xor     r8d, r8d
0x180030517  test    eax, eax
0x180030519  jnz     short loc_180030525
0x18003051b  mov     edi, 80000048h
0x180030520  jmp     loc_180030E61
0x180030525  mov     ebx, 228h
0x18003052a  lea     r8, pszSrc; "\\"
0x180030531  mov     edx, ebx; cbDest
0x180030533  lea     rcx, [rbp+270h+Buffer]; pszDest
0x180030537  call    StringCbCatW
0x18003053c  lea     r8, gszFileName; "..\\TAPI\\tsec.ini"
0x180030543  mov     edx, ebx; cbDest
0x180030545  lea     rcx, [rbp+270h+Buffer]; pszDest
0x180030549  call    StringCbCatW
0x18003054e  xor     r8d, r8d
0x180030551  lea     rcx, [rbp+270h+Buffer]; lpFileName
0x180030555  mov     [rsp+370h+hTemplateFile], r8; hTemplateFile
0x18003055a  xor     r9d, r9d; lpSecurityAttributes
0x18003055d  mov     [rsp+370h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x180030562  mov     edx, 80000000h; dwDesiredAccess
0x180030567  mov     [rsp+370h+dwCreationDisposition], 3; dwCreationDisposition
0x18003056f  lea     r8d, [r9+1]; dwShareMode
0x180030573  call    cs:__imp_CreateFileW
0x180030579  mov     [rbp+270h+var_2B8], rax
0x18003057d  mov     rbx, rax
0x180030580  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180030584  jnz     short loc_1800305A1
0x180030586  call    cs:__imp_GetLastError
0x18003058c  add     eax, 0FFFFFFFEh
0x18003058f  xor     r8d, r8d
0x180030592  cmp     eax, 1
0x180030595  ja      short loc_18003051B
0x180030597  mov     r14d, r8d
0x18003059a  mov     [rsp+370h+var_32C], r8d
0x18003059f  jmp     short loc_180030610
0x1800305a1  xor     edx, edx; lpFileSizeHigh
0x1800305a3  mov     rcx, rbx; hFile
0x1800305a6  call    cs:__imp_GetFileSize
0x1800305ac  xor     r8d, r8d
0x1800305af  mov     [rsp+370h+var_32C], eax
0x1800305b3  mov     r14d, eax
0x1800305b6  test    eax, eax
0x1800305b8  jz      short loc_18003060C
0x1800305ba  mov     qword ptr [rsp+370h+dwFlagsAndAttributes], r8; lpName
0x1800305bf  xor     r9d, r9d; dwMaximumSizeHigh
0x1800305c2  mov     [rsp+370h+dwCreationDisposition], r8d; dwMaximumSizeLow
0x1800305c7  xor     edx, edx; lpFileMappingAttributes
0x1800305c9  mov     rcx, rbx; hFile
0x1800305cc  lea     r8d, [r9+2]; flProtect
0x1800305d0  call    cs:__imp_CreateFileMappingW
0x1800305d6  xor     r8d, r8d; dwFileOffsetHigh
0x1800305d9  mov     [rbp+270h+hObject], rax
0x1800305dd  mov     rcx, rax; hFileMappingObject
0x1800305e0  test    rax, rax
0x1800305e3  jz      loc_18003051B
0x1800305e9  xor     r9d, r9d; dwFileOffsetLow
0x1800305ec  mov     qword ptr [rsp+370h+dwCreationDisposition], r8; dwNumberOfBytesToMap
0x1800305f1  lea     edx, [r8+4]; dwDesiredAccess
0x1800305f5  call    cs:__imp_MapViewOfFile
0x1800305fb  xor     r8d, r8d
0x1800305fe  mov     [rbp+270h+lpBaseAddress], rax
0x180030602  test    rax, rax
0x180030605  jnz     short loc_180030610
0x180030607  jmp     loc_18003051B
0x18003060c  mov     [rsp+370h+var_32C], eax
0x180030610  mov     ebx, 200h
0x180030615  mov     [rbp+270h+var_2D0], r15d
0x180030619  mov     ecx, r8d
0x18003061c  mov     [rbp+270h+var_2F0], ebx
0x18003061f  mov     [rsp+370h+var_330], ecx
0x180030623  jmp     short loc_18003062E
0x180030625  mov     ecx, [rsp+370h+var_330]
0x180030629  mov     rbx, [rsp+370h+var_320]
0x18003062e  cmp     ecx, r14d
0x180030631  jnb     loc_180030D5C
0x180030637  mov     rcx, cs:ghEventService; hHandle
0x18003063e  xor     edx, edx; dwMilliseconds
0x180030640  call    cs:__imp_WaitForSingleObject
0x180030646  xor     r8d, r8d
0x180030649  test    eax, eax
0x18003064b  jz      loc_18003051B
0x180030651  mov     r15d, r8d
0x180030654  mov     dword ptr [rbp+270h+Size], r8d
0x180030658  mov     ecx, r8d
0x18003065b  mov     r12d, r8d
0x18003065e  cmp     cx, 0Ah
0x180030662  jz      loc_18003074D
0x180030668  cmp     cx, 0Dh
0x18003066c  jz      loc_180030752
0x180030672  mov     edx, [rsp+370h+var_330]
0x180030676  cmp     edx, r14d
0x180030679  jnb     loc_18003077F
0x18003067f  cmp     r12d, ebx
0x180030682  jb      short loc_1800306DC
0x180030684  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003068b  lea     r14d, [rbx+100h]
0x180030692  mov     r8d, r14d; dwBytes
0x180030695  mov     edx, 8; dwFlags
0x18003069a  call    cs:__imp_HeapAlloc
0x1800306a0  xor     r8d, r8d
0x1800306a3  mov     rbx, rax
0x1800306a6  test    rax, rax
0x1800306a9  jz      loc_1800307CB
0x1800306af  mov     rdx, [rsp+370h+Src]; Src
0x1800306b4  mov     rcx, rax; void *
0x1800306b7  mov     r8d, r12d; Size
0x1800306ba  call    memcpy_0
0x1800306bf  mov     rcx, [rsp+370h+Src]; lpMem
0x1800306c4  call    ServerFree
0x1800306c9  mov     edx, [rsp+370h+var_330]
0x1800306cd  mov     dword ptr [rsp+370h+var_320], r14d
0x1800306d2  mov     r14d, [rsp+370h+var_32C]
0x1800306d7  mov     [rsp+370h+Src], rbx
0x1800306dc  mov     rcx, [rbp+270h+lpBaseAddress]
0x1800306e0  mov     r8, [rsp+370h+Src]
0x1800306e5  mov     eax, edx
0x1800306e7  inc     edx
0x1800306e9  mov     [rsp+370h+var_330], edx
0x1800306ed  movsx   ecx, byte ptr [rax+rcx]; TestChar
0x1800306f1  mov     eax, r12d
0x1800306f4  inc     r12d
0x1800306f7  movzx   ebx, cx
0x1800306fa  mov     dword ptr [rbp+270h+Size], r12d
  ... truncated ...
```
