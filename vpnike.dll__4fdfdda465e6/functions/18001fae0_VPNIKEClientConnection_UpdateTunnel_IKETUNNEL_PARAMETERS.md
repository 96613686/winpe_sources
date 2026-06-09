# VPNIKEClientConnection::UpdateTunnel(_IKETUNNEL_PARAMETERS_ &)

- ea: `0x18001fae0`
- end: `0x18001fe02`
- name: `?UpdateTunnel@VPNIKEClientConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@@Z`
- size: `802`
- prototype: `unsigned int __fastcall(VPNIKEClientConnection *__hidden this, struct _IKETUNNEL_PARAMETERS_ *)`
- caller_count: `0`
- callee_count: `17`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180004ab8`
- `0x180007610`
- `0x180007794`
- `0x1800077bc`
- `0x18000e3b8`
- `0x180013fa0`
- `0x18001fae0`
- `0x18004b20c`
- `0x18004c8a8`
- `0x18004fca8`
- `0x180050368`
- `0x1800768d4`
- `0x180076990`
- `0x180076ca0`
- `0x18007755e`
- `0x180077590`
- `0x18007a010`

## import_xrefs

- `rasman!RasSetPortUserData` at `0x18001fd84`
- `rasman!RasSetPortUserData` at `0x18001fd84`

## string_xrefs

- `0x18001fbb2`: `VPNIKEClientConnection::UpdateTunnel`
- `0x18001fc4e`: `VPNIKEConnection::UpdateTunnel failed.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall VPNIKEClientConnection::UpdateTunnel(
        VPNIKEClientConnection *this,
        struct _IKETUNNEL_PARAMETERS_ *a2)
{
  int v4; // r14d
  unsigned int v5; // edi
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9
  __int64 v9; // rax
  __int64 v10; // rdx
  __int128 *v11; // r9
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // r9
  __int64 v15; // rax
  __int64 v16; // rdx
  __int128 *v17; // r9
  unsigned int v18; // ebx
  unsigned int updated; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh] BYREF
  __int64 v22; // [rsp+38h] [rbp-C8h] BYREF
  __int128 v23; // [rsp+40h] [rbp-C0h]
  __int128 v24; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+60h] [rbp-A0h]
  int v26; // [rsp+68h] [rbp-98h]
  int v27; // [rsp+6Ch] [rbp-94h]
  __int128 v28; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v29[224]; // [rsp+80h] [rbp-80h] BYREF
  int v30; // [rsp+160h] [rbp+60h] BYREF
  __int128 v31; // [rsp+164h] [rbp+64h]
  __int128 v32; // [rsp+174h] [rbp+74h]
  int v33; // [rsp+184h] [rbp+84h]

  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids);
  }
  updated = 0;
  v4 = *((_DWORD *)this + 38);
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v28 = 0;
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v25 = 0;
  v5 = -1;
  v26 = -1;
  v27 = 0;
  if ( (byte_1800AA941 & 8) != 0 )
    EtwFuncEntryExitTracer::Initialize(
      (EtwFuncEntryExitTracer *)&v22,
      L"VPNIKEClientConnection::UpdateTunnel",
      &updated,
      (void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int))RasVpnIkeTraceFunctionWithVpnParams,
      *((void **)this + 14));
  updated = VPNIKEConnection::UpdateTunnel(this, a2);
  if ( updated )
  {
    if ( (byte_1800AA941 & 4) != 0 )
    {
      LOWORD(v30) = 0;
      v9 = *((_QWORD *)this + 14);
      if ( v9 && *(_QWORD *)(v9 + 16) )
        v5 = *(_DWORD *)(v9 + 16);
      ConvertPortNoToString(&v30, v5);
      if ( (byte_1800AA941 & 4) != 0 )
      {
        v10 = *((_QWORD *)this + 14);
        LODWORD(v11) = v10 + 2120;
        if ( !v10 )
          v11 = &v28;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceError,
          (unsigned int)L"VPNIKEConnection::UpdateTunnel failed.",
          (_DWORD)v11,
          (v10 + 2686) & -(__int64)(v10 != 0),
          (__int64)&v30);
      }
    }
  }
  else
  {
    if ( (v4 & 0x200000) != 0 )
    {
      if ( IPv4Helper::DoNegotiate(*((IPv4Helper **)this + 4), v6, v7, v8) )
        IPv4Helper::UpdateDefaultRoutes(*((IPv4Helper **)this + 4), 1u);
      if ( IPv6Helper::DoNegotiate(*((IPv6Helper **)this + 5), v12, v13, v14) )
        IPv6Helper::UpdateDefaultRoutes(*((IPv6Helper **)this + 5), 1u);
    }
    memset_0(v29, 0, sizeof(v29));
    VPNIKEConnection::GetProjectionResult((IPv4Helper **)this, (struct _PROTOCOL_PROJECTION_RESULT *)v29);
    (*((void (__fastcall **)(_QWORD, __int64, _BYTE *, __int64))&xmmword_1800AA980 + 1))(
      *(_QWORD *)(*((_QWORD *)this + 14) + 24LL),
      1,
      v29,
      224);
    v21 = 0x2000;
    if ( (byte_1800AA941 & 8) != 0 )
    {
      LOWORD(v30) = 0;
      v15 = *((_QWORD *)this + 14);
      if ( v15 && *(_QWORD *)(v15 + 16) )
        v5 = *(_DWORD *)(v15 + 16);
      ConvertPortNoToString(&v30, v5);
      if ( (byte_1800AA941 & 8) != 0 )
      {
        v16 = *((_QWORD *)this + 14);
        LODWORD(v17) = v16 + 2120;
        if ( !v16 )
          v17 = &v28;
        McTemplateU0zjzz_EventWriteTransfer(
          (unsigned int)&MICROSOFT_WINDOWS_RRAS_PROVIDER_Context,
          (unsigned int)RasVpnIkeParamTraceInfo,
          (unsigned int)L"Setting RASPortSubStatus to RASCSS_Reconnected.",
          (_DWORD)v17,
          (v16 + 2686) & -(__int64)(v16 != 0),
          (__int64)&v30);
      }
    }
    RasSetPortUserData(*((_QWORD *)this + 3), 14, &v21);
    VPNIKEProtocolEngine::NotifyCaller(*((_QWORD *)this + 3), 15, 0);
  }
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, &WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids, updated);
  }
  v18 = updated;
  EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer((EtwFuncEntryExitTracer *)&v22);
  return v18;
}

```

## disassembly

```asm
0x18001fae0  mov     [rsp-8+arg_10], rbx
0x18001fae5  push    rbp
0x18001fae6  push    rsi
0x18001fae7  push    rdi
0x18001fae8  push    r13
0x18001faea  push    r14
0x18001faec  lea     rbp, [rsp-90h]
0x18001faf4  sub     rsp, 190h
0x18001fafb  mov     rax, cs:__security_cookie
0x18001fb02  xor     rax, rsp
0x18001fb05  mov     [rbp+0B0h+var_28], rax
0x18001fb0c  mov     rsi, rdx
0x18001fb0f  mov     rbx, rcx
0x18001fb12  lea     r13, WPP_GLOBAL_Control
0x18001fb19  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb20  cmp     rcx, r13
0x18001fb23  jz      short loc_18001FB46
0x18001fb25  test    byte ptr [rcx+1Ch], 1
0x18001fb29  jz      short loc_18001FB46
0x18001fb2b  cmp     byte ptr [rcx+19h], 6
0x18001fb2f  jb      short loc_18001FB46
0x18001fb31  mov     edx, 3Ch ; '<'
0x18001fb36  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001fb3d  mov     rcx, [rcx+10h]
0x18001fb41  call    WPP_SF_
0x18001fb46  mov     [rsp+1B0h+var_180], 0
0x18001fb4e  mov     r14d, [rbx+98h]
0x18001fb55  xor     eax, eax
0x18001fb57  mov     [rbp+0B0h+var_50], eax
0x18001fb5a  xorps   xmm0, xmm0
0x18001fb5d  movups  [rbp+0B0h+var_4C], xmm0
0x18001fb61  movups  [rbp+0B0h+var_3C], xmm0
0x18001fb65  mov     [rbp+0B0h+var_2C], eax
0x18001fb6b  movups  [rsp+1B0h+var_140], xmm0
0x18001fb70  xorps   xmm1, xmm1
0x18001fb73  movdqu  [rsp+1B0h+var_170], xmm1
0x18001fb79  mov     [rsp+1B0h+var_178], rax
0x18001fb7e  movdqu  [rsp+1B0h+var_160], xmm0
0x18001fb84  mov     [rsp+1B0h+var_150], rax
0x18001fb89  or      edi, 0FFFFFFFFh
0x18001fb8c  mov     [rsp+1B0h+var_148], edi
0x18001fb90  mov     [rsp+1B0h+var_144], eax
0x18001fb94  test    cs:byte_1800AA941, 8
0x18001fb9b  jz      short loc_18001FBC3
0x18001fb9d  mov     rax, [rbx+70h]
0x18001fba1  mov     [rsp+1B0h+var_190], rax; void *
0x18001fba6  lea     r9, ?RasVpnIkeTraceFunctionWithVpnParams@@YAXPEAGPEAXPEAU_GUID@@0K@Z; void (*)(unsigned __int16 *, void *, struct _GUID *, unsigned __int16 *, unsigned int)
0x18001fbad  lea     r8, [rsp+1B0h+var_180]; unsigned int *
0x18001fbb2  lea     rdx, aVpnikeclientco_2; "VPNIKEClientConnection::UpdateTunnel"
0x18001fbb9  lea     rcx, [rsp+1B0h+var_178]; this
0x18001fbbe  call    ?Initialize@EtwFuncEntryExitTracer@@QEAAXPEAGPEAKP6AX0PEAXPEAU_GUID@@0K@Z2@Z; EtwFuncEntryExitTracer::Initialize(ushort *,ulong *,void (*)(ushort *,void *,_GUID *,ushort *,ulong),void *)
0x18001fbc3  mov     rdx, rsi; struct _IKETUNNEL_PARAMETERS_ *
0x18001fbc6  mov     rcx, rbx; this
0x18001fbc9  call    ?UpdateTunnel@VPNIKEConnection@@UEAAKAEAU_IKETUNNEL_PARAMETERS_@@@Z; VPNIKEConnection::UpdateTunnel(_IKETUNNEL_PARAMETERS_ &)
0x18001fbce  mov     [rsp+1B0h+var_180], eax
0x18001fbd2  test    eax, eax
0x18001fbd4  jz      loc_18001FC6D
0x18001fbda  test    cs:byte_1800AA941, 4
0x18001fbe1  jz      loc_18001FD9A
0x18001fbe7  xor     eax, eax
0x18001fbe9  mov     word ptr [rbp+0B0h+var_50], ax
0x18001fbed  mov     rax, [rbx+70h]
0x18001fbf1  test    rax, rax
0x18001fbf4  jz      short loc_18001FC00
0x18001fbf6  cmp     qword ptr [rax+10h], 0
0x18001fbfb  jz      short loc_18001FC00
0x18001fbfd  mov     edi, [rax+10h]
0x18001fc00  mov     edx, edi
0x18001fc02  lea     rcx, [rbp+0B0h+var_50]
0x18001fc06  call    ConvertPortNoToString
0x18001fc0b  test    cs:byte_1800AA941, 4
0x18001fc12  jz      loc_18001FD9A
0x18001fc18  mov     rdx, [rbx+70h]
0x18001fc1c  mov     rax, rdx
0x18001fc1f  lea     rcx, [rdx+0A7Eh]
0x18001fc26  neg     rax
0x18001fc29  sbb     r8, r8
0x18001fc2c  and     r8, rcx
0x18001fc2f  test    rdx, rdx
0x18001fc32  lea     r9, [rdx+848h]
0x18001fc39  jnz     short loc_18001FC40
0x18001fc3b  lea     r9, [rsp+1B0h+var_140]
0x18001fc40  lea     rax, [rbp+0B0h+var_50]
0x18001fc44  mov     [rsp+1B0h+var_188], rax
0x18001fc49  mov     [rsp+1B0h+var_190], r8
0x18001fc4e  lea     r8, aVpnikeconnecti_11; "VPNIKEConnection::UpdateTunnel failed."
0x18001fc55  lea     rdx, RasVpnIkeParamTraceError
0x18001fc5c  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fc63  call    McTemplateU0zjzz_EventWriteTransfer
0x18001fc68  jmp     loc_18001FD9A
0x18001fc6d  bt      r14d, 15h
0x18001fc72  jnb     short loc_18001FCA4
0x18001fc74  mov     rcx, [rbx+20h]; this
0x18001fc78  call    ?DoNegotiate@IPv4Helper@@QEAAEXZ; IPv4Helper::DoNegotiate(void)
0x18001fc7d  test    al, al
0x18001fc7f  jz      short loc_18001FC8C
0x18001fc81  mov     dl, 1; unsigned __int8
0x18001fc83  mov     rcx, [rbx+20h]; this
0x18001fc87  call    ?UpdateDefaultRoutes@IPv4Helper@@QEAAXE@Z; IPv4Helper::UpdateDefaultRoutes(uchar)
0x18001fc8c  mov     rcx, [rbx+28h]; this
0x18001fc90  call    ?DoNegotiate@IPv6Helper@@QEAAEXZ; IPv6Helper::DoNegotiate(void)
0x18001fc95  test    al, al
0x18001fc97  jz      short loc_18001FCA4
0x18001fc99  mov     dl, 1; unsigned __int8
0x18001fc9b  mov     rcx, [rbx+28h]; this
0x18001fc9f  call    ?UpdateDefaultRoutes@IPv6Helper@@QEAAXE@Z; IPv6Helper::UpdateDefaultRoutes(uchar)
0x18001fca4  mov     esi, 0E0h
0x18001fca9  mov     r8d, esi; Size
0x18001fcac  xor     edx, edx; Val
0x18001fcae  lea     rcx, [rbp+0B0h+var_130]; void *
0x18001fcb2  call    memset_0
0x18001fcb7  lea     rdx, [rbp+0B0h+var_130]; struct _PROTOCOL_PROJECTION_RESULT *
0x18001fcbb  mov     rcx, rbx; this
0x18001fcbe  call    ?GetProjectionResult@VPNIKEConnection@@IEAAXAEAU_PROTOCOL_PROJECTION_RESULT@@@Z; VPNIKEConnection::GetProjectionResult(_PROTOCOL_PROJECTION_RESULT &)
0x18001fcc3  mov     rcx, [rbx+70h]
0x18001fcc7  mov     r9d, esi
0x18001fcca  lea     r8, [rbp+0B0h+var_130]
0x18001fcce  mov     edx, 1
0x18001fcd3  mov     rcx, [rcx+18h]
0x18001fcd7  mov     rax, qword ptr cs:xmmword_1800AA980+8
0x18001fcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fce3  mov     [rsp+1B0h+var_17C], 2000h
0x18001fceb  test    cs:byte_1800AA941, 8
0x18001fcf2  jz      short loc_18001FD71
0x18001fcf4  xor     eax, eax
0x18001fcf6  mov     word ptr [rbp+0B0h+var_50], ax
0x18001fcfa  mov     rax, [rbx+70h]
0x18001fcfe  test    rax, rax
0x18001fd01  jz      short loc_18001FD0D
0x18001fd03  cmp     qword ptr [rax+10h], 0
0x18001fd08  jz      short loc_18001FD0D
0x18001fd0a  mov     edi, [rax+10h]
0x18001fd0d  mov     edx, edi
0x18001fd0f  lea     rcx, [rbp+0B0h+var_50]
0x18001fd13  call    ConvertPortNoToString
0x18001fd18  test    cs:byte_1800AA941, 8
0x18001fd1f  jz      short loc_18001FD71
0x18001fd21  mov     rdx, [rbx+70h]
0x18001fd25  mov     rax, rdx
0x18001fd28  lea     rcx, [rdx+0A7Eh]
0x18001fd2f  neg     rax
0x18001fd32  sbb     r8, r8
0x18001fd35  and     r8, rcx
0x18001fd38  test    rdx, rdx
0x18001fd3b  lea     r9, [rdx+848h]
0x18001fd42  jnz     short loc_18001FD49
0x18001fd44  lea     r9, [rsp+1B0h+var_140]
0x18001fd49  lea     rax, [rbp+0B0h+var_50]
0x18001fd4d  mov     [rsp+1B0h+var_188], rax
0x18001fd52  mov     [rsp+1B0h+var_190], r8
0x18001fd57  lea     r8, aSettingRasport; "Setting RASPortSubStatus to RASCSS_Reco"...
0x18001fd5e  lea     rdx, RasVpnIkeParamTraceInfo
0x18001fd65  lea     rcx, MICROSOFT_WINDOWS_RRAS_PROVIDER_Context
0x18001fd6c  call    McTemplateU0zjzz_EventWriteTransfer
0x18001fd71  mov     r9d, 4
0x18001fd77  lea     r8, [rsp+1B0h+var_17C]
0x18001fd7c  lea     edx, [r9+0Ah]
0x18001fd80  mov     rcx, [rbx+18h]
0x18001fd84  call    cs:__imp_RasSetPortUserData
0x18001fd8a  xor     r8d, r8d
0x18001fd8d  lea     edx, [r8+0Fh]
0x18001fd91  mov     rcx, [rbx+18h]
0x18001fd95  call    ?NotifyCaller@VPNIKEProtocolEngine@@SAXPEAXW4_PROTOCOL_RESULT_ID@@0@Z; VPNIKEProtocolEngine::NotifyCaller(void *,_PROTOCOL_RESULT_ID,void *)
0x18001fd9a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fda1  cmp     rcx, r13
0x18001fda4  jz      short loc_18001FDCC
0x18001fda6  test    byte ptr [rcx+1Ch], 1
0x18001fdaa  jz      short loc_18001FDCC
0x18001fdac  cmp     byte ptr [rcx+19h], 6
0x18001fdb0  jb      short loc_18001FDCC
0x18001fdb2  mov     edx, 3Dh ; '='
0x18001fdb7  mov     r9d, [rsp+1B0h+var_180]
0x18001fdbc  lea     r8, WPP_d095eb42f253352a4c7fb272692bfd83_Traceguids
0x18001fdc3  mov     rcx, [rcx+10h]
0x18001fdc7  call    WPP_SF_d
0x18001fdcc  mov     ebx, [rsp+1B0h+var_180]
0x18001fdd0  lea     rcx, [rsp+1B0h+var_178]; this
0x18001fdd5  call    ??1EtwFuncEntryExitTracer@@QEAA@XZ; EtwFuncEntryExitTracer::~EtwFuncEntryExitTracer(void)
0x18001fdda  mov     eax, ebx
0x18001fddc  mov     rcx, [rbp+0B0h+var_28]
0x18001fde3  xor     rcx, rsp; StackCookie
0x18001fde6  call    __security_check_cookie
0x18001fdeb  mov     rbx, [rsp+1B0h+arg_10]
0x18001fdf3  add     rsp, 190h
0x18001fdfa  pop     r14
0x18001fdfc  pop     r13
0x18001fdfe  pop     rdi
0x18001fdff  pop     rsi
0x18001fe00  pop     rbp
0x18001fe01  retn
```
