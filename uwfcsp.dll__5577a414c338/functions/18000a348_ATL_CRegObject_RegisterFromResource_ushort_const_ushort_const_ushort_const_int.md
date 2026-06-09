# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000a348`
- end: `0x18000a503`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000bb3c`
- `0x18000be5c`

## callees

- `0x180008b28`
- `0x180008c58`
- `0x180008c94`
- `0x180009288`
- `0x18000a1b8`
- `0x18000a348`
- `0x18001a210`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a3dd`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000a3dd`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a3bf`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000a3bf`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a399`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000a399`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a4b8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000a4b8`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000a3f1`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000a3f1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a482`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000a482`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  LPCWSTR v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  v15 = cchWideChar + 1;
  if ( (unsigned int)v15 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 )
      ATL::AtlThrowImpl(-2147024809, 0xFFFFFFFFFFFFFFFFuLL % (unsigned int)v15, v15);
    if ( (unsigned __int64)(2 * v15) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2 * v15);
      lpWideCharStr = v20;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v8);
      goto LABEL_21;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v20[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer(v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a348  mov     [rsp-8+arg_0], rbx
0x18000a34d  push    rbp
0x18000a34e  push    rsi
0x18000a34f  push    rdi
0x18000a350  lea     rbp, [rsp-360h]
0x18000a358  sub     rsp, 460h
0x18000a35f  mov     rax, cs:__security_cookie
0x18000a366  xor     rax, rsp
0x18000a369  mov     [rbp+370h+var_20], rax
0x18000a370  mov     rax, rdx
0x18000a373  mov     [rsp+470h+var_438], rcx
0x18000a378  xor     edx, edx; hFile
0x18000a37a  mov     [rsp+470h+var_440], 0
0x18000a383  mov     rbx, r8
0x18000a386  mov     [rsp+470h+var_430], 0
0x18000a38f  mov     rcx, rax; lpLibFileName
0x18000a392  mov     rsi, r9
0x18000a395  lea     r8d, [rdx+2]; dwFlags
0x18000a399  call    cs:__imp_LoadLibraryExW
0x18000a39f  mov     rdi, rax
0x18000a3a2  test    rax, rax
0x18000a3a5  jnz     short loc_18000A3B3
0x18000a3a7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a3ac  mov     ebx, eax
0x18000a3ae  jmp     loc_18000A4BE
0x18000a3b3  xor     r9d, r9d; wLanguage
0x18000a3b6  mov     r8, rbx; lpName
0x18000a3b9  mov     rdx, rsi; lpType
0x18000a3bc  mov     rcx, rdi; hModule
0x18000a3bf  call    cs:__imp_FindResourceExW
0x18000a3c5  mov     rbx, rax
0x18000a3c8  test    rax, rax
0x18000a3cb  jnz     short loc_18000A3D7
0x18000a3cd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000a3d2  jmp     loc_18000A4B3
0x18000a3d7  mov     rdx, rbx; hResInfo
0x18000a3da  mov     rcx, rdi; hModule
0x18000a3dd  call    cs:__imp_LoadResource
0x18000a3e3  mov     rsi, rax
0x18000a3e6  test    rax, rax
0x18000a3e9  jz      short loc_18000A3CD
0x18000a3eb  mov     rdx, rbx; hResInfo
0x18000a3ee  mov     rcx, rdi; hModule
0x18000a3f1  call    cs:__imp_SizeofResource
0x18000a3f7  mov     ebx, eax
0x18000a3f9  lea     ecx, [rax+1]
0x18000a3fc  cmp     ecx, eax
0x18000a3fe  jnb     short loc_18000A420
0x18000a400  lea     rax, [rsp+470h+var_428]
0x18000a405  cmp     [rsp+470h+var_430], rax
0x18000a40a  jz      short loc_18000A416
0x18000a40c  lea     rcx, [rsp+470h+var_430]
0x18000a411  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000a416  mov     eax, 8007000Eh
0x18000a41b  jmp     loc_18000A4D6
0x18000a420  test    ecx, ecx
0x18000a422  jz      short loc_18000A458
0x18000a424  xor     edx, edx
0x18000a426  mov     r8d, ecx
0x18000a429  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000a42d  div     r8
0x18000a430  cmp     rax, 2
0x18000a434  jb      loc_18000A4F8
0x18000a43a  lea     rdx, [rcx+rcx]
0x18000a43e  cmp     rdx, 400h
0x18000a445  jbe     short loc_18000A458
0x18000a447  lea     rcx, [rsp+470h+var_430]
0x18000a44c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000a451  mov     rax, [rsp+470h+var_430]
0x18000a456  jmp     short loc_18000A462
0x18000a458  lea     rax, [rsp+470h+var_428]
0x18000a45d  mov     [rsp+470h+var_430], rax
0x18000a462  test    rax, rax
0x18000a465  jnz     short loc_18000A46E
0x18000a467  mov     ebx, 8007000Eh
0x18000a46c  jmp     short loc_18000A4B5
0x18000a46e  xor     edx, edx; dwFlags
0x18000a470  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x18000a474  mov     r9d, ebx; cbMultiByte
0x18000a477  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000a47c  mov     r8, rsi; lpMultiByteStr
0x18000a47f  lea     ecx, [rdx+3]; CodePage
0x18000a482  call    cs:__imp_MultiByteToWideChar
0x18000a488  test    eax, eax
0x18000a48a  jz      loc_18000A3CD
0x18000a490  mov     r8d, [rbp+370h+arg_20]; int
0x18000a497  xor     ecx, ecx
0x18000a499  mov     edx, eax
0x18000a49b  mov     rax, [rsp+470h+var_430]
0x18000a4a0  mov     [rax+rdx*2], cx
0x18000a4a4  lea     rcx, [rsp+470h+var_440]; this
0x18000a4a9  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000a4ae  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000a4b3  mov     ebx, eax
0x18000a4b5  mov     rcx, rdi; hLibModule
0x18000a4b8  call    cs:__imp_FreeLibrary
0x18000a4be  lea     rax, [rsp+470h+var_428]
0x18000a4c3  cmp     [rsp+470h+var_430], rax
0x18000a4c8  jz      short loc_18000A4D4
0x18000a4ca  lea     rcx, [rsp+470h+var_430]
0x18000a4cf  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000a4d4  mov     eax, ebx
0x18000a4d6  mov     rcx, [rbp+370h+var_20]
0x18000a4dd  xor     rcx, rsp; StackCookie
0x18000a4e0  call    __security_check_cookie
0x18000a4e5  mov     rbx, [rsp+470h+arg_0]
0x18000a4ed  add     rsp, 460h
0x18000a4f4  pop     rdi
0x18000a4f5  pop     rsi
0x18000a4f6  pop     rbp
0x18000a4f7  retn
0x18000a4f8  mov     ecx, 80070057h; int
0x18000a4fd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
