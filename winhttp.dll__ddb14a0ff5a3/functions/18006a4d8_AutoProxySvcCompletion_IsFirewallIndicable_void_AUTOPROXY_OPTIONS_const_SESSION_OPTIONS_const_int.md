# AutoProxySvcCompletion::IsFirewallIndicable(void *,_AUTOPROXY_OPTIONS const *,_SESSION_OPTIONS const *,int *)

- ea: `0x18006a4d8`
- end: `0x18006a756`
- name: `?IsFirewallIndicable@AutoProxySvcCompletion@@QEAAJPEAXPEBU_AUTOPROXY_OPTIONS@@PEBU_SESSION_OPTIONS@@PEAH@Z`
- size: `638`
- prototype: `int(AutoProxySvcCompletion *__hidden this, void *, const struct _AUTOPROXY_OPTIONS *, const struct _SESSION_OPTIONS *, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18006a0f0`

## callees

- `0x1800193a0`
- `0x18001e610`
- `0x18006a4d8`
- `0x1800a1d10`
- `0x1800d06fc`
- `0x1800db6b0`
- `0x1800db704`
- `0x1800dda90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006a5f5`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18006a5f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a5ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18006a5ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006a65f`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18006a65f`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a6d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a6ea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a701`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a6d3`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a6ea`
- `api-ms-win-core-heap-l2-1-0!GlobalFree` at `0x18006a701`
- `RPCRT4!RpcImpersonateClient` at `0x18006a58f`
- `RPCRT4!RpcImpersonateClient` at `0x18006a58f`
- `RPCRT4!RpcRevertToSelf` at `0x18006a6c4`
- `RPCRT4!RpcRevertToSelf` at `0x18006a6c4`

## pseudocode

```c
__int64 __fastcall AutoProxySvcCompletion::IsFirewallIndicable(
        AutoProxySvcCompletion *this,
        void *a2,
        const struct _AUTOPROXY_OPTIONS *a3,
        const struct _SESSION_OPTIONS *a4,
        int *a5)
{
  signed int v7; // ebx
  RPC_STATUS v8; // eax
  signed int LastError; // eax
  int v10; // eax
  LPWSTR lpszAutoConfigUrl; // rdi
  PDWORD ReturnLength; // [rsp+20h] [rbp-51h]
  _QWORD v14[2]; // [rsp+48h] [rbp-29h] BYREF
  WINHTTP_CURRENT_USER_IE_PROXY_CONFIG pProxyConfig; // [rsp+58h] [rbp-19h] BYREF
  int TokenInformation; // [rsp+78h] [rbp+7h] BYREF
  DWORD TokenInformationLength; // [rsp+7Ch] [rbp+Bh] BYREF

  TokenInformationLength = 4;
  TokenInformation = 0;
  v14[0] = qword_1800E7D10;
  v14[1] = 0;
  memset(&pProxyConfig, 0, sizeof(pProxyConfig));
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_qqqq(
      1029,
      143,
      (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids,
      (_DWORD)this,
      (__int64)a2,
      (__int64)a3,
      (__int64)a4);
  if ( a5 )
  {
    *a5 = 0;
    v8 = RpcImpersonateClient(a2);
    v7 = v8;
    if ( v8 > 0 )
      v7 = (unsigned __int16)v8 | 0x80070000;
    if ( v7 >= 0 )
    {
      if ( (xmmword_180107A60 & 0x20) != 0 )
        WPP_SF_q(1029, 144, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids);
      if ( GetTokenInformation(
             (HANDLE)0xFFFFFFFFFFFFFFFBLL,
             TokenIsAppContainer,
             &TokenInformation,
             TokenInformationLength,
             &TokenInformationLength) )
      {
        v10 = TokenInformation;
        v7 = 0;
        if ( TokenInformation )
        {
          if ( *((_QWORD *)a3 + 1) )
          {
            WinHttpGetIEProxyConfigForCurrentUser(&pProxyConfig);
            lpszAutoConfigUrl = pProxyConfig.lpszAutoConfigUrl;
            if ( pProxyConfig.lpszAutoConfigUrl
              && CompareStringW(0x7Fu, 1u, *((PCNZWCH *)a3 + 1), -1, pProxyConfig.lpszAutoConfigUrl, -1) == 2 )
            {
              v10 = TokenInformation;
            }
            else
            {
              if ( (xmmword_180107A60 & 0x20) != 0 )
                WPP_SF_SS(
                  1029,
                  145,
                  (unsigned int)WPP_641a94d440413893505b2c7b2413b0bb_Traceguids,
                  *((_QWORD *)a3 + 1),
                  (__int64)lpszAutoConfigUrl);
              v10 = 0;
              TokenInformation = 0;
            }
          }
          if ( v10 )
            *a5 = 1;
        }
        if ( (xmmword_180107A60 & 0x20) != 0 )
          WPP_SF_d(1029, 146, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)*a5, ReturnLength);
      }
      else
      {
        LastError = GetLastError();
        v7 = LastError;
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
        if ( v7 >= 0 )
          v7 = -2147418113;
      }
      RpcRevertToSelf();
    }
  }
  else
  {
    v7 = -2147024809;
  }
  if ( pProxyConfig.lpszProxy )
  {
    GlobalFree(pProxyConfig.lpszProxy);
    pProxyConfig.lpszProxy = 0;
  }
  if ( pProxyConfig.lpszProxyBypass )
  {
    GlobalFree(pProxyConfig.lpszProxyBypass);
    pProxyConfig.lpszProxyBypass = 0;
  }
  if ( pProxyConfig.lpszAutoConfigUrl )
  {
    GlobalFree(pProxyConfig.lpszAutoConfigUrl);
    pProxyConfig.lpszAutoConfigUrl = 0;
  }
  if ( (xmmword_180107A60 & 0x20) != 0 )
    WPP_SF_d(1029, 147, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids, (unsigned int)v7, ReturnLength);
  CWxString::_Release((CWxString *)v14);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18006a4d8  push    rbp
0x18006a4da  push    rbx
0x18006a4db  push    rsi
0x18006a4dc  push    rdi
0x18006a4dd  push    r13
0x18006a4df  push    r14
0x18006a4e1  lea     rbp, [rsp-27h]
0x18006a4e6  sub     rsp, 98h
0x18006a4ed  mov     rax, cs:__security_cookie
0x18006a4f4  xor     rax, rsp
0x18006a4f7  mov     [rbp+4Fh+var_40], rax
0x18006a4fb  mov     rsi, [rbp+4Fh+arg_20]
0x18006a4ff  xorps   xmm0, xmm0
0x18006a502  mov     rax, r9
0x18006a505  mov     [rbp+4Fh+var_7C], 0
0x18006a50c  mov     r9, rcx
0x18006a50f  mov     [rbp+4Fh+TokenInformationLength], 4
0x18006a516  lea     rcx, qword_1800E7D10
0x18006a51d  mov     [rbp+4Fh+TokenInformation], 0
0x18006a524  mov     [rbp+4Fh+var_78], rcx
0x18006a528  mov     r14, r8
0x18006a52b  mov     rbx, rdx
0x18006a52e  mov     [rbp+4Fh+var_70], 0
0x18006a536  movups  xmmword ptr [rbp+4Fh+pProxyConfig.fAutoDetect], xmm0
0x18006a53a  movups  xmmword ptr [rbp+4Fh+pProxyConfig.lpszProxy], xmm0
0x18006a53e  test    byte ptr cs:xmmword_180107A60, 20h
0x18006a545  mov     r13d, 405h
0x18006a54b  jz      short loc_18006A570
0x18006a54d  mov     [rsp+0C0h+var_90], rax
0x18006a552  mov     edx, 8Fh
0x18006a557  mov     qword ptr [rsp+0C0h+cchCount2], r8
0x18006a55c  mov     ecx, r13d
0x18006a55f  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18006a566  mov     [rsp+0C0h+ReturnLength], rbx
0x18006a56b  call    WPP_SF_qqqq
0x18006a570  test    rsi, rsi
0x18006a573  jnz     short loc_18006A586
0x18006a575  mov     ebx, 80070057h
0x18006a57a  mov     [rbp+4Fh+var_7C], 10FCh
0x18006a581  jmp     loc_18006A6CA
0x18006a586  mov     rcx, rbx; BindingHandle
0x18006a589  mov     dword ptr [rsi], 0
0x18006a58f  call    cs:__imp_RpcImpersonateClient
0x18006a595  mov     ebx, eax
0x18006a597  mov     edi, 80070000h
0x18006a59c  test    eax, eax
0x18006a59e  jle     short loc_18006A5A5
0x18006a5a0  movzx   ebx, ax
0x18006a5a3  or      ebx, edi
0x18006a5a5  test    ebx, ebx
0x18006a5a7  jns     short loc_18006A5B5
0x18006a5a9  mov     [rbp+4Fh+var_7C], 1104h
0x18006a5b0  jmp     loc_18006A6CA
0x18006a5b5  test    byte ptr cs:xmmword_180107A60, 20h
0x18006a5bc  mov     rbx, 0FFFFFFFFFFFFFFFBh
0x18006a5c3  jz      short loc_18006A5DC
0x18006a5c5  mov     edx, 90h
0x18006a5ca  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18006a5d1  mov     ecx, r13d
0x18006a5d4  mov     r9, rbx
0x18006a5d7  call    WPP_SF_q
0x18006a5dc  mov     r9d, [rbp+4Fh+TokenInformationLength]; TokenInformationLength
0x18006a5e0  lea     rax, [rbp+4Fh+TokenInformationLength]
0x18006a5e4  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x18006a5e8  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x18006a5ed  mov     edx, 1Dh; TokenInformationClass
0x18006a5f2  mov     rcx, rbx; TokenHandle
0x18006a5f5  call    cs:__imp_GetTokenInformation
0x18006a5fb  test    eax, eax
0x18006a5fd  jnz     short loc_18006A626
0x18006a5ff  call    cs:__imp_GetLastError
0x18006a605  mov     ebx, eax
0x18006a607  test    eax, eax
0x18006a609  jle     short loc_18006A610
0x18006a60b  movzx   ebx, ax
0x18006a60e  or      ebx, edi
0x18006a610  test    ebx, ebx
0x18006a612  mov     [rbp+4Fh+var_7C], 1112h
0x18006a619  mov     eax, 8000FFFFh
0x18006a61e  cmovns  ebx, eax
0x18006a621  jmp     loc_18006A6C4
0x18006a626  mov     eax, [rbp+4Fh+TokenInformation]
0x18006a629  xor     ebx, ebx
0x18006a62b  test    eax, eax
0x18006a62d  jz      short loc_18006A6A4
0x18006a62f  cmp     [r14+8], rbx
0x18006a633  jz      short loc_18006A69A
0x18006a635  lea     rcx, [rbp+4Fh+pProxyConfig]; pProxyConfig
0x18006a639  call    WinHttpGetIEProxyConfigForCurrentUser
0x18006a63e  mov     rdi, [rbp+4Fh+pProxyConfig.lpszAutoConfigUrl]
0x18006a642  test    rdi, rdi
0x18006a645  jz      short loc_18006A66F
0x18006a647  mov     r8, [r14+8]; lpString1
0x18006a64b  lea     edx, [rbx+1]; dwCmpFlags
0x18006a64e  or      r9d, 0FFFFFFFFh; cchCount1
0x18006a652  lea     ecx, [rbx+7Fh]; Locale
0x18006a655  mov     [rsp+0C0h+cchCount2], r9d; cchCount2
0x18006a65a  mov     [rsp+0C0h+ReturnLength], rdi; lpString2
0x18006a65f  call    cs:__imp_CompareStringW
0x18006a665  cmp     eax, 2
0x18006a668  jnz     short loc_18006A66F
0x18006a66a  mov     eax, [rbp+4Fh+TokenInformation]
0x18006a66d  jmp     short loc_18006A69A
0x18006a66f  test    byte ptr cs:xmmword_180107A60, 20h
0x18006a676  jz      short loc_18006A695
0x18006a678  mov     r9, [r14+8]
0x18006a67c  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18006a683  mov     edx, 91h
0x18006a688  mov     [rsp+0C0h+ReturnLength], rdi
0x18006a68d  mov     ecx, r13d
0x18006a690  call    WPP_SF_SS
0x18006a695  xor     eax, eax
0x18006a697  mov     [rbp+4Fh+TokenInformation], eax
0x18006a69a  test    eax, eax
0x18006a69c  jz      short loc_18006A6A4
0x18006a69e  mov     dword ptr [rsi], 1
0x18006a6a4  test    byte ptr cs:xmmword_180107A60, 20h
0x18006a6ab  jz      short loc_18006A6C4
0x18006a6ad  mov     r9d, [rsi]
0x18006a6b0  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18006a6b7  mov     edx, 92h
0x18006a6bc  mov     ecx, r13d
0x18006a6bf  call    WPP_SF_d
0x18006a6c4  call    cs:__imp_RpcRevertToSelf
0x18006a6ca  mov     rcx, [rbp+4Fh+pProxyConfig.lpszProxy]; hMem
0x18006a6ce  test    rcx, rcx
0x18006a6d1  jz      short loc_18006A6E1
0x18006a6d3  call    cs:__imp_GlobalFree
0x18006a6d9  mov     [rbp+4Fh+pProxyConfig.lpszProxy], 0
0x18006a6e1  mov     rcx, [rbp+4Fh+pProxyConfig.lpszProxyBypass]; hMem
0x18006a6e5  test    rcx, rcx
0x18006a6e8  jz      short loc_18006A6F8
0x18006a6ea  call    cs:__imp_GlobalFree
0x18006a6f0  mov     [rbp+4Fh+pProxyConfig.lpszProxyBypass], 0
0x18006a6f8  mov     rcx, [rbp+4Fh+pProxyConfig.lpszAutoConfigUrl]; hMem
0x18006a6fc  test    rcx, rcx
0x18006a6ff  jz      short loc_18006A70F
0x18006a701  call    cs:__imp_GlobalFree
0x18006a707  mov     [rbp+4Fh+pProxyConfig.lpszAutoConfigUrl], 0
0x18006a70f  test    byte ptr cs:xmmword_180107A60, 20h
0x18006a716  jz      short loc_18006A72F
0x18006a718  mov     edx, 93h
0x18006a71d  lea     r8, WPP_641a94d440413893505b2c7b2413b0bb_Traceguids
0x18006a724  mov     ecx, r13d
0x18006a727  mov     r9d, ebx
0x18006a72a  call    WPP_SF_d
0x18006a72f  lea     rcx, [rbp+4Fh+var_78]; this
0x18006a733  call    ?_Release@CWxString@@AEAAXXZ; CWxString::_Release(void)
0x18006a738  mov     eax, ebx
0x18006a73a  mov     rcx, [rbp+4Fh+var_40]
0x18006a73e  xor     rcx, rsp; StackCookie
0x18006a741  call    __security_check_cookie
0x18006a746  add     rsp, 98h
0x18006a74d  pop     r14
0x18006a74f  pop     r13
0x18006a751  pop     rdi
0x18006a752  pop     rsi
0x18006a753  pop     rbx
0x18006a754  pop     rbp
0x18006a755  retn
```
