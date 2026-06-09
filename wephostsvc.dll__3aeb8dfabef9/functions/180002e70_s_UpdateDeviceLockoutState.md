# s_UpdateDeviceLockoutState

- ea: `0x180002e70`
- end: `0x180002f80`
- name: `s_UpdateDeviceLockoutState`
- size: `272`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x1800026e0`
- `0x180002e70`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002f6f`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002f6f`
- `RPCRT4!RpcImpersonateClient` at `0x180002e81`
- `RPCRT4!RpcImpersonateClient` at `0x180002e81`

## pseudocode

```c
__int64 __fastcall s_UpdateDeviceLockoutState(__int64 a1, __int64 a2, unsigned int a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx

  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( !v5 )
  {
    v7 = CheckCallerAdminAccess();
    v6 = v7;
    if ( v7 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 31, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v7 = ((__int64 (__fastcall *)(__int64, _QWORD))qword_180008738)(a2, a3);
      v6 = v7;
      if ( v7 >= 0 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 33, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        goto LABEL_19;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_19:
        RevertToSelf();
        return v6;
      }
      v9 = 32;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_19;
      v9 = 30;
    }
    WPP_SF_D(v8[2], v9, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, (unsigned int)v7);
    goto LABEL_19;
  }
  if ( v5 >= 0 )
    return (unsigned __int16)v5 | 0x80010000;
  return v6;
}

```

## disassembly

```asm
0x180002e70  push    rbx
0x180002e72  push    rbp
0x180002e73  push    rsi
0x180002e74  push    rdi
0x180002e75  sub     rsp, 28h
0x180002e79  xor     ecx, ecx; BindingHandle
0x180002e7b  mov     esi, r8d
0x180002e7e  mov     rbp, rdx
0x180002e81  call    cs:__imp_RpcImpersonateClient
0x180002e87  mov     ebx, eax
0x180002e89  test    eax, eax
0x180002e8b  jz      short loc_180002EA1
0x180002e8d  js      loc_180002F75
0x180002e93  movzx   ebx, ax
0x180002e96  or      ebx, 80010000h
0x180002e9c  jmp     loc_180002F75
0x180002ea1  call    ?CheckCallerAdminAccess@@YAJXZ; CheckCallerAdminAccess(void)
0x180002ea6  mov     ebx, eax
0x180002ea8  test    eax, eax
0x180002eaa  jns     short loc_180002EEA
0x180002eac  mov     rcx, cs:WPP_GLOBAL_Control
0x180002eb3  lea     rdi, WPP_GLOBAL_Control
0x180002eba  cmp     rcx, rdi
0x180002ebd  jz      loc_180002F6F
0x180002ec3  test    byte ptr [rcx+1Ch], 1
0x180002ec7  jz      loc_180002F6F
0x180002ecd  mov     edx, 1Eh
0x180002ed2  mov     rcx, [rcx+10h]
0x180002ed6  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002edd  mov     r9d, eax
0x180002ee0  call    WPP_SF_D
0x180002ee5  jmp     loc_180002F6F
0x180002eea  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ef1  lea     rdi, WPP_GLOBAL_Control
0x180002ef8  cmp     rcx, rdi
0x180002efb  jz      short loc_180002F18
0x180002efd  test    byte ptr [rcx+1Ch], 20h
0x180002f01  jz      short loc_180002F18
0x180002f03  mov     rcx, [rcx+10h]
0x180002f07  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002f0e  mov     edx, 1Fh
0x180002f13  call    WPP_SF_
0x180002f18  mov     rax, cs:qword_180008738
0x180002f1f  mov     edx, esi
0x180002f21  mov     rcx, rbp
0x180002f24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f29  mov     ebx, eax
0x180002f2b  test    eax, eax
0x180002f2d  jns     short loc_180002F48
0x180002f2f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f36  cmp     rcx, rdi
0x180002f39  jz      short loc_180002F6F
0x180002f3b  test    byte ptr [rcx+1Ch], 1
0x180002f3f  jz      short loc_180002F6F
0x180002f41  mov     edx, 20h ; ' '
0x180002f46  jmp     short loc_180002ED2
0x180002f48  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f4f  cmp     rcx, rdi
0x180002f52  jz      short loc_180002F6F
0x180002f54  test    byte ptr [rcx+1Ch], 20h
0x180002f58  jz      short loc_180002F6F
0x180002f5a  mov     rcx, [rcx+10h]
0x180002f5e  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002f65  mov     edx, 21h ; '!'
0x180002f6a  call    WPP_SF_
0x180002f6f  call    cs:__imp_RevertToSelf
0x180002f75  mov     eax, ebx
0x180002f77  add     rsp, 28h
0x180002f7b  pop     rdi
0x180002f7c  pop     rsi
0x180002f7d  pop     rbp
0x180002f7e  pop     rbx
0x180002f7f  retn
```
