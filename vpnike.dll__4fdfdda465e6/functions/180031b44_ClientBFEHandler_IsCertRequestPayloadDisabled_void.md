# ClientBFEHandler::IsCertRequestPayloadDisabled(void)

- ea: `0x180031b44`
- end: `0x180031f0a`
- name: `?IsCertRequestPayloadDisabled@ClientBFEHandler@@IEAAHXZ`
- size: `966`
- prototype: `__int64 __fastcall(ClientBFEHandler *__hidden this)`
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
- `0x180031b44`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180031c4f`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExA` at `0x180031c4f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e45`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180031e45`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180031c07`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExA` at `0x180031c07`

## string_xrefs

- `0x180031bcc`: `System\CurrentControlSet\Services\rasman\IKEv2`
- `0x180031caf`: `IsCertRequestPayloadDisabled: DisableCertReqPayload value as read from the registry is: %d`

## pseudocode

```c
__int64 __fastcall ClientBFEHandler::IsCertRequestPayloadDisabled(ClientBFEHandler *this)
{
  unsigned int v2; // edi
  unsigned int v3; // eax
  __int64 v4; // r9
  unsigned int v5; // esi
  __int64 v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rdx
  __int64 v9; // rdx
  __int64 v10; // rcx
  _QWORD *v11; // rax
  __int64 v12; // rcx
  __int128 *v13; // r9
  PVOID *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // rdx
  __int64 v17; // rdx
  __int64 v18; // rcx
  _QWORD *v19; // rax
  __int64 v20; // rcx
  __int128 *v21; // r9
  BYTE Data[4]; // [rsp+30h] [rbp-D0h] BYREF
  DWORD Type; // [rsp+34h] [rbp-CCh] BYREF
  DWORD cbData; // [rsp+38h] [rbp-C8h] BYREF
  HKEY hKey; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v27; // [rsp+48h] [rbp-B8h] BYREF
  int v28; // [rsp+58h] [rbp-A8h] BYREF
  __int128 v29; // [rsp+5Ch] [rbp-A4h]
  __int128 v30; // [rsp+6Ch] [rbp-94h]
  int v31; // [rsp+7Ch] [rbp-84h]
  int v32; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v33[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 181, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids);
  }
  hKey = 0;
  v32 = 0;
  v2 = 0;
  memset_0(v33, 0, sizeof(v33));
  v28 = 0;
  v31 = 0;
  v29 = 0;
  v30 = 0;
  v27 = 0;
  v3 = RegOpenKeyExA(HKEY_LOCAL_MACHINE, "System\\CurrentControlSet\\Services\\rasman\\IKEv2", 0, 0x20019u, &hKey);
  v5 = v3;
  if ( !v3 )
  {
    Type = 0;
    *(_DWORD *)Data = 0;
    cbData = 4;
    LODWORD(v6) = RegQueryValueExA(hKey, "DisableCertReqPayload", 0, &Type, Data, &cbData);
    v5 = v6;
    if ( (_DWORD)v6 )
    {
      v14 = (PVOID *)WPP_GLOBAL_Control;
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
        v15 = *((_QWORD *)this + 6);
        LOWORD(v32) = 0;
        LOWORD(v28) = 0;
        if ( v15 && (v16 = *(_QWORD *)(v15 + 112)) != 0 && *(_QWORD *)(v16 + 16) )
          v17 = *(unsigned int *)(v16 + 16);
        else
          v17 = 0xFFFFFFFFLL;
        ConvertPortNoToString(&v28, v17);
        FormatRRASErrorString(
          &v32,
          L"IsCertRequestPayloadDisabled: RegQueryValueEx for DisableCertReqPayload failed with %d",
          v5);
        if ( (byte_1800AA941 & 4) == 0 )
        {
LABEL_46:
          v14 = (PVOID *)WPP_GLOBAL_Control;
          goto LABEL_47;
        }
        v18 = *((_QWORD *)this + 6);
        v19 = (_QWORD *)(v18 + 112);
        if ( v18 )
        {
          if ( *v19 )
            v20 = *v19 + 2686LL;
          else
            v20 = 0;
          if ( *v19 )
          {
            v21 = (__int128 *)(*v19 + 2120LL);
LABEL_45:
            McTemplateU0zjzz_EventWriteTransfer(
              (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
              (unsigned int)RasVpnIkeParamTraceError,
              (unsigned int)&v32,
              (_DWORD)v21,
              v20,
              (__int64)&v28);
            goto LABEL_46;
          }
        }
        else
        {
          v20 = 0;
        }
        v21 = &v27;
        goto LABEL_45;
      }
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        182,
        &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids,
        (unsigned int)v6);
    }
    else if ( Type == 4 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v7 = *((_QWORD *)this + 6);
      LOWORD(v32) = 0;
      LOWORD(v28) = 0;
      if ( v7 && (v8 = *(_QWORD *)(v7 + 112)) != 0 && *(_QWORD *)(v8 + 16) != v6 )
        v9 = *(unsigned int *)(v8 + 16);
      else
        v9 = 0xFFFFFFFFLL;
      ConvertPortNoToString(&v28, v9);
      FormatRRASErrorString(
        &v32,
        L"IsCertRequestPayloadDisabled: DisableCertReqPayload value as read from the registry is: %d",
        *(unsigned int *)Data);
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_24;
      v10 = *((_QWORD *)this + 6);
      v11 = (_QWORD *)(v10 + 112);
      if ( v10 )
      {
        if ( *v11 )
          v12 = *v11 + 2686LL;
        else
          v12 = 0;
        if ( *v11 )
        {
          v13 = (__int128 *)(*v11 + 2120LL);
LABEL_23:
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v32,
            (_DWORD)v13,
            v12,
            (__int64)&v28);
LABEL_24:
          LOBYTE(v2) = *(_DWORD *)Data == 1;
          goto LABEL_46;
        }
      }
      else
      {
        v12 = 0;
      }
      v13 = &v27;
      goto LABEL_23;
    }
    v14 = (PVOID *)WPP_GLOBAL_Control;
    goto LABEL_30;
  }
  v14 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control )
    return v2;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 183, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v3);
LABEL_53:
    v14 = (PVOID *)WPP_GLOBAL_Control;
  }
LABEL_54:
  if ( v14 != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 5u )
    {
      LOBYTE(v4) = v2;
      WPP_SF_c(v14[2], 184, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v4);
      v14 = (PVOID *)WPP_GLOBAL_Control;
    }
    if ( v14 != &WPP_GLOBAL_Control && (*((_BYTE *)v14 + 28) & 1) != 0 && *((_BYTE *)v14 + 25) >= 6u )
      WPP_SF_d(v14[2], 185, &WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids, v5);
  }
  return v2;
}

```

## disassembly

```asm
0x180031b44  mov     [rsp-8+arg_8], rbx
0x180031b49  mov     [rsp-8+arg_10], rsi
0x180031b4e  push    rbp
0x180031b4f  push    rdi
0x180031b50  push    r13
0x180031b52  lea     rbp, [rsp-790h]
0x180031b5a  sub     rsp, 890h
0x180031b61  mov     rax, cs:__security_cookie
0x180031b68  xor     rax, rsp
0x180031b6b  mov     [rbp+7A0h+var_20], rax
0x180031b72  mov     rbx, rcx
0x180031b75  mov     rcx, cs:WPP_GLOBAL_Control
0x180031b7c  lea     r13, WPP_GLOBAL_Control
0x180031b83  cmp     rcx, r13
0x180031b86  jz      short loc_180031BA9
0x180031b88  test    byte ptr [rcx+1Ch], 1
0x180031b8c  jz      short loc_180031BA9
0x180031b8e  cmp     byte ptr [rcx+19h], 6
0x180031b92  jb      short loc_180031BA9
0x180031b94  mov     rcx, [rcx+10h]
0x180031b98  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031b9f  mov     edx, 0B5h
0x180031ba4  call    WPP_SF_
0x180031ba9  xor     eax, eax
0x180031bab  mov     [rsp+8A0h+hKey], 0
0x180031bb4  xor     edx, edx; Val
0x180031bb6  mov     [rbp+7A0h+var_820], eax
0x180031bb9  mov     r8d, 7FCh; Size
0x180031bbf  lea     rcx, [rbp+7A0h+var_81C]; void *
0x180031bc3  xor     edi, edi
0x180031bc5  call    memset_0
0x180031bca  xor     eax, eax
0x180031bcc  lea     rdx, SubKey; "System\\CurrentControlSet\\Services\\ra"...
0x180031bd3  xorps   xmm0, xmm0
0x180031bd6  mov     [rsp+8A0h+var_848], eax
0x180031bda  mov     [rsp+8A0h+var_824], eax
0x180031bde  mov     r9d, 20019h; samDesired
0x180031be4  lea     rax, [rsp+8A0h+hKey]
0x180031be9  xor     r8d, r8d; ulOptions
0x180031bec  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180031bf3  mov     [rsp+8A0h+phkResult], rax; phkResult
0x180031bf8  movups  [rsp+8A0h+var_844], xmm0
0x180031bfd  movups  [rsp+8A0h+var_834], xmm0
0x180031c02  movups  [rsp+8A0h+var_858], xmm0
0x180031c07  call    cs:__imp_RegOpenKeyExA
0x180031c0d  mov     esi, eax
0x180031c0f  test    eax, eax
0x180031c11  jnz     loc_180031E4D
0x180031c17  mov     rcx, [rsp+8A0h+hKey]; hKey
0x180031c1c  lea     rax, [rsp+8A0h+cbData]
0x180031c21  mov     [rsp+8A0h+lpcbData], rax; lpcbData
0x180031c26  lea     r9, [rsp+8A0h+Type]; lpType
0x180031c2b  lea     rax, [rsp+8A0h+Data]
0x180031c30  mov     [rsp+8A0h+Type], edi
0x180031c34  xor     r8d, r8d; lpReserved
0x180031c37  mov     [rsp+8A0h+phkResult], rax; lpData
0x180031c3c  lea     rdx, aDisablecertreq; "DisableCertReqPayload"
0x180031c43  mov     dword ptr [rsp+8A0h+Data], edi
0x180031c47  mov     [rsp+8A0h+cbData], 4
0x180031c4f  call    cs:__imp_RegQueryValueExA
0x180031c55  mov     esi, eax
0x180031c57  test    eax, eax
0x180031c59  jnz     loc_180031D39
0x180031c5f  cmp     [rsp+8A0h+Type], 4
0x180031c64  jnz     loc_180031D69
0x180031c6a  test    cs:byte_1800AA941, 4
0x180031c71  jz      loc_180031D2B
0x180031c77  mov     rdx, [rbx+30h]
0x180031c7b  mov     word ptr [rbp+7A0h+var_820], ax
0x180031c7f  mov     word ptr [rsp+8A0h+var_848], ax
0x180031c84  test    rdx, rdx
0x180031c87  jz      short loc_180031C9D
0x180031c89  mov     rdx, [rdx+70h]
0x180031c8d  test    rdx, rdx
0x180031c90  jz      short loc_180031C9D
0x180031c92  cmp     [rdx+10h], rax
0x180031c96  jz      short loc_180031C9D
0x180031c98  mov     edx, [rdx+10h]
0x180031c9b  jmp     short loc_180031CA0
0x180031c9d  or      edx, 0FFFFFFFFh
0x180031ca0  lea     rcx, [rsp+8A0h+var_848]
0x180031ca5  call    ConvertPortNoToString
0x180031caa  mov     r8d, dword ptr [rsp+8A0h+Data]
0x180031caf  lea     rdx, aIscertrequestp; "IsCertRequestPayloadDisabled: DisableCe"...
0x180031cb6  lea     rcx, [rbp+7A0h+var_820]
0x180031cba  call    FormatRRASErrorString
0x180031cbf  test    cs:byte_1800AA941, 4
0x180031cc6  jz      short loc_180031D2B
0x180031cc8  mov     rcx, [rbx+30h]
0x180031ccc  lea     rax, [rcx+70h]
0x180031cd0  test    rcx, rcx
0x180031cd3  jz      short loc_180031CFE
0x180031cd5  mov     rdx, [rax]
0x180031cd8  test    rdx, rdx
0x180031cdb  jz      short loc_180031CE6
0x180031cdd  lea     rcx, [rdx+0A7Eh]
0x180031ce4  jmp     short loc_180031CED
0x180031ce6  test    rcx, rcx
0x180031ce9  jz      short loc_180031CFE
0x180031ceb  xor     ecx, ecx
0x180031ced  mov     rdx, [rax]
0x180031cf0  test    rdx, rdx
0x180031cf3  jz      short loc_180031D00
0x180031cf5  lea     r9, [rdx+848h]
0x180031cfc  jmp     short loc_180031D05
0x180031cfe  xor     ecx, ecx
0x180031d00  lea     r9, [rsp+8A0h+var_858]
0x180031d05  lea     rax, [rsp+8A0h+var_848]
0x180031d0a  mov     [rsp+8A0h+lpcbData], rax
0x180031d0f  lea     r8, [rbp+7A0h+var_820]
0x180031d13  mov     [rsp+8A0h+phkResult], rcx
0x180031d18  lea     rdx, RasVpnIkeParamTraceError
0x180031d1f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031d26  call    McTemplateU0zjzz_EventWriteTransfer
0x180031d2b  cmp     dword ptr [rsp+8A0h+Data], 1
0x180031d30  setz    dil
0x180031d34  jmp     loc_180031E31
0x180031d39  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d40  cmp     rcx, r13
0x180031d43  jz      short loc_180031D70
0x180031d45  test    byte ptr [rcx+1Ch], 1
0x180031d49  jz      short loc_180031D70
0x180031d4b  cmp     byte ptr [rcx+19h], 2
0x180031d4f  jb      short loc_180031D70
0x180031d51  mov     rcx, [rcx+10h]
0x180031d55  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031d5c  mov     edx, 0B6h
0x180031d61  mov     r9d, esi
0x180031d64  call    WPP_SF_d
0x180031d69  mov     rcx, cs:WPP_GLOBAL_Control
0x180031d70  test    cs:byte_1800AA941, 4
0x180031d77  jz      loc_180031E38
0x180031d7d  mov     rdx, [rbx+30h]
0x180031d81  xor     eax, eax
0x180031d83  mov     word ptr [rbp+7A0h+var_820], ax
0x180031d87  mov     word ptr [rsp+8A0h+var_848], ax
0x180031d8c  test    rdx, rdx
0x180031d8f  jz      short loc_180031DA5
0x180031d91  mov     rdx, [rdx+70h]
0x180031d95  test    rdx, rdx
0x180031d98  jz      short loc_180031DA5
0x180031d9a  cmp     [rdx+10h], rax
0x180031d9e  jz      short loc_180031DA5
0x180031da0  mov     edx, [rdx+10h]
0x180031da3  jmp     short loc_180031DA8
0x180031da5  or      edx, 0FFFFFFFFh
0x180031da8  lea     rcx, [rsp+8A0h+var_848]
0x180031dad  call    ConvertPortNoToString
0x180031db2  mov     r8d, esi
0x180031db5  lea     rdx, aIscertrequestp_0; "IsCertRequestPayloadDisabled: RegQueryV"...
0x180031dbc  lea     rcx, [rbp+7A0h+var_820]
0x180031dc0  call    FormatRRASErrorString
0x180031dc5  test    cs:byte_1800AA941, 4
0x180031dcc  jz      short loc_180031E31
0x180031dce  mov     rcx, [rbx+30h]
0x180031dd2  lea     rax, [rcx+70h]
0x180031dd6  test    rcx, rcx
0x180031dd9  jz      short loc_180031E04
0x180031ddb  mov     rdx, [rax]
0x180031dde  test    rdx, rdx
0x180031de1  jz      short loc_180031DEC
0x180031de3  lea     rcx, [rdx+0A7Eh]
0x180031dea  jmp     short loc_180031DF3
0x180031dec  test    rcx, rcx
0x180031def  jz      short loc_180031E04
0x180031df1  xor     ecx, ecx
0x180031df3  mov     rdx, [rax]
0x180031df6  test    rdx, rdx
0x180031df9  jz      short loc_180031E06
0x180031dfb  lea     r9, [rdx+848h]
0x180031e02  jmp     short loc_180031E0B
0x180031e04  xor     ecx, ecx
0x180031e06  lea     r9, [rsp+8A0h+var_858]
0x180031e0b  lea     rax, [rsp+8A0h+var_848]
0x180031e10  mov     [rsp+8A0h+lpcbData], rax
0x180031e15  lea     r8, [rbp+7A0h+var_820]
0x180031e19  mov     [rsp+8A0h+phkResult], rcx
0x180031e1e  lea     rdx, RasVpnIkeParamTraceError
0x180031e25  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180031e2c  call    McTemplateU0zjzz_EventWriteTransfer
0x180031e31  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e38  mov     rax, [rsp+8A0h+hKey]
0x180031e3d  test    rax, rax
0x180031e40  jz      short loc_180031E88
0x180031e42  mov     rcx, rax; hKey
0x180031e45  call    cs:__imp_RegCloseKey
0x180031e4b  jmp     short loc_180031E81
0x180031e4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e54  cmp     rcx, r13
0x180031e57  jz      loc_180031EE1
0x180031e5d  test    byte ptr [rcx+1Ch], 1
0x180031e61  jz      short loc_180031E88
0x180031e63  cmp     byte ptr [rcx+19h], 2
0x180031e67  jb      short loc_180031E88
0x180031e69  mov     rcx, [rcx+10h]
0x180031e6d  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031e74  mov     edx, 0B7h
0x180031e79  mov     r9d, eax
0x180031e7c  call    WPP_SF_d
0x180031e81  mov     rcx, cs:WPP_GLOBAL_Control
0x180031e88  cmp     rcx, r13
0x180031e8b  jz      short loc_180031EE1
0x180031e8d  test    byte ptr [rcx+1Ch], 1
0x180031e91  jz      short loc_180031EB8
0x180031e93  cmp     byte ptr [rcx+19h], 5
0x180031e97  jb      short loc_180031EB8
0x180031e99  mov     rcx, [rcx+10h]
0x180031e9d  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031ea4  mov     r9b, dil
0x180031ea7  mov     edx, 0B8h
0x180031eac  call    WPP_SF_c
0x180031eb1  mov     rcx, cs:WPP_GLOBAL_Control
0x180031eb8  cmp     rcx, r13
0x180031ebb  jz      short loc_180031EE1
0x180031ebd  test    byte ptr [rcx+1Ch], 1
0x180031ec1  jz      short loc_180031EE1
0x180031ec3  cmp     byte ptr [rcx+19h], 6
0x180031ec7  jb      short loc_180031EE1
0x180031ec9  mov     rcx, [rcx+10h]
0x180031ecd  lea     r8, WPP_cb2e8e6748b838ceed61c877d673660f_Traceguids
0x180031ed4  mov     edx, 0B9h
0x180031ed9  mov     r9d, esi
0x180031edc  call    WPP_SF_d
0x180031ee1  mov     eax, edi
0x180031ee3  mov     rcx, [rbp+7A0h+var_20]
0x180031eea  xor     rcx, rsp; StackCookie
0x180031eed  call    __security_check_cookie
0x180031ef2  lea     r11, [rsp+8A0h+var_10]
0x180031efa  mov     rbx, [r11+28h]
0x180031efe  mov     rsi, [r11+30h]
0x180031f02  mov     rsp, r11
0x180031f05  pop     r13
0x180031f07  pop     rdi
0x180031f08  pop     rbp
0x180031f09  retn
```
