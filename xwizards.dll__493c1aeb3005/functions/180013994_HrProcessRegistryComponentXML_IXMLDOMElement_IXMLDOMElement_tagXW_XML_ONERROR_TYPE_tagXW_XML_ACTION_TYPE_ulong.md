# HrProcessRegistryComponentXML(IXMLDOMElement *,IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,tagXW_XML_ACTION_TYPE,ulong,int,ulong,void *,IXWizard *)

- ea: `0x180013994`
- end: `0x180014241`
- name: `?HrProcessRegistryComponentXML@@YAJPEAUIXMLDOMElement@@0W4tagXW_XML_ONERROR_TYPE@@W4tagXW_XML_ACTION_TYPE@@KHKPEAXPEAUIXWizard@@@Z`
- size: `2221`
- prototype: ``
- caller_count: `2`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180013994`
- `0x180014248`

## callees

- `0x18000addc`
- `0x18000ae04`
- `0x18000e1f4`
- `0x18000e560`
- `0x180012678`
- `0x1800127a0`
- `0x180013994`
- `0x18001a27c`
- `0x18001a2cc`
- `0x18001a308`
- `0x18001a4b4`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180013d6c`
- `msvcrt!wcstoul` at `0x180013dcc`
- `msvcrt!wcstoul` at `0x180013d6c`
- `msvcrt!wcstoul` at `0x180013dcc`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013a73`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013b43`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013a73`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x180013b43`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180013be7`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bf0`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bb5`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bbe`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bd3`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bdd`
- `OLEAUT32!__imp_SysFreeString` at `0x180013be7`
- `OLEAUT32!__imp_SysFreeString` at `0x180013bf0`

## string_xrefs

- `0x180013dda`: `commandline`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall HrProcessRegistryComponentXML(
        struct IXMLDOMElement *a1,
        struct IXMLDOMElement *a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6,
        int a7,
        __int64 a8,
        __int64 *a9)
{
  struct IXMLDOMElement *v9; // r14
  int v11; // esi
  struct IXMLDOMElement *v12; // r13
  int v13; // r15d
  HRESULT TagComponentType; // ebx
  unsigned int NamedAttributeValue; // ebx
  const OLECHAR *v16; // rdi
  unsigned int v17; // ebx
  const OLECHAR *v18; // rdi
  _QWORD *v19; // rcx
  __int64 v20; // rdx
  unsigned int v21; // esi
  OLECHAR *v22; // rdi
  OLECHAR *v23; // r15
  int v24; // edi
  unsigned int v25; // edi
  unsigned int v26; // r14d
  struct IXMLDOMElement *v27; // r13
  int v28; // eax
  PVOID *v29; // rcx
  HRESULT v30; // eax
  int v31; // eax
  PVOID *v32; // rcx
  __int64 v33; // rax
  GUID *p_pclsid; // rdx
  __int64 v35; // rax
  GUID *v36; // rdx
  __int64 v37; // rax
  bool v38; // zf
  LPCOLESTR lpsz; // [rsp+58h] [rbp-A8h] BYREF
  LPCOLESTR v42; // [rsp+60h] [rbp-A0h] BYREF
  int v43; // [rsp+68h] [rbp-98h] BYREF
  struct IXMLDOMElement *v44; // [rsp+70h] [rbp-90h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-88h] BYREF
  BSTR v46; // [rsp+80h] [rbp-80h] BYREF
  int v47; // [rsp+88h] [rbp-78h]
  struct IXMLDOMElement *v48; // [rsp+90h] [rbp-70h]
  int v49; // [rsp+98h] [rbp-68h] BYREF
  int v50; // [rsp+9Ch] [rbp-64h] BYREF
  unsigned int v51; // [rsp+A0h] [rbp-60h]
  BSTR String; // [rsp+A8h] [rbp-58h] BYREF
  BSTR v53; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v54; // [rsp+B8h] [rbp-48h]
  _BYTE v55[24]; // [rsp+C0h] [rbp-40h] BYREF
  GUID v56; // [rsp+D8h] [rbp-28h] BYREF
  GUID pclsid; // [rsp+E8h] [rbp-18h] BYREF

  v51 = a3;
  v9 = a2;
  v48 = a2;
  v54 = a8;
  v11 = 0;
  v49 = 0;
  v43 = 0;
  lpsz = 0;
  v42 = 0;
  bstrString = 0;
  v46 = 0;
  String = 0;
  v53 = 0;
  v12 = 0;
  v44 = 0;
  pclsid = 0;
  v56 = 0;
  v13 = 0;
  v50 = 0;
  v47 = 0;
  if ( a1 )
  {
    TagComponentType = HrGetTagComponentType(a1, (enum tagXW_COMPONENT_TYPE *)&v49);
    if ( TagComponentType < 0 )
    {
      v19 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
        goto LABEL_26;
      v20 = 31;
LABEL_25:
      WPP_SF_d(v19[2], v20, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, (unsigned int)TagComponentType);
LABEL_26:
      v21 = a4;
LABEL_27:
      v22 = (OLECHAR *)lpsz;
      v23 = (OLECHAR *)v42;
      goto LABEL_28;
    }
    NamedAttributeValue = HrGetNamedAttributeValue(a1, L"id", (unsigned __int16 **)&lpsz);
    if ( NamedAttributeValue || (v16 = lpsz, !(unsigned int)IsValidGUIDString((unsigned __int16 *)lpsz)) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          29,
          &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
          NamedAttributeValue);
      TagComponentType = -2147418113;
      goto LABEL_26;
    }
    TagComponentType = CLSIDFromString(v16, &pclsid);
    if ( TagComponentType < 0 )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          30,
          &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
          (unsigned int)TagComponentType);
      goto LABEL_26;
    }
    v11 = v49;
  }
  TagComponentType = HrGetTagComponentType(v9, (enum tagXW_COMPONENT_TYPE *)&v43);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 39;
    goto LABEL_25;
  }
  v17 = HrGetNamedAttributeValue(v9, L"id", (unsigned __int16 **)&v42);
  if ( v17 || (v18 = v42, !(unsigned int)IsValidGUIDString((unsigned __int16 *)v42)) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, v17);
    TagComponentType = -2147418113;
    goto LABEL_26;
  }
  TagComponentType = CLSIDFromString(v18, &v56);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 33;
    goto LABEL_25;
  }
  TagComponentType = HrGetNamedAttributeValue(v9, L"filename", &bstrString);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 34;
    goto LABEL_25;
  }
  TagComponentType = HrGetNamedAttributeValue(v9, L"name", &v46);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 35;
    goto LABEL_25;
  }
  TagComponentType = HrGetNamedAttributeValue(v9, L"behavior", &String);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 36;
    goto LABEL_25;
  }
  v25 = a5;
  if ( !TagComponentType )
    v25 = a5 | wcstoul(String, 0, 16);
  TagComponentType = HrGetNamedAttributeValue(v9, L"flags", &v53);
  if ( TagComponentType < 0 )
  {
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    v20 = 37;
    goto LABEL_25;
  }
  v26 = 0;
  if ( !TagComponentType )
    v26 = wcstoul(v53, 0, 16);
  v27 = v48;
  TagComponentType = HrGetNamedAttributeValue(v48, L"commandline", (unsigned __int16 **)&v44);
  if ( TagComponentType < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        38,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)TagComponentType);
    goto LABEL_56;
  }
  if ( !v11 )
  {
    TagComponentType = HrHasChildTags(v27, &v50);
    if ( TagComponentType < 0 )
    {
LABEL_56:
      v12 = v44;
      v9 = v48;
      goto LABEL_26;
    }
    v13 = v50;
  }
  v28 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64))(*a9 + 216))(a9, 303, v54);
  if ( v28 >= 0 )
    goto LABEL_64;
  v29 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      40,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)v28);
LABEL_64:
    v29 = (PVOID *)WPP_GLOBAL_Control;
  }
  v12 = v44;
  if ( v11 )
  {
    if ( v11 == 1 )
    {
      if ( v43 == 2 )
      {
        v33 = *a9;
        v21 = a4;
        p_pclsid = &pclsid;
        if ( a4 == 3 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *))(v33 + 80))(a9, &pclsid, &v56);
          goto LABEL_69;
        }
        goto LABEL_90;
      }
    }
    else if ( v11 == 2 )
    {
      if ( v43 == 3 )
      {
        v35 = *a9;
        v21 = a4;
        v36 = &pclsid;
        if ( a4 == 3 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *))(v35 + 88))(a9, &pclsid, &v56);
          goto LABEL_69;
        }
        goto LABEL_96;
      }
    }
    else if ( v11 == 3 && v43 == 3 )
    {
      v37 = *a9;
      v21 = a4;
      if ( a4 == 3 )
        v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *))(v37 + 96))(a9, &pclsid, &v56);
      else
        v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, BSTR, BSTR, unsigned int, unsigned int, struct IXMLDOMElement *))(v37 + 48))(
                a9,
                &pclsid,
                &v56,
                bstrString,
                v46,
                v25,
                v26,
                v44);
      goto LABEL_69;
    }
LABEL_112:
    TagComponentType = -2147418113;
    if ( v29 != &WPP_GLOBAL_Control && (*((_BYTE *)v29 + 28) & 8) != 0 )
      WPP_SF_d(v29[2], 41, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, 2147549183LL);
    v21 = a4;
    goto LABEL_70;
  }
  if ( v43 != 1 )
  {
    if ( v43 == 2 )
    {
      v21 = a4;
      if ( a4 == 3 )
      {
        if ( !v13 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD))(*a9 + 64))(a9, &v56, a6);
          goto LABEL_69;
        }
        goto LABEL_70;
      }
      v33 = *a9;
      p_pclsid = 0;
LABEL_90:
      v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, BSTR, BSTR, unsigned int, unsigned int, struct IXMLDOMElement *))(v33 + 32))(
              a9,
              p_pclsid,
              &v56,
              bstrString,
              v46,
              v25,
              v26,
              v44);
      goto LABEL_69;
    }
    if ( v43 == 3 )
    {
      v21 = a4;
      if ( a4 == 3 )
      {
        if ( !v13 )
        {
          v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD))(*a9 + 72))(a9, &v56, a6);
          goto LABEL_69;
        }
        goto LABEL_70;
      }
      v35 = *a9;
      v36 = 0;
LABEL_96:
      v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, GUID *, BSTR, BSTR, unsigned int, unsigned int, struct IXMLDOMElement *))(v35 + 40))(
              a9,
              v36,
              &v56,
              bstrString,
              v46,
              v25,
              v26,
              v44);
      goto LABEL_69;
    }
    goto LABEL_112;
  }
  v21 = a4;
  if ( a4 != 3 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, BSTR, BSTR, unsigned int))(*a9 + 24))(
            a9,
            &v56,
            bstrString,
            v46,
            v25);
LABEL_69:
    TagComponentType = v30;
    goto LABEL_70;
  }
  if ( !v13 )
  {
    v30 = (*(__int64 (__fastcall **)(__int64 *, GUID *, _QWORD))(*a9 + 56))(a9, &v56, a6);
    goto LABEL_69;
  }
LABEL_70:
  v31 = (*(__int64 (__fastcall **)(__int64 *, __int64, _QWORD))(*a9 + 216))(a9, 303, 0);
  if ( v31 >= 0 )
  {
LABEL_74:
    v32 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_75;
  }
  v32 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      42,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)v31);
    goto LABEL_74;
  }
LABEL_75:
  if ( TagComponentType >= 0 )
  {
    v9 = v48;
    goto LABEL_27;
  }
  v22 = (OLECHAR *)lpsz;
  v23 = (OLECHAR *)v42;
  if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x10) != 0 )
  {
    WPP_SF_SSD(
      (unsigned int)v32[2],
      43,
      (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (_DWORD)v42,
      (__int64)lpsz,
      TagComponentType);
    v32 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v51 == 2 )
  {
    if ( v32 != &WPP_GLOBAL_Control && (*((_BYTE *)v32 + 28) & 0x10) != 0 )
      WPP_SF_(v32[2], 44, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids);
    v47 = 1;
    TagComponentType = 0;
  }
  v9 = v48;
LABEL_28:
  SysFreeString(v22);
  SysFreeString(v23);
  SysFreeString(bstrString);
  SysFreeString(v46);
  SysFreeString(String);
  SysFreeString(v53);
  SysFreeString((BSTR)v12);
  if ( TagComponentType >= 0 )
  {
    CTagEnum::CTagEnum((CTagEnum *)v55, v9);
    v44 = 0;
    v24 = CTagEnum::HrNext((CTagEnum *)v55, &v44);
    if ( !v24 )
    {
      while ( 1 )
      {
        v24 = HrProcessRegistryComponentXML(v9, v44, v51, v21, a5, a6, a7, v54, a9);
        ((void (__fastcall *)(struct IXMLDOMElement *))v44->lpVtbl->Release)(v44);
        if ( v24 == 1 )
          break;
        v38 = v24 == 0;
        if ( v24 >= 0 )
          goto LABEL_125;
LABEL_126:
        if ( !v38 )
          goto LABEL_127;
      }
      v47 = 1;
LABEL_125:
      v24 = CTagEnum::HrNext((CTagEnum *)v55, &v44);
      v38 = v24 == 0;
      goto LABEL_126;
    }
LABEL_127:
    CTagEnum::~CTagEnum((CTagEnum *)v55);
    TagComponentType = 0;
    if ( v24 != 1 )
      TagComponentType = v24;
  }
  if ( v47 )
    TagComponentType = 1;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      45,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)TagComponentType);
  return (unsigned int)TagComponentType;
}

```

## disassembly

```asm
0x180013994  push    rbp
0x180013996  push    rbx
0x180013997  push    rsi
0x180013998  push    rdi
0x180013999  push    r12
0x18001399b  push    r13
0x18001399d  push    r14
0x18001399f  push    r15
0x1800139a1  lea     rbp, [rsp-8]
0x1800139a6  sub     rsp, 108h
0x1800139ad  mov     rax, cs:__security_cookie
0x1800139b4  xor     rax, rsp
0x1800139b7  mov     [rbp+40h+var_48], rax
0x1800139bb  mov     [rsp+140h+var_F0], r9d
0x1800139c0  mov     [rbp+40h+var_A0], r8d
0x1800139c4  mov     r14, rdx
0x1800139c7  mov     [rbp+40h+var_B0], rdx
0x1800139cb  mov     rdi, rcx
0x1800139ce  mov     rax, [rbp+40h+arg_38]
0x1800139d5  mov     [rbp+40h+var_88], rax
0x1800139d9  mov     r12, [rbp+40h+arg_40]
0x1800139e0  xor     eax, eax
0x1800139e2  mov     esi, eax
0x1800139e4  mov     [rbp+40h+var_A8], eax
0x1800139e7  mov     [rsp+140h+var_D8], eax
0x1800139eb  mov     [rsp+140h+lpsz], rax
0x1800139f0  mov     [rsp+140h+var_E0], rax
0x1800139f5  mov     [rsp+140h+bstrString], rax
0x1800139fa  mov     [rbp+40h+var_C0], rax
0x1800139fe  mov     [rbp+40h+String], rax
0x180013a02  mov     [rbp+40h+var_90], rax
0x180013a06  mov     r13d, eax
0x180013a09  mov     [rsp+140h+var_D0], rax
0x180013a0e  xorps   xmm0, xmm0
0x180013a11  movups  xmmword ptr [rbp+40h+pclsid.Data1], xmm0
0x180013a15  xorps   xmm1, xmm1
0x180013a18  movups  xmmword ptr [rbp+40h+var_68.Data1], xmm1
0x180013a1c  mov     r15d, eax
0x180013a1f  mov     [rbp+40h+var_A4], eax
0x180013a22  mov     [rbp+40h+var_B8], eax
0x180013a25  test    rcx, rcx
0x180013a28  jz      loc_180013AF2
0x180013a2e  lea     rdx, [rbp+40h+var_A8]; enum tagXW_COMPONENT_TYPE *
0x180013a32  call    ?HrGetTagComponentType@@YAJPEAUIXMLDOMElement@@PEAW4tagXW_COMPONENT_TYPE@@@Z; HrGetTagComponentType(IXMLDOMElement *,tagXW_COMPONENT_TYPE *)
0x180013a37  mov     ebx, eax
0x180013a39  test    eax, eax
0x180013a3b  js      loc_180013B73
0x180013a41  lea     r8, [rsp+140h+lpsz]; unsigned __int16 **
0x180013a46  lea     rdx, aId; "id"
0x180013a4d  mov     rcx, rdi; struct IXMLDOMElement *
0x180013a50  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013a55  mov     ebx, eax
0x180013a57  test    eax, eax
0x180013a59  jnz     short loc_180013AB1
0x180013a5b  mov     rdi, [rsp+140h+lpsz]
0x180013a60  mov     rcx, rdi; unsigned __int16 *
0x180013a63  call    ?IsValidGUIDString@@YAHPEAG@Z; IsValidGUIDString(ushort *)
0x180013a68  test    eax, eax
0x180013a6a  jz      short loc_180013AB1
0x180013a6c  lea     rdx, [rbp+40h+pclsid]; pclsid
0x180013a70  mov     rcx, rdi; lpsz
0x180013a73  call    cs:__imp_CLSIDFromString
0x180013a79  mov     ebx, eax
0x180013a7b  test    eax, eax
0x180013a7d  jns     short loc_180013AEF
0x180013a7f  mov     rcx, cs:WPP_GLOBAL_Control
0x180013a86  lea     rax, WPP_GLOBAL_Control
0x180013a8d  cmp     rcx, rax
0x180013a90  jz      short loc_180013AE7
0x180013a92  test    byte ptr [rcx+1Ch], 4
0x180013a96  jz      short loc_180013AE7
0x180013a98  lea     edx, [r13+1Eh]
0x180013a9c  mov     r9d, ebx
0x180013a9f  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180013aa6  mov     rcx, [rcx+10h]
0x180013aaa  call    WPP_SF_d
0x180013aaf  jmp     short loc_180013AE7
0x180013ab1  mov     rcx, cs:WPP_GLOBAL_Control
0x180013ab8  lea     rax, WPP_GLOBAL_Control
0x180013abf  cmp     rcx, rax
0x180013ac2  jz      short loc_180013AE2
0x180013ac4  test    byte ptr [rcx+1Ch], 8
0x180013ac8  jz      short loc_180013AE2
0x180013aca  mov     edx, 1Dh
0x180013acf  mov     r9d, ebx
0x180013ad2  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180013ad9  mov     rcx, [rcx+10h]
0x180013add  call    WPP_SF_d
0x180013ae2  mov     ebx, 8000FFFFh
0x180013ae7  test    ebx, ebx
0x180013ae9  js      loc_180013BA4
0x180013aef  mov     esi, [rbp+40h+var_A8]
0x180013af2  lea     rdx, [rsp+140h+var_D8]; enum tagXW_COMPONENT_TYPE *
0x180013af7  mov     rcx, r14; struct IXMLDOMElement *
0x180013afa  call    ?HrGetTagComponentType@@YAJPEAUIXMLDOMElement@@PEAW4tagXW_COMPONENT_TYPE@@@Z; HrGetTagComponentType(IXMLDOMElement *,tagXW_COMPONENT_TYPE *)
0x180013aff  mov     ebx, eax
0x180013b01  test    eax, eax
0x180013b03  js      loc_18001417D
0x180013b09  lea     r8, [rsp+140h+var_E0]; unsigned __int16 **
0x180013b0e  lea     rdx, aId; "id"
0x180013b15  mov     rcx, r14; struct IXMLDOMElement *
0x180013b18  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013b1d  mov     ebx, eax
0x180013b1f  test    eax, eax
0x180013b21  jnz     loc_180014142
0x180013b27  mov     rdi, [rsp+140h+var_E0]
0x180013b2c  mov     rcx, rdi; unsigned __int16 *
0x180013b2f  call    ?IsValidGUIDString@@YAHPEAG@Z; IsValidGUIDString(ushort *)
0x180013b34  test    eax, eax
0x180013b36  jz      loc_180014142
0x180013b3c  lea     rdx, [rbp+40h+var_68]; pclsid
0x180013b40  mov     rcx, rdi; lpsz
0x180013b43  call    cs:__imp_CLSIDFromString
0x180013b49  mov     ebx, eax
0x180013b4b  test    eax, eax
0x180013b4d  jns     loc_180013C8E
0x180013b53  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b5a  lea     rax, WPP_GLOBAL_Control
0x180013b61  cmp     rcx, rax
0x180013b64  jz      short loc_180013BA4
0x180013b66  test    byte ptr [rcx+1Ch], 4
0x180013b6a  jz      short loc_180013BA4
0x180013b6c  mov     edx, 21h ; '!'
0x180013b71  jmp     short loc_180013B91
0x180013b73  mov     rcx, cs:WPP_GLOBAL_Control
0x180013b7a  lea     rax, WPP_GLOBAL_Control
0x180013b81  cmp     rcx, rax
0x180013b84  jz      short loc_180013BA4
0x180013b86  test    byte ptr [rcx+1Ch], 4
0x180013b8a  jz      short loc_180013BA4
0x180013b8c  mov     edx, 1Fh
0x180013b91  mov     r9d, ebx
0x180013b94  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180013b9b  mov     rcx, [rcx+10h]
0x180013b9f  call    WPP_SF_d
0x180013ba4  mov     esi, [rsp+140h+var_F0]
0x180013ba8  mov     rdi, [rsp+140h+lpsz]
0x180013bad  mov     r15, [rsp+140h+var_E0]
0x180013bb2  mov     rcx, rdi; bstrString
0x180013bb5  call    cs:__imp_SysFreeString
0x180013bbb  mov     rcx, r15; bstrString
0x180013bbe  call    cs:__imp_SysFreeString
0x180013bc4  mov     rcx, [rsp+140h+bstrString]; bstrString
0x180013bc9  call    cs:__imp_SysFreeString
0x180013bcf  mov     rcx, [rbp+40h+var_C0]; bstrString
0x180013bd3  call    cs:__imp_SysFreeString
0x180013bd9  mov     rcx, [rbp+40h+String]; bstrString
0x180013bdd  call    cs:__imp_SysFreeString
0x180013be3  mov     rcx, [rbp+40h+var_90]; bstrString
0x180013be7  call    cs:__imp_SysFreeString
0x180013bed  mov     rcx, r13; bstrString
0x180013bf0  call    cs:__imp_SysFreeString
0x180013bf6  test    ebx, ebx
0x180013bf8  js      loc_1800141E2
0x180013bfe  mov     rdx, r14; struct IXMLDOMElement *
0x180013c01  lea     rcx, [rbp+40h+var_80]; this
0x180013c05  call    ??0CTagEnum@@QEAA@PEAUIXMLDOMElement@@@Z; CTagEnum::CTagEnum(IXMLDOMElement *)
0x180013c0a  nop
0x180013c0b  mov     [rsp+140h+var_D0], 0
0x180013c14  lea     rdx, [rsp+140h+var_D0]; struct IXMLDOMElement **
0x180013c19  lea     rcx, [rbp+40h+var_80]; this
0x180013c1d  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x180013c22  mov     edi, eax
0x180013c24  test    eax, eax
0x180013c26  jnz     loc_1800141CD
0x180013c2c  mov     ebx, [rbp+40h+arg_30]
0x180013c32  mov     [rsp+140h+var_100], r12
0x180013c37  mov     rax, [rbp+40h+var_88]
0x180013c3b  mov     [rsp+140h+var_108], rax
0x180013c40  mov     [rsp+140h+var_110], ebx
0x180013c44  mov     eax, [rbp+40h+arg_28]
0x180013c47  mov     [rsp+140h+var_118], eax
0x180013c4b  mov     eax, [rbp+40h+arg_20]
0x180013c4e  mov     dword ptr [rsp+140h+var_120], eax
0x180013c52  mov     r9d, esi
0x180013c55  mov     r8d, [rbp+40h+var_A0]
0x180013c59  mov     rdx, [rsp+140h+var_D0]
0x180013c5e  mov     rcx, r14
0x180013c61  call    ?HrProcessRegistryComponentXML@@YAJPEAUIXMLDOMElement@@0W4tagXW_XML_ONERROR_TYPE@@W4tagXW_XML_ACTION_TYPE@@KHKPEAXPEAUIXWizard@@@Z; HrProcessRegistryComponentXML(IXMLDOMElement *,IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,tagXW_XML_ACTION_TYPE,ulong,int,ulong,void *,IXWizard *)
0x180013c66  mov     edi, eax
0x180013c68  mov     rcx, [rsp+140h+var_D0]
0x180013c6d  mov     rax, [rcx]
0x180013c70  mov     rax, [rax+10h]
0x180013c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c79  mov     eax, 1
0x180013c7e  cmp     edi, eax
0x180013c80  jnz     loc_1800141B1
0x180013c86  mov     [rbp+40h+var_B8], eax
0x180013c89  jmp     loc_1800141B5
0x180013c8e  lea     r8, [rsp+140h+bstrString]; unsigned __int16 **
0x180013c93  lea     rdx, aFilename; "filename"
0x180013c9a  mov     rcx, r14; struct IXMLDOMElement *
0x180013c9d  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013ca2  mov     ebx, eax
0x180013ca4  test    eax, eax
0x180013ca6  jns     short loc_180013CD3
0x180013ca8  mov     rcx, cs:WPP_GLOBAL_Control
0x180013caf  lea     rax, WPP_GLOBAL_Control
0x180013cb6  cmp     rcx, rax
0x180013cb9  jz      loc_180013BA4
0x180013cbf  test    byte ptr [rcx+1Ch], 4
0x180013cc3  jz      loc_180013BA4
0x180013cc9  mov     edx, 22h ; '"'
0x180013cce  jmp     loc_180013B91
0x180013cd3  lea     r8, [rbp+40h+var_C0]; unsigned __int16 **
0x180013cd7  lea     rdx, aName; "name"
0x180013cde  mov     rcx, r14; struct IXMLDOMElement *
0x180013ce1  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013ce6  mov     ebx, eax
0x180013ce8  test    eax, eax
0x180013cea  jns     short loc_180013D17
0x180013cec  mov     rcx, cs:WPP_GLOBAL_Control
0x180013cf3  lea     rax, WPP_GLOBAL_Control
0x180013cfa  cmp     rcx, rax
0x180013cfd  jz      loc_180013BA4
0x180013d03  test    byte ptr [rcx+1Ch], 4
0x180013d07  jz      loc_180013BA4
0x180013d0d  mov     edx, 23h ; '#'
0x180013d12  jmp     loc_180013B91
0x180013d17  lea     r8, [rbp+40h+String]; unsigned __int16 **
0x180013d1b  lea     rdx, aBehavior; "behavior"
0x180013d22  mov     rcx, r14; struct IXMLDOMElement *
0x180013d25  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013d2a  mov     ebx, eax
0x180013d2c  test    eax, eax
0x180013d2e  jns     short loc_180013D5B
0x180013d30  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d37  lea     rax, WPP_GLOBAL_Control
0x180013d3e  cmp     rcx, rax
0x180013d41  jz      loc_180013BA4
0x180013d47  test    byte ptr [rcx+1Ch], 4
0x180013d4b  jz      loc_180013BA4
0x180013d51  mov     edx, 24h ; '$'
0x180013d56  jmp     loc_180013B91
0x180013d5b  mov     edi, [rbp+40h+arg_20]
0x180013d5e  test    ebx, ebx
0x180013d60  jnz     short loc_180013D77
0x180013d62  xor     edx, edx; EndPtr
0x180013d64  lea     r8d, [rbx+10h]; Radix
0x180013d68  mov     rcx, [rbp+40h+String]; String
0x180013d6c  call    cs:__imp_wcstoul
0x180013d72  mov     edi, eax
0x180013d74  or      edi, [rbp+40h+arg_20]
0x180013d77  lea     r8, [rbp+40h+var_90]; unsigned __int16 **
0x180013d7b  lea     rdx, aFlags; "flags"
0x180013d82  mov     rcx, r14; struct IXMLDOMElement *
0x180013d85  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013d8a  mov     ebx, eax
0x180013d8c  test    eax, eax
0x180013d8e  jns     short loc_180013DBB
0x180013d90  mov     rcx, cs:WPP_GLOBAL_Control
0x180013d97  lea     rax, WPP_GLOBAL_Control
0x180013d9e  cmp     rcx, rax
0x180013da1  jz      loc_180013BA4
0x180013da7  test    byte ptr [rcx+1Ch], 4
0x180013dab  jz      loc_180013BA4
0x180013db1  mov     edx, 25h ; '%'
0x180013db6  jmp     loc_180013B91
0x180013dbb  xor     r14d, r14d
0x180013dbe  test    ebx, ebx
0x180013dc0  jnz     short loc_180013DD5
0x180013dc2  xor     edx, edx; EndPtr
0x180013dc4  lea     r8d, [r14+10h]; Radix
0x180013dc8  mov     rcx, [rbp+40h+var_90]; String
0x180013dcc  call    cs:__imp_wcstoul
0x180013dd2  mov     r14d, eax
0x180013dd5  lea     r8, [rsp+140h+var_D0]; unsigned __int16 **
0x180013dda  lea     rdx, aCommandline; "commandline"
0x180013de1  mov     r13, [rbp+40h+var_B0]
0x180013de5  mov     rcx, r13; struct IXMLDOMElement *
0x180013de8  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180013ded  mov     ebx, eax
0x180013def  test    eax, eax
0x180013df1  jns     short loc_180013E32
0x180013df3  mov     rcx, cs:WPP_GLOBAL_Control
0x180013dfa  lea     rax, WPP_GLOBAL_Control
0x180013e01  cmp     rcx, rax
0x180013e04  jz      short loc_180013E24
0x180013e06  test    byte ptr [rcx+1Ch], 4
0x180013e0a  jz      short loc_180013E24
0x180013e0c  mov     edx, 26h ; '&'
0x180013e11  mov     r9d, ebx
0x180013e14  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180013e1b  mov     rcx, [rcx+10h]
0x180013e1f  call    WPP_SF_d
0x180013e24  mov     r13, [rsp+140h+var_D0]
0x180013e29  mov     r14, [rbp+40h+var_B0]
0x180013e2d  jmp     loc_180013BA4
0x180013e32  test    esi, esi
0x180013e34  jnz     short loc_180013E4C
0x180013e36  lea     rdx, [rbp+40h+var_A4]; int *
0x180013e3a  mov     rcx, r13; struct IXMLDOMElement *
0x180013e3d  call    ?HrHasChildTags@@YAJPEAUIXMLDOMElement@@PEAH@Z; HrHasChildTags(IXMLDOMElement *,int *)
0x180013e42  mov     ebx, eax
0x180013e44  test    eax, eax
0x180013e46  js      short loc_180013E24
0x180013e48  mov     r15d, [rbp+40h+var_A4]
0x180013e4c  mov     rax, [r12]
0x180013e50  mov     r8, [rbp+40h+var_88]
0x180013e54  mov     edx, 12Fh
  ... truncated ...
```
