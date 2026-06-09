# SecpGetRpcBinding

- ea: `0x18000b9f4`
- end: `0x18000ba85`
- name: `SecpGetRpcBinding`
- size: `145`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b940`

## callees

- `0x18000b9f4`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18000ba5c`
- `RPCRT4!RpcStringFreeW` at `0x18000ba5c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ba7d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000ba7d`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ba39`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000ba39`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ba4f`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000ba4f`

## pseudocode

```c
int __fastcall SecpGetRpcBinding(RPC_BINDING_HANDLE *a1)
{
  RPC_STATUS v2; // ebx
  RPC_WSTR StringBinding; // [rsp+48h] [rbp+10h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+50h] [rbp+18h] BYREF

  StringBinding = 0;
  Binding = 0;
  v2 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncalrpc",
         0,
         (RPC_WSTR)L"lsasspirpc",
         (RPC_WSTR)&qword_1800319E0,
         &StringBinding);
  if ( v2 )
    return I_RpcMapWin32Status(v2);
  v2 = RpcBindingFromStringBindingW(StringBinding, &Binding);
  RpcStringFreeW(&StringBinding);
  if ( v2 )
    return I_RpcMapWin32Status(v2);
  *a1 = Binding;
  return 0;
}

```

## disassembly

```asm
0x18000b9f4  mov     r11, rsp
0x18000b9f7  mov     [r11+8], rbx
0x18000b9fb  push    rdi
0x18000b9fc  sub     rsp, 30h
0x18000ba00  lea     rax, [r11+10h]
0x18000ba04  mov     qword ptr [r11+10h], 0
0x18000ba0c  mov     [r11-10h], rax
0x18000ba10  lea     r9, Endpoint; "lsasspirpc"
0x18000ba17  lea     rax, qword_1800319E0
0x18000ba1e  mov     qword ptr [r11+18h], 0
0x18000ba26  mov     rdi, rcx
0x18000ba29  mov     [r11-18h], rax
0x18000ba2d  xor     r8d, r8d; NetworkAddr
0x18000ba30  lea     rdx, ProtSeq; "ncalrpc"
0x18000ba37  xor     ecx, ecx; ObjUuid
0x18000ba39  call    cs:__imp_RpcStringBindingComposeW
0x18000ba3f  mov     ebx, eax
0x18000ba41  test    eax, eax
0x18000ba43  jnz     short loc_18000BA7B
0x18000ba45  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18000ba4a  lea     rdx, [rsp+38h+Binding]; Binding
0x18000ba4f  call    cs:__imp_RpcBindingFromStringBindingW
0x18000ba55  lea     rcx, [rsp+38h+StringBinding]; String
0x18000ba5a  mov     ebx, eax
0x18000ba5c  call    cs:__imp_RpcStringFreeW
0x18000ba62  test    ebx, ebx
0x18000ba64  jnz     short loc_18000BA7B
0x18000ba66  mov     rax, [rsp+38h+Binding]
0x18000ba6b  mov     [rdi], rax
0x18000ba6e  xor     eax, eax
0x18000ba70  mov     rbx, [rsp+38h+arg_0]
0x18000ba75  add     rsp, 30h
0x18000ba79  pop     rdi
0x18000ba7a  retn
0x18000ba7b  mov     ecx, ebx; Status
0x18000ba7d  call    cs:__imp_I_RpcMapWin32Status
0x18000ba83  jmp     short loc_18000BA70
```
