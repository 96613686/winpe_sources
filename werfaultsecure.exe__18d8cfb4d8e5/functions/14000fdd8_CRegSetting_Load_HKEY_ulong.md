# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x14000fdd8`
- end: `0x1400100a3`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `715`
- prototype: `__int64 __fastcall(CRegSetting *__hidden this, HKEY, unsigned int)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x1400104f4`

## callees

- `0x1400023f4`
- `0x140002fcc`
- `0x1400085f0`
- `0x14000cb38`
- `0x14000e12c`
- `0x14000fdd8`
- `0x14001130c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fe80`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14000fe80`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010087`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140010087`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000feb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ff9e`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000feb8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x14000ff9e`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, DWORD a3)
{
  __int64 v4; // rax
  HKEY v6; // rbx
  HKEY *phkResult; // rax
  int v8; // ebx
  __int64 v9; // r8
  DWORD v10; // eax
  __int64 v11; // rcx
  int v12; // ecx
  int v13; // edx
  LPBYTE *v14; // rdi
  unsigned __int64 v15; // r15
  LPBYTE v16; // rax
  unsigned __int64 v17; // r14
  bool v18; // zf
  __int64 v19; // r8
  __int64 v20; // r9
  LPBYTE v21; // rax
  __int64 v22; // rbx
  unsigned __int64 v23; // r14
  __int64 v24; // r8
  __int64 v25; // r9
  LPBYTE v26; // rax
  _WORD v27[8]; // [rsp+40h] [rbp-10h] BYREF
  DWORD Type; // [rsp+88h] [rbp+38h] BYREF
  int v29; // [rsp+8Ch] [rbp+3Ch]
  DWORD cbData; // [rsp+90h] [rbp+40h] BYREF
  HKEY hKey; // [rsp+98h] [rbp+48h] BYREF

  cbData = a3;
  v29 = HIDWORD(a2);
  hKey = 0;
  Type = 0;
  v27[0] = 0;
  v4 = *((_QWORD *)this + 9);
  cbData = 0;
  if ( *((_QWORD *)this + 8) == v4 )
    return 2149285891LL;
  if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
    goto LABEL_44;
  if ( *((_QWORD *)this + 4) == *((_QWORD *)this + 5) )
  {
    v6 = HKEY_LOCAL_MACHINE;
  }
  else
  {
    phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&hKey);
    if ( RegOpenKeyExW(HKEY_LOCAL_MACHINE, *((LPCWSTR *)this + 4), 0, 0x20119u, phkResult) )
      goto LABEL_8;
    v6 = hKey;
  }
  if ( RegQueryValueExW(v6, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
    goto LABEL_8;
  v10 = cbData;
  if ( Type - 1 <= 1 )
  {
    v10 = cbData + 1;
    goto LABEL_15;
  }
  if ( Type == 7 )
  {
    v10 = cbData + 2;
LABEL_15:
    cbData = v10;
  }
  v11 = 0;
  while ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11 + 1) != Type )
  {
    v11 = (unsigned int)(v11 + 1);
    if ( (unsigned int)v11 >= 0xB )
    {
      v12 = 9;
      goto LABEL_21;
    }
  }
  v12 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * v11);
LABEL_21:
  v13 = *((_DWORD *)this + 1);
  if ( v13 == v12 || v13 == 9 || v13 == 5 && v12 == 1 || v13 == 1 && v12 == 5 || !v13 && v12 == 1 )
  {
    v14 = (LPBYTE *)((char *)this + 8);
    *((_DWORD *)this + 1) = v12;
    v15 = v10;
    v16 = (LPBYTE)*((_QWORD *)this + 1);
    v17 = *((_QWORD *)this + 2) - (_QWORD)v16;
    if ( v15 > v17 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v15,
                               v9,
                               &CRegSetting::s_typeMapping) )
      {
LABEL_31:
        v8 = -2147024882;
        goto LABEL_45;
      }
      memset_0(*((void **)this + 2), 0, v15 - v17);
      v16 = *v14;
    }
    *((_QWORD *)this + 2) = &v16[v15];
    v18 = RegQueryValueExW(v6, *((LPCWSTR *)this + 8), 0, &Type, *v14, &cbData) == 0;
    v21 = *v14;
    if ( !v18 )
    {
      v8 = -2147467259;
      *((_QWORD *)this + 2) = v21;
      goto LABEL_45;
    }
    v22 = cbData;
    v23 = *((_QWORD *)this + 2) - (_QWORD)v21;
    if ( cbData > v23 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 8,
                              cbData,
                              v19,
                              v20) )
      {
        memset_0(*((void **)this + 2), 0, v22 - v23);
        *((_QWORD *)this + 2) = &(*v14)[v22];
      }
    }
    else
    {
      *((_QWORD *)this + 2) = &v21[cbData];
    }
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v8 = UtilExpandEnvironmentStrings((LPCWSTR)*v14);
      if ( v8 < 0 )
        goto LABEL_45;
      v26 = *v14;
      cbData = 2;
      *((_QWORD *)this + 2) = v26;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               2,
                               v24,
                               v25) )
        goto LABEL_31;
      memcpy_0(*((void **)this + 2), v27, 2u);
      *((_QWORD *)this + 2) += 2LL;
    }
    *(_BYTE *)this = 1;
LABEL_44:
    v8 = 0;
    goto LABEL_45;
  }
LABEL_8:
  v8 = -2147467259;
LABEL_45:
  if ( hKey )
    RegCloseKey(hKey);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14000fdd8  mov     [rsp-28h+arg_0], rbx
0x14000fddd  mov     [rsp-28h+cbData], r8d
0x14000fde2  mov     qword ptr [rsp-28h+Type], rdx
0x14000fde7  push    rbp
0x14000fde8  push    rsi
0x14000fde9  push    rdi
0x14000fdea  push    r14
0x14000fdec  push    r15
0x14000fdee  mov     rbp, rsp
0x14000fdf1  sub     rsp, 50h
0x14000fdf5  lea     rax, [rbp+var_10]
0x14000fdf9  mov     [rbp+hKey], 0
0x14000fe01  mov     [rbp+Src], rax
0x14000fe05  mov     rsi, rcx
0x14000fe08  lea     rax, [rbp+var_10]
0x14000fe0c  mov     [rbp+Type], 0
0x14000fe13  mov     [rbp+var_18], rax
0x14000fe17  xor     eax, eax
0x14000fe19  mov     [rbp+var_10], ax
0x14000fe1d  mov     rax, [rcx+48h]
0x14000fe21  mov     [rbp+cbData], 0
0x14000fe28  cmp     [rcx+40h], rax
0x14000fe2c  jnz     short loc_14000FE38
0x14000fe2e  mov     eax, 801B8003h
0x14000fe33  jmp     loc_14001008F
0x14000fe38  cmp     byte ptr [rcx+1], 0
0x14000fe3c  jz      loc_140010063
0x14000fe42  cmp     byte ptr [rcx], 0
0x14000fe45  jnz     loc_140010063
0x14000fe4b  mov     rax, [rcx+28h]
0x14000fe4f  cmp     [rcx+20h], rax
0x14000fe53  jnz     short loc_14000FE5E
0x14000fe55  mov     rbx, 0FFFFFFFF80000002h
0x14000fe5c  jmp     short loc_14000FE98
0x14000fe5e  lea     rcx, [rbp+hKey]
0x14000fe62  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x14000fe67  mov     rdx, [rsi+20h]; lpSubKey
0x14000fe6b  mov     r9d, 20119h; samDesired
0x14000fe71  xor     r8d, r8d; ulOptions
0x14000fe74  mov     [rsp+50h+phkResult], rax; phkResult
0x14000fe79  mov     rcx, 0FFFFFFFF80000002h; hKey
0x14000fe80  call    cs:__imp_RegOpenKeyExW
0x14000fe86  test    eax, eax
0x14000fe88  jz      short loc_14000FE94
0x14000fe8a  mov     ebx, 80004005h
0x14000fe8f  jmp     loc_140010065
0x14000fe94  mov     rbx, [rbp+hKey]
0x14000fe98  mov     rdx, [rsi+40h]; lpValueName
0x14000fe9c  lea     rax, [rbp+cbData]
0x14000fea0  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000fea5  lea     r9, [rbp+Type]; lpType
0x14000fea9  xor     r8d, r8d; lpReserved
0x14000feac  mov     [rsp+50h+phkResult], 0; lpData
0x14000feb5  mov     rcx, rbx; hKey
0x14000feb8  call    cs:__imp_RegQueryValueExW
0x14000febe  test    eax, eax
0x14000fec0  jnz     short loc_14000FE8A
0x14000fec2  mov     edx, [rbp+Type]
0x14000fec5  lea     eax, [rdx-1]
0x14000fec8  cmp     eax, 1
0x14000fecb  mov     eax, [rbp+cbData]
0x14000fece  jbe     short loc_14000FEDA
0x14000fed0  cmp     edx, 7
0x14000fed3  jnz     short loc_14000FEDF
0x14000fed5  add     eax, 2
0x14000fed8  jmp     short loc_14000FEDC
0x14000feda  inc     eax
0x14000fedc  mov     [rbp+cbData], eax
0x14000fedf  xor     ecx, ecx
0x14000fee1  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x14000fee8  cmp     [r9+rcx*8+4], edx
0x14000feed  jz      short loc_14000FEFD
0x14000feef  inc     ecx
0x14000fef1  cmp     ecx, 0Bh
0x14000fef4  jb      short loc_14000FEE8
0x14000fef6  mov     ecx, 9
0x14000fefb  jmp     short loc_14000FF01
0x14000fefd  mov     ecx, [r9+rcx*8]
0x14000ff01  mov     edx, [rsi+4]
0x14000ff04  cmp     edx, ecx
0x14000ff06  jz      short loc_14000FF32
0x14000ff08  cmp     edx, 9
0x14000ff0b  jz      short loc_14000FF32
0x14000ff0d  cmp     edx, 5
0x14000ff10  jnz     short loc_14000FF17
0x14000ff12  cmp     ecx, 1
0x14000ff15  jz      short loc_14000FF32
0x14000ff17  cmp     edx, 1
0x14000ff1a  jnz     short loc_14000FF21
0x14000ff1c  cmp     ecx, 5
0x14000ff1f  jz      short loc_14000FF32
0x14000ff21  test    edx, edx
0x14000ff23  jnz     loc_14000FE8A
0x14000ff29  cmp     ecx, 1
0x14000ff2c  jnz     loc_14000FE8A
0x14000ff32  lea     rdi, [rsi+8]
0x14000ff36  mov     [rsi+4], ecx
0x14000ff39  mov     r14, [rdi+8]
0x14000ff3d  mov     r15d, eax
0x14000ff40  mov     rax, [rdi]
0x14000ff43  sub     r14, rax
0x14000ff46  cmp     r15, r14
0x14000ff49  jbe     short loc_14000FF78
0x14000ff4b  mov     edx, r15d
0x14000ff4e  mov     rcx, rdi
0x14000ff51  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000ff56  test    al, al
0x14000ff58  jnz     short loc_14000FF64
0x14000ff5a  mov     ebx, 8007000Eh
0x14000ff5f  jmp     loc_140010065
0x14000ff64  mov     rcx, [rdi+8]; void *
0x14000ff68  mov     r8, r15
0x14000ff6b  sub     r8, r14; Size
0x14000ff6e  xor     edx, edx; Val
0x14000ff70  call    memset_0
0x14000ff75  mov     rax, [rdi]
0x14000ff78  add     rax, r15
0x14000ff7b  lea     r9, [rbp+Type]; lpType
0x14000ff7f  mov     [rdi+8], rax
0x14000ff83  xor     r8d, r8d; lpReserved
0x14000ff86  mov     rdx, [rsi+40h]; lpValueName
0x14000ff8a  lea     rax, [rbp+cbData]
0x14000ff8e  mov     [rsp+50h+lpcbData], rax; lpcbData
0x14000ff93  mov     rcx, rbx; hKey
0x14000ff96  mov     rax, [rdi]
0x14000ff99  mov     [rsp+50h+phkResult], rax; lpData
0x14000ff9e  call    cs:__imp_RegQueryValueExW
0x14000ffa4  test    eax, eax
0x14000ffa6  mov     rax, [rdi]
0x14000ffa9  jz      short loc_14000FFB9
0x14000ffab  mov     ebx, 80004005h
0x14000ffb0  mov     [rdi+8], rax
0x14000ffb4  jmp     loc_140010065
0x14000ffb9  mov     r14, [rdi+8]
0x14000ffbd  mov     ebx, [rbp+cbData]
0x14000ffc0  sub     r14, rax
0x14000ffc3  cmp     rbx, r14
0x14000ffc6  ja      short loc_14000FFD1
0x14000ffc8  add     rax, rbx
0x14000ffcb  mov     [rdi+8], rax
0x14000ffcf  jmp     short loc_14000FFFB
0x14000ffd1  mov     rdx, rbx
0x14000ffd4  mov     rcx, rdi
0x14000ffd7  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x14000ffdc  test    al, al
0x14000ffde  jz      short loc_14000FFFB
0x14000ffe0  mov     rcx, [rdi+8]; void *
0x14000ffe4  mov     r8, rbx
0x14000ffe7  sub     r8, r14; Size
0x14000ffea  xor     edx, edx; Val
0x14000ffec  call    memset_0
0x14000fff1  mov     rcx, [rdi]
0x14000fff4  add     rcx, rbx
0x14000fff7  mov     [rdi+8], rcx
0x14000fffb  cmp     dword ptr [rsi+4], 5
0x14000ffff  jnz     short loc_140010060
0x140010001  mov     rcx, [rdi]; lpSrc
0x140010004  lea     rdx, [rbp+Src]
0x140010008  call    ?UtilExpandEnvironmentStrings@@YAJPEB_WPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z; UtilExpandEnvironmentStrings(wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *)
0x14001000d  mov     ebx, eax
0x14001000f  test    eax, eax
0x140010011  js      short loc_140010065
0x140010013  mov     r14, [rbp+Src]
0x140010017  mov     rax, [rbp+var_18]
0x14001001b  sub     rax, r14
0x14001001e  sar     rax, 1
0x140010021  lea     ecx, ds:2[rax*2]
0x140010028  mov     rax, [rdi]
0x14001002b  mov     ebx, ecx
0x14001002d  mov     [rbp+cbData], ecx
0x140010030  sub     rbx, r14
0x140010033  add     rbx, r14
0x140010036  mov     [rdi+8], rax
0x14001003a  mov     rdx, rbx
0x14001003d  mov     rcx, rdi
0x140010040  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x140010045  test    al, al
0x140010047  jz      loc_14000FF5A
0x14001004d  mov     rcx, [rdi+8]; void *
0x140010051  mov     r8, rbx; Size
0x140010054  mov     rdx, r14; Src
0x140010057  call    memcpy_0
0x14001005c  add     [rdi+8], rbx
0x140010060  mov     byte ptr [rsi], 1
0x140010063  xor     ebx, ebx
0x140010065  mov     rcx, [rbp+Src]; void *
0x140010069  lea     rax, [rbp+var_10]
0x14001006d  cmp     rcx, rax
0x140010070  jz      short loc_14001007E
0x140010072  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140010079  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14001007e  mov     rcx, [rbp+hKey]; hKey
0x140010082  test    rcx, rcx
0x140010085  jz      short loc_14001008D
0x140010087  call    cs:__imp_RegCloseKey
0x14001008d  mov     eax, ebx
0x14001008f  mov     rbx, [rsp+50h+arg_0]
0x140010097  add     rsp, 50h
0x14001009b  pop     r15
0x14001009d  pop     r14
0x14001009f  pop     rdi
0x1400100a0  pop     rsi
0x1400100a1  pop     rbp
0x1400100a2  retn
```
