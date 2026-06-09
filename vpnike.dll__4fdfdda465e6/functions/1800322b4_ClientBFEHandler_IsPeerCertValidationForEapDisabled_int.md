# ClientBFEHandler::IsPeerCertValidationForEapDisabled(int *)

- ea: `0x1800322b4`
- end: `0x180032688`
- name: `?IsPeerCertValidationForEapDisabled@ClientBFEHandler@@IEAAKPEAH@Z`
- size: `980`
- prototype: `__int64 __fastcall(ClientBFEHandler *this, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180032690`

## callees

- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x180007894`
- `0x1800322b4`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800323c6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x1800323c6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800325bf`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800325bf`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003237a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x18003237a`

## string_xrefs

- `0x18003233d`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x180032426`: `IsPeerCertValidationForEapDiasabled: IkeAuthTypeNoServerCert value as read from the registry is: %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::IsPeerCertValidationForEapDisabled(ClientBFEHandler *this, int *a2)
{
  unsigned int v4; // eax
  __int64 v5; // r9
  unsigned int v6; // ebx
  __int64 v7; // rax
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  _QWORD *v12; // rax
  __int64 v13; // rcx
  __int128 *v14; // r9
  PVOID *v15; // rcx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rdx
  __int64 v19; // rcx
  _QWORD *v20; // rax
  __int64 v21; // rcx
  __int128 *v22; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v28; // [rsp+48h] [rbp-B8h] BYREF
  int v29; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v30; // [rsp+5Ch] [rbp-A4h]
  __int128 v31; // [rsp+6Ch] [rbp-94h]
  int v32; // [rsp+7Ch] [rbp-84h]
  int v33; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v34[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 176, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
  }
  hKey = 0;
  v33 = 0;
  memset_0(v34, 0, sizeof(v34));
  v29 = 0;
  v32 = 0;
  *a2 = 0;
  v30 = 0;
  v31 = 0;
  v28 = 0;
  v4 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 0x20019u, &hKey);
  v6 = v4;
  if ( !v4 )
  {
    Type = 0;
    *(_DWORD *)Data = 1;
    cbData = 4;
    LODWORD(v7) = RegQueryValueExA(hKey, "IkeAuthTypeNoServerCert", 0, &Type, Data, &cbData);
    v6 = v7;
    if ( (_DWORD)v7 )
    {
      v15 = (PVOID *)WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_30:
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_47:
          if ( !hKey )
            goto LABEL_54;
          RegCloseKey(hKey);
          goto LABEL_53;
        }
        v16 = *((_QWORD *)this + 6);
        LOWORD(v33) = 0;
        LOWORD(v29) = 0;
        if ( v16 && (v17 = *(_QWORD *)(v16 + 112)) != 0 && *(_QWORD *)(v17 + 16) )
          v18 = *(unsigned int *)(v17 + 16);
        else
          v18 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v29, v18);
        FormatRRASErrorString(
          &v33,
          L"IsPeerCertValidationForEapDiasabled: RegQueryValueEx for IkeAuthTypeNoServerCert failed with %d",
          v6);
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_46:
          v15 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_47;
        }
        v19 = *((_QWORD *)this + 6);
        v20 = (_QWORD *)(v19 + 112);
        if ( v19 )
        {
          if ( *v20 )
            v21 = *v20 + 2686LL;
          else
            v21 = 0;
          if ( *v20 )
          {
            v22 = (__int128 *)(*v20 + 2120LL);
LABEL_45:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v33,
              (_DWORD)v22,
              v21,
              (__int64)&v29);
            goto LABEL_46;
          }
        }
        else
        {
          v21 = 0;
        }
        v22 = &v28;
        goto LABEL_45;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        177,
        &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
        (unsigned int)v7);
    }
    else if ( Type == 4 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v8 = *((_QWORD *)this + 6);
      LOWORD(v33) = 0;
      LOWORD(v29) = 0;
      if ( v8 && (v9 = *(_QWORD *)(v8 + 112)) != 0 && *(_QWORD *)(v9 + 16) != v7 )
        v10 = *(unsigned int *)(v9 + 16);
      else
        v10 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v29, v10);
      FormatRRASErrorString(
        &v33,
        L"IsPeerCertValidationForEapDiasabled: IkeAuthTypeNoServerCert value as read from the registry is: %d",
        *(unsigned int *)Data);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v11 = *((_QWORD *)this + 6);
      v12 = (_QWORD *)(v11 + 112);
      if ( v11 )
      {
        if ( *v12 )
          v13 = *v12 + 2686LL;
        else
          v13 = 0;
        if ( *v12 )
        {
          v14 = (__int128 *)(*v12 + 2120LL);
LABEL_23:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v33,
            (_DWORD)v14,
            v13,
            (__int64)&v29);
LABEL_24:
          *a2 = *(_DWORD *)Data == 1;
          goto LABEL_46;
        }
      }
      else
      {
        v13 = 0;
      }
      v14 = &v28;
      goto LABEL_23;
    }
    v15 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  v15 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v6;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 178, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v4);
LABEL_53:
    v15 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_54:
  if ( v15 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 5u )
    {
      LOBYTE(v5) = *a2 != 0;
      WPP_SF_c(v15[2], 179, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v5);
      v15 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v15 != &WPP_GLOBAL_Control && (*((_BYTE *)v15 + 28) & 1) != 0 && *((_BYTE *)v15 + 25) >= 6u )
      WPP_SF_d(v15[2], 180, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v6);
  }
  return v6;
}

```

## disassembly

```asm
0x1800322b4  mov     [rsp-8+arg_10], rbx
0x1800322b9  mov     [rsp-8+arg_18], rsi
0x1800322be  push    rbp
0x1800322bf  push    rdi
0x1800322c0  push    r13
0x1800322c2  lea     rbp, [rsp-790h]
0x1800322ca  sub     rsp, 890h
0x1800322d1  mov     rax, cs:__security_cookie
0x1800322d8  xor     rax, rsp
0x1800322db  mov     [rbp+7A0h+var_20], rax
0x1800322e2  mov     rsi, rdx
0x1800322e5  mov     rdi, rcx
0x1800322e8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800322ef  lea     r13, WPP_GLOBAL_Control
0x1800322f6  cmp     rcx, r13
0x1800322f9  jz      short loc_18003231C
0x1800322fb  test    byte ptr [rcx+1Ch], 1
0x1800322ff  jz      short loc_18003231C
0x180032301  cmp     byte ptr [rcx+19h], 6
0x180032305  jb      short loc_18003231C
0x180032307  mov     rcx, [rcx+10h]
0x18003230b  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032312  mov     edx, 0B0h
0x180032317  call    WPP_SF_
0x18003231c  xor     eax, eax
0x18003231e  mov     [rsp+8A0h+hKey], 0
0x180032327  xor     edx, edx; Val
0x180032329  mov     [rbp+7A0h+var_820], eax
0x18003232c  mov     r8d, 7FCh; Size
0x180032332  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180032336  call    memset_0
0x18003233b  xor     eax, eax
0x18003233d  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180032344  xorps   xmm0, xmm0
0x180032347  mov     [rsp+8A0h+var_848], eax
0x18003234b  mov     [rsp+8A0h+var_824], eax
0x18003234f  mov     r9d, 20019h; samDesired
0x180032355  mov     [rsi], eax
0x180032357  xor     r8d, r8d; ulOptions
0x18003235a  lea     rax, [rsp+8A0h+hKey]
0x18003235f  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180032366  mov     [rsp+8A0h+phkResult], rax; phkResult
0x18003236b  movups  [rsp+8A0h+var_844], xmm0
0x180032370  movups  [rsp+8A0h+var_834], xmm0
0x180032375  movups  [rsp+8A0h+var_858], xmm0
0x18003237a  call    cs:__imp_RegOpenKeyExA
0x180032380  mov     ebx, eax
0x180032382  test    eax, eax
0x180032384  jnz     loc_1800325C7
0x18003238a  mov     rcx, [rsp+8A0h+hKey]; hKey
0x18003238f  lea     r9, [rsp+8A0h+Type]; lpType
0x180032394  mov     [rsp+8A0h+Type], eax
0x180032398  lea     rdx, aIkeauthtypenos; "IkeAuthTypeNoServerCert"
0x18003239f  lea     rax, [rsp+8A0h+cbData]
0x1800323a4  mov     dword ptr [rsp+8A0h+Data], 1
0x1800323ac  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x1800323b1  xor     r8d, r8d; lpReserved
0x1800323b4  lea     rax, [rsp+8A0h+Data]
0x1800323b9  mov     [rsp+8A0h+cbData], 4
0x1800323c1  mov     [rsp+8A0h+phkResult], rax; lpData
0x1800323c6  call    cs:__imp_RegQueryValueExA
0x1800323cc  mov     ebx, eax
0x1800323ce  test    eax, eax
0x1800323d0  jnz     loc_1800324B3
0x1800323d6  cmp     [rsp+8A0h+Type], 4
0x1800323db  jnz     loc_1800324E3
0x1800323e1  test    cs:byte_1800AA941, 4
0x1800323e8  jz      loc_1800324A2
0x1800323ee  mov     rdx, [rdi+30h]
0x1800323f2  mov     word ptr [rbp+7A0h+var_820], ax
0x1800323f6  mov     word ptr [rsp+8A0h+var_848], ax
0x1800323fb  test    rdx, rdx
0x1800323fe  jz      short loc_180032414
0x180032400  mov     rdx, [rdx+70h]
0x180032404  test    rdx, rdx
0x180032407  jz      short loc_180032414
0x180032409  cmp     [rdx+10h], rax
0x18003240d  jz      short loc_180032414
0x18003240f  mov     edx, [rdx+10h]
0x180032412  jmp     short loc_180032417
0x180032414  or      edx, 0FFFFFFFFh
0x180032417  lea     rcx, [rsp+8A0h+var_848]
0x18003241c  call    ConvertPortNoToString
0x180032421  mov     r8d, dword ptr [rsp+8A0h+Data]
0x180032426  lea     rdx, aIspeercertvali_0; "IsPeerCertValidationForEapDiasabled: Ik"...
0x18003242d  lea     rcx, [rbp+7A0h+var_820]
0x180032431  call    FormatRRASErrorString
0x180032436  test    cs:byte_1800AA941, 4
0x18003243d  jz      short loc_1800324A2
0x18003243f  mov     rcx, [rdi+30h]
0x180032443  lea     rax, [rcx+70h]
0x180032447  test    rcx, rcx
0x18003244a  jz      short loc_180032475
0x18003244c  mov     rdx, [rax]
0x18003244f  test    rdx, rdx
0x180032452  jz      short loc_18003245D
0x180032454  lea     rcx, [rdx+0A7Eh]
0x18003245b  jmp     short loc_180032464
0x18003245d  test    rcx, rcx
0x180032460  jz      short loc_180032475
0x180032462  xor     ecx, ecx
0x180032464  mov     rdx, [rax]
0x180032467  test    rdx, rdx
0x18003246a  jz      short loc_180032477
0x18003246c  lea     r9, [rdx+848h]
0x180032473  jmp     short loc_18003247C
0x180032475  xor     ecx, ecx
0x180032477  lea     r9, [rsp+8A0h+var_858]
0x18003247c  lea     rax, [rsp+8A0h+var_848]
0x180032481  mov     [rsp+8A0h+lpcbData], rax
0x180032486  lea     r8, [rbp+7A0h+var_820]
0x18003248a  mov     [rsp+8A0h+phkResult], rcx
0x18003248f  lea     rdx, RasVpnIkeParamTraceError
0x180032496  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003249d  call    McTemplateU0zjzz_EventWriteTransfer
0x1800324a2  xor     eax, eax
0x1800324a4  cmp     dword ptr [rsp+8A0h+Data], 1
0x1800324a9  setz    al
0x1800324ac  mov     [rsi], eax
0x1800324ae  jmp     loc_1800325AB
0x1800324b3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324ba  cmp     rcx, r13
0x1800324bd  jz      short loc_1800324EA
0x1800324bf  test    byte ptr [rcx+1Ch], 1
0x1800324c3  jz      short loc_1800324EA
0x1800324c5  cmp     byte ptr [rcx+19h], 2
0x1800324c9  jb      short loc_1800324EA
0x1800324cb  mov     rcx, [rcx+10h]
0x1800324cf  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800324d6  mov     edx, 0B1h
0x1800324db  mov     r9d, ebx
0x1800324de  call    WPP_SF_d
0x1800324e3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800324ea  test    cs:byte_1800AA941, 4
0x1800324f1  jz      loc_1800325B2
0x1800324f7  mov     rdx, [rdi+30h]
0x1800324fb  xor     eax, eax
0x1800324fd  mov     word ptr [rbp+7A0h+var_820], ax
0x180032501  mov     word ptr [rsp+8A0h+var_848], ax
0x180032506  test    rdx, rdx
0x180032509  jz      short loc_18003251F
0x18003250b  mov     rdx, [rdx+70h]
0x18003250f  test    rdx, rdx
0x180032512  jz      short loc_18003251F
0x180032514  cmp     [rdx+10h], rax
0x180032518  jz      short loc_18003251F
0x18003251a  mov     edx, [rdx+10h]
0x18003251d  jmp     short loc_180032522
0x18003251f  or      edx, 0FFFFFFFFh
0x180032522  lea     rcx, [rsp+8A0h+var_848]
0x180032527  call    ConvertPortNoToString
0x18003252c  mov     r8d, ebx
0x18003252f  lea     rdx, aIspeercertvali; "IsPeerCertValidationForEapDiasabled: Re"...
0x180032536  lea     rcx, [rbp+7A0h+var_820]
0x18003253a  call    FormatRRASErrorString
0x18003253f  test    cs:byte_1800AA941, 4
0x180032546  jz      short loc_1800325AB
0x180032548  mov     rcx, [rdi+30h]
0x18003254c  lea     rax, [rcx+70h]
0x180032550  test    rcx, rcx
0x180032553  jz      short loc_18003257E
0x180032555  mov     rdx, [rax]
0x180032558  test    rdx, rdx
0x18003255b  jz      short loc_180032566
0x18003255d  lea     rcx, [rdx+0A7Eh]
0x180032564  jmp     short loc_18003256D
0x180032566  test    rcx, rcx
0x180032569  jz      short loc_18003257E
0x18003256b  xor     ecx, ecx
0x18003256d  mov     rdx, [rax]
0x180032570  test    rdx, rdx
0x180032573  jz      short loc_180032580
0x180032575  lea     r9, [rdx+848h]
0x18003257c  jmp     short loc_180032585
0x18003257e  xor     ecx, ecx
0x180032580  lea     r9, [rsp+8A0h+var_858]
0x180032585  lea     rax, [rsp+8A0h+var_848]
0x18003258a  mov     [rsp+8A0h+lpcbData], rax
0x18003258f  lea     r8, [rbp+7A0h+var_820]
0x180032593  mov     [rsp+8A0h+phkResult], rcx
0x180032598  lea     rdx, RasVpnIkeParamTraceError
0x18003259f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x1800325a6  call    McTemplateU0zjzz_EventWriteTransfer
0x1800325ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325b2  mov     rax, [rsp+8A0h+hKey]
0x1800325b7  test    rax, rax
0x1800325ba  jz      short loc_180032602
0x1800325bc  mov     rcx, rax; hKey
0x1800325bf  call    cs:__imp_RegCloseKey
0x1800325c5  jmp     short loc_1800325FB
0x1800325c7  mov     rcx, cs:WPP_GLOBAL_Control
0x1800325ce  cmp     rcx, r13
0x1800325d1  jz      loc_18003265F
0x1800325d7  test    byte ptr [rcx+1Ch], 1
0x1800325db  jz      short loc_180032602
0x1800325dd  cmp     byte ptr [rcx+19h], 2
0x1800325e1  jb      short loc_180032602
0x1800325e3  mov     rcx, [rcx+10h]
0x1800325e7  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x1800325ee  mov     edx, 0B2h
0x1800325f3  mov     r9d, eax
0x1800325f6  call    WPP_SF_d
0x1800325fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180032602  cmp     rcx, r13
0x180032605  jz      short loc_18003265F
0x180032607  test    byte ptr [rcx+1Ch], 1
0x18003260b  jz      short loc_180032636
0x18003260d  cmp     byte ptr [rcx+19h], 5
0x180032611  jb      short loc_180032636
0x180032613  cmp     dword ptr [rsi], 0
0x180032616  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x18003261d  mov     rcx, [rcx+10h]
0x180032621  mov     edx, 0B3h
0x180032626  setnz   r9b
0x18003262a  call    WPP_SF_c
0x18003262f  mov     rcx, cs:WPP_GLOBAL_Control
0x180032636  cmp     rcx, r13
0x180032639  jz      short loc_18003265F
0x18003263b  test    byte ptr [rcx+1Ch], 1
0x18003263f  jz      short loc_18003265F
0x180032641  cmp     byte ptr [rcx+19h], 6
0x180032645  jb      short loc_18003265F
0x180032647  mov     rcx, [rcx+10h]
0x18003264b  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180032652  mov     edx, 0B4h
0x180032657  mov     r9d, ebx
0x18003265a  call    WPP_SF_d
0x18003265f  mov     eax, ebx
0x180032661  mov     rcx, [rbp+7A0h+var_20]
0x180032668  xor     rcx, rsp; StackCookie
0x18003266b  call    __security_check_cookie
0x180032670  lea     r11, [rsp+8A0h+var_10]
0x180032678  mov     rbx, [r11+30h]
0x18003267c  mov     rsi, [r11+38h]
0x180032680  mov     rsp, r11
0x180032683  pop     r13
0x180032685  pop     rdi
0x180032686  pop     rbp
0x180032687  retn
```
