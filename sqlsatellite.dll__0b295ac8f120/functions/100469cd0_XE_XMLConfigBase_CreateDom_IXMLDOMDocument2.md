# XE_XMLConfigBase::CreateDom(IXMLDOMDocument2 * *)

- ea: `0x100469cd0`
- end: `0x10046a1be`
- name: `?CreateDom@XE_XMLConfigBase@@IEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x100405990`
- `0x10046a5d0`
- `0x10046a790`
- `0x10046b390`

## callees

- `0x10040d8a0`
- `0x100469cd0`
- `0x100486af0`
- `0x100487e80`

## import_xrefs

- `ole32!CoCreateInstance` at `0x100469d37`
- `ole32!CoCreateInstance` at `0x100469d37`
- `OLEAUT32!__imp_SysAllocString` at `0x100469d68`
- `OLEAUT32!__imp_SysAllocString` at `0x100469dce`
- `OLEAUT32!__imp_SysAllocString` at `0x100469e2e`
- `OLEAUT32!__imp_SysAllocString` at `0x100469f26`
- `OLEAUT32!__imp_SysAllocString` at `0x100469d68`
- `OLEAUT32!__imp_SysAllocString` at `0x100469dce`
- `OLEAUT32!__imp_SysAllocString` at `0x100469e2e`
- `OLEAUT32!__imp_SysAllocString` at `0x100469f26`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a10c`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a11c`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a144`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a153`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a162`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a10c`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a11c`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a144`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a153`
- `OLEAUT32!__imp_SysFreeString` at `0x10046a162`
- `OLEAUT32!__imp_SysStringLen` at `0x100469eb0`
- `OLEAUT32!__imp_SysStringLen` at `0x10046a056`
- `OLEAUT32!__imp_SysStringLen` at `0x10046a063`
- `OLEAUT32!__imp_SysStringLen` at `0x100469eb0`
- `OLEAUT32!__imp_SysStringLen` at `0x10046a056`
- `OLEAUT32!__imp_SysStringLen` at `0x10046a063`
- `OLEAUT32!__imp_VariantClear` at `0x100469db9`
- `OLEAUT32!__imp_VariantClear` at `0x100469e19`
- `OLEAUT32!__imp_VariantClear` at `0x100469e81`
- `OLEAUT32!__imp_VariantClear` at `0x100469f6c`
- `OLEAUT32!__imp_VariantClear` at `0x100469db9`
- `OLEAUT32!__imp_VariantClear` at `0x100469e19`
- `OLEAUT32!__imp_VariantClear` at `0x100469e81`
- `OLEAUT32!__imp_VariantClear` at `0x100469f6c`

## string_xrefs

- `0x100469dc7`: `MaxXMLSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall XE_XMLConfigBase::CreateDom(OLECHAR *psz, struct IXMLDOMDocument2 **a2)
{
  HRESULT v4; // ebx
  OLECHAR *v5; // rsi
  OLECHAR *v6; // r14
  OLECHAR *v7; // r15
  __int64 v8; // rcx
  OLECHAR *v9; // rax
  __int64 v10; // r12
  unsigned __int64 v11; // r12
  unsigned int v12; // eax
  wchar_t *v13; // rbx
  wchar_t *v14; // rcx
  __int64 v15; // rcx
  struct IXMLDOMDocument2 *v16; // rax
  LPVOID *ppv; // [rsp+20h] [rbp-E0h]
  LPVOID v19; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v20; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v21; // [rsp+50h] [rbp-B0h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-A8h] BYREF
  int v23; // [rsp+70h] [rbp-90h] BYREF
  int v24; // [rsp+74h] [rbp-8Ch] BYREF
  BSTR pbstr; // [rsp+78h] [rbp-88h] BYREF
  BSTR bstrString; // [rsp+80h] [rbp-80h] BYREF
  HRESULT v27; // [rsp+88h] [rbp-78h] BYREF
  VARIANTARG v28; // [rsp+90h] [rbp-70h] BYREF
  __int64 v29; // [rsp+B0h] [rbp-50h]
  OLECHAR *v30; // [rsp+B8h] [rbp-48h]
  OLECHAR *v31; // [rsp+C0h] [rbp-40h]
  OLECHAR *v32; // [rsp+C8h] [rbp-38h]
  _OWORD v33[4]; // [rsp+D0h] [rbp-30h] BYREF

  v29 = -2;
  v21 = 0;
  v19 = 0;
  v4 = CoCreateInstance(&CLSID_DOMFreeThreadedDocument, 0, 1u, &GUID_2933bf95_7b36_11d2_b20e_00c04f983e60, &v19);
  if ( v4 < 0 )
    goto LABEL_44;
  v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v19 + 504LL))(v19, 0);
  if ( v4 < 0 )
    goto LABEL_44;
  v5 = SysAllocString(L"MaxElementDepth");
  v30 = v5;
  pvarg.vt = 22;
  pvarg.lVal = 100;
  v28 = pvarg;
  v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v19 + 640LL))(v19, v5, &v28);
  VariantClear(&pvarg);
  if ( v4 >= 0 )
  {
    v6 = SysAllocString(L"MaxXMLSize");
    v31 = v6;
    pvarg.vt = 22;
    pvarg.lVal = 0x3FFFFF;
    v28 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v19 + 640LL))(v19, v6, &v28);
    VariantClear(&pvarg);
    if ( v4 < 0 )
    {
LABEL_40:
      if ( v6 )
        SysFreeString(v6);
      goto LABEL_42;
    }
    v7 = SysAllocString(L"ProhibitDTD");
    v32 = v7;
    pvarg.vt = 2;
    pvarg.iVal = -1;
    v28 = pvarg;
    v4 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v19 + 640LL))(v19, v7, &v28);
    VariantClear(&pvarg);
    if ( v4 >= 0 )
    {
      v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v19 + 560LL))(v19, 0);
      if ( v4 >= 0 )
      {
        if ( SysStringLen(*((BSTR *)psz + 65)) )
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, _QWORD, __int16 *))(*(_QWORD *)v19 + 520LL))(
                 v19,
                 *((_QWORD *)psz + 65),
                 &v20);
          if ( v4 < 0 )
            goto LABEL_38;
        }
        else
        {
          v8 = 260;
          v9 = psz;
          do
          {
            if ( !*v9 )
              break;
            ++v9;
            --v8;
          }
          while ( v8 );
          if ( !v8 || 260 == v8 )
          {
            v4 = -2147467259;
            goto LABEL_38;
          }
          pvarg.vt = 8;
          pvarg.llVal = (LONGLONG)SysAllocString(psz);
          if ( !pvarg.llVal )
          {
            _com_issue_error(-2147024882);
            JUMPOUT(0x10046A1BDLL);
          }
          v28 = pvarg;
          v4 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)v19 + 464LL))(v19, &v28, &v20);
          VariantClear(&pvarg);
          if ( v4 < 0 )
            goto LABEL_38;
        }
        if ( v20 == -1 )
        {
          v16 = (struct IXMLDOMDocument2 *)v19;
          v19 = 0;
          *a2 = v16;
          v4 = 0;
        }
        else
        {
          v4 = (*(__int64 (__fastcall **)(LPVOID, __int64 *))(*(_QWORD *)v19 + 480LL))(v19, &v21);
          if ( v4 >= 0 )
          {
            (*(void (__fastcall **)(__int64, HRESULT *))(*(_QWORD *)v21 + 56LL))(v21, &v27);
            bstrString = 0;
            v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 72LL))(v21, &bstrString);
            if ( v4 >= 0 )
            {
              pbstr = 0;
              v4 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v21 + 80LL))(v21, &pbstr);
              if ( v4 >= 0 )
              {
                v24 = 0;
                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 88LL))(v21, &v24);
                v23 = 0;
                (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v21 + 96LL))(v21, &v23);
                wcscpy((wchar_t *)v33, L"%s at line %d position %d\n%s");
                v10 = SysStringLen(pbstr);
                v11 = SysStringLen(bstrString) + 51LL + v10;
                v12 = 2 * v11;
                if ( !is_mul_ok(v11, 2u) )
                  v12 = -1;
                v13 = (wchar_t *)qword_1005170E8(0, v12);
                v14 = (wchar_t *)*((_QWORD *)psz + 66);
                if ( v14 != v13 && v14 )
                  qword_1005170F0(v14);
                *((_QWORD *)psz + 66) = v13;
                if ( v13 )
                {
                  LODWORD(ppv) = v24;
                  if ( (int)StringCchPrintfW(v13, v11, (const wchar_t *)v33, bstrString, ppv, v23, pbstr) < 0 )
                  {
                    v15 = *((_QWORD *)psz + 66);
                    if ( v15 )
                      qword_1005170F0(v15);
                    *((_QWORD *)psz + 66) = 0;
                  }
                }
                v4 = v27;
              }
              if ( pbstr )
                SysFreeString(pbstr);
            }
            if ( bstrString )
              SysFreeString(bstrString);
          }
        }
      }
    }
LABEL_38:
    if ( v7 )
      SysFreeString(v7);
    goto LABEL_40;
  }
LABEL_42:
  if ( v5 )
    SysFreeString(v5);
LABEL_44:
  if ( v19 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v19 + 16LL))(v19);
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x100469cd0  push    rbp
0x100469cd2  push    rsi
0x100469cd3  push    rdi
0x100469cd4  push    r12
0x100469cd6  push    r13
0x100469cd8  push    r14
0x100469cda  push    r15
0x100469cdc  lea     rbp, [rsp-20h]
0x100469ce1  sub     rsp, 120h
0x100469ce8  mov     [rbp+50h+var_A0], 0FFFFFFFFFFFFFFFEh
0x100469cf0  mov     [rsp+150h+arg_10], rbx
0x100469cf8  mov     rax, cs:__security_cookie
0x100469cff  xor     rax, rsp
0x100469d02  mov     [rbp+50h+var_40], rax
0x100469d06  mov     r12, rdx
0x100469d09  mov     rdi, rcx
0x100469d0c  xor     r13d, r13d
0x100469d0f  mov     [rsp+150h+var_100], r13
0x100469d14  mov     [rsp+150h+var_110], r13
0x100469d19  lea     rax, [rsp+150h+var_110]
0x100469d1e  mov     [rsp+150h+ppv], rax; ppv
0x100469d23  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x100469d2a  xor     edx, edx; pUnkOuter
0x100469d2c  lea     r8d, [r13+1]; dwClsContext
0x100469d30  lea     rcx, CLSID_DOMFreeThreadedDocument; rclsid
0x100469d37  call    cs:__imp_CoCreateInstance
0x100469d3d  mov     ebx, eax
0x100469d3f  test    eax, eax
0x100469d41  js      loc_10046A169
0x100469d47  mov     rcx, [rsp+150h+var_110]
0x100469d4c  mov     rax, [rcx]
0x100469d4f  xor     edx, edx
0x100469d51  call    qword ptr [rax+1F8h]
0x100469d57  mov     ebx, eax
0x100469d59  test    eax, eax
0x100469d5b  js      loc_10046A169
0x100469d61  lea     rcx, aMaxelementdept; "MaxElementDepth"
0x100469d68  call    cs:__imp_SysAllocString
0x100469d6e  mov     rsi, rax
0x100469d71  mov     [rbp+50h+var_98], rax
0x100469d75  mov     r15d, 16h
0x100469d7b  mov     word ptr [rsp+150h+pvarg], r15w
0x100469d81  mov     dword ptr [rsp+150h+pvarg+8], 64h ; 'd'
0x100469d89  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x100469d8e  movaps  [rbp+50h+var_C0], xmm0
0x100469d92  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x100469d98  movsd   [rbp+50h+var_B0], xmm1
0x100469d9d  mov     rcx, [rsp+150h+var_110]
0x100469da2  mov     rax, [rcx]
0x100469da5  lea     r8, [rbp+50h+var_C0]
0x100469da9  mov     rdx, rsi
0x100469dac  call    qword ptr [rax+280h]
0x100469db2  mov     ebx, eax
0x100469db4  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100469db9  call    cs:__imp_VariantClear
0x100469dbf  test    ebx, ebx
0x100469dc1  js      loc_10046A15A
0x100469dc7  lea     rcx, aMaxxmlsize; "MaxXMLSize"
0x100469dce  call    cs:__imp_SysAllocString
0x100469dd4  mov     r14, rax
0x100469dd7  mov     [rbp+50h+var_90], rax
0x100469ddb  mov     word ptr [rsp+150h+pvarg], r15w
0x100469de1  mov     dword ptr [rsp+150h+pvarg+8], 3FFFFFh
0x100469de9  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x100469dee  movaps  [rbp+50h+var_C0], xmm0
0x100469df2  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x100469df8  movsd   [rbp+50h+var_B0], xmm1
0x100469dfd  mov     rcx, [rsp+150h+var_110]
0x100469e02  mov     rax, [rcx]
0x100469e05  lea     r8, [rbp+50h+var_C0]
0x100469e09  mov     rdx, r14
0x100469e0c  call    qword ptr [rax+280h]
0x100469e12  mov     ebx, eax
0x100469e14  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100469e19  call    cs:__imp_VariantClear
0x100469e1f  test    ebx, ebx
0x100469e21  js      loc_10046A14B
0x100469e27  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x100469e2e  call    cs:__imp_SysAllocString
0x100469e34  mov     r15, rax
0x100469e37  mov     [rbp+50h+var_88], rax
0x100469e3b  mov     eax, 2
0x100469e40  mov     word ptr [rsp+150h+pvarg], ax
0x100469e45  mov     rax, 0FFFFFFFFFFFFFFFFh
0x100469e4c  mov     word ptr [rsp+150h+pvarg+8], ax
0x100469e51  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x100469e56  movaps  [rbp+50h+var_C0], xmm0
0x100469e5a  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x100469e60  movsd   [rbp+50h+var_B0], xmm1
0x100469e65  mov     rcx, [rsp+150h+var_110]
0x100469e6a  mov     rax, [rcx]
0x100469e6d  lea     r8, [rbp+50h+var_C0]
0x100469e71  mov     rdx, r15
0x100469e74  call    qword ptr [rax+280h]
0x100469e7a  mov     ebx, eax
0x100469e7c  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100469e81  call    cs:__imp_VariantClear
0x100469e87  test    ebx, ebx
0x100469e89  js      loc_10046A13C
0x100469e8f  mov     rcx, [rsp+150h+var_110]
0x100469e94  mov     rax, [rcx]
0x100469e97  xor     edx, edx
0x100469e99  call    qword ptr [rax+230h]
0x100469e9f  mov     ebx, eax
0x100469ea1  test    eax, eax
0x100469ea3  js      loc_10046A13C
0x100469ea9  mov     rcx, [rdi+208h]; pbstr
0x100469eb0  call    cs:__imp_SysStringLen
0x100469eb6  test    eax, eax
0x100469eb8  jz      short loc_100469EE3
0x100469eba  mov     rcx, [rsp+150h+var_110]
0x100469ebf  mov     rax, [rcx]
0x100469ec2  lea     r8, [rsp+150h+var_108]
0x100469ec7  mov     rdx, [rdi+208h]
0x100469ece  call    qword ptr [rax+208h]
0x100469ed4  mov     ebx, eax
0x100469ed6  test    eax, eax
0x100469ed8  jns     loc_100469F7A
0x100469ede  jmp     loc_10046A13C
0x100469ee3  mov     edx, 104h
0x100469ee8  mov     ecx, edx
0x100469eea  mov     rax, rdi
0x100469eed  nop     dword ptr [rax]
0x100469ef0  cmp     word ptr [rax], 0
0x100469ef4  jz      short loc_100469F00
0x100469ef6  add     rax, 2
0x100469efa  sub     rcx, 1
0x100469efe  jnz     short loc_100469EF0
0x100469f00  sub     rdx, rcx
0x100469f03  test    rcx, rcx
0x100469f06  cmovz   rdx, r13
0x100469f0a  jz      loc_10046A137
0x100469f10  test    rdx, rdx
0x100469f13  jz      loc_10046A137
0x100469f19  mov     eax, 8
0x100469f1e  mov     word ptr [rsp+150h+pvarg], ax
0x100469f23  mov     rcx, rdi; psz
0x100469f26  call    cs:__imp_SysAllocString
0x100469f2c  mov     qword ptr [rsp+150h+pvarg+8], rax
0x100469f31  test    rax, rax
0x100469f34  jz      loc_10046A1B3
0x100469f3a  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x100469f3f  movaps  [rbp+50h+var_C0], xmm0
0x100469f43  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x100469f49  movsd   [rbp+50h+var_B0], xmm1
0x100469f4e  mov     rcx, [rsp+150h+var_110]
0x100469f53  mov     rax, [rcx]
0x100469f56  lea     r8, [rsp+150h+var_108]
0x100469f5b  lea     rdx, [rbp+50h+var_C0]
0x100469f5f  call    qword ptr [rax+1D0h]
0x100469f65  mov     ebx, eax
0x100469f67  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100469f6c  call    cs:__imp_VariantClear
0x100469f72  test    ebx, ebx
0x100469f74  js      loc_10046A13C
0x100469f7a  cmp     [rsp+150h+var_108], 0FFFFh
0x100469f80  jz      loc_10046A124
0x100469f86  mov     rcx, [rsp+150h+var_110]
0x100469f8b  mov     rax, [rcx]
0x100469f8e  lea     rdx, [rsp+150h+var_100]
0x100469f93  call    qword ptr [rax+1E0h]
0x100469f99  mov     ebx, eax
0x100469f9b  test    eax, eax
0x100469f9d  js      loc_10046A13C
0x100469fa3  mov     rcx, [rsp+150h+var_100]
0x100469fa8  mov     rax, [rcx]
0x100469fab  lea     rdx, [rbp+50h+var_C8]
0x100469faf  call    qword ptr [rax+38h]
0x100469fb2  mov     [rbp+50h+bstrString], r13
0x100469fb6  mov     rcx, [rsp+150h+var_100]
0x100469fbb  mov     rax, [rcx]
0x100469fbe  lea     rdx, [rbp+50h+bstrString]
0x100469fc2  call    qword ptr [rax+48h]
0x100469fc5  mov     ebx, eax
0x100469fc7  test    eax, eax
0x100469fc9  js      loc_10046A113
0x100469fcf  mov     [rsp+150h+pbstr], r13
0x100469fd4  mov     rcx, [rsp+150h+var_100]
0x100469fd9  mov     rax, [rcx]
0x100469fdc  lea     rdx, [rsp+150h+pbstr]
0x100469fe1  call    qword ptr [rax+50h]
0x100469fe4  mov     ebx, eax
0x100469fe6  test    eax, eax
0x100469fe8  js      loc_10046A102
0x100469fee  mov     [rsp+150h+var_DC], r13d
0x100469ff3  mov     rcx, [rsp+150h+var_100]
0x100469ff8  mov     rax, [rcx]
0x100469ffb  lea     rdx, [rsp+150h+var_DC]
0x10046a000  call    qword ptr [rax+58h]
0x10046a003  mov     [rsp+150h+var_E0], r13d
0x10046a008  mov     rcx, [rsp+150h+var_100]
0x10046a00d  mov     rax, [rcx]
0x10046a010  lea     rdx, [rsp+150h+var_E0]
0x10046a015  call    qword ptr [rax+60h]
0x10046a018  movups  xmm0, xmmword ptr cs:aSAtLineDPositi; "%s at line %d position %d\n%s"
0x10046a01f  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x10046a023  movups  xmm1, xmmword ptr cs:aSAtLineDPositi+10h; "ne %d position %d\n%s"
0x10046a02a  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x10046a02e  movups  xmm0, xmmword ptr cs:aSAtLineDPositi+20h; "sition %d\n%s"
0x10046a035  movups  [rbp+50h+var_60], xmm0
0x10046a039  movsd   xmm1, qword ptr cs:aSAtLineDPositi+30h; "d\n%s"
0x10046a041  movsd   [rbp+50h+var_50], xmm1
0x10046a046  movzx   eax, word ptr cs:aSAtLineDPositi+38h; ""
0x10046a04d  mov     [rbp+50h+var_48], ax
0x10046a051  mov     rcx, [rsp+150h+pbstr]; pbstr
0x10046a056  call    cs:__imp_SysStringLen
0x10046a05c  mov     r12d, eax
0x10046a05f  mov     rcx, [rbp+50h+bstrString]; pbstr
0x10046a063  call    cs:__imp_SysStringLen
0x10046a069  mov     eax, eax
0x10046a06b  add     rax, 33h ; '3'
0x10046a06f  add     r12, rax
0x10046a072  mov     eax, 2
0x10046a077  mul     r12
0x10046a07a  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x10046a081  cmovo   rax, rcx
0x10046a085  mov     edx, eax
0x10046a087  xor     ecx, ecx
0x10046a089  call    cs:qword_1005170E8
0x10046a08f  mov     rbx, rax
0x10046a092  mov     rcx, [rdi+210h]
0x10046a099  cmp     rcx, rax
0x10046a09c  jz      short loc_10046A0A9
0x10046a09e  test    rcx, rcx
0x10046a0a1  jz      short loc_10046A0A9
0x10046a0a3  call    cs:qword_1005170F0
0x10046a0a9  mov     [rdi+210h], rbx
0x10046a0b0  test    rbx, rbx
0x10046a0b3  jz      short loc_10046A0FF
0x10046a0b5  mov     rax, [rsp+150h+pbstr]
0x10046a0ba  mov     [rsp+150h+var_120], rax
0x10046a0bf  mov     eax, [rsp+150h+var_E0]
0x10046a0c3  mov     [rsp+150h+var_128], eax
0x10046a0c7  mov     eax, [rsp+150h+var_DC]
0x10046a0cb  mov     dword ptr [rsp+150h+ppv], eax
0x10046a0cf  mov     r9, [rbp+50h+bstrString]
0x10046a0d3  lea     r8, [rbp+50h+var_80]; wchar_t *
0x10046a0d7  mov     rdx, r12; unsigned __int64
0x10046a0da  mov     rcx, rbx; Buffer
0x10046a0dd  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10046a0e2  test    eax, eax
0x10046a0e4  jns     short loc_10046A0FF
0x10046a0e6  mov     rcx, [rdi+210h]
0x10046a0ed  test    rcx, rcx
0x10046a0f0  jz      short loc_10046A0F8
0x10046a0f2  call    cs:qword_1005170F0
0x10046a0f8  mov     [rdi+210h], r13
0x10046a0ff  mov     ebx, [rbp+50h+var_C8]
0x10046a102  mov     rcx, [rsp+150h+pbstr]; bstrString
0x10046a107  test    rcx, rcx
0x10046a10a  jz      short loc_10046A113
0x10046a10c  call    cs:__imp_SysFreeString
0x10046a112  nop
0x10046a113  mov     rcx, [rbp+50h+bstrString]; bstrString
0x10046a117  test    rcx, rcx
0x10046a11a  jz      short loc_10046A13C
0x10046a11c  call    cs:__imp_SysFreeString
0x10046a122  jmp     short loc_10046A13C
0x10046a124  mov     rax, [rsp+150h+var_110]
0x10046a129  mov     [rsp+150h+var_110], r13
0x10046a12e  mov     [r12], rax
0x10046a132  mov     ebx, r13d
0x10046a135  jmp     short loc_10046A13C
0x10046a137  mov     ebx, 80004005h
0x10046a13c  test    r15, r15
0x10046a13f  jz      short loc_10046A14B
0x10046a141  mov     rcx, r15; bstrString
0x10046a144  call    cs:__imp_SysFreeString
0x10046a14a  nop
0x10046a14b  test    r14, r14
0x10046a14e  jz      short loc_10046A15A
0x10046a150  mov     rcx, r14; bstrString
0x10046a153  call    cs:__imp_SysFreeString
0x10046a159  nop
0x10046a15a  test    rsi, rsi
0x10046a15d  jz      short loc_10046A169
0x10046a15f  mov     rcx, rsi; bstrString
0x10046a162  call    cs:__imp_SysFreeString
0x10046a168  nop
0x10046a169  mov     rcx, [rsp+150h+var_110]
0x10046a16e  test    rcx, rcx
0x10046a171  jz      short loc_10046A17A
0x10046a173  mov     rdx, [rcx]
0x10046a176  call    qword ptr [rdx+10h]
0x10046a179  nop
0x10046a17a  mov     rcx, [rsp+150h+var_100]
0x10046a17f  test    rcx, rcx
0x10046a182  jz      short loc_10046A18A
0x10046a184  mov     rdx, [rcx]
0x10046a187  call    qword ptr [rdx+10h]
0x10046a18a  mov     eax, ebx
0x10046a18c  mov     rcx, [rbp+50h+var_40]
0x10046a190  xor     rcx, rsp; StackCookie
0x10046a193  call    __security_check_cookie
0x10046a198  mov     rbx, [rsp+150h+arg_10]
0x10046a1a0  add     rsp, 120h
0x10046a1a7  pop     r15
0x10046a1a9  pop     r14
0x10046a1ab  pop     r13
0x10046a1ad  pop     r12
  ... truncated ...
```
