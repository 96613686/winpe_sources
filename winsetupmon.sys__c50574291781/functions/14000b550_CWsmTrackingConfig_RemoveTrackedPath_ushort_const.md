# CWsmTrackingConfig::RemoveTrackedPath(ushort const *)

- ea: `0x14000b550`
- end: `0x14000b775`
- name: `?RemoveTrackedPath@CWsmTrackingConfig@@UEAAJPEBG@Z`
- size: `549`
- prototype: `int(CWsmTrackingConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000b550`
- `0x14000b77c`
- `0x14000c410`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b61e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b67b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b746`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b5f7`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b61e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b67b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b68d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b6dc`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b746`

## string_xrefs

- `0x14000b6ef`: `CWsmTrackingConfig::RemoveTrackedPath: Failed to update configuration (with %ws removed) (0x%08X)`
- `0x14000b721`: `CWsmTrackingConfig::RemoveTrackedPath: Failed to read new buffer into configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::RemoveTrackedPath(
        __int64 (__fastcall ***this)(char *),
        const unsigned __int16 *a2)
{
  CWsmTrackingConfig *v4; // rsi
  struct CWsmTrackingConfig::CTrackingConfig **v5; // rbx
  struct _WSM_TRACKING_CONFIG *v6; // rax
  int Instance; // edi
  CWsmTrackingConfig::CTrackingConfig *v8; // rbx
  PVOID v9; // rbx
  CWsmTrackingConfig::CTrackingConfig *v10; // r15
  int v11; // eax
  void **v12; // rbx
  CWsmTrackingConfig::CTrackingConfig *v13; // rcx
  const unsigned __int16 *v14; // rdx
  void *v15; // rcx
  int v16; // eax
  unsigned int v17; // ebx
  PVOID v18; // rdi
  void **v19; // [rsp+20h] [rbp-20h] BYREF
  PVOID v20; // [rsp+28h] [rbp-18h]
  PVOID P; // [rsp+78h] [rbp+38h] BYREF

  if ( !a2 )
    return 3221225485LL;
  v4 = (CWsmTrackingConfig *)(this - 1);
  if ( !(**(this - 1))((char *)this - 8) )
    return (unsigned int)-1073741275;
  P = 0;
  v5 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v19,
                                                        &P);
  v6 = (struct _WSM_TRACKING_CONFIG *)(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))v4)(v4);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v6, 1, v5);
  if ( v19 )
  {
    v8 = *(CWsmTrackingConfig::CTrackingConfig **)v20;
    *(_QWORD *)v20 = v19;
    if ( v8 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v8);
      ExFreePoolWithTag(v8, 0x6E6D7377u);
    }
  }
  if ( Instance < 0 )
    goto LABEL_8;
  v10 = (CWsmTrackingConfig::CTrackingConfig *)P;
  v19 = &wsm_stable_path::`vftable';
  v20 = 0;
  v11 = wsm_stable_path::assign((wsm_stable_path *)&v19, a2);
  v12 = (void **)v20;
  Instance = v11;
  if ( v11 >= 0 )
  {
    if ( v20 )
      v14 = *(const unsigned __int16 **)v20;
    else
      v14 = 0;
    Instance = CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath(v10, v14);
    if ( v12 )
    {
      v15 = *v12;
      if ( *v12 != v12 + 2 && v15 )
        ExFreePoolWithTag(v15, 0x6E6D7377u);
      ExFreePoolWithTag(v12, 0x6E6D7377u);
    }
    if ( Instance < 0 )
      goto LABEL_26;
    v16 = CWsmTrackingConfig::Read(v4, (struct _WSM_TRACKING_CONFIG *const)((char *)P + 88), 1);
    v17 = v16;
    if ( v16 < 0 )
      WriteLog(0, "CWsmTrackingConfig::RemoveTrackedPath: Failed to read new buffer into configuration (0x%08X)", v16);
    v18 = P;
    if ( P )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
      ExFreePoolWithTag(v18, 0x6E6D7377u);
    }
    return v17;
  }
  if ( v20 )
  {
    v13 = *(CWsmTrackingConfig::CTrackingConfig **)v20;
    if ( *(PVOID *)v20 != (char *)v20 + 16 && v13 )
      ExFreePoolWithTag(v13, 0x6E6D7377u);
    ExFreePoolWithTag(v12, 0x6E6D7377u);
  }
LABEL_26:
  WriteLog(
    0,
    "CWsmTrackingConfig::RemoveTrackedPath: Failed to update configuration (with %ws removed) (0x%08X)",
    a2,
    (unsigned int)Instance);
LABEL_8:
  v9 = P;
  if ( P )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
    ExFreePoolWithTag(v9, 0x6E6D7377u);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14000b550  mov     [rsp-28h+arg_0], rbx
0x14000b555  mov     [rsp-28h+arg_10], rsi
0x14000b55a  push    rbp
0x14000b55b  push    rdi
0x14000b55c  push    r12
0x14000b55e  push    r14
0x14000b560  push    r15
0x14000b562  mov     rbp, rsp
0x14000b565  sub     rsp, 40h
0x14000b569  mov     r14, rdx
0x14000b56c  test    rdx, rdx
0x14000b56f  jnz     short loc_14000B57B
0x14000b571  mov     eax, 0C000000Dh
0x14000b576  jmp     loc_14000B75B
0x14000b57b  lea     rsi, [rcx-8]
0x14000b57f  mov     rax, [rsi]
0x14000b582  mov     rcx, rsi
0x14000b585  mov     rax, [rax]
0x14000b588  call    _guard_dispatch_icall
0x14000b58d  test    rax, rax
0x14000b590  jz      loc_14000B754
0x14000b596  lea     rdx, [rbp+P]
0x14000b59a  mov     [rbp+P], 0
0x14000b5a2  lea     rcx, [rbp+var_20]
0x14000b5a6  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000b5ab  mov     rcx, [rsi]
0x14000b5ae  mov     rbx, rax
0x14000b5b1  mov     rax, [rcx]
0x14000b5b4  mov     rcx, rsi
0x14000b5b7  call    _guard_dispatch_icall
0x14000b5bc  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x14000b5bf  mov     dl, 1; bool
0x14000b5c1  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x14000b5c4  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x14000b5c9  mov     edi, eax
0x14000b5cb  mov     r12d, 6E6D7377h
0x14000b5d1  mov     rax, [rbp+var_20]
0x14000b5d5  test    rax, rax
0x14000b5d8  jz      short loc_14000B603
0x14000b5da  mov     rdx, [rbp+var_18]
0x14000b5de  mov     rbx, [rdx]
0x14000b5e1  mov     [rdx], rax
0x14000b5e4  test    rbx, rbx
0x14000b5e7  jz      short loc_14000B603
0x14000b5e9  mov     rcx, rbx; this
0x14000b5ec  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000b5f1  mov     edx, r12d; Tag
0x14000b5f4  mov     rcx, rbx; P
0x14000b5f7  call    cs:__imp_ExFreePoolWithTag
0x14000b5fe  nop     dword ptr [rax+rax+00h]
0x14000b603  test    edi, edi
0x14000b605  jns     short loc_14000B631
0x14000b607  mov     rbx, [rbp+P]
0x14000b60b  test    rbx, rbx
0x14000b60e  jz      short loc_14000B62A
0x14000b610  mov     rcx, rbx; this
0x14000b613  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000b618  mov     edx, r12d; Tag
0x14000b61b  mov     rcx, rbx; P
0x14000b61e  call    cs:__imp_ExFreePoolWithTag
0x14000b625  nop     dword ptr [rax+rax+00h]
0x14000b62a  mov     eax, edi
0x14000b62c  jmp     loc_14000B75B
0x14000b631  mov     r15, [rbp+P]
0x14000b635  lea     rax, ??_7wsm_stable_path@@6B@; const wsm_stable_path::`vftable'
0x14000b63c  mov     rdx, r14; SourceString
0x14000b63f  mov     [rbp+var_20], rax
0x14000b643  lea     rcx, [rbp+var_20]; this
0x14000b647  mov     [rbp+var_18], 0
0x14000b64f  call    ?assign@wsm_stable_path@@UEAAJPEBG@Z; wsm_stable_path::assign(ushort const *)
0x14000b654  mov     rbx, [rbp+var_18]
0x14000b658  mov     edi, eax
0x14000b65a  test    eax, eax
0x14000b65c  jns     short loc_14000B69B
0x14000b65e  test    rbx, rbx
0x14000b661  jz      loc_14000B6EC
0x14000b667  mov     rcx, [rbx]; P
0x14000b66a  lea     rax, [rbx+10h]
0x14000b66e  cmp     rcx, rax
0x14000b671  jz      short loc_14000B687
0x14000b673  test    rcx, rcx
0x14000b676  jz      short loc_14000B687
0x14000b678  mov     edx, r12d; Tag
0x14000b67b  call    cs:__imp_ExFreePoolWithTag
0x14000b682  nop     dword ptr [rax+rax+00h]
0x14000b687  mov     edx, r12d; Tag
0x14000b68a  mov     rcx, rbx; P
0x14000b68d  call    cs:__imp_ExFreePoolWithTag
0x14000b694  nop     dword ptr [rax+rax+00h]
0x14000b699  jmp     short loc_14000B6EC
0x14000b69b  test    rbx, rbx
0x14000b69e  jz      short loc_14000B6A5
0x14000b6a0  mov     rdx, [rbx]
0x14000b6a3  jmp     short loc_14000B6A7
0x14000b6a5  xor     edx, edx; unsigned __int16 *
0x14000b6a7  mov     rcx, r15; this
0x14000b6aa  call    ?RemoveTrackedStablePath@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBG@Z; CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath(ushort const *)
0x14000b6af  mov     edi, eax
0x14000b6b1  test    rbx, rbx
0x14000b6b4  jz      short loc_14000B6E8
0x14000b6b6  mov     rcx, [rbx]; P
0x14000b6b9  lea     rax, [rbx+10h]
0x14000b6bd  cmp     rcx, rax
0x14000b6c0  jz      short loc_14000B6D6
0x14000b6c2  test    rcx, rcx
0x14000b6c5  jz      short loc_14000B6D6
0x14000b6c7  mov     edx, r12d; Tag
0x14000b6ca  call    cs:__imp_ExFreePoolWithTag
0x14000b6d1  nop     dword ptr [rax+rax+00h]
0x14000b6d6  mov     edx, r12d; Tag
0x14000b6d9  mov     rcx, rbx; P
0x14000b6dc  call    cs:__imp_ExFreePoolWithTag
0x14000b6e3  nop     dword ptr [rax+rax+00h]
0x14000b6e8  test    edi, edi
0x14000b6ea  jns     short loc_14000B705
0x14000b6ec  mov     r9d, edi
0x14000b6ef  lea     rdx, aCwsmtrackingco; "CWsmTrackingConfig::RemoveTrackedPath: "...
0x14000b6f6  mov     r8, r14
0x14000b6f9  xor     ecx, ecx
0x14000b6fb  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000b700  jmp     loc_14000B607
0x14000b705  mov     rdx, [rbp+P]
0x14000b709  mov     r8b, 1; bool
0x14000b70c  add     rdx, 58h ; 'X'; struct _WSM_TRACKING_CONFIG *
0x14000b710  mov     rcx, rsi; this
0x14000b713  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x14000b718  mov     ebx, eax
0x14000b71a  test    eax, eax
0x14000b71c  jns     short loc_14000B72F
0x14000b71e  mov     r8d, eax
0x14000b721  lea     rdx, aCwsmtrackingco_7; "CWsmTrackingConfig::RemoveTrackedPath: "...
0x14000b728  xor     ecx, ecx
0x14000b72a  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000b72f  mov     rdi, [rbp+P]
0x14000b733  test    rdi, rdi
0x14000b736  jz      short loc_14000B759
0x14000b738  mov     rcx, rdi; this
0x14000b73b  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000b740  mov     edx, r12d; Tag
0x14000b743  mov     rcx, rdi; P
0x14000b746  call    cs:__imp_ExFreePoolWithTag
0x14000b74d  nop     dword ptr [rax+rax+00h]
0x14000b752  jmp     short loc_14000B759
0x14000b754  mov     ebx, 0C0000225h
0x14000b759  mov     eax, ebx
0x14000b75b  lea     r11, [rsp+40h+var_s0]
0x14000b760  mov     rbx, [r11+30h]
0x14000b764  mov     rsi, [r11+40h]
0x14000b768  mov     rsp, r11
0x14000b76b  pop     r15
0x14000b76d  pop     r14
0x14000b76f  pop     r12
0x14000b771  pop     rdi
0x14000b772  pop     rbp
0x14000b773  retn
```
