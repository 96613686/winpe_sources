# ScStatusAccessCheck(CServiceRecord *)

- ea: `0x1400089c8`
- end: `0x140008b89`
- name: `?ScStatusAccessCheck@@YAKPEAVCServiceRecord@@@Z`
- size: `449`
- prototype: `unsigned int __fastcall(struct CServiceRecord *)`
- caller_count: `5`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x140007d80`
- `0x1400135b0`
- `0x140017178`
- `0x140020a30`
- `0x140029340`

## callees

- `0x140004c58`
- `0x1400089c8`
- `0x140013b0c`
- `0x14004401c`
- `0x1400575b0`
- `0x140094020`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b0f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140008b0f`
- `RPCRT4!RpcImpersonateClient` at `0x140008a11`
- `RPCRT4!RpcImpersonateClient` at `0x140008a11`
- `RPCRT4!RpcRevertToSelf` at `0x140008ab7`
- `RPCRT4!RpcRevertToSelf` at `0x140008ab7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140008a51`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x140008a51`

## pseudocode

```c
__int64 __fastcall ScStatusAccessCheck(struct CServiceRecord *a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // edi
  __int64 v4; // rax
  __int64 v5; // rax
  unsigned int v6; // eax
  unsigned int v7; // ebx
  DWORD LastError; // eax
  DWORD ReturnLength; // [rsp+30h] [rbp-19h] BYREF
  __int128 TokenInformation; // [rsp+38h] [rbp-11h] BYREF
  __int128 v12; // [rsp+48h] [rbp-1h]
  __int128 v13; // [rsp+58h] [rbp+Fh]
  __int64 v14; // [rsp+68h] [rbp+1Fh]

  ReturnLength = 0;
  if ( a1 && !(*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)a1 + 160LL))(a1) )
    return 1062;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 )
  {
    ScLogImpersonateFailureEvent(v2);
    return v3;
  }
  else
  {
    v14 = 0;
    TokenInformation = 0;
    v12 = 0;
    v13 = 0;
    if ( GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenStatistics, &TokenInformation, 0x38u, &ReturnLength) )
    {
      if ( (DWORD2(v12) != 2 || SHIDWORD(v12) >= 2)
        && (*((_QWORD *)&TokenInformation + 1) == 999
         || a1
         && (v4 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)a1 + 160LL))(a1),
             DWORD2(TokenInformation) == *(_DWORD *)(v4 + 72))
         && (v5 = (*(__int64 (__fastcall **)(struct CServiceRecord *))(*(_QWORD *)a1 + 160LL))(a1),
             HIDWORD(TokenInformation) == *(_DWORD *)(v5 + 76))) )
      {
        ReturnLength = 0;
      }
      else
      {
        ReturnLength = 5;
      }
    }
    else
    {
      LastError = GetLastError();
      ReturnLength = LastError;
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 42, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, LastError);
    }
    v6 = RpcRevertToSelf();
    v7 = v6;
    if ( v6 )
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 43, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v6);
      ScLogEvent(5u, L"RpcRevertToSelf", v7);
      return v7;
    }
    else
    {
      return ReturnLength;
    }
  }
}

```

## disassembly

```asm
0x1400089c8  push    rbp
0x1400089ca  push    rbx
0x1400089cb  push    rdi
0x1400089cc  push    r14
0x1400089ce  lea     rbp, [rsp-3Fh]
0x1400089d3  sub     rsp, 88h
0x1400089da  mov     rax, cs:__security_cookie
0x1400089e1  xor     rax, rsp
0x1400089e4  mov     [rbp+57h+var_30], rax
0x1400089e8  mov     [rbp+57h+var_70], 0
0x1400089ef  mov     rbx, rcx
0x1400089f2  test    rcx, rcx
0x1400089f5  jz      short loc_140008A0F
0x1400089f7  mov     rax, [rcx]
0x1400089fa  mov     rax, [rax+0A0h]
0x140008a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a06  test    rax, rax
0x140008a09  jz      loc_140008AE3
0x140008a0f  xor     ecx, ecx; BindingHandle
0x140008a11  call    cs:__imp_RpcImpersonateClient
0x140008a17  mov     edi, eax
0x140008a19  test    eax, eax
0x140008a1b  jnz     loc_140008B04
0x140008a21  xorps   xmm0, xmm0
0x140008a24  lea     r9d, [rdi+38h]; TokenInformationLength
0x140008a28  xor     eax, eax
0x140008a2a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x140008a2e  mov     [rbp+57h+var_38], rax
0x140008a32  lea     edx, [rdi+0Ah]; TokenInformationClass
0x140008a35  lea     rax, [rbp+57h+var_70]
0x140008a39  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x140008a40  mov     [rsp+0A0h+ReturnLength], rax; ReturnLength
0x140008a45  movups  [rbp+57h+TokenInformation], xmm0
0x140008a49  movups  [rbp+57h+var_58], xmm0
0x140008a4d  movups  [rbp+57h+var_48], xmm0
0x140008a51  call    cs:__imp_GetTokenInformation
0x140008a57  lea     r14, WPP_GLOBAL_Control
0x140008a5e  mov     edi, 5
0x140008a63  test    eax, eax
0x140008a65  jz      loc_140008B0F
0x140008a6b  cmp     dword ptr [rbp+57h+var_58+8], 2
0x140008a6f  jz      short loc_140008AEA
0x140008a71  cmp     dword ptr [rbp+57h+TokenInformation+0Ch], 0
0x140008a75  jz      short loc_140008AF5
0x140008a77  test    rbx, rbx
0x140008a7a  jz      short loc_140008AF0
0x140008a7c  mov     rax, [rbx]
0x140008a7f  mov     rcx, rbx
0x140008a82  mov     rax, [rax+0A0h]
0x140008a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008a8e  mov     edx, [rax+48h]
0x140008a91  cmp     dword ptr [rbp+57h+TokenInformation+8], edx
0x140008a94  jnz     short loc_140008AF0
0x140008a96  mov     rax, [rbx]
0x140008a99  mov     rcx, rbx
0x140008a9c  mov     rax, [rax+0A0h]
0x140008aa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008aa8  mov     ecx, [rax+4Ch]
0x140008aab  cmp     dword ptr [rbp+57h+TokenInformation+0Ch], ecx
0x140008aae  jnz     short loc_140008AF0
0x140008ab0  mov     [rbp+57h+var_70], 0
0x140008ab7  call    cs:__imp_RpcRevertToSelf
0x140008abd  mov     ebx, eax
0x140008abf  test    eax, eax
0x140008ac1  jnz     loc_140008B47
0x140008ac7  mov     eax, [rbp+57h+var_70]
0x140008aca  mov     rcx, [rbp+57h+var_30]
0x140008ace  xor     rcx, rsp; StackCookie
0x140008ad1  call    __security_check_cookie
0x140008ad6  add     rsp, 88h
0x140008add  pop     r14
0x140008adf  pop     rdi
0x140008ae0  pop     rbx
0x140008ae1  pop     rbp
0x140008ae2  retn
0x140008ae3  mov     eax, 426h
0x140008ae8  jmp     short loc_140008ACA
0x140008aea  cmp     dword ptr [rbp+57h+var_58+0Ch], 2
0x140008aee  jge     short loc_140008A71
0x140008af0  mov     [rbp+57h+var_70], edi
0x140008af3  jmp     short loc_140008AB7
0x140008af5  cmp     dword ptr [rbp+57h+TokenInformation+8], 3E7h
0x140008afc  jnz     loc_140008A77
0x140008b02  jmp     short loc_140008AB0
0x140008b04  mov     ecx, edi; int
0x140008b06  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x140008b0b  mov     eax, edi
0x140008b0d  jmp     short loc_140008ACA
0x140008b0f  call    cs:__imp_GetLastError
0x140008b15  mov     [rbp+57h+var_70], eax
0x140008b18  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b1f  cmp     rcx, r14
0x140008b22  jz      short loc_140008AB7
0x140008b24  test    byte ptr [rcx+1Ch], 1
0x140008b28  jz      short loc_140008AB7
0x140008b2a  mov     rcx, [rcx+10h]
0x140008b2e  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140008b35  mov     edx, 2Ah ; '*'
0x140008b3a  mov     r9d, eax
0x140008b3d  call    WPP_SF_d
0x140008b42  jmp     loc_140008AB7
0x140008b47  mov     rcx, cs:WPP_GLOBAL_Control
0x140008b4e  cmp     rcx, r14
0x140008b51  jz      short loc_140008B71
0x140008b53  test    byte ptr [rcx+1Ch], 1
0x140008b57  jz      short loc_140008B71
0x140008b59  mov     rcx, [rcx+10h]
0x140008b5d  lea     r8, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140008b64  mov     edx, 2Bh ; '+'
0x140008b69  mov     r9d, ebx
0x140008b6c  call    WPP_SF_d
0x140008b71  mov     r8d, ebx
0x140008b74  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140008b7b  mov     ecx, edi; unsigned int
0x140008b7d  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140008b82  mov     eax, ebx
0x140008b84  jmp     loc_140008ACA
```
