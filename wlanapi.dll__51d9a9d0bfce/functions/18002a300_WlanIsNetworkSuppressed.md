# WlanIsNetworkSuppressed

- ea: `0x18002a300`
- end: `0x18002a489`
- name: `WlanIsNetworkSuppressed`
- size: `393`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation`

## callees

- `0x1800063a0`
- `0x180006934`
- `0x18002a300`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a36f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002a36f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002a37f`
- `api-ms-win-core-processthreads-l1-1-0!ProcessIdToSessionId` at `0x18002a37f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a389`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002a389`
- `RPCRT4!NdrClientCall3` at `0x18002a3d5`
- `RPCRT4!NdrClientCall3` at `0x18002a3d5`

## pseudocode

```c
__int64 __fastcall WlanIsNetworkSuppressed(__int64 a1, unsigned int *a2)
{
  union DOT11_OUI_HEADER *v4; // rcx
  DWORD CurrentProcessId; // eax
  DWORD Pointer; // ebx
  CLIENT_CALL_RETURN v7; // rax
  unsigned int v9; // [rsp+70h] [rbp+8h] BYREF
  unsigned int *v10; // [rsp+78h] [rbp+10h]
  DWORD pSessionId; // [rsp+80h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v12; // [rsp+88h] [rbp+20h]

  v10 = a2;
  v9 = 0;
  pSessionId = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 24, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( a1 && a2 )
  {
    CurrentProcessId = GetCurrentProcessId();
    if ( ProcessIdToSessionId(CurrentProcessId, &pSessionId) )
    {
      v12.Simple = 0;
      v7.Pointer = NdrClientCall3(
                     (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                     0x28u,
                     0,
                     &g_strBinding,
                     pSessionId,
                     a1,
                     &v9).Pointer;
      Pointer = (DWORD)v7.Pointer;
      v12.Pointer = v7.Pointer;
    }
    else
    {
      Pointer = GetLastError();
    }
    v4 = WPP_GLOBAL_Control;
  }
  else
  {
    Pointer = 87;
  }
  if ( !Pointer )
  {
    *a2 = v9;
    v4 = WPP_GLOBAL_Control;
  }
  if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)v4 + 105) >= 4u && (*((_BYTE *)v4 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v4 + 12), 25, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, v9);
      v4 = WPP_GLOBAL_Control;
    }
    if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
      && *((_BYTE *)v4 + 105) >= 4u
      && (*((_BYTE *)v4 + 108) & 2) != 0 )
    {
      WPP_SF_d(*((_QWORD *)v4 + 12), 26, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids, Pointer);
    }
  }
  return Pointer;
}

```

## disassembly

```asm
0x18002a300  mov     rax, rsp
0x18002a303  mov     [rax+10h], rdx
0x18002a307  push    rbx
0x18002a308  push    rsi
0x18002a309  push    rdi
0x18002a30a  sub     rsp, 50h
0x18002a30e  mov     rdi, rdx
0x18002a311  mov     rbx, rcx
0x18002a314  mov     dword ptr [rax+8], 0
0x18002a31b  mov     dword ptr [rax+18h], 0
0x18002a322  lea     rsi, WPP_GLOBAL_Control
0x18002a329  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a330  cmp     rcx, rsi
0x18002a333  jz      short loc_18002A35D
0x18002a335  cmp     byte ptr [rcx+69h], 4
0x18002a339  jb      short loc_18002A35D
0x18002a33b  test    byte ptr [rcx+6Ch], 2
0x18002a33f  jz      short loc_18002A35D
0x18002a341  mov     edx, 18h
0x18002a346  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a34d  mov     rcx, [rcx+60h]
0x18002a351  call    WPP_SF_
0x18002a356  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a35d  test    rbx, rbx
0x18002a360  jz      loc_18002A40E
0x18002a366  test    rdi, rdi
0x18002a369  jz      loc_18002A40E
0x18002a36f  call    cs:__imp_GetCurrentProcessId
0x18002a375  mov     ecx, eax; dwProcessId
0x18002a377  lea     rdx, [rsp+68h+pSessionId]; pSessionId
0x18002a37f  call    cs:__imp_ProcessIdToSessionId
0x18002a385  test    eax, eax
0x18002a387  jnz     short loc_18002A39A
0x18002a389  call    cs:__imp_GetLastError
0x18002a38f  mov     ebx, eax
0x18002a391  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a398  jmp     short loc_18002A413
0x18002a39a  mov     eax, [rsp+68h+pSessionId]
0x18002a3a1  mov     [rsp+68h+arg_18], 0
0x18002a3ad  lea     rcx, [rsp+68h+arg_0]
0x18002a3b2  mov     [rsp+68h+var_38], rcx
0x18002a3b7  mov     [rsp+68h+var_40], rbx
0x18002a3bc  mov     [rsp+68h+var_48], eax
0x18002a3c0  lea     r9, ?g_strBinding@@3PAGA; ushort near * g_strBinding
0x18002a3c7  xor     r8d, r8d; pReturnValue
0x18002a3ca  lea     edx, [r8+28h]; nProcNum
0x18002a3ce  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x18002a3d5  call    cs:__imp_NdrClientCall3
0x18002a3db  mov     rbx, rax
0x18002a3de  mov     [rsp+68h+arg_18], rax
0x18002a3e6  mov     [rsp+68h+var_28], eax
0x18002a3ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a3f1  jmp     short loc_18002A413
0x18002a3f3  mov     ebx, eax
0x18002a3f5  mov     [rsp+68h+var_28], eax
0x18002a3f9  lea     rsi, WPP_GLOBAL_Control
0x18002a400  mov     rdi, [rsp+68h+arg_8]
0x18002a405  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a40c  jmp     short loc_18002A413
0x18002a40e  mov     ebx, 57h ; 'W'
0x18002a413  test    ebx, ebx
0x18002a415  jnz     short loc_18002A424
0x18002a417  mov     eax, [rsp+68h+arg_0]
0x18002a41b  mov     [rdi], eax
0x18002a41d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a424  cmp     rcx, rsi
0x18002a427  jz      short loc_18002A47F
0x18002a429  cmp     byte ptr [rcx+69h], 4
0x18002a42d  jb      short loc_18002A456
0x18002a42f  test    byte ptr [rcx+6Ch], 2
0x18002a433  jz      short loc_18002A456
0x18002a435  mov     edx, 19h
0x18002a43a  mov     r9d, [rsp+68h+arg_0]
0x18002a43f  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a446  mov     rcx, [rcx+60h]
0x18002a44a  call    WPP_SF_d
0x18002a44f  mov     rcx, cs:WPP_GLOBAL_Control
0x18002a456  cmp     rcx, rsi
0x18002a459  jz      short loc_18002A47F
0x18002a45b  cmp     byte ptr [rcx+69h], 4
0x18002a45f  jb      short loc_18002A47F
0x18002a461  test    byte ptr [rcx+6Ch], 2
0x18002a465  jz      short loc_18002A47F
0x18002a467  mov     edx, 1Ah
0x18002a46c  mov     r9d, ebx
0x18002a46f  lea     r8, WPP_55d48d1570f93cb68d377f2b982ff7a4_Traceguids
0x18002a476  mov     rcx, [rcx+60h]
0x18002a47a  call    WPP_SF_d
0x18002a47f  mov     eax, ebx
0x18002a481  add     rsp, 50h
0x18002a485  pop     rdi
0x18002a486  pop     rsi
0x18002a487  pop     rbx
0x18002a488  retn
0x180060bba  push    rbp
0x180060bbc  sub     rsp, 40h
0x180060bc0  mov     rbp, rdx
0x180060bc3  mov     rcx, [rcx]
0x180060bc6  mov     ecx, [rcx]; ExceptionCode
0x180060bc8  call    cs:__imp_RpcExceptionFilter
0x180060bce  nop
0x180060bcf  add     rsp, 40h
0x180060bd3  pop     rbp
0x180060bd4  retn
```
