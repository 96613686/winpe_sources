# CWsmTrackingConfig::RemoveTrackedStablePath(ushort const *)

- ea: `0x14000b970`
- end: `0x14000bae1`
- name: `?RemoveTrackedStablePath@CWsmTrackingConfig@@UEAAJPEBG@Z`
- size: `369`
- prototype: `__int64 __fastcall(CWsmTrackingConfig *__hidden this, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `8`
- tags: `registry_config, installer_update`

## callees

- `0x140008b00`
- `0x140009018`
- `0x14000a728`
- `0x14000b1b4`
- `0x14000b77c`
- `0x14000b970`
- `0x14000f684`
- `0x14000f9e0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bab8`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba11`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000ba39`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000bab8`

## string_xrefs

- `0x14000ba62`: `CWsmTrackingConfig::RemoveTrackedStablePath: Failed to update configuration (with %ws removed) (0x%08X)`
- `0x14000ba92`: `CWsmTrackingConfig::RemoveTrackedStablePath: Failed to read new buffer into configuration (0x%08X)`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::RemoveTrackedStablePath(CWsmTrackingConfig *this, const unsigned __int16 *a2)
{
  struct CWsmTrackingConfig::CTrackingConfig **v5; // rbx
  struct _WSM_TRACKING_CONFIG *v6; // rax
  int Instance; // edi
  CWsmTrackingConfig::CTrackingConfig *v8; // rbx
  PVOID v9; // rbx
  int v10; // eax
  int v11; // eax
  unsigned int v12; // ebx
  PVOID v13; // rdi
  CWsmTrackingConfig::CTrackingConfig *v14; // [rsp+20h] [rbp-38h] BYREF
  CWsmTrackingConfig::CTrackingConfig **v15; // [rsp+28h] [rbp-30h]
  PVOID P; // [rsp+68h] [rbp+10h] BYREF

  if ( !a2 )
    return 3221225485LL;
  if ( !(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))this)(this) )
    return (unsigned int)-1073741275;
  P = 0;
  v5 = (struct CWsmTrackingConfig::CTrackingConfig **)utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
                                                        &v14,
                                                        &P);
  v6 = (struct _WSM_TRACKING_CONFIG *)(**(__int64 (__fastcall ***)(CWsmTrackingConfig *))this)(this);
  Instance = CWsmTrackingConfig::CTrackingConfig::CreateInstance(v6, 1, v5);
  if ( v14 )
  {
    v8 = *v15;
    *v15 = v14;
    if ( v8 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v8);
      ExFreePoolWithTag(v8, 0x6E6D7377u);
    }
  }
  if ( Instance < 0 )
    goto LABEL_8;
  v10 = CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath((CWsmTrackingConfig::CTrackingConfig *)P, a2);
  Instance = v10;
  if ( v10 >= 0 )
  {
    v11 = CWsmTrackingConfig::Read(this, (struct _WSM_TRACKING_CONFIG *const)((char *)P + 88), 1);
    v12 = v11;
    if ( v11 < 0 )
      WriteLog(
        0,
        "CWsmTrackingConfig::RemoveTrackedStablePath: Failed to read new buffer into configuration (0x%08X)",
        v11);
    v13 = P;
    if ( P )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((CWsmTrackingConfig::CTrackingConfig *)P);
      ExFreePoolWithTag(v13, 0x6E6D7377u);
    }
    return v12;
  }
  WriteLog(
    0,
    "CWsmTrackingConfig::RemoveTrackedStablePath: Failed to update configuration (with %ws removed) (0x%08X)",
    a2,
    (unsigned int)v10);
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
0x14000b970  mov     [rsp+arg_0], rbx
0x14000b975  mov     [rsp+arg_10], rbp
0x14000b97a  push    rsi
0x14000b97b  push    rdi
0x14000b97c  push    r14
0x14000b97e  sub     rsp, 40h
0x14000b982  mov     rbp, rdx
0x14000b985  mov     rsi, rcx
0x14000b988  test    rdx, rdx
0x14000b98b  jnz     short loc_14000B997
0x14000b98d  mov     eax, 0C000000Dh
0x14000b992  jmp     loc_14000BACD
0x14000b997  mov     rax, [rcx]
0x14000b99a  mov     rax, [rax]
0x14000b99d  call    _guard_dispatch_icall
0x14000b9a2  test    rax, rax
0x14000b9a5  jz      loc_14000BAC6
0x14000b9ab  lea     rdx, [rsp+58h+P]
0x14000b9b0  mov     [rsp+58h+P], 0
0x14000b9b9  lea     rcx, [rsp+58h+var_38]
0x14000b9be  call    ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z
0x14000b9c3  mov     rcx, [rsi]
0x14000b9c6  mov     rbx, rax
0x14000b9c9  mov     rax, [rcx]
0x14000b9cc  mov     rcx, rsi
0x14000b9cf  call    _guard_dispatch_icall
0x14000b9d4  mov     r8, rbx; struct CWsmTrackingConfig::CTrackingConfig **
0x14000b9d7  mov     dl, 1; bool
0x14000b9d9  mov     rcx, rax; struct _WSM_TRACKING_CONFIG *
0x14000b9dc  call    ?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z; CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)
0x14000b9e1  mov     edi, eax
0x14000b9e3  mov     r14d, 6E6D7377h
0x14000b9e9  mov     rax, [rsp+58h+var_38]
0x14000b9ee  test    rax, rax
0x14000b9f1  jz      short loc_14000BA1D
0x14000b9f3  mov     rdx, [rsp+58h+var_30]
0x14000b9f8  mov     rbx, [rdx]
0x14000b9fb  mov     [rdx], rax
0x14000b9fe  test    rbx, rbx
0x14000ba01  jz      short loc_14000BA1D
0x14000ba03  mov     rcx, rbx; this
0x14000ba06  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000ba0b  mov     edx, r14d; Tag
0x14000ba0e  mov     rcx, rbx; P
0x14000ba11  call    cs:__imp_ExFreePoolWithTag
0x14000ba18  nop     dword ptr [rax+rax+00h]
0x14000ba1d  test    edi, edi
0x14000ba1f  jns     short loc_14000BA4C
0x14000ba21  mov     rbx, [rsp+58h+P]
0x14000ba26  test    rbx, rbx
0x14000ba29  jz      short loc_14000BA45
0x14000ba2b  mov     rcx, rbx; this
0x14000ba2e  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000ba33  mov     edx, r14d; Tag
0x14000ba36  mov     rcx, rbx; P
0x14000ba39  call    cs:__imp_ExFreePoolWithTag
0x14000ba40  nop     dword ptr [rax+rax+00h]
0x14000ba45  mov     eax, edi
0x14000ba47  jmp     loc_14000BACD
0x14000ba4c  mov     rcx, [rsp+58h+P]; this
0x14000ba51  mov     rdx, rbp; unsigned __int16 *
0x14000ba54  call    ?RemoveTrackedStablePath@CTrackingConfig@CWsmTrackingConfig@@QEAAJPEBG@Z; CWsmTrackingConfig::CTrackingConfig::RemoveTrackedStablePath(ushort const *)
0x14000ba59  mov     edi, eax
0x14000ba5b  test    eax, eax
0x14000ba5d  jns     short loc_14000BA75
0x14000ba5f  mov     r9d, eax
0x14000ba62  lea     rdx, aCwsmtrackingco_0; "CWsmTrackingConfig::RemoveTrackedStable"...
0x14000ba69  mov     r8, rbp
0x14000ba6c  xor     ecx, ecx
0x14000ba6e  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000ba73  jmp     short loc_14000BA21
0x14000ba75  mov     rdx, [rsp+58h+P]
0x14000ba7a  mov     r8b, 1; bool
0x14000ba7d  add     rdx, 58h ; 'X'; struct _WSM_TRACKING_CONFIG *
0x14000ba81  mov     rcx, rsi; this
0x14000ba84  call    ?Read@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::Read(_WSM_TRACKING_CONFIG * const,bool)
0x14000ba89  mov     ebx, eax
0x14000ba8b  test    eax, eax
0x14000ba8d  jns     short loc_14000BAA0
0x14000ba8f  mov     r8d, eax
0x14000ba92  lea     rdx, aCwsmtrackingco_10; "CWsmTrackingConfig::RemoveTrackedStable"...
0x14000ba99  xor     ecx, ecx
0x14000ba9b  call    ?WriteLog@@YAXW4LogLevel@@PEBDZZ; WriteLog(LogLevel,char const *,...)
0x14000baa0  mov     rdi, [rsp+58h+P]
0x14000baa5  test    rdi, rdi
0x14000baa8  jz      short loc_14000BACB
0x14000baaa  mov     rcx, rdi; this
0x14000baad  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000bab2  mov     edx, r14d; Tag
0x14000bab5  mov     rcx, rdi; P
0x14000bab8  call    cs:__imp_ExFreePoolWithTag
0x14000babf  nop     dword ptr [rax+rax+00h]
0x14000bac4  jmp     short loc_14000BACB
0x14000bac6  mov     ebx, 0C0000225h
0x14000bacb  mov     eax, ebx
0x14000bacd  mov     rbx, [rsp+58h+arg_0]
0x14000bad2  mov     rbp, [rsp+58h+arg_10]
0x14000bad7  add     rsp, 40h
0x14000badb  pop     r14
0x14000badd  pop     rdi
0x14000bade  pop     rsi
0x14000badf  retn
```
