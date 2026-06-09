# PathFileExistsAndAttributesW

- ea: `0x180007b60`
- end: `0x180007c6e`
- name: `PathFileExistsAndAttributesW`
- size: `270`
- prototype: `__int64 __fastcall(WCHAR *pszPath, DWORD *)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180007b60`
- `0x180012550`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180007bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180007bdd`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180007bb9`
- `api-ms-win-core-errorhandling-l1-1-0!SetErrorMode` at `0x180007bdd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007bc4`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180007bc4`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180007c05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareW` at `0x180007c05`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180007bf8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerW` at `0x180007bf8`
- `MPR!WNetGetResourceInformationW` at `0x180007c50`
- `MPR!WNetGetResourceInformationW` at `0x180007c50`

## pseudocode

```c
__int64 __fastcall PathFileExistsAndAttributesW(WCHAR *pszPath, DWORD *a2)
{
  unsigned int v2; // esi
  UINT v6; // ebp
  DWORD FileAttributesW; // eax
  DWORD ResourceInformationW; // eax
  LPWSTR lpSystem; // [rsp+20h] [rbp-268h] BYREF
  struct _NETRESOURCEW NetResource; // [rsp+28h] [rbp-260h] BYREF
  DWORD cbBuffer; // [rsp+58h] [rbp-230h] BYREF
  _BYTE Buffer[512]; // [rsp+60h] [rbp-228h] BYREF

  v2 = 0;
  if ( a2 )
    *a2 = -1;
  if ( pszPath )
  {
    v6 = SetErrorMode(1u);
    FileAttributesW = GetFileAttributesW(pszPath);
    if ( a2 )
      *a2 = FileAttributesW;
    if ( FileAttributesW != -1
      || (PathIsUNCServerW(pszPath) || PathIsUNCServerShareW(pszPath))
      && ((*(_QWORD *)&NetResource.dwScope = 2,
           NetResource.lpRemoteName = pszPath,
           cbBuffer = 512,
           lpSystem = 0,
           *(_OWORD *)&NetResource.dwDisplayType = 0,
           *(_OWORD *)&NetResource.lpComment = 0,
           (ResourceInformationW = WNetGetResourceInformationW(&NetResource, Buffer, &cbBuffer, &lpSystem)) == 0)
       || ResourceInformationW == 234) )
    {
      v2 = 1;
    }
    SetErrorMode(v6);
  }
  return v2;
}

```

## disassembly

```asm
0x180007b60  push    rbx
0x180007b62  push    rsi
0x180007b63  push    rdi
0x180007b64  sub     rsp, 270h
0x180007b6b  mov     rax, cs:__security_cookie
0x180007b72  xor     rax, rsp
0x180007b75  mov     [rsp+288h+var_28], rax
0x180007b7d  xor     esi, esi
0x180007b7f  mov     rdi, rdx
0x180007b82  mov     rbx, rcx
0x180007b85  test    rdx, rdx
0x180007b88  jnz     short loc_180007BED
0x180007b8a  test    rbx, rbx
0x180007b8d  jnz     short loc_180007BAC
0x180007b8f  mov     eax, esi
0x180007b91  mov     rcx, [rsp+288h+var_28]
0x180007b99  xor     rcx, rsp; StackCookie
0x180007b9c  call    __security_check_cookie
0x180007ba1  add     rsp, 270h
0x180007ba8  pop     rdi
0x180007ba9  pop     rsi
0x180007baa  pop     rbx
0x180007bab  retn
0x180007bac  mov     ecx, 1; uMode
0x180007bb1  mov     [rsp+288h+arg_10], rbp
0x180007bb9  call    cs:__imp_SetErrorMode
0x180007bbf  mov     rcx, rbx; lpFileName
0x180007bc2  mov     ebp, eax
0x180007bc4  call    cs:__imp_GetFileAttributesW
0x180007bca  test    rdi, rdi
0x180007bcd  jz      short loc_180007BD1
0x180007bcf  mov     [rdi], eax
0x180007bd1  cmp     eax, 0FFFFFFFFh
0x180007bd4  jz      short loc_180007BF5
0x180007bd6  mov     esi, 1
0x180007bdb  mov     ecx, ebp; uMode
0x180007bdd  call    cs:__imp_SetErrorMode
0x180007be3  mov     rbp, [rsp+288h+arg_10]
0x180007beb  jmp     short loc_180007B8F
0x180007bed  mov     dword ptr [rdx], 0FFFFFFFFh
0x180007bf3  jmp     short loc_180007B8A
0x180007bf5  mov     rcx, rbx; pszPath
0x180007bf8  call    cs:__imp_PathIsUNCServerW
0x180007bfe  test    eax, eax
0x180007c00  jnz     short loc_180007C0F
0x180007c02  mov     rcx, rbx; pszPath
0x180007c05  call    cs:__imp_PathIsUNCServerShareW
0x180007c0b  test    eax, eax
0x180007c0d  jz      short loc_180007BDB
0x180007c0f  xorps   xmm0, xmm0
0x180007c12  mov     qword ptr [rsp+288h+NetResource.dwScope], 2
0x180007c1b  xorps   xmm1, xmm1
0x180007c1e  mov     [rsp+288h+NetResource.lpRemoteName], rbx
0x180007c23  lea     r9, [rsp+288h+lpSystem]; lplpSystem
0x180007c28  mov     [rsp+288h+cbBuffer], 200h
0x180007c30  lea     r8, [rsp+288h+cbBuffer]; lpcbBuffer
0x180007c35  mov     [rsp+288h+lpSystem], rsi
0x180007c3a  lea     rdx, [rsp+288h+Buffer]; lpBuffer
0x180007c3f  lea     rcx, [rsp+288h+NetResource]; lpNetResource
0x180007c44  movdqu  xmmword ptr [rsp+288h+NetResource.dwDisplayType], xmm0
0x180007c4a  movdqu  xmmword ptr [rsp+288h+NetResource.lpComment], xmm1
0x180007c50  call    cs:__imp_WNetGetResourceInformationW
0x180007c56  test    eax, eax
0x180007c58  jz      loc_180007BD6
0x180007c5e  cmp     eax, 0EAh
0x180007c63  jnz     loc_180007BDB
0x180007c69  jmp     loc_180007BD6
```
