# RfsRpcBindingInitialize

- ea: `0x1400411a0`
- end: `0x14004120f`
- name: `RfsRpcBindingInitialize`
- size: `111`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE_TEMPLATE_V1_W *Template, RPC_BINDING_HANDLE_SECURITY_V1_W *Security, RPC_BINDING_HANDLE_OPTIONS_V1 *Options)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140056e3c`

## callees

- `0x14002a840`
- `0x1400411a0`

## import_xrefs

- `msrpc!RpcBindingCreateW` at `0x1400411e8`
- `msrpc!RpcBindingCreateW` at `0x1400411e8`

## pseudocode

```c
RPC_STATUS __fastcall RfsRpcBindingInitialize(
        RPC_BINDING_HANDLE_TEMPLATE_V1_W *Template,
        RPC_BINDING_HANDLE_SECURITY_V1_W *Security,
        RPC_BINDING_HANDLE_OPTIONS_V1 *Options)
{
  memset(&SrvIdSegRpcBinding, 0, 0x40u);
  qword_140036FB8 = (__int64)qword_14002E0E0;
  return RpcBindingCreateW(Template, Security, Options, &SrvIdSegRpcBinding);
}

```

## disassembly

```asm
0x1400411a0  mov     [rsp+arg_0], rbx
0x1400411a5  mov     [rsp+arg_8], rsi
0x1400411aa  push    rdi
0x1400411ab  sub     rsp, 30h
0x1400411af  mov     rbx, r8
0x1400411b2  mov     rdi, rdx
0x1400411b5  mov     rsi, rcx
0x1400411b8  xor     edx, edx; Val
0x1400411ba  lea     r8d, [rdx+40h]; Size
0x1400411be  lea     rcx, SrvIdSegRpcBinding; void *
0x1400411c5  call    memset
0x1400411ca  lea     rax, qword_14002E0E0
0x1400411d1  mov     cs:qword_140036FB8, rax
0x1400411d8  lea     r9, SrvIdSegRpcBinding; Binding
0x1400411df  mov     r8, rbx; Options
0x1400411e2  mov     rdx, rdi; Security
0x1400411e5  mov     rcx, rsi; Template
0x1400411e8  call    cs:__imp_RpcBindingCreateW
0x1400411ef  nop     dword ptr [rax+rax+00h]
0x1400411f4  mov     [rsp+38h+var_18], eax
0x1400411f8  jmp     short loc_1400411FE
0x1400411fa  mov     [rsp+38h+var_18], eax
0x1400411fe  mov     rbx, [rsp+38h+arg_0]
0x140041203  mov     rsi, [rsp+38h+arg_8]
0x140041208  add     rsp, 30h
0x14004120c  pop     rdi
0x14004120d  retn
0x1400574e0  push    rbp
0x1400574e2  sub     rsp, 20h
0x1400574e6  mov     rbp, rdx
0x1400574e9  mov     rcx, [rcx]
0x1400574ec  mov     ecx, [rcx]; ExceptionCode
0x1400574ee  call    cs:__imp_I_RpcExceptionFilter
0x1400574f5  nop     dword ptr [rax+rax+00h]
0x1400574fa  nop
0x1400574fb  add     rsp, 20h
0x1400574ff  pop     rbp
0x140057500  retn
```
