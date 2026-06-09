# CRegSetting::Load(HKEY__ *,ulong)

- ea: `0x180009d14`
- end: `0x180009fbf`
- name: `?Load@CRegSetting@@QEAAJPEAUHKEY__@@K@Z`
- size: `683`
- prototype: `__int64 __fastcall(CRegSetting *this, HKEY, int)`
- caller_count: `3`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x18000a8f4`
- `0x18000b334`
- `0x180014860`

## callees

- `0x180005c80`
- `0x180009580`
- `0x1800098f8`
- `0x180009a78`
- `0x180009d14`
- `0x18000ad10`
- `0x18000aed0`
- `0x180016c06`
- `0x180016c1e`

## import_xrefs

- `ADVAPI32!RegOpenKeyExW` at `0x180009db0`
- `ADVAPI32!RegOpenKeyExW` at `0x180009db0`
- `ADVAPI32!RegQueryValueExW` at `0x180009de8`
- `ADVAPI32!RegQueryValueExW` at `0x180009ed0`
- `ADVAPI32!RegQueryValueExW` at `0x180009de8`
- `ADVAPI32!RegQueryValueExW` at `0x180009ed0`

## pseudocode

```c
__int64 __fastcall CRegSetting::Load(CRegSetting *this, HKEY a2, int a3)
{
  int v6; // ebx
  HKEY *phkResult; // rax
  __int64 v8; // r8
  DWORD v9; // eax
  __int64 i; // rcx
  int v11; // ecx
  int v12; // edx
  LPBYTE *v13; // rdi
  unsigned __int64 v14; // r15
  LPBYTE v15; // rax
  unsigned __int64 v16; // r14
  bool v17; // zf
  __int64 v18; // r8
  __int64 v19; // r9
  LPBYTE v20; // rax
  __int64 v21; // rbx
  unsigned __int64 v22; // r14
  __int64 v23; // r8
  __int64 v24; // r9
  const void *v25; // r14
  LPBYTE v26; // rax
  size_t v27; // rbx
  HKEY v29; // [rsp+30h] [rbp-30h] BYREF
  void *Src[5]; // [rsp+38h] [rbp-28h] BYREF
  DWORD cbData; // [rsp+98h] [rbp+38h] BYREF
  DWORD Type; // [rsp+A8h] [rbp+48h] BYREF

  v29 = 0;
  Type = 0;
  cbData = 0;
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>(Src);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 8) == *((_QWORD *)this + 9) )
    {
      v6 = -2145681405;
      goto LABEL_47;
    }
    if ( !*((_BYTE *)this + 1) || *(_BYTE *)this )
      goto LABEL_46;
    if ( *((_QWORD *)this + 4) != *((_QWORD *)this + 5) )
    {
      phkResult = (HKEY *)tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
      if ( RegOpenKeyExW(a2, *((LPCWSTR *)this + 4), 0, a3 | 0x20019, phkResult) )
      {
LABEL_9:
        v6 = -2147467259;
        goto LABEL_47;
      }
      a2 = v29;
    }
    if ( RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, 0, &cbData) )
      goto LABEL_9;
    v9 = cbData;
    if ( Type - 1 <= 1 )
    {
      v9 = cbData + 1;
    }
    else
    {
      if ( Type != 7 )
        goto LABEL_17;
      v9 = cbData + 2;
    }
    cbData = v9;
LABEL_17:
    for ( i = 0; (unsigned int)i < 0xB; i = (unsigned int)(i + 1) )
    {
      if ( *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i + 1) == Type )
      {
        v11 = *((_DWORD *)&CRegSetting::s_typeMapping + 2 * i);
        goto LABEL_23;
      }
    }
    v11 = 9;
LABEL_23:
    v12 = *((_DWORD *)this + 1);
    if ( v12 != v11 && v12 != 9 && (v12 != 5 || v11 != 1) && (v12 != 1 || v11 != 5) && (v12 || v11 != 1) )
      goto LABEL_9;
    v13 = (LPBYTE *)((char *)this + 8);
    *((_DWORD *)this + 1) = v11;
    v14 = v9;
    v15 = (LPBYTE)*((_QWORD *)this + 1);
    v16 = *((_QWORD *)this + 2) - (_QWORD)v15;
    if ( v14 > v16 )
    {
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               (unsigned int)v14,
                               v8,
                               &CRegSetting::s_typeMapping) )
      {
LABEL_33:
        v6 = -2147024882;
        goto LABEL_47;
      }
      memset_0(*((void **)this + 2), 0, v14 - v16);
      v15 = *v13;
    }
    *((_QWORD *)this + 2) = &v15[v14];
    v17 = RegQueryValueExW(a2, *((LPCWSTR *)this + 8), 0, &Type, *v13, &cbData) == 0;
    v20 = *v13;
    if ( !v17 )
    {
      v6 = -2147467259;
      *((_QWORD *)this + 2) = v20;
      goto LABEL_47;
    }
    v21 = cbData;
    v22 = *((_QWORD *)this + 2) - (_QWORD)v20;
    if ( cbData > v22 )
    {
      if ( (unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                              (char *)this + 8,
                              cbData,
                              v18,
                              v19) )
      {
        memset_0(*((void **)this + 2), 0, v21 - v22);
        *((_QWORD *)this + 2) = &(*v13)[v21];
      }
    }
    else
    {
      *((_QWORD *)this + 2) = &v20[cbData];
    }
    if ( *((_DWORD *)this + 1) == 5 )
    {
      v6 = UtilExpandEnvironmentStrings((LPCWSTR)*v13);
      if ( v6 < 0 )
        goto LABEL_47;
      v25 = Src[0];
      v26 = *v13;
      cbData = 2 * (((char *)Src[1] - (char *)Src[0]) >> 1) + 2;
      v27 = cbData;
      *((_QWORD *)this + 2) = v26;
      if ( !(unsigned __int8)utl::vector<unsigned char,utl::allocator<unsigned char>>::reserve(
                               (char *)this + 8,
                               v27,
                               v23,
                               v24) )
        goto LABEL_33;
      memcpy_0(*((void **)this + 2), v25, v27);
      *((_QWORD *)this + 2) += v27;
    }
    *(_BYTE *)this = 1;
LABEL_46:
    v6 = 0;
    goto LABEL_47;
  }
  v6 = -2147024809;
LABEL_47:
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit(Src);
  tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),0>>(&v29);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180009d14  mov     [rsp-28h+arg_0], rbx
0x180009d19  push    rbp
0x180009d1a  push    rsi
0x180009d1b  push    rdi
0x180009d1c  push    r14
0x180009d1e  push    r15
0x180009d20  mov     rbp, rsp
0x180009d23  sub     rsp, 60h
0x180009d27  mov     rsi, rcx
0x180009d2a  mov     [rbp+var_30], 0
0x180009d32  lea     rcx, [rbp+Src]; void *
0x180009d36  mov     [rbp+Type], 0
0x180009d3d  mov     edi, r8d
0x180009d40  mov     [rbp+cbData], 0
0x180009d47  mov     rbx, rdx
0x180009d4a  call    ??0?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA@AEBV?$allocator@G@1@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>(utl::allocator<ushort> const &)
0x180009d4f  test    rbx, rbx
0x180009d52  jnz     short loc_180009D5E
0x180009d54  mov     ebx, 80070057h
0x180009d59  jmp     loc_180009F97
0x180009d5e  mov     rax, [rsi+48h]
0x180009d62  cmp     [rsi+40h], rax
0x180009d66  jnz     short loc_180009D72
0x180009d68  mov     ebx, 801B8003h
0x180009d6d  jmp     loc_180009F97
0x180009d72  cmp     byte ptr [rsi+1], 0
0x180009d76  jz      loc_180009F95
0x180009d7c  cmp     byte ptr [rsi], 0
0x180009d7f  jnz     loc_180009F95
0x180009d85  mov     rax, [rsi+28h]
0x180009d89  cmp     [rsi+20h], rax
0x180009d8d  jz      short loc_180009DC8
0x180009d8f  lea     rcx, [rbp+var_30]
0x180009d93  call    ??$replace@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@YAPEAPEAUHKEY__@@AEAV?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@0@@Z; tlx::replace<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>> &)
0x180009d98  mov     rdx, [rsi+20h]; lpSubKey
0x180009d9c  or      edi, 20019h
0x180009da2  mov     r9d, edi; samDesired
0x180009da5  mov     [rsp+60h+phkResult], rax; phkResult
0x180009daa  xor     r8d, r8d; ulOptions
0x180009dad  mov     rcx, rbx; hKey
0x180009db0  call    cs:__imp_RegOpenKeyExW
0x180009db6  test    eax, eax
0x180009db8  jz      short loc_180009DC4
0x180009dba  mov     ebx, 80004005h
0x180009dbf  jmp     loc_180009F97
0x180009dc4  mov     rbx, [rbp+var_30]
0x180009dc8  mov     rdx, [rsi+40h]; lpValueName
0x180009dcc  lea     rax, [rbp+cbData]
0x180009dd0  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180009dd5  lea     r9, [rbp+Type]; lpType
0x180009dd9  xor     r8d, r8d; lpReserved
0x180009ddc  mov     [rsp+60h+phkResult], 0; lpData
0x180009de5  mov     rcx, rbx; hKey
0x180009de8  call    cs:__imp_RegQueryValueExW
0x180009dee  test    eax, eax
0x180009df0  jnz     short loc_180009DBA
0x180009df2  mov     edx, [rbp+Type]
0x180009df5  lea     eax, [rdx-1]
0x180009df8  cmp     eax, 1
0x180009dfb  mov     eax, [rbp+cbData]
0x180009dfe  jbe     short loc_180009E0A
0x180009e00  cmp     edx, 7
0x180009e03  jnz     short loc_180009E0F
0x180009e05  add     eax, 2
0x180009e08  jmp     short loc_180009E0C
0x180009e0a  inc     eax
0x180009e0c  mov     [rbp+cbData], eax
0x180009e0f  xor     ecx, ecx
0x180009e11  lea     r9, ?s_typeMapping@CRegSetting@@0QBUDATATYPE_REG_MAPPING@1@B; CRegSetting::DATATYPE_REG_MAPPING const near * const CRegSetting::s_typeMapping
0x180009e18  cmp     ecx, 0Bh
0x180009e1b  jnb     short loc_180009E2E
0x180009e1d  cmp     [r9+rcx*8+4], edx
0x180009e22  jz      short loc_180009E28
0x180009e24  inc     ecx
0x180009e26  jmp     short loc_180009E18
0x180009e28  mov     ecx, [r9+rcx*8]
0x180009e2c  jmp     short loc_180009E33
0x180009e2e  mov     ecx, 9
0x180009e33  mov     edx, [rsi+4]
0x180009e36  cmp     edx, ecx
0x180009e38  jz      short loc_180009E64
0x180009e3a  cmp     edx, 9
0x180009e3d  jz      short loc_180009E64
0x180009e3f  cmp     edx, 5
0x180009e42  jnz     short loc_180009E49
0x180009e44  cmp     ecx, 1
0x180009e47  jz      short loc_180009E64
0x180009e49  cmp     edx, 1
0x180009e4c  jnz     short loc_180009E53
0x180009e4e  cmp     ecx, 5
0x180009e51  jz      short loc_180009E64
0x180009e53  test    edx, edx
0x180009e55  jnz     loc_180009DBA
0x180009e5b  cmp     ecx, 1
0x180009e5e  jnz     loc_180009DBA
0x180009e64  lea     rdi, [rsi+8]
0x180009e68  mov     [rsi+4], ecx
0x180009e6b  mov     r14, [rdi+8]
0x180009e6f  mov     r15d, eax
0x180009e72  mov     rax, [rdi]
0x180009e75  sub     r14, rax
0x180009e78  cmp     r15, r14
0x180009e7b  jbe     short loc_180009EAA
0x180009e7d  mov     edx, r15d
0x180009e80  mov     rcx, rdi
0x180009e83  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180009e88  test    al, al
0x180009e8a  jnz     short loc_180009E96
0x180009e8c  mov     ebx, 8007000Eh
0x180009e91  jmp     loc_180009F97
0x180009e96  mov     rcx, [rdi+8]; void *
0x180009e9a  mov     r8, r15
0x180009e9d  sub     r8, r14; Size
0x180009ea0  xor     edx, edx; Val
0x180009ea2  call    memset_0
0x180009ea7  mov     rax, [rdi]
0x180009eaa  add     rax, r15
0x180009ead  lea     r9, [rbp+Type]; lpType
0x180009eb1  mov     [rdi+8], rax
0x180009eb5  xor     r8d, r8d; lpReserved
0x180009eb8  mov     rdx, [rsi+40h]; lpValueName
0x180009ebc  lea     rax, [rbp+cbData]
0x180009ec0  mov     [rsp+60h+lpcbData], rax; lpcbData
0x180009ec5  mov     rcx, rbx; hKey
0x180009ec8  mov     rax, [rdi]
0x180009ecb  mov     [rsp+60h+phkResult], rax; lpData
0x180009ed0  call    cs:__imp_RegQueryValueExW
0x180009ed6  test    eax, eax
0x180009ed8  mov     rax, [rdi]
0x180009edb  jz      short loc_180009EEB
0x180009edd  mov     ebx, 80004005h
0x180009ee2  mov     [rdi+8], rax
0x180009ee6  jmp     loc_180009F97
0x180009eeb  mov     r14, [rdi+8]
0x180009eef  mov     ebx, [rbp+cbData]
0x180009ef2  sub     r14, rax
0x180009ef5  cmp     rbx, r14
0x180009ef8  ja      short loc_180009F03
0x180009efa  add     rax, rbx
0x180009efd  mov     [rdi+8], rax
0x180009f01  jmp     short loc_180009F2D
0x180009f03  mov     rdx, rbx
0x180009f06  mov     rcx, rdi
0x180009f09  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180009f0e  test    al, al
0x180009f10  jz      short loc_180009F2D
0x180009f12  mov     rcx, [rdi+8]; void *
0x180009f16  mov     r8, rbx
0x180009f19  sub     r8, r14; Size
0x180009f1c  xor     edx, edx; Val
0x180009f1e  call    memset_0
0x180009f23  mov     rcx, [rdi]
0x180009f26  add     rcx, rbx
0x180009f29  mov     [rdi+8], rcx
0x180009f2d  cmp     dword ptr [rsi+4], 5
0x180009f31  jnz     short loc_180009F92
0x180009f33  mov     rcx, [rdi]; lpSrc
0x180009f36  lea     rdx, [rbp+Src]
0x180009f3a  call    ?UtilExpandEnvironmentStrings@@YAJPEBGPEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@Z; UtilExpandEnvironmentStrings(ushort const *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> *)
0x180009f3f  mov     ebx, eax
0x180009f41  test    eax, eax
0x180009f43  js      short loc_180009F97
0x180009f45  mov     r14, [rbp+Src]
0x180009f49  mov     rax, [rbp+var_20]
0x180009f4d  sub     rax, r14
0x180009f50  sar     rax, 1
0x180009f53  lea     ecx, ds:2[rax*2]
0x180009f5a  mov     rax, [rdi]
0x180009f5d  mov     ebx, ecx
0x180009f5f  mov     [rbp+cbData], ecx
0x180009f62  sub     rbx, r14
0x180009f65  add     rbx, r14
0x180009f68  mov     [rdi+8], rax
0x180009f6c  mov     rdx, rbx
0x180009f6f  mov     rcx, rdi
0x180009f72  call    ?reserve@?$vector@EV?$allocator@E@utl@@@utl@@QEAA_N_K@Z; utl::vector<uchar,utl::allocator<uchar>>::reserve(unsigned __int64)
0x180009f77  test    al, al
0x180009f79  jz      loc_180009E8C
0x180009f7f  mov     rcx, [rdi+8]; void *
0x180009f83  mov     r8, rbx; Size
0x180009f86  mov     rdx, r14; Src
0x180009f89  call    memcpy_0
0x180009f8e  add     [rdi+8], rbx
0x180009f92  mov     byte ptr [rsi], 1
0x180009f95  xor     ebx, ebx
0x180009f97  lea     rcx, [rbp+Src]
0x180009f9b  call    ?_Uninit@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@AEAAXXZ; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::_Uninit(void)
0x180009fa0  lea     rcx, [rbp+var_30]
0x180009fa4  call    ??1?$unique_any@U?$handle_traits@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@Z$0A@@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>::~unique_any<tlx::handle_traits<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),0>>(void)
0x180009fa9  mov     eax, ebx
0x180009fab  mov     rbx, [rsp+60h+arg_0]
0x180009fb3  add     rsp, 60h
0x180009fb7  pop     r15
0x180009fb9  pop     r14
0x180009fbb  pop     rdi
0x180009fbc  pop     rsi
0x180009fbd  pop     rbp
0x180009fbe  retn
```
