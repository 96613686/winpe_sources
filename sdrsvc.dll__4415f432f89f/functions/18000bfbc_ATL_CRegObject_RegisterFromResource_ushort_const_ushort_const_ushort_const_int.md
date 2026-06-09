# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000bfbc`
- end: `0x18000c168`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `428`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18000d7ec`
- `0x18000db0c`

## callees

- `0x180009704`
- `0x1800098f4`
- `0x18000ab34`
- `0x18000bcbc`
- `0x18000bfbc`
- `0x180021740`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c00d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000c00d`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000c065`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000c065`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000c051`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18000c051`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000c033`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18000c033`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c128`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000c128`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c0f2`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18000c0f2`

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
    if ( cchWideChar == -1 || 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v15 < 2 || (unsigned __int64)(2 * v15) <= 0x400 )
    {
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
0x18000bfbc  mov     [rsp-8+arg_0], rbx
0x18000bfc1  push    rbp
0x18000bfc2  push    rsi
0x18000bfc3  push    rdi
0x18000bfc4  lea     rbp, [rsp-360h]
0x18000bfcc  sub     rsp, 460h
0x18000bfd3  mov     rax, cs:__security_cookie
0x18000bfda  xor     rax, rsp
0x18000bfdd  mov     [rbp+370h+var_20], rax
0x18000bfe4  mov     rax, rdx
0x18000bfe7  mov     [rsp+470h+var_438], rcx
0x18000bfec  xor     edx, edx; hFile
0x18000bfee  mov     [rsp+470h+var_440], 0
0x18000bff7  mov     rbx, r8
0x18000bffa  mov     [rsp+470h+var_430], 0
0x18000c003  mov     rcx, rax; lpLibFileName
0x18000c006  mov     rsi, r9
0x18000c009  lea     r8d, [rdx+2]; dwFlags
0x18000c00d  call    cs:__imp_LoadLibraryExW
0x18000c013  mov     rdi, rax
0x18000c016  test    rax, rax
0x18000c019  jnz     short loc_18000C027
0x18000c01b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c020  mov     ebx, eax
0x18000c022  jmp     loc_18000C12E
0x18000c027  xor     r9d, r9d; wLanguage
0x18000c02a  mov     r8, rbx; lpName
0x18000c02d  mov     rdx, rsi; lpType
0x18000c030  mov     rcx, rdi; hModule
0x18000c033  call    cs:__imp_FindResourceExW
0x18000c039  mov     rbx, rax
0x18000c03c  test    rax, rax
0x18000c03f  jnz     short loc_18000C04B
0x18000c041  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000c046  jmp     loc_18000C123
0x18000c04b  mov     rdx, rbx; hResInfo
0x18000c04e  mov     rcx, rdi; hModule
0x18000c051  call    cs:__imp_LoadResource
0x18000c057  mov     rsi, rax
0x18000c05a  test    rax, rax
0x18000c05d  jz      short loc_18000C041
0x18000c05f  mov     rdx, rbx; hResInfo
0x18000c062  mov     rcx, rdi; hModule
0x18000c065  call    cs:__imp_SizeofResource
0x18000c06b  mov     ebx, eax
0x18000c06d  lea     ecx, [rax+1]
0x18000c070  cmp     ecx, eax
0x18000c072  jnb     short loc_18000C094
0x18000c074  lea     rax, [rsp+470h+var_428]
0x18000c079  cmp     [rsp+470h+var_430], rax
0x18000c07e  jz      short loc_18000C08A
0x18000c080  lea     rcx, [rsp+470h+var_430]
0x18000c085  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000c08a  mov     eax, 8007000Eh
0x18000c08f  jmp     loc_18000C146
0x18000c094  test    ecx, ecx
0x18000c096  jz      short loc_18000C0C8
0x18000c098  xor     edx, edx
0x18000c09a  mov     r8d, ecx
0x18000c09d  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000c0a1  div     r8
0x18000c0a4  cmp     rax, 2
0x18000c0a8  jb      short loc_18000C0C8
0x18000c0aa  lea     rdx, [rcx+rcx]
0x18000c0ae  cmp     rdx, 400h
0x18000c0b5  jbe     short loc_18000C0C8
0x18000c0b7  lea     rcx, [rsp+470h+var_430]
0x18000c0bc  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000c0c1  mov     rax, [rsp+470h+var_430]
0x18000c0c6  jmp     short loc_18000C0D2
0x18000c0c8  lea     rax, [rsp+470h+var_428]
0x18000c0cd  mov     [rsp+470h+var_430], rax
0x18000c0d2  test    rax, rax
0x18000c0d5  jnz     short loc_18000C0DE
0x18000c0d7  mov     ebx, 8007000Eh
0x18000c0dc  jmp     short loc_18000C125
0x18000c0de  xor     edx, edx; dwFlags
0x18000c0e0  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x18000c0e4  mov     r9d, ebx; cbMultiByte
0x18000c0e7  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000c0ec  mov     r8, rsi; lpMultiByteStr
0x18000c0ef  lea     ecx, [rdx+3]; CodePage
0x18000c0f2  call    cs:__imp_MultiByteToWideChar
0x18000c0f8  test    eax, eax
0x18000c0fa  jz      loc_18000C041
0x18000c100  mov     r8d, [rbp+370h+arg_20]; int
0x18000c107  xor     ecx, ecx
0x18000c109  mov     edx, eax
0x18000c10b  mov     rax, [rsp+470h+var_430]
0x18000c110  mov     [rax+rdx*2], cx
0x18000c114  lea     rcx, [rsp+470h+var_440]; this
0x18000c119  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000c11e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000c123  mov     ebx, eax
0x18000c125  mov     rcx, rdi; hLibModule
0x18000c128  call    cs:__imp_FreeLibrary
0x18000c12e  lea     rax, [rsp+470h+var_428]
0x18000c133  cmp     [rsp+470h+var_430], rax
0x18000c138  jz      short loc_18000C144
0x18000c13a  lea     rcx, [rsp+470h+var_430]
0x18000c13f  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000c144  mov     eax, ebx
0x18000c146  mov     rcx, [rbp+370h+var_20]
0x18000c14d  xor     rcx, rsp; StackCookie
0x18000c150  call    __security_check_cookie
0x18000c155  mov     rbx, [rsp+470h+arg_0]
0x18000c15d  add     rsp, 460h
0x18000c164  pop     rdi
0x18000c165  pop     rsi
0x18000c166  pop     rbp
0x18000c167  retn
```
