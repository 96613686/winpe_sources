# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18001ac10`
- end: `0x18001adb8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `424`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18001bccc`
- `0x18001bf44`

## callees

- `0x1800034b0`
- `0x180014ae8`
- `0x180014f98`
- `0x180015750`
- `0x180016c74`
- `0x180016f48`
- `0x18001aa9c`
- `0x18001ac10`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ad76`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18001ad76`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ac5a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001ac5a`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001acbc`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x18001acbc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001aca3`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x18001aca3`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ac85`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x18001ac85`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ad41`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x18001ad41`

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
0x18001ac10  mov     [rsp+arg_0], rbx
0x18001ac15  push    rsi
0x18001ac16  push    rdi
0x18001ac17  push    r14
0x18001ac19  sub     rsp, 480h
0x18001ac20  mov     rax, cs:__security_cookie
0x18001ac27  xor     rax, rsp
0x18001ac2a  mov     [rsp+498h+var_28], rax
0x18001ac32  mov     r14, r9
0x18001ac35  mov     rdi, r8
0x18001ac38  mov     rax, rdx
0x18001ac3b  xor     ebx, ebx
0x18001ac3d  mov     [rsp+498h+var_450], rbx
0x18001ac42  mov     [rsp+498h+var_440], rcx
0x18001ac47  mov     [rsp+498h+var_448], rbx
0x18001ac4c  mov     [rsp+498h+var_438], rbx
0x18001ac51  xor     edx, edx; hFile
0x18001ac53  lea     r8d, [rbx+2]; dwFlags
0x18001ac57  mov     rcx, rax; lpLibFileName
0x18001ac5a  call    cs:__imp_LoadLibraryExW
0x18001ac60  mov     rsi, rax
0x18001ac63  mov     [rsp+498h+var_460], rax
0x18001ac68  test    rax, rax
0x18001ac6b  jnz     short loc_18001AC79
0x18001ac6d  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ac72  mov     ebx, eax
0x18001ac74  jmp     loc_18001AD7D
0x18001ac79  xor     r9d, r9d; wLanguage
0x18001ac7c  mov     r8, rdi; lpName
0x18001ac7f  mov     rdx, r14; lpType
0x18001ac82  mov     rcx, rsi; hModule
0x18001ac85  call    cs:__imp_FindResourceExW
0x18001ac8b  mov     rdi, rax
0x18001ac8e  test    rax, rax
0x18001ac91  jnz     short loc_18001AC9D
0x18001ac93  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x18001ac98  jmp     loc_18001AD71
0x18001ac9d  mov     rdx, rdi; hResInfo
0x18001aca0  mov     rcx, rsi; hModule
0x18001aca3  call    cs:__imp_LoadResource
0x18001aca9  mov     r14, rax
0x18001acac  mov     [rsp+498h+var_458], rax
0x18001acb1  test    rax, rax
0x18001acb4  jz      short loc_18001AC93
0x18001acb6  mov     rdx, rdi; hResInfo
0x18001acb9  mov     rcx, rsi; hModule
0x18001acbc  call    cs:__imp_SizeofResource
0x18001acc2  mov     edi, eax
0x18001acc4  mov     [rsp+498h+var_468], eax
0x18001acc8  inc     eax
0x18001acca  cmp     eax, edi
0x18001accc  jnb     short loc_18001ACD8
0x18001acce  mov     ebx, 8007000Eh
0x18001acd3  jmp     loc_18001AD7D
0x18001acd8  mov     ecx, eax
0x18001acda  mov     edx, 2
0x18001acdf  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x18001ace4  cmp     rax, 400h
0x18001acea  jbe     short loc_18001AD00
0x18001acec  mov     rdx, rax
0x18001acef  lea     rcx, [rsp+498h+var_438]
0x18001acf4  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18001acf9  mov     rax, [rsp+498h+var_438]
0x18001acfe  jmp     short loc_18001AD0A
0x18001ad00  lea     rax, [rsp+498h+var_430]
0x18001ad05  mov     [rsp+498h+var_438], rax
0x18001ad0a  jmp     short loc_18001AD21
0x18001ad0c  xor     ebx, ebx
0x18001ad0e  mov     rsi, [rsp+498h+var_460]
0x18001ad13  mov     r14, [rsp+498h+var_458]
0x18001ad18  mov     edi, [rsp+498h+var_468]
0x18001ad1c  mov     rax, [rsp+498h+var_438]
0x18001ad21  test    rax, rax
0x18001ad24  jnz     short loc_18001AD2D
0x18001ad26  mov     ebx, 8007000Eh
0x18001ad2b  jmp     short loc_18001AD73
0x18001ad2d  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x18001ad31  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x18001ad36  mov     r9d, edi; cbMultiByte
0x18001ad39  mov     r8, r14; lpMultiByteStr
0x18001ad3c  xor     edx, edx; dwFlags
0x18001ad3e  lea     ecx, [rdx+3]; CodePage
0x18001ad41  call    cs:__imp_MultiByteToWideChar
0x18001ad47  test    eax, eax
0x18001ad49  jz      loc_18001AC93
0x18001ad4f  mov     ecx, eax
0x18001ad51  mov     rax, [rsp+498h+var_438]
0x18001ad56  mov     [rax+rcx*2], bx
0x18001ad5a  mov     r8d, [rsp+498h+arg_20]; int
0x18001ad62  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x18001ad67  lea     rcx, [rsp+498h+var_448]; this
0x18001ad6c  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x18001ad71  mov     ebx, eax
0x18001ad73  mov     rcx, rsi; hLibModule
0x18001ad76  call    cs:__imp_FreeLibrary
0x18001ad7c  nop
0x18001ad7d  lea     rcx, [rsp+498h+var_438]
0x18001ad82  call    ??1?$CTempBuffer@E$0BAA@VCCRTAllocator@ATL@@@ATL@@QEAA@XZ; ATL::CTempBuffer<uchar,256,ATL::CCRTAllocator>::~CTempBuffer<uchar,256,ATL::CCRTAllocator>(void)
0x18001ad87  nop
0x18001ad88  lea     rcx, [rsp+498h+var_450]
0x18001ad8d  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18001ad92  mov     eax, ebx
0x18001ad94  mov     rcx, [rsp+498h+var_28]
0x18001ad9c  xor     rcx, rsp; StackCookie
0x18001ad9f  call    __security_check_cookie
0x18001ada4  mov     rbx, [rsp+498h+arg_0]
0x18001adac  add     rsp, 480h
0x18001adb3  pop     r14
0x18001adb5  pop     rdi
0x18001adb6  pop     rsi
0x18001adb7  retn
```
