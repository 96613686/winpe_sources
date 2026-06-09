# CRpcImpersonateClient::CRpcImpersonateClient(void *)

- ea: `0x18001fb24`
- end: `0x18001fb80`
- name: `??0CRpcImpersonateClient@@QEAA@PEAX@Z`
- size: `92`
- prototype: `CRpcImpersonateClient *__fastcall(CRpcImpersonateClient *this, void *)`
- caller_count: `8`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180031e24`
- `0x180031efc`
- `0x180033750`
- `0x1800337d0`
- `0x180033b90`
- `0x18003532c`
- `0x1800356b4`
- `0x18003d620`

## callees

- `0x180008e48`
- `0x18001fb24`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18001fb30`
- `RPCRT4!RpcImpersonateClient` at `0x18001fb30`
- `RPCRT4!RpcRaiseException` at `0x18001fb79`
- `RPCRT4!RpcRaiseException` at `0x18001fb79`

## pseudocode

```c
CRpcImpersonateClient *__fastcall CRpcImpersonateClient::CRpcImpersonateClient(CRpcImpersonateClient *this, void *a2)
{
  unsigned int v3; // eax

  v3 = RpcImpersonateClient(a2);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v3);
    }
    RpcRaiseException(5);
  }
  return this;
}

```

## disassembly

```asm
0x18001fb24  push    rbx
0x18001fb26  sub     rsp, 20h
0x18001fb2a  mov     rbx, rcx
0x18001fb2d  mov     rcx, rdx; BindingHandle
0x18001fb30  call    cs:__imp_RpcImpersonateClient
0x18001fb36  test    eax, eax
0x18001fb38  jnz     short loc_18001FB43
0x18001fb3a  mov     rax, rbx
0x18001fb3d  add     rsp, 20h
0x18001fb41  pop     rbx
0x18001fb42  retn
0x18001fb43  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fb4a  lea     rdx, WPP_GLOBAL_Control
0x18001fb51  cmp     rcx, rdx
0x18001fb54  jz      short loc_18001FB74
0x18001fb56  test    byte ptr [rcx+1Ch], 1
0x18001fb5a  jz      short loc_18001FB74
0x18001fb5c  mov     rcx, [rcx+10h]
0x18001fb60  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001fb67  mov     edx, 1Bh
0x18001fb6c  mov     r9d, eax
0x18001fb6f  call    WPP_SF_d
0x18001fb74  mov     ecx, 5; exception
0x18001fb79  call    cs:__imp_RpcRaiseException
```
