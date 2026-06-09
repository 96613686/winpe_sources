# PfXpAddBootImageAndImportsToList

- ea: `0x180093660`
- end: `0x180093a83`
- name: `PfXpAddBootImageAndImportsToList`
- size: `1059`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, service_task`

## callers

- `0x180093a8c`

## callees

- `0x18001a400`
- `0x18003bafc`
- `0x180048c10`
- `0x180049d6c`
- `0x18004b9fc`
- `0x18004bd64`
- `0x180052b7c`
- `0x180058308`
- `0x180093660`
- `0x180094cac`
- `0x1800b645a`
- `0x1800b64c0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180093949`
- `msvcrt!_wcsicmp` at `0x18009395d`
- `msvcrt!_wcsicmp` at `0x180093981`
- `msvcrt!_wcsicmp` at `0x180093949`
- `msvcrt!_wcsicmp` at `0x18009395d`
- `msvcrt!_wcsicmp` at `0x180093981`
- `ntdll!RtlImageRvaToVa` at `0x18009390e`
- `ntdll!RtlImageRvaToVa` at `0x18009390e`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800938d4`
- `ntdll!RtlImageDirectoryEntryToData` at `0x1800938d4`
- `ntdll!RtlImageNtHeader` at `0x18009387d`
- `ntdll!RtlImageNtHeader` at `0x18009387d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009391c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009391c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800937e3`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800937e3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800939cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093a58`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800939cb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093a3c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180093a58`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093723`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180093723`

## string_xrefs

- `0x180093953`: `hal.dll`

## pseudocode

```c
__int64 __fastcall PfXpAddBootImageAndImportsToList(__int64 a1, const wchar_t *a2, int a3)
{
  __int64 v3; // r13
  const wchar_t **v4; // r14
  unsigned int v5; // esi
  const wchar_t *v6; // rax
  const wchar_t *v7; // rdi
  __int64 v8; // r15
  const wchar_t **v9; // rax
  unsigned int v10; // edi
  unsigned int v11; // r12d
  const wchar_t *v12; // r12
  __int64 v13; // rdi
  unsigned int v14; // r11d
  __int64 v15; // r8
  PVOID v16; // r12
  _DWORD *v17; // r13
  struct _IMAGE_NT_HEADERS64 *v18; // r15
  ULONG v19; // r8d
  wchar_t *v20; // rdi
  unsigned int i; // r12d
  char v22; // al
  unsigned int j; // ebx
  int v25; // [rsp+34h] [rbp-4E4h] BYREF
  int v26; // [rsp+38h] [rbp-4E0h]
  unsigned int v27; // [rsp+3Ch] [rbp-4DCh]
  int v28; // [rsp+40h] [rbp-4D8h]
  PVOID v29; // [rsp+48h] [rbp-4D0h]
  __int64 v30; // [rsp+50h] [rbp-4C8h] BYREF
  ULONG Size; // [rsp+58h] [rbp-4C0h] BYREF
  PIMAGE_NT_HEADERS NtHeader; // [rsp+60h] [rbp-4B8h]
  __int64 v33; // [rsp+68h] [rbp-4B0h]
  __int64 v34; // [rsp+70h] [rbp-4A8h]
  PVOID BaseAddress[2]; // [rsp+78h] [rbp-4A0h] BYREF
  const wchar_t **v36; // [rsp+88h] [rbp-490h]
  __int64 v37; // [rsp+90h] [rbp-488h]
  LPCCH lpMultiByteStr; // [rsp+A0h] [rbp-478h]
  const wchar_t **v39; // [rsp+A8h] [rbp-470h]
  wchar_t FileName[264]; // [rsp+B0h] [rbp-468h] BYREF
  wchar_t pszDest[264]; // [rsp+2C0h] [rbp-258h] BYREF

  v3 = a1;
  v34 = a1;
  v37 = a1;
  LODWORD(v30) = 0;
  v25 = 0;
  Size = 0;
  v4 = 0;
  v5 = 0;
  if ( !a3 )
    goto LABEL_47;
  v6 = &a2[a3 - 1];
  if ( *v6 == 92 )
    goto LABEL_47;
  do
  {
    v7 = v6;
    if ( v6 <= a2 )
      break;
    --v6;
  }
  while ( *v6 != 92 );
  v8 = v7 - a2;
  v33 = v8;
  HIDWORD(v30) = v8;
  if ( (unsigned int)v8 >= 0x104 )
  {
LABEL_47:
    v10 = 24;
  }
  else
  {
    StringCbCopyNW(pszDest, 0x20Au, a2, 2LL * (unsigned int)v8);
    v9 = (const wchar_t **)HeapAlloc(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, 0x800u);
    v4 = v9;
    v36 = v9;
    if ( v9 )
    {
      v39 = v9;
      v27 = 256;
      v11 = 0;
      v28 = 0;
      memset_0(v9 + 1, 0, 0x7F8u);
      *v4 = v7;
      v5 = 1;
      v26 = 1;
      while ( v11 < v5 )
      {
        *(_OWORD *)BaseAddress = 0;
        v12 = v4[v11];
        v13 = -1;
        do
          ++v13;
        while ( v12[v13] );
        if ( (unsigned int)(v13 + v8) < 0x104 )
        {
          StringCbCopyW(FileName, 0x20Au, pszDest);
          StringCbCatW(FileName, v14, v12);
          if ( GetFileAttributesW(FileName) != -1 || !(unsigned int)PfXpLocateBootServiceFile(v12, (__int64)&v30) )
          {
            v15 = -1;
            do
              ++v15;
            while ( FileName[v15] );
            PfXpAddToPathList(v3);
            if ( !(unsigned int)PfSvGetViewOfFileEx(FileName, 0, BaseAddress, &v25) )
            {
              v16 = BaseAddress[1];
              v29 = BaseAddress[1];
              if ( !(unsigned int)PfXpVerifyImageImportTable(BaseAddress[1]) )
              {
                NtHeader = RtlImageNtHeader(v16);
                if ( NtHeader )
                {
                  v17 = RtlImageDirectoryEntryToData(v16, 0, 1u, &Size);
                  if ( v17 )
                  {
                    v18 = NtHeader;
                    do
                    {
                      v19 = v17[3];
                      if ( !v19 || !v17[4] )
                        break;
                      v20 = 0;
                      lpMultiByteStr = (LPCCH)RtlImageRvaToVa(v18, v16, v19, 0);
                      GetLastError();
                      if ( lpMultiByteStr )
                        v20 = (wchar_t *)PfSvAnsiToUnicode(lpMultiByteStr);
                      if ( v20 && _wcsicmp(v20, L"ntoskrnl.exe") && _wcsicmp(v20, L"hal.dll") )
                      {
                        for ( i = 0; i < v5; ++i )
                        {
                          if ( !_wcsicmp(v20, v39[i]) )
                          {
                            v16 = v29;
                            goto LABEL_36;
                          }
                        }
                        v16 = v29;
                        if ( v5 >= v27 )
                          goto LABEL_36;
                        v4[v5++] = v20;
                        v26 = v5;
                        v22 = 1;
                      }
                      else
                      {
LABEL_36:
                        v22 = 0;
                      }
                      if ( !v22 && v20 )
                        HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v20);
                      if ( v5 >= v27 )
                        break;
                      v17 += 5;
                    }
                    while ( v17 );
                    LODWORD(v8) = v33;
                  }
                }
              }
            }
          }
        }
        if ( BaseAddress[1] )
          PfSvUnmapViewOfFile(BaseAddress);
        v11 = ++v28;
        v3 = v34;
      }
      v10 = 0;
    }
    else
    {
      v10 = 8;
    }
  }
  if ( v4 )
  {
    for ( j = 1; j < v5; ++j )
      HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, (LPVOID)v4[j]);
    HeapFree(*(HANDLE *)(*(_QWORD *)&PfSvcGlobals + 88LL), 0, v4);
  }
  return v10;
}

```

## disassembly

```asm
0x180093660  push    rbx
0x180093662  push    rsi
0x180093663  push    rdi
0x180093664  push    r12
0x180093666  push    r13
0x180093668  push    r14
0x18009366a  push    r15
0x18009366c  sub     rsp, 4E0h
0x180093673  mov     rax, cs:__security_cookie
0x18009367a  xor     rax, rsp
0x18009367d  mov     [rsp+518h+var_48], rax
0x180093685  mov     r13, rcx
0x180093688  mov     [rsp+518h+var_4A8], rcx
0x18009368d  mov     [rsp+518h+var_488], rcx
0x180093695  xor     ebx, ebx
0x180093697  mov     dword ptr [rsp+518h+var_4C8], ebx
0x18009369b  mov     [rsp+518h+var_4E4], ebx
0x18009369f  mov     [rsp+518h+Size], ebx
0x1800936a3  mov     r14d, ebx
0x1800936a6  mov     esi, ebx
0x1800936a8  test    r8d, r8d
0x1800936ab  jz      loc_180093A15
0x1800936b1  lea     eax, [r8-1]
0x1800936b5  lea     rax, [rdx+rax*2]
0x1800936b9  cmp     word ptr [rax], 5Ch ; '\'
0x1800936bd  jz      loc_180093A15
0x1800936c3  mov     rdi, rax
0x1800936c6  cmp     rax, rdx
0x1800936c9  jbe     short loc_1800936D5
0x1800936cb  sub     rax, 2
0x1800936cf  cmp     word ptr [rax], 5Ch ; '\'
0x1800936d3  jnz     short loc_1800936C3
0x1800936d5  mov     r15, rdi
0x1800936d8  sub     r15, rdx
0x1800936db  sar     r15, 1
0x1800936de  mov     [rsp+518h+var_4B0], r15
0x1800936e3  mov     dword ptr [rsp+518h+var_4C8+4], r15d
0x1800936e8  cmp     r15d, 104h
0x1800936ef  jnb     loc_180093A15
0x1800936f5  mov     r9d, r15d
0x1800936f8  add     r9, r9; cbToCopy
0x1800936fb  mov     r8, rdx; pszSrc
0x1800936fe  mov     edx, 20Ah; cbDest
0x180093703  lea     rcx, [rsp+518h+pszDest]; pszDest
0x18009370b  call    StringCbCopyNW
0x180093710  xor     edx, edx; dwFlags
0x180093712  mov     r8d, 800h; dwBytes
0x180093718  mov     rcx, cs:PfSvcGlobals
0x18009371f  mov     rcx, [rcx+58h]; hHeap
0x180093723  call    cs:__imp_HeapAlloc
0x180093729  mov     r14, rax
0x18009372c  mov     [rsp+518h+var_490], rax
0x180093734  test    rax, rax
0x180093737  jnz     short loc_180093741
0x180093739  lea     edi, [rax+8]
0x18009373c  jmp     loc_180093A1A
0x180093741  mov     [rsp+518h+var_470], r14
0x180093749  mov     [rsp+518h+var_4DC], 100h
0x180093751  mov     r12d, ebx
0x180093754  mov     [rsp+518h+var_4D8], ebx
0x180093758  lea     rcx, [rax+8]; void *
0x18009375c  xor     edx, edx; Val
0x18009375e  mov     r8d, 7F8h; Size
0x180093764  call    memset_0
0x180093769  mov     [r14], rdi
0x18009376c  mov     esi, 1
0x180093771  mov     [rsp+518h+var_4E0], esi
0x180093775  cmp     r12d, esi
0x180093778  jnb     loc_180093A11
0x18009377e  xorps   xmm0, xmm0
0x180093781  movups  xmmword ptr [rsp+518h+BaseAddress], xmm0
0x180093786  mov     eax, r12d
0x180093789  mov     r12, [r14+rax*8]
0x18009378d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180093791  inc     rdi
0x180093794  cmp     [r12+rdi*2], bx
0x180093799  jnz     short loc_180093791
0x18009379b  lea     eax, [rdi+r15]
0x18009379f  cmp     eax, 104h
0x1800937a4  jnb     loc_1800939E6
0x1800937aa  lea     r8, [rsp+518h+pszDest]; pszSrc
0x1800937b2  mov     r11d, 20Ah
0x1800937b8  mov     edx, r11d; cbDest
0x1800937bb  lea     rcx, [rsp+518h+FileName]; pszDest
0x1800937c3  call    StringCbCopyW
0x1800937c8  mov     r8, r12; pszSrc
0x1800937cb  mov     edx, r11d; cbDest
0x1800937ce  lea     rcx, [rsp+518h+FileName]; pszDest
0x1800937d6  call    StringCbCatW
0x1800937db  lea     rcx, [rsp+518h+FileName]; lpFileName
0x1800937e3  call    cs:__imp_GetFileAttributesW
0x1800937e9  cmp     eax, 0FFFFFFFFh
0x1800937ec  jnz     short loc_180093812
0x1800937ee  lea     rax, [rsp+518h+var_4C8]
0x1800937f3  mov     [rsp+518h+var_4F8], rax; __int64
0x1800937f8  lea     r8, [rsp+518h+FileName]
0x180093800  mov     edx, edi
0x180093802  mov     rcx, r12; pszSrc
0x180093805  call    PfXpLocateBootServiceFile
0x18009380a  test    eax, eax
0x18009380c  jnz     loc_1800939E6
0x180093812  lea     rax, [rsp+518h+FileName]
0x18009381a  or      r8, 0FFFFFFFFFFFFFFFFh
0x18009381e  inc     r8
0x180093821  cmp     [rax+r8*2], bx
0x180093826  jnz     short loc_18009381E
0x180093828  lea     rdx, [rsp+518h+FileName]
0x180093830  mov     rcx, r13
0x180093833  call    PfXpAddToPathList
0x180093838  lea     r9, [rsp+518h+var_4E4]
0x18009383d  lea     r8, [rsp+518h+BaseAddress]
0x180093842  xor     edx, edx
0x180093844  lea     rcx, [rsp+518h+FileName]
0x18009384c  call    PfSvGetViewOfFileEx
0x180093851  test    eax, eax
0x180093853  jnz     loc_1800939E6
0x180093859  mov     r12, [rsp+518h+BaseAddress+8]
0x180093861  mov     [rsp+518h+var_4D0], r12
0x180093866  mov     edx, [rsp+518h+var_4E4]
0x18009386a  mov     rcx, r12; BaseAddress
0x18009386d  call    PfXpVerifyImageImportTable
0x180093872  test    eax, eax
0x180093874  jnz     loc_1800939E6
0x18009387a  mov     rcx, r12; BaseAddress
0x18009387d  call    cs:__imp_RtlImageNtHeader
0x180093883  mov     [rsp+518h+NtHeader], rax
0x180093888  jmp     short loc_1800938BB
0x18009388a  xor     eax, eax
0x18009388c  mov     [rsp+518h+NtHeader], rax
0x180093891  xor     ebx, ebx
0x180093893  mov     esi, [rsp+518h+var_4E0]
0x180093897  mov     r14, [rsp+518h+var_490]
0x18009389f  mov     r15d, dword ptr [rsp+518h+var_4C8+4]
0x1800938a4  mov     [rsp+518h+var_4B0], r15
0x1800938a9  mov     r12, [rsp+518h+var_4D0]
0x1800938ae  mov     rcx, [rsp+518h+var_488]
0x1800938b6  mov     [rsp+518h+var_4A8], rcx
0x1800938bb  test    rax, rax
0x1800938be  jz      loc_1800939E6
0x1800938c4  mov     r8d, 1; Directory
0x1800938ca  lea     r9, [rsp+518h+Size]; Size
0x1800938cf  xor     edx, edx; MappedAsImage
0x1800938d1  mov     rcx, r12; BaseAddress
0x1800938d4  call    cs:__imp_RtlImageDirectoryEntryToData
0x1800938da  mov     r13, rax
0x1800938dd  test    rax, rax
0x1800938e0  jz      loc_1800939E6
0x1800938e6  mov     r15, [rsp+518h+NtHeader]
0x1800938eb  mov     r8d, [r13+0Ch]; Rva
0x1800938ef  test    r8d, r8d
0x1800938f2  jz      loc_1800939E1
0x1800938f8  cmp     [r13+10h], ebx
0x1800938fc  jz      loc_1800939E1
0x180093902  mov     rdi, rbx
0x180093905  xor     r9d, r9d; SectionHeader
0x180093908  mov     rdx, r12; BaseAddress
0x18009390b  mov     rcx, r15; NtHeader
0x18009390e  call    cs:__imp_RtlImageRvaToVa
0x180093914  mov     [rsp+518h+lpMultiByteStr], rax
0x18009391c  call    cs:__imp_GetLastError
0x180093922  mov     rax, [rsp+518h+lpMultiByteStr]
0x18009392a  test    rax, rax
0x18009392d  jz      short loc_18009393A
0x18009392f  mov     rcx, rax; lpMultiByteStr
0x180093932  call    PfSvAnsiToUnicode
0x180093937  mov     rdi, rax
0x18009393a  test    rdi, rdi
0x18009393d  jz      short loc_1800939B0
0x18009393f  lea     rdx, aNtoskrnlExe; "ntoskrnl.exe"
0x180093946  mov     rcx, rdi; String1
0x180093949  call    cs:__imp__wcsicmp
0x18009394f  test    eax, eax
0x180093951  jz      short loc_1800939B0
0x180093953  lea     rdx, aHalDll; "hal.dll"
0x18009395a  mov     rcx, rdi; String1
0x18009395d  call    cs:__imp__wcsicmp
0x180093963  test    eax, eax
0x180093965  jz      short loc_1800939B0
0x180093967  mov     r12d, ebx
0x18009396a  cmp     r12d, esi
0x18009396d  jnb     short loc_180093990
0x18009396f  mov     edx, r12d
0x180093972  mov     rax, [rsp+518h+var_470]
0x18009397a  mov     rdx, [rax+rdx*8]; String2
0x18009397e  mov     rcx, rdi; String1
0x180093981  call    cs:__imp__wcsicmp
0x180093987  test    eax, eax
0x180093989  jz      short loc_1800939AB
0x18009398b  inc     r12d
0x18009398e  jmp     short loc_18009396A
0x180093990  mov     r12, [rsp+518h+var_4D0]
0x180093995  cmp     esi, [rsp+518h+var_4DC]
0x180093999  jnb     short loc_1800939B0
0x18009399b  mov     eax, esi
0x18009399d  mov     [r14+rax*8], rdi
0x1800939a1  inc     esi
0x1800939a3  mov     [rsp+518h+var_4E0], esi
0x1800939a7  mov     al, 1
0x1800939a9  jmp     short loc_1800939B2
0x1800939ab  mov     r12, [rsp+518h+var_4D0]
0x1800939b0  mov     al, bl
0x1800939b2  test    al, al
0x1800939b4  jnz     short loc_1800939D1
0x1800939b6  test    rdi, rdi
0x1800939b9  jz      short loc_1800939D1
0x1800939bb  mov     r8, rdi; lpMem
0x1800939be  xor     edx, edx; dwFlags
0x1800939c0  mov     rcx, cs:PfSvcGlobals
0x1800939c7  mov     rcx, [rcx+58h]; hHeap
0x1800939cb  call    cs:__imp_HeapFree
0x1800939d1  cmp     esi, [rsp+518h+var_4DC]
0x1800939d5  jnb     short loc_1800939E1
0x1800939d7  add     r13, 14h
0x1800939db  jnz     loc_1800938EB
0x1800939e1  mov     r15, [rsp+518h+var_4B0]
0x1800939e6  cmp     [rsp+518h+BaseAddress+8], rbx
0x1800939ee  jz      short loc_1800939FA
0x1800939f0  lea     rcx, [rsp+518h+BaseAddress]
0x1800939f5  call    PfSvUnmapViewOfFile
0x1800939fa  mov     r12d, [rsp+518h+var_4D8]
0x1800939ff  inc     r12d
0x180093a02  mov     [rsp+518h+var_4D8], r12d
0x180093a07  mov     r13, [rsp+518h+var_4A8]
0x180093a0c  jmp     loc_180093775
0x180093a11  mov     edi, ebx
0x180093a13  jmp     short loc_180093A1A
0x180093a15  mov     edi, 18h
0x180093a1a  test    r14, r14
0x180093a1d  jz      short loc_180093A5E
0x180093a1f  mov     ebx, 1
0x180093a24  cmp     esi, ebx
0x180093a26  jbe     short loc_180093A48
0x180093a28  mov     r8d, ebx
0x180093a2b  mov     r8, [r14+r8*8]; lpMem
0x180093a2f  xor     edx, edx; dwFlags
0x180093a31  mov     rcx, cs:PfSvcGlobals
0x180093a38  mov     rcx, [rcx+58h]; hHeap
0x180093a3c  call    cs:__imp_HeapFree
0x180093a42  inc     ebx
0x180093a44  cmp     ebx, esi
0x180093a46  jb      short loc_180093A28
0x180093a48  mov     r8, r14; lpMem
0x180093a4b  xor     edx, edx; dwFlags
0x180093a4d  mov     rcx, cs:PfSvcGlobals
0x180093a54  mov     rcx, [rcx+58h]; hHeap
0x180093a58  call    cs:__imp_HeapFree
0x180093a5e  mov     eax, edi
0x180093a60  mov     rcx, [rsp+518h+var_48]
0x180093a68  xor     rcx, rsp; StackCookie
0x180093a6b  call    __security_check_cookie
0x180093a70  add     rsp, 4E0h
0x180093a77  pop     r15
0x180093a79  pop     r14
0x180093a7b  pop     r13
0x180093a7d  pop     r12
0x180093a7f  pop     rdi
0x180093a80  pop     rsi
0x180093a81  pop     rbx
0x180093a82  retn
```
