# WcmGetInterfaceContextTable

- ea: `0x180002bd0`
- end: `0x180002df2`
- name: `WcmGetInterfaceContextTable`
- size: `546`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180002bd0`
- `0x180004450`
- `0x1800044b0`
- `0x180008a90`
- `0x1800111dc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c74`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180002c74`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002c56`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180002c56`
- `RPCRT4!NdrClientCall3` at `0x180002cd3`
- `RPCRT4!NdrClientCall3` at `0x180002cd3`
- `RPCRT4!RpcExceptionFilter` at `0x18001c97e`
- `RPCRT4!RpcExceptionFilter` at `0x18001c97e`
- `RMCLIENT!RmAccessCheck` at `0x180002c87`
- `RMCLIENT!RmAccessCheck` at `0x180002c87`

## pseudocode

```c
__int64 __fastcall WcmGetInterfaceContextTable(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5)
{
  BOOL v9; // ecx
  DWORD CurrentProcessId; // eax
  unsigned int Pointer; // ebx
  BOOL v13; // [rsp+28h] [rbp-90h]
  int v14; // [rsp+30h] [rbp-88h]
  _WORD v15[2]; // [rsp+60h] [rbp-58h] BYREF
  int TokenInformation; // [rsp+64h] [rbp-54h] BYREF
  DWORD ReturnLength; // [rsp+68h] [rbp-50h] BYREF

  v15[0] = 0;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      140,
      &WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      "WcmGetInterfaceContextTable");
  }
  TokenInformation = 0;
  ReturnLength = 0;
  if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFCLL, TokenIsAppContainer, &TokenInformation, 4u, &ReturnLength)
    && TokenInformation )
  {
    CurrentProcessId = GetCurrentProcessId();
    v9 = RmAccessCheck(30, CurrentProcessId) != -2147024891;
  }
  else
  {
    v9 = 1;
  }
  v14 = a2;
  v13 = v9;
  Pointer = (unsigned int)NdrClientCall3(
                            (MIDL_STUBLESS_PROXY_INFO *)&stru_18001F030,
                            6u,
                            0,
                            v15,
                            a1,
                            v13,
                            v14,
                            a3,
                            a4,
                            a5).Pointer;
  if ( Pointer == 1702 || Pointer == 1717 || Pointer == 1726 || Pointer == 1753 )
    Pointer = 1062;
  if ( WPP_GLOBAL_Control != (WcmPolicyManager *)&WPP_GLOBAL_Control
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sL(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      142,
      (unsigned int)&WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids,
      (unsigned int)"WcmGetInterfaceContextTable",
      Pointer);
  }
  return Pointer;
}

```

## disassembly

```asm
0x180002bd0  push    rbx
0x180002bd2  push    rsi
0x180002bd3  push    rdi
0x180002bd4  push    r12
0x180002bd6  push    r13
0x180002bd8  push    r14
0x180002bda  push    r15
0x180002bdc  sub     rsp, 80h
0x180002be3  mov     rax, cs:__security_cookie
0x180002bea  xor     rax, rsp
0x180002bed  mov     [rsp+0B8h+var_48], rax
0x180002bf2  mov     r15, r9
0x180002bf5  mov     r14, r8
0x180002bf8  mov     esi, edx
0x180002bfa  mov     rbx, rcx
0x180002bfd  mov     r12, [rsp+0B8h+arg_20]
0x180002c05  xor     r13d, r13d
0x180002c08  mov     [rsp+0B8h+var_58], r13w
0x180002c0e  lea     rdi, WPP_GLOBAL_Control
0x180002c15  mov     rcx, cs:WPP_GLOBAL_Control
0x180002c1c  cmp     rcx, rdi
0x180002c1f  jz      short loc_180002C2B
0x180002c21  cmp     byte ptr [rcx+19h], 5
0x180002c25  jnb     loc_180002DBD
0x180002c2b  mov     [rsp+0B8h+TokenInformation], r13d
0x180002c30  mov     [rsp+0B8h+var_50], r13d
0x180002c35  lea     rax, [rsp+0B8h+var_50]
0x180002c3a  mov     [rsp+0B8h+ReturnLength], rax; ReturnLength
0x180002c3f  mov     r9d, 4; TokenInformationLength
0x180002c45  lea     r8, [rsp+0B8h+TokenInformation]; TokenInformation
0x180002c4a  mov     edx, 1Dh; TokenInformationClass
0x180002c4f  mov     rcx, 0FFFFFFFFFFFFFFFCh; TokenHandle
0x180002c56  call    cs:__imp_GetTokenInformation
0x180002c5d  nop     dword ptr [rax+rax+00h]
0x180002c62  test    eax, eax
0x180002c64  jz      short loc_180002C6D
0x180002c66  cmp     [rsp+0B8h+TokenInformation], 0
0x180002c6b  jnz     short loc_180002C74
0x180002c6d  mov     ecx, 1
0x180002c72  jmp     short loc_180002C9E
0x180002c74  call    cs:__imp_GetCurrentProcessId
0x180002c7b  nop     dword ptr [rax+rax+00h]
0x180002c80  mov     edx, eax
0x180002c82  mov     ecx, 1Eh
0x180002c87  call    cs:__imp_RmAccessCheck
0x180002c8e  nop     dword ptr [rax+rax+00h]
0x180002c93  mov     ecx, r13d
0x180002c96  cmp     eax, 80070005h
0x180002c9b  setnz   cl
0x180002c9e  mov     [rsp+0B8h+var_60], r13
0x180002ca3  mov     [rsp+0B8h+var_70], r12
0x180002ca8  mov     [rsp+0B8h+var_78], r15
0x180002cad  mov     [rsp+0B8h+var_80], r14
0x180002cb2  mov     [rsp+0B8h+var_88], esi
0x180002cb6  mov     [rsp+0B8h+var_90], ecx
0x180002cba  mov     [rsp+0B8h+ReturnLength], rbx
0x180002cbf  lea     r9, [rsp+0B8h+var_58]
0x180002cc4  xor     r8d, r8d; pReturnValue
0x180002cc7  mov     edx, 6; nProcNum
0x180002ccc  lea     rcx, stru_18001F030; pProxyInfo
0x180002cd3  call    cs:__imp_NdrClientCall3
0x180002cda  nop     dword ptr [rax+rax+00h]
0x180002cdf  mov     rbx, rax
0x180002ce2  mov     [rsp+0B8h+var_60], rax
0x180002ce7  mov     [rsp+0B8h+var_68], eax
0x180002ceb  mov     rcx, cs:WPP_GLOBAL_Control
0x180002cf2  jmp     short loc_180002D3F
0x180002cf4  mov     ebx, eax
0x180002cf6  mov     [rsp+0B8h+var_68], eax
0x180002cfa  lea     rdx, WPP_GLOBAL_Control
0x180002d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d08  cmp     rcx, rdx
0x180002d0b  jz      short loc_180002D38
0x180002d0d  cmp     byte ptr [rcx+19h], 1
0x180002d11  jb      short loc_180002D38
0x180002d13  test    byte ptr [rcx+1Ch], 1
0x180002d17  jz      short loc_180002D38
0x180002d19  mov     edx, 8Dh
0x180002d1e  mov     r9d, eax
0x180002d21  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180002d28  mov     rcx, [rcx+10h]
0x180002d2c  call    WPP_SF_D
0x180002d31  mov     rcx, cs:WPP_GLOBAL_Control
0x180002d38  lea     rdi, WPP_GLOBAL_Control
0x180002d3f  mov     eax, ebx
0x180002d41  sub     eax, 6A6h
0x180002d46  jz      loc_180002DE8
0x180002d4c  sub     eax, 0Fh
0x180002d4f  jz      loc_180002DE8
0x180002d55  sub     eax, 9
0x180002d58  jz      loc_180002DE8
0x180002d5e  cmp     eax, 1Bh
0x180002d61  jz      loc_180002DE8
0x180002d67  cmp     rcx, rdi
0x180002d6a  jz      short loc_180002D72
0x180002d6c  cmp     byte ptr [rcx+19h], 5
0x180002d70  jnb     short loc_180002D95
0x180002d72  mov     eax, ebx
0x180002d74  mov     rcx, [rsp+0B8h+var_48]
0x180002d79  xor     rcx, rsp; StackCookie
0x180002d7c  call    __security_check_cookie
0x180002d81  add     rsp, 80h
0x180002d88  pop     r15
0x180002d8a  pop     r14
0x180002d8c  pop     r13
0x180002d8e  pop     r12
0x180002d90  pop     rdi
0x180002d91  pop     rsi
0x180002d92  pop     rbx
0x180002d93  retn
0x180002d95  test    byte ptr [rcx+1Ch], 1
0x180002d99  jz      short loc_180002D72
0x180002d9b  mov     edx, 8Eh
0x180002da0  mov     dword ptr [rsp+0B8h+ReturnLength], ebx
0x180002da4  lea     r9, aWcmgetinterfac_0; "WcmGetInterfaceContextTable"
0x180002dab  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180002db2  mov     rcx, [rcx+10h]
0x180002db6  call    WPP_SF_sL
0x180002dbb  jmp     short loc_180002D72
0x180002dbd  test    byte ptr [rcx+1Ch], 1
0x180002dc1  jz      loc_180002C2B
0x180002dc7  mov     edx, 8Ch
0x180002dcc  lea     r9, aWcmgetinterfac_0; "WcmGetInterfaceContextTable"
0x180002dd3  lea     r8, WPP_2d14fcc579e4320e6edf39a7387a6039_Traceguids
0x180002dda  mov     rcx, [rcx+10h]
0x180002dde  call    WPP_SF_s
0x180002de3  jmp     loc_180002C2B
0x180002de8  mov     ebx, 426h
0x180002ded  jmp     loc_180002D67
0x18001c970  push    rbp
0x18001c972  sub     rsp, 50h
0x18001c976  mov     rbp, rdx
0x18001c979  mov     rcx, [rcx]
0x18001c97c  mov     ecx, [rcx]; ExceptionCode
0x18001c97e  call    cs:__imp_RpcExceptionFilter
0x18001c985  nop     dword ptr [rax+rax+00h]
0x18001c98a  nop
0x18001c98b  add     rsp, 50h
0x18001c98f  pop     rbp
0x18001c990  retn
```
