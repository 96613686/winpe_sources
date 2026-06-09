# PathIsDirectoryA

- ea: `0x180019190`
- end: `0x180019292`
- name: `PathIsDirectoryA`
- size: `258`
- prototype: `BOOL __stdcall(LPCSTR pszPath)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops`

## callees

- `0x180012550`
- `0x180013066`
- `0x180019190`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180019259`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesA` at `0x180019259`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x1800191c2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerA` at `0x1800191c2`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x1800191d3`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathIsUNCServerShareA` at `0x1800191d3`
- `MPR!WNetGetResourceInformationA` at `0x180019226`
- `MPR!WNetGetResourceInformationA` at `0x180019226`

## pseudocode

```c
BOOL __stdcall PathIsDirectoryA(LPCSTR pszPath)
{
  BOOL result; // eax
  DWORD FileAttributesA; // edx
  LPSTR lpSystem; // [rsp+20h] [rbp-E0h] BYREF
  struct _NETRESOURCEA NetResource; // [rsp+30h] [rbp-D0h] BYREF
  DWORD cbBuffer; // [rsp+230h] [rbp+130h] BYREF

  if ( !pszPath || PathIsUNCServerA(pszPath) )
    return 0;
  if ( PathIsUNCServerShareA(pszPath) )
  {
    memset_0(&NetResource.dwType, 0, 0x1FCu);
    lpSystem = 0;
    cbBuffer = 512;
    *(_QWORD *)&NetResource.dwScope = 2;
    NetResource.lpRemoteName = (LPSTR)pszPath;
    if ( !WNetGetResourceInformationA(&NetResource, &NetResource, &cbBuffer, &lpSystem) )
    {
      if ( NetResource.dwDisplayType )
      {
        if ( NetResource.dwDisplayType == 3 )
          return !NetResource.dwType || NetResource.dwType == 1;
        return 0;
      }
    }
  }
  FileAttributesA = GetFileAttributesA(pszPath);
  result = 0;
  if ( FileAttributesA != -1 )
    return FileAttributesA & 0x10;
  return result;
}

```

## disassembly

```asm
0x180019190  mov     [rsp-8+arg_8], rbx
0x180019195  push    rbp
0x180019196  lea     rbp, [rsp-140h]
0x18001919e  sub     rsp, 240h
0x1800191a5  mov     rax, cs:__security_cookie
0x1800191ac  xor     rax, rsp
0x1800191af  mov     [rbp+140h+var_8], rax
0x1800191b6  mov     rbx, rcx
0x1800191b9  test    rcx, rcx
0x1800191bc  jz      loc_180019270
0x1800191c2  call    cs:__imp_PathIsUNCServerA
0x1800191c8  test    eax, eax
0x1800191ca  jnz     loc_180019270
0x1800191d0  mov     rcx, rbx; pszPath
0x1800191d3  call    cs:__imp_PathIsUNCServerShareA
0x1800191d9  test    eax, eax
0x1800191db  jz      short loc_180019256
0x1800191dd  xor     edx, edx; Val
0x1800191df  lea     rcx, [rsp+240h+NetResource.dwType]; void *
0x1800191e4  mov     r8d, 1FCh; Size
0x1800191ea  call    memset_0
0x1800191ef  lea     r9, [rsp+240h+lpSystem]; lplpSystem
0x1800191f4  mov     [rsp+240h+lpSystem], 0
0x1800191fd  lea     r8, [rbp+140h+cbBuffer]; lpcbBuffer
0x180019204  mov     [rbp+140h+cbBuffer], 200h
0x18001920e  lea     rdx, [rsp+240h+NetResource]; lpBuffer
0x180019213  mov     qword ptr [rsp+240h+NetResource.dwScope], 2
0x18001921c  lea     rcx, [rsp+240h+NetResource]; lpNetResource
0x180019221  mov     [rsp+240h+NetResource.lpRemoteName], rbx
0x180019226  call    cs:__imp_WNetGetResourceInformationA
0x18001922c  test    eax, eax
0x18001922e  jnz     short loc_180019256
0x180019230  mov     eax, [rsp+240h+NetResource.dwDisplayType]
0x180019234  test    eax, eax
0x180019236  jz      short loc_180019256
0x180019238  cmp     eax, 3
0x18001923b  jnz     short loc_180019270
0x18001923d  mov     ecx, [rsp+240h+NetResource.dwType]
0x180019241  test    ecx, ecx
0x180019243  jz      short loc_18001924F
0x180019245  xor     eax, eax
0x180019247  cmp     ecx, 1
0x18001924a  setz    al
0x18001924d  jmp     short loc_180019272
0x18001924f  mov     eax, 1
0x180019254  jmp     short loc_180019272
0x180019256  mov     rcx, rbx; lpFileName
0x180019259  call    cs:__imp_GetFileAttributesA
0x18001925f  mov     ecx, eax
0x180019261  mov     edx, eax
0x180019263  and     ecx, 10h
0x180019266  xor     eax, eax
0x180019268  cmp     edx, 0FFFFFFFFh
0x18001926b  cmovnz  eax, ecx
0x18001926e  jmp     short loc_180019272
0x180019270  xor     eax, eax
0x180019272  mov     rcx, [rbp+140h+var_8]
0x180019279  xor     rcx, rsp; StackCookie
0x18001927c  call    __security_check_cookie
0x180019281  mov     rbx, [rsp+240h+arg_8]
0x180019289  add     rsp, 240h
0x180019290  pop     rbp
0x180019291  retn
```
