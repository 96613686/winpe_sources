# CWdsVssWriter::`scalar deleting destructor'(uint)

- ea: `0x18001a550`
- end: `0x18001a58e`
- name: `??_GCWdsVssWriter@@UEAAPEAXI@Z`
- size: `62`
- prototype: `void *__fastcall(CWdsVssWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18001a550`

## import_xrefs

- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x18001a55f`
- `VSSAPI!??1CVssJetWriter@@UEAA@XZ` at `0x18001a55f`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001a573`
- `WdsServerCommonLib!?WdsPrivateHpFree@@YAKPEAX@Z` at `0x18001a573`

## pseudocode

```c
CWdsVssWriter *__fastcall CWdsVssWriter::`scalar deleting destructor'(CWdsVssWriter *this, char a2)
{
  CVssJetWriter::~CVssJetWriter(this);
  if ( (a2 & 1) != 0 )
    WdsPrivateHpFree(this);
  return this;
}

```

## disassembly

```asm
0x18001a550  mov     [rsp+arg_0], rbx
0x18001a555  push    rdi
0x18001a556  sub     rsp, 20h
0x18001a55a  mov     ebx, edx
0x18001a55c  mov     rdi, rcx
0x18001a55f  call    cs:__imp_??1CVssJetWriter@@UEAA@XZ; CVssJetWriter::~CVssJetWriter(void)
0x18001a566  nop     dword ptr [rax+rax+00h]
0x18001a56b  test    bl, 1
0x18001a56e  jz      short loc_18001A57F
0x18001a570  mov     rcx, rdi
0x18001a573  call    cs:__imp_?WdsPrivateHpFree@@YAKPEAX@Z; WdsPrivateHpFree(void *)
0x18001a57a  nop     dword ptr [rax+rax+00h]
0x18001a57f  mov     rbx, [rsp+28h+arg_0]
0x18001a584  mov     rax, rdi
0x18001a587  add     rsp, 20h
0x18001a58b  pop     rdi
0x18001a58c  retn
```
