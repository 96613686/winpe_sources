# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000b584`
- end: `0x18000b732`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `430`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000cd1c`
- `0x18000cfc8`

## callees

- `0x180004818`
- `0x180004a18`
- `0x18000540c`
- `0x180006a9c`
- `0x180006d14`
- `0x18000b410`
- `0x18000b584`
- `0x18009a520`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b604`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000b604`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b622`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000b622`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b63b`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000b63b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b5d9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000b5d9`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b6f0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000b6f0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b6bb`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000b6bb`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  unsigned __int64 v15; // rax
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-470h]
  __int64 v19; // [rsp+48h] [rbp-460h] BYREF
  _QWORD v20[4]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR lpWideCharStr; // [rsp+70h] [rbp-438h] BYREF
  char v22; // [rsp+78h] [rbp-430h] BYREF

  v20[2] = -2;
  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  lpWideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v18 = Library;
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
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>(cchWideChar + 1, 2);
      if ( v15 <= 0x400 )
        lpWideCharStr = (LPWSTR)&v22;
      else
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&lpWideCharStr, v15);
    }
    catch ( ... )
    {
      v8 = v18;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v16 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v16 )
    {
      lpWideCharStr[v16] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, lpWideCharStr, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&lpWideCharStr);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v9;
}

```

## disassembly

```asm
0x18000b584  mov     rax, rsp
0x18000b587  push    rsi
0x18000b588  push    rdi
0x18000b589  push    r14
0x18000b58b  sub     rsp, 490h
0x18000b592  mov     [rsp+4A8h+var_448], 0FFFFFFFFFFFFFFFEh
0x18000b59b  mov     [rax+8], rbx
0x18000b59f  mov     rax, cs:__security_cookie
0x18000b5a6  xor     rax, rsp
0x18000b5a9  mov     [rsp+4A8h+var_28], rax
0x18000b5b1  mov     r14, r9
0x18000b5b4  mov     rdi, r8
0x18000b5b7  mov     rax, rdx
0x18000b5ba  xor     ebx, ebx
0x18000b5bc  mov     [rsp+4A8h+var_460], rbx
0x18000b5c1  mov     [rsp+4A8h+var_450], rcx
0x18000b5c6  mov     [rsp+4A8h+var_458], rbx
0x18000b5cb  mov     [rsp+4A8h+var_438], rbx
0x18000b5d0  xor     edx, edx; hFile
0x18000b5d2  lea     r8d, [rbx+2]; dwFlags
0x18000b5d6  mov     rcx, rax; lpLibFileName
0x18000b5d9  call    cs:__imp_LoadLibraryExW
0x18000b5df  mov     rsi, rax
0x18000b5e2  mov     [rsp+4A8h+var_470], rax
0x18000b5e7  test    rax, rax
0x18000b5ea  jnz     short loc_18000B5F8
0x18000b5ec  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b5f1  mov     ebx, eax
0x18000b5f3  jmp     loc_18000B6F7
0x18000b5f8  xor     r9d, r9d; wLanguage
0x18000b5fb  mov     r8, rdi; lpName
0x18000b5fe  mov     rdx, r14; lpType
0x18000b601  mov     rcx, rsi; hModule
0x18000b604  call    cs:__imp_FindResourceExW
0x18000b60a  mov     rdi, rax
0x18000b60d  test    rax, rax
0x18000b610  jnz     short loc_18000B61C
0x18000b612  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b617  jmp     loc_18000B6EB
0x18000b61c  mov     rdx, rdi; hResInfo
0x18000b61f  mov     rcx, rsi; hModule
0x18000b622  call    cs:__imp_LoadResource
0x18000b628  mov     r14, rax
0x18000b62b  mov     [rsp+4A8h+var_468], rax
0x18000b630  test    rax, rax
0x18000b633  jz      short loc_18000B612
0x18000b635  mov     rdx, rdi; hResInfo
0x18000b638  mov     rcx, rsi; hModule
0x18000b63b  call    cs:__imp_SizeofResource
0x18000b641  mov     edi, eax
0x18000b643  mov     [rsp+4A8h+var_478], eax
0x18000b647  inc     eax
0x18000b649  cmp     eax, edi
0x18000b64b  jnb     short loc_18000B657
0x18000b64d  mov     ebx, 8007000Eh
0x18000b652  jmp     loc_18000B6F7
0x18000b657  mov     ecx, eax
0x18000b659  mov     edx, 2
0x18000b65e  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000b663  cmp     rax, 400h
0x18000b669  jbe     short loc_18000B67A
0x18000b66b  mov     rdx, rax
0x18000b66e  lea     rcx, [rsp+4A8h+var_438]
0x18000b673  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b678  jmp     short loc_18000B684
0x18000b67a  lea     rax, [rsp+4A8h+var_430]
0x18000b67f  mov     [rsp+4A8h+var_438], rax
0x18000b684  jmp     short loc_18000B696
0x18000b686  xor     ebx, ebx
0x18000b688  mov     rsi, [rsp+4A8h+var_470]
0x18000b68d  mov     r14, [rsp+4A8h+var_468]
0x18000b692  mov     edi, [rsp+4A8h+var_478]
0x18000b696  mov     rax, [rsp+4A8h+var_438]
0x18000b69b  test    rax, rax
0x18000b69e  jnz     short loc_18000B6A7
0x18000b6a0  mov     ebx, 8007000Eh
0x18000b6a5  jmp     short loc_18000B6ED
0x18000b6a7  mov     [rsp+4A8h+cchWideChar], edi; cchWideChar
0x18000b6ab  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18000b6b0  mov     r9d, edi; cbMultiByte
0x18000b6b3  mov     r8, r14; lpMultiByteStr
0x18000b6b6  xor     edx, edx; dwFlags
0x18000b6b8  lea     ecx, [rdx+3]; CodePage
0x18000b6bb  call    cs:__imp_MultiByteToWideChar
0x18000b6c1  test    eax, eax
0x18000b6c3  jz      loc_18000B612
0x18000b6c9  mov     ecx, eax
0x18000b6cb  mov     rax, [rsp+4A8h+var_438]
0x18000b6d0  mov     [rax+rcx*2], bx
0x18000b6d4  mov     r8d, [rsp+4A8h+arg_20]; int
0x18000b6dc  mov     rdx, [rsp+4A8h+var_438]; unsigned __int16 *
0x18000b6e1  lea     rcx, [rsp+4A8h+var_458]; this
0x18000b6e6  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000b6eb  mov     ebx, eax
0x18000b6ed  mov     rcx, rsi; hLibModule
0x18000b6f0  call    cs:__imp_FreeLibrary
0x18000b6f6  nop
0x18000b6f7  lea     rcx, [rsp+4A8h+var_438]
0x18000b6fc  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000b701  nop
0x18000b702  lea     rcx, [rsp+4A8h+var_460]
0x18000b707  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000b70c  mov     eax, ebx
0x18000b70e  mov     rcx, [rsp+4A8h+var_28]
0x18000b716  xor     rcx, rsp; StackCookie
0x18000b719  call    __security_check_cookie
0x18000b71e  mov     rbx, [rsp+4A8h+arg_0]
0x18000b726  add     rsp, 490h
0x18000b72d  pop     r14
0x18000b72f  pop     rdi
0x18000b730  pop     rsi
0x18000b731  retn
```
