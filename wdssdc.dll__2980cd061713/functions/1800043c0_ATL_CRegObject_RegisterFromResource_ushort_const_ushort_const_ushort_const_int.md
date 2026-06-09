# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800043c0`
- end: `0x180004594`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `468`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1800050c8`

## callees

- `0x1800015b0`
- `0x1800031c0`
- `0x18000331c`
- `0x18000335c`
- `0x1800038c8`
- `0x18000420c`
- `0x1800043c0`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x180004437`
- `KERNEL32!FindResourceExW` at `0x180004437`
- `KERNEL32!LoadResource` at `0x18000445b`
- `KERNEL32!LoadResource` at `0x18000445b`
- `KERNEL32!FreeLibrary` at `0x180004547`
- `KERNEL32!FreeLibrary` at `0x180004547`
- `KERNEL32!LoadLibraryExW` at `0x18000440b`
- `KERNEL32!LoadLibraryExW` at `0x18000440b`
- `KERNEL32!MultiByteToWideChar` at `0x18000450c`
- `KERNEL32!MultiByteToWideChar` at `0x18000450c`
- `KERNEL32!SizeofResource` at `0x180004475`
- `KERNEL32!SizeofResource` at `0x180004475`

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
0x1800043c0  push    rbp
0x1800043c2  push    rbx
0x1800043c3  push    rsi
0x1800043c4  push    rdi
0x1800043c5  push    r14
0x1800043c7  lea     rbp, [rsp-360h]
0x1800043cf  sub     rsp, 460h
0x1800043d6  mov     rax, cs:__security_cookie
0x1800043dd  xor     rax, rsp
0x1800043e0  mov     [rbp+380h+var_30], rax
0x1800043e7  xor     r14d, r14d
0x1800043ea  mov     [rsp+480h+var_448], rcx
0x1800043ef  mov     rax, rdx
0x1800043f2  mov     [rsp+480h+var_450], r14
0x1800043f7  mov     rbx, r8
0x1800043fa  mov     [rsp+480h+var_440], r14
0x1800043ff  xor     edx, edx; hFile
0x180004401  mov     rcx, rax; lpLibFileName
0x180004404  lea     r8d, [r14+2]; dwFlags
0x180004408  mov     rsi, r9
0x18000440b  call    cs:__imp_LoadLibraryExW
0x180004412  nop     dword ptr [rax+rax+00h]
0x180004417  mov     rdi, rax
0x18000441a  test    rax, rax
0x18000441d  jnz     short loc_18000442B
0x18000441f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004424  mov     ebx, eax
0x180004426  jmp     loc_180004553
0x18000442b  xor     r9d, r9d; wLanguage
0x18000442e  mov     r8, rbx; lpName
0x180004431  mov     rdx, rsi; lpType
0x180004434  mov     rcx, rdi; hModule
0x180004437  call    cs:__imp_FindResourceExW
0x18000443e  nop     dword ptr [rax+rax+00h]
0x180004443  mov     rbx, rax
0x180004446  test    rax, rax
0x180004449  jnz     short loc_180004455
0x18000444b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004450  jmp     loc_180004542
0x180004455  mov     rdx, rbx; hResInfo
0x180004458  mov     rcx, rdi; hModule
0x18000445b  call    cs:__imp_LoadResource
0x180004462  nop     dword ptr [rax+rax+00h]
0x180004467  mov     rsi, rax
0x18000446a  test    rax, rax
0x18000446d  jz      short loc_18000444B
0x18000446f  mov     rdx, rbx; hResInfo
0x180004472  mov     rcx, rdi; hModule
0x180004475  call    cs:__imp_SizeofResource
0x18000447c  nop     dword ptr [rax+rax+00h]
0x180004481  mov     ebx, eax
0x180004483  lea     ecx, [rax+1]
0x180004486  cmp     ecx, eax
0x180004488  jnb     short loc_1800044AA
0x18000448a  lea     rax, [rsp+480h+var_438]
0x18000448f  cmp     [rsp+480h+var_440], rax
0x180004494  jz      short loc_1800044A0
0x180004496  lea     rcx, [rsp+480h+var_440]
0x18000449b  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800044a0  mov     eax, 8007000Eh
0x1800044a5  jmp     loc_18000456B
0x1800044aa  mov     r8d, ecx
0x1800044ad  test    ecx, ecx
0x1800044af  jz      short loc_1800044E2
0x1800044b1  xor     edx, edx
0x1800044b3  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800044b7  div     r8
0x1800044ba  cmp     rax, 2
0x1800044be  jb      loc_180004589
0x1800044c4  lea     rdx, [rcx+rcx]
0x1800044c8  cmp     rdx, 400h
0x1800044cf  jbe     short loc_1800044E2
0x1800044d1  lea     rcx, [rsp+480h+var_440]
0x1800044d6  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800044db  mov     rax, [rsp+480h+var_440]
0x1800044e0  jmp     short loc_1800044EC
0x1800044e2  lea     rax, [rsp+480h+var_438]
0x1800044e7  mov     [rsp+480h+var_440], rax
0x1800044ec  test    rax, rax
0x1800044ef  jnz     short loc_1800044F8
0x1800044f1  mov     ebx, 8007000Eh
0x1800044f6  jmp     short loc_180004544
0x1800044f8  xor     edx, edx; dwFlags
0x1800044fa  mov     [rsp+480h+cchWideChar], ebx; cchWideChar
0x1800044fe  mov     r9d, ebx; cbMultiByte
0x180004501  mov     [rsp+480h+lpWideCharStr], rax; lpWideCharStr
0x180004506  mov     r8, rsi; lpMultiByteStr
0x180004509  lea     ecx, [rdx+3]; CodePage
0x18000450c  call    cs:__imp_MultiByteToWideChar
0x180004513  nop     dword ptr [rax+rax+00h]
0x180004518  test    eax, eax
0x18000451a  jz      loc_18000444B
0x180004520  mov     r8d, [rbp+380h+arg_20]; int
0x180004527  mov     ecx, eax
0x180004529  mov     rax, [rsp+480h+var_440]
0x18000452e  mov     [rax+rcx*2], r14w
0x180004533  lea     rcx, [rsp+480h+var_450]; this
0x180004538  mov     rdx, [rsp+480h+var_440]; unsigned __int16 *
0x18000453d  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004542  mov     ebx, eax
0x180004544  mov     rcx, rdi; hLibModule
0x180004547  call    cs:__imp_FreeLibrary
0x18000454e  nop     dword ptr [rax+rax+00h]
0x180004553  lea     rax, [rsp+480h+var_438]
0x180004558  cmp     [rsp+480h+var_440], rax
0x18000455d  jz      short loc_180004569
0x18000455f  lea     rcx, [rsp+480h+var_440]
0x180004564  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180004569  mov     eax, ebx
0x18000456b  mov     rcx, [rbp+380h+var_30]
0x180004572  xor     rcx, rsp; StackCookie
0x180004575  call    __security_check_cookie
0x18000457a  add     rsp, 460h
0x180004581  pop     r14
0x180004583  pop     rdi
0x180004584  pop     rsi
0x180004585  pop     rbx
0x180004586  pop     rbp
0x180004587  retn
0x180004589  mov     ecx, 80070057h; int
0x18000458e  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
