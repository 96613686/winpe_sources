# ServerBFEHandler::AddRDIkev2Policy(_PROTOCOL_RD_IKEv2_POLICY_INFO *)

- ea: `0x18003ac84`
- end: `0x18003afba`
- name: `?AddRDIkev2Policy@ServerBFEHandler@@SAKPEAU_PROTOCOL_RD_IKEv2_POLICY_INFO@@@Z`
- size: `822`
- prototype: `__int64 __fastcall(struct _PROTOCOL_RD_IKEv2_POLICY_INFO *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800052bc`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18003a470`
- `0x18003ac84`
- `0x18003da94`
- `0x180068c60`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003af4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003af4b`

## string_xrefs

- `0x18003adce`: `AddRDIkev2Policy: Global policy object is not yet created`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::AddRDIkev2Policy(struct _PROTOCOL_RD_IKEv2_POLICY_INFO *a1)
{
  struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *v2; // rsi
  char v3; // bl
  unsigned int v4; // eax
  unsigned int i; // ebx
  unsigned int v6; // eax
  unsigned int v7; // ebx
  unsigned int v9; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v10; // [rsp+38h] [rbp-C8h] BYREF
  HLOCAL hMem[2]; // [rsp+48h] [rbp-B8h]
  __int128 v12; // [rsp+58h] [rbp-A8h]
  __int64 v13; // [rsp+68h] [rbp-98h] BYREF
  __int128 v14; // [rsp+70h] [rbp-90h]
  __int128 v15; // [rsp+80h] [rbp-80h]
  __int64 v16; // [rsp+90h] [rbp-70h]
  int v17; // [rsp+98h] [rbp-68h]
  int v18; // [rsp+9Ch] [rbp-64h]
  _BYTE v19[4]; // [rsp+A0h] [rbp-60h] BYREF
  HLOCAL v20; // [rsp+A8h] [rbp-58h]
  int v21; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v22[2044]; // [rsp+114h] [rbp+14h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v9 = 0;
  v10 = 0;
  *(_OWORD *)hMem = 0;
  v12 = 0;
  memset_0(v19, 0, 0x70u);
  v2 = (struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)*((_QWORD *)a1 + 1);
  v21 = 0;
  memset_0(v22, 0, sizeof(v22));
  v14 = 0;
  v13 = 0;
  v15 = 0;
  v16 = 0;
  v17 = -1;
  v18 = 0;
  v3 = byte_1800AA941;
  if ( (byte_1800AA941 & 8) != 0 )
  {
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v13,
      L"ServerBFEHandler::AddRDIkev2Policy",
      &v9,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
    v3 = byte_1800AA941;
  }
  v10 = 0;
  *(_OWORD *)hMem = 0;
  v12 = 0;
  memset_0(v19, 0, 0x70u);
  if ( *((_DWORD *)a1 + 4) && *((_QWORD *)a1 + 3) )
  {
    if ( ServerBFEHandler::globalPolicyObjectCreated )
    {
      v4 = ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(
             (struct IPSEC_TUNNEL_POLICY2_ *)v19,
             (struct IKEEXT_POLICY2_ *)&v10,
             v2,
             0);
      v9 = v4;
      if ( v4 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v21) = 0;
          FormatRRASErrorString(&v21, L"AddRDIkev2Policy: PopulateRDGlobalOrInterfacePolicy failed: %d", v4);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v21);
        }
      }
      else
      {
        for ( i = 0; i < *((_DWORD *)a1 + 4); ++i )
        {
          v6 = ServerBFEHandler::AddPolicyForInterface(
                 *(void **)(32LL * i + *((_QWORD *)a1 + 3)),
                 (struct IKEEXT_POLICY2_ *)&v10,
                 (struct IPSEC_TUNNEL_POLICY2_ *)v19,
                 0,
                 *(_DWORD *)(32LL * i + *((_QWORD *)a1 + 3) + 16),
                 *(struct _ROUTER_IP_ADDRESS **)(32LL * i + *((_QWORD *)a1 + 3) + 24));
          v9 = v6;
          if ( v6 )
          {
            if ( (byte_1800AA941 & 4) != 0 )
            {
              LOWORD(v21) = 0;
              FormatRRASErrorString(&v21, L"AddRDIkev2Policy: AddPolicyForInterface failed: %d", v6);
              if ( (byte_1800AA941 & 4) != 0 )
                McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v21);
            }
            v9 = 0;
          }
        }
      }
    }
    else
    {
      if ( (v3 & 4) != 0 )
        McTemplateU0z_EventWriteTransfer(
          &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          RasVpnIkeTraceError,
          L"AddRDIkev2Policy: Global policy object is not yet created");
      v9 = 956;
    }
  }
  else
  {
    if ( (v3 & 4) != 0 )
      McTemplateU0z_EventWriteTransfer(
        &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
        RasVpnIkeTraceError,
        L"AddRDIkev2Policy: Invalid input parameters");
    v9 = 87;
  }
  if ( v20 && v20 != (HLOCAL)*(&ServerBFEHandler::globalQMPolicyObject + 1) )
    FreeIpsecOffers(v20);
  if ( hMem[1] && hMem[1] != ::hMem )
    LocalFree(hMem[1]);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 56, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v9);
  }
  v7 = v9;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v13);
  return v7;
}

```

## disassembly

```asm
0x18003ac84  mov     [rsp-8+arg_8], rbx
0x18003ac89  mov     [rsp-8+arg_10], rsi
0x18003ac8e  push    rbp
0x18003ac8f  push    rdi
0x18003ac90  push    r12
0x18003ac92  lea     rbp, [rsp-820h]
0x18003ac9a  sub     rsp, 920h
0x18003aca1  mov     rax, cs:__security_cookie
0x18003aca8  xor     rax, rsp
0x18003acab  mov     [rbp+830h+var_20], rax
0x18003acb2  mov     rdi, rcx
0x18003acb5  lea     r12, WPP_GLOBAL_Control
0x18003acbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003acc3  cmp     rcx, r12
0x18003acc6  jz      short loc_18003ACE9
0x18003acc8  test    byte ptr [rcx+1Ch], 1
0x18003accc  jz      short loc_18003ACE9
0x18003acce  cmp     byte ptr [rcx+19h], 6
0x18003acd2  jb      short loc_18003ACE9
0x18003acd4  mov     edx, 37h ; '7'
0x18003acd9  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003ace0  mov     rcx, [rcx+10h]
0x18003ace4  call    WPP_SF_
0x18003ace9  mov     [rsp+930h+var_900], 0
0x18003acf1  xorps   xmm0, xmm0
0x18003acf4  movups  [rsp+930h+var_8F8], xmm0
0x18003acf9  movups  xmmword ptr [rsp+930h+hMem], xmm0
0x18003acfe  movups  [rsp+930h+var_8D8], xmm0
0x18003ad03  xor     edx, edx; Val
0x18003ad05  lea     r8d, [rdx+70h]; Size
0x18003ad09  lea     rcx, [rbp+830h+var_890]; void *
0x18003ad0d  call    memset_0
0x18003ad12  mov     rsi, [rdi+8]
0x18003ad16  xor     eax, eax
0x18003ad18  mov     [rbp+830h+var_820], eax
0x18003ad1b  xor     edx, edx; Val
0x18003ad1d  mov     r8d, 7FCh; Size
0x18003ad23  lea     rcx, [rbp+830h+var_81C]; void *
0x18003ad27  call    memset_0
0x18003ad2c  xorps   xmm0, xmm0
0x18003ad2f  movdqu  [rsp+930h+var_8C0], xmm0
0x18003ad35  mov     [rsp+930h+var_8C8], 0
0x18003ad3e  xorps   xmm1, xmm1
0x18003ad41  movdqu  [rbp+830h+var_8B0], xmm1
0x18003ad46  mov     [rbp+830h+var_8A0], 0
0x18003ad4e  mov     [rbp+830h+var_898], 0FFFFFFFFh
0x18003ad55  mov     [rbp+830h+var_894], 0
0x18003ad5c  mov     bl, cs:byte_1800AA941
0x18003ad62  test    bl, 8
0x18003ad65  jz      short loc_18003AD8A
0x18003ad67  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003ad6e  lea     r8, [rsp+930h+var_900]; unsigned int *
0x18003ad73  lea     rdx, aServerbfehandl; "ServerBFEHandler::AddRDIkev2Policy"
0x18003ad7a  lea     rcx, [rsp+930h+var_8C8]; this
0x18003ad7f  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003ad84  mov     bl, cs:byte_1800AA941
0x18003ad8a  xorps   xmm0, xmm0
0x18003ad8d  movups  [rsp+930h+var_8F8], xmm0
0x18003ad92  movups  xmmword ptr [rsp+930h+hMem], xmm0
0x18003ad97  movups  [rsp+930h+var_8D8], xmm0
0x18003ad9c  xor     edx, edx; Val
0x18003ad9e  lea     r8d, [rdx+70h]; Size
0x18003ada2  lea     rcx, [rbp+830h+var_890]; void *
0x18003ada6  call    memset_0
0x18003adab  cmp     dword ptr [rdi+10h], 0
0x18003adaf  jz      loc_18003AEF7
0x18003adb5  cmp     qword ptr [rdi+18h], 0
0x18003adba  jz      loc_18003AEF7
0x18003adc0  cmp     cs:?globalPolicyObjectCreated@ServerBFEHandler@@1HA, 0; int ServerBFEHandler::globalPolicyObjectCreated
0x18003adc7  jnz     short loc_18003ADF5
0x18003adc9  test    bl, 4
0x18003adcc  jz      short loc_18003ADE8
0x18003adce  lea     r8, aAddrdikev2poli_2; "AddRDIkev2Policy: Global policy object "...
0x18003add5  lea     rdx, RasVpnIkeTraceError
0x18003addc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ade3  call    McTemplateU0z_EventWriteTransfer
0x18003ade8  mov     [rsp+930h+var_900], 3BCh
0x18003adf0  jmp     loc_18003AF1E
0x18003adf5  xor     r9d, r9d; int
0x18003adf8  mov     r8, rsi; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18003adfb  lea     rdx, [rsp+930h+var_8F8]; struct IKEEXT_POLICY2_ *
0x18003ae00  lea     rcx, [rbp+830h+var_890]; struct IPSEC_TUNNEL_POLICY2_ *
0x18003ae04  call    ?PopulateRDGlobalOrInterfacePolicy@ServerBFEHandler@@KAKPEAUIPSEC_TUNNEL_POLICY2_@@PEAUIKEEXT_POLICY2_@@PEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@H@Z; ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(IPSEC_TUNNEL_POLICY2_ *,IKEEXT_POLICY2_ *,_IKEV2_TUNNEL_CONFIG_PARAMS_4 *,int)
0x18003ae09  mov     r8d, eax
0x18003ae0c  mov     [rsp+930h+var_900], eax
0x18003ae10  test    eax, eax
0x18003ae12  jz      short loc_18003AE60
0x18003ae14  test    cs:byte_1800AA941, 4
0x18003ae1b  jz      loc_18003AF1E
0x18003ae21  xor     eax, eax
0x18003ae23  mov     word ptr [rbp+830h+var_820], ax
0x18003ae27  lea     rdx, aAddrdikev2poli_3; "AddRDIkev2Policy: PopulateRDGlobalOrInt"...
0x18003ae2e  lea     rcx, [rbp+830h+var_820]
0x18003ae32  call    FormatRRASErrorString
0x18003ae37  test    cs:byte_1800AA941, 4
0x18003ae3e  jz      loc_18003AF1E
0x18003ae44  lea     r8, [rbp+830h+var_820]
0x18003ae48  lea     rdx, RasVpnIkeTraceError
0x18003ae4f  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003ae56  call    McTemplateU0z_EventWriteTransfer
0x18003ae5b  jmp     loc_18003AF1E
0x18003ae60  xor     ebx, ebx
0x18003ae62  cmp     ebx, [rdi+10h]
0x18003ae65  jnb     loc_18003AF1E
0x18003ae6b  mov     r10d, ebx
0x18003ae6e  shl     r10, 5
0x18003ae72  mov     rcx, [rdi+18h]
0x18003ae76  mov     rax, [r10+rcx+18h]
0x18003ae7b  mov     [rsp+930h+var_908], rax; struct _ROUTER_IP_ADDRESS *
0x18003ae80  mov     eax, [r10+rcx+10h]
0x18003ae85  mov     [rsp+930h+var_910], eax; unsigned int
0x18003ae89  xor     r9d, r9d; struct _ROUTER_IP_ADDRESS *
0x18003ae8c  lea     r8, [rbp+830h+var_890]; struct IPSEC_TUNNEL_POLICY2_ *
0x18003ae90  lea     rdx, [rsp+930h+var_8F8]; struct IKEEXT_POLICY2_ *
0x18003ae95  mov     rcx, [r10+rcx]; void *
0x18003ae99  call    ?AddPolicyForInterface@ServerBFEHandler@@KAKPEAXPEAUIKEEXT_POLICY2_@@PEAUIPSEC_TUNNEL_POLICY2_@@PEAU_ROUTER_IP_ADDRESS@@K3@Z; ServerBFEHandler::AddPolicyForInterface(void *,IKEEXT_POLICY2_ *,IPSEC_TUNNEL_POLICY2_ *,_ROUTER_IP_ADDRESS *,ulong,_ROUTER_IP_ADDRESS *)
0x18003ae9e  mov     r8d, eax
0x18003aea1  mov     [rsp+930h+var_900], eax
0x18003aea5  test    eax, eax
0x18003aea7  jz      short loc_18003AEF0
0x18003aea9  test    cs:byte_1800AA941, 4
0x18003aeb0  jz      short loc_18003AEE8
0x18003aeb2  xor     eax, eax
0x18003aeb4  mov     word ptr [rbp+830h+var_820], ax
0x18003aeb8  lea     rdx, aAddrdikev2poli; "AddRDIkev2Policy: AddPolicyForInterface"...
0x18003aebf  lea     rcx, [rbp+830h+var_820]
0x18003aec3  call    FormatRRASErrorString
0x18003aec8  test    cs:byte_1800AA941, 4
0x18003aecf  jz      short loc_18003AEE8
0x18003aed1  lea     r8, [rbp+830h+var_820]
0x18003aed5  lea     rdx, RasVpnIkeTraceError
0x18003aedc  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003aee3  call    McTemplateU0z_EventWriteTransfer
0x18003aee8  mov     [rsp+930h+var_900], 0
0x18003aef0  inc     ebx
0x18003aef2  jmp     loc_18003AE62
0x18003aef7  test    bl, 4
0x18003aefa  jz      short loc_18003AF16
0x18003aefc  lea     r8, aAddrdikev2poli_1; "AddRDIkev2Policy: Invalid input paramet"...
0x18003af03  lea     rdx, RasVpnIkeTraceError
0x18003af0a  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003af11  call    McTemplateU0z_EventWriteTransfer
0x18003af16  mov     [rsp+930h+var_900], 57h ; 'W'
0x18003af1e  mov     rcx, [rbp+830h+var_888]; hMem
0x18003af22  test    rcx, rcx
0x18003af25  jz      short loc_18003AF38
0x18003af27  cmp     rcx, qword ptr cs:?globalQMPolicyObject@ServerBFEHandler@@1UIPSEC_TUNNEL_POLICY2_@@A+8; IPSEC_TUNNEL_POLICY2_ ServerBFEHandler::globalQMPolicyObject
0x18003af2e  jz      short loc_18003AF38
0x18003af30  mov     edx, [rbp+830h+var_88C]
0x18003af33  call    FreeIpsecOffers
0x18003af38  mov     rcx, [rsp+930h+hMem+8]; hMem
0x18003af3d  test    rcx, rcx
0x18003af40  jz      short loc_18003AF51
0x18003af42  cmp     rcx, cs:hMem
0x18003af49  jz      short loc_18003AF51
0x18003af4b  call    cs:__imp_LocalFree
0x18003af51  mov     rcx, cs:WPP_GLOBAL_Control
0x18003af58  cmp     rcx, r12
0x18003af5b  jz      short loc_18003AF83
0x18003af5d  test    byte ptr [rcx+1Ch], 1
0x18003af61  jz      short loc_18003AF83
0x18003af63  cmp     byte ptr [rcx+19h], 6
0x18003af67  jb      short loc_18003AF83
0x18003af69  mov     edx, 38h ; '8'
0x18003af6e  mov     r9d, [rsp+930h+var_900]
0x18003af73  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003af7a  mov     rcx, [rcx+10h]
0x18003af7e  call    WPP_SF_d
0x18003af83  mov     ebx, [rsp+930h+var_900]
0x18003af87  lea     rcx, [rsp+930h+var_8C8]; this
0x18003af8c  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003af91  mov     eax, ebx
0x18003af93  mov     rcx, [rbp+830h+var_20]
0x18003af9a  xor     rcx, rsp; StackCookie
0x18003af9d  call    __security_check_cookie
0x18003afa2  lea     r11, [rsp+930h+var_10]
0x18003afaa  mov     rbx, [r11+28h]
0x18003afae  mov     rsi, [r11+30h]
0x18003afb2  mov     rsp, r11
0x18003afb5  pop     r12
0x18003afb7  pop     rdi
0x18003afb8  pop     rbp
0x18003afb9  retn
```
