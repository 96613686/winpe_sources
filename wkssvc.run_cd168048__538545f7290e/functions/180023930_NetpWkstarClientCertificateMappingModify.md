# NetpWkstarClientCertificateMappingModify

- ea: `0x180023930`
- end: `0x180023db4`
- name: `NetpWkstarClientCertificateMappingModify`
- size: `1156`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180009010`
- `0x180009090`
- `0x18000a240`
- `0x18001dcac`
- `0x1800204f6`
- `0x180021ea8`
- `0x180022afc`
- `0x180023930`
- `0x180024520`
- `0x180024e24`
- `0x180024f38`
- `0x180025164`
- `0x180025b38`
- `0x180026638`
- `0x180026bc8`
- `0x180026ef0`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180023ce5`
- `ntdll!RtlNtStatusToDosError` at `0x180023ce5`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023991`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023991`
- `ntdll!RtlReleaseResource` at `0x180023d8e`
- `ntdll!RtlReleaseResource` at `0x180023d8e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023bdb`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180023bdb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d63`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d40`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180023d63`

## string_xrefs

- `0x180023960`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingModify(__int64 a1, __int64 a2, __int64 *a3)
{
  int v3; // ebx
  __int64 *v5; // rcx
  _QWORD *v6; // rax
  __int64 v7; // r14
  int v8; // r12d
  unsigned int updated; // ebx
  char v10; // r15
  __int64 v11; // r9
  _DWORD *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // rdx
  _DWORD *v16; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  _QWORD *v19; // rcx
  PCWSTR v20; // r9
  int v21; // edx
  int v22; // edx
  int v23; // ebx
  __int64 *v24; // [rsp+80h] [rbp+40h] BYREF

  v24 = a3;
  v3 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_180051B90, 1u);
  if ( v3 )
    return 124;
  v5 = v24;
  if ( v24 && (v6 = (_QWORD *)*v24) != 0 && *v6 )
  {
    v7 = 0;
    v8 = 0;
    if ( !v6[3] && !v6[8] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
        v5 = v24;
      }
      updated = ClientCertificateMappingActionImpl(v5, 0, 3);
LABEL_60:
      if ( updated )
      {
        if ( v8 )
          WsRemoveCertificateMappingFromRegistry(*(PCWSTR *)v7);
      }
      goto LABEL_64;
    }
    v10 = 0;
    if ( !v6[8] || !v6[2] )
    {
LABEL_24:
      v11 = *v5;
      v12 = 0;
      v13 = *(_QWORD *)(*v5 + 24);
      if ( v13 )
      {
        v14 = *(_QWORD *)(v11 + 64);
        if ( v14 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          {
            WPP_SF_SSSd(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, v14, *(_DWORD *)(v11 + 84));
          }
        }
      }
      updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 21);
      if ( updated )
        goto LABEL_56;
      updated = WsValidateCertificateAndUpdateInfo(&v24, v15);
      WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3866);
      if ( updated )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids);
        }
        goto LABEL_56;
      }
      v7 = *v24;
      updated = WsAddCertMappingToRegistry(*v24, *(const WCHAR **)*v24, 0);
      if ( updated )
      {
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_56;
        }
        v21 = 111;
        v20 = *(PCWSTR *)*v24;
      }
      else
      {
        v8 = 1;
        v16 = LocalAlloc(0x40u, 0xB54u);
        v12 = v16;
        if ( !v16 )
        {
          updated = 8;
          goto LABEL_56;
        }
        memset_0(v16, 0, 0xB54u);
        updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 64);
        if ( updated )
          goto LABEL_56;
        updated = WsGetCertificateMappingsFromStore(
                    *(_QWORD *)v7,
                    v17,
                    v18,
                    *(const WCHAR **)(v7 + 24),
                    *(void **)(v7 + 64),
                    (__int64)v12);
        WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3914);
        if ( !updated )
        {
          v22 = v12[34];
          v12[1] = 2;
          *v12 = *(_DWORD *)(v7 + 84);
          v23 = WsCertificateUpdate(v12, v22 + 140);
          if ( v23 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
              *(_QWORD *)*v24,
              v23);
          }
          updated = RtlNtStatusToDosError(v23);
          goto LABEL_56;
        }
        v19 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
LABEL_56:
          if ( v10 )
          {
            LocalFree(*(HLOCAL *)(*v24 + 24));
            *(_QWORD *)(*v24 + 24) = 0;
          }
          if ( v12 )
            LocalFree(v12);
          goto LABEL_60;
        }
        v20 = *(PCWSTR *)v7;
        v21 = 109;
      }
      WPP_SF_Sd(v19[2], v21, (unsigned int)&WPP_abf29b036dd53d344014067ca7a3b351_Traceguids, (_DWORD)v20, updated);
      goto LABEL_56;
    }
    updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 244);
    if ( !updated )
    {
      updated = LmFindCertificateThatExpiresLast(
                  *(const void **)(*v24 + 64),
                  *(const void **)(*v24 + 16),
                  (_QWORD *)(*v24 + 24));
      WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3835);
      if ( updated )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            &WPP_abf29b036dd53d344014067ca7a3b351_Traceguids,
            *(_QWORD *)(*v24 + 16));
        }
        goto LABEL_64;
      }
      v5 = v24;
      v10 = 1;
      goto LABEL_24;
    }
  }
  else
  {
    updated = 87;
  }
LABEL_64:
  RtlReleaseResource(&stru_180051B90);
  return updated;
}

```

## disassembly

```asm
0x180023930  mov     r11, rsp
0x180023933  mov     [r11+8], rbx
0x180023937  mov     [r11+10h], rsi
0x18002393b  mov     [r11+18h], r8
0x18002393f  push    rbp
0x180023940  push    rdi
0x180023941  push    r12
0x180023943  push    r14
0x180023945  push    r15
0x180023947  mov     rbp, rsp
0x18002394a  sub     rsp, 40h
0x18002394e  mov     rax, cs:ConfigurationInfoSd
0x180023955  lea     rcx, WsConfigInfoMapping
0x18002395c  mov     [r11-38h], rcx
0x180023960  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180023967  mov     dword ptr [rsp+40h+var_18], 8
0x18002396f  mov     ebx, edx
0x180023971  mov     [r11-48h], rax
0x180023975  call    NetpAccessCheckAndAuditEx
0x18002397a  test    eax, eax
0x18002397c  jz      short loc_180023988
0x18002397e  mov     eax, 5
0x180023983  jmp     loc_180023D9C
0x180023988  mov     dl, 1; Wait
0x18002398a  lea     rcx, stru_180051B90; Resource
0x180023991  call    cs:__imp_RtlAcquireResourceExclusive
0x180023998  nop     dword ptr [rax+rax+00h]
0x18002399d  test    ebx, ebx
0x18002399f  jz      short loc_1800239AB
0x1800239a1  mov     eax, 7Ch ; '|'
0x1800239a6  jmp     loc_180023D9C
0x1800239ab  mov     rcx, [rbp+arg_10]
0x1800239af  test    rcx, rcx
0x1800239b2  jz      loc_180023D82
0x1800239b8  mov     rax, [rcx]
0x1800239bb  test    rax, rax
0x1800239be  jz      loc_180023D82
0x1800239c4  cmp     qword ptr [rax], 0
0x1800239c8  jz      loc_180023D82
0x1800239ce  xor     r14d, r14d
0x1800239d1  xor     r12d, r12d
0x1800239d4  cmp     [rax+18h], r12
0x1800239d8  jnz     short loc_180023A29
0x1800239da  cmp     [rax+40h], r12
0x1800239de  jnz     short loc_180023A29
0x1800239e0  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800239e7  lea     rdi, WPP_GLOBAL_Control
0x1800239ee  cmp     rax, rdi
0x1800239f1  jz      short loc_180023A17
0x1800239f3  test    byte ptr [rax+1Ch], 2
0x1800239f7  jz      short loc_180023A17
0x1800239f9  cmp     byte ptr [rax+19h], 2
0x1800239fd  jb      short loc_180023A17
0x1800239ff  mov     rcx, [rax+10h]
0x180023a03  lea     edx, [r14+69h]
0x180023a07  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023a0e  call    WPP_SF_
0x180023a13  mov     rcx, [rbp+arg_10]
0x180023a17  xor     edx, edx
0x180023a19  lea     r8d, [rdx+3]
0x180023a1d  call    ClientCertificateMappingActionImpl
0x180023a22  mov     ebx, eax
0x180023a24  jmp     loc_180023D6F
0x180023a29  xor     r15b, r15b
0x180023a2c  cmp     [rax+40h], r12
0x180023a30  jz      loc_180023AE1
0x180023a36  cmp     [rax+10h], r12
0x180023a3a  jz      loc_180023AE1
0x180023a40  mov     edx, 0EF4h
0x180023a45  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023a4c  call    WsImpersonateClient2
0x180023a51  mov     ebx, eax
0x180023a53  test    eax, eax
0x180023a55  jnz     loc_180023D87
0x180023a5b  mov     rax, [rbp+arg_10]
0x180023a5f  mov     rcx, [rax]
0x180023a62  mov     rdx, [rcx+10h]
0x180023a66  lea     r8, [rcx+18h]
0x180023a6a  mov     rcx, [rcx+40h]
0x180023a6e  call    LmFindCertificateThatExpiresLast
0x180023a73  mov     edx, 0EFBh
0x180023a78  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023a7f  mov     ebx, eax
0x180023a81  call    WsRevertToSelf2
0x180023a86  test    ebx, ebx
0x180023a88  jz      short loc_180023ADA
0x180023a8a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023a91  lea     rdi, WPP_GLOBAL_Control
0x180023a98  cmp     rcx, rdi
0x180023a9b  jz      loc_180023D87
0x180023aa1  test    byte ptr [rcx+1Ch], 2
0x180023aa5  jz      loc_180023D87
0x180023aab  cmp     byte ptr [rcx+19h], 1
0x180023aaf  jb      loc_180023D87
0x180023ab5  mov     rax, [rbp+arg_10]
0x180023ab9  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023ac0  mov     rcx, [rcx+10h]
0x180023ac4  mov     edx, 6Ah ; 'j'
0x180023ac9  mov     r9, [rax]
0x180023acc  mov     r9, [r9+10h]
0x180023ad0  call    WPP_SF_S
0x180023ad5  jmp     loc_180023D87
0x180023ada  mov     rcx, [rbp+arg_10]
0x180023ade  mov     r15b, 1
0x180023ae1  mov     r9, [rcx]
0x180023ae4  lea     rdi, WPP_GLOBAL_Control
0x180023aeb  xor     esi, esi
0x180023aed  mov     r8, [r9+18h]
0x180023af1  test    r8, r8
0x180023af4  jz      short loc_180023B35
0x180023af6  mov     rdx, [r9+40h]
0x180023afa  test    rdx, rdx
0x180023afd  jz      short loc_180023B35
0x180023aff  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023b06  cmp     rcx, rdi
0x180023b09  jz      short loc_180023B35
0x180023b0b  test    byte ptr [rcx+1Ch], 2
0x180023b0f  jz      short loc_180023B35
0x180023b11  cmp     byte ptr [rcx+19h], 2
0x180023b15  jb      short loc_180023B35
0x180023b17  mov     eax, [r9+54h]
0x180023b1b  mov     r9, [r9]
0x180023b1e  mov     rcx, [rcx+10h]; LoggerHandle
0x180023b22  mov     dword ptr [rsp+40h+var_10], eax; char
0x180023b26  mov     [rsp+40h+var_18], rdx; __int64
0x180023b2b  mov     [rsp+40h+var_20], r8; __int64
0x180023b30  call    WPP_SF_SSSd
0x180023b35  mov     edx, 0F15h
0x180023b3a  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023b41  call    WsImpersonateClient2
0x180023b46  mov     ebx, eax
0x180023b48  test    eax, eax
0x180023b4a  jnz     loc_180023D30
0x180023b50  lea     rcx, [rbp+arg_10]
0x180023b54  call    WsValidateCertificateAndUpdateInfo
0x180023b59  mov     edx, 0F1Ah
0x180023b5e  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023b65  mov     ebx, eax
0x180023b67  call    WsRevertToSelf2
0x180023b6c  test    ebx, ebx
0x180023b6e  jz      short loc_180023BAE
0x180023b70  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023b77  cmp     rcx, rdi
0x180023b7a  jz      loc_180023D30
0x180023b80  test    byte ptr [rcx+1Ch], 2
0x180023b84  jz      loc_180023D30
0x180023b8a  cmp     byte ptr [rcx+19h], 1
0x180023b8e  jb      loc_180023D30
0x180023b94  mov     rcx, [rcx+10h]
0x180023b98  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023b9f  mov     edx, 6Ch ; 'l'
0x180023ba4  call    WPP_SF_
0x180023ba9  jmp     loc_180023D30
0x180023bae  mov     rax, [rbp+arg_10]
0x180023bb2  xor     r8d, r8d
0x180023bb5  mov     r14, [rax]
0x180023bb8  mov     rcx, r14
0x180023bbb  mov     rdx, [r14]
0x180023bbe  call    WsAddCertMappingToRegistry
0x180023bc3  mov     ebx, eax
0x180023bc5  test    eax, eax
0x180023bc7  jnz     loc_180023CF5
0x180023bcd  mov     ebx, 0B54h
0x180023bd2  lea     ecx, [rax+40h]; uFlags
0x180023bd5  mov     edx, ebx; uBytes
0x180023bd7  lea     r12d, [rax+1]
0x180023bdb  call    cs:__imp_LocalAlloc
0x180023be2  nop     dword ptr [rax+rax+00h]
0x180023be7  mov     rsi, rax
0x180023bea  test    rax, rax
0x180023bed  jnz     short loc_180023BF7
0x180023bef  lea     ebx, [rax+8]
0x180023bf2  jmp     loc_180023D30
0x180023bf7  mov     r8, rbx; Size
0x180023bfa  xor     edx, edx; Val
0x180023bfc  mov     rcx, rsi; void *
0x180023bff  call    memset_0
0x180023c04  mov     edx, 0F40h
0x180023c09  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023c10  call    WsImpersonateClient2
0x180023c15  mov     ebx, eax
0x180023c17  test    eax, eax
0x180023c19  jnz     loc_180023D30
0x180023c1f  mov     rax, [r14+40h]
0x180023c23  mov     r9, [r14+18h]
0x180023c27  mov     rcx, [r14]
0x180023c2a  mov     [rsp+40h+var_18], rsi
0x180023c2f  mov     [rsp+40h+var_20], rax
0x180023c34  call    WsGetCertificateMappingsFromStore
0x180023c39  mov     edx, 0F4Ah
0x180023c3e  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180023c45  mov     ebx, eax
0x180023c47  call    WsRevertToSelf2
0x180023c4c  test    ebx, ebx
0x180023c4e  jz      short loc_180023C81
0x180023c50  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023c57  cmp     rcx, rdi
0x180023c5a  jz      loc_180023D30
0x180023c60  test    byte ptr [rcx+1Ch], 2
0x180023c64  jz      loc_180023D30
0x180023c6a  cmp     [rcx+19h], r12b
0x180023c6e  jb      loc_180023D30
0x180023c74  mov     r9, [r14]
0x180023c77  mov     edx, 6Dh ; 'm'
0x180023c7c  jmp     loc_180023D1C
0x180023c81  mov     edx, [rsi+88h]
0x180023c87  mov     rcx, rsi; InputBuffer
0x180023c8a  mov     dword ptr [rsi+4], 2
0x180023c91  add     edx, 8Ch; InputBufferLength
0x180023c97  mov     eax, [r14+54h]
0x180023c9b  mov     [rsi], eax
0x180023c9d  call    WsCertificateUpdate
0x180023ca2  mov     ebx, eax
0x180023ca4  test    eax, eax
0x180023ca6  jns     short loc_180023CE3
0x180023ca8  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023caf  cmp     rcx, rdi
0x180023cb2  jz      short loc_180023CE3
0x180023cb4  test    byte ptr [rcx+1Ch], 2
0x180023cb8  jz      short loc_180023CE3
0x180023cba  cmp     [rcx+19h], r12b
0x180023cbe  jb      short loc_180023CE3
0x180023cc0  mov     rax, [rbp+arg_10]
0x180023cc4  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023ccb  mov     rcx, [rcx+10h]
0x180023ccf  mov     edx, 6Eh ; 'n'
0x180023cd4  mov     dword ptr [rsp+40h+var_20], ebx
0x180023cd8  mov     r9, [rax]
0x180023cdb  mov     r9, [r9]
0x180023cde  call    WPP_SF_Sd
0x180023ce3  mov     ecx, ebx; Status
0x180023ce5  call    cs:__imp_RtlNtStatusToDosError
0x180023cec  nop     dword ptr [rax+rax+00h]
0x180023cf1  mov     ebx, eax
0x180023cf3  jmp     short loc_180023D30
0x180023cf5  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180023cfc  cmp     rcx, rdi
0x180023cff  jz      short loc_180023D30
0x180023d01  test    byte ptr [rcx+1Ch], 2
0x180023d05  jz      short loc_180023D30
0x180023d07  cmp     byte ptr [rcx+19h], 1
0x180023d0b  jb      short loc_180023D30
0x180023d0d  mov     rax, [rbp+arg_10]
0x180023d11  mov     edx, 6Fh ; 'o'
0x180023d16  mov     r9, [rax]
0x180023d19  mov     r9, [r9]
0x180023d1c  mov     rcx, [rcx+10h]
0x180023d20  lea     r8, WPP_abf29b036dd53d344014067ca7a3b351_Traceguids
0x180023d27  mov     dword ptr [rsp+40h+var_20], ebx
0x180023d2b  call    WPP_SF_Sd
0x180023d30  test    r15b, r15b
0x180023d33  jz      short loc_180023D5B
0x180023d35  mov     rax, [rbp+arg_10]
0x180023d39  mov     rcx, [rax]
0x180023d3c  mov     rcx, [rcx+18h]; hMem
0x180023d40  call    cs:__imp_LocalFree
0x180023d47  nop     dword ptr [rax+rax+00h]
0x180023d4c  mov     rax, [rbp+arg_10]
0x180023d50  mov     rcx, [rax]
0x180023d53  mov     qword ptr [rcx+18h], 0
0x180023d5b  test    rsi, rsi
0x180023d5e  jz      short loc_180023D6F
0x180023d60  mov     rcx, rsi; hMem
0x180023d63  call    cs:__imp_LocalFree
0x180023d6a  nop     dword ptr [rax+rax+00h]
0x180023d6f  test    ebx, ebx
0x180023d71  jz      short loc_180023D87
0x180023d73  test    r12d, r12d
0x180023d76  jz      short loc_180023D87
0x180023d78  mov     rcx, [r14]; ValueName
0x180023d7b  call    WsRemoveCertificateMappingFromRegistry
0x180023d80  jmp     short loc_180023D87
0x180023d82  mov     ebx, 57h ; 'W'
0x180023d87  lea     rcx, stru_180051B90; Resource
0x180023d8e  call    cs:__imp_RtlReleaseResource
0x180023d95  nop     dword ptr [rax+rax+00h]
0x180023d9a  mov     eax, ebx
0x180023d9c  mov     rbx, [rsp+40h+arg_0]
0x180023da1  mov     rsi, [rsp+40h+arg_8]
0x180023da6  add     rsp, 40h
0x180023daa  pop     r15
0x180023dac  pop     r14
0x180023dae  pop     r12
0x180023db0  pop     rdi
0x180023db1  pop     rbp
0x180023db2  retn
```
