# HrValidateArguments(IXMLDOMNode *,IXMLDOMNodeList *,IUPnPServiceDescriptionInfo *)

- ea: `0x180008a4c`
- end: `0x180008e31`
- name: `?HrValidateArguments@@YAJPEAUIXMLDOMNode@@PEAUIXMLDOMNodeList@@PEAUIUPnPServiceDescriptionInfo@@@Z`
- size: `997`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, struct IXMLDOMNodeList *, struct IUPnPServiceDescriptionInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180008e38`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180008a4c`
- `0x1800096b0`
- `0x18000bab5`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008bb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008c00`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008bb0`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180008c00`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d78`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180008d86`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c74`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d47`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d94`
- `OLEAUT32!__imp_SysFreeString` at `0x180008c74`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d47`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d5d`
- `OLEAUT32!__imp_SysFreeString` at `0x180008d94`

## pseudocode

```c
__int64 __fastcall HrValidateArguments(
        struct IXMLDOMNode *a1,
        struct IXMLDOMNodeList *a2,
        struct IUPnPServiceDescriptionInfo *a3)
{
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  int v6; // eax
  int v7; // edi
  int v8; // r15d
  struct IXMLDOMNodeListVtbl *v9; // rax
  int v10; // eax
  unsigned int v11; // eax
  int v12; // r13d
  __int64 i; // r14
  struct IXMLDOMNodeListVtbl *v14; // rax
  int v15; // eax
  unsigned int v16; // r14d
  __int64 v17; // rbx
  _QWORD *v18; // rcx
  LPVOID pv; // [rsp+30h] [rbp-30h] BYREF
  LPVOID v21; // [rsp+38h] [rbp-28h] BYREF
  BSTR bstrString; // [rsp+40h] [rbp-20h] BYREF
  wchar_t *String1; // [rsp+48h] [rbp-18h] BYREF
  __int64 v24; // [rsp+50h] [rbp-10h] BYREF
  unsigned int v25; // [rsp+A0h] [rbp+40h] BYREF
  int v26; // [rsp+B8h] [rbp+58h] BYREF

  lpVtbl = a1->lpVtbl;
  String1 = 0;
  v6 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, wchar_t **))lpVtbl->get_baseName)(a1, &String1);
  v7 = v6;
  if ( !v6 )
  {
    v25 = 0;
    pv = 0;
    v21 = 0;
    if ( !wcscmp_0(String1, L"QueryStateVariable") )
    {
      v8 = 1;
      v25 = 1;
    }
    else
    {
      v8 = 0;
      v7 = (*(__int64 (__fastcall **)(struct IUPnPServiceDescriptionInfo *, wchar_t *, unsigned int *, LPVOID *, LPVOID *))(*(_QWORD *)a3 + 32LL))(
             a3,
             String1,
             &v25,
             &pv,
             &v21);
      if ( v7 < 0 )
      {
LABEL_48:
        SysFreeString(String1);
LABEL_52:
        v18 = WPP_GLOBAL_Control;
        goto LABEL_53;
      }
    }
    v9 = a2->lpVtbl;
    v26 = 0;
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, int *))v9->get_length)(a2, &v26);
    v7 = v10;
    if ( v10 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          17,
          (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
          (unsigned int)"HrValidateArguments(): Failed to get list length",
          v10);
    }
    else
    {
      v11 = v25;
      if ( v26 == v25 )
      {
        if ( v25 )
        {
          v12 = IsActionArgCheckingDisabled();
          for ( i = 0; ; i = (unsigned int)(i + 1) )
          {
            if ( !v12 && v7 < 0 )
              goto LABEL_38;
            v11 = v25;
            if ( (unsigned int)i >= v25 )
              goto LABEL_43;
            v14 = a2->lpVtbl;
            v24 = 0;
            v15 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, __int64 *))v14->get_item)(
                    a2,
                    (unsigned int)i,
                    &v24);
            v7 = v15;
            if ( !v15 )
              break;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              WPP_SF_sd(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                15,
                (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
                (unsigned int)"HrValidateArguments(): Failed to get item",
                v15);
LABEL_34:
            ;
          }
          bstrString = 0;
          v7 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v24 + 328LL))(v24, &bstrString);
          if ( v7 )
          {
LABEL_30:
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
            goto LABEL_34;
          }
          if ( v8 )
          {
            if ( (unsigned int)_o__wcsicmp(bstrString, L"varName") )
            {
              v7 = -2147220984;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  12,
                  (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
                  (unsigned int)"HrValidateArguments(): Invalid argument name",
                  8);
              }
              goto LABEL_29;
            }
          }
          else if ( (unsigned int)_o__wcsicmp(bstrString, *((_QWORD *)pv + i)) )
          {
            if ( (_DWORD)i )
            {
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
              {
                WPP_SF_sd(
                  *((_QWORD *)WPP_GLOBAL_Control + 2),
                  14,
                  (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
                  (unsigned int)"HrValidateArguments(): Invalid argument name",
                  8);
              }
              v7 = -2147220984;
              goto LABEL_29;
            }
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
              && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
            }
          }
          v7 = 0;
LABEL_29:
          SysFreeString(bstrString);
          goto LABEL_30;
        }
        goto LABEL_43;
      }
      v7 = -2147220984;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_43:
        if ( !v8 && v11 )
        {
          v16 = 0;
          do
          {
            v17 = v16;
            SysFreeString(*((BSTR *)pv + v16));
            *((_QWORD *)pv + v16) = 0;
            SysFreeString(*((BSTR *)v21 + v16++));
            *((_QWORD *)v21 + v17) = 0;
          }
          while ( v16 < v25 );
          CoTaskMemFree(pv);
          pv = 0;
          CoTaskMemFree(v21);
          v21 = 0;
        }
        goto LABEL_48;
      }
      WPP_SF_sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        16,
        (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
        (unsigned int)"HrValidateArguments(): Wrong number of input arguments in request",
        8);
    }
LABEL_38:
    v11 = v25;
    goto LABEL_43;
  }
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      18,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateArguments(): Failed to get action name",
      v6);
    goto LABEL_52;
  }
LABEL_53:
  if ( v7 == 1 )
  {
    v7 = -2147467259;
  }
  else if ( !v7 )
  {
    return (unsigned int)v7;
  }
  if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
    WPP_SF_sd(
      v18[2],
      19,
      (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
      (unsigned int)"HrValidateArguments(): Exiting",
      v7);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180008a4c  mov     [rsp-38h+arg_8], rbx
0x180008a51  push    rbp
0x180008a52  push    rsi
0x180008a53  push    rdi
0x180008a54  push    r12
0x180008a56  push    r13
0x180008a58  push    r14
0x180008a5a  push    r15
0x180008a5c  mov     rbp, rsp
0x180008a5f  sub     rsp, 60h
0x180008a63  mov     rax, [rcx]
0x180008a66  mov     r12, rdx
0x180008a69  xor     r13d, r13d
0x180008a6c  lea     rdx, [rbp+String1]
0x180008a70  mov     rbx, r8
0x180008a73  mov     [rbp+String1], r13
0x180008a77  mov     rax, [rax+148h]
0x180008a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a83  mov     edi, eax
0x180008a85  test    eax, eax
0x180008a87  jnz     loc_180008D9C
0x180008a8d  mov     rcx, [rbp+String1]; String1
0x180008a91  lea     rdx, aQuerystatevari; "QueryStateVariable"
0x180008a98  mov     [rbp+arg_0], r13d
0x180008a9c  mov     [rbp+pv], r13
0x180008aa0  mov     [rbp+var_28], r13
0x180008aa4  call    wcscmp_0
0x180008aa9  lea     rsi, WPP_GLOBAL_Control
0x180008ab0  test    eax, eax
0x180008ab2  jnz     short loc_180008ABE
0x180008ab4  lea     r15d, [r13+1]
0x180008ab8  mov     [rbp+arg_0], r15d
0x180008abc  jmp     short loc_180008AEF
0x180008abe  mov     rax, [rbx]
0x180008ac1  lea     rcx, [rbp+var_28]
0x180008ac5  mov     rdx, [rbp+String1]
0x180008ac9  lea     r9, [rbp+pv]
0x180008acd  mov     [rsp+60h+var_40], rcx
0x180008ad2  lea     r8, [rbp+arg_0]
0x180008ad6  mov     rcx, rbx
0x180008ad9  mov     r15d, r13d
0x180008adc  mov     rax, [rax+20h]
0x180008ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ae5  mov     edi, eax
0x180008ae7  test    eax, eax
0x180008ae9  js      loc_180008D90
0x180008aef  mov     rax, [r12]
0x180008af3  lea     rdx, [rbp+arg_18]
0x180008af7  mov     rcx, r12
0x180008afa  mov     [rbp+arg_18], r13d
0x180008afe  mov     rax, [rax+40h]
0x180008b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b07  mov     edi, eax
0x180008b09  test    eax, eax
0x180008b0b  jnz     loc_180008D04
0x180008b11  mov     eax, [rbp+arg_0]
0x180008b14  cmp     [rbp+arg_18], eax
0x180008b17  jnz     loc_180008CC6
0x180008b1d  test    eax, eax
0x180008b1f  jz      loc_180008D30
0x180008b25  call    ?IsActionArgCheckingDisabled@@YAHXZ; IsActionArgCheckingDisabled(void)
0x180008b2a  mov     r13d, eax
0x180008b2d  xor     r14d, r14d
0x180008b30  mov     ebx, 80040208h
0x180008b35  test    r13d, r13d
0x180008b38  jnz     short loc_180008B42
0x180008b3a  test    edi, edi
0x180008b3c  js      loc_180008D28
0x180008b42  mov     eax, [rbp+arg_0]
0x180008b45  cmp     r14d, eax
0x180008b48  jnb     loc_180008D2D
0x180008b4e  mov     rax, [r12]
0x180008b52  lea     r8, [rbp+var_10]
0x180008b56  mov     edx, r14d
0x180008b59  mov     [rbp+var_10], 0
0x180008b61  mov     rcx, r12
0x180008b64  mov     rax, [rax+38h]
0x180008b68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b6d  mov     edi, eax
0x180008b6f  test    eax, eax
0x180008b71  jnz     loc_180008C8C
0x180008b77  mov     rcx, [rbp+var_10]
0x180008b7b  lea     rdx, [rbp+bstrString]
0x180008b7f  mov     [rbp+bstrString], 0
0x180008b87  mov     rax, [rcx]
0x180008b8a  mov     rax, [rax+148h]
0x180008b91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b96  mov     edi, eax
0x180008b98  test    eax, eax
0x180008b9a  jnz     loc_180008C7A
0x180008ba0  mov     rcx, [rbp+bstrString]
0x180008ba4  test    r15d, r15d
0x180008ba7  jz      short loc_180008BF8
0x180008ba9  lea     rdx, aVarname; "varName"
0x180008bb0  call    cs:__imp__o__wcsicmp
0x180008bb6  test    eax, eax
0x180008bb8  jz      short loc_180008C38
0x180008bba  mov     edi, ebx
0x180008bbc  mov     rcx, cs:WPP_GLOBAL_Control
0x180008bc3  cmp     rcx, rsi
0x180008bc6  jz      loc_180008C70
0x180008bcc  test    byte ptr [rcx+1Ch], 1
0x180008bd0  jz      loc_180008C70
0x180008bd6  mov     rcx, [rcx+10h]
0x180008bda  lea     r9, aHrvalidateargu_4; "HrValidateArguments(): Invalid argument"...
0x180008be1  mov     edx, 0Ch
0x180008be6  mov     dword ptr [rsp+60h+var_40], ebx
0x180008bea  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008bf1  call    WPP_SF_sd
0x180008bf6  jmp     short loc_180008C70
0x180008bf8  mov     rdx, [rbp+pv]
0x180008bfc  mov     rdx, [rdx+r14*8]
0x180008c00  call    cs:__imp__o__wcsicmp
0x180008c06  test    eax, eax
0x180008c08  jz      short loc_180008C38
0x180008c0a  test    r14d, r14d
0x180008c0d  jnz     short loc_180008C3C
0x180008c0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c16  cmp     rcx, rsi
0x180008c19  jz      short loc_180008C38
0x180008c1b  test    dword ptr [rcx+1Ch], 400h
0x180008c22  jz      short loc_180008C38
0x180008c24  mov     rcx, [rcx+10h]
0x180008c28  lea     edx, [r14+0Dh]
0x180008c2c  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008c33  call    WPP_SF_
0x180008c38  xor     edi, edi
0x180008c3a  jmp     short loc_180008C70
0x180008c3c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c43  cmp     rcx, rsi
0x180008c46  jz      short loc_180008C6E
0x180008c48  test    byte ptr [rcx+1Ch], 1
0x180008c4c  jz      short loc_180008C6E
0x180008c4e  mov     rcx, [rcx+10h]
0x180008c52  lea     r9, aHrvalidateargu_4; "HrValidateArguments(): Invalid argument"...
0x180008c59  mov     edx, 0Eh
0x180008c5e  mov     dword ptr [rsp+60h+var_40], ebx
0x180008c62  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008c69  call    WPP_SF_sd
0x180008c6e  mov     edi, ebx
0x180008c70  mov     rcx, [rbp+bstrString]; bstrString
0x180008c74  call    cs:__imp_SysFreeString
0x180008c7a  mov     rcx, [rbp+var_10]
0x180008c7e  mov     rax, [rcx]
0x180008c81  mov     rax, [rax+10h]
0x180008c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c8a  jmp     short loc_180008CBE
0x180008c8c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008c93  cmp     rcx, rsi
0x180008c96  jz      short loc_180008CBE
0x180008c98  test    byte ptr [rcx+1Ch], 1
0x180008c9c  jz      short loc_180008CBE
0x180008c9e  mov     rcx, [rcx+10h]
0x180008ca2  lea     r9, aHrvalidateargu_1; "HrValidateArguments(): Failed to get it"...
0x180008ca9  mov     edx, 0Fh
0x180008cae  mov     dword ptr [rsp+60h+var_40], eax
0x180008cb2  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008cb9  call    WPP_SF_sd
0x180008cbe  inc     r14d
0x180008cc1  jmp     loc_180008B35
0x180008cc6  mov     ebx, 80040208h
0x180008ccb  mov     edi, ebx
0x180008ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x180008cd4  cmp     rcx, rsi
0x180008cd7  jz      short loc_180008D30
0x180008cd9  test    byte ptr [rcx+1Ch], 1
0x180008cdd  jz      short loc_180008D30
0x180008cdf  mov     edx, 10h
0x180008ce4  mov     dword ptr [rsp+60h+var_40], ebx
0x180008ce8  lea     r9, aHrvalidateargu_0; "HrValidateArguments(): Wrong number of "...
0x180008cef  mov     rcx, [rcx+10h]
0x180008cf3  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008cfa  call    WPP_SF_sd
0x180008cff  mov     eax, [rbp+arg_0]
0x180008d02  jmp     short loc_180008D30
0x180008d04  mov     rcx, cs:WPP_GLOBAL_Control
0x180008d0b  cmp     rcx, rsi
0x180008d0e  jz      short loc_180008CFF
0x180008d10  test    byte ptr [rcx+1Ch], 1
0x180008d14  jz      short loc_180008CFF
0x180008d16  mov     edx, 11h
0x180008d1b  mov     dword ptr [rsp+60h+var_40], eax
0x180008d1f  lea     r9, aHrvalidateargu_2; "HrValidateArguments(): Failed to get li"...
0x180008d26  jmp     short loc_180008CEF
0x180008d28  xor     r13d, r13d
0x180008d2b  jmp     short loc_180008CFF
0x180008d2d  xor     r13d, r13d
0x180008d30  test    r15d, r15d
0x180008d33  jnz     short loc_180008D90
0x180008d35  test    eax, eax
0x180008d37  jz      short loc_180008D90
0x180008d39  mov     r14d, r13d
0x180008d3c  mov     rcx, [rbp+pv]
0x180008d40  mov     ebx, r14d
0x180008d43  mov     rcx, [rcx+rbx*8]; bstrString
0x180008d47  call    cs:__imp_SysFreeString
0x180008d4d  mov     rax, [rbp+pv]
0x180008d51  mov     [rax+rbx*8], r13
0x180008d55  mov     rcx, [rbp+var_28]
0x180008d59  mov     rcx, [rcx+rbx*8]; bstrString
0x180008d5d  call    cs:__imp_SysFreeString
0x180008d63  mov     rax, [rbp+var_28]
0x180008d67  inc     r14d
0x180008d6a  mov     [rax+rbx*8], r13
0x180008d6e  cmp     r14d, [rbp+arg_0]
0x180008d72  jb      short loc_180008D3C
0x180008d74  mov     rcx, [rbp+pv]; pv
0x180008d78  call    cs:__imp_CoTaskMemFree
0x180008d7e  mov     rcx, [rbp+var_28]; pv
0x180008d82  mov     [rbp+pv], r13
0x180008d86  call    cs:__imp_CoTaskMemFree
0x180008d8c  mov     [rbp+var_28], r13
0x180008d90  mov     rcx, [rbp+String1]; bstrString
0x180008d94  call    cs:__imp_SysFreeString
0x180008d9a  jmp     short loc_180008DD5
0x180008d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x180008da3  lea     rsi, WPP_GLOBAL_Control
0x180008daa  cmp     rcx, rsi
0x180008dad  jz      short loc_180008DDC
0x180008daf  test    byte ptr [rcx+1Ch], 1
0x180008db3  jz      short loc_180008DDC
0x180008db5  mov     rcx, [rcx+10h]
0x180008db9  lea     r9, aHrvalidateargu_3; "HrValidateArguments(): Failed to get ac"...
0x180008dc0  mov     edx, 12h
0x180008dc5  mov     dword ptr [rsp+60h+var_40], eax
0x180008dc9  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008dd0  call    WPP_SF_sd
0x180008dd5  mov     rcx, cs:WPP_GLOBAL_Control
0x180008ddc  cmp     edi, 1
0x180008ddf  jnz     short loc_180008DE8
0x180008de1  mov     edi, 80004005h
0x180008de6  jmp     short loc_180008DEC
0x180008de8  test    edi, edi
0x180008dea  jz      short loc_180008E17
0x180008dec  cmp     rcx, rsi
0x180008def  jz      short loc_180008E17
0x180008df1  test    byte ptr [rcx+1Ch], 1
0x180008df5  jz      short loc_180008E17
0x180008df7  mov     rcx, [rcx+10h]
0x180008dfb  lea     r9, aHrvalidateargu; "HrValidateArguments(): Exiting"
0x180008e02  mov     edx, 13h
0x180008e07  mov     dword ptr [rsp+60h+var_40], edi
0x180008e0b  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008e12  call    WPP_SF_sd
0x180008e17  mov     rbx, [rsp+60h+arg_8]
0x180008e1f  mov     eax, edi
0x180008e21  add     rsp, 60h
0x180008e25  pop     r15
0x180008e27  pop     r14
0x180008e29  pop     r13
0x180008e2b  pop     r12
0x180008e2d  pop     rdi
0x180008e2e  pop     rsi
0x180008e2f  pop     rbp
0x180008e30  retn
```
