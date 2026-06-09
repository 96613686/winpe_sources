# HrValidateSpecVersion(IXMLDOMNode *,ushort * *)

- ea: `0x180026fa0`
- end: `0x180027677`
- name: `?HrValidateSpecVersion@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1751`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x180010800`

## callees

- `0x18000db4c`
- `0x180026fa0`
- `0x180038980`
- `0x18003a560`
- `0x180055010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027485`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027500`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027485`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x180027500`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18002749c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027513`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x18002749c`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180027513`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800273e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002744a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027460`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800274c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800274db`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800273e2`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x18002744a`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180027460`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800274c5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800274db`
- `OLEAUT32!__imp_SysFreeString` at `0x18002717a`
- `OLEAUT32!__imp_SysFreeString` at `0x180027185`
- `OLEAUT32!__imp_SysFreeString` at `0x180027380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002738b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273f5`
- `OLEAUT32!__imp_SysFreeString` at `0x18002717a`
- `OLEAUT32!__imp_SysFreeString` at `0x180027185`
- `OLEAUT32!__imp_SysFreeString` at `0x180027380`
- `OLEAUT32!__imp_SysFreeString` at `0x18002738b`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273ce`
- `OLEAUT32!__imp_SysFreeString` at `0x1800273f5`

## string_xrefs

- `0x1800270c6`: `urn:schemas-upnp-org:service-1-`
- `0x1800272cc`: `urn:schemas-upnp-org:service-1-`

## pseudocode

```c
__int64 __fastcall HrValidateSpecVersion(struct IXMLDOMNode *a1, unsigned __int16 **a2)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v4; // r12d
  int v5; // r15d
  int v6; // eax
  int v7; // ecx
  __int64 *v8; // rdi
  int v9; // ebx
  __int64 v10; // rax
  int v11; // r14d
  signed int v12; // ebx
  OLECHAR *v13; // r8
  BSTR v14; // rax
  __int64 v15; // rdx
  unsigned __int64 v16; // rsi
  __int64 v17; // rax
  __int64 v18; // rdx
  const wchar_t *v19; // rcx
  WCHAR *v20; // r9
  WCHAR *v21; // rcx
  __int64 v22; // rcx
  WCHAR *v23; // rax
  OLECHAR *v24; // r9
  __int64 v25; // rdx
  WCHAR *v26; // rcx
  __int64 *v28; // rdi
  int v29; // r14d
  signed int v30; // ebx
  OLECHAR *v31; // r8
  BSTR v32; // rax
  __int64 v33; // rdx
  unsigned __int64 v34; // rsi
  __int64 v35; // rax
  __int64 v36; // rdx
  const wchar_t *v37; // rcx
  WCHAR *v38; // r9
  WCHAR *v39; // rcx
  __int64 v40; // rcx
  WCHAR *v41; // rax
  OLECHAR *v42; // r9
  __int64 v43; // rdx
  WCHAR *v44; // rcx
  int v45; // ecx
  unsigned __int64 i; // rdi
  unsigned __int64 j; // rdi
  const unsigned __int16 *v48; // rdx
  BSTR v49; // [rsp+30h] [rbp-D0h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-C8h] BYREF
  __int64 *v51; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 *v52; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v53; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR String2[256]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String1[256]; // [rsp+260h] [rbp+160h] BYREF

  lpVtbl = a1->lpVtbl;
  v52 = 0;
  v51 = 0;
  v4 = 0;
  v5 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, __int64 **))lpVtbl->get_firstChild)(a1, &v51);
  v8 = v51;
  v9 = v6;
  while ( 1 )
  {
    if ( v9 < 0 )
      goto LABEL_32;
    if ( !v8 )
      break;
    v53 = 0;
    v10 = *v8;
    v49 = 0;
    v11 = 0;
    bstrString = 0;
    v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(v10 + 328))(v8, &v49);
    if ( v12 >= 0 && v49 )
    {
      v12 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v8 + 312))(v8, &bstrString);
      if ( v12 >= 0 )
      {
        v13 = bstrString;
        if ( bstrString )
        {
          v14 = bstrString;
          v15 = 0x7FFFFFFF;
          do
          {
            if ( !*v14 )
              break;
            ++v14;
            --v15;
          }
          while ( v15 );
          v12 = v15 == 0 ? 0x80070057 : 0;
          v16 = (0x7FFFFFFF - v15) & -(__int64)(v15 != 0);
          if ( v15 )
          {
            v17 = 31;
            v18 = 256;
            v19 = L"urn:schemas-upnp-org:service-1-";
            v20 = String1;
            do
            {
              if ( !v17 )
                break;
              if ( !*v19 )
                break;
              *v20++ = *v19++;
              --v17;
              --v18;
            }
            while ( v18 );
            v21 = v20 - 1;
            v12 = v18 == 0 ? 0x8007007A : 0;
            if ( v18 )
              v21 = v20;
            *v21 = 0;
            if ( v18 )
            {
              v22 = 31;
              v23 = String2;
              v24 = v13;
              v25 = 256;
              do
              {
                if ( !v22 )
                  break;
                if ( !*v24 )
                  break;
                *v23++ = *v24++;
                --v22;
                --v25;
              }
              while ( v25 );
              v26 = v23 - 1;
              if ( v25 )
                v26 = v23;
              *v26 = 0;
              v12 = v25 == 0 ? 0x8007007A : 0;
              if ( v25 )
              {
                if ( !lstrcmpW(v49, L"major") && !lstrcmpW(String1, String2) )
                {
                  v11 = 1;
                  if ( v16 > 0x1F )
                  {
                    for ( i = 31; i < v16; ++i )
                    {
                      if ( !IsCharAlphaNumericW(bstrString[i]) || IsCharAlphaW(bstrString[i]) )
                      {
                        v13 = bstrString;
                        v11 = 0;
                        goto LABEL_26;
                      }
                    }
                  }
                }
                v13 = bstrString;
              }
            }
          }
LABEL_26:
          SysFreeString(v13);
        }
      }
      SysFreeString(v49);
    }
    if ( v12 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        20,
        (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
        (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
        v12);
    v49 = 0;
    if ( v11 )
    {
      ++v4;
      v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v51 + 208))(v51, &v49);
      if ( v9 < 0 )
        goto LABEL_31;
      if ( lstrcmpW(v49, L"1") )
        v9 = HrAllocErrorStringAndReturnHr(v45, L"<major> version number is incorrect - should be \"1\"", 0, &v52);
      SysFreeString(v49);
      if ( v9 < 0 )
      {
LABEL_31:
        (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
        goto LABEL_32;
      }
    }
    else
    {
      v28 = v51;
      v29 = 0;
      bstrString = 0;
      v30 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v51 + 328))(v51, &v49);
      if ( v30 >= 0 && v49 )
      {
        v30 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v28 + 312))(v28, &bstrString);
        if ( v30 >= 0 )
        {
          v31 = bstrString;
          if ( bstrString )
          {
            v32 = bstrString;
            v33 = 0x7FFFFFFF;
            do
            {
              if ( !*v32 )
                break;
              ++v32;
              --v33;
            }
            while ( v33 );
            v30 = v33 == 0 ? 0x80070057 : 0;
            v34 = (0x7FFFFFFF - v33) & -(__int64)(v33 != 0);
            if ( v33 )
            {
              v35 = 31;
              v36 = 256;
              v37 = L"urn:schemas-upnp-org:service-1-";
              v38 = String2;
              do
              {
                if ( !v35 )
                  break;
                if ( !*v37 )
                  break;
                *v38++ = *v37++;
                --v35;
                --v36;
              }
              while ( v36 );
              v39 = v38 - 1;
              v30 = v36 == 0 ? 0x8007007A : 0;
              if ( v36 )
                v39 = v38;
              *v39 = 0;
              if ( v36 )
              {
                v40 = 31;
                v41 = String1;
                v42 = v31;
                v43 = 256;
                do
                {
                  if ( !v40 )
                    break;
                  if ( !*v42 )
                    break;
                  *v41++ = *v42++;
                  --v40;
                  --v43;
                }
                while ( v43 );
                v44 = v41 - 1;
                if ( v43 )
                  v44 = v41;
                *v44 = 0;
                v30 = v43 == 0 ? 0x8007007A : 0;
                if ( v43 )
                {
                  if ( !lstrcmpW(v49, L"minor") && !lstrcmpW(String2, String1) )
                  {
                    v29 = 1;
                    if ( v34 > 0x1F )
                    {
                      for ( j = 31; j < v34; ++j )
                      {
                        if ( !IsCharAlphaNumericW(bstrString[j]) || IsCharAlphaW(bstrString[j]) )
                        {
                          v31 = bstrString;
                          v29 = 0;
                          goto LABEL_58;
                        }
                      }
                    }
                  }
                  v31 = bstrString;
                }
              }
            }
LABEL_58:
            SysFreeString(v31);
          }
        }
        SysFreeString(v49);
      }
      if ( v30 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          20,
          (unsigned int)WPP_1663e5dd4df63ad0f4f5db840799a00c_Traceguids,
          (unsigned int)"FIsThisTheNodeNameWithNamespace(): Exiting",
          v30);
      if ( v29 )
      {
        v49 = 0;
        ++v5;
        v9 = (*(__int64 (__fastcall **)(__int64 *, BSTR *))(*v51 + 208))(v51, &v49);
        if ( v9 < 0 )
          goto LABEL_31;
        SysFreeString(v49);
      }
    }
    v9 = (*(__int64 (__fastcall **)(__int64 *, __int64 **))(*v51 + 128))(v51, &v53);
    (*(void (__fastcall **)(__int64 *))(*v51 + 16))(v51);
    v8 = v53;
    v51 = v53;
  }
  if ( v4 != 1 )
  {
    v48 = L"<major> specVersion element must appear exactly once";
LABEL_98:
    v9 = HrAllocErrorStringAndReturnHr(v7, v48, 0, &v52);
    goto LABEL_32;
  }
  if ( v5 != 1 )
  {
    v48 = L"<minor> specVersion element must appear exactly once";
    goto LABEL_98;
  }
  v9 = 0;
LABEL_32:
  if ( v52 )
    *a2 = v52;
  if ( v9 && WPP_GLOBAL_Control != (STRSAFE_PCNZWCH)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 1) != 0 )
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      38,
      (unsigned int)WPP_b522c78dcf6c3de65204eee127e73824_Traceguids,
      (unsigned int)"HrValidateSpecVersion(): Exiting",
      v9);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180026fa0  mov     [rsp-8+arg_10], rbx
0x180026fa5  push    rbp
0x180026fa6  push    rsi
0x180026fa7  push    rdi
0x180026fa8  push    r12
0x180026faa  push    r13
0x180026fac  push    r14
0x180026fae  push    r15
0x180026fb0  lea     rbp, [rsp-370h]
0x180026fb8  sub     rsp, 470h
0x180026fbf  mov     rax, cs:__security_cookie
0x180026fc6  xor     rax, rsp
0x180026fc9  mov     [rbp+3A0h+var_40], rax
0x180026fd0  mov     rax, [rcx]
0x180026fd3  xor     esi, esi
0x180026fd5  mov     r13, rdx
0x180026fd8  mov     [rsp+4A0h+var_458], rsi
0x180026fdd  lea     rdx, [rsp+4A0h+var_460]
0x180026fe2  mov     [rsp+4A0h+var_460], rsi
0x180026fe7  mov     r12d, esi
0x180026fea  mov     r15d, esi
0x180026fed  mov     rax, [rax+68h]
0x180026ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026ff6  mov     rdi, [rsp+4A0h+var_460]
0x180026ffb  mov     ebx, eax
0x180026ffd  test    ebx, ebx
0x180026fff  js      loc_1800271DC
0x180027005  test    rdi, rdi
0x180027008  jz      loc_1800275F1
0x18002700e  mov     [rsp+4A0h+var_450], rsi
0x180027013  lea     rdx, [rsp+4A0h+var_470]
0x180027018  mov     rax, [rdi]
0x18002701b  mov     rcx, rdi
0x18002701e  mov     [rsp+4A0h+var_470], rsi
0x180027023  mov     r14d, esi
0x180027026  mov     [rsp+4A0h+bstrString], rsi
0x18002702b  mov     rax, [rax+148h]
0x180027032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027037  mov     ebx, eax
0x180027039  test    eax, eax
0x18002703b  js      loc_18002718B
0x180027041  cmp     [rsp+4A0h+var_470], rsi
0x180027046  jz      loc_18002718B
0x18002704c  mov     rax, [rdi]
0x18002704f  lea     rdx, [rsp+4A0h+bstrString]
0x180027054  mov     rcx, rdi
0x180027057  mov     rax, [rax+138h]
0x18002705e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027063  mov     ebx, eax
0x180027065  test    eax, eax
0x180027067  js      loc_180027180
0x18002706d  mov     r8, [rsp+4A0h+bstrString]
0x180027072  test    r8, r8
0x180027075  jz      loc_180027180
0x18002707b  mov     ecx, 7FFFFFFFh
0x180027080  mov     rax, r8
0x180027083  mov     edx, ecx
0x180027085  cmp     [rax], si
0x180027088  jz      short loc_180027094
0x18002708a  add     rax, 2
0x18002708e  sub     rdx, 1
0x180027092  jnz     short loc_180027085
0x180027094  mov     rax, rdx
0x180027097  neg     rax
0x18002709a  mov     rax, rdx
0x18002709d  sbb     ebx, ebx
0x18002709f  sub     rcx, rdx
0x1800270a2  not     ebx
0x1800270a4  and     ebx, 80070057h
0x1800270aa  neg     rax
0x1800270ad  sbb     rsi, rsi
0x1800270b0  xor     edi, edi
0x1800270b2  and     rsi, rcx
0x1800270b5  test    rdx, rdx
0x1800270b8  jz      loc_180027175
0x1800270be  lea     eax, [rdi+1Fh]
0x1800270c1  mov     edx, 100h
0x1800270c6  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x1800270cd  lea     r9, [rbp+3A0h+String1]
0x1800270d4  test    rax, rax
0x1800270d7  jz      short loc_1800270F8
0x1800270d9  movzx   r10d, word ptr [rcx]
0x1800270dd  test    r10w, r10w
0x1800270e1  jz      short loc_1800270F8
0x1800270e3  mov     [r9], r10w
0x1800270e7  add     rcx, 2
0x1800270eb  add     r9, 2
0x1800270ef  dec     rax
0x1800270f2  sub     rdx, 1
0x1800270f6  jnz     short loc_1800270D4
0x1800270f8  mov     rax, rdx
0x1800270fb  lea     rcx, [r9-2]
0x1800270ff  neg     rax
0x180027102  mov     r11d, 8007007Ah
0x180027108  sbb     ebx, ebx
0x18002710a  not     ebx
0x18002710c  and     ebx, r11d
0x18002710f  test    rdx, rdx
0x180027112  cmovnz  rcx, r9
0x180027116  mov     [rcx], di
0x180027119  jz      short loc_180027175
0x18002711b  mov     ecx, 1Fh
0x180027120  lea     rax, [rsp+4A0h+String2]
0x180027125  mov     r9, r8
0x180027128  mov     edx, 100h
0x18002712d  test    rcx, rcx
0x180027130  jz      short loc_180027151
0x180027132  movzx   r10d, word ptr [r9]
0x180027136  test    r10w, r10w
0x18002713a  jz      short loc_180027151
0x18002713c  mov     [rax], r10w
0x180027140  add     r9, 2
0x180027144  add     rax, 2
0x180027148  dec     rcx
0x18002714b  sub     rdx, 1
0x18002714f  jnz     short loc_18002712D
0x180027151  test    rdx, rdx
0x180027154  lea     rcx, [rax-2]
0x180027158  cmovnz  rcx, rax
0x18002715c  mov     rax, rdx
0x18002715f  neg     rax
0x180027162  sbb     ebx, ebx
0x180027164  not     ebx
0x180027166  mov     [rcx], di
0x180027169  and     ebx, r11d
0x18002716c  test    rdx, rdx
0x18002716f  jnz     loc_18002743E
0x180027175  xor     esi, esi
0x180027177  mov     rcx, r8; bstrString
0x18002717a  call    cs:__imp_SysFreeString
0x180027180  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x180027185  call    cs:__imp_SysFreeString
0x18002718b  test    ebx, ebx
0x18002718d  jnz     loc_18002754A
0x180027193  mov     [rsp+4A0h+var_470], rsi
0x180027198  lea     rdx, [rsp+4A0h+var_470]
0x18002719d  test    r14d, r14d
0x1800271a0  jz      short loc_18002721E
0x1800271a2  mov     rcx, [rsp+4A0h+var_460]
0x1800271a7  inc     r12d
0x1800271aa  mov     rax, [rcx]
0x1800271ad  mov     rax, [rax+0D0h]
0x1800271b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271b9  mov     ebx, eax
0x1800271bb  test    eax, eax
0x1800271bd  jns     loc_1800273D6
0x1800271c3  mov     rcx, [rsp+4A0h+var_460]
0x1800271c8  mov     rax, [rcx]
0x1800271cb  mov     rax, [rax+10h]
0x1800271cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800271d4  test    ebx, ebx
0x1800271d6  jns     loc_1800275F1
0x1800271dc  mov     rax, [rsp+4A0h+var_458]
0x1800271e1  test    rax, rax
0x1800271e4  jnz     loc_180027628
0x1800271ea  test    ebx, ebx
0x1800271ec  jnz     loc_180027631
0x1800271f2  mov     eax, ebx
0x1800271f4  mov     rcx, [rbp+3A0h+var_40]
0x1800271fb  xor     rcx, rsp; StackCookie
0x1800271fe  call    __security_check_cookie
0x180027203  mov     rbx, [rsp+4A0h+arg_10]
0x18002720b  add     rsp, 470h
0x180027212  pop     r15
0x180027214  pop     r14
0x180027216  pop     r13
0x180027218  pop     r12
0x18002721a  pop     rdi
0x18002721b  pop     rsi
0x18002721c  pop     rbp
0x18002721d  retn
0x18002721e  mov     rdi, [rsp+4A0h+var_460]
0x180027223  mov     r14d, esi
0x180027226  mov     rcx, rdi
0x180027229  mov     [rsp+4A0h+bstrString], rsi
0x18002722e  mov     rax, [rdi]
0x180027231  mov     rax, [rax+148h]
0x180027238  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002723d  mov     ebx, eax
0x18002723f  test    eax, eax
0x180027241  js      loc_180027391
0x180027247  cmp     [rsp+4A0h+var_470], rsi
0x18002724c  jz      loc_180027391
0x180027252  mov     rax, [rdi]
0x180027255  lea     rdx, [rsp+4A0h+bstrString]
0x18002725a  mov     rcx, rdi
0x18002725d  mov     rax, [rax+138h]
0x180027264  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027269  mov     ebx, eax
0x18002726b  test    eax, eax
0x18002726d  js      loc_180027386
0x180027273  mov     r8, [rsp+4A0h+bstrString]
0x180027278  test    r8, r8
0x18002727b  jz      loc_180027386
0x180027281  mov     ecx, 7FFFFFFFh
0x180027286  mov     rax, r8
0x180027289  mov     edx, ecx
0x18002728b  cmp     [rax], si
0x18002728e  jz      short loc_18002729A
0x180027290  add     rax, 2
0x180027294  sub     rdx, 1
0x180027298  jnz     short loc_18002728B
0x18002729a  mov     rax, rdx
0x18002729d  neg     rax
0x1800272a0  mov     rax, rdx
0x1800272a3  sbb     ebx, ebx
0x1800272a5  sub     rcx, rdx
0x1800272a8  not     ebx
0x1800272aa  and     ebx, 80070057h
0x1800272b0  neg     rax
0x1800272b3  sbb     rsi, rsi
0x1800272b6  xor     edi, edi
0x1800272b8  and     rsi, rcx
0x1800272bb  test    rdx, rdx
0x1800272be  jz      loc_18002737B
0x1800272c4  lea     eax, [rdi+1Fh]
0x1800272c7  mov     edx, 100h
0x1800272cc  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x1800272d3  lea     r9, [rsp+4A0h+String2]
0x1800272d8  test    rax, rax
0x1800272db  jz      short loc_1800272FC
0x1800272dd  movzx   r10d, word ptr [rcx]
0x1800272e1  test    r10w, r10w
0x1800272e5  jz      short loc_1800272FC
0x1800272e7  mov     [r9], r10w
0x1800272eb  add     rcx, 2
0x1800272ef  add     r9, 2
0x1800272f3  dec     rax
0x1800272f6  sub     rdx, 1
0x1800272fa  jnz     short loc_1800272D8
0x1800272fc  mov     rax, rdx
0x1800272ff  lea     rcx, [r9-2]
0x180027303  neg     rax
0x180027306  mov     r11d, 8007007Ah
0x18002730c  sbb     ebx, ebx
0x18002730e  not     ebx
0x180027310  and     ebx, r11d
0x180027313  test    rdx, rdx
0x180027316  cmovnz  rcx, r9
0x18002731a  mov     [rcx], di
0x18002731d  jz      short loc_18002737B
0x18002731f  mov     ecx, 1Fh
0x180027324  lea     rax, [rbp+3A0h+String1]
0x18002732b  mov     r9, r8
0x18002732e  mov     edx, 100h
0x180027333  test    rcx, rcx
0x180027336  jz      short loc_180027357
0x180027338  movzx   r10d, word ptr [r9]
0x18002733c  test    r10w, r10w
0x180027340  jz      short loc_180027357
0x180027342  mov     [rax], r10w
0x180027346  add     r9, 2
0x18002734a  add     rax, 2
0x18002734e  dec     rcx
0x180027351  sub     rdx, 1
0x180027355  jnz     short loc_180027333
0x180027357  test    rdx, rdx
0x18002735a  lea     rcx, [rax-2]
0x18002735e  cmovnz  rcx, rax
0x180027362  mov     rax, rdx
0x180027365  neg     rax
0x180027368  sbb     ebx, ebx
0x18002736a  not     ebx
0x18002736c  mov     [rcx], di
0x18002736f  and     ebx, r11d
0x180027372  test    rdx, rdx
0x180027375  jnz     loc_1800274B9
0x18002737b  xor     esi, esi
0x18002737d  mov     rcx, r8; bstrString
0x180027380  call    cs:__imp_SysFreeString
0x180027386  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x18002738b  call    cs:__imp_SysFreeString
0x180027391  test    ebx, ebx
0x180027393  jnz     loc_1800275AB
0x180027399  test    r14d, r14d
0x18002739c  jz      short loc_180027403
0x18002739e  mov     rcx, [rsp+4A0h+var_460]
0x1800273a3  lea     rdx, [rsp+4A0h+var_470]
0x1800273a8  mov     [rsp+4A0h+var_470], rsi
0x1800273ad  inc     r15d
0x1800273b0  mov     rax, [rcx]
0x1800273b3  mov     rax, [rax+0D0h]
0x1800273ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273bf  mov     ebx, eax
0x1800273c1  test    eax, eax
0x1800273c3  js      loc_1800271C3
0x1800273c9  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x1800273ce  call    cs:__imp_SysFreeString
0x1800273d4  jmp     short loc_180027403
0x1800273d6  mov     rcx, [rsp+4A0h+var_470]; lpString1
0x1800273db  lea     rdx, a1; "1"
0x1800273e2  call    cs:__imp_lstrcmpW
0x1800273e8  test    eax, eax
0x1800273ea  jnz     loc_180027590
0x1800273f0  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x1800273f5  call    cs:__imp_SysFreeString
0x1800273fb  test    ebx, ebx
0x1800273fd  js      loc_1800271C3
0x180027403  mov     rcx, [rsp+4A0h+var_460]
0x180027408  lea     rdx, [rsp+4A0h+var_450]
  ... truncated ...
```
