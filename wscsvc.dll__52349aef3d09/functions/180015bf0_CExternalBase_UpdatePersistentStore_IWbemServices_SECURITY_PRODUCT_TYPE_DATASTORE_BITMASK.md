# CExternalBase::UpdatePersistentStore(IWbemServices *,_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)

- ea: `0x180015bf0`
- end: `0x18001610f`
- name: `?UpdatePersistentStore@CExternalBase@@QEAAJPEAUIWbemServices@@W4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z`
- size: `1311`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `5`
- callee_count: `10`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180024b40`
- `0x180025520`
- `0x18002fc00`
- `0x180036adc`
- `0x18003d364`

## callees

- `0x180008e48`
- `0x180015bf0`
- `0x180016120`
- `0x180016b74`
- `0x180018ab0`
- `0x1800296d4`
- `0x180029e74`
- `0x180037960`
- `0x18003fc30`
- `0x180042010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180015d1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e47`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e97`
- `OLEAUT32!__imp_SysAllocString` at `0x180015f1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180015f6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180015fba`
- `OLEAUT32!__imp_SysAllocString` at `0x180015d1f`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e47`
- `OLEAUT32!__imp_SysAllocString` at `0x180015e97`
- `OLEAUT32!__imp_SysAllocString` at `0x180015f1a`
- `OLEAUT32!__imp_SysAllocString` at `0x180015f6a`
- `OLEAUT32!__imp_SysAllocString` at `0x180015fba`
- `OLEAUT32!__imp_SysFreeString` at `0x180015d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180015da5`
- `OLEAUT32!__imp_SysFreeString` at `0x180015d97`
- `OLEAUT32!__imp_SysFreeString` at `0x180015da5`
- `OLEAUT32!__imp_VariantInit` at `0x180015e27`
- `OLEAUT32!__imp_VariantInit` at `0x180015e27`
- `OLEAUT32!__imp_VariantClear` at `0x180015e7c`
- `OLEAUT32!__imp_VariantClear` at `0x180015ecc`
- `OLEAUT32!__imp_VariantClear` at `0x180015f0b`
- `OLEAUT32!__imp_VariantClear` at `0x180015f4f`
- `OLEAUT32!__imp_VariantClear` at `0x180015f9f`
- `OLEAUT32!__imp_VariantClear` at `0x180015fef`
- `OLEAUT32!__imp_VariantClear` at `0x180015e7c`
- `OLEAUT32!__imp_VariantClear` at `0x180015ecc`
- `OLEAUT32!__imp_VariantClear` at `0x180015f0b`
- `OLEAUT32!__imp_VariantClear` at `0x180015f4f`
- `OLEAUT32!__imp_VariantClear` at `0x180015f9f`
- `OLEAUT32!__imp_VariantClear` at `0x180015fef`

## string_xrefs

- `0x180015f8a`: `pathToSignedProductExe`
- `0x180015fda`: `pathToSignedReportingExe`
- `0x180015cb7`: `admin\wsc\src\client\service\wscsvclib\externalbase.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CExternalBase::UpdatePersistentStore(__int64 a1, __int64 a2, int a3, char a4)
{
  int updated; // r14d
  LONG v7; // r12d
  __int64 v8; // rax
  int v9; // eax
  int v10; // ebx
  const OLECHAR *v11; // rax
  OLECHAR *v12; // r15
  OLECHAR *v13; // rcx
  OLECHAR *v14; // rcx
  OLECHAR *v15; // rcx
  OLECHAR *v16; // rcx
  int v18; // [rsp+20h] [rbp-B9h]
  __int64 v19; // [rsp+40h] [rbp-99h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-91h] BYREF
  __int64 v21; // [rsp+70h] [rbp-69h] BYREF
  OLECHAR v22[4]; // [rsp+78h] [rbp-61h] BYREF
  __int64 v23; // [rsp+88h] [rbp-51h]
  unsigned __int64 v24; // [rsp+90h] [rbp-49h]
  OLECHAR v25[4]; // [rsp+98h] [rbp-41h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-31h]
  unsigned __int64 v27; // [rsp+B0h] [rbp-29h]
  OLECHAR v28[4]; // [rsp+B8h] [rbp-21h] BYREF
  __int64 v29; // [rsp+C8h] [rbp-11h]
  unsigned __int64 v30; // [rsp+D0h] [rbp-9h]
  OLECHAR psz[4]; // [rsp+D8h] [rbp-1h] BYREF
  __int64 v32; // [rsp+E8h] [rbp+Fh]
  unsigned __int64 v33; // [rsp+F0h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+138h] [rbp+5Fh]

  updated = CExternalBase::UpdatePersistentStoreRegistry(a1, a3, a4);
  v33 = 7;
  v32 = 0;
  psz[0] = 0;
  v30 = 7;
  v29 = 0;
  v28[0] = 0;
  v7 = *(_DWORD *)(a1 + 80);
  v27 = 7;
  v26 = 0;
  v25[0] = 0;
  v24 = 7;
  v23 = 0;
  v22[0] = 0;
  v8 = lambda_5190e6ea1bae239ca2f9bafce766553d_::_lambda_5190e6ea1bae239ca2f9bafce766553d_(
         (unsigned int)&pvarg,
         (unsigned int)psz,
         a1,
         (unsigned int)v28,
         (__int64)v25,
         (__int64)v22);
  v9 = wil::ResultFromException__lambda_0576dd544a9b489b566bf4e2973c12e9___(v8);
  v10 = v9;
  if ( v9 >= 0 )
  {
    v21 = 0;
    v11 = (const OLECHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)a1 + 16LL))(a1);
    v12 = SysAllocString(v11);
    if ( v12 )
    {
      v10 = (*(__int64 (__fastcall **)(__int64, OLECHAR *, _QWORD, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a2 + 48LL))(
              a2,
              v12,
              0,
              0,
              &v21,
              0);
      if ( v10 >= 0
        || WPP_GLOBAL_Control == (CThirdPartyManager *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
        SysFreeString(v12);
        if ( v10 >= 0 )
        {
          v19 = 0;
          v10 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v21 + 120LL))(v21, 0, &v19);
          if ( v10 >= 0 )
          {
            memset(&pvarg, 0, sizeof(pvarg));
            VariantInit(&pvarg);
            pvarg.vt = 8;
            if ( v33 < 8 )
              v13 = psz;
            else
              v13 = *(OLECHAR **)psz;
            pvarg.llVal = (LONGLONG)SysAllocString(v13);
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"instanceGuid",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            pvarg.vt = 8;
            if ( v30 < 8 )
              v14 = v28;
            else
              v14 = *(OLECHAR **)v28;
            pvarg.llVal = (LONGLONG)SysAllocString(v14);
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"displayName",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            pvarg.vt = 3;
            pvarg.lVal = v7;
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"productState",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            pvarg.vt = 8;
            pvarg.llVal = (LONGLONG)SysAllocString(*(const OLECHAR **)(a1 + 72));
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"timestamp",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            pvarg.vt = 8;
            if ( v27 < 8 )
              v15 = v25;
            else
              v15 = *(OLECHAR **)v25;
            pvarg.llVal = (LONGLONG)SysAllocString(v15);
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"pathToSignedProductExe",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            pvarg.vt = 8;
            if ( v24 < 8 )
              v16 = v22;
            else
              v16 = *(OLECHAR **)v22;
            pvarg.llVal = (LONGLONG)SysAllocString(v16);
            (*(void (__fastcall **)(__int64, const wchar_t *, _QWORD, VARIANTARG *, _DWORD))(*(_QWORD *)v19 + 40LL))(
              v19,
              L"pathToSignedReportingExe",
              0,
              &pvarg,
              0);
            VariantClear(&pvarg);
            v10 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a2 + 112LL))(
                    a2,
                    v19,
                    0,
                    0,
                    0);
            if ( v10 < 0
              && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                24,
                WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
                (unsigned int)v10);
            }
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
          }
          else if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
                 && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_d(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              23,
              WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
              (unsigned int)v10);
          }
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
        }
      }
      else
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          22,
          WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids,
          (unsigned int)v10);
        SysFreeString(v12);
      }
    }
    else
    {
      v10 = -2147024882;
    }
    if ( updated < 0 )
      v10 = updated;
    if ( v24 >= 8 )
      operator delete(*(void **)v22);
    v24 = 7;
    v23 = 0;
    v22[0] = 0;
    if ( v27 >= 8 )
      operator delete(*(void **)v25);
    v27 = 7;
    v26 = 0;
    v25[0] = 0;
    if ( v30 >= 8 )
      operator delete(*(void **)v28);
    v30 = 7;
    v29 = 0;
    v28[0] = 0;
    if ( v33 >= 8 )
      operator delete(*(void **)psz);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"admin\\wsc\\src\\client\\service\\wscsvclib\\externalbase.cpp",
      (const char *)(unsigned int)v9,
      v18);
    std::wstring::_Tidy(v22, 1, 0);
    std::wstring::_Tidy(v25, 1, 0);
    std::wstring::_Tidy(v28, 1, 0);
    std::wstring::_Tidy(psz, 1, 0);
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180015bf0  mov     [rsp-8+arg_10], rbx
0x180015bf5  push    rbp
0x180015bf6  push    rsi
0x180015bf7  push    rdi
0x180015bf8  push    r12
0x180015bfa  push    r13
0x180015bfc  push    r14
0x180015bfe  push    r15
0x180015c00  lea     rbp, [rsp-27h]
0x180015c05  sub     rsp, 100h
0x180015c0c  mov     rax, cs:__security_cookie
0x180015c13  xor     rax, rsp
0x180015c16  mov     [rbp+57h+var_38], rax
0x180015c1a  mov     eax, r8d
0x180015c1d  mov     rsi, rdx
0x180015c20  mov     rdi, rcx
0x180015c23  mov     r8d, r9d
0x180015c26  mov     edx, eax
0x180015c28  call    ?UpdatePersistentStoreRegistry@CExternalBase@@QEAAJW4_SECURITY_PRODUCT_TYPE@@W4_DATASTORE_BITMASK@@@Z; CExternalBase::UpdatePersistentStoreRegistry(_SECURITY_PRODUCT_TYPE,_DATASTORE_BITMASK)
0x180015c2d  mov     r14d, eax
0x180015c30  mov     [rbp+57h+var_40], 7
0x180015c38  xor     r13d, r13d
0x180015c3b  mov     [rbp+57h+var_48], r13
0x180015c3f  mov     [rbp+57h+psz], r13w
0x180015c44  mov     [rbp+57h+var_60], 7
0x180015c4c  mov     [rbp+57h+var_68], r13
0x180015c50  mov     [rbp+57h+var_78], r13w
0x180015c55  mov     r12d, [rdi+50h]
0x180015c59  mov     [rbp+57h+var_80], 7
0x180015c61  mov     [rbp+57h+var_88], r13
0x180015c65  mov     [rbp+57h+var_98], r13w
0x180015c6a  mov     [rbp+57h+var_A0], 7
0x180015c72  mov     [rbp+57h+var_A8], r13
0x180015c76  mov     [rbp+57h+var_B8], r13w
0x180015c7b  lea     rax, [rbp+57h+var_B8]
0x180015c7f  mov     [rsp+130h+var_108], rax
0x180015c84  lea     rax, [rbp+57h+var_98]
0x180015c88  mov     qword ptr [rsp+130h+var_110], rax; int
0x180015c8d  lea     r9, [rbp+57h+var_78]
0x180015c91  mov     r8, rdi
0x180015c94  lea     rdx, [rbp+57h+psz]
0x180015c98  lea     rcx, [rsp+130h+pvarg]
0x180015c9d  call    _lambda_5190e6ea1bae239ca2f9bafce766553d____lambda_5190e6ea1bae239ca2f9bafce766553d_
0x180015ca2  mov     rcx, rax
0x180015ca5  call    wil__ResultFromException__lambda_0576dd544a9b489b566bf4e2973c12e9___
0x180015caa  mov     ebx, eax
0x180015cac  test    eax, eax
0x180015cae  jns     short loc_180015D09
0x180015cb0  mov     rcx, [rbp+5Fh]; this
0x180015cb4  mov     r9d, eax; char *
0x180015cb7  lea     r8, aAdminWscSrcCli_0; "admin\\wsc\\src\\client\\service\\wscsv"...
0x180015cbe  mov     edx, 35Fh; void *
0x180015cc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015cc8  nop
0x180015cc9  xor     r8d, r8d
0x180015ccc  mov     dl, 1
0x180015cce  lea     rcx, [rbp+57h+var_B8]
0x180015cd2  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015cd7  nop
0x180015cd8  xor     r8d, r8d
0x180015cdb  mov     dl, 1
0x180015cdd  lea     rcx, [rbp+57h+var_98]
0x180015ce1  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015ce6  nop
0x180015ce7  xor     r8d, r8d
0x180015cea  mov     dl, 1
0x180015cec  lea     rcx, [rbp+57h+var_78]
0x180015cf0  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015cf5  nop
0x180015cf6  xor     r8d, r8d
0x180015cf9  mov     dl, 1
0x180015cfb  lea     rcx, [rbp+57h+psz]
0x180015cff  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180015d04  jmp     loc_1800160E6
0x180015d09  mov     [rbp+57h+var_C0], r13
0x180015d0d  mov     rax, [rdi]
0x180015d10  mov     rcx, rdi
0x180015d13  mov     rax, [rax+10h]
0x180015d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d1c  mov     rcx, rax; psz
0x180015d1f  call    cs:__imp_SysAllocString
0x180015d25  mov     r15, rax
0x180015d28  test    rax, rax
0x180015d2b  jnz     short loc_180015D37
0x180015d2d  mov     ebx, 8007000Eh
0x180015d32  jmp     loc_18001606C
0x180015d37  mov     rax, [rsi]
0x180015d3a  mov     [rsp+130h+var_108], r13
0x180015d3f  lea     rcx, [rbp+57h+var_C0]
0x180015d43  mov     qword ptr [rsp+130h+var_110], rcx
0x180015d48  xor     r9d, r9d
0x180015d4b  xor     r8d, r8d
0x180015d4e  mov     rdx, r15
0x180015d51  mov     rcx, rsi
0x180015d54  mov     rax, [rax+30h]
0x180015d58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015d5d  mov     ebx, eax
0x180015d5f  lea     rax, WPP_GLOBAL_Control
0x180015d66  test    ebx, ebx
0x180015d68  jns     short loc_180015DA2
0x180015d6a  mov     rcx, cs:WPP_GLOBAL_Control
0x180015d71  cmp     rcx, rax
0x180015d74  jz      short loc_180015DA2
0x180015d76  test    byte ptr [rcx+1Ch], 1
0x180015d7a  jz      short loc_180015DA2
0x180015d7c  mov     edx, 16h
0x180015d81  mov     r9d, ebx
0x180015d84  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180015d8b  mov     rcx, [rcx+10h]
0x180015d8f  call    WPP_SF_d
0x180015d94  mov     rcx, r15; bstrString
0x180015d97  call    cs:__imp_SysFreeString
0x180015d9d  jmp     loc_18001606C
0x180015da2  mov     rcx, r15; bstrString
0x180015da5  call    cs:__imp_SysFreeString
0x180015dab  test    ebx, ebx
0x180015dad  js      loc_18001606C
0x180015db3  mov     [rsp+130h+var_F0], r13
0x180015db8  mov     rcx, [rbp+57h+var_C0]
0x180015dbc  mov     rax, [rcx]
0x180015dbf  lea     r8, [rsp+130h+var_F0]
0x180015dc4  xor     edx, edx
0x180015dc6  mov     rax, [rax+78h]
0x180015dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015dcf  mov     ebx, eax
0x180015dd1  test    eax, eax
0x180015dd3  jns     short loc_180015E13
0x180015dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180015ddc  lea     rax, WPP_GLOBAL_Control
0x180015de3  cmp     rcx, rax
0x180015de6  jz      loc_18001605C
0x180015dec  test    byte ptr [rcx+1Ch], 1
0x180015df0  jz      loc_18001605C
0x180015df6  mov     edx, 17h
0x180015dfb  mov     r9d, ebx
0x180015dfe  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180015e05  mov     rcx, [rcx+10h]
0x180015e09  call    WPP_SF_d
0x180015e0e  jmp     loc_18001605C
0x180015e13  xorps   xmm0, xmm0
0x180015e16  xor     eax, eax
0x180015e18  movups  xmmword ptr [rsp+130h+pvarg], xmm0
0x180015e1d  mov     qword ptr [rsp+130h+pvarg+10h], rax
0x180015e22  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015e27  call    cs:__imp_VariantInit
0x180015e2d  mov     ebx, 8
0x180015e32  mov     word ptr [rsp+130h+pvarg], bx
0x180015e37  cmp     [rbp+57h+var_40], rbx
0x180015e3b  jb      short loc_180015E43
0x180015e3d  mov     rcx, qword ptr [rbp+57h+psz]
0x180015e41  jmp     short loc_180015E47
0x180015e43  lea     rcx, [rbp+57h+psz]; psz
0x180015e47  call    cs:__imp_SysAllocString
0x180015e4d  mov     qword ptr [rsp+130h+pvarg+8], rax
0x180015e52  mov     rcx, [rsp+130h+var_F0]
0x180015e57  mov     rax, [rcx]
0x180015e5a  mov     [rsp+130h+var_110], r13d
0x180015e5f  lea     r9, [rsp+130h+pvarg]
0x180015e64  xor     r8d, r8d
0x180015e67  lea     rdx, aInstanceguid; "instanceGuid"
0x180015e6e  mov     rax, [rax+28h]
0x180015e72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e77  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015e7c  call    cs:__imp_VariantClear
0x180015e82  mov     word ptr [rsp+130h+pvarg], bx
0x180015e87  cmp     [rbp+57h+var_60], rbx
0x180015e8b  jb      short loc_180015E93
0x180015e8d  mov     rcx, qword ptr [rbp+57h+var_78]
0x180015e91  jmp     short loc_180015E97
0x180015e93  lea     rcx, [rbp+57h+var_78]; psz
0x180015e97  call    cs:__imp_SysAllocString
0x180015e9d  mov     qword ptr [rsp+130h+pvarg+8], rax
0x180015ea2  mov     rcx, [rsp+130h+var_F0]
0x180015ea7  mov     rax, [rcx]
0x180015eaa  mov     [rsp+130h+var_110], r13d
0x180015eaf  lea     r9, [rsp+130h+pvarg]
0x180015eb4  xor     r8d, r8d
0x180015eb7  lea     rdx, aDisplayname_0; "displayName"
0x180015ebe  mov     rax, [rax+28h]
0x180015ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ec7  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015ecc  call    cs:__imp_VariantClear
0x180015ed2  mov     eax, 3
0x180015ed7  mov     word ptr [rsp+130h+pvarg], ax
0x180015edc  mov     dword ptr [rsp+130h+pvarg+8], r12d
0x180015ee1  mov     rcx, [rsp+130h+var_F0]
0x180015ee6  mov     rax, [rcx]
0x180015ee9  mov     [rsp+130h+var_110], r13d
0x180015eee  lea     r9, [rsp+130h+pvarg]
0x180015ef3  xor     r8d, r8d
0x180015ef6  lea     rdx, aProductstate; "productState"
0x180015efd  mov     rax, [rax+28h]
0x180015f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f06  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015f0b  call    cs:__imp_VariantClear
0x180015f11  mov     word ptr [rsp+130h+pvarg], bx
0x180015f16  mov     rcx, [rdi+48h]; psz
0x180015f1a  call    cs:__imp_SysAllocString
0x180015f20  mov     qword ptr [rsp+130h+pvarg+8], rax
0x180015f25  mov     rcx, [rsp+130h+var_F0]
0x180015f2a  mov     rax, [rcx]
0x180015f2d  mov     [rsp+130h+var_110], r13d
0x180015f32  lea     r9, [rsp+130h+pvarg]
0x180015f37  xor     r8d, r8d
0x180015f3a  lea     rdx, aTimestamp; "timestamp"
0x180015f41  mov     rax, [rax+28h]
0x180015f45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f4a  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015f4f  call    cs:__imp_VariantClear
0x180015f55  mov     word ptr [rsp+130h+pvarg], bx
0x180015f5a  cmp     [rbp+57h+var_80], rbx
0x180015f5e  jb      short loc_180015F66
0x180015f60  mov     rcx, qword ptr [rbp+57h+var_98]
0x180015f64  jmp     short loc_180015F6A
0x180015f66  lea     rcx, [rbp+57h+var_98]; psz
0x180015f6a  call    cs:__imp_SysAllocString
0x180015f70  mov     qword ptr [rsp+130h+pvarg+8], rax
0x180015f75  mov     rcx, [rsp+130h+var_F0]
0x180015f7a  mov     rax, [rcx]
0x180015f7d  mov     [rsp+130h+var_110], r13d
0x180015f82  lea     r9, [rsp+130h+pvarg]
0x180015f87  xor     r8d, r8d
0x180015f8a  lea     rdx, aPathtosignedpr; "pathToSignedProductExe"
0x180015f91  mov     rax, [rax+28h]
0x180015f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f9a  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015f9f  call    cs:__imp_VariantClear
0x180015fa5  mov     word ptr [rsp+130h+pvarg], bx
0x180015faa  cmp     [rbp+57h+var_A0], rbx
0x180015fae  jb      short loc_180015FB6
0x180015fb0  mov     rcx, qword ptr [rbp+57h+var_B8]
0x180015fb4  jmp     short loc_180015FBA
0x180015fb6  lea     rcx, [rbp+57h+var_B8]; psz
0x180015fba  call    cs:__imp_SysAllocString
0x180015fc0  mov     qword ptr [rsp+130h+pvarg+8], rax
0x180015fc5  mov     rcx, [rsp+130h+var_F0]
0x180015fca  mov     rax, [rcx]
0x180015fcd  mov     [rsp+130h+var_110], r13d
0x180015fd2  lea     r9, [rsp+130h+pvarg]
0x180015fd7  xor     r8d, r8d
0x180015fda  lea     rdx, aPathtosignedre_0; "pathToSignedReportingExe"
0x180015fe1  mov     rax, [rax+28h]
0x180015fe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fea  lea     rcx, [rsp+130h+pvarg]; pvarg
0x180015fef  call    cs:__imp_VariantClear
0x180015ff5  mov     rax, [rsi]
0x180015ff8  mov     qword ptr [rsp+130h+var_110], r13
0x180015ffd  xor     r9d, r9d
0x180016000  xor     r8d, r8d
0x180016003  mov     rdx, [rsp+130h+var_F0]
0x180016008  mov     rcx, rsi
0x18001600b  mov     rax, [rax+70h]
0x18001600f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016014  mov     ebx, eax
0x180016016  test    eax, eax
0x180016018  jns     short loc_18001604B
0x18001601a  mov     rcx, cs:WPP_GLOBAL_Control
0x180016021  lea     rax, WPP_GLOBAL_Control
0x180016028  cmp     rcx, rax
0x18001602b  jz      short loc_18001604B
0x18001602d  test    byte ptr [rcx+1Ch], 1
0x180016031  jz      short loc_18001604B
0x180016033  mov     edx, 18h
0x180016038  mov     r9d, ebx
0x18001603b  lea     r8, WPP_98edacfde76e3c1ddb9bd9d8b029c255_Traceguids
0x180016042  mov     rcx, [rcx+10h]
0x180016046  call    WPP_SF_d
0x18001604b  mov     rcx, [rsp+130h+var_F0]
0x180016050  mov     rax, [rcx]
0x180016053  mov     rax, [rax+10h]
0x180016057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001605c  mov     rcx, [rbp+57h+var_C0]
0x180016060  mov     rax, [rcx]
0x180016063  mov     rax, [rax+10h]
0x180016067  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001606c  test    r14d, r14d
0x18001606f  cmovs   ebx, r14d
0x180016073  cmp     [rbp+57h+var_A0], 8
0x180016078  jb      short loc_180016083
0x18001607a  mov     rcx, qword ptr [rbp+57h+var_B8]; Block
0x18001607e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180016083  mov     [rbp+57h+var_A0], 7
0x18001608b  mov     [rbp+57h+var_A8], r13
0x18001608f  mov     [rbp+57h+var_B8], r13w
0x180016094  cmp     [rbp+57h+var_80], 8
0x180016099  jb      short loc_1800160A4
0x18001609b  mov     rcx, qword ptr [rbp+57h+var_98]; Block
0x18001609f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800160a4  mov     [rbp+57h+var_80], 7
0x1800160ac  mov     [rbp+57h+var_88], r13
0x1800160b0  mov     [rbp+57h+var_98], r13w
0x1800160b5  cmp     [rbp+57h+var_60], 8
0x1800160ba  jb      short loc_1800160C5
0x1800160bc  mov     rcx, qword ptr [rbp+57h+var_78]; Block
0x1800160c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800160c5  mov     [rbp+57h+var_60], 7
0x1800160cd  mov     [rbp+57h+var_68], r13
0x1800160d1  mov     [rbp+57h+var_78], r13w
0x1800160d6  cmp     [rbp+57h+var_40], 8
0x1800160db  jb      short loc_1800160E6
  ... truncated ...
```
