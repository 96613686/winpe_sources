# PnPRpcIfCallback

- ea: `0x18000fd90`
- end: `0x18000fe60`
- name: `PnPRpcIfCallback`
- size: `208`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18000be30`
- `0x18000fd90`
- `0x18001091c`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fe12`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18000fe12`
- `RPCRT4!RpcStringFreeW` at `0x18000fdee`
- `RPCRT4!RpcStringFreeW` at `0x18000fe52`
- `RPCRT4!RpcStringFreeW` at `0x18000fdee`
- `RPCRT4!RpcStringFreeW` at `0x18000fe52`
- `RPCRT4!RpcStringBindingParseW` at `0x18000fde1`
- `RPCRT4!RpcStringBindingParseW` at `0x18000fde1`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000fdb0`
- `RPCRT4!RpcBindingToStringBindingW` at `0x18000fdb0`

## pseudocode

```c
__int64 __fastcall PnPRpcIfCallback(__int64 a1, void *a2)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v4; // ecx
  RPC_WSTR Protseq; // [rsp+48h] [rbp+10h] BYREF
  RPC_WSTR StringBinding; // [rsp+50h] [rbp+18h] BYREF

  StringBinding = 0;
  Protseq = 0;
  v2 = RpcBindingToStringBindingW(a2, &StringBinding);
  if ( !v2 )
  {
    v2 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    RpcStringFreeW(&StringBinding);
    if ( !v2 )
    {
      if ( CompareStringOrdinal(Protseq, -1, L"ncalrpc", -1, 1) == 2 && (unsigned int)VerifyClientAccessToObject(1) )
      {
        v3 = IsClientLocal();
        v4 = 0;
        if ( !v3 )
          v4 = 5;
        v2 = v4;
      }
      else
      {
        v2 = 5;
      }
    }
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  return v2;
}

```

## disassembly

```asm
0x18000fd90  push    rbx
0x18000fd92  sub     rsp, 30h
0x18000fd96  mov     rcx, rdx; Binding
0x18000fd99  mov     [rsp+38h+StringBinding], 0
0x18000fda2  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x18000fda7  mov     [rsp+38h+Protseq], 0
0x18000fdb0  call    cs:__imp_RpcBindingToStringBindingW
0x18000fdb6  mov     ebx, eax
0x18000fdb8  test    eax, eax
0x18000fdba  jnz     loc_18000FE45
0x18000fdc0  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18000fdc5  lea     r8, [rsp+38h+Protseq]; Protseq
0x18000fdca  mov     [rsp+38h+NetworkOptions], 0; NetworkOptions
0x18000fdd3  xor     r9d, r9d; NetworkAddr
0x18000fdd6  xor     edx, edx; ObjUuid
0x18000fdd8  mov     [rsp+38h+Endpoint], 0; Endpoint
0x18000fde1  call    cs:__imp_RpcStringBindingParseW
0x18000fde7  lea     rcx, [rsp+38h+StringBinding]; String
0x18000fdec  mov     ebx, eax
0x18000fdee  call    cs:__imp_RpcStringFreeW
0x18000fdf4  test    ebx, ebx
0x18000fdf6  jnz     short loc_18000FE45
0x18000fdf8  mov     rcx, [rsp+38h+Protseq]; lpString1
0x18000fdfd  lea     r8, String2; "ncalrpc"
0x18000fe04  or      edx, 0FFFFFFFFh; cchCount1
0x18000fe07  mov     dword ptr [rsp+38h+Endpoint], 1; bIgnoreCase
0x18000fe0f  mov     r9d, edx; cchCount2
0x18000fe12  call    cs:__imp_CompareStringOrdinal
0x18000fe18  cmp     eax, 2
0x18000fe1b  jz      short loc_18000FE24
0x18000fe1d  mov     ebx, 5
0x18000fe22  jmp     short loc_18000FE45
0x18000fe24  mov     ecx, 1
0x18000fe29  call    VerifyClientAccessToObject
0x18000fe2e  test    eax, eax
0x18000fe30  jz      short loc_18000FE1D
0x18000fe32  call    IsClientLocal
0x18000fe37  mov     ecx, ebx
0x18000fe39  test    eax, eax
0x18000fe3b  mov     ebx, 5
0x18000fe40  cmovz   ecx, ebx
0x18000fe43  mov     ebx, ecx
0x18000fe45  cmp     [rsp+38h+Protseq], 0
0x18000fe4b  jz      short loc_18000FE58
0x18000fe4d  lea     rcx, [rsp+38h+Protseq]; String
0x18000fe52  call    cs:__imp_RpcStringFreeW
0x18000fe58  mov     eax, ebx
0x18000fe5a  add     rsp, 30h
0x18000fe5e  pop     rbx
0x18000fe5f  retn
```
