# CWsmTrackingConfig::CTrackingConfig::CreateInstance(_WSM_TRACKING_CONFIG * const,bool,CWsmTrackingConfig::CTrackingConfig * *)

- ea: `0x14000a728`
- end: `0x14000a79b`
- name: `?CreateInstance@CTrackingConfig@CWsmTrackingConfig@@SAJQEAU_WSM_TRACKING_CONFIG@@_NPEAPEAV12@@Z`
- size: `115`
- prototype: `__int64 __fastcall(struct _WSM_TRACKING_CONFIG *const, bool, struct CWsmTrackingConfig::CTrackingConfig **)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1400099e0`
- `0x140009ee0`
- `0x14000a300`
- `0x14000b1b4`
- `0x14000b550`
- `0x14000b970`
- `0x14000bdf0`

## callees

- `0x14000899c`
- `0x140009018`
- `0x14000a728`
- `0x14000ab4c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000a77e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000a77e`

## pseudocode

```c
__int64 __fastcall CWsmTrackingConfig::CTrackingConfig::CreateInstance(
        struct _WSM_TRACKING_CONFIG *const a1,
        bool a2,
        struct CWsmTrackingConfig::CTrackingConfig **a3)
{
  struct CWsmTrackingConfig::CTrackingConfig *v6; // rbx
  __int64 result; // rax
  unsigned int v8; // edi
  PVOID P; // [rsp+68h] [rbp+20h] BYREF

  utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(&P);
  v6 = (struct CWsmTrackingConfig::CTrackingConfig *)P;
  if ( !P )
    return 3221225626LL;
  result = CWsmTrackingConfig::CTrackingConfig::Initialize((CWsmTrackingConfig::CTrackingConfig *)P, a1, a2);
  v8 = result;
  if ( (int)result >= 0 )
  {
    *a3 = v6;
  }
  else
  {
    if ( v6 )
    {
      CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig((void ***)v6);
      ExFreePoolWithTag(v6, 0x6E6D7377u);
    }
    return v8;
  }
  return result;
}

```

## disassembly

```asm
0x14000a728  push    rbx
0x14000a72a  push    rbp
0x14000a72b  push    rsi
0x14000a72c  push    rdi
0x14000a72d  sub     rsp, 28h
0x14000a731  mov     rbp, rcx
0x14000a734  mov     rsi, r8
0x14000a737  lea     rcx, [rsp+48h+P]
0x14000a73c  mov     dil, dl
0x14000a73f  call    ??$make_unique@VCTrackingConfig@CWsmTrackingConfig@@$$V$0A@@utl@@YA?AV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@XZ; utl::make_unique<CWsmTrackingConfig::CTrackingConfig,,0>(void)
0x14000a744  mov     rbx, [rsp+48h+P]
0x14000a749  test    rbx, rbx
0x14000a74c  jnz     short loc_14000A755
0x14000a74e  mov     eax, 0C000009Ah
0x14000a753  jmp     short loc_14000A791
0x14000a755  mov     r8b, dil; bool
0x14000a758  mov     rdx, rbp; struct _WSM_TRACKING_CONFIG *
0x14000a75b  mov     rcx, rbx; this
0x14000a75e  call    ?Initialize@CTrackingConfig@CWsmTrackingConfig@@IEAAJQEAU_WSM_TRACKING_CONFIG@@_N@Z; CWsmTrackingConfig::CTrackingConfig::Initialize(_WSM_TRACKING_CONFIG * const,bool)
0x14000a763  mov     edi, eax
0x14000a765  test    eax, eax
0x14000a767  jns     short loc_14000A78E
0x14000a769  test    rbx, rbx
0x14000a76c  jz      short loc_14000A78A
0x14000a76e  mov     rcx, rbx; this
0x14000a771  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000a776  mov     edx, 6E6D7377h; Tag
0x14000a77b  mov     rcx, rbx; P
0x14000a77e  call    cs:__imp_ExFreePoolWithTag
0x14000a785  nop     dword ptr [rax+rax+00h]
0x14000a78a  mov     eax, edi
0x14000a78c  jmp     short loc_14000A791
0x14000a78e  mov     [rsi], rbx
0x14000a791  add     rsp, 28h
0x14000a795  pop     rdi
0x14000a796  pop     rsi
0x14000a797  pop     rbp
0x14000a798  pop     rbx
0x14000a799  retn
```
