# GetElementArray

- ea: `0x180039858`
- end: `0x180039b37`
- name: `GetElementArray`
- size: `735`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180039b40`

## callees

- `0x180003950`
- `0x18000c0b4`
- `0x180039704`
- `0x180039858`
- `0x180042114`
- `0x180042158`
- `0x180042630`
- `0x180049260`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800399f4`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800399f4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800399a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800399cd`
- `OLEAUT32!__imp_SysFreeString` at `0x180039a04`
- `OLEAUT32!__imp_SysFreeString` at `0x1800399a8`
- `OLEAUT32!__imp_SysFreeString` at `0x1800399cd`
- `OLEAUT32!__imp_SysFreeString` at `0x180039a04`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
__int64 __fastcall GetElementArray(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v6; // rbx
  int v7; // r12d
  int v8; // edi
  int v9; // r8d
  __int64 v10; // rdx
  signed int v11; // r13d
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  __int64 v13; // rbx
  int v14; // eax
  int (__fastcall *v15)(__int64, BSTR *); // rdi
  OLECHAR *v16; // rcx
  int v17; // eax
  int NextSlot; // eax
  int Element; // eax
  __int64 v20; // r9
  __int64 v21; // r9
  int lpString2; // [rsp+20h] [rbp-50h]
  unsigned __int8 *v24; // [rsp+30h] [rbp-40h] BYREF
  __int64 v25; // [rsp+38h] [rbp-38h]
  __int64 v26; // [rsp+40h] [rbp-30h]
  __int64 v27; // [rsp+48h] [rbp-28h] BYREF
  unsigned int v28; // [rsp+50h] [rbp-20h] BYREF
  BSTR bstrString; // [rsp+58h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  v26 = a4;
  v6 = a1;
  v25 = a1;
  v27 = 0;
  v24 = 0;
  v28 = 0;
  v7 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)a1 + 64LL))(a1, &v28);
  if ( v8 < 0 )
  {
    v10 = 1112;
    goto LABEL_37;
  }
  v8 = CDSArrayBuilder::put_MinimumSize((CDSArrayBuilder *)a3, v28, v9);
  if ( v8 < 0 )
  {
    v10 = 1113;
    goto LABEL_37;
  }
  v8 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v6 + 80LL))(v6);
  if ( v8 < 0 )
  {
    v10 = 1114;
LABEL_37:
    v21 = (unsigned int)v8;
LABEL_35:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
      (const char *)v21,
      lpString2);
    goto LABEL_39;
  }
  v11 = 0;
  if ( (int)v28 <= 0 )
    goto LABEL_32;
  do
  {
    v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v6 + 72LL);
    if ( v27 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      v27 = 0;
    }
    v8 = v12(v25, &v27);
    if ( v8 < 0 )
    {
      v10 = 1122;
      goto LABEL_37;
    }
    v13 = v27;
    if ( !v27 )
      goto LABEL_40;
    if ( *(_DWORD *)(a2 + 24) == 22 )
    {
      LODWORD(bstrString) = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 80LL))(v27, &bstrString);
      if ( v14 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x468,
          (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
          (const char *)(unsigned int)v14,
          lpString2);
      if ( (_DWORD)bstrString != 1 )
        goto LABEL_30;
    }
    else
    {
      bstrString = 0;
      v15 = *(int (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v27 + 56LL);
      SysFreeString(0);
      bstrString = 0;
      if ( v15(v13, &bstrString) < 0 )
      {
        v16 = bstrString;
LABEL_19:
        SysFreeString(v16);
        goto LABEL_30;
      }
      v17 = CompareStringW(0x7Fu, 0, bstrString, -1, *(PCNZWCH *)(a2 + 8), -1);
      v16 = bstrString;
      if ( v17 != 2 )
        goto LABEL_19;
      SysFreeString(bstrString);
    }
    ++v7;
    NextSlot = CDSArrayBuilder::get_NextSlot((CDSArrayBuilder *)a3, &v24);
    if ( NextSlot < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x485,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
        (const char *)(unsigned int)NextSlot,
        lpString2);
    Element = GetElement(v27, v24, a2, v26);
    v8 = Element;
    if ( Element < 0 )
    {
      v21 = (unsigned int)Element;
      v10 = 1158;
      goto LABEL_35;
    }
    if ( v24 == (unsigned __int8 *)(*(_QWORD *)(a3 + 8) + (unsigned int)(*(_DWORD *)(a3 + 16) * *(_DWORD *)(a3 + 24))) )
    {
      ++*(_DWORD *)(a3 + 24);
      v20 = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\lib\\dsutil\\dsarray.cpp",
        (const char *)0x80070057LL,
        lpString2);
      v20 = 2147942487LL;
    }
    if ( (int)v20 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x487,
        (unsigned int)"C:\\__w\\1\\s\\src\\Client\\Engine\\lib\\updparse\\dsparse.cpp",
        (const char *)v20,
        lpString2);
LABEL_30:
    ++v11;
    v6 = v25;
  }
  while ( v11 < (int)v28 );
  if ( v7 )
    goto LABEL_38;
LABEL_32:
  if ( *(_BYTE *)(a2 + 32) )
  {
    v8 = -2145124339;
    v21 = 2149842957LL;
    v10 = 1162;
    goto LABEL_35;
  }
LABEL_38:
  v8 = 0;
LABEL_39:
  v13 = v27;
LABEL_40:
  if ( v13 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180039858  push    rbp
0x18003985a  push    rbx
0x18003985b  push    rdi
0x18003985c  push    r12
0x18003985e  push    r13
0x180039860  push    r14
0x180039862  push    r15
0x180039864  mov     rbp, rsp
0x180039867  sub     rsp, 70h
0x18003986b  mov     rax, cs:__security_cookie
0x180039872  xor     rax, rsp
0x180039875  mov     [rbp+var_10], rax
0x180039879  mov     [rbp+var_30], r9
0x18003987d  mov     r15, r8
0x180039880  mov     r14, rdx
0x180039883  mov     rbx, rcx
0x180039886  mov     [rbp+var_38], rcx
0x18003988a  xor     r13d, r13d
0x18003988d  mov     [rbp+var_28], r13
0x180039891  mov     [rbp+var_40], r13
0x180039895  mov     [rbp+var_20], r13d
0x180039899  mov     r12d, r13d
0x18003989c  mov     rax, [rcx]
0x18003989f  lea     rdx, [rbp+var_20]
0x1800398a3  mov     rax, [rax+40h]
0x1800398a7  call    _guard_dispatch_icall
0x1800398ac  mov     edi, eax
0x1800398ae  test    eax, eax
0x1800398b0  jns     short loc_1800398BC
0x1800398b2  mov     edx, 458h
0x1800398b7  jmp     loc_180039AF9
0x1800398bc  mov     edx, [rbp+var_20]; unsigned int
0x1800398bf  mov     rcx, r15; this
0x1800398c2  call    ?put_MinimumSize@CDSArrayBuilder@@QEAAJKH@Z; CDSArrayBuilder::put_MinimumSize(ulong,int)
0x1800398c7  mov     edi, eax
0x1800398c9  test    eax, eax
0x1800398cb  jns     short loc_1800398D7
0x1800398cd  mov     edx, 459h
0x1800398d2  jmp     loc_180039AF9
0x1800398d7  mov     rax, [rbx]
0x1800398da  mov     rcx, rbx
0x1800398dd  mov     rax, [rax+50h]
0x1800398e1  call    _guard_dispatch_icall
0x1800398e6  mov     edi, eax
0x1800398e8  test    eax, eax
0x1800398ea  jns     short loc_1800398F6
0x1800398ec  mov     edx, 45Ah
0x1800398f1  jmp     loc_180039AF9
0x1800398f6  xor     r13d, r13d
0x1800398f9  cmp     [rbp+var_20], r12d
0x1800398fd  jle     loc_180039AC4
0x180039903  mov     rax, [rbx]
0x180039906  mov     rbx, [rax+48h]
0x18003990a  mov     rcx, [rbp+var_28]
0x18003990e  test    rcx, rcx
0x180039911  jz      short loc_180039927
0x180039913  mov     rdx, [rcx]
0x180039916  mov     rax, [rdx+10h]
0x18003991a  call    _guard_dispatch_icall
0x18003991f  mov     [rbp+var_28], 0
0x180039927  lea     rdx, [rbp+var_28]
0x18003992b  mov     rcx, [rbp+var_38]
0x18003992f  mov     rax, rbx
0x180039932  call    _guard_dispatch_icall
0x180039937  mov     edi, eax
0x180039939  test    eax, eax
0x18003993b  js      loc_180039AF4
0x180039941  mov     rbx, [rbp+var_28]
0x180039945  test    rbx, rbx
0x180039948  jz      loc_180039B04
0x18003994e  cmp     dword ptr [r14+18h], 16h
0x180039953  jnz     short loc_180039997
0x180039955  mov     dword ptr [rbp+bstrString], 0
0x18003995c  mov     rax, [rbx]
0x18003995f  lea     rdx, [rbp+bstrString]
0x180039963  mov     rcx, rbx
0x180039966  mov     rax, [rax+50h]
0x18003996a  call    _guard_dispatch_icall
0x18003996f  mov     rcx, [rbp+38h]; this
0x180039973  test    eax, eax
0x180039975  jns     short loc_18003998B
0x180039977  mov     r9d, eax; char *
0x18003997a  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180039981  mov     edx, 468h; void *
0x180039986  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003998b  cmp     dword ptr [rbp+bstrString], 1
0x18003998f  jnz     loc_180039AAE
0x180039995  jmp     short loc_180039A0A
0x180039997  mov     [rbp+bstrString], 0
0x18003999f  mov     rax, [rbx]
0x1800399a2  mov     rdi, [rax+38h]
0x1800399a6  xor     ecx, ecx; bstrString
0x1800399a8  call    cs:__imp_SysFreeString
0x1800399ae  mov     [rbp+bstrString], 0
0x1800399b6  lea     rdx, [rbp+bstrString]
0x1800399ba  mov     rcx, rbx
0x1800399bd  mov     rax, rdi
0x1800399c0  call    _guard_dispatch_icall
0x1800399c5  test    eax, eax
0x1800399c7  jns     short loc_1800399D8
0x1800399c9  mov     rcx, [rbp+bstrString]; bstrString
0x1800399cd  call    cs:__imp_SysFreeString
0x1800399d3  jmp     loc_180039AAE
0x1800399d8  or      edi, 0FFFFFFFFh
0x1800399db  mov     [rsp+70h+cchCount2], edi; cchCount2
0x1800399df  mov     rax, [r14+8]
0x1800399e3  mov     [rsp+70h+lpString2], rax; int
0x1800399e8  mov     r9d, edi; cchCount1
0x1800399eb  mov     r8, [rbp+bstrString]; lpString1
0x1800399ef  xor     edx, edx; dwCmpFlags
0x1800399f1  lea     ecx, [rdx+7Fh]; Locale
0x1800399f4  call    cs:__imp_CompareStringW
0x1800399fa  nop
0x1800399fb  mov     rcx, [rbp+bstrString]; bstrString
0x1800399ff  cmp     eax, 2
0x180039a02  jnz     short loc_1800399CD
0x180039a04  call    cs:__imp_SysFreeString
0x180039a0a  inc     r12d
0x180039a0d  lea     rdx, [rbp+var_40]; unsigned __int8 **
0x180039a11  mov     rcx, r15; this
0x180039a14  call    ?get_NextSlot@CDSArrayBuilder@@QEAAJPEAPEAE@Z; CDSArrayBuilder::get_NextSlot(uchar * *)
0x180039a19  mov     rcx, [rbp+38h]; this
0x180039a1d  test    eax, eax
0x180039a1f  jns     short loc_180039A35
0x180039a21  mov     r9d, eax; char *
0x180039a24  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180039a2b  mov     edx, 485h; void *
0x180039a30  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039a35  mov     r9, [rbp+var_30]
0x180039a39  mov     r8, r14
0x180039a3c  mov     rdx, [rbp+var_40]
0x180039a40  mov     rcx, [rbp+var_28]
0x180039a44  call    GetElement
0x180039a49  mov     edi, eax
0x180039a4b  test    eax, eax
0x180039a4d  js      loc_180039ADA
0x180039a53  mov     edx, [r15+18h]
0x180039a57  mov     ecx, edx
0x180039a59  imul    ecx, [r15+10h]
0x180039a5e  add     rcx, [r15+8]
0x180039a62  cmp     [rbp+var_40], rcx
0x180039a66  jz      short loc_180039A8A
0x180039a68  mov     rcx, [rbp+38h]; this
0x180039a6c  mov     ebx, 80070057h
0x180039a71  mov     r9d, ebx; char *
0x180039a74  lea     r8, aCW1SSrcClientL_5; "C:\\__w\\1\\s\\src\\Client\\lib\\dsutil"...
0x180039a7b  mov     edx, 85h; void *
0x180039a80  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039a85  mov     r9d, ebx
0x180039a88  jmp     short loc_180039A94
0x180039a8a  lea     eax, [rdx+1]
0x180039a8d  mov     [r15+18h], eax
0x180039a91  xor     r9d, r9d; char *
0x180039a94  mov     rcx, [rbp+38h]; this
0x180039a98  test    r9d, r9d
0x180039a9b  jns     short loc_180039AAE
0x180039a9d  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180039aa4  mov     edx, 487h; void *
0x180039aa9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180039aae  inc     r13d
0x180039ab1  cmp     r13d, [rbp+var_20]
0x180039ab5  mov     rbx, [rbp+var_38]
0x180039ab9  jl      loc_180039903
0x180039abf  test    r12d, r12d
0x180039ac2  jnz     short loc_180039AFE
0x180039ac4  cmp     byte ptr [r14+20h], 0
0x180039ac9  jz      short loc_180039AFE
0x180039acb  mov     edi, 8024000Dh
0x180039ad0  mov     r9d, edi
0x180039ad3  mov     edx, 48Ah
0x180039ad8  jmp     short loc_180039AE2
0x180039ada  mov     r9d, eax; char *
0x180039add  mov     edx, 486h; void *
0x180039ae2  mov     rcx, [rbp+38h]; this
0x180039ae6  lea     r8, aCW1SSrcClientE_4; "C:\\__w\\1\\s\\src\\Client\\Engine\\lib"...
0x180039aed  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180039af2  jmp     short loc_180039B00
0x180039af4  mov     edx, 462h
0x180039af9  mov     r9d, edi
0x180039afc  jmp     short loc_180039AE2
0x180039afe  xor     edi, edi
0x180039b00  mov     rbx, [rbp+var_28]
0x180039b04  test    rbx, rbx
0x180039b07  jz      short loc_180039B19
0x180039b09  mov     rcx, [rbx]
0x180039b0c  mov     rax, [rcx+10h]
0x180039b10  mov     rcx, rbx
0x180039b13  call    _guard_dispatch_icall
0x180039b18  nop
0x180039b19  mov     eax, edi
0x180039b1b  mov     rcx, [rbp+var_10]
0x180039b1f  xor     rcx, rsp; StackCookie
0x180039b22  call    __security_check_cookie
0x180039b27  add     rsp, 70h
0x180039b2b  pop     r15
0x180039b2d  pop     r14
0x180039b2f  pop     r13
0x180039b31  pop     r12
0x180039b33  pop     rdi
0x180039b34  pop     rbx
0x180039b35  pop     rbp
0x180039b36  retn
```
