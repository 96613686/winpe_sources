# ??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z

- ea: `0x140008bb0`
- end: `0x140008c02`
- name: `??$out_ptr@XV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingPathInfo@CWsmTrackingConfig@@U?$default_delete@VCTrackingPathInfo@CWsmTrackingConfig@@@utl@@@0@@Z`
- size: `82`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000960c`
- `0x14000a0fc`
- `0x14000ab4c`
- `0x14000c6f0`

## callees

- `0x140008bb0`
- `0x1400091cc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008be7`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008be7`

## pseudocode

```c
_QWORD *__fastcall utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingPathInfo,utl::default_delete<CWsmTrackingConfig::CTrackingPathInfo>>,>(
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
    CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(v2);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  return a1;
}

```

## disassembly

```asm
0x140008bb0  mov     [rsp+arg_0], rbx
0x140008bb5  push    rdi
0x140008bb6  sub     rsp, 20h
0x140008bba  mov     rdi, [rdx]
0x140008bbd  mov     rbx, rcx
0x140008bc0  mov     qword ptr [rcx], 0
0x140008bc7  mov     [rcx+8], rdx
0x140008bcb  mov     qword ptr [rdx], 0
0x140008bd2  test    rdi, rdi
0x140008bd5  jz      short loc_140008BF3
0x140008bd7  mov     rcx, rdi; this
0x140008bda  call    ??1CTrackingPathInfo@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingPathInfo::~CTrackingPathInfo(void)
0x140008bdf  mov     edx, 6E6D7377h; Tag
0x140008be4  mov     rcx, rdi; P
0x140008be7  call    cs:__imp_ExFreePoolWithTag
0x140008bee  nop     dword ptr [rax+rax+00h]
0x140008bf3  mov     rax, rbx
0x140008bf6  mov     rbx, [rsp+28h+arg_0]
0x140008bfb  add     rsp, 20h
0x140008bff  pop     rdi
0x140008c00  retn
```
