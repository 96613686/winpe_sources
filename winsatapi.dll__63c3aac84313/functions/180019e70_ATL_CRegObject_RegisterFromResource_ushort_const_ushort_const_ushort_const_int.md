# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180019e70`
- end: `0x18001a023`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `435`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001ae4c`
- `0x18001b0cc`

## callees

- `0x1800151ec`
- `0x180015290`
- `0x1800157e0`
- `0x180016798`
- `0x180016a68`
- `0x180019cfc`
- `0x180019e70`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019f0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180019f0e`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019ec5`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180019ec5`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019ef0`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180019ef0`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019fe1`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180019fe1`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019f27`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180019f27`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019fac`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180019fac`

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
  HMODULE v19; // [rsp+38h] [rbp-470h]
  _QWORD *v20; // [rsp+48h] [rbp-460h] BYREF
  _QWORD v21[4]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR v22; // [rsp+70h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+78h] [rbp-430h] BYREF

  v21[2] = -2;
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
0x180019e70  mov     rax, rsp
0x180019e73  push    rsi
0x180019e74  push    rdi
0x180019e75  push    r14
0x180019e77  sub     rsp, 490h
0x180019e7e  mov     [rsp+4A8h+var_448], 0FFFFFFFFFFFFFFFEh
0x180019e87  mov     [rax+8], rbx
0x180019e8b  mov     rax, cs:__security_cookie
0x180019e92  xor     rax, rsp
0x180019e95  mov     [rsp+4A8h+var_28], rax
0x180019e9d  mov     r14, r9
0x180019ea0  mov     rdi, r8
0x180019ea3  mov     rax, rdx
0x180019ea6  xor     ebx, ebx
0x180019ea8  mov     [rsp+4A8h+var_460], rbx
0x180019ead  mov     [rsp+4A8h+var_450], rcx
0x180019eb2  mov     [rsp+4A8h+var_458], rbx
0x180019eb7  mov     [rsp+4A8h+var_438], rbx
0x180019ebc  xor     edx, edx; hFile
0x180019ebe  lea     r8d, [rbx+2]; dwFlags
0x180019ec2  mov     rcx, rax; lpLibFileName
0x180019ec5  call    cs:__imp_LoadLibraryExW
0x180019ecb  mov     rsi, rax
0x180019ece  mov     [rsp+4A8h+var_470], rax
0x180019ed3  test    rax, rax
0x180019ed6  jnz     short loc_180019EE4
0x180019ed8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019edd  mov     ebx, eax
0x180019edf  jmp     loc_180019FE8
0x180019ee4  xor     r9d, r9d; wLanguage
0x180019ee7  mov     r8, rdi; lpName
0x180019eea  mov     rdx, r14; lpType
0x180019eed  mov     rcx, rsi; hModule
0x180019ef0  call    cs:__imp_FindResourceExW
0x180019ef6  mov     rdi, rax
0x180019ef9  test    rax, rax
0x180019efc  jnz     short loc_180019F08
0x180019efe  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180019f03  jmp     loc_180019FDC
0x180019f08  mov     rdx, rdi; hResInfo
0x180019f0b  mov     rcx, rsi; hModule
0x180019f0e  call    cs:__imp_LoadResource
0x180019f14  mov     r14, rax
0x180019f17  mov     [rsp+4A8h+var_468], rax
0x180019f1c  test    rax, rax
0x180019f1f  jz      short loc_180019EFE
0x180019f21  mov     rdx, rdi; hResInfo
0x180019f24  mov     rcx, rsi; hModule
0x180019f27  call    cs:__imp_SizeofResource
0x180019f2d  mov     edi, eax
0x180019f2f  mov     [rsp+4A8h+var_478], eax
0x180019f33  inc     eax
0x180019f35  cmp     eax, edi
0x180019f37  jnb     short loc_180019F43
0x180019f39  mov     ebx, 8007000Eh
0x180019f3e  jmp     loc_180019FE8
0x180019f43  mov     ecx, eax
0x180019f45  mov     edx, 2
0x180019f4a  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180019f4f  cmp     rax, 400h
0x180019f55  jbe     short loc_180019F6B
0x180019f57  mov     rdx, rax
0x180019f5a  lea     rcx, [rsp+4A8h+var_438]
0x180019f5f  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180019f64  mov     rax, [rsp+4A8h+var_438]
0x180019f69  jmp     short loc_180019F75
0x180019f6b  lea     rax, [rsp+4A8h+var_430]
0x180019f70  mov     [rsp+4A8h+var_438], rax
0x180019f75  jmp     short loc_180019F8C
0x180019f77  xor     ebx, ebx
0x180019f79  mov     rsi, [rsp+4A8h+var_470]
0x180019f7e  mov     r14, [rsp+4A8h+var_468]
0x180019f83  mov     edi, [rsp+4A8h+var_478]
0x180019f87  mov     rax, [rsp+4A8h+var_438]
0x180019f8c  test    rax, rax
0x180019f8f  jnz     short loc_180019F98
0x180019f91  mov     ebx, 8007000Eh
0x180019f96  jmp     short loc_180019FDE
0x180019f98  mov     [rsp+4A8h+cchWideChar], edi; cchWideChar
0x180019f9c  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x180019fa1  mov     r9d, edi; cbMultiByte
0x180019fa4  mov     r8, r14; lpMultiByteStr
0x180019fa7  xor     edx, edx; dwFlags
0x180019fa9  lea     ecx, [rdx+3]; CodePage
0x180019fac  call    cs:__imp_MultiByteToWideChar
0x180019fb2  test    eax, eax
0x180019fb4  jz      loc_180019EFE
0x180019fba  mov     ecx, eax
0x180019fbc  mov     rax, [rsp+4A8h+var_438]
0x180019fc1  mov     [rax+rcx*2], bx
0x180019fc5  mov     r8d, [rsp+4A8h+arg_20]; int
0x180019fcd  mov     rdx, [rsp+4A8h+var_438]; unsigned __int16 *
0x180019fd2  lea     rcx, [rsp+4A8h+var_458]; this
0x180019fd7  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180019fdc  mov     ebx, eax
0x180019fde  mov     rcx, rsi; hLibModule
0x180019fe1  call    cs:__imp_FreeLibrary
0x180019fe7  nop
0x180019fe8  lea     rcx, [rsp+4A8h+var_438]
0x180019fed  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180019ff2  nop
0x180019ff3  lea     rcx, [rsp+4A8h+var_460]
0x180019ff8  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180019ffd  mov     eax, ebx
0x180019fff  mov     rcx, [rsp+4A8h+var_28]
0x18001a007  xor     rcx, rsp; StackCookie
0x18001a00a  call    __security_check_cookie
0x18001a00f  mov     rbx, [rsp+4A8h+arg_0]
0x18001a017  add     rsp, 490h
0x18001a01e  pop     r14
0x18001a020  pop     rdi
0x18001a021  pop     rsi
0x18001a022  retn
```
