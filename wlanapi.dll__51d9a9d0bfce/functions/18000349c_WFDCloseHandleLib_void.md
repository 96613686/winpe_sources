# WFDCloseHandleLib(void *)

- ea: `0x18000349c`
- end: `0x180003677`
- name: `?WFDCloseHandleLib@@YAKPEAX@Z`
- size: `475`
- prototype: `unsigned int __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x180003490`
- `0x180038c50`

## callees

- `0x18000349c`
- `0x18000368c`
- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x180017ccc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003567`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolCleanupGroupMembers` at `0x180003567`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000358b`
- `RPCRT4!RpcSsDestroyClientContext` at `0x18000358b`
- `RPCRT4!RpcExceptionFilter` at `0x1800602de`
- `RPCRT4!RpcExceptionFilter` at `0x1800602de`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800035b9`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x1800035b9`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000353a`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x18000353a`

## pseudocode

```c
__int64 __fastcall WFDCloseHandleLib(void *a1)
{
  union DOT11_OUI_HEADER *v2; // rcx
  unsigned int v3; // ebx
  unsigned int v4; // eax
  unsigned int v6; // [rsp+30h] [rbp-18h]
  void **ContextHandle; // [rsp+58h] [rbp+10h] BYREF

  ContextHandle = 0;
  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 73, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v2 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    v4 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1466525252, 1448036676, 0, &ContextHandle);
    v3 = v4;
    if ( v4 )
    {
      v2 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
        return v3;
      if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
        goto LABEL_10;
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 75, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v4);
    }
    else
    {
      wfdClientUnregisterNotification((struct _WFD_CLIENT_CONTEXT *)ContextHandle, 0);
      CloseThreadpoolCleanupGroupMembers((PTP_CLEANUP_GROUP)ContextHandle[38], 0, 0);
      v6 = RpcWlanCloseHandle(ContextHandle);
      v3 = ServiceStatus(v6);
      HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
    }
    goto LABEL_9;
  }
  v3 = 87;
  if ( v2 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v3;
  if ( *((_BYTE *)v2 + 105) && (*((_DWORD *)v2 + 27) & 0x1000) != 0 )
  {
    WPP_SF_(*((_QWORD *)v2 + 12), 74, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
LABEL_9:
    v2 = WPP_GLOBAL_Control;
  }
LABEL_10:
  if ( v2 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v2 + 105) >= 4u
    && (*((_BYTE *)v2 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v2 + 12), 76, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v3);
  }
  return v3;
}

```

## disassembly

```asm
0x18000349c  mov     rax, rsp
0x18000349f  mov     [rax+18h], rbx
0x1800034a3  mov     [rax+20h], rsi
0x1800034a7  mov     [rax+8], rcx
0x1800034ab  push    rdi
0x1800034ac  sub     rsp, 40h
0x1800034b0  mov     rsi, rcx
0x1800034b3  mov     qword ptr [rax+10h], 0
0x1800034bb  lea     rdi, WPP_GLOBAL_Control
0x1800034c2  mov     rcx, cs:WPP_GLOBAL_Control
0x1800034c9  cmp     rcx, rdi
0x1800034cc  jnz     loc_1800035E3
0x1800034d2  test    rsi, rsi
0x1800034d5  jnz     short loc_180003512
0x1800034d7  lea     ebx, [rsi+57h]
0x1800034da  cmp     rcx, rdi
0x1800034dd  jz      loc_1800035D1
0x1800034e3  cmp     byte ptr [rcx+69h], 1
0x1800034e7  jb      loc_1800035C6
0x1800034ed  test    dword ptr [rcx+6Ch], 1000h
0x1800034f4  jz      loc_1800035C6
0x1800034fa  lea     edx, [rsi+4Ah]
0x1800034fd  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003504  mov     rcx, [rcx+60h]
0x180003508  call    WPP_SF_
0x18000350d  jmp     loc_1800035BF
0x180003512  lea     rax, [rsp+48h+ContextHandle]
0x180003517  mov     [rsp+48h+var_20], rax
0x18000351c  mov     [rsp+48h+var_28], 0
0x180003524  mov     r9d, 564F4944h
0x18000352a  mov     r8d, 57696644h
0x180003530  mov     rdx, rsi
0x180003533  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x18000353a  call    cs:__imp_HtReferenceHandleWithTag
0x180003540  mov     ebx, eax
0x180003542  test    eax, eax
0x180003544  jnz     loc_180003618
0x18000354a  xor     edx, edx; unsigned int *
0x18000354c  mov     rcx, [rsp+48h+ContextHandle]; struct _WFD_CLIENT_CONTEXT *
0x180003551  call    ?wfdClientUnregisterNotification@@YAKPEAU_WFD_CLIENT_CONTEXT@@PEAK@Z; wfdClientUnregisterNotification(_WFD_CLIENT_CONTEXT *,ulong *)
0x180003556  xor     r8d, r8d; pvCleanupContext
0x180003559  xor     edx, edx; fCancelPendingCallbacks
0x18000355b  mov     rcx, [rsp+48h+ContextHandle]
0x180003560  mov     rcx, [rcx+130h]; ptpcg
0x180003567  call    cs:__imp_CloseThreadpoolCleanupGroupMembers
0x18000356d  nop
0x18000356e  mov     rcx, [rsp+48h+ContextHandle]
0x180003573  call    RpcWlanCloseHandle
0x180003578  mov     ebx, eax
0x18000357a  mov     [rsp+48h+var_18], eax
0x18000357e  jmp     short loc_18000359D
0x180003580  mov     ebx, eax
0x180003582  mov     [rsp+48h+var_18], eax
0x180003586  mov     rcx, [rsp+48h+ContextHandle]; ContextHandle
0x18000358b  call    cs:__imp_RpcSsDestroyClientContext
0x180003591  lea     rdi, WPP_GLOBAL_Control
0x180003598  mov     rsi, [rsp+48h+arg_0]
0x18000359d  mov     ecx, ebx; unsigned int
0x18000359f  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800035a4  mov     ebx, eax
0x1800035a6  mov     r9d, 1
0x1800035ac  xor     r8d, r8d
0x1800035af  mov     rdx, rsi
0x1800035b2  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800035b9  call    cs:__imp_HtDereferenceHandleWithTag
0x1800035bf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800035c6  cmp     rcx, rdi
0x1800035c9  jz      short loc_1800035D1
0x1800035cb  cmp     byte ptr [rcx+69h], 4
0x1800035cf  jnb     short loc_180003650
0x1800035d1  mov     eax, ebx
0x1800035d3  mov     rbx, [rsp+48h+arg_10]
0x1800035d8  mov     rsi, [rsp+48h+arg_18]
0x1800035dd  add     rsp, 40h
0x1800035e1  pop     rdi
0x1800035e2  retn
0x1800035e3  cmp     byte ptr [rcx+69h], 4
0x1800035e7  jb      loc_1800034D2
0x1800035ed  test    byte ptr [rcx+6Ch], 2
0x1800035f1  jz      loc_1800034D2
0x1800035f7  mov     edx, 49h ; 'I'
0x1800035fc  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003603  mov     rcx, [rcx+60h]
0x180003607  call    WPP_SF_
0x18000360c  mov     rcx, cs:WPP_GLOBAL_Control
0x180003613  jmp     loc_1800034D2
0x180003618  mov     rcx, cs:WPP_GLOBAL_Control
0x18000361f  cmp     rcx, rdi
0x180003622  jz      short loc_1800035D1
0x180003624  cmp     byte ptr [rcx+69h], 1
0x180003628  jb      short loc_1800035C6
0x18000362a  test    dword ptr [rcx+6Ch], 1000h
0x180003631  jz      short loc_1800035C6
0x180003633  mov     edx, 4Bh ; 'K'
0x180003638  mov     r9d, eax
0x18000363b  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003642  mov     rcx, [rcx+60h]
0x180003646  call    WPP_SF_d
0x18000364b  jmp     loc_1800035BF
0x180003650  test    byte ptr [rcx+6Ch], 2
0x180003654  jz      loc_1800035D1
0x18000365a  mov     edx, 4Ch ; 'L'
0x18000365f  mov     r9d, ebx
0x180003662  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180003669  mov     rcx, [rcx+60h]
0x18000366d  call    WPP_SF_d
0x180003672  jmp     loc_1800035D1
0x1800602d0  push    rbp
0x1800602d2  sub     rsp, 30h
0x1800602d6  mov     rbp, rdx
0x1800602d9  mov     rcx, [rcx]
0x1800602dc  mov     ecx, [rcx]; ExceptionCode
0x1800602de  call    cs:__imp_RpcExceptionFilter
0x1800602e4  nop
0x1800602e5  add     rsp, 30h
0x1800602e9  pop     rbp
0x1800602ea  retn
```
