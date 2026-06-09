# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x1800087c8`
- end: `0x1800089ad`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `485`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800063ec`
- `0x1800089b4`

## callees

- `0x180006b44`
- `0x180006b74`
- `0x180006ba4`
- `0x1800078c8`
- `0x18000862c`
- `0x1800087c8`
- `0x18002fda9`
- `0x18002ffd0`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008823`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000883f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180008823`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000883f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008885`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180008885`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000889e`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000889e`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008962`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180008962`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180008867`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x180008867`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008928`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180008928`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5)
{
  HMODULE Library; // rsi
  unsigned int Error; // ebx
  HRSRC ResourceW; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *Resource; // r14
  DWORD cchWideChar; // ebx
  DWORD v15; // eax
  int v16; // eax
  HMODULE v18; // [rsp+38h] [rbp-470h]
  _QWORD v19[2]; // [rsp+50h] [rbp-458h] BYREF
  LPWSTR lpWideCharStr; // [rsp+60h] [rbp-448h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-440h] BYREF

  v19[1] = this;
  v19[0] = 0;
  memset_0(&lpWideCharStr, 0, 0x408u);
  lpWideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 0x60u);
  v18 = Library;
  if ( !Library )
  {
    Library = LoadLibraryExW(a2, 0, 2u);
    v18 = Library;
    if ( !Library )
    {
      Error = ATL::AtlHresultFromLastError();
      goto LABEL_20;
    }
  }
  ResourceW = FindResourceW(Library, a3, a4);
  v11 = ResourceW;
  if ( !ResourceW )
    goto LABEL_5;
  Resource = (const CHAR *)LoadResource(Library, ResourceW);
  if ( !Resource )
    goto LABEL_5;
  cchWideChar = SizeofResource(Library, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 < cchWideChar )
    goto LABEL_8;
  try
  {
    if ( cchWideChar == -1 )
      goto LABEL_13;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
      ATL::AtlThrowImpl(-2147024362);
    if ( 2 * (unsigned __int64)v15 <= 0x400 )
LABEL_13:
      lpWideCharStr = (LPWSTR)v21;
    else
      ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&lpWideCharStr, 2LL * v15);
  }
  catch ( ... )
  {
    Library = v18;
  }
  if ( !lpWideCharStr )
  {
LABEL_8:
    Error = -2147024882;
    goto LABEL_18;
  }
  v16 = MultiByteToWideChar(3u, 0, Resource, cchWideChar, lpWideCharStr, cchWideChar);
  if ( v16 )
  {
    lpWideCharStr[v16] = 0;
    v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, lpWideCharStr, a5);
  }
  else
  {
LABEL_5:
    v12 = ATL::AtlHresultFromLastError();
  }
  Error = v12;
LABEL_18:
  if ( Library )
    FreeLibrary(Library);
LABEL_20:
  if ( lpWideCharStr != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap((void **)&lpWideCharStr);
  return Error;
}

```

## disassembly

```asm
0x1800087c8  push    rbx
0x1800087ca  push    rsi
0x1800087cb  push    rdi
0x1800087cc  push    r14
0x1800087ce  push    r15
0x1800087d0  sub     rsp, 480h
0x1800087d7  mov     rax, cs:__security_cookie
0x1800087de  xor     rax, rsp
0x1800087e1  mov     [rsp+4A8h+var_38], rax
0x1800087e9  mov     r15, r9
0x1800087ec  mov     r14, r8
0x1800087ef  mov     rbx, rdx
0x1800087f2  xor     edi, edi
0x1800087f4  mov     [rsp+4A8h+var_460], rdi
0x1800087f9  mov     [rsp+4A8h+var_450], rcx
0x1800087fe  mov     [rsp+4A8h+var_458], rdi
0x180008803  xor     edx, edx; Val
0x180008805  mov     r8d, 408h; Size
0x18000880b  lea     rcx, [rsp+4A8h+var_448]; void *
0x180008810  call    memset_0
0x180008815  mov     [rsp+4A8h+var_448], rdi
0x18000881a  xor     edx, edx; hFile
0x18000881c  lea     r8d, [rdi+60h]; dwFlags
0x180008820  mov     rcx, rbx; lpLibFileName
0x180008823  call    cs:__imp_LoadLibraryExW
0x180008829  mov     rsi, rax
0x18000882c  mov     [rsp+4A8h+var_470], rax
0x180008831  test    rax, rax
0x180008834  jnz     short loc_18000885E
0x180008836  xor     edx, edx; hFile
0x180008838  lea     r8d, [rdi+2]; dwFlags
0x18000883c  mov     rcx, rbx; lpLibFileName
0x18000883f  call    cs:__imp_LoadLibraryExW
0x180008845  mov     rsi, rax
0x180008848  mov     [rsp+4A8h+var_470], rax
0x18000884d  test    rax, rax
0x180008850  jnz     short loc_18000885E
0x180008852  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008857  mov     ebx, eax
0x180008859  jmp     loc_180008969
0x18000885e  mov     r8, r15; lpType
0x180008861  mov     rdx, r14; lpName
0x180008864  mov     rcx, rsi; hModule
0x180008867  call    cs:__imp_FindResourceW
0x18000886d  mov     rbx, rax
0x180008870  test    rax, rax
0x180008873  jnz     short loc_18000887F
0x180008875  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000887a  jmp     loc_180008958
0x18000887f  mov     rdx, rbx; hResInfo
0x180008882  mov     rcx, rsi; hModule
0x180008885  call    cs:__imp_LoadResource
0x18000888b  mov     r14, rax
0x18000888e  mov     [rsp+4A8h+var_468], rax
0x180008893  test    rax, rax
0x180008896  jz      short loc_180008875
0x180008898  mov     rdx, rbx; hResInfo
0x18000889b  mov     rcx, rsi; hModule
0x18000889e  call    cs:__imp_SizeofResource
0x1800088a4  mov     ebx, eax
0x1800088a6  mov     [rsp+4A8h+var_478], eax
0x1800088aa  inc     eax
0x1800088ac  cmp     eax, ebx
0x1800088ae  jnb     short loc_1800088BA
0x1800088b0  mov     ebx, 8007000Eh
0x1800088b5  jmp     loc_18000895A
0x1800088ba  test    eax, eax
0x1800088bc  jz      short loc_1800088EC
0x1800088be  mov     ecx, eax
0x1800088c0  xor     edx, edx
0x1800088c2  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800088c6  div     rcx
0x1800088c9  cmp     rax, 2
0x1800088cd  jb      loc_1800089A1
0x1800088d3  lea     rdx, [rcx+rcx]
0x1800088d7  cmp     rdx, 400h
0x1800088de  jbe     short loc_1800088EC
0x1800088e0  lea     rcx, [rsp+4A8h+var_448]
0x1800088e5  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800088ea  jmp     short loc_1800088F6
0x1800088ec  lea     rax, [rsp+4A8h+var_440]
0x1800088f1  mov     [rsp+4A8h+var_448], rax
0x1800088f6  jmp     short loc_180008908
0x1800088f8  xor     edi, edi
0x1800088fa  mov     rsi, [rsp+4A8h+var_470]
0x1800088ff  mov     r14, [rsp+4A8h+var_468]
0x180008904  mov     ebx, [rsp+4A8h+var_478]
0x180008908  cmp     [rsp+4A8h+var_448], rdi
0x18000890d  jz      short loc_1800088B0
0x18000890f  mov     rax, [rsp+4A8h+var_448]
0x180008914  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x180008918  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18000891d  mov     r9d, ebx; cbMultiByte
0x180008920  mov     r8, r14; lpMultiByteStr
0x180008923  xor     edx, edx; dwFlags
0x180008925  lea     ecx, [rdx+3]; CodePage
0x180008928  call    cs:__imp_MultiByteToWideChar
0x18000892e  test    eax, eax
0x180008930  jz      loc_180008875
0x180008936  mov     ecx, eax
0x180008938  mov     rax, [rsp+4A8h+var_448]
0x18000893d  mov     [rax+rcx*2], di
0x180008941  mov     r8d, [rsp+4A8h+arg_20]; int
0x180008949  mov     rdx, [rsp+4A8h+var_448]; wchar_t *
0x18000894e  lea     rcx, [rsp+4A8h+var_458]; this
0x180008953  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x180008958  mov     ebx, eax
0x18000895a  test    rsi, rsi
0x18000895d  jz      short loc_180008969
0x18000895f  mov     rcx, rsi; hLibModule
0x180008962  call    cs:__imp_FreeLibrary
0x180008968  nop
0x180008969  lea     rax, [rsp+4A8h+var_440]
0x18000896e  cmp     [rsp+4A8h+var_448], rax
0x180008973  jz      short loc_180008980
0x180008975  lea     rcx, [rsp+4A8h+var_448]
0x18000897a  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18000897f  nop
0x180008980  mov     eax, ebx
0x180008982  mov     rcx, [rsp+4A8h+var_38]
0x18000898a  xor     rcx, rsp; StackCookie
0x18000898d  call    __security_check_cookie
0x180008992  add     rsp, 480h
0x180008999  pop     r15
0x18000899b  pop     r14
0x18000899d  pop     rdi
0x18000899e  pop     rsi
0x18000899f  pop     rbx
0x1800089a0  retn
0x1800089a1  mov     ecx, 80070216h; int
0x1800089a6  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
