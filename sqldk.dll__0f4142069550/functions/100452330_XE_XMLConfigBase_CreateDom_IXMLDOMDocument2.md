# XE_XMLConfigBase::CreateDom(IXMLDOMDocument2 * *)

- ea: `0x100452330`
- end: `0x10045281e`
- name: `?CreateDom@XE_XMLConfigBase@@IEAAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `1262`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x100453680`

## callees

- `0x100403070`
- `0x10044acd0`
- `0x100452330`
- `0x100614770`

## import_xrefs

- `ole32!CoCreateInstance` at `0x100452397`
- `ole32!CoCreateInstance` at `0x100452397`
- `OLEAUT32!__imp_SysAllocString` at `0x1004523c8`
- `OLEAUT32!__imp_SysAllocString` at `0x10045242e`
- `OLEAUT32!__imp_SysAllocString` at `0x10045248e`
- `OLEAUT32!__imp_SysAllocString` at `0x100452586`
- `OLEAUT32!__imp_SysAllocString` at `0x1004523c8`
- `OLEAUT32!__imp_SysAllocString` at `0x10045242e`
- `OLEAUT32!__imp_SysAllocString` at `0x10045248e`
- `OLEAUT32!__imp_SysAllocString` at `0x100452586`
- `OLEAUT32!__imp_SysFreeString` at `0x10045276c`
- `OLEAUT32!__imp_SysFreeString` at `0x10045277c`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527c2`
- `OLEAUT32!__imp_SysFreeString` at `0x10045276c`
- `OLEAUT32!__imp_SysFreeString` at `0x10045277c`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527a4`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527b3`
- `OLEAUT32!__imp_SysFreeString` at `0x1004527c2`
- `OLEAUT32!__imp_SysStringLen` at `0x100452510`
- `OLEAUT32!__imp_SysStringLen` at `0x1004526b6`
- `OLEAUT32!__imp_SysStringLen` at `0x1004526c3`
- `OLEAUT32!__imp_SysStringLen` at `0x100452510`
- `OLEAUT32!__imp_SysStringLen` at `0x1004526b6`
- `OLEAUT32!__imp_SysStringLen` at `0x1004526c3`
- `OLEAUT32!__imp_VariantClear` at `0x100452419`
- `OLEAUT32!__imp_VariantClear` at `0x100452479`
- `OLEAUT32!__imp_VariantClear` at `0x1004524e1`
- `OLEAUT32!__imp_VariantClear` at `0x1004525cc`
- `OLEAUT32!__imp_VariantClear` at `0x100452419`
- `OLEAUT32!__imp_VariantClear` at `0x100452479`
- `OLEAUT32!__imp_VariantClear` at `0x1004524e1`
- `OLEAUT32!__imp_VariantClear` at `0x1004525cc`

## string_xrefs

- `0x100452427`: `MaxXMLSize`

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
            __debugbreak();
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
                v13 = (wchar_t *)qword_100714F08(0, v12);
                v14 = (wchar_t *)*((_QWORD *)psz + 66);
                if ( v14 != v13 && v14 )
                  qword_100714F10(v14);
                *((_QWORD *)psz + 66) = v13;
                if ( v13 )
                {
                  LODWORD(ppv) = v24;
                  if ( (int)StringCchPrintfW(v13, v11, (const wchar_t *)v33, bstrString, ppv, v23, pbstr) < 0 )
                  {
                    v15 = *((_QWORD *)psz + 66);
                    if ( v15 )
                      qword_100714F10(v15);
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
0x100452330  push    rbp
0x100452332  push    rsi
0x100452333  push    rdi
0x100452334  push    r12
0x100452336  push    r13
0x100452338  push    r14
0x10045233a  push    r15
0x10045233c  lea     rbp, [rsp-20h]
0x100452341  sub     rsp, 120h
0x100452348  mov     [rbp+50h+var_A0], 0FFFFFFFFFFFFFFFEh
0x100452350  mov     [rsp+150h+arg_10], rbx
0x100452358  mov     rax, cs:__security_cookie
0x10045235f  xor     rax, rsp
0x100452362  mov     [rbp+50h+var_40], rax
0x100452366  mov     r12, rdx
0x100452369  mov     rdi, rcx
0x10045236c  xor     r13d, r13d
0x10045236f  mov     [rsp+150h+var_100], r13
0x100452374  mov     [rsp+150h+var_110], r13
0x100452379  lea     rax, [rsp+150h+var_110]
0x10045237e  mov     [rsp+150h+ppv], rax; ppv
0x100452383  lea     r9, _GUID_2933bf95_7b36_11d2_b20e_00c04f983e60; riid
0x10045238a  xor     edx, edx; pUnkOuter
0x10045238c  lea     r8d, [r13+1]; dwClsContext
0x100452390  lea     rcx, CLSID_DOMFreeThreadedDocument; rclsid
0x100452397  call    cs:__imp_CoCreateInstance
0x10045239d  mov     ebx, eax
0x10045239f  test    eax, eax
0x1004523a1  js      loc_1004527C9
0x1004523a7  mov     rcx, [rsp+150h+var_110]
0x1004523ac  mov     rax, [rcx]
0x1004523af  xor     edx, edx
0x1004523b1  call    qword ptr [rax+1F8h]
0x1004523b7  mov     ebx, eax
0x1004523b9  test    eax, eax
0x1004523bb  js      loc_1004527C9
0x1004523c1  lea     rcx, psz; "MaxElementDepth"
0x1004523c8  call    cs:__imp_SysAllocString
0x1004523ce  mov     rsi, rax
0x1004523d1  mov     [rbp+50h+var_98], rax
0x1004523d5  mov     r15d, 16h
0x1004523db  mov     word ptr [rsp+150h+pvarg], r15w
0x1004523e1  mov     dword ptr [rsp+150h+pvarg+8], 64h ; 'd'
0x1004523e9  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x1004523ee  movaps  [rbp+50h+var_C0], xmm0
0x1004523f2  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x1004523f8  movsd   [rbp+50h+var_B0], xmm1
0x1004523fd  mov     rcx, [rsp+150h+var_110]
0x100452402  mov     rax, [rcx]
0x100452405  lea     r8, [rbp+50h+var_C0]
0x100452409  mov     rdx, rsi
0x10045240c  call    qword ptr [rax+280h]
0x100452412  mov     ebx, eax
0x100452414  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100452419  call    cs:__imp_VariantClear
0x10045241f  test    ebx, ebx
0x100452421  js      loc_1004527BA
0x100452427  lea     rcx, aMaxxmlsize; "MaxXMLSize"
0x10045242e  call    cs:__imp_SysAllocString
0x100452434  mov     r14, rax
0x100452437  mov     [rbp+50h+var_90], rax
0x10045243b  mov     word ptr [rsp+150h+pvarg], r15w
0x100452441  mov     dword ptr [rsp+150h+pvarg+8], 3FFFFFh
0x100452449  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x10045244e  movaps  [rbp+50h+var_C0], xmm0
0x100452452  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x100452458  movsd   [rbp+50h+var_B0], xmm1
0x10045245d  mov     rcx, [rsp+150h+var_110]
0x100452462  mov     rax, [rcx]
0x100452465  lea     r8, [rbp+50h+var_C0]
0x100452469  mov     rdx, r14
0x10045246c  call    qword ptr [rax+280h]
0x100452472  mov     ebx, eax
0x100452474  lea     rcx, [rsp+150h+pvarg]; pvarg
0x100452479  call    cs:__imp_VariantClear
0x10045247f  test    ebx, ebx
0x100452481  js      loc_1004527AB
0x100452487  lea     rcx, aProhibitdtd; "ProhibitDTD"
0x10045248e  call    cs:__imp_SysAllocString
0x100452494  mov     r15, rax
0x100452497  mov     [rbp+50h+var_88], rax
0x10045249b  mov     eax, 2
0x1004524a0  mov     word ptr [rsp+150h+pvarg], ax
0x1004524a5  mov     rax, 0FFFFFFFFFFFFFFFFh
0x1004524ac  mov     word ptr [rsp+150h+pvarg+8], ax
0x1004524b1  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x1004524b6  movaps  [rbp+50h+var_C0], xmm0
0x1004524ba  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x1004524c0  movsd   [rbp+50h+var_B0], xmm1
0x1004524c5  mov     rcx, [rsp+150h+var_110]
0x1004524ca  mov     rax, [rcx]
0x1004524cd  lea     r8, [rbp+50h+var_C0]
0x1004524d1  mov     rdx, r15
0x1004524d4  call    qword ptr [rax+280h]
0x1004524da  mov     ebx, eax
0x1004524dc  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1004524e1  call    cs:__imp_VariantClear
0x1004524e7  test    ebx, ebx
0x1004524e9  js      loc_10045279C
0x1004524ef  mov     rcx, [rsp+150h+var_110]
0x1004524f4  mov     rax, [rcx]
0x1004524f7  xor     edx, edx
0x1004524f9  call    qword ptr [rax+230h]
0x1004524ff  mov     ebx, eax
0x100452501  test    eax, eax
0x100452503  js      loc_10045279C
0x100452509  mov     rcx, [rdi+208h]; pbstr
0x100452510  call    cs:__imp_SysStringLen
0x100452516  test    eax, eax
0x100452518  jz      short loc_100452543
0x10045251a  mov     rcx, [rsp+150h+var_110]
0x10045251f  mov     rax, [rcx]
0x100452522  lea     r8, [rsp+150h+var_108]
0x100452527  mov     rdx, [rdi+208h]
0x10045252e  call    qword ptr [rax+208h]
0x100452534  mov     ebx, eax
0x100452536  test    eax, eax
0x100452538  jns     loc_1004525DA
0x10045253e  jmp     loc_10045279C
0x100452543  mov     edx, 104h
0x100452548  mov     ecx, edx
0x10045254a  mov     rax, rdi
0x10045254d  nop     dword ptr [rax]
0x100452550  cmp     word ptr [rax], 0
0x100452554  jz      short loc_100452560
0x100452556  add     rax, 2
0x10045255a  sub     rcx, 1
0x10045255e  jnz     short loc_100452550
0x100452560  sub     rdx, rcx
0x100452563  test    rcx, rcx
0x100452566  cmovz   rdx, r13
0x10045256a  jz      loc_100452797
0x100452570  test    rdx, rdx
0x100452573  jz      loc_100452797
0x100452579  mov     eax, 8
0x10045257e  mov     word ptr [rsp+150h+pvarg], ax
0x100452583  mov     rcx, rdi; psz
0x100452586  call    cs:__imp_SysAllocString
0x10045258c  mov     qword ptr [rsp+150h+pvarg+8], rax
0x100452591  test    rax, rax
0x100452594  jz      loc_100452813
0x10045259a  movups  xmm0, xmmword ptr [rsp+150h+pvarg]
0x10045259f  movaps  [rbp+50h+var_C0], xmm0
0x1004525a3  movsd   xmm1, qword ptr [rsp+150h+pvarg+10h]
0x1004525a9  movsd   [rbp+50h+var_B0], xmm1
0x1004525ae  mov     rcx, [rsp+150h+var_110]
0x1004525b3  mov     rax, [rcx]
0x1004525b6  lea     r8, [rsp+150h+var_108]
0x1004525bb  lea     rdx, [rbp+50h+var_C0]
0x1004525bf  call    qword ptr [rax+1D0h]
0x1004525c5  mov     ebx, eax
0x1004525c7  lea     rcx, [rsp+150h+pvarg]; pvarg
0x1004525cc  call    cs:__imp_VariantClear
0x1004525d2  test    ebx, ebx
0x1004525d4  js      loc_10045279C
0x1004525da  cmp     [rsp+150h+var_108], 0FFFFh
0x1004525e0  jz      loc_100452784
0x1004525e6  mov     rcx, [rsp+150h+var_110]
0x1004525eb  mov     rax, [rcx]
0x1004525ee  lea     rdx, [rsp+150h+var_100]
0x1004525f3  call    qword ptr [rax+1E0h]
0x1004525f9  mov     ebx, eax
0x1004525fb  test    eax, eax
0x1004525fd  js      loc_10045279C
0x100452603  mov     rcx, [rsp+150h+var_100]
0x100452608  mov     rax, [rcx]
0x10045260b  lea     rdx, [rbp+50h+var_C8]
0x10045260f  call    qword ptr [rax+38h]
0x100452612  mov     [rbp+50h+bstrString], r13
0x100452616  mov     rcx, [rsp+150h+var_100]
0x10045261b  mov     rax, [rcx]
0x10045261e  lea     rdx, [rbp+50h+bstrString]
0x100452622  call    qword ptr [rax+48h]
0x100452625  mov     ebx, eax
0x100452627  test    eax, eax
0x100452629  js      loc_100452773
0x10045262f  mov     [rsp+150h+pbstr], r13
0x100452634  mov     rcx, [rsp+150h+var_100]
0x100452639  mov     rax, [rcx]
0x10045263c  lea     rdx, [rsp+150h+pbstr]
0x100452641  call    qword ptr [rax+50h]
0x100452644  mov     ebx, eax
0x100452646  test    eax, eax
0x100452648  js      loc_100452762
0x10045264e  mov     [rsp+150h+var_DC], r13d
0x100452653  mov     rcx, [rsp+150h+var_100]
0x100452658  mov     rax, [rcx]
0x10045265b  lea     rdx, [rsp+150h+var_DC]
0x100452660  call    qword ptr [rax+58h]
0x100452663  mov     [rsp+150h+var_E0], r13d
0x100452668  mov     rcx, [rsp+150h+var_100]
0x10045266d  mov     rax, [rcx]
0x100452670  lea     rdx, [rsp+150h+var_E0]
0x100452675  call    qword ptr [rax+60h]
0x100452678  movups  xmm0, xmmword ptr cs:aSAtLineDPositi; "%s at line %d position %d\n%s"
0x10045267f  movups  xmmword ptr [rbp+50h+var_80], xmm0
0x100452683  movups  xmm1, xmmword ptr cs:aSAtLineDPositi+10h; "ne %d position %d\n%s"
0x10045268a  movups  xmmword ptr [rbp+50h+var_80+10h], xmm1
0x10045268e  movups  xmm0, xmmword ptr cs:aSAtLineDPositi+20h; "sition %d\n%s"
0x100452695  movups  [rbp+50h+var_60], xmm0
0x100452699  movsd   xmm1, qword ptr cs:aSAtLineDPositi+30h; "d\n%s"
0x1004526a1  movsd   [rbp+50h+var_50], xmm1
0x1004526a6  movzx   eax, word ptr cs:aSAtLineDPositi+38h; ""
0x1004526ad  mov     [rbp+50h+var_48], ax
0x1004526b1  mov     rcx, [rsp+150h+pbstr]; pbstr
0x1004526b6  call    cs:__imp_SysStringLen
0x1004526bc  mov     r12d, eax
0x1004526bf  mov     rcx, [rbp+50h+bstrString]; pbstr
0x1004526c3  call    cs:__imp_SysStringLen
0x1004526c9  mov     eax, eax
0x1004526cb  add     rax, 33h ; '3'
0x1004526cf  add     r12, rax
0x1004526d2  mov     eax, 2
0x1004526d7  mul     r12
0x1004526da  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1004526e1  cmovo   rax, rcx
0x1004526e5  mov     edx, eax
0x1004526e7  xor     ecx, ecx
0x1004526e9  call    cs:qword_100714F08
0x1004526ef  mov     rbx, rax
0x1004526f2  mov     rcx, [rdi+210h]
0x1004526f9  cmp     rcx, rax
0x1004526fc  jz      short loc_100452709
0x1004526fe  test    rcx, rcx
0x100452701  jz      short loc_100452709
0x100452703  call    cs:qword_100714F10
0x100452709  mov     [rdi+210h], rbx
0x100452710  test    rbx, rbx
0x100452713  jz      short loc_10045275F
0x100452715  mov     rax, [rsp+150h+pbstr]
0x10045271a  mov     [rsp+150h+var_120], rax
0x10045271f  mov     eax, [rsp+150h+var_E0]
0x100452723  mov     [rsp+150h+var_128], eax
0x100452727  mov     eax, [rsp+150h+var_DC]
0x10045272b  mov     dword ptr [rsp+150h+ppv], eax
0x10045272f  mov     r9, [rbp+50h+bstrString]
0x100452733  lea     r8, [rbp+50h+var_80]; wchar_t *
0x100452737  mov     rdx, r12; unsigned __int64
0x10045273a  mov     rcx, rbx; Buffer
0x10045273d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100452742  test    eax, eax
0x100452744  jns     short loc_10045275F
0x100452746  mov     rcx, [rdi+210h]
0x10045274d  test    rcx, rcx
0x100452750  jz      short loc_100452758
0x100452752  call    cs:qword_100714F10
0x100452758  mov     [rdi+210h], r13
0x10045275f  mov     ebx, [rbp+50h+var_C8]
0x100452762  mov     rcx, [rsp+150h+pbstr]; bstrString
0x100452767  test    rcx, rcx
0x10045276a  jz      short loc_100452773
0x10045276c  call    cs:__imp_SysFreeString
0x100452772  nop
0x100452773  mov     rcx, [rbp+50h+bstrString]; bstrString
0x100452777  test    rcx, rcx
0x10045277a  jz      short loc_10045279C
0x10045277c  call    cs:__imp_SysFreeString
0x100452782  jmp     short loc_10045279C
0x100452784  mov     rax, [rsp+150h+var_110]
0x100452789  mov     [rsp+150h+var_110], r13
0x10045278e  mov     [r12], rax
0x100452792  mov     ebx, r13d
0x100452795  jmp     short loc_10045279C
0x100452797  mov     ebx, 80004005h
0x10045279c  test    r15, r15
0x10045279f  jz      short loc_1004527AB
0x1004527a1  mov     rcx, r15; bstrString
0x1004527a4  call    cs:__imp_SysFreeString
0x1004527aa  nop
0x1004527ab  test    r14, r14
0x1004527ae  jz      short loc_1004527BA
0x1004527b0  mov     rcx, r14; bstrString
0x1004527b3  call    cs:__imp_SysFreeString
0x1004527b9  nop
0x1004527ba  test    rsi, rsi
0x1004527bd  jz      short loc_1004527C9
0x1004527bf  mov     rcx, rsi; bstrString
0x1004527c2  call    cs:__imp_SysFreeString
0x1004527c8  nop
0x1004527c9  mov     rcx, [rsp+150h+var_110]
0x1004527ce  test    rcx, rcx
0x1004527d1  jz      short loc_1004527DA
0x1004527d3  mov     rdx, [rcx]
0x1004527d6  call    qword ptr [rdx+10h]
0x1004527d9  nop
0x1004527da  mov     rcx, [rsp+150h+var_100]
0x1004527df  test    rcx, rcx
0x1004527e2  jz      short loc_1004527EA
0x1004527e4  mov     rdx, [rcx]
0x1004527e7  call    qword ptr [rdx+10h]
0x1004527ea  mov     eax, ebx
0x1004527ec  mov     rcx, [rbp+50h+var_40]
0x1004527f0  xor     rcx, rsp; StackCookie
0x1004527f3  call    __security_check_cookie
0x1004527f8  mov     rbx, [rsp+150h+arg_10]
0x100452800  add     rsp, 120h
0x100452807  pop     r15
0x100452809  pop     r14
0x10045280b  pop     r13
0x10045280d  pop     r12
  ... truncated ...
```
