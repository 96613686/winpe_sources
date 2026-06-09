# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000bd28`
- end: `0x18000bed0`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000cfec`
- `0x18000d264`

## callees

- `0x180001580`
- `0x180007e18`
- `0x180007f50`
- `0x180008094`
- `0x180008c24`
- `0x180008ed8`
- `0x18000bb2c`
- `0x18000bd28`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000bdd4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000bdd4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000bdbb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000bdbb`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000bd9d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000bd9d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd72`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000bd72`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be8e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000be8e`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000be59`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000be59`

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
  size_t v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
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
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
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
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
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
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18000bd28  mov     [rsp+arg_0], rbx
0x18000bd2d  push    rsi
0x18000bd2e  push    rdi
0x18000bd2f  push    r14
0x18000bd31  sub     rsp, 480h
0x18000bd38  mov     rax, cs:__security_cookie
0x18000bd3f  xor     rax, rsp
0x18000bd42  mov     [rsp+498h+var_28], rax
0x18000bd4a  mov     r14, r9
0x18000bd4d  mov     rdi, r8
0x18000bd50  mov     rax, rdx
0x18000bd53  xor     ebx, ebx
0x18000bd55  mov     [rsp+498h+var_450], rbx
0x18000bd5a  mov     [rsp+498h+var_440], rcx
0x18000bd5f  mov     [rsp+498h+var_448], rbx
0x18000bd64  mov     [rsp+498h+var_438], rbx
0x18000bd69  xor     edx, edx; hFile
0x18000bd6b  lea     r8d, [rbx+2]; dwFlags
0x18000bd6f  mov     rcx, rax; lpLibFileName
0x18000bd72  call    cs:__imp_LoadLibraryExW
0x18000bd78  mov     rsi, rax
0x18000bd7b  mov     [rsp+498h+var_460], rax
0x18000bd80  test    rax, rax
0x18000bd83  jnz     short loc_18000BD91
0x18000bd85  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bd8a  mov     ebx, eax
0x18000bd8c  jmp     loc_18000BE95
0x18000bd91  xor     r9d, r9d; wLanguage
0x18000bd94  mov     r8, rdi; lpName
0x18000bd97  mov     rdx, r14; lpType
0x18000bd9a  mov     rcx, rsi; hModule
0x18000bd9d  call    cs:__imp_FindResourceExW
0x18000bda3  mov     rdi, rax
0x18000bda6  test    rax, rax
0x18000bda9  jnz     short loc_18000BDB5
0x18000bdab  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000bdb0  jmp     loc_18000BE89
0x18000bdb5  mov     rdx, rdi; hResInfo
0x18000bdb8  mov     rcx, rsi; hModule
0x18000bdbb  call    cs:__imp_LoadResource
0x18000bdc1  mov     r14, rax
0x18000bdc4  mov     [rsp+498h+var_458], rax
0x18000bdc9  test    rax, rax
0x18000bdcc  jz      short loc_18000BDAB
0x18000bdce  mov     rdx, rdi; hResInfo
0x18000bdd1  mov     rcx, rsi; hModule
0x18000bdd4  call    cs:__imp_SizeofResource
0x18000bdda  mov     edi, eax
0x18000bddc  mov     [rsp+498h+var_468], eax
0x18000bde0  inc     eax
0x18000bde2  cmp     eax, edi
0x18000bde4  jnb     short loc_18000BDF0
0x18000bde6  mov     ebx, 8007000Eh
0x18000bdeb  jmp     loc_18000BE95
0x18000bdf0  mov     ecx, eax
0x18000bdf2  mov     edx, 2
0x18000bdf7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000bdfc  cmp     rax, 400h
0x18000be02  jbe     short loc_18000BE18
0x18000be04  mov     rdx, rax
0x18000be07  lea     rcx, [rsp+498h+var_438]
0x18000be0c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000be11  mov     rax, [rsp+498h+var_438]
0x18000be16  jmp     short loc_18000BE22
0x18000be18  lea     rax, [rsp+498h+var_430]
0x18000be1d  mov     [rsp+498h+var_438], rax
0x18000be22  jmp     short loc_18000BE39
0x18000be24  xor     ebx, ebx
0x18000be26  mov     rsi, [rsp+498h+var_460]
0x18000be2b  mov     r14, [rsp+498h+var_458]
0x18000be30  mov     edi, [rsp+498h+var_468]
0x18000be34  mov     rax, [rsp+498h+var_438]
0x18000be39  test    rax, rax
0x18000be3c  jnz     short loc_18000BE45
0x18000be3e  mov     ebx, 8007000Eh
0x18000be43  jmp     short loc_18000BE8B
0x18000be45  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18000be49  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18000be4e  mov     r9d, edi; cbMultiByte
0x18000be51  mov     r8, r14; lpMultiByteStr
0x18000be54  xor     edx, edx; dwFlags
0x18000be56  lea     ecx, [rdx+3]; CodePage
0x18000be59  call    cs:__imp_MultiByteToWideChar
0x18000be5f  test    eax, eax
0x18000be61  jz      loc_18000BDAB
0x18000be67  mov     ecx, eax
0x18000be69  mov     rax, [rsp+498h+var_438]
0x18000be6e  mov     [rax+rcx*2], bx
0x18000be72  mov     r8d, [rsp+498h+arg_20]; int
0x18000be7a  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18000be7f  lea     rcx, [rsp+498h+var_448]; this
0x18000be84  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000be89  mov     ebx, eax
0x18000be8b  mov     rcx, rsi; hLibModule
0x18000be8e  call    cs:__imp_FreeLibrary
0x18000be94  nop
0x18000be95  lea     rcx, [rsp+498h+var_438]
0x18000be9a  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000be9f  nop
0x18000bea0  lea     rcx, [rsp+498h+var_450]
0x18000bea5  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000beaa  mov     eax, ebx
0x18000beac  mov     rcx, [rsp+498h+var_28]
0x18000beb4  xor     rcx, rsp; StackCookie
0x18000beb7  call    __security_check_cookie
0x18000bebc  mov     rbx, [rsp+498h+arg_0]
0x18000bec4  add     rsp, 480h
0x18000becb  pop     r14
0x18000becd  pop     rdi
0x18000bece  pop     rsi
0x18000becf  retn
```
