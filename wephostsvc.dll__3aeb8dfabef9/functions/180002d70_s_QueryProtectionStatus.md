# s_QueryProtectionStatus

- ea: `0x180002d70`
- end: `0x180002e60`
- name: `s_QueryProtectionStatus`
- size: `240`
- prototype: `__int64 __fastcall(__int64, unsigned int *, int *)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e04`
- `0x1800026e0`
- `0x180002708`
- `0x180002d70`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002e4f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002e4f`
- `RPCRT4!RpcImpersonateClient` at `0x180002d81`
- `RPCRT4!RpcImpersonateClient` at `0x180002d81`

## pseudocode

```c
__int64 __fastcall s_QueryProtectionStatus(__int64 a1, unsigned int *a2, int *a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // r9
  int v10; // eax

  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( v5 )
  {
    if ( v5 >= 0 )
      return (unsigned __int16)v5 | 0x80010000;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
    v7 = g_Table(a2, a3);
    v6 = v7;
    if ( v7 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
      {
        v9 = 0xFFFFFFFFLL;
        if ( a3 )
          v10 = *a3;
        else
          v10 = -1;
        if ( a2 )
          v9 = *a2;
        WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, v8, v9, v10);
      }
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        11,
        &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids,
        (unsigned int)v7);
    }
    RevertToSelf();
  }
  return v6;
}

```

## disassembly

```asm
0x180002d70  push    rbx
0x180002d72  push    rbp
0x180002d73  push    rsi
0x180002d74  push    rdi
0x180002d75  sub     rsp, 38h
0x180002d79  xor     ecx, ecx; BindingHandle
0x180002d7b  mov     rdi, r8
0x180002d7e  mov     rsi, rdx
0x180002d81  call    cs:__imp_RpcImpersonateClient
0x180002d87  mov     ebx, eax
0x180002d89  test    eax, eax
0x180002d8b  jz      short loc_180002DA1
0x180002d8d  js      loc_180002E55
0x180002d93  movzx   ebx, ax
0x180002d96  or      ebx, 80010000h
0x180002d9c  jmp     loc_180002E55
0x180002da1  mov     rcx, cs:WPP_GLOBAL_Control
0x180002da8  lea     rbp, WPP_GLOBAL_Control
0x180002daf  cmp     rcx, rbp
0x180002db2  jz      short loc_180002DCF
0x180002db4  test    byte ptr [rcx+1Ch], 20h
0x180002db8  jz      short loc_180002DCF
0x180002dba  mov     rcx, [rcx+10h]
0x180002dbe  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002dc5  mov     edx, 0Ah
0x180002dca  call    WPP_SF_
0x180002dcf  mov     rax, qword ptr cs:?g_Table@@3U_tagPluginAPITable@@A; _tagPluginAPITable g_Table
0x180002dd6  mov     rdx, rdi
0x180002dd9  mov     rcx, rsi
0x180002ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002de1  mov     ebx, eax
0x180002de3  test    eax, eax
0x180002de5  jns     short loc_180002E13
0x180002de7  mov     rcx, cs:WPP_GLOBAL_Control
0x180002dee  cmp     rcx, rbp
0x180002df1  jz      short loc_180002E4F
0x180002df3  test    byte ptr [rcx+1Ch], 1
0x180002df7  jz      short loc_180002E4F
0x180002df9  mov     rcx, [rcx+10h]
0x180002dfd  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002e04  mov     edx, 0Bh
0x180002e09  mov     r9d, eax
0x180002e0c  call    WPP_SF_D
0x180002e11  jmp     short loc_180002E4F
0x180002e13  mov     rcx, cs:WPP_GLOBAL_Control
0x180002e1a  cmp     rcx, rbp
0x180002e1d  jz      short loc_180002E4F
0x180002e1f  test    byte ptr [rcx+1Ch], 20h
0x180002e23  jz      short loc_180002E4F
0x180002e25  or      r9d, 0FFFFFFFFh
0x180002e29  test    rdi, rdi
0x180002e2c  jz      short loc_180002E32
0x180002e2e  mov     eax, [rdi]
0x180002e30  jmp     short loc_180002E35
0x180002e32  mov     eax, r9d
0x180002e35  test    rsi, rsi
0x180002e38  jz      short loc_180002E3D
0x180002e3a  mov     r9d, [rsi]
0x180002e3d  mov     rcx, [rcx+10h]
0x180002e41  mov     edx, 0Ch
0x180002e46  mov     [rsp+58h+var_38], eax
0x180002e4a  call    WPP_SF_DD
0x180002e4f  call    cs:__imp_RevertToSelf
0x180002e55  mov     eax, ebx
0x180002e57  add     rsp, 38h
0x180002e5b  pop     rdi
0x180002e5c  pop     rsi
0x180002e5d  pop     rbp
0x180002e5e  pop     rbx
0x180002e5f  retn
```
