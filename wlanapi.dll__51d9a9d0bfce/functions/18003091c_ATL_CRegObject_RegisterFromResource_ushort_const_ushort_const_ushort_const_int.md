# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18003091c`
- end: `0x180030ac4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18003142c`
- `0x1800316a4`

## callees

- `0x180019a20`
- `0x18002ef64`
- `0x18002f054`
- `0x18002f0f8`
- `0x18002f9a8`
- `0x18002fb5c`
- `0x1800307ac`
- `0x18003091c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030966`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180030966`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800309af`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800309af`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180030991`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180030991`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030a82`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180030a82`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800309c8`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800309c8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030a4d`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180030a4d`

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
0x18003091c  mov     [rsp+arg_0], rbx
0x180030921  push    rsi
0x180030922  push    rdi
0x180030923  push    r14
0x180030925  sub     rsp, 480h
0x18003092c  mov     rax, cs:__security_cookie
0x180030933  xor     rax, rsp
0x180030936  mov     [rsp+498h+var_28], rax
0x18003093e  mov     r14, r9
0x180030941  mov     rdi, r8
0x180030944  mov     rax, rdx
0x180030947  xor     ebx, ebx
0x180030949  mov     [rsp+498h+var_450], rbx
0x18003094e  mov     [rsp+498h+var_440], rcx
0x180030953  mov     [rsp+498h+var_448], rbx
0x180030958  mov     [rsp+498h+var_438], rbx
0x18003095d  xor     edx, edx; hFile
0x18003095f  lea     r8d, [rbx+2]; dwFlags
0x180030963  mov     rcx, rax; lpLibFileName
0x180030966  call    cs:__imp_LoadLibraryExW
0x18003096c  mov     rsi, rax
0x18003096f  mov     [rsp+498h+var_460], rax
0x180030974  test    rax, rax
0x180030977  jnz     short loc_180030985
0x180030979  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18003097e  mov     ebx, eax
0x180030980  jmp     loc_180030A89
0x180030985  xor     r9d, r9d; wLanguage
0x180030988  mov     r8, rdi; lpName
0x18003098b  mov     rdx, r14; lpType
0x18003098e  mov     rcx, rsi; hModule
0x180030991  call    cs:__imp_FindResourceExW
0x180030997  mov     rdi, rax
0x18003099a  test    rax, rax
0x18003099d  jnz     short loc_1800309A9
0x18003099f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800309a4  jmp     loc_180030A7D
0x1800309a9  mov     rdx, rdi; hResInfo
0x1800309ac  mov     rcx, rsi; hModule
0x1800309af  call    cs:__imp_LoadResource
0x1800309b5  mov     r14, rax
0x1800309b8  mov     [rsp+498h+var_458], rax
0x1800309bd  test    rax, rax
0x1800309c0  jz      short loc_18003099F
0x1800309c2  mov     rdx, rdi; hResInfo
0x1800309c5  mov     rcx, rsi; hModule
0x1800309c8  call    cs:__imp_SizeofResource
0x1800309ce  mov     edi, eax
0x1800309d0  mov     [rsp+498h+var_468], eax
0x1800309d4  inc     eax
0x1800309d6  cmp     eax, edi
0x1800309d8  jnb     short loc_1800309E4
0x1800309da  mov     ebx, 8007000Eh
0x1800309df  jmp     loc_180030A89
0x1800309e4  mov     ecx, eax
0x1800309e6  mov     edx, 2
0x1800309eb  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800309f0  cmp     rax, 400h
0x1800309f6  jbe     short loc_180030A0C
0x1800309f8  mov     rdx, rax
0x1800309fb  lea     rcx, [rsp+498h+var_438]
0x180030a00  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180030a05  mov     rax, [rsp+498h+var_438]
0x180030a0a  jmp     short loc_180030A16
0x180030a0c  lea     rax, [rsp+498h+var_430]
0x180030a11  mov     [rsp+498h+var_438], rax
0x180030a16  jmp     short loc_180030A2D
0x180030a18  xor     ebx, ebx
0x180030a1a  mov     rsi, [rsp+498h+var_460]
0x180030a1f  mov     r14, [rsp+498h+var_458]
0x180030a24  mov     edi, [rsp+498h+var_468]
0x180030a28  mov     rax, [rsp+498h+var_438]
0x180030a2d  test    rax, rax
0x180030a30  jnz     short loc_180030A39
0x180030a32  mov     ebx, 8007000Eh
0x180030a37  jmp     short loc_180030A7F
0x180030a39  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180030a3d  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180030a42  mov     r9d, edi; cbMultiByte
0x180030a45  mov     r8, r14; lpMultiByteStr
0x180030a48  xor     edx, edx; dwFlags
0x180030a4a  lea     ecx, [rdx+3]; CodePage
0x180030a4d  call    cs:__imp_MultiByteToWideChar
0x180030a53  test    eax, eax
0x180030a55  jz      loc_18003099F
0x180030a5b  mov     ecx, eax
0x180030a5d  mov     rax, [rsp+498h+var_438]
0x180030a62  mov     [rax+rcx*2], bx
0x180030a66  mov     r8d, [rsp+498h+arg_20]; int
0x180030a6e  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180030a73  lea     rcx, [rsp+498h+var_448]; this
0x180030a78  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180030a7d  mov     ebx, eax
0x180030a7f  mov     rcx, rsi; hLibModule
0x180030a82  call    cs:__imp_FreeLibrary
0x180030a88  nop
0x180030a89  lea     rcx, [rsp+498h+var_438]
0x180030a8e  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180030a93  nop
0x180030a94  lea     rcx, [rsp+498h+var_450]
0x180030a99  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180030a9e  mov     eax, ebx
0x180030aa0  mov     rcx, [rsp+498h+var_28]
0x180030aa8  xor     rcx, rsp; StackCookie
0x180030aab  call    __security_check_cookie
0x180030ab0  mov     rbx, [rsp+498h+arg_0]
0x180030ab8  add     rsp, 480h
0x180030abf  pop     r14
0x180030ac1  pop     rdi
0x180030ac2  pop     rsi
0x180030ac3  retn
```
