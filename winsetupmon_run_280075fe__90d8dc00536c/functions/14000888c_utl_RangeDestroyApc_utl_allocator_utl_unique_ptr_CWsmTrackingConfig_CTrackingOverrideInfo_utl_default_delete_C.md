# utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>> &,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>> *,unsigned __int64)

- ea: `0x14000888c`
- end: `0x1400088e4`
- name: `??$_RangeDestroyApc@V?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@utl@@@utl@@YAXAEAV?$allocator@V?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@@0@PEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@_K@Z`
- size: `88`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400091cc`
- `0x14000b414`
- `0x14000c0c0`
- `0x14000d174`

## callees

- `0x14000888c`
- `0x140009120`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400088c2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400088c2`

## pseudocode

```c
void __fastcall utl::_RangeDestroyApc<utl::allocator<utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>>>(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rbx
  void *v5; // rdi

  if ( a3 )
  {
    v3 = a3;
    do
    {
      --v3;
      v5 = *(void **)(a2 + 8 * v3);
      if ( v5 )
      {
        CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(*(void ****)(a2 + 8 * v3));
        ExFreePoolWithTag(v5, 0x6E6D7377u);
      }
    }
    while ( v3 );
  }
}

```

## disassembly

```asm
0x14000888c  test    r8, r8
0x14000888f  jz      short locret_1400088E2
0x140008891  mov     [rsp+arg_0], rbx
0x140008896  mov     [rsp+arg_8], rsi
0x14000889b  push    rdi
0x14000889c  sub     rsp, 20h
0x1400088a0  mov     rbx, r8
0x1400088a3  mov     rsi, rdx
0x1400088a6  dec     rbx
0x1400088a9  mov     rdi, [rsi+rbx*8]
0x1400088ad  test    rdi, rdi
0x1400088b0  jz      short loc_1400088CE
0x1400088b2  mov     rcx, rdi; this
0x1400088b5  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x1400088ba  mov     edx, 6E6D7377h; Tag
0x1400088bf  mov     rcx, rdi; P
0x1400088c2  call    cs:__imp_ExFreePoolWithTag
0x1400088c9  nop     dword ptr [rax+rax+00h]
0x1400088ce  test    rbx, rbx
0x1400088d1  jnz     short loc_1400088A6
0x1400088d3  mov     rbx, [rsp+28h+arg_0]
0x1400088d8  mov     rsi, [rsp+28h+arg_8]
0x1400088dd  add     rsp, 20h
0x1400088e1  pop     rdi
0x1400088e2  retn
```
