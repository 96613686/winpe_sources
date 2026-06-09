# WcmDeleteProxyInformation

- ea: `0x180011f80`
- end: `0x180012124`
- name: `WcmDeleteProxyInformation`
- size: `420`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, service_task`

## callees

- `0x180002728`
- `0x180004450`
- `0x1800044b0`
- `0x180004d10`
- `0x180008a90`
- `0x1800111dc`
- `0x180011f80`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180012059`
- `RPCRT4!NdrClientCall3` at `0x180012059`

## string_xrefs

- `0x180011fd2`: `WcmDeleteProxyInformation`
- `0x1800120ec`: `WcmDeleteProxyInformation`

## pseudocode

```c
__int64 __fastcall WcmDeleteProxyInformation(__int64 a1, __int64 a2, int a3)
{
  WcmPolicyManager *v6; // r10
  unsigned int v7; // ebx
  unsigned int Pointer; // [rsp+40h] [rbp-38h]
  __int16 v10; // [rsp+50h] [rbp-28h] BYREF

  v10 = 0;
  v6 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      161,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmDeleteProxyInformation");
    v6 = WPP_GLOBAL_Control;
  }
  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_1800209D8, 1u, 0, &v10, a1, a2, a3).Pointer;
    v7 = ServiceStatus(Pointer);
  }
  else
  {
    if ( v6 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) && (*((_BYTE *)v6 + 28) & 1) != 0 )
    {
      WPP_SF_(*((_QWORD *)v6 + 2), 162, &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids);
      v6 = WPP_GLOBAL_Control;
    }
    v7 = 87;
  }
  if ( v6 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v6 + 25) >= 5u && (*((_BYTE *)v6 + 28) & 1) != 0 )
    WPP_SF_sL(
      *((_QWORD *)v6 + 2),
      164,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmDeleteProxyInformation",
      v7);
  return v7;
}

```

## disassembly

```asm
0x180011f80  mov     [rsp+arg_18], rbx
0x180011f85  push    rsi
0x180011f86  push    rdi
0x180011f87  push    r14
0x180011f89  sub     rsp, 60h
0x180011f8d  mov     rax, cs:__security_cookie
0x180011f94  xor     rax, rsp
0x180011f97  mov     [rsp+78h+var_20], rax
0x180011f9c  mov     r14d, r8d
0x180011f9f  mov     rsi, rdx
0x180011fa2  mov     rbx, rcx
0x180011fa5  xor     eax, eax
0x180011fa7  mov     [rsp+78h+var_28], ax
0x180011fac  lea     rdi, WPP_GLOBAL_Control
0x180011fb3  mov     r10, cs:WPP_GLOBAL_Control
0x180011fba  cmp     r10, rdi
0x180011fbd  jz      short loc_180011FF0
0x180011fbf  cmp     byte ptr [r10+19h], 5
0x180011fc4  jb      short loc_180011FF0
0x180011fc6  test    byte ptr [r10+1Ch], 1
0x180011fcb  jz      short loc_180011FF0
0x180011fcd  mov     edx, 0A1h
0x180011fd2  lea     r9, aWcmdeleteproxy_0; "WcmDeleteProxyInformation"
0x180011fd9  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180011fe0  mov     rcx, [r10+10h]
0x180011fe4  call    WPP_SF_s
0x180011fe9  mov     r10, cs:WPP_GLOBAL_Control
0x180011ff0  test    rbx, rbx
0x180011ff3  jnz     short loc_18001202E
0x180011ff5  cmp     r10, rdi
0x180011ff8  jz      short loc_180012024
0x180011ffa  cmp     byte ptr [r10+19h], 1
0x180011fff  jb      short loc_180012024
0x180012001  test    byte ptr [r10+1Ch], 1
0x180012006  jz      short loc_180012024
0x180012008  mov     edx, 0A2h
0x18001200d  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180012014  mov     rcx, [r10+10h]
0x180012018  call    WPP_SF_
0x18001201d  mov     r10, cs:WPP_GLOBAL_Control
0x180012024  mov     ebx, 57h ; 'W'
0x180012029  jmp     loc_1800120D0
0x18001202e  mov     [rsp+78h+var_30], 0
0x180012037  mov     [rsp+78h+var_48], r14d
0x18001203c  mov     [rsp+78h+var_50], rsi
0x180012041  mov     [rsp+78h+var_58], rbx
0x180012046  lea     r9, [rsp+78h+var_28]
0x18001204b  xor     r8d, r8d; pReturnValue
0x18001204e  lea     edx, [r8+1]; nProcNum
0x180012052  lea     rcx, stru_1800209D8; pProxyInfo
0x180012059  call    cs:__imp_NdrClientCall3
0x180012060  nop     dword ptr [rax+rax+00h]
0x180012065  mov     rbx, rax
0x180012068  mov     [rsp+78h+var_30], rax
0x18001206d  mov     [rsp+78h+var_38], eax
0x180012071  mov     r10, cs:WPP_GLOBAL_Control
0x180012078  jmp     short loc_1800120C7
0x18001207a  mov     ebx, eax
0x18001207c  mov     [rsp+78h+var_38], eax
0x180012080  lea     rcx, WPP_GLOBAL_Control
0x180012087  mov     r10, cs:WPP_GLOBAL_Control
0x18001208e  cmp     r10, rcx
0x180012091  jz      short loc_1800120C0
0x180012093  cmp     byte ptr [r10+19h], 1
0x180012098  jb      short loc_1800120C0
0x18001209a  test    byte ptr [r10+1Ch], 1
0x18001209f  jz      short loc_1800120C0
0x1800120a1  mov     edx, 0A3h
0x1800120a6  mov     r9d, eax
0x1800120a9  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800120b0  mov     rcx, [r10+10h]
0x1800120b4  call    WPP_SF_D
0x1800120b9  mov     r10, cs:WPP_GLOBAL_Control
0x1800120c0  lea     rdi, WPP_GLOBAL_Control
0x1800120c7  mov     ecx, ebx; unsigned int
0x1800120c9  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x1800120ce  mov     ebx, eax
0x1800120d0  cmp     r10, rdi
0x1800120d3  jz      short loc_180012103
0x1800120d5  cmp     byte ptr [r10+19h], 5
0x1800120da  jb      short loc_180012103
0x1800120dc  test    byte ptr [r10+1Ch], 1
0x1800120e1  jz      short loc_180012103
0x1800120e3  mov     edx, 0A4h
0x1800120e8  mov     dword ptr [rsp+78h+var_58], ebx
0x1800120ec  lea     r9, aWcmdeleteproxy_0; "WcmDeleteProxyInformation"
0x1800120f3  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x1800120fa  mov     rcx, [r10+10h]
0x1800120fe  call    WPP_SF_sL
0x180012103  mov     eax, ebx
0x180012105  mov     rcx, [rsp+78h+var_20]
0x18001210a  xor     rcx, rsp; StackCookie
0x18001210d  call    __security_check_cookie
0x180012112  mov     rbx, [rsp+78h+arg_18]
0x18001211a  add     rsp, 60h
0x18001211e  pop     r14
0x180012120  pop     rdi
0x180012121  pop     rsi
0x180012122  retn
0x18001d219  push    rbp
0x18001d21b  sub     rsp, 40h
0x18001d21f  mov     rbp, rdx
0x18001d222  mov     rcx, [rcx]
0x18001d225  mov     ecx, [rcx]; ExceptionCode
0x18001d227  call    cs:__imp_RpcExceptionFilter
0x18001d22e  nop     dword ptr [rax+rax+00h]
0x18001d233  nop
0x18001d234  add     rsp, 40h
0x18001d238  pop     rbp
0x18001d239  retn
```
