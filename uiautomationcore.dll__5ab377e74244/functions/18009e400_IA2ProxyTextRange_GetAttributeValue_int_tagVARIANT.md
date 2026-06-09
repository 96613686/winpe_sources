# IA2ProxyTextRange::GetAttributeValue(int,tagVARIANT *)

- ea: `0x18009e400`
- end: `0x18009e6e9`
- name: `?GetAttributeValue@IA2ProxyTextRange@@UEAAJHPEAUtagVARIANT@@@Z`
- size: `745`
- prototype: `int(IA2ProxyTextRange *__hidden this, int, struct tagVARIANT *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1802922d0`

## callees

- `0x18000f680`
- `0x180032724`
- `0x1800844a4`
- `0x18008ae94`
- `0x18009e400`
- `0x18009e6f0`
- `0x18009e938`
- `0x18009eb50`
- `0x1801bb884`
- `0x1801e8320`
- `0x180283954`
- `0x180292ac0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e4bf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009e4bf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e4d4`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18009e4d4`
- `OLEAUT32!__imp_VariantInit` at `0x18009e44d`
- `OLEAUT32!__imp_VariantInit` at `0x18009e458`
- `OLEAUT32!__imp_VariantInit` at `0x18009e4b9`
- `OLEAUT32!__imp_VariantInit` at `0x18009e44d`
- `OLEAUT32!__imp_VariantInit` at `0x18009e458`
- `OLEAUT32!__imp_VariantInit` at `0x18009e4b9`
- `OLEAUT32!__imp_VariantClear` at `0x18009e4cc`
- `OLEAUT32!__imp_VariantClear` at `0x18009e4ea`
- `OLEAUT32!__imp_VariantClear` at `0x18009e524`
- `OLEAUT32!__imp_VariantClear` at `0x18009e4cc`
- `OLEAUT32!__imp_VariantClear` at `0x18009e4ea`
- `OLEAUT32!__imp_VariantClear` at `0x18009e524`
- `OLEAUT32!__imp_VariantCopy` at `0x18009e4f8`
- `OLEAUT32!__imp_VariantCopy` at `0x18009e4f8`

## string_xrefs

- `0x18009e50d`: `onecore\windows\accessibletech\uiautomationcore\proxies\ia2proxytextrange.cpp`
- `0x18009e565`: `onecore\windows\accessibletech\uiautomationcore\proxies\ia2proxytextrange.cpp`
- `0x18009e5dd`: `onecore\windows\accessibletech\uiautomationcore\proxies\ia2proxytextrange.cpp`
- `0x18009e5f1`: `onecore\windows\accessibletech\uiautomationcore\proxies\ia2proxytextrange.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall IA2ProxyTextRange::GetAttributeValue(IA2ProxyTextRange *this, int a2, struct tagVARIANT *a3, int a4)
{
  VARIANTARG *AttributeValueFromNodeAttributes; // rax
  __int128 v8; // xmm6
  IRecordInfo *pRecInfo; // xmm7_8
  DWORD LastError; // ebx
  HRESULT v11; // eax
  int v12; // ecx
  int v13; // r8d
  const char *v14; // r9
  __int64 result; // rax
  int v16; // ecx
  HRESULT ReservedNotSupportedValue; // eax
  int inited; // eax
  bool v19; // zf
  VARIANTARG *AttributeValueFromTextAttributes; // rax
  int v21; // [rsp+20h] [rbp-88h]
  VARIANTARG pvarg; // [rsp+30h] [rbp-78h] BYREF
  VARIANTARG v23; // [rsp+48h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  try
  {
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EtwEventWriteTransfer(
        (_DWORD)this,
        (unsigned int)IA2TextRange_GetAttributeValue_Start,
        (_DWORD)a3,
        a4,
        (__int64)&v23);
    if ( !a3 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x443,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\ia2proxytextrange.cpp",
        (const char *)0x80004003LL,
        v21);
    VariantInit(a3);
    VariantInit(&pvarg);
    if ( a2 > 40016 )
    {
      if ( a2 > 40030 )
      {
        if ( a2 != 40031 )
        {
          if ( a2 == 40034 )
            goto LABEL_9;
          v16 = a2 - 40038;
          if ( a2 == 40038 )
          {
            pvarg.vt = 3;
            pvarg.lVal = IA2ProxyTextRange::GetCaretPosition(this);
            goto LABEL_12;
          }
LABEL_33:
          if ( v16 == 1 )
            goto LABEL_34;
LABEL_20:
          *(_QWORD *)&v23.vt = 0;
          wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(&v23);
          ReservedNotSupportedValue = UiaGetReservedNotSupportedValue((IUnknown **)&v23);
          if ( ReservedNotSupportedValue < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x472,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\ia2proxytextrange.cpp",
              (const char *)(unsigned int)ReservedNotSupportedValue,
              v21);
          inited = InitVariantFromUnknown(*(struct IUnknown **)&v23.vt, &pvarg);
          if ( inited < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x473,
              (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\ia2proxytextrange.cpp",
              (const char *)(unsigned int)inited,
              v21);
          wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(&v23);
          goto LABEL_12;
        }
LABEL_34:
        AttributeValueFromTextAttributes = (VARIANTARG *)IA2ProxyTextRange::GetAttributeValueFromTextAttributes(
                                                           this,
                                                           &v23,
                                                           (unsigned int)a2);
        wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&long VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&void VariantInit(tagVARIANT *)>::operator=(
          &pvarg,
          AttributeValueFromTextAttributes);
LABEL_11:
        VariantClear(&v23);
LABEL_12:
        v11 = VariantCopy(a3, &pvarg);
        if ( v11 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x478,
            (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\ia2proxytextrange.cpp",
            (const char *)(unsigned int)v11,
            v21);
        VariantClear(&pvarg);
        if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(
            v12,
            (unsigned int)IA2TextRange_GetAttributeValue_Stop,
            v13,
            (_DWORD)v14,
            (__int64)&v23);
        return 0;
      }
      if ( a2 == 40030 || a2 == 40017 || a2 == 40025 || a2 == 40026 )
        goto LABEL_34;
      v16 = a2 - 40028;
      v19 = a2 == 40028;
LABEL_32:
      if ( !v19 )
        goto LABEL_33;
      goto LABEL_34;
    }
    if ( a2 == 40016 )
      goto LABEL_34;
    if ( a2 > 40007 )
    {
      if ( a2 == 40008 )
        goto LABEL_34;
      if ( a2 != 40013 )
      {
        if ( a2 == 40014 )
          goto LABEL_34;
        if ( a2 != 40015 )
          goto LABEL_20;
      }
    }
    else
    {
      if ( a2 == 40007 || a2 == 40001 )
        goto LABEL_34;
      if ( a2 != 40002 )
      {
        if ( a2 == 40004 )
          goto LABEL_34;
        v16 = a2 - 40005;
        v19 = a2 == 40005;
        goto LABEL_32;
      }
    }
LABEL_9:
    AttributeValueFromNodeAttributes = (VARIANTARG *)IA2ProxyTextRange::GetAttributeValueFromNodeAttributes(
                                                       this,
                                                       &v23,
                                                       (unsigned int)a2);
    if ( &pvarg != AttributeValueFromNodeAttributes )
    {
      v8 = *(_OWORD *)&AttributeValueFromNodeAttributes->vt;
      pRecInfo = AttributeValueFromNodeAttributes->pRecInfo;
      VariantInit(AttributeValueFromNodeAttributes);
      LastError = GetLastError();
      VariantClear(&pvarg);
      SetLastError(LastError);
      *(_OWORD *)&pvarg.vt = v8;
      pvarg.pRecInfo = pRecInfo;
    }
    goto LABEL_11;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x47B,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\ia2proxytextrange.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18009e400  mov     rax, rsp
0x18009e403  push    rbx
0x18009e404  push    rsi
0x18009e405  push    rdi
0x18009e406  sub     rsp, 90h
0x18009e40d  movaps  xmmword ptr [rax-28h], xmm6
0x18009e411  movaps  xmmword ptr [rax-38h], xmm7
0x18009e415  mov     rax, cs:__security_cookie
0x18009e41c  xor     rax, rsp
0x18009e41f  mov     [rsp+0A8h+var_40], rax
0x18009e424  mov     rsi, r8
0x18009e427  mov     ebx, edx
0x18009e429  mov     rdi, rcx
0x18009e42c  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18009e433  jnz     loc_18009E612
0x18009e439  mov     rcx, [rsp+0A8h]; this
0x18009e441  test    rsi, rsi
0x18009e444  jz      loc_18009E55F
0x18009e44a  mov     rcx, rsi; pvarg
0x18009e44d  call    cs:__imp_VariantInit
0x18009e453  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009e458  call    cs:__imp_VariantInit
0x18009e45e  nop
0x18009e45f  mov     eax, 9C50h
0x18009e464  cmp     ebx, eax
0x18009e466  jle     loc_18009E62D
0x18009e46c  mov     eax, 9C5Eh
0x18009e471  cmp     ebx, eax
0x18009e473  jle     loc_18009E6AD
0x18009e479  mov     ecx, ebx
0x18009e47b  sub     ecx, 9C5Fh
0x18009e481  jz      loc_18009E665
0x18009e487  mov     eax, 3
0x18009e48c  sub     ecx, eax
0x18009e48e  jnz     loc_18009E577
0x18009e494  mov     r8d, ebx
0x18009e497  lea     rdx, [rsp+0A8h+var_60]
0x18009e49c  mov     rcx, rdi
0x18009e49f  call    ?GetAttributeValueFromNodeAttributes@IA2ProxyTextRange@@AEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@H@Z; IA2ProxyTextRange::GetAttributeValueFromNodeAttributes(int)
0x18009e4a4  lea     rcx, [rsp+0A8h+pvarg]
0x18009e4a9  cmp     rcx, rax
0x18009e4ac  jz      short loc_18009E4E5
0x18009e4ae  movups  xmm6, xmmword ptr [rax]
0x18009e4b1  movsd   xmm7, qword ptr [rax+10h]
0x18009e4b6  mov     rcx, rax; pvarg
0x18009e4b9  call    cs:__imp_VariantInit
0x18009e4bf  call    cs:__imp_GetLastError
0x18009e4c5  mov     ebx, eax
0x18009e4c7  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009e4cc  call    cs:__imp_VariantClear
0x18009e4d2  mov     ecx, ebx; dwErrCode
0x18009e4d4  call    cs:__imp_SetLastError
0x18009e4da  movups  xmmword ptr [rsp+0A8h+pvarg], xmm6
0x18009e4df  movsd   qword ptr [rsp+0A8h+pvarg+10h], xmm7
0x18009e4e5  lea     rcx, [rsp+0A8h+var_60]; pvarg
0x18009e4ea  call    cs:__imp_VariantClear
0x18009e4f0  lea     rdx, [rsp+0A8h+pvarg]; pvargSrc
0x18009e4f5  mov     rcx, rsi; pvargDest
0x18009e4f8  call    cs:__imp_VariantCopy
0x18009e4fe  mov     rcx, [rsp+0A8h]; this
0x18009e506  test    eax, eax
0x18009e508  jns     short loc_18009E51F
0x18009e50a  mov     r9d, eax; char *
0x18009e50d  lea     r8, aOnecoreWindows_173; "onecore\\windows\\accessibletech\\uiaut"...
0x18009e514  mov     edx, 478h; void *
0x18009e519  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009e51f  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009e524  call    cs:__imp_VariantClear
0x18009e52a  nop
0x18009e52b  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x18009e532  jnz     loc_18009E6C5
0x18009e538  xor     eax, eax
0x18009e53a  mov     rcx, [rsp+0A8h+var_40]
0x18009e53f  xor     rcx, rsp; StackCookie
0x18009e542  call    __security_check_cookie
0x18009e547  movaps  xmm6, [rsp+0A8h+var_28]
0x18009e54f  movaps  xmm7, [rsp+0A8h+var_38]
0x18009e554  add     rsp, 90h
0x18009e55b  pop     rdi
0x18009e55c  pop     rsi
0x18009e55d  pop     rbx
0x18009e55e  retn
0x18009e55f  mov     r9d, 80004003h; char *
0x18009e565  lea     r8, aOnecoreWindows_173; "onecore\\windows\\accessibletech\\uiaut"...
0x18009e56c  mov     edx, 443h; void *
0x18009e571  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009e577  sub     ecx, 4
0x18009e57a  jnz     loc_18009E65C
0x18009e580  mov     word ptr [rsp+0A8h+pvarg], ax
0x18009e585  mov     rcx, rdi; this
0x18009e588  call    ?GetCaretPosition@IA2ProxyTextRange@@QEBA?AW4CaretPosition@@XZ; IA2ProxyTextRange::GetCaretPosition(void)
0x18009e58d  mov     dword ptr [rsp+0A8h+pvarg+8], eax
0x18009e591  jmp     loc_18009E4F0
0x18009e596  mov     qword ptr [rsp+0A8h+var_60], 0
0x18009e59f  lea     rcx, [rsp+0A8h+var_60]
0x18009e5a4  call    ?reset@?$com_ptr_t@UIAccessible2@@Uerr_exception_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IAccessible2,wil::err_exception_policy>::reset(void)
0x18009e5a9  lea     rcx, [rsp+0A8h+var_60]; punkNotSupportedValue
0x18009e5ae  call    UiaGetReservedNotSupportedValue
0x18009e5b3  mov     rcx, [rsp+0A8h]; this
0x18009e5bb  test    eax, eax
0x18009e5bd  js      short loc_18009E5EE
0x18009e5bf  lea     rdx, [rsp+0A8h+pvarg]; struct tagVARIANT *
0x18009e5c4  mov     rcx, qword ptr [rsp+0A8h+var_60]; struct IUnknown *
0x18009e5c9  call    ?InitVariantFromUnknown@@YAJPEAUIUnknown@@PEAUtagVARIANT@@@Z; InitVariantFromUnknown(IUnknown *,tagVARIANT *)
0x18009e5ce  mov     rcx, [rsp+0A8h]; this
0x18009e5d6  test    eax, eax
0x18009e5d8  jns     short loc_18009E603
0x18009e5da  mov     r9d, eax; char *
0x18009e5dd  lea     r8, aOnecoreWindows_173; "onecore\\windows\\accessibletech\\uiaut"...
0x18009e5e4  mov     edx, 473h; void *
0x18009e5e9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009e5ee  mov     r9d, eax; char *
0x18009e5f1  lea     r8, aOnecoreWindows_173; "onecore\\windows\\accessibletech\\uiaut"...
0x18009e5f8  mov     edx, 472h; void *
0x18009e5fd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18009e603  lea     rcx, [rsp+0A8h+var_60]; void *
0x18009e608  call    ??1?$com_ptr_t@UIAccessibleAction@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(void)
0x18009e60d  jmp     loc_18009E4F0
0x18009e612  lea     rax, [rsp+0A8h+var_60]
0x18009e617  mov     qword ptr [rsp+0A8h+var_88], rax
0x18009e61c  lea     rdx, IA2TextRange_GetAttributeValue_Start
0x18009e623  call    McGenEventWrite_EtwEventWriteTransfer
0x18009e628  jmp     loc_18009E439
0x18009e62d  jz      short loc_18009E665
0x18009e62f  mov     eax, 9C47h
0x18009e634  cmp     ebx, eax
0x18009e636  jg      short loc_18009E687
0x18009e638  jz      short loc_18009E665
0x18009e63a  mov     ecx, ebx
0x18009e63c  sub     ecx, 9C41h
0x18009e642  jz      short loc_18009E665
0x18009e644  sub     ecx, 1
0x18009e647  jz      loc_18009E494
0x18009e64d  sub     ecx, 2
0x18009e650  jz      short loc_18009E665
0x18009e652  sub     ecx, 1
0x18009e655  jmp     short loc_18009E65A
0x18009e657  sub     ecx, 2
0x18009e65a  jz      short loc_18009E665
0x18009e65c  cmp     ecx, 1
0x18009e65f  jnz     loc_18009E596
0x18009e665  mov     r8d, ebx
0x18009e668  lea     rdx, [rsp+0A8h+var_60]
0x18009e66d  mov     rcx, rdi
0x18009e670  call    ?GetAttributeValueFromTextAttributes@IA2ProxyTextRange@@AEAA?AV?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@H@Z; IA2ProxyTextRange::GetAttributeValueFromTextAttributes(int)
0x18009e675  mov     rdx, rax; VARIANTARG *
0x18009e678  lea     rcx, [rsp+0A8h+pvarg]; pvarg
0x18009e67d  call    ??4?$unique_struct@UtagVARIANT@@P6AJPEAU1@@Z$1?VariantClear@@YAJ0@ZP6AX0@Z$1?VariantInit@@YAX0@Z@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)>::operator=(wil::unique_struct<tagVARIANT,long (*)(tagVARIANT *),&VariantClear(tagVARIANT *),void (*)(tagVARIANT *),&VariantInit(tagVARIANT *)> &&)
0x18009e682  jmp     loc_18009E4E5
0x18009e687  mov     ecx, ebx
0x18009e689  sub     ecx, 9C48h
0x18009e68f  jz      short loc_18009E665
0x18009e691  sub     ecx, 5
0x18009e694  jz      loc_18009E494
0x18009e69a  sub     ecx, 1
0x18009e69d  jz      short loc_18009E665
0x18009e69f  cmp     ecx, 1
0x18009e6a2  jz      loc_18009E494
0x18009e6a8  jmp     loc_18009E596
0x18009e6ad  jz      short loc_18009E665
0x18009e6af  mov     ecx, ebx
0x18009e6b1  sub     ecx, 9C51h
0x18009e6b7  jz      short loc_18009E665
0x18009e6b9  sub     ecx, 8
0x18009e6bc  jz      short loc_18009E665
0x18009e6be  sub     ecx, 1
0x18009e6c1  jz      short loc_18009E665
0x18009e6c3  jmp     short loc_18009E657
0x18009e6c5  lea     rax, [rsp+0A8h+var_60]
0x18009e6ca  mov     qword ptr [rsp+0A8h+var_88], rax
0x18009e6cf  lea     rdx, IA2TextRange_GetAttributeValue_Stop
0x18009e6d6  call    McGenEventWrite_EtwEventWriteTransfer
0x18009e6db  jmp     loc_18009E538
0x18009e6e0  mov     eax, dword ptr [rsp+0A8h+var_60]
0x18009e6e4  jmp     loc_18009E53A
```
