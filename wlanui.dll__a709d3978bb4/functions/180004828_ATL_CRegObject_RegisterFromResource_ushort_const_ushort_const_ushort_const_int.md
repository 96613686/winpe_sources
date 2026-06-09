# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004828`
- end: `0x1800049e3`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `443`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800054fc`
- `0x18000581c`

## callees

- `0x1800035f8`
- `0x180003834`
- `0x180003870`
- `0x180003da4`
- `0x180004698`
- `0x180004828`
- `0x18001bf40`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004998`
- `KERNEL32!FreeLibrary` at `0x180004998`
- `KERNEL32!LoadLibraryExW` at `0x180004879`
- `KERNEL32!LoadLibraryExW` at `0x180004879`
- `KERNEL32!MultiByteToWideChar` at `0x180004962`
- `KERNEL32!MultiByteToWideChar` at `0x180004962`
- `KERNEL32!SizeofResource` at `0x1800048d1`
- `KERNEL32!SizeofResource` at `0x1800048d1`
- `KERNEL32!LoadResource` at `0x1800048bd`
- `KERNEL32!LoadResource` at `0x1800048bd`
- `KERNEL32!FindResourceExW` at `0x18000489f`
- `KERNEL32!FindResourceExW` at `0x18000489f`

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
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rbx
  unsigned int v12; // eax
  const CHAR *v13; // rsi
  DWORD cchWideChar; // ebx
  __int64 v15; // rcx
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  _QWORD v19[2]; // [rsp+30h] [rbp-D0h] BYREF
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
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
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
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v19, v20, a5);
      goto LABEL_19;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v12;
    goto LABEL_20;
  }
  if ( v20 != (LPWSTR)v21 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v20);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180004828  mov     [rsp-8+arg_0], rbx
0x18000482d  push    rbp
0x18000482e  push    rsi
0x18000482f  push    rdi
0x180004830  lea     rbp, [rsp-360h]
0x180004838  sub     rsp, 460h
0x18000483f  mov     rax, cs:__security_cookie
0x180004846  xor     rax, rsp
0x180004849  mov     [rbp+370h+var_20], rax
0x180004850  mov     rax, rdx
0x180004853  mov     [rsp+470h+var_438], rcx
0x180004858  xor     edx, edx; hFile
0x18000485a  mov     [rsp+470h+var_440], 0
0x180004863  mov     rbx, r8
0x180004866  mov     [rsp+470h+var_430], 0
0x18000486f  mov     rcx, rax; lpLibFileName
0x180004872  mov     rsi, r9
0x180004875  lea     r8d, [rdx+2]; dwFlags
0x180004879  call    cs:__imp_LoadLibraryExW
0x18000487f  mov     rdi, rax
0x180004882  test    rax, rax
0x180004885  jnz     short loc_180004893
0x180004887  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000488c  mov     ebx, eax
0x18000488e  jmp     loc_18000499E
0x180004893  xor     r9d, r9d; wLanguage
0x180004896  mov     r8, rbx; lpName
0x180004899  mov     rdx, rsi; lpType
0x18000489c  mov     rcx, rdi; hModule
0x18000489f  call    cs:__imp_FindResourceExW
0x1800048a5  mov     rbx, rax
0x1800048a8  test    rax, rax
0x1800048ab  jnz     short loc_1800048B7
0x1800048ad  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800048b2  jmp     loc_180004993
0x1800048b7  mov     rdx, rbx; hResInfo
0x1800048ba  mov     rcx, rdi; hModule
0x1800048bd  call    cs:__imp_LoadResource
0x1800048c3  mov     rsi, rax
0x1800048c6  test    rax, rax
0x1800048c9  jz      short loc_1800048AD
0x1800048cb  mov     rdx, rbx; hResInfo
0x1800048ce  mov     rcx, rdi; hModule
0x1800048d1  call    cs:__imp_SizeofResource
0x1800048d7  mov     ebx, eax
0x1800048d9  lea     ecx, [rax+1]
0x1800048dc  cmp     ecx, eax
0x1800048de  jnb     short loc_180004900
0x1800048e0  lea     rax, [rsp+470h+var_428]
0x1800048e5  cmp     [rsp+470h+var_430], rax
0x1800048ea  jz      short loc_1800048F6
0x1800048ec  lea     rcx, [rsp+470h+var_430]
0x1800048f1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800048f6  mov     eax, 8007000Eh
0x1800048fb  jmp     loc_1800049B6
0x180004900  test    ecx, ecx
0x180004902  jz      short loc_180004938
0x180004904  xor     edx, edx
0x180004906  mov     r8d, ecx
0x180004909  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000490d  div     r8
0x180004910  cmp     rax, 2
0x180004914  jb      loc_1800049D8
0x18000491a  lea     rdx, [rcx+rcx]
0x18000491e  cmp     rdx, 400h
0x180004925  jbe     short loc_180004938
0x180004927  lea     rcx, [rsp+470h+var_430]
0x18000492c  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004931  mov     rax, [rsp+470h+var_430]
0x180004936  jmp     short loc_180004942
0x180004938  lea     rax, [rsp+470h+var_428]
0x18000493d  mov     [rsp+470h+var_430], rax
0x180004942  test    rax, rax
0x180004945  jnz     short loc_18000494E
0x180004947  mov     ebx, 8007000Eh
0x18000494c  jmp     short loc_180004995
0x18000494e  xor     edx, edx; dwFlags
0x180004950  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180004954  mov     r9d, ebx; cbMultiByte
0x180004957  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000495c  mov     r8, rsi; lpMultiByteStr
0x18000495f  lea     ecx, [rdx+3]; CodePage
0x180004962  call    cs:__imp_MultiByteToWideChar
0x180004968  test    eax, eax
0x18000496a  jz      loc_1800048AD
0x180004970  mov     r8d, [rbp+370h+arg_20]; int
0x180004977  xor     ecx, ecx
0x180004979  mov     edx, eax
0x18000497b  mov     rax, [rsp+470h+var_430]
0x180004980  mov     [rax+rdx*2], cx
0x180004984  lea     rcx, [rsp+470h+var_440]; this
0x180004989  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000498e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004993  mov     ebx, eax
0x180004995  mov     rcx, rdi; hLibModule
0x180004998  call    cs:__imp_FreeLibrary
0x18000499e  lea     rax, [rsp+470h+var_428]
0x1800049a3  cmp     [rsp+470h+var_430], rax
0x1800049a8  jz      short loc_1800049B4
0x1800049aa  lea     rcx, [rsp+470h+var_430]
0x1800049af  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800049b4  mov     eax, ebx
0x1800049b6  mov     rcx, [rbp+370h+var_20]
0x1800049bd  xor     rcx, rsp; StackCookie
0x1800049c0  call    __security_check_cookie
0x1800049c5  mov     rbx, [rsp+470h+arg_0]
0x1800049cd  add     rsp, 460h
0x1800049d4  pop     rdi
0x1800049d5  pop     rsi
0x1800049d6  pop     rbp
0x1800049d7  retn
0x1800049d8  mov     ecx, 80070057h; int
0x1800049dd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
