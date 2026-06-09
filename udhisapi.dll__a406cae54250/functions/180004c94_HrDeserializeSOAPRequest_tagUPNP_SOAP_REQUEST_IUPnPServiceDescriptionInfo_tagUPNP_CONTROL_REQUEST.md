# HrDeserializeSOAPRequest(tagUPNP_SOAP_REQUEST *,IUPnPServiceDescriptionInfo *,tagUPNP_CONTROL_REQUEST *)

- ea: `0x180004c94`
- end: `0x180005124`
- name: `?HrDeserializeSOAPRequest@@YAJPEAUtagUPNP_SOAP_REQUEST@@PEAUIUPnPServiceDescriptionInfo@@PEAUtagUPNP_CONTROL_REQUEST@@@Z`
- size: `1168`
- prototype: `__int64 __fastcall(const OLECHAR **, struct IUPnPServiceDescriptionInfo *, struct tagUPNP_CONTROL_REQUEST *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x18000512c`

## callees

- `0x180001c96`
- `0x180003728`
- `0x1800038ec`
- `0x180003960`
- `0x180004c94`
- `0x18000afb4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004d3f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x180004d3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fce`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180004fce`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004cf0`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpW` at `0x180004cf0`
- `OLEAUT32!__imp_SysAllocString` at `0x180004cc9`
- `OLEAUT32!__imp_SysAllocString` at `0x180004cc9`
- `OLEAUT32!__imp_SysFreeString` at `0x180004f8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fa5`
- `OLEAUT32!__imp_SysFreeString` at `0x180004f8f`
- `OLEAUT32!__imp_SysFreeString` at `0x180004fa5`

## string_xrefs

- `0x180004e79`: `HrDeserializeSOAPRequest(): Failed to get variable name for QSV request`
- `0x180004f03`: `HrDeserializeSOAPRequest(): Failed to get node value`
- `0x180004f5a`: `HrDeserializeSOAPRequest(): Failed to get item from list`
- `0x180005028`: `HrDeserializeSOAPRequest(): Failed to allocate array of variant arguments`
- `0x18000505c`: `HrDeserializeSOAPRequest(): Failed to get argument list length`
- `0x1800050a8`: `HrDeserializeSOAPRequest(): Failed to allocate memory to copy action name`
- `0x1800050ee`: `HrDeserializeSOAPRequest(): Exiting`

## pseudocode

```c
__int64 __fastcall HrDeserializeSOAPRequest(
        const OLECHAR **a1,
        struct IUPnPServiceDescriptionInfo *a2,
        struct tagUPNP_CONTROL_REQUEST *a3)
{
  const OLECHAR *v4; // rcx
  struct tagVARIANT *v5; // rsi
  const WCHAR *v8; // rax
  const WCHAR *v9; // rbx
  int v10; // eax
  const OLECHAR *v11; // rcx
  int v12; // r12d
  int v13; // eax
  int TypedValueFromElement; // edi
  size_t v15; // rbx
  unsigned int v16; // r14d
  unsigned int v17; // r14d
  struct tagVARIANT *v18; // rbx
  _QWORD *v19; // rcx
  LONGLONG llVal; // r9
  __int64 v21; // rdx
  _QWORD *v22; // rcx
  int v23; // edx
  const char *v24; // r9
  __int64 i; // r14
  unsigned int v27; // [rsp+30h] [rbp-40h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-38h] BYREF
  LPVOID v29; // [rsp+40h] [rbp-30h] BYREF
  struct IXMLDOMNode *v30; // [rsp+48h] [rbp-28h] BYREF
  __int128 v31; // [rsp+50h] [rbp-20h] BYREF
  struct tagVARIANT *v32; // [rsp+60h] [rbp-10h]
  unsigned int v34; // [rsp+C8h] [rbp+58h] BYREF

  v4 = *a1;
  v5 = 0;
  v31 = 0;
  v32 = 0;
  v8 = SysAllocString(v4);
  *(_QWORD *)&v31 = v8;
  v9 = v8;
  if ( !v8 )
  {
    TypedValueFromElement = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        67,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrDeserializeSOAPRequest(): Failed to allocate memory to copy action name",
        14);
    goto LABEL_56;
  }
  v10 = lstrcmpW(v8, L"QueryStateVariable");
  v11 = a1[1];
  v12 = v10;
  if ( !v11 )
  {
    TypedValueFromElement = 0;
    goto LABEL_52;
  }
  v27 = 0;
  v13 = (*(__int64 (__fastcall **)(const OLECHAR *, unsigned int *))(*(_QWORD *)v11 + 64LL))(v11, &v27);
  TypedValueFromElement = v13;
  if ( v13 < 0 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        66,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrDeserializeSOAPRequest(): Failed to get argument list length",
        v13);
    goto LABEL_43;
  }
  if ( !v27 )
  {
LABEL_52:
    DWORD2(v31) = 0;
    v32 = 0;
    goto LABEL_43;
  }
  DWORD2(v31) = v27;
  v15 = 24LL * v27;
  v16 = v27;
  v5 = (struct tagVARIANT *)malloc(v15);
  v32 = v5;
  if ( !v5 )
  {
    TypedValueFromElement = -2147024882;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        65,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrDeserializeSOAPRequest(): Failed to allocate array of variant arguments",
        14);
      goto LABEL_42;
    }
    goto LABEL_56;
  }
  v34 = 0;
  pv = 0;
  v29 = 0;
  memset_0(v5, 0, v15);
  if ( v12 )
  {
    TypedValueFromElement = (*(__int64 (__fastcall **)(struct IUPnPServiceDescriptionInfo *, _QWORD, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)a2 + 32LL))(
                              a2,
                              v31,
                              &v34,
                              &pv,
                              &v29);
    if ( TypedValueFromElement < 0 )
    {
LABEL_56:
      CleanupDeserializedRequest((struct tagUPNP_CONTROL_REQUEST *)&v31);
      goto LABEL_57;
    }
    if ( v34 != v16 )
    {
      TypedValueFromElement = -2147467259;
      goto LABEL_56;
    }
  }
  v17 = 0;
  while ( (int)v17 < (int)v27 )
  {
    v30 = 0;
    TypedValueFromElement = (*(__int64 (__fastcall **)(const OLECHAR *, _QWORD, struct IXMLDOMNode **))(*(_QWORD *)a1[1] + 56LL))(
                              a1[1],
                              v17,
                              &v30);
    if ( TypedValueFromElement >= 0 )
    {
      if ( v12 )
      {
        TypedValueFromElement = HrGetTypedValueFromElement(v30, *((OLECHAR **)v29 + (int)v17), &v5[v17]);
        if ( TypedValueFromElement >= 0 )
        {
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            v21 = 62;
            llVal = *((_QWORD *)pv + (int)v17);
LABEL_25:
            WPP_SF_S(v19[2], v21, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids, llVal);
          }
LABEL_32:
          ((void (__fastcall *)(struct IXMLDOMNode *))v30->lpVtbl->Release)(v30);
          goto LABEL_35;
        }
        if ( TypedValueFromElement == -2147467259 )
          TypedValueFromElement = -2147220984;
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v23 = 63;
        v24 = "HrDeserializeSOAPRequest(): Failed to get node value";
      }
      else
      {
        v18 = &v5[v17];
        TypedValueFromElement = ((__int64 (__fastcall *)(struct IXMLDOMNode *, ULONG *))v30->lpVtbl->get_text)(
                                  v30,
                                  &v18->decVal.Lo32);
        if ( TypedValueFromElement >= 0 )
        {
          v5[v17].vt = 8;
          v19 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            llVal = v18->llVal;
            v21 = 60;
            goto LABEL_25;
          }
          goto LABEL_32;
        }
        v22 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
          goto LABEL_32;
        v23 = 61;
        v24 = "HrDeserializeSOAPRequest(): Failed to get variable name for QSV request";
      }
      WPP_SF_sd(
        v22[2],
        v23,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (_DWORD)v24,
        TypedValueFromElement);
      goto LABEL_32;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        64,
        (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
        (unsigned int)"HrDeserializeSOAPRequest(): Failed to get item from list",
        TypedValueFromElement);
      break;
    }
LABEL_35:
    ++v17;
    if ( TypedValueFromElement < 0 )
      break;
  }
  if ( v12 )
  {
    for ( i = 0; (unsigned int)i < v34; i = (unsigned int)(i + 1) )
    {
      SysFreeString(*((BSTR *)pv + i));
      *((_QWORD *)pv + i) = 0;
      SysFreeString(*((BSTR *)v29 + i));
      *((_QWORD *)v29 + i) = 0;
    }
    CoTaskMemFree(pv);
    pv = 0;
    CoTaskMemFree(v29);
  }
LABEL_42:
  v9 = (const WCHAR *)v31;
LABEL_43:
  if ( TypedValueFromElement < 0 )
    goto LABEL_56;
  CleanupDeserializedRequest(a3);
  *((_DWORD *)a3 + 2) = DWORD2(v31);
  *(_QWORD *)a3 = v9;
  *((_QWORD *)a3 + 2) = v5;
LABEL_57:
  if ( TypedValueFromElement
    && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      68,
      (unsigned int)WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids,
      (unsigned int)"HrDeserializeSOAPRequest(): Exiting",
      TypedValueFromElement);
  }
  return (unsigned int)TypedValueFromElement;
}

```

## disassembly

```asm
0x180004c94  mov     [rsp-38h+arg_8], rbx
0x180004c99  mov     [rsp-38h+arg_0], rcx
0x180004c9e  push    rbp
0x180004c9f  push    rsi
0x180004ca0  push    rdi
0x180004ca1  push    r12
0x180004ca3  push    r13
0x180004ca5  push    r14
0x180004ca7  push    r15
0x180004ca9  mov     rbp, rsp
0x180004cac  sub     rsp, 70h
0x180004cb0  mov     rdi, rcx
0x180004cb3  xorps   xmm0, xmm0
0x180004cb6  mov     rcx, [rcx]; psz
0x180004cb9  xor     esi, esi
0x180004cbb  movups  [rbp+var_20], xmm0
0x180004cbf  mov     [rbp+var_10], rsi
0x180004cc3  mov     r13, r8
0x180004cc6  mov     r15, rdx
0x180004cc9  call    cs:__imp_SysAllocString
0x180004ccf  mov     qword ptr [rbp+var_20], rax
0x180004cd3  mov     rbx, rax
0x180004cd6  lea     r14, WPP_GLOBAL_Control
0x180004cdd  test    rax, rax
0x180004ce0  jz      loc_18000508B
0x180004ce6  lea     rdx, aQuerystatevari; "QueryStateVariable"
0x180004ced  mov     rcx, rax; lpString1
0x180004cf0  call    cs:__imp_lstrcmpW
0x180004cf6  mov     rcx, [rdi+8]
0x180004cfa  mov     r12d, eax
0x180004cfd  test    rcx, rcx
0x180004d00  jz      loc_18000507D
0x180004d06  mov     [rbp+var_40], esi
0x180004d09  lea     rdx, [rbp+var_40]
0x180004d0d  mov     rax, [rcx]
0x180004d10  mov     rax, [rax+40h]
0x180004d14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d19  mov     edi, eax
0x180004d1b  test    eax, eax
0x180004d1d  js      loc_180005046
0x180004d23  mov     eax, [rbp+var_40]
0x180004d26  test    eax, eax
0x180004d28  jz      loc_18000507F
0x180004d2e  lea     rbx, [rax+rax*2]
0x180004d32  mov     dword ptr [rbp+var_20+8], eax
0x180004d35  shl     rbx, 3
0x180004d39  mov     r14d, eax
0x180004d3c  mov     rcx, rbx; Size
0x180004d3f  call    cs:__imp_malloc
0x180004d45  mov     rsi, rax
0x180004d48  mov     [rbp+var_10], rax
0x180004d4c  xor     eax, eax
0x180004d4e  test    rsi, rsi
0x180004d51  jz      loc_180004FFC
0x180004d57  mov     r8, rbx; Size
0x180004d5a  mov     [rbp+arg_18], eax
0x180004d5d  xor     edx, edx; Val
0x180004d5f  mov     [rbp+pv], rax
0x180004d63  mov     rcx, rsi; void *
0x180004d66  mov     [rbp+var_30], rax
0x180004d6a  call    memset_0
0x180004d6f  test    r12d, r12d
0x180004d72  jz      short loc_180004DB2
0x180004d74  mov     rax, [r15]
0x180004d77  lea     rcx, [rbp+var_30]
0x180004d7b  mov     rdx, qword ptr [rbp+var_20]
0x180004d7f  lea     r9, [rbp+pv]
0x180004d83  mov     [rsp+70h+var_50], rcx
0x180004d88  lea     r8, [rbp+arg_18]
0x180004d8c  mov     rcx, r15
0x180004d8f  mov     rax, [rax+20h]
0x180004d93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d98  mov     edi, eax
0x180004d9a  test    eax, eax
0x180004d9c  js      loc_1800050C4
0x180004da2  cmp     [rbp+arg_18], r14d
0x180004da6  jz      short loc_180004DB2
0x180004da8  mov     edi, 80004005h
0x180004dad  jmp     loc_1800050C4
0x180004db2  xor     r14d, r14d
0x180004db5  cmp     r14d, [rbp+var_40]
0x180004db9  jge     loc_180004F76
0x180004dbf  mov     rax, [rbp+arg_0]
0x180004dc3  lea     r8, [rbp+var_28]
0x180004dc7  mov     [rbp+var_28], 0
0x180004dcf  mov     edx, r14d
0x180004dd2  mov     rcx, [rax+8]
0x180004dd6  mov     rax, [rcx]
0x180004dd9  mov     rax, [rax+38h]
0x180004ddd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004de2  mov     edi, eax
0x180004de4  test    eax, eax
0x180004de6  js      loc_180004F30
0x180004dec  mov     rcx, [rbp+var_28]; struct IXMLDOMNode *
0x180004df0  movsxd  rbx, r14d
0x180004df3  lea     r15, [rbx+rbx*2]
0x180004df7  test    r12d, r12d
0x180004dfa  jnz     loc_180004E85
0x180004e00  mov     rax, [rcx]
0x180004e03  lea     rbx, [rsi+r15*8]
0x180004e07  lea     rdx, [rbx+8]
0x180004e0b  mov     rax, [rax+0D0h]
0x180004e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e17  mov     edi, eax
0x180004e19  test    eax, eax
0x180004e1b  js      short loc_180004E53
0x180004e1d  mov     word ptr [rsi+r15*8], 8
0x180004e24  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e2b  lea     rax, WPP_GLOBAL_Control
0x180004e32  cmp     rcx, rax
0x180004e35  jz      loc_180004F1E
0x180004e3b  test    dword ptr [rcx+1Ch], 400h
0x180004e42  jz      loc_180004F1E
0x180004e48  mov     r9, [rbx+8]
0x180004e4c  lea     edx, [r12+3Ch]
0x180004e51  jmp     short loc_180004EC5
0x180004e53  mov     rcx, cs:WPP_GLOBAL_Control
0x180004e5a  lea     rax, WPP_GLOBAL_Control
0x180004e61  cmp     rcx, rax
0x180004e64  jz      loc_180004F1E
0x180004e6a  test    byte ptr [rcx+1Ch], 1
0x180004e6e  jz      loc_180004F1E
0x180004e74  mov     edx, 3Dh ; '='
0x180004e79  lea     r9, aHrdeserializes_5; "HrDeserializeSOAPRequest(): Failed to g"...
0x180004e80  jmp     loc_180004F0A
0x180004e85  mov     rdx, [rbp+var_30]
0x180004e89  lea     r8, [rsi+r15*8]; struct tagVARIANT *
0x180004e8d  mov     rdx, [rdx+rbx*8]; psz
0x180004e91  call    ?HrGetTypedValueFromElement@@YAJPEAUIXMLDOMNode@@QEBGPEAUtagVARIANT@@@Z; HrGetTypedValueFromElement(IXMLDOMNode *,ushort const * const,tagVARIANT *)
0x180004e96  mov     edi, eax
0x180004e98  test    eax, eax
0x180004e9a  js      short loc_180004ED7
0x180004e9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180004ea3  lea     rax, WPP_GLOBAL_Control
0x180004eaa  cmp     rcx, rax
0x180004ead  jz      short loc_180004F1E
0x180004eaf  test    dword ptr [rcx+1Ch], 400h
0x180004eb6  jz      short loc_180004F1E
0x180004eb8  mov     r9, [rbp+pv]
0x180004ebc  mov     edx, 3Eh ; '>'
0x180004ec1  mov     r9, [r9+rbx*8]
0x180004ec5  mov     rcx, [rcx+10h]
0x180004ec9  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004ed0  call    WPP_SF_S
0x180004ed5  jmp     short loc_180004F1E
0x180004ed7  cmp     edi, 80004005h
0x180004edd  mov     eax, 80040208h
0x180004ee2  cmovz   edi, eax
0x180004ee5  mov     rcx, cs:WPP_GLOBAL_Control
0x180004eec  lea     rax, WPP_GLOBAL_Control
0x180004ef3  cmp     rcx, rax
0x180004ef6  jz      short loc_180004F1E
0x180004ef8  test    byte ptr [rcx+1Ch], 1
0x180004efc  jz      short loc_180004F1E
0x180004efe  mov     edx, 3Fh ; '?'
0x180004f03  lea     r9, aHrdeserializes_1; "HrDeserializeSOAPRequest(): Failed to g"...
0x180004f0a  mov     rcx, [rcx+10h]
0x180004f0e  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004f15  mov     dword ptr [rsp+70h+var_50], edi
0x180004f19  call    WPP_SF_sd
0x180004f1e  mov     rcx, [rbp+var_28]
0x180004f22  mov     rax, [rcx]
0x180004f25  mov     rax, [rax+10h]
0x180004f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f2e  jmp     short loc_180004F49
0x180004f30  mov     rcx, cs:WPP_GLOBAL_Control
0x180004f37  lea     rax, WPP_GLOBAL_Control
0x180004f3e  cmp     rcx, rax
0x180004f41  jz      short loc_180004F49
0x180004f43  test    byte ptr [rcx+1Ch], 1
0x180004f47  jnz     short loc_180004F56
0x180004f49  inc     r14d
0x180004f4c  test    edi, edi
0x180004f4e  jns     loc_180004DB5
0x180004f54  jmp     short loc_180004F76
0x180004f56  mov     rcx, [rcx+10h]
0x180004f5a  lea     r9, aHrdeserializes_2; "HrDeserializeSOAPRequest(): Failed to g"...
0x180004f61  mov     edx, 40h ; '@'
0x180004f66  mov     dword ptr [rsp+70h+var_50], edi
0x180004f6a  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180004f71  call    WPP_SF_sd
0x180004f76  test    r12d, r12d
0x180004f79  jz      short loc_180004FD4
0x180004f7b  xor     r14d, r14d
0x180004f7e  xor     r15d, r15d
0x180004f81  cmp     [rbp+arg_18], r15d
0x180004f85  jbe     short loc_180004FBC
0x180004f87  mov     rcx, [rbp+pv]
0x180004f8b  mov     rcx, [rcx+r14*8]; bstrString
0x180004f8f  call    cs:__imp_SysFreeString
0x180004f95  mov     rax, [rbp+pv]
0x180004f99  mov     [rax+r14*8], r15
0x180004f9d  mov     rcx, [rbp+var_30]
0x180004fa1  mov     rcx, [rcx+r14*8]; bstrString
0x180004fa5  call    cs:__imp_SysFreeString
0x180004fab  mov     rax, [rbp+var_30]
0x180004faf  mov     [rax+r14*8], r15
0x180004fb3  inc     r14d
0x180004fb6  cmp     r14d, [rbp+arg_18]
0x180004fba  jb      short loc_180004F87
0x180004fbc  mov     rcx, [rbp+pv]; pv
0x180004fc0  call    cs:__imp_CoTaskMemFree
0x180004fc6  mov     rcx, [rbp+var_30]; pv
0x180004fca  mov     [rbp+pv], r15
0x180004fce  call    cs:__imp_CoTaskMemFree
0x180004fd4  mov     rbx, qword ptr [rbp+var_20]
0x180004fd8  test    edi, edi
0x180004fda  js      loc_1800050C4
0x180004fe0  mov     rcx, r13; struct tagUPNP_CONTROL_REQUEST *
0x180004fe3  call    ?CleanupDeserializedRequest@@YAXPEAUtagUPNP_CONTROL_REQUEST@@@Z; CleanupDeserializedRequest(tagUPNP_CONTROL_REQUEST *)
0x180004fe8  mov     eax, dword ptr [rbp+var_20+8]
0x180004feb  mov     [r13+8], eax
0x180004fef  mov     [r13+0], rbx
0x180004ff3  mov     [r13+10h], rsi
0x180004ff7  jmp     loc_1800050CD
0x180004ffc  mov     eax, 8007000Eh
0x180005001  mov     edi, eax
0x180005003  mov     rcx, cs:WPP_GLOBAL_Control
0x18000500a  lea     rdx, WPP_GLOBAL_Control
0x180005011  cmp     rcx, rdx
0x180005014  jz      loc_1800050C4
0x18000501a  test    byte ptr [rcx+1Ch], 1
0x18000501e  jz      loc_1800050C4
0x180005024  mov     rcx, [rcx+10h]
0x180005028  lea     r9, aHrdeserializes_3; "HrDeserializeSOAPRequest(): Failed to a"...
0x18000502f  mov     edx, 41h ; 'A'
0x180005034  mov     dword ptr [rsp+70h+var_50], eax
0x180005038  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x18000503f  call    WPP_SF_sd
0x180005044  jmp     short loc_180004FD4
0x180005046  mov     rcx, cs:WPP_GLOBAL_Control
0x18000504d  cmp     rcx, r14
0x180005050  jz      short loc_180004FD8
0x180005052  test    byte ptr [rcx+1Ch], 1
0x180005056  jz      short loc_180004FD8
0x180005058  mov     rcx, [rcx+10h]
0x18000505c  lea     r9, aHrdeserializes_0; "HrDeserializeSOAPRequest(): Failed to g"...
0x180005063  mov     edx, 42h ; 'B'
0x180005068  mov     dword ptr [rsp+70h+var_50], eax
0x18000506c  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005073  call    WPP_SF_sd
0x180005078  jmp     loc_180004FD8
0x18000507d  xor     edi, edi
0x18000507f  mov     dword ptr [rbp+var_20+8], esi
0x180005082  mov     [rbp+var_10], rsi
0x180005086  jmp     loc_180004FD8
0x18000508b  mov     eax, 8007000Eh
0x180005090  mov     edi, eax
0x180005092  mov     rcx, cs:WPP_GLOBAL_Control
0x180005099  cmp     rcx, r14
0x18000509c  jz      short loc_1800050C4
0x18000509e  test    byte ptr [rcx+1Ch], 1
0x1800050a2  jz      short loc_1800050C4
0x1800050a4  mov     rcx, [rcx+10h]
0x1800050a8  lea     r9, aHrdeserializes_4; "HrDeserializeSOAPRequest(): Failed to a"...
0x1800050af  mov     edx, 43h ; 'C'
0x1800050b4  mov     dword ptr [rsp+70h+var_50], eax
0x1800050b8  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x1800050bf  call    WPP_SF_sd
0x1800050c4  lea     rcx, [rbp+var_20]; struct tagUPNP_CONTROL_REQUEST *
0x1800050c8  call    ?CleanupDeserializedRequest@@YAXPEAUtagUPNP_CONTROL_REQUEST@@@Z; CleanupDeserializedRequest(tagUPNP_CONTROL_REQUEST *)
0x1800050cd  test    edi, edi
0x1800050cf  jz      short loc_18000510A
0x1800050d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800050d8  lea     rax, WPP_GLOBAL_Control
0x1800050df  cmp     rcx, rax
0x1800050e2  jz      short loc_18000510A
0x1800050e4  test    byte ptr [rcx+1Ch], 1
0x1800050e8  jz      short loc_18000510A
0x1800050ea  mov     rcx, [rcx+10h]
0x1800050ee  lea     r9, aHrdeserializes; "HrDeserializeSOAPRequest(): Exiting"
0x1800050f5  mov     edx, 44h ; 'D'
0x1800050fa  mov     dword ptr [rsp+70h+var_50], edi
0x1800050fe  lea     r8, WPP_c31745aca67c3ec3b1ba12b46a9045bb_Traceguids
0x180005105  call    WPP_SF_sd
0x18000510a  mov     rbx, [rsp+70h+arg_8]
0x180005112  mov     eax, edi
0x180005114  add     rsp, 70h
0x180005118  pop     r15
0x18000511a  pop     r14
0x18000511c  pop     r13
0x18000511e  pop     r12
0x180005120  pop     rdi
0x180005121  pop     rsi
0x180005122  pop     rbp
0x180005123  retn
```
