# CWsmTrackingConfig::Release(void)

- ea: `0x14000b500`
- end: `0x14000b52d`
- name: `?Release@CWsmTrackingConfig@@UEAAXXZ`
- size: `45`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b540`

## callees

- `0x140009300`
- `0x14000b500`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b51a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b51a`

## pseudocode

```c
void __fastcall CWsmTrackingConfig::Release(CWsmTrackingConfig *P)
{
  if ( P )
  {
    CWsmTrackingConfig::~CWsmTrackingConfig(P);
    ExFreePoolWithTag(P, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x14000b500  test    rcx, rcx
0x14000b503  jz      short locret_14000B52B
0x14000b505  push    rbx
0x14000b506  sub     rsp, 20h
0x14000b50a  mov     rbx, rcx
0x14000b50d  call    ??1CWsmTrackingConfig@@QEAA@XZ; CWsmTrackingConfig::~CWsmTrackingConfig(void)
0x14000b512  mov     edx, 6E6D7377h; Tag
0x14000b517  mov     rcx, rbx; P
0x14000b51a  call    cs:__imp_ExFreePoolWithTag
0x14000b521  nop     dword ptr [rax+rax+00h]
0x14000b526  add     rsp, 20h
0x14000b52a  pop     rbx
0x14000b52b  retn
```
