# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x18000764c`
- end: `0x180007816`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `458`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `loader_planting`

## callers

- `0x18000830c`
- `0x18000858c`

## callees

- `0x180002570`
- `0x1800056c0`
- `0x180005798`
- `0x1800062a8`
- `0x18000655c`
- `0x180006db8`
- `0x1800074dc`
- `0x18000764c`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800076f8`
- `api-ms-win-core-libraryloader-l1-2-0!SizeofResource` at `0x1800076f8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800076df`
- `api-ms-win-core-libraryloader-l1-2-0!LoadResource` at `0x1800076df`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800076c1`
- `api-ms-win-core-libraryloader-l1-2-0!FindResourceExW` at `0x1800076c1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007696`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x180007696`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800077c8`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800077c8`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007793`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x180007793`

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
  unsigned int Error; // ebx
  HRSRC Resource; // rax
  HRSRC v11; // rdi
  unsigned int v12; // eax
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
  if ( !Library )
  {
    Error = ATL::AtlHresultFromLastError();
    goto LABEL_19;
  }
  Resource = FindResourceExW(Library, a4, a3, 0);
  v11 = Resource;
  if ( !Resource )
    goto LABEL_4;
  v13 = (const CHAR *)LoadResource(v8, Resource);
  if ( !v13 )
    goto LABEL_4;
  cchWideChar = SizeofResource(v8, v11);
  if ( cchWideChar + 1 >= cchWideChar )
  {
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
      Error = -2147024882;
LABEL_18:
      FreeLibrary(v8);
LABEL_19:
      if ( v22 != (LPWSTR)v23 )
        ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v22);
      goto LABEL_21;
    }
    v17 = MultiByteToWideChar(3u, 0, v13, cchWideChar, lpWideCharStr, cchWideChar);
    if ( v17 )
    {
      v22[v17] = 0;
      v12 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)v21, v22, a5);
      goto LABEL_17;
    }
LABEL_4:
    v12 = ATL::AtlHresultFromLastError();
LABEL_17:
    Error = v12;
    goto LABEL_18;
  }
  if ( v22 != (LPWSTR)v23 )
    ATL::CTempBuffer<unsigned short,1024,ATL::CCRTAllocator>::FreeHeap(&v22);
  Error = -2147024882;
LABEL_21:
  ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v20);
  return Error;
}

```

## disassembly

```asm
0x18000764c  mov     [rsp+arg_0], rbx
0x180007651  push    rsi
0x180007652  push    rdi
0x180007653  push    r14
0x180007655  sub     rsp, 480h
0x18000765c  mov     rax, cs:__security_cookie
0x180007663  xor     rax, rsp
0x180007666  mov     [rsp+498h+var_28], rax
0x18000766e  mov     r14, r9
0x180007671  mov     rdi, r8
0x180007674  mov     rax, rdx
0x180007677  xor     ebx, ebx
0x180007679  mov     [rsp+498h+var_450], rbx
0x18000767e  mov     [rsp+498h+var_440], rcx
0x180007683  mov     [rsp+498h+var_448], rbx
0x180007688  mov     [rsp+498h+var_438], rbx
0x18000768d  xor     edx, edx; hFile
0x18000768f  lea     r8d, [rbx+2]; dwFlags
0x180007693  mov     rcx, rax; lpLibFileName
0x180007696  call    cs:__imp_LoadLibraryExW
0x18000769c  mov     rsi, rax
0x18000769f  mov     [rsp+498h+var_460], rax
0x1800076a4  test    rax, rax
0x1800076a7  jnz     short loc_1800076B5
0x1800076a9  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800076ae  mov     ebx, eax
0x1800076b0  jmp     loc_1800077CF
0x1800076b5  xor     r9d, r9d; wLanguage
0x1800076b8  mov     r8, rdi; lpName
0x1800076bb  mov     rdx, r14; lpType
0x1800076be  mov     rcx, rsi; hModule
0x1800076c1  call    cs:__imp_FindResourceExW
0x1800076c7  mov     rdi, rax
0x1800076ca  test    rax, rax
0x1800076cd  jnz     short loc_1800076D9
0x1800076cf  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800076d4  jmp     loc_1800077C3
0x1800076d9  mov     rdx, rdi; hResInfo
0x1800076dc  mov     rcx, rsi; hModule
0x1800076df  call    cs:__imp_LoadResource
0x1800076e5  mov     r14, rax
0x1800076e8  mov     [rsp+498h+var_458], rax
0x1800076ed  test    rax, rax
0x1800076f0  jz      short loc_1800076CF
0x1800076f2  mov     rdx, rdi; hResInfo
0x1800076f5  mov     rcx, rsi; hModule
0x1800076f8  call    cs:__imp_SizeofResource
0x1800076fe  mov     edi, eax
0x180007700  mov     [rsp+498h+var_468], eax
0x180007704  inc     eax
0x180007706  cmp     eax, edi
0x180007708  jnb     short loc_18000772A
0x18000770a  lea     rax, [rsp+498h+var_430]
0x18000770f  cmp     [rsp+498h+var_438], rax
0x180007714  jz      short loc_180007720
0x180007716  lea     rcx, [rsp+498h+var_438]
0x18000771b  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180007720  mov     ebx, 8007000Eh
0x180007725  jmp     loc_1800077E6
0x18000772a  mov     ecx, eax
0x18000772c  mov     edx, 2
0x180007731  call    ??$AtlMultiplyThrow@_K@ATL@@YA_K_K0@Z; ATL::AtlMultiplyThrow<unsigned __int64>(unsigned __int64,unsigned __int64)
0x180007736  cmp     rax, 400h
0x18000773c  jbe     short loc_180007752
0x18000773e  mov     rdx, rax
0x180007741  lea     rcx, [rsp+498h+var_438]
0x180007746  call    ?AllocateHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x18000774b  mov     rax, [rsp+498h+var_438]
0x180007750  jmp     short loc_18000775C
0x180007752  lea     rax, [rsp+498h+var_430]
0x180007757  mov     [rsp+498h+var_438], rax
0x18000775c  jmp     short loc_180007773
0x18000775e  xor     ebx, ebx
0x180007760  mov     rsi, [rsp+498h+var_460]
0x180007765  mov     r14, [rsp+498h+var_458]
0x18000776a  mov     edi, [rsp+498h+var_468]
0x18000776e  mov     rax, [rsp+498h+var_438]
0x180007773  test    rax, rax
0x180007776  jnz     short loc_18000777F
0x180007778  mov     ebx, 8007000Eh
0x18000777d  jmp     short loc_1800077C5
0x18000777f  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x180007783  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x180007788  mov     r9d, edi; cbMultiByte
0x18000778b  mov     r8, r14; lpMultiByteStr
0x18000778e  xor     edx, edx; dwFlags
0x180007790  lea     ecx, [rdx+3]; CodePage
0x180007793  call    cs:__imp_MultiByteToWideChar
0x180007799  test    eax, eax
0x18000779b  jz      loc_1800076CF
0x1800077a1  mov     ecx, eax
0x1800077a3  mov     rax, [rsp+498h+var_438]
0x1800077a8  mov     [rax+rcx*2], bx
0x1800077ac  mov     r8d, [rsp+498h+arg_20]; int
0x1800077b4  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x1800077b9  lea     rcx, [rsp+498h+var_448]; this
0x1800077be  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x1800077c3  mov     ebx, eax
0x1800077c5  mov     rcx, rsi; hLibModule
0x1800077c8  call    cs:__imp_FreeLibrary
0x1800077ce  nop
0x1800077cf  lea     rax, [rsp+498h+var_430]
0x1800077d4  cmp     [rsp+498h+var_438], rax
0x1800077d9  jz      short loc_1800077E6
0x1800077db  lea     rcx, [rsp+498h+var_438]
0x1800077e0  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800077e5  nop
0x1800077e6  lea     rcx, [rsp+498h+var_450]
0x1800077eb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1800077f0  mov     eax, ebx
0x1800077f2  mov     rcx, [rsp+498h+var_28]
0x1800077fa  xor     rcx, rsp; StackCookie
0x1800077fd  call    __security_check_cookie
0x180007802  mov     rbx, [rsp+498h+arg_0]
0x18000780a  add     rsp, 480h
0x180007811  pop     r14
0x180007813  pop     rdi
0x180007814  pop     rsi
0x180007815  retn
```
