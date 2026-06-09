# HrProcessRunWizardXML(IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,IPXWizardPropertyBag *,IXWizard *)

- ea: `0x180014724`
- end: `0x180014c77`
- name: `?HrProcessRunWizardXML@@YAJPEAUIXMLDOMElement@@W4tagXW_XML_ONERROR_TYPE@@PEAUIPXWizardPropertyBag@@PEAUIXWizard@@@Z`
- size: `1363`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x18000ae04`
- `0x18000ae90`
- `0x18000e560`
- `0x180014724`
- `0x18001592c`
- `0x18001a308`
- `0x18001df3c`
- `0x180032a30`
- `0x180034010`

## import_xrefs

- `msvcrt!wcstoul` at `0x180014989`
- `msvcrt!wcstoul` at `0x180014a3b`
- `msvcrt!wcstoul` at `0x180014989`
- `msvcrt!wcstoul` at `0x180014a3b`
- `msvcrt!_wcsicmp` at `0x18001485b`
- `msvcrt!_wcsicmp` at `0x18001486f`
- `msvcrt!_wcsicmp` at `0x1800148d0`
- `msvcrt!_wcsicmp` at `0x1800148eb`
- `msvcrt!_wcsicmp` at `0x180014904`
- `msvcrt!_wcsicmp` at `0x180014920`
- `msvcrt!_wcsicmp` at `0x18001485b`
- `msvcrt!_wcsicmp` at `0x18001486f`
- `msvcrt!_wcsicmp` at `0x1800148d0`
- `msvcrt!_wcsicmp` at `0x1800148eb`
- `msvcrt!_wcsicmp` at `0x180014904`
- `msvcrt!_wcsicmp` at `0x180014920`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800147bd`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x1800147bd`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c00`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c09`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c13`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c27`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c00`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c09`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c13`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c1d`
- `OLEAUT32!__imp_SysFreeString` at `0x180014c27`

## string_xrefs

- `0x180014999`: `commandline`

## pseudocode

```c
__int64 __fastcall HrProcessRunWizardXML(struct IXMLDOMElement *a1, int a2, __int64 a3, __int64 a4)
{
  unsigned int v4; // r15d
  wchar_t *v5; // rdi
  unsigned int NamedAttributeValue; // ebx
  HRESULT v9; // eax
  int v10; // ebx
  _QWORD *v11; // rcx
  __int64 v12; // rdx
  int v13; // eax
  unsigned int v14; // esi
  unsigned int v15; // r14d
  BSTR v16; // r12
  int v17; // eax
  PVOID *v18; // rcx
  LPCOLESTR lpsz; // [rsp+50h] [rbp-49h] BYREF
  wchar_t *String2; // [rsp+58h] [rbp-41h] BYREF
  int v22; // [rsp+60h] [rbp-39h]
  struct IPXWizardTask *v23; // [rsp+68h] [rbp-31h] BYREF
  wchar_t *String; // [rsp+70h] [rbp-29h] BYREF
  BSTR bstrString; // [rsp+78h] [rbp-21h] BYREF
  BSTR v26; // [rsp+80h] [rbp-19h] BYREF
  struct IMultiObjectElevationFactory **v27; // [rsp+88h] [rbp-11h] BYREF
  HWND v28; // [rsp+90h] [rbp-9h] BYREF
  __int64 v29; // [rsp+98h] [rbp-1h]
  GUID pclsid; // [rsp+A0h] [rbp+7h] BYREF

  v4 = 0;
  v29 = a3;
  v22 = a2;
  lpsz = 0;
  String2 = 0;
  pclsid = 0;
  v5 = 0;
  String = 0;
  bstrString = 0;
  v26 = 0;
  v28 = 0;
  v23 = 0;
  v27 = 0;
  NamedAttributeValue = HrGetNamedAttributeValue(a1, L"id", (unsigned __int16 **)&lpsz);
  if ( NamedAttributeValue || !(unsigned int)IsValidGUIDString((unsigned __int16 *)lpsz) )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        84,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        NamedAttributeValue);
    v10 = -2147418113;
    goto LABEL_66;
  }
  v9 = CLSIDFromString(lpsz, &pclsid);
  v10 = v9;
  if ( v9 < 0 )
  {
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      v12 = 85;
LABEL_37:
      WPP_SF_d(v11[2], v12, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, (unsigned int)v9);
      goto LABEL_66;
    }
    goto LABEL_66;
  }
  v13 = HrGetNamedAttributeValue(a1, L"type", &String2);
  v10 = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)v13);
    v5 = String2;
    goto LABEL_66;
  }
  v5 = String2;
  v14 = 0;
  if ( !v13 && _wcsicmp(L"default", String2) )
  {
    if ( _wcsicmp(L"dui", v5) )
    {
      if ( _wcsicmp(L"moderndui", v5) )
      {
        if ( _wcsicmp(L"propertysheet97", v5) )
        {
          if ( _wcsicmp(L"wizard97", v5) )
          {
            if ( _wcsicmp(L"aero", v5) )
            {
              v10 = -2147418113;
              if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
                WPP_SF_SD(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  87,
                  (unsigned int)&WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
                  (_DWORD)v5,
                  255);
              goto LABEL_66;
            }
            v14 = 32;
          }
          else
          {
            v14 = 2;
          }
        }
        else
        {
          v14 = 1;
        }
      }
      else
      {
        v14 = 1024;
      }
    }
    else
    {
      v14 = 512;
    }
  }
  v9 = HrGetNamedAttributeValue(a1, L"flags", &String);
  v10 = v9;
  if ( v9 >= 0 )
  {
    if ( !v9 )
      v4 = wcstoul(String, 0, 16);
    v9 = HrGetNamedAttributeValue(a1, L"commandline", &bstrString);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 89;
        goto LABEL_37;
      }
      goto LABEL_66;
    }
    v9 = HrGetNamedAttributeValue(a1, L"contextflags", &v26);
    v10 = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      {
        v12 = 90;
        goto LABEL_37;
      }
      goto LABEL_66;
    }
    v15 = 0;
    if ( !v9 )
      v15 = wcstoul(v26, 0, 16);
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, struct IMultiObjectElevationFactory ***))(*(_QWORD *)a4 + 224LL))(
            a4,
            302,
            &v27);
    if ( v10 < 0 )
      goto LABEL_66;
    v10 = (*(__int64 (__fastcall **)(__int64, __int64, HWND *))(*(_QWORD *)a4 + 224LL))(a4, 1, &v28);
    if ( v10 < 0 )
      goto LABEL_66;
    v10 = CPXWizardTask::HrCreateInstance(v28, v27, &v23);
    if ( v10 < 0 )
    {
      v18 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      {
LABEL_57:
        if ( v22 == 2 )
        {
          if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 0x10) != 0 )
            WPP_SF_d(v18[2], 93, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, (unsigned int)v10);
          v10 = 1;
        }
        goto LABEL_66;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        92,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)v10);
    }
    else
    {
      v16 = bstrString;
      v17 = (*(__int64 (__fastcall **)(struct IPXWizardTask *, _QWORD, GUID *, _QWORD, unsigned int, BSTR, _QWORD, unsigned int, __int64))(*(_QWORD *)v23 + 80LL))(
              v23,
              0,
              &pclsid,
              v14,
              v4,
              bstrString,
              0,
              v15,
              v29);
      v10 = v17;
      if ( v17 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_SSDDSD(*((_QWORD *)WPP_GLOBAL_Control + 2), (__int64)v5, v4, v15, (__int64)v16, v17);
      (*(void (__fastcall **)(struct IPXWizardTask *))(*(_QWORD *)v23 + 16LL))(v23);
      if ( v10 >= 0 )
        goto LABEL_66;
    }
    v18 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_57;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
  {
    v12 = 88;
    goto LABEL_37;
  }
LABEL_66:
  SysFreeString((BSTR)lpsz);
  SysFreeString(v5);
  SysFreeString(String);
  SysFreeString(bstrString);
  SysFreeString(v26);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x10) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      94,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)v10);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x180014724  push    rbp
0x180014726  push    rbx
0x180014727  push    rsi
0x180014728  push    rdi
0x180014729  push    r12
0x18001472b  push    r14
0x18001472d  push    r15
0x18001472f  lea     rbp, [rsp-27h]
0x180014734  sub     rsp, 0C0h
0x18001473b  mov     rax, cs:__security_cookie
0x180014742  xor     rax, rsp
0x180014745  mov     [rbp+57h+var_40], rax
0x180014749  xor     r15d, r15d
0x18001474c  mov     [rbp+57h+var_58], r8
0x180014750  mov     [rbp+57h+var_90], edx
0x180014753  lea     r8, [rbp+57h+lpsz]; unsigned __int16 **
0x180014757  xorps   xmm0, xmm0
0x18001475a  mov     [rbp+57h+lpsz], r15
0x18001475e  lea     rdx, aId; "id"
0x180014765  mov     [rbp+57h+String2], r15
0x180014769  movups  xmmword ptr [rbp+57h+pclsid.Data1], xmm0
0x18001476d  mov     edi, r15d
0x180014770  mov     [rbp+57h+String], r15
0x180014774  mov     [rbp+57h+bstrString], r15
0x180014778  mov     r12, r9
0x18001477b  mov     [rbp+57h+var_70], r15
0x18001477f  mov     r14, rcx
0x180014782  mov     [rbp+57h+var_60], r15
0x180014786  mov     [rbp+57h+var_88], r15
0x18001478a  mov     [rbp+57h+var_68], r15
0x18001478e  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014793  mov     ebx, eax
0x180014795  lea     rax, WPP_GLOBAL_Control
0x18001479c  test    ebx, ebx
0x18001479e  jnz     loc_180014BC6
0x1800147a4  mov     rcx, [rbp+57h+lpsz]; unsigned __int16 *
0x1800147a8  call    ?IsValidGUIDString@@YAHPEAG@Z; IsValidGUIDString(ushort *)
0x1800147ad  test    eax, eax
0x1800147af  jz      loc_180014BBF
0x1800147b5  mov     rcx, [rbp+57h+lpsz]; lpsz
0x1800147b9  lea     rdx, [rbp+57h+pclsid]; pclsid
0x1800147bd  call    cs:__imp_CLSIDFromString
0x1800147c3  mov     ebx, eax
0x1800147c5  test    eax, eax
0x1800147c7  jns     short loc_1800147F3
0x1800147c9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800147d0  lea     rsi, WPP_GLOBAL_Control
0x1800147d7  cmp     rcx, rsi
0x1800147da  jz      loc_180014BFC
0x1800147e0  test    byte ptr [rcx+1Ch], 4
0x1800147e4  jz      loc_180014BFC
0x1800147ea  lea     edx, [r15+55h]
0x1800147ee  jmp     loc_1800149D1
0x1800147f3  lea     r8, [rbp+57h+String2]; unsigned __int16 **
0x1800147f7  mov     rcx, r14; struct IXMLDOMElement *
0x1800147fa  lea     rdx, aType; "type"
0x180014801  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014806  mov     ebx, eax
0x180014808  test    eax, eax
0x18001480a  jns     short loc_180014846
0x18001480c  mov     rcx, cs:WPP_GLOBAL_Control
0x180014813  lea     rsi, WPP_GLOBAL_Control
0x18001481a  cmp     rcx, rsi
0x18001481d  jz      short loc_18001483D
0x18001481f  test    byte ptr [rcx+1Ch], 4
0x180014823  jz      short loc_18001483D
0x180014825  mov     rcx, [rcx+10h]
0x180014829  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014830  mov     edx, 56h ; 'V'
0x180014835  mov     r9d, eax
0x180014838  call    WPP_SF_d
0x18001483d  mov     rdi, [rbp+57h+String2]
0x180014841  jmp     loc_180014BFC
0x180014846  mov     rdi, [rbp+57h+String2]
0x18001484a  mov     esi, r15d
0x18001484d  test    eax, eax
0x18001484f  jnz     short loc_18001487E
0x180014851  mov     rdx, rdi; String2
0x180014854  lea     rcx, aDefault; "default"
0x18001485b  call    cs:__imp__wcsicmp
0x180014861  test    eax, eax
0x180014863  jz      short loc_18001487E
0x180014865  mov     rdx, rdi; String2
0x180014868  lea     rcx, aDui; "dui"
0x18001486f  call    cs:__imp__wcsicmp
0x180014875  test    eax, eax
0x180014877  jnz     short loc_1800148C6
0x180014879  mov     esi, 200h
0x18001487e  lea     r8, [rbp+57h+String]; unsigned __int16 **
0x180014882  mov     rcx, r14; struct IXMLDOMElement *
0x180014885  lea     rdx, aFlags; "flags"
0x18001488c  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014891  mov     ebx, eax
0x180014893  test    eax, eax
0x180014895  jns     loc_18001497D
0x18001489b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800148a2  lea     rsi, WPP_GLOBAL_Control
0x1800148a9  cmp     rcx, rsi
0x1800148ac  jz      loc_180014BFC
0x1800148b2  test    byte ptr [rcx+1Ch], 4
0x1800148b6  jz      loc_180014BFC
0x1800148bc  mov     edx, 58h ; 'X'
0x1800148c1  jmp     loc_1800149D1
0x1800148c6  mov     rdx, rdi; String2
0x1800148c9  lea     rcx, aModerndui; "moderndui"
0x1800148d0  call    cs:__imp__wcsicmp
0x1800148d6  test    eax, eax
0x1800148d8  jnz     short loc_1800148E1
0x1800148da  mov     esi, 400h
0x1800148df  jmp     short loc_18001487E
0x1800148e1  mov     rdx, rdi; String2
0x1800148e4  lea     rcx, aPropertysheet9; "propertysheet97"
0x1800148eb  call    cs:__imp__wcsicmp
0x1800148f1  test    eax, eax
0x1800148f3  jnz     short loc_1800148FA
0x1800148f5  lea     esi, [rax+1]
0x1800148f8  jmp     short loc_18001487E
0x1800148fa  mov     rdx, rdi; String2
0x1800148fd  lea     rcx, aWizard97; "wizard97"
0x180014904  call    cs:__imp__wcsicmp
0x18001490a  test    eax, eax
0x18001490c  jnz     short loc_180014916
0x18001490e  lea     esi, [rax+2]
0x180014911  jmp     loc_18001487E
0x180014916  mov     rdx, rdi; String2
0x180014919  lea     rcx, aAero; "aero"
0x180014920  call    cs:__imp__wcsicmp
0x180014926  test    eax, eax
0x180014928  jnz     short loc_180014932
0x18001492a  lea     esi, [rax+20h]
0x18001492d  jmp     loc_18001487E
0x180014932  mov     ebx, 8000FFFFh
0x180014937  mov     rcx, cs:WPP_GLOBAL_Control
0x18001493e  lea     rsi, WPP_GLOBAL_Control
0x180014945  cmp     rcx, rsi
0x180014948  jz      loc_180014BFC
0x18001494e  test    byte ptr [rcx+1Ch], 8
0x180014952  jz      loc_180014BFC
0x180014958  mov     rcx, [rcx+10h]
0x18001495c  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014963  mov     edx, 57h ; 'W'
0x180014968  mov     dword ptr [rsp+0F0h+var_D0], 8000FFFFh
0x180014970  mov     r9, rdi
0x180014973  call    WPP_SF_SD
0x180014978  jmp     loc_180014BFC
0x18001497d  jnz     short loc_180014992
0x18001497f  mov     rcx, [rbp+57h+String]; String
0x180014983  xor     edx, edx; EndPtr
0x180014985  lea     r8d, [rdx+10h]; Radix
0x180014989  call    cs:__imp_wcstoul
0x18001498f  mov     r15d, eax
0x180014992  lea     r8, [rbp+57h+bstrString]; unsigned __int16 **
0x180014996  mov     rcx, r14; struct IXMLDOMElement *
0x180014999  lea     rdx, aCommandline; "commandline"
0x1800149a0  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x1800149a5  mov     ebx, eax
0x1800149a7  test    eax, eax
0x1800149a9  jns     short loc_1800149E9
0x1800149ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800149b2  lea     rsi, WPP_GLOBAL_Control
0x1800149b9  cmp     rcx, rsi
0x1800149bc  jz      loc_180014BFC
0x1800149c2  test    byte ptr [rcx+1Ch], 4
0x1800149c6  jz      loc_180014BFC
0x1800149cc  mov     edx, 59h ; 'Y'
0x1800149d1  mov     rcx, [rcx+10h]
0x1800149d5  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x1800149dc  mov     r9d, eax
0x1800149df  call    WPP_SF_d
0x1800149e4  jmp     loc_180014BFC
0x1800149e9  lea     r8, [rbp+57h+var_70]; unsigned __int16 **
0x1800149ed  mov     rcx, r14; struct IXMLDOMElement *
0x1800149f0  lea     rdx, aContextflags; "contextflags"
0x1800149f7  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x1800149fc  mov     ebx, eax
0x1800149fe  test    eax, eax
0x180014a00  jns     short loc_180014A2A
0x180014a02  mov     rcx, cs:WPP_GLOBAL_Control
0x180014a09  lea     rsi, WPP_GLOBAL_Control
0x180014a10  cmp     rcx, rsi
0x180014a13  jz      loc_180014BFC
0x180014a19  test    byte ptr [rcx+1Ch], 4
0x180014a1d  jz      loc_180014BFC
0x180014a23  mov     edx, 5Ah ; 'Z'
0x180014a28  jmp     short loc_1800149D1
0x180014a2a  xor     r14d, r14d
0x180014a2d  test    eax, eax
0x180014a2f  jnz     short loc_180014A44
0x180014a31  mov     rcx, [rbp+57h+var_70]; String
0x180014a35  lea     r8d, [r14+10h]; Radix
0x180014a39  xor     edx, edx; EndPtr
0x180014a3b  call    cs:__imp_wcstoul
0x180014a41  mov     r14d, eax
0x180014a44  mov     rcx, [r12]
0x180014a48  lea     r8, [rbp+57h+var_68]
0x180014a4c  mov     edx, 12Eh
0x180014a51  mov     rax, [rcx+0E0h]
0x180014a58  mov     rcx, r12
0x180014a5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a60  mov     ebx, eax
0x180014a62  test    eax, eax
0x180014a64  js      loc_180014BF5
0x180014a6a  mov     rax, [r12]
0x180014a6e  lea     r8, [rbp+57h+var_60]
0x180014a72  mov     edx, 1
0x180014a77  mov     rcx, r12
0x180014a7a  mov     rax, [rax+0E0h]
0x180014a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a86  mov     ebx, eax
0x180014a88  test    eax, eax
0x180014a8a  js      loc_180014BF5
0x180014a90  mov     rdx, [rbp+57h+var_68]; struct IMultiObjectElevationFactory **
0x180014a94  lea     r8, [rbp+57h+var_88]; struct IPXWizardTask **
0x180014a98  mov     rcx, [rbp+57h+var_60]; HWND
0x180014a9c  call    ?HrCreateInstance@CPXWizardTask@@SAJPEAUHWND__@@PEAPEAUIMultiObjectElevationFactory@@PEAPEAUIPXWizardTask@@@Z; CPXWizardTask::HrCreateInstance(HWND__ *,IMultiObjectElevationFactory * *,IPXWizardTask * *)
0x180014aa1  mov     ebx, eax
0x180014aa3  test    eax, eax
0x180014aa5  js      loc_180014B50
0x180014aab  mov     rcx, [rbp+57h+var_88]
0x180014aaf  lea     r8, [rbp+57h+pclsid]
0x180014ab3  mov     rdx, [rbp+57h+var_58]
0x180014ab7  mov     r9d, esi
0x180014aba  mov     r12, [rbp+57h+bstrString]
0x180014abe  mov     qword ptr [rsp+0F0h+var_B0], rdx
0x180014ac3  xor     edx, edx
0x180014ac5  mov     rax, [rcx]
0x180014ac8  mov     dword ptr [rsp+0F0h+var_B8], r14d
0x180014acd  mov     qword ptr [rsp+0F0h+var_C0], 0
0x180014ad6  mov     qword ptr [rsp+0F0h+var_C8], r12
0x180014adb  mov     rax, [rax+50h]
0x180014adf  mov     dword ptr [rsp+0F0h+var_D0], r15d
0x180014ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014ae9  mov     ebx, eax
0x180014aeb  test    eax, eax
0x180014aed  jns     short loc_180014B2F
0x180014aef  mov     rcx, cs:WPP_GLOBAL_Control
0x180014af6  lea     rsi, WPP_GLOBAL_Control
0x180014afd  cmp     rcx, rsi
0x180014b00  jz      short loc_180014B36
0x180014b02  test    byte ptr [rcx+1Ch], 4
0x180014b06  jz      short loc_180014B36
0x180014b08  mov     r9, [rbp+57h+lpsz]
0x180014b0c  mov     rcx, [rcx+10h]; LoggerHandle
0x180014b10  mov     dword ptr [rsp+0F0h+var_B0], eax; char
0x180014b14  mov     [rsp+0F0h+var_B8], r12; __int64
0x180014b19  mov     dword ptr [rsp+0F0h+var_C0], r14d; char
0x180014b1e  mov     dword ptr [rsp+0F0h+var_C8], r15d; char
0x180014b23  mov     [rsp+0F0h+var_D0], rdi; __int64
0x180014b28  call    WPP_SF_SSDDSD
0x180014b2d  jmp     short loc_180014B36
0x180014b2f  lea     rsi, WPP_GLOBAL_Control
0x180014b36  mov     rcx, [rbp+57h+var_88]
0x180014b3a  mov     rax, [rcx]
0x180014b3d  mov     rax, [rax+10h]
0x180014b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b46  test    ebx, ebx
0x180014b48  jns     loc_180014BFC
0x180014b4e  jmp     short loc_180014B81
0x180014b50  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b57  lea     rax, WPP_GLOBAL_Control
0x180014b5e  cmp     rcx, rax
0x180014b61  jz      short loc_180014B8F
0x180014b63  test    byte ptr [rcx+1Ch], 4
0x180014b67  jz      short loc_180014B8F
0x180014b69  mov     rcx, [rcx+10h]
0x180014b6d  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014b74  mov     edx, 5Ch ; '\'
0x180014b79  mov     r9d, ebx
0x180014b7c  call    WPP_SF_d
0x180014b81  mov     rcx, cs:WPP_GLOBAL_Control
0x180014b88  lea     rax, WPP_GLOBAL_Control
0x180014b8f  cmp     [rbp+57h+var_90], 2
0x180014b93  jnz     short loc_180014BF5
0x180014b95  cmp     rcx, rax
0x180014b98  jz      short loc_180014BB8
0x180014b9a  test    byte ptr [rcx+1Ch], 10h
0x180014b9e  jz      short loc_180014BB8
0x180014ba0  mov     rcx, [rcx+10h]
0x180014ba4  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014bab  mov     edx, 5Dh ; ']'
0x180014bb0  mov     r9d, ebx
0x180014bb3  call    WPP_SF_d
0x180014bb8  mov     ebx, 1
0x180014bbd  jmp     short loc_180014BF5
0x180014bbf  lea     rax, WPP_GLOBAL_Control
0x180014bc6  mov     rcx, cs:WPP_GLOBAL_Control
0x180014bcd  cmp     rcx, rax
0x180014bd0  jz      short loc_180014BF0
0x180014bd2  test    byte ptr [rcx+1Ch], 8
0x180014bd6  jz      short loc_180014BF0
0x180014bd8  mov     rcx, [rcx+10h]
0x180014bdc  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014be3  mov     edx, 54h ; 'T'
0x180014be8  mov     r9d, ebx
0x180014beb  call    WPP_SF_d
0x180014bf0  mov     ebx, 8000FFFFh
0x180014bf5  lea     rsi, WPP_GLOBAL_Control
0x180014bfc  mov     rcx, [rbp+57h+lpsz]; bstrString
0x180014c00  call    cs:__imp_SysFreeString
0x180014c06  mov     rcx, rdi; bstrString
  ... truncated ...
```
