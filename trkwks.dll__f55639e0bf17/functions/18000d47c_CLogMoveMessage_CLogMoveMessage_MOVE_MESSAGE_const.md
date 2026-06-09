# CLogMoveMessage::CLogMoveMessage(MOVE_MESSAGE const &)

- ea: `0x18000d47c`
- end: `0x18000d4d4`
- name: `??0CLogMoveMessage@@QEAA@AEBUMOVE_MESSAGE@@@Z`
- size: `88`
- prototype: `CLogMoveMessage *__fastcall(CLogMoveMessage *__hidden this, const struct MOVE_MESSAGE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path`

## callers

- `0x1800022d4`

## callees

- `0x180006850`

## pseudocode

```c
CLogMoveMessage *__fastcall CLogMoveMessage::CLogMoveMessage(CLogMoveMessage *this, const struct MOVE_MESSAGE *a2)
{
  __int128 v3; // xmm1
  __int128 v4; // xmm1
  __int128 v5; // xmm2
  CMachineId *v6; // rcx

  v3 = *(_OWORD *)((char *)a2 + 52);
  *(_OWORD *)this = *(_OWORD *)((char *)a2 + 36);
  *((_OWORD *)this + 1) = v3;
  v4 = *(_OWORD *)((char *)a2 + 20);
  *((_OWORD *)this + 2) = *(_OWORD *)((char *)a2 + 4);
  *((_OWORD *)this + 3) = v4;
  v5 = *(_OWORD *)((char *)a2 + 104);
  *((_OWORD *)this + 4) = *(_OWORD *)((char *)a2 + 88);
  *((_OWORD *)this + 5) = v5;
  v6 = (CLogMoveMessage *)((char *)this + 96);
  *(_OWORD *)v6 = *(_OWORD *)((char *)a2 + 120);
  CMachineId::Normalize(v6);
  return this;
}

```

## disassembly

```asm
0x18000d47c  push    rbx
0x18000d47e  sub     rsp, 20h
0x18000d482  movups  xmm0, xmmword ptr [rdx+24h]
0x18000d486  mov     rbx, rcx
0x18000d489  movups  xmm1, xmmword ptr [rdx+34h]
0x18000d48d  movdqu  xmmword ptr [rcx], xmm0
0x18000d491  movdqu  xmmword ptr [rcx+10h], xmm1
0x18000d496  movups  xmm0, xmmword ptr [rdx+4]
0x18000d49a  movups  xmm1, xmmword ptr [rdx+14h]
0x18000d49e  movdqu  xmmword ptr [rcx+20h], xmm0
0x18000d4a3  movdqu  xmmword ptr [rcx+30h], xmm1
0x18000d4a8  movups  xmm0, xmmword ptr [rdx+58h]
0x18000d4ac  movups  xmm2, xmmword ptr [rdx+68h]
0x18000d4b0  movdqu  xmmword ptr [rcx+40h], xmm0
0x18000d4b5  movdqu  xmmword ptr [rcx+50h], xmm2
0x18000d4ba  add     rcx, 60h ; '`'; this
0x18000d4be  movups  xmm0, xmmword ptr [rdx+78h]
0x18000d4c2  movdqu  xmmword ptr [rcx], xmm0
0x18000d4c6  call    ?Normalize@CMachineId@@QEAAXXZ; CMachineId::Normalize(void)
0x18000d4cb  mov     rax, rbx
0x18000d4ce  add     rsp, 20h
0x18000d4d2  pop     rbx
0x18000d4d3  retn
```
