# WFDAcceptConnectRequestAndOpenSessionLib(void *,void *,ushort *,ulong *,_GUID *,void * *)

- ea: `0x180050370`
- end: `0x180050707`
- name: `?WFDAcceptConnectRequestAndOpenSessionLib@@YAKPEAX0PEAGPEAKPEAU_GUID@@PEAPEAX@Z`
- size: `919`
- prototype: `unsigned int __usercall@<eax>(void *@<rcx>, void *@<rdx>, unsigned __int16 *@<r8>, unsigned int *@<r9>, struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task`

## callers

- `0x18002c2e0`

## callees

- `0x1800038d0`
- `0x1800063a0`
- `0x180006934`
- `0x1800132cc`
- `0x180019a20`
- `0x1800281e8`
- `0x180043d68`
- `0x18004ffb8`
- `0x180050370`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005055e`
- `api-ms-win-eventing-provider-l1-1-0!EventActivityIdControl` at `0x18005055e`
- `RPCRT4!NdrClientCall3` at `0x1800505bb`
- `RPCRT4!NdrClientCall3` at `0x1800505bb`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180050679`
- `MobileNetworking!HtDereferenceHandleWithTag` at `0x180050679`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800504af`
- `MobileNetworking!HtReferenceHandleWithTag` at `0x1800504af`

## pseudocode

```c
__int64 __fastcall WFDAcceptConnectRequestAndOpenSessionLib(
        void *a1,
        void *a2,
        unsigned __int16 *a3,
        unsigned int *a4,
        struct _GUID *a5,
        void **a6)
{
  struct _GUID *v9; // rax
  union DOT11_OUI_HEADER *v10; // r10
  unsigned int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v14; // rdi
  __int64 v15; // rdx
  struct _WFD_API_ASYNC_CONTEXT *v17; // [rsp+58h] [rbp-90h] BYREF
  __int64 *v18; // [rsp+60h] [rbp-88h] BYREF
  struct _GUID *v19; // [rsp+68h] [rbp-80h]
  unsigned __int16 *v20; // [rsp+70h] [rbp-78h]
  CLIENT_CALL_RETURN v21; // [rsp+78h] [rbp-70h]
  void *v22; // [rsp+80h] [rbp-68h]
  void **v23; // [rsp+88h] [rbp-60h]
  GUID ActivityId; // [rsp+90h] [rbp-58h] BYREF

  v20 = a3;
  v22 = a1;
  v9 = a5;
  v19 = a5;
  v23 = a6;
  v18 = 0;
  v17 = 0;
  ActivityId = 0;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 105) >= 4u
    && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 2) != 0 )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 12), 206, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    v10 = WPP_GLOBAL_Control;
    v9 = v19;
  }
  if ( !a1 || !a2 || !a4 || !a6 || !v9 )
  {
    v12 = 87;
    if ( v10 == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v12;
    if ( !*((_BYTE *)v10 + 105) || (*((_DWORD *)v10 + 27) & 0x1000) == 0 )
      goto LABEL_34;
    v13 = 207;
LABEL_32:
    WPP_SF_(*((_QWORD *)v10 + 12), v13, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids);
    goto LABEL_33;
  }
  if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v10 + 105) >= 3u
    && (*((_DWORD *)v10 + 27) & 0x1000) != 0 )
  {
    WPP_SF_q(*((_QWORD *)v10 + 12), 208, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, a2);
  }
  v11 = HtReferenceHandleWithTag(g_hHandleTable, a1, 1466525252, 0, 1, &v18);
  v12 = v11;
  if ( !v11 )
  {
    v12 = LocalWfdAsyncContextCreateInternal(a1, &v17, 0);
    if ( !v12 )
    {
      v14 = v17;
      *(_DWORD *)v17 = 5;
      EventActivityIdControl(1u, &ActivityId);
      v15 = *v18;
      v21.Simple = 0;
      v21.Pointer = NdrClientCall3(
                      (MIDL_STUBLESS_PROXY_INFO *)&winwlan_ProxyInfo,
                      0x62u,
                      0,
                      &ActivityId,
                      v15,
                      a2,
                      v20,
                      a4,
                      v19,
                      (char *)v14 + 152).Pointer;
      v12 = ServiceStatus((unsigned int)v21.Pointer);
      if ( !v12 )
      {
        LocalWfdAsyncContextPendingMarkIdle(v14);
        *a6 = (void *)*((_QWORD *)v14 + 2);
        v10 = WPP_GLOBAL_Control;
      }
      if ( !v18 )
        goto LABEL_34;
      HtDereferenceHandleWithTag(g_hHandleTable, a1, 0, 1);
      goto LABEL_33;
    }
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
      return v12;
    if ( !*((_BYTE *)WPP_GLOBAL_Control + 105) || (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) == 0 )
      goto LABEL_34;
    v13 = 210;
    goto LABEL_32;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control )
    return v12;
  if ( *((_BYTE *)WPP_GLOBAL_Control + 105) && (*((_DWORD *)WPP_GLOBAL_Control + 27) & 0x1000) != 0 )
  {
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 12), 209, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, a1, v11);
LABEL_33:
    v10 = WPP_GLOBAL_Control;
  }
LABEL_34:
  if ( v10 != (union DOT11_OUI_HEADER *)&WPP_GLOBAL_Control
    && *((_BYTE *)v10 + 105) >= 4u
    && (*((_BYTE *)v10 + 108) & 2) != 0 )
  {
    WPP_SF_d(*((_QWORD *)v10 + 12), 212, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids, v12);
  }
  return v12;
}

```

## disassembly

```asm
0x180050370  push    rbx
0x180050372  push    rsi
0x180050373  push    rdi
0x180050374  push    r12
0x180050376  push    r13
0x180050378  push    r14
0x18005037a  push    r15
0x18005037c  sub     rsp, 0B0h
0x180050383  mov     rax, cs:__security_cookie
0x18005038a  xor     rax, rsp
0x18005038d  mov     [rsp+0E8h+var_48], rax
0x180050395  mov     r13, r9
0x180050398  mov     [rsp+0E8h+var_78], r8
0x18005039d  mov     r12, rdx
0x1800503a0  mov     r14, rcx
0x1800503a3  mov     [rsp+0E8h+var_68], rcx
0x1800503ab  mov     rax, [rsp+0E8h+arg_20]
0x1800503b3  mov     [rsp+0E8h+var_80], rax
0x1800503b8  mov     r15, [rsp+0E8h+arg_28]
0x1800503c0  mov     [rsp+0E8h+var_60], r15
0x1800503c8  mov     [rsp+0E8h+var_88], 0
0x1800503d1  mov     [rsp+0E8h+var_90], 0
0x1800503da  xorps   xmm0, xmm0
0x1800503dd  movups  xmmword ptr [rsp+0E8h+ActivityId.Data1], xmm0
0x1800503e5  lea     rsi, WPP_GLOBAL_Control
0x1800503ec  mov     r10, cs:WPP_GLOBAL_Control
0x1800503f3  cmp     r10, rsi
0x1800503f6  jz      short loc_180050427
0x1800503f8  cmp     byte ptr [r10+69h], 4
0x1800503fd  jb      short loc_180050427
0x1800503ff  test    byte ptr [r10+6Ch], 2
0x180050404  jz      short loc_180050427
0x180050406  mov     edx, 0CEh
0x18005040b  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x180050412  mov     rcx, [r10+60h]
0x180050416  call    WPP_SF_
0x18005041b  mov     r10, cs:WPP_GLOBAL_Control
0x180050422  mov     rax, [rsp+0E8h+var_80]
0x180050427  test    r14, r14
0x18005042a  jz      loc_180050681
0x180050430  test    r12, r12
0x180050433  jz      loc_180050681
0x180050439  test    r13, r13
0x18005043c  jz      loc_180050681
0x180050442  test    r15, r15
0x180050445  jz      loc_180050681
0x18005044b  test    rax, rax
0x18005044e  jz      loc_180050681
0x180050454  cmp     r10, rsi
0x180050457  jz      short loc_180050485
0x180050459  cmp     byte ptr [r10+69h], 3
0x18005045e  jb      short loc_180050485
0x180050460  mov     edi, 1000h
0x180050465  test    [r10+6Ch], edi
0x180050469  jz      short loc_18005048A
0x18005046b  mov     edx, 0D0h
0x180050470  mov     r9, r12
0x180050473  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005047a  mov     rcx, [r10+60h]
0x18005047e  call    WPP_SF_q
0x180050483  jmp     short loc_18005048A
0x180050485  mov     edi, 1000h
0x18005048a  lea     rax, [rsp+0E8h+var_88]
0x18005048f  mov     [rsp+0E8h+var_C0], rax
0x180050494  mov     dword ptr [rsp+0E8h+var_C8], 1
0x18005049c  xor     r9d, r9d
0x18005049f  mov     r8d, 57696644h
0x1800504a5  mov     rdx, r14
0x1800504a8  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x1800504af  call    cs:__imp_HtReferenceHandleWithTag
0x1800504b5  mov     ebx, eax
0x1800504b7  test    eax, eax
0x1800504b9  jz      short loc_180050501
0x1800504bb  mov     r10, cs:WPP_GLOBAL_Control
0x1800504c2  cmp     r10, rsi
0x1800504c5  jz      loc_1800506E2
0x1800504cb  cmp     byte ptr [r10+69h], 1
0x1800504d0  jb      loc_1800506B7
0x1800504d6  test    [r10+6Ch], edi
0x1800504da  jz      loc_1800506B7
0x1800504e0  mov     edx, 0D1h
0x1800504e5  mov     dword ptr [rsp+0E8h+var_C8], eax
0x1800504e9  mov     r9, r14
0x1800504ec  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800504f3  mov     rcx, [r10+60h]
0x1800504f7  call    WPP_SF_qD
0x1800504fc  jmp     loc_1800506B0
0x180050501  xor     r8d, r8d; int
0x180050504  lea     rdx, [rsp+0E8h+var_90]; struct _WFD_API_ASYNC_CONTEXT **
0x180050509  mov     rcx, r14; void *
0x18005050c  call    ?LocalWfdAsyncContextCreateInternal@@YAKPEAXPEAPEAU_WFD_API_ASYNC_CONTEXT@@H@Z; LocalWfdAsyncContextCreateInternal(void *,_WFD_API_ASYNC_CONTEXT * *,int)
0x180050511  mov     ebx, eax
0x180050513  test    eax, eax
0x180050515  jz      short loc_180050546
0x180050517  mov     r10, cs:WPP_GLOBAL_Control
0x18005051e  cmp     r10, rsi
0x180050521  jz      loc_1800506E2
0x180050527  cmp     byte ptr [r10+69h], 1
0x18005052c  jb      loc_1800506B7
0x180050532  test    [r10+6Ch], edi
0x180050536  jz      loc_1800506B7
0x18005053c  mov     edx, 0D2h
0x180050541  jmp     loc_1800506A0
0x180050546  mov     rdi, [rsp+0E8h+var_90]
0x18005054b  mov     dword ptr [rdi], 5
0x180050551  lea     rdx, [rsp+0E8h+ActivityId]; ActivityId
0x180050559  mov     ecx, 1; ControlCode
0x18005055e  call    cs:__imp_EventActivityIdControl
0x180050564  nop
0x180050565  lea     rcx, [rdi+98h]
0x18005056c  mov     rax, [rsp+0E8h+var_88]
0x180050571  mov     rdx, [rax]
0x180050574  mov     [rsp+0E8h+var_70], 0
0x18005057d  mov     [rsp+0E8h+var_A0], rcx
0x180050582  mov     rax, [rsp+0E8h+var_80]
0x180050587  mov     [rsp+0E8h+var_A8], rax
0x18005058c  mov     [rsp+0E8h+var_B0], r13
0x180050591  mov     rax, [rsp+0E8h+var_78]
0x180050596  mov     [rsp+0E8h+var_B8], rax
0x18005059b  mov     [rsp+0E8h+var_C0], r12
0x1800505a0  mov     [rsp+0E8h+var_C8], rdx
0x1800505a5  lea     r9, [rsp+0E8h+ActivityId]
0x1800505ad  xor     r8d, r8d; pReturnValue
0x1800505b0  lea     edx, [r8+62h]; nProcNum
0x1800505b4  lea     rcx, ?winwlan_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x1800505bb  call    cs:__imp_NdrClientCall3
0x1800505c1  mov     rbx, rax
0x1800505c4  mov     [rsp+0E8h+var_70], rax
0x1800505c9  mov     [rsp+0E8h+var_98], eax
0x1800505cd  mov     r10, cs:WPP_GLOBAL_Control
0x1800505d4  jmp     short loc_18005063B
0x1800505d6  mov     ebx, eax
0x1800505d8  mov     [rsp+0E8h+var_98], eax
0x1800505dc  lea     rcx, WPP_GLOBAL_Control
0x1800505e3  mov     r10, cs:WPP_GLOBAL_Control
0x1800505ea  cmp     r10, rcx
0x1800505ed  jz      short loc_18005061F
0x1800505ef  cmp     byte ptr [r10+69h], 1
0x1800505f4  jb      short loc_18005061F
0x1800505f6  test    dword ptr [r10+6Ch], 1000h
0x1800505fe  jz      short loc_18005061F
0x180050600  mov     edx, 0D3h
0x180050605  mov     r9d, eax
0x180050608  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x18005060f  mov     rcx, [r10+60h]
0x180050613  call    WPP_SF_d
0x180050618  mov     r10, cs:WPP_GLOBAL_Control
0x18005061f  lea     rsi, WPP_GLOBAL_Control
0x180050626  mov     rdi, [rsp+0E8h+var_90]
0x18005062b  mov     r14, [rsp+0E8h+var_68]
0x180050633  mov     r15, [rsp+0E8h+var_60]
0x18005063b  mov     ecx, ebx; unsigned int
0x18005063d  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180050642  mov     ebx, eax
0x180050644  test    eax, eax
0x180050646  jnz     short loc_18005065E
0x180050648  mov     rcx, rdi; struct _WFD_API_ASYNC_CONTEXT *
0x18005064b  call    ?LocalWfdAsyncContextPendingMarkIdle@@YAKPEAU_WFD_API_ASYNC_CONTEXT@@@Z; LocalWfdAsyncContextPendingMarkIdle(_WFD_API_ASYNC_CONTEXT *)
0x180050650  mov     rax, [rdi+10h]
0x180050654  mov     [r15], rax
0x180050657  mov     r10, cs:WPP_GLOBAL_Control
0x18005065e  cmp     [rsp+0E8h+var_88], 0
0x180050664  jz      short loc_1800506B7
0x180050666  mov     r9d, 1
0x18005066c  xor     r8d, r8d
0x18005066f  mov     rdx, r14
0x180050672  mov     rcx, cs:?g_hHandleTable@@3PEAXEA; void * g_hHandleTable
0x180050679  call    cs:__imp_HtDereferenceHandleWithTag
0x18005067f  jmp     short loc_1800506B0
0x180050681  mov     ebx, 57h ; 'W'
0x180050686  cmp     r10, rsi
0x180050689  jz      short loc_1800506E2
0x18005068b  cmp     byte ptr [r10+69h], 1
0x180050690  jb      short loc_1800506B7
0x180050692  mov     edi, 1000h
0x180050697  test    [r10+6Ch], edi
0x18005069b  jz      short loc_1800506B7
0x18005069d  lea     edx, [rbx+78h]
0x1800506a0  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800506a7  mov     rcx, [r10+60h]
0x1800506ab  call    WPP_SF_
0x1800506b0  mov     r10, cs:WPP_GLOBAL_Control
0x1800506b7  cmp     r10, rsi
0x1800506ba  jz      short loc_1800506E2
0x1800506bc  cmp     byte ptr [r10+69h], 4
0x1800506c1  jb      short loc_1800506E2
0x1800506c3  test    byte ptr [r10+6Ch], 2
0x1800506c8  jz      short loc_1800506E2
0x1800506ca  mov     edx, 0D4h
0x1800506cf  mov     r9d, ebx
0x1800506d2  lea     r8, WPP_de4c4d172dae37ca16eaa1b0651a94d4_Traceguids
0x1800506d9  mov     rcx, [r10+60h]
0x1800506dd  call    WPP_SF_d
0x1800506e2  mov     eax, ebx
0x1800506e4  mov     rcx, [rsp+0E8h+var_48]
0x1800506ec  xor     rcx, rsp; StackCookie
0x1800506ef  call    __security_check_cookie
0x1800506f4  add     rsp, 0B0h
0x1800506fb  pop     r15
0x1800506fd  pop     r14
0x1800506ff  pop     r13
0x180050701  pop     r12
0x180050703  pop     rdi
0x180050704  pop     rsi
0x180050705  pop     rbx
0x180050706  retn
0x180060ff4  push    rbp
0x180060ff6  sub     rsp, 50h
0x180060ffa  mov     rbp, rdx
0x180060ffd  mov     rcx, [rcx]
0x180061000  mov     ecx, [rcx]; ExceptionCode
0x180061002  call    cs:__imp_RpcExceptionFilter
0x180061008  nop
0x180061009  add     rsp, 50h
0x18006100d  pop     rbp
0x18006100e  retn
```
