# WdsCpParameterDelete

- ea: `0x18000d320`
- end: `0x18000d3a8`
- name: `WdsCpParameterDelete`
- size: `136`
- prototype: `__int64 __fastcall(struct ControlPacket *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000bfcc`
- `0x18000c594`
- `0x18000d320`

## import_xrefs

- `WdsCommonLib!?WdsGetStringHash@@YAKPEBG@Z` at `0x18000d35f`
- `WdsCommonLib!?WdsGetStringHash@@YAKPEBG@Z` at `0x18000d35f`

## pseudocode

```c
__int64 __fastcall WdsCpParameterDelete(void **a1, const unsigned __int16 *a2)
{
  unsigned int v2; // ebx
  unsigned int StringHash; // eax
  unsigned __int16 *v6; // rax
  CControlProtocol *v7; // rcx

  v2 = 0;
  if ( dword_180015948 )
  {
    if ( a1 && a2 )
    {
      if ( *((_DWORD *)a1 + 6) )
      {
        StringHash = WdsGetStringHash(a2);
        v6 = CSmHashTable<PacketVariable,CNoLock,113>::RemoveItem<unsigned short const *>(
               (__int64)(a1 + 4),
               StringHash,
               (__int64)a2);
        if ( v6 )
          CControlProtocol::FreeVariable(v7, a1, (struct PacketVariable *)v6);
        else
          return 2;
      }
      else
      {
        return 1;
      }
    }
    else
    {
      return 87;
    }
  }
  else
  {
    return 5023;
  }
  return v2;
}

```

## disassembly

```asm
0x18000d320  mov     [rsp+arg_0], rbx
0x18000d325  mov     [rsp+arg_8], rsi
0x18000d32a  push    rdi
0x18000d32b  sub     rsp, 20h
0x18000d32f  xor     ebx, ebx
0x18000d331  mov     rsi, rdx
0x18000d334  cmp     cs:dword_180015948, ebx
0x18000d33a  mov     rdi, rcx
0x18000d33d  jnz     short loc_18000D346
0x18000d33f  mov     ebx, 139Fh
0x18000d344  jmp     short loc_18000D395
0x18000d346  test    rdi, rdi
0x18000d349  jz      short loc_18000D390
0x18000d34b  test    rsi, rsi
0x18000d34e  jz      short loc_18000D390
0x18000d350  cmp     [rcx+18h], ebx
0x18000d353  jnz     short loc_18000D35C
0x18000d355  mov     ebx, 1
0x18000d35a  jmp     short loc_18000D395
0x18000d35c  mov     rcx, rsi
0x18000d35f  call    cs:__imp_?WdsGetStringHash@@YAKPEBG@Z; WdsGetStringHash(ushort const *)
0x18000d366  nop     dword ptr [rax+rax+00h]
0x18000d36b  lea     rcx, [rdi+20h]
0x18000d36f  mov     r8, rsi
0x18000d372  mov     edx, eax
0x18000d374  call    ??$RemoveItem@PEBG@?$CSmHashTable@UPacketVariable@@VCNoLock@@$0HB@@@QEAAPEAUPacketVariable@@KPEBG@Z; CSmHashTable<PacketVariable,CNoLock,113>::RemoveItem<ushort const *>(ulong,ushort const *)
0x18000d379  test    rax, rax
0x18000d37c  jnz     short loc_18000D383
0x18000d37e  lea     ebx, [rax+2]
0x18000d381  jmp     short loc_18000D395
0x18000d383  mov     r8, rax; struct PacketVariable *
0x18000d386  mov     rdx, rdi; struct ControlPacket *
0x18000d389  call    ?FreeVariable@CControlProtocol@@AEAAXPEAUControlPacket@@PEAUPacketVariable@@@Z; CControlProtocol::FreeVariable(ControlPacket *,PacketVariable *)
0x18000d38e  jmp     short loc_18000D395
0x18000d390  mov     ebx, 57h ; 'W'
0x18000d395  mov     rsi, [rsp+28h+arg_8]
0x18000d39a  mov     eax, ebx
0x18000d39c  mov     rbx, [rsp+28h+arg_0]
0x18000d3a1  add     rsp, 20h
0x18000d3a5  pop     rdi
0x18000d3a6  retn
```
