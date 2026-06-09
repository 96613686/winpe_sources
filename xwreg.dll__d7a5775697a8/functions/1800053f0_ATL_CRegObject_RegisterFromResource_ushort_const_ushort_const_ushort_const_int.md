# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x1800053f0`
- end: `0x180005598`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x1800060fc`
- `0x180006374`

## callees

- `0x180002ab8`
- `0x180002b1c`
- `0x180002d54`
- `0x180003934`
- `0x180003b90`
- `0x18000527c`
- `0x1800053f0`
- `0x180012800`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005483`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x180005483`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000543a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000543a`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005465`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x180005465`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000549c`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18000549c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005556`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180005556`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005521`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180005521`

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
  unsigned int LastErrorHRESULT; // eax
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
      LastErrorHRESULT = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
    }
    else
    {
LABEL_4:
      LastErrorHRESULT = GetLastErrorHRESULT();
    }
    v9 = LastErrorHRESULT;
    goto LABEL_16;
  }
  v9 = GetLastErrorHRESULT();
LABEL_17:
  ATL::CTempBuffer<unsigned char,256,ATL::CCRTAllocator>::~CTempBuffer<unsigned char,256,ATL::CCRTAllocator>(&v22);
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return v9;
}

```

## disassembly

```asm
0x1800053f0  mov     [rsp+arg_0], rbx
0x1800053f5  push    rsi
0x1800053f6  push    rdi
0x1800053f7  push    r14
0x1800053f9  sub     rsp, 480h
0x180005400  mov     rax, cs:__security_cookie
0x180005407  xor     rax, rsp
0x18000540a  mov     [rsp+498h+var_28], rax
0x180005412  mov     r14, r9
0x180005415  mov     rdi, r8
0x180005418  mov     rax, rdx
0x18000541b  xor     ebx, ebx
0x18000541d  mov     [rsp+498h+var_450], rbx
0x180005422  mov     [rsp+498h+var_440], rcx
0x180005427  mov     [rsp+498h+var_448], rbx
0x18000542c  mov     [rsp+498h+var_438], rbx
0x180005431  xor     edx, edx; hFile
0x180005433  lea     r8d, [rbx+2]; dwFlags
0x180005437  mov     rcx, rax; lpLibFileName
0x18000543a  call    cs:__imp_LoadLibraryExW
0x180005440  mov     rsi, rax
0x180005443  mov     [rsp+498h+var_460], rax
0x180005448  test    rax, rax
0x18000544b  jnz     short loc_180005459
0x18000544d  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180005452  mov     ebx, eax
0x180005454  jmp     loc_18000555D
0x180005459  xor     r9d, r9d; wLanguage
0x18000545c  mov     r8, rdi; lpName
0x18000545f  mov     rdx, r14; lpType
0x180005462  mov     rcx, rsi; hModule
0x180005465  call    cs:__imp_FindResourceExW
0x18000546b  mov     rdi, rax
0x18000546e  test    rax, rax
0x180005471  jnz     short loc_18000547D
0x180005473  call    ?GetLastErrorHRESULT@@YAJXZ; GetLastErrorHRESULT(void)
0x180005478  jmp     loc_180005551
0x18000547d  mov     rdx, rdi; hResInfo
0x180005480  mov     rcx, rsi; hModule
0x180005483  call    cs:__imp_LoadResource
0x180005489  mov     r14, rax
0x18000548c  mov     [rsp+498h+var_458], rax
0x180005491  test    rax, rax
0x180005494  jz      short loc_180005473
0x180005496  mov     rdx, rdi; hResInfo
0x180005499  mov     rcx, rsi; hModule
0x18000549c  call    cs:__imp_SizeofResource
0x1800054a2  mov     edi, eax
0x1800054a4  mov     [rsp+498h+var_468], eax
0x1800054a8  inc     eax
0x1800054aa  cmp     eax, edi
0x1800054ac  jnb     short loc_1800054B8
0x1800054ae  mov     ebx, 8007000Eh
0x1800054b3  jmp     loc_18000555D
0x1800054b8  mov     ecx, eax
0x1800054ba  mov     edx, 2
0x1800054bf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x1800054c4  cmp     rax, 400h
0x1800054ca  jbe     short loc_1800054E0
0x1800054cc  mov     rdx, rax
0x1800054cf  lea     rcx, [rsp+498h+var_438]
0x1800054d4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800054d9  mov     rax, [rsp+498h+var_438]
0x1800054de  jmp     short loc_1800054EA
0x1800054e0  lea     rax, [rsp+498h+var_430]
0x1800054e5  mov     [rsp+498h+var_438], rax
0x1800054ea  jmp     short loc_180005501
0x1800054ec  xor     ebx, ebx
0x1800054ee  mov     rsi, [rsp+498h+var_460]
0x1800054f3  mov     r14, [rsp+498h+var_458]
0x1800054f8  mov     edi, [rsp+498h+var_468]
0x1800054fc  mov     rax, [rsp+498h+var_438]
0x180005501  test    rax, rax
0x180005504  jnz     short loc_18000550D
0x180005506  mov     ebx, 8007000Eh
0x18000550b  jmp     short loc_180005553
0x18000550d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180005511  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180005516  mov     r9d, edi; cbMultiByte
0x180005519  mov     r8, r14; lpMultiByteStr
0x18000551c  xor     edx, edx; dwFlags
0x18000551e  lea     ecx, [rdx+3]; CodePage
0x180005521  call    cs:__imp_MultiByteToWideChar
0x180005527  test    eax, eax
0x180005529  jz      loc_180005473
0x18000552f  mov     ecx, eax
0x180005531  mov     rax, [rsp+498h+var_438]
0x180005536  mov     [rax+rcx*2], bx
0x18000553a  mov     r8d, [rsp+498h+arg_20]; int
0x180005542  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x180005547  lea     rcx, [rsp+498h+var_448]; this
0x18000554c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x180005551  mov     ebx, eax
0x180005553  mov     rcx, rsi; hLibModule
0x180005556  call    cs:__imp_FreeLibrary
0x18000555c  nop
0x18000555d  lea     rcx, [rsp+498h+var_438]
0x180005562  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x180005567  nop
0x180005568  lea     rcx, [rsp+498h+var_450]
0x18000556d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x180005572  mov     eax, ebx
0x180005574  mov     rcx, [rsp+498h+var_28]
0x18000557c  xor     rcx, rsp; StackCookie
0x18000557f  call    __security_check_cookie
0x180005584  mov     rbx, [rsp+498h+arg_0]
0x18000558c  add     rsp, 480h
0x180005593  pop     r14
0x180005595  pop     rdi
0x180005596  pop     rsi
0x180005597  retn
```
