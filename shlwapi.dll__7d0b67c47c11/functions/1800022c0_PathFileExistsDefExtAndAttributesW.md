# PathFileExistsDefExtAndAttributesW

- ea: `0x1800022c0`
- end: `0x18000247c`
- name: `PathFileExistsDefExtAndAttributesW`
- size: `444`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180001f40`
- `0x180001f90`

## callees

- `0x1800022c0`
- `0x1800025bc`
- `0x180012550`
- `0x180013066`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002343`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002360`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002389`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002343`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002360`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180002389`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000234e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002394`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18000234e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180002394`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1800023bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x1800023bc`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800023ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x1800023ad`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180002469`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsRelativeW` at `0x180002469`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000231f`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18000231f`
- `MPR!WNetGetResourceInformationW` at `0x18000240b`
- `MPR!WNetGetResourceInformationW` at `0x18000240b`

## pseudocode

```c
__int64 __fastcall PathFileExistsDefExtAndAttributesW(WCHAR *lpFileName, int a2, DWORD *a3)
{
  __int64 result; // rax
  __int64 v7; // rax
  UINT v9; // esi
  DWORD FileAttributesW; // eax
  unsigned int v11; // edi
  DWORD ResourceInformationW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-2B8h] BYREF
  _NETRESOURCEW NetResource; // [rsp+28h] [rbp-2B0h] BYREF
  DWORD cbBuffer; // [rsp+58h] [rbp-280h] BYREF
  _DWORD Buffer[148]; // [rsp+60h] [rbp-278h] BYREF

  if ( a3 )
    *a3 = -1;
  result = 0;
  if ( lpFileName )
  {
    v7 = -1;
    while ( lpFileName[++v7] != 0 )
      ;
    if ( lpFileName[v7 - 1] == 92 && !PathIsRelativeW(lpFileName)
      || !a2
      || *PathFindExtensionW(lpFileName) && (a2 & 0x40) != 0 )
    {
      if ( a3 )
      {
        *a3 = -1;
        v9 = SetErrorMode(1u);
        FileAttributesW = GetFileAttributesW(lpFileName);
        *a3 = FileAttributesW;
      }
      else
      {
        v9 = SetErrorMode(1u);
        FileAttributesW = GetFileAttributesW(lpFileName);
      }
      if ( FileAttributesW != -1 )
        goto LABEL_13;
      if ( !PathIsUNCServerW(lpFileName) )
      {
        v11 = 0;
        if ( !PathIsUNCServerShareW(lpFileName) )
          goto LABEL_14;
      }
      *(_QWORD *)&NetResource.dwScope = 2;
      NetResource.lpRemoteName = lpFileName;
      cbBuffer = 512;
      lpSystem = 0;
      *(_OWORD *)&NetResource.dwDisplayType = 0;
      *(_OWORD *)&NetResource.lpComment = 0;
      ResourceInformationW = WNetGetResourceInformationW(&NetResource, Buffer, &cbBuffer, &lpSystem);
      if ( ResourceInformationW && ResourceInformationW != 234 )
        v11 = 0;
      else
LABEL_13:
        v11 = 1;
LABEL_14:
      SetErrorMode(v9);
      return v11;
    }
    memset_0(Buffer, 0, sizeof(Buffer));
    result = ApplyDefaultExts(lpFileName);
    if ( (_DWORD)result && a3 )
      *a3 = Buffer[0];
  }
  return result;
}

```

## disassembly

```asm
0x1800022c0  push    rbx
0x1800022c2  push    rsi
0x1800022c3  push    rdi
0x1800022c4  sub     rsp, 2C0h
0x1800022cb  mov     rax, cs:__security_cookie
0x1800022d2  xor     rax, rsp
0x1800022d5  mov     [rsp+2D8h+var_28], rax
0x1800022dd  mov     rdi, r8
0x1800022e0  mov     esi, edx
0x1800022e2  mov     rbx, rcx
0x1800022e5  test    r8, r8
0x1800022e8  jnz     loc_18000239E
0x1800022ee  xor     eax, eax
0x1800022f0  test    rbx, rbx
0x1800022f3  jz      short loc_180002368
0x1800022f5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1800022fc  nop     dword ptr [rax+00h]
0x180002300  cmp     word ptr [rcx+rax*2+2], 0
0x180002306  lea     rax, [rax+1]
0x18000230a  jnz     short loc_180002300
0x18000230c  cmp     word ptr [rcx+rax*2-2], 5Ch ; '\'
0x180002312  jz      loc_180002469
0x180002318  test    esi, esi
0x18000231a  jz      short loc_180002339
0x18000231c  mov     rcx, rbx; pszPath
0x18000231f  call    cs:__imp_PathFindExtensionW
0x180002325  cmp     word ptr [rax], 0
0x180002329  jz      loc_18000242B
0x18000232f  test    sil, 40h
0x180002333  jz      loc_18000242B
0x180002339  mov     ecx, 1; uMode
0x18000233e  test    rdi, rdi
0x180002341  jnz     short loc_180002383
0x180002343  call    cs:__imp_SetErrorMode
0x180002349  mov     rcx, rbx; lpFileName
0x18000234c  mov     esi, eax
0x18000234e  call    cs:__imp_GetFileAttributesW
0x180002354  cmp     eax, 0FFFFFFFFh
0x180002357  jz      short loc_1800023AA
0x180002359  mov     edi, 1
0x18000235e  mov     ecx, esi; uMode
0x180002360  call    cs:__imp_SetErrorMode
0x180002366  mov     eax, edi
0x180002368  mov     rcx, [rsp+2D8h+var_28]
0x180002370  xor     rcx, rsp; StackCookie
0x180002373  call    __security_check_cookie
0x180002378  add     rsp, 2C0h
0x18000237f  pop     rdi
0x180002380  pop     rsi
0x180002381  pop     rbx
0x180002382  retn
0x180002383  mov     dword ptr [rdi], 0FFFFFFFFh
0x180002389  call    cs:__imp_SetErrorMode
0x18000238f  mov     rcx, rbx; lpFileName
0x180002392  mov     esi, eax
0x180002394  call    cs:__imp_GetFileAttributesW
0x18000239a  mov     [rdi], eax
0x18000239c  jmp     short loc_180002354
0x18000239e  mov     dword ptr [r8], 0FFFFFFFFh
0x1800023a5  jmp     loc_1800022EE
0x1800023aa  mov     rcx, rbx; pszPath
0x1800023ad  call    cs:__imp_PathIsUNCServerW
0x1800023b3  test    eax, eax
0x1800023b5  jnz     short loc_1800023C6
0x1800023b7  mov     rcx, rbx; pszPath
0x1800023ba  xor     edi, edi
0x1800023bc  call    cs:__imp_PathIsUNCServerShareW
0x1800023c2  test    eax, eax
0x1800023c4  jz      short loc_18000235E
0x1800023c6  xorps   xmm0, xmm0
0x1800023c9  mov     qword ptr [rsp+2D8h+NetResource.dwScope], 2
0x1800023d2  xorps   xmm1, xmm1
0x1800023d5  mov     [rsp+2D8h+NetResource.lpRemoteName], rbx
0x1800023da  lea     r9, [rsp+2D8h+lpSystem]; lplpSystem
0x1800023df  mov     [rsp+2D8h+cbBuffer], 200h
0x1800023e7  lea     r8, [rsp+2D8h+cbBuffer]; lpcbBuffer
0x1800023ec  mov     [rsp+2D8h+lpSystem], 0
0x1800023f5  lea     rdx, [rsp+2D8h+Buffer]; lpBuffer
0x1800023fa  lea     rcx, [rsp+2D8h+NetResource]; lpNetResource
0x1800023ff  movdqu  xmmword ptr [rsp+2D8h+NetResource.dwDisplayType], xmm0
0x180002405  movdqu  xmmword ptr [rsp+2D8h+NetResource.lpComment], xmm1
0x18000240b  call    cs:__imp_WNetGetResourceInformationW
0x180002411  test    eax, eax
0x180002413  jz      loc_180002359
0x180002419  cmp     eax, 0EAh
0x18000241e  jz      loc_180002359
0x180002424  xor     edi, edi
0x180002426  jmp     loc_18000235E
0x18000242b  xor     edx, edx; Val
0x18000242d  lea     rcx, [rsp+2D8h+Buffer]; void *
0x180002432  mov     r8d, 250h; Size
0x180002438  call    memset_0
0x18000243d  lea     r9, [rsp+2D8h+Buffer]
0x180002442  mov     r8d, esi
0x180002445  mov     rcx, rbx; lpFileName
0x180002448  call    ApplyDefaultExts
0x18000244d  test    eax, eax
0x18000244f  jz      loc_180002368
0x180002455  test    rdi, rdi
0x180002458  jz      loc_180002368
0x18000245e  mov     ecx, [rsp+2D8h+Buffer]; pszPath
0x180002462  mov     [rdi], ecx
0x180002464  jmp     loc_180002368
0x180002469  call    cs:__imp_PathIsRelativeW
0x18000246f  test    eax, eax
0x180002471  jz      loc_180002339
0x180002477  jmp     loc_180002318
```
