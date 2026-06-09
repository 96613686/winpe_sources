# WanpSetPacketFilterComplete

- ea: `0x140003210`
- end: `0x14000326b`
- name: `WanpSetPacketFilterComplete`
- size: `91`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002d70`
- `0x1400030e0`
- `0x140003210`

## pseudocode

```c
void __fastcall WanpSetPacketFilterComplete(__int64 a1, __int64 OidRequest, int a3)
{
  if ( a3 )
  {
    WanpLastOidComplete(a1, (void *)OidRequest, a3);
  }
  else
  {
    *(_WORD *)(OidRequest + 258) = 14;
    *(_WORD *)(OidRequest + 256) = 2;
    WanpDoNdisRequest(
      a1,
      65817,
      OidRequest + 256,
      4,
      (PNDIS_OID_REQUEST)OidRequest,
      (__int64)WanpLastOidComplete,
      a1 == 212578788);
  }
}

```

## disassembly

```asm
0x140003210  sub     rsp, 48h
0x140003214  cmp     rcx, 0CABB1E4h
0x14000321b  setz    al
0x14000321e  test    r8d, r8d
0x140003221  jz      short loc_14000322A
0x140003223  call    WanpLastOidComplete
0x140003228  jmp     short loc_140003265
0x14000322a  mov     [rsp+48h+var_18], al; char
0x14000322e  lea     r8, [rdx+100h]; int
0x140003235  lea     rax, WanpLastOidComplete
0x14000323c  mov     word ptr [rdx+102h], 0Eh
0x140003245  mov     [rsp+48h+var_20], rax; __int64
0x14000324a  mov     r9d, 4; int
0x140003250  mov     [rsp+48h+OidRequest], rdx; OidRequest
0x140003255  mov     edx, 10119h; int
0x14000325a  mov     word ptr [r8], 2
0x140003260  call    WanpDoNdisRequest
0x140003265  add     rsp, 48h
0x140003269  retn
```
