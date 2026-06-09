# ATL::CRegObject::RegisterFromResource(ushort const *,char const *,char const *,int)

- ea: `0x180011800`
- end: `0x180011b03`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBGPEBD1H@Z`
- size: `771`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const char *, const char *, int)`
- caller_count: `4`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x1800124b4`
- `0x1800125c4`
- `0x1800127d8`
- `0x1800128e8`

## callees

- `0x180003b70`
- `0x1800099ac`
- `0x18000fe34`
- `0x180010050`
- `0x180010f34`
- `0x18001167c`
- `0x180011800`
- `0x180014270`
- `0x180014300`

## import_xrefs

- `msvcrt!memcpy_s` at `0x180011a0f`
- `msvcrt!memcpy_s` at `0x180011a0f`
- `msvcrt!free` at `0x1800119b0`
- `msvcrt!free` at `0x180011a7f`
- `msvcrt!free` at `0x180011aa9`
- `msvcrt!free` at `0x1800119b0`
- `msvcrt!free` at `0x180011a7f`
- `msvcrt!free` at `0x180011aa9`
- `msvcrt!malloc` at `0x1800118d2`
- `msvcrt!malloc` at `0x1800118d2`
- `KERNEL32!LoadLibraryExA` at `0x18001192e`
- `KERNEL32!LoadLibraryExA` at `0x18001192e`
- `KERNEL32!FreeLibrary` at `0x180011a5e`
- `KERNEL32!FreeLibrary` at `0x180011a5e`
- `KERNEL32!WideCharToMultiByte` at `0x180011917`
- `KERNEL32!WideCharToMultiByte` at `0x180011917`
- `KERNEL32!LoadResource` at `0x180011972`
- `KERNEL32!LoadResource` at `0x180011972`
- `KERNEL32!SizeofResource` at `0x180011986`
- `KERNEL32!SizeofResource` at `0x180011986`
- `KERNEL32!FindResourceExA` at `0x180011954`
- `KERNEL32!FindResourceExA` at `0x180011954`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        ATL::CRegObject *this,
        const unsigned __int16 *a2,
        const char *a3,
        const char *a4,
        int a5)
{
  _QWORD *v8; // rbx
  __int64 v9; // rax
  __int64 cbMultiByte; // rsi
  unsigned __int64 v11; // rax
  void *v12; // rsp
  CHAR *lpMultiByteStr; // rdi
  _QWORD *v14; // rax
  HMODULE Library; // rax
  HMODULE v16; // rsi
  unsigned int v17; // edi
  HRSRC Resource; // rax
  HRSRC v19; // rdi
  unsigned int Error; // eax
  HGLOBAL v21; // r14
  DWORD v22; // eax
  rsize_t v23; // rdi
  unsigned __int64 v24; // rcx
  void *v25; // rcx
  char *v26; // rcx
  errno_t v27; // eax
  void *v28; // rcx
  void *v30; // rcx
  CHAR MultiByteStr[8]; // [rsp+40h] [rbp+0h] BYREF
  ATL::CRegObject *v32; // [rsp+48h] [rbp+8h]
  char *v33; // [rsp+50h] [rbp+10h] BYREF
  _BYTE Destination[1032]; // [rsp+58h] [rbp+18h] BYREF

  v32 = this;
  *(_QWORD *)MultiByteStr = 0;
  v33 = 0;
  v8 = 0;
  if ( !a2 )
    goto LABEL_47;
  v9 = -1;
  do
    ++v9;
  while ( a2[v9] );
  cbMultiByte = 2LL * ((int)v9 + 1);
  if ( (unsigned __int64)(cbMultiByte + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_47;
  if ( (int)cbMultiByte <= 1024
    && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(
         (ATL::_ATL_SAFE_ALLOCA_IMPL *)(int)cbMultiByte,
         (unsigned __int64)a2) )
  {
    v11 = (int)cbMultiByte + 15LL;
    if ( v11 < (int)cbMultiByte )
      v11 = 0xFFFFFFFFFFFFFF0LL;
    v12 = alloca(v11 & 0xFFFFFFFFFFFFFFF0uLL);
    lpMultiByteStr = MultiByteStr;
  }
  else
  {
    if ( (unsigned __int64)~(__int64)(int)cbMultiByte < 0x10 )
      goto LABEL_52;
    v14 = malloc((int)cbMultiByte + 16LL);
    if ( v14 )
    {
      *v14 = 0;
      lpMultiByteStr = (CHAR *)(v14 + 2);
      v8 = v14;
    }
    else
    {
      lpMultiByteStr = 0;
    }
  }
  if ( !lpMultiByteStr || (*lpMultiByteStr = 0, !WideCharToMultiByte(3u, 0, a2, -1, lpMultiByteStr, cbMultiByte, 0, 0)) )
  {
LABEL_47:
    if ( v33 != Destination )
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v33);
    while ( v8 )
    {
      v30 = v8;
      v8 = (_QWORD *)*v8;
      free(v30);
    }
    return 2147942414LL;
  }
  Library = LoadLibraryExA(lpMultiByteStr, 0, 2u);
  v16 = Library;
  if ( Library )
  {
    Resource = FindResourceExA(Library, a4, a3, 0);
    v19 = Resource;
    if ( !Resource || (v21 = LoadResource(v16, Resource)) == 0 )
    {
      Error = ATL::AtlHresultFromLastError();
LABEL_40:
      v17 = Error;
      goto LABEL_41;
    }
    v22 = SizeofResource(v16, v19);
    v23 = v22;
    v24 = v22 + 1;
    if ( (unsigned int)v24 < v22 )
    {
      if ( v33 != Destination )
        ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v33);
      while ( v8 )
      {
        v25 = v8;
        v8 = (_QWORD *)*v8;
        free(v25);
      }
      return 2147942414LL;
    }
    if ( v22 == -1 )
      goto LABEL_31;
    if ( !(0xFFFFFFFFFFFFFFFFuLL / v24) )
      goto LABEL_52;
    if ( v24 <= 0x400 )
    {
LABEL_31:
      v26 = Destination;
      v33 = Destination;
    }
    else
    {
      ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(&v33, v24);
      v26 = v33;
    }
    if ( !v26 )
    {
      v17 = -2147024882;
LABEL_41:
      FreeLibrary(v16);
      goto LABEL_42;
    }
    v27 = memcpy_s(v26, v23, v21, v23);
    if ( !v27 )
      goto LABEL_39;
    if ( v27 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v27 != 22 && v27 != 34 )
    {
      if ( v27 != 80 )
        ATL::AtlThrowImpl(-2147467259);
LABEL_39:
      v33[v23] = 0;
      Error = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)MultiByteStr, v33, a5);
      goto LABEL_40;
    }
LABEL_52:
    ATL::AtlThrowImpl(-2147024809);
  }
  v17 = ATL::AtlHresultFromLastError();
LABEL_42:
  if ( v33 != Destination )
    ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(&v33);
  while ( v8 )
  {
    v28 = v8;
    v8 = (_QWORD *)*v8;
    free(v28);
  }
  return v17;
}

```

## disassembly

```asm
0x180011800  push    rbp
0x180011802  push    rsi
0x180011803  push    rdi
0x180011804  push    r12
0x180011806  push    r13
0x180011808  push    r14
0x18001180a  push    r15
0x18001180c  sub     rsp, 470h
0x180011813  lea     rbp, [rsp+40h]
0x180011818  mov     [rbp+460h+arg_0], rbx
0x18001181f  mov     rax, cs:__security_cookie
0x180011826  xor     rax, rbp
0x180011829  mov     [rbp+460h+var_40], rax
0x180011830  xor     r13d, r13d
0x180011833  mov     [rbp+460h+var_458], rcx
0x180011837  mov     qword ptr [rbp+460h+MultiByteStr], r13
0x18001183b  mov     r12, r9
0x18001183e  mov     [rbp+460h+var_450], r13
0x180011842  mov     r15, r8
0x180011845  mov     r14, rdx
0x180011848  mov     ebx, r13d
0x18001184b  test    rdx, rdx
0x18001184e  jz      loc_180011A8E
0x180011854  or      rax, 0FFFFFFFFFFFFFFFFh
0x180011858  inc     rax
0x18001185b  cmp     [rdx+rax*2], r13w
0x180011860  jnz     short loc_180011858
0x180011862  inc     eax
0x180011864  movsxd  rcx, eax
0x180011867  mov     eax, 80000000h
0x18001186c  lea     rsi, [rcx+rcx]
0x180011870  mov     ecx, 0FFFFFFFFh
0x180011875  add     rax, rsi
0x180011878  cmp     rax, rcx
0x18001187b  ja      loc_180011A8E
0x180011881  movsxd  rdi, esi
0x180011884  cmp     esi, 400h
0x18001188a  jg      short loc_1800118BE
0x18001188c  mov     rcx, rdi; this
0x18001188f  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x180011894  test    al, al
0x180011896  jz      short loc_1800118BE
0x180011898  lea     rax, [rdi+0Fh]
0x18001189c  cmp     rax, rdi
0x18001189f  ja      short loc_1800118AB
0x1800118a1  mov     rax, 0FFFFFFFFFFFFFF0h
0x1800118ab  and     rax, 0FFFFFFFFFFFFFFF0h
0x1800118af  call    _alloca_probe
0x1800118b4  sub     rsp, rax
0x1800118b7  lea     rdi, [rsp+4A0h+MultiByteStr]
0x1800118bc  jmp     short loc_1800118EC
0x1800118be  mov     rax, rdi
0x1800118c1  not     rax
0x1800118c4  cmp     rax, 10h
0x1800118c8  jb      loc_180011AE2
0x1800118ce  lea     rcx, [rdi+10h]; Size
0x1800118d2  call    cs:__imp_malloc
0x1800118d8  test    rax, rax
0x1800118db  jnz     short loc_1800118E2
0x1800118dd  mov     rdi, r13
0x1800118e0  jmp     short loc_1800118EC
0x1800118e2  mov     [rax], r13
0x1800118e5  lea     rdi, [rax+10h]
0x1800118e9  mov     rbx, rax
0x1800118ec  test    rdi, rdi
0x1800118ef  jz      loc_180011A8E
0x1800118f5  mov     [rsp+4A0h+lpUsedDefaultChar], r13; lpUsedDefaultChar
0x1800118fa  xor     edx, edx; dwFlags
0x1800118fc  mov     [rsp+4A0h+lpDefaultChar], r13; lpDefaultChar
0x180011901  or      r9d, 0FFFFFFFFh; cchWideChar
0x180011905  mov     [rsp+4A0h+cbMultiByte], esi; cbMultiByte
0x180011909  mov     r8, r14; lpWideCharStr
0x18001190c  mov     [rdi], r13b
0x18001190f  lea     ecx, [rdx+3]; CodePage
0x180011912  mov     [rsp+4A0h+lpMultiByteStr], rdi; lpMultiByteStr
0x180011917  call    cs:__imp_WideCharToMultiByte
0x18001191d  test    eax, eax
0x18001191f  jz      loc_180011A8E
0x180011925  xor     edx, edx; hFile
0x180011927  mov     rcx, rdi; lpLibFileName
0x18001192a  lea     r8d, [rdx+2]; dwFlags
0x18001192e  call    cs:__imp_LoadLibraryExA
0x180011934  mov     rsi, rax
0x180011937  test    rax, rax
0x18001193a  jnz     short loc_180011948
0x18001193c  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011941  mov     edi, eax
0x180011943  jmp     loc_180011A64
0x180011948  xor     r9d, r9d; wLanguage
0x18001194b  mov     r8, r15; lpName
0x18001194e  mov     rdx, r12; lpType
0x180011951  mov     rcx, rsi; hModule
0x180011954  call    cs:__imp_FindResourceExA
0x18001195a  mov     rdi, rax
0x18001195d  test    rax, rax
0x180011960  jnz     short loc_18001196C
0x180011962  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180011967  jmp     loc_180011A59
0x18001196c  mov     rdx, rdi; hResInfo
0x18001196f  mov     rcx, rsi; hModule
0x180011972  call    cs:__imp_LoadResource
0x180011978  mov     r14, rax
0x18001197b  test    rax, rax
0x18001197e  jz      short loc_180011962
0x180011980  mov     rdx, rdi; hResInfo
0x180011983  mov     rcx, rsi; hModule
0x180011986  call    cs:__imp_SizeofResource
0x18001198c  mov     edi, eax
0x18001198e  lea     ecx, [rdi+1]
0x180011991  cmp     ecx, eax
0x180011993  jnb     short loc_1800119C0
0x180011995  lea     rax, [rbp+460h+Destination]
0x180011999  cmp     [rbp+460h+var_450], rax
0x18001199d  jz      short loc_1800119B6
0x18001199f  lea     rcx, [rbp+460h+var_450]
0x1800119a3  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x1800119a8  jmp     short loc_1800119B6
0x1800119aa  mov     rcx, rbx; Block
0x1800119ad  mov     rbx, [rbx]
0x1800119b0  call    cs:__imp_free
0x1800119b6  test    rbx, rbx
0x1800119b9  jnz     short loc_1800119AA
0x1800119bb  jmp     loc_180011AB4
0x1800119c0  test    ecx, ecx
0x1800119c2  jz      short loc_1800119F2
0x1800119c4  xor     edx, edx
0x1800119c6  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800119ca  div     rcx
0x1800119cd  cmp     rax, 1
0x1800119d1  jb      loc_180011AE2
0x1800119d7  cmp     rcx, 400h
0x1800119de  jbe     short loc_1800119F2
0x1800119e0  mov     rdx, rcx
0x1800119e3  lea     rcx, [rbp+460h+var_450]
0x1800119e7  call    ?AllocateHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAX_K@Z; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::AllocateHeap(unsigned __int64)
0x1800119ec  mov     rcx, [rbp+460h+var_450]
0x1800119f0  jmp     short loc_1800119FA
0x1800119f2  lea     rcx, [rbp+460h+Destination]; Destination
0x1800119f6  mov     [rbp+460h+var_450], rcx
0x1800119fa  test    rcx, rcx
0x1800119fd  jnz     short loc_180011A06
0x1800119ff  mov     edi, 8007000Eh
0x180011a04  jmp     short loc_180011A5B
0x180011a06  mov     r9, rdi; SourceSize
0x180011a09  mov     r8, r14; Source
0x180011a0c  mov     rdx, rdi; DestinationSize
0x180011a0f  call    cs:__imp_memcpy_s
0x180011a15  test    eax, eax
0x180011a17  jz      short loc_180011A3D
0x180011a19  cmp     eax, 0Ch
0x180011a1c  jz      loc_180011AF8
0x180011a22  cmp     eax, 16h
0x180011a25  jz      loc_180011AE2
0x180011a2b  cmp     eax, 22h ; '"'
0x180011a2e  jz      loc_180011AE2
0x180011a34  cmp     eax, 50h ; 'P'
0x180011a37  jnz     loc_180011AED
0x180011a3d  mov     rax, [rbp+460h+var_450]
0x180011a41  lea     rcx, [rbp+460h+MultiByteStr]; this
0x180011a45  mov     r8d, [rbp+460h+arg_20]; int
0x180011a4c  mov     [rdi+rax], r13b
0x180011a50  mov     rdx, [rbp+460h+var_450]; char *
0x180011a54  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEADH@Z; ATL::CRegParser::RegisterBuffer(char *,int)
0x180011a59  mov     edi, eax
0x180011a5b  mov     rcx, rsi; hLibModule
0x180011a5e  call    cs:__imp_FreeLibrary
0x180011a64  lea     rax, [rbp+460h+Destination]
0x180011a68  cmp     [rbp+460h+var_450], rax
0x180011a6c  jz      short loc_180011A85
0x180011a6e  lea     rcx, [rbp+460h+var_450]
0x180011a72  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180011a77  jmp     short loc_180011A85
0x180011a79  mov     rcx, rbx; Block
0x180011a7c  mov     rbx, [rbx]
0x180011a7f  call    cs:__imp_free
0x180011a85  test    rbx, rbx
0x180011a88  jnz     short loc_180011A79
0x180011a8a  mov     eax, edi
0x180011a8c  jmp     short loc_180011AB9
0x180011a8e  lea     rax, [rbp+460h+Destination]
0x180011a92  cmp     [rbp+460h+var_450], rax
0x180011a96  jz      short loc_180011AAF
0x180011a98  lea     rcx, [rbp+460h+var_450]
0x180011a9c  call    ?FreeHeap@?$CTempBuffer@D$0EAA@VCCRTAllocator@ATL@@@ATL@@AEAAXXZ; ATL::CTempBuffer<char,1024,ATL::CCRTAllocator>::FreeHeap(void)
0x180011aa1  jmp     short loc_180011AAF
0x180011aa3  mov     rcx, rbx; Block
0x180011aa6  mov     rbx, [rbx]
0x180011aa9  call    cs:__imp_free
0x180011aaf  test    rbx, rbx
0x180011ab2  jnz     short loc_180011AA3
0x180011ab4  mov     eax, 8007000Eh
0x180011ab9  mov     rcx, [rbp+460h+var_40]
0x180011ac0  xor     rcx, rbp; StackCookie
0x180011ac3  call    __security_check_cookie
0x180011ac8  mov     rbx, [rbp+460h+arg_0]
0x180011acf  lea     rsp, [rbp+430h]
0x180011ad6  pop     r15
0x180011ad8  pop     r14
0x180011ada  pop     r13
0x180011adc  pop     r12
0x180011ade  pop     rdi
0x180011adf  pop     rsi
0x180011ae0  pop     rbp
0x180011ae1  retn
0x180011ae2  mov     ecx, 80070057h; int
0x180011ae7  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011aed  mov     ecx, 80004005h; int
0x180011af2  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011af8  mov     ecx, 8007000Eh; int
0x180011afd  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
