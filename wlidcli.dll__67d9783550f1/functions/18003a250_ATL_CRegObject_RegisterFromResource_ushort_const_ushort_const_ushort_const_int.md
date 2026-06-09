# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18003a250`
- end: `0x18003a3f6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `422`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003ac80`

## callees

- `0x180002da0`
- `0x18000fa9c`
- `0x180013410`
- `0x180038440`
- `0x1800384f4`
- `0x180038e4c`
- `0x18003a0dc`
- `0x18003a250`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a297`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18003a297`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18003a2fa`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18003a2fa`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18003a2c3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18003a2c3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18003a2e1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18003a2e1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a3b4`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18003a3b4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a37f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18003a37f`

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
  HMODULE v7; // rdi
  unsigned int v8; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rsi
  signed int Error; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  size_t v14; // rax
  WCHAR *lpWideCharStr; // rax
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-460h]
  __int64 v19; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v20[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19 = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  v18 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x66, 0);
    v10 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v12 = (const CHAR *)LoadResource(v7, Resource);
    if ( !v12 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v7, v10);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v8 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v14 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v14 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, v14);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v7 = v18;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      v8 = -2147024882;
LABEL_16:
      FreeLibrary(v7);
      goto LABEL_17;
    }
    v16 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v16 )
    {
      v21[v16] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v8 = Error;
    goto LABEL_16;
  }
  v8 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v21);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v19);
  return v8;
}

```

## disassembly

```asm
0x18003a250  mov     [rsp+arg_0], rbx
0x18003a255  push    rsi
0x18003a256  push    rdi
0x18003a257  push    r14
0x18003a259  sub     rsp, 480h
0x18003a260  mov     rax, cs:__security_cookie
0x18003a267  xor     rax, rsp
0x18003a26a  mov     [rsp+498h+var_28], rax
0x18003a272  mov     rsi, r9
0x18003a275  mov     rax, rdx
0x18003a278  xor     ebx, ebx
0x18003a27a  mov     [rsp+498h+var_450], rbx
0x18003a27f  mov     [rsp+498h+var_440], rcx
0x18003a284  mov     [rsp+498h+var_448], rbx
0x18003a289  mov     [rsp+498h+var_438], rbx
0x18003a28e  xor     edx, edx; hFile
0x18003a290  lea     r8d, [rbx+2]; dwFlags
0x18003a294  mov     rcx, rax; lpLibFileName
0x18003a297  call    cs:__imp_LoadLibraryExW
0x18003a29d  mov     rdi, rax
0x18003a2a0  mov     [rsp+498h+var_460], rax
0x18003a2a5  test    rax, rax
0x18003a2a8  jnz     short loc_18003A2B6
0x18003a2aa  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003a2af  mov     ebx, eax
0x18003a2b1  jmp     loc_18003A3BB
0x18003a2b6  xor     r9d, r9d; wLanguage
0x18003a2b9  lea     r8d, [r9+66h]; lpName
0x18003a2bd  mov     rdx, rsi; lpType
0x18003a2c0  mov     rcx, rdi; hModule
0x18003a2c3  call    cs:__imp_FindResourceExW
0x18003a2c9  mov     rsi, rax
0x18003a2cc  test    rax, rax
0x18003a2cf  jnz     short loc_18003A2DB
0x18003a2d1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003a2d6  jmp     loc_18003A3AF
0x18003a2db  mov     rdx, rsi; hResInfo
0x18003a2de  mov     rcx, rdi; hModule
0x18003a2e1  call    cs:__imp_LoadResource
0x18003a2e7  mov     r14, rax
0x18003a2ea  mov     [rsp+498h+var_458], rax
0x18003a2ef  test    rax, rax
0x18003a2f2  jz      short loc_18003A2D1
0x18003a2f4  mov     rdx, rsi; hResInfo
0x18003a2f7  mov     rcx, rdi; hModule
0x18003a2fa  call    cs:__imp_SizeofResource
0x18003a300  mov     esi, eax
0x18003a302  mov     [rsp+498h+var_468], eax
0x18003a306  inc     eax
0x18003a308  cmp     eax, esi
0x18003a30a  jnb     short loc_18003A316
0x18003a30c  mov     ebx, 8007000Eh
0x18003a311  jmp     loc_18003A3BB
0x18003a316  mov     ecx, eax
0x18003a318  mov     edx, 2
0x18003a31d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18003a322  cmp     rax, 400h
0x18003a328  jbe     short loc_18003A33E
0x18003a32a  mov     rdx, rax
0x18003a32d  lea     rcx, [rsp+498h+var_438]
0x18003a332  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18003a337  mov     rax, [rsp+498h+var_438]
0x18003a33c  jmp     short loc_18003A348
0x18003a33e  lea     rax, [rsp+498h+var_430]
0x18003a343  mov     [rsp+498h+var_438], rax
0x18003a348  jmp     short loc_18003A35F
0x18003a34a  xor     ebx, ebx
0x18003a34c  mov     rdi, [rsp+498h+var_460]
0x18003a351  mov     r14, [rsp+498h+var_458]
0x18003a356  mov     esi, [rsp+498h+var_468]
0x18003a35a  mov     rax, [rsp+498h+var_438]
0x18003a35f  test    rax, rax
0x18003a362  jnz     short loc_18003A36B
0x18003a364  mov     ebx, 8007000Eh
0x18003a369  jmp     short loc_18003A3B1
0x18003a36b  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x18003a36f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18003a374  mov     r9d, esi; cbMultiByte
0x18003a377  mov     r8, r14; lpMultiByteStr
0x18003a37a  xor     edx, edx; dwFlags
0x18003a37c  lea     ecx, [rdx+3]; CodePage
0x18003a37f  call    cs:__imp_MultiByteToWideChar
0x18003a385  test    eax, eax
0x18003a387  jz      loc_18003A2D1
0x18003a38d  mov     ecx, eax
0x18003a38f  mov     rax, [rsp+498h+var_438]
0x18003a394  mov     [rax+rcx*2], bx
0x18003a398  mov     r8d, [rsp+498h+arg_20]; int
0x18003a3a0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18003a3a5  lea     rcx, [rsp+498h+var_448]; this
0x18003a3aa  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18003a3af  mov     ebx, eax
0x18003a3b1  mov     rcx, rdi; hLibModule
0x18003a3b4  call    cs:__imp_FreeLibrary
0x18003a3ba  nop
0x18003a3bb  lea     rcx, [rsp+498h+var_438]
0x18003a3c0  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18003a3c5  nop
0x18003a3c6  lea     rcx, [rsp+498h+var_450]
0x18003a3cb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18003a3d0  mov     eax, ebx
0x18003a3d2  mov     rcx, [rsp+498h+var_28]
0x18003a3da  xor     rcx, rsp; StackCookie
0x18003a3dd  call    __security_check_cookie
0x18003a3e2  mov     rbx, [rsp+498h+arg_0]
0x18003a3ea  add     rsp, 480h
0x18003a3f1  pop     r14
0x18003a3f3  pop     rdi
0x18003a3f4  pop     rsi
0x18003a3f5  retn
```
