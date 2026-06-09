# STRING_BINDING_HANDLE_bind

- ea: `0x1800050d0`
- end: `0x1800051be`
- name: `STRING_BINDING_HANDLE_bind`
- size: `238`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800050d0`
- `0x180005230`
- `0x180008a90`

## import_xrefs

- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000513a`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x18000513a`
- `RPCRT4!RpcBindingSetOption` at `0x18000515c`
- `RPCRT4!RpcBindingSetOption` at `0x18000515c`
- `RPCRT4!RpcStringFreeW` at `0x180005176`
- `RPCRT4!RpcStringFreeW` at `0x180005176`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000511e`
- `RPCRT4!RpcStringBindingComposeW` at `0x18000511e`

## string_xrefs

- `0x180005101`: `Security=Impersonation Dynamic False`

## pseudocode

```c
RPC_BINDING_HANDLE __fastcall STRING_BINDING_HANDLE_bind(__int64 a1)
{
  RPC_STATUS v2; // ebx
  RPC_BINDING_HANDLE result; // rax
  RPC_WSTR StringBinding; // [rsp+30h] [rbp-28h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+38h] [rbp-20h] BYREF

  StringBinding = 0;
  Binding = 0;
  v2 = RpcStringBindingComposeW(0, (RPC_WSTR)L"ncalrpc", 0, 0, L"Security=Impersonation Dynamic False", &StringBinding);
  if ( !v2 )
  {
    v2 = RpcBindingFromStringBindingW(StringBinding, &Binding);
    if ( !v2 )
      v2 = RpcBindingSetOption(Binding, 9u, 1u);
  }
  if ( StringBinding )
    RpcStringFreeW(&StringBinding);
  result = Binding;
  if ( v2 )
  {
    if ( Binding )
    {
      STRING_BINDING_HANDLE_unbind(a1, Binding);
      return 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800050d0  mov     r11, rsp
0x1800050d3  mov     [r11+8], rbx
0x1800050d7  mov     [r11+10h], rsi
0x1800050db  push    rdi
0x1800050dc  sub     rsp, 50h
0x1800050e0  mov     rax, cs:__security_cookie
0x1800050e7  xor     rax, rsp
0x1800050ea  mov     [rsp+58h+var_18], rax
0x1800050ef  lea     rax, [r11-28h]
0x1800050f3  mov     rdi, rcx
0x1800050f6  mov     [r11-30h], rax
0x1800050fa  lea     rdx, ProtSeq; "ncalrpc"
0x180005101  lea     rax, aSecurityImpers; "Security=Impersonation Dynamic False"
0x180005108  xor     esi, esi
0x18000510a  xor     r9d, r9d; Endpoint
0x18000510d  mov     [r11-38h], rax
0x180005111  xor     r8d, r8d; NetworkAddr
0x180005114  mov     [r11-28h], rsi
0x180005118  xor     ecx, ecx; ObjUuid
0x18000511a  mov     [r11-20h], rsi
0x18000511e  call    cs:__imp_RpcStringBindingComposeW
0x180005125  nop     dword ptr [rax+rax+00h]
0x18000512a  mov     ebx, eax
0x18000512c  test    eax, eax
0x18000512e  jnz     short loc_18000516A
0x180005130  mov     rcx, [rsp+58h+StringBinding]; StringBinding
0x180005135  lea     rdx, [rsp+58h+Binding]; Binding
0x18000513a  call    cs:__imp_RpcBindingFromStringBindingW
0x180005141  nop     dword ptr [rax+rax+00h]
0x180005146  mov     ebx, eax
0x180005148  test    eax, eax
0x18000514a  jnz     short loc_18000516A
0x18000514c  mov     rcx, [rsp+58h+Binding]; hBinding
0x180005151  mov     edx, 9; option
0x180005156  mov     r8d, 1; optionValue
0x18000515c  call    cs:__imp_RpcBindingSetOption
0x180005163  nop     dword ptr [rax+rax+00h]
0x180005168  mov     ebx, eax
0x18000516a  cmp     [rsp+58h+StringBinding], rsi
0x18000516f  jz      short loc_180005182
0x180005171  lea     rcx, [rsp+58h+StringBinding]; String
0x180005176  call    cs:__imp_RpcStringFreeW
0x18000517d  nop     dword ptr [rax+rax+00h]
0x180005182  mov     rax, [rsp+58h+Binding]
0x180005187  test    ebx, ebx
0x180005189  jnz     short loc_1800051A9
0x18000518b  mov     rcx, [rsp+58h+var_18]
0x180005190  xor     rcx, rsp; StackCookie
0x180005193  call    __security_check_cookie
0x180005198  mov     rbx, [rsp+58h+arg_0]
0x18000519d  mov     rsi, [rsp+58h+arg_8]
0x1800051a2  add     rsp, 50h
0x1800051a6  pop     rdi
0x1800051a7  retn
0x1800051a9  test    rax, rax
0x1800051ac  jz      short loc_18000518B
0x1800051ae  mov     rdx, rax
0x1800051b1  mov     rcx, rdi
0x1800051b4  call    STRING_BINDING_HANDLE_unbind
0x1800051b9  mov     rax, rsi
0x1800051bc  jmp     short loc_18000518B
```
