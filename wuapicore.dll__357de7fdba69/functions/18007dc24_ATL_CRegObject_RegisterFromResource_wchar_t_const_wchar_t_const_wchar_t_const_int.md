# ATL::CRegObject::RegisterFromResource(wchar_t const *,wchar_t const *,wchar_t const *,int)

- ea: `0x18007dc24`
- end: `0x18007de09`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEB_W00H@Z`
- size: `485`
- prototype: `int(ATL::CRegObject *__hidden this, const wchar_t *, const wchar_t *, const wchar_t *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18007de10`

## callees

- `0x180004d50`
- `0x18007c004`
- `0x18007c034`
- `0x18007c064`
- `0x18007da88`
- `0x18007dc24`
- `0x18009ae75`
- `0x18009b050`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007ddbe`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18007ddbe`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18007dcfa`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18007dcfa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18007dce1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18007dce1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dc7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dc9b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dc7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18007dc9b`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007dd84`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18007dd84`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18007dcc3`
- `api-ms-win-core-libraryloader-l1-2-1!FindResourceW` at `0x18007dcc3`

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
    ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::FreeHeap(&lpWideCharStr);
  return Error;
}

```

## disassembly

```asm
0x18007dc24  push    rbx
0x18007dc26  push    rsi
0x18007dc27  push    rdi
0x18007dc28  push    r14
0x18007dc2a  push    r15
0x18007dc2c  sub     rsp, 480h
0x18007dc33  mov     rax, cs:__security_cookie
0x18007dc3a  xor     rax, rsp
0x18007dc3d  mov     [rsp+4A8h+var_38], rax
0x18007dc45  mov     r15, r9
0x18007dc48  mov     r14, r8
0x18007dc4b  mov     rbx, rdx
0x18007dc4e  xor     edi, edi
0x18007dc50  mov     [rsp+4A8h+var_460], rdi
0x18007dc55  mov     [rsp+4A8h+var_450], rcx
0x18007dc5a  mov     [rsp+4A8h+var_458], rdi
0x18007dc5f  xor     edx, edx; Val
0x18007dc61  mov     r8d, 408h; Size
0x18007dc67  lea     rcx, [rsp+4A8h+var_448]; void *
0x18007dc6c  call    memset_0
0x18007dc71  mov     [rsp+4A8h+var_448], rdi
0x18007dc76  xor     edx, edx; hFile
0x18007dc78  lea     r8d, [rdi+60h]; dwFlags
0x18007dc7c  mov     rcx, rbx; lpLibFileName
0x18007dc7f  call    cs:__imp_LoadLibraryExW
0x18007dc85  mov     rsi, rax
0x18007dc88  mov     [rsp+4A8h+var_470], rax
0x18007dc8d  test    rax, rax
0x18007dc90  jnz     short loc_18007DCBA
0x18007dc92  xor     edx, edx; hFile
0x18007dc94  lea     r8d, [rdi+2]; dwFlags
0x18007dc98  mov     rcx, rbx; lpLibFileName
0x18007dc9b  call    cs:__imp_LoadLibraryExW
0x18007dca1  mov     rsi, rax
0x18007dca4  mov     [rsp+4A8h+var_470], rax
0x18007dca9  test    rax, rax
0x18007dcac  jnz     short loc_18007DCBA
0x18007dcae  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007dcb3  mov     ebx, eax
0x18007dcb5  jmp     loc_18007DDC5
0x18007dcba  mov     r8, r15; lpType
0x18007dcbd  mov     rdx, r14; lpName
0x18007dcc0  mov     rcx, rsi; hModule
0x18007dcc3  call    cs:__imp_FindResourceW
0x18007dcc9  mov     rbx, rax
0x18007dccc  test    rax, rax
0x18007dccf  jnz     short loc_18007DCDB
0x18007dcd1  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18007dcd6  jmp     loc_18007DDB4
0x18007dcdb  mov     rdx, rbx; hResInfo
0x18007dcde  mov     rcx, rsi; hModule
0x18007dce1  call    cs:__imp_LoadResource
0x18007dce7  mov     r14, rax
0x18007dcea  mov     [rsp+4A8h+var_468], rax
0x18007dcef  test    rax, rax
0x18007dcf2  jz      short loc_18007DCD1
0x18007dcf4  mov     rdx, rbx; hResInfo
0x18007dcf7  mov     rcx, rsi; hModule
0x18007dcfa  call    cs:__imp_SizeofResource
0x18007dd00  mov     ebx, eax
0x18007dd02  mov     [rsp+4A8h+var_478], eax
0x18007dd06  inc     eax
0x18007dd08  cmp     eax, ebx
0x18007dd0a  jnb     short loc_18007DD16
0x18007dd0c  mov     ebx, 8007000Eh
0x18007dd11  jmp     loc_18007DDB6
0x18007dd16  test    eax, eax
0x18007dd18  jz      short loc_18007DD48
0x18007dd1a  mov     ecx, eax
0x18007dd1c  xor     edx, edx
0x18007dd1e  or      rax, 0FFFFFFFFFFFFFFFFh
0x18007dd22  div     rcx
0x18007dd25  cmp     rax, 2
0x18007dd29  jb      loc_18007DDFD
0x18007dd2f  lea     rdx, [rcx+rcx]
0x18007dd33  cmp     rdx, 400h
0x18007dd3a  jbe     short loc_18007DD48
0x18007dd3c  lea     rcx, [rsp+4A8h+var_448]
0x18007dd41  call    ?AllocateHeap@?$CTempBuffer@_W$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<wchar_t,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18007dd46  jmp     short loc_18007DD52
0x18007dd48  lea     rax, [rsp+4A8h+var_440]
0x18007dd4d  mov     [rsp+4A8h+var_448], rax
0x18007dd52  jmp     short loc_18007DD64
0x18007dd54  xor     edi, edi
0x18007dd56  mov     rsi, [rsp+4A8h+var_470]
0x18007dd5b  mov     r14, [rsp+4A8h+var_468]
0x18007dd60  mov     ebx, [rsp+4A8h+var_478]
0x18007dd64  cmp     [rsp+4A8h+var_448], rdi
0x18007dd69  jz      short loc_18007DD0C
0x18007dd6b  mov     rax, [rsp+4A8h+var_448]
0x18007dd70  mov     [rsp+4A8h+cchWideChar], ebx; cchWideChar
0x18007dd74  mov     [rsp+4A8h+lpWideCharStr], rax; lpWideCharStr
0x18007dd79  mov     r9d, ebx; cbMultiByte
0x18007dd7c  mov     r8, r14; lpMultiByteStr
0x18007dd7f  xor     edx, edx; dwFlags
0x18007dd81  lea     ecx, [rdx+3]; CodePage
0x18007dd84  call    cs:__imp_MultiByteToWideChar
0x18007dd8a  test    eax, eax
0x18007dd8c  jz      loc_18007DCD1
0x18007dd92  mov     ecx, eax
0x18007dd94  mov     rax, [rsp+4A8h+var_448]
0x18007dd99  mov     [rax+rcx*2], di
0x18007dd9d  mov     r8d, [rsp+4A8h+arg_20]; int
0x18007dda5  mov     rdx, [rsp+4A8h+var_448]; wchar_t *
0x18007ddaa  lea     rcx, [rsp+4A8h+var_458]; this
0x18007ddaf  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEA_WH@Z; ATL::CRegParser::RegisterBuffer(wchar_t *,int)
0x18007ddb4  mov     ebx, eax
0x18007ddb6  test    rsi, rsi
0x18007ddb9  jz      short loc_18007DDC5
0x18007ddbb  mov     rcx, rsi; hLibModule
0x18007ddbe  call    cs:__imp_FreeLibrary
0x18007ddc4  nop
0x18007ddc5  lea     rax, [rsp+4A8h+var_440]
0x18007ddca  cmp     [rsp+4A8h+var_448], rax
0x18007ddcf  jz      short loc_18007DDDC
0x18007ddd1  lea     rcx, [rsp+4A8h+var_448]
0x18007ddd6  call    ?FreeHeap@?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::FreeHeap(void)
0x18007dddb  nop
0x18007dddc  mov     eax, ebx
0x18007ddde  mov     rcx, [rsp+4A8h+var_38]
0x18007dde6  xor     rcx, rsp; StackCookie
0x18007dde9  call    __security_check_cookie
0x18007ddee  add     rsp, 480h
0x18007ddf5  pop     r15
0x18007ddf7  pop     r14
0x18007ddf9  pop     rdi
0x18007ddfa  pop     rsi
0x18007ddfb  pop     rbx
0x18007ddfc  retn
0x18007ddfd  mov     ecx, 80070216h; int
0x18007de02  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
