# CControlPacket::SendInitialize(void *,ulong,uchar)

- ea: `0x1800126f8`
- end: `0x180012777`
- name: `?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z`
- size: `127`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, void *, unsigned int, unsigned __int8)`
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

- `0x1800126f8`

## import_xrefs

- `WDSCSL!WdsCpPacketRelease` at `0x180012729`
- `WDSCSL!WdsCpPacketRelease` at `0x180012729`
- `WDSCSL!WdsCpPacketInitialize` at `0x180012770`

## pseudocode

```c
__int64 __fastcall CControlPacket::SendInitialize(CControlPacket *this, void *a2, int a3, char a4)
{
  _QWORD *v4; // rdi

  v4 = (_QWORD *)((char *)this + 8);
  if ( *((_QWORD *)this + 1) )
  {
    WdsCpPacketRelease();
    *v4 = 0;
  }
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *(_QWORD *)this = a2;
  *((_DWORD *)this + 4) = 12;
  *((_BYTE *)this + 20) = a4;
  *((_DWORD *)this + 6) = a3;
  return WdsCpPacketInitialize(a2, (char *)this + 16, v4);
}

```

## disassembly

```asm
0x1800126f8  mov     rax, rsp
0x1800126fb  mov     [rax+8], rbx
0x1800126ff  mov     [rax+10h], rbp
0x180012703  mov     [rax+18h], rsi
0x180012707  mov     [rax+20h], rdi
0x18001270b  push    r14
0x18001270d  sub     rsp, 20h
0x180012711  lea     rdi, [rcx+8]
0x180012715  mov     rbx, rcx
0x180012718  mov     rcx, [rdi]
0x18001271b  mov     bpl, r9b
0x18001271e  mov     r14d, r8d
0x180012721  mov     rsi, rdx
0x180012724  test    rcx, rcx
0x180012727  jz      short loc_180012733
0x180012729  call    cs:__imp_WdsCpPacketRelease
0x18001272f  and     qword ptr [rdi], 0
0x180012733  lea     rdx, [rbx+10h]
0x180012737  xor     eax, eax
0x180012739  mov     [rdx], rax
0x18001273c  mov     r8, rdi
0x18001273f  mov     [rdx+8], eax
0x180012742  mov     rcx, rsi
0x180012745  mov     [rbx], rsi
0x180012748  mov     dword ptr [rdx], 0Ch
0x18001274e  mov     [rbx+14h], bpl
0x180012752  mov     [rbx+18h], r14d
0x180012756  mov     rbx, [rsp+28h+arg_0]
0x18001275b  mov     rbp, [rsp+28h+arg_8]
0x180012760  mov     rsi, [rsp+28h+arg_10]
0x180012765  mov     rdi, [rsp+28h+arg_18]
0x18001276a  add     rsp, 20h
0x18001276e  pop     r14
0x180012770  jmp     cs:__imp_WdsCpPacketInitialize
```
