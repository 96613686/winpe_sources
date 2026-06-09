# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140004698`
- end: `0x140004853`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x14000550c`
- `0x140005834`

## callees

- `0x140001490`
- `0x140002928`
- `0x140002a18`
- `0x140003298`
- `0x140003754`
- `0x1400043a8`
- `0x140004698`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14000470f`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x14000470f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14000472d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x14000472d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004808`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x140004808`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140004741`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x140004741`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400046e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1400046e9`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400047d2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1400047d2`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  LPCWSTR v19[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v20; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v21[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v19[1] = this;
  v19[0] = 0;
  v20 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v20 != (LPWSTR)v21 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
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
  if ( (unsigned int)v15 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned __int64)(2 * v15) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v20, 2 * v15);
      lpWideCharStr = v20;
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
      v20[v18] = 0;
      v12 = ATL::CRegParser::RegisterBuffer(v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x140004698  mov     [rsp-8+arg_0], rbx
0x14000469d  push    rbp
0x14000469e  push    rsi
0x14000469f  push    rdi
0x1400046a0  lea     rbp, [rsp-360h]
0x1400046a8  sub     rsp, 460h
0x1400046af  mov     rax, cs:__security_cookie
0x1400046b6  xor     rax, rsp
0x1400046b9  mov     [rbp+370h+var_20], rax
0x1400046c0  mov     rax, rdx
0x1400046c3  mov     [rsp+470h+var_438], rcx
0x1400046c8  xor     edx, edx; hFile
0x1400046ca  mov     [rsp+470h+var_440], 0
0x1400046d3  mov     rbx, r8
0x1400046d6  mov     [rsp+470h+var_430], 0
0x1400046df  mov     rcx, rax; lpLibFileName
0x1400046e2  mov     rsi, r9
0x1400046e5  lea     r8d, [rdx+2]; dwFlags
0x1400046e9  call    cs:__imp_LoadLibraryExW
0x1400046ef  mov     rdi, rax
0x1400046f2  test    rax, rax
0x1400046f5  jnz     short loc_140004703
0x1400046f7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1400046fc  mov     ebx, eax
0x1400046fe  jmp     loc_14000480E
0x140004703  xor     r9d, r9d; wLanguage
0x140004706  mov     r8, rbx; lpName
0x140004709  mov     rdx, rsi; lpType
0x14000470c  mov     rcx, rdi; hModule
0x14000470f  call    cs:__imp_FindResourceExW
0x140004715  mov     rbx, rax
0x140004718  test    rax, rax
0x14000471b  jnz     short loc_140004727
0x14000471d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140004722  jmp     loc_140004803
0x140004727  mov     rdx, rbx; hResInfo
0x14000472a  mov     rcx, rdi; hModule
0x14000472d  call    cs:__imp_LoadResource
0x140004733  mov     rsi, rax
0x140004736  test    rax, rax
0x140004739  jz      short loc_14000471D
0x14000473b  mov     rdx, rbx; hResInfo
0x14000473e  mov     rcx, rdi; hModule
0x140004741  call    cs:__imp_SizeofResource
0x140004747  mov     ebx, eax
0x140004749  lea     ecx, [rax+1]
0x14000474c  cmp     ecx, eax
0x14000474e  jnb     short loc_140004770
0x140004750  lea     rax, [rsp+470h+var_428]
0x140004755  cmp     [rsp+470h+var_430], rax
0x14000475a  jz      short loc_140004766
0x14000475c  lea     rcx, [rsp+470h+var_430]
0x140004761  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140004766  mov     eax, 8007000Eh
0x14000476b  jmp     loc_140004826
0x140004770  test    ecx, ecx
0x140004772  jz      short loc_1400047A8
0x140004774  xor     edx, edx
0x140004776  mov     r8d, ecx
0x140004779  or      rax, 0FFFFFFFFFFFFFFFFh
0x14000477d  div     r8
0x140004780  cmp     rax, 2
0x140004784  jb      loc_140004848
0x14000478a  lea     rdx, [rcx+rcx]
0x14000478e  cmp     rdx, 400h
0x140004795  jbe     short loc_1400047A8
0x140004797  lea     rcx, [rsp+470h+var_430]
0x14000479c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400047a1  mov     rax, [rsp+470h+var_430]
0x1400047a6  jmp     short loc_1400047B2
0x1400047a8  lea     rax, [rsp+470h+var_428]
0x1400047ad  mov     [rsp+470h+var_430], rax
0x1400047b2  test    rax, rax
0x1400047b5  jnz     short loc_1400047BE
0x1400047b7  mov     ebx, 8007000Eh
0x1400047bc  jmp     short loc_140004805
0x1400047be  xor     edx, edx; dwFlags
0x1400047c0  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x1400047c4  mov     r9d, ebx; cbMultiByte
0x1400047c7  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x1400047cc  mov     r8, rsi; lpMultiByteStr
0x1400047cf  lea     ecx, [rdx+3]; CodePage
0x1400047d2  call    cs:__imp_MultiByteToWideChar
0x1400047d8  test    eax, eax
0x1400047da  jz      loc_14000471D
0x1400047e0  mov     r8d, [rbp+370h+arg_20]; int
0x1400047e7  xor     ecx, ecx
0x1400047e9  mov     edx, eax
0x1400047eb  mov     rax, [rsp+470h+var_430]
0x1400047f0  mov     [rax+rdx*2], cx
0x1400047f4  lea     rcx, [rsp+470h+var_440]; this
0x1400047f9  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x1400047fe  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140004803  mov     ebx, eax
0x140004805  mov     rcx, rdi; hLibModule
0x140004808  call    cs:__imp_FreeLibrary
0x14000480e  lea     rax, [rsp+470h+var_428]
0x140004813  cmp     [rsp+470h+var_430], rax
0x140004818  jz      short loc_140004824
0x14000481a  lea     rcx, [rsp+470h+var_430]
0x14000481f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140004824  mov     eax, ebx
0x140004826  mov     rcx, [rbp+370h+var_20]
0x14000482d  xor     rcx, rsp; StackCookie
0x140004830  call    __security_check_cookie
0x140004835  mov     rbx, [rsp+470h+arg_0]
0x14000483d  add     rsp, 460h
0x140004844  pop     rdi
0x140004845  pop     rsi
0x140004846  pop     rbp
0x140004847  retn
0x140004848  mov     ecx, 80070057h; int
0x14000484d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
