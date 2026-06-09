# DumperConfig::InsertXmlElement(ATL::CComPtr<IXMLDOMDocument2>,ATL::CComVariant,wchar_t const *,wchar_t const *,wchar_t *,ushort)

- ea: `0x100444fc0`
- end: `0x1004452b4`
- name: `?InsertXmlElement@DumperConfig@@CA_NV?$CComPtr@UIXMLDOMDocument2@@@ATL@@VCComVariant@3@PEB_W2PEA_WG@Z`
- size: `756`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x100444870`

## callees

- `0x100404a30`
- `0x100444590`
- `0x100444fc0`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x10044500d`
- `OLEAUT32!__imp_SysAllocString` at `0x10044513c`
- `OLEAUT32!__imp_SysAllocString` at `0x10044515a`
- `OLEAUT32!__imp_SysAllocString` at `0x10044500d`
- `OLEAUT32!__imp_SysAllocString` at `0x10044513c`
- `OLEAUT32!__imp_SysAllocString` at `0x10044515a`
- `OLEAUT32!__imp_SysFreeString` at `0x1004451e4`
- `OLEAUT32!__imp_SysFreeString` at `0x10044521b`
- `OLEAUT32!__imp_SysFreeString` at `0x10044523e`
- `OLEAUT32!__imp_SysFreeString` at `0x1004451e4`
- `OLEAUT32!__imp_SysFreeString` at `0x10044521b`
- `OLEAUT32!__imp_SysFreeString` at `0x10044523e`
- `OLEAUT32!__imp_VariantClear` at `0x100445268`
- `OLEAUT32!__imp_VariantClear` at `0x100445268`

## string_xrefs

- `0x1004451f7`: `doc->createElement failed. hr=0x%x`
- `0x10044522a`: `spXMLDoc->selectSingleNode failed to get root node of [/SqlDumper] in configuration file. hr=0x%x`
- `0x100445186`: `"<%ls>%ls</%ls>" inserted to dumper config file successfully.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall DumperConfig::InsertXmlElement(
        _QWORD *a1,
        VARIANTARG *a2,
        const OLECHAR *a3,
        const OLECHAR *a4,
        wchar_t *Buffer,
        unsigned __int16 a6)
{
  unsigned __int8 v10; // bl
  OLECHAR *v11; // rsi
  int v12; // eax
  OLECHAR *v13; // rdi
  int v14; // eax
  OLECHAR *v15; // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  char v21; // [rsp+38h] [rbp-49h]
  __int64 v22; // [rsp+40h] [rbp-41h] BYREF
  __int64 v23; // [rsp+48h] [rbp-39h] BYREF
  BSTR v24; // [rsp+50h] [rbp-31h]
  BSTR bstrString; // [rsp+58h] [rbp-29h]
  __int64 v26; // [rsp+60h] [rbp-21h] BYREF
  BSTR v27; // [rsp+68h] [rbp-19h]
  __int64 v28; // [rsp+70h] [rbp-11h]
  __int128 v29; // [rsp+78h] [rbp-9h] BYREF
  IRecordInfo *pRecInfo; // [rsp+88h] [rbp+7h]

  v28 = -2;
  v10 = 0;
  v21 = 0;
  v23 = 0;
  v11 = SysAllocString(L"./SqlDumper");
  v27 = v11;
  if ( !v11 )
    ATL::AtlThrowImpl(-2147024882);
  v12 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(*(_QWORD *)*a1 + 296LL))(*a1, v11, &v23);
  if ( v12 >= 0 && v23 )
  {
    if ( a3 )
    {
      v13 = SysAllocString(a3);
      v24 = v13;
      if ( !v13 )
        ATL::AtlThrowImpl(-2147024882);
    }
    else
    {
      v13 = 0;
      v24 = 0;
    }
    v22 = 0;
    v14 = (*(__int64 (__fastcall **)(_QWORD, OLECHAR *, __int64 *))(*(_QWORD *)*a1 + 376LL))(*a1, v13, &v22);
    if ( v14 >= 0 && v22 )
    {
      if ( a4 )
      {
        v15 = SysAllocString(a4);
        bstrString = v15;
        if ( !v15 )
          ATL::AtlThrowImpl(-2147024882);
      }
      else
      {
        v15 = 0;
        bstrString = 0;
      }
      v16 = (*(__int64 (__fastcall **)(__int64, OLECHAR *))(*(_QWORD *)v22 + 216LL))(v22, v15);
      if ( v16 < 0 || v16 == 1 )
      {
        StringCchPrintfW(Buffer, a6, L"child->put_text failed. hr=0x%x", (unsigned int)v16);
      }
      else
      {
        v26 = 0;
        v17 = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v23 + 168LL))(v23, v22, &v26);
        if ( v17 >= 0 && v26 )
        {
          v18 = *a1;
          v29 = *(_OWORD *)&a2->vt;
          pRecInfo = a2->pRecInfo;
          v19 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v18 + 528LL))(v18, &v29);
          _mm_lfence();
          if ( v19 >= 0 )
          {
            v21 = 1;
            StringCchPrintfW(Buffer, a6, L"\"<%ls>%ls</%ls>\" inserted to dumper config file successfully.", a3, a4, a3);
          }
          else
          {
            StringCchPrintfW(Buffer, a6, L"doc->save failed.hr=0x%x", (unsigned int)v19);
          }
          v11 = v27;
          v13 = v24;
          v15 = bstrString;
        }
        else
        {
          StringCchPrintfW(Buffer, a6, L"root->appendChild failed. hr=0x%x", (unsigned int)v17);
        }
        if ( v26 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
      }
      SysFreeString(v15);
      v10 = v21;
    }
    else
    {
      StringCchPrintfW(Buffer, a6, L"doc->createElement failed. hr=0x%x", (unsigned int)v14);
    }
    if ( v22 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    SysFreeString(v13);
  }
  else
  {
    StringCchPrintfW(
      Buffer,
      a6,
      L"spXMLDoc->selectSingleNode failed to get root node of [/SqlDumper] in configuration file. hr=0x%x",
      (unsigned int)v12);
  }
  SysFreeString(v11);
  if ( v23 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
  if ( *a1 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a1 + 16LL))(*a1);
  VariantClear(a2);
  return v10;
}

```

## disassembly

```asm
0x100444fc0  mov     rax, rsp
0x100444fc3  mov     [rax+10h], rdx
0x100444fc7  mov     [rax+8], rcx
0x100444fcb  push    rbp
0x100444fcc  push    rsi
0x100444fcd  push    rdi
0x100444fce  push    r12
0x100444fd0  push    r13
0x100444fd2  push    r14
0x100444fd4  push    r15
0x100444fd6  lea     rbp, [rax-4Fh]
0x100444fda  sub     rsp, 90h
0x100444fe1  mov     [rbp+47h+var_58], 0FFFFFFFFFFFFFFFEh
0x100444fe9  mov     [rax+18h], rbx
0x100444fed  mov     r15, r9
0x100444ff0  mov     r14, r8
0x100444ff3  mov     r13, rdx
0x100444ff6  mov     r12, rcx
0x100444ff9  xor     bl, bl
0x100444ffb  mov     [rbp+47h+var_90], bl
0x100444ffe  mov     [rbp+47h+var_80], 0
0x100445006  lea     rcx, psz; "./SqlDumper"
0x10044500d  call    cs:__imp_SysAllocString
0x100445013  mov     rsi, rax
0x100445016  mov     [rbp+47h+var_60], rax
0x10044501a  test    rax, rax
0x10044501d  jz      loc_10044528C
0x100445023  mov     rcx, [r12]
0x100445027  mov     rax, [rcx]
0x10044502a  lea     r8, [rbp+47h+var_80]
0x10044502e  mov     rdx, rsi
0x100445031  call    qword ptr [rax+128h]
0x100445037  test    eax, eax
0x100445039  js      loc_100445223
0x10044503f  cmp     [rbp+47h+var_80], 0
0x100445044  jz      loc_100445223
0x10044504a  test    r14, r14
0x10044504d  jnz     loc_100445139
0x100445053  xor     edi, edi
0x100445055  mov     [rbp+47h+var_78], rdi
0x100445059  mov     [rbp+47h+var_88], 0
0x100445061  mov     rcx, [r12]
0x100445065  mov     rax, [rcx]
0x100445068  lea     r8, [rbp+47h+var_88]
0x10044506c  mov     rdx, rdi
0x10044506f  call    qword ptr [rax+178h]
0x100445075  test    eax, eax
0x100445077  js      loc_1004451F0
0x10044507d  cmp     [rbp+47h+var_88], 0
0x100445082  jz      loc_1004451F0
0x100445088  test    r15, r15
0x10044508b  jnz     loc_100445157
0x100445091  xor     ebx, ebx
0x100445093  mov     [rbp+47h+bstrString], rbx
0x100445097  mov     rcx, [rbp+47h+var_88]
0x10044509b  mov     rax, [rcx]
0x10044509e  mov     rdx, rbx
0x1004450a1  call    qword ptr [rax+0D8h]
0x1004450a7  test    eax, eax
0x1004450a9  js      loc_1004451C9
0x1004450af  cmp     eax, 1
0x1004450b2  jz      loc_1004451C9
0x1004450b8  mov     [rbp+47h+var_68], 0
0x1004450c0  mov     rcx, [rbp+47h+var_80]
0x1004450c4  mov     rax, [rcx]
0x1004450c7  lea     r8, [rbp+47h+var_68]
0x1004450cb  mov     rdx, [rbp+47h+var_88]
0x1004450cf  call    qword ptr [rax+0A8h]
0x1004450d5  test    eax, eax
0x1004450d7  js      loc_1004451A0
0x1004450dd  cmp     [rbp+47h+var_68], 0
0x1004450e2  jz      loc_1004451A0
0x1004450e8  mov     rcx, [r12]
0x1004450ec  movups  xmm0, xmmword ptr [r13+0]
0x1004450f1  movaps  [rbp+47h+var_50], xmm0
0x1004450f5  movsd   xmm1, qword ptr [r13+10h]
0x1004450fb  movsd   [rbp+47h+var_40], xmm1
0x100445100  mov     rax, [rcx]
0x100445103  lea     rdx, [rbp+47h+var_50]
0x100445107  call    qword ptr [rax+210h]
0x10044510d  movzx   edx, [rbp+47h+arg_28]; unsigned __int64
0x100445111  lfence
0x100445114  mov     rcx, [rbp+47h+Buffer]; Buffer
0x100445118  test    eax, eax
0x10044511a  jns     short loc_100445175
0x10044511c  mov     r9d, eax
0x10044511f  lea     r8, aDocSaveFailedH_0; "doc->save failed.hr=0x%x"
0x100445126  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044512b  mov     rsi, [rbp+47h+var_60]
0x10044512f  mov     rdi, [rbp+47h+var_78]
0x100445133  mov     rbx, [rbp+47h+bstrString]
0x100445137  jmp     short loc_1004451B8
0x100445139  mov     rcx, r14; psz
0x10044513c  call    cs:__imp_SysAllocString
0x100445142  mov     rdi, rax
0x100445145  mov     [rbp+47h+var_78], rax
0x100445149  test    rax, rax
0x10044514c  jz      loc_10044529B
0x100445152  jmp     loc_100445059
0x100445157  mov     rcx, r15; psz
0x10044515a  call    cs:__imp_SysAllocString
0x100445160  mov     rbx, rax
0x100445163  mov     [rbp+47h+bstrString], rax
0x100445167  test    rax, rax
0x10044516a  jz      loc_1004452A9
0x100445170  jmp     loc_100445097
0x100445175  mov     [rbp+47h+var_90], 1
0x100445179  mov     [rsp+28h], r14
0x10044517e  mov     [rsp+0C0h+var_A0], r15
0x100445183  mov     r9, r14
0x100445186  lea     r8, aLsLsLsInserted; "\"<%ls>%ls</%ls>\" inserted to dumper c"...
0x10044518d  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100445192  mov     rsi, [rbp+47h+var_60]
0x100445196  mov     rdi, [rbp+47h+var_78]
0x10044519a  mov     rbx, [rbp+47h+bstrString]
0x10044519e  jmp     short loc_1004451B8
0x1004451a0  movzx   edx, [rbp+47h+arg_28]; unsigned __int64
0x1004451a4  mov     r9d, eax
0x1004451a7  lea     r8, aRootAppendchil; "root->appendChild failed. hr=0x%x"
0x1004451ae  mov     rcx, [rbp+47h+Buffer]; Buffer
0x1004451b2  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004451b7  nop
0x1004451b8  mov     rcx, [rbp+47h+var_68]
0x1004451bc  test    rcx, rcx
0x1004451bf  jz      short loc_1004451E1
0x1004451c1  mov     rax, [rcx]
0x1004451c4  call    qword ptr [rax+10h]
0x1004451c7  jmp     short loc_1004451E1
0x1004451c9  movzx   edx, [rbp+47h+arg_28]; unsigned __int64
0x1004451cd  mov     r9d, eax
0x1004451d0  lea     r8, aChildPutTextFa; "child->put_text failed. hr=0x%x"
0x1004451d7  mov     rcx, [rbp+47h+Buffer]; Buffer
0x1004451db  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1004451e0  nop
0x1004451e1  mov     rcx, rbx; bstrString
0x1004451e4  call    cs:__imp_SysFreeString
0x1004451ea  movzx   ebx, [rbp+47h+var_90]
0x1004451ee  jmp     short loc_100445208
0x1004451f0  movzx   edx, [rbp+47h+arg_28]; unsigned __int64
0x1004451f4  mov     r9d, eax
0x1004451f7  lea     r8, aDocCreateeleme; "doc->createElement failed. hr=0x%x"
0x1004451fe  mov     rcx, [rbp+47h+Buffer]; Buffer
0x100445202  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x100445207  nop
0x100445208  mov     rcx, [rbp+47h+var_88]
0x10044520c  test    rcx, rcx
0x10044520f  jz      short loc_100445218
0x100445211  mov     rax, [rcx]
0x100445214  call    qword ptr [rax+10h]
0x100445217  nop
0x100445218  mov     rcx, rdi; bstrString
0x10044521b  call    cs:__imp_SysFreeString
0x100445221  jmp     short loc_10044523B
0x100445223  movzx   edx, [rbp+47h+arg_28]; unsigned __int64
0x100445227  mov     r9d, eax
0x10044522a  lea     r8, aSpxmldocSelect; "spXMLDoc->selectSingleNode failed to ge"...
0x100445231  mov     rcx, [rbp+47h+Buffer]; Buffer
0x100445235  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x10044523a  nop
0x10044523b  mov     rcx, rsi; bstrString
0x10044523e  call    cs:__imp_SysFreeString
0x100445244  nop
0x100445245  mov     rcx, [rbp+47h+var_80]
0x100445249  test    rcx, rcx
0x10044524c  jz      short loc_100445255
0x10044524e  mov     rax, [rcx]
0x100445251  call    qword ptr [rax+10h]
0x100445254  nop
0x100445255  mov     rcx, [r12]
0x100445259  test    rcx, rcx
0x10044525c  jz      short loc_100445265
0x10044525e  mov     rdx, [rcx]
0x100445261  call    qword ptr [rdx+10h]
0x100445264  nop
0x100445265  mov     rcx, r13; pvarg
0x100445268  call    cs:__imp_VariantClear
0x10044526e  movzx   eax, bl
0x100445271  mov     rbx, [rsp+0C0h+arg_10]
0x100445279  add     rsp, 90h
0x100445280  pop     r15
0x100445282  pop     r14
0x100445284  pop     r13
0x100445286  pop     r12
0x100445288  pop     rdi
0x100445289  pop     rsi
0x10044528a  pop     rbp
0x10044528b  retn
0x10044528c  mov     ecx, 8007000Eh; int
0x100445291  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x100445297  jmp     short loc_10044529A
0x10044529a  nop
0x10044529b  mov     ecx, 8007000Eh; int
0x1004452a0  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x1004452a6  jmp     short $+2
0x1004452a8  nop
0x1004452a9  mov     ecx, 8007000Eh; int
0x1004452ae  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
