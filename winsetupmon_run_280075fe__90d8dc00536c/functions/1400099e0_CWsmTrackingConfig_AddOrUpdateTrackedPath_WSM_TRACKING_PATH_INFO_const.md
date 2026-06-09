# CWsmTrackingConfig::AddOrUpdateTrackedPath(_WSM_TRACKING_PATH_INFO * const)

- ea: `0x1400099e0`
- end: `0x140009b67`
- name: `?AddOrUpdateTrackedPath@CWsmTrackingConfig@@UEAAJQEAU_WSM_TRACKING_PATH_INFO@@@Z`
- size: `391`
- prototype: `int(CWsmTrackingConfig *__hidden this, struct _WSM_TRACKING_PATH_INFO *const)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000960c`
- `0x1400099e0`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b07`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009a8e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009ab6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009b07`

## string_xrefs

- `0x140009adf`: `CWsmTrackingConfig::AddOrUpdateTrackedPath: Failed to update configuration (with path info for %ws added) (0x%08X)`
- `0x140009b44`: `CWsmTrackingConfig::AddOrUpdateTrackedPath: Failed to read configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::AddOrUpdateTrackedPath(
        CWsmTrackingConfig *this,
        struct _WSM_TRACKING_PATH_INFO *const a2)
{
  CWsmTrackingConfig *v3; // rsi
  __int64 (__fastcall **v4)(char *); // rax
  __int64 (__fastcall *v5)(char *); // rax
  struct CWsmTrackingConfig::CTrackingConfig **v6; // rbx
  struct _WSM_TRACKING_CONFIG *v7; // rax
  int Instance; // r14d
  CWsmTrackingConfig::CTrackingConfig *v9; // rbx
  PVOID v10; // rbx
  int updated; // eax
  unsigned int v13; // ebx
  PVOID v14; // rdi
  struct _WSM_TRACKING_CONFIG *v15; // rdx
  int v16; // eax
  CWsmTrackingConfig::CTrackingConfig *v17; // [rsp+20h] [rbp-48h] BYREF
  CWsmTrackingConfig::CTrackingConfig **v18; // [rsp+28h] [rbp-40h]
  __int128 v19; // [rsp+38h] [rbp-30h] BYREF
  __int128 v20; // [rsp+48h] [rbp-20h]
  PVOID P; // [rsp+A8h] [rbp+40h] BYREF

  if ( !a2 || !*(_QWORD *)a2 )
    return 3221225485LL;
  v3 = (CWsmTrackingConfig *)((char *)this - 8);
  P = 0;
  v4 = (__int64 (__fastcall **)(char *))*((_QWORD *)this - 1);
  v19 = 0;
  v5 = *v4;
  v20 = 0;
  if ( !v5((char *)this - 8) )
  {
    LODWORD(v20) = 1;
    v15 = (struct _WSM_TRACKING_CONFIG *)&v19;
    *((_QWORD *)&v20 + 1) = a2;
LABEL_18:
    v16 = CWsmTrackingConfig::Read(v3, v15, 0);
    v13 = v16;
    if ( v16 < 0 )
      WriteLog(0, "CWsmTrackingConfig::AddOrUpdateTrackedPath: Failed to read configuration (0x%08X)", v16);
    goto LABEL_13;
  }
  v6 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v17,
                                                        &P);
  v7 = (struct _WSM_TRACKING_CONFIG *)(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))v3)(v3);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v7, 1, v6);
  if ( v17 )
  {
    v9 = *v18;
    *v18 = v17;
    if ( v9 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v9);
      ExFreePoolWithTag(v9, 0x6E6D7377u);
    }
  }
  if ( Instance < 0 )
  {
    v10 = P;
    if ( P )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
      ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
    return (unsigned int)Instance;
  }
  updated = CWsmTrackingConfig::CTrackingConfig::AddOrUpdateTrackedPath((CWsmTrackingConfig::CTrackingConfig *)P, a2);
  v13 = updated;
  if ( updated >= 0 )
  {
    v15 = (struct _WSM_TRACKING_CONFIG *)((char *)P + 88);
    goto LABEL_18;
  }
  WriteLog(
    0,
    "CWsmTrackingConfig::AddOrUpdateTrackedPath: Failed to update configuration (with path info for %ws added) (0x%08X)",
    *(_QWORD *)a2,
    (unsigned int)updated);
LABEL_13:
  v14 = P;
  if ( P )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
    ExFreePoolWithTag(v14, 0x6E6D7377u);
  }
  return v13;
}

```

## disassembly

```asm
0x1400099e0  push    rbp
0x1400099e2  push    rbx
0x1400099e3  push    rsi
0x1400099e4  push    rdi
0x1400099e5  push    r14
0x1400099e7  push    r15
0x1400099e9  mov     rbp, rsp
0x1400099ec  sub     rsp, 68h
0x1400099f0  mov     rdi, rdx
0x1400099f3  test    rdx, rdx
0x1400099f6  jz      loc_140009B54
0x1400099fc  cmp     qword ptr [rdx], 0
0x140009a00  jz      loc_140009B54
0x140009a06  lea     rsi, [rcx-8]
0x140009a0a  mov     [rbp+P], 0
0x140009a12  mov     rax, [rsi]
0x140009a15  xorps   xmm0, xmm0
0x140009a18  mov     rcx, rsi
0x140009a1b  movups  [rbp+var_30], xmm0
0x140009a1f  mov     rax, [rax]
0x140009a22  movups  [rbp+var_20], xmm0
0x140009a26  call    _guard_dispatch_icall
0x140009a2b  mov     r15d, 6E6D7377h
0x140009a31  test    rax, rax
0x140009a34  jz      loc_140009B21
0x140009a3a  lea     rdx, [rbp+P]
0x140009a3e  lea     rcx, [rbp+var_48]
0x140009a42  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x140009a47  mov     rcx, [rsi]
0x140009a4a  mov     rbx, rax
0x140009a4d  mov     rax, [rcx]
0x140009a50  mov     rcx, rsi
0x140009a53  call    _guard_dispatch_icall
0x140009a58  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x140009a5b  mov     dl, 1; bool
0x140009a5d  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x140009a60  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x140009a65  mov     r14d, eax
0x140009a68  mov     rax, [rbp+var_48]
0x140009a6c  test    rax, rax
0x140009a6f  jz      short loc_140009A9A
0x140009a71  mov     rdx, [rbp+var_40]
0x140009a75  mov     rbx, [rdx]
0x140009a78  mov     [rdx], rax
0x140009a7b  test    rbx, rbx
0x140009a7e  jz      short loc_140009A9A
0x140009a80  mov     rcx, rbx; this
0x140009a83  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140009a88  mov     edx, r15d; Tag
0x140009a8b  mov     rcx, rbx; P
0x140009a8e  call    cs:__imp_ExFreePoolWithTag
0x140009a95  nop     dword ptr [rax+rax+00h]
0x140009a9a  test    r14d, r14d
0x140009a9d  jns     short loc_140009ACA
0x140009a9f  mov     rbx, [rbp+P]
0x140009aa3  test    rbx, rbx
0x140009aa6  jz      short loc_140009AC2
0x140009aa8  mov     rcx, rbx; this
0x140009aab  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140009ab0  mov     edx, r15d; Tag
0x140009ab3  mov     rcx, rbx; P
0x140009ab6  call    cs:__imp_ExFreePoolWithTag
0x140009abd  nop     dword ptr [rax+rax+00h]
0x140009ac2  mov     eax, r14d
0x140009ac5  jmp     loc_140009B59
0x140009aca  mov     rcx, [rbp+P]; this
0x140009ace  mov     rdx, rdi; struct _WSM_TRACKING_PATH_INFO *
0x140009ad1  call    ?AddOrUpdateTrackedPath@CTrackingConfig@CWsmTrackingConfig@@QEAAJQEAU_WSM_TRACKING_PATH_INFO@@@Z; CWsmTrackingConfig::CTrackingConfig::AddOrUpdateTrackedPath(_WSM_TRACKING_PATH_INFO * const)
0x140009ad6  mov     ebx, eax
0x140009ad8  test    eax, eax
0x140009ada  jns     short loc_140009B17
0x140009adc  mov     r8, [rdi]
0x140009adf  lea     rdx, aCwsmtrackingco_1; "CWsmTrackingConfig::AddOrUpdateTrackedP"...
0x140009ae6  mov     r9d, eax
0x140009ae9  xor     ecx, ecx
0x140009aeb  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x140009af0  mov     rdi, [rbp+P]
0x140009af4  test    rdi, rdi
0x140009af7  jz      short loc_140009B13
0x140009af9  mov     rcx, rdi; this
0x140009afc  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140009b01  mov     edx, r15d; Tag
0x140009b04  mov     rcx, rdi; P
0x140009b07  call    cs:__imp_ExFreePoolWithTag
0x140009b0e  nop     dword ptr [rax+rax+00h]
0x140009b13  mov     eax, ebx
0x140009b15  jmp     short loc_140009B59
0x140009b17  mov     rdx, [rbp+P]
0x140009b1b  add     rdx, 58h ; 'X'
0x140009b1f  jmp     short loc_140009B30
0x140009b21  mov     dword ptr [rbp+var_20], 1
0x140009b28  lea     rdx, [rbp+var_30]; struct _WSM_TRACKING_CONFIG *
0x140009b2c  mov     qword ptr [rbp+var_20+8], rdi
0x140009b30  xor     r8d, r8d; bool
0x140009b33  mov     rcx, rsi; this
0x140009b36  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x140009b3b  mov     ebx, eax
0x140009b3d  test    eax, eax
0x140009b3f  jns     short loc_140009AF0
0x140009b41  mov     r8d, eax
0x140009b44  lea     rdx, aCwsmtrackingco_4; "CWsmTrackingConfig::AddOrUpdateTrackedP"...
0x140009b4b  xor     ecx, ecx
0x140009b4d  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x140009b52  jmp     short loc_140009AF0
0x140009b54  mov     eax, 0C000000Dh
0x140009b59  add     rsp, 68h
0x140009b5d  pop     r15
0x140009b5f  pop     r14
0x140009b61  pop     rdi
0x140009b62  pop     rsi
0x140009b63  pop     rbx
0x140009b64  pop     rbp
0x140009b65  retn
```
