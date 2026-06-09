# CWindowsLiveProvider::MakeServiceCall(RefWLIDHandle &,bool,ushort const *,bool)

- ea: `0x18002520c`
- end: `0x180025599`
- name: `?MakeServiceCall@CWindowsLiveProvider@@AEAAJAEAVRefWLIDHandle@@_NPEBG1@Z`
- size: `909`
- prototype: `int(CWindowsLiveProvider *__hidden this, struct RefWLIDHandle *, bool, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180025bbc`

## callees

- `0x1800061a8`
- `0x1800090c0`
- `0x180009630`
- `0x18000a400`
- `0x18000bcc4`
- `0x1800130a4`
- `0x180013434`
- `0x18001a0d0`
- `0x18002520c`
- `0x180043944`
- `0x1800463a0`
- `0x180046a58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025552`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180025552`

## string_xrefs

- `0x1800253b6`: `WLIDCAcquireTokens failed, hr=0x%X`
- `0x1800254b7`: `WLIDCAcquireTokens returned hrAuthState=0x%X, hrRequestStatus=0x%X`
- `0x180025289`: `CWindowsLiveProvider::MakeServiceCall`
- `0x180025307`: `CWindowsLiveProvider::MakeServiceCall`
- `0x1800252f2`: `hr = WLIDCGetConfigString(c_wsz_cfg_AccountDomain, &wszAccountDomain)`
- `0x180025337`: `hr = WLIDCGetConfigString(c_wsz_cfg_ConnectAccountPolicy, &wszAccountPolicy)`
- `0x180025518`: `WLIDCAcquireTokens failed, ignoring due to migration, hr=0x%X mappedHr=0x%X`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CWindowsLiveProvider::MakeServiceCall(
        CWindowsLiveProvider *this,
        struct RefWLIDHandle *a2,
        unsigned __int8 a3,
        const unsigned __int16 *a4,
        bool a5)
{
  int v6; // r14d
  const unsigned __int16 *v8; // rdi
  int v9; // eax
  const char *v10; // rcx
  unsigned int v11; // r8d
  void *const *Handle; // rax
  struct _WLIDRequestParams *v13; // r9
  int v14; // eax
  int v15; // ecx
  void *const *v16; // rax
  const unsigned __int16 *v17; // r9
  unsigned int v18; // r8d
  char v19; // bl
  void *const *v20; // rax
  int v21; // ecx
  int v22; // eax
  unsigned int v23; // ebx
  struct _WLIDAcquireTokenResults *v25; // [rsp+20h] [rbp-A1h]
  struct _WLIDAcquireTokenResults *v26; // [rsp+20h] [rbp-A1h]
  struct _WLIDResponseParams **v27; // [rsp+28h] [rbp-99h]
  bool v28; // [rsp+30h] [rbp-91h] BYREF
  int v29; // [rsp+34h] [rbp-8Dh] BYREF
  unsigned __int16 *v30; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int16 *v31; // [rsp+40h] [rbp-81h] BYREF
  void *Block; // [rsp+48h] [rbp-79h] BYREF
  unsigned __int16 *v33; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int16 *v34; // [rsp+58h] [rbp-69h] BYREF
  unsigned __int16 *v35; // [rsp+60h] [rbp-61h] BYREF
  __int128 v36; // [rsp+68h] [rbp-59h]
  __int128 v37; // [rsp+78h] [rbp-49h]
  __int64 v38; // [rsp+88h] [rbp-39h] BYREF
  const unsigned __int16 *v39; // [rsp+90h] [rbp-31h]
  __int128 v40; // [rsp+98h] [rbp-29h]
  _QWORD v41[4]; // [rsp+A8h] [rbp-19h] BYREF
  __int128 v42; // [rsp+C8h] [rbp+7h] BYREF
  int v43; // [rsp+D8h] [rbp+17h]

  v6 = a3;
  v29 = 0;
  v38 = 1152;
  v8 = &qword_180063440;
  v39 = &qword_180063440;
  v40 = 0;
  v42 = 0;
  v43 = 0;
  v35 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v33 = 0;
  Block = 0;
  v41[0] = "CWindowsLiveProvider::MakeServiceCall";
  v41[1] = &v29;
  v41[2] = 0;
  v41[3] = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    "CWindowsLiveProvider::MakeServiceCall",
    (const char *)0xAE5,
    0,
    (const unsigned __int16 *)v25);
  if ( (_BYTE)v6 == 1 )
  {
    v38 = 0x200000480LL;
    goto LABEL_9;
  }
  v9 = WLIDCGetConfigString(L"cfg:AccountDomain", &v34);
  v29 = v9;
  if ( v9 < 0 )
  {
    v10 = "hr = WLIDCGetConfigString(c_wsz_cfg_AccountDomain, &wszAccountDomain)";
    v11 = 2800;
LABEL_5:
    Telemetry::IfFailExit(
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      "CWindowsLiveProvider::MakeServiceCall",
      v11,
      v9,
      v10);
    goto LABEL_34;
  }
  v9 = WLIDCGetConfigString(L"cfg:ConnectAccountPolicy", &v33);
  v29 = v9;
  if ( v9 < 0 )
  {
    v10 = "hr = WLIDCGetConfigString(c_wsz_cfg_ConnectAccountPolicy, &wszAccountPolicy)";
    v11 = 2805;
    goto LABEL_5;
  }
  v35 = v34;
  *(_QWORD *)&v36 = v33;
  HIDWORD(v37) = 1;
  *(_QWORD *)&v37 = 0;
LABEL_9:
  if ( a4 )
  {
    if ( *a4 )
      v8 = a4;
    v39 = v8;
  }
  Handle = RefWLIDHandle::GetHandle(a2);
  v13 = (struct _WLIDRequestParams *)&v35;
  if ( (_BYTE)v6 )
    v13 = 0;
  v14 = WLIDCAcquireTokensEx(
          *Handle,
          (struct _WLIDAcquireTokenParams *const)&v38,
          v6 ^ 1u,
          v13,
          (struct _WLIDAcquireTokenResults *)&v42,
          (struct _WLIDResponseParams **)&Block);
  v29 = v14;
  if ( v14 < 0 )
  {
    LODWORD(v26) = v14;
    TracePrintW(
      2u,
      "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
      0xB0Cu,
      L"WLIDCAcquireTokens failed, hr=0x%X",
      v26);
    goto LABEL_34;
  }
  v15 = v42;
  if ( (int)v42 >= 0 )
    goto LABEL_34;
  if ( (_BYTE)v6 && !a5 )
    goto LABEL_31;
  v31 = 0;
  v30 = 0;
  v16 = RefWLIDHandle::GetHandle(a2);
  if ( (int)WLIDCGetIdentityProperty(*v16, L"AuthUrl", &v30) >= 0 && v30 && *v30 )
  {
    v17 = L"Auth URL is present. Ignoring the error for connect.";
    v18 = 2851;
  }
  else
  {
    v19 = 0;
    v20 = RefWLIDHandle::GetHandle(a2);
    if ( (int)WLIDCGetIdentityProperty(*v20, L"FlowUrl", &v31) < 0 || !v31 || !*v31 )
      goto LABEL_29;
    v17 = L"Flow URL is present. Ignoring the error for connect.";
    v18 = 2863;
  }
  v19 = 1;
  TracePrintW(5u, "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp", v18, v17);
LABEL_29:
  CMIDLPtr<unsigned short *>::Clear(&v30);
  CMIDLPtr<unsigned short *>::Clear(&v31);
  if ( v19 )
    goto LABEL_34;
  v15 = v42;
LABEL_31:
  LODWORD(v27) = DWORD2(v42);
  LODWORD(v26) = v15;
  TracePrintW(
    2u,
    "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
    0xB37u,
    L"WLIDCAcquireTokens returned hrAuthState=0x%X, hrRequestStatus=0x%X",
    v26,
    v27);
  v21 = v42;
  if ( SDWORD2(v42) < 0 )
    v21 = DWORD2(v42);
  v29 = v21;
LABEL_34:
  if ( v29 < 0 && a5 )
  {
    v28 = 0;
    v22 = ErrorHandlingUtilities::MapInternalErrorToExternal(v29, 0, &v28);
    if ( v28 )
    {
      LODWORD(v27) = v22;
      LODWORD(v26) = v29;
      TracePrintW(
        3u,
        "onecoreuap\\ds\\ext\\live\\identity\\identityprovider\\lib\\windowsliveprovider.cpp",
        0xB56u,
        L"WLIDCAcquireTokens failed, ignoring due to migration, hr=0x%X mappedHr=0x%X",
        v26,
        v27);
      v29 = 0;
    }
  }
  v23 = v29;
  CTraceFuncW<long>::~CTraceFuncW<long>(v41);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  CMIDLPtr<unsigned short *>::Clear(&v33);
  CMIDLPtr<unsigned short *>::Clear(&v34);
  return v23;
}

```

## disassembly

```asm
0x18002520c  mov     [rsp-8+arg_0], rbx
0x180025211  mov     [rsp-8+arg_10], rsi
0x180025216  push    rbp
0x180025217  push    rdi
0x180025218  push    r12
0x18002521a  push    r14
0x18002521c  push    r15
0x18002521e  lea     rbp, [rsp-2Fh]
0x180025223  sub     rsp, 0F0h
0x18002522a  mov     rax, cs:__security_cookie
0x180025231  xor     rax, rsp
0x180025234  mov     [rbp+4Fh+var_30], rax
0x180025238  mov     rsi, r9
0x18002523b  movzx   r14d, r8b
0x18002523f  mov     r15, rdx
0x180025242  xor     r12d, r12d
0x180025245  mov     [rsp+110h+var_DC], r12d
0x18002524a  mov     ebx, 480h
0x18002524f  mov     [rbp+4Fh+var_88], rbx
0x180025253  lea     rdi, qword_180063440
0x18002525a  mov     [rbp+4Fh+var_80], rdi
0x18002525e  xorps   xmm0, xmm0
0x180025261  movups  [rbp+4Fh+var_78], xmm0
0x180025265  xorps   xmm1, xmm1
0x180025268  movdqu  [rbp+4Fh+var_48], xmm1
0x18002526d  mov     [rbp+4Fh+var_38], r12d
0x180025271  mov     [rbp+4Fh+var_B0], r12
0x180025275  movups  [rbp+4Fh+var_A8], xmm0
0x180025279  movups  [rbp+4Fh+var_98], xmm0
0x18002527d  mov     [rbp+4Fh+var_B8], r12
0x180025281  mov     [rbp+4Fh+var_C0], r12
0x180025285  mov     [rbp+4Fh+Block], r12
0x180025289  lea     rcx, aCwindowslivepr_6; "CWindowsLiveProvider::MakeServiceCall"
0x180025290  mov     [rbp+4Fh+var_68], rcx
0x180025294  lea     rax, [rsp+110h+var_DC]
0x180025299  mov     [rbp+4Fh+var_60], rax
0x18002529d  mov     [rbp+4Fh+var_58], r12
0x1800252a1  mov     [rbp+4Fh+var_50], r12
0x1800252a5  xor     r9d, r9d; unsigned int
0x1800252a8  mov     r8d, 0AE5h; char *
0x1800252ae  mov     rdx, rcx; char *
0x1800252b1  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800252b8  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x1800252bd  nop
0x1800252be  cmp     r14b, 1
0x1800252c2  jnz     short loc_1800252DA
0x1800252c4  mov     rax, 200000000h
0x1800252ce  or      rbx, rax
0x1800252d1  mov     [rbp+4Fh+var_88], rbx
0x1800252d5  jmp     loc_180025361
0x1800252da  lea     rdx, [rbp+4Fh+var_B8]; unsigned __int16 **
0x1800252de  lea     rcx, aCfgAccountdoma; "cfg:AccountDomain"
0x1800252e5  call    ?WLIDCGetConfigString@@YAJPEBGPEAPEAG@Z; WLIDCGetConfigString(ushort const *,ushort * *)
0x1800252ea  mov     [rsp+110h+var_DC], eax
0x1800252ee  test    eax, eax
0x1800252f0  jns     short loc_18002531F
0x1800252f2  lea     rcx, aHrWlidcgetconf_0; "hr = WLIDCGetConfigString(c_wsz_cfg_Acc"...
0x1800252f9  mov     r8d, 0AF0h; unsigned int
0x1800252ff  mov     r9d, eax; int
0x180025302  mov     [rsp+110h+var_F0], rcx; char *
0x180025307  lea     rdx, aCwindowslivepr_6; "CWindowsLiveProvider::MakeServiceCall"
0x18002530e  lea     rcx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025315  call    ?IfFailExit@Telemetry@@SAXPEBD0KJ0@Z; Telemetry::IfFailExit(char const *,char const *,ulong,long,char const *)
0x18002531a  jmp     loc_1800254E4
0x18002531f  lea     rdx, [rbp+4Fh+var_C0]; unsigned __int16 **
0x180025323  lea     rcx, aCfgConnectacco; "cfg:ConnectAccountPolicy"
0x18002532a  call    ?WLIDCGetConfigString@@YAJPEBGPEAPEAG@Z; WLIDCGetConfigString(ushort const *,ushort * *)
0x18002532f  mov     [rsp+110h+var_DC], eax
0x180025333  test    eax, eax
0x180025335  jns     short loc_180025346
0x180025337  lea     rcx, aHrWlidcgetconf; "hr = WLIDCGetConfigString(c_wsz_cfg_Con"...
0x18002533e  mov     r8d, 0AF5h
0x180025344  jmp     short loc_1800252FF
0x180025346  mov     rax, [rbp+4Fh+var_B8]
0x18002534a  mov     [rbp+4Fh+var_B0], rax
0x18002534e  mov     rax, [rbp+4Fh+var_C0]
0x180025352  mov     qword ptr [rbp+4Fh+var_A8], rax
0x180025356  mov     dword ptr [rbp+4Fh+var_98+0Ch], 1
0x18002535d  mov     qword ptr [rbp+4Fh+var_98], r12
0x180025361  test    rsi, rsi
0x180025364  jz      short loc_180025372
0x180025366  cmp     [rsi], r12w
0x18002536a  cmovnz  rdi, rsi
0x18002536e  mov     [rbp+4Fh+var_80], rdi
0x180025372  mov     rcx, r15; this
0x180025375  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x18002537a  lea     r9, [rbp+4Fh+var_B0]
0x18002537e  test    r14b, r14b
0x180025381  cmovnz  r9, r12; struct _WLIDRequestParams *
0x180025385  mov     r8d, r14d
0x180025388  xor     r8d, 1; unsigned int
0x18002538c  lea     rcx, [rbp+4Fh+Block]
0x180025390  mov     [rsp+110h+var_E8], rcx; struct _WLIDResponseParams **
0x180025395  lea     rcx, [rbp+4Fh+var_48]
0x180025399  mov     [rsp+110h+var_F0], rcx; struct _WLIDAcquireTokenResults *
0x18002539e  lea     rdx, [rbp+4Fh+var_88]; struct _WLIDAcquireTokenParams *
0x1800253a2  mov     rcx, [rax]; void *
0x1800253a5  call    ?WLIDCAcquireTokensEx@@YAJQEAXQEAU_WLIDAcquireTokenParams@@KQEAU_WLIDRequestParams@@PEAU_WLIDAcquireTokenResults@@PEAPEAU_WLIDResponseParams@@@Z; WLIDCAcquireTokensEx(void * const,_WLIDAcquireTokenParams * const,ulong,_WLIDRequestParams * const,_WLIDAcquireTokenResults *,_WLIDResponseParams * *)
0x1800253aa  mov     [rsp+110h+var_DC], eax
0x1800253ae  test    eax, eax
0x1800253b0  jns     short loc_1800253D9
0x1800253b2  mov     dword ptr [rsp+110h+var_F0], eax
0x1800253b6  lea     r9, aWlidcacquireto_4; "WLIDCAcquireTokens failed, hr=0x%X"
0x1800253bd  mov     r8d, 0B0Ch; unsigned int
0x1800253c3  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800253ca  mov     ecx, 2; unsigned __int8
0x1800253cf  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800253d4  jmp     loc_1800254E4
0x1800253d9  mov     ecx, dword ptr [rbp+4Fh+var_48]
0x1800253dc  test    ecx, ecx
0x1800253de  jns     loc_1800254E4
0x1800253e4  test    r14b, r14b
0x1800253e7  jz      short loc_1800253F3
0x1800253e9  cmp     [rbp+4Fh+arg_20], 1
0x1800253ed  jnz     loc_1800254AC
0x1800253f3  mov     [rsp+110h+var_D0], r12
0x1800253f8  mov     [rsp+110h+var_D8], r12
0x1800253fd  mov     rcx, r15; this
0x180025400  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x180025405  lea     r8, [rsp+110h+var_D8]; unsigned __int16 **
0x18002540a  lea     rdx, aAuthurl; "AuthUrl"
0x180025411  mov     rcx, [rax]; void *
0x180025414  call    ?WLIDCGetIdentityProperty@@YAJQEAXPEBGPEAPEAG@Z; WLIDCGetIdentityProperty(void * const,ushort const *,ushort * *)
0x180025419  test    eax, eax
0x18002541b  js      short loc_18002543C
0x18002541d  mov     rax, [rsp+110h+var_D8]
0x180025422  test    rax, rax
0x180025425  jz      short loc_18002543C
0x180025427  cmp     [rax], r12w
0x18002542b  jz      short loc_18002543C
0x18002542d  lea     r9, aAuthUrlIsPrese; "Auth URL is present. Ignoring the error"...
0x180025434  mov     r8d, 0B23h
0x18002543a  jmp     short loc_18002547C
0x18002543c  mov     bl, r12b
0x18002543f  mov     rcx, r15; this
0x180025442  call    ?GetHandle@RefWLIDHandle@@AEAAPEAPEAXXZ; RefWLIDHandle::GetHandle(void)
0x180025447  lea     r8, [rsp+110h+var_D0]; unsigned __int16 **
0x18002544c  lea     rdx, aFlowurl; "FlowUrl"
0x180025453  mov     rcx, [rax]; void *
0x180025456  call    ?WLIDCGetIdentityProperty@@YAJQEAXPEBGPEAPEAG@Z; WLIDCGetIdentityProperty(void * const,ushort const *,ushort * *)
0x18002545b  test    eax, eax
0x18002545d  js      short loc_180025490
0x18002545f  mov     rax, [rsp+110h+var_D0]
0x180025464  test    rax, rax
0x180025467  jz      short loc_180025490
0x180025469  cmp     [rax], r12w
0x18002546d  jz      short loc_180025490
0x18002546f  lea     r9, aFlowUrlIsPrese; "Flow URL is present. Ignoring the error"...
0x180025476  mov     r8d, 0B2Fh; unsigned int
0x18002547c  mov     bl, 1
0x18002547e  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x180025485  mov     ecx, 5; unsigned __int8
0x18002548a  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x18002548f  nop
0x180025490  lea     rcx, [rsp+110h+var_D8]
0x180025495  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18002549a  nop
0x18002549b  lea     rcx, [rsp+110h+var_D0]
0x1800254a0  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x1800254a5  test    bl, bl
0x1800254a7  jnz     short loc_1800254E4
0x1800254a9  mov     ecx, dword ptr [rbp+4Fh+var_48]
0x1800254ac  mov     eax, dword ptr [rbp+4Fh+var_48+8]
0x1800254af  mov     dword ptr [rsp+110h+var_E8], eax
0x1800254b3  mov     dword ptr [rsp+110h+var_F0], ecx
0x1800254b7  lea     r9, aWlidcacquireto_0; "WLIDCAcquireTokens returned hrAuthState"...
0x1800254be  mov     r8d, 0B37h; unsigned int
0x1800254c4  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x1800254cb  mov     ecx, 2; unsigned __int8
0x1800254d0  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x1800254d5  mov     ecx, dword ptr [rbp+4Fh+var_48]
0x1800254d8  mov     eax, dword ptr [rbp+4Fh+var_48+8]
0x1800254db  test    eax, eax
0x1800254dd  cmovs   ecx, eax
0x1800254e0  mov     [rsp+110h+var_DC], ecx
0x1800254e4  mov     eax, [rsp+110h+var_DC]
0x1800254e8  test    eax, eax
0x1800254ea  jns     short loc_18002553B
0x1800254ec  cmp     [rbp+4Fh+arg_20], 1
0x1800254f0  jnz     short loc_18002553B
0x1800254f2  mov     [rsp+110h+var_E0], r12b
0x1800254f7  lea     r8, [rsp+110h+var_E0]; bool *
0x1800254fc  xor     edx, edx; bool
0x1800254fe  mov     ecx, eax; int
0x180025500  call    ?MapInternalErrorToExternal@ErrorHandlingUtilities@@SAJJ_NPEA_N@Z; ErrorHandlingUtilities::MapInternalErrorToExternal(long,bool,bool *)
0x180025505  cmp     [rsp+110h+var_E0], 1
0x18002550a  jnz     short loc_18002553B
0x18002550c  mov     dword ptr [rsp+110h+var_E8], eax
0x180025510  mov     eax, [rsp+110h+var_DC]
0x180025514  mov     dword ptr [rsp+110h+var_F0], eax
0x180025518  lea     r9, aWlidcacquireto; "WLIDCAcquireTokens failed, ignoring due"...
0x18002551f  mov     r8d, 0B56h; unsigned int
0x180025525  lea     rdx, aOnecoreuapDsEx; "onecoreuap\\ds\\ext\\live\\identity\\id"...
0x18002552c  mov     ecx, 3; unsigned __int8
0x180025531  call    ?TracePrintW@@YAXEPEBDKPEBGZZ; TracePrintW(uchar,char const *,ulong,ushort const *,...)
0x180025536  mov     [rsp+110h+var_DC], r12d
0x18002553b  mov     ebx, [rsp+110h+var_DC]
0x18002553f  lea     rcx, [rbp+4Fh+var_68]
0x180025543  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180025548  nop
0x180025549  mov     rcx, [rbp+4Fh+Block]; Block
0x18002554d  test    rcx, rcx
0x180025550  jz      short loc_18002555C
0x180025552  call    cs:__imp_free
0x180025558  mov     [rbp+4Fh+Block], r12
0x18002555c  lea     rcx, [rbp+4Fh+var_C0]
0x180025560  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x180025565  nop
0x180025566  lea     rcx, [rbp+4Fh+var_B8]
0x18002556a  call    ?Clear@?$CMIDLPtr@PEAG@@QEAAXXZ; CMIDLPtr<ushort *>::Clear(void)
0x18002556f  mov     eax, ebx
0x180025571  mov     rcx, [rbp+4Fh+var_30]
0x180025575  xor     rcx, rsp; StackCookie
0x180025578  call    __security_check_cookie
0x18002557d  lea     r11, [rsp+110h+var_20]
0x180025585  mov     rbx, [r11+30h]
0x180025589  mov     rsi, [r11+40h]
0x18002558d  mov     rsp, r11
0x180025590  pop     r15
0x180025592  pop     r14
0x180025594  pop     r12
0x180025596  pop     rdi
0x180025597  pop     rbp
0x180025598  retn
```
