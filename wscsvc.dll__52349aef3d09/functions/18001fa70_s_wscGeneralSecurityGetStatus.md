# s_wscGeneralSecurityGetStatus

- ea: `0x18001fa70`
- end: `0x18001fb1d`
- name: `s_wscGeneralSecurityGetStatus`
- size: `173`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180008e48`
- `0x18001fa70`
- `0x180042010`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x18001fa9b`
- `RPCRT4!RpcRevertToSelf` at `0x18001fa9b`
- `RPCRT4!RpcImpersonateClient` at `0x18001fa79`
- `RPCRT4!RpcImpersonateClient` at `0x18001fa79`
- `RPCRT4!RpcRaiseException` at `0x18001fae3`
- `RPCRT4!RpcRaiseException` at `0x18001fae3`

## pseudocode

```c
__int64 __fastcall s_wscGeneralSecurityGetStatus(void *a1, _DWORD *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax

  v3 = RpcImpersonateClient(a1);
  if ( v3 )
  {
    if ( WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v3);
    }
    RpcRaiseException(5);
  }
  *a2 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)g_pSecureSettingsManager + 24LL))(*(_QWORD *)g_pSecureSettingsManager);
  v4 = RpcRevertToSelf();
  if ( v4
    && WPP_GLOBAL_Control != (CThirdPartyManager *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_58c7d8ca840131a6c20521327163655c_Traceguids, v4);
  }
  return 0;
}

```

## disassembly

```asm
0x18001fa70  push    rbx
0x18001fa72  sub     rsp, 20h
0x18001fa76  mov     rbx, rdx
0x18001fa79  call    cs:__imp_RpcImpersonateClient
0x18001fa7f  test    eax, eax
0x18001fa81  jnz     short loc_18001FAAD
0x18001fa83  mov     rax, cs:?g_pSecureSettingsManager@@3PEAVCSecureSettingsManager@@EA; CSecureSettingsManager * g_pSecureSettingsManager
0x18001fa8a  mov     rcx, [rax]
0x18001fa8d  mov     rax, [rcx]
0x18001fa90  mov     rax, [rax+18h]
0x18001fa94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fa99  mov     [rbx], eax
0x18001fa9b  call    cs:__imp_RpcRevertToSelf
0x18001faa1  test    eax, eax
0x18001faa3  jnz     short loc_18001FAEA
0x18001faa5  xor     eax, eax
0x18001faa7  add     rsp, 20h
0x18001faab  pop     rbx
0x18001faac  retn
0x18001faad  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fab4  lea     rdx, WPP_GLOBAL_Control
0x18001fabb  cmp     rcx, rdx
0x18001fabe  jz      short loc_18001FADE
0x18001fac0  test    byte ptr [rcx+1Ch], 1
0x18001fac4  jz      short loc_18001FADE
0x18001fac6  mov     rcx, [rcx+10h]
0x18001faca  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001fad1  mov     edx, 1Bh
0x18001fad6  mov     r9d, eax
0x18001fad9  call    WPP_SF_d
0x18001fade  mov     ecx, 5; exception
0x18001fae3  call    cs:__imp_RpcRaiseException
0x18001fae9  int     3; Trap to Debugger
0x18001faea  mov     rcx, cs:WPP_GLOBAL_Control
0x18001faf1  lea     rdx, WPP_GLOBAL_Control
0x18001faf8  cmp     rcx, rdx
0x18001fafb  jz      short loc_18001FAA5
0x18001fafd  test    byte ptr [rcx+1Ch], 1
0x18001fb01  jz      short loc_18001FAA5
0x18001fb03  mov     rcx, [rcx+10h]
0x18001fb07  lea     r8, WPP_58c7d8ca840131a6c20521327163655c_Traceguids
0x18001fb0e  mov     edx, 1Ch
0x18001fb13  mov     r9d, eax
0x18001fb16  call    WPP_SF_d
0x18001fb1b  jmp     short loc_18001FAA5
```
