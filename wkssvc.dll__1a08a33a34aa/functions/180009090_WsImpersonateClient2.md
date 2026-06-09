# WsImpersonateClient2

- ea: `0x180009090`
- end: `0x18000910a`
- name: `WsImpersonateClient2`
- size: `122`
- prototype: ``
- caller_count: `23`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800012a0`
- `0x180001750`
- `0x1800089ac`
- `0x180022510`
- `0x180022dd0`
- `0x1800233b0`
- `0x180023930`
- `0x180025164`
- `0x180026bc8`
- `0x1800288a8`
- `0x18002a1a0`
- `0x18002a610`
- `0x18002a7a0`
- `0x18002a930`
- `0x18002aae0`
- `0x18002ae70`
- `0x18002b0d0`
- `0x18002b510`
- `0x18002b6c0`
- `0x18002b870`
- `0x18002b9f0`
- `0x1800308e0`
- `0x180031b70`

## callees

- `0x180009090`
- `0x180031878`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800090a1`
- `RPCRT4!RpcImpersonateClient` at `0x1800090a1`

## pseudocode

```c
RPC_STATUS __fastcall WsImpersonateClient2(const char *a1, char a2)
{
  RPC_STATUS result; // eax
  int v5; // r8d

  result = RpcImpersonateClient(0);
  if ( result )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) )
    {
      if ( !a1 )
        a1 = "unknown";
      WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, v5, (_DWORD)a1, a2, result);
    }
    return 5;
  }
  return result;
}

```

## disassembly

```asm
0x180009090  mov     [rsp+arg_0], rbx
0x180009095  push    rdi
0x180009096  sub     rsp, 30h
0x18000909a  mov     rbx, rcx
0x18000909d  mov     edi, edx
0x18000909f  xor     ecx, ecx; BindingHandle
0x1800090a1  call    cs:__imp_RpcImpersonateClient
0x1800090a8  nop     dword ptr [rax+rax+00h]
0x1800090ad  test    eax, eax
0x1800090af  jnz     short loc_1800090BD
0x1800090b1  mov     rbx, [rsp+38h+arg_0]
0x1800090b6  add     rsp, 30h
0x1800090ba  pop     rdi
0x1800090bb  retn
0x1800090bd  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800090c4  lea     rdx, WPP_GLOBAL_Control
0x1800090cb  cmp     rcx, rdx
0x1800090ce  jz      short loc_180009103
0x1800090d0  test    byte ptr [rcx+1Ch], 4
0x1800090d4  jz      short loc_180009103
0x1800090d6  cmp     byte ptr [rcx+19h], 1
0x1800090da  jb      short loc_180009103
0x1800090dc  mov     rcx, [rcx+10h]
0x1800090e0  lea     rdx, aUnknown; "unknown"
0x1800090e7  test    rbx, rbx
0x1800090ea  mov     [rsp+38h+var_10], eax
0x1800090ee  mov     [rsp+38h+var_18], edi
0x1800090f2  cmovz   rbx, rdx
0x1800090f6  mov     edx, 0Ah
0x1800090fb  mov     r9, rbx
0x1800090fe  call    WPP_SF_sdL
0x180009103  mov     eax, 5
0x180009108  jmp     short loc_1800090B1
```
