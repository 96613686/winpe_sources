# OSDeploymentHelper::ParseHandlerXml(tagDSDataBlob const &,wchar_t * *)

- ea: `0x180019e00`
- end: `0x18001a08c`
- name: `?ParseHandlerXml@OSDeploymentHelper@@YAJAEBUtagDSDataBlob@@PEAPEA_W@Z`
- size: `652`
- prototype: `__int64 __fastcall(OSDeploymentHelper *__hidden this, const struct tagDSDataBlob *, wchar_t **)`
- caller_count: `6`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18001d330`
- `0x18001fe7c`
- `0x180020fe8`
- `0x180025850`
- `0x180028ea8`
- `0x18002a83c`

## callees

- `0x180003950`
- `0x18000b0b8`
- `0x180019e00`
- `0x18003233c`
- `0x180039b40`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a068`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a068`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e56`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e68`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ecc`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f39`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ff4`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e56`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e68`
- `OLEAUT32!__imp_SysFreeString` at `0x180019e9a`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ecc`
- `OLEAUT32!__imp_SysFreeString` at `0x180019f39`
- `OLEAUT32!__imp_SysFreeString` at `0x180019fbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180019ff4`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180019e8a`
- `OLEAUT32!__imp_SysAllocStringByteLen` at `0x180019e8a`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall OSDeploymentHelper::ParseHandlerXml(
        OSDeploymentHelper *this,
        const struct tagDSDataBlob *a2,
        wchar_t **a3)
{
  wchar_t *v4; // rbx
  UINT v5; // edx
  const CHAR *v6; // rcx
  BSTR v7; // rdi
  int ElementSet; // edi
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdx
  BOOL v12; // edi
  BSTR v14; // [rsp+20h] [rbp-50h]
  int v15; // [rsp+20h] [rbp-50h]
  LPVOID pv; // [rsp+28h] [rbp-48h] BYREF
  struct IXMLDOMNode *v17; // [rsp+30h] [rbp-40h] BYREF
  __int128 v18; // [rsp+38h] [rbp-38h] BYREF
  __int128 v19; // [rsp+48h] [rbp-28h]
  __int64 v20; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]

  pv = 0;
  *(_QWORD *)a2 = 0;
  v17 = 0;
  v18 = 0;
  v19 = 0;
  v20 = 0;
  v4 = 0;
  v14 = 0;
  v5 = *(_DWORD *)this;
  if ( !*(_DWORD *)this || (v6 = (const CHAR *)*((_QWORD *)this + 1)) == 0 )
  {
    SysFreeString(0);
LABEL_22:
    ElementSet = -2145116151;
    v11 = 383;
    goto LABEL_25;
  }
  v7 = SysAllocStringByteLen(v6, v5);
  if ( v7 )
  {
    SysFreeString(0);
    v4 = v7;
    v14 = v7;
  }
  if ( !v4 )
  {
    ElementSet = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56D,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)0x8007000ELL,
      (int)v14);
    SysFreeString(0);
LABEL_18:
    v11 = 381;
LABEL_25:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v11,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\handler\\OSDeployment\\Helper\\OSDeploymentHelper.cpp",
      (const char *)(unsigned int)ElementSet,
      (int)v14);
    goto LABEL_27;
  }
  v9 = DspCreateDOMAndLoadXml(v4, &v17);
  ElementSet = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x56F,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)v9,
      (int)v14);
    SysFreeString(v4);
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
    goto LABEL_18;
  }
  if ( !v17 )
  {
    ElementSet = -2147467261;
    v10 = 1326;
    goto LABEL_16;
  }
  ElementSet = GetElementSet(v17, &pv, &qword_1800757A0, &v18, v14);
  if ( ElementSet < 0 )
  {
    v10 = 1340;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)ElementSet,
      (int)v14);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x570,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)(unsigned int)ElementSet,
      v15);
    SysFreeString(v4);
    if ( v17 )
      ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
    goto LABEL_18;
  }
  v12 = HIDWORD(v19) != 0;
  SysFreeString(v4);
  if ( v17 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v17->lpVtbl->Release)(v17);
  if ( !v12 )
    goto LABEL_22;
  v17 = 0;
  ElementSet = SusStrCchDup<wchar_t *,wchar_t *>(pv);
  if ( ElementSet < 0 )
  {
    v11 = 386;
    goto LABEL_25;
  }
  *(_QWORD *)a2 = v17;
  ElementSet = 0;
LABEL_27:
  if ( pv )
    CoTaskMemFree(pv);
  return (unsigned int)ElementSet;
}

```

## disassembly

```asm
0x180019e00  mov     [rsp-18h+arg_10], rbx
0x180019e05  push    rbp
0x180019e06  push    rsi
0x180019e07  push    rdi
0x180019e08  mov     rbp, rsp
0x180019e0b  sub     rsp, 70h
0x180019e0f  mov     rax, cs:__security_cookie
0x180019e16  xor     rax, rsp
0x180019e19  mov     [rbp+var_10], rax
0x180019e1d  mov     rsi, rdx
0x180019e20  mov     [rbp+pv], 0
0x180019e28  mov     qword ptr [rdx], 0
0x180019e2f  mov     [rbp+var_40], 0
0x180019e37  xorps   xmm0, xmm0
0x180019e3a  xor     eax, eax
0x180019e3c  movups  [rbp+var_38], xmm0
0x180019e40  movups  [rbp+var_28], xmm0
0x180019e44  mov     [rbp+var_18], rax
0x180019e48  xor     ebx, ebx
0x180019e4a  mov     [rbp+var_50], rbx
0x180019e4e  mov     edx, [rcx]; len
0x180019e50  test    edx, edx
0x180019e52  jnz     short loc_180019E5F
0x180019e54  xor     ecx, ecx; bstrString
0x180019e56  call    cs:__imp_SysFreeString
0x180019e5c  nop
0x180019e5d  jmp     short loc_180019E6F
0x180019e5f  mov     rcx, [rcx+8]; psz
0x180019e63  test    rcx, rcx
0x180019e66  jnz     short loc_180019E8A
0x180019e68  call    cs:__imp_SysFreeString
0x180019e6e  nop
0x180019e6f  mov     rcx, [rbp+var_40]
0x180019e73  test    rcx, rcx
0x180019e76  jz      short loc_180019E85
0x180019e78  mov     rax, [rcx]
0x180019e7b  mov     rax, [rax+10h]
0x180019e7f  call    _guard_dispatch_icall
0x180019e84  nop
0x180019e85  jmp     loc_18001A015
0x180019e8a  call    cs:__imp_SysAllocStringByteLen
0x180019e90  mov     rdi, rax
0x180019e93  test    rax, rax
0x180019e96  jz      short loc_180019EA7
0x180019e98  xor     ecx, ecx; bstrString
0x180019e9a  call    cs:__imp_SysFreeString
0x180019ea0  mov     rbx, rdi
0x180019ea3  mov     [rbp+var_50], rbx
0x180019ea7  test    rbx, rbx
0x180019eaa  jnz     short loc_180019EEE
0x180019eac  mov     rcx, [rbp+18h]; this
0x180019eb0  mov     edi, 8007000Eh
0x180019eb5  mov     r9d, edi; char *
0x180019eb8  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180019ebf  mov     edx, 56Dh; void *
0x180019ec4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019ec9  nop
0x180019eca  xor     ecx, ecx; bstrString
0x180019ecc  call    cs:__imp_SysFreeString
0x180019ed2  nop
0x180019ed3  mov     rcx, [rbp+var_40]
0x180019ed7  test    rcx, rcx
0x180019eda  jz      short loc_180019EE9
0x180019edc  mov     rax, [rcx]
0x180019edf  mov     rax, [rax+10h]
0x180019ee3  call    _guard_dispatch_icall
0x180019ee8  nop
0x180019ee9  jmp     loc_180019FDF
0x180019eee  mov     rcx, [rbp+var_40]
0x180019ef2  test    rcx, rcx
0x180019ef5  jz      short loc_180019F0B
0x180019ef7  mov     rax, [rcx]
0x180019efa  mov     rax, [rax+10h]
0x180019efe  call    _guard_dispatch_icall
0x180019f03  mov     [rbp+var_40], 0
0x180019f0b  lea     rdx, [rbp+var_40]; struct IXMLDOMNode **
0x180019f0f  mov     rcx, rbx; wchar_t *
0x180019f12  call    ?DspCreateDOMAndLoadXml@@YAJPEA_WPEAPEAUIXMLDOMNode@@@Z; DspCreateDOMAndLoadXml(wchar_t *,IXMLDOMNode * *)
0x180019f17  mov     edi, eax
0x180019f19  test    eax, eax
0x180019f1b  jns     short loc_180019F5B
0x180019f1d  mov     rcx, [rbp+18h]; this
0x180019f21  mov     r9d, eax; char *
0x180019f24  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180019f2b  mov     edx, 56Fh; void *
0x180019f30  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019f35  nop
0x180019f36  mov     rcx, rbx; bstrString
0x180019f39  call    cs:__imp_SysFreeString
0x180019f3f  nop
0x180019f40  mov     rcx, [rbp+var_40]
0x180019f44  test    rcx, rcx
0x180019f47  jz      short loc_180019F56
0x180019f49  mov     rax, [rcx]
0x180019f4c  mov     rax, [rax+10h]
0x180019f50  call    _guard_dispatch_icall
0x180019f55  nop
0x180019f56  jmp     loc_180019FDF
0x180019f5b  mov     rcx, [rbp+var_40]
0x180019f5f  test    rcx, rcx
0x180019f62  jnz     short loc_180019F70
0x180019f64  mov     edi, 80004003h
0x180019f69  mov     edx, 52Eh
0x180019f6e  jmp     short loc_180019F8F
0x180019f70  lea     r9, [rbp+var_38]
0x180019f74  lea     r8, qword_1800757A0
0x180019f7b  lea     rdx, [rbp+pv]
0x180019f7f  call    GetElementSet
0x180019f84  mov     edi, eax
0x180019f86  test    eax, eax
0x180019f88  jns     short loc_180019FE6
0x180019f8a  mov     edx, 53Ch; void *
0x180019f8f  mov     r9d, edi; char *
0x180019f92  mov     rcx, [rbp+18h]; this
0x180019f96  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180019f9d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fa2  mov     rcx, [rbp+18h]; this
0x180019fa6  mov     r9d, edi; char *
0x180019fa9  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180019fb0  mov     edx, 570h; void *
0x180019fb5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019fba  nop
0x180019fbb  mov     rcx, rbx; bstrString
0x180019fbe  call    cs:__imp_SysFreeString
0x180019fc4  nop
0x180019fc5  mov     rcx, [rbp+var_40]
0x180019fc9  test    rcx, rcx
0x180019fcc  jz      short loc_180019FDB
0x180019fce  mov     rax, [rcx]
0x180019fd1  mov     rax, [rax+10h]
0x180019fd5  call    _guard_dispatch_icall
0x180019fda  nop
0x180019fdb  test    edi, edi
0x180019fdd  jns     short loc_18001A015
0x180019fdf  mov     edx, 17Dh
0x180019fe4  jmp     short loc_18001A041
0x180019fe6  xor     edi, edi
0x180019fe8  lea     eax, [rdi+1]
0x180019feb  cmp     dword ptr [rbp+var_28+0Ch], edi
0x180019fee  cmova   edi, eax
0x180019ff1  mov     rcx, rbx; bstrString
0x180019ff4  call    cs:__imp_SysFreeString
0x180019ffa  nop
0x180019ffb  mov     rcx, [rbp+var_40]
0x180019fff  test    rcx, rcx
0x18001a002  jz      short loc_18001A011
0x18001a004  mov     rax, [rcx]
0x18001a007  mov     rax, [rax+10h]
0x18001a00b  call    _guard_dispatch_icall
0x18001a010  nop
0x18001a011  test    edi, edi
0x18001a013  jnz     short loc_18001A021
0x18001a015  mov     edi, 80242009h
0x18001a01a  mov     edx, 17Fh
0x18001a01f  jmp     short loc_18001A041
0x18001a021  mov     [rbp+var_40], 0
0x18001a029  lea     r8, [rbp+var_40]
0x18001a02d  mov     rcx, [rbp+pv]; Src
0x18001a031  call    ??$SusStrCchDup@PEA_WPEA_W@@YAJPEA_WIPEAPEA_W@Z; SusStrCchDup<wchar_t *,wchar_t *>(wchar_t *,uint,wchar_t * *)
0x18001a036  mov     edi, eax
0x18001a038  test    eax, eax
0x18001a03a  jns     short loc_18001A056
0x18001a03c  mov     edx, 182h; void *
0x18001a041  mov     rcx, [rbp+18h]; this
0x18001a045  mov     r9d, edi; char *
0x18001a048  lea     r8, aCW1SSrcClientE_13; "C:\\__w\\1\\s\\src\\Client\\Engine\\han"...
0x18001a04f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001a054  jmp     short loc_18001A05F
0x18001a056  mov     rax, [rbp+var_40]
0x18001a05a  mov     [rsi], rax
0x18001a05d  xor     edi, edi
0x18001a05f  mov     rcx, [rbp+pv]; pv
0x18001a063  test    rcx, rcx
0x18001a066  jz      short loc_18001A06E
0x18001a068  call    cs:__imp_CoTaskMemFree
0x18001a06e  mov     eax, edi
0x18001a070  mov     rcx, [rbp+var_10]
0x18001a074  xor     rcx, rsp; StackCookie
0x18001a077  call    __security_check_cookie
0x18001a07c  mov     rbx, [rsp+70h+arg_10]
0x18001a084  add     rsp, 70h
0x18001a088  pop     rdi
0x18001a089  pop     rsi
0x18001a08a  pop     rbp
0x18001a08b  retn
```
