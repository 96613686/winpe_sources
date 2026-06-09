# s_GetDeviceLockoutData

- ea: `0x180002870`
- end: `0x1800029c0`
- name: `s_GetDeviceLockoutData`
- size: `336`
- prototype: `__int64 __fastcall(__int64, __int64, _DWORD *)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180001e04`
- `0x180001f58`
- `0x1800026e0`
- `0x180002708`
- `0x180002870`
- `0x180004010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800029af`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800029af`
- `RPCRT4!RpcImpersonateClient` at `0x180002881`
- `RPCRT4!RpcImpersonateClient` at `0x180002881`

## pseudocode

```c
__int64 __fastcall s_GetDeviceLockoutData(__int64 a1, __int64 a2, _DWORD *a3)
{
  RPC_STATUS v5; // eax
  unsigned int v6; // ebx
  int v7; // eax
  _QWORD *v8; // rcx
  __int64 v9; // rdx
  __int64 v10; // r8

  v5 = RpcImpersonateClient(0);
  v6 = v5;
  if ( !v5 )
  {
    v7 = CheckCallerAdminAccess();
    v6 = v7;
    if ( v7 >= 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
      v7 = (*((__int64 (__fastcall **)(__int64, _DWORD *))&xmmword_180008728 + 1))(a2, a3);
      v6 = v7;
      if ( v7 >= 0 )
      {
        if ( a3 && *a3 > 0x400u )
        {
          v6 = -2013200375;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_DD(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, v10, 2281766921LL, *a3);
        }
        else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
               && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids);
        }
        goto LABEL_24;
      }
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      {
LABEL_24:
        RevertToSelf();
        return v6;
      }
      v9 = 23;
    }
    else
    {
      v8 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        goto LABEL_24;
      v9 = 21;
    }
    WPP_SF_D(v8[2], v9, &WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids, (unsigned int)v7);
    goto LABEL_24;
  }
  if ( v5 >= 0 )
    return (unsigned __int16)v5 | 0x80010000;
  return v6;
}

```

## disassembly

```asm
0x180002870  push    rbx
0x180002872  push    rbp
0x180002873  push    rsi
0x180002874  push    rdi
0x180002875  sub     rsp, 38h
0x180002879  xor     ecx, ecx; BindingHandle
0x18000287b  mov     rsi, r8
0x18000287e  mov     rbp, rdx
0x180002881  call    cs:__imp_RpcImpersonateClient
0x180002887  mov     ebx, eax
0x180002889  test    eax, eax
0x18000288b  jz      short loc_1800028A1
0x18000288d  js      loc_1800029B5
0x180002893  movzx   ebx, ax
0x180002896  or      ebx, 80010000h
0x18000289c  jmp     loc_1800029B5
0x1800028a1  call    ?CheckCallerAdminAccess@@YAJXZ; CheckCallerAdminAccess(void)
0x1800028a6  mov     ebx, eax
0x1800028a8  test    eax, eax
0x1800028aa  jns     short loc_1800028EA
0x1800028ac  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028b3  lea     rdi, WPP_GLOBAL_Control
0x1800028ba  cmp     rcx, rdi
0x1800028bd  jz      loc_1800029AF
0x1800028c3  test    byte ptr [rcx+1Ch], 1
0x1800028c7  jz      loc_1800029AF
0x1800028cd  mov     edx, 15h
0x1800028d2  mov     rcx, [rcx+10h]
0x1800028d6  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x1800028dd  mov     r9d, eax
0x1800028e0  call    WPP_SF_D
0x1800028e5  jmp     loc_1800029AF
0x1800028ea  mov     rcx, cs:WPP_GLOBAL_Control
0x1800028f1  lea     rdi, WPP_GLOBAL_Control
0x1800028f8  cmp     rcx, rdi
0x1800028fb  jz      short loc_180002918
0x1800028fd  test    byte ptr [rcx+1Ch], 20h
0x180002901  jz      short loc_180002918
0x180002903  mov     rcx, [rcx+10h]
0x180002907  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x18000290e  mov     edx, 16h
0x180002913  call    WPP_SF_
0x180002918  mov     rax, qword ptr cs:xmmword_180008728+8
0x18000291f  mov     rdx, rsi
0x180002922  mov     rcx, rbp
0x180002925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000292a  mov     ebx, eax
0x18000292c  test    eax, eax
0x18000292e  jns     short loc_180002949
0x180002930  mov     rcx, cs:WPP_GLOBAL_Control
0x180002937  cmp     rcx, rdi
0x18000293a  jz      short loc_1800029AF
0x18000293c  test    byte ptr [rcx+1Ch], 1
0x180002940  jz      short loc_1800029AF
0x180002942  mov     edx, 17h
0x180002947  jmp     short loc_1800028D2
0x180002949  test    rsi, rsi
0x18000294c  jz      short loc_180002988
0x18000294e  mov     eax, [rsi]
0x180002950  cmp     eax, 400h
0x180002955  jbe     short loc_180002988
0x180002957  mov     ebx, 88010009h
0x18000295c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002963  cmp     rcx, rdi
0x180002966  jz      short loc_1800029AF
0x180002968  test    byte ptr [rcx+1Ch], 1
0x18000296c  jz      short loc_1800029AF
0x18000296e  mov     rcx, [rcx+10h]
0x180002972  mov     edx, 18h
0x180002977  mov     r9d, 88010009h
0x18000297d  mov     [rsp+58h+var_38], eax
0x180002981  call    WPP_SF_DD
0x180002986  jmp     short loc_1800029AF
0x180002988  mov     rcx, cs:WPP_GLOBAL_Control
0x18000298f  cmp     rcx, rdi
0x180002992  jz      short loc_1800029AF
0x180002994  test    byte ptr [rcx+1Ch], 20h
0x180002998  jz      short loc_1800029AF
0x18000299a  mov     rcx, [rcx+10h]
0x18000299e  lea     r8, WPP_b7093816b9563fa5bd5004f376244ec4_Traceguids
0x1800029a5  mov     edx, 19h
0x1800029aa  call    WPP_SF_
0x1800029af  call    cs:__imp_RevertToSelf
0x1800029b5  mov     eax, ebx
0x1800029b7  add     rsp, 38h
0x1800029bb  pop     rdi
0x1800029bc  pop     rsi
0x1800029bd  pop     rbp
0x1800029be  pop     rbx
0x1800029bf  retn
```
