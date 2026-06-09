# s_wscGetAlertStatus

- ea: `0x18001a630`
- end: `0x18001a6fc`
- name: `s_wscGetAlertStatus`
- size: `204`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x180008e48`
- `0x18001a630`
- `0x18001a710`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001a675`
- `RPCRT4!RpcRevertToSelf` at `0x18001a675`
- `RPCRT4!RpcImpersonateClient` at `0x18001a65a`
- `RPCRT4!RpcImpersonateClient` at `0x18001a65a`
- `RPCRT4!RpcRaiseException` at `0x18001a6c2`
- `RPCRT4!RpcRaiseException` at `0x18001a6c2`

## pseudocode

```c
__int64 __fastcall s_wscGetAlertStatus(void *a1, _DWORD *a2, int *a3)
{
  unsigned int v6; // eax
  unsigned int v7; // eax

  if ( !a2 || !a3 )
    return 87;
  v6 = RpcImpersonateClient(a1);
  if ( v6 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v6);
    }
    RpcRaiseException(5);
  }
  *a2 = CAlertStatus::GetAlertStatus((CAlertStatus *)g_pAlertStatus, a3);
  v7 = RpcRevertToSelf();
  if ( v7
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v7);
  }
  return 0;
}

```

## disassembly

```asm
0x18001a630  mov     [rsp+arg_0], rbx
0x18001a635  push    rdi
0x18001a636  sub     rsp, 20h
0x18001a63a  mov     rdi, r8
0x18001a63d  mov     rbx, rdx
0x18001a640  test    rdx, rdx
0x18001a643  jz      short loc_18001A64A
0x18001a645  test    r8, r8
0x18001a648  jnz     short loc_18001A65A
0x18001a64a  mov     eax, 57h ; 'W'
0x18001a64f  mov     rbx, [rsp+28h+arg_0]
0x18001a654  add     rsp, 20h
0x18001a658  pop     rdi
0x18001a659  retn
0x18001a65a  call    cs:__imp_RpcImpersonateClient
0x18001a660  test    eax, eax
0x18001a662  jnz     short loc_18001A68C
0x18001a664  mov     rcx, cs:?g_pAlertStatus@@3PEAVCAlertStatus@@EA; this
0x18001a66b  mov     rdx, rdi; int *
0x18001a66e  call    ?GetAlertStatus@CAlertStatus@@QEAAKPEAH@Z; CAlertStatus::GetAlertStatus(int *)
0x18001a673  mov     [rbx], eax
0x18001a675  call    cs:__imp_RpcRevertToSelf
0x18001a67b  test    eax, eax
0x18001a67d  jnz     short loc_18001A6C9
0x18001a67f  mov     rbx, [rsp+28h+arg_0]
0x18001a684  xor     eax, eax
0x18001a686  add     rsp, 20h
0x18001a68a  pop     rdi
0x18001a68b  retn
0x18001a68c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a693  lea     rdx, WPP_GLOBAL_Control
0x18001a69a  cmp     rcx, rdx
0x18001a69d  jz      short loc_18001A6BD
0x18001a69f  test    byte ptr [rcx+1Ch], 1
0x18001a6a3  jz      short loc_18001A6BD
0x18001a6a5  mov     rcx, [rcx+10h]
0x18001a6a9  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001a6b0  mov     edx, 1Bh
0x18001a6b5  mov     r9d, eax
0x18001a6b8  call    WPP_SF_d
0x18001a6bd  mov     ecx, 5; exception
0x18001a6c2  call    cs:__imp_RpcRaiseException
0x18001a6c8  int     3; Trap to Debugger
0x18001a6c9  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a6d0  lea     rdx, WPP_GLOBAL_Control
0x18001a6d7  cmp     rcx, rdx
0x18001a6da  jz      short loc_18001A67F
0x18001a6dc  test    byte ptr [rcx+1Ch], 1
0x18001a6e0  jz      short loc_18001A67F
0x18001a6e2  mov     rcx, [rcx+10h]
0x18001a6e6  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001a6ed  mov     edx, 1Ch
0x18001a6f2  mov     r9d, eax
0x18001a6f5  call    WPP_SF_d
0x18001a6fa  jmp     short loc_18001A67F
```
