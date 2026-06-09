# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18001e190`
- end: `0x18001e338`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001f1cc`
- `0x18001f444`

## callees

- `0x180005cc0`
- `0x180010680`
- `0x18001a1e4`
- `0x18001a324`
- `0x18001a6d0`
- `0x18001b644`
- `0x18001e01c`
- `0x18001e190`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001e223`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001e223`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001e205`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001e205`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001e23c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001e23c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e1da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001e1da`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e2f6`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001e2f6`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e2c1`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001e2c1`

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
  _QWORD *v20; // [rsp+48h] [rbp-450h] BYREF
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
      Error = ResultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ResultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x18001e190  mov     [rsp+arg_0], rbx
0x18001e195  push    rsi
0x18001e196  push    rdi
0x18001e197  push    r14
0x18001e199  sub     rsp, 480h
0x18001e1a0  mov     rax, cs:__security_cookie
0x18001e1a7  xor     rax, rsp
0x18001e1aa  mov     [rsp+498h+var_28], rax
0x18001e1b2  mov     r14, r9
0x18001e1b5  mov     rdi, r8
0x18001e1b8  mov     rax, rdx
0x18001e1bb  xor     ebx, ebx
0x18001e1bd  mov     [rsp+498h+var_450], rbx
0x18001e1c2  mov     [rsp+498h+var_440], rcx
0x18001e1c7  mov     [rsp+498h+var_448], rbx
0x18001e1cc  mov     [rsp+498h+var_438], rbx
0x18001e1d1  xor     edx, edx; hFile
0x18001e1d3  lea     r8d, [rbx+2]; dwFlags
0x18001e1d7  mov     rcx, rax; lpLibFileName
0x18001e1da  call    cs:__imp_LoadLibraryExW
0x18001e1e0  mov     rsi, rax
0x18001e1e3  mov     [rsp+498h+var_460], rax
0x18001e1e8  test    rax, rax
0x18001e1eb  jnz     short loc_18001E1F9
0x18001e1ed  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001e1f2  mov     ebx, eax
0x18001e1f4  jmp     loc_18001E2FD
0x18001e1f9  xor     r9d, r9d; wLanguage
0x18001e1fc  mov     r8, rdi; lpName
0x18001e1ff  mov     rdx, r14; lpType
0x18001e202  mov     rcx, rsi; hModule
0x18001e205  call    cs:__imp_FindResourceExW
0x18001e20b  mov     rdi, rax
0x18001e20e  test    rax, rax
0x18001e211  jnz     short loc_18001E21D
0x18001e213  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001e218  jmp     loc_18001E2F1
0x18001e21d  mov     rdx, rdi; hResInfo
0x18001e220  mov     rcx, rsi; hModule
0x18001e223  call    cs:__imp_LoadResource
0x18001e229  mov     r14, rax
0x18001e22c  mov     [rsp+498h+var_458], rax
0x18001e231  test    rax, rax
0x18001e234  jz      short loc_18001E213
0x18001e236  mov     rdx, rdi; hResInfo
0x18001e239  mov     rcx, rsi; hModule
0x18001e23c  call    cs:__imp_SizeofResource
0x18001e242  mov     edi, eax
0x18001e244  mov     [rsp+498h+var_468], eax
0x18001e248  inc     eax
0x18001e24a  cmp     eax, edi
0x18001e24c  jnb     short loc_18001E258
0x18001e24e  mov     ebx, 8007000Eh
0x18001e253  jmp     loc_18001E2FD
0x18001e258  mov     ecx, eax
0x18001e25a  mov     edx, 2
0x18001e25f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001e264  cmp     rax, 400h
0x18001e26a  jbe     short loc_18001E280
0x18001e26c  mov     rdx, rax
0x18001e26f  lea     rcx, [rsp+498h+var_438]
0x18001e274  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001e279  mov     rax, [rsp+498h+var_438]
0x18001e27e  jmp     short loc_18001E28A
0x18001e280  lea     rax, [rsp+498h+var_430]
0x18001e285  mov     [rsp+498h+var_438], rax
0x18001e28a  jmp     short loc_18001E2A1
0x18001e28c  xor     ebx, ebx
0x18001e28e  mov     rsi, [rsp+498h+var_460]
0x18001e293  mov     r14, [rsp+498h+var_458]
0x18001e298  mov     edi, [rsp+498h+var_468]
0x18001e29c  mov     rax, [rsp+498h+var_438]
0x18001e2a1  test    rax, rax
0x18001e2a4  jnz     short loc_18001E2AD
0x18001e2a6  mov     ebx, 8007000Eh
0x18001e2ab  jmp     short loc_18001E2F3
0x18001e2ad  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18001e2b1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001e2b6  mov     r9d, edi; cbMultiByte
0x18001e2b9  mov     r8, r14; lpMultiByteStr
0x18001e2bc  xor     edx, edx; dwFlags
0x18001e2be  lea     ecx, [rdx+3]; CodePage
0x18001e2c1  call    cs:__imp_MultiByteToWideChar
0x18001e2c7  test    eax, eax
0x18001e2c9  jz      loc_18001E213
0x18001e2cf  mov     ecx, eax
0x18001e2d1  mov     rax, [rsp+498h+var_438]
0x18001e2d6  mov     [rax+rcx*2], bx
0x18001e2da  mov     r8d, [rsp+498h+arg_20]; int
0x18001e2e2  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18001e2e7  lea     rcx, [rsp+498h+var_448]; this
0x18001e2ec  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001e2f1  mov     ebx, eax
0x18001e2f3  mov     rcx, rsi; hLibModule
0x18001e2f6  call    cs:__imp_FreeLibrary
0x18001e2fc  nop
0x18001e2fd  lea     rcx, [rsp+498h+var_438]
0x18001e302  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001e307  nop
0x18001e308  lea     rcx, [rsp+498h+var_450]
0x18001e30d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001e312  mov     eax, ebx
0x18001e314  mov     rcx, [rsp+498h+var_28]
0x18001e31c  xor     rcx, rsp; StackCookie
0x18001e31f  call    __security_check_cookie
0x18001e324  mov     rbx, [rsp+498h+arg_0]
0x18001e32c  add     rsp, 480h
0x18001e333  pop     r14
0x18001e335  pop     rdi
0x18001e336  pop     rsi
0x18001e337  retn
```
