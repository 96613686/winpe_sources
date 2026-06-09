# CControlPacket::SendInitialize(void *,ulong,uchar)

- ea: `0x1800121ac`
- end: `0x18001220c`
- name: `?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z`
- size: `96`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, void *, unsigned int, unsigned __int8)`
- caller_count: `14`
- callee_count: `1`
- tags: ``

## callers

- `0x180003838`
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

- `WDSCSL!WdsCpPacketInitialize` at `0x180012200`

## pseudocode

```c
__int64 __fastcall CControlPacket::SendInitialize(CControlPacket *this, void *a2, int a3, char a4)
{
  CControlPacket::Shutdown(this);
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 4) = 12;
  *((_BYTE *)this + 20) = a4;
  *((_DWORD *)this + 6) = a3;
  return WdsCpPacketInitialize(a2, (char *)this + 16, (char *)this + 8);
}

```

## disassembly

```asm
0x1800121ac  mov     [rsp+arg_0], rbx
0x1800121b1  mov     [rsp+arg_8], rbp
0x1800121b6  mov     [rsp+arg_10], rsi
0x1800121bb  push    rdi
0x1800121bc  sub     rsp, 20h
0x1800121c0  mov     dil, r9b
0x1800121c3  mov     esi, r8d
0x1800121c6  mov     rbp, rdx
0x1800121c9  mov     rbx, rcx
0x1800121cc  call    ?Shutdown@CControlPacket@@QEAAKXZ; CControlPacket::Shutdown(void)
0x1800121d1  lea     rdx, [rbx+10h]
0x1800121d5  mov     [rbx], rbp
0x1800121d8  lea     r8, [rbx+8]
0x1800121dc  mov     dword ptr [rdx], 0Ch
0x1800121e2  mov     rcx, rbp
0x1800121e5  mov     [rbx+14h], dil
0x1800121e9  mov     [rbx+18h], esi
0x1800121ec  mov     rbx, [rsp+28h+arg_0]
0x1800121f1  mov     rbp, [rsp+28h+arg_8]
0x1800121f6  mov     rsi, [rsp+28h+arg_10]
0x1800121fb  add     rsp, 20h
0x1800121ff  pop     rdi
0x180012200  jmp     cs:__imp_WdsCpPacketInitialize
```
