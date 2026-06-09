# wil::details::WilApiImpl_GetFeatureEnabledState(uint,FEATURE_CHANGE_TIME,int *)

- ea: `0x1800027a0`
- end: `0x18000298f`
- name: `?WilApiImpl_GetFeatureEnabledState@details@wil@@YA?AW4FEATURE_ENABLED_STATE@@IW4FEATURE_CHANGE_TIME@@PEAH@Z`
- size: `495`
- prototype: `enum FEATURE_ENABLED_STATE __fastcall(wil::details *__hidden this, unsigned int, enum FEATURE_CHANGE_TIME, int *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting`

## callees

- `0x1800027a0`
- `0x1800029a0`
- `0x180004a48`
- `0x180008320`
- `0x18000d020`
- `0x1800105e0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000291a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000291a`

## string_xrefs

- `0x180002913`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil::details::WilApiImpl_GetFeatureEnabledState(wil::details *this, int a2, _DWORD *a3, int *a4)
{
  unsigned int v5; // r15d
  bool v6; // bp
  volatile __int32 *v7; // rdi
  unsigned int v8; // esi
  volatile __int32 v9; // eax
  int v10; // r12d
  int v11; // r9d
  int FeatureState; // ebx
  int v13; // eax
  char v14; // cl
  int v15; // ebx
  FARPROC ProcAddress; // rax
  HMODULE NtDllModuleHandle; // rax
  int v19; // eax
  __int64 v20; // [rsp+30h] [rbp-68h] BYREF
  __int128 v21; // [rsp+38h] [rbp-60h] BYREF
  __int64 v22; // [rsp+48h] [rbp-50h]
  __int64 v23; // [rsp+50h] [rbp-48h] BYREF
  int v24; // [rsp+58h] [rbp-40h]

  v5 = (unsigned int)this;
  v6 = (a2 & 0xFFFFFF7F) - 2 <= 1;
  v7 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::machineStoreProbe;
  v8 = 0;
  v22 = 0;
  if ( (a2 & 0x80) != 0 )
    v7 = (volatile __int32 *)&`wil::details::IsFeatureConfigured'::`2'::userStoreProbe;
  v21 = 0;
  v9 = *v7;
  if ( (*v7 & 2) == 0 )
  {
LABEL_6:
    LODWORD(v20) = 1;
    v10 = wil::details::EnsureSubscribedToFeatureConfigurationChanges((wil::details *)&`wil::details::IsFeatureConfigured'::`2'::userStoreProbe);
    FeatureState = wil_QueryFeatureState((unsigned int)&v21, v5, v6, v11, (__int64)&v20, (__int64)a3);
    v13 = v20;
    v14 = _InterlockedExchange(v7, ((_DWORD)v20 != 0) + 6);
    if ( !v13 && (v14 & 4) == 0 )
      wil::details::SubscribeFeatureStateCacheToConfigurationChanges(v7, 0, v10);
    if ( !FeatureState )
      goto LABEL_10;
    goto LABEL_23;
  }
  if ( (v9 & 1) == 0 )
    goto LABEL_10;
  if ( (v9 & 2) == 0 )
    goto LABEL_6;
  v20 = 0;
  v23 = 0;
  v15 = 1;
  v24 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  *a3 = 1;
  if ( !ProcAddress )
  {
    NtDllModuleHandle = wil_details_GetNtDllModuleHandle();
    ProcAddress = GetProcAddress(NtDllModuleHandle, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
      goto LABEL_10;
  }
  v19 = ((__int64 (__fastcall *)(_QWORD, bool, __int64 *, __int64 *))ProcAddress)(v5, !v6, &v20, &v23);
  if ( !v19 )
  {
    LODWORD(v21) = (HIDWORD(v23) >> 4) & 3;
    HIDWORD(v22) = (BYTE4(v23) >> 6) & 1;
    if ( (v23 & 0x8000000000LL) == 0 )
      v15 = 0;
    goto LABEL_24;
  }
  if ( v19 != 279 )
  {
LABEL_10:
    v15 = v22;
    goto LABEL_11;
  }
  if ( (v23 & 0x8000000000LL) == 0 )
LABEL_23:
    v15 = v22;
LABEL_24:
  v8 = v21;
LABEL_11:
  if ( v15 )
    v8 |= 0x80u;
  if ( HIDWORD(v22) )
    v8 |= 0x40u;
  return v8;
}

```

## disassembly

```asm
0x1800027a0  mov     r11, rsp
0x1800027a3  push    rsi
0x1800027a4  sub     rsp, 90h
0x1800027ab  mov     rax, cs:__security_cookie
0x1800027b2  xor     rax, rsp
0x1800027b5  mov     [rsp+98h+var_38], rax
0x1800027ba  mov     [r11+10h], rbx
0x1800027be  mov     eax, edx
0x1800027c0  mov     [r11+20h], rbp
0x1800027c4  btr     edx, 7
0x1800027c8  mov     [r11-10h], rdi
0x1800027cc  sub     edx, 2
0x1800027cf  mov     [r11-20h], r14
0x1800027d3  and     eax, 80h
0x1800027d8  mov     [r11-28h], r15
0x1800027dc  mov     r14, r8
0x1800027df  mov     r15d, ecx
0x1800027e2  cmp     edx, 1
0x1800027e5  jbe     short loc_1800027EC
0x1800027e7  xor     bpl, bpl
0x1800027ea  jmp     short loc_1800027EF
0x1800027ec  mov     bpl, 1
0x1800027ef  xor     ecx, ecx
0x1800027f1  lea     rdi, ?machineStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; wil_details_FeatureStateCache `wil::details::IsFeatureConfigured(wil_FeatureState *,uint,bool,wil_FeatureStore,int *)'::`2'::machineStoreProbe
0x1800027f8  xor     esi, esi
0x1800027fa  mov     [rsp+98h+var_50], rcx
0x1800027ff  test    eax, eax
0x180002801  lea     rcx, ?userStoreProbe@?1??IsFeatureConfigured@details@wil@@YA_NPEAUwil_FeatureState@@I_NW4wil_FeatureStore@@PEAH@Z@4Twil_details_FeatureStateCache@@A; this
0x180002808  xorps   xmm0, xmm0
0x18000280b  cmovnz  rdi, rcx
0x18000280f  movups  [rsp+98h+var_60], xmm0
0x180002814  mov     eax, [rdi]
0x180002816  test    al, 2
0x180002818  jz      short loc_180002826
0x18000281a  test    al, 1
0x18000281c  jz      short loc_180002897
0x18000281e  test    al, 2
0x180002820  jnz     loc_1800028E7
0x180002826  mov     ebx, 1
0x18000282b  mov     [rsp+98h+var_18], r12
0x180002833  mov     dword ptr [rsp+98h+var_68], ebx
0x180002837  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000283c  mov     r12d, eax
0x18000283f  movzx   r8d, bpl
0x180002843  lea     rax, [rsp+98h+var_68]
0x180002848  mov     [rsp+98h+var_70], r14
0x18000284d  mov     edx, r15d
0x180002850  mov     [rsp+98h+var_78], rax
0x180002855  lea     rcx, [rsp+98h+var_60]
0x18000285a  call    wil_QueryFeatureState
0x18000285f  xor     ecx, ecx
0x180002861  mov     ebx, eax
0x180002863  mov     eax, dword ptr [rsp+98h+var_68]
0x180002867  test    eax, eax
0x180002869  setnz   cl
0x18000286c  add     ecx, 6
0x18000286f  xchg    ecx, [rdi]
0x180002871  test    eax, eax
0x180002873  jnz     short loc_180002887
0x180002875  test    cl, 4
0x180002878  jnz     short loc_180002887
0x18000287a  mov     r8d, r12d
0x18000287d  xor     edx, edx
0x18000287f  mov     rcx, rdi
0x180002882  call    ?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z; wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)
0x180002887  mov     r12, [rsp+98h+var_18]
0x18000288f  test    ebx, ebx
0x180002891  jnz     loc_180002982
0x180002897  mov     ebx, dword ptr [rsp+98h+var_50]
0x18000289b  mov     r15, [rsp+98h+var_28]
0x1800028a0  test    ebx, ebx
0x1800028a2  mov     rbx, [rsp+98h+arg_8]
0x1800028aa  mov     r14, [rsp+98h+var_20]
0x1800028af  mov     rdi, [rsp+98h+var_10]
0x1800028b7  mov     rbp, [rsp+98h+arg_18]
0x1800028bf  jz      short loc_1800028C5
0x1800028c1  bts     esi, 7
0x1800028c5  cmp     dword ptr [rsp+98h+var_50+4], 0
0x1800028ca  jz      short loc_1800028CF
0x1800028cc  or      esi, 40h
0x1800028cf  mov     eax, esi
0x1800028d1  mov     rcx, [rsp+98h+var_38]
0x1800028d6  xor     rcx, rsp; StackCookie
0x1800028d9  call    __security_check_cookie
0x1800028de  add     rsp, 90h
0x1800028e5  pop     rsi
0x1800028e6  retn
0x1800028e7  xor     eax, eax
0x1800028e9  mov     [rsp+98h+var_68], rsi
0x1800028ee  mov     [rsp+98h+var_48], rax
0x1800028f3  mov     ebx, 1
0x1800028f8  mov     [rsp+98h+var_40], eax
0x1800028fc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180002903  mov     [r8], ebx
0x180002906  test    rax, rax
0x180002909  jnz     short loc_180002930
0x18000290b  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180002910  mov     rcx, rax; hModule
0x180002913  lea     rdx, ProcName; "RtlQueryFeatureConfiguration"
0x18000291a  call    cs:__imp_GetProcAddress
0x180002920  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180002927  test    rax, rax
0x18000292a  jz      loc_180002897
0x180002930  movzx   edx, bpl
0x180002934  lea     r9, [rsp+98h+var_48]
0x180002939  xor     edx, ebx
0x18000293b  lea     r8, [rsp+98h+var_68]
0x180002940  mov     ecx, r15d
0x180002943  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002948  test    eax, eax
0x18000294a  jnz     short loc_180002970
0x18000294c  mov     ecx, dword ptr [rsp+98h+var_48+4]
0x180002950  mov     eax, ecx
0x180002952  shr     eax, 4
0x180002955  and     eax, 3
0x180002958  mov     dword ptr [rsp+98h+var_60], eax
0x18000295c  movzx   eax, cl
0x18000295f  shr     eax, 6
0x180002962  and     eax, ebx
0x180002964  mov     dword ptr [rsp+98h+var_50+4], eax
0x180002968  test    cl, cl
0x18000296a  js      short loc_180002986
0x18000296c  xor     ebx, ebx
0x18000296e  jmp     short loc_180002986
0x180002970  cmp     eax, 117h
0x180002975  jnz     loc_180002897
0x18000297b  test    byte ptr [rsp+98h+var_48+4], 80h
0x180002980  jnz     short loc_180002986
0x180002982  mov     ebx, dword ptr [rsp+98h+var_50]
0x180002986  mov     esi, dword ptr [rsp+98h+var_60]
0x18000298a  jmp     loc_18000289B
```
