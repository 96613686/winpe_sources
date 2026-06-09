# WamRegGlobal::DeleteApp(ushort const *,int,int)

- ea: `0x180004acc`
- end: `0x180004da5`
- name: `?DeleteApp@WamRegGlobal@@QEAAJPEBGHH@Z`
- size: `729`
- prototype: `__int64 __fastcall(WamRegGlobal *this, const unsigned __int16 *, unsigned int, int)`
- caller_count: `3`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180001ed0`
- `0x1800029e0`
- `0x180003720`

## callees

- `0x180004acc`
- `0x180005138`
- `0x180005a50`
- `0x180005b90`
- `0x1800060f4`
- `0x180006408`
- `0x180006850`
- `0x180007010`

## import_xrefs

- `iisutil!PuDbgPrint` at `0x180004b70`
- `iisutil!PuDbgPrint` at `0x180004bd3`
- `iisutil!PuDbgPrint` at `0x180004c53`
- `iisutil!PuDbgPrint` at `0x180004b70`
- `iisutil!PuDbgPrint` at `0x180004bd3`
- `iisutil!PuDbgPrint` at `0x180004c53`

## string_xrefs

- `0x180004b4c`: `WamRegGlobal::DeleteApp`
- `0x180004baa`: `WamRegGlobal::DeleteApp`
- `0x180004c26`: `WamRegGlobal::DeleteApp`
- `0x180004bbc`: `W3ServiceUtil APPCMD_DELETE Failed on (%S) hr=%08x\n`
- `0x180004c47`: `Failed to UnRegister WAMCLSID(%S), hr = %08x\n`

## pseudocode

```c
__int64 __fastcall WamRegGlobal::DeleteApp(WamRegGlobal *this, const unsigned __int16 *a2, unsigned int a3, int a4)
{
  __int64 result; // rax
  WamRegMetabaseConfig *v8; // rcx
  unsigned int v9; // r8d
  int v10; // eax
  WamRegMetabaseConfig *v11; // rcx
  int v12; // eax
  int v13; // ebx
  WamRegRegistryConfig *v14; // rcx
  int v15; // r8d
  int v16; // eax
  int v17; // eax
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  unsigned int v20[3]; // [rsp+44h] [rbp-BCh] BYREF
  __int128 v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+60h] [rbp-A0h]
  __int128 v23; // [rsp+70h] [rbp-90h]
  __int128 v24; // [rsp+80h] [rbp-80h]
  __int128 v25; // [rsp+90h] [rbp-70h]
  __int128 v26; // [rsp+A0h] [rbp-60h]
  __int128 v27; // [rsp+B0h] [rbp-50h]
  __int128 v28; // [rsp+C0h] [rbp-40h]
  __int128 v29; // [rsp+D0h] [rbp-30h]
  __int128 v30; // [rsp+E0h] [rbp-20h]
  __int128 v31; // [rsp+F0h] [rbp-10h]
  __int128 v32; // [rsp+100h] [rbp+0h]
  __int128 v33; // [rsp+110h] [rbp+10h]
  __int128 v34; // [rsp+120h] [rbp+20h]
  __int128 v35; // [rsp+130h] [rbp+30h]
  unsigned __int16 v36[40]; // [rsp+140h] [rbp+40h] BYREF
  unsigned __int16 v37[40]; // [rsp+190h] [rbp+90h] BYREF

  v19 = 0;
  v20[0] = 0;
  result = WamRegMetabaseConfig::MDGetDWORD(this, a2, a3, &v19);
  if ( (_DWORD)result == -2146646015 )
    return 0;
  if ( (int)result < 0 )
    return result;
  v10 = WamRegMetabaseConfig::MDSetAppState(v8, a2, v9);
  if ( v10 < 0 && (g_dwDebugFlags & 3) != 0 )
    PuDbgPrint(
      g_pDebug,
      "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
      1198,
      "WamRegGlobal::DeleteApp",
      "MDSetAppState Failed hr=%08x\n",
      v10);
  if ( g_pfnW3ServiceSink )
  {
    v12 = g_pfnW3ServiceSink((const char *)a2, 8u, v20);
    v13 = v12;
    if ( v12 < 0 && (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
        1208,
        "WamRegGlobal::DeleteApp",
        "W3ServiceUtil APPCMD_DELETE Failed on (%S) hr=%08x\n",
        a2,
        v12);
  }
  else
  {
    v20[0] = 5;
    v13 = 0;
  }
  if ( v19 != 1 )
  {
LABEL_15:
    if ( v13 < 0 )
      return 0;
    goto LABEL_16;
  }
  WamRegMetabaseConfig::MDGetIDs(v11, a2, v36, v37, 1u);
  v16 = WamRegRegistryConfig::UnRegisterCLSID(v14, v36, v15);
  v13 = v16;
  if ( v16 < 0 )
  {
    if ( (g_dwDebugFlags & 3) != 0 )
      PuDbgPrint(
        g_pDebug,
        "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfunc.cpp",
        1227,
        "WamRegGlobal::DeleteApp",
        "Failed to UnRegister WAMCLSID(%S), hr = %08x\n",
        v36,
        v16);
    goto LABEL_15;
  }
LABEL_16:
  v17 = 0;
  v21 = *(_OWORD *)&WamRegMetabaseConfig::m_rgMDPropTemplate;
  v23 = xmmword_180009770;
  v22 = xmmword_180009760;
  v25 = xmmword_180009790;
  v24 = xmmword_180009780;
  v27 = xmmword_1800097B0;
  v26 = xmmword_1800097A0;
  v29 = xmmword_1800097D0;
  v28 = xmmword_1800097C0;
  v31 = xmmword_1800097F0;
  v30 = xmmword_1800097E0;
  v33 = xmmword_180009810;
  v32 = xmmword_180009800;
  v35 = xmmword_180009830;
  v34 = xmmword_180009820;
  if ( v19 == 1 )
  {
    LODWORD(v28) = 2;
    DWORD2(v26) = 2;
    LODWORD(v25) = 2;
    if ( (unsigned int)(g_PlatformType - 1) <= 1 )
    {
      DWORD2(v29) = 1;
      *(_QWORD *)&v29 = v37;
    }
    v17 = 1;
  }
  if ( !a3 )
  {
    LODWORD(v31) = 2;
    LODWORD(v22) = 2;
    DWORD2(v23) = 2;
    DWORD2(v32) = 2;
    if ( a4 )
      DWORD2(v35) = 2;
    if ( v19 == 1 )
      LODWORD(v34) = 2;
    goto LABEL_26;
  }
  if ( v17 )
LABEL_26:
    WamRegMetabaseConfig::UpdateMD((WamRegMetabaseConfig *)2, (struct MDPropItem *)&v21, 0, a2, v18);
  return 0;
}

```

## disassembly

```asm
0x180004acc  mov     [rsp-8+arg_0], rbx
0x180004ad1  mov     [rsp-8+arg_10], rsi
0x180004ad6  push    rbp
0x180004ad7  push    rdi
0x180004ad8  push    r14
0x180004ada  lea     rbp, [rsp-0F0h]
0x180004ae2  sub     rsp, 1F0h
0x180004ae9  mov     rax, cs:__security_cookie
0x180004af0  xor     rax, rsp
0x180004af3  mov     [rbp+100h+var_20], rax
0x180004afa  mov     esi, r9d
0x180004afd  mov     [rsp+200h+var_1C0], 0
0x180004b05  lea     r9, [rsp+200h+var_1C0]; unsigned int *
0x180004b0a  mov     [rsp+200h+var_1BC], 0
0x180004b12  mov     r14d, r8d
0x180004b15  mov     rdi, rdx
0x180004b18  call    ?MDGetDWORD@WamRegMetabaseConfig@@QEAAJPEBGKPEAK@Z; WamRegMetabaseConfig::MDGetDWORD(ushort const *,ulong,ulong *)
0x180004b1d  cmp     eax, 800CC801h
0x180004b22  jz      loc_180004D7C
0x180004b28  test    eax, eax
0x180004b2a  js      loc_180004D7E
0x180004b30  mov     rdx, rdi; unsigned __int16 *
0x180004b33  call    ?MDSetAppState@WamRegMetabaseConfig@@QEAAJPEBGK@Z; WamRegMetabaseConfig::MDSetAppState(ushort const *,ulong)
0x180004b38  test    eax, eax
0x180004b3a  jns     short loc_180004B76
0x180004b3c  test    byte ptr cs:g_dwDebugFlags, 3
0x180004b43  jz      short loc_180004B76
0x180004b45  mov     rcx, cs:g_pDebug
0x180004b4c  lea     r9, aWamregglobalDe; "WamRegGlobal::DeleteApp"
0x180004b53  mov     dword ptr [rsp+200h+var_1D8], eax
0x180004b57  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004b5e  lea     rax, aMdsetappstateF; "MDSetAppState Failed hr=%08x\n"
0x180004b65  mov     r8d, 4AEh
0x180004b6b  mov     qword ptr [rsp+200h+var_1E0], rax
0x180004b70  call    cs:__imp_PuDbgPrint
0x180004b76  mov     rax, cs:?g_pfnW3ServiceSink@@3P6AJPEBDKPEAK@ZEA; long (*g_pfnW3ServiceSink)(char const *,ulong,ulong *)
0x180004b7d  test    rax, rax
0x180004b80  jz      short loc_180004BDB
0x180004b82  lea     r8, [rsp+200h+var_1BC]
0x180004b87  mov     edx, 8
0x180004b8c  mov     rcx, rdi
0x180004b8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b94  mov     ebx, eax
0x180004b96  test    eax, eax
0x180004b98  jns     short loc_180004BE5
0x180004b9a  test    byte ptr cs:g_dwDebugFlags, 3
0x180004ba1  jz      short loc_180004BE5
0x180004ba3  mov     rcx, cs:g_pDebug
0x180004baa  lea     r9, aWamregglobalDe; "WamRegGlobal::DeleteApp"
0x180004bb1  mov     [rsp+200h+var_1D0], eax
0x180004bb5  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004bbc  lea     rax, aW3serviceutilA; "W3ServiceUtil APPCMD_DELETE Failed on ("...
0x180004bc3  mov     [rsp+200h+var_1D8], rdi
0x180004bc8  mov     r8d, 4B8h
0x180004bce  mov     qword ptr [rsp+200h+var_1E0], rax
0x180004bd3  call    cs:__imp_PuDbgPrint
0x180004bd9  jmp     short loc_180004BE5
0x180004bdb  mov     [rsp+200h+var_1BC], 5
0x180004be3  xor     ebx, ebx
0x180004be5  cmp     [rsp+200h+var_1C0], 1
0x180004bea  jnz     short loc_180004C59
0x180004bec  lea     r9, [rbp+100h+var_70]; unsigned __int16 *
0x180004bf3  mov     [rsp+200h+var_1E0], 1; unsigned int
0x180004bfb  lea     r8, [rbp+100h+var_C0]; unsigned __int16 *
0x180004bff  mov     rdx, rdi; unsigned __int16 *
0x180004c02  call    ?MDGetIDs@WamRegMetabaseConfig@@QEAAJPEBGPEAG1K@Z; WamRegMetabaseConfig::MDGetIDs(ushort const *,ushort *,ushort *,ulong)
0x180004c07  lea     rdx, [rbp+100h+var_C0]; unsigned __int16 *
0x180004c0b  call    ?UnRegisterCLSID@WamRegRegistryConfig@@QEAAJPEBGH@Z; WamRegRegistryConfig::UnRegisterCLSID(ushort const *,int)
0x180004c10  mov     ebx, eax
0x180004c12  test    eax, eax
0x180004c14  jns     short loc_180004C61
0x180004c16  test    byte ptr cs:g_dwDebugFlags, 3
0x180004c1d  jz      short loc_180004C59
0x180004c1f  mov     rcx, cs:g_pDebug
0x180004c26  lea     r9, aWamregglobalDe; "WamRegGlobal::DeleteApp"
0x180004c2d  mov     [rsp+200h+var_1D0], eax
0x180004c31  lea     rdx, aInetsrvIisSvcs; "inetsrv\\iis\\svcs\\wam\\wamreg\\auxfun"...
0x180004c38  lea     rax, [rbp+100h+var_C0]
0x180004c3c  mov     r8d, 4CBh
0x180004c42  mov     [rsp+200h+var_1D8], rax
0x180004c47  lea     rax, aFailedToUnregi; "Failed to UnRegister WAMCLSID(%S), hr ="...
0x180004c4e  mov     qword ptr [rsp+200h+var_1E0], rax; int
0x180004c53  call    cs:__imp_PuDbgPrint
0x180004c59  test    ebx, ebx
0x180004c5b  js      loc_180004D7C
0x180004c61  movaps  xmm0, cs:?m_rgMDPropTemplate@WamRegMetabaseConfig@@0QBUMDPropItem@@B; MDPropItem const near * const WamRegMetabaseConfig::m_rgMDPropTemplate
0x180004c68  xor     eax, eax
0x180004c6a  cmp     [rsp+200h+var_1C0], 1
0x180004c6f  movaps  xmm1, cs:xmmword_180009760
0x180004c76  movups  [rsp+200h+var_1B0], xmm0
0x180004c7b  lea     ecx, [rax+2]; this
0x180004c7e  movaps  xmm0, cs:xmmword_180009770
0x180004c85  movups  [rsp+200h+var_190], xmm0
0x180004c8a  movaps  xmm0, cs:xmmword_180009790
0x180004c91  movups  [rsp+200h+var_1A0], xmm1
0x180004c96  movaps  xmm1, cs:xmmword_180009780
0x180004c9d  movups  [rbp+100h+var_170], xmm0
0x180004ca1  movaps  xmm0, cs:xmmword_1800097B0
0x180004ca8  movups  [rbp+100h+var_180], xmm1
0x180004cac  movaps  xmm1, cs:xmmword_1800097A0
0x180004cb3  movups  [rbp+100h+var_150], xmm0
0x180004cb7  movaps  xmm0, cs:xmmword_1800097D0
0x180004cbe  movups  [rbp+100h+var_160], xmm1
0x180004cc2  movaps  xmm1, cs:xmmword_1800097C0
0x180004cc9  movups  [rbp+100h+var_130], xmm0
0x180004ccd  movaps  xmm0, cs:xmmword_1800097F0
0x180004cd4  movups  [rbp+100h+var_140], xmm1
0x180004cd8  movaps  xmm1, cs:xmmword_1800097E0
0x180004cdf  movups  [rbp+100h+var_110], xmm0
0x180004ce3  movaps  xmm0, cs:xmmword_180009810
0x180004cea  movups  [rbp+100h+var_120], xmm1
0x180004cee  movaps  xmm1, cs:xmmword_180009800
0x180004cf5  movups  [rbp+100h+var_F0], xmm0
0x180004cf9  movaps  xmm0, cs:xmmword_180009830
0x180004d00  movups  [rbp+100h+var_100], xmm1
0x180004d04  movaps  xmm1, cs:xmmword_180009820
0x180004d0b  movups  [rbp+100h+var_D0], xmm0
0x180004d0f  movups  [rbp+100h+var_E0], xmm1
0x180004d13  jnz     short loc_180004D42
0x180004d15  mov     eax, cs:g_PlatformType
0x180004d1b  dec     eax
0x180004d1d  mov     dword ptr [rbp+100h+var_140], ecx
0x180004d20  mov     dword ptr [rbp+100h+var_160+8], ecx
0x180004d23  mov     dword ptr [rbp+100h+var_170], ecx
0x180004d26  cmp     eax, 1
0x180004d29  ja      short loc_180004D3D
0x180004d2b  lea     rax, [rbp+100h+var_70]
0x180004d32  mov     dword ptr [rbp+100h+var_130+8], 1
0x180004d39  mov     qword ptr [rbp+100h+var_130], rax
0x180004d3d  mov     eax, 1
0x180004d42  test    r14d, r14d
0x180004d45  jnz     short loc_180004D68
0x180004d47  mov     dword ptr [rbp+100h+var_110], ecx
0x180004d4a  mov     dword ptr [rsp+200h+var_1A0], ecx
0x180004d4e  mov     dword ptr [rsp+200h+var_190+8], ecx
0x180004d52  mov     dword ptr [rbp+100h+var_100+8], ecx
0x180004d55  test    esi, esi
0x180004d57  jz      short loc_180004D5C
0x180004d59  mov     dword ptr [rbp+100h+var_D0+8], ecx
0x180004d5c  cmp     [rsp+200h+var_1C0], 1
0x180004d61  jnz     short loc_180004D6C
0x180004d63  mov     dword ptr [rbp+100h+var_E0], ecx
0x180004d66  jmp     short loc_180004D6C
0x180004d68  test    eax, eax
0x180004d6a  jz      short loc_180004D7C
0x180004d6c  mov     r9, rdi; unsigned __int16 *
0x180004d6f  lea     rdx, [rsp+200h+var_1B0]; struct MDPropItem *
0x180004d74  xor     r8d, r8d; unsigned int
0x180004d77  call    ?UpdateMD@WamRegMetabaseConfig@@QEAAJPEAUMDPropItem@@KPEBGH@Z; WamRegMetabaseConfig::UpdateMD(MDPropItem *,ulong,ushort const *,int)
0x180004d7c  xor     eax, eax
0x180004d7e  mov     rcx, [rbp+100h+var_20]
0x180004d85  xor     rcx, rsp; StackCookie
0x180004d88  call    __security_check_cookie
0x180004d8d  lea     r11, [rsp+200h+var_10]
0x180004d95  mov     rbx, [r11+20h]
0x180004d99  mov     rsi, [r11+30h]
0x180004d9d  mov     rsp, r11
0x180004da0  pop     r14
0x180004da2  pop     rdi
0x180004da3  pop     rbp
0x180004da4  retn
```
