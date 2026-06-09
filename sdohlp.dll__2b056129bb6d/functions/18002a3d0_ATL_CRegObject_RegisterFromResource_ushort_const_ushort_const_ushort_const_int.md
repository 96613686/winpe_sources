# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18002a3d0`
- end: `0x18002a578`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18002c48c`
- `0x18002c6d4`

## callees

- `0x180024610`
- `0x180024850`
- `0x180024cd0`
- `0x180025d50`
- `0x180025fc0`
- `0x18002a25c`
- `0x18002a3d0`
- `0x180055030`

## import_xrefs

- `KERNEL32!FindResourceExW` at `0x18002a445`
- `KERNEL32!FindResourceExW` at `0x18002a445`
- `KERNEL32!LoadResource` at `0x18002a463`
- `KERNEL32!LoadResource` at `0x18002a463`
- `KERNEL32!SizeofResource` at `0x18002a47c`
- `KERNEL32!SizeofResource` at `0x18002a47c`
- `KERNEL32!MultiByteToWideChar` at `0x18002a501`
- `KERNEL32!MultiByteToWideChar` at `0x18002a501`
- `KERNEL32!LoadLibraryExW` at `0x18002a41a`
- `KERNEL32!LoadLibraryExW` at `0x18002a41a`
- `KERNEL32!FreeLibrary` at `0x18002a536`
- `KERNEL32!FreeLibrary` at `0x18002a536`

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
0x18002a3d0  mov     [rsp+arg_0], rbx
0x18002a3d5  push    rsi
0x18002a3d6  push    rdi
0x18002a3d7  push    r14
0x18002a3d9  sub     rsp, 480h
0x18002a3e0  mov     rax, cs:__security_cookie
0x18002a3e7  xor     rax, rsp
0x18002a3ea  mov     [rsp+498h+var_28], rax
0x18002a3f2  mov     r14, r9
0x18002a3f5  mov     rdi, r8
0x18002a3f8  mov     rax, rdx
0x18002a3fb  xor     ebx, ebx
0x18002a3fd  mov     [rsp+498h+var_450], rbx
0x18002a402  mov     [rsp+498h+var_440], rcx
0x18002a407  mov     [rsp+498h+var_448], rbx
0x18002a40c  mov     [rsp+498h+var_438], rbx
0x18002a411  xor     edx, edx; hFile
0x18002a413  lea     r8d, [rbx+2]; dwFlags
0x18002a417  mov     rcx, rax; lpLibFileName
0x18002a41a  call    cs:__imp_LoadLibraryExW
0x18002a420  mov     rsi, rax
0x18002a423  mov     [rsp+498h+var_460], rax
0x18002a428  test    rax, rax
0x18002a42b  jnz     short loc_18002A439
0x18002a42d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002a432  mov     ebx, eax
0x18002a434  jmp     loc_18002A53D
0x18002a439  xor     r9d, r9d; wLanguage
0x18002a43c  mov     r8, rdi; lpName
0x18002a43f  mov     rdx, r14; lpType
0x18002a442  mov     rcx, rsi; hModule
0x18002a445  call    cs:__imp_FindResourceExW
0x18002a44b  mov     rdi, rax
0x18002a44e  test    rax, rax
0x18002a451  jnz     short loc_18002A45D
0x18002a453  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18002a458  jmp     loc_18002A531
0x18002a45d  mov     rdx, rdi; hResInfo
0x18002a460  mov     rcx, rsi; hModule
0x18002a463  call    cs:__imp_LoadResource
0x18002a469  mov     r14, rax
0x18002a46c  mov     [rsp+498h+var_458], rax
0x18002a471  test    rax, rax
0x18002a474  jz      short loc_18002A453
0x18002a476  mov     rdx, rdi; hResInfo
0x18002a479  mov     rcx, rsi; hModule
0x18002a47c  call    cs:__imp_SizeofResource
0x18002a482  mov     edi, eax
0x18002a484  mov     [rsp+498h+var_468], eax
0x18002a488  inc     eax
0x18002a48a  cmp     eax, edi
0x18002a48c  jnb     short loc_18002A498
0x18002a48e  mov     ebx, 8007000Eh
0x18002a493  jmp     loc_18002A53D
0x18002a498  mov     ecx, eax
0x18002a49a  mov     edx, 2
0x18002a49f  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18002a4a4  cmp     rax, 400h
0x18002a4aa  jbe     short loc_18002A4C0
0x18002a4ac  mov     rdx, rax
0x18002a4af  lea     rcx, [rsp+498h+var_438]
0x18002a4b4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18002a4b9  mov     rax, [rsp+498h+var_438]
0x18002a4be  jmp     short loc_18002A4CA
0x18002a4c0  lea     rax, [rsp+498h+var_430]
0x18002a4c5  mov     [rsp+498h+var_438], rax
0x18002a4ca  jmp     short loc_18002A4E1
0x18002a4cc  xor     ebx, ebx
0x18002a4ce  mov     rsi, [rsp+498h+var_460]
0x18002a4d3  mov     r14, [rsp+498h+var_458]
0x18002a4d8  mov     edi, [rsp+498h+var_468]
0x18002a4dc  mov     rax, [rsp+498h+var_438]
0x18002a4e1  test    rax, rax
0x18002a4e4  jnz     short loc_18002A4ED
0x18002a4e6  mov     ebx, 8007000Eh
0x18002a4eb  jmp     short loc_18002A533
0x18002a4ed  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18002a4f1  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18002a4f6  mov     r9d, edi; cbMultiByte
0x18002a4f9  mov     r8, r14; lpMultiByteStr
0x18002a4fc  xor     edx, edx; dwFlags
0x18002a4fe  lea     ecx, [rdx+3]; CodePage
0x18002a501  call    cs:__imp_MultiByteToWideChar
0x18002a507  test    eax, eax
0x18002a509  jz      loc_18002A453
0x18002a50f  mov     ecx, eax
0x18002a511  mov     rax, [rsp+498h+var_438]
0x18002a516  mov     [rax+rcx*2], bx
0x18002a51a  mov     r8d, [rsp+498h+arg_20]; int
0x18002a522  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18002a527  lea     rcx, [rsp+498h+var_448]; this
0x18002a52c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18002a531  mov     ebx, eax
0x18002a533  mov     rcx, rsi; hLibModule
0x18002a536  call    cs:__imp_FreeLibrary
0x18002a53c  nop
0x18002a53d  lea     rcx, [rsp+498h+var_438]
0x18002a542  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18002a547  nop
0x18002a548  lea     rcx, [rsp+498h+var_450]
0x18002a54d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18002a552  mov     eax, ebx
0x18002a554  mov     rcx, [rsp+498h+var_28]
0x18002a55c  xor     rcx, rsp; StackCookie
0x18002a55f  call    __security_check_cookie
0x18002a564  mov     rbx, [rsp+498h+arg_0]
0x18002a56c  add     rsp, 480h
0x18002a573  pop     r14
0x18002a575  pop     rdi
0x18002a576  pop     rsi
0x18002a577  retn
```
