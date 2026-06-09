# WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::CImpersonationToken(void *)

- ea: `0x18005e55c`
- end: `0x18005e604`
- name: `??0CImpersonationToken@CRpcImpersonationProvider@WFDSConMgr@@QEAA@PEAX@Z`
- size: `168`
- prototype: `WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken *__fastcall(WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken *this, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x18005eab0`

## callees

- `0x180009b5c`
- `0x18005c888`
- `0x18005e55c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x18005e5ba`
- `RPCRT4!RpcImpersonateClient` at `0x18005e5ba`

## string_xrefs

- `0x18005e5e5`: `onecoreuap\net\wlan\wfdsconmgr\util\src\impersonationprovider.cpp`
- `0x18005e5d3`: `RpcImpersonateClient failed`
- `0x18005e5ec`: `WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::CImpersonationToken`

## pseudocode

```c
WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken *__fastcall WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::CImpersonationToken(
        WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken *this,
        void *a2)
{
  RPC_STATUS v3; // eax

  *(_QWORD *)this = &WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::`vftable';
  *((_QWORD *)this + 1) = a2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_7d681293e58d38db1ed4308781b49152_Traceguids, this, a2);
  }
  v3 = RpcImpersonateClient(*((RPC_BINDING_HANDLE *)this + 1));
  if ( v3 )
    WFDSConMgr::CException::Throw(
      v3,
      "WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::CImpersonationToken",
      "onecoreuap\\net\\wlan\\wfdsconmgr\\util\\src\\impersonationprovider.cpp",
      25,
      L"RpcImpersonateClient failed",
      this);
  return this;
}

```

## disassembly

```asm
0x18005e55c  mov     [rsp+arg_0], rcx
0x18005e561  push    rbx
0x18005e562  sub     rsp, 30h
0x18005e566  mov     rax, rdx
0x18005e569  mov     rbx, rcx
0x18005e56c  lea     rcx, ??_7CImpersonationToken@CRpcImpersonationProvider@WFDSConMgr@@6B@; const WFDSConMgr::CRpcImpersonationProvider::CImpersonationToken::`vftable'
0x18005e573  mov     [rbx], rcx
0x18005e576  mov     [rbx+8], rdx
0x18005e57a  lea     rdx, WPP_GLOBAL_Control
0x18005e581  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e588  cmp     rcx, rdx
0x18005e58b  jz      short loc_18005E5B6
0x18005e58d  cmp     byte ptr [rcx+19h], 4
0x18005e591  jb      short loc_18005E5B6
0x18005e593  test    byte ptr [rcx+1Ch], 1
0x18005e597  jz      short loc_18005E5B6
0x18005e599  mov     edx, 0Ah
0x18005e59e  mov     [rsp+38h+var_18], rax
0x18005e5a3  mov     r9, rbx
0x18005e5a6  lea     r8, WPP_7d681293e58d38db1ed4308781b49152_Traceguids
0x18005e5ad  mov     rcx, [rcx+10h]
0x18005e5b1  call    WPP_SF_qq
0x18005e5b6  mov     rcx, [rbx+8]; BindingHandle
0x18005e5ba  call    cs:__imp_RpcImpersonateClient
0x18005e5c0  test    eax, eax
0x18005e5c2  jz      short loc_18005E5FB
0x18005e5c4  jle     short loc_18005E5CE
0x18005e5c6  movzx   eax, ax
0x18005e5c9  or      eax, 80070000h
0x18005e5ce  mov     [rsp+38h+var_10], rbx; void *
0x18005e5d3  lea     rcx, aRpcimpersonate; "RpcImpersonateClient failed"
0x18005e5da  mov     [rsp+38h+var_18], rcx; unsigned __int16 *
0x18005e5df  mov     r9d, 19h; char
0x18005e5e5  lea     r8, aOnecoreuapNetW_15; "onecoreuap\\net\\wlan\\wfdsconmgr\\util"...
0x18005e5ec  lea     rdx, aWfdsconmgrCrpc; "WFDSConMgr::CRpcImpersonationProvider::"...
0x18005e5f3  mov     ecx, eax; char
0x18005e5f5  call    ?Throw@CException@WFDSConMgr@@SAXJPEBD0KPEBGPEBX@Z; WFDSConMgr::CException::Throw(long,char const *,char const *,ulong,ushort const *,void const *)
0x18005e5fb  mov     rax, rbx
0x18005e5fe  add     rsp, 30h
0x18005e602  pop     rbx
0x18005e603  retn
```
