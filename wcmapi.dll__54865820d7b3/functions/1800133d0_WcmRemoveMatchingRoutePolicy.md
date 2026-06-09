# WcmRemoveMatchingRoutePolicy

- ea: `0x1800133d0`
- end: `0x180013579`
- name: `WcmRemoveMatchingRoutePolicy`
- size: `425`
- prototype: `__int64 __fastcall(unsigned __int16 *)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180008a90`
- `0x18000e8a8`
- `0x1800111dc`
- `0x1800133d0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180013469`
- `RPCRT4!NdrClientCall3` at `0x180013469`

## string_xrefs

- `0x18001342f`: `WcmRemoveMatchingRoutePolicy`
- `0x180013539`: `WcmRemoveMatchingRoutePolicy`

## pseudocode

```c
__int64 __fastcall WcmRemoveMatchingRoutePolicy(unsigned __int16 *a1, int a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  unsigned int v6; // r9d
  int v8; // [rsp+28h] [rbp-70h]
  unsigned int Pointer; // [rsp+30h] [rbp-68h]
  __int64 v10; // [rsp+50h] [rbp-48h] BYREF
  GUID v11; // [rsp+58h] [rbp-40h]
  __int16 v12; // [rsp+68h] [rbp-30h] BYREF

  v12 = 0;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      150,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmRemoveMatchingRoutePolicy");
  }
  v8 = a2;
  Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001F030, 9u, 0, &v12, a1, v8).Pointer;
  v4 = ServiceStatus(Pointer);
  v5 = v4;
  if ( v4 > 0 )
    v6 = (unsigned __int16)v4 | 0x80070000;
  else
    v6 = v4;
  v10 = 4;
  v11 = GUID_NULL;
  NetworkingTriageScenario::OnDemand::OnDemandRequestRemoveHttpRouteAction(
    (const struct NetworkingTriageScenario::OnDemand::RequiredFields *)&v10,
    a1,
    a2 != 0,
    v6);
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      152,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmRemoveMatchingRoutePolicy",
      v5);
  }
  return v5;
}

```

## disassembly

```asm
0x1800133d0  mov     [rsp+arg_10], rbx
0x1800133d5  mov     [rsp+arg_18], rsi
0x1800133da  push    rdi
0x1800133db  push    r14
0x1800133dd  push    r15
0x1800133df  sub     rsp, 80h
0x1800133e6  mov     rax, cs:__security_cookie
0x1800133ed  xor     rax, rsp
0x1800133f0  mov     [rsp+98h+var_28], rax
0x1800133f5  mov     r14d, edx
0x1800133f8  mov     rsi, rcx
0x1800133fb  mov     [rsp+98h+var_50], rcx
0x180013400  mov     [rsp+98h+var_60], edx
0x180013404  xor     edi, edi
0x180013406  mov     [rsp+98h+var_30], di
0x18001340b  lea     r15, WPP_GLOBAL_Control
0x180013412  mov     rcx, cs:WPP_GLOBAL_Control
0x180013419  cmp     rcx, r15
0x18001341c  jz      short loc_180013447
0x18001341e  cmp     byte ptr [rcx+19h], 5
0x180013422  jb      short loc_180013447
0x180013424  test    byte ptr [rcx+1Ch], 1
0x180013428  jz      short loc_180013447
0x18001342a  mov     edx, 96h
0x18001342f  lea     r9, aWcmremovematch_0; "WcmRemoveMatchingRoutePolicy"
0x180013436  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x18001343d  mov     rcx, [rcx+10h]
0x180013441  call    WPP_SF_s
0x180013446  nop
0x180013447  mov     [rsp+98h+var_58], rdi
0x18001344c  mov     [rsp+98h+var_70], r14d
0x180013451  mov     [rsp+98h+var_78], rsi
0x180013456  lea     r9, [rsp+98h+var_30]
0x18001345b  xor     r8d, r8d; pReturnValue
0x18001345e  lea     edx, [r8+9]; nProcNum
0x180013462  lea     rcx, stru_18001F030; pProxyInfo
0x180013469  call    cs:__imp_NdrClientCall3
0x180013470  nop     dword ptr [rax+rax+00h]
0x180013475  mov     rbx, rax
0x180013478  mov     [rsp+98h+var_58], rax
0x18001347d  mov     [rsp+98h+var_68], eax
0x180013481  jmp     short loc_1800134D1
0x180013483  mov     ebx, eax
0x180013485  mov     [rsp+98h+var_68], eax
0x180013489  lea     rdx, WPP_GLOBAL_Control
0x180013490  mov     rcx, cs:WPP_GLOBAL_Control
0x180013497  cmp     rcx, rdx
0x18001349a  jz      short loc_1800134C0
0x18001349c  cmp     byte ptr [rcx+19h], 1
0x1800134a0  jb      short loc_1800134C0
0x1800134a2  test    byte ptr [rcx+1Ch], 1
0x1800134a6  jz      short loc_1800134C0
0x1800134a8  mov     edx, 97h
0x1800134ad  mov     r9d, eax
0x1800134b0  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800134b7  mov     rcx, [rcx+10h]
0x1800134bb  call    WPP_SF_D
0x1800134c0  lea     r15, WPP_GLOBAL_Control
0x1800134c7  mov     rsi, [rsp+98h+var_50]
0x1800134cc  mov     r14d, [rsp+98h+var_60]
0x1800134d1  mov     ecx, ebx; unsigned int
0x1800134d3  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800134d8  mov     ebx, eax
0x1800134da  test    eax, eax
0x1800134dc  jg      short loc_1800134E3
0x1800134de  mov     r9d, eax
0x1800134e1  jmp     short loc_1800134EE
0x1800134e3  movzx   r9d, bx
0x1800134e7  or      r9d, 80070000h; int
0x1800134ee  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x1800134f5  mov     [rsp+98h+var_48], 4
0x1800134fe  movdqu  [rsp+98h+var_40], xmm0
0x180013504  test    r14d, r14d
0x180013507  setnz   r8b; bool
0x18001350b  mov     rdx, rsi; unsigned __int16 *
0x18001350e  lea     rcx, [rsp+98h+var_48]; struct NetworkingTriageScenario::OnDemand::RequiredFields *
0x180013513  call    ?OnDemandRequestRemoveHttpRouteAction@OnDemand@NetworkingTriageScenario@@SAXAEBURequiredFields@12@PEBG_NJ@Z; NetworkingTriageScenario::OnDemand::OnDemandRequestRemoveHttpRouteAction(NetworkingTriageScenario::OnDemand::RequiredFields const &,ushort const *,bool,long)
0x180013518  mov     rcx, cs:WPP_GLOBAL_Control
0x18001351f  cmp     rcx, r15
0x180013522  jz      short loc_180013550
0x180013524  cmp     byte ptr [rcx+19h], 5
0x180013528  jb      short loc_180013550
0x18001352a  test    byte ptr [rcx+1Ch], 1
0x18001352e  jz      short loc_180013550
0x180013530  mov     edx, 98h
0x180013535  mov     dword ptr [rsp+98h+var_78], ebx
0x180013539  lea     r9, aWcmremovematch_0; "WcmRemoveMatchingRoutePolicy"
0x180013540  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180013547  mov     rcx, [rcx+10h]
0x18001354b  call    WPP_SF_sL
0x180013550  mov     eax, ebx
0x180013552  mov     rcx, [rsp+98h+var_28]
0x180013557  xor     rcx, rsp; StackCookie
0x18001355a  call    __security_check_cookie
0x18001355f  lea     r11, [rsp+98h+var_18]
0x180013567  mov     rbx, [r11+30h]
0x18001356b  mov     rsi, [r11+38h]
0x18001356f  mov     rsp, r11
0x180013572  pop     r15
0x180013574  pop     r14
0x180013576  pop     rdi
0x180013577  retn
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
