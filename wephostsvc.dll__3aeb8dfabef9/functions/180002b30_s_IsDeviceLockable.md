# s_IsDeviceLockable

- ea: `0x180002b30`
- end: `0x180002c38`
- name: `s_IsDeviceLockable`
- size: `264`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x1800026e0`
- `0x180002b30`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c25`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002c25`
- `RPCRT4!RpcImpersonateClient` at `0x180002b3c`
- `RPCRT4!RpcImpersonateClient` at `0x180002b3c`

## pseudocode

```c
__int64 s_IsDeviceLockable()
{
  RPC_STATUS v0; // eax
  unsigned int v1; // ebx
  int v2; // eax
  _QWORD *v3; // rcx
  __int64 v4; // rdx

  v0 = RpcImpersonateClient(0);
  v1 = v0;
  if ( !v0 )
  {
    v2 = CheckCallerAdminAccess();
    v1 = v2;
    if ( v2 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v2 = (*(&g_Table + 1))();
      v1 = v2;
      if ( !v2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        goto LABEL_19;
      }
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        RevertToSelf();
        return v1;
      }
      v4 = 15;
    }
    else
    {
      v3 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v4 = 13;
    }
    WPP_SF_D(v3[2], v4, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, (unsigned int)v2);
    goto LABEL_19;
  }
  if ( v0 >= 0 )
    return (unsigned __int16)v0 | 0x80010000;
  return v1;
}

```

## disassembly

```asm
0x180002b30  mov     [rsp+arg_0], rbx
0x180002b35  push    rdi
0x180002b36  sub     rsp, 20h
0x180002b3a  xor     ecx, ecx; BindingHandle
0x180002b3c  call    cs:__imp_RpcImpersonateClient
0x180002b42  mov     ebx, eax
0x180002b44  test    eax, eax
0x180002b46  jz      short loc_180002B5C
0x180002b48  js      loc_180002C2B
0x180002b4e  movzx   ebx, ax
0x180002b51  or      ebx, 80010000h
0x180002b57  jmp     loc_180002C2B
0x180002b5c  call    ?CheckCallerAdminAccess@@YAJXZ; CheckCallerAdminAccess(void)
0x180002b61  mov     ebx, eax
0x180002b63  test    eax, eax
0x180002b65  jns     short loc_180002BA5
0x180002b67  mov     rcx, cs:WPP_GLOBAL_Control
0x180002b6e  lea     rdi, WPP_GLOBAL_Control
0x180002b75  cmp     rcx, rdi
0x180002b78  jz      loc_180002C25
0x180002b7e  test    byte ptr [rcx+1Ch], 1
0x180002b82  jz      loc_180002C25
0x180002b88  mov     edx, 0Dh
0x180002b8d  mov     rcx, [rcx+10h]
0x180002b91  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002b98  mov     r9d, eax
0x180002b9b  call    WPP_SF_D
0x180002ba0  jmp     loc_180002C25
0x180002ba5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bac  lea     rdi, WPP_GLOBAL_Control
0x180002bb3  cmp     rcx, rdi
0x180002bb6  jz      short loc_180002BD3
0x180002bb8  test    byte ptr [rcx+1Ch], 20h
0x180002bbc  jz      short loc_180002BD3
0x180002bbe  mov     rcx, [rcx+10h]
0x180002bc2  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002bc9  mov     edx, 0Eh
0x180002bce  call    WPP_SF_
0x180002bd3  mov     rax, qword ptr cs:?g_Table@@3U_tagPluginAPITable@@A+8; _tagPluginAPITable g_Table
0x180002bda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002bdf  mov     ebx, eax
0x180002be1  test    eax, eax
0x180002be3  jz      short loc_180002BFE
0x180002be5  mov     rcx, cs:WPP_GLOBAL_Control
0x180002bec  cmp     rcx, rdi
0x180002bef  jz      short loc_180002C25
0x180002bf1  test    byte ptr [rcx+1Ch], 1
0x180002bf5  jz      short loc_180002C25
0x180002bf7  mov     edx, 0Fh
0x180002bfc  jmp     short loc_180002B8D
0x180002bfe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c05  cmp     rcx, rdi
0x180002c08  jz      short loc_180002C25
0x180002c0a  test    byte ptr [rcx+1Ch], 20h
0x180002c0e  jz      short loc_180002C25
0x180002c10  mov     rcx, [rcx+10h]
0x180002c14  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002c1b  mov     edx, 10h
0x180002c20  call    WPP_SF_
0x180002c25  call    cs:__imp_RevertToSelf
0x180002c2b  mov     eax, ebx
0x180002c2d  mov     rbx, [rsp+28h+arg_0]
0x180002c32  add     rsp, 20h
0x180002c36  pop     rdi
0x180002c37  retn
```
