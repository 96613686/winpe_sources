# CControlPacket::~CControlPacket(void)

- ea: `0x180012640`
- end: `0x180012670`
- name: `??1CControlPacket@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(CControlPacket *__hidden this)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x1800026ac`
- `0x18000294c`
- `0x18000d540`
- `0x18000d7bc`
- `0x18000d954`

## callees

- `0x180012640`

## import_xrefs

- `WDSCSL!WdsCpPacketRelease` at `0x180012652`
- `WDSCSL!WdsCpPacketRelease` at `0x180012652`

## pseudocode

```c
void __fastcall CControlPacket::~CControlPacket(CControlPacket *this)
{
  if ( *((_QWORD *)this + 1) )
  {
    WdsCpPacketRelease();
    *((_QWORD *)this + 1) = 0;
  }
  *(_QWORD *)this = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
}

```

## disassembly

```asm
0x180012640  push    rbx
0x180012642  sub     rsp, 20h
0x180012646  mov     rbx, rcx
0x180012649  mov     rcx, [rcx+8]
0x18001264d  test    rcx, rcx
0x180012650  jz      short loc_18001265D
0x180012652  call    cs:__imp_WdsCpPacketRelease
0x180012658  and     qword ptr [rbx+8], 0
0x18001265d  and     qword ptr [rbx], 0
0x180012661  xor     eax, eax
0x180012663  mov     [rbx+10h], rax
0x180012667  mov     [rbx+18h], eax
0x18001266a  add     rsp, 20h
0x18001266e  pop     rbx
0x18001266f  retn
```
