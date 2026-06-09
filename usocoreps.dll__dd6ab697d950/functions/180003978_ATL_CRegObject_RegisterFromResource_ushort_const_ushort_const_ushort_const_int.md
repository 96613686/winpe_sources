# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180003978`
- end: `0x180003b54`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800043ec`
- `0x180004714`

## callees

- `0x180001510`
- `0x180002cf8`
- `0x180002ef4`
- `0x180002f30`
- `0x180003110`
- `0x1800037e8`
- `0x180003978`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039c2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800039c2`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003a24`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x180003a24`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800039ed`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800039ed`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003a0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180003a0b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003b04`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180003b04`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003acf`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180003acf`

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
  LPCWSTR v20[3]; // [rsp+48h] [rbp-450h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
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
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v21, 2LL * v15);
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
      v12 = ATL::CRegParser::RegisterBuffer(v20, v21, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v21 != (LPWSTR)v22 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap((void **)&v21);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180003978  mov     [rsp+arg_0], rbx
0x18000397d  push    rsi
0x18000397e  push    rdi
0x18000397f  push    r14
0x180003981  sub     rsp, 480h
0x180003988  mov     rax, cs:__security_cookie
0x18000398f  xor     rax, rsp
0x180003992  mov     [rsp+498h+var_28], rax
0x18000399a  mov     r14, r9
0x18000399d  mov     rdi, r8
0x1800039a0  mov     rax, rdx
0x1800039a3  xor     ebx, ebx
0x1800039a5  mov     [rsp+498h+var_440], rbx
0x1800039aa  mov     [rsp+498h+var_448], rcx
0x1800039af  mov     [rsp+498h+var_450], rbx
0x1800039b4  mov     [rsp+498h+var_438], rbx
0x1800039b9  xor     edx, edx; hFile
0x1800039bb  lea     r8d, [rbx+2]; dwFlags
0x1800039bf  mov     rcx, rax; lpLibFileName
0x1800039c2  call    cs:__imp_LoadLibraryExW
0x1800039c8  mov     rsi, rax
0x1800039cb  mov     [rsp+498h+var_460], rax
0x1800039d0  test    rax, rax
0x1800039d3  jnz     short loc_1800039E1
0x1800039d5  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800039da  mov     ebx, eax
0x1800039dc  jmp     loc_180003B0B
0x1800039e1  xor     r9d, r9d; wLanguage
0x1800039e4  mov     r8, rdi; lpName
0x1800039e7  mov     rdx, r14; lpType
0x1800039ea  mov     rcx, rsi; hModule
0x1800039ed  call    cs:__imp_FindResourceExW
0x1800039f3  mov     rdi, rax
0x1800039f6  test    rax, rax
0x1800039f9  jnz     short loc_180003A05
0x1800039fb  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180003a00  jmp     loc_180003AFF
0x180003a05  mov     rdx, rdi; hResInfo
0x180003a08  mov     rcx, rsi; hModule
0x180003a0b  call    cs:__imp_LoadResource
0x180003a11  mov     r14, rax
0x180003a14  mov     [rsp+498h+var_458], rax
0x180003a19  test    rax, rax
0x180003a1c  jz      short loc_1800039FB
0x180003a1e  mov     rdx, rdi; hResInfo
0x180003a21  mov     rcx, rsi; hModule
0x180003a24  call    cs:__imp_SizeofResource
0x180003a2a  mov     edi, eax
0x180003a2c  mov     [rsp+498h+var_468], eax
0x180003a30  inc     eax
0x180003a32  cmp     eax, edi
0x180003a34  jnb     short loc_180003A57
0x180003a36  lea     rax, [rsp+498h+var_430]
0x180003a3b  cmp     [rsp+498h+var_438], rax
0x180003a40  jz      short loc_180003A4D
0x180003a42  lea     rcx, [rsp+498h+var_438]
0x180003a47  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003a4c  nop
0x180003a4d  mov     eax, 8007000Eh
0x180003a52  jmp     loc_180003B24
0x180003a57  test    eax, eax
0x180003a59  jz      short loc_180003A8E
0x180003a5b  mov     ecx, eax
0x180003a5d  xor     edx, edx
0x180003a5f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180003a63  div     rcx
0x180003a66  cmp     rax, 2
0x180003a6a  jb      loc_180003B48
0x180003a70  lea     rdx, [rcx+rcx]
0x180003a74  cmp     rdx, 400h
0x180003a7b  jbe     short loc_180003A8E
0x180003a7d  lea     rcx, [rsp+498h+var_438]
0x180003a82  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180003a87  mov     rax, [rsp+498h+var_438]
0x180003a8c  jmp     short loc_180003A98
0x180003a8e  lea     rax, [rsp+498h+var_430]
0x180003a93  mov     [rsp+498h+var_438], rax
0x180003a98  jmp     short loc_180003AAF
0x180003a9a  xor     ebx, ebx
0x180003a9c  mov     rsi, [rsp+498h+var_460]
0x180003aa1  mov     r14, [rsp+498h+var_458]
0x180003aa6  mov     edi, [rsp+498h+var_468]
0x180003aaa  mov     rax, [rsp+498h+var_438]
0x180003aaf  test    rax, rax
0x180003ab2  jnz     short loc_180003ABB
0x180003ab4  mov     ebx, 8007000Eh
0x180003ab9  jmp     short loc_180003B01
0x180003abb  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180003abf  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180003ac4  mov     r9d, edi; cbMultiByte
0x180003ac7  mov     r8, r14; lpMultiByteStr
0x180003aca  xor     edx, edx; dwFlags
0x180003acc  lea     ecx, [rdx+3]; CodePage
0x180003acf  call    cs:__imp_MultiByteToWideChar
0x180003ad5  test    eax, eax
0x180003ad7  jz      loc_1800039FB
0x180003add  mov     ecx, eax
0x180003adf  mov     rax, [rsp+498h+var_438]
0x180003ae4  mov     [rax+rcx*2], bx
0x180003ae8  mov     r8d, [rsp+498h+arg_20]; int
0x180003af0  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180003af5  lea     rcx, [rsp+498h+var_450]; this
0x180003afa  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180003aff  mov     ebx, eax
0x180003b01  mov     rcx, rsi; hLibModule
0x180003b04  call    cs:__imp_FreeLibrary
0x180003b0a  nop
0x180003b0b  lea     rax, [rsp+498h+var_430]
0x180003b10  cmp     [rsp+498h+var_438], rax
0x180003b15  jz      short loc_180003B22
0x180003b17  lea     rcx, [rsp+498h+var_438]
0x180003b1c  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180003b21  nop
0x180003b22  mov     eax, ebx
0x180003b24  mov     rcx, [rsp+498h+var_28]
0x180003b2c  xor     rcx, rsp; StackCookie
0x180003b2f  call    __security_check_cookie
0x180003b34  mov     rbx, [rsp+498h+arg_0]
0x180003b3c  add     rsp, 480h
0x180003b43  pop     r14
0x180003b45  pop     rdi
0x180003b46  pop     rsi
0x180003b47  retn
0x180003b48  mov     ecx, 80070057h; int
0x180003b4d  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
