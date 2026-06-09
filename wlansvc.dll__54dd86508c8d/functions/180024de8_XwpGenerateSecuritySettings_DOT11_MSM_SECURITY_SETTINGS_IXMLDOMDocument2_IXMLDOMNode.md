# XwpGenerateSecuritySettings(_DOT11_MSM_SECURITY_SETTINGS *,IXMLDOMDocument2 *,IXMLDOMNode *)

- ea: `0x180024de8`
- end: `0x180025670`
- name: `?XwpGenerateSecuritySettings@@YAKPEAU_DOT11_MSM_SECURITY_SETTINGS@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z`
- size: `2184`
- prototype: `unsigned int(struct _DOT11_MSM_SECURITY_SETTINGS *, struct IXMLDOMDocument2 *, struct IXMLDOMNode *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800258d8`

## callees

- `0x180024930`
- `0x180024de8`
- `0x1800263d0`
- `0x180026490`
- `0x180026e60`
- `0x1800804d0`
- `0x180080700`
- `0x18022c010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x180024e41`
- `OLEAUT32!__imp_SysAllocString` at `0x18002507e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002514c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252af`
- `OLEAUT32!__imp_SysAllocString` at `0x1800253c2`
- `OLEAUT32!__imp_SysAllocString` at `0x180024e41`
- `OLEAUT32!__imp_SysAllocString` at `0x18002507e`
- `OLEAUT32!__imp_SysAllocString` at `0x18002514c`
- `OLEAUT32!__imp_SysAllocString` at `0x1800252af`
- `OLEAUT32!__imp_SysAllocString` at `0x1800253c2`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e34`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e55`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ec5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025075`
- `OLEAUT32!__imp_SysFreeString` at `0x180025092`
- `OLEAUT32!__imp_SysFreeString` at `0x1800250c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025143`
- `OLEAUT32!__imp_SysFreeString` at `0x180025160`
- `OLEAUT32!__imp_SysFreeString` at `0x180025193`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180025405`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e34`
- `OLEAUT32!__imp_SysFreeString` at `0x180024e55`
- `OLEAUT32!__imp_SysFreeString` at `0x180024ec5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025075`
- `OLEAUT32!__imp_SysFreeString` at `0x180025092`
- `OLEAUT32!__imp_SysFreeString` at `0x1800250c5`
- `OLEAUT32!__imp_SysFreeString` at `0x180025143`
- `OLEAUT32!__imp_SysFreeString` at `0x180025160`
- `OLEAUT32!__imp_SysFreeString` at `0x180025193`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252a6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252c3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800252f6`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253b9`
- `OLEAUT32!__imp_SysFreeString` at `0x1800253d6`
- `OLEAUT32!__imp_SysFreeString` at `0x180025405`

## string_xrefs

- `0x180024f3b`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180024f76`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x18002501c`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800250a6`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180025174`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800251e6`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x1800252d7`: `http://www.microsoft.com/networking/WLAN/profile/v1`
- `0x180024f7d`: `security`
- `0x1800253ed`: `PMKCacheMode`
- `0x180025437`: `PMKCacheTTL`
- `0x180025522`: `http://www.microsoft.com/networking/WLAN/profile/v2`
- `0x180025547`: `http://www.microsoft.com/networking/WLAN/profile/v4`
- `0x1800255b4`: `PMKCacheSize`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall XwpGenerateSecuritySettings(
        struct _DOT11_MSM_SECURITY_SETTINGS *a1,
        struct IXMLDOMDocument2 *a2,
        struct IXMLDOMNode *a3)
{
  struct IXMLDOMNode *v4; // rsi
  __int64 v5; // r13
  __int64 v6; // rbx
  int v7; // r14d
  OLECHAR *v8; // rdi
  int v9; // eax
  unsigned int SharedKey; // r15d
  int v11; // eax
  __int64 v12; // rcx
  int v13; // eax
  struct IXMLDOMNode *v14; // rdx
  struct IXMLDOMDocument2 *v15; // r12
  unsigned int v16; // r11d
  __int64 *v17; // r10
  struct IXMLDOMNode *v18; // rdi
  __int64 v19; // r14
  int v20; // r9d
  int v21; // r8d
  __int64 i; // rbx
  int v23; // edx
  unsigned int v24; // eax
  unsigned __int16 *v25; // rbx
  const OLECHAR *v26; // rbx
  unsigned __int16 *v27; // rbx
  unsigned int v28; // eax
  bool v29; // zf
  const OLECHAR *v30; // rbx
  unsigned __int16 *v31; // rbx
  const OLECHAR *v33; // rbx
  unsigned int v34; // eax
  unsigned __int16 *v35; // rbx
  unsigned int v36; // eax
  const OLECHAR *v37; // rbx
  struct _ONEX_CONNECTION_PROFILE *v38; // rcx
  struct IXMLDOMNode **v39; // [rsp+28h] [rbp-38h]
  struct IXMLDOMNode **v40; // [rsp+38h] [rbp-28h]
  __int64 v41; // [rsp+40h] [rbp-20h] BYREF
  struct IXMLDOMNode *v42; // [rsp+48h] [rbp-18h] BYREF
  struct IXMLDOMNode *v43; // [rsp+50h] [rbp-10h] BYREF
  struct IXMLDOMNode *v44; // [rsp+58h] [rbp-8h] BYREF
  int v47; // [rsp+B8h] [rbp+58h] BYREF

  v42 = 0;
  v4 = 0;
  v44 = 0;
  v5 = *(_QWORD *)a1;
  if ( !*(_QWORD *)a1 )
  {
    SharedKey = 0;
    goto LABEL_69;
  }
  v6 = 0;
  v7 = 0;
  v41 = 0;
  v47 = 0;
  SysFreeString(0);
  v8 = SysAllocString(L"WLANProfile:MSM");
  if ( !v8 )
  {
    v8 = 0;
    SharedKey = 14;
    goto LABEL_105;
  }
  SysFreeString(0);
  v9 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, __int64 *))a3->lpVtbl->selectNodes)(a3, v8, &v41);
  SharedKey = v9;
  if ( v9 < 0 )
  {
    if ( (v9 & 0x1FFF0000) == 0x70000 )
      SharedKey = (unsigned __int16)v9;
    if ( SharedKey )
      goto LABEL_105;
  }
  v11 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v41 + 64LL))(v41, &v47);
  SharedKey = v11;
  if ( v11 < 0 )
  {
    if ( (v11 & 0x1FFF0000) == 0x70000 )
      SharedKey = (unsigned __int16)v11;
    if ( !SharedKey )
      goto LABEL_6;
LABEL_105:
    v12 = v41;
    goto LABEL_7;
  }
  SharedKey = 0;
LABEL_6:
  v6 = v41;
  v12 = 0;
  v41 = 0;
  v7 = v47;
LABEL_7:
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  SysFreeString(v8);
  if ( !SharedKey )
  {
    if ( v7 <= 0 )
    {
      SharedKey = 1168;
    }
    else if ( v7 > 1 )
    {
      SharedKey = 1206;
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)v6 + 56LL))(v6, 0, &v42);
      SharedKey = v13;
      if ( v13 < 0 )
      {
        if ( (v13 & 0x1FFF0000) == 0x70000 )
          SharedKey = (unsigned __int16)v13;
      }
      else
      {
        SharedKey = 0;
      }
    }
  }
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  if ( SharedKey == 1168 )
  {
    v14 = a3;
    v15 = a2;
    SharedKey = XcAddChildElement(a2, v14, L"MSM", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v42);
  }
  else
  {
    v15 = a2;
  }
  if ( SharedKey )
    goto LABEL_69;
  SharedKey = XcAddChildElement(v15, v42, L"security", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v44);
  v4 = v44;
  if ( SharedKey )
    goto LABEL_69;
  v16 = *(_DWORD *)(v5 + 16);
  if ( !v16 )
    goto LABEL_65;
  v17 = *(__int64 **)(v5 + 24);
  if ( !v17 )
    goto LABEL_65;
  v18 = 0;
  v43 = 0;
  LOBYTE(v47) = 0;
  v19 = *v17;
  v41 = *v17;
  if ( v16 == 1 )
    goto LABEL_31;
  v20 = 0;
  v21 = 0;
  for ( i = 0; (unsigned int)i < v16; i = (unsigned int)(i + 1) )
  {
    v23 = v17[i];
    if ( v23 == 6 || LODWORD(v17[i]) == 7 )
    {
      if ( !v21 )
      {
        v21 = v17[i];
        continue;
      }
      v29 = v21 == v23;
    }
    else
    {
      if ( LODWORD(v17[i]) != 8 && LODWORD(v17[i]) != 9 && (unsigned int)(LODWORD(v17[i]) - 10) > 1 )
        goto LABEL_47;
      if ( !v20 )
      {
        v20 = v17[i];
        v19 = v17[i];
        v41 = v19;
        continue;
      }
      v29 = v20 == v23;
    }
    if ( !v29 )
      goto LABEL_47;
  }
  if ( v20 && v21 )
  {
    if ( v20 != 9 || v21 != 7 )
    {
LABEL_47:
      SharedKey = 1206;
      goto LABEL_55;
    }
    LOBYTE(v47) = 1;
  }
LABEL_31:
  v24 = XcAddChildElement(v15, v44, L"authEncryption", L"http://www.microsoft.com/networking/WLAN/profile/v1", 0, &v43);
  SharedKey = v24;
  if ( v24 )
  {
    v18 = v43;
  }
  else
  {
    v25 = 0;
    SharedKey = 1206;
    while ( 1 )
    {
      v18 = v43;
      if ( v24 >= 0xB )
        break;
      if ( dword_1802397F8[4 * v24] == (_DWORD)v19 )
      {
        v26 = (&off_1802397F0)[2 * v24];
        SysFreeString(0);
        v25 = SysAllocString(v26);
        if ( v25 )
        {
          SysFreeString(0);
          SharedKey = XcAddChildElement(
                        v15,
                        v18,
                        L"authentication",
                        L"http://www.microsoft.com/networking/WLAN/profile/v1",
                        v25,
                        0);
        }
        else
        {
          v25 = 0;
          SharedKey = 14;
        }
        break;
      }
      ++v24;
    }
    SysFreeString(v25);
    if ( !SharedKey )
    {
      v27 = 0;
      SharedKey = 1206;
      v28 = 0;
      if ( (_DWORD)v19 == 8 )
      {
        while ( !v28 )
        {
          if ( HIDWORD(v41) == 9 )
          {
            v33 = L"GCMP256";
            goto LABEL_75;
          }
          v28 = 1;
        }
      }
      else
      {
        while ( v28 < 7 )
        {
          if ( dword_180239748[4 * v28] == HIDWORD(v41) )
          {
            v33 = (&off_180239740)[2 * v28];
LABEL_75:
            SysFreeString(0);
            v27 = SysAllocString(v33);
            if ( v27 )
            {
              SysFreeString(0);
              SharedKey = XcAddChildElement(
                            v15,
                            v18,
                            L"encryption",
                            L"http://www.microsoft.com/networking/WLAN/profile/v1",
                            v27,
                            0);
            }
            else
            {
              v27 = 0;
              SharedKey = 14;
            }
            break;
          }
          ++v28;
        }
      }
      SysFreeString(v27);
      if ( !SharedKey )
      {
        v31 = 0;
        v34 = 0;
        SharedKey = 1206;
        while ( v34 < 4 )
        {
          if ( dword_18022D008[4 * v34] == (*(_DWORD *)(v5 + 32) != 0) )
          {
            v30 = (&off_18022D000)[2 * v34];
            SysFreeString(0);
            v31 = SysAllocString(v30);
            if ( v31 )
            {
              SysFreeString(0);
              SharedKey = XcAddChildElement(
                            v15,
                            v18,
                            L"useOneX",
                            L"http://www.microsoft.com/networking/WLAN/profile/v1",
                            v31,
                            0);
            }
            else
            {
              v31 = 0;
              SharedKey = 14;
            }
            break;
          }
          ++v34;
        }
        SysFreeString(v31);
        if ( (*(_DWORD *)v5 & 0x1000) != 0 )
          SharedKey = XcAddChildElementBoolean(
                        v15,
                        v18,
                        L"FIPSMode",
                        L"http://www.microsoft.com/networking/WLAN/profile/v2",
                        1,
                        v39);
        if ( (_BYTE)v47 )
          SharedKey = XcAddChildElementBoolean(
                        v15,
                        v18,
                        L"transitionMode",
                        L"http://www.microsoft.com/networking/WLAN/profile/v4",
                        (unsigned __int8)v47,
                        v39);
      }
    }
  }
LABEL_55:
  if ( v18 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v18->lpVtbl->Release)(v18);
  if ( !SharedKey )
  {
    SharedKey = XwpGenerateSharedKey((struct DOT11_MSMSEC_CONNECTION_PROFILE *)v5, v15, v4);
    if ( !SharedKey
      && ((*(_BYTE *)v5 & 4) == 0
       || (SharedKey = XcAddChildElementDWORD(
                         v15,
                         v4,
                         L"keyIndex",
                         L"http://www.microsoft.com/networking/WLAN/profile/v1",
                         *(_DWORD *)(v5 + 56),
                         v39)) == 0) )
    {
      if ( (*(_BYTE *)v5 & 0x20) == 0 )
        goto LABEL_138;
      v35 = 0;
      v36 = 0;
      SharedKey = 1206;
      while ( v36 < 2 )
      {
        if ( dword_180239718[4 * v36] == *(_DWORD *)(v5 + 112) )
        {
          v37 = (&off_180239710)[2 * v36];
          SysFreeString(0);
          v35 = SysAllocString(v37);
          if ( v35 )
          {
            SysFreeString(0);
            SharedKey = XcAddChildElement(
                          v15,
                          v4,
                          L"PMKCacheMode",
                          L"http://www.microsoft.com/networking/WLAN/profile/v1",
                          v35,
                          0);
          }
          else
          {
            v35 = 0;
            SharedKey = 14;
          }
          break;
        }
        ++v36;
      }
      SysFreeString(v35);
      if ( !SharedKey )
      {
LABEL_138:
        if ( (*(char *)v5 >= 0
           || (SharedKey = XcAddChildElementDWORD(
                             v15,
                             v4,
                             L"PMKCacheTTL",
                             L"http://www.microsoft.com/networking/WLAN/profile/v1",
                             *(_DWORD *)(v5 + 120) / 0x3Cu,
                             v39)) == 0)
          && ((*(_BYTE *)v5 & 0x40) == 0
           || (SharedKey = XcAddChildElementDWORD(
                             v15,
                             v4,
                             L"PMKCacheSize",
                             L"http://www.microsoft.com/networking/WLAN/profile/v1",
                             *(_DWORD *)(v5 + 116),
                             v39)) == 0)
          && ((*(_BYTE *)v5 & 8) == 0
           || (SharedKey = XcAddChildElementEnum(
                             v15,
                             v4,
                             L"preAuthMode",
                             L"http://www.microsoft.com/networking/WLAN/profile/v1",
                             *(_DWORD *)(v5 + 104),
                             (const struct _XC_STRING_VALUE_MAPPING *)&off_1802397B0,
                             2u,
                             v40)) == 0)
          && ((*(_BYTE *)v5 & 0x10) == 0
           || (SharedKey = XcAddChildElementDWORD(
                             v15,
                             v4,
                             L"preAuthThrottle",
                             L"http://www.microsoft.com/networking/WLAN/profile/v1",
                             *(_DWORD *)(v5 + 108),
                             v39)) == 0) )
        {
LABEL_65:
          if ( *(_DWORD *)(v5 + 16) && *(_QWORD *)(v5 + 24) && *(_DWORD *)(v5 + 32) || *((_DWORD *)a1 + 3) )
          {
            if ( *(_DWORD *)(v5 + 40) )
            {
              v38 = *(struct _ONEX_CONNECTION_PROFILE **)(v5 + 48);
              if ( v38 )
                SharedKey = XoGenerateOnexProfile(v38, v15, v4);
            }
          }
        }
      }
    }
  }
LABEL_69:
  if ( v4 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v4->lpVtbl->Release)(v4);
  if ( v42 )
    ((void (__fastcall *)(struct IXMLDOMNode *))v42->lpVtbl->Release)(v42);
  return SharedKey;
}

```

## disassembly

```asm
0x180024de8  mov     [rsp-38h+arg_10], rbx
0x180024ded  mov     [rsp-38h+arg_8], rdx
0x180024df2  mov     [rsp-38h+arg_0], rcx
0x180024df7  push    rbp
0x180024df8  push    rsi
0x180024df9  push    rdi
0x180024dfa  push    r12
0x180024dfc  push    r13
0x180024dfe  push    r14
0x180024e00  push    r15
0x180024e02  mov     rbp, rsp
0x180024e05  sub     rsp, 60h
0x180024e09  mov     r12, r8
0x180024e0c  mov     [rbp+var_18], 0
0x180024e14  xor     esi, esi
0x180024e16  mov     [rbp+var_8], rsi
0x180024e1a  mov     r13, [rcx]
0x180024e1d  test    r13, r13
0x180024e20  jz      loc_18002535D
0x180024e26  xor     ebx, ebx
0x180024e28  xor     r14d, r14d
0x180024e2b  mov     [rbp+var_20], rbx
0x180024e2f  mov     [rbp+arg_18], ebx
0x180024e32  xor     ecx, ecx; bstrString
0x180024e34  call    cs:__imp_SysFreeString
0x180024e3a  lea     rcx, aWlanprofileMsm_1; "WLANProfile:MSM"
0x180024e41  call    cs:__imp_SysAllocString
0x180024e47  mov     rdi, rax
0x180024e4a  test    rax, rax
0x180024e4d  jz      loc_1800254A2
0x180024e53  xor     ecx, ecx; bstrString
0x180024e55  call    cs:__imp_SysFreeString
0x180024e5b  mov     rax, [r12]
0x180024e5f  lea     r8, [rbp+var_20]
0x180024e63  mov     rdx, rdi
0x180024e66  mov     rcx, r12
0x180024e69  mov     rax, [rax+120h]
0x180024e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e75  mov     r15d, eax
0x180024e78  test    eax, eax
0x180024e7a  js      loc_18002547E
0x180024e80  mov     rcx, [rbp+var_20]
0x180024e84  mov     rax, [rcx]
0x180024e87  lea     rdx, [rbp+arg_18]
0x180024e8b  mov     rax, [rax+40h]
0x180024e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024e94  mov     r15d, eax
0x180024e97  test    eax, eax
0x180024e99  js      loc_180025490
0x180024e9f  xor     r15d, r15d
0x180024ea2  mov     rbx, [rbp+var_20]
0x180024ea6  xor     ecx, ecx
0x180024ea8  mov     [rbp+var_20], rcx
0x180024eac  mov     r14d, [rbp+arg_18]
0x180024eb0  test    rcx, rcx
0x180024eb3  jz      short loc_180024EC2
0x180024eb5  mov     rax, [rcx]
0x180024eb8  mov     rax, [rax+10h]
0x180024ebc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024ec1  nop
0x180024ec2  mov     rcx, rdi; bstrString
0x180024ec5  call    cs:__imp_SysFreeString
0x180024ecb  mov     edi, 490h
0x180024ed0  test    r15d, r15d
0x180024ed3  jnz     short loc_180024F0B
0x180024ed5  test    r14d, r14d
0x180024ed8  jle     loc_180025119
0x180024ede  cmp     r14d, 1
0x180024ee2  jg      loc_180025419
0x180024ee8  mov     rax, [rbx]
0x180024eeb  lea     r8, [rbp+var_18]
0x180024eef  xor     edx, edx
0x180024ef1  mov     rcx, rbx
0x180024ef4  mov     rax, [rax+38h]
0x180024ef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024efd  mov     r15d, eax
0x180024f00  test    eax, eax
0x180024f02  js      loc_1800254AA
0x180024f08  xor     r15d, r15d
0x180024f0b  test    rbx, rbx
0x180024f0e  jz      short loc_180024F20
0x180024f10  mov     rax, [rbx]
0x180024f13  mov     rcx, rbx
0x180024f16  mov     rax, [rax+10h]
0x180024f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f1f  nop
0x180024f20  cmp     r15d, edi
0x180024f23  jnz     loc_180025459
0x180024f29  lea     rax, [rbp+var_18]
0x180024f2d  mov     [rsp+60h+var_38], rax; struct IXMLDOMNode **
0x180024f32  mov     [rsp+60h+var_40], 0; unsigned __int16 *
0x180024f3b  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180024f42  lea     r8, aMsm; "MSM"
0x180024f49  mov     rdx, r12; struct IXMLDOMNode *
0x180024f4c  mov     r12, [rbp+arg_8]
0x180024f50  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180024f53  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180024f58  mov     r15d, eax
0x180024f5b  test    r15d, r15d
0x180024f5e  jnz     loc_180025256
0x180024f64  lea     rax, [rbp+var_8]
0x180024f68  mov     [rsp+60h+var_38], rax; struct IXMLDOMNode **
0x180024f6d  mov     [rsp+60h+var_40], 0; unsigned __int16 *
0x180024f76  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180024f7d  lea     r8, aSecurity; "security"
0x180024f84  mov     rdx, [rbp+var_18]; struct IXMLDOMNode *
0x180024f88  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180024f8b  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180024f90  mov     r15d, eax
0x180024f93  mov     rsi, [rbp+var_8]
0x180024f97  test    eax, eax
0x180024f99  jnz     loc_180025256
0x180024f9f  mov     r11d, [r13+10h]
0x180024fa3  test    r11d, r11d
0x180024fa6  jz      loc_18002522F
0x180024fac  mov     r10, [r13+18h]
0x180024fb0  test    r10, r10
0x180024fb3  jz      loc_18002522F
0x180024fb9  xor     edi, edi
0x180024fbb  mov     [rbp+var_10], rdi
0x180024fbf  mov     byte ptr [rbp+arg_18], dil
0x180024fc3  mov     r14, [r10]
0x180024fc6  mov     [rbp+var_20], r14
0x180024fca  cmp     r11d, 1
0x180024fce  jz      short loc_18002500A
0x180024fd0  xor     r9d, r9d
0x180024fd3  xor     r8d, r8d
0x180024fd6  xor     ebx, ebx
0x180024fd8  cmp     ebx, r11d
0x180024fdb  jnb     short loc_180025001
0x180024fdd  mov     edx, [r10+rbx*8]
0x180024fe1  mov     ecx, edx
0x180024fe3  sub     ecx, 6
0x180024fe6  jz      short loc_180024FF1
0x180024fe8  sub     ecx, 1
0x180024feb  jnz     loc_180025365
0x180024ff1  test    r8d, r8d
0x180024ff4  jnz     loc_18002510E
0x180024ffa  mov     r8d, edx
0x180024ffd  inc     ebx
0x180024fff  jmp     short loc_180024FD8
0x180025001  test    r9d, r9d
0x180025004  jnz     loc_1800254D3
0x18002500a  lea     rax, [rbp+var_10]
0x18002500e  mov     [rsp+60h+var_38], rax; struct IXMLDOMNode **
0x180025013  mov     [rsp+60h+var_40], 0; unsigned __int16 *
0x18002501c  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x180025023  lea     r8, aAuthencryption; "authEncryption"
0x18002502a  mov     rdx, rsi; struct IXMLDOMNode *
0x18002502d  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025030  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x180025035  mov     r15d, eax
0x180025038  test    eax, eax
0x18002503a  jnz     loc_180025568
0x180025040  xor     ebx, ebx
0x180025042  mov     r15d, 4B6h
0x180025048  lea     rdx, __ImageBase
0x18002504f  mov     rdi, [rbp+var_10]
0x180025053  cmp     eax, 0Bh
0x180025056  jnb     short loc_1800250C2
0x180025058  mov     ecx, eax
0x18002505a  add     rcx, rcx
0x18002505d  cmp     ds:rva dword_1802397F8[rdx+rcx*8], r14d
0x180025065  jz      short loc_18002506B
0x180025067  inc     eax
0x180025069  jmp     short loc_18002504F
0x18002506b  mov     rbx, ds:rva off_1802397F0[rdx+rcx*8]; "open" ...
0x180025073  xor     ecx, ecx; bstrString
0x180025075  call    cs:__imp_SysFreeString
0x18002507b  mov     rcx, rbx; psz
0x18002507e  call    cs:__imp_SysAllocString
0x180025084  mov     rbx, rax
0x180025087  test    rax, rax
0x18002508a  jz      loc_1800254F9
0x180025090  xor     ecx, ecx; bstrString
0x180025092  call    cs:__imp_SysFreeString
0x180025098  mov     [rsp+60h+var_38], 0; struct IXMLDOMNode **
0x1800250a1  mov     [rsp+60h+var_40], rbx; unsigned __int16 *
0x1800250a6  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x1800250ad  lea     r8, aAuthentication; "authentication"
0x1800250b4  mov     rdx, rdi; struct IXMLDOMNode *
0x1800250b7  mov     rcx, r12; struct IXMLDOMDocument2 *
0x1800250ba  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x1800250bf  mov     r15d, eax
0x1800250c2  mov     rcx, rbx; bstrString
0x1800250c5  call    cs:__imp_SysFreeString
0x1800250cb  test    r15d, r15d
0x1800250ce  jnz     short loc_180025130
0x1800250d0  mov     edx, dword ptr [rbp+var_20+4]
0x1800250d3  xor     ebx, ebx
0x1800250d5  mov     r15d, 4B6h
0x1800250db  xor     eax, eax
0x1800250dd  cmp     r14d, 8
0x1800250e1  lea     r14, __ImageBase
0x1800250e8  jnz     loc_180025338
0x1800250ee  cmp     eax, 1
0x1800250f1  jnb     loc_1800252F3
0x1800250f7  mov     ecx, eax
0x1800250f9  add     rcx, rcx
0x1800250fc  cmp     ds:rva dword_180239738[r14+rcx*8], edx
0x180025104  jz      loc_18002529C
0x18002510a  inc     eax
0x18002510c  jmp     short loc_1800250EE
0x18002510e  cmp     r8d, edx
0x180025111  jz      loc_180024FFD
0x180025117  jmp     short loc_18002512A
0x180025119  mov     r15d, edi
0x18002511c  jmp     loc_180024F0B
0x180025121  cmp     ecx, 1
0x180025124  jz      loc_180025378
0x18002512a  mov     r15d, 4B6h
0x180025130  lea     r14, __ImageBase
0x180025137  jmp     short loc_1800251B3
0x180025139  mov     rbx, ds:rva off_18022D000[r14+rcx*8]; "true" ...
0x180025141  xor     ecx, ecx; bstrString
0x180025143  call    cs:__imp_SysFreeString
0x180025149  mov     rcx, rbx; psz
0x18002514c  call    cs:__imp_SysAllocString
0x180025152  mov     rbx, rax
0x180025155  test    rax, rax
0x180025158  jz      loc_18002550F
0x18002515e  xor     ecx, ecx; bstrString
0x180025160  call    cs:__imp_SysFreeString
0x180025166  mov     [rsp+60h+var_38], 0; struct IXMLDOMNode **
0x18002516f  mov     [rsp+60h+var_40], rbx; unsigned __int16 *
0x180025174  lea     r9, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x18002517b  lea     r8, aUseonex; "useOneX"
0x180025182  mov     rdx, rdi; struct IXMLDOMNode *
0x180025185  mov     rcx, r12; struct IXMLDOMDocument2 *
0x180025188  call    ?XcAddChildElement@@YAKPEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@PEBG22PEAPEAU2@@Z; XcAddChildElement(IXMLDOMDocument2 *,IXMLDOMNode *,ushort const *,ushort const *,ushort const *,IXMLDOMNode * *)
0x18002518d  mov     r15d, eax
0x180025190  mov     rcx, rbx; bstrString
0x180025193  call    cs:__imp_SysFreeString
0x180025199  test    dword ptr [r13+0], 1000h
0x1800251a1  jnz     loc_18002551A
0x1800251a7  movzx   eax, byte ptr [rbp+arg_18]
0x1800251ab  test    al, al
0x1800251ad  jnz     loc_180025543
0x1800251b3  test    rdi, rdi
0x1800251b6  jz      short loc_1800251C8
0x1800251b8  mov     rax, [rdi]
0x1800251bb  mov     rcx, rdi
0x1800251be  mov     rax, [rax+10h]
0x1800251c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800251c7  nop
0x1800251c8  test    r15d, r15d
0x1800251cb  jnz     loc_180025256
0x1800251d1  mov     r8, rsi; struct IXMLDOMNode *
0x1800251d4  mov     rdx, r12; struct IXMLDOMDocument2 *
0x1800251d7  mov     rcx, r13; struct DOT11_MSMSEC_CONNECTION_PROFILE *
0x1800251da  call    ?XwpGenerateSharedKey@@YAKPEAUDOT11_MSMSEC_CONNECTION_PROFILE@@PEAUIXMLDOMDocument2@@PEAUIXMLDOMNode@@@Z; XwpGenerateSharedKey(DOT11_MSMSEC_CONNECTION_PROFILE *,IXMLDOMDocument2 *,IXMLDOMNode *)
0x1800251df  mov     r15d, eax
0x1800251e2  test    eax, eax
0x1800251e4  jnz     short loc_180025256
0x1800251e6  lea     rdi, aHttpWwwMicroso_7; "http://www.microsoft.com/networking/WLA"...
0x1800251ed  test    byte ptr [r13+0], 4
0x1800251f2  jnz     loc_180025571
0x1800251f8  test    byte ptr [r13+0], 20h
0x1800251fd  jnz     loc_180025389
0x180025203  test    byte ptr [r13+0], 80h
0x180025208  jnz     loc_180025424
0x18002520e  test    byte ptr [r13+0], 40h
0x180025213  jnz     loc_1800255A9
0x180025219  test    byte ptr [r13+0], 8
0x18002521e  jnz     loc_1800255D6
0x180025224  test    byte ptr [r13+0], 10h
0x180025229  jnz     loc_180025617
0x18002522f  cmp     dword ptr [r13+10h], 0
0x180025234  jz      short loc_180025248
0x180025236  cmp     qword ptr [r13+18h], 0
0x18002523b  jz      short loc_180025248
0x18002523d  cmp     dword ptr [r13+20h], 0
0x180025242  jnz     loc_180025644
0x180025248  mov     rax, [rbp+arg_0]
0x18002524c  cmp     dword ptr [rax+0Ch], 0
0x180025250  jnz     loc_180025644
0x180025256  test    rsi, rsi
0x180025259  jz      short loc_18002526B
0x18002525b  mov     rax, [rsi]
0x18002525e  mov     rcx, rsi
0x180025261  mov     rax, [rax+10h]
0x180025265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002526a  nop
0x18002526b  mov     rcx, [rbp+var_18]
0x18002526f  test    rcx, rcx
0x180025272  jz      short loc_180025281
0x180025274  mov     rax, [rcx]
0x180025277  mov     rax, [rax+10h]
0x18002527b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025280  nop
0x180025281  mov     eax, r15d
0x180025284  mov     rbx, [rsp+60h+arg_10]
0x18002528c  add     rsp, 60h
0x180025290  pop     r15
0x180025292  pop     r14
0x180025294  pop     r13
0x180025296  pop     r12
0x180025298  pop     rdi
0x180025299  pop     rsi
0x18002529a  pop     rbp
  ... truncated ...
```
