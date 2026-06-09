# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000b518`
- end: `0x18000b6f6`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `478`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x18000ce24`

## callees

- `0x180004074`
- `0x1800041b8`
- `0x1800041f8`
- `0x180004bdc`
- `0x18000b374`
- `0x18000b518`
- `0x180012db0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x18000b6a4`
- `KERNEL32!FreeLibrary` at `0x18000b6a4`
- `KERNEL32!LoadLibraryExW` at `0x18000b566`
- `KERNEL32!LoadLibraryExW` at `0x18000b566`
- `KERNEL32!MultiByteToWideChar` at `0x18000b668`
- `KERNEL32!MultiByteToWideChar` at `0x18000b668`
- `KERNEL32!SizeofResource` at `0x18000b5d1`
- `KERNEL32!SizeofResource` at `0x18000b5d1`
- `KERNEL32!LoadResource` at `0x18000b5b7`
- `KERNEL32!LoadResource` at `0x18000b5b7`
- `KERNEL32!FindResourceExW` at `0x18000b593`
- `KERNEL32!FindResourceExW` at `0x18000b593`

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
  HMODULE v7; // rdi
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v10; // rbx
  unsigned int v11; // eax
  const CHAR *v12; // rsi
  DWORD cchWideChar; // ebx
  __int64 v14; // rcx
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  _QWORD v18[2]; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v19; // [rsp+40h] [rbp-C0h] BYREF
  _BYTE v20[1032]; // [rsp+48h] [rbp-B8h] BYREF

  v18[1] = this;
  v18[0] = 0;
  v19 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
LABEL_21:
    if ( v19 != (LPWSTR)v20 )
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v19);
    return Error;
  }
  Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
  v10 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v12 = (const CHAR *)LoadResource(v7, Resource);
  if ( !v12 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v7, v10);
  v14 = cchWideChar + 1;
  if ( (unsigned int)v14 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / (unsigned int)v14 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( (unsigned __int64)(2 * v14) <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v20;
      v19 = (LPWSTR)v20;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v19, 2 * v14);
      lpWideCharStr = v19;
    }
    if ( !lpWideCharStr )
    {
      Error = -2147024882;
LABEL_20:
      FreeLibrary(v7);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v12, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v19[v17] = 0;
      v11 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v18, v19, a5);
      goto LABEL_19;
    }
LABEL_4:
    v11 = ATL::AtlHresultFromLastError();
LABEL_19:
    Error = v11;
    goto LABEL_20;
  }
  if ( v19 != (LPWSTR)v20 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v19);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000b518  mov     [rsp-8+arg_0], rbx
0x18000b51d  push    rbp
0x18000b51e  push    rsi
0x18000b51f  push    rdi
0x18000b520  lea     rbp, [rsp-360h]
0x18000b528  sub     rsp, 460h
0x18000b52f  mov     rax, cs:__security_cookie
0x18000b536  xor     rax, rsp
0x18000b539  mov     [rbp+370h+var_20], rax
0x18000b540  mov     rax, rdx
0x18000b543  mov     [rsp+470h+var_438], rcx
0x18000b548  xor     edx, edx; hFile
0x18000b54a  mov     [rsp+470h+var_440], 0
0x18000b553  mov     rcx, rax; lpLibFileName
0x18000b556  mov     [rsp+470h+var_430], 0
0x18000b55f  mov     rbx, r9
0x18000b562  lea     r8d, [rdx+2]; dwFlags
0x18000b566  call    cs:__imp_LoadLibraryExW
0x18000b56d  nop     dword ptr [rax+rax+00h]
0x18000b572  mov     rdi, rax
0x18000b575  test    rax, rax
0x18000b578  jnz     short loc_18000B586
0x18000b57a  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b57f  mov     ebx, eax
0x18000b581  jmp     loc_18000B6B0
0x18000b586  xor     r9d, r9d; wLanguage
0x18000b589  mov     rdx, rbx; lpType
0x18000b58c  mov     rcx, rdi; hModule
0x18000b58f  lea     r8d, [r9+65h]; lpName
0x18000b593  call    cs:__imp_FindResourceExW
0x18000b59a  nop     dword ptr [rax+rax+00h]
0x18000b59f  mov     rbx, rax
0x18000b5a2  test    rax, rax
0x18000b5a5  jnz     short loc_18000B5B1
0x18000b5a7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18000b5ac  jmp     loc_18000B69F
0x18000b5b1  mov     rdx, rbx; hResInfo
0x18000b5b4  mov     rcx, rdi; hModule
0x18000b5b7  call    cs:__imp_LoadResource
0x18000b5be  nop     dword ptr [rax+rax+00h]
0x18000b5c3  mov     rsi, rax
0x18000b5c6  test    rax, rax
0x18000b5c9  jz      short loc_18000B5A7
0x18000b5cb  mov     rdx, rbx; hResInfo
0x18000b5ce  mov     rcx, rdi; hModule
0x18000b5d1  call    cs:__imp_SizeofResource
0x18000b5d8  nop     dword ptr [rax+rax+00h]
0x18000b5dd  mov     ebx, eax
0x18000b5df  lea     ecx, [rax+1]
0x18000b5e2  cmp     ecx, eax
0x18000b5e4  jnb     short loc_18000B606
0x18000b5e6  lea     rax, [rsp+470h+var_428]
0x18000b5eb  cmp     [rsp+470h+var_430], rax
0x18000b5f0  jz      short loc_18000B5FC
0x18000b5f2  lea     rcx, [rsp+470h+var_430]
0x18000b5f7  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000b5fc  mov     eax, 8007000Eh
0x18000b601  jmp     loc_18000B6C8
0x18000b606  test    ecx, ecx
0x18000b608  jz      short loc_18000B63E
0x18000b60a  xor     edx, edx
0x18000b60c  mov     r8d, ecx
0x18000b60f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000b613  div     r8
0x18000b616  cmp     rax, 2
0x18000b61a  jb      loc_18000B6EB
0x18000b620  lea     rdx, [rcx+rcx]
0x18000b624  cmp     rdx, 400h
0x18000b62b  jbe     short loc_18000B63E
0x18000b62d  lea     rcx, [rsp+470h+var_430]
0x18000b632  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000b637  mov     rax, [rsp+470h+var_430]
0x18000b63c  jmp     short loc_18000B648
0x18000b63e  lea     rax, [rsp+470h+var_428]
0x18000b643  mov     [rsp+470h+var_430], rax
0x18000b648  test    rax, rax
0x18000b64b  jnz     short loc_18000B654
0x18000b64d  mov     ebx, 8007000Eh
0x18000b652  jmp     short loc_18000B6A1
0x18000b654  xor     edx, edx; dwFlags
0x18000b656  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x18000b65a  mov     r9d, ebx; cbMultiByte
0x18000b65d  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x18000b662  mov     r8, rsi; lpMultiByteStr
0x18000b665  lea     ecx, [rdx+3]; CodePage
0x18000b668  call    cs:__imp_MultiByteToWideChar
0x18000b66f  nop     dword ptr [rax+rax+00h]
0x18000b674  test    eax, eax
0x18000b676  jz      loc_18000B5A7
0x18000b67c  mov     r8d, [rbp+370h+arg_20]; int
0x18000b683  xor     ecx, ecx
0x18000b685  mov     edx, eax
0x18000b687  mov     rax, [rsp+470h+var_430]
0x18000b68c  mov     [rax+rdx*2], cx
0x18000b690  lea     rcx, [rsp+470h+var_440]; this
0x18000b695  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x18000b69a  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18000b69f  mov     ebx, eax
0x18000b6a1  mov     rcx, rdi; hLibModule
0x18000b6a4  call    cs:__imp_FreeLibrary
0x18000b6ab  nop     dword ptr [rax+rax+00h]
0x18000b6b0  lea     rax, [rsp+470h+var_428]
0x18000b6b5  cmp     [rsp+470h+var_430], rax
0x18000b6ba  jz      short loc_18000B6C6
0x18000b6bc  lea     rcx, [rsp+470h+var_430]
0x18000b6c1  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x18000b6c6  mov     eax, ebx
0x18000b6c8  mov     rcx, [rbp+370h+var_20]
0x18000b6cf  xor     rcx, rsp; StackCookie
0x18000b6d2  call    __security_check_cookie
0x18000b6d7  mov     rbx, [rsp+470h+arg_0]
0x18000b6df  add     rsp, 460h
0x18000b6e6  pop     rdi
0x18000b6e7  pop     rsi
0x18000b6e8  pop     rbp
0x18000b6e9  retn
0x18000b6eb  mov     ecx, 80070057h; int
0x18000b6f0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
