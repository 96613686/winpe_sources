# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180008e78`
- end: `0x180009024`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `428`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x180009a6c`
- `0x180009d8c`

## callees

- `0x180007a04`
- `0x180007bf4`
- `0x1800083c4`
- `0x180008ce8`
- `0x180008e78`
- `0x1800157f0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180008fe4`
- `KERNEL32!FreeLibrary` at `0x180008fe4`
- `KERNEL32!LoadLibraryExW` at `0x180008ec9`
- `KERNEL32!LoadLibraryExW` at `0x180008ec9`
- `KERNEL32!MultiByteToWideChar` at `0x180008fae`
- `KERNEL32!MultiByteToWideChar` at `0x180008fae`
- `KERNEL32!SizeofResource` at `0x180008f21`
- `KERNEL32!SizeofResource` at `0x180008f21`
- `KERNEL32!LoadResource` at `0x180008f0d`
- `KERNEL32!LoadResource` at `0x180008f0d`
- `KERNEL32!FindResourceExW` at `0x180008eef`
- `KERNEL32!FindResourceExW` at `0x180008eef`

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
0x180008e78  mov     [rsp-8+arg_0], rbx
0x180008e7d  push    rbp
0x180008e7e  push    rsi
0x180008e7f  push    rdi
0x180008e80  lea     rbp, [rsp-360h]
0x180008e88  sub     rsp, 460h
0x180008e8f  mov     rax, cs:__security_cookie
0x180008e96  xor     rax, rsp
0x180008e99  mov     [rbp+370h+var_20], rax
0x180008ea0  mov     rax, rdx
0x180008ea3  mov     [rsp+470h+var_438], rcx
0x180008ea8  xor     edx, edx; hFile
0x180008eaa  mov     [rsp+470h+var_440], 0
0x180008eb3  mov     rbx, r8
0x180008eb6  mov     [rsp+470h+var_430], 0
0x180008ebf  mov     rcx, rax; lpLibFileName
0x180008ec2  mov     rsi, r9
0x180008ec5  lea     r8d, [rdx+2]; dwFlags
0x180008ec9  call    cs:__imp_LoadLibraryExW
0x180008ecf  mov     rdi, rax
0x180008ed2  test    rax, rax
0x180008ed5  jnz     short loc_180008EE3
0x180008ed7  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008edc  mov     ebx, eax
0x180008ede  jmp     loc_180008FEA
0x180008ee3  xor     r9d, r9d; wLanguage
0x180008ee6  mov     r8, rbx; lpName
0x180008ee9  mov     rdx, rsi; lpType
0x180008eec  mov     rcx, rdi; hModule
0x180008eef  call    cs:__imp_FindResourceExW
0x180008ef5  mov     rbx, rax
0x180008ef8  test    rax, rax
0x180008efb  jnz     short loc_180008F07
0x180008efd  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180008f02  jmp     loc_180008FDF
0x180008f07  mov     rdx, rbx; hResInfo
0x180008f0a  mov     rcx, rdi; hModule
0x180008f0d  call    cs:__imp_LoadResource
0x180008f13  mov     rsi, rax
0x180008f16  test    rax, rax
0x180008f19  jz      short loc_180008EFD
0x180008f1b  mov     rdx, rbx; hResInfo
0x180008f1e  mov     rcx, rdi; hModule
0x180008f21  call    cs:__imp_SizeofResource
0x180008f27  mov     ebx, eax
0x180008f29  lea     ecx, [rax+1]
0x180008f2c  cmp     ecx, eax
0x180008f2e  jnb     short loc_180008F50
0x180008f30  lea     rax, [rsp+470h+var_428]
0x180008f35  cmp     [rsp+470h+var_430], rax
0x180008f3a  jz      short loc_180008F46
0x180008f3c  lea     rcx, [rsp+470h+var_430]
0x180008f41  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180008f46  mov     eax, 8007000Eh
0x180008f4b  jmp     loc_180009002
0x180008f50  test    ecx, ecx
0x180008f52  jz      short loc_180008F84
0x180008f54  xor     edx, edx
0x180008f56  mov     r8d, ecx
0x180008f59  or      rax, 0FFFFFFFFFFFFFFFFh
0x180008f5d  div     r8
0x180008f60  cmp     rax, 2
0x180008f64  jb      short loc_180008F84
0x180008f66  lea     rdx, [rcx+rcx]
0x180008f6a  cmp     rdx, 400h
0x180008f71  jbe     short loc_180008F84
0x180008f73  lea     rcx, [rsp+470h+var_430]
0x180008f78  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180008f7d  mov     rax, [rsp+470h+var_430]
0x180008f82  jmp     short loc_180008F8E
0x180008f84  lea     rax, [rsp+470h+var_428]
0x180008f89  mov     [rsp+470h+var_430], rax
0x180008f8e  test    rax, rax
0x180008f91  jnz     short loc_180008F9A
0x180008f93  mov     ebx, 8007000Eh
0x180008f98  jmp     short loc_180008FE1
0x180008f9a  xor     edx, edx; dwFlags
0x180008f9c  mov     [rsp+470h+cchWideChar], ebx; cchWideChar
0x180008fa0  mov     r9d, ebx; cbMultiByte
0x180008fa3  mov     [rsp+470h+lpWideCharStr], rax; lpWideCharStr
0x180008fa8  mov     r8, rsi; lpMultiByteStr
0x180008fab  lea     ecx, [rdx+3]; CodePage
0x180008fae  call    cs:__imp_MultiByteToWideChar
0x180008fb4  test    eax, eax
0x180008fb6  jz      loc_180008EFD
0x180008fbc  mov     r8d, [rbp+370h+arg_20]; int
0x180008fc3  xor     ecx, ecx
0x180008fc5  mov     edx, eax
0x180008fc7  mov     rax, [rsp+470h+var_430]
0x180008fcc  mov     [rax+rdx*2], cx
0x180008fd0  lea     rcx, [rsp+470h+var_440]; this
0x180008fd5  mov     rdx, [rsp+470h+var_430]; unsigned __int16 *
0x180008fda  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180008fdf  mov     ebx, eax
0x180008fe1  mov     rcx, rdi; hLibModule
0x180008fe4  call    cs:__imp_FreeLibrary
0x180008fea  lea     rax, [rsp+470h+var_428]
0x180008fef  cmp     [rsp+470h+var_430], rax
0x180008ff4  jz      short loc_180009000
0x180008ff6  lea     rcx, [rsp+470h+var_430]
0x180008ffb  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180009000  mov     eax, ebx
0x180009002  mov     rcx, [rbp+370h+var_20]
0x180009009  xor     rcx, rsp; StackCookie
0x18000900c  call    __security_check_cookie
0x180009011  mov     rbx, [rsp+470h+arg_0]
0x180009019  add     rsp, 460h
0x180009020  pop     rdi
0x180009021  pop     rsi
0x180009022  pop     rbp
0x180009023  retn
```
