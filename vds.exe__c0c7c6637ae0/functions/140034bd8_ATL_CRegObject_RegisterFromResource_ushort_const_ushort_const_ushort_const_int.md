# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140034bd8`
- end: `0x140034d7b`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `419`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x14003627c`
- `0x140036520`

## callees

- `0x14002f1bc`
- `0x14002f8c8`
- `0x1400301c4`
- `0x1400312a0`
- `0x1400314bc`
- `0x14003494c`
- `0x140034bd8`
- `0x140052e80`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140034c22`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140034c22`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140034d39`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140034d39`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140034c6b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x140034c6b`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140034c4d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x140034c4d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140034c84`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140034c84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034d04`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x140034d04`

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
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  _QWORD *v19; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR lpWideCharStr; // [rsp+60h] [rbp-438h] BYREF
  char v22; // [rsp+68h] [rbp-430h] BYREF

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
0x140034bd8  mov     [rsp+arg_0], rbx
0x140034bdd  push    rsi
0x140034bde  push    rdi
0x140034bdf  push    r14
0x140034be1  sub     rsp, 480h
0x140034be8  mov     rax, cs:__security_cookie
0x140034bef  xor     rax, rsp
0x140034bf2  mov     [rsp+498h+var_28], rax
0x140034bfa  mov     r14, r9
0x140034bfd  mov     rdi, r8
0x140034c00  mov     rax, rdx
0x140034c03  xor     ebx, ebx
0x140034c05  mov     [rsp+498h+var_450], rbx
0x140034c0a  mov     [rsp+498h+var_440], rcx
0x140034c0f  mov     [rsp+498h+var_448], rbx
0x140034c14  mov     [rsp+498h+var_438], rbx
0x140034c19  xor     edx, edx; hFile
0x140034c1b  lea     r8d, [rbx+2]; dwFlags
0x140034c1f  mov     rcx, rax; lpLibFileName
0x140034c22  call    cs:__imp_LoadLibraryExW
0x140034c28  mov     rsi, rax
0x140034c2b  mov     [rsp+498h+var_460], rax
0x140034c30  test    rax, rax
0x140034c33  jnz     short loc_140034C41
0x140034c35  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140034c3a  mov     ebx, eax
0x140034c3c  jmp     loc_140034D40
0x140034c41  xor     r9d, r9d; wLanguage
0x140034c44  mov     r8, rdi; lpName
0x140034c47  mov     rdx, r14; lpType
0x140034c4a  mov     rcx, rsi; hModule
0x140034c4d  call    cs:__imp_FindResourceExW
0x140034c53  mov     rdi, rax
0x140034c56  test    rax, rax
0x140034c59  jnz     short loc_140034C65
0x140034c5b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140034c60  jmp     loc_140034D34
0x140034c65  mov     rdx, rdi; hResInfo
0x140034c68  mov     rcx, rsi; hModule
0x140034c6b  call    cs:__imp_LoadResource
0x140034c71  mov     r14, rax
0x140034c74  mov     [rsp+498h+var_458], rax
0x140034c79  test    rax, rax
0x140034c7c  jz      short loc_140034C5B
0x140034c7e  mov     rdx, rdi; hResInfo
0x140034c81  mov     rcx, rsi; hModule
0x140034c84  call    cs:__imp_SizeofResource
0x140034c8a  mov     edi, eax
0x140034c8c  mov     [rsp+498h+var_468], eax
0x140034c90  inc     eax
0x140034c92  cmp     eax, edi
0x140034c94  jnb     short loc_140034CA0
0x140034c96  mov     ebx, 8007000Eh
0x140034c9b  jmp     loc_140034D40
0x140034ca0  mov     ecx, eax
0x140034ca2  mov     edx, 2
0x140034ca7  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x140034cac  cmp     rax, 400h
0x140034cb2  jbe     short loc_140034CC3
0x140034cb4  mov     rdx, rax
0x140034cb7  lea     rcx, [rsp+498h+var_438]
0x140034cbc  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x140034cc1  jmp     short loc_140034CCD
0x140034cc3  lea     rax, [rsp+498h+var_430]
0x140034cc8  mov     [rsp+498h+var_438], rax
0x140034ccd  jmp     short loc_140034CDF
0x140034ccf  xor     ebx, ebx
0x140034cd1  mov     rsi, [rsp+498h+var_460]
0x140034cd6  mov     r14, [rsp+498h+var_458]
0x140034cdb  mov     edi, [rsp+498h+var_468]
0x140034cdf  mov     rax, [rsp+498h+var_438]
0x140034ce4  test    rax, rax
0x140034ce7  jnz     short loc_140034CF0
0x140034ce9  mov     ebx, 8007000Eh
0x140034cee  jmp     short loc_140034D36
0x140034cf0  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x140034cf4  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x140034cf9  mov     r9d, edi; cbMultiByte
0x140034cfc  mov     r8, r14; lpMultiByteStr
0x140034cff  xor     edx, edx; dwFlags
0x140034d01  lea     ecx, [rdx+3]; CodePage
0x140034d04  call    cs:__imp_MultiByteToWideChar
0x140034d0a  test    eax, eax
0x140034d0c  jz      loc_140034C5B
0x140034d12  mov     ecx, eax
0x140034d14  mov     rax, [rsp+498h+var_438]
0x140034d19  mov     [rax+rcx*2], bx
0x140034d1d  mov     r8d, [rsp+498h+arg_20]; int
0x140034d25  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x140034d2a  lea     rcx, [rsp+498h+var_448]; this
0x140034d2f  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140034d34  mov     ebx, eax
0x140034d36  mov     rcx, rsi; hLibModule
0x140034d39  call    cs:__imp_FreeLibrary
0x140034d3f  nop
0x140034d40  lea     rcx, [rsp+498h+var_438]
0x140034d45  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x140034d4a  nop
0x140034d4b  lea     rcx, [rsp+498h+var_450]
0x140034d50  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x140034d55  mov     eax, ebx
0x140034d57  mov     rcx, [rsp+498h+var_28]
0x140034d5f  xor     rcx, rsp; StackCookie
0x140034d62  call    __security_check_cookie
0x140034d67  mov     rbx, [rsp+498h+arg_0]
0x140034d6f  add     rsp, 480h
0x140034d76  pop     r14
0x140034d78  pop     rdi
0x140034d79  pop     rsi
0x140034d7a  retn
```
