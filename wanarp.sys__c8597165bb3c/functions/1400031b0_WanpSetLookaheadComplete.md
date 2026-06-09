# WanpSetLookaheadComplete

- ea: `0x1400031b0`
- end: `0x140003203`
- name: `WanpSetLookaheadComplete`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002d70`
- `0x1400030e0`
- `0x1400031b0`

## pseudocode

```c
void __fastcall WanpSetLookaheadComplete(__int64 a1, __int64 OidRequest, int a3)
{
  if ( a3 )
  {
    WanpLastOidComplete(a1, (void *)OidRequest, a3);
  }
  else
  {
    *(_DWORD *)(OidRequest + 256) = 9;
    WanpDoNdisRequest(
      a1,
      65806,
      OidRequest + 256,
      4,
      (PNDIS_OID_REQUEST)OidRequest,
      (__int64)&WanpSetPacketFilterComplete,
      a1 == 212578788);
  }
}

```

## disassembly

```asm
0x1400031b0  sub     rsp, 48h
0x1400031b4  cmp     rcx, 0CABB1E4h
0x1400031bb  setz    al
0x1400031be  test    r8d, r8d
0x1400031c1  jz      short loc_1400031CA
0x1400031c3  call    WanpLastOidComplete
0x1400031c8  jmp     short loc_1400031FD
0x1400031ca  mov     [rsp+48h+var_18], al; char
0x1400031ce  lea     r8, [rdx+100h]; int
0x1400031d5  lea     rax, WanpSetPacketFilterComplete
0x1400031dc  mov     dword ptr [r8], 9
0x1400031e3  mov     [rsp+48h+var_20], rax; __int64
0x1400031e8  mov     r9d, 4; int
0x1400031ee  mov     [rsp+48h+OidRequest], rdx; OidRequest
0x1400031f3  mov     edx, 1010Eh; int
0x1400031f8  call    WanpDoNdisRequest
0x1400031fd  add     rsp, 48h
0x140003201  retn
```
