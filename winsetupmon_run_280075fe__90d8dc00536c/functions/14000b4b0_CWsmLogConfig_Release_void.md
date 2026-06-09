# CWsmLogConfig::Release(void)

- ea: `0x14000b4b0`
- end: `0x14000b4dd`
- name: `?Release@CWsmLogConfig@@UEAAXXZ`
- size: `45`
- prototype: `void __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000b4f0`

## callees

- `0x140009298`
- `0x14000b4b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000b4ca`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000b4ca`

## pseudocode

```c
void __fastcall CWsmLogConfig::Release(CWsmLogConfig *P)
{
  if ( P )
  {
    CWsmLogConfig::~CWsmLogConfig(P);
    ExFreePoolWithTag(P, 0x6E6D7377u);
  }
}

```

## disassembly

```asm
0x14000b4b0  test    rcx, rcx
0x14000b4b3  jz      short locret_14000B4DB
0x14000b4b5  push    rbx
0x14000b4b6  sub     rsp, 20h
0x14000b4ba  mov     rbx, rcx
0x14000b4bd  call    ??1CWsmLogConfig@@QEAA@XZ; CWsmLogConfig::~CWsmLogConfig(void)
0x14000b4c2  mov     edx, 6E6D7377h; Tag
0x14000b4c7  mov     rcx, rbx; P
0x14000b4ca  call    cs:__imp_ExFreePoolWithTag
0x14000b4d1  nop     dword ptr [rax+rax+00h]
0x14000b4d6  add     rsp, 20h
0x14000b4da  pop     rbx
0x14000b4db  retn
```
