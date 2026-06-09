# CWsmTrackingConfig::AddTrackedStablePath(ushort const *,_WSM_TRACKING_MODE)

- ea: `0x14000a300`
- end: `0x14000a4a9`
- name: `?AddTrackedStablePath@CWsmTrackingConfig@@UEAAJPEBGW4_WSM_TRACKING_MODE@@@Z`
- size: `425`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000a0fc`
- `0x14000a300`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a481`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3be`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a3e5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a481`

## string_xrefs

- `0x14000a410`: `CWsmTrackingConfig::AddTrackedStablePath: Failed to update configuration (with path info for %ws added) (0x%08X)`
- `0x14000a45c`: `CWsmTrackingConfig::AddTrackedStablePath: Failed to read configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::AddTrackedStablePath(CWsmTrackingConfig *a1, __int64 a2, unsigned int a3)
{
  __int64 (__fastcall **v7)(CWsmTrackingConfig *); // rax
  __int64 (__fastcall *v8)(CWsmTrackingConfig *); // rax
  struct CWsmTrackingConfig::CTrackingConfig **v9; // rbx
  struct _WSM_TRACKING_CONFIG *v10; // rax
  int Instance; // esi
  CWsmTrackingConfig::CTrackingConfig *v12; // rbx
  PVOID v13; // rbx
  int v14; // eax
  struct _WSM_TRACKING_CONFIG *v15; // rdx
  int v16; // eax
  unsigned int v17; // edi
  PVOID v18; // rbx
  __int128 v19; // [rsp+20h] [rbp-50h] BYREF
  __int64 v20; // [rsp+30h] [rbp-40h]
  CWsmTrackingConfig::CTrackingConfig *v21; // [rsp+38h] [rbp-38h] BYREF
  CWsmTrackingConfig::CTrackingConfig **v22; // [rsp+40h] [rbp-30h]
  __int128 v23; // [rsp+50h] [rbp-20h] BYREF
  __int128 v24; // [rsp+60h] [rbp-10h]
  PVOID P; // [rsp+A8h] [rbp+38h] BYREF

  if ( !a2 )
    return 3221225485LL;
  P = 0;
  v20 = 0;
  v7 = *(__int64 (__fastcall ***)(CWsmTrackingConfig *))a1;
  v23 = 0;
  v24 = 0;
  v8 = *v7;
  v19 = 0;
  if ( v8(a1) )
  {
    v9 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                          &v21,
                                                          &P);
    v10 = (struct _WSM_TRACKING_CONFIG *)(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))a1)(a1);
    Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v10, 1, v9);
    if ( v21 )
    {
      v12 = *v22;
      *v22 = v21;
      if ( v12 )
      {
        CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v12);
        ExFreePoolWithTag(v12, 0x6E6D7377u);
      }
    }
    if ( Instance < 0 )
      goto LABEL_8;
    v14 = CWsmTrackingConfig::CTrackingConfig::AddTrackedStablePath(P, a2, a3);
    Instance = v14;
    if ( v14 < 0 )
    {
      WriteLog(
        0,
        "CWsmTrackingConfig::AddTrackedStablePath: Failed to update configuration (with path info for %ws added) (0x%08X)",
        a2,
        (unsigned int)v14);
LABEL_8:
      v13 = P;
      if ( P )
      {
        CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
        ExFreePoolWithTag(v13, 0x6E6D7377u);
      }
      return (unsigned int)Instance;
    }
    v15 = (struct _WSM_TRACKING_CONFIG *)((char *)P + 88);
  }
  else
  {
    *(_QWORD *)&v19 = a2;
    *((_QWORD *)&v24 + 1) = &v19;
    v15 = (struct _WSM_TRACKING_CONFIG *)&v23;
    DWORD2(v19) = a3;
    LODWORD(v24) = 1;
  }
  v16 = CWsmTrackingConfig::Read(a1, v15, 1);
  v17 = v16;
  if ( v16 < 0 )
    WriteLog(0, "CWsmTrackingConfig::AddTrackedStablePath: Failed to read configuration (0x%08X)", v16);
  v18 = P;
  if ( P )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
    ExFreePoolWithTag(v18, 0x6E6D7377u);
  }
  return v17;
}

```

## disassembly

```asm
0x14000a300  mov     [rsp-28h+arg_0], rbx
0x14000a305  mov     [rsp-28h+arg_10], rsi
0x14000a30a  push    rbp
0x14000a30b  push    rdi
0x14000a30c  push    r12
0x14000a30e  push    r14
0x14000a310  push    r15
0x14000a312  mov     rbp, rsp
0x14000a315  sub     rsp, 70h
0x14000a319  mov     r15d, r8d
0x14000a31c  mov     rdi, rdx
0x14000a31f  mov     r14, rcx
0x14000a322  test    rdx, rdx
0x14000a325  jnz     short loc_14000A331
0x14000a327  mov     eax, 0C000000Dh
0x14000a32c  jmp     loc_14000A48F
0x14000a331  xor     eax, eax
0x14000a333  mov     [rbp+P], 0
0x14000a33b  mov     [rbp+var_40], rax
0x14000a33f  xorps   xmm0, xmm0
0x14000a342  mov     rax, [rcx]
0x14000a345  xorps   xmm1, xmm1
0x14000a348  movups  [rbp+var_20], xmm0
0x14000a34c  movups  [rbp+var_10], xmm0
0x14000a350  mov     rax, [rax]
0x14000a353  movups  [rbp+var_50], xmm1
0x14000a357  call    _guard_dispatch_icall
0x14000a35c  mov     r12d, 6E6D7377h
0x14000a362  test    rax, rax
0x14000a365  jz      loc_14000A42D
0x14000a36b  lea     rdx, [rbp+P]
0x14000a36f  lea     rcx, [rbp+var_38]
0x14000a373  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000a378  mov     rcx, [r14]
0x14000a37b  mov     rbx, rax
0x14000a37e  mov     rax, [rcx]
0x14000a381  mov     rcx, r14
0x14000a384  call    _guard_dispatch_icall
0x14000a389  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x14000a38c  mov     dl, 1; bool
0x14000a38e  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x14000a391  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x14000a396  mov     esi, eax
0x14000a398  mov     rax, [rbp+var_38]
0x14000a39c  test    rax, rax
0x14000a39f  jz      short loc_14000A3CA
0x14000a3a1  mov     rdx, [rbp+var_30]
0x14000a3a5  mov     rbx, [rdx]
0x14000a3a8  mov     [rdx], rax
0x14000a3ab  test    rbx, rbx
0x14000a3ae  jz      short loc_14000A3CA
0x14000a3b0  mov     rcx, rbx; this
0x14000a3b3  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a3b8  mov     edx, r12d; Tag
0x14000a3bb  mov     rcx, rbx; P
0x14000a3be  call    cs:__imp_ExFreePoolWithTag
0x14000a3c5  nop     dword ptr [rax+rax+00h]
0x14000a3ca  test    esi, esi
0x14000a3cc  jns     short loc_14000A3F8
0x14000a3ce  mov     rbx, [rbp+P]
0x14000a3d2  test    rbx, rbx
0x14000a3d5  jz      short loc_14000A3F1
0x14000a3d7  mov     rcx, rbx; this
0x14000a3da  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a3df  mov     edx, r12d; Tag
0x14000a3e2  mov     rcx, rbx; P
0x14000a3e5  call    cs:__imp_ExFreePoolWithTag
0x14000a3ec  nop     dword ptr [rax+rax+00h]
0x14000a3f1  mov     eax, esi
0x14000a3f3  jmp     loc_14000A48F
0x14000a3f8  mov     rcx, [rbp+P]
0x14000a3fc  mov     r8d, r15d
0x14000a3ff  mov     rdx, rdi
0x14000a402  call    ?AddTrackedStablePath@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBGW4_WSM_TRACKING_MODE@@@Z; CWsmTrackingConfig::CTrackingConfig::AddTrackedStablePath(ushort const *,_WSM_TRACKING_MODE)
0x14000a407  mov     esi, eax
0x14000a409  test    eax, eax
0x14000a40b  jns     short loc_14000A423
0x14000a40d  mov     r9d, eax
0x14000a410  lea     rdx, aCwsmtrackingco_5; "CWsmTrackingConfig::AddTrackedStablePat"...
0x14000a417  mov     r8, rdi
0x14000a41a  xor     ecx, ecx
0x14000a41c  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000a421  jmp     short loc_14000A3CE
0x14000a423  mov     rdx, [rbp+P]
0x14000a427  add     rdx, 58h ; 'X'
0x14000a42b  jmp     short loc_14000A448
0x14000a42d  lea     rax, [rbp+var_50]
0x14000a431  mov     qword ptr [rbp+var_50], rdi
0x14000a435  mov     qword ptr [rbp+var_10+8], rax
0x14000a439  lea     rdx, [rbp+var_20]; struct _WSM_TRACKING_CONFIG *
0x14000a43d  mov     dword ptr [rbp+var_50+8], r15d
0x14000a441  mov     dword ptr [rbp+var_10], 1
0x14000a448  mov     r8b, 1; bool
0x14000a44b  mov     rcx, r14; this
0x14000a44e  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x14000a453  mov     edi, eax
0x14000a455  test    eax, eax
0x14000a457  jns     short loc_14000A46A
0x14000a459  mov     r8d, eax
0x14000a45c  lea     rdx, aCwsmtrackingco_6; "CWsmTrackingConfig::AddTrackedStablePat"...
0x14000a463  xor     ecx, ecx
0x14000a465  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000a46a  mov     rbx, [rbp+P]
0x14000a46e  test    rbx, rbx
0x14000a471  jz      short loc_14000A48D
0x14000a473  mov     rcx, rbx; this
0x14000a476  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a47b  mov     edx, r12d; Tag
0x14000a47e  mov     rcx, rbx; P
0x14000a481  call    cs:__imp_ExFreePoolWithTag
0x14000a488  nop     dword ptr [rax+rax+00h]
0x14000a48d  mov     eax, edi
0x14000a48f  lea     r11, [rsp+70h+var_s0]
0x14000a494  mov     rbx, [r11+30h]
0x14000a498  mov     rsi, [r11+40h]
0x14000a49c  mov     rsp, r11
0x14000a49f  pop     r15
0x14000a4a1  pop     r14
0x14000a4a3  pop     r12
0x14000a4a5  pop     rdi
0x14000a4a6  pop     rbp
0x14000a4a7  retn
```
