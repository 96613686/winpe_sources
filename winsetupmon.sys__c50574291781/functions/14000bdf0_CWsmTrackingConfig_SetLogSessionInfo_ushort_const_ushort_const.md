# CWsmTrackingConfig::SetLogSessionInfo(ushort const *,ushort const *)

- ea: `0x14000bdf0`
- end: `0x14000bf37`
- name: `?SetLogSessionInfo@CWsmTrackingConfig@@UEAAJPEBG0@Z`
- size: `327`
- prototype: `__int64 __fastcall(CWsmTrackingConfig *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callers

- `0x14000bf40`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000bcdc`
- `0x14000bdf0`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000be92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf0f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000be92`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bf0f`

## string_xrefs

- `0x14000beb7`: `CWsmTrackingConfig::SetLogSessionInfo: Failed to update configuration (with session info) (0x%08X)`
- `0x14000bee7`: `CWsmTrackingConfig::SetLogSessionInfo: Failed to read configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::SetLogSessionInfo(
        __int64 (__fastcall ***this)(CWsmTrackingConfig *),
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 (__fastcall **v3)(CWsmTrackingConfig *); // rax
  struct CWsmTrackingConfig::CTrackingConfig **v7; // rbx
  struct _WSM_TRACKING_CONFIG *v8; // rax
  int Instance; // edi
  CWsmTrackingConfig::CTrackingConfig *v10; // rbx
  struct _WSM_TRACKING_CONFIG *v11; // rdx
  PVOID v12; // rbx
  CWsmTrackingConfig::CTrackingConfig *v14; // [rsp+20h] [rbp-40h] BYREF
  CWsmTrackingConfig::CTrackingConfig **v15; // [rsp+28h] [rbp-38h]
  _OWORD v16[2]; // [rsp+38h] [rbp-28h] BYREF
  PVOID P; // [rsp+90h] [rbp+30h] BYREF

  v3 = *this;
  P = 0;
  memset(v16, 0, sizeof(v16));
  if ( !(*v3)((CWsmTrackingConfig *)this) )
  {
    *(_QWORD *)&v16[0] = a2;
    v11 = (struct _WSM_TRACKING_CONFIG *)v16;
    *((_QWORD *)&v16[0] + 1) = a3;
LABEL_10:
    Instance = CWsmTrackingConfig::Read((CWsmTrackingConfig *)this, v11, 1);
    if ( Instance < 0 )
      WriteLog(
        0,
        "CWsmTrackingConfig::SetLogSessionInfo: Failed to read configuration (0x%08X)",
        (unsigned int)Instance);
    goto LABEL_12;
  }
  v7 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v14,
                                                        &P);
  v8 = (struct _WSM_TRACKING_CONFIG *)(**this)((CWsmTrackingConfig *)this);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v8, 1, v7);
  if ( v14 )
  {
    v10 = *v15;
    *v15 = v14;
    if ( v10 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v10);
      ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
  }
  if ( Instance >= 0 )
  {
    Instance = CWsmTrackingConfig::CTrackingConfig::SetLogSessionInfo((CWsmTrackingConfig::CTrackingConfig *)P, a2, a3);
    if ( Instance < 0 )
    {
      WriteLog(
        0,
        "CWsmTrackingConfig::SetLogSessionInfo: Failed to update configuration (with session info) (0x%08X)",
        (unsigned int)Instance);
      goto LABEL_12;
    }
    v11 = (struct _WSM_TRACKING_CONFIG *)((char *)P + 88);
    goto LABEL_10;
  }
LABEL_12:
  v12 = P;
  if ( P )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
    ExFreePoolWithTag(v12, 0x6E6D7377u);
  }
  return (unsigned int)Instance;
}

```

## disassembly

```asm
0x14000bdf0  mov     [rsp-28h+arg_8], rbx
0x14000bdf5  mov     [rsp-28h+arg_10], rsi
0x14000bdfa  push    rbp
0x14000bdfb  push    rdi
0x14000bdfc  push    r12
0x14000bdfe  push    r14
0x14000be00  push    r15
0x14000be02  mov     rbp, rsp
0x14000be05  sub     rsp, 60h
0x14000be09  mov     rax, [rcx]
0x14000be0c  xorps   xmm0, xmm0
0x14000be0f  mov     r14, r8
0x14000be12  mov     [rbp+P], 0
0x14000be1a  mov     r15, rdx
0x14000be1d  mov     rsi, rcx
0x14000be20  movups  [rbp+var_28], xmm0
0x14000be24  mov     rax, [rax]
0x14000be27  movups  [rbp+var_18], xmm0
0x14000be2b  call    _guard_dispatch_icall
0x14000be30  mov     r12d, 6E6D7377h
0x14000be36  test    rax, rax
0x14000be39  jz      loc_14000BECA
0x14000be3f  lea     rdx, [rbp+P]
0x14000be43  lea     rcx, [rbp+var_40]
0x14000be47  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000be4c  mov     rcx, [rsi]
0x14000be4f  mov     rbx, rax
0x14000be52  mov     rax, [rcx]
0x14000be55  mov     rcx, rsi
0x14000be58  call    _guard_dispatch_icall
0x14000be5d  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x14000be60  mov     dl, 1; bool
0x14000be62  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x14000be65  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x14000be6a  mov     edi, eax
0x14000be6c  mov     rax, [rbp+var_40]
0x14000be70  test    rax, rax
0x14000be73  jz      short loc_14000BE9E
0x14000be75  mov     rdx, [rbp+var_38]
0x14000be79  mov     rbx, [rdx]
0x14000be7c  mov     [rdx], rax
0x14000be7f  test    rbx, rbx
0x14000be82  jz      short loc_14000BE9E
0x14000be84  mov     rcx, rbx; this
0x14000be87  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000be8c  mov     edx, r12d; Tag
0x14000be8f  mov     rcx, rbx; P
0x14000be92  call    cs:__imp_ExFreePoolWithTag
0x14000be99  nop     dword ptr [rax+rax+00h]
0x14000be9e  test    edi, edi
0x14000bea0  js      short loc_14000BEF8
0x14000bea2  mov     rcx, [rbp+P]; this
0x14000bea6  mov     r8, r14; unsigned __int16 *
0x14000bea9  mov     rdx, r15; unsigned __int16 *
0x14000beac  call    ?SetLogSessionInfo@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBG0@Z; CWsmTrackingConfig::CTrackingConfig::SetLogSessionInfo(ushort const *,ushort const *)
0x14000beb1  mov     edi, eax
0x14000beb3  test    eax, eax
0x14000beb5  jns     short loc_14000BEC0
0x14000beb7  lea     rdx, aCwsmtrackingco_9; "CWsmTrackingConfig::SetLogSessionInfo: "...
0x14000bebe  jmp     short loc_14000BEEE
0x14000bec0  mov     rdx, [rbp+P]
0x14000bec4  add     rdx, 58h ; 'X'
0x14000bec8  jmp     short loc_14000BED6
0x14000beca  mov     qword ptr [rbp+var_28], r15
0x14000bece  lea     rdx, [rbp+var_28]; struct _WSM_TRACKING_CONFIG *
0x14000bed2  mov     qword ptr [rbp+var_28+8], r14
0x14000bed6  mov     r8b, 1; bool
0x14000bed9  mov     rcx, rsi; this
0x14000bedc  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x14000bee1  mov     edi, eax
0x14000bee3  test    eax, eax
0x14000bee5  jns     short loc_14000BEF8
0x14000bee7  lea     rdx, aCwsmtrackingco_2; "CWsmTrackingConfig::SetLogSessionInfo: "...
0x14000beee  mov     r8d, edi
0x14000bef1  xor     ecx, ecx
0x14000bef3  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000bef8  mov     rbx, [rbp+P]
0x14000befc  test    rbx, rbx
0x14000beff  jz      short loc_14000BF1B
0x14000bf01  mov     rcx, rbx; this
0x14000bf04  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000bf09  mov     edx, r12d; Tag
0x14000bf0c  mov     rcx, rbx; P
0x14000bf0f  call    cs:__imp_ExFreePoolWithTag
0x14000bf16  nop     dword ptr [rax+rax+00h]
0x14000bf1b  lea     r11, [rsp+60h+var_s0]
0x14000bf20  mov     eax, edi
0x14000bf22  mov     rbx, [r11+38h]
0x14000bf26  mov     rsi, [r11+40h]
0x14000bf2a  mov     rsp, r11
0x14000bf2d  pop     r15
0x14000bf2f  pop     r14
0x14000bf31  pop     r12
0x14000bf33  pop     rdi
0x14000bf34  pop     rbp
0x14000bf35  retn
```
