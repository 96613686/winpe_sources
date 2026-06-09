# XmlLoad(wchar_t const *)

- ea: `0x140002c70`
- end: `0x14000347a`
- name: `?XmlLoad@@YA?AU?$com_ptr@UIXMLDOMDocument3@@@winrt@@PEB_W@Z`
- size: `2058`
- prototype: `__int64 __fastcall(char *, wchar_t *)`
- caller_count: `2`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140001ce0`
- `0x140019c4c`

## callees

- `0x140002c70`
- `0x140010450`
- `0x140022cec`
- `0x140029b20`
- `0x14002f6c8`
- `0x140031810`
- `0x140034010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140002cd7`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x140002cd7`
- `OLEAUT32!__imp_SysAllocString` at `0x140003158`
- `OLEAUT32!__imp_SysAllocString` at `0x140003158`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002deb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002e81`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002fa0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140003030`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002deb`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002e81`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140002fa0`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x140003030`
- `OLEAUT32!__imp_SysFreeString` at `0x14000321c`
- `OLEAUT32!__imp_SysFreeString` at `0x140003231`
- `OLEAUT32!__imp_SysFreeString` at `0x14000321c`
- `OLEAUT32!__imp_SysFreeString` at `0x140003231`
- `OLEAUT32!__imp_VariantInit` at `0x140002e63`
- `OLEAUT32!__imp_VariantInit` at `0x140003018`
- `OLEAUT32!__imp_VariantInit` at `0x140003149`
- `OLEAUT32!__imp_VariantInit` at `0x140002e63`
- `OLEAUT32!__imp_VariantInit` at `0x140003018`
- `OLEAUT32!__imp_VariantInit` at `0x140003149`
- `OLEAUT32!__imp_VariantClear` at `0x140003207`
- `OLEAUT32!__imp_VariantClear` at `0x140003212`
- `OLEAUT32!__imp_VariantClear` at `0x140003227`
- `OLEAUT32!__imp_VariantClear` at `0x140003207`
- `OLEAUT32!__imp_VariantClear` at `0x140003212`
- `OLEAUT32!__imp_VariantClear` at `0x140003227`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
LPVOID *__fastcall XmlLoad(LPVOID *a1, wchar_t *a2, const char *a3)
{
  HRESULT Instance; // ebx
  signed int v6; // ebx
  OLECHAR *v7; // rbx
  const char *v8; // r8
  const char *v9; // r8
  LPVOID v10; // rcx
  signed int v11; // edi
  OLECHAR *v12; // rdi
  const char *v13; // r8
  const char *v14; // r8
  LPVOID v15; // rcx
  signed int v16; // r15d
  const char *v17; // r8
  LPVOID v18; // rcx
  signed int v19; // r15d
  unsigned int v21; // ebx
  LPVOID *ppv; // [rsp+20h] [rbp-99h]
  VARIANTARG pExceptionObject[2]; // [rsp+40h] [rbp-79h] BYREF
  int v24; // [rsp+70h] [rbp-49h]
  VARIANTARG v25; // [rsp+78h] [rbp-41h] BYREF
  VARIANTARG v26; // [rsp+90h] [rbp-29h] BYREF
  VARIANTARG pvarg; // [rsp+A8h] [rbp-11h] BYREF
  OLECHAR *v28; // [rsp+C0h] [rbp+7h]
  OLECHAR *v29; // [rsp+C8h] [rbp+Fh]
  __int16 v30; // [rsp+128h] [rbp+6Fh] BYREF
  unsigned int v31; // [rsp+130h] [rbp+77h] BYREF
  struct IXMLDOMParseError *v32; // [rsp+138h] [rbp+7Fh] BYREF

  *a1 = 0;
  v24 = 1;
  v30 = 0;
  if ( !a2 || !*a2 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 87);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x57u, a3, 69);
    throw (EvtException *)pExceptionObject;
  }
  Instance = CoCreateInstance(&CLSID_DOMDocument60, 0, 1u, &IID_IXMLDOMDocument3, a1);
  if ( Instance < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)Instance);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, Instance, 0, 0, (const char *)ppv, 79, 0x20u, a2);
    throw (EvtException *)pExceptionObject;
  }
  v6 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)*a1 + 504LL))(*a1, 0);
  if ( v6 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        12,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)v6);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v6, 0, 0, (const char *)ppv, 85, 0x20u, a2);
    throw (EvtException *)pExceptionObject;
  }
  v7 = SysAllocStringLen(L"SelectionLanguage", 0x11u);
  v28 = v7;
  if ( !v7 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v8, 91);
    throw (EvtException *)pExceptionObject;
  }
  VariantInit(&pvarg);
  pvarg.vt = 8;
  pvarg.llVal = (LONGLONG)SysAllocStringLen(L"XPath", 5u);
  if ( !pvarg.llVal )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v9, 99);
    throw (EvtException *)pExceptionObject;
  }
  v10 = *a1;
  pExceptionObject[0] = pvarg;
  v11 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v10 + 640LL))(v10, v7, pExceptionObject);
  if ( v11 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)v11);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v11, 0, 0, (const char *)ppv, 105, 0x20u, a2);
    throw (EvtException *)pExceptionObject;
  }
  v12 = SysAllocStringLen(L"SelectionNamespaces", 0x13u);
  v29 = v12;
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v13, 111);
    throw (EvtException *)pExceptionObject;
  }
  VariantInit(&v26);
  v26.vt = 8;
  v26.llVal = (LONGLONG)SysAllocStringLen(L"xmlns:ns='http://schemas.microsoft.com/win/2004/08/events'", 0x3Au);
  if ( !v26.llVal )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v14, 119);
    throw (EvtException *)pExceptionObject;
  }
  v15 = *a1;
  pExceptionObject[0] = v26;
  v16 = (*(__int64 (__fastcall **)(LPVOID, OLECHAR *, VARIANTARG *))(*(_QWORD *)v15 + 640LL))(
          v15,
          v12,
          pExceptionObject);
  if ( v16 < 0 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        18,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)v16);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v16, 0, 0, (const char *)ppv, 125, 0x20u, a2);
    throw (EvtException *)pExceptionObject;
  }
  VariantInit(&v25);
  v25.vt = 8;
  v25.llVal = (LONGLONG)SysAllocString(a2);
  if ( !v25.llVal )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2147942414LL);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, 0x8007000E, v17, 133);
    throw (EvtException *)pExceptionObject;
  }
  v18 = *a1;
  pExceptionObject[0] = v25;
  v19 = (*(__int64 (__fastcall **)(LPVOID, VARIANTARG *, __int16 *))(*(_QWORD *)v18 + 464LL))(
          v18,
          pExceptionObject,
          &v30);
  if ( v19 < 0 || !v30 )
  {
    v32 = 0;
    if ( (*(int (__fastcall **)(LPVOID, struct IXMLDOMParseError **))(*(_QWORD *)*a1 + 480LL))(*a1, &v32) >= 0 )
    {
      v31 = 0;
      if ( ((int (__fastcall *)(struct IXMLDOMParseError *, unsigned int *))v32->lpVtbl->get_errorCode)(v32, &v31) >= 0 )
      {
        if ( v31 == -2146697210 )
        {
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, 2);
          }
          EvtException::EvtException((EvtException *)pExceptionObject, 2u, 0, 0, (const char *)ppv, 148, 0x20u, a2);
          throw (EvtException *)pExceptionObject;
        }
        DumpErrorInfo(v32, a2);
        v21 = v31;
        if ( !v31 )
          v21 = -2147418113;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids, v21);
        }
        EvtException::EvtException((EvtException *)pExceptionObject, v21, 0, 0, (const char *)ppv, 153, 0x20u, a2);
        throw (EvtException *)pExceptionObject;
      }
    }
    if ( !v19 )
      v19 = -2147418113;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids,
        (unsigned int)v19);
    }
    EvtException::EvtException((EvtException *)pExceptionObject, v19, 0, 0, (const char *)ppv, 157, 0x20u, a2);
    throw (EvtException *)pExceptionObject;
  }
  VariantClear(&v25);
  VariantClear(&v26);
  SysFreeString(v12);
  VariantClear(&pvarg);
  SysFreeString(v7);
  return a1;
}

```

## disassembly

```asm
0x140002c70  mov     [rsp-8+arg_0], rcx
0x140002c75  push    rbp
0x140002c76  push    rbx
0x140002c77  push    rsi
0x140002c78  push    rdi
0x140002c79  push    r12
0x140002c7b  push    r13
0x140002c7d  push    r14
0x140002c7f  push    r15
0x140002c81  lea     rbp, [rsp-1Fh]
0x140002c86  sub     rsp, 0D8h
0x140002c8d  mov     rsi, rdx
0x140002c90  mov     r14, rcx
0x140002c93  xor     r12d, r12d
0x140002c96  mov     [rbp+57h+var_A0], r12d
0x140002c9a  mov     [rcx], r12
0x140002c9d  mov     [rbp+57h+var_A0], 1
0x140002ca4  mov     [rbp+57h+arg_8], r12w
0x140002ca9  test    rdx, rdx
0x140002cac  jz      loc_140003418
0x140002cb2  cmp     [rdx], r12w
0x140002cb6  jz      loc_140003418
0x140002cbc  mov     [rsp+110h+ppv], rcx; char *
0x140002cc1  lea     r9, IID_IXMLDOMDocument3; riid
0x140002cc8  xor     edx, edx; pUnkOuter
0x140002cca  mov     r8d, 1; dwClsContext
0x140002cd0  lea     rcx, CLSID_DOMDocument60; rclsid
0x140002cd7  call    cs:__imp_CoCreateInstance
0x140002cdd  mov     ebx, eax
0x140002cdf  test    eax, eax
0x140002ce1  jns     short loc_140002D54
0x140002ce3  lea     rax, WPP_GLOBAL_Control
0x140002cea  mov     rcx, cs:WPP_GLOBAL_Control
0x140002cf1  cmp     rcx, rax
0x140002cf4  jz      short loc_140002D1D
0x140002cf6  test    dword ptr [rcx+1Ch], 400000h
0x140002cfd  jz      short loc_140002D1D
0x140002cff  cmp     byte ptr [rcx+19h], 2
0x140002d03  jb      short loc_140002D1D
0x140002d05  mov     edx, 0Bh
0x140002d0a  mov     r9d, ebx
0x140002d0d  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002d14  mov     rcx, [rcx+10h]
0x140002d18  call    WPP_SF_d
0x140002d1d  mov     [rsp+110h+Src], rsi; Src
0x140002d22  mov     [rsp+110h+var_E0], 20h ; ' '; unsigned int
0x140002d2a  mov     [rsp+110h+var_E8], 4Fh ; 'O'; int
0x140002d32  xor     r9d, r9d; unsigned int
0x140002d35  xor     r8d, r8d; unsigned int
0x140002d38  mov     edx, ebx; unsigned int
0x140002d3a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002d3e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140002d43  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002d4a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140002d4e  call    _CxxThrowException_0
0x140002d54  mov     rcx, [r14]
0x140002d57  mov     rax, [rcx]
0x140002d5a  xor     edx, edx
0x140002d5c  mov     rax, [rax+1F8h]
0x140002d63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002d68  mov     ebx, eax
0x140002d6a  test    eax, eax
0x140002d6c  jns     short loc_140002DDF
0x140002d6e  lea     rax, WPP_GLOBAL_Control
0x140002d75  mov     rcx, cs:WPP_GLOBAL_Control
0x140002d7c  cmp     rcx, rax
0x140002d7f  jz      short loc_140002DA8
0x140002d81  test    dword ptr [rcx+1Ch], 400000h
0x140002d88  jz      short loc_140002DA8
0x140002d8a  cmp     byte ptr [rcx+19h], 2
0x140002d8e  jb      short loc_140002DA8
0x140002d90  mov     edx, 0Ch
0x140002d95  mov     r9d, ebx
0x140002d98  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002d9f  mov     rcx, [rcx+10h]
0x140002da3  call    WPP_SF_d
0x140002da8  mov     [rsp+110h+Src], rsi; Src
0x140002dad  mov     [rsp+110h+var_E0], 20h ; ' '; unsigned int
0x140002db5  mov     [rsp+110h+var_E8], 55h ; 'U'; int
0x140002dbd  xor     r9d, r9d; unsigned int
0x140002dc0  xor     r8d, r8d; unsigned int
0x140002dc3  mov     edx, ebx; unsigned int
0x140002dc5  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002dc9  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140002dce  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002dd5  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140002dd9  call    _CxxThrowException_0
0x140002ddf  mov     edx, 11h; ui
0x140002de4  mov     rcx, cs:strIn; strIn
0x140002deb  call    cs:__imp_SysAllocStringLen
0x140002df1  mov     rbx, rax
0x140002df4  mov     [rbp+57h+var_50], rax
0x140002df8  test    rax, rax
0x140002dfb  jnz     short loc_140002E5F
0x140002dfd  lea     rax, WPP_GLOBAL_Control
0x140002e04  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e0b  cmp     rcx, rax
0x140002e0e  jz      short loc_140002E3A
0x140002e10  test    dword ptr [rcx+1Ch], 400000h
0x140002e17  jz      short loc_140002E3A
0x140002e19  cmp     byte ptr [rcx+19h], 2
0x140002e1d  jb      short loc_140002E3A
0x140002e1f  mov     edx, 0Dh
0x140002e24  mov     r9d, 8007000Eh
0x140002e2a  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002e31  mov     rcx, [rcx+10h]
0x140002e35  call    WPP_SF_d
0x140002e3a  mov     edx, 8007000Eh; unsigned int
0x140002e3f  mov     r9d, 5Bh ; '['; int
0x140002e45  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002e49  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140002e4e  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002e55  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140002e59  call    _CxxThrowException_0
0x140002e5f  lea     rcx, [rbp+57h+pvarg]; pvarg
0x140002e63  call    cs:__imp_VariantInit
0x140002e69  nop
0x140002e6a  mov     r13d, 8
0x140002e70  mov     word ptr [rbp+57h+pvarg], r13w
0x140002e75  mov     edx, 5; ui
0x140002e7a  mov     rcx, cs:off_140035030; strIn
0x140002e81  call    cs:__imp_SysAllocStringLen
0x140002e87  mov     qword ptr [rbp+57h+pvarg+8], rax
0x140002e8b  test    rax, rax
0x140002e8e  jnz     short loc_140002EF2
0x140002e90  lea     rax, WPP_GLOBAL_Control
0x140002e97  mov     rcx, cs:WPP_GLOBAL_Control
0x140002e9e  cmp     rcx, rax
0x140002ea1  jz      short loc_140002ECD
0x140002ea3  test    dword ptr [rcx+1Ch], 400000h
0x140002eaa  jz      short loc_140002ECD
0x140002eac  cmp     byte ptr [rcx+19h], 2
0x140002eb0  jb      short loc_140002ECD
0x140002eb2  mov     edx, 0Eh
0x140002eb7  mov     r9d, 8007000Eh
0x140002ebd  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002ec4  mov     rcx, [rcx+10h]
0x140002ec8  call    WPP_SF_d
0x140002ecd  mov     edx, 8007000Eh; unsigned int
0x140002ed2  mov     r9d, 63h ; 'c'; int
0x140002ed8  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002edc  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140002ee1  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002ee8  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140002eec  call    _CxxThrowException_0
0x140002ef2  mov     rcx, [r14]
0x140002ef5  movups  xmm0, xmmword ptr [rbp+57h+pvarg]
0x140002ef9  movaps  [rbp+57h+pExceptionObject], xmm0
0x140002efd  movsd   xmm1, qword ptr [rbp+57h+pvarg+10h]
0x140002f02  movsd   [rbp+57h+var_C0], xmm1
0x140002f07  mov     rax, [rcx]
0x140002f0a  lea     r8, [rbp+57h+pExceptionObject]
0x140002f0e  mov     rdx, rbx
0x140002f11  mov     rax, [rax+280h]
0x140002f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f1d  mov     edi, eax
0x140002f1f  test    eax, eax
0x140002f21  jns     short loc_140002F94
0x140002f23  lea     rax, WPP_GLOBAL_Control
0x140002f2a  mov     rcx, cs:WPP_GLOBAL_Control
0x140002f31  cmp     rcx, rax
0x140002f34  jz      short loc_140002F5D
0x140002f36  test    dword ptr [rcx+1Ch], 400000h
0x140002f3d  jz      short loc_140002F5D
0x140002f3f  cmp     byte ptr [rcx+19h], 2
0x140002f43  jb      short loc_140002F5D
0x140002f45  mov     edx, 0Fh
0x140002f4a  mov     r9d, edi
0x140002f4d  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002f54  mov     rcx, [rcx+10h]
0x140002f58  call    WPP_SF_d
0x140002f5d  mov     [rsp+110h+Src], rsi; Src
0x140002f62  mov     [rsp+110h+var_E0], 20h ; ' '; unsigned int
0x140002f6a  mov     [rsp+110h+var_E8], 69h ; 'i'; int
0x140002f72  xor     r9d, r9d; unsigned int
0x140002f75  xor     r8d, r8d; unsigned int
0x140002f78  mov     edx, edi; unsigned int
0x140002f7a  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002f7e  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140002f83  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140002f8a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x140002f8e  call    _CxxThrowException_0
0x140002f94  mov     edx, 13h; ui
0x140002f99  mov     rcx, cs:off_140035060; strIn
0x140002fa0  call    cs:__imp_SysAllocStringLen
0x140002fa6  mov     rdi, rax
0x140002fa9  mov     [rbp+57h+var_48], rax
0x140002fad  test    rax, rax
0x140002fb0  jnz     short loc_140003014
0x140002fb2  lea     rax, WPP_GLOBAL_Control
0x140002fb9  mov     rcx, cs:WPP_GLOBAL_Control
0x140002fc0  cmp     rcx, rax
0x140002fc3  jz      short loc_140002FEF
0x140002fc5  test    dword ptr [rcx+1Ch], 400000h
0x140002fcc  jz      short loc_140002FEF
0x140002fce  cmp     byte ptr [rcx+19h], 2
0x140002fd2  jb      short loc_140002FEF
0x140002fd4  mov     edx, 10h
0x140002fd9  mov     r9d, 8007000Eh
0x140002fdf  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140002fe6  mov     rcx, [rcx+10h]
0x140002fea  call    WPP_SF_d
0x140002fef  mov     edx, 8007000Eh; unsigned int
0x140002ff4  mov     r9d, 6Fh ; 'o'; int
0x140002ffa  lea     rcx, [rbp+57h+pExceptionObject]; this
0x140002ffe  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003003  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000300a  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000300e  call    _CxxThrowException_0
0x140003014  lea     rcx, [rbp+57h+var_80]; pvarg
0x140003018  call    cs:__imp_VariantInit
0x14000301e  nop
0x14000301f  mov     word ptr [rbp+57h+var_80], r13w
0x140003024  mov     edx, 3Ah ; ':'; ui
0x140003029  mov     rcx, cs:off_140035040; strIn
0x140003030  call    cs:__imp_SysAllocStringLen
0x140003036  mov     qword ptr [rbp+57h+var_80+8], rax
0x14000303a  test    rax, rax
0x14000303d  jnz     short loc_1400030A1
0x14000303f  lea     rax, WPP_GLOBAL_Control
0x140003046  mov     rcx, cs:WPP_GLOBAL_Control
0x14000304d  cmp     rcx, rax
0x140003050  jz      short loc_14000307C
0x140003052  test    dword ptr [rcx+1Ch], 400000h
0x140003059  jz      short loc_14000307C
0x14000305b  cmp     byte ptr [rcx+19h], 2
0x14000305f  jb      short loc_14000307C
0x140003061  mov     edx, 11h
0x140003066  mov     r9d, 8007000Eh
0x14000306c  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140003073  mov     rcx, [rcx+10h]
0x140003077  call    WPP_SF_d
0x14000307c  mov     edx, 8007000Eh; unsigned int
0x140003081  mov     r9d, 77h ; 'w'; int
0x140003087  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000308b  call    ??0EvtException@@QEAA@KPEBDH@Z; EvtException::EvtException(ulong,char const *,int)
0x140003090  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x140003097  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000309b  call    _CxxThrowException_0
0x1400030a1  mov     rcx, [r14]
0x1400030a4  movups  xmm0, xmmword ptr [rbp+57h+var_80]
0x1400030a8  movaps  [rbp+57h+pExceptionObject], xmm0
0x1400030ac  movsd   xmm1, qword ptr [rbp+57h+var_80+10h]
0x1400030b1  movsd   [rbp+57h+var_C0], xmm1
0x1400030b6  mov     rax, [rcx]
0x1400030b9  lea     r8, [rbp+57h+pExceptionObject]
0x1400030bd  mov     rdx, rdi
0x1400030c0  mov     rax, [rax+280h]
0x1400030c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030cc  mov     r15d, eax
0x1400030cf  test    eax, eax
0x1400030d1  jns     short loc_140003145
0x1400030d3  lea     rax, WPP_GLOBAL_Control
0x1400030da  mov     rcx, cs:WPP_GLOBAL_Control
0x1400030e1  cmp     rcx, rax
0x1400030e4  jz      short loc_14000310D
0x1400030e6  test    dword ptr [rcx+1Ch], 400000h
0x1400030ed  jz      short loc_14000310D
0x1400030ef  cmp     byte ptr [rcx+19h], 2
0x1400030f3  jb      short loc_14000310D
0x1400030f5  mov     edx, 12h
0x1400030fa  mov     r9d, r15d
0x1400030fd  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x140003104  mov     rcx, [rcx+10h]
0x140003108  call    WPP_SF_d
0x14000310d  mov     [rsp+110h+Src], rsi; Src
0x140003112  mov     [rsp+110h+var_E0], 20h ; ' '; unsigned int
0x14000311a  mov     [rsp+110h+var_E8], 7Dh ; '}'; int
0x140003122  xor     r9d, r9d; unsigned int
0x140003125  xor     r8d, r8d; unsigned int
0x140003128  mov     edx, r15d; unsigned int
0x14000312b  lea     rcx, [rbp+57h+pExceptionObject]; this
0x14000312f  call    ??0EvtException@@QEAA@KKKPEBDHKPEB_W@Z; EvtException::EvtException(ulong,ulong,ulong,char const *,int,ulong,wchar_t const *)
0x140003134  lea     rdx, _TI1?AVEvtException@@; pThrowInfo
0x14000313b  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x14000313f  call    _CxxThrowException_0
0x140003145  lea     rcx, [rbp+57h+var_98]; pvarg
0x140003149  call    cs:__imp_VariantInit
0x14000314f  nop
0x140003150  mov     word ptr [rbp+57h+var_98], r13w
0x140003155  mov     rcx, rsi; psz
0x140003158  call    cs:__imp_SysAllocString
0x14000315e  mov     qword ptr [rbp+57h+var_98+8], rax
0x140003162  test    rax, rax
0x140003165  jnz     short loc_1400031C9
0x140003167  lea     rax, WPP_GLOBAL_Control
0x14000316e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003175  cmp     rcx, rax
0x140003178  jz      short loc_1400031A4
0x14000317a  test    dword ptr [rcx+1Ch], 400000h
0x140003181  jz      short loc_1400031A4
0x140003183  cmp     byte ptr [rcx+19h], 2
0x140003187  jb      short loc_1400031A4
0x140003189  mov     edx, 13h
0x14000318e  mov     r9d, 8007000Eh
0x140003194  lea     r8, WPP_b5eee6dfe5e5327afdf1cdaca9dcbb97_Traceguids
0x14000319b  mov     rcx, [rcx+10h]
0x14000319f  call    WPP_SF_d
0x1400031a4  mov     edx, 8007000Eh; unsigned int
0x1400031a9  mov     r9d, 85h; int
  ... truncated ...
```
