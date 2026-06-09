# s_GetDeviceLockoutSize

- ea: `0x1800029d0`
- end: `0x180002b29`
- name: `s_GetDeviceLockoutSize`
- size: `345`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x1800026e0`
- `0x180002708`
- `0x1800029d0`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002b11`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180002b11`
- `RPCRT4!RpcImpersonateClient` at `0x1800029e4`
- `RPCRT4!RpcImpersonateClient` at `0x1800029e4`

## pseudocode

```c
__int64 __fastcall s_GetDeviceLockoutSize(__int64 a1, _DWORD *a2)
{
  RPC_STATUS v3; // eax
  unsigned int v4; // ebx
  int v5; // eax
  _QWORD *v6; // rcx
  __int64 v7; // rdx
  __int64 v8; // r8

  v3 = RpcImpersonateClient(0);
  v4 = v3;
  if ( !v3 )
  {
    v5 = CheckCallerAdminAccess();
    v4 = v5;
    if ( v5 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v5 = (*((__int64 (__fastcall **)(_QWORD, _DWORD *))&xmmword_180008728 + 1))(0, a2);
      v4 = v5;
      if ( v5 >= 0 )
      {
        if ( a2 && *a2 > 0x400u )
        {
          v4 = -2013200375;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, v8, 2281766921LL, *a2);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 42, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        }
        goto LABEL_24;
      }
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        RevertToSelf();
        return v4;
      }
      v7 = 40;
    }
    else
    {
      v6 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v7 = 38;
    }
    WPP_SF_D(v6[2], v7, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, (unsigned int)v5);
    goto LABEL_24;
  }
  if ( v3 >= 0 )
    return (unsigned __int16)v3 | 0x80010000;
  return v4;
}

```

## disassembly

```asm
0x1800029d0  mov     [rsp+arg_0], rbx
0x1800029d5  mov     [rsp+arg_8], rsi
0x1800029da  push    rdi
0x1800029db  sub     rsp, 30h
0x1800029df  xor     ecx, ecx; BindingHandle
0x1800029e1  mov     rsi, rdx
0x1800029e4  call    cs:__imp_RpcImpersonateClient
0x1800029ea  mov     ebx, eax
0x1800029ec  test    eax, eax
0x1800029ee  jz      short loc_180002A04
0x1800029f0  js      loc_180002B17
0x1800029f6  movzx   ebx, ax
0x1800029f9  or      ebx, 80010000h
0x1800029ff  jmp     loc_180002B17
0x180002a04  call    ?CheckCallerAdminAccess@@YAJXZ; CheckCallerAdminAccess(void)
0x180002a09  mov     ebx, eax
0x180002a0b  test    eax, eax
0x180002a0d  jns     short loc_180002A4D
0x180002a0f  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a16  lea     rdi, WPP_GLOBAL_Control
0x180002a1d  cmp     rcx, rdi
0x180002a20  jz      loc_180002B11
0x180002a26  test    byte ptr [rcx+1Ch], 1
0x180002a2a  jz      loc_180002B11
0x180002a30  mov     edx, 26h ; '&'
0x180002a35  mov     rcx, [rcx+10h]
0x180002a39  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002a40  mov     r9d, eax
0x180002a43  call    WPP_SF_D
0x180002a48  jmp     loc_180002B11
0x180002a4d  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a54  lea     rdi, WPP_GLOBAL_Control
0x180002a5b  cmp     rcx, rdi
0x180002a5e  jz      short loc_180002A7B
0x180002a60  test    byte ptr [rcx+1Ch], 20h
0x180002a64  jz      short loc_180002A7B
0x180002a66  mov     rcx, [rcx+10h]
0x180002a6a  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002a71  mov     edx, 27h ; '''
0x180002a76  call    WPP_SF_
0x180002a7b  mov     rax, qword ptr cs:xmmword_180008728+8
0x180002a82  mov     rdx, rsi
0x180002a85  xor     ecx, ecx
0x180002a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a8c  mov     ebx, eax
0x180002a8e  test    eax, eax
0x180002a90  jns     short loc_180002AAB
0x180002a92  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a99  cmp     rcx, rdi
0x180002a9c  jz      short loc_180002B11
0x180002a9e  test    byte ptr [rcx+1Ch], 1
0x180002aa2  jz      short loc_180002B11
0x180002aa4  mov     edx, 28h ; '('
0x180002aa9  jmp     short loc_180002A35
0x180002aab  test    rsi, rsi
0x180002aae  jz      short loc_180002AEA
0x180002ab0  mov     eax, [rsi]
0x180002ab2  cmp     eax, 400h
0x180002ab7  jbe     short loc_180002AEA
0x180002ab9  mov     ebx, 88010009h
0x180002abe  mov     rcx, cs:WPP_GLOBAL_Control
0x180002ac5  cmp     rcx, rdi
0x180002ac8  jz      short loc_180002B11
0x180002aca  test    byte ptr [rcx+1Ch], 1
0x180002ace  jz      short loc_180002B11
0x180002ad0  mov     rcx, [rcx+10h]
0x180002ad4  mov     edx, 29h ; ')'
0x180002ad9  mov     r9d, 88010009h
0x180002adf  mov     [rsp+38h+var_18], eax
0x180002ae3  call    WPP_SF_DD
0x180002ae8  jmp     short loc_180002B11
0x180002aea  mov     rcx, cs:WPP_GLOBAL_Control
0x180002af1  cmp     rcx, rdi
0x180002af4  jz      short loc_180002B11
0x180002af6  test    byte ptr [rcx+1Ch], 20h
0x180002afa  jz      short loc_180002B11
0x180002afc  mov     rcx, [rcx+10h]
0x180002b00  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x180002b07  mov     edx, 2Ah ; '*'
0x180002b0c  call    WPP_SF_
0x180002b11  call    cs:__imp_RevertToSelf
0x180002b17  mov     rsi, [rsp+38h+arg_8]
0x180002b1c  mov     eax, ebx
0x180002b1e  mov     rbx, [rsp+38h+arg_0]
0x180002b23  add     rsp, 30h
0x180002b27  pop     rdi
0x180002b28  retn
```
