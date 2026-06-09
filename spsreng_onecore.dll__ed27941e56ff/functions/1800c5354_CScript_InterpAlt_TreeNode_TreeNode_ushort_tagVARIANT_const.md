# CScript::InterpAlt(TreeNode * *,TreeNode * *,ushort,tagVARIANT const *)

- ea: `0x1800c5354`
- end: `0x1800c598d`
- name: `?InterpAlt@CScript@@QEAAJPEAPEAUTreeNode@@0GPEBUtagVARIANT@@@Z`
- size: `1593`
- prototype: `__int64 __fastcall(CScript *__hidden this, struct TreeNode **, struct TreeNode **, unsigned __int16, const struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800c5994`

## callees

- `0x180002db8`
- `0x180003650`
- `0x1800040b8`
- `0x1800042d8`
- `0x180004306`
- `0x1800b36c4`
- `0x1800b3b24`
- `0x1800b4b20`
- `0x1800b8cc8`
- `0x1800c5354`
- `0x180102010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800c5837`
- `api-ms-win-crt-private-l1-1-0!_o__wcsdup` at `0x1800c5837`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800c56b5`
- `api-ms-win-crt-private-l1-1-0!_o__wtol` at `0x1800c56b5`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c547b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5512`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c586a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c58e0`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c547b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c5512`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c586a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800c58e0`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5429`
- `OLEAUT32!__imp_VariantInit` at `0x1800c54c4`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5636`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5712`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5429`
- `OLEAUT32!__imp_VariantInit` at `0x1800c54c4`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5636`
- `OLEAUT32!__imp_VariantInit` at `0x1800c5712`
- `OLEAUT32!__imp_VariantClear` at `0x1800c589c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c58ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5937`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5942`
- `OLEAUT32!__imp_VariantClear` at `0x1800c589c`
- `OLEAUT32!__imp_VariantClear` at `0x1800c58ee`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5937`
- `OLEAUT32!__imp_VariantClear` at `0x1800c5942`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800c5823`
- `OLEAUT32!__imp_VariantChangeType` at `0x1800c5823`

## string_xrefs

- `0x1800c544e`: `cToken`
- `0x1800c54e3`: `rgToken`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CScript::InterpAlt(
        OLECHAR *this,
        struct TreeNode **a2,
        struct TreeNode **a3,
        __int16 a4,
        const struct tagVARIANT *a5)
{
  struct TreeNode **v6; // r12
  struct TreeNode *v7; // rsi
  OLECHAR *v8; // rax
  int v9; // ebx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, _QWORD, __int64, unsigned int *); // rbx
  _QWORD *v12; // rax
  bool v13; // sf
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64, unsigned int *); // rbx
  _QWORD *v16; // rax
  unsigned int uiVal; // eax
  unsigned __int64 v18; // rax
  unsigned __int64 v19; // kr00_8
  void *v20; // rax
  __int64 v21; // rdx
  HRESULT v22; // edi
  __int64 i; // rcx
  bool v24; // sf
  __int64 v25; // rdx
  unsigned __int16 v26; // r15
  __int64 v27; // rcx
  TreeNode *v28; // rax
  TreeNode *v29; // r14
  unsigned int v30; // edx
  __int64 v31; // rax
  unsigned int v32; // edx
  __int64 v33; // rdx
  __int64 v35; // [rsp+58h] [rbp-91h] BYREF
  __int64 v36; // [rsp+60h] [rbp-89h] BYREF
  __int64 v37; // [rsp+68h] [rbp-81h] BYREF
  wchar_t *String1; // [rsp+70h] [rbp-79h] BYREF
  BSTR v39; // [rsp+78h] [rbp-71h] BYREF
  __int128 v40; // [rsp+80h] [rbp-69h] BYREF
  __int64 v41; // [rsp+90h] [rbp-59h]
  VARIANTARG pvargDest; // [rsp+98h] [rbp-51h] BYREF
  VARIANTARG v43; // [rsp+B0h] [rbp-39h] BYREF
  VARIANTARG v44; // [rsp+C8h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+E0h] [rbp-9h] BYREF
  TreeNode *v46; // [rsp+F8h] [rbp+Fh]
  BSTR bstrString; // [rsp+148h] [rbp+5Fh] BYREF
  struct TreeNode **v48; // [rsp+150h] [rbp+67h]
  unsigned int v49; // [rsp+160h] [rbp+77h] BYREF

  LOWORD(v49) = a4;
  v48 = a2;
  bstrString = this;
  v6 = a2;
  v7 = *a2;
  if ( !*a2 )
  {
    v8 = (OLECHAR *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
    v7 = (struct TreeNode *)v8;
    bstrString = v8;
    if ( !v8 )
      return (unsigned int)-2147024882;
    *(_QWORD *)v8 = -1;
    v8[4] = 0;
    *((_DWORD *)v8 + 3) = 3;
    *((_DWORD *)v8 + 4) = -65536;
    *((_QWORD *)v8 + 3) = 0;
    *((_DWORD *)v8 + 8) = 3;
    v8[18] = 0;
    *((_QWORD *)v8 + 5) = 0;
    *((_QWORD *)v8 + 6) = 0;
    v8[28] = 1;
    *((_DWORD *)v8 + 15) = 0;
  }
  v9 = 0;
  if ( a5->vt != 9 )
  {
LABEL_58:
    *v6 = v7;
    return (unsigned int)v9;
  }
  v40 = 0;
  v41 = 0;
  v37 = 0;
  v9 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))a5->llVal)(
         a5->llVal,
         &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9,
         &v37);
  VariantInit(&pvarg);
  if ( !v9 )
  {
    v49 = 0;
    v10 = v37;
    v11 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned int *))(*(_QWORD *)v37 + 56LL);
    v12 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"cToken");
    v9 = v11(v10, *v12, 1, &v49);
    SysFreeString(bstrString);
    if ( !v9 )
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v37 + 64LL))(
             v37,
             v49,
             1024,
             2,
             &v40,
             &pvarg,
             0,
             0);
  }
  VariantInit(&v44);
  v13 = v9 < 0;
  if ( !v9 )
  {
    v49 = 0;
    v14 = v37;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64, unsigned int *))(*(_QWORD *)v37 + 56LL);
    v16 = (_QWORD *)ATL::CComBSTR::CComBSTR((ATL::CComBSTR *)&bstrString, L"rgToken");
    v9 = v15(v14, *v16, 1, &v49);
    SysFreeString(bstrString);
    v13 = v9 < 0;
    if ( !v9 )
    {
      v9 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v37 + 64LL))(
             v37,
             v49,
             1024,
             2,
             &v40,
             &v44,
             0,
             0);
      v13 = v9 < 0;
    }
  }
  if ( !v13 )
  {
    uiVal = pvarg.uiVal;
    if ( pvarg.iVal > 0 )
    {
      *((_WORD *)v7 + 18) = pvarg.iVal;
      *((_DWORD *)v7 + 8) = 0;
      v19 = uiVal;
      v18 = 8LL * uiVal;
      if ( !is_mul_ok(v19, 8u) )
        v18 = -1;
      v20 = operator new[](v18, (const struct std::nothrow_t *)&std::nothrow);
      *((_QWORD *)v7 + 5) = v20;
      if ( !v20 )
      {
        v9 = -2147024882;
LABEL_53:
        TreeNode::ClearOutNodes(v7);
        goto LABEL_54;
      }
      memset_0(v20, 0, 8LL * *((unsigned __int16 *)v7 + 18));
      v35 = 0;
      v22 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v44.llVal)(
              v44.llVal,
              &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9,
              &v35);
      LODWORD(bstrString) = -1;
      if ( !v22 )
      {
        i = v35;
        if ( !v35 )
          goto LABEL_20;
        v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, BSTR *))(*(_QWORD *)v35 + 104LL))(
                v35,
                2,
                0xFFFFFFFFLL,
                &bstrString);
        if ( !v22 )
        {
          for ( i = v35; ; i = v35 )
          {
LABEL_20:
            v39 = 0;
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, BSTR *))(*(_QWORD *)i + 96LL))(
                    i,
                    (unsigned int)bstrString,
                    &v39);
            VariantInit(&v43);
            if ( !v22 )
              v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v35 + 64LL))(
                      v35,
                      (unsigned int)bstrString,
                      1024,
                      2,
                      &v40,
                      &v43,
                      0,
                      0);
            if ( v43.vt == 9 )
            {
              v24 = v22 < 0;
              if ( v22 )
                goto LABEL_44;
              v36 = 0;
              v22 = (**(__int64 (__fastcall ***)(LONGLONG, GUID *, __int64 *))v43.llVal)(
                      v43.llVal,
                      &GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9,
                      &v36);
              v26 = _o__wtol(v39);
              v49 = -1;
              if ( !v22 )
              {
                v22 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, unsigned int *))(*(_QWORD *)v36 + 104LL))(
                        v36,
                        2,
                        -1,
                        &v49);
                while ( !v22 )
                {
                  String1 = 0;
                  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, wchar_t **))(*(_QWORD *)v36 + 96LL))(
                          v36,
                          v49,
                          &String1);
                  VariantInit(&pvargDest);
                  if ( v22 < 0 )
                    goto LABEL_37;
                  v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, __int64, __int128 *, VARIANTARG *, _QWORD, _QWORD))(*(_QWORD *)v36 + 64LL))(
                          v36,
                          v49,
                          1024,
                          2,
                          &v40,
                          &pvargDest,
                          0,
                          0);
                  if ( v22 < 0 )
                    goto LABEL_37;
                  if ( !wcscmp_0(String1, L"Latt") )
                  {
                    *(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL * v26) = a3[pvargDest.iVal];
                    v27 = *(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL * v26);
                    ++*(_WORD *)(v27 + 56);
                  }
                  else
                  {
                    v28 = (TreeNode *)operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
                    v29 = v28;
                    v46 = v28;
                    if ( !v28 )
                      goto LABEL_36;
                    *(_QWORD *)v28 = -1;
                    *((_WORD *)v28 + 4) = 0;
                    *((_DWORD *)v28 + 3) = 3;
                    *((_DWORD *)v28 + 4) = -65536;
                    *((_QWORD *)v28 + 3) = 0;
                    *((_DWORD *)v28 + 8) = 3;
                    *((_WORD *)v28 + 18) = 0;
                    *((_QWORD *)v28 + 5) = 0;
                    *((_QWORD *)v28 + 6) = 0;
                    *((_WORD *)v28 + 28) = 1;
                    *((_DWORD *)v28 + 15) = 0;
                    *((_DWORD *)v28 + 8) = 2;
                    v22 = VariantChangeType(&pvargDest, &pvargDest, 0, 8u);
                    if ( v22 < 0 )
                    {
                      TreeNode::`scalar deleting destructor'(v29, v30);
                      goto LABEL_37;
                    }
                    v31 = _o__wcsdup(pvargDest.llVal);
                    *((_QWORD *)v29 + 5) = v31;
                    if ( !v31 )
                    {
                      TreeNode::`scalar deleting destructor'(v29, v32);
LABEL_36:
                      v22 = -2147024882;
                      goto LABEL_37;
                    }
                    *(_QWORD *)(*((_QWORD *)v7 + 5) + 8LL * v26) = v29;
                  }
LABEL_37:
                  if ( String1 )
                  {
                    SysFreeString(String1);
                    String1 = 0;
                  }
                  if ( v22 >= 0 )
                    v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, unsigned int *))(*(_QWORD *)v36 + 104LL))(
                            v36,
                            2,
                            v49,
                            &v49);
                  VariantClear(&pvargDest);
                }
              }
              ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v36, v25);
            }
            v24 = v22 < 0;
LABEL_44:
            if ( !v24 )
              v22 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, BSTR *))(*(_QWORD *)v35 + 104LL))(
                      v35,
                      2,
                      (unsigned int)bstrString,
                      &bstrString);
            SysFreeString(v39);
            v39 = 0;
            VariantClear(&v43);
            if ( v22 )
            {
              v6 = v48;
              break;
            }
          }
        }
      }
      v9 = v22;
      ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v35, v21);
      if ( v22 < 0 )
        goto LABEL_53;
    }
  }
LABEL_54:
  VariantClear(&v44);
  VariantClear(&pvarg);
  ATL::CComPtrBase<ISpObjectToken>::~CComPtrBase<ISpObjectToken>(&v37, v33);
  if ( v9 >= 0 )
    goto LABEL_58;
  if ( v7 && !*v6 )
    TreeNode::Release(v7);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x1800c5354  mov     rax, rsp
0x1800c5357  mov     [rax+18h], rbx
0x1800c535b  mov     [rax+20h], r9w
0x1800c5360  mov     [rax+10h], rdx
0x1800c5364  mov     [rax+8], rcx
0x1800c5368  push    rbp
0x1800c5369  push    rsi
0x1800c536a  push    rdi
0x1800c536b  push    r12
0x1800c536d  push    r13
0x1800c536f  push    r14
0x1800c5371  push    r15
0x1800c5373  lea     rbp, [rax-57h]
0x1800c5377  sub     rsp, 100h
0x1800c537e  mov     r13, r8
0x1800c5381  mov     r12, rdx
0x1800c5384  mov     rsi, [rdx]
0x1800c5387  xor     r14d, r14d
0x1800c538a  test    rsi, rsi
0x1800c538d  jnz     short loc_1800C53E6
0x1800c538f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c5396  lea     ecx, [rsi+40h]; unsigned __int64
0x1800c5399  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c539e  mov     rsi, rax
0x1800c53a1  mov     [rbp+4Fh+bstrString], rax
0x1800c53a5  test    rax, rax
0x1800c53a8  jz      loc_1800C57A7
0x1800c53ae  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800c53b5  mov     [rax+8], r14w
0x1800c53ba  lea     edx, [r14+3]
0x1800c53be  mov     [rax+0Ch], edx
0x1800c53c1  mov     dword ptr [rax+10h], 0FFFF0000h
0x1800c53c8  mov     [rax+18h], r14
0x1800c53cc  mov     [rax+20h], edx
0x1800c53cf  mov     [rax+24h], r14w
0x1800c53d4  mov     [rax+28h], r14
0x1800c53d8  mov     [rax+30h], r14
0x1800c53dc  mov     word ptr [rax+38h], 1
0x1800c53e2  mov     [rax+3Ch], r14d
0x1800c53e6  mov     ebx, r14d
0x1800c53e9  mov     rcx, [rbp+4Fh+arg_20]
0x1800c53ed  cmp     word ptr [rcx], 9
0x1800c53f1  jnz     loc_1800C596C
0x1800c53f7  xorps   xmm0, xmm0
0x1800c53fa  movdqu  [rbp+4Fh+var_B8], xmm0
0x1800c53ff  mov     [rbp+4Fh+var_A8], r14
0x1800c5403  mov     [rsp+130h+var_D0], r14
0x1800c5408  mov     rcx, [rcx+8]
0x1800c540c  mov     rax, [rcx]
0x1800c540f  lea     r8, [rsp+130h+var_D0]
0x1800c5414  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x1800c541b  mov     rax, [rax]
0x1800c541e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5423  mov     ebx, eax
0x1800c5425  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x1800c5429  call    cs:__imp_VariantInit
0x1800c542f  nop
0x1800c5430  mov     r15d, 2
0x1800c5436  test    ebx, ebx
0x1800c5438  jnz     loc_1800C54C0
0x1800c543e  mov     [rbp+4Fh+arg_18], r14d
0x1800c5442  mov     rdi, [rsp+130h+var_D0]
0x1800c5447  mov     rax, [rdi]
0x1800c544a  mov     rbx, [rax+38h]
0x1800c544e  lea     rdx, aCtoken; "cToken"
0x1800c5455  lea     rcx, [rbp+4Fh+bstrString]; this
0x1800c5459  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800c545e  nop
0x1800c545f  lea     r9, [rbp+4Fh+arg_18]
0x1800c5463  lea     r8d, [r15-1]
0x1800c5467  mov     rdx, [rax]
0x1800c546a  mov     rcx, rdi
0x1800c546d  mov     rax, rbx
0x1800c5470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5475  mov     ebx, eax
0x1800c5477  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800c547b  call    cs:__imp_SysFreeString
0x1800c5481  test    ebx, ebx
0x1800c5483  jnz     short loc_1800C54C0
0x1800c5485  mov     rcx, [rsp+130h+var_D0]
0x1800c548a  mov     rax, [rcx]
0x1800c548d  mov     r9d, r15d
0x1800c5490  mov     [rsp+38h], r14
0x1800c5495  mov     [rsp+130h+var_100], r14
0x1800c549a  lea     rdx, [rbp+4Fh+pvarg]
0x1800c549e  mov     [rsp+130h+var_108], rdx
0x1800c54a3  lea     rdx, [rbp+4Fh+var_B8]
0x1800c54a7  mov     [rsp+130h+var_110], rdx
0x1800c54ac  mov     r8d, 400h
0x1800c54b2  mov     edx, [rbp+4Fh+arg_18]
0x1800c54b5  mov     rax, [rax+40h]
0x1800c54b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c54be  mov     ebx, eax
0x1800c54c0  lea     rcx, [rbp+4Fh+var_70]; pvarg
0x1800c54c4  call    cs:__imp_VariantInit
0x1800c54ca  nop
0x1800c54cb  test    ebx, ebx
0x1800c54cd  jnz     loc_1800C5559
0x1800c54d3  mov     [rbp+4Fh+arg_18], r14d
0x1800c54d7  mov     rdi, [rsp+130h+var_D0]
0x1800c54dc  mov     rax, [rdi]
0x1800c54df  mov     rbx, [rax+38h]
0x1800c54e3  lea     rdx, aRgtoken; "rgToken"
0x1800c54ea  lea     rcx, [rbp+4Fh+bstrString]; this
0x1800c54ee  call    ??0CComBSTR@ATL@@QEAA@PEBG@Z; ATL::CComBSTR::CComBSTR(ushort const *)
0x1800c54f3  nop
0x1800c54f4  lea     r9, [rbp+4Fh+arg_18]
0x1800c54f8  mov     r8d, 1
0x1800c54fe  mov     rdx, [rax]
0x1800c5501  mov     rcx, rdi
0x1800c5504  mov     rax, rbx
0x1800c5507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c550c  mov     ebx, eax
0x1800c550e  mov     rcx, [rbp+4Fh+bstrString]; bstrString
0x1800c5512  call    cs:__imp_SysFreeString
0x1800c5518  test    ebx, ebx
0x1800c551a  jnz     short loc_1800C5559
0x1800c551c  mov     rcx, [rsp+130h+var_D0]
0x1800c5521  mov     rax, [rcx]
0x1800c5524  mov     r9d, r15d
0x1800c5527  mov     [rsp+38h], r14
0x1800c552c  mov     [rsp+130h+var_100], r14
0x1800c5531  lea     rdx, [rbp+4Fh+var_70]
0x1800c5535  mov     [rsp+130h+var_108], rdx
0x1800c553a  lea     rdx, [rbp+4Fh+var_B8]
0x1800c553e  mov     [rsp+130h+var_110], rdx
0x1800c5543  mov     r8d, 400h
0x1800c5549  mov     edx, [rbp+4Fh+arg_18]
0x1800c554c  mov     rax, [rax+40h]
0x1800c5550  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5555  mov     ebx, eax
0x1800c5557  test    eax, eax
0x1800c5559  js      loc_1800C5933
0x1800c555f  movzx   eax, word ptr [rbp+4Fh+pvarg+8]
0x1800c5563  test    ax, ax
0x1800c5566  jle     loc_1800C5933
0x1800c556c  mov     ecx, eax
0x1800c556e  mov     [rsi+24h], cx
0x1800c5572  mov     [rsi+20h], r14d
0x1800c5576  mov     eax, 8
0x1800c557b  mul     rcx
0x1800c557e  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800c5585  cmovb   rax, rbx
0x1800c5589  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c5590  mov     rcx, rax; unsigned __int64
0x1800c5593  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1800c5598  mov     [rsi+28h], rax
0x1800c559c  test    rax, rax
0x1800c559f  jz      loc_1800C5925
0x1800c55a5  movzx   r8d, word ptr [rsi+24h]
0x1800c55aa  shl     r8, 3; Size
0x1800c55ae  xor     edx, edx; Val
0x1800c55b0  mov     rcx, rax; void *
0x1800c55b3  call    memset_0
0x1800c55b8  mov     [rsp+130h+var_E0], r14
0x1800c55bd  mov     rcx, qword ptr [rbp+4Fh+var_70+8]
0x1800c55c1  mov     rax, [rcx]
0x1800c55c4  lea     r8, [rsp+130h+var_E0]
0x1800c55c9  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x1800c55d0  mov     rax, [rax]
0x1800c55d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c55d8  mov     edi, eax
0x1800c55da  mov     dword ptr [rbp+4Fh+bstrString], ebx
0x1800c55dd  test    eax, eax
0x1800c55df  jnz     loc_1800C5913
0x1800c55e5  mov     rcx, [rsp+130h+var_E0]
0x1800c55ea  test    rcx, rcx
0x1800c55ed  jz      short loc_1800C5614
0x1800c55ef  mov     rax, [rcx]
0x1800c55f2  lea     r9, [rbp+4Fh+bstrString]
0x1800c55f6  mov     r8d, ebx
0x1800c55f9  mov     edx, r15d
0x1800c55fc  mov     rax, [rax+68h]
0x1800c5600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5605  mov     edi, eax
0x1800c5607  test    eax, eax
0x1800c5609  jnz     loc_1800C5913
0x1800c560f  mov     rcx, [rsp+130h+var_E0]
0x1800c5614  mov     ebx, 8007000Eh
0x1800c5619  mov     [rbp+4Fh+var_C0], r14
0x1800c561d  mov     rax, [rcx]
0x1800c5620  lea     r8, [rbp+4Fh+var_C0]
0x1800c5624  mov     edx, dword ptr [rbp+4Fh+bstrString]
0x1800c5627  mov     rax, [rax+60h]
0x1800c562b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c5630  mov     edi, eax
0x1800c5632  lea     rcx, [rbp+4Fh+var_88]; pvarg
0x1800c5636  call    cs:__imp_VariantInit
0x1800c563c  nop
0x1800c563d  test    edi, edi
0x1800c563f  jnz     short loc_1800C567C
0x1800c5641  mov     rcx, [rsp+130h+var_E0]
0x1800c5646  mov     rax, [rcx]
0x1800c5649  mov     r9d, r15d
0x1800c564c  mov     [rsp+38h], r14
0x1800c5651  mov     [rsp+130h+var_100], r14
0x1800c5656  lea     rdx, [rbp+4Fh+var_88]
0x1800c565a  mov     [rsp+130h+var_108], rdx
0x1800c565f  lea     rdx, [rbp+4Fh+var_B8]
0x1800c5663  mov     [rsp+130h+var_110], rdx
0x1800c5668  mov     r8d, 400h
0x1800c566e  mov     edx, dword ptr [rbp+4Fh+bstrString]
0x1800c5671  mov     rax, [rax+40h]
0x1800c5675  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c567a  mov     edi, eax
0x1800c567c  cmp     word ptr [rbp+4Fh+var_88], 9
0x1800c5681  jnz     loc_1800C58BA
0x1800c5687  test    edi, edi
0x1800c5689  jnz     loc_1800C58BC
0x1800c568f  mov     [rsp+130h+var_D8], r14
0x1800c5694  mov     rcx, qword ptr [rbp+4Fh+var_88+8]
0x1800c5698  mov     rax, [rcx]
0x1800c569b  lea     r8, [rsp+130h+var_D8]
0x1800c56a0  lea     rdx, _GUID_a6ef9860_c720_11d0_9337_00a0c90dcaa9
0x1800c56a7  mov     rax, [rax]
0x1800c56aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c56af  mov     edi, eax
0x1800c56b1  mov     rcx, [rbp+4Fh+var_C0]
0x1800c56b5  call    cs:__imp__o__wtol
0x1800c56bb  mov     r15d, eax
0x1800c56be  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800c56c2  mov     [rbp+4Fh+arg_18], r8d
0x1800c56c6  test    edi, edi
0x1800c56c8  jnz     loc_1800C58AA
0x1800c56ce  mov     rcx, [rsp+130h+var_D8]
0x1800c56d3  mov     rdx, [rcx]
0x1800c56d6  mov     rax, [rdx+68h]
0x1800c56da  lea     r9, [rbp+4Fh+arg_18]
0x1800c56de  lea     edx, [rdi+2]
0x1800c56e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c56e6  mov     edi, eax
0x1800c56e8  test    eax, eax
0x1800c56ea  jnz     loc_1800C58AA
0x1800c56f0  mov     [rbp+4Fh+String1], r14
0x1800c56f4  mov     rcx, [rsp+130h+var_D8]
0x1800c56f9  mov     rax, [rcx]
0x1800c56fc  lea     r8, [rbp+4Fh+String1]
0x1800c5700  mov     edx, [rbp+4Fh+arg_18]
0x1800c5703  mov     rax, [rax+60h]
0x1800c5707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c570c  mov     edi, eax
0x1800c570e  lea     rcx, [rbp+4Fh+pvargDest]; pvarg
0x1800c5712  call    cs:__imp_VariantInit
0x1800c5718  nop
0x1800c5719  test    edi, edi
0x1800c571b  js      loc_1800C5861
0x1800c5721  mov     rcx, [rsp+130h+var_D8]
0x1800c5726  mov     rax, [rcx]
0x1800c5729  mov     r9d, 2
0x1800c572f  mov     [rsp+38h], r14
0x1800c5734  mov     [rsp+130h+var_100], r14
0x1800c5739  lea     rdx, [rbp+4Fh+pvargDest]
0x1800c573d  mov     [rsp+130h+var_108], rdx
0x1800c5742  lea     rdx, [rbp+4Fh+var_B8]
0x1800c5746  mov     [rsp+130h+var_110], rdx
0x1800c574b  mov     r8d, 400h
0x1800c5751  mov     edx, [rbp+4Fh+arg_18]
0x1800c5754  mov     rax, [rax+40h]
0x1800c5758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c575d  mov     edi, eax
0x1800c575f  test    eax, eax
0x1800c5761  js      loc_1800C5861
0x1800c5767  lea     rdx, aLatt; "Latt"
0x1800c576e  mov     rcx, [rbp+4Fh+String1]; String1
0x1800c5772  call    wcscmp_0
0x1800c5777  test    eax, eax
0x1800c5779  jnz     short loc_1800C57B1
0x1800c577b  movzx   edx, r15w
0x1800c577f  movsx   rax, word ptr [rbp+4Fh+pvargDest+8]
0x1800c5784  mov     rcx, [rsi+28h]
0x1800c5788  mov     rax, [r13+rax*8+0]
0x1800c578d  mov     [rcx+rdx*8], rax
0x1800c5791  mov     rax, [rsi+28h]
0x1800c5795  mov     rcx, [rax+rdx*8]
0x1800c5799  mov     eax, 1
0x1800c579e  add     [rcx+38h], ax
0x1800c57a2  jmp     loc_1800C5861
0x1800c57a7  mov     ebx, 8007000Eh
0x1800c57ac  jmp     loc_1800C5970
0x1800c57b1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800c57b8  mov     ecx, 40h ; '@'; unsigned __int64
0x1800c57bd  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800c57c2  mov     r14, rax
0x1800c57c5  mov     [rbp+4Fh+var_40], rax
0x1800c57c9  xor     ecx, ecx
0x1800c57cb  test    rax, rax
0x1800c57ce  jz      loc_1800C585C
0x1800c57d4  mov     qword ptr [rax], 0FFFFFFFFFFFFFFFFh
0x1800c57db  mov     [rax+8], cx
0x1800c57df  lea     edx, [rcx+3]
0x1800c57e2  mov     [rax+0Ch], edx
0x1800c57e5  mov     dword ptr [rax+10h], 0FFFF0000h
0x1800c57ec  mov     [rax+18h], rcx
0x1800c57f0  mov     [rax+20h], edx
0x1800c57f3  mov     [rax+24h], cx
0x1800c57f7  mov     [rax+28h], rcx
0x1800c57fb  mov     [rax+30h], rcx
0x1800c57ff  mov     word ptr [rax+38h], 1
0x1800c5805  mov     [rax+3Ch], ecx
0x1800c5808  test    rax, rax
  ... truncated ...
```
