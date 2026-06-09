# WlanCloseHandle

- ea: `0x1800063e0`
- end: `0x180006616`
- name: `WlanCloseHandle`
- size: `566`
- prototype: `DWORD __stdcall(HANDLE hClientHandle, PVOID pReserved)`
- caller_count: `3`
- callee_count: `4`
- tags: ``

## callers

- `0x1800056e0`
- `0x18002eac0`
- `0x18002ee10`

## callees

- `0x1800063a0`
- `0x1800063e0`
- `0x180006620`
- `0x180006934`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000657f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x18000657f`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800064b8`
- `RPCRT4!RpcSsDestroyClientContext` at `0x1800064b8`
- `RPCRT4!NdrClientCall3` at `0x180006499`
- `RPCRT4!NdrClientCall3` at `0x180006499`
- `RPCRT4!RpcExceptionFilter` at `0x18006042e`
- `RPCRT4!RpcExceptionFilter` at `0x18006042e`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800064ee`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800064ee`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180006454`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x180006454`

## pseudocode

```c
DWORD __stdcall WlanCloseHandle(HANDLE hClientHandle, PVOID pReserved)
{
  union DOT11_OUI_HEADER *v4; // rcx
  DWORD v5; // eax
  DWORD Pointer; // ebx
  struct _TP_CLEANUP_GROUP *v7; // rcx
  CLIENT_CALL_RETURN v8; // rax
  int v10; // eax
  int v11; // eax
  void **ContextHandle; // [rsp+70h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+78h] [rbp+20h]

  ContextHandle = 0;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 53, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !hClientHandle || pReserved )
  {
    Pointer = 87;
    if ( v4 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return Pointer;
    if ( !*((_BYTE *)v4 + 105) || (*((_BYTE *)v4 + 108) & 2) == 0 )
      goto LABEL_12;
    WPP_SF_(*((_QWORD *)v4 + 12), 54, WPP_797f1b088bb039a5f91226960c081484_Traceguids);
    goto LABEL_11;
  }
  v5 = HtReferenceHandleWithTag(g_hHandleTable, hClientHandle, 1129074260, 1448036676, 0, &ContextHandle);
  Pointer = v5;
  if ( !v5 )
  {
    ClientUnregisterNotification((struct _WLAN_CLIENT_CONTEXT *)ContextHandle, 0);
    v7 = (struct _TP_CLEANUP_GROUP *)ContextHandle[37];
    if ( v7 )
      CloseThreadpoolCleanupGroupMembers(v7, 0, 0);
    v13.Simple = 0;
    v8.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo, 1u, 0).Pointer;
    Pointer = (DWORD)v8.Pointer;
    v13.Pointer = v8.Pointer;
    if ( LODWORD(v8.Pointer) == 1717
      || (v10 = LODWORD(v8.Pointer) - 1702, Pointer == 1702)
      || (v11 = v10 - 24) == 0
      || v11 == 27 )
    {
      Pointer = 1062;
    }
    HtDereferenceHandleWithTag(g_hHandleTable, hClientHandle, 0, 1);
    goto LABEL_11;
  }
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return Pointer;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 55, WPP_797f1b088bb039a5f91226960c081484_Traceguids, v5);
LABEL_11:
    v4 = WPP_GLOBAL_Control;
  }
LABEL_12:
  if ( v4 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v4 + 105) >= 4u
    && (*((_BYTE *)v4 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v4 + 12), 56, WPP_797f1b088bb039a5f91226960c081484_Traceguids, Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x1800063e0  mov     [rsp+arg_8], rbx
0x1800063e5  mov     [rsp+arg_0], rcx
0x1800063ea  push    rsi
0x1800063eb  push    rdi
0x1800063ec  push    r14
0x1800063ee  sub     rsp, 40h
0x1800063f2  mov     rbx, rdx
0x1800063f5  mov     rdi, rcx
0x1800063f8  xor     r14d, r14d
0x1800063fb  mov     [rsp+58h+ContextHandle], r14
0x180006400  lea     rsi, WPP_GLOBAL_Control
0x180006407  mov     rcx, cs:WPP_GLOBAL_Control
0x18000640e  cmp     rcx, rsi
0x180006411  jz      short loc_18000641D
0x180006413  cmp     byte ptr [rcx+69h], 4
0x180006417  jnb     loc_18000651A
0x18000641d  test    rdi, rdi
0x180006420  jz      loc_1800065B3
0x180006426  test    rbx, rbx
0x180006429  jnz     loc_1800065B3
0x18000642f  lea     rax, [rsp+58h+ContextHandle]
0x180006434  mov     [rsp+58h+var_30], rax
0x180006439  mov     [rsp+58h+var_38], r14d
0x18000643e  mov     r9d, 564F4944h
0x180006444  mov     r8d, 434C4E54h
0x18000644a  mov     rdx, rdi
0x18000644d  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180006454  call    cs:__imp_HtReferenceHandleWithTag
0x18000645a  mov     ebx, eax
0x18000645c  test    eax, eax
0x18000645e  jnz     loc_180006545
0x180006464  xor     edx, edx; unsigned int *
0x180006466  mov     rcx, [rsp+58h+ContextHandle]; struct _WLAN_CLIENT_CONTEXT *
0x18000646b  call    ?ClientUnregisterNotification@@YAKPEAU_WLAN_CLIENT_CONTEXT@@PEAK@Z; ClientUnregisterNotification(_WLAN_CLIENT_CONTEXT *,ulong *)
0x180006470  mov     r9, [rsp+58h+ContextHandle]
0x180006475  mov     rcx, [r9+128h]; ptpcg
0x18000647c  test    rcx, rcx
0x18000647f  jnz     loc_18000657A
0x180006485  mov     [rsp+58h+arg_18], r14
0x18000648a  xor     r8d, r8d; pReturnValue
0x18000648d  mov     edx, 1; nProcNum
0x180006492  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180006499  call    cs:__imp_NdrClientCall3
0x18000649f  mov     rbx, rax
0x1800064a2  mov     [rsp+58h+arg_18], rax
0x1800064a7  mov     [rsp+58h+var_28], eax
0x1800064ab  jmp     short loc_1800064CA
0x1800064ad  mov     ebx, eax
0x1800064af  mov     [rsp+58h+var_28], eax
0x1800064b3  mov     rcx, [rsp+58h+ContextHandle]; ContextHandle
0x1800064b8  call    cs:__imp_RpcSsDestroyClientContext
0x1800064be  lea     rsi, WPP_GLOBAL_Control
0x1800064c5  mov     rdi, [rsp+58h+arg_0]
0x1800064ca  cmp     ebx, 6B5h
0x1800064d0  jnz     loc_18000658F
0x1800064d6  mov     ebx, 426h
0x1800064db  mov     r9d, 1
0x1800064e1  xor     r8d, r8d
0x1800064e4  mov     rdx, rdi
0x1800064e7  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800064ee  call    cs:__imp_HtDereferenceHandleWithTag
0x1800064f4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800064fb  cmp     rcx, rsi
0x1800064fe  jz      short loc_18000650A
0x180006500  cmp     byte ptr [rcx+69h], 4
0x180006504  jnb     loc_1800065EF
0x18000650a  mov     eax, ebx
0x18000650c  mov     rbx, [rsp+58h+arg_8]
0x180006511  add     rsp, 40h
0x180006515  pop     r14
0x180006517  pop     rdi
0x180006518  pop     rsi
0x180006519  retn
0x18000651a  test    byte ptr [rcx+6Ch], 2
0x18000651e  jz      loc_18000641D
0x180006524  mov     edx, 35h ; '5'
0x180006529  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180006530  mov     rcx, [rcx+60h]
0x180006534  call    WPP_SF_
0x180006539  mov     rcx, cs:WPP_GLOBAL_Control
0x180006540  jmp     loc_18000641D
0x180006545  mov     rcx, cs:WPP_GLOBAL_Control
0x18000654c  cmp     rcx, rsi
0x18000654f  jz      short loc_18000650A
0x180006551  cmp     byte ptr [rcx+69h], 1
0x180006555  jb      short loc_1800064FB
0x180006557  test    byte ptr [rcx+6Ch], 2
0x18000655b  jz      short loc_1800064FB
0x18000655d  mov     edx, 37h ; '7'
0x180006562  mov     r9d, eax
0x180006565  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x18000656c  mov     rcx, [rcx+60h]
0x180006570  call    WPP_SF_d
0x180006575  jmp     loc_1800064F4
0x18000657a  xor     r8d, r8d; pvCleanupContext
0x18000657d  xor     edx, edx; fCancelPendingCallbacks
0x18000657f  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x180006585  mov     r9, [rsp+58h+ContextHandle]
0x18000658a  jmp     loc_180006485
0x18000658f  mov     eax, ebx
0x180006591  sub     eax, 6A6h
0x180006596  jz      loc_1800064D6
0x18000659c  sub     eax, 18h
0x18000659f  jz      loc_1800064D6
0x1800065a5  cmp     eax, 1Bh
0x1800065a8  jnz     loc_1800064DB
0x1800065ae  jmp     loc_1800064D6
0x1800065b3  mov     ebx, 57h ; 'W'
0x1800065b8  cmp     rcx, rsi
0x1800065bb  jz      loc_18000650A
0x1800065c1  cmp     byte ptr [rcx+69h], 1
0x1800065c5  jb      loc_1800064FB
0x1800065cb  test    byte ptr [rcx+6Ch], 2
0x1800065cf  jz      loc_1800064FB
0x1800065d5  mov     edx, 36h ; '6'
0x1800065da  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x1800065e1  mov     rcx, [rcx+60h]
0x1800065e5  call    WPP_SF_
0x1800065ea  jmp     loc_1800064F4
0x1800065ef  test    byte ptr [rcx+6Ch], 2
0x1800065f3  jz      loc_18000650A
0x1800065f9  mov     edx, 38h ; '8'
0x1800065fe  mov     r9d, ebx
0x180006601  lea     r8, WPP_797f1b088bb039a5f91226960c081484_Traceguids
0x180006608  mov     rcx, [rcx+60h]
0x18000660c  call    WPP_SF_d
0x180006611  jmp     loc_18000650A
0x180060420  push    rbp
0x180060422  sub     rsp, 30h
0x180060426  mov     rbp, rdx
0x180060429  mov     rcx, [rcx]
0x18006042c  mov     ecx, [rcx]; ExceptionCode
0x18006042e  call    cs:__imp_RpcExceptionFilter
0x180060434  nop
0x180060435  add     rsp, 30h
0x180060439  pop     rbp
0x18006043a  retn
```
