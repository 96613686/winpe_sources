# SsImpersonateClient

- ea: `0x180028928`
- end: `0x18002899d`
- name: `SsImpersonateClient`
- size: `117`
- prototype: ``
- caller_count: `5`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x180022ff0`
- `0x180031c8c`
- `0x180032480`
- `0x1800329f0`
- `0x180032f00`

## callees

- `0x180028928`
- `0x180028cb8`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x180028939`
- `RPCRT4!RpcImpersonateClient` at `0x180028939`

## pseudocode

```c
__int64 __fastcall SsImpersonateClient(const char *a1, char a2)
{
  RPC_STATUS v4; // eax
  int v5; // r8d

  v4 = RpcImpersonateClient(0);
  if ( !v4 )
    return 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) )
  {
    if ( !a1 )
      a1 = "unknown";
    WPP_SF_sdL(*((_QWORD *)WPP_GLOBAL_Control + 2), 21, v5, (_DWORD)a1, a2, v4);
  }
  return 5;
}

```

## disassembly

```asm
0x180028928  mov     [rsp+arg_0], rbx
0x18002892d  push    rdi
0x18002892e  sub     rsp, 30h
0x180028932  mov     rbx, rcx
0x180028935  mov     edi, edx
0x180028937  xor     ecx, ecx; BindingHandle
0x180028939  call    cs:__imp_RpcImpersonateClient
0x18002893f  test    eax, eax
0x180028941  jz      short loc_180028990
0x180028943  mov     rcx, cs:WPP_GLOBAL_Control
0x18002894a  lea     rdx, WPP_GLOBAL_Control
0x180028951  cmp     rcx, rdx
0x180028954  jz      short loc_180028989
0x180028956  test    byte ptr [rcx+1Ch], 1
0x18002895a  jz      short loc_180028989
0x18002895c  cmp     byte ptr [rcx+19h], 1
0x180028960  jb      short loc_180028989
0x180028962  mov     rcx, [rcx+10h]
0x180028966  lea     rdx, aUnknown; "unknown"
0x18002896d  test    rbx, rbx
0x180028970  mov     [rsp+38h+var_10], eax
0x180028974  mov     [rsp+38h+var_18], edi
0x180028978  cmovz   rbx, rdx
0x18002897c  mov     edx, 15h
0x180028981  mov     r9, rbx
0x180028984  call    WPP_SF_sdL
0x180028989  mov     eax, 5
0x18002898e  jmp     short loc_180028992
0x180028990  xor     eax, eax
0x180028992  mov     rbx, [rsp+38h+arg_0]
0x180028997  add     rsp, 30h
0x18002899b  pop     rdi
0x18002899c  retn
```
