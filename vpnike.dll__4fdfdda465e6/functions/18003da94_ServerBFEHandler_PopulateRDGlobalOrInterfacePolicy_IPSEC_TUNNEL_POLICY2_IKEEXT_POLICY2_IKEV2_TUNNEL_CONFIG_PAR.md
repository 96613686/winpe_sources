# ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(IPSEC_TUNNEL_POLICY2_ *,IKEEXT_POLICY2_ *,_IKEV2_TUNNEL_CONFIG_PARAMS_4 *,int)

- ea: `0x18003da94`
- end: `0x18003ddf4`
- name: `?PopulateRDGlobalOrInterfacePolicy@ServerBFEHandler@@KAKPEAUIPSEC_TUNNEL_POLICY2_@@PEAUIKEEXT_POLICY2_@@PEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@H@Z`
- size: `864`
- prototype: `__int64 __fastcall(struct IPSEC_TUNNEL_POLICY2_ *, struct IKEEXT_POLICY2_ *, struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003a830`
- `0x18003ac84`

## callees

- `0x180007590`
- `0x180007794`
- `0x1800077bc`
- `0x18003afc0`
- `0x18003b2b4`
- `0x18003da94`
- `0x180068c60`
- `0x1800768d4`
- `0x180076b60`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003dd82`

## string_xrefs

- `0x18003dc02`: `PopulateRDGlobalOrInterfacePolicy: custom configuration is not specified. Using global MM and QM policy`

## pseudocode

```c
__int64 __fastcall ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy(
        struct IPSEC_TUNNEL_POLICY2_ *a1,
        struct IKEEXT_POLICY2_ *a2,
        struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *a3,
        int a4)
{
  int v8; // esi
  int v9; // r15d
  unsigned int v10; // eax
  struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *v11; // rax
  unsigned int v12; // eax
  unsigned int v13; // eax
  unsigned int v14; // ebx
  struct IPSEC_PROPOSAL0_ *v15; // rcx
  unsigned int v16; // ebx
  unsigned int v18; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v19; // [rsp+24h] [rbp-DCh] BYREF
  unsigned int v20; // [rsp+28h] [rbp-D8h] BYREF
  struct IPSEC_PROPOSAL0_ *v21; // [rsp+30h] [rbp-D0h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v23; // [rsp+40h] [rbp-C0h] BYREF
  __int128 v24; // [rsp+48h] [rbp-B8h]
  __int128 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+70h] [rbp-90h]
  int v28; // [rsp+74h] [rbp-8Ch]
  int v29; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v30[2044]; // [rsp+84h] [rbp-7Ch] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids);
  }
  v18 = 0;
  v19 = 0;
  v20 = 0;
  hMem = 0;
  v21 = 0;
  v29 = 0;
  memset_0(v30, 0, sizeof(v30));
  v24 = 0;
  v23 = 0;
  v25 = 0;
  v26 = 0;
  v27 = -1;
  v28 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v23,
      L"ServerBFEHandler::PopulateRDGlobalOrInterfacePolicy",
      &v18,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunction);
  *(_OWORD *)a2 = ServerBFEHandler::globalMMPolicyObject;
  *((_OWORD *)a2 + 1) = *(_OWORD *)byte_1800AAA98;
  *((_OWORD *)a2 + 2) = xmmword_1800AAAA8;
  *(_OWORD *)a1 = ServerBFEHandler::globalQMPolicyObject;
  *((_OWORD *)a1 + 1) = xmmword_1800AAAF0;
  *((_OWORD *)a1 + 2) = xmmword_1800AAB00;
  *((_OWORD *)a1 + 3) = xmmword_1800AAB10;
  *((_OWORD *)a1 + 4) = xmmword_1800AAB20;
  *((_OWORD *)a1 + 5) = *(_OWORD *)byte_1800AAB30;
  *((_OWORD *)a1 + 6) = xmmword_1800AAB40;
  if ( a3 )
  {
    v8 = 1800;
    v9 = 300;
    v10 = *((_DWORD *)a3 + 1);
    if ( v10 )
    {
      v8 = *((_DWORD *)a3 + 1);
      if ( v10 < 0x78 )
        v8 = 120;
    }
    if ( *(_DWORD *)a3 )
      v9 = *(_DWORD *)a3;
    if ( a4 && !*((_QWORD *)a3 + 7) )
    {
      v11 = (struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *)&ServerBFEHandler::serverConfigParams;
      if ( !ServerBFEHandler::serverCustomPolicyConfigured )
        v11 = a3;
      a3 = v11;
    }
    v12 = ServerBFEHandler::BuildIkeProposals(a3, &v19, (struct IKEEXT_PROPOSAL0_ **)&hMem);
    v18 = v12;
    if ( v12 )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v29) = 0;
        FormatRRASErrorString(&v29, L"BuildIkeProposals failed: %d", v12);
        if ( (byte_1800AA941 & 4) != 0 )
          McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v29);
      }
    }
    else
    {
      v13 = ServerBFEHandler::BuildIpsecProposals(a3, &v20, &v21, a4);
      v18 = v13;
      v14 = v20;
      if ( v13 )
      {
        if ( (byte_1800AA941 & 4) != 0 )
        {
          LOWORD(v29) = 0;
          FormatRRASErrorString(&v29, L"BuildIpsecProposals failed: %d", v13);
          if ( (byte_1800AA941 & 4) != 0 )
            McTemplateU0z_EventWriteTransfer(&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context, RasVpnIkeTraceError, &v29);
        }
        v15 = v21;
      }
      else
      {
        *((_DWORD *)a2 + 5) = v19;
        *((_QWORD *)a2 + 3) = hMem;
        hMem = 0;
        *((_DWORD *)a2 + 9) = 100;
        *((_DWORD *)a2 + 10) = v8;
        *((_QWORD *)a1 + 1) = v21;
        v15 = 0;
        *((_DWORD *)a1 + 1) = v14;
        *((_DWORD *)a1 + 22) = v9;
      }
      if ( v15 )
        FreeIpsecOffers(v15);
    }
    if ( hMem )
      LocalFree(hMem);
  }
  else if ( (byte_1800AA941 & 4) != 0 )
  {
    McTemplateU0z_EventWriteTransfer(
      &MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
      RasVpnIkeTraceError,
      L"PopulateRDGlobalOrInterfacePolicy: custom configuration is not specified. Using global MM and QM policy");
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids, v18);
  }
  v16 = v18;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v23);
  return v16;
}

```

## disassembly

```asm
0x18003da94  push    rbp
0x18003da96  push    rbx
0x18003da97  push    rsi
0x18003da98  push    rdi
0x18003da99  push    r12
0x18003da9b  push    r13
0x18003da9d  push    r14
0x18003da9f  push    r15
0x18003daa1  lea     rbp, [rsp-798h]
0x18003daa9  sub     rsp, 898h
0x18003dab0  mov     rax, cs:__security_cookie
0x18003dab7  xor     rax, rsp
0x18003daba  mov     [rbp+7D0h+var_50], rax
0x18003dac1  mov     r12d, r9d
0x18003dac4  mov     rbx, r8
0x18003dac7  mov     r14, rdx
0x18003daca  mov     rdi, rcx
0x18003dacd  lea     rax, WPP_GLOBAL_Control
0x18003dad4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dadb  cmp     rcx, rax
0x18003dade  jz      short loc_18003DB01
0x18003dae0  test    byte ptr [rcx+1Ch], 1
0x18003dae4  jz      short loc_18003DB01
0x18003dae6  cmp     byte ptr [rcx+19h], 6
0x18003daea  jb      short loc_18003DB01
0x18003daec  mov     edx, 35h ; '5'
0x18003daf1  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003daf8  mov     rcx, [rcx+10h]
0x18003dafc  call    WPP_SF_
0x18003db01  xor     r13d, r13d
0x18003db04  mov     [rsp+8D0h+var_8B0], r13d
0x18003db09  mov     [rsp+8D0h+var_8AC], r13d
0x18003db0e  mov     [rsp+8D0h+var_8A8], r13d
0x18003db13  mov     [rsp+8D0h+hMem], r13
0x18003db18  mov     [rsp+8D0h+var_8A0], r13
0x18003db1d  mov     [rbp+7D0h+var_850], r13d
0x18003db21  xor     edx, edx; Val
0x18003db23  mov     r8d, 7FCh; Size
0x18003db29  lea     rcx, [rbp+7D0h+var_84C]; void *
0x18003db2d  call    memset_0
0x18003db32  xorps   xmm0, xmm0
0x18003db35  movdqu  [rsp+8D0h+var_888], xmm0
0x18003db3b  mov     [rsp+8D0h+var_890], r13
0x18003db40  xorps   xmm1, xmm1
0x18003db43  movdqu  [rsp+8D0h+var_878], xmm1
0x18003db49  mov     [rsp+8D0h+var_868], r13
0x18003db4e  mov     [rsp+8D0h+var_860], 0FFFFFFFFh
0x18003db56  mov     [rsp+8D0h+var_85C], r13d
0x18003db5b  test    cs:byte_1800AA941, 8
0x18003db62  jz      short loc_18003DB81
0x18003db64  lea     r9, ?RasVpnIkeTraceFunction@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18003db6b  lea     r8, [rsp+8D0h+var_8B0]; unsigned int *
0x18003db70  lea     rdx, aServerbfehandl_1; "ServerBFEHandler::PopulateRDGlobalOrInt"...
0x18003db77  lea     rcx, [rsp+8D0h+var_890]; this
0x18003db7c  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong))
0x18003db81  movups  xmm0, xmmword ptr cs:?globalMMPolicyObject@ServerBFEHandler@@1UIKEEXT_POLICY2_@@A; IKEEXT_POLICY2_ ServerBFEHandler::globalMMPolicyObject
0x18003db88  movups  xmmword ptr [r14], xmm0
0x18003db8c  movups  xmm1, xmmword ptr cs:byte_1800AAA98
0x18003db93  movups  xmmword ptr [r14+10h], xmm1
0x18003db98  movups  xmm0, cs:xmmword_1800AAAA8
0x18003db9f  movups  xmmword ptr [r14+20h], xmm0
0x18003dba4  movaps  xmm1, cs:?globalQMPolicyObject@ServerBFEHandler@@1UIPSEC_TUNNEL_POLICY2_@@A; IPSEC_TUNNEL_POLICY2_ ServerBFEHandler::globalQMPolicyObject
0x18003dbab  movaps  xmmword ptr [rdi], xmm1
0x18003dbae  movaps  xmm0, cs:xmmword_1800AAAF0
0x18003dbb5  movaps  xmmword ptr [rdi+10h], xmm0
0x18003dbb9  movaps  xmm1, cs:xmmword_1800AAB00
0x18003dbc0  movaps  xmmword ptr [rdi+20h], xmm1
0x18003dbc4  movaps  xmm0, cs:xmmword_1800AAB10
0x18003dbcb  movaps  xmmword ptr [rdi+30h], xmm0
0x18003dbcf  movaps  xmm1, cs:xmmword_1800AAB20
0x18003dbd6  movaps  xmmword ptr [rdi+40h], xmm1
0x18003dbda  movaps  xmm0, xmmword ptr cs:byte_1800AAB30
0x18003dbe1  movaps  xmmword ptr [rdi+50h], xmm0
0x18003dbe5  movaps  xmm1, cs:xmmword_1800AAB40
0x18003dbec  movaps  xmmword ptr [rdi+60h], xmm1
0x18003dbf0  test    rbx, rbx
0x18003dbf3  jnz     short loc_18003DC21
0x18003dbf5  test    cs:byte_1800AA941, 4
0x18003dbfc  jz      loc_18003DD88
0x18003dc02  lea     r8, aPopulaterdglob; "PopulateRDGlobalOrInterfacePolicy: cust"...
0x18003dc09  lea     rdx, RasVpnIkeTraceError
0x18003dc10  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dc17  call    McTemplateU0z_EventWriteTransfer
0x18003dc1c  jmp     loc_18003DD88
0x18003dc21  mov     esi, 708h
0x18003dc26  mov     r15d, 12Ch
0x18003dc2c  mov     eax, [rbx+4]
0x18003dc2f  test    eax, eax
0x18003dc31  jz      short loc_18003DC3F
0x18003dc33  mov     esi, eax
0x18003dc35  mov     ecx, 78h ; 'x'
0x18003dc3a  cmp     eax, ecx
0x18003dc3c  cmovb   esi, ecx
0x18003dc3f  cmp     [rbx], r13d
0x18003dc42  cmova   r15d, [rbx]
0x18003dc46  test    r12d, r12d
0x18003dc49  jz      short loc_18003DC66
0x18003dc4b  cmp     [rbx+38h], r13
0x18003dc4f  jnz     short loc_18003DC66
0x18003dc51  lea     rax, ?serverConfigParams@ServerBFEHandler@@1U_IKEV2_TUNNEL_CONFIG_PARAMS_4@@A; _IKEV2_TUNNEL_CONFIG_PARAMS_4 ServerBFEHandler::serverConfigParams
0x18003dc58  cmp     cs:?serverCustomPolicyConfigured@ServerBFEHandler@@1HA, r13d; int ServerBFEHandler::serverCustomPolicyConfigured
0x18003dc5f  cmovz   rax, rbx
0x18003dc63  mov     rbx, rax
0x18003dc66  lea     r8, [rsp+8D0h+hMem]; struct IKEEXT_PROPOSAL0_ **
0x18003dc6b  lea     rdx, [rsp+8D0h+var_8AC]; unsigned int *
0x18003dc70  mov     rcx, rbx; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18003dc73  call    ?BuildIkeProposals@ServerBFEHandler@@KAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@PEAKPEAPEAUIKEEXT_PROPOSAL0_@@@Z; ServerBFEHandler::BuildIkeProposals(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *,ulong *,IKEEXT_PROPOSAL0_ * *)
0x18003dc78  mov     r8d, eax
0x18003dc7b  mov     [rsp+8D0h+var_8B0], eax
0x18003dc7f  test    eax, eax
0x18003dc81  jz      short loc_18003DCCE
0x18003dc83  test    cs:byte_1800AA941, 4
0x18003dc8a  jz      loc_18003DD78
0x18003dc90  mov     word ptr [rbp+7D0h+var_850], r13w
0x18003dc95  lea     rdx, aBuildikepropos; "BuildIkeProposals failed: %d"
0x18003dc9c  lea     rcx, [rbp+7D0h+var_850]
0x18003dca0  call    FormatRRASErrorString
0x18003dca5  test    cs:byte_1800AA941, 4
0x18003dcac  jz      loc_18003DD78
0x18003dcb2  lea     r8, [rbp+7D0h+var_850]
0x18003dcb6  lea     rdx, RasVpnIkeTraceError
0x18003dcbd  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dcc4  call    McTemplateU0z_EventWriteTransfer
0x18003dcc9  jmp     loc_18003DD78
0x18003dcce  mov     r9d, r12d; int
0x18003dcd1  lea     r8, [rsp+8D0h+var_8A0]; struct IPSEC_PROPOSAL0_ **
0x18003dcd6  lea     rdx, [rsp+8D0h+var_8A8]; unsigned int *
0x18003dcdb  mov     rcx, rbx; struct _IKEV2_TUNNEL_CONFIG_PARAMS_4 *
0x18003dcde  call    ?BuildIpsecProposals@ServerBFEHandler@@KAKPEAU_IKEV2_TUNNEL_CONFIG_PARAMS_4@@PEAKPEAPEAUIPSEC_PROPOSAL0_@@H@Z; ServerBFEHandler::BuildIpsecProposals(_IKEV2_TUNNEL_CONFIG_PARAMS_4 *,ulong *,IPSEC_PROPOSAL0_ * *,int)
0x18003dce3  mov     r8d, eax
0x18003dce6  mov     [rsp+8D0h+var_8B0], eax
0x18003dcea  mov     ebx, [rsp+8D0h+var_8A8]
0x18003dcee  test    eax, eax
0x18003dcf0  jz      short loc_18003DD37
0x18003dcf2  test    cs:byte_1800AA941, 4
0x18003dcf9  jz      short loc_18003DD30
0x18003dcfb  mov     word ptr [rbp+7D0h+var_850], r13w
0x18003dd00  lea     rdx, aBuildipsecprop; "BuildIpsecProposals failed: %d"
0x18003dd07  lea     rcx, [rbp+7D0h+var_850]
0x18003dd0b  call    FormatRRASErrorString
0x18003dd10  test    cs:byte_1800AA941, 4
0x18003dd17  jz      short loc_18003DD30
0x18003dd19  lea     r8, [rbp+7D0h+var_850]
0x18003dd1d  lea     rdx, RasVpnIkeTraceError
0x18003dd24  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18003dd2b  call    McTemplateU0z_EventWriteTransfer
0x18003dd30  mov     rcx, [rsp+8D0h+var_8A0]
0x18003dd35  jmp     short loc_18003DD6C
0x18003dd37  mov     eax, [rsp+8D0h+var_8AC]
0x18003dd3b  mov     [r14+14h], eax
0x18003dd3f  mov     rax, [rsp+8D0h+hMem]
0x18003dd44  mov     [r14+18h], rax
0x18003dd48  mov     [rsp+8D0h+hMem], r13
0x18003dd4d  mov     dword ptr [r14+24h], 64h ; 'd'
0x18003dd55  mov     [r14+28h], esi
0x18003dd59  mov     rax, [rsp+8D0h+var_8A0]
0x18003dd5e  mov     [rdi+8], rax
0x18003dd62  mov     rcx, r13; hMem
0x18003dd65  mov     [rdi+4], ebx
0x18003dd68  mov     [rdi+58h], r15d
0x18003dd6c  test    rcx, rcx
0x18003dd6f  jz      short loc_18003DD78
0x18003dd71  mov     edx, ebx
0x18003dd73  call    FreeIpsecOffers
0x18003dd78  mov     rcx, [rsp+8D0h+hMem]; hMem
0x18003dd7d  test    rcx, rcx
0x18003dd80  jz      short loc_18003DD88
0x18003dd82  call    cs:__imp_LocalFree
0x18003dd88  mov     rcx, cs:WPP_GLOBAL_Control
0x18003dd8f  lea     rax, WPP_GLOBAL_Control
0x18003dd96  cmp     rcx, rax
0x18003dd99  jz      short loc_18003DDC1
0x18003dd9b  test    byte ptr [rcx+1Ch], 1
0x18003dd9f  jz      short loc_18003DDC1
0x18003dda1  cmp     byte ptr [rcx+19h], 6
0x18003dda5  jb      short loc_18003DDC1
0x18003dda7  mov     edx, 36h ; '6'
0x18003ddac  mov     r9d, [rsp+8D0h+var_8B0]
0x18003ddb1  lea     r8, WPP_c10b5fac593a3d45d1c9ab0c5414ff55_Traceguids
0x18003ddb8  mov     rcx, [rcx+10h]
0x18003ddbc  call    WPP_SF_d
0x18003ddc1  mov     ebx, [rsp+8D0h+var_8B0]
0x18003ddc5  lea     rcx, [rsp+8D0h+var_890]; this
0x18003ddca  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18003ddcf  mov     eax, ebx
0x18003ddd1  mov     rcx, [rbp+7D0h+var_50]
0x18003ddd8  xor     rcx, rsp; StackCookie
0x18003dddb  call    __security_check_cookie
0x18003dde0  add     rsp, 898h
0x18003dde7  pop     r15
0x18003dde9  pop     r14
0x18003ddeb  pop     r13
0x18003dded  pop     r12
0x18003ddef  pop     rdi
0x18003ddf0  pop     rsi
0x18003ddf1  pop     rbx
0x18003ddf2  pop     rbp
0x18003ddf3  retn
```
