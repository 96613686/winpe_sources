# CSrmFileSafe::CreateMetadataFolder(ushort const *)

- ea: `0x180077c54`
- end: `0x180077fcf`
- name: `?CreateMetadataFolder@CSrmFileSafe@@AEAAXPEBG@Z`
- size: `891`
- prototype: `void(CSrmFileSafe *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180079b9c`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x180010bc4`
- `0x18006febc`
- `0x1800700b8`
- `0x180077704`
- `0x18007791c`
- `0x180077c54`
- `0x18007c16c`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180077d25`
- `OLEAUT32!__imp_SysAllocString` at `0x180077d6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180077db5`
- `OLEAUT32!__imp_SysAllocString` at `0x180077dfd`
- `OLEAUT32!__imp_SysAllocString` at `0x180077ee0`
- `OLEAUT32!__imp_SysAllocString` at `0x180077d25`
- `OLEAUT32!__imp_SysAllocString` at `0x180077d6d`
- `OLEAUT32!__imp_SysAllocString` at `0x180077db5`
- `OLEAUT32!__imp_SysAllocString` at `0x180077dfd`
- `OLEAUT32!__imp_SysAllocString` at `0x180077ee0`
- `OLEAUT32!__imp_SysFreeString` at `0x180077cf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180077d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180077da8`
- `OLEAUT32!__imp_SysFreeString` at `0x180077df0`
- `OLEAUT32!__imp_SysFreeString` at `0x180077e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ea7`
- `OLEAUT32!__imp_SysFreeString` at `0x180077cf2`
- `OLEAUT32!__imp_SysFreeString` at `0x180077d60`
- `OLEAUT32!__imp_SysFreeString` at `0x180077da8`
- `OLEAUT32!__imp_SysFreeString` at `0x180077df0`
- `OLEAUT32!__imp_SysFreeString` at `0x180077e38`
- `OLEAUT32!__imp_SysFreeString` at `0x180077ea7`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d3f`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d87`
- `OLEAUT32!__imp_SysStringLen` at `0x180077dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180077e17`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d3f`
- `OLEAUT32!__imp_SysStringLen` at `0x180077d87`
- `OLEAUT32!__imp_SysStringLen` at `0x180077dcf`
- `OLEAUT32!__imp_SysStringLen` at `0x180077e17`
- `KERNEL32!SetFileAttributesW` at `0x180077e7d`
- `KERNEL32!SetFileAttributesW` at `0x180077e7d`

## string_xrefs

- `0x180077c88`: `CSrmFileSafe::CreateMetadataFolder`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CSrmFileSafe::CreateMetadataFolder(CSrmFileSafe *this, const unsigned __int16 *a2)
{
  __int64 v3; // rdi
  __int64 v4; // rax
  OLECHAR *v5; // rax
  unsigned __int16 *v6; // rbx
  UINT v7; // eax
  int v8; // eax
  OLECHAR *v9; // rax
  unsigned __int16 *v10; // rbx
  UINT v11; // eax
  int v12; // eax
  OLECHAR *v13; // rax
  unsigned __int16 *v14; // rbx
  UINT v15; // eax
  int v16; // eax
  OLECHAR *v17; // rax
  unsigned __int16 *v18; // rbx
  UINT v19; // eax
  int v20; // eax
  WCHAR *v21; // rbx
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-D8h] BYREF
  OLECHAR *v24; // [rsp+30h] [rbp-D0h]
  _QWORD v25[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v26; // [rsp+50h] [rbp-B0h]
  int v27; // [rsp+54h] [rbp-ACh]
  int v28; // [rsp+58h] [rbp-A8h]
  _BYTE v29[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v30; // [rsp+C0h] [rbp-40h]
  void *Block[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v32; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v33; // [rsp+E0h] [rbp-20h]
  _QWORD v34[22]; // [rsp+F0h] [rbp-10h] BYREF

  v25[0] = L"base\\fs\\fsrm\\utilities\\file\\filesafe.cpp";
  v25[1] = L"CSrmFileSafe::CreateMetadataFolder";
  v25[2] = L"FILESF_C";
  v26 = 1083;
  v27 = 17;
  v28 = 255;
  v30 = 0x1000000;
  memset_0(v29, 0, sizeof(v29));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)v34, (const struct CSrmDebugInfo *)v25, 0);
  lpFileName = 0;
  SrmCreateSystemVolumeInformationFolder(a2);
  SysFreeString(0);
  if ( a2 )
  {
    lpFileName = SysAllocString(a2);
    if ( !lpFileName )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    lpFileName = 0;
  }
  v3 = -1;
  v4 = -1;
  do
    ++v4;
  while ( a2[v4] );
  if ( a2[v4 - 1] != 92 )
  {
    v5 = SysAllocString(L"\\");
    v6 = v5;
    v24 = v5;
    if ( !v5 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
    v7 = SysStringLen(v5);
    v8 = CSrmComBSTR::Append((CSrmComBSTR *)&lpFileName, v6, v7);
    if ( v8 < 0 )
    {
      pExceptionObject = v8;
      throw (long *)&pExceptionObject;
    }
    SysFreeString(v6);
  }
  v9 = SysAllocString(L"System Volume Information");
  v10 = v9;
  v24 = v9;
  if ( !v9 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v11 = SysStringLen(v9);
  v12 = CSrmComBSTR::Append((CSrmComBSTR *)&lpFileName, v10, v11);
  if ( v12 < 0 )
  {
    pExceptionObject = v12;
    throw (long *)&pExceptionObject;
  }
  SysFreeString(v10);
  v13 = SysAllocString(L"\\");
  v14 = v13;
  v24 = v13;
  if ( !v13 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v15 = SysStringLen(v13);
  v16 = CSrmComBSTR::Append((CSrmComBSTR *)&lpFileName, v14, v15);
  if ( v16 < 0 )
  {
    pExceptionObject = v16;
    throw (long *)&pExceptionObject;
  }
  SysFreeString(v14);
  v17 = SysAllocString(L"SRM");
  v18 = v17;
  v24 = v17;
  if ( !v17 )
  {
    pExceptionObject = -2147024882;
    throw (long *)&pExceptionObject;
  }
  v19 = SysStringLen(v17);
  v20 = CSrmComBSTR::Append((CSrmComBSTR *)&lpFileName, v18, v19);
  if ( v20 < 0 )
  {
    pExceptionObject = v20;
    throw (long *)&pExceptionObject;
  }
  SysFreeString(v18);
  v21 = (WCHAR *)lpFileName;
  v33 = 7;
  v32 = 0;
  LOWORD(Block[0]) = 0;
  do
    ++v3;
  while ( lpFileName[v3] );
  std::wstring::assign(Block, (void *)lpFileName);
  CSrmFileSafe::CreateDirectoryInternal((LPCWSTR)Block);
  SetFileAttributesW(v21, 6u);
  if ( v33 >= 8 )
    operator delete(Block[0]);
  v33 = 7;
  v32 = 0;
  LOWORD(Block[0]) = 0;
  SysFreeString(v21);
  v34[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v34);
}

```

## disassembly

```asm
0x180077c54  push    rbp
0x180077c56  push    rbx
0x180077c57  push    rsi
0x180077c58  push    rdi
0x180077c59  lea     rbp, [rsp-0B8h]
0x180077c61  sub     rsp, 1B8h
0x180077c68  mov     rax, cs:__security_cookie
0x180077c6f  xor     rax, rsp
0x180077c72  mov     [rbp+0D0h+var_30], rax
0x180077c79  mov     rbx, rdx
0x180077c7c  lea     rax, aBaseFsFsrmUtil_10; "base\\fs\\fsrm\\utilities\\file\\filesa"...
0x180077c83  mov     [rsp+1D0h+var_198], rax
0x180077c88  lea     rax, aCsrmfilesafeCr_0; "CSrmFileSafe::CreateMetadataFolder"
0x180077c8f  mov     [rsp+1D0h+var_190], rax
0x180077c94  lea     rax, aFilesfC; "FILESF_C"
0x180077c9b  mov     [rsp+1D0h+var_188], rax
0x180077ca0  mov     [rsp+1D0h+var_180], 43Bh
0x180077ca8  mov     [rsp+1D0h+var_17C], 11h
0x180077cb0  mov     [rsp+1D0h+var_178], 0FFh
0x180077cb8  xor     esi, esi
0x180077cba  mov     [rbp+0D0h+var_110], 1000000h
0x180077cc1  xor     edx, edx; Val
0x180077cc3  lea     r8d, [rsi+60h]; Size
0x180077cc7  lea     rcx, [rsp+1D0h+var_170]; void *
0x180077ccc  call    memset_0
0x180077cd1  xor     r8d, r8d
0x180077cd4  lea     rdx, [rsp+1D0h+var_198]
0x180077cd9  lea     rcx, [rbp+0D0h+var_E0]
0x180077cdd  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180077ce2  nop
0x180077ce3  mov     [rsp+1D0h+lpFileName], rsi
0x180077ce8  mov     rcx, rbx; unsigned __int16 *
0x180077ceb  call    ?SrmCreateSystemVolumeInformationFolder@@YAXPEBG@Z; SrmCreateSystemVolumeInformationFolder(ushort const *)
0x180077cf0  xor     ecx, ecx; bstrString
0x180077cf2  call    cs:__imp_SysFreeString
0x180077cf8  test    rbx, rbx
0x180077cfb  jnz     loc_180077EDD
0x180077d01  mov     [rsp+1D0h+lpFileName], rsi
0x180077d06  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180077d0a  mov     rax, rdi
0x180077d0d  inc     rax
0x180077d10  cmp     [rbx+rax*2], si
0x180077d14  jnz     short loc_180077D0D
0x180077d16  cmp     word ptr [rbx+rax*2-2], 5Ch ; '\'
0x180077d1c  jz      short loc_180077D66
0x180077d1e  lea     rcx, psz; "\\"
0x180077d25  call    cs:__imp_SysAllocString
0x180077d2b  mov     rbx, rax
0x180077d2e  mov     [rsp+1D0h+var_1A0], rax
0x180077d33  test    rax, rax
0x180077d36  jz      loc_180077F25
0x180077d3c  mov     rcx, rbx; pbstr
0x180077d3f  call    cs:__imp_SysStringLen
0x180077d45  mov     r8d, eax; int
0x180077d48  mov     rdx, rbx; unsigned __int16 *
0x180077d4b  lea     rcx, [rsp+1D0h+lpFileName]; this
0x180077d50  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x180077d55  test    eax, eax
0x180077d57  js      loc_180077F3F
0x180077d5d  mov     rcx, rbx; bstrString
0x180077d60  call    cs:__imp_SysFreeString
0x180077d66  lea     rcx, aSystemVolumeIn; "System Volume Information"
0x180077d6d  call    cs:__imp_SysAllocString
0x180077d73  mov     rbx, rax
0x180077d76  mov     [rsp+1D0h+var_1A0], rax
0x180077d7b  test    rax, rax
0x180077d7e  jz      loc_180077F55
0x180077d84  mov     rcx, rax; pbstr
0x180077d87  call    cs:__imp_SysStringLen
0x180077d8d  mov     r8d, eax; int
0x180077d90  mov     rdx, rbx; unsigned __int16 *
0x180077d93  lea     rcx, [rsp+1D0h+lpFileName]; this
0x180077d98  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x180077d9d  test    eax, eax
0x180077d9f  js      loc_180077F6F
0x180077da5  mov     rcx, rbx; bstrString
0x180077da8  call    cs:__imp_SysFreeString
0x180077dae  lea     rcx, psz; "\\"
0x180077db5  call    cs:__imp_SysAllocString
0x180077dbb  mov     rbx, rax
0x180077dbe  mov     [rsp+1D0h+var_1A0], rax
0x180077dc3  test    rax, rax
0x180077dc6  jz      loc_180077F85
0x180077dcc  mov     rcx, rax; pbstr
0x180077dcf  call    cs:__imp_SysStringLen
0x180077dd5  mov     r8d, eax; int
0x180077dd8  mov     rdx, rbx; unsigned __int16 *
0x180077ddb  lea     rcx, [rsp+1D0h+lpFileName]; this
0x180077de0  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x180077de5  test    eax, eax
0x180077de7  js      loc_180077F9F
0x180077ded  mov     rcx, rbx; bstrString
0x180077df0  call    cs:__imp_SysFreeString
0x180077df6  lea     rcx, aSrm_0; "SRM"
0x180077dfd  call    cs:__imp_SysAllocString
0x180077e03  mov     rbx, rax
0x180077e06  mov     [rsp+1D0h+var_1A0], rax
0x180077e0b  test    rax, rax
0x180077e0e  jz      loc_180077FB5
0x180077e14  mov     rcx, rax; pbstr
0x180077e17  call    cs:__imp_SysStringLen
0x180077e1d  mov     r8d, eax; int
0x180077e20  mov     rdx, rbx; unsigned __int16 *
0x180077e23  lea     rcx, [rsp+1D0h+lpFileName]; this
0x180077e28  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x180077e2d  test    eax, eax
0x180077e2f  js      loc_180077EF5
0x180077e35  mov     rcx, rbx; bstrString
0x180077e38  call    cs:__imp_SysFreeString
0x180077e3e  mov     rbx, [rsp+1D0h+lpFileName]
0x180077e43  mov     [rbp+0D0h+var_F0], 7
0x180077e4b  mov     [rbp+0D0h+var_F8], rsi
0x180077e4f  mov     word ptr [rbp+0D0h+Block], si
0x180077e53  inc     rdi
0x180077e56  cmp     [rbx+rdi*2], si
0x180077e5a  jnz     short loc_180077E53
0x180077e5c  mov     r8, rdi
0x180077e5f  mov     rdx, rbx; Src
0x180077e62  lea     rcx, [rbp+0D0h+Block]; void *
0x180077e66  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180077e6b  nop
0x180077e6c  lea     rcx, [rbp+0D0h+Block]; lpPathName
0x180077e70  call    ?CreateDirectoryInternal@CSrmFileSafe@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CSrmFileSafe::CreateDirectoryInternal(std::wstring const &)
0x180077e75  mov     edx, 6; dwFileAttributes
0x180077e7a  mov     rcx, rbx; lpFileName
0x180077e7d  call    cs:__imp_SetFileAttributesW
0x180077e83  nop
0x180077e84  cmp     [rbp+0D0h+var_F0], 8
0x180077e89  jb      short loc_180077E94
0x180077e8b  mov     rcx, [rbp+0D0h+Block]; Block
0x180077e8f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180077e94  mov     [rbp+0D0h+var_F0], 7
0x180077e9c  mov     [rbp+0D0h+var_F8], rsi
0x180077ea0  mov     word ptr [rbp+0D0h+Block], si
0x180077ea4  mov     rcx, rbx; bstrString
0x180077ea7  call    cs:__imp_SysFreeString
0x180077ead  nop
0x180077eae  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180077eb5  mov     [rbp+0D0h+var_E0], rax
0x180077eb9  lea     rcx, [rbp+0D0h+var_E0]; this
0x180077ebd  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180077ec2  mov     rcx, [rbp+0D0h+var_30]
0x180077ec9  xor     rcx, rsp; StackCookie
0x180077ecc  call    __security_check_cookie
0x180077ed1  add     rsp, 1B8h
0x180077ed8  pop     rdi
0x180077ed9  pop     rsi
0x180077eda  pop     rbx
0x180077edb  pop     rbp
0x180077edc  retn
0x180077edd  mov     rcx, rbx; psz
0x180077ee0  call    cs:__imp_SysAllocString
0x180077ee6  mov     [rsp+1D0h+lpFileName], rax
0x180077eeb  test    rax, rax
0x180077eee  jz      short loc_180077F0B
0x180077ef0  jmp     loc_180077D06
0x180077ef5  mov     [rsp+1D0h+pExceptionObject], eax
0x180077ef9  lea     rdx, _TI1J; pThrowInfo
0x180077f00  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f05  call    _CxxThrowException_0
0x180077f0b  mov     [rsp+1D0h+pExceptionObject], 8007000Eh
0x180077f13  lea     rdx, _TI1J; pThrowInfo
0x180077f1a  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f1f  call    _CxxThrowException_0
0x180077f25  mov     [rsp+1D0h+pExceptionObject], 8007000Eh
0x180077f2d  lea     rdx, _TI1J; pThrowInfo
0x180077f34  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f39  call    _CxxThrowException_0
0x180077f3f  mov     [rsp+1D0h+pExceptionObject], eax
0x180077f43  lea     rdx, _TI1J; pThrowInfo
0x180077f4a  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f4f  call    _CxxThrowException_0
0x180077f55  mov     [rsp+1D0h+pExceptionObject], 8007000Eh
0x180077f5d  lea     rdx, _TI1J; pThrowInfo
0x180077f64  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f69  call    _CxxThrowException_0
0x180077f6f  mov     [rsp+1D0h+pExceptionObject], eax
0x180077f73  lea     rdx, _TI1J; pThrowInfo
0x180077f7a  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f7f  call    _CxxThrowException_0
0x180077f85  mov     [rsp+1D0h+pExceptionObject], 8007000Eh
0x180077f8d  lea     rdx, _TI1J; pThrowInfo
0x180077f94  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077f99  call    _CxxThrowException_0
0x180077f9f  mov     [rsp+1D0h+pExceptionObject], eax
0x180077fa3  lea     rdx, _TI1J; pThrowInfo
0x180077faa  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077faf  call    _CxxThrowException_0
0x180077fb5  mov     [rsp+1D0h+pExceptionObject], 8007000Eh
0x180077fbd  lea     rdx, _TI1J; pThrowInfo
0x180077fc4  lea     rcx, [rsp+1D0h+pExceptionObject]; pExceptionObject
0x180077fc9  call    _CxxThrowException_0
```
