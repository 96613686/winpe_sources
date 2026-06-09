# CControlProtocol::FindVariable(ControlPacket *,ushort const *)

- ea: `0x18000c4f8`
- end: `0x18000c58b`
- name: `?FindVariable@CControlProtocol@@AEAAPEAUPacketVariable@@PEAUControlPacket@@PEBG@Z`
- size: `147`
- prototype: `struct PacketVariable *__fastcall(CControlProtocol *__hidden this, struct ControlPacket *, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000c190`
- `0x18000d3b0`
- `0x18000d450`

## callees

- `0x18000c4f8`

## import_xrefs

- `WdsCommonLib!?WdsGetStringHash@@YAKPEBG@Z` at `0x18000c50b`
- `WdsCommonLib!?WdsGetStringHash@@YAKPEBG@Z` at `0x18000c50b`

## pseudocode

```c
struct PacketVariable *__fastcall CControlProtocol::FindVariable(
        CControlProtocol *this,
        struct ControlPacket *a2,
        const unsigned __int16 *a3)
{
  unsigned int StringHash; // r11d
  char *v6; // r9
  char *v7; // rdx
  unsigned __int16 *v8; // rax
  int v9; // r10d
  int v10; // ecx

  StringHash = WdsGetStringHash(a3);
  v6 = 0;
  v7 = (char *)*((_QWORD *)a2 + 3 * (StringHash % 0x71) + 5);
  while ( v7 )
  {
    v6 = v7;
    v7 = (char *)*((_QWORD *)v7 + 12);
    if ( *((_DWORD *)v6 + 28) == StringHash )
    {
      v8 = (unsigned __int16 *)v6;
      do
      {
        v9 = *(unsigned __int16 *)((char *)v8 + (char *)a3 - v6);
        v10 = *v8 - v9;
        if ( v10 )
          break;
        ++v8;
      }
      while ( v9 );
      if ( !v10 )
        break;
    }
    v6 = 0;
  }
  return (struct PacketVariable *)v6;
}

```

## disassembly

```asm
0x18000c4f8  mov     [rsp+arg_0], rbx
0x18000c4fd  push    rdi
0x18000c4fe  sub     rsp, 20h
0x18000c502  mov     rcx, r8
0x18000c505  mov     rdi, r8
0x18000c508  mov     rbx, rdx
0x18000c50b  call    cs:__imp_?WdsGetStringHash@@YAKPEBG@Z; WdsGetStringHash(ushort const *)
0x18000c512  nop     dword ptr [rax+rax+00h]
0x18000c517  mov     r11d, eax
0x18000c51a  xor     r9d, r9d
0x18000c51d  mov     ecx, r11d
0x18000c520  mov     eax, 21FB7813h
0x18000c525  mul     r11d
0x18000c528  sub     ecx, edx
0x18000c52a  shr     ecx, 1
0x18000c52c  add     ecx, edx
0x18000c52e  shr     ecx, 6
0x18000c531  imul    eax, ecx, 71h ; 'q'
0x18000c534  mov     ecx, r11d
0x18000c537  sub     ecx, eax
0x18000c539  lea     rcx, [rcx+rcx*2]
0x18000c53d  mov     rdx, [rbx+rcx*8+28h]
0x18000c542  jmp     short loc_18000C577
0x18000c544  mov     r9, rdx
0x18000c547  mov     rdx, [rdx+60h]
0x18000c54b  cmp     [r9+70h], r11d
0x18000c54f  jnz     short loc_18000C574
0x18000c551  mov     r8, rdi
0x18000c554  mov     rax, r9
0x18000c557  sub     r8, r9
0x18000c55a  movzx   ecx, word ptr [rax]
0x18000c55d  movzx   r10d, word ptr [rax+r8]
0x18000c562  sub     ecx, r10d
0x18000c565  jnz     short loc_18000C570
0x18000c567  add     rax, 2
0x18000c56b  test    r10d, r10d
0x18000c56e  jnz     short loc_18000C55A
0x18000c570  test    ecx, ecx
0x18000c572  jz      short loc_18000C57C
0x18000c574  xor     r9d, r9d
0x18000c577  test    rdx, rdx
0x18000c57a  jnz     short loc_18000C544
0x18000c57c  mov     rbx, [rsp+28h+arg_0]
0x18000c581  mov     rax, r9
0x18000c584  add     rsp, 20h
0x18000c588  pop     rdi
0x18000c589  retn
```
