# WcmDeleteAppBasedRoutePolicy

- ea: `0x180011de0`
- end: `0x180011f6f`
- name: `WcmDeleteAppBasedRoutePolicy`
- size: `399`
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
- `0x180011de0`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180011eaa`
- `RPCRT4!NdrClientCall3` at `0x180011eaa`

## string_xrefs

- `0x180011e20`: `WcmDeleteAppBasedRoutePolicy`
- `0x180011e68`: `WcmDeleteAppBasedRoutePolicy`
- `0x180011f3d`: `WcmDeleteAppBasedRoutePolicy`

## pseudocode

```c
__int64 __fastcall WcmDeleteAppBasedRoutePolicy(__int64 a1)
{
  WcmPolicyManager *v2; // rcx
  unsigned int v4; // eax
  __int64 v5; // r10
  unsigned int v6; // ebx
  unsigned int Pointer; // [rsp+30h] [rbp-28h]
  __int16 v8; // [rsp+40h] [rbp-18h] BYREF

  v2 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      169,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmDeleteAppBasedRoutePolicy");
    v2 = WPP_GLOBAL_Control;
  }
  v8 = 0;
  if ( a1 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 3u, 0, &v8, a1).Pointer;
    v4 = ServiceStatus(Pointer);
    v6 = v4;
    if ( (WcmPolicyManager **)v5 != &WPP_GLOBAL_Control && *(_BYTE *)(v5 + 25) >= 5u && (*(_BYTE *)(v5 + 28) & 1) != 0 )
      WPP_SF_sL(
        *(_QWORD *)(v5 + 16),
        172,
        (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
        (unsigned int)"WcmDeleteAppBasedRoutePolicy",
        v4);
    return v6;
  }
  else
  {
    if ( v2 != (WcmPolicyManager *)&WPP_GLOBAL_Control && *((_BYTE *)v2 + 25) >= 5u && (*((_BYTE *)v2 + 28) & 1) != 0 )
      WPP_SF_sL(
        *((_QWORD *)v2 + 2),
        170,
        (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
        (unsigned int)"WcmDeleteAppBasedRoutePolicy",
        87);
    return 87;
  }
}

```

## disassembly

```asm
0x180011de0  mov     [rsp+arg_8], rbx
0x180011de5  push    rdi
0x180011de6  sub     rsp, 50h
0x180011dea  mov     rax, cs:__security_cookie
0x180011df1  xor     rax, rsp
0x180011df4  mov     [rsp+58h+var_10], rax
0x180011df9  mov     rbx, rcx
0x180011dfc  lea     rdi, WPP_GLOBAL_Control
0x180011e03  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e0a  cmp     rcx, rdi
0x180011e0d  jz      short loc_180011E3E
0x180011e0f  cmp     byte ptr [rcx+19h], 5
0x180011e13  jb      short loc_180011E3E
0x180011e15  test    byte ptr [rcx+1Ch], 1
0x180011e19  jz      short loc_180011E3E
0x180011e1b  mov     edx, 0A9h
0x180011e20  lea     r9, aWcmdeleteappba_0; "WcmDeleteAppBasedRoutePolicy"
0x180011e27  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180011e2e  mov     rcx, [rcx+10h]
0x180011e32  call    WPP_SF_s
0x180011e37  mov     rcx, cs:WPP_GLOBAL_Control
0x180011e3e  xor     eax, eax
0x180011e40  mov     [rsp+58h+var_18], ax
0x180011e45  test    rbx, rbx
0x180011e48  jnz     short loc_180011E89
0x180011e4a  cmp     rcx, rdi
0x180011e4d  jz      short loc_180011E7F
0x180011e4f  cmp     byte ptr [rcx+19h], 5
0x180011e53  jb      short loc_180011E7F
0x180011e55  test    byte ptr [rcx+1Ch], 1
0x180011e59  jz      short loc_180011E7F
0x180011e5b  mov     edx, 0AAh
0x180011e60  mov     dword ptr [rsp+58h+var_38], 57h ; 'W'
0x180011e68  lea     r9, aWcmdeleteappba_0; "WcmDeleteAppBasedRoutePolicy"
0x180011e6f  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180011e76  mov     rcx, [rcx+10h]
0x180011e7a  call    WPP_SF_sL
0x180011e7f  mov     eax, 57h ; 'W'
0x180011e84  jmp     loc_180011F56
0x180011e89  mov     [rsp+58h+var_20], 0
0x180011e92  mov     [rsp+58h+var_38], rbx
0x180011e97  lea     r9, [rsp+58h+var_18]
0x180011e9c  xor     r8d, r8d; pReturnValue
0x180011e9f  lea     edx, [r8+3]; nProcNum
0x180011ea3  lea     rcx, pProxyInfo; pProxyInfo
0x180011eaa  call    cs:__imp_NdrClientCall3
0x180011eb1  nop     dword ptr [rax+rax+00h]
0x180011eb6  mov     rbx, rax
0x180011eb9  mov     [rsp+58h+var_20], rax
0x180011ebe  mov     [rsp+58h+var_28], eax
0x180011ec2  mov     r10, cs:WPP_GLOBAL_Control
0x180011ec9  jmp     short loc_180011F18
0x180011ecb  mov     ebx, eax
0x180011ecd  mov     [rsp+58h+var_28], eax
0x180011ed1  lea     rcx, WPP_GLOBAL_Control
0x180011ed8  mov     r10, cs:WPP_GLOBAL_Control
0x180011edf  cmp     r10, rcx
0x180011ee2  jz      short loc_180011F11
0x180011ee4  cmp     byte ptr [r10+19h], 1
0x180011ee9  jb      short loc_180011F11
0x180011eeb  test    byte ptr [r10+1Ch], 1
0x180011ef0  jz      short loc_180011F11
0x180011ef2  mov     edx, 0ABh
0x180011ef7  mov     r9d, eax
0x180011efa  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180011f01  mov     rcx, [r10+10h]
0x180011f05  call    WPP_SF_D
0x180011f0a  mov     r10, cs:WPP_GLOBAL_Control
0x180011f11  lea     rdi, WPP_GLOBAL_Control
0x180011f18  mov     ecx, ebx; unsigned int
0x180011f1a  call    ?ServiceStatus@@YAKK@Z; ServiceStatus(ulong)
0x180011f1f  mov     ebx, eax
0x180011f21  cmp     r10, rdi
0x180011f24  jz      short loc_180011F54
0x180011f26  cmp     byte ptr [r10+19h], 5
0x180011f2b  jb      short loc_180011F54
0x180011f2d  test    byte ptr [r10+1Ch], 1
0x180011f32  jz      short loc_180011F54
0x180011f34  mov     edx, 0ACh
0x180011f39  mov     dword ptr [rsp+58h+var_38], eax
0x180011f3d  lea     r9, aWcmdeleteappba_0; "WcmDeleteAppBasedRoutePolicy"
0x180011f44  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180011f4b  mov     rcx, [r10+10h]
0x180011f4f  call    WPP_SF_sL
0x180011f54  mov     eax, ebx
0x180011f56  mov     rcx, [rsp+58h+var_10]
0x180011f5b  xor     rcx, rsp; StackCookie
0x180011f5e  call    __security_check_cookie
0x180011f63  mov     rbx, [rsp+58h+arg_8]
0x180011f68  add     rsp, 50h
0x180011f6c  pop     rdi
0x180011f6d  retn
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
