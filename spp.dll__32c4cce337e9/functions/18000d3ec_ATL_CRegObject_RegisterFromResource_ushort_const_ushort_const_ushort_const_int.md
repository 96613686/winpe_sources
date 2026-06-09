# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000d3ec`
- end: `0x18000d57c`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `400`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000fb2c`
- `0x18000fda4`

## callees

- `0x180002158`
- `0x180002274`
- `0x18000273c`
- `0x1800037c0`
- `0x180004528`
- `0x18000d27c`
- `0x18000d3ec`
- `0x180035bd0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000d53e`
- `KERNEL32!FreeLibrary` at `0x18000d53e`
- `KERNEL32!LoadLibraryExW` at `0x18000d446`
- `KERNEL32!LoadLibraryExW` at `0x18000d446`
- `KERNEL32!MultiByteToWideChar` at `0x18000d508`
- `KERNEL32!MultiByteToWideChar` at `0x18000d508`
- `KERNEL32!SizeofResource` at `0x18000d49e`
- `KERNEL32!SizeofResource` at `0x18000d49e`
- `KERNEL32!LoadResource` at `0x18000d48a`
- `KERNEL32!LoadResource` at `0x18000d48a`
- `KERNEL32!FindResourceExW` at `0x18000d46c`
- `KERNEL32!FindResourceExW` at `0x18000d46c`

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
0x18000d3ec  mov     [rsp-8+arg_0], rbx
0x18000d3f1  push    rbp
0x18000d3f2  push    rsi
0x18000d3f3  push    rdi
0x18000d3f4  lea     rbp, [rsp-370h]
0x18000d3fc  sub     rsp, 470h
0x18000d403  mov     rax, cs:__security_cookie
0x18000d40a  xor     rax, rsp
0x18000d40d  mov     [rbp+380h+var_20], rax
0x18000d414  mov     rax, rdx
0x18000d417  mov     [rsp+480h+var_440], rcx
0x18000d41c  xor     edx, edx; hFile
0x18000d41e  mov     [rsp+480h+var_450], 0
0x18000d427  mov     rbx, r8
0x18000d42a  mov     [rsp+480h+var_448], 0
0x18000d433  mov     rcx, rax; lpLibFileName
0x18000d436  mov     [rsp+480h+var_430], 0
0x18000d43f  mov     rsi, r9
0x18000d442  lea     r8d, [rdx+2]; dwFlags
0x18000d446  call    cs:__imp_LoadLibraryExW
0x18000d44c  mov     rdi, rax
0x18000d44f  test    rax, rax
0x18000d452  jnz     short loc_18000D460
0x18000d454  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000d459  mov     ebx, eax
0x18000d45b  jmp     loc_18000D544
0x18000d460  xor     r9d, r9d; wLanguage
0x18000d463  mov     r8, rbx; lpName
0x18000d466  mov     rdx, rsi; lpType
0x18000d469  mov     rcx, rdi; hModule
0x18000d46c  call    cs:__imp_FindResourceExW
0x18000d472  mov     rbx, rax
0x18000d475  test    rax, rax
0x18000d478  jnz     short loc_18000D484
0x18000d47a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000d47f  jmp     loc_18000D539
0x18000d484  mov     rdx, rbx; hResInfo
0x18000d487  mov     rcx, rdi; hModule
0x18000d48a  call    cs:__imp_LoadResource
0x18000d490  mov     rsi, rax
0x18000d493  test    rax, rax
0x18000d496  jz      short loc_18000D47A
0x18000d498  mov     rdx, rbx; hResInfo
0x18000d49b  mov     rcx, rdi; hModule
0x18000d49e  call    cs:__imp_SizeofResource
0x18000d4a4  mov     ebx, eax
0x18000d4a6  inc     eax
0x18000d4a8  cmp     eax, ebx
0x18000d4aa  jnb     short loc_18000D4B6
0x18000d4ac  mov     ebx, 8007000Eh
0x18000d4b1  jmp     loc_18000D544
0x18000d4b6  mov     ecx, eax
0x18000d4b8  mov     edx, 2
0x18000d4bd  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18000d4c2  cmp     rax, 400h
0x18000d4c8  jbe     short loc_18000D4DE
0x18000d4ca  mov     rdx, rax
0x18000d4cd  lea     rcx, [rsp+480h+var_430]
0x18000d4d2  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000d4d7  mov     rax, [rsp+480h+var_430]
0x18000d4dc  jmp     short loc_18000D4E8
0x18000d4de  lea     rax, [rsp+480h+var_428]
0x18000d4e3  mov     [rsp+480h+var_430], rax
0x18000d4e8  test    rax, rax
0x18000d4eb  jnz     short loc_18000D4F4
0x18000d4ed  mov     ebx, 8007000Eh
0x18000d4f2  jmp     short loc_18000D53B
0x18000d4f4  xor     edx, edx; dwFlags
0x18000d4f6  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x18000d4fa  mov     r9d, ebx; cbMultiByte
0x18000d4fd  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x18000d502  mov     r8, rsi; lpMultiByteStr
0x18000d505  lea     ecx, [rdx+3]; CodePage
0x18000d508  call    cs:__imp_MultiByteToWideChar
0x18000d50e  test    eax, eax
0x18000d510  jz      loc_18000D47A
0x18000d516  mov     r8d, [rbp+380h+arg_20]; int
0x18000d51d  xor     ecx, ecx
0x18000d51f  mov     edx, eax
0x18000d521  mov     rax, [rsp+480h+var_430]
0x18000d526  mov     [rax+rdx*2], cx
0x18000d52a  lea     rcx, [rsp+480h+var_448]; this
0x18000d52f  mov     rdx, [rsp+480h+var_430]; unsigned __int16 *
0x18000d534  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000d539  mov     ebx, eax
0x18000d53b  mov     rcx, rdi; hLibModule
0x18000d53e  call    cs:__imp_FreeLibrary
0x18000d544  lea     rcx, [rsp+480h+var_430]
0x18000d549  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18000d54e  lea     rcx, [rsp+480h+var_450]
0x18000d553  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000d558  mov     eax, ebx
0x18000d55a  mov     rcx, [rbp+380h+var_20]
0x18000d561  xor     rcx, rsp; StackCookie
0x18000d564  call    __security_check_cookie
0x18000d569  mov     rbx, [rsp+480h+arg_0]
0x18000d571  add     rsp, 470h
0x18000d578  pop     rdi
0x18000d579  pop     rsi
0x18000d57a  pop     rbp
0x18000d57b  retn
```
