# CControlPacket::SendInitialize(void *,ulong,uchar)

- ea: `0x180020404`
- end: `0x180020483`
- name: `?SendInitialize@CControlPacket@@QEAAKPEAXKE@Z`
- size: `127`
- prototype: `unsigned int __fastcall(CControlPacket *__hidden this, void *, unsigned int, unsigned __int8)`
- caller_count: `5`
- callee_count: `1`
- tags: ``

## callers

- `0x180007e64`
- `0x180008040`
- `0x1800082d0`
- `0x1800175b4`
- `0x18001b9f8`

## callees

- `0x180020404`

## import_xrefs

- `WDSCSL!WdsCpPacketRelease` at `0x180020435`
- `WDSCSL!WdsCpPacketRelease` at `0x180020435`
- `WDSCSL!WdsCpPacketInitialize` at `0x18002047c`

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
0x180020404  mov     rax, rsp
0x180020407  mov     [rax+8], rbx
0x18002040b  mov     [rax+10h], rbp
0x18002040f  mov     [rax+18h], rsi
0x180020413  mov     [rax+20h], rdi
0x180020417  push    r14
0x180020419  sub     rsp, 20h
0x18002041d  lea     rdi, [rcx+8]
0x180020421  mov     rbx, rcx
0x180020424  mov     rcx, [rdi]
0x180020427  mov     bpl, r9b
0x18002042a  mov     r14d, r8d
0x18002042d  mov     rsi, rdx
0x180020430  test    rcx, rcx
0x180020433  jz      short loc_18002043F
0x180020435  call    cs:__imp_WdsCpPacketRelease
0x18002043b  and     qword ptr [rdi], 0
0x18002043f  lea     rdx, [rbx+10h]
0x180020443  xor     eax, eax
0x180020445  mov     [rdx], rax
0x180020448  mov     r8, rdi
0x18002044b  mov     [rdx+8], eax
0x18002044e  mov     rcx, rsi
0x180020451  mov     [rbx], rsi
0x180020454  mov     dword ptr [rdx], 0Ch
0x18002045a  mov     [rbx+14h], bpl
0x18002045e  mov     [rbx+18h], r14d
0x180020462  mov     rbx, [rsp+28h+arg_0]
0x180020467  mov     rbp, [rsp+28h+arg_8]
0x18002046c  mov     rsi, [rsp+28h+arg_10]
0x180020471  mov     rdi, [rsp+28h+arg_18]
0x180020476  add     rsp, 20h
0x18002047a  pop     r14
0x18002047c  jmp     cs:__imp_WdsCpPacketInitialize
```
