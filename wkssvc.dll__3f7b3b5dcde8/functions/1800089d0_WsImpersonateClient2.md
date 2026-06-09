# WsImpersonateClient2

- ea: `0x1800089d0`
- end: `0x180008a43`
- name: `WsImpersonateClient2`
- size: `115`
- prototype: `RPC_STATUS __fastcall(const char *, char)`
- caller_count: `23`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x1800012a0`
- `0x180001710`
- `0x1800084d8`
- `0x180020d14`
- `0x180021540`
- `0x180021ad0`
- `0x180021ff0`
- `0x18002373c`
- `0x180024f40`
- `0x180026840`
- `0x180027e70`
- `0x180028260`
- `0x1800283e0`
- `0x180028560`
- `0x180028700`
- `0x180028a80`
- `0x180028cb0`
- `0x1800290c0`
- `0x180029250`
- `0x1800293e0`
- `0x180029540`
- `0x18002de90`
- `0x18002ef7c`

## callees

- `0x1800089d0`
- `0x18002ecc0`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x1800089e1`
- `RPCRT4!RpcImpersonateClient` at `0x1800089e1`

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
0x1800089d0  mov     [rsp+arg_0], rbx
0x1800089d5  push    rdi
0x1800089d6  sub     rsp, 30h
0x1800089da  mov     rbx, rcx
0x1800089dd  mov     edi, edx
0x1800089df  xor     ecx, ecx; BindingHandle
0x1800089e1  call    cs:__imp_RpcImpersonateClient
0x1800089e7  test    eax, eax
0x1800089e9  jnz     short loc_1800089F6
0x1800089eb  mov     rbx, [rsp+38h+arg_0]
0x1800089f0  add     rsp, 30h
0x1800089f4  pop     rdi
0x1800089f5  retn
0x1800089f6  mov     rcx, cs:WPP_GLOBAL_Control; __annotation("TMF:",
0x1800089fd  lea     rdx, WPP_GLOBAL_Control
0x180008a04  cmp     rcx, rdx
0x180008a07  jz      short loc_180008A3C
0x180008a09  test    byte ptr [rcx+1Ch], 4
0x180008a0d  jz      short loc_180008A3C
0x180008a0f  cmp     byte ptr [rcx+19h], 1
0x180008a13  jb      short loc_180008A3C
0x180008a15  mov     rcx, [rcx+10h]
0x180008a19  lea     rdx, aUnknown; "unknown"
0x180008a20  test    rbx, rbx
0x180008a23  mov     [rsp+38h+var_10], eax
0x180008a27  mov     [rsp+38h+var_18], edi
0x180008a2b  cmovz   rbx, rdx
0x180008a2f  mov     edx, 0Ah
0x180008a34  mov     r9, rbx
0x180008a37  call    WPP_SF_sdL
0x180008a3c  mov     eax, 5
0x180008a41  jmp     short loc_1800089EB
```
