# ATL::CRegObject::RegisterFromResource(ushort const *,ushort const *,ushort const *,int)

- ea: `0x180003688`
- end: `0x1800038ea`
- name: `?RegisterFromResource@CRegObject@ATL@@IEAAJPEBG00H@Z`
- size: `610`
- prototype: `__int64 __fastcall(const WCHAR *this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, int)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800045a0`

## callees

- `0x180001470`
- `0x1800034f0`
- `0x180003688`
- `0x180004730`
- `0x180004ee0`
- `0x180004f4c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038c2`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800038c2`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800037ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003855`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800037ae`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180003855`
- `KERNEL32!MultiByteToWideChar` at `0x18000388c`
- `KERNEL32!MultiByteToWideChar` at `0x18000388c`
- `KERNEL32!SizeofResource` at `0x18000374e`
- `KERNEL32!SizeofResource` at `0x18000374e`
- `KERNEL32!LoadResource` at `0x18000373a`
- `KERNEL32!LoadResource` at `0x18000373a`
- `KERNEL32!FindResourceExW` at `0x180003708`
- `KERNEL32!FindResourceExW` at `0x180003708`
- `KERNEL32!LoadLibraryExW` at `0x1800036cf`
- `KERNEL32!LoadLibraryExW` at `0x1800036cf`
- `KERNEL32!GetLastError` at `0x1800036dd`
- `KERNEL32!GetLastError` at `0x180003716`
- `KERNEL32!GetLastError` at `0x1800036dd`
- `KERNEL32!GetLastError` at `0x180003716`
- `KERNEL32!FreeLibrary` at `0x1800038b3`
- `KERNEL32!FreeLibrary` at `0x1800038b3`

## pseudocode

```c
__int64 __fastcall ATL::CRegObject::RegisterFromResource(
        const WCHAR *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4,
        int a5)
{
  _QWORD *v6; // rbx
  HMODULE Library; // rax
  HMODULE v8; // r15
  signed int v9; // eax
  unsigned int v10; // edi
  HRSRC Resource; // rax
  HRSRC v12; // rdi
  signed int LastError; // eax
  HGLOBAL v14; // r14
  DWORD v15; // eax
  __int64 v16; // r12
  unsigned int v17; // eax
  size_t v18; // rdi
  __int64 v19; // rax
  void *v20; // rsp
  CHAR *v21; // rsi
  _QWORD *v22; // rax
  __int64 v23; // rax
  int cchWideChar; // r14d
  unsigned __int64 v25; // rdi
  __int64 v26; // rax
  void *v27; // rsp
  WCHAR *lpWideCharStr; // rdi
  _QWORD *v29; // rax
  WCHAR *v30; // rdx
  void *v31; // rcx
  CHAR MultiByteStr[8]; // [rsp+30h] [rbp+0h] BYREF
  LPCWSTR v34[3]; // [rsp+38h] [rbp+8h] BYREF

  v34[2] = (LPCWSTR)-2LL;
  v6 = 0;
  *(_QWORD *)MultiByteStr = 0;
  v34[1] = this;
  v34[0] = 0;
  Library = LoadLibraryExW(a2, 0, 2u);
  v8 = Library;
  if ( Library )
  {
    Resource = FindResourceExW(Library, a4, (LPCWSTR)0x65, 0);
    v12 = Resource;
    if ( !Resource || (v14 = LoadResource(v8, Resource)) == 0 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( LastError > 0 )
        v10 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_37;
    }
    v15 = SizeofResource(v8, v12);
    v16 = v15;
    if ( *((_BYTE *)v14 + v15) )
    {
      v17 = v15 + 1;
      v18 = v17;
      if ( v17 <= 0x400 && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)v17) )
      {
        v19 = v18 + 15;
        if ( v18 + 15 < v18 )
          v19 = 0xFFFFFFFFFFFFFF0LL;
        v20 = alloca(v19 & 0xFFFFFFFFFFFFFFF0uLL);
        v21 = MultiByteStr;
      }
      else if ( v18 + 16 >= v18 && (v22 = malloc(v18 + 16)) != 0 )
      {
        *v22 = 0;
        v6 = v22;
        *(_QWORD *)MultiByteStr = v22;
        v21 = (CHAR *)(v22 + 2);
      }
      else
      {
        v21 = 0;
      }
      if ( !v21 )
      {
        v10 = -2147024882;
LABEL_37:
        FreeLibrary(v8);
        goto LABEL_40;
      }
      memcpy_0(v21, v14, v18);
      v21[v16] = 0;
    }
    else
    {
      v21 = (CHAR *)v14;
    }
    v23 = -1;
    do
      ++v23;
    while ( v21[v23] );
    cchWideChar = v23 + 1;
    v25 = 2LL * ((int)v23 + 1);
    if ( v25 <= 0x400
      && ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable((ATL::_ATL_SAFE_ALLOCA_IMPL *)(2LL * cchWideChar)) )
    {
      v26 = v25 + 15;
      if ( v25 + 15 < v25 )
        v26 = 0xFFFFFFFFFFFFFF0LL;
      v27 = alloca(v26 & 0xFFFFFFFFFFFFFFF0uLL);
      lpWideCharStr = (WCHAR *)MultiByteStr;
    }
    else if ( v25 + 16 >= v25 && (v29 = malloc(v25 + 16)) != 0 )
    {
      *v29 = v6;
      v6 = v29;
      *(_QWORD *)MultiByteStr = v29;
      lpWideCharStr = (WCHAR *)(v29 + 2);
    }
    else
    {
      lpWideCharStr = 0;
    }
    if ( lpWideCharStr )
    {
      *lpWideCharStr = 0;
      v30 = (WCHAR *)((unsigned __int64)lpWideCharStr
                    & -(__int64)(MultiByteToWideChar(0, 0, v21, -1, lpWideCharStr, cchWideChar) != 0));
    }
    else
    {
      v30 = 0;
    }
    v10 = ATL::CRegParser::RegisterBuffer(v34, v30, a5);
    goto LABEL_37;
  }
  v9 = GetLastError();
  v10 = v9;
  if ( v9 > 0 )
    v10 = (unsigned __int16)v9 | 0x80070000;
LABEL_40:
  while ( v6 )
  {
    v31 = v6;
    v6 = (_QWORD *)*v6;
    free(v31);
  }
  return v10;
}

```

## disassembly

```asm
0x180003688  push    rbp
0x18000368a  push    rbx
0x18000368b  push    rsi
0x18000368c  push    rdi
0x18000368d  push    r12
0x18000368f  push    r14
0x180003691  push    r15
0x180003693  sub     rsp, 60h
0x180003697  lea     rbp, [rsp+30h]
0x18000369c  mov     [rbp+60h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800036a4  mov     rax, cs:__security_cookie
0x1800036ab  xor     rax, rbp
0x1800036ae  mov     [rbp+60h+var_40], rax
0x1800036b2  mov     rdi, r9
0x1800036b5  mov     rax, rdx
0x1800036b8  xor     ebx, ebx
0x1800036ba  mov     qword ptr [rbp+60h+MultiByteStr], rbx
0x1800036be  mov     [rbp+60h+var_50], rcx
0x1800036c2  mov     [rbp+60h+var_58], rbx
0x1800036c6  xor     edx, edx; hFile
0x1800036c8  lea     r8d, [rbx+2]; dwFlags
0x1800036cc  mov     rcx, rax; lpLibFileName
0x1800036cf  call    cs:__imp_LoadLibraryExW
0x1800036d5  mov     r15, rax
0x1800036d8  test    rax, rax
0x1800036db  jnz     short loc_1800036FB
0x1800036dd  call    cs:__imp_GetLastError
0x1800036e3  mov     edi, eax
0x1800036e5  test    eax, eax
0x1800036e7  jle     loc_1800038BA
0x1800036ed  movzx   edi, ax
0x1800036f0  or      edi, 80070000h
0x1800036f6  jmp     loc_1800038BA
0x1800036fb  xor     r9d, r9d; wLanguage
0x1800036fe  lea     r8d, [r9+65h]; lpName
0x180003702  mov     rdx, rdi; lpType
0x180003705  mov     rcx, r15; hModule
0x180003708  call    cs:__imp_FindResourceExW
0x18000370e  mov     rdi, rax
0x180003711  test    rax, rax
0x180003714  jnz     short loc_180003734
0x180003716  call    cs:__imp_GetLastError
0x18000371c  mov     edi, eax
0x18000371e  test    eax, eax
0x180003720  jle     loc_1800038B0
0x180003726  movzx   edi, ax
0x180003729  or      edi, 80070000h
0x18000372f  jmp     loc_1800038B0
0x180003734  mov     rdx, rdi; hResInfo
0x180003737  mov     rcx, r15; hModule
0x18000373a  call    cs:__imp_LoadResource
0x180003740  mov     r14, rax
0x180003743  test    rax, rax
0x180003746  jz      short loc_180003716
0x180003748  mov     rdx, rdi; hResInfo
0x18000374b  mov     rcx, r15; hModule
0x18000374e  call    cs:__imp_SizeofResource
0x180003754  mov     r12d, eax
0x180003757  mov     rsi, 0FFFFFFFFFFFFFF0h
0x180003761  cmp     byte ptr [r12+r14], 0
0x180003766  jz      loc_1800037EF
0x18000376c  inc     eax
0x18000376e  mov     edi, eax
0x180003770  cmp     eax, 400h
0x180003775  ja      short loc_1800037A1
0x180003777  mov     ecx, edi; this
0x180003779  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000377e  test    al, al
0x180003780  jz      short loc_1800037A1
0x180003782  lea     rax, [rdi+0Fh]
0x180003786  cmp     rax, rdi
0x180003789  ja      short loc_18000378E
0x18000378b  mov     rax, rsi
0x18000378e  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003792  call    _alloca_probe
0x180003797  sub     rsp, rax
0x18000379a  lea     rsi, [rsp+90h+MultiByteStr]
0x18000379f  jmp     short loc_1800037CB
0x1800037a1  lea     rcx, [rdi+10h]; Size
0x1800037a5  cmp     rcx, rdi
0x1800037a8  jnb     short loc_1800037AE
0x1800037aa  xor     esi, esi
0x1800037ac  jmp     short loc_1800037CB
0x1800037ae  call    cs:__imp_malloc
0x1800037b4  test    rax, rax
0x1800037b7  jz      short loc_1800037AA
0x1800037b9  mov     qword ptr [rax], 0
0x1800037c0  mov     rbx, rax
0x1800037c3  mov     qword ptr [rbp+60h+MultiByteStr], rax
0x1800037c7  lea     rsi, [rax+10h]
0x1800037cb  test    rsi, rsi
0x1800037ce  jnz     short loc_1800037DA
0x1800037d0  mov     edi, 8007000Eh
0x1800037d5  jmp     loc_1800038B0
0x1800037da  mov     r8, rdi; Size
0x1800037dd  mov     rdx, r14; Src
0x1800037e0  mov     rcx, rsi; void *
0x1800037e3  call    memcpy_0
0x1800037e8  mov     byte ptr [r12+rsi], 0
0x1800037ed  jmp     short loc_1800037F2
0x1800037ef  mov     rsi, r14
0x1800037f2  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800037f6  mov     rax, r12
0x1800037f9  inc     rax
0x1800037fc  cmp     byte ptr [rsi+rax], 0
0x180003800  jnz     short loc_1800037F9
0x180003802  lea     r14d, [rax+1]
0x180003806  movsxd  rax, r14d
0x180003809  lea     rdi, [rax+rax]
0x18000380d  cmp     rdi, 400h
0x180003814  ja      short loc_180003848
0x180003816  mov     rcx, rdi; this
0x180003819  call    ?_AtlVerifyStackAvailable@_ATL_SAFE_ALLOCA_IMPL@ATL@@YA_N_K@Z; ATL::_ATL_SAFE_ALLOCA_IMPL::_AtlVerifyStackAvailable(unsigned __int64)
0x18000381e  test    al, al
0x180003820  jz      short loc_180003848
0x180003822  lea     rax, [rdi+0Fh]
0x180003826  cmp     rax, rdi
0x180003829  ja      short loc_180003835
0x18000382b  mov     rax, 0FFFFFFFFFFFFFF0h
0x180003835  and     rax, 0FFFFFFFFFFFFFFF0h
0x180003839  call    _alloca_probe
0x18000383e  sub     rsp, rax
0x180003841  lea     rdi, [rsp+90h+MultiByteStr]
0x180003846  jmp     short loc_18000386E
0x180003848  lea     rcx, [rdi+10h]; Size
0x18000384c  cmp     rcx, rdi
0x18000384f  jnb     short loc_180003855
0x180003851  xor     edi, edi
0x180003853  jmp     short loc_18000386E
0x180003855  call    cs:__imp_malloc
0x18000385b  test    rax, rax
0x18000385e  jz      short loc_180003851
0x180003860  mov     [rax], rbx
0x180003863  mov     rbx, rax
0x180003866  mov     qword ptr [rbp+60h+MultiByteStr], rax
0x18000386a  lea     rdi, [rax+10h]
0x18000386e  test    rdi, rdi
0x180003871  jz      short loc_18000389C
0x180003873  xor     eax, eax
0x180003875  mov     [rdi], ax
0x180003878  mov     [rsp+90h+cchWideChar], r14d; cchWideChar
0x18000387d  mov     [rsp+90h+lpWideCharStr], rdi; lpWideCharStr
0x180003882  mov     r9d, r12d; cbMultiByte
0x180003885  mov     r8, rsi; lpMultiByteStr
0x180003888  xor     edx, edx; dwFlags
0x18000388a  xor     ecx, ecx; CodePage
0x18000388c  call    cs:__imp_MultiByteToWideChar
0x180003892  neg     eax
0x180003894  sbb     rdx, rdx
0x180003897  and     rdx, rdi
0x18000389a  jmp     short loc_18000389E
0x18000389c  xor     edx, edx; unsigned __int16 *
0x18000389e  mov     r8d, [rbp+60h+arg_20]; int
0x1800038a5  lea     rcx, [rbp+60h+var_58]; this
0x1800038a9  call    ?RegisterBuffer@CRegParser@ATL@@QEAAJPEBGH@Z; ATL::CRegParser::RegisterBuffer(ushort const *,int)
0x1800038ae  mov     edi, eax
0x1800038b0  mov     rcx, r15; hLibModule
0x1800038b3  call    cs:__imp_FreeLibrary
0x1800038b9  nop
0x1800038ba  jmp     short loc_1800038C8
0x1800038bc  mov     rcx, rbx; Block
0x1800038bf  mov     rbx, [rbx]
0x1800038c2  call    cs:__imp_free
0x1800038c8  test    rbx, rbx
0x1800038cb  jnz     short loc_1800038BC
0x1800038cd  mov     eax, edi
0x1800038cf  mov     rcx, [rbp+60h+var_40]
0x1800038d3  xor     rcx, rbp; StackCookie
0x1800038d6  call    __security_check_cookie
0x1800038db  lea     rsp, [rbp+30h]
0x1800038df  pop     r15
0x1800038e1  pop     r14
0x1800038e3  pop     r12
0x1800038e5  pop     rdi
0x1800038e6  pop     rsi
0x1800038e7  pop     rbx
0x1800038e8  pop     rbp
0x1800038e9  retn
```
