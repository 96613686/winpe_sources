# ??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z

- ea: `0x140008b58`
- end: `0x140008baa`
- name: `??$out_ptr@XV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingOverrideInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingOverrideInfo@CWsmTrackingConfig@@@utl@@@0@@Z`
- size: `82`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140009b70`
- `0x14000adb8`
- `0x14000cad0`

## callees

- `0x140008b58`
- `0x140009120`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008b8f`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b8f`

## pseudocode

```c
_QWORD *__fastcall utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingOverrideInfo,utl::default_delete<CWsmTrackingConfig::CTrackingOverrideInfo>>,>(
        _QWORD *a1,
        void ****a2)
{
  void ***v2; // rdi

  v2 = *a2;
  *a1 = 0;
  a1[1] = a2;
  *a2 = 0;
  if ( v2 )
  {
    CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(v2);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  return a1;
}

```

## disassembly

```asm
0x140008b58  mov     [rsp+arg_0], rbx
0x140008b5d  push    rdi
0x140008b5e  sub     rsp, 20h
0x140008b62  mov     rdi, [rdx]
0x140008b65  mov     rbx, rcx
0x140008b68  mov     qword ptr [rcx], 0
0x140008b6f  mov     [rcx+8], rdx
0x140008b73  mov     qword ptr [rdx], 0
0x140008b7a  test    rdi, rdi
0x140008b7d  jz      short loc_140008B9B
0x140008b7f  mov     rcx, rdi; this
0x140008b82  call    ??1CTrackingOverrideInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingOverrideInfo::~CTrackingOverrideInfo(void)
0x140008b87  mov     edx, 6E6D7377h; Tag
0x140008b8c  mov     rcx, rdi; P
0x140008b8f  call    cs:__imp_ExFreePoolWithTag
0x140008b96  nop     dword ptr [rax+rax+00h]
0x140008b9b  mov     rax, rbx
0x140008b9e  mov     rbx, [rsp+28h+arg_0]
0x140008ba3  add     rsp, 20h
0x140008ba7  pop     rdi
0x140008ba8  retn
```
