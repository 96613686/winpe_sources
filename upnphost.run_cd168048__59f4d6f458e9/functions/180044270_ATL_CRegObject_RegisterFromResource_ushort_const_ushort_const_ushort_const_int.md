# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180044270`
- end: `0x180044425`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `437`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180046500`
- `0x180046784`

## callees

- `0x18003cb60`
- `0x18003e240`
- `0x18003ec5c`
- `0x18003f12c`
- `0x180040410`
- `0x18004062c`
- `0x180044058`
- `0x180044270`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800442f6`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800442f6`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180044334`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180044334`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004431a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18004431a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800442ca`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800442ca`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800443e0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800443e0`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800443a4`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800443a4`

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
  unsigned __int64 v15; // rax
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
0x180044270  mov     [rsp-8+arg_0], rbx
0x180044275  push    rbp
0x180044276  push    rsi
0x180044277  push    rdi
0x180044278  lea     rbp, [rsp-370h]
0x180044280  sub     rsp, 470h
0x180044287  mov     rax, cs:__security_cookie
0x18004428e  xor     rax, rsp
0x180044291  mov     [rbp+380h+var_20], rax
0x180044298  mov     rax, rdx
0x18004429b  mov     [rsp+480h+var_440], rcx
0x1800442a0  xor     edx, edx; hFile
0x1800442a2  mov     [rsp+480h+var_450], 0
0x1800442ab  mov     rbx, r8
0x1800442ae  mov     [rsp+480h+var_448], 0
0x1800442b7  mov     rcx, rax; lpLibFileName
0x1800442ba  mov     [rsp+480h+var_430], 0
0x1800442c3  mov     rsi, r9
0x1800442c6  lea     r8d, [rdx+2]; dwFlags
0x1800442ca  call    cs:__imp_LoadLibraryExW
0x1800442d1  nop     dword ptr [rax+rax+00h]
0x1800442d6  mov     rdi, rax
0x1800442d9  test    rax, rax
0x1800442dc  jnz     short loc_1800442EA
0x1800442de  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800442e3  mov     ebx, eax
0x1800442e5  jmp     loc_1800443EC
0x1800442ea  xor     r9d, r9d; wLanguage
0x1800442ed  mov     r8, rbx; lpName
0x1800442f0  mov     rdx, rsi; lpType
0x1800442f3  mov     rcx, rdi; hModule
0x1800442f6  call    cs:__imp_FindResourceExW
0x1800442fd  nop     dword ptr [rax+rax+00h]
0x180044302  mov     rbx, rax
0x180044305  test    rax, rax
0x180044308  jnz     short loc_180044314
0x18004430a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18004430f  jmp     loc_1800443DB
0x180044314  mov     rdx, rbx; hResInfo
0x180044317  mov     rcx, rdi; hModule
0x18004431a  call    cs:__imp_LoadResource
0x180044321  nop     dword ptr [rax+rax+00h]
0x180044326  mov     rsi, rax
0x180044329  test    rax, rax
0x18004432c  jz      short loc_18004430A
0x18004432e  mov     rdx, rbx; hResInfo
0x180044331  mov     rcx, rdi; hModule
0x180044334  call    cs:__imp_SizeofResource
0x18004433b  nop     dword ptr [rax+rax+00h]
0x180044340  mov     ebx, eax
0x180044342  inc     eax
0x180044344  cmp     eax, ebx
0x180044346  jnb     short loc_180044352
0x180044348  mov     ebx, 8007000Eh
0x18004434d  jmp     loc_1800443EC
0x180044352  mov     ecx, eax
0x180044354  mov     edx, 2
0x180044359  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18004435e  cmp     rax, 400h
0x180044364  jbe     short loc_18004437A
0x180044366  mov     rdx, rax
0x180044369  lea     rcx, [rsp+480h+var_430]
0x18004436e  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180044373  mov     rax, [rsp+480h+var_430]
0x180044378  jmp     short loc_180044384
0x18004437a  lea     rax, [rsp+480h+var_428]
0x18004437f  mov     [rsp+480h+var_430], rax
0x180044384  test    rax, rax
0x180044387  jnz     short loc_180044390
0x180044389  mov     ebx, 8007000Eh
0x18004438e  jmp     short loc_1800443DD
0x180044390  xor     edx, edx; dwFlags
0x180044392  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x180044396  mov     r9d, ebx; cbMultiByte
0x180044399  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x18004439e  mov     r8, rsi; lpMultiByteStr
0x1800443a1  lea     ecx, [rdx+3]; CodePage
0x1800443a4  call    cs:__imp_MultiByteToWideChar
0x1800443ab  nop     dword ptr [rax+rax+00h]
0x1800443b0  test    eax, eax
0x1800443b2  jz      loc_18004430A
0x1800443b8  mov     r8d, [rbp+380h+arg_20]; int
0x1800443bf  xor     ecx, ecx
0x1800443c1  mov     edx, eax
0x1800443c3  mov     rax, [rsp+480h+var_430]
0x1800443c8  mov     [rax+rdx*2], cx
0x1800443cc  lea     rcx, [rsp+480h+var_448]; this
0x1800443d1  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x1800443d6  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800443db  mov     ebx, eax
0x1800443dd  mov     rcx, rdi; hLibModule
0x1800443e0  call    cs:__imp_FreeLibrary
0x1800443e7  nop     dword ptr [rax+rax+00h]
0x1800443ec  lea     rcx, [rsp+480h+var_430]
0x1800443f1  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x1800443f6  lea     rcx, [rsp+480h+var_450]
0x1800443fb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180044400  mov     eax, ebx
0x180044402  mov     rcx, [rbp+380h+var_20]
0x180044409  xor     rcx, rsp; StackCookie
0x18004440c  call    __security_check_cookie
0x180044411  mov     rbx, [rsp+480h+arg_0]
0x180044419  add     rsp, 470h
0x180044420  pop     rdi
0x180044421  pop     rsi
0x180044422  pop     rbp
0x180044423  retn
```
