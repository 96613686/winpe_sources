# CWsmTrackingConfig::~CWsmTrackingConfig(void)

- ea: `0x140009300`
- end: `0x140009362`
- name: `??1CWsmTrackingConfig@@QEAA@XZ`
- size: `98`
- prototype: `void __fastcall(CWsmTrackingConfig *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000a598`
- `0x14000b500`

## callees

- `0x140009018`
- `0x140009300`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140009326`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000934a`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009326`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000934a`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::~CWsmTrackingConfig(CWsmTrackingConfig *this)
{
  void *v1; // rdi
  void *v3; // rcx

  v1 = (void *)*((_QWORD *)this + 5);
  if ( v1 )
  {
    CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(*((void ****)this + 5));
    ExFreePoolWithTag(v1, 0x6E6D7377u);
  }
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 != (void *)-1LL )
  {
    *((_QWORD *)this + 3) = v3;
    if ( v3 )
      ExFreePoolWithTag(v3, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x140009300  mov     [rsp+arg_0], rbx
0x140009305  push    rdi
0x140009306  sub     rsp, 20h
0x14000930a  mov     rdi, [rcx+28h]
0x14000930e  mov     rbx, rcx
0x140009311  test    rdi, rdi
0x140009314  jz      short loc_140009332
0x140009316  mov     rcx, rdi; this
0x140009319  call    ??1CTrackingConfig@CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::CTrackingConfig::~CTrackingConfig(void)
0x14000931e  mov     edx, 6E6D7377h; Tag
0x140009323  mov     rcx, rdi; P
0x140009326  call    cs:__imp_ExFreePoolWithTag
0x14000932d  nop     dword ptr [rax+rax+00h]
0x140009332  mov     rcx, [rbx+10h]; P
0x140009336  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x14000933a  jz      short loc_140009356
0x14000933c  mov     [rbx+18h], rcx
0x140009340  test    rcx, rcx
0x140009343  jz      short loc_140009356
0x140009345  mov     edx, 6E6D7377h; Tag
0x14000934a  call    cs:__imp_ExFreePoolWithTag
0x140009351  nop     dword ptr [rax+rax+00h]
0x140009356  mov     rbx, [rsp+28h+arg_0]
0x14000935b  add     rsp, 20h
0x14000935f  pop     rdi
0x140009360  retn
```
