# ScClientBindToServerUsingNamedPipes(ushort *,void * *)

- ea: `0x18003ad54`
- end: `0x18003add4`
- name: `?ScClientBindToServerUsingNamedPipes@@YAKPEAGPEAPEAX@Z`
- size: `128`
- prototype: `unsigned int __fastcall(RPC_WSTR NetworkAddr, RPC_BINDING_HANDLE *Binding)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18000b9a0`
- `0x18003ac6c`

## callees

- `0x18003ad54`

## import_xrefs

- `RPCRT4!RpcStringFreeW` at `0x18003adc1`
- `RPCRT4!RpcStringFreeW` at `0x18003adc1`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003adac`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18003adac`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003ad98`
- `RPCRT4!RpcStringBindingComposeW` at `0x18003ad98`

## string_xrefs

- `0x18003ad76`: `Security=Impersonation Dynamic False`

## pseudocode

```c
__int64 __fastcall ScClientBindToServerUsingNamedPipes(RPC_WSTR NetworkAddr, RPC_BINDING_HANDLE *Binding)
{
  unsigned int v3; // ebx
  RPC_WSTR StringBinding; // [rsp+48h] [rbp+10h] BYREF

  *Binding = 0;
  StringBinding = 0;
  v3 = RpcStringBindingComposeW(
         0,
         (RPC_WSTR)L"ncacn_np",
         NetworkAddr,
         (RPC_WSTR)L"\\pipe\\svcctl",
         L"Security=Impersonation Dynamic False",
         &StringBinding);
  if ( !v3 )
    v3 = RpcBindingFromStringBindingW(StringBinding, Binding);
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  return v3;
}

```

## disassembly

```asm
0x18003ad54  mov     r11, rsp
0x18003ad57  mov     [r11+8], rbx
0x18003ad5b  push    rdi
0x18003ad5c  sub     rsp, 30h
0x18003ad60  lea     rax, [r11+10h]
0x18003ad64  mov     qword ptr [rdx], 0
0x18003ad6b  mov     [r11-10h], rax
0x18003ad6f  lea     r9, aPipeSvcctl; "\\pipe\\svcctl"
0x18003ad76  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic False"
0x18003ad7d  mov     qword ptr [r11+10h], 0
0x18003ad85  mov     rdi, rdx
0x18003ad88  mov     [r11-18h], rax
0x18003ad8c  mov     r8, rcx; NetworkAddr
0x18003ad8f  lea     rdx, ProtSeq; "ncacn_np"
0x18003ad96  xor     ecx, ecx; ObjUuid
0x18003ad98  call    cs:__imp_RpcStringBindingComposeW
0x18003ad9e  mov     ebx, eax
0x18003ada0  test    eax, eax
0x18003ada2  jnz     short loc_18003ADB4
0x18003ada4  mov     rcx, [rsp+38h+StringBinding]; StringBinding
0x18003ada9  mov     rdx, rdi; Binding
0x18003adac  call    cs:__imp_RpcBindingFromStringBindingW
0x18003adb2  mov     ebx, eax
0x18003adb4  cmp     [rsp+38h+StringBinding], 0
0x18003adba  jz      short loc_18003ADC7
0x18003adbc  lea     rcx, [rsp+38h+StringBinding]; String
0x18003adc1  call    cs:__imp_RpcStringFreeW
0x18003adc7  mov     eax, ebx
0x18003adc9  mov     rbx, [rsp+38h+arg_0]
0x18003adce  add     rsp, 30h
0x18003add2  pop     rdi
0x18003add3  retn
```
