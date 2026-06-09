# CRegUdpEndpoint::InformEndpointRemoved(tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)

- ea: `0x180014c00`
- end: `0x180014c1d`
- name: `?InformEndpointRemoved@CRegUdpEndpoint@@UEAAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z`
- size: `29`
- prototype: `void __fastcall(CRegUdpEndpoint *__hidden this, struct tagWDS_ENDPOINT *, struct tagWDS_INTERFACE_INFO *)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180014390`
- `0x180014c00`

## pseudocode

```c
void __fastcall CRegUdpEndpoint::InformEndpointRemoved(
        CRegUdpEndpoint *this,
        struct tagWDS_ENDPOINT *a2,
        struct tagWDS_INTERFACE_INFO *a3)
{
  if ( !_InterlockedExchangeAdd((volatile signed __int32 *)this + 518, 0) )
    CRegEndpoint::InformEndpointRemoved(this, a2, a3);
}

```

## disassembly

```asm
0x180014c00  sub     rsp, 28h
0x180014c04  xor     eax, eax
0x180014c06  lock xadd [rcx+818h], eax
0x180014c0e  test    eax, eax
0x180014c10  jnz     short loc_180014C17
0x180014c12  call    ?InformEndpointRemoved@CRegEndpoint@@UEAAXPEAUtagWDS_ENDPOINT@@PEAUtagWDS_INTERFACE_INFO@@@Z; CRegEndpoint::InformEndpointRemoved(tagWDS_ENDPOINT *,tagWDS_INTERFACE_INFO *)
0x180014c17  add     rsp, 28h
0x180014c1b  retn
```
