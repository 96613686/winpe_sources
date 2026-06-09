# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180041918`
- end: `0x180041aa8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180043a4c`
- `0x180043cc4`

## callees

- `0x18003a560`
- `0x18003bbdc`
- `0x18003c5c8`
- `0x18003cae8`
- `0x18003ddcc`
- `0x18003df80`
- `0x180041690`
- `0x180041918`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180041998`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180041998`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800419ca`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800419ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800419b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800419b6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041972`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180041972`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041a6a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180041a6a`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180041a34`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180041a34`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int Error; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  __int64 v19; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v20[3]; // [rsp+38h] [rbp-C8h] BYREF
  LPWSTR v21; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v22[1032]; // [rsp+58h] [rbp-A8h] BYREF

  v20[1] = this;
  v19 = 0;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
    if ( v15 <= 0x400 )
    {
      lpWideCharStr = (WCHAR *)v22;
      v21 = (LPWSTR)v22;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v15);
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v21[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x180041918  mov     [rsp-8+arg_0], rbx
0x18004191d  push    rbp
0x18004191e  push    rsi
0x18004191f  push    rdi
0x180041920  lea     rbp, [rsp-370h]
0x180041928  sub     rsp, 470h
0x18004192f  mov     rax, cs:__security_cookie
0x180041936  xor     rax, rsp
0x180041939  mov     [rbp+380h+var_20], rax
0x180041940  mov     rax, rdx
0x180041943  mov     [rsp+480h+var_440], rcx
0x180041948  xor     edx, edx; hFile
0x18004194a  mov     [rsp+480h+var_450], 0
0x180041953  mov     rbx, r8
0x180041956  mov     [rsp+480h+var_448], 0
0x18004195f  mov     rcx, rax; lpLibFileName
0x180041962  mov     [rsp+480h+var_430], 0
0x18004196b  mov     rsi, r9
0x18004196e  lea     r8d, [rdx+2]; dwFlags
0x180041972  call    cs:__imp_LoadLibraryExW
0x180041978  mov     rdi, rax
0x18004197b  test    rax, rax
0x18004197e  jnz     short loc_18004198C
0x180041980  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180041985  mov     ebx, eax
0x180041987  jmp     loc_180041A70
0x18004198c  xor     r9d, r9d; wLanguage
0x18004198f  mov     r8, rbx; lpName
0x180041992  mov     rdx, rsi; lpType
0x180041995  mov     rcx, rdi; hModule
0x180041998  call    cs:__imp_FindResourceExW
0x18004199e  mov     rbx, rax
0x1800419a1  test    rax, rax
0x1800419a4  jnz     short loc_1800419B0
0x1800419a6  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800419ab  jmp     loc_180041A65
0x1800419b0  mov     rdx, rbx; hResInfo
0x1800419b3  mov     rcx, rdi; hModule
0x1800419b6  call    cs:__imp_LoadResource
0x1800419bc  mov     rsi, rax
0x1800419bf  test    rax, rax
0x1800419c2  jz      short loc_1800419A6
0x1800419c4  mov     rdx, rbx; hResInfo
0x1800419c7  mov     rcx, rdi; hModule
0x1800419ca  call    cs:__imp_SizeofResource
0x1800419d0  mov     ebx, eax
0x1800419d2  inc     eax
0x1800419d4  cmp     eax, ebx
0x1800419d6  jnb     short loc_1800419E2
0x1800419d8  mov     ebx, 8007000Eh
0x1800419dd  jmp     loc_180041A70
0x1800419e2  mov     ecx, eax
0x1800419e4  mov     edx, 2
0x1800419e9  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800419ee  cmp     rax, 400h
0x1800419f4  jbe     short loc_180041A0A
0x1800419f6  mov     rdx, rax
0x1800419f9  lea     rcx, [rsp+480h+var_430]
0x1800419fe  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180041a03  mov     rax, [rsp+480h+var_430]
0x180041a08  jmp     short loc_180041A14
0x180041a0a  lea     rax, [rsp+480h+var_428]
0x180041a0f  mov     [rsp+480h+var_430], rax
0x180041a14  test    rax, rax
0x180041a17  jnz     short loc_180041A20
0x180041a19  mov     ebx, 8007000Eh
0x180041a1e  jmp     short loc_180041A67
0x180041a20  xor     edx, edx; dwFlags
0x180041a22  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180041a26  mov     r9d, ebx; cbMultiByte
0x180041a29  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x180041a2e  mov     r8, rsi; lpMultiByteStr
0x180041a31  lea     ecx, [rdx+3]; CodePage
0x180041a34  call    cs:__imp_MultiByteToWideChar
0x180041a3a  test    eax, eax
0x180041a3c  jz      loc_1800419A6
0x180041a42  mov     r8d, [rbp+380h+arg_20]; int
0x180041a49  xor     ecx, ecx
0x180041a4b  mov     edx, eax
0x180041a4d  mov     rax, [rsp+480h+var_430]
0x180041a52  mov     [rax+rdx*2], cx
0x180041a56  lea     rcx, [rsp+480h+var_448]; this
0x180041a5b  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x180041a60  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180041a65  mov     ebx, eax
0x180041a67  mov     rcx, rdi; hLibModule
0x180041a6a  call    cs:__imp_FreeLibrary
0x180041a70  lea     rcx, [rsp+480h+var_430]
0x180041a75  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180041a7a  lea     rcx, [rsp+480h+var_450]
0x180041a7f  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180041a84  mov     eax, ebx
0x180041a86  mov     rcx, [rbp+380h+var_20]
0x180041a8d  xor     rcx, rsp; StackCookie
0x180041a90  call    __security_check_cookie
0x180041a95  mov     rbx, [rsp+480h+arg_0]
0x180041a9d  add     rsp, 470h
0x180041aa4  pop     rdi
0x180041aa5  pop     rsi
0x180041aa6  pop     rbp
0x180041aa7  retn
```
