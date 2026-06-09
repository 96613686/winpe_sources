# CControlPacket::Shutdown(void)

- ea: `0x180012214`
- end: `0x18001224b`
- name: `?Shutdown@CControlPacket@@QEAAKXZ`
- size: `55`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this)`
- caller_count: `17`
- callee_count: `1`
- tags: ``

## callers

- `0x180003838`
- `0x180006e50`
- `0x180012144`
- `0x1800121ac`
- `0x180012890`
- `0x180012a18`
- `0x180012c20`
- `0x180012d80`
- `0x180013030`
- `0x180013170`
- `0x180013ed0`
- `0x180014050`
- `0x1800141b0`
- `0x1800142e0`
- `0x180014590`
- `0x180014740`
- `0x180014990`

## callees

- `0x180012214`

## import_xrefs

- `WDSCSL!WdsCpPacketRelease` at `0x180012226`
- `WDSCSL!WdsCpPacketRelease` at `0x180012226`

## pseudocode

```c
__int64 __fastcall CControlPacket::Shutdown(CControlPacket *this)
{
  __int64 result; // rax

  if ( *((_QWORD *)this + 1) )
  {
    WdsCpPacketRelease();
    *((_QWORD *)this + 1) = 0;
  }
  *(_QWORD *)this = 0;
  result = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  return result;
}

```

## disassembly

```asm
0x180012214  push    rbx
0x180012216  sub     rsp, 20h
0x18001221a  mov     rbx, rcx
0x18001221d  mov     rcx, [rcx+8]
0x180012221  test    rcx, rcx
0x180012224  jz      short loc_180012237
0x180012226  call    cs:__imp_WdsCpPacketRelease
0x18001222d  nop     dword ptr [rax+rax+00h]
0x180012232  and     qword ptr [rbx+8], 0
0x180012237  and     qword ptr [rbx], 0
0x18001223b  xor     eax, eax
0x18001223d  mov     [rbx+10h], rax
0x180012241  mov     [rbx+18h], eax
0x180012244  add     rsp, 20h
0x180012248  pop     rbx
0x180012249  retn
```
