# HrProcessRunXML(IXMLDOMElement *,ulong,IXWizard *)

- ea: `0x180014c80`
- end: `0x180014f00`
- name: `?HrProcessRunXML@@YAJPEAUIXMLDOMElement@@KPEAUIXWizard@@@Z`
- size: `640`
- prototype: `__int64 __fastcall(struct IXMLDOMElement *, __int64, struct IXWizard *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180014f08`

## callees

- `0x18000ae04`
- `0x18001226c`
- `0x1800128a8`
- `0x180014724`
- `0x180014c80`
- `0x18001a27c`
- `0x18001a2cc`
- `0x18001a308`
- `0x18001a4b4`
- `0x180034010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x180014d0a`
- `msvcrt!_wcsicmp` at `0x180014d89`
- `msvcrt!_wcsicmp` at `0x180014db2`
- `msvcrt!_wcsicmp` at `0x180014d0a`
- `msvcrt!_wcsicmp` at `0x180014d89`
- `msvcrt!_wcsicmp` at `0x180014db2`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dfb`
- `OLEAUT32!__imp_SysFreeString` at `0x180014d1c`
- `OLEAUT32!__imp_SysFreeString` at `0x180014dfb`

## pseudocode

```c
__int64 __fastcall HrProcessRunXML(struct IXMLDOMElement *a1, __int64 a2, struct IXWizard *a3)
{
  int NamedAttributeValue; // eax
  int v6; // ebx
  BOOL v7; // esi
  int v8; // eax
  bool v9; // zf
  PVOID *v10; // rcx
  struct IXMLDOMElement *v12; // [rsp+20h] [rbp-30h] BYREF
  BSTR bstrString; // [rsp+28h] [rbp-28h] BYREF
  wchar_t *String2; // [rsp+30h] [rbp-20h] BYREF
  _BYTE v15[24]; // [rsp+38h] [rbp-18h] BYREF
  struct IPXWizardPropertyBag *v16; // [rsp+88h] [rbp+38h] BYREF

  String2 = 0;
  v16 = 0;
  NamedAttributeValue = HrGetNamedAttributeValue(a1, L"onerror", &String2);
  v6 = NamedAttributeValue;
  if ( NamedAttributeValue < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        95,
        &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
        (unsigned int)NamedAttributeValue);
    return (unsigned int)v6;
  }
  v7 = _wcsicmp(L"ignore", String2) == 0;
  SysFreeString(String2);
  CTagEnum::CTagEnum((CTagEnum *)v15, a1);
  v12 = 0;
  bstrString = 0;
  v6 = CTagEnum::HrNext((CTagEnum *)v15, &v12);
  if ( !v6 )
  {
    do
    {
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMElement *, BSTR *))v12->lpVtbl->get_tagName)(v12, &bstrString);
      v6 = v8;
      if ( v8 < 0 )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            96,
            &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
            (unsigned int)v8);
      }
      else
      {
        if ( _wcsicmp(L"properties", bstrString) )
        {
          if ( !_wcsicmp(L"wizard", bstrString) )
          {
            v6 = HrProcessRunWizardXML(v12, (unsigned int)(v7 + 1), v16, a3);
            if ( v16 )
            {
              HrClearXMLProperties(v16);
              (*(void (__fastcall **)(struct IPXWizardPropertyBag *))(*(_QWORD *)v16 + 16LL))(v16);
              v16 = 0;
            }
          }
        }
        else
        {
          v6 = HrProcessPropertiesXML(v12, (unsigned int)(v7 + 1), &v16);
        }
        SysFreeString(bstrString);
      }
      ((void (__fastcall *)(struct IXMLDOMElement *))v12->lpVtbl->Release)(v12);
      v9 = v6 == 0;
      if ( v6 >= 0 )
      {
        v6 = CTagEnum::HrNext((CTagEnum *)v15, &v12);
        v9 = v6 == 0;
      }
    }
    while ( v9 );
  }
  if ( v6 == 1 )
  {
    v6 = 0;
  }
  else if ( v6 < 0 )
  {
    v10 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0 )
      goto LABEL_26;
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      97,
      &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids,
      (unsigned int)v6);
  }
  v10 = (PVOID *)WPP_GLOBAL_Control;
LABEL_26:
  if ( v16 )
  {
    HrClearXMLProperties(v16);
    (*(void (__fastcall **)(struct IPXWizardPropertyBag *))(*(_QWORD *)v16 + 16LL))(v16);
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x10) != 0 )
    WPP_SF_d(v10[2], 98, &WPP_92b4ede73d0c3990e751819403b3312f_Traceguids, (unsigned int)v6);
  CTagEnum::~CTagEnum((CTagEnum *)v15);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180014c80  mov     [rsp-18h+arg_0], rbx
0x180014c85  mov     [rsp-18h+arg_8], rsi
0x180014c8a  push    rbp
0x180014c8b  push    rdi
0x180014c8c  push    r14
0x180014c8e  mov     rbp, rsp
0x180014c91  sub     rsp, 50h
0x180014c95  mov     r14, r8
0x180014c98  mov     rdi, rcx
0x180014c9b  mov     [rbp+String2], 0
0x180014ca3  mov     [rbp+arg_18], 0
0x180014cab  lea     r8, [rbp+String2]; unsigned __int16 **
0x180014caf  lea     rdx, aOnerror; "onerror"
0x180014cb6  call    ?HrGetNamedAttributeValue@@YAJPEAUIXMLDOMElement@@PEAGPEAPEAG@Z; HrGetNamedAttributeValue(IXMLDOMElement *,ushort *,ushort * *)
0x180014cbb  mov     ebx, eax
0x180014cbd  test    eax, eax
0x180014cbf  jns     short loc_180014CFF
0x180014cc1  lea     rdi, WPP_GLOBAL_Control
0x180014cc8  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ccf  cmp     rcx, rdi
0x180014cd2  jz      loc_180014EEB
0x180014cd8  test    byte ptr [rcx+1Ch], 4
0x180014cdc  jz      loc_180014EEB
0x180014ce2  mov     edx, 5Fh ; '_'
0x180014ce7  mov     r9d, eax
0x180014cea  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014cf1  mov     rcx, [rcx+10h]
0x180014cf5  call    WPP_SF_d
0x180014cfa  jmp     loc_180014EEB
0x180014cff  mov     rdx, [rbp+String2]; String2
0x180014d03  lea     rcx, aIgnore; "ignore"
0x180014d0a  call    cs:__imp__wcsicmp
0x180014d10  xor     esi, esi
0x180014d12  test    eax, eax
0x180014d14  setz    sil
0x180014d18  mov     rcx, [rbp+String2]; bstrString
0x180014d1c  call    cs:__imp_SysFreeString
0x180014d22  mov     rdx, rdi; struct IXMLDOMElement *
0x180014d25  lea     rcx, [rbp+var_18]; this
0x180014d29  call    ??0CTagEnum@@QEAA@PEAUIXMLDOMElement@@@Z; CTagEnum::CTagEnum(IXMLDOMElement *)
0x180014d2e  nop
0x180014d2f  mov     [rbp+var_30], 0
0x180014d37  mov     [rbp+bstrString], 0
0x180014d3f  lea     rdx, [rbp+var_30]; struct IXMLDOMElement **
0x180014d43  lea     rcx, [rbp+var_18]; this
0x180014d47  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x180014d4c  mov     ebx, eax
0x180014d4e  lea     rdi, WPP_GLOBAL_Control
0x180014d55  test    eax, eax
0x180014d57  jnz     loc_180014E58
0x180014d5d  mov     rcx, [rbp+var_30]
0x180014d61  mov     rax, [rcx]
0x180014d64  lea     rdx, [rbp+bstrString]
0x180014d68  mov     rax, [rax+158h]
0x180014d6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014d74  mov     ebx, eax
0x180014d76  test    eax, eax
0x180014d78  js      loc_180014E03
0x180014d7e  mov     rdx, [rbp+bstrString]; String2
0x180014d82  lea     rcx, aProperties; "properties"
0x180014d89  call    cs:__imp__wcsicmp
0x180014d8f  test    eax, eax
0x180014d91  jnz     short loc_180014DA7
0x180014d93  lea     r8, [rbp+arg_18]
0x180014d97  lea     edx, [rsi+1]
0x180014d9a  mov     rcx, [rbp+var_30]
0x180014d9e  call    ?HrProcessPropertiesXML@@YAJPEAUIXMLDOMElement@@W4tagXW_XML_ONERROR_TYPE@@PEAPEAUIPXWizardPropertyBag@@@Z; HrProcessPropertiesXML(IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,IPXWizardPropertyBag * *)
0x180014da3  mov     ebx, eax
0x180014da5  jmp     short loc_180014DF7
0x180014da7  mov     rdx, [rbp+bstrString]; String2
0x180014dab  lea     rcx, aWizard; "wizard"
0x180014db2  call    cs:__imp__wcsicmp
0x180014db8  test    eax, eax
0x180014dba  jnz     short loc_180014DF7
0x180014dbc  mov     r9, r14
0x180014dbf  mov     r8, [rbp+arg_18]
0x180014dc3  lea     edx, [rsi+1]
0x180014dc6  mov     rcx, [rbp+var_30]
0x180014dca  call    ?HrProcessRunWizardXML@@YAJPEAUIXMLDOMElement@@W4tagXW_XML_ONERROR_TYPE@@PEAUIPXWizardPropertyBag@@PEAUIXWizard@@@Z; HrProcessRunWizardXML(IXMLDOMElement *,tagXW_XML_ONERROR_TYPE,IPXWizardPropertyBag *,IXWizard *)
0x180014dcf  mov     ebx, eax
0x180014dd1  mov     rcx, [rbp+arg_18]; struct IPXWizardPropertyBag *
0x180014dd5  test    rcx, rcx
0x180014dd8  jz      short loc_180014DF7
0x180014dda  call    ?HrClearXMLProperties@@YAJPEAUIPXWizardPropertyBag@@@Z; HrClearXMLProperties(IPXWizardPropertyBag *)
0x180014ddf  mov     rcx, [rbp+arg_18]
0x180014de3  mov     rax, [rcx]
0x180014de6  mov     rax, [rax+10h]
0x180014dea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014def  mov     [rbp+arg_18], 0
0x180014df7  mov     rcx, [rbp+bstrString]; bstrString
0x180014dfb  call    cs:__imp_SysFreeString
0x180014e01  jmp     short loc_180014E2D
0x180014e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e0a  cmp     rcx, rdi
0x180014e0d  jz      short loc_180014E2D
0x180014e0f  test    byte ptr [rcx+1Ch], 4
0x180014e13  jz      short loc_180014E2D
0x180014e15  mov     edx, 60h ; '`'
0x180014e1a  mov     r9d, eax
0x180014e1d  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014e24  mov     rcx, [rcx+10h]
0x180014e28  call    WPP_SF_d
0x180014e2d  mov     rcx, [rbp+var_30]
0x180014e31  mov     rax, [rcx]
0x180014e34  mov     rax, [rax+10h]
0x180014e38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e3d  test    ebx, ebx
0x180014e3f  js      short loc_180014E52
0x180014e41  lea     rdx, [rbp+var_30]; struct IXMLDOMElement **
0x180014e45  lea     rcx, [rbp+var_18]; this
0x180014e49  call    ?HrNext@CTagEnum@@QEAAJPEAPEAUIXMLDOMElement@@@Z; CTagEnum::HrNext(IXMLDOMElement * *)
0x180014e4e  mov     ebx, eax
0x180014e50  test    eax, eax
0x180014e52  jz      loc_180014D5D
0x180014e58  cmp     ebx, 1
0x180014e5b  jnz     short loc_180014E61
0x180014e5d  xor     ebx, ebx
0x180014e5f  jmp     short loc_180014E8F
0x180014e61  test    ebx, ebx
0x180014e63  jns     short loc_180014E8F
0x180014e65  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e6c  cmp     rcx, rdi
0x180014e6f  jz      short loc_180014E96
0x180014e71  test    byte ptr [rcx+1Ch], 4
0x180014e75  jz      short loc_180014E96
0x180014e77  mov     edx, 61h ; 'a'
0x180014e7c  mov     r9d, ebx
0x180014e7f  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014e86  mov     rcx, [rcx+10h]
0x180014e8a  call    WPP_SF_d
0x180014e8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180014e96  mov     rax, [rbp+arg_18]
0x180014e9a  test    rax, rax
0x180014e9d  jz      short loc_180014EBE
0x180014e9f  mov     rcx, rax; struct IPXWizardPropertyBag *
0x180014ea2  call    ?HrClearXMLProperties@@YAJPEAUIPXWizardPropertyBag@@@Z; HrClearXMLProperties(IPXWizardPropertyBag *)
0x180014ea7  mov     rcx, [rbp+arg_18]
0x180014eab  mov     rax, [rcx]
0x180014eae  mov     rax, [rax+10h]
0x180014eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014eb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180014ebe  cmp     rcx, rdi
0x180014ec1  jz      short loc_180014EE2
0x180014ec3  test    byte ptr [rcx+1Ch], 10h
0x180014ec7  jz      short loc_180014EE2
0x180014ec9  mov     edx, 62h ; 'b'
0x180014ece  mov     r9d, ebx
0x180014ed1  lea     r8, WPP_92b4ede73d0c3990e751819403b3312f_Traceguids
0x180014ed8  mov     rcx, [rcx+10h]
0x180014edc  call    WPP_SF_d
0x180014ee1  nop
0x180014ee2  lea     rcx, [rbp+var_18]; this
0x180014ee6  call    ??1CTagEnum@@QEAA@XZ; CTagEnum::~CTagEnum(void)
0x180014eeb  mov     eax, ebx
0x180014eed  mov     rbx, [rsp+50h+arg_0]
0x180014ef2  mov     rsi, [rsp+50h+arg_8]
0x180014ef7  add     rsp, 50h
0x180014efb  pop     r14
0x180014efd  pop     rdi
0x180014efe  pop     rbp
0x180014eff  retn
```
