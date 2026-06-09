# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x14000b9a0`
- end: `0x14000bbe8`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `584`
- prototype: `int(ATL::CRegObject *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x14000c860`

## callees

- `0x140001390`
- `0x14000b808`
- `0x14000b9a0`
- `0x14000ca78`
- `0x14000e380`
- `0x14000e3e0`

## import_xrefs

- `KERNEL32!SizeofResource` at `0x14000ba5e`
- `KERNEL32!SizeofResource` at `0x14000ba5e`
- `KERNEL32!MultiByteToWideChar` at `0x14000bb8b`
- `KERNEL32!MultiByteToWideChar` at `0x14000bb8b`
- `KERNEL32!FindResourceExW` at `0x14000ba18`
- `KERNEL32!FindResourceExW` at `0x14000ba18`
- `KERNEL32!LoadResource` at `0x14000ba4a`
- `KERNEL32!LoadResource` at `0x14000ba4a`
- `KERNEL32!FreeLibrary` at `0x14000bbb2`
- `KERNEL32!FreeLibrary` at `0x14000bbb2`
- `KERNEL32!LoadLibraryExW` at `0x14000b9dd`
- `KERNEL32!LoadLibraryExW` at `0x14000b9dd`
- `KERNEL32!GetLastError` at `0x14000b9eb`
- `KERNEL32!GetLastError` at `0x14000ba26`
- `KERNEL32!GetLastError` at `0x14000b9eb`
- `KERNEL32!GetLastError` at `0x14000ba26`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000bbc0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14000bbc0`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000bab9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000bb58`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000bab9`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14000bb58`

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
  HMODULE v7; // r15
  signed int v8; // eax
  unsigned int v9; // edi
  _QWORD *v10; // rbx
  HRSRC Resource; // rax
  HRSRC v12; // rdi
  signed int LastError; // eax
  HGLOBAL v14; // r14
  DWORD v15; // eax
  unsigned __int64 v16; // rdx
  __int64 v17; // r12
  unsigned int v18; // eax
  size_t v19; // rdi
  __int64 v20; // rax
  void *v21; // rsp
  WCHAR *v22; // rsi
  _QWORD *v23; // rax
  __int64 v24; // rax
  int cchWideChar; // r14d
  unsigned __int64 v26; // rdi
  __int64 v27; // rax
  void *v28; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v30; // rax
  const unsigned __int16 *v31; // rdx
  void *v32; // rcx
  WCHAR WideCharStr[4]; // [rsp+30h] [rbp+0h] BYREF
  ATL::CRegObject *v35; // [rsp+38h] [rbp+8h]

  v35 = this;
  *(_QWORD *)WideCharStr = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v7 = Library;
  if ( Library )
  {
    v10 = 0;
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
    v12 = Resource;
    if ( !Resource || (v14 = LoadResource(v7, Resource)) == 0 )
    {
      LastError = GetLastError();
      v9 = LastError;
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_37;
    }
    v15 = SizeofResource(v7, v12);
    v17 = v15;
    if ( *((_BYTE *)v14 + v15) )
    {
      v18 = v15 + 1;
      v19 = v18;
      if ( v18 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v18, v16) )
      {
        v20 = v19 + 15;
        if ( v19 + 15 < v19 )
          v20 = 0xFFFFFFFFFFFFFF0LL;
        v21 = alloca(v20 & 0xFFFFFFFFFFFFFFF0uLL);
        v22 = WideCharStr;
      }
      else if ( v19 + 16 >= v19 && (v23 = malloc(v19 + 16)) != 0 )
      {
        *v23 = 0;
        v22 = (WCHAR *)(v23 + 2);
        v10 = v23;
      }
      else
      {
        v22 = 0;
      }
      if ( !v22 )
      {
        v9 = -2147024882;
LABEL_37:
        FreeLibrary(v7);
        while ( v10 )
        {
          v32 = v10;
          v10 = (_QWORD *)*v10;
          free(v32);
        }
        return v9;
      }
      memcpy_0(v22, v14, v19);
      *((_BYTE *)v22 + v17) = 0;
    }
    else
    {
      v22 = (WCHAR *)v14;
    }
    v24 = -1;
    do
      ++v24;
    while ( *((_BYTE *)v22 + v24) );
    cchWideChar = v24 + 1;
    v26 = 2LL * ((int)v24 + 1);
    if ( v26 <= 0x400
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(2LL * cchWideChar), v16) )
    {
      v27 = v26 + 15;
      if ( v26 + 15 < v26 )
        v27 = 0xFFFFFFFFFFFFFF0LL;
      v28 = alloca(v27 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = WideCharStr;
    }
    else if ( v26 + 16 >= v26 && (v30 = malloc(v26 + 16)) != 0 )
    {
      *v30 = v10;
      lpWideCharStr = (WCHAR *)(v30 + 2);
      v10 = v30;
    }
    else
    {
      lpWideCharStr = 0;
    }
    if ( lpWideCharStr )
    {
      *lpWideCharStr = 0;
      v31 = (const unsigned __int16 *)((unsigned __int64)lpWideCharStr
                                     & -(__int64)(MultiByteToWideChar(0, 0, (LPCCH)v22, -1, lpWideCharStr, cchWideChar) != 0));
    }
    else
    {
      v31 = 0;
    }
    v9 = ATL::CRegParser::RegisterBuffer((ATL::CRegParser *)WideCharStr, v31, a5);
    goto LABEL_37;
  }
  v8 = GetLastError();
  v9 = v8;
  if ( v8 > 0 )
    return (unsigned __int16)v8 | 0x80070000;
  return v9;
}

```

## disassembly

```asm
0x14000b9a0  push    rbp
0x14000b9a2  push    rbx
0x14000b9a3  push    rsi
0x14000b9a4  push    rdi
0x14000b9a5  push    r12
0x14000b9a7  push    r14
0x14000b9a9  push    r15
0x14000b9ab  sub     rsp, 50h
0x14000b9af  lea     rbp, [rsp+30h]
0x14000b9b4  mov     rax, cs:__security_cookie
0x14000b9bb  xor     rax, rbp
0x14000b9be  mov     [rbp+50h+var_40], rax
0x14000b9c2  mov     rax, rdx
0x14000b9c5  mov     [rbp+50h+var_48], rcx
0x14000b9c9  xor     edx, edx; hFile
0x14000b9cb  mov     qword ptr [rbp+50h+WideCharStr], 0
0x14000b9d3  mov     rcx, rax; lpLibFileName
0x14000b9d6  mov     rdi, r9
0x14000b9d9  lea     r8d, [rdx+2]; dwFlags
0x14000b9dd  call    cs:__imp_LoadLibraryExW
0x14000b9e3  mov     r15, rax
0x14000b9e6  test    rax, rax
0x14000b9e9  jnz     short loc_14000BA09
0x14000b9eb  call    cs:__imp_GetLastError
0x14000b9f1  mov     edi, eax
0x14000b9f3  test    eax, eax
0x14000b9f5  jle     loc_14000BBCB
0x14000b9fb  movzx   edi, ax
0x14000b9fe  or      edi, 80070000h
0x14000ba04  jmp     loc_14000BBCB
0x14000ba09  xor     ebx, ebx
0x14000ba0b  xor     r9d, r9d; wLanguage
0x14000ba0e  mov     rdx, rdi; lpType
0x14000ba11  mov     rcx, r15; hModule
0x14000ba14  lea     r8d, [rbx+65h]; lpName
0x14000ba18  call    cs:__imp_FindResourceExW
0x14000ba1e  mov     rdi, rax
0x14000ba21  test    rax, rax
0x14000ba24  jnz     short loc_14000BA44
0x14000ba26  call    cs:__imp_GetLastError
0x14000ba2c  mov     edi, eax
0x14000ba2e  test    eax, eax
0x14000ba30  jle     loc_14000BBAF
0x14000ba36  movzx   edi, ax
0x14000ba39  or      edi, 80070000h
0x14000ba3f  jmp     loc_14000BBAF
0x14000ba44  mov     rdx, rdi; hResInfo
0x14000ba47  mov     rcx, r15; hModule
0x14000ba4a  call    cs:__imp_LoadResource
0x14000ba50  mov     r14, rax
0x14000ba53  test    rax, rax
0x14000ba56  jz      short loc_14000BA26
0x14000ba58  mov     rdx, rdi; hResInfo
0x14000ba5b  mov     rcx, r15; hModule
0x14000ba5e  call    cs:__imp_SizeofResource
0x14000ba64  mov     r12d, eax
0x14000ba67  mov     rsi, 0FFFFFFFFFFFFFF0h
0x14000ba71  cmp     [r12+r14], bl
0x14000ba75  jz      short loc_14000BAF2
0x14000ba77  inc     eax
0x14000ba79  mov     edi, eax
0x14000ba7b  cmp     eax, 400h
0x14000ba80  ja      short loc_14000BAAC
0x14000ba82  mov     ecx, edi; this
0x14000ba84  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x14000ba89  test    al, al
0x14000ba8b  jz      short loc_14000BAAC
0x14000ba8d  lea     rax, [rdi+0Fh]
0x14000ba91  cmp     rax, rdi
0x14000ba94  ja      short loc_14000BA99
0x14000ba96  mov     rax, rsi
0x14000ba99  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000ba9d  call    _alloca_probe
0x14000baa2  sub     rsp, rax
0x14000baa5  lea     rsi, [rsp+80h+WideCharStr]
0x14000baaa  jmp     short loc_14000BACE
0x14000baac  lea     rcx, [rdi+10h]; Size
0x14000bab0  cmp     rcx, rdi
0x14000bab3  jnb     short loc_14000BAB9
0x14000bab5  xor     esi, esi
0x14000bab7  jmp     short loc_14000BACE
0x14000bab9  call    cs:__imp_malloc
0x14000babf  test    rax, rax
0x14000bac2  jz      short loc_14000BAB5
0x14000bac4  mov     [rax], rbx
0x14000bac7  lea     rsi, [rax+10h]
0x14000bacb  mov     rbx, rax
0x14000bace  test    rsi, rsi
0x14000bad1  jnz     short loc_14000BADD
0x14000bad3  mov     edi, 8007000Eh
0x14000bad8  jmp     loc_14000BBAF
0x14000badd  mov     r8, rdi; Size
0x14000bae0  mov     rdx, r14; Src
0x14000bae3  mov     rcx, rsi; void *
0x14000bae6  call    memcpy_0
0x14000baeb  mov     byte ptr [r12+rsi], 0
0x14000baf0  jmp     short loc_14000BAF5
0x14000baf2  mov     rsi, r14
0x14000baf5  or      r12, 0FFFFFFFFFFFFFFFFh
0x14000baf9  mov     rax, r12
0x14000bafc  inc     rax
0x14000baff  cmp     byte ptr [rsi+rax], 0
0x14000bb03  jnz     short loc_14000BAFC
0x14000bb05  lea     r14d, [rax+1]
0x14000bb09  movsxd  rax, r14d
0x14000bb0c  lea     rdi, [rax+rax]
0x14000bb10  cmp     rdi, 400h
0x14000bb17  ja      short loc_14000BB4B
0x14000bb19  mov     rcx, rdi; this
0x14000bb1c  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x14000bb21  test    al, al
0x14000bb23  jz      short loc_14000BB4B
0x14000bb25  lea     rax, [rdi+0Fh]
0x14000bb29  cmp     rax, rdi
0x14000bb2c  ja      short loc_14000BB38
0x14000bb2e  mov     rax, 0FFFFFFFFFFFFFF0h
0x14000bb38  and     rax, 0FFFFFFFFFFFFFFF0h
0x14000bb3c  call    _alloca_probe
0x14000bb41  sub     rsp, rax
0x14000bb44  lea     rdi, [rsp+80h+WideCharStr]
0x14000bb49  jmp     short loc_14000BB6D
0x14000bb4b  lea     rcx, [rdi+10h]; Size
0x14000bb4f  cmp     rcx, rdi
0x14000bb52  jnb     short loc_14000BB58
0x14000bb54  xor     edi, edi
0x14000bb56  jmp     short loc_14000BB6D
0x14000bb58  call    cs:__imp_malloc
0x14000bb5e  test    rax, rax
0x14000bb61  jz      short loc_14000BB54
0x14000bb63  mov     [rax], rbx
0x14000bb66  lea     rdi, [rax+10h]
0x14000bb6a  mov     rbx, rax
0x14000bb6d  test    rdi, rdi
0x14000bb70  jz      short loc_14000BB9B
0x14000bb72  xor     eax, eax
0x14000bb74  mov     [rsp+80h+cchWideChar], r14d; cchWideChar
0x14000bb79  mov     r9d, r12d; cbMultiByte
0x14000bb7c  mov     [rdi], ax
0x14000bb7f  mov     r8, rsi; lpMultiByteStr
0x14000bb82  mov     [rsp+80h+lpWideCharStr], rdi; lpWideCharStr
0x14000bb87  xor     edx, edx; dwFlags
0x14000bb89  xor     ecx, ecx; CodePage
0x14000bb8b  call    cs:__imp_MultiByteToWideChar
0x14000bb91  neg     eax
0x14000bb93  sbb     rdx, rdx
0x14000bb96  and     rdx, rdi
0x14000bb99  jmp     short loc_14000BB9D
0x14000bb9b  xor     edx, edx; unsigned __int16 *
0x14000bb9d  mov     r8d, [rbp+50h+arg_20]; int
0x14000bba4  lea     rcx, [rbp+50h+WideCharStr]; this
0x14000bba8  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z; ATL::CRegParser::RegisterBuffer(ushort const *,int)
0x14000bbad  mov     edi, eax
0x14000bbaf  mov     rcx, r15; hLibModule
0x14000bbb2  call    cs:__imp_FreeLibrary
0x14000bbb8  jmp     short loc_14000BBC6
0x14000bbba  mov     rcx, rbx; Block
0x14000bbbd  mov     rbx, [rbx]
0x14000bbc0  call    cs:__imp_free
0x14000bbc6  test    rbx, rbx
0x14000bbc9  jnz     short loc_14000BBBA
0x14000bbcb  mov     eax, edi
0x14000bbcd  mov     rcx, [rbp+50h+var_40]
0x14000bbd1  xor     rcx, rbp; StackCookie
0x14000bbd4  call    __security_check_cookie
0x14000bbd9  lea     rsp, [rbp+20h]
0x14000bbdd  pop     r15
0x14000bbdf  pop     r14
0x14000bbe1  pop     r12
0x14000bbe3  pop     rdi
0x14000bbe4  pop     rsi
0x14000bbe5  pop     rbx
0x14000bbe6  pop     rbp
0x14000bbe7  retn
```
