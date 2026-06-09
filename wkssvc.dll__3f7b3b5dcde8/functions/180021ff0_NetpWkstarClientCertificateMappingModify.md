# NetpWkstarClientCertificateMappingModify

- ea: `0x180021ff0`
- end: `0x18002244f`
- name: `NetpWkstarClientCertificateMappingModify`
- size: `1119`
- prototype: `__int64 __fastcall(__int64, __int64, __int64 *)`
- caller_count: `0`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update`

## callees

- `0x180008950`
- `0x1800089d0`
- `0x180009a40`
- `0x18001c6dc`
- `0x18001ed46`
- `0x1800206ec`
- `0x1800212b4`
- `0x180021ff0`
- `0x180022b54`
- `0x180023428`
- `0x180023534`
- `0x18002373c`
- `0x180024018`
- `0x180024a24`
- `0x180024f40`
- `0x180025220`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x180022399`
- `ntdll!RtlNtStatusToDosError` at `0x180022399`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022051`
- `ntdll!RtlAcquireResourceExclusive` at `0x180022051`
- `ntdll!RtlReleaseResource` at `0x180022430`
- `ntdll!RtlReleaseResource` at `0x180022430`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022295`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180022295`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002240b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800223ee`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18002240b`

## string_xrefs

- `0x180022020`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingModify(__int64 a1, __int64 a2, __int64 *a3)
{
  int v3; // ebx
  __int64 *v5; // rcx
  _QWORD *v6; // rax
  _QWORD *v7; // r14
  int v8; // r12d
  ULONG updated; // ebx
  char v10; // r15
  __int64 v11; // r9
  _DWORD *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // rdx
  _DWORD *v15; // rax
  __int64 v16; // rdx
  __int64 v17; // r8
  _QWORD *v18; // rcx
  PCWSTR v19; // r9
  int v20; // edx
  int v21; // edx
  int v22; // ebx
  __int64 *v23; // [rsp+80h] [rbp+40h] BYREF

  v23 = a3;
  v3 = a2;
  if ( (unsigned int)NetpAccessCheckAndAuditEx(&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_18004EB90, 1u);
  if ( v3 )
    return 124;
  v5 = v23;
  if ( v23 && (v6 = (_QWORD *)*v23) != 0 && *v6 )
  {
    v7 = 0;
    v8 = 0;
    if ( !v6[3] && !v6[8] )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 105, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
        v5 = v23;
      }
      updated = ClientCertificateMappingActionImpl(v5, 0, 3);
LABEL_60:
      if ( updated )
      {
        if ( v8 )
          WsRemoveCertificateMappingFromRegistry((PCWSTR)*v7);
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
      updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 3855);
      if ( updated )
        goto LABEL_56;
      updated = WsValidateCertificateAndUpdateInfo(&v23);
      WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3860);
      if ( updated )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 108, &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids);
        }
        goto LABEL_56;
      }
      v7 = (_QWORD *)*v23;
      updated = WsAddCertMappingToRegistry(*v23, *(const WCHAR **)*v23, 0);
      if ( updated )
      {
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          goto LABEL_56;
        }
        v20 = 111;
        v19 = *(PCWSTR *)*v23;
      }
      else
      {
        v8 = 1;
        v15 = LocalAlloc(0x40u, 0xB54u);
        v12 = v15;
        if ( !v15 )
        {
          updated = 8;
          goto LABEL_56;
        }
        memset_0(v15, 0, 0xB54u);
        updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 3898);
        if ( updated )
          goto LABEL_56;
        updated = WsGetCertificateMappingsFromStore(*v7, v16, v17, v7[3], v7[8], v12);
        WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3908);
        if ( !updated )
        {
          v21 = v12[34];
          v12[1] = 2;
          *v12 = *((_DWORD *)v7 + 21);
          v22 = WsCertificateUpdate(v12, v21 + 140);
          if ( v22 < 0
            && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
            && *((_BYTE *)WPP_GLOBAL_Control + 25) )
          {
            WPP_SF_Sd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              110,
              (unsigned int)&WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
              *(_QWORD *)*v23,
              v22);
          }
          updated = RtlNtStatusToDosError(v22);
          goto LABEL_56;
        }
        v18 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || !*((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
LABEL_56:
          if ( v10 )
          {
            LocalFree(*(HLOCAL *)(*v23 + 24));
            *(_QWORD *)(*v23 + 24) = 0;
          }
          if ( v12 )
            LocalFree(v12);
          goto LABEL_60;
        }
        v19 = (PCWSTR)*v7;
        v20 = 109;
      }
      WPP_SF_Sd(v18[2], v20, (unsigned int)&WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids, (_DWORD)v19, updated);
      goto LABEL_56;
    }
    updated = WsImpersonateClient2("NetpWkstarClientCertificateMappingModify", 3822);
    if ( !updated )
    {
      updated = LmFindCertificateThatExpiresLast(*(_QWORD *)(*v23 + 64), *(_QWORD *)(*v23 + 16), *v23 + 24);
      WsRevertToSelf2("NetpWkstarClientCertificateMappingModify", 3829);
      if ( updated )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) )
        {
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            106,
            &WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids,
            *(_QWORD *)(*v23 + 16));
        }
        goto LABEL_64;
      }
      v5 = v23;
      v10 = 1;
      goto LABEL_24;
    }
  }
  else
  {
    updated = 87;
  }
LABEL_64:
  RtlReleaseResource(&stru_18004EB90);
  return updated;
}

```

## disassembly

```asm
0x180021ff0  mov     r11, rsp
0x180021ff3  mov     [r11+8], rbx
0x180021ff7  mov     [r11+10h], rsi
0x180021ffb  mov     [r11+18h], r8
0x180021fff  push    rbp
0x180022000  push    rdi
0x180022001  push    r12
0x180022003  push    r14
0x180022005  push    r15
0x180022007  mov     rbp, rsp
0x18002200a  sub     rsp, 40h
0x18002200e  mov     rax, cs:ConfigurationInfoSd
0x180022015  lea     rcx, WsConfigInfoMapping
0x18002201c  mov     [r11-38h], rcx
0x180022020  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180022027  mov     dword ptr [rsp+40h+var_18], 8
0x18002202f  mov     ebx, edx
0x180022031  mov     [r11-48h], rax
0x180022035  call    NetpAccessCheckAndAuditEx
0x18002203a  test    eax, eax
0x18002203c  jz      short loc_180022048
0x18002203e  mov     eax, 5
0x180022043  jmp     loc_180022438
0x180022048  mov     dl, 1; Wait
0x18002204a  lea     rcx, stru_18004EB90; Resource
0x180022051  call    cs:__imp_RtlAcquireResourceExclusive
0x180022057  test    ebx, ebx
0x180022059  jz      short loc_180022065
0x18002205b  mov     eax, 7Ch ; '|'
0x180022060  jmp     loc_180022438
0x180022065  mov     rcx, [rbp+arg_10]
0x180022069  test    rcx, rcx
0x18002206c  jz      loc_180022424
0x180022072  mov     rax, [rcx]
0x180022075  test    rax, rax
0x180022078  jz      loc_180022424
0x18002207e  cmp     qword ptr [rax], 0
0x180022082  jz      loc_180022424
0x180022088  xor     r14d, r14d
0x18002208b  xor     r12d, r12d
0x18002208e  cmp     [rax+18h], r12
0x180022092  jnz     short loc_1800220E3
0x180022094  cmp     [rax+40h], r12
0x180022098  jnz     short loc_1800220E3
0x18002209a  mov     rax, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800220a1  lea     rdi, WPP_GLOBAL_Control
0x1800220a8  cmp     rax, rdi
0x1800220ab  jz      short loc_1800220D1
0x1800220ad  test    byte ptr [rax+1Ch], 2
0x1800220b1  jz      short loc_1800220D1
0x1800220b3  cmp     byte ptr [rax+19h], 2
0x1800220b7  jb      short loc_1800220D1
0x1800220b9  mov     rcx, [rax+10h]
0x1800220bd  lea     edx, [r14+69h]
0x1800220c1  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800220c8  call    WPP_SF_
0x1800220cd  mov     rcx, [rbp+arg_10]
0x1800220d1  xor     edx, edx
0x1800220d3  lea     r8d, [rdx+3]
0x1800220d7  call    ClientCertificateMappingActionImpl
0x1800220dc  mov     ebx, eax
0x1800220de  jmp     loc_180022411
0x1800220e3  xor     r15b, r15b
0x1800220e6  cmp     [rax+40h], r12
0x1800220ea  jz      loc_18002219B
0x1800220f0  cmp     [rax+10h], r12
0x1800220f4  jz      loc_18002219B
0x1800220fa  mov     edx, 0EEEh
0x1800220ff  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180022106  call    WsImpersonateClient2
0x18002210b  mov     ebx, eax
0x18002210d  test    eax, eax
0x18002210f  jnz     loc_180022429
0x180022115  mov     rax, [rbp+arg_10]
0x180022119  mov     rcx, [rax]
0x18002211c  mov     rdx, [rcx+10h]
0x180022120  lea     r8, [rcx+18h]
0x180022124  mov     rcx, [rcx+40h]
0x180022128  call    LmFindCertificateThatExpiresLast
0x18002212d  mov     edx, 0EF5h
0x180022132  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x180022139  mov     ebx, eax
0x18002213b  call    WsRevertToSelf2
0x180022140  test    ebx, ebx
0x180022142  jz      short loc_180022194
0x180022144  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002214b  lea     rdi, WPP_GLOBAL_Control
0x180022152  cmp     rcx, rdi
0x180022155  jz      loc_180022429
0x18002215b  test    byte ptr [rcx+1Ch], 2
0x18002215f  jz      loc_180022429
0x180022165  cmp     byte ptr [rcx+19h], 1
0x180022169  jb      loc_180022429
0x18002216f  mov     rax, [rbp+arg_10]
0x180022173  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002217a  mov     rcx, [rcx+10h]
0x18002217e  mov     edx, 6Ah ; 'j'
0x180022183  mov     r9, [rax]
0x180022186  mov     r9, [r9+10h]
0x18002218a  call    WPP_SF_S
0x18002218f  jmp     loc_180022429
0x180022194  mov     rcx, [rbp+arg_10]
0x180022198  mov     r15b, 1
0x18002219b  mov     r9, [rcx]
0x18002219e  lea     rdi, WPP_GLOBAL_Control
0x1800221a5  xor     esi, esi
0x1800221a7  mov     r8, [r9+18h]
0x1800221ab  test    r8, r8
0x1800221ae  jz      short loc_1800221EF
0x1800221b0  mov     rdx, [r9+40h]
0x1800221b4  test    rdx, rdx
0x1800221b7  jz      short loc_1800221EF
0x1800221b9  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800221c0  cmp     rcx, rdi
0x1800221c3  jz      short loc_1800221EF
0x1800221c5  test    byte ptr [rcx+1Ch], 2
0x1800221c9  jz      short loc_1800221EF
0x1800221cb  cmp     byte ptr [rcx+19h], 2
0x1800221cf  jb      short loc_1800221EF
0x1800221d1  mov     eax, [r9+54h]
0x1800221d5  mov     r9, [r9]
0x1800221d8  mov     rcx, [rcx+10h]; LoggerHandle
0x1800221dc  mov     dword ptr [rsp+40h+var_10], eax; char
0x1800221e0  mov     [rsp+40h+var_18], rdx; __int64
0x1800221e5  mov     [rsp+40h+var_20], r8; __int64
0x1800221ea  call    WPP_SF_SSSd
0x1800221ef  mov     edx, 0F0Fh
0x1800221f4  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x1800221fb  call    WsImpersonateClient2
0x180022200  mov     ebx, eax
0x180022202  test    eax, eax
0x180022204  jnz     loc_1800223DE
0x18002220a  lea     rcx, [rbp+arg_10]
0x18002220e  call    WsValidateCertificateAndUpdateInfo
0x180022213  mov     edx, 0F14h
0x180022218  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x18002221f  mov     ebx, eax
0x180022221  call    WsRevertToSelf2
0x180022226  test    ebx, ebx
0x180022228  jz      short loc_180022268
0x18002222a  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022231  cmp     rcx, rdi
0x180022234  jz      loc_1800223DE
0x18002223a  test    byte ptr [rcx+1Ch], 2
0x18002223e  jz      loc_1800223DE
0x180022244  cmp     byte ptr [rcx+19h], 1
0x180022248  jb      loc_1800223DE
0x18002224e  mov     rcx, [rcx+10h]
0x180022252  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x180022259  mov     edx, 6Ch ; 'l'
0x18002225e  call    WPP_SF_
0x180022263  jmp     loc_1800223DE
0x180022268  mov     rax, [rbp+arg_10]
0x18002226c  xor     r8d, r8d
0x18002226f  mov     r14, [rax]
0x180022272  mov     rcx, r14
0x180022275  mov     rdx, [r14]
0x180022278  call    WsAddCertMappingToRegistry
0x18002227d  mov     ebx, eax
0x18002227f  test    eax, eax
0x180022281  jnz     loc_1800223A3
0x180022287  mov     ebx, 0B54h
0x18002228c  lea     ecx, [rax+40h]; uFlags
0x18002228f  mov     edx, ebx; uBytes
0x180022291  lea     r12d, [rax+1]
0x180022295  call    cs:__imp_LocalAlloc
0x18002229b  mov     rsi, rax
0x18002229e  test    rax, rax
0x1800222a1  jnz     short loc_1800222AB
0x1800222a3  lea     ebx, [rax+8]
0x1800222a6  jmp     loc_1800223DE
0x1800222ab  mov     r8, rbx; Size
0x1800222ae  xor     edx, edx; Val
0x1800222b0  mov     rcx, rsi; void *
0x1800222b3  call    memset_0
0x1800222b8  mov     edx, 0F3Ah
0x1800222bd  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x1800222c4  call    WsImpersonateClient2
0x1800222c9  mov     ebx, eax
0x1800222cb  test    eax, eax
0x1800222cd  jnz     loc_1800223DE
0x1800222d3  mov     rax, [r14+40h]
0x1800222d7  mov     r9, [r14+18h]
0x1800222db  mov     rcx, [r14]
0x1800222de  mov     [rsp+40h+var_18], rsi
0x1800222e3  mov     [rsp+40h+var_20], rax
0x1800222e8  call    WsGetCertificateMappingsFromStore
0x1800222ed  mov     edx, 0F44h
0x1800222f2  lea     rcx, aNetpwkstarclie_1; "NetpWkstarClientCertificateMappingModif"...
0x1800222f9  mov     ebx, eax
0x1800222fb  call    WsRevertToSelf2
0x180022300  test    ebx, ebx
0x180022302  jz      short loc_180022335
0x180022304  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x18002230b  cmp     rcx, rdi
0x18002230e  jz      loc_1800223DE
0x180022314  test    byte ptr [rcx+1Ch], 2
0x180022318  jz      loc_1800223DE
0x18002231e  cmp     [rcx+19h], r12b
0x180022322  jb      loc_1800223DE
0x180022328  mov     r9, [r14]
0x18002232b  mov     edx, 6Dh ; 'm'
0x180022330  jmp     loc_1800223CA
0x180022335  mov     edx, [rsi+88h]
0x18002233b  mov     rcx, rsi; InputBuffer
0x18002233e  mov     dword ptr [rsi+4], 2
0x180022345  add     edx, 8Ch; InputBufferLength
0x18002234b  mov     eax, [r14+54h]
0x18002234f  mov     [rsi], eax
0x180022351  call    WsCertificateUpdate
0x180022356  mov     ebx, eax
0x180022358  test    eax, eax
0x18002235a  jns     short loc_180022397
0x18002235c  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x180022363  cmp     rcx, rdi
0x180022366  jz      short loc_180022397
0x180022368  test    byte ptr [rcx+1Ch], 2
0x18002236c  jz      short loc_180022397
0x18002236e  cmp     [rcx+19h], r12b
0x180022372  jb      short loc_180022397
0x180022374  mov     rax, [rbp+arg_10]
0x180022378  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x18002237f  mov     rcx, [rcx+10h]
0x180022383  mov     edx, 6Eh ; 'n'
0x180022388  mov     dword ptr [rsp+40h+var_20], ebx
0x18002238c  mov     r9, [rax]
0x18002238f  mov     r9, [r9]
0x180022392  call    WPP_SF_Sd
0x180022397  mov     ecx, ebx; Status
0x180022399  call    cs:__imp_RtlNtStatusToDosError
0x18002239f  mov     ebx, eax
0x1800223a1  jmp     short loc_1800223DE
0x1800223a3  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800223aa  cmp     rcx, rdi
0x1800223ad  jz      short loc_1800223DE
0x1800223af  test    byte ptr [rcx+1Ch], 2
0x1800223b3  jz      short loc_1800223DE
0x1800223b5  cmp     byte ptr [rcx+19h], 1
0x1800223b9  jb      short loc_1800223DE
0x1800223bb  mov     rax, [rbp+arg_10]
0x1800223bf  mov     edx, 6Fh ; 'o'
0x1800223c4  mov     r9, [rax]
0x1800223c7  mov     r9, [r9]
0x1800223ca  mov     rcx, [rcx+10h]
0x1800223ce  lea     r8, WPP_a52edf5dabf93e0508dbdd13042930fe_Traceguids
0x1800223d5  mov     dword ptr [rsp+40h+var_20], ebx
0x1800223d9  call    WPP_SF_Sd
0x1800223de  test    r15b, r15b
0x1800223e1  jz      short loc_180022403
0x1800223e3  mov     rax, [rbp+arg_10]
0x1800223e7  mov     rcx, [rax]
0x1800223ea  mov     rcx, [rcx+18h]; hMem
0x1800223ee  call    cs:__imp_LocalFree
0x1800223f4  mov     rax, [rbp+arg_10]
0x1800223f8  mov     rcx, [rax]
0x1800223fb  mov     qword ptr [rcx+18h], 0
0x180022403  test    rsi, rsi
0x180022406  jz      short loc_180022411
0x180022408  mov     rcx, rsi; hMem
0x18002240b  call    cs:__imp_LocalFree
0x180022411  test    ebx, ebx
0x180022413  jz      short loc_180022429
0x180022415  test    r12d, r12d
0x180022418  jz      short loc_180022429
0x18002241a  mov     rcx, [r14]; ValueName
0x18002241d  call    WsRemoveCertificateMappingFromRegistry
0x180022422  jmp     short loc_180022429
0x180022424  mov     ebx, 57h ; 'W'
0x180022429  lea     rcx, stru_18004EB90; Resource
0x180022430  call    cs:__imp_RtlReleaseResource
0x180022436  mov     eax, ebx
0x180022438  mov     rbx, [rsp+40h+arg_0]
0x18002243d  mov     rsi, [rsp+40h+arg_8]
0x180022442  add     rsp, 40h
0x180022446  pop     r15
0x180022448  pop     r14
0x18002244a  pop     r12
0x18002244c  pop     rdi
0x18002244d  pop     rbp
0x18002244e  retn
```
