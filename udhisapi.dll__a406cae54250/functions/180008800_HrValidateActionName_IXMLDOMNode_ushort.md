# HrValidateActionName(IXMLDOMNode *,ushort *)

- ea: `0x180008800`
- end: `0x180008a44`
- name: `?HrValidateActionName@@YAJPEAUIXMLDOMNode@@PEAG@Z`
- size: `580`
- prototype: `__int64 __fastcall(struct IXMLDOMNode *, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180008e38`

## callees

- `0x18000249c`
- `0x1800038ec`
- `0x180008800`
- `0x18000c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800088c6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800088c6`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008885`
- `api-ms-win-crt-private-l1-1-0!wcsstr` at `0x180008885`
- `OLEAUT32!__imp_SysFreeString` at `0x180008946`
- `OLEAUT32!__imp_SysFreeString` at `0x180008946`

## pseudocode

```c
__int64 __fastcall HrValidateActionName(struct IXMLDOMNode *a1, unsigned __int16 *a2)
{
  unsigned __int16 *v2; // r8
  unsigned __int16 *v4; // rax
  __int64 v5; // rdx
  unsigned int v6; // edi
  __int64 v7; // rcx
  wchar_t *v8; // rbx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  unsigned int v10; // eax
  _QWORD *v11; // rcx
  int v12; // edx
  const char *v13; // r9
  BSTR bstrString; // [rsp+68h] [rbp+10h] BYREF

  v2 = a2;
  if ( a2 )
  {
    v4 = a2;
    v5 = 0x7FFFFFFF;
    do
    {
      if ( !*v4 )
        break;
      ++v4;
      --v5;
    }
    while ( v5 );
    v6 = v5 == 0 ? 0x80070057 : 0;
    v7 = (0x7FFFFFFF - v5) & -(__int64)(v5 != 0);
    if ( v5 )
    {
      if ( *v2 == 34 && v2[v7 - 1] == 34 )
      {
        v2[v7 - 1] = 0;
        ++v2;
      }
      v8 = wcsstr(v2, L"#");
      if ( !v8 )
      {
        v6 = -2147467259;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control )
          return v6;
        if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_sd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
            (unsigned int)"HrValidateActionName(): SOAPActionHeader did not contain \"#\" character",
            5);
          v11 = WPP_GLOBAL_Control;
        }
LABEL_28:
        if ( v11 != &WPP_GLOBAL_Control && (*((_BYTE *)v11 + 28) & 1) != 0 )
        {
          v12 = 25;
          v13 = "HrValidateActionName(): Exiting";
LABEL_35:
          WPP_SF_sd(v11[2], v12, (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids, (_DWORD)v13, v6);
          return v6;
        }
        return v6;
      }
      lpVtbl = a1->lpVtbl;
      bstrString = 0;
      v10 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, BSTR *))lpVtbl->get_baseName)(a1, &bstrString);
      v6 = v10;
      if ( v10 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
LABEL_23:
          if ( !v6 )
            return v6;
          goto LABEL_28;
        }
        WPP_SF_sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          23,
          (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
          (unsigned int)"HrValidateActionName(): Failed to get node name",
          v10);
      }
      else
      {
        if ( (unsigned int)_o__wcsicmp(bstrString, v8 + 1) )
        {
          v6 = -2147220985;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              22,
              (unsigned int)WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids,
              (unsigned int)"HrValidateActionName(): Action node name did not match SOAPAction header",
              7);
        }
        else
        {
          v6 = 0;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x400) != 0 )
          {
            WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids);
          }
        }
        SysFreeString(bstrString);
      }
      v11 = WPP_GLOBAL_Control;
      goto LABEL_23;
    }
  }
  else
  {
    v6 = -2147024809;
  }
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    v12 = 20;
    v13 = "HrValidateActionName(): StringCchLength failed!";
    goto LABEL_35;
  }
  return v6;
}

```

## disassembly

```asm
0x180008800  push    rbx
0x180008802  push    rbp
0x180008803  push    rdi
0x180008804  push    r14
0x180008806  sub     rsp, 38h
0x18000880a  xor     ebp, ebp
0x18000880c  mov     r8, rdx
0x18000880f  mov     r14, rcx
0x180008812  test    rdx, rdx
0x180008815  jz      loc_1800089FA
0x18000881b  mov     r9d, 7FFFFFFFh
0x180008821  mov     rax, r8
0x180008824  mov     edx, r9d
0x180008827  cmp     [rax], bp
0x18000882a  jz      short loc_180008836
0x18000882c  add     rax, 2
0x180008830  sub     rdx, 1
0x180008834  jnz     short loc_180008827
0x180008836  mov     rax, rdx
0x180008839  neg     rax
0x18000883c  mov     rax, rdx
0x18000883f  sbb     edi, edi
0x180008841  sub     r9, rdx
0x180008844  not     edi
0x180008846  and     edi, 80070057h
0x18000884c  neg     rax
0x18000884f  sbb     rcx, rcx
0x180008852  and     rcx, r9
0x180008855  test    rdx, rdx
0x180008858  jz      loc_1800089FF
0x18000885e  mov     eax, 22h ; '"'
0x180008863  cmp     ax, [r8]
0x180008867  jnz     short loc_18000887B
0x180008869  cmp     ax, [r8+rcx*2-2]
0x18000886f  jnz     short loc_18000887B
0x180008871  mov     [r8+rcx*2-2], bp
0x180008877  add     r8, 2
0x18000887b  lea     rdx, asc_18000F278; "#"
0x180008882  mov     rcx, r8; Str
0x180008885  call    cs:__imp_wcsstr
0x18000888b  mov     rbx, rax
0x18000888e  test    rax, rax
0x180008891  jz      loc_180008998
0x180008897  mov     rax, [r14]
0x18000889a  lea     rdx, [rsp+58h+bstrString]
0x18000889f  mov     rcx, r14
0x1800088a2  mov     [rsp+58h+bstrString], rbp
0x1800088a7  mov     rax, [rax+148h]
0x1800088ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b3  mov     edi, eax
0x1800088b5  test    eax, eax
0x1800088b7  jnz     loc_18000894E
0x1800088bd  mov     rcx, [rsp+58h+bstrString]
0x1800088c2  lea     rdx, [rbx+2]
0x1800088c6  call    cs:__imp__o__wcsicmp
0x1800088cc  test    eax, eax
0x1800088ce  jnz     short loc_180008903
0x1800088d0  mov     edi, ebp
0x1800088d2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800088d9  lea     rbx, WPP_GLOBAL_Control
0x1800088e0  cmp     rcx, rbx
0x1800088e3  jz      short loc_180008941
0x1800088e5  test    dword ptr [rcx+1Ch], 400h
0x1800088ec  jz      short loc_180008941
0x1800088ee  mov     rcx, [rcx+10h]
0x1800088f2  lea     edx, [rax+15h]
0x1800088f5  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800088fc  call    WPP_SF_
0x180008901  jmp     short loc_180008941
0x180008903  mov     edi, 80040207h
0x180008908  mov     rcx, cs:WPP_GLOBAL_Control
0x18000890f  lea     rbx, WPP_GLOBAL_Control
0x180008916  cmp     rcx, rbx
0x180008919  jz      short loc_180008941
0x18000891b  test    byte ptr [rcx+1Ch], 1
0x18000891f  jz      short loc_180008941
0x180008921  mov     rcx, [rcx+10h]
0x180008925  lea     r9, aHrvalidateacti; "HrValidateActionName(): Action node nam"...
0x18000892c  mov     edx, 16h
0x180008931  mov     [rsp+58h+var_38], edi
0x180008935  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x18000893c  call    WPP_SF_sd
0x180008941  mov     rcx, [rsp+58h+bstrString]; bstrString
0x180008946  call    cs:__imp_SysFreeString
0x18000894c  jmp     short loc_180008987
0x18000894e  mov     rcx, cs:WPP_GLOBAL_Control
0x180008955  lea     rbx, WPP_GLOBAL_Control
0x18000895c  cmp     rcx, rbx
0x18000895f  jz      short loc_18000898E
0x180008961  test    byte ptr [rcx+1Ch], 1
0x180008965  jz      short loc_18000898E
0x180008967  mov     rcx, [rcx+10h]
0x18000896b  lea     r9, aHrvalidateacti_0; "HrValidateActionName(): Failed to get n"...
0x180008972  mov     edx, 17h
0x180008977  mov     [rsp+58h+var_38], eax
0x18000897b  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008982  call    WPP_SF_sd
0x180008987  mov     rcx, cs:WPP_GLOBAL_Control
0x18000898e  test    edi, edi
0x180008990  jz      loc_180008A38
0x180008996  jmp     short loc_1800089E1
0x180008998  mov     edi, 80004005h
0x18000899d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089a4  lea     rbx, WPP_GLOBAL_Control
0x1800089ab  cmp     rcx, rbx
0x1800089ae  jz      loc_180008A38
0x1800089b4  test    byte ptr [rcx+1Ch], 1
0x1800089b8  jz      short loc_1800089E1
0x1800089ba  mov     rcx, [rcx+10h]
0x1800089be  lea     r9, aHrvalidateacti_3; "HrValidateActionName(): SOAPActionHeade"...
0x1800089c5  mov     edx, 18h
0x1800089ca  mov     [rsp+58h+var_38], edi
0x1800089ce  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x1800089d5  call    WPP_SF_sd
0x1800089da  mov     rcx, cs:WPP_GLOBAL_Control
0x1800089e1  cmp     rcx, rbx
0x1800089e4  jz      short loc_180008A38
0x1800089e6  test    byte ptr [rcx+1Ch], 1
0x1800089ea  jz      short loc_180008A38
0x1800089ec  mov     edx, 19h
0x1800089f1  lea     r9, aHrvalidateacti_1; "HrValidateActionName(): Exiting"
0x1800089f8  jmp     short loc_180008A24
0x1800089fa  mov     edi, 80070057h
0x1800089ff  mov     rcx, cs:WPP_GLOBAL_Control
0x180008a06  lea     rbx, WPP_GLOBAL_Control
0x180008a0d  cmp     rcx, rbx
0x180008a10  jz      short loc_180008A38
0x180008a12  test    byte ptr [rcx+1Ch], 1
0x180008a16  jz      short loc_180008A38
0x180008a18  mov     edx, 14h
0x180008a1d  lea     r9, aHrvalidateacti_2; "HrValidateActionName(): StringCchLength"...
0x180008a24  mov     rcx, [rcx+10h]
0x180008a28  lea     r8, WPP_796b6a8aa5893180319a0ef3129721cd_Traceguids
0x180008a2f  mov     [rsp+58h+var_38], edi
0x180008a33  call    WPP_SF_sd
0x180008a38  mov     eax, edi
0x180008a3a  add     rsp, 38h
0x180008a3e  pop     r14
0x180008a40  pop     rdi
0x180008a41  pop     rbp
0x180008a42  pop     rbx
0x180008a43  retn
```
