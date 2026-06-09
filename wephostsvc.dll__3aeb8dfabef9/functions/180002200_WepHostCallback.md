# WepHostCallback

- ea: `0x180002200`
- end: `0x1800022b9`
- name: `WepHostCallback`
- size: `185`
- prototype: `__int64 __fastcall(__int64, void *)`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180002200`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002279`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180002279`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002220`
- `RPCRT4!RpcBindingToStringBindingW` at `0x180002220`
- `RPCRT4!RpcStringBindingParseW` at `0x18000224d`
- `RPCRT4!RpcStringBindingParseW` at `0x18000224d`
- `RPCRT4!RpcStringFreeW` at `0x180002298`
- `RPCRT4!RpcStringFreeW` at `0x1800022ab`
- `RPCRT4!RpcStringFreeW` at `0x180002298`
- `RPCRT4!RpcStringFreeW` at `0x1800022ab`

## pseudocode

```c
__int64 __fastcall WepHostCallback(__int64 a1, void *a2)
{
  unsigned int v2; // ebx
  RPC_WSTR Protseq; // [rsp+50h] [rbp+18h] BYREF
  RPC_WSTR StringBinding; // [rsp+58h] [rbp+20h] BYREF

  StringBinding = 0;
  Protseq = 0;
  v2 = RpcBindingToStringBindingW(a2, &StringBinding);
  if ( !v2 )
  {
    v2 = RpcStringBindingParseW(StringBinding, 0, &Protseq, 0, 0, 0);
    if ( !v2 )
      v2 = CompareStringW(0x7Fu, 1u, Protseq, -1, L"ncalrpc", -1) != 2 ? 5 : 0;
  }
  if ( Protseq )
    RpcStringFreeW(&Protseq);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v2;
}

```

## disassembly

```asm
0x180002200  push    rbx
0x180002202  sub     rsp, 30h
0x180002206  mov     rcx, rdx; Binding
0x180002209  mov     [rsp+38h+StringBinding], 0
0x180002212  lea     rdx, [rsp+38h+StringBinding]; StringBinding
0x180002217  mov     [rsp+38h+Protseq], 0
0x180002220  call    cs:__imp_RpcBindingToStringBindingW
0x180002226  mov     ebx, eax
0x180002228  test    eax, eax
0x18000222a  jnz     short loc_18000228B
0x18000222c  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x180002231  lea     r8, [rsp+38h+Protseq]; Protseq
0x180002236  mov     [rsp+38h+NetworkOptions], 0; NetworkOptions
0x18000223f  xor     r9d, r9d; NetworkAddr
0x180002242  xor     edx, edx; ObjUuid
0x180002244  mov     [rsp+38h+Endpoint], 0; Endpoint
0x18000224d  call    cs:__imp_RpcStringBindingParseW
0x180002253  mov     ebx, eax
0x180002255  test    eax, eax
0x180002257  jnz     short loc_18000228B
0x180002259  mov     r8, [rsp+38h+Protseq]; lpString1
0x18000225e  lea     rax, Protseq; "ncalrpc"
0x180002265  or      r9d, 0FFFFFFFFh; cchCount1
0x180002269  lea     edx, [rbx+1]; dwCmpFlags
0x18000226c  mov     dword ptr [rsp+38h+NetworkOptions], r9d; cchCount2
0x180002271  lea     ecx, [rbx+7Fh]; Locale
0x180002274  mov     [rsp+38h+Endpoint], rax; lpString2
0x180002279  call    cs:__imp_CompareStringW
0x18000227f  lea     ecx, [rbx+2]
0x180002282  sub     ecx, eax
0x180002284  neg     ecx
0x180002286  sbb     ebx, ebx
0x180002288  and     ebx, 5
0x18000228b  cmp     [rsp+38h+Protseq], 0
0x180002291  jz      short loc_18000229E
0x180002293  lea     rcx, [rsp+38h+Protseq]; String
0x180002298  call    cs:__imp_RpcStringFreeW
0x18000229e  cmp     [rsp+38h+StringBinding], 0
0x1800022a4  jz      short loc_1800022B1
0x1800022a6  lea     rcx, [rsp+38h+StringBinding]; String
0x1800022ab  call    cs:__imp_RpcStringFreeW
0x1800022b1  mov     eax, ebx
0x1800022b3  add     rsp, 30h
0x1800022b7  pop     rbx
0x1800022b8  retn
```
