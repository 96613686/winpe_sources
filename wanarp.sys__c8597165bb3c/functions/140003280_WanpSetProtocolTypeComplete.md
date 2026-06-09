# WanpSetProtocolTypeComplete

- ea: `0x140003280`
- end: `0x1400032d3`
- name: `WanpSetProtocolTypeComplete`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140002d70`
- `0x1400030e0`
- `0x140003280`

## pseudocode

```c
void __fastcall WanpSetProtocolTypeComplete(__int64 a1, __int64 OidRequest, int a3)
{
  if ( a3 )
  {
    WanpLastOidComplete(a1, (void *)OidRequest, a3);
  }
  else
  {
    *(_DWORD *)(OidRequest + 256) = 128;
    WanpDoNdisRequest(
      a1,
      65807,
      OidRequest + 256,
      4,
      (PNDIS_OID_REQUEST)OidRequest,
      (__int64)WanpSetLookaheadComplete,
      a1 == 212578788);
  }
}

```

## disassembly

```asm
0x140003280  sub     rsp, 48h
0x140003284  cmp     rcx, 0CABB1E4h
0x14000328b  setz    al
0x14000328e  test    r8d, r8d
0x140003291  jz      short loc_14000329A
0x140003293  call    WanpLastOidComplete
0x140003298  jmp     short loc_1400032CD
0x14000329a  mov     [rsp+48h+var_18], al; char
0x14000329e  lea     r8, [rdx+100h]; int
0x1400032a5  lea     rax, WanpSetLookaheadComplete
0x1400032ac  mov     dword ptr [r8], 80h
0x1400032b3  mov     [rsp+48h+var_20], rax; __int64
0x1400032b8  mov     r9d, 4; int
0x1400032be  mov     [rsp+48h+OidRequest], rdx; OidRequest
0x1400032c3  mov     edx, 1010Fh; int
0x1400032c8  call    WanpDoNdisRequest
0x1400032cd  add     rsp, 48h
0x1400032d1  retn
```
