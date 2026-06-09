# RpcInterfaceSecurityCallback(void *,void *)

- ea: `0x180002990`
- end: `0x1800029c2`
- name: `?RpcInterfaceSecurityCallback@@YAJPEAX0@Z`
- size: `50`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE InterfaceUuid, void *Context, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x180002990`
- `0x180002cb0`
- `0x180002f14`

## pseudocode

```c
__int64 __fastcall RpcInterfaceSecurityCallback(RPC_IF_HANDLE InterfaceUuid, void *Context, unsigned int a3)
{
  __int64 result; // rax
  const wmi::Exception *v4; // [rsp+20h] [rbp-18h] BYREF
  unsigned __int16 *v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = L"ncalrpc";
  try
  {
    VerifyProtSeq(Context, (const unsigned __int16 **)&v5, a3);
    VerifyRpcAccess();
    result = 0;
  }
  catch ( const wmi::Exception *v4 )
  {
    LODWORD(v5) = 5;
    return 5;
  }
  VerifyProtSeq(Context, (const unsigned __int16 **)&v5, a3);
}

```

## disassembly

```asm
0x180002990  sub     rsp, 38h
0x180002994  mov     rax, rdx
0x180002997  lea     rcx, Protseq; "ncalrpc"
0x18000299e  mov     [rsp+38h+arg_10], rcx
0x1800029a3  lea     rdx, [rsp+38h+arg_10]; unsigned __int16 **
0x1800029a8  mov     rcx, rax; void *
0x1800029ab  call    ?VerifyProtSeq@@YAXPEAXPEAPEBGK@Z; VerifyProtSeq(void *,ushort const * *,ulong)
0x1800029b0  call    ?VerifyRpcAccess@@YAXXZ; VerifyRpcAccess(void)
0x1800029b5  xor     eax, eax
0x1800029b7  jmp     short loc_1800029BD
0x1800029b9  mov     eax, dword ptr [rsp+38h+arg_10]
0x1800029bd  add     rsp, 38h
0x1800029c1  retn
```
