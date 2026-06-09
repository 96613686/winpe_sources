# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x140003fac`
- end: `0x140004188`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `476`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `2`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x140004d0c`
- `0x140005034`

## callees

- `0x1400014f0`
- `0x140002e98`
- `0x140002fc8`
- `0x140003004`
- `0x14000339c`
- `0x140003e1c`
- `0x140003fac`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x140004138`
- `KERNEL32!FreeLibrary` at `0x140004138`
- `KERNEL32!LoadLibraryExW` at `0x140003ff6`
- `KERNEL32!LoadLibraryExW` at `0x140003ff6`
- `KERNEL32!MultiByteToWideChar` at `0x140004103`
- `KERNEL32!MultiByteToWideChar` at `0x140004103`
- `KERNEL32!SizeofResource` at `0x140004058`
- `KERNEL32!SizeofResource` at `0x140004058`
- `KERNEL32!LoadResource` at `0x14000403f`
- `KERNEL32!LoadResource` at `0x14000403f`
- `KERNEL32!FindResourceExW` at `0x140004021`
- `KERNEL32!FindResourceExW` at `0x140004021`

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
  DWORD v15; // eax
  WCHAR *lpWideCharStr; // rax
  int v18; // eax
  _QWORD v19[3]; // [rsp+48h] [rbp-450h] BYREF
  LPWSTR v20; // [rsp+60h] [rbp-438h] BYREF
  _BYTE v21[1032]; // [rsp+68h] [rbp-430h] BYREF

  v19[2] = 0;
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
  if ( cchWideChar + 1 >= cchWideChar )
  {
    if ( cchWideChar == -1 )
      goto LABEL_14;
    if ( 0xFFFFFFFFFFFFFFFFuLL / v15 < 2 )
      ATL::AtlThrowImpl(-2147024809);
    if ( 2 * (unsigned __int64)v15 <= 0x400 )
    {
LABEL_14:
      lpWideCharStr = (WCHAR *)v21;
      v20 = (LPWSTR)v21;
    }
    else
    {
      ATL::CTempBuffer<unsigned short,128,ATL::CCRTAllocator>::AllocateHeap(&v20, 2LL * v15);
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
0x140003fac  mov     [rsp+arg_0], rbx
0x140003fb1  push    rsi
0x140003fb2  push    rdi
0x140003fb3  push    r14
0x140003fb5  sub     rsp, 480h
0x140003fbc  mov     rax, cs:__security_cookie
0x140003fc3  xor     rax, rsp
0x140003fc6  mov     [rsp+498h+var_28], rax
0x140003fce  mov     r14, r9
0x140003fd1  mov     rdi, r8
0x140003fd4  mov     rax, rdx
0x140003fd7  xor     ebx, ebx
0x140003fd9  mov     [rsp+498h+var_440], rbx
0x140003fde  mov     [rsp+498h+var_448], rcx
0x140003fe3  mov     [rsp+498h+var_450], rbx
0x140003fe8  mov     [rsp+498h+var_438], rbx
0x140003fed  xor     edx, edx; hFile
0x140003fef  lea     r8d, [rbx+2]; dwFlags
0x140003ff3  mov     rcx, rax; lpLibFileName
0x140003ff6  call    cs:__imp_LoadLibraryExW
0x140003ffc  mov     rsi, rax
0x140003fff  mov     [rsp+498h+var_460], rax
0x140004004  test    rax, rax
0x140004007  jnz     short loc_140004015
0x140004009  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x14000400e  mov     ebx, eax
0x140004010  jmp     loc_14000413F
0x140004015  xor     r9d, r9d; wLanguage
0x140004018  mov     r8, rdi; lpName
0x14000401b  mov     rdx, r14; lpType
0x14000401e  mov     rcx, rsi; hModule
0x140004021  call    cs:__imp_FindResourceExW
0x140004027  mov     rdi, rax
0x14000402a  test    rax, rax
0x14000402d  jnz     short loc_140004039
0x14000402f  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x140004034  jmp     loc_140004133
0x140004039  mov     rdx, rdi; hResInfo
0x14000403c  mov     rcx, rsi; hModule
0x14000403f  call    cs:__imp_LoadResource
0x140004045  mov     r14, rax
0x140004048  mov     [rsp+498h+var_458], rax
0x14000404d  test    rax, rax
0x140004050  jz      short loc_14000402F
0x140004052  mov     rdx, rdi; hResInfo
0x140004055  mov     rcx, rsi; hModule
0x140004058  call    cs:__imp_SizeofResource
0x14000405e  mov     edi, eax
0x140004060  mov     [rsp+498h+var_468], eax
0x140004064  inc     eax
0x140004066  cmp     eax, edi
0x140004068  jnb     short loc_14000408B
0x14000406a  lea     rax, [rsp+498h+var_430]
0x14000406f  cmp     [rsp+498h+var_438], rax
0x140004074  jz      short loc_140004081
0x140004076  lea     rcx, [rsp+498h+var_438]
0x14000407b  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140004080  nop
0x140004081  mov     eax, 8007000Eh
0x140004086  jmp     loc_140004158
0x14000408b  test    eax, eax
0x14000408d  jz      short loc_1400040C2
0x14000408f  mov     ecx, eax
0x140004091  xor     edx, edx
0x140004093  or      rax, 0FFFFFFFFFFFFFFFFh
0x140004097  div     rcx
0x14000409a  cmp     rax, 2
0x14000409e  jb      loc_14000417C
0x1400040a4  lea     rdx, [rcx+rcx]
0x1400040a8  cmp     rdx, 400h
0x1400040af  jbe     short loc_1400040C2
0x1400040b1  lea     rcx, [rsp+498h+var_438]
0x1400040b6  call    ?AllocateHeap@?$CTempBuffer@G$0IA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<ushort,128,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1400040bb  mov     rax, [rsp+498h+var_438]
0x1400040c0  jmp     short loc_1400040CC
0x1400040c2  lea     rax, [rsp+498h+var_430]
0x1400040c7  mov     [rsp+498h+var_438], rax
0x1400040cc  jmp     short loc_1400040E3
0x1400040ce  xor     ebx, ebx
0x1400040d0  mov     rsi, [rsp+498h+var_460]
0x1400040d5  mov     r14, [rsp+498h+var_458]
0x1400040da  mov     edi, [rsp+498h+var_468]
0x1400040de  mov     rax, [rsp+498h+var_438]
0x1400040e3  test    rax, rax
0x1400040e6  jnz     short loc_1400040EF
0x1400040e8  mov     ebx, 8007000Eh
0x1400040ed  jmp     short loc_140004135
0x1400040ef  mov     [rsp+498h+cchWideChar], edi; cchWideChar
0x1400040f3  mov     [rsp+498h+lpWideCharStr], rax; lpWideCharStr
0x1400040f8  mov     r9d, edi; cbMultiByte
0x1400040fb  mov     r8, r14; lpMultiByteStr
0x1400040fe  xor     edx, edx; dwFlags
0x140004100  lea     ecx, [rdx+3]; CodePage
0x140004103  call    cs:__imp_MultiByteToWideChar
0x140004109  test    eax, eax
0x14000410b  jz      loc_14000402F
0x140004111  mov     ecx, eax
0x140004113  mov     rax, [rsp+498h+var_438]
0x140004118  mov     [rax+rcx*2], bx
0x14000411c  mov     r8d, [rsp+498h+arg_20]; int
0x140004124  mov     rdx, [rsp+498h+var_438]; unsigned __int16 *
0x140004129  lea     rcx, [rsp+498h+var_450]; this
0x14000412e  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEAGH@Z; ATL::CRegParser::RegisterBuffer(ushort *,int)
0x140004133  mov     ebx, eax
0x140004135  mov     rcx, rsi; hLibModule
0x140004138  call    cs:__imp_FreeLibrary
0x14000413e  nop
0x14000413f  lea     rax, [rsp+498h+var_430]
0x140004144  cmp     [rsp+498h+var_438], rax
0x140004149  jz      short loc_140004156
0x14000414b  lea     rcx, [rsp+498h+var_438]
0x140004150  call    ?FreeHeap@?$CTempBuffer@G$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<ushort,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x140004155  nop
0x140004156  mov     eax, ebx
0x140004158  mov     rcx, [rsp+498h+var_28]
0x140004160  xor     rcx, rsp; StackCookie
0x140004163  call    __security_check_cookie
0x140004168  mov     rbx, [rsp+498h+arg_0]
0x140004170  add     rsp, 480h
0x140004177  pop     r14
0x140004179  pop     rdi
0x14000417a  pop     rsi
0x14000417b  retn
0x14000417c  mov     ecx, 80070057h; int
0x140004181  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
