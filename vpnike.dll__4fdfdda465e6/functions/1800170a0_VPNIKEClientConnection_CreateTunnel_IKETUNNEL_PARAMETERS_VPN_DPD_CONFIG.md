# VPNIKEClientConnection::CreateTunnel(_IKETUNNEL_PARAMETERS_ &,_VPN_DPD_CONFIG_ *)

- ea: `0x1800170a0`
- end: `0x180017711`
- name: `?CreateTunnel@VPNIKEClientConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@PEAU_VPN_DPD_CONFIG_@@@Z`
- size: `1649`
- prototype: `__int64 __fastcall(void **this, struct _IKETUNNEL_PARAMETERS_ *, struct _VPN_DPD_CONFIG_ *)`
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, installer_update, broker_com_uri`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000d620`
- `0x18000e3b8`
- `0x18000f1b4`
- `0x1800135b0`
- `0x1800170a0`
- `0x180018a04`
- `0x18001a5f0`
- `0x18001f10c`
- `0x18005c804`
- `0x180075a3c`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x180076ccc`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rtutils!RouterLogEventA` at `0x18001769b`
- `rtutils!RouterLogEventA` at `0x18001769b`

## string_xrefs

- `0x1800171df`: `VPNIKEClientConnection::CreateTunnel`
- `0x180017286`: `VPNIKEClientConnection::CreateTunnel failed.`
- `0x1800172fc`: `VPNIKEConnection::UpdateRoutes failed: %d`

## pseudocode

```c
__int64 __fastcall VPNIKEClientConnection::CreateTunnel(
        void **this,
        struct _IKETUNNEL_PARAMETERS_ *a2,
        struct _VPN_DPD_CONFIG_ *a3)
{
  unsigned int v6; // esi
  _DWORD *v7; // rax
  void *v8; // rdx
  __int128 *v9; // r9
  _DWORD *v10; // rax
  void *v11; // rdx
  __int128 *v12; // r9
  void (__fastcall *v13)(_QWORD, __int64, unsigned int *); // rbx
  unsigned int *MobikeTimeOut; // rax
  char *v15; // rcx
  _QWORD *v16; // rcx
  __int64 v17; // rax
  _QWORD *v18; // rax
  __int64 v19; // rdx
  void *v20; // rdx
  __int128 *v21; // r9
  __int64 v22; // rdx
  _DWORD *v23; // rax
  void *v24; // rdx
  __int128 *v25; // r9
  unsigned int v26; // ebx
  unsigned int Tunnel; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v29; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v30; // [rsp+48h] [rbp-B8h] BYREF
  __int128 v31; // [rsp+50h] [rbp-B0h]
  __int128 v32; // [rsp+60h] [rbp-A0h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  int v34; // [rsp+78h] [rbp-88h]
  int v35; // [rsp+7Ch] [rbp-84h]
  __int128 v36; // [rsp+80h] [rbp-80h] BYREF
  _BYTE v37[184]; // [rsp+90h] [rbp-70h] BYREF
  char v38[40]; // [rsp+148h] [rbp+48h] BYREF
  LPSTR plpszSubStringArray[2]; // [rsp+170h] [rbp+70h] BYREF
  char *p_pszDest; // [rsp+180h] [rbp+80h]
  int v41; // [rsp+188h] [rbp+88h] BYREF
  __int128 v42; // [rsp+18Ch] [rbp+8Ch]
  __int128 v43; // [rsp+19Ch] [rbp+9Ch]
  int v44; // [rsp+1ACh] [rbp+ACh]
  char pszDest; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v46; // [rsp+1B1h] [rbp+B1h]
  _BYTE v47[23]; // [rsp+1C1h] [rbp+C1h] BYREF
  _OWORD v48[3]; // [rsp+1E0h] [rbp+E0h] BYREF
  _BYTE v49[30]; // [rsp+210h] [rbp+110h]
  __int16 v50; // [rsp+22Eh] [rbp+12Eh]
  int v51; // [rsp+230h] [rbp+130h] BYREF
  char v52[2044]; // [rsp+234h] [rbp+134h] BYREF

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 54, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
  Tunnel = 0;
  v48[0] = *(_OWORD *)L"{00000000-0000-0000-0000-000000000000}";
  v48[1] = *(_OWORD *)L"0-0000-0000-0000-000000000000}";
  v48[2] = *(_OWORD *)L"000-0000-000000000000}";
  *(_OWORD *)v49 = *(_OWORD *)L"-000000000000}";
  *(_OWORD *)&v49[14] = *(_OWORD *)L"000000}";
  v50 = 0;
  v51 = 0;
  memset_0(v52, 0, sizeof(v52));
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v36 = 0;
  v31 = 0;
  v30 = 0;
  v32 = 0;
  v33 = 0;
  v6 = -1;
  v34 = -1;
  v35 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v30,
      L"VPNIKEClientConnection::CreateTunnel",
      &Tunnel,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      this[14]);
  Tunnel = VPNIKEConnection::CreateTunnel((VPNIKEConnection *)this, a2, a3);
  if ( Tunnel )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v41) = 0;
      v7 = this[14];
      if ( v7 && *((_QWORD *)v7 + 2) )
        v6 = v7[4];
      ConvertPortNoToString(&v41, v6);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v8 = this[14];
        LODWORD(v9) = (_DWORD)v8 + 2120;
        if ( !v8 )
          v9 = &v36;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"VPNIKEClientConnection::CreateTunnel failed.",
          (_DWORD)v9,
          ((unsigned __int64)v8 + 2686) & -(__int64)(v8 != 0),
          (__int64)&v41);
      }
    }
  }
  else
  {
    Tunnel = VPNIKEConnection::UpdateRoutes((VPNIKEConnection *)this);
    if ( Tunnel )
    {
      if ( (byte_1800AA941 & 4) != 0 )
      {
        LOWORD(v51) = 0;
        LOWORD(v41) = 0;
        v10 = this[14];
        if ( v10 && *((_QWORD *)v10 + 2) )
          v6 = v10[4];
        ConvertPortNoToString(&v41, v6);
        FormatRRASErrorString(&v51, L"VPNIKEConnection::UpdateRoutes failed: %d", Tunnel);
        if ( (byte_1800AA941 & 4) != 0 )
        {
          v11 = this[14];
          LODWORD(v12) = (_DWORD)v11 + 2120;
          if ( !v11 )
            v12 = &v36;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceError,
            (unsigned int)&v51,
            (_DWORD)v12,
            ((unsigned __int64)v11 + 2686) & -(__int64)(v11 != 0),
            (__int64)&v41);
        }
      }
    }
    else
    {
      memset_0(v37, 0, 0xE0u);
      VPNIKEConnection::GetProjectionResult((VPNIKEConnection *)this, (struct _PROTOCOL_PROJECTION_RESULT *)v37);
      VPNIKEConnection::PopulateTrafficSelectorSubnets((VPNIKEConnection *)this, (struct _TS_SUBNETS *)v38);
      VPNIKEProtocolEngine::NotifyCaller(this[3], 4, v37);
      (*((void (__fastcall **)(_QWORD, __int64, _BYTE *, __int64))&xmmword_1800AA980 + 1))(
        *((_QWORD *)this[14] + 3),
        1,
        v37,
        224);
      VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x10000u);
      v13 = (void (__fastcall *)(_QWORD, __int64, unsigned int *))*((_QWORD *)&xmmword_1800AA980 + 1);
      MobikeTimeOut = VPNIKEClientConnection::GetMobikeTimeOut((VPNIKEClientConnection *)this);
      v13(*((_QWORD *)this[14] + 3), 12, MobikeTimeOut);
      v15 = (char *)this[14];
      if ( *((_DWORD *)v15 + 368) == 2 )
      {
        v16 = v15 + 2120;
        if ( v16 )
        {
          v17 = *v16 - *(_QWORD *)&GUID_NULL.Data1;
          if ( *v16 == *(_QWORD *)&GUID_NULL.Data1 )
            v17 = v16[1] - *(_QWORD *)GUID_NULL.Data4;
          if ( v17 )
          {
            Tunnel = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)this[16] + 8LL))(this[16]);
            if ( Tunnel )
            {
              if ( (byte_1800AA941 & 4) != 0 )
              {
                LOWORD(v51) = 0;
                LOWORD(v41) = 0;
                v18 = this[14];
                if ( v18 && v18[2] )
                  v19 = *((unsigned int *)v18 + 4);
                else
                  v19 = 0xFFFFFFFFLL;
                ConvertPortNoToString(&v41, v19);
                FormatRRASErrorString(&v51, L"StartAccounting failed with error: %d", Tunnel);
                if ( (byte_1800AA941 & 4) != 0 )
                {
                  v20 = this[14];
                  LODWORD(v21) = (_DWORD)v20 + 2120;
                  if ( !v20 )
                    v21 = &v36;
                  McTemplateU0zjzz_EventWriteTransfer(
                    (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
                    (unsigned int)RasVpnIkeParamTraceError,
                    (unsigned int)&v51,
                    (_DWORD)v21,
                    ((unsigned __int64)v20 + 2686) & -(__int64)(v20 != 0),
                    (__int64)&v41);
                }
              }
              Tunnel = 0;
            }
            else
            {
              VPNIKEClientConnection::UpdateConnectionState((VPNIKEClientConnection *)this, 0x80000u);
            }
          }
        }
      }
      pszDest = 0;
      v46 = 0;
      memset(v47, 0, sizeof(v47));
      *(_OWORD *)plpszSubStringArray = 0;
      p_pszDest = 0;
      v29 = *(_OWORD *)((char *)a2 + 56);
      PrintGuid(&pszDest);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        LOWORD(v51) = 0;
        LOWORD(v41) = 0;
        v23 = this[14];
        if ( v23 && *((_QWORD *)v23 + 2) )
          v6 = v23[4];
        ConvertPortNoToString(&v41, v6);
        FormatRRASErrorString(&v51, L"ServerCoID=%S : ClientCoID=%S", &pszDest, (char *)this[14] + 360);
        if ( (byte_1800AA941 & 8) != 0 )
        {
          v24 = this[14];
          LODWORD(v25) = (_DWORD)v24 + 2120;
          if ( !v24 )
            v25 = &v36;
          McTemplateU0zjzz_EventWriteTransfer(
            (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
            (unsigned int)RasVpnIkeParamTraceInfo,
            (unsigned int)&v51,
            (_DWORD)v25,
            ((unsigned __int64)v24 + 2686) & -(__int64)(v24 != 0),
            (__int64)&v41);
        }
      }
      v29 = *(_OWORD *)((char *)this[14] + 2120);
      MprConvertGuidToString(&v29, v22, v48);
      plpszSubStringArray[0] = (LPSTR)v48;
      plpszSubStringArray[1] = (char *)this[14] + 360;
      p_pszDest = &pszDest;
      RouterLogEventA(*((HANDLE *)VpnIkeProtocolEngine + 2), 4u, 0x4F38u, 3u, plpszSubStringArray, 0);
      VPNIKEClientConnection::NotifyDone((VPNIKEClientConnection *)this);
    }
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 55, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, Tunnel);
  }
  v26 = Tunnel;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v30);
  return v26;
}

```

## disassembly

```asm
0x1800170a0  mov     [rsp-8+arg_18], rbx
0x1800170a5  push    rbp
0x1800170a6  push    rsi
0x1800170a7  push    rdi
0x1800170a8  push    r13
0x1800170aa  push    r14
0x1800170ac  lea     rbp, [rsp-940h]
0x1800170b4  sub     rsp, 0A40h
0x1800170bb  mov     rax, cs:__security_cookie
0x1800170c2  xor     rax, rsp
0x1800170c5  mov     [rbp+960h+var_30], rax
0x1800170cc  mov     rbx, r8
0x1800170cf  mov     r14, rdx
0x1800170d2  mov     rdi, rcx
0x1800170d5  lea     r13, WPP_GLOBAL_Control
0x1800170dc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800170e3  cmp     rcx, r13
0x1800170e6  jz      short loc_180017109
0x1800170e8  test    byte ptr [rcx+1Ch], 1
0x1800170ec  jz      short loc_180017109
0x1800170ee  cmp     byte ptr [rcx+19h], 6
0x1800170f2  jb      short loc_180017109
0x1800170f4  mov     edx, 36h ; '6'
0x1800170f9  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x180017100  mov     rcx, [rcx+10h]
0x180017104  call    WPP_SF_
0x180017109  mov     [rsp+0A60h+var_A30], 0
0x180017111  movaps  xmm0, xmmword ptr cs:a00000000000000; "{00000000-0000-0000-0000-000000000000}"
0x180017118  movaps  [rbp+960h+var_880], xmm0
0x18001711f  movaps  xmm1, xmmword ptr cs:a00000000000000+10h; "0-0000-0000-0000-000000000000}"
0x180017126  movaps  [rbp+960h+var_870], xmm1
0x18001712d  movaps  xmm0, xmmword ptr cs:a00000000000000+20h; "000-0000-000000000000}"
0x180017134  movaps  [rbp+960h+var_860], xmm0
0x18001713b  movaps  xmm1, xmmword ptr cs:a00000000000000+30h; "-000000000000}"
0x180017142  movaps  xmmword ptr [rbp+960h+var_850], xmm1
0x180017149  movups  xmm0, xmmword ptr cs:a00000000000000+3Eh; "000000}"
0x180017150  movups  xmmword ptr [rbp+960h+var_850+0Eh], xmm0
0x180017157  xor     eax, eax
0x180017159  mov     [rbp+960h+var_832], ax
0x180017160  mov     [rbp+960h+var_830], eax
0x180017166  xor     edx, edx; Val
0x180017168  mov     r8d, 7FCh; Size
0x18001716e  lea     rcx, [rbp+960h+var_82C]; void *
0x180017175  call    memset_0
0x18001717a  xor     eax, eax
0x18001717c  mov     [rbp+960h+var_8D8], eax
0x180017182  xorps   xmm0, xmm0
0x180017185  movups  [rbp+960h+var_8D4], xmm0
0x18001718c  movups  [rbp+960h+var_8C4], xmm0
0x180017193  mov     [rbp+960h+var_8B4], eax
0x180017199  movups  [rbp+960h+var_9E0], xmm0
0x18001719d  xorps   xmm1, xmm1
0x1800171a0  movdqu  [rsp+0A60h+var_A10], xmm1
0x1800171a6  mov     [rsp+0A60h+var_A18], rax
0x1800171ab  movdqu  [rsp+0A60h+var_A00], xmm0
0x1800171b1  mov     [rsp+0A60h+var_9F0], rax
0x1800171b6  or      esi, 0FFFFFFFFh
0x1800171b9  mov     [rsp+0A60h+var_9E8], esi
0x1800171bd  mov     [rsp+0A60h+var_9E4], eax
0x1800171c1  test    cs:byte_1800AA941, 8
0x1800171c8  jz      short loc_1800171F0
0x1800171ca  mov     rax, [rdi+70h]
0x1800171ce  mov     [rsp+0A60h+plpszSubStringArray], rax; void *
0x1800171d3  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x1800171da  lea     r8, [rsp+0A60h+var_A30]; unsigned int *
0x1800171df  lea     rdx, aVpnikeclientco_9; "VPNIKEClientConnection::CreateTunnel"
0x1800171e6  lea     rcx, [rsp+0A60h+var_A18]; this
0x1800171eb  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x1800171f0  mov     r8, rbx; struct _VPN_DPD_CONFIG_ *
0x1800171f3  mov     rdx, r14; struct _IKETUNNEL_PARAMETERS_ *
0x1800171f6  mov     rcx, rdi; this
0x1800171f9  call    ?CreateTunnel@VPNIKEConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@PEAU_VPN_DPD_CONFIG_@@@Z; VPNIKEConnection::CreateTunnel(_IKETUNNEL_PARAMETERS_ &,_VPN_DPD_CONFIG_ *)
0x1800171fe  mov     [rsp+0A60h+var_A30], eax
0x180017202  test    eax, eax
0x180017204  jz      loc_1800172A5
0x18001720a  test    cs:byte_1800AA941, 4
0x180017211  jz      loc_1800176A9
0x180017217  xor     eax, eax
0x180017219  mov     word ptr [rbp+960h+var_8D8], ax
0x180017220  mov     rax, [rdi+70h]
0x180017224  test    rax, rax
0x180017227  jz      short loc_180017233
0x180017229  cmp     qword ptr [rax+10h], 0
0x18001722e  jz      short loc_180017233
0x180017230  mov     esi, [rax+10h]
0x180017233  mov     edx, esi
0x180017235  lea     rcx, [rbp+960h+var_8D8]
0x18001723c  call    ConvertPortNoToString
0x180017241  test    cs:byte_1800AA941, 4
0x180017248  jz      loc_1800176A9
0x18001724e  mov     rdx, [rdi+70h]
0x180017252  mov     rax, rdx
0x180017255  lea     rcx, [rdx+0A7Eh]
0x18001725c  neg     rax
0x18001725f  sbb     r8, r8
0x180017262  and     r8, rcx
0x180017265  test    rdx, rdx
0x180017268  lea     r9, [rdx+848h]
0x18001726f  jnz     short loc_180017275
0x180017271  lea     r9, [rbp+960h+var_9E0]
0x180017275  lea     rax, [rbp+960h+var_8D8]
0x18001727c  mov     qword ptr [rsp+0A60h+dwErrorCode], rax
0x180017281  mov     [rsp+0A60h+plpszSubStringArray], r8
0x180017286  lea     r8, aVpnikeclientco_7; "VPNIKEClientConnection::CreateTunnel fa"...
0x18001728d  lea     rdx, RasVpnIkeParamTraceError
0x180017294  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001729b  call    McTemplateU0zjzz_EventWriteTransfer
0x1800172a0  jmp     loc_1800176A9
0x1800172a5  mov     rcx, rdi; this
0x1800172a8  call    ?UpdateRoutes@VPNIKEConnection@@IEAAKXZ; VPNIKEConnection::UpdateRoutes(void)
0x1800172ad  mov     [rsp+0A60h+var_A30], eax
0x1800172b1  test    eax, eax
0x1800172b3  jz      loc_180017360
0x1800172b9  test    cs:byte_1800AA941, 4
0x1800172c0  jz      loc_1800176A9
0x1800172c6  xor     eax, eax
0x1800172c8  mov     word ptr [rbp+960h+var_830], ax
0x1800172cf  mov     word ptr [rbp+960h+var_8D8], ax
0x1800172d6  mov     rax, [rdi+70h]
0x1800172da  test    rax, rax
0x1800172dd  jz      short loc_1800172E9
0x1800172df  cmp     qword ptr [rax+10h], 0
0x1800172e4  jz      short loc_1800172E9
0x1800172e6  mov     esi, [rax+10h]
0x1800172e9  mov     edx, esi
0x1800172eb  lea     rcx, [rbp+960h+var_8D8]
0x1800172f2  call    ConvertPortNoToString
0x1800172f7  mov     r8d, [rsp+0A60h+var_A30]
0x1800172fc  lea     rdx, aVpnikeconnecti_5; "VPNIKEConnection::UpdateRoutes failed: "...
0x180017303  lea     rcx, [rbp+960h+var_830]
0x18001730a  call    FormatRRASErrorString
0x18001730f  test    cs:byte_1800AA941, 4
0x180017316  jz      loc_1800176A9
0x18001731c  mov     rdx, [rdi+70h]
0x180017320  mov     rax, rdx
0x180017323  lea     rcx, [rdx+0A7Eh]
0x18001732a  neg     rax
0x18001732d  sbb     r8, r8
0x180017330  and     r8, rcx
0x180017333  test    rdx, rdx
0x180017336  lea     r9, [rdx+848h]
0x18001733d  jnz     short loc_180017343
0x18001733f  lea     r9, [rbp+960h+var_9E0]
0x180017343  lea     rax, [rbp+960h+var_8D8]
0x18001734a  mov     qword ptr [rsp+0A60h+dwErrorCode], rax
0x18001734f  mov     [rsp+0A60h+plpszSubStringArray], r8
0x180017354  lea     r8, [rbp+960h+var_830]
0x18001735b  jmp     loc_18001728D
0x180017360  mov     ebx, 0E0h
0x180017365  mov     r8d, ebx; Size
0x180017368  xor     edx, edx; Val
0x18001736a  lea     rcx, [rbp+960h+var_9D0]; void *
0x18001736e  call    memset_0
0x180017373  lea     rdx, [rbp+960h+var_9D0]; struct _PROTOCOL_PROJECTION_RESULT *
0x180017377  mov     rcx, rdi; this
0x18001737a  call    ?GetProjectionResult@VPNIKEConnection@@IEAAXAEAU_PROTOCOL_PROJECTION_RESULT@@@Z; VPNIKEConnection::GetProjectionResult(_PROTOCOL_PROJECTION_RESULT &)
0x18001737f  lea     rdx, [rbp+960h+var_918]; struct _TS_SUBNETS *
0x180017383  mov     rcx, rdi; this
0x180017386  call    ?PopulateTrafficSelectorSubnets@VPNIKEConnection@@IEAAXAEAU_TS_SUBNETS@@@Z; VPNIKEConnection::PopulateTrafficSelectorSubnets(_TS_SUBNETS &)
0x18001738b  lea     r8, [rbp+960h+var_9D0]
0x18001738f  mov     edx, 4
0x180017394  mov     rcx, [rdi+18h]
0x180017398  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x18001739d  mov     rcx, [rdi+70h]
0x1800173a1  mov     r9d, ebx
0x1800173a4  lea     r8, [rbp+960h+var_9D0]
0x1800173a8  mov     edx, 1
0x1800173ad  mov     rcx, [rcx+18h]
0x1800173b1  mov     rax, qword ptr cs:xmmword_1800AA980+8
0x1800173b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173bd  mov     edx, 10000h; unsigned int
0x1800173c2  mov     rcx, rdi; this
0x1800173c5  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x1800173ca  mov     rbx, qword ptr cs:xmmword_1800AA980+8
0x1800173d1  mov     rcx, rdi; this
0x1800173d4  call    ?GetMobikeTimeOut@VPNIKEClientConnection@@IEAAAEAKXZ; VPNIKEClientConnection::GetMobikeTimeOut(void)
0x1800173d9  mov     rcx, [rdi+70h]
0x1800173dd  mov     r9d, 4
0x1800173e3  mov     r8, rax
0x1800173e6  lea     edx, [r9+8]
0x1800173ea  mov     rcx, [rcx+18h]
0x1800173ee  mov     rax, rbx
0x1800173f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800173f6  mov     rcx, [rdi+70h]
0x1800173fa  cmp     dword ptr [rcx+5C0h], 2
0x180017401  jnz     loc_18001751C
0x180017407  add     rcx, 848h
0x18001740e  jz      loc_18001751C
0x180017414  mov     rax, [rcx]
0x180017417  sub     rax, qword ptr cs:GUID_NULL.Data1
0x18001741e  jnz     short loc_18001742B
0x180017420  mov     rax, [rcx+8]
0x180017424  sub     rax, qword ptr cs:GUID_NULL.Data4
0x18001742b  test    rax, rax
0x18001742e  jz      loc_18001751C
0x180017434  mov     rcx, [rdi+80h]
0x18001743b  mov     rax, [rcx]
0x18001743e  mov     rax, [rax+8]
0x180017442  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017447  mov     [rsp+0A60h+var_A30], eax
0x18001744b  test    eax, eax
0x18001744d  jnz     short loc_180017461
0x18001744f  mov     edx, 80000h; unsigned int
0x180017454  mov     rcx, rdi; this
0x180017457  call    ?UpdateConnectionState@VPNIKEClientConnection@@IEAAXK@Z; VPNIKEClientConnection::UpdateConnectionState(ulong)
0x18001745c  jmp     loc_18001751C
0x180017461  test    cs:byte_1800AA941, 4
0x180017468  jz      loc_180017514
0x18001746e  xor     eax, eax
0x180017470  mov     word ptr [rbp+960h+var_830], ax
0x180017477  mov     word ptr [rbp+960h+var_8D8], ax
0x18001747e  mov     rax, [rdi+70h]
0x180017482  test    rax, rax
0x180017485  jz      short loc_180017493
0x180017487  cmp     qword ptr [rax+10h], 0
0x18001748c  jz      short loc_180017493
0x18001748e  mov     edx, [rax+10h]
0x180017491  jmp     short loc_180017495
0x180017493  mov     edx, esi
0x180017495  lea     rcx, [rbp+960h+var_8D8]
0x18001749c  call    ConvertPortNoToString
0x1800174a1  mov     r8d, [rsp+0A60h+var_A30]
0x1800174a6  lea     rdx, aStartaccountin; "StartAccounting failed with error: %d"
0x1800174ad  lea     rcx, [rbp+960h+var_830]
0x1800174b4  call    FormatRRASErrorString
0x1800174b9  test    cs:byte_1800AA941, 4
0x1800174c0  jz      short loc_180017514
0x1800174c2  mov     rdx, [rdi+70h]
0x1800174c6  mov     rax, rdx
0x1800174c9  lea     rcx, [rdx+0A7Eh]
0x1800174d0  neg     rax
0x1800174d3  sbb     r8, r8
0x1800174d6  and     r8, rcx
0x1800174d9  test    rdx, rdx
0x1800174dc  lea     r9, [rdx+848h]
0x1800174e3  jnz     short loc_1800174E9
0x1800174e5  lea     r9, [rbp+960h+var_9E0]
0x1800174e9  lea     rax, [rbp+960h+var_8D8]
0x1800174f0  mov     qword ptr [rsp+0A60h+dwErrorCode], rax
0x1800174f5  mov     [rsp+0A60h+plpszSubStringArray], r8
0x1800174fa  lea     r8, [rbp+960h+var_830]
0x180017501  lea     rdx, RasVpnIkeParamTraceError
0x180017508  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001750f  call    McTemplateU0zjzz_EventWriteTransfer
0x180017514  mov     [rsp+0A60h+var_A30], 0
0x18001751c  mov     [rbp+960h+pszDest], 0
0x180017523  xorps   xmm0, xmm0
0x180017526  xor     eax, eax
0x180017528  movups  [rbp+960h+var_8AF], xmm0
0x18001752f  movups  xmmword ptr [rbp+960h+var_89F], xmm0
0x180017536  mov     qword ptr [rbp+960h+var_89F+0Fh], rax
0x18001753d  movups  xmmword ptr [rbp+960h+var_8F0], xmm0
0x180017541  mov     [rbp+960h+var_8E0], rax
0x180017548  mov     rax, [r14+38h]
0x18001754c  mov     qword ptr [rsp+0A60h+var_A28], rax
0x180017551  mov     rax, [r14+40h]
0x180017555  mov     qword ptr [rsp+0A60h+var_A28+8], rax
0x18001755a  lea     r8, [rsp+0A60h+var_A28]
0x18001755f  lea     rcx, [rbp+960h+pszDest]; pszDest
0x180017566  call    PrintGuid
0x18001756b  mov     ebx, 168h
0x180017570  test    cs:byte_1800AA941, 8
0x180017577  jz      loc_18001762A
0x18001757d  xor     eax, eax
0x18001757f  mov     word ptr [rbp+960h+var_830], ax
0x180017586  mov     word ptr [rbp+960h+var_8D8], ax
0x18001758d  mov     rax, [rdi+70h]
0x180017591  test    rax, rax
0x180017594  jz      short loc_1800175A0
0x180017596  cmp     qword ptr [rax+10h], 0
0x18001759b  jz      short loc_1800175A0
0x18001759d  mov     esi, [rax+10h]
0x1800175a0  mov     edx, esi
0x1800175a2  lea     rcx, [rbp+960h+var_8D8]
0x1800175a9  call    ConvertPortNoToString
0x1800175ae  mov     r9, [rdi+70h]
0x1800175b2  add     r9, rbx
0x1800175b5  lea     r8, [rbp+960h+pszDest]
0x1800175bc  lea     rdx, aServercoidSCli; "ServerCoID=%S : ClientCoID=%S"
0x1800175c3  lea     rcx, [rbp+960h+var_830]
0x1800175ca  call    FormatRRASErrorString
0x1800175cf  test    cs:byte_1800AA941, 8
0x1800175d6  jz      short loc_18001762A
0x1800175d8  mov     rdx, [rdi+70h]
0x1800175dc  mov     rax, rdx
0x1800175df  lea     rcx, [rdx+0A7Eh]
0x1800175e6  neg     rax
0x1800175e9  sbb     r8, r8
0x1800175ec  and     r8, rcx
0x1800175ef  test    rdx, rdx
0x1800175f2  lea     r9, [rdx+848h]
0x1800175f9  jnz     short loc_1800175FF
0x1800175fb  lea     r9, [rbp+960h+var_9E0]
0x1800175ff  lea     rax, [rbp+960h+var_8D8]
0x180017606  mov     qword ptr [rsp+0A60h+dwErrorCode], rax
0x18001760b  mov     [rsp+0A60h+plpszSubStringArray], r8
0x180017610  lea     r8, [rbp+960h+var_830]
0x180017617  lea     rdx, RasVpnIkeParamTraceInfo
0x18001761e  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x180017625  call    McTemplateU0zjzz_EventWriteTransfer
  ... truncated ...
```
