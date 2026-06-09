# SrmDoesPathExist(ushort const *,ulong *)

- ea: `0x18007c45c`
- end: `0x18007c7a8`
- name: `?SrmDoesPathExist@@YA_NPEBGPEAK@Z`
- size: `844`
- prototype: `bool __fastcall(const unsigned __int16 *, unsigned int *)`
- caller_count: `4`
- callee_count: `13`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180050fd0`
- `0x18005162c`
- `0x18006fb7c`
- `0x1800996f0`

## callees

- `0x1800020ba`
- `0x180006a1c`
- `0x1800095f4`
- `0x18006febc`
- `0x1800700b8`
- `0x180073a80`
- `0x180077704`
- `0x18007b114`
- `0x18007c45c`
- `0x18007e620`
- `0x1800b078a`
- `0x1800b07a2`
- `0x1800b07d0`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18007c664`
- `ole32!CoTaskMemFree` at `0x18007c664`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c5bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c691`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c5bd`
- `OLEAUT32!__imp_SysAllocString` at `0x18007c691`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c635`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c658`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c5f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c635`
- `OLEAUT32!__imp_SysFreeString` at `0x18007c658`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c5d7`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c614`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c5d7`
- `OLEAUT32!__imp_SysStringLen` at `0x18007c614`
- `KERNEL32!GetFileAttributesW` at `0x18007c640`
- `KERNEL32!GetFileAttributesW` at `0x18007c640`

## string_xrefs

- `0x18007c495`: `base\fs\fsrm\utilities\path\srmpath.cpp`
- `0x18007c4ad`: `SRMPATHC`
- `0x18007c4a1`: `SrmDoesPathExist`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
bool __fastcall SrmDoesPathExist(const unsigned __int16 *a1, unsigned int *a2)
{
  __int64 v4; // rdx
  const unsigned __int16 *v5; // rax
  unsigned int v6; // ecx
  __int64 v7; // r8
  int v8; // eax
  OLECHAR *v9; // rax
  unsigned __int16 *v10; // rbx
  UINT v11; // eax
  int v12; // eax
  OLECHAR *v13; // rbx
  UINT v14; // eax
  int v15; // eax
  DWORD FileAttributesW; // eax
  bool v17; // bl
  int Hr; // eax
  char v20; // al
  char v21; // al
  int pExceptionObject; // [rsp+20h] [rbp-E0h] BYREF
  wchar_t *String2; // [rsp+28h] [rbp-D8h] BYREF
  LPCWSTR lpFileName; // [rsp+30h] [rbp-D0h] BYREF
  OLECHAR *v25; // [rsp+38h] [rbp-C8h]
  _QWORD v26[4]; // [rsp+40h] [rbp-C0h] BYREF
  int v27; // [rsp+60h] [rbp-A0h]
  _BYTE v28[96]; // [rsp+68h] [rbp-98h] BYREF
  int v29; // [rsp+C8h] [rbp-38h]
  void **v30; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v31; // [rsp+D8h] [rbp-28h]

  v25 = (OLECHAR *)v26;
  v26[0] = L"base\\fs\\fsrm\\utilities\\path\\srmpath.cpp";
  v26[1] = L"SrmDoesPathExist";
  v26[2] = L"SRMPATHC";
  v26[3] = 835;
  v27 = 255;
  v29 = 0x1000000;
  memset_0(v28, 0, sizeof(v28));
  CSrmFunctionTracer::CSrmFunctionTracer((__int64)&v30, (const struct CSrmDebugInfo *)v26, 0);
  if ( !a1 )
  {
    v6 = -2147024809;
LABEL_23:
    v31 = v6;
LABEL_24:
    v30 = &CSrmFunctionTracer::`vftable';
    CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
    return 0;
  }
  v4 = 0x8000;
  v5 = a1;
  do
  {
    if ( !*v5 )
      break;
    ++v5;
    --v4;
  }
  while ( v4 );
  v6 = v4 == 0 ? 0x80070057 : 0;
  v7 = (0x8000 - v4) & -(__int64)(v4 != 0);
  if ( !v4 )
    goto LABEL_23;
  v31 = v4 == 0 ? 0x80070057 : 0;
  if ( !v7 || a1[v7 - 1] == 58 )
    goto LABEL_24;
  String2 = 0;
  v8 = TrimEdgeQuotes(a1, &String2);
  v31 = v8;
  if ( v8 < 0 )
  {
    Hr = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, Hr);
    v20 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0x350u, v20, 0);
  }
  v31 = v8;
  if ( !CheckAndPreparePath(String2) )
  {
    CSrmFunctionTracerBase::SetHr((CSrmFunctionTracerBase *)&v30, -2147024809);
    v21 = CSrmFunctionTracerBase::GetHr((CSrmFunctionTracerBase *)&v30);
    CSrmFunctionTracer::Throw((CSrmFunctionTracer *)&v30, 0x352u, v21, 0);
  }
  v31 = 0;
  lpFileName = 0;
  if ( wcsncmp_0(L"\\\\?\\", String2, 4u) )
  {
    v9 = SysAllocString(L"\\\\?\\");
    v10 = v9;
    v25 = v9;
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
  }
  if ( String2 )
  {
    v13 = SysAllocString(String2);
    v25 = v13;
    if ( !v13 )
    {
      pExceptionObject = -2147024882;
      throw (long *)&pExceptionObject;
    }
  }
  else
  {
    v13 = 0;
    v25 = 0;
  }
  v14 = SysStringLen(v13);
  v15 = CSrmComBSTR::Append((CSrmComBSTR *)&lpFileName, v13, v14);
  if ( v15 < 0 )
  {
    pExceptionObject = v15;
    throw (long *)&pExceptionObject;
  }
  SysFreeString(v13);
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( a2 )
    *a2 = FileAttributesW;
  v17 = FileAttributesW != -1;
  SysFreeString((BSTR)lpFileName);
  CoTaskMemFree(String2);
  String2 = 0;
  v30 = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)&v30);
  return v17;
}

```

## disassembly

```asm
0x18007c45c  mov     [rsp-8+arg_10], rbx
0x18007c461  push    rbp
0x18007c462  push    rsi
0x18007c463  push    r14
0x18007c465  lea     rbp, [rsp-90h]
0x18007c46d  sub     rsp, 190h
0x18007c474  mov     rax, cs:__security_cookie
0x18007c47b  xor     rax, rsp
0x18007c47e  mov     [rbp+0A0h+var_20], rax
0x18007c485  mov     rsi, rdx
0x18007c488  mov     rbx, rcx
0x18007c48b  lea     rax, [rsp+1A0h+var_160]
0x18007c490  mov     [rsp+1A0h+var_168], rax
0x18007c495  lea     rax, aBaseFsFsrmUtil_6; "base\\fs\\fsrm\\utilities\\path\\srmpat"...
0x18007c49c  mov     [rsp+1A0h+var_160], rax
0x18007c4a1  lea     rax, aSrmdoespathexi; "SrmDoesPathExist"
0x18007c4a8  mov     [rsp+1A0h+var_158], rax
0x18007c4ad  lea     rax, aSrmpathc; "SRMPATHC"
0x18007c4b4  mov     [rsp+1A0h+var_150], rax
0x18007c4b9  mov     [rsp+1A0h+var_148], 343h
0x18007c4c2  xor     r14d, r14d
0x18007c4c5  mov     [rsp+1A0h+var_140], 0FFh
0x18007c4cd  mov     [rbp+0A0h+var_D8], 1000000h
0x18007c4d4  xor     edx, edx; Val
0x18007c4d6  lea     r8d, [r14+60h]; Size
0x18007c4da  lea     rcx, [rsp+1A0h+var_138]; void *
0x18007c4df  call    memset_0
0x18007c4e4  nop
0x18007c4e5  xor     r8d, r8d
0x18007c4e8  lea     rdx, [rsp+1A0h+var_160]
0x18007c4ed  lea     rcx, [rbp+0A0h+var_D0]
0x18007c4f1  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x18007c4f6  nop
0x18007c4f7  test    rbx, rbx
0x18007c4fa  jz      loc_18007C6A9
0x18007c500  mov     r9d, 8000h
0x18007c506  mov     edx, r9d
0x18007c509  mov     rax, rbx
0x18007c50c  cmp     [rax], r14w
0x18007c510  jz      short loc_18007C51C
0x18007c512  add     rax, 2
0x18007c516  sub     rdx, 1
0x18007c51a  jnz     short loc_18007C50C
0x18007c51c  mov     rax, rdx
0x18007c51f  neg     rax
0x18007c522  sbb     ecx, ecx
0x18007c524  not     ecx
0x18007c526  and     ecx, 80070057h
0x18007c52c  mov     rax, rdx
0x18007c52f  sub     r9, rdx
0x18007c532  neg     rax
0x18007c535  sbb     r8, r8
0x18007c538  and     r8, r9
0x18007c53b  test    rdx, rdx
0x18007c53e  jz      loc_18007C6AE
0x18007c544  mov     [rbp+0A0h+var_C8], ecx
0x18007c547  test    r8, r8
0x18007c54a  jz      loc_18007C6B1
0x18007c550  cmp     word ptr [rbx+r8*2-2], 3Ah ; ':'
0x18007c557  jz      loc_18007C6B1
0x18007c55d  mov     [rsp+1A0h+String2], r14
0x18007c562  lea     rdx, [rsp+1A0h+String2]; unsigned __int16 **
0x18007c567  mov     rcx, rbx; unsigned __int16 *
0x18007c56a  call    ?TrimEdgeQuotes@@YAJPEBGPEAPEAG@Z; TrimEdgeQuotes(ushort const *,ushort * *)
0x18007c56f  mov     [rbp+0A0h+var_C8], eax
0x18007c572  test    eax, eax
0x18007c574  js      loc_18007C71A
0x18007c57a  mov     [rbp+0A0h+var_C8], eax
0x18007c57d  mov     [rbp+0A0h+var_C8], eax
0x18007c580  mov     rcx, [rsp+1A0h+String2]; String2
0x18007c585  call    ?CheckAndPreparePath@@YA_NPEAG@Z; CheckAndPreparePath(ushort *)
0x18007c58a  test    al, al
0x18007c58c  jz      loc_18007C74C
0x18007c592  mov     [rbp+0A0h+var_C8], r14d
0x18007c596  mov     [rsp+1A0h+lpFileName], r14
0x18007c59b  mov     r8d, 4; MaxCount
0x18007c5a1  mov     rdx, [rsp+1A0h+String2]; String2
0x18007c5a6  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007c5ad  call    wcsncmp_0
0x18007c5b2  test    eax, eax
0x18007c5b4  jz      short loc_18007C5FE
0x18007c5b6  lea     rcx, asc_1800EFAE0; "\\\\?\\"
0x18007c5bd  call    cs:__imp_SysAllocString
0x18007c5c3  mov     rbx, rax
0x18007c5c6  mov     [rsp+1A0h+var_168], rax
0x18007c5cb  test    rax, rax
0x18007c5ce  jz      loc_18007C778
0x18007c5d4  mov     rcx, rax; pbstr
0x18007c5d7  call    cs:__imp_SysStringLen
0x18007c5dd  mov     r8d, eax; int
0x18007c5e0  mov     rdx, rbx; unsigned __int16 *
0x18007c5e3  lea     rcx, [rsp+1A0h+lpFileName]; this
0x18007c5e8  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x18007c5ed  test    eax, eax
0x18007c5ef  js      loc_18007C792
0x18007c5f5  mov     rcx, rbx; bstrString
0x18007c5f8  call    cs:__imp_SysFreeString
0x18007c5fe  cmp     [rsp+1A0h+String2], r14
0x18007c603  jnz     loc_18007C68C
0x18007c609  mov     rbx, r14
0x18007c60c  mov     [rsp+1A0h+var_168], rbx
0x18007c611  mov     rcx, rbx; pbstr
0x18007c614  call    cs:__imp_SysStringLen
0x18007c61a  mov     r8d, eax; int
0x18007c61d  mov     rdx, rbx; unsigned __int16 *
0x18007c620  lea     rcx, [rsp+1A0h+lpFileName]; this
0x18007c625  call    ?Append@CSrmComBSTR@@QEAAJPEBGH@Z; CSrmComBSTR::Append(ushort const *,int)
0x18007c62a  test    eax, eax
0x18007c62c  js      loc_18007C6EA
0x18007c632  mov     rcx, rbx; bstrString
0x18007c635  call    cs:__imp_SysFreeString
0x18007c63b  mov     rcx, [rsp+1A0h+lpFileName]; lpFileName
0x18007c640  call    cs:__imp_GetFileAttributesW
0x18007c646  test    rsi, rsi
0x18007c649  jz      short loc_18007C64D
0x18007c64b  mov     [rsi], eax
0x18007c64d  cmp     eax, 0FFFFFFFFh
0x18007c650  setnz   bl
0x18007c653  mov     rcx, [rsp+1A0h+lpFileName]; bstrString
0x18007c658  call    cs:__imp_SysFreeString
0x18007c65e  nop
0x18007c65f  mov     rcx, [rsp+1A0h+String2]; pv
0x18007c664  call    cs:__imp_CoTaskMemFree
0x18007c66a  mov     [rsp+1A0h+String2], r14
0x18007c66f  mov     [rsp+1A0h+String2], r14
0x18007c674  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007c67b  mov     [rbp+0A0h+var_D0], rax
0x18007c67f  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c683  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007c688  mov     al, bl
0x18007c68a  jmp     short loc_18007C6C7
0x18007c68c  mov     rcx, [rsp+1A0h+String2]; psz
0x18007c691  call    cs:__imp_SysAllocString
0x18007c697  mov     rbx, rax
0x18007c69a  mov     [rsp+1A0h+var_168], rax
0x18007c69f  test    rax, rax
0x18007c6a2  jz      short loc_18007C700
0x18007c6a4  jmp     loc_18007C611
0x18007c6a9  mov     ecx, 80070057h
0x18007c6ae  mov     [rbp+0A0h+var_C8], ecx
0x18007c6b1  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x18007c6b8  mov     [rbp+0A0h+var_D0], rax
0x18007c6bc  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c6c0  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x18007c6c5  xor     al, al
0x18007c6c7  mov     rcx, [rbp+0A0h+var_20]
0x18007c6ce  xor     rcx, rsp; StackCookie
0x18007c6d1  call    __security_check_cookie
0x18007c6d6  mov     rbx, [rsp+1A0h+arg_10]
0x18007c6de  add     rsp, 190h
0x18007c6e5  pop     r14
0x18007c6e7  pop     rsi
0x18007c6e8  pop     rbp
0x18007c6e9  retn
0x18007c6ea  mov     [rsp+1A0h+pExceptionObject], eax
0x18007c6ee  lea     rdx, _TI1J; pThrowInfo
0x18007c6f5  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18007c6fa  call    _CxxThrowException_0
0x18007c700  mov     [rsp+1A0h+pExceptionObject], 8007000Eh
0x18007c708  lea     rdx, _TI1J; pThrowInfo
0x18007c70f  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18007c714  call    _CxxThrowException_0
0x18007c71a  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c71e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007c723  mov     edx, eax; int
0x18007c725  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c729  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007c72e  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c732  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007c737  mov     r8d, eax; char
0x18007c73a  xor     r9d, r9d; unsigned __int16 *
0x18007c73d  mov     edx, 350h; unsigned int
0x18007c742  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c746  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18007c74c  mov     edx, 80070057h; int
0x18007c751  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c755  call    ?SetHr@CSrmFunctionTracerBase@@QEAAXJ@Z; CSrmFunctionTracerBase::SetHr(long)
0x18007c75a  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c75e  call    ?GetHr@CSrmFunctionTracerBase@@QEAAJXZ; CSrmFunctionTracerBase::GetHr(void)
0x18007c763  mov     r8d, eax; char
0x18007c766  xor     r9d, r9d; unsigned __int16 *
0x18007c769  mov     edx, 352h; unsigned int
0x18007c76e  lea     rcx, [rbp+0A0h+var_D0]; this
0x18007c772  call    ?Throw@CSrmFunctionTracer@@QEAAXKJPEBGZZ; CSrmFunctionTracer::Throw(ulong,long,ushort const *,...)
0x18007c778  mov     [rsp+1A0h+pExceptionObject], 8007000Eh
0x18007c780  lea     rdx, _TI1J; pThrowInfo
0x18007c787  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18007c78c  call    _CxxThrowException_0
0x18007c792  mov     [rsp+1A0h+pExceptionObject], eax
0x18007c796  lea     rdx, _TI1J; pThrowInfo
0x18007c79d  lea     rcx, [rsp+1A0h+pExceptionObject]; pExceptionObject
0x18007c7a2  call    _CxxThrowException_0
```
