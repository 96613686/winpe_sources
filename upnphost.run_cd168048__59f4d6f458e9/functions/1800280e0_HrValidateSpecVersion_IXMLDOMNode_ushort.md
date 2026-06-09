# HrValidateSpecVersion(IXMLDOMNode *,ushort * *)

- ea: `0x1800280e0`
- end: `0x180028812`
- name: `?HrValidateSpecVersion@@YAJPEAUIXMLDOMNode@@PEAPEAG@Z`
- size: `1842`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task`

## callers

- `0x1800047a0`

## callees

- `0x1800200f4`
- `0x1800280e0`
- `0x18003ac1c`
- `0x18003cb60`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800285fc`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002868f`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x1800285fc`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaNumericW` at `0x18002868f`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180028619`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800286a8`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x180028619`
- `api-ms-win-core-string-l2-1-0!IsCharAlphaW` at `0x1800286a8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028541`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800285b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800285d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028648`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028664`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028541`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800285b5`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x1800285d1`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028648`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180028664`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284de`
- `OLEAUT32!__imp_SysFreeString` at `0x180028527`
- `OLEAUT32!__imp_SysFreeString` at `0x18002855a`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282ba`
- `OLEAUT32!__imp_SysFreeString` at `0x1800282cb`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284cd`
- `OLEAUT32!__imp_SysFreeString` at `0x1800284de`
- `OLEAUT32!__imp_SysFreeString` at `0x180028527`
- `OLEAUT32!__imp_SysFreeString` at `0x18002855a`

## string_xrefs

- `0x180028206`: `urn:schemas-upnp-org:service-1-`
- `0x180028419`: `urn:schemas-upnp-org:service-1-`

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
0x1800280e0  mov     [rsp-8+arg_10], rbx
0x1800280e5  push    rbp
0x1800280e6  push    rsi
0x1800280e7  push    rdi
0x1800280e8  push    r12
0x1800280ea  push    r13
0x1800280ec  push    r14
0x1800280ee  push    r15
0x1800280f0  lea     rbp, [rsp-370h]
0x1800280f8  sub     rsp, 470h
0x1800280ff  mov     rax, cs:__security_cookie
0x180028106  xor     rax, rsp
0x180028109  mov     [rbp+3A0h+var_40], rax
0x180028110  mov     rax, [rcx]
0x180028113  xor     esi, esi
0x180028115  mov     r13, rdx
0x180028118  mov     [rsp+4A0h+var_458], rsi
0x18002811d  lea     rdx, [rsp+4A0h+var_460]
0x180028122  mov     [rsp+4A0h+var_460], rsi
0x180028127  mov     r12d, esi
0x18002812a  mov     r15d, esi
0x18002812d  mov     rax, [rax+68h]
0x180028131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028136  mov     rdi, [rsp+4A0h+var_460]
0x18002813b  mov     ebx, eax
0x18002813d  test    ebx, ebx
0x18002813f  js      loc_180028328
0x180028145  test    rdi, rdi
0x180028148  jz      loc_18002878C
0x18002814e  mov     [rsp+4A0h+var_450], rsi
0x180028153  lea     rdx, [rsp+4A0h+var_470]
0x180028158  mov     rax, [rdi]
0x18002815b  mov     rcx, rdi
0x18002815e  mov     [rsp+4A0h+var_470], rsi
0x180028163  mov     r14d, esi
0x180028166  mov     [rsp+4A0h+bstrString], rsi
0x18002816b  mov     rax, [rax+148h]
0x180028172  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028177  mov     ebx, eax
0x180028179  test    eax, eax
0x18002817b  js      loc_1800282D7
0x180028181  cmp     [rsp+4A0h+var_470], rsi
0x180028186  jz      loc_1800282D7
0x18002818c  mov     rax, [rdi]
0x18002818f  lea     rdx, [rsp+4A0h+bstrString]
0x180028194  mov     rcx, rdi
0x180028197  mov     rax, [rax+138h]
0x18002819e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281a3  mov     ebx, eax
0x1800281a5  test    eax, eax
0x1800281a7  js      loc_1800282C6
0x1800281ad  mov     r8, [rsp+4A0h+bstrString]
0x1800281b2  test    r8, r8
0x1800281b5  jz      loc_1800282C6
0x1800281bb  mov     ecx, 7FFFFFFFh
0x1800281c0  mov     rax, r8
0x1800281c3  mov     edx, ecx
0x1800281c5  cmp     [rax], si
0x1800281c8  jz      short loc_1800281D4
0x1800281ca  add     rax, 2
0x1800281ce  sub     rdx, 1
0x1800281d2  jnz     short loc_1800281C5
0x1800281d4  mov     rax, rdx
0x1800281d7  neg     rax
0x1800281da  mov     rax, rdx
0x1800281dd  sbb     ebx, ebx
0x1800281df  sub     rcx, rdx
0x1800281e2  not     ebx
0x1800281e4  and     ebx, 80070057h
0x1800281ea  neg     rax
0x1800281ed  sbb     rsi, rsi
0x1800281f0  xor     edi, edi
0x1800281f2  and     rsi, rcx
0x1800281f5  test    rdx, rdx
0x1800281f8  jz      loc_1800282B5
0x1800281fe  lea     eax, [rdi+1Fh]
0x180028201  mov     edx, 100h
0x180028206  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x18002820d  lea     r9, [rbp+3A0h+String1]
0x180028214  test    rax, rax
0x180028217  jz      short loc_180028238
0x180028219  movzx   r10d, word ptr [rcx]
0x18002821d  test    r10w, r10w
0x180028221  jz      short loc_180028238
0x180028223  mov     [r9], r10w
0x180028227  add     rcx, 2
0x18002822b  add     r9, 2
0x18002822f  dec     rax
0x180028232  sub     rdx, 1
0x180028236  jnz     short loc_180028214
0x180028238  mov     rax, rdx
0x18002823b  lea     rcx, [r9-2]
0x18002823f  neg     rax
0x180028242  mov     r11d, 8007007Ah
0x180028248  sbb     ebx, ebx
0x18002824a  not     ebx
0x18002824c  and     ebx, r11d
0x18002824f  test    rdx, rdx
0x180028252  cmovnz  rcx, r9
0x180028256  mov     [rcx], di
0x180028259  jz      short loc_1800282B5
0x18002825b  mov     ecx, 1Fh
0x180028260  lea     rax, [rsp+4A0h+String2]
0x180028265  mov     r9, r8
0x180028268  mov     edx, 100h
0x18002826d  test    rcx, rcx
0x180028270  jz      short loc_180028291
0x180028272  movzx   r10d, word ptr [r9]
0x180028276  test    r10w, r10w
0x18002827a  jz      short loc_180028291
0x18002827c  mov     [rax], r10w
0x180028280  add     r9, 2
0x180028284  add     rax, 2
0x180028288  dec     rcx
0x18002828b  sub     rdx, 1
0x18002828f  jnz     short loc_18002826D
0x180028291  test    rdx, rdx
0x180028294  lea     rcx, [rax-2]
0x180028298  cmovnz  rcx, rax
0x18002829c  mov     rax, rdx
0x18002829f  neg     rax
0x1800282a2  sbb     ebx, ebx
0x1800282a4  not     ebx
0x1800282a6  mov     [rcx], di
0x1800282a9  and     ebx, r11d
0x1800282ac  test    rdx, rdx
0x1800282af  jnz     loc_1800285A9
0x1800282b5  xor     esi, esi
0x1800282b7  mov     rcx, r8; bstrString
0x1800282ba  call    cs:__imp_SysFreeString
0x1800282c1  nop     dword ptr [rax+rax+00h]
0x1800282c6  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x1800282cb  call    cs:__imp_SysFreeString
0x1800282d2  nop     dword ptr [rax+rax+00h]
0x1800282d7  test    ebx, ebx
0x1800282d9  jnz     loc_1800286E5
0x1800282df  mov     [rsp+4A0h+var_470], rsi
0x1800282e4  lea     rdx, [rsp+4A0h+var_470]
0x1800282e9  test    r14d, r14d
0x1800282ec  jz      short loc_18002836B
0x1800282ee  mov     rcx, [rsp+4A0h+var_460]
0x1800282f3  inc     r12d
0x1800282f6  mov     rax, [rcx]
0x1800282f9  mov     rax, [rax+0D0h]
0x180028300  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028305  mov     ebx, eax
0x180028307  test    eax, eax
0x180028309  jns     loc_180028535
0x18002830f  mov     rcx, [rsp+4A0h+var_460]
0x180028314  mov     rax, [rcx]
0x180028317  mov     rax, [rax+10h]
0x18002831b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028320  test    ebx, ebx
0x180028322  jns     loc_18002878C
0x180028328  mov     rax, [rsp+4A0h+var_458]
0x18002832d  test    rax, rax
0x180028330  jnz     loc_1800287C3
0x180028336  test    ebx, ebx
0x180028338  jnz     loc_1800287CC
0x18002833e  mov     eax, ebx
0x180028340  mov     rcx, [rbp+3A0h+var_40]
0x180028347  xor     rcx, rsp; StackCookie
0x18002834a  call    __security_check_cookie
0x18002834f  mov     rbx, [rsp+4A0h+arg_10]
0x180028357  add     rsp, 470h
0x18002835e  pop     r15
0x180028360  pop     r14
0x180028362  pop     r13
0x180028364  pop     r12
0x180028366  pop     rdi
0x180028367  pop     rsi
0x180028368  pop     rbp
0x180028369  retn
0x18002836b  mov     rdi, [rsp+4A0h+var_460]
0x180028370  mov     r14d, esi
0x180028373  mov     rcx, rdi
0x180028376  mov     [rsp+4A0h+bstrString], rsi
0x18002837b  mov     rax, [rdi]
0x18002837e  mov     rax, [rax+148h]
0x180028385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002838a  mov     ebx, eax
0x18002838c  test    eax, eax
0x18002838e  js      loc_1800284EA
0x180028394  cmp     [rsp+4A0h+var_470], rsi
0x180028399  jz      loc_1800284EA
0x18002839f  mov     rax, [rdi]
0x1800283a2  lea     rdx, [rsp+4A0h+bstrString]
0x1800283a7  mov     rcx, rdi
0x1800283aa  mov     rax, [rax+138h]
0x1800283b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800283b6  mov     ebx, eax
0x1800283b8  test    eax, eax
0x1800283ba  js      loc_1800284D9
0x1800283c0  mov     r8, [rsp+4A0h+bstrString]
0x1800283c5  test    r8, r8
0x1800283c8  jz      loc_1800284D9
0x1800283ce  mov     ecx, 7FFFFFFFh
0x1800283d3  mov     rax, r8
0x1800283d6  mov     edx, ecx
0x1800283d8  cmp     [rax], si
0x1800283db  jz      short loc_1800283E7
0x1800283dd  add     rax, 2
0x1800283e1  sub     rdx, 1
0x1800283e5  jnz     short loc_1800283D8
0x1800283e7  mov     rax, rdx
0x1800283ea  neg     rax
0x1800283ed  mov     rax, rdx
0x1800283f0  sbb     ebx, ebx
0x1800283f2  sub     rcx, rdx
0x1800283f5  not     ebx
0x1800283f7  and     ebx, 80070057h
0x1800283fd  neg     rax
0x180028400  sbb     rsi, rsi
0x180028403  xor     edi, edi
0x180028405  and     rsi, rcx
0x180028408  test    rdx, rdx
0x18002840b  jz      loc_1800284C8
0x180028411  lea     eax, [rdi+1Fh]
0x180028414  mov     edx, 100h
0x180028419  lea     rcx, aUrnSchemasUpnp_1; "urn:schemas-upnp-org:service-1-"
0x180028420  lea     r9, [rsp+4A0h+String2]
0x180028425  test    rax, rax
0x180028428  jz      short loc_180028449
0x18002842a  movzx   r10d, word ptr [rcx]
0x18002842e  test    r10w, r10w
0x180028432  jz      short loc_180028449
0x180028434  mov     [r9], r10w
0x180028438  add     rcx, 2
0x18002843c  add     r9, 2
0x180028440  dec     rax
0x180028443  sub     rdx, 1
0x180028447  jnz     short loc_180028425
0x180028449  mov     rax, rdx
0x18002844c  lea     rcx, [r9-2]
0x180028450  neg     rax
0x180028453  mov     r11d, 8007007Ah
0x180028459  sbb     ebx, ebx
0x18002845b  not     ebx
0x18002845d  and     ebx, r11d
0x180028460  test    rdx, rdx
0x180028463  cmovnz  rcx, r9
0x180028467  mov     [rcx], di
0x18002846a  jz      short loc_1800284C8
0x18002846c  mov     ecx, 1Fh
0x180028471  lea     rax, [rbp+3A0h+String1]
0x180028478  mov     r9, r8
0x18002847b  mov     edx, 100h
0x180028480  test    rcx, rcx
0x180028483  jz      short loc_1800284A4
0x180028485  movzx   r10d, word ptr [r9]
0x180028489  test    r10w, r10w
0x18002848d  jz      short loc_1800284A4
0x18002848f  mov     [rax], r10w
0x180028493  add     r9, 2
0x180028497  add     rax, 2
0x18002849b  dec     rcx
0x18002849e  sub     rdx, 1
0x1800284a2  jnz     short loc_180028480
0x1800284a4  test    rdx, rdx
0x1800284a7  lea     rcx, [rax-2]
0x1800284ab  cmovnz  rcx, rax
0x1800284af  mov     rax, rdx
0x1800284b2  neg     rax
0x1800284b5  sbb     ebx, ebx
0x1800284b7  not     ebx
0x1800284b9  mov     [rcx], di
0x1800284bc  and     ebx, r11d
0x1800284bf  test    rdx, rdx
0x1800284c2  jnz     loc_18002863C
0x1800284c8  xor     esi, esi
0x1800284ca  mov     rcx, r8; bstrString
0x1800284cd  call    cs:__imp_SysFreeString
0x1800284d4  nop     dword ptr [rax+rax+00h]
0x1800284d9  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x1800284de  call    cs:__imp_SysFreeString
0x1800284e5  nop     dword ptr [rax+rax+00h]
0x1800284ea  test    ebx, ebx
0x1800284ec  jnz     loc_180028746
0x1800284f2  test    r14d, r14d
0x1800284f5  jz      short loc_18002856E
0x1800284f7  mov     rcx, [rsp+4A0h+var_460]
0x1800284fc  lea     rdx, [rsp+4A0h+var_470]
0x180028501  mov     [rsp+4A0h+var_470], rsi
0x180028506  inc     r15d
0x180028509  mov     rax, [rcx]
0x18002850c  mov     rax, [rax+0D0h]
0x180028513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028518  mov     ebx, eax
0x18002851a  test    eax, eax
0x18002851c  js      loc_18002830F
0x180028522  mov     rcx, [rsp+4A0h+var_470]; bstrString
0x180028527  call    cs:__imp_SysFreeString
0x18002852e  nop     dword ptr [rax+rax+00h]
0x180028533  jmp     short loc_18002856E
0x180028535  mov     rcx, [rsp+4A0h+var_470]; lpString1
0x18002853a  lea     rdx, a1; "1"
0x180028541  call    cs:__imp_lstrcmpW
0x180028548  nop     dword ptr [rax+rax+00h]
0x18002854d  test    eax, eax
0x18002854f  jnz     loc_18002872B
  ... truncated ...
```
