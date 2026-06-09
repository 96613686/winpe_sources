# CClassManager::EnsureAndCheckUnmappedPath(ushort const *,CSrmComBSTR &)

- ea: `0x180065c60`
- end: `0x180065e61`
- name: `?EnsureAndCheckUnmappedPath@CClassManager@@AEAAXPEBGAEAVCSrmComBSTR@@@Z`
- size: `513`
- prototype: `void __fastcall(CClassManager *this, wchar_t *, BSTR *)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180062b10`
- `0x180064400`
- `0x1800660b0`
- `0x180067600`
- `0x180069dc0`

## callees

- `0x180001350`
- `0x1800020ba`
- `0x1800657d4`
- `0x180065c60`
- `0x18006a7e8`
- `0x18006febc`
- `0x1800700b8`
- `0x180073f54`
- `0x1800b078a`
- `0x1800b07d0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180065d79`
- `OLEAUT32!__imp_SysAllocString` at `0x180065e1b`
- `OLEAUT32!__imp_SysAllocString` at `0x180065d79`
- `OLEAUT32!__imp_SysAllocString` at `0x180065e1b`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d90`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d6b`
- `OLEAUT32!__imp_SysFreeString` at `0x180065d90`
- `SHLWAPI!PathIsUNCW` at `0x180065da7`
- `SHLWAPI!PathIsUNCW` at `0x180065da7`

## string_xrefs

- `0x180065c9b`: `base\fs\fsrm\service\classmanager\classmanager.cpp`
- `0x180065ca7`: `CClassManager::EnsureAndCheckUnmappedPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall CClassManager::EnsureAndCheckUnmappedPath(CClassManager *this, wchar_t *a2, BSTR *a3)
{
  OLECHAR **v5; // rax
  const OLECHAR *v6; // rdi
  const WCHAR *v7; // rax
  _QWORD *pExceptionObject; // [rsp+30h] [rbp-D0h] BYREF
  _QWORD v9[3]; // [rsp+38h] [rbp-C8h] BYREF
  int v10; // [rsp+50h] [rbp-B0h]
  int v11; // [rsp+54h] [rbp-ACh]
  int v12; // [rsp+58h] [rbp-A8h]
  _BYTE v13[96]; // [rsp+60h] [rbp-A0h] BYREF
  int v14; // [rsp+C0h] [rbp-40h]
  OLECHAR *psz[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v16; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v17; // [rsp+E0h] [rbp-20h]
  _QWORD v18[22]; // [rsp+F0h] [rbp-10h] BYREF

  pExceptionObject = v9;
  v9[0] = L"base\\fs\\fsrm\\service\\classmanager\\classmanager.cpp";
  v9[1] = L"CClassManager::EnsureAndCheckUnmappedPath";
  v9[2] = L"SRMCLSCC";
  v10 = 2140;
  v11 = 21;
  v12 = 255;
  v14 = 0x1000000;
  memset_0(v13, 0, sizeof(v13));
  CSrmFunctionTracer::CSrmFunctionTracer(v18, v9, 0);
  v17 = 7;
  v16 = 0;
  LOWORD(psz[0]) = 0;
  if ( (unsigned __int8)SrmGetMappedDrivePath(a2, psz) )
  {
    v5 = psz;
    if ( v17 >= 8 )
      v5 = (OLECHAR **)psz[0];
    CSrmFunctionTracer::Trace(
      (CSrmFunctionTracer *)v18,
      0x8Cu,
      0x864u,
      L"Unmapping file %s to %s",
      a2,
      v5,
      pExceptionObject);
    v6 = (const OLECHAR *)psz;
    if ( v17 >= 8 )
      v6 = psz[0];
    SysFreeString(*a3);
    if ( v6 )
    {
      v7 = SysAllocString(v6);
      *a3 = (BSTR)v7;
      if ( !v7 )
      {
        LODWORD(pExceptionObject) = -2147024882;
        throw (long *)&pExceptionObject;
      }
      goto LABEL_11;
    }
LABEL_10:
    *a3 = 0;
    v7 = 0;
    goto LABEL_11;
  }
  SysFreeString(*a3);
  if ( !a2 )
    goto LABEL_10;
  v7 = SysAllocString(a2);
  *a3 = (BSTR)v7;
  if ( !v7 )
  {
    LODWORD(pExceptionObject) = -2147024882;
    throw (long *)&pExceptionObject;
  }
LABEL_11:
  if ( PathIsUNCW(v7) )
    CClassManager::DoClientSideCachingChecks((const struct CSrmComBSTR *)a3);
  if ( v17 >= 8 )
    operator delete(psz[0]);
  v17 = 7;
  v16 = 0;
  LOWORD(psz[0]) = 0;
  v18[0] = &CSrmFunctionTracer::`vftable';
  CSrmFunctionTracerBase::~CSrmFunctionTracerBase((CSrmFunctionTracerBase *)v18);
}

```

## disassembly

```asm
0x180065c60  mov     [rsp-8+arg_0], rbx
0x180065c65  mov     [rsp-8+arg_18], rdi
0x180065c6a  push    rbp
0x180065c6b  lea     rbp, [rsp-0B0h]
0x180065c73  sub     rsp, 1B0h
0x180065c7a  mov     rax, cs:__security_cookie
0x180065c81  xor     rax, rsp
0x180065c84  mov     [rbp+0B0h+var_10], rax
0x180065c8b  mov     rbx, r8
0x180065c8e  mov     rdi, rdx
0x180065c91  lea     rax, [rsp+1B0h+var_178]
0x180065c96  mov     [rsp+1B0h+pExceptionObject], rax
0x180065c9b  lea     rax, aBaseFsFsrmServ_24; "base\\fs\\fsrm\\service\\classmanager\\"...
0x180065ca2  mov     [rsp+1B0h+var_178], rax
0x180065ca7  lea     rax, aCclassmanagerE_0; "CClassManager::EnsureAndCheckUnmappedPa"...
0x180065cae  mov     [rsp+1B0h+var_170], rax
0x180065cb3  lea     rax, aSrmclscc; "SRMCLSCC"
0x180065cba  mov     [rsp+1B0h+var_168], rax
0x180065cbf  mov     [rsp+1B0h+var_160], 85Ch
0x180065cc7  mov     [rsp+1B0h+var_15C], 15h
0x180065ccf  mov     [rsp+1B0h+var_158], 0FFh
0x180065cd7  mov     [rbp+0B0h+var_F0], 1000000h
0x180065cde  xor     edx, edx; Val
0x180065ce0  lea     r8d, [rdx+60h]; Size
0x180065ce4  lea     rcx, [rsp+1B0h+var_150]; void *
0x180065ce9  call    memset_0
0x180065cee  nop
0x180065cef  xor     r8d, r8d
0x180065cf2  lea     rdx, [rsp+1B0h+var_178]
0x180065cf7  lea     rcx, [rbp+0B0h+var_C0]
0x180065cfb  call    ??0CSrmFunctionTracer@@QEAA@UCSrmDebugInfo@@PEBG@Z; CSrmFunctionTracer::CSrmFunctionTracer(CSrmDebugInfo,ushort const *)
0x180065d00  nop
0x180065d01  mov     [rbp+0B0h+var_D0], 7
0x180065d09  mov     [rbp+0B0h+var_D8], 0
0x180065d11  xor     eax, eax
0x180065d13  mov     word ptr [rbp+0B0h+psz], ax
0x180065d17  lea     rdx, [rbp+0B0h+psz]; void *
0x180065d1b  mov     rcx, rdi; String2
0x180065d1e  call    ?SrmGetMappedDrivePath@@YA_NPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; SrmGetMappedDrivePath(ushort const *,std::wstring &)
0x180065d23  test    al, al
0x180065d25  jz      short loc_180065D8D
0x180065d27  lea     rax, [rbp+0B0h+psz]
0x180065d2b  cmp     [rbp+0B0h+var_D0], 8
0x180065d30  cmovnb  rax, [rbp+0B0h+psz]
0x180065d35  mov     [rsp+1B0h+var_188], rax
0x180065d3a  mov     [rsp+1B0h+var_190], rdi
0x180065d3f  lea     r9, aUnmappingFileS; "Unmapping file %s to %s"
0x180065d46  mov     edx, 8Ch; unsigned int
0x180065d4b  mov     r8d, 864h; unsigned int
0x180065d51  lea     rcx, [rbp+0B0h+var_C0]; this
0x180065d55  call    ?Trace@CSrmFunctionTracer@@QEAAXKKPEBGZZ; CSrmFunctionTracer::Trace(ulong,ulong,ushort const *,...)
0x180065d5a  lea     rdi, [rbp+0B0h+psz]
0x180065d5e  cmp     [rbp+0B0h+var_D0], 8
0x180065d63  cmovnb  rdi, [rbp+0B0h+psz]
0x180065d68  mov     rcx, [rbx]; bstrString
0x180065d6b  call    cs:__imp_SysFreeString
0x180065d71  test    rdi, rdi
0x180065d74  jz      short loc_180065D9B
0x180065d76  mov     rcx, rdi; psz
0x180065d79  call    cs:__imp_SysAllocString
0x180065d7f  mov     [rbx], rax
0x180065d82  test    rax, rax
0x180065d85  jz      loc_180065E47
0x180065d8b  jmp     short loc_180065DA4
0x180065d8d  mov     rcx, [rbx]; bstrString
0x180065d90  call    cs:__imp_SysFreeString
0x180065d96  test    rdi, rdi
0x180065d99  jnz     short loc_180065E18
0x180065d9b  mov     qword ptr [rbx], 0
0x180065da2  xor     eax, eax
0x180065da4  mov     rcx, rax; pszPath
0x180065da7  call    cs:__imp_PathIsUNCW
0x180065dad  test    eax, eax
0x180065daf  jz      short loc_180065DBA
0x180065db1  mov     rcx, rbx; struct CSrmComBSTR *
0x180065db4  call    ?DoClientSideCachingChecks@CClassManager@@CAXAEBVCSrmComBSTR@@@Z; CClassManager::DoClientSideCachingChecks(CSrmComBSTR const &)
0x180065db9  nop
0x180065dba  cmp     [rbp+0B0h+var_D0], 8
0x180065dbf  jb      short loc_180065DCA
0x180065dc1  mov     rcx, [rbp+0B0h+psz]; Block
0x180065dc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180065dca  mov     [rbp+0B0h+var_D0], 7
0x180065dd2  mov     [rbp+0B0h+var_D8], 0
0x180065dda  xor     eax, eax
0x180065ddc  mov     word ptr [rbp+0B0h+psz], ax
0x180065de0  lea     rax, ??_7CSrmFunctionTracer@@6B@; const CSrmFunctionTracer::`vftable'
0x180065de7  mov     [rbp+0B0h+var_C0], rax
0x180065deb  lea     rcx, [rbp+0B0h+var_C0]; this
0x180065def  call    ??1CSrmFunctionTracerBase@@UEAA@XZ; CSrmFunctionTracerBase::~CSrmFunctionTracerBase(void)
0x180065df4  mov     rcx, [rbp+0B0h+var_10]
0x180065dfb  xor     rcx, rsp; StackCookie
0x180065dfe  call    __security_check_cookie
0x180065e03  lea     r11, [rsp+1B0h+var_s0]
0x180065e0b  mov     rbx, [r11+10h]
0x180065e0f  mov     rdi, [r11+28h]
0x180065e13  mov     rsp, r11
0x180065e16  pop     rbp
0x180065e17  retn
0x180065e18  mov     rcx, rdi; psz
0x180065e1b  call    cs:__imp_SysAllocString
0x180065e21  mov     [rbx], rax
0x180065e24  test    rax, rax
0x180065e27  jnz     loc_180065DA4
0x180065e2d  mov     dword ptr [rsp+1B0h+pExceptionObject], 8007000Eh
0x180065e35  lea     rdx, _TI1J; pThrowInfo
0x180065e3c  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180065e41  call    _CxxThrowException_0
0x180065e47  mov     dword ptr [rsp+1B0h+pExceptionObject], 8007000Eh
0x180065e4f  lea     rdx, _TI1J; pThrowInfo
0x180065e56  lea     rcx, [rsp+1B0h+pExceptionObject]; pExceptionObject
0x180065e5b  call    _CxxThrowException_0
```
