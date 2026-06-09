# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x180012508`
- end: `0x1800126e4`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(ATL::CRegObject *this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18001325c`
- `0x1800134f8`

## callees

- `0x1800020e0`
- `0x1800109ec`
- `0x180010be8`
- `0x180011478`
- `0x180011a14`
- `0x180012378`
- `0x180012508`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001265f`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001265f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001257d`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001257d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800125b4`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800125b4`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001259b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001259b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012694`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180012694`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012552`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180012552`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const wchar_t *a2,
        const wchar_t *a3,
        const wchar_t *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int v12; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  _QWORD v20[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v21; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v22[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20[2] = 0;
  v20[1] = this;
  v20[0] = 0;
  v21 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v21 != (LPWSTR)v22 )
      ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v21);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  v15 = cchWideChar + 1;
  if ( cchWideChar + 1 >= cchWideChar )
  {
    try
    {
      if ( cchWideChar == -1 )
        goto LABEL_14;
      if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
        ATL::AtlThrowImpl(-2147024809);
      if ( 2 * (unsigned __int64)v15 <= 0x400 )
      {
LABEL_14:
        lpWideCharStr = (WCHAR *)v22;
        v21 = (LPWSTR)v22;
      }
      else
      {
        ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(&v21);
        lpWideCharStr = v21;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v21;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v8);
      goto LABEL_21;
    }
    v18 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v18 )
    {
      v21[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180012508  mov     [rsp+arg_0], rbx
0x18001250d  push    rsi
0x18001250e  push    rdi
0x18001250f  push    r14
0x180012511  sub     rsp, 480h
0x180012518  mov     rax, cs:__security_cookie
0x18001251f  xor     rax, rsp
0x180012522  mov     [rsp+498h+var_28], rax
0x18001252a  mov     r14, r9
0x18001252d  mov     rdi, r8
0x180012530  mov     rax, rdx
0x180012533  xor     ebx, ebx
0x180012535  mov     [rsp+498h+var_440], rbx
0x18001253a  mov     [rsp+498h+var_448], rcx
0x18001253f  mov     [rsp+498h+var_450], rbx
0x180012544  mov     [rsp+498h+var_438], rbx
0x180012549  xor     edx, edx; hFile
0x18001254b  lea     r8d, [rbx+2]; dwFlags
0x18001254f  mov     rcx, rax; lpLibFileName
0x180012552  call    cs:__imp_LoadLibraryExW
0x180012558  mov     rsi, rax
0x18001255b  mov     [rsp+498h+var_460], rax
0x180012560  test    rax, rax
0x180012563  jnz     short loc_180012571
0x180012565  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001256a  mov     ebx, eax
0x18001256c  jmp     loc_18001269B
0x180012571  xor     r9d, r9d; wLanguage
0x180012574  mov     r8, rdi; lpName
0x180012577  mov     rdx, r14; lpType
0x18001257a  mov     rcx, rsi; hModule
0x18001257d  call    cs:__imp_FindResourceExW
0x180012583  mov     rdi, rax
0x180012586  test    rax, rax
0x180012589  jnz     short loc_180012595
0x18001258b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180012590  jmp     loc_18001268F
0x180012595  mov     rdx, rdi; hResInfo
0x180012598  mov     rcx, rsi; hModule
0x18001259b  call    cs:__imp_LoadResource
0x1800125a1  mov     r14, rax
0x1800125a4  mov     [rsp+498h+var_458], rax
0x1800125a9  test    rax, rax
0x1800125ac  jz      short loc_18001258B
0x1800125ae  mov     rdx, rdi; hResInfo
0x1800125b1  mov     rcx, rsi; hModule
0x1800125b4  call    cs:__imp_SizeofResource
0x1800125ba  mov     edi, eax
0x1800125bc  mov     [rsp+498h+var_468], eax
0x1800125c0  inc     eax
0x1800125c2  cmp     eax, edi
0x1800125c4  jnb     short loc_1800125E7
0x1800125c6  lea     rax, [rsp+498h+var_430]
0x1800125cb  cmp     [rsp+498h+var_438], rax
0x1800125d0  jz      short loc_1800125DD
0x1800125d2  lea     rcx, [rsp+498h+var_438]
0x1800125d7  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x1800125dc  nop
0x1800125dd  mov     eax, 8007000Eh
0x1800125e2  jmp     loc_1800126B4
0x1800125e7  test    eax, eax
0x1800125e9  jz      short loc_18001261E
0x1800125eb  mov     ecx, eax
0x1800125ed  xor     edx, edx
0x1800125ef  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800125f3  div     rcx
0x1800125f6  cmp     rax, 2
0x1800125fa  jb      loc_1800126D8
0x180012600  lea     rdx, [rcx+rcx]
0x180012604  cmp     rdx, 400h
0x18001260b  jbe     short loc_18001261E
0x18001260d  lea     rcx, [rsp+498h+var_438]
0x180012612  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180012617  mov     rax, [rsp+498h+var_438]
0x18001261c  jmp     short loc_180012628
0x18001261e  lea     rax, [rsp+498h+var_430]
0x180012623  mov     [rsp+498h+var_438], rax
0x180012628  jmp     short loc_18001263F
0x18001262a  xor     ebx, ebx
0x18001262c  mov     rsi, [rsp+498h+var_460]
0x180012631  mov     r14, [rsp+498h+var_458]
0x180012636  mov     edi, [rsp+498h+var_468]
0x18001263a  mov     rax, [rsp+498h+var_438]
0x18001263f  test    rax, rax
0x180012642  jnz     short loc_18001264B
0x180012644  mov     ebx, 8007000Eh
0x180012649  jmp     short loc_180012691
0x18001264b  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18001264f  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180012654  mov     r9d, edi; cbMultiByte
0x180012657  mov     r8, r14; lpMultiByteStr
0x18001265a  xor     edx, edx; dwFlags
0x18001265c  lea     ecx, [rdx+3]; CodePage
0x18001265f  call    cs:__imp_MultiByteToWideChar
0x180012665  test    eax, eax
0x180012667  jz      loc_18001258B
0x18001266d  mov     ecx, eax
0x18001266f  mov     rax, [rsp+498h+var_438]
0x180012674  mov     [rax+rcx*2], bx
0x180012678  mov     r8d, [rsp+498h+arg_20]; int
0x180012680  mov     rdx, [rsp+498h+var_438]; wchar_t *
0x180012685  lea     rcx, [rsp+498h+var_450]; this
0x18001268a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18001268f  mov     ebx, eax
0x180012691  mov     rcx, rsi; hLibModule
0x180012694  call    cs:__imp_FreeLibrary
0x18001269a  nop
0x18001269b  lea     rax, [rsp+498h+var_430]
0x1800126a0  cmp     [rsp+498h+var_438], rax
0x1800126a5  jz      short loc_1800126B2
0x1800126a7  lea     rcx, [rsp+498h+var_438]
0x1800126ac  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x1800126b1  nop
0x1800126b2  mov     eax, ebx
0x1800126b4  mov     rcx, [rsp+498h+var_28]
0x1800126bc  xor     rcx, rsp; StackCookie
0x1800126bf  call    __security_check_cookie
0x1800126c4  mov     rbx, [rsp+498h+arg_0]
0x1800126cc  add     rsp, 480h
0x1800126d3  pop     r14
0x1800126d5  pop     rdi
0x1800126d6  pop     rsi
0x1800126d7  retn
0x1800126d8  mov     ecx, 80070057h; int
0x1800126dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
