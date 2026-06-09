# ServerBFEHandler::AddPskPolicyForInterface(_PROTOCOL_IKEv2_PSK_POLICY_INFO *)

- ea: `0x18003a830`
- end: `0x18003ac7b`
- name: `?AddPskPolicyForInterface@ServerBFEHandler@@SAKPEAU_PROTOCOL_IKEv2_PSK_POLICY_INFO@@@Z`
- size: `1099`
- prototype: `__int64 __fastcall(struct _PROTOCOL_IKEv2_PSK_POLICY_INFO *)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800052bc`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18003a470`
- `0x18003a830`
- `0x18003da94`
- `0x180040308`
- `0x180068c60`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ac05`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003ac05`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003aa46`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18003aa46`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aa32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003abf7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003aa32`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003abf7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abec`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003abec`

## string_xrefs

- `0x18003a974`: `AddPskPolicyForInterface: Global policy object is not yet created`
- `0x18003aa29`: `AddPskPolicyForInterface: RemovePskPolicyForInterface failed: %d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ServerBFEHandler::AddPskPolicyForInterface(struct _PROTOCOL_IKEv2_PSK_POLICY_INFO *a1)
{
  _DWORD *v2; // rdi
  struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *v3; // r14
  char v4; // bl
  _BYTE *v5; // rax
  unsigned int v6; // eax
  __int64 v7; // r8
  const wchar_t *v8; // rdx
  unsigned int v9; // eax
  HANDLE ProcessHeap; // rax
  __int64 v11; // r11
  int v12; // r8d
  __int64 v13; // r9
  unsigned int i; // ecx
  _OWORD *v15; // r10
  int v16; // ebx
  int v17; // eax
  __int64 v18; // rcx
  int v19; // eax
  __int64 v20; // rcx
  int v21; // eax
  unsigned int v22; // eax
  HANDLE v23; // rax
  unsigned int v24; // ebx
  unsigned int v26; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v27; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-B8h]
  __int128 v29; // [rsp+58h] [rbp-A8h]
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int128 v32; // [rsp+80h] [rbp-80h]
  __int64 v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+98h] [rbp-68h]
  int v35; // [rsp+9Ch] [rbp-64h]
  _BYTE v36[4]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v37; // [rsp+A8h] [rbp-58h]
  int v38; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v39[2044]; // [rsp+114h] [rbp+14h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 49, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v26 = 0;
  v27 = 0;
  *(_OWORD *)hMem = 0;
  v29 = 0;
  memset_0(v36, 0, 0x70u);
  v2 = 0;
  v3 = (struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)*((_QWORD *)a1 + 7);
  v38 = 0;
  memset_0(v39, 0, sizeof(v39));
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v34 = -1;
  v35 = 0;
  v4 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"ServerBFEHandler::AddPskPolicyForInterface",
      &v26,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v4 = byte_1800AA941;
  }
  memset_0(v36, 0, 0x70u);
  if ( *((_DWORD *)a1 + 10) && *((_QWORD *)a1 + 6) && (v5 = (_BYTE *)*((_QWORD *)a1 + 2)) != 0 && *v5 )
  {
    if ( !ServerBFEHandler::globalPolicyObjectCreated )
    {
      if ( (v4 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"AddPskPolicyForInterface: Global policy object is not yet created");
      v26 = 956;
      goto LABEL_44;
    }
    v6 = ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(
           (struct IPSEC_TUNNEL_POLICY2_ *)v36,
           (struct IKEEXT_POLICY2_ *)&v27,
           v3,
           1);
    v7 = v6;
    v26 = v6;
    if ( v6 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_44;
      v8 = L"AddPskPolicyForInterface: PopulateRDGlobalOrInterfacePolicy failed: %d";
      goto LABEL_18;
    }
    v9 = ServerBFEHandler::RemovePskPolicyForInterface(a1);
    v7 = v9;
    v26 = v9;
    if ( v9 )
    {
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_44;
      v8 = L"AddPskPolicyForInterface: RemovePskPolicyForInterface failed: %d";
      goto LABEL_18;
    }
    ProcessHeap = GetProcessHeap();
    v2 = HeapAlloc(ProcessHeap, 8u, 0x1E0u);
    if ( !v2 )
    {
      v26 = 8;
      if ( (byte_1800AA941 & 4) == 0 )
        goto LABEL_44;
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, L"VPNIKE_MALLOC failed: %d", 8);
      goto LABEL_19;
    }
    v11 = 0;
    v12 = -1;
    v13 = 0;
    for ( i = dword_1800AAA8C; (unsigned int)v13 < i; v13 = (unsigned int)(v13 + 1) )
    {
      v15 = lpMem;
      v16 = *((_DWORD *)lpMem + 20 * v13);
      v17 = v11;
      if ( v16 )
        v17 = v12;
      v12 = v17;
      if ( v16 != 1 && (unsigned int)(v16 - 7) > 1 )
      {
        v18 = 10 * v11;
        *(_OWORD *)&v2[2 * v18] = *((_OWORD *)lpMem + 5 * v13);
        *(_OWORD *)&v2[2 * v18 + 4] = v15[5 * v13 + 1];
        *(_OWORD *)&v2[2 * v18 + 8] = v15[5 * v13 + 2];
        *(_OWORD *)&v2[2 * v18 + 12] = v15[5 * v13 + 3];
        *(_OWORD *)&v2[2 * v18 + 16] = v15[5 * v13 + 4];
        v11 = (unsigned int)(v11 + 1);
        i = dword_1800AAA8C;
      }
    }
    v19 = v11;
    if ( v12 != -1 )
      v19 = v12;
    v20 = 10LL * v19;
    v2[2 * v20] = 0;
    v2[2 * v20 + 2] = *((_DWORD *)a1 + 6);
    *(_QWORD *)&v2[2 * v20 + 4] = *((_QWORD *)a1 + 2);
    v2[2 * v20 + 6] = 0;
    *((_QWORD *)&v27 + 1) = v2;
    v21 = v11 + 1;
    if ( v12 != -1 )
      v21 = v11;
    DWORD1(v27) = v21;
    v22 = ServerBFEHandler::AddPolicyForInterface(
            *(void **)a1,
            (struct IKEEXT_POLICY2_ *)&v27,
            (struct IPSEC_TUNNEL_POLICY2_ *)v36,
            *((struct _ROUTER_IP_ADDRESS **)a1 + 4),
            *((_DWORD *)a1 + 10),
            *((struct _ROUTER_IP_ADDRESS **)a1 + 6));
    v7 = v22;
    v26 = v22;
    if ( v22 && (byte_1800AA941 & 4) != 0 )
    {
      v8 = L"AddPskPolicyForInterface: AddPolicyForInterface failed: %d";
LABEL_18:
      LOWORD(v38) = 0;
      FormatRRASErrorString(&v38, v8, v7);
LABEL_19:
      if ( (byte_1800AA941 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v38);
    }
  }
  else
  {
    if ( (v4 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"AddPskPolicyForInterface: Invalid input parameters");
    v26 = 87;
  }
LABEL_44:
  if ( v37 && v37 != (HLOCAL)*(&ServerBFEHandler::globalQMPolicyObject + 1) )
    FreeIpsecOffers(v37);
  if ( hMem[1] && hMem[1] != ::hMem )
    LocalFree(hMem[1]);
  if ( v2 )
  {
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v2);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v26);
  }
  v24 = v26;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return v24;
}

```

## disassembly

```asm
0x18003a830  mov     [rsp-8+arg_8], rbx
0x18003a835  mov     [rsp-8+arg_10], rsi
0x18003a83a  push    rbp
0x18003a83b  push    rdi
0x18003a83c  push    r14
0x18003a83e  lea     rbp, [rsp-820h]
0x18003a846  sub     rsp, 920h
0x18003a84d  mov     rax, cs:__security_cookie
0x18003a854  xor     rax, rsp
0x18003a857  mov     [rbp+830h+var_20], rax
0x18003a85e  mov     rsi, rcx
0x18003a861  lea     rax, WPP_GLOBAL_Control
0x18003a868  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a86f  cmp     rcx, rax
0x18003a872  jz      short loc_18003A895
0x18003a874  test    byte ptr [rcx+1Ch], 1
0x18003a878  jz      short loc_18003A895
0x18003a87a  cmp     byte ptr [rcx+19h], 6
0x18003a87e  jb      short loc_18003A895
0x18003a880  mov     edx, 31h ; '1'
0x18003a885  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003a88c  mov     rcx, [rcx+10h]
0x18003a890  call    WPP_SF_
0x18003a895  mov     [rsp+930h+var_900], 0
0x18003a89d  xorps   xmm0, xmm0
0x18003a8a0  movups  [rsp+930h+var_8F8], xmm0
0x18003a8a5  movups  xmmword ptr [rsp+930h+hMem], xmm0
0x18003a8aa  movups  [rsp+930h+var_8D8], xmm0
0x18003a8af  xor     edx, edx; Val
0x18003a8b1  lea     r8d, [rdx+70h]; Size
0x18003a8b5  lea     rcx, [rbp+830h+var_890]; void *
0x18003a8b9  call    memset_0
0x18003a8be  xor     edi, edi
0x18003a8c0  mov     r14, [rsi+38h]
0x18003a8c4  xor     eax, eax
0x18003a8c6  mov     [rbp+830h+var_820], eax
0x18003a8c9  xor     edx, edx; Val
0x18003a8cb  mov     r8d, 7FCh; Size
0x18003a8d1  lea     rcx, [rbp+830h+var_81C]; void *
0x18003a8d5  call    memset_0
0x18003a8da  xorps   xmm0, xmm0
0x18003a8dd  movdqu  [rsp+930h+var_8C0], xmm0
0x18003a8e3  mov     [rsp+930h+var_8C8], rdi
0x18003a8e8  xorps   xmm1, xmm1
0x18003a8eb  movdqu  [rbp+830h+var_8B0], xmm1
0x18003a8f0  mov     [rbp+830h+var_8A0], rdi
0x18003a8f4  mov     [rbp+830h+var_898], 0FFFFFFFFh
0x18003a8fb  mov     [rbp+830h+var_894], edi
0x18003a8fe  mov     bl, cs:byte_1800AA941
0x18003a904  test    bl, 8
0x18003a907  jz      short loc_18003A92C
0x18003a909  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003a910  lea     r8, [rsp+930h+var_900]; unsigned int *
0x18003a915  lea     rdx, aServerbfehandl_16; "ServerBFEHandler::AddPskPolicyForInterf"...
0x18003a91c  lea     rcx, [rsp+930h+var_8C8]; this
0x18003a921  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003a926  mov     bl, cs:byte_1800AA941
0x18003a92c  xor     edx, edx; Val
0x18003a92e  lea     r8d, [rdx+70h]; Size
0x18003a932  lea     rcx, [rbp+830h+var_890]; void *
0x18003a936  call    memset_0
0x18003a93b  cmp     dword ptr [rsi+28h], 0
0x18003a93f  jz      loc_18003AB98
0x18003a945  cmp     qword ptr [rsi+30h], 0
0x18003a94a  jz      loc_18003AB98
0x18003a950  mov     rax, [rsi+10h]
0x18003a954  test    rax, rax
0x18003a957  jz      loc_18003AB98
0x18003a95d  cmp     byte ptr [rax], 0
0x18003a960  jz      loc_18003AB98
0x18003a966  cmp     cs:?globalPolicyObjectCreated@ServerBFEHandler@@1HA, 0; int ServerBFEHandler::globalPolicyObjectCreated
0x18003a96d  jnz     short loc_18003A99B
0x18003a96f  test    bl, 4
0x18003a972  jz      short loc_18003A98E
0x18003a974  lea     r8, aAddpskpolicyfo_2; "AddPskPolicyForInterface: Global policy"...
0x18003a97b  lea     rdx, RasVpnIkeTraceError
0x18003a982  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003a989  call    McTemplateU0z_EventWriteTransfer
0x18003a98e  mov     [rsp+930h+var_900], 3BCh
0x18003a996  jmp     loc_18003ABBF
0x18003a99b  mov     r9d, 1; int
0x18003a9a1  mov     r8, r14; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18003a9a4  lea     rdx, [rsp+930h+var_8F8]; struct IKEEXT_POLICY2_ *
0x18003a9a9  lea     rcx, [rbp+830h+var_890]; struct IPSEC_TUNNEL_POLICY2_ *
0x18003a9ad  call    ?PopulateRDGlobalOrInterfacePolicy@ServerBFEHandler@@KAKPEAUIPSEC_TUNNEL_POLICY2_@@PEAUIKEEXT_POLICY2_@@PEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@H@Z; ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(IPSEC_TUNNEL_POLICY2_ *,IKEEXT_POLICY2_ *,_IKEV2_TUNNEL_CONFIG_PARAMS_4 *,int)
0x18003a9b2  mov     r8d, eax
0x18003a9b5  mov     [rsp+930h+var_900], eax
0x18003a9b9  test    eax, eax
0x18003a9bb  jz      short loc_18003AA09
0x18003a9bd  test    cs:byte_1800AA941, 4
0x18003a9c4  jz      loc_18003ABBF
0x18003a9ca  lea     rdx, aAddpskpolicyfo; "AddPskPolicyForInterface: PopulateRDGlo"...
0x18003a9d1  xor     eax, eax
0x18003a9d3  mov     word ptr [rbp+830h+var_820], ax
0x18003a9d7  lea     rcx, [rbp+830h+var_820]
0x18003a9db  call    FormatRRASErrorString
0x18003a9e0  test    cs:byte_1800AA941, 4
0x18003a9e7  jz      loc_18003ABBF
0x18003a9ed  lea     r8, [rbp+830h+var_820]
0x18003a9f1  lea     rdx, RasVpnIkeTraceError
0x18003a9f8  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003a9ff  call    McTemplateU0z_EventWriteTransfer
0x18003aa04  jmp     loc_18003ABBF
0x18003aa09  mov     rcx, rsi; struct _PROTOCOL_IKEv2_PSK_POLICY_INFO *
0x18003aa0c  call    ?RemovePskPolicyForInterface@ServerBFEHandler@@SAKPEAU_PROTOCOL_IKEv2_PSK_POLICY_INFO@@@Z; ServerBFEHandler::RemovePskPolicyForInterface(_PROTOCOL_IKEv2_PSK_POLICY_INFO *)
0x18003aa11  mov     r8d, eax
0x18003aa14  mov     [rsp+930h+var_900], eax
0x18003aa18  test    eax, eax
0x18003aa1a  jz      short loc_18003AA32
0x18003aa1c  test    cs:byte_1800AA941, 4
0x18003aa23  jz      loc_18003ABBF
0x18003aa29  lea     rdx, aAddpskpolicyfo_0; "AddPskPolicyForInterface: RemovePskPoli"...
0x18003aa30  jmp     short loc_18003A9D1
0x18003aa32  call    cs:__imp_GetProcessHeap
0x18003aa38  mov     rcx, rax; hHeap
0x18003aa3b  mov     edx, 8; dwFlags
0x18003aa40  mov     r8d, 1E0h; dwBytes
0x18003aa46  call    cs:__imp_HeapAlloc
0x18003aa4c  mov     rdi, rax
0x18003aa4f  test    rax, rax
0x18003aa52  jnz     short loc_18003AA7F
0x18003aa54  mov     [rsp+930h+var_900], 8
0x18003aa5c  test    cs:byte_1800AA941, 4
0x18003aa63  jz      loc_18003ABBF
0x18003aa69  xor     ecx, ecx
0x18003aa6b  mov     word ptr [rbp+830h+var_820], cx
0x18003aa6f  lea     r8d, [rax+8]
0x18003aa73  lea     rdx, aVpnikeMallocFa_0; "VPNIKE_MALLOC failed: %d"
0x18003aa7a  jmp     loc_18003A9D7
0x18003aa7f  xor     r11d, r11d
0x18003aa82  or      r8d, 0FFFFFFFFh
0x18003aa86  xor     r9d, r9d
0x18003aa89  mov     ecx, cs:dword_1800AAA8C
0x18003aa8f  test    ecx, ecx
0x18003aa91  jz      short loc_18003AB0B
0x18003aa93  lea     rdx, [r9+r9*4]
0x18003aa97  add     rdx, rdx
0x18003aa9a  mov     r10, cs:lpMem
0x18003aaa1  mov     ebx, [r10+rdx*8]
0x18003aaa5  mov     eax, r11d
0x18003aaa8  test    ebx, ebx
0x18003aaaa  cmovnz  eax, r8d
0x18003aaae  mov     r8d, eax
0x18003aab1  cmp     ebx, 1
0x18003aab4  jz      short loc_18003AB03
0x18003aab6  lea     eax, [rbx-7]
0x18003aab9  cmp     eax, 1
0x18003aabc  jbe     short loc_18003AB03
0x18003aabe  lea     rcx, [r11+r11*4]
0x18003aac2  add     rcx, rcx
0x18003aac5  movups  xmm0, xmmword ptr [r10+rdx*8]
0x18003aaca  movups  xmmword ptr [rdi+rcx*8], xmm0
0x18003aace  movups  xmm1, xmmword ptr [r10+rdx*8+10h]
0x18003aad4  movups  xmmword ptr [rdi+rcx*8+10h], xmm1
0x18003aad9  movups  xmm0, xmmword ptr [r10+rdx*8+20h]
0x18003aadf  movups  xmmword ptr [rdi+rcx*8+20h], xmm0
0x18003aae4  movups  xmm1, xmmword ptr [r10+rdx*8+30h]
0x18003aaea  movups  xmmword ptr [rdi+rcx*8+30h], xmm1
0x18003aaef  movups  xmm0, xmmword ptr [r10+rdx*8+40h]
0x18003aaf5  movups  xmmword ptr [rdi+rcx*8+40h], xmm0
0x18003aafa  inc     r11d
0x18003aafd  mov     ecx, cs:dword_1800AAA8C
0x18003ab03  inc     r9d
0x18003ab06  cmp     r9d, ecx
0x18003ab09  jb      short loc_18003AA93
0x18003ab0b  mov     eax, r11d
0x18003ab0e  cmp     r8d, 0FFFFFFFFh
0x18003ab12  cmovnz  eax, r8d
0x18003ab16  cdqe
0x18003ab18  lea     rcx, [rax+rax*4]
0x18003ab1c  add     rcx, rcx
0x18003ab1f  mov     dword ptr [rdi+rcx*8], 0
0x18003ab26  mov     eax, [rsi+18h]
0x18003ab29  mov     [rdi+rcx*8+8], eax
0x18003ab2d  mov     rax, [rsi+10h]
0x18003ab31  mov     [rdi+rcx*8+10h], rax
0x18003ab36  mov     dword ptr [rdi+rcx*8+18h], 0
0x18003ab3e  mov     qword ptr [rsp+930h+var_8F8+8], rdi
0x18003ab43  lea     eax, [r11+1]
0x18003ab47  cmp     r8d, 0FFFFFFFFh
0x18003ab4b  cmovnz  eax, r11d
0x18003ab4f  mov     dword ptr [rsp+930h+var_8F8+4], eax
0x18003ab53  mov     rax, [rsi+30h]
0x18003ab57  mov     [rsp+930h+var_908], rax; struct _ROUTER_IP_ADDRESS *
0x18003ab5c  mov     eax, [rsi+28h]
0x18003ab5f  mov     [rsp+930h+var_910], eax; unsigned int
0x18003ab63  mov     r9, [rsi+20h]; struct _ROUTER_IP_ADDRESS *
0x18003ab67  lea     r8, [rbp+830h+var_890]; struct IPSEC_TUNNEL_POLICY2_ *
0x18003ab6b  lea     rdx, [rsp+930h+var_8F8]; struct IKEEXT_POLICY2_ *
0x18003ab70  mov     rcx, [rsi]; void *
0x18003ab73  call    ?AddPolicyForInterface@ServerBFEHandler@@KAKPEAXPEAUIKEEXT_POLICY2_@@PEAUIPSEC_TUNNEL_POLICY2_@@PEAU_ROUTER_IP_ADDRESS@@K3@Z; ServerBFEHandler::AddPolicyForInterface(void *,IKEEXT_POLICY2_ *,IPSEC_TUNNEL_POLICY2_ *,_ROUTER_IP_ADDRESS *,ulong,_ROUTER_IP_ADDRESS *)
0x18003ab78  mov     r8d, eax
0x18003ab7b  mov     [rsp+930h+var_900], eax
0x18003ab7f  test    eax, eax
0x18003ab81  jz      short loc_18003ABBF
0x18003ab83  test    cs:byte_1800AA941, 4
0x18003ab8a  jz      short loc_18003ABBF
0x18003ab8c  lea     rdx, aAddpskpolicyfo_1; "AddPskPolicyForInterface: AddPolicyForI"...
0x18003ab93  jmp     loc_18003A9D1
0x18003ab98  test    bl, 4
0x18003ab9b  jz      short loc_18003ABB7
0x18003ab9d  lea     r8, aAddpskpolicyfo_3; "AddPskPolicyForInterface: Invalid input"...
0x18003aba4  lea     rdx, RasVpnIkeTraceError
0x18003abab  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003abb2  call    McTemplateU0z_EventWriteTransfer
0x18003abb7  mov     [rsp+930h+var_900], 57h ; 'W'
0x18003abbf  mov     rcx, [rbp+830h+var_888]; hMem
0x18003abc3  test    rcx, rcx
0x18003abc6  jz      short loc_18003ABD9
0x18003abc8  cmp     rcx, qword ptr cs:?globalQMPolicyObject@ServerBFEHandler@@1UIPSEC_TUNNEL_POLICY2_@@A+8; IPSEC_TUNNEL_POLICY2_ ServerBFEHandler::globalQMPolicyObject
0x18003abcf  jz      short loc_18003ABD9
0x18003abd1  mov     edx, [rbp+830h+var_88C]
0x18003abd4  call    FreeIpsecOffers
0x18003abd9  mov     rcx, [rsp+930h+hMem+8]; hMem
0x18003abde  test    rcx, rcx
0x18003abe1  jz      short loc_18003ABF2
0x18003abe3  cmp     rcx, cs:hMem
0x18003abea  jz      short loc_18003ABF2
0x18003abec  call    cs:__imp_LocalFree
0x18003abf2  test    rdi, rdi
0x18003abf5  jz      short loc_18003AC0B
0x18003abf7  call    cs:__imp_GetProcessHeap
0x18003abfd  mov     rcx, rax; hHeap
0x18003ac00  mov     r8, rdi; lpMem
0x18003ac03  xor     edx, edx; dwFlags
0x18003ac05  call    cs:__imp_HeapFree
0x18003ac0b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac12  lea     rax, WPP_GLOBAL_Control
0x18003ac19  cmp     rcx, rax
0x18003ac1c  jz      short loc_18003AC44
0x18003ac1e  test    byte ptr [rcx+1Ch], 1
0x18003ac22  jz      short loc_18003AC44
0x18003ac24  cmp     byte ptr [rcx+19h], 6
0x18003ac28  jb      short loc_18003AC44
0x18003ac2a  mov     edx, 32h ; '2'
0x18003ac2f  mov     r9d, [rsp+930h+var_900]
0x18003ac34  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003ac3b  mov     rcx, [rcx+10h]
0x18003ac3f  call    WPP_SF_d
0x18003ac44  mov     ebx, [rsp+930h+var_900]
0x18003ac48  lea     rcx, [rsp+930h+var_8C8]; this
0x18003ac4d  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003ac52  mov     eax, ebx
0x18003ac54  mov     rcx, [rbp+830h+var_20]
0x18003ac5b  xor     rcx, rsp; StackCookie
0x18003ac5e  call    __security_check_cookie
0x18003ac63  lea     r11, [rsp+930h+var_10]
0x18003ac6b  mov     rbx, [r11+28h]
0x18003ac6f  mov     rsi, [r11+30h]
0x18003ac73  mov     rsp, r11
0x18003ac76  pop     r14
0x18003ac78  pop     rdi
0x18003ac79  pop     rbp
0x18003ac7a  retn
```
