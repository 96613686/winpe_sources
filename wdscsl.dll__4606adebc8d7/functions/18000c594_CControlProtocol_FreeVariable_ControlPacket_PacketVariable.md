# CControlProtocol::FreeVariable(ControlPacket *,PacketVariable *)

- ea: `0x18000c594`
- end: `0x18000c5d5`
- name: `?FreeVariable@CControlProtocol@@AEAAXPEAUControlPacket@@PEAUPacketVariable@@@Z`
- size: `65`
- prototype: `void __fastcall(CControlProtocol *__hidden this, struct ControlPacket *, struct PacketVariable *)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000c190`
- `0x18000cc4c`
- `0x18000d320`

## callees

- `0x180006080`
- `0x18000c594`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c5c9`

## pseudocode

```c
void __fastcall CControlProtocol::FreeVariable(CControlProtocol *this, void **a2, struct PacketVariable *a3)
{
  void *v4; // r8

  v4 = (void *)*((_QWORD *)a3 + 9);
  if ( v4 )
  {
    if ( *((_DWORD *)a2 + 6) )
      CClientLibrary::FreePacket((CClientLibrary *)&stru_1800158D0, a2[2], v4);
    *((_QWORD *)a3 + 9) = 0;
  }
  operator delete(a3);
}

```

## disassembly

```asm
0x18000c594  push    rbx
0x18000c596  sub     rsp, 20h
0x18000c59a  mov     rbx, r8
0x18000c59d  mov     r8, [r8+48h]; void *
0x18000c5a1  test    r8, r8
0x18000c5a4  jz      short loc_18000C5C1
0x18000c5a6  cmp     dword ptr [rdx+18h], 0
0x18000c5aa  jz      short loc_18000C5BC
0x18000c5ac  mov     rdx, [rdx+10h]; void *
0x18000c5b0  lea     rcx, stru_1800158D0; this
0x18000c5b7  call    ?FreePacket@CClientLibrary@@QEAAKPEAX0@Z; CClientLibrary::FreePacket(void *,void *)
0x18000c5bc  and     qword ptr [rbx+48h], 0
0x18000c5c1  mov     rcx, rbx
0x18000c5c4  add     rsp, 20h
0x18000c5c8  pop     rbx
0x18000c5c9  jmp     cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
```
