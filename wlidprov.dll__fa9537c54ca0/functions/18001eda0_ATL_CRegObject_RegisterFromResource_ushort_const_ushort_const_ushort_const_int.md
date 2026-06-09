# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18001eda0`
- end: `0x18001ef46`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `422`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001fa60`

## callees

- `0x18001a0d0`
- `0x18001cb34`
- `0x18001cc14`
- `0x18001cdf0`
- `0x18001d8f8`
- `0x18001da08`
- `0x18001ec2c`
- `0x18001eda0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ede7`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ede7`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ef04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ef04`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001ee31`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001ee31`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001ee4a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001ee4a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ee13`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ee13`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001eecf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001eecf`

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
  unsigned int Error; // eax
  const CHAR *v12; // r14
  DWORD cchWideChar; // esi
  unsigned __int64 v14; // rax
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
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
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
0x18001eda0  mov     [rsp+arg_0], rbx
0x18001eda5  push    rsi
0x18001eda6  push    rdi
0x18001eda7  push    r14
0x18001eda9  sub     rsp, 480h
0x18001edb0  mov     rax, cs:__security_cookie
0x18001edb7  xor     rax, rsp
0x18001edba  mov     [rsp+498h+var_28], rax
0x18001edc2  mov     rsi, r9
0x18001edc5  mov     rax, rdx
0x18001edc8  xor     ebx, ebx
0x18001edca  mov     [rsp+498h+var_450], rbx
0x18001edcf  mov     [rsp+498h+var_440], rcx
0x18001edd4  mov     [rsp+498h+var_448], rbx
0x18001edd9  mov     [rsp+498h+var_438], rbx
0x18001edde  xor     edx, edx; hFile
0x18001ede0  lea     r8d, [rbx+2]; dwFlags
0x18001ede4  mov     rcx, rax; lpLibFileName
0x18001ede7  call    cs:__imp_LoadLibraryExW
0x18001eded  mov     rdi, rax
0x18001edf0  mov     [rsp+498h+var_460], rax
0x18001edf5  test    rax, rax
0x18001edf8  jnz     short loc_18001EE06
0x18001edfa  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001edff  mov     ebx, eax
0x18001ee01  jmp     loc_18001EF0B
0x18001ee06  xor     r9d, r9d; wLanguage
0x18001ee09  lea     r8d, [r9+65h]; lpName
0x18001ee0d  mov     rdx, rsi; lpType
0x18001ee10  mov     rcx, rdi; hModule
0x18001ee13  call    cs:__imp_FindResourceExW
0x18001ee19  mov     rsi, rax
0x18001ee1c  test    rax, rax
0x18001ee1f  jnz     short loc_18001EE2B
0x18001ee21  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ee26  jmp     loc_18001EEFF
0x18001ee2b  mov     rdx, rsi; hResInfo
0x18001ee2e  mov     rcx, rdi; hModule
0x18001ee31  call    cs:__imp_LoadResource
0x18001ee37  mov     r14, rax
0x18001ee3a  mov     [rsp+498h+var_458], rax
0x18001ee3f  test    rax, rax
0x18001ee42  jz      short loc_18001EE21
0x18001ee44  mov     rdx, rsi; hResInfo
0x18001ee47  mov     rcx, rdi; hModule
0x18001ee4a  call    cs:__imp_SizeofResource
0x18001ee50  mov     esi, eax
0x18001ee52  mov     [rsp+498h+var_468], eax
0x18001ee56  inc     eax
0x18001ee58  cmp     eax, esi
0x18001ee5a  jnb     short loc_18001EE66
0x18001ee5c  mov     ebx, 8007000Eh
0x18001ee61  jmp     loc_18001EF0B
0x18001ee66  mov     ecx, eax
0x18001ee68  mov     edx, 2
0x18001ee6d  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001ee72  cmp     rax, 400h
0x18001ee78  jbe     short loc_18001EE8E
0x18001ee7a  mov     rdx, rax
0x18001ee7d  lea     rcx, [rsp+498h+var_438]
0x18001ee82  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001ee87  mov     rax, [rsp+498h+var_438]
0x18001ee8c  jmp     short loc_18001EE98
0x18001ee8e  lea     rax, [rsp+498h+var_430]
0x18001ee93  mov     [rsp+498h+var_438], rax
0x18001ee98  jmp     short loc_18001EEAF
0x18001ee9a  xor     ebx, ebx
0x18001ee9c  mov     rdi, [rsp+498h+var_460]
0x18001eea1  mov     r14, [rsp+498h+var_458]
0x18001eea6  mov     esi, [rsp+498h+var_468]
0x18001eeaa  mov     rax, [rsp+498h+var_438]
0x18001eeaf  test    rax, rax
0x18001eeb2  jnz     short loc_18001EEBB
0x18001eeb4  mov     ebx, 8007000Eh
0x18001eeb9  jmp     short loc_18001EF01
0x18001eebb  mov     [rsp+498h+cchWideChar], esi; cchWideChar
0x18001eebf  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001eec4  mov     r9d, esi; cbMultiByte
0x18001eec7  mov     r8, r14; lpMultiByteStr
0x18001eeca  xor     edx, edx; dwFlags
0x18001eecc  lea     ecx, [rdx+3]; CodePage
0x18001eecf  call    cs:__imp_MultiByteToWideChar
0x18001eed5  test    eax, eax
0x18001eed7  jz      loc_18001EE21
0x18001eedd  mov     ecx, eax
0x18001eedf  mov     rax, [rsp+498h+var_438]
0x18001eee4  mov     [rax+rcx*2], bx
0x18001eee8  mov     r8d, [rsp+498h+arg_20]; int
0x18001eef0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18001eef5  lea     rcx, [rsp+498h+var_448]; this
0x18001eefa  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001eeff  mov     ebx, eax
0x18001ef01  mov     rcx, rdi; hLibModule
0x18001ef04  call    cs:__imp_FreeLibrary
0x18001ef0a  nop
0x18001ef0b  lea     rcx, [rsp+498h+var_438]
0x18001ef10  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001ef15  nop
0x18001ef16  lea     rcx, [rsp+498h+var_450]
0x18001ef1b  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ef20  mov     eax, ebx
0x18001ef22  mov     rcx, [rsp+498h+var_28]
0x18001ef2a  xor     rcx, rsp; StackCookie
0x18001ef2d  call    __security_check_cookie
0x18001ef32  mov     rbx, [rsp+498h+arg_0]
0x18001ef3a  add     rsp, 480h
0x18001ef41  pop     r14
0x18001ef43  pop     rdi
0x18001ef44  pop     rsi
0x18001ef45  retn
```
