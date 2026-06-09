# ??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z

- ea: `0x140008b00`
- end: `0x140008b52`
- name: `??$out_ptr@XV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@utl@@$$V@utl@@YA?A_PAEAV?$unique_ptr@VCTrackingConfig@CWsmTrackingConfig@@U?$default_delete@VCTrackingConfig@CWsmTrackingConfig@@@utl@@@0@@Z`
- size: `82`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
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

- `0x140008b00`
- `0x140009018`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140008b37`
- `ntoskrnl!ExFreePoolWithTag` at `0x140008b37`

## pseudocode

```c
_QWORD *__fastcall utl::out_ptr<void,utl::unique_ptr<CWsmTrackingConfig::CTrackingConfig,utl::default_delete<CWsmTrackingConfig::CTrackingConfig>>,>(
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
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(v2);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  return a1;
}

```

## disassembly

```asm
0x140008b00  mov     [rsp+arg_0], rbx
0x140008b05  push    rdi
0x140008b06  sub     rsp, 20h
0x140008b0a  mov     rdi, [rdx]
0x140008b0d  mov     rbx, rcx
0x140008b10  mov     qword ptr [rcx], 0
0x140008b17  mov     [rcx+8], rdx
0x140008b1b  mov     qword ptr [rdx], 0
0x140008b22  test    rdi, rdi
0x140008b25  jz      short loc_140008B43
0x140008b27  mov     rcx, rdi; this
0x140008b2a  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x140008b2f  mov     edx, 6E6D7377h; Tag
0x140008b34  mov     rcx, rdi; P
0x140008b37  call    cs:__imp_ExFreePoolWithTag
0x140008b3e  nop     dword ptr [rax+rax+00h]
0x140008b43  mov     rax, rbx
0x140008b46  mov     rbx, [rsp+28h+arg_0]
0x140008b4b  add     rsp, 20h
0x140008b4f  pop     rdi
0x140008b50  retn
```
