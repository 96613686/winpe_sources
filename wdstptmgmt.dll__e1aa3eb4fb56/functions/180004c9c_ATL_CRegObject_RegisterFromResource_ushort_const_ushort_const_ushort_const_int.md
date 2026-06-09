# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180004c9c`
- end: `0x180004e69`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `461`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x180005914`

## callees

- `0x180002a88`
- `0x180002ae8`
- `0x180002ba4`
- `0x180003548`
- `0x1800037f8`
- `0x180004b10`
- `0x180004c9c`
- `0x18001e9f0`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180004e20`
- `KERNEL32!FreeLibrary` at `0x180004e20`
- `KERNEL32!LoadLibraryExW` at `0x180004ce6`
- `KERNEL32!LoadLibraryExW` at `0x180004ce6`
- `KERNEL32!MultiByteToWideChar` at `0x180004de5`
- `KERNEL32!MultiByteToWideChar` at `0x180004de5`
- `KERNEL32!SizeofResource` at `0x180004d5a`
- `KERNEL32!SizeofResource` at `0x180004d5a`
- `KERNEL32!LoadResource` at `0x180004d3b`
- `KERNEL32!LoadResource` at `0x180004d3b`
- `KERNEL32!FindResourceExW` at `0x180004d17`
- `KERNEL32!FindResourceExW` at `0x180004d17`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  HMODULE Library; // rax
  HMODULE v8; // rsi
  unsigned int v9; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int Error; // eax
  const CHAR *v13; // r14
  DWORD cchWideChar; // edi
  unsigned __int64 v15; // rax
  WCHAR *lpWideCharStr; // rax
  int v17; // eax
  HMODULE v19; // [rsp+38h] [rbp-460h]
  __int64 v20; // [rsp+48h] [rbp-450h] BYREF
  _QWORD v21[2]; // [rsp+50h] [rbp-448h] BYREF
  LPWSTR v22; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v23[1032]; // [rsp+68h] [rbp-430h] BYREF

  v20 = 0;
  v21[1] = this;
  v21[0] = 0;
  v22 = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  v19 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, a3, 0);
    v11 = Resource;
    if ( !Resource )
      goto LABEL_4;
    v13 = (const CHAR *)LoadResource(v8, Resource);
    if ( !v13 )
      goto LABEL_4;
    cchWideChar = SizeofResource(v8, v11);
    if ( cchWideChar + 1 < cchWideChar )
    {
      v9 = -2147024882;
      goto LABEL_17;
    }
    try
    {
      v15 = ATL::AtlMultiplyThrow<unsigned __int64>();
      if ( v15 <= 0x400 )
      {
        lpWideCharStr = (WCHAR *)v23;
        v22 = (LPWSTR)v23;
      }
      else
      {
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::AllocateHeap(&v22, v15);
        lpWideCharStr = v22;
      }
    }
    catch ( ... )
    {
      v8 = v19;
      lpWideCharStr = v22;
    }
    if ( !lpWideCharStr )
    {
      v9 = -2147024882;
LABEL_16:
      FreeLibrary(v8);
      goto LABEL_17;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v22[v17] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
    }
    else
    {
LABEL_4:
      Error = ATL::AtlHresultFromLastError();
    }
    v9 = Error;
    goto LABEL_16;
  }
  v9 = ATL::AtlHresultFromLastError();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x180004c9c  mov     [rsp+arg_0], rbx
0x180004ca1  push    rsi
0x180004ca2  push    rdi
0x180004ca3  push    r14
0x180004ca5  sub     rsp, 480h
0x180004cac  mov     rax, cs:__security_cookie
0x180004cb3  xor     rax, rsp
0x180004cb6  mov     [rsp+498h+var_28], rax
0x180004cbe  mov     r14, r9
0x180004cc1  mov     rdi, r8
0x180004cc4  mov     rax, rdx
0x180004cc7  xor     ebx, ebx
0x180004cc9  mov     [rsp+498h+var_450], rbx
0x180004cce  mov     [rsp+498h+var_440], rcx
0x180004cd3  mov     [rsp+498h+var_448], rbx
0x180004cd8  mov     [rsp+498h+var_438], rbx
0x180004cdd  xor     edx, edx; hFile
0x180004cdf  lea     r8d, [rbx+2]; dwFlags
0x180004ce3  mov     rcx, rax; lpLibFileName
0x180004ce6  call    cs:__imp_LoadLibraryExW
0x180004ced  nop     dword ptr [rax+rax+00h]
0x180004cf2  mov     rsi, rax
0x180004cf5  mov     [rsp+498h+var_460], rax
0x180004cfa  test    rax, rax
0x180004cfd  jnz     short loc_180004D0B
0x180004cff  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004d04  mov     ebx, eax
0x180004d06  jmp     loc_180004E2D
0x180004d0b  xor     r9d, r9d; wLanguage
0x180004d0e  mov     r8, rdi; lpName
0x180004d11  mov     rdx, r14; lpType
0x180004d14  mov     rcx, rsi; hModule
0x180004d17  call    cs:__imp_FindResourceExW
0x180004d1e  nop     dword ptr [rax+rax+00h]
0x180004d23  mov     rdi, rax
0x180004d26  test    rax, rax
0x180004d29  jnz     short loc_180004D35
0x180004d2b  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180004d30  jmp     loc_180004E1B
0x180004d35  mov     rdx, rdi; hResInfo
0x180004d38  mov     rcx, rsi; hModule
0x180004d3b  call    cs:__imp_LoadResource
0x180004d42  nop     dword ptr [rax+rax+00h]
0x180004d47  mov     r14, rax
0x180004d4a  mov     [rsp+498h+var_458], rax
0x180004d4f  test    rax, rax
0x180004d52  jz      short loc_180004D2B
0x180004d54  mov     rdx, rdi; hResInfo
0x180004d57  mov     rcx, rsi; hModule
0x180004d5a  call    cs:__imp_SizeofResource
0x180004d61  nop     dword ptr [rax+rax+00h]
0x180004d66  mov     edi, eax
0x180004d68  mov     [rsp+498h+var_468], eax
0x180004d6c  inc     eax
0x180004d6e  cmp     eax, edi
0x180004d70  jnb     short loc_180004D7C
0x180004d72  mov     ebx, 8007000Eh
0x180004d77  jmp     loc_180004E2D
0x180004d7c  mov     ecx, eax
0x180004d7e  mov     edx, 2
0x180004d83  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180004d88  cmp     rax, 400h
0x180004d8e  jbe     short loc_180004DA4
0x180004d90  mov     rdx, rax
0x180004d93  lea     rcx, [rsp+498h+var_438]
0x180004d98  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x180004d9d  mov     rax, [rsp+498h+var_438]
0x180004da2  jmp     short loc_180004DAE
0x180004da4  lea     rax, [rsp+498h+var_430]
0x180004da9  mov     [rsp+498h+var_438], rax
0x180004dae  jmp     short loc_180004DC5
0x180004db0  xor     ebx, ebx
0x180004db2  mov     rsi, [rsp+498h+var_460]
0x180004db7  mov     r14, [rsp+498h+var_458]
0x180004dbc  mov     edi, [rsp+498h+var_468]
0x180004dc0  mov     rax, [rsp+498h+var_438]
0x180004dc5  test    rax, rax
0x180004dc8  jnz     short loc_180004DD1
0x180004dca  mov     ebx, 8007000Eh
0x180004dcf  jmp     short loc_180004E1D
0x180004dd1  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180004dd5  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180004dda  mov     r9d, edi; cbMultiByte
0x180004ddd  mov     r8, r14; lpMultiByteStr
0x180004de0  xor     edx, edx; dwFlags
0x180004de2  lea     ecx, [rdx+3]; CodePage
0x180004de5  call    cs:__imp_MultiByteToWideChar
0x180004dec  nop     dword ptr [rax+rax+00h]
0x180004df1  test    eax, eax
0x180004df3  jz      loc_180004D2B
0x180004df9  mov     ecx, eax
0x180004dfb  mov     rax, [rsp+498h+var_438]
0x180004e00  mov     [rax+rcx*2], bx
0x180004e04  mov     r8d, [rsp+498h+arg_20]; int
0x180004e0c  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180004e11  lea     rcx, [rsp+498h+var_448]; this
0x180004e16  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180004e1b  mov     ebx, eax
0x180004e1d  mov     rcx, rsi; hLibModule
0x180004e20  call    cs:__imp_FreeLibrary
0x180004e27  nop     dword ptr [rax+rax+00h]
0x180004e2c  nop
0x180004e2d  lea     rcx, [rsp+498h+var_438]
0x180004e32  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180004e37  nop
0x180004e38  lea     rcx, [rsp+498h+var_450]
0x180004e3d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180004e42  mov     eax, ebx
0x180004e44  mov     rcx, [rsp+498h+var_28]
0x180004e4c  xor     rcx, rsp; StackCookie
0x180004e4f  call    __security_check_cookie
0x180004e54  mov     rbx, [rsp+498h+arg_0]
0x180004e5c  add     rsp, 480h
0x180004e63  pop     r14
0x180004e65  pop     rdi
0x180004e66  pop     rsi
0x180004e67  retn
```
