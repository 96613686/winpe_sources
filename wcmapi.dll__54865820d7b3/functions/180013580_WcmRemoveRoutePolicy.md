# WcmRemoveRoutePolicy

- ea: `0x180013580`
- end: `0x1800136b6`
- name: `WcmRemoveRoutePolicy`
- size: `310`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task`

## callees

- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180008a90`
- `0x1800111dc`
- `0x180013580`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800135f7`
- `RPCRT4!NdrClientCall3` at `0x1800135f7`
- `RPCRT4!RpcExceptionFilter` at `0x18001caec`
- `RPCRT4!RpcExceptionFilter` at `0x18001caec`

## string_xrefs

- `0x1800135c7`: `WcmRemoveRoutePolicy`
- `0x180013684`: `WcmRemoveRoutePolicy`

## pseudocode

```c
__int64 __fastcall WcmRemoveRoutePolicy(__int64 a1)
{
  unsigned int v2; // eax
  __int64 v3; // r10
  unsigned int v4; // ebx
  __int16 v6; // [rsp+34h] [rbp-14h] BYREF

  v6 = 0;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      147,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmRemoveRoutePolicy");
  }
  NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001F030, 8u, 0, &v6, a1);
  v2 = ServiceStatus(0);
  v4 = v2;
  if ( (WcmPolicyManager **)v3 != &WPP_GLOBAL_Control && *(_BYTE *)(v3 + 25) >= 5u && (*(_BYTE *)(v3 + 28) & 1) != 0 )
    WPP_SF_sL(
      *(_QWORD *)(v3 + 16),
      149,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmRemoveRoutePolicy",
      v2);
  return v4;
}

```

## disassembly

```asm
0x180013580  mov     [rsp+arg_8], rbx
0x180013585  push    rdi
0x180013586  sub     rsp, 40h
0x18001358a  mov     rax, cs:__security_cookie
0x180013591  xor     rax, rsp
0x180013594  mov     [rsp+48h+var_10], rax
0x180013599  mov     rbx, rcx
0x18001359c  xor     eax, eax
0x18001359e  mov     [rsp+48h+var_14], ax
0x1800135a3  lea     rdi, WPP_GLOBAL_Control
0x1800135aa  mov     rcx, cs:WPP_GLOBAL_Control
0x1800135b1  cmp     rcx, rdi
0x1800135b4  jz      short loc_1800135DF
0x1800135b6  cmp     byte ptr [rcx+19h], 5
0x1800135ba  jb      short loc_1800135DF
0x1800135bc  test    byte ptr [rcx+1Ch], 1
0x1800135c0  jz      short loc_1800135DF
0x1800135c2  mov     edx, 93h
0x1800135c7  lea     r9, aWcmremoveroute_0; "WcmRemoveRoutePolicy"
0x1800135ce  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800135d5  mov     rcx, [rcx+10h]
0x1800135d9  call    WPP_SF_s
0x1800135de  nop
0x1800135df  mov     [rsp+48h+var_28], rbx
0x1800135e4  lea     r9, [rsp+48h+var_14]
0x1800135e9  xor     r8d, r8d; pReturnValue
0x1800135ec  lea     edx, [r8+8]; nProcNum
0x1800135f0  lea     rcx, stru_18001F030; pProxyInfo
0x1800135f7  call    cs:__imp_NdrClientCall3
0x1800135fe  nop     dword ptr [rax+rax+00h]
0x180013603  xor     ebx, ebx
0x180013605  mov     [rsp+48h+var_18], ebx
0x180013609  mov     r10, cs:WPP_GLOBAL_Control
0x180013610  jmp     short loc_18001365F
0x180013612  mov     ebx, eax
0x180013614  mov     [rsp+48h+var_18], eax
0x180013618  lea     rax, WPP_GLOBAL_Control
0x18001361f  mov     r10, cs:WPP_GLOBAL_Control
0x180013626  cmp     r10, rax
0x180013629  jz      short loc_180013658
0x18001362b  cmp     byte ptr [r10+19h], 1
0x180013630  jb      short loc_180013658
0x180013632  test    byte ptr [r10+1Ch], 1
0x180013637  jz      short loc_180013658
0x180013639  mov     edx, 94h
0x18001363e  mov     r9d, ebx
0x180013641  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180013648  mov     rcx, [r10+10h]
0x18001364c  call    WPP_SF_D
0x180013651  mov     r10, cs:WPP_GLOBAL_Control
0x180013658  lea     rdi, WPP_GLOBAL_Control
0x18001365f  mov     ecx, ebx; unsigned int
0x180013661  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180013666  mov     ebx, eax
0x180013668  cmp     r10, rdi
0x18001366b  jz      short loc_18001369B
0x18001366d  cmp     byte ptr [r10+19h], 5
0x180013672  jb      short loc_18001369B
0x180013674  test    byte ptr [r10+1Ch], 1
0x180013679  jz      short loc_18001369B
0x18001367b  mov     edx, 95h
0x180013680  mov     dword ptr [rsp+48h+var_28], eax
0x180013684  lea     r9, aWcmremoveroute_0; "WcmRemoveRoutePolicy"
0x18001368b  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180013692  mov     rcx, [r10+10h]
0x180013696  call    WPP_SF_sL
0x18001369b  mov     eax, ebx
0x18001369d  mov     rcx, [rsp+48h+var_10]
0x1800136a2  xor     rcx, rsp; StackCookie
0x1800136a5  call    __security_check_cookie
0x1800136aa  mov     rbx, [rsp+48h+arg_8]
0x1800136af  add     rsp, 40h
0x1800136b3  pop     rdi
0x1800136b4  retn
0x18001cade  push    rbp
0x18001cae0  sub     rsp, 30h
0x18001cae4  mov     rbp, rdx
0x18001cae7  mov     rcx, [rcx]
0x18001caea  mov     ecx, [rcx]; ExceptionCode
0x18001caec  call    cs:__imp_RpcExceptionFilter
0x18001caf3  nop     dword ptr [rax+rax+00h]
0x18001caf8  nop
0x18001caf9  add     rsp, 30h
0x18001cafd  pop     rbp
0x18001cafe  retn
```
