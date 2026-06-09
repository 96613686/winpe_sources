# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180007700`
- end: `0x1800078a8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800088f0`
- `0x180008b68`

## callees

- `0x180002d14`
- `0x180002d78`
- `0x18000325c`
- `0x180004114`
- `0x180004370`
- `0x18000758c`
- `0x180007700`
- `0x180032a30`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000774a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000774a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800077ac`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800077ac`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007775`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180007775`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180007793`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180007793`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007866`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180007866`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007831`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007831`

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
  unsigned int LastErrorHRESULT; // eax
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
      LastErrorHRESULT = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
    }
    else
    {
LABEL_4:
      LastErrorHRESULT = GetLastErrorHRESULT();
    }
    v9 = LastErrorHRESULT;
    goto LABEL_16;
  }
  v9 = GetLastErrorHRESULT();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x180007700  mov     [rsp+arg_0], rbx
0x180007705  push    rsi
0x180007706  push    rdi
0x180007707  push    r14
0x180007709  sub     rsp, 480h
0x180007710  mov     rax, cs:__security_cookie
0x180007717  xor     rax, rsp
0x18000771a  mov     [rsp+498h+var_28], rax
0x180007722  mov     r14, r9
0x180007725  mov     rdi, r8
0x180007728  mov     rax, rdx
0x18000772b  xor     ebx, ebx
0x18000772d  mov     [rsp+498h+var_450], rbx
0x180007732  mov     [rsp+498h+var_440], rcx
0x180007737  mov     [rsp+498h+var_448], rbx
0x18000773c  mov     [rsp+498h+var_438], rbx
0x180007741  xor     edx, edx; hFile
0x180007743  lea     r8d, [rbx+2]; dwFlags
0x180007747  mov     rcx, rax; lpLibFileName
0x18000774a  call    cs:__imp_LoadLibraryExW
0x180007750  mov     rsi, rax
0x180007753  mov     [rsp+498h+var_460], rax
0x180007758  test    rax, rax
0x18000775b  jnz     short loc_180007769
0x18000775d  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180007762  mov     ebx, eax
0x180007764  jmp     loc_18000786D
0x180007769  xor     r9d, r9d; wLanguage
0x18000776c  mov     r8, rdi; lpName
0x18000776f  mov     rdx, r14; lpType
0x180007772  mov     rcx, rsi; hModule
0x180007775  call    cs:__imp_FindResourceExW
0x18000777b  mov     rdi, rax
0x18000777e  test    rax, rax
0x180007781  jnz     short loc_18000778D
0x180007783  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180007788  jmp     loc_180007861
0x18000778d  mov     rdx, rdi; hResInfo
0x180007790  mov     rcx, rsi; hModule
0x180007793  call    cs:__imp_LoadResource
0x180007799  mov     r14, rax
0x18000779c  mov     [rsp+498h+var_458], rax
0x1800077a1  test    rax, rax
0x1800077a4  jz      short loc_180007783
0x1800077a6  mov     rdx, rdi; hResInfo
0x1800077a9  mov     rcx, rsi; hModule
0x1800077ac  call    cs:__imp_SizeofResource
0x1800077b2  mov     edi, eax
0x1800077b4  mov     [rsp+498h+var_468], eax
0x1800077b8  inc     eax
0x1800077ba  cmp     eax, edi
0x1800077bc  jnb     short loc_1800077C8
0x1800077be  mov     ebx, 8007000Eh
0x1800077c3  jmp     loc_18000786D
0x1800077c8  mov     ecx, eax
0x1800077ca  mov     edx, 2
0x1800077cf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800077d4  cmp     rax, 400h
0x1800077da  jbe     short loc_1800077F0
0x1800077dc  mov     rdx, rax
0x1800077df  lea     rcx, [rsp+498h+var_438]
0x1800077e4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800077e9  mov     rax, [rsp+498h+var_438]
0x1800077ee  jmp     short loc_1800077FA
0x1800077f0  lea     rax, [rsp+498h+var_430]
0x1800077f5  mov     [rsp+498h+var_438], rax
0x1800077fa  jmp     short loc_180007811
0x1800077fc  xor     ebx, ebx
0x1800077fe  mov     rsi, [rsp+498h+var_460]
0x180007803  mov     r14, [rsp+498h+var_458]
0x180007808  mov     edi, [rsp+498h+var_468]
0x18000780c  mov     rax, [rsp+498h+var_438]
0x180007811  test    rax, rax
0x180007814  jnz     short loc_18000781D
0x180007816  mov     ebx, 8007000Eh
0x18000781b  jmp     short loc_180007863
0x18000781d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180007821  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180007826  mov     r9d, edi; cbMultiByte
0x180007829  mov     r8, r14; lpMultiByteStr
0x18000782c  xor     edx, edx; dwFlags
0x18000782e  lea     ecx, [rdx+3]; CodePage
0x180007831  call    cs:__imp_MultiByteToWideChar
0x180007837  test    eax, eax
0x180007839  jz      loc_180007783
0x18000783f  mov     ecx, eax
0x180007841  mov     rax, [rsp+498h+var_438]
0x180007846  mov     [rax+rcx*2], bx
0x18000784a  mov     r8d, [rsp+498h+arg_20]; int
0x180007852  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180007857  lea     rcx, [rsp+498h+var_448]; this
0x18000785c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180007861  mov     ebx, eax
0x180007863  mov     rcx, rsi; hLibModule
0x180007866  call    cs:__imp_FreeLibrary
0x18000786c  nop
0x18000786d  lea     rcx, [rsp+498h+var_438]
0x180007872  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180007877  nop
0x180007878  lea     rcx, [rsp+498h+var_450]
0x18000787d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180007882  mov     eax, ebx
0x180007884  mov     rcx, [rsp+498h+var_28]
0x18000788c  xor     rcx, rsp; StackCookie
0x18000788f  call    __security_check_cookie
0x180007894  mov     rbx, [rsp+498h+arg_0]
0x18000789c  add     rsp, 480h
0x1800078a3  pop     r14
0x1800078a5  pop     rdi
0x1800078a6  pop     rsi
0x1800078a7  retn
```
