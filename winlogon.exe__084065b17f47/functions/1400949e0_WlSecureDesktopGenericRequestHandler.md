# WlSecureDesktopGenericRequestHandler

- ea: `0x1400949e0`
- end: `0x140094b8b`
- name: `WlSecureDesktopGenericRequestHandler`
- size: `427`
- prototype: `__int64 __usercall@<rax>(PRPC_ASYNC_STATE pAsync@<rcx>, RPC_BINDING_HANDLE Binding@<rdx>, __int64)`
- caller_count: `4`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140094ba0`
- `0x140094c50`
- `0x140094cc0`
- `0x140094d30`

## callees

- `0x140053720`
- `0x1400930b8`
- `0x140094894`
- `0x1400949e0`

## import_xrefs

- `RPCRT4!RpcRevertToSelf` at `0x140094b54`
- `RPCRT4!RpcRevertToSelf` at `0x140094b54`
- `RPCRT4!RpcImpersonateClient` at `0x140094a2c`
- `RPCRT4!RpcImpersonateClient` at `0x140094a2c`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140094a47`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x140094a47`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140094b67`
- `RPCRT4!RpcAsyncCompleteCall` at `0x140094b67`
- `ntdll!NtOpenThreadToken` at `0x140094aeb`
- `ntdll!NtOpenThreadToken` at `0x140094aeb`
- `ntdll!NtQueryInformationToken` at `0x140094b0f`
- `ntdll!NtQueryInformationToken` at `0x140094b0f`
- `ntdll!RtlNtStatusToDosError` at `0x140094b38`
- `ntdll!RtlNtStatusToDosError` at `0x140094b38`
- `ntdll!NtClose` at `0x140094b4a`
- `ntdll!NtClose` at `0x140094b4a`

## pseudocode

```c
RPC_STATUS __fastcall WlSecureDesktopGenericRequestHandler(
        PRPC_ASYNC_STATE pAsync,
        RPC_BINDING_HANDLE Binding,
        __int64 a3,
        unsigned int a4,
        __int64 a5)
{
  int v6; // esi
  RPC_STATUS result; // eax
  int v11; // ecx
  int v12; // ecx
  _QWORD *v13; // rdi
  RPC_STATUS Reply; // [rsp+30h] [rbp-41h] BYREF
  unsigned int Pid; // [rsp+34h] [rbp-3Dh] BYREF
  ULONG TokenInformationLength; // [rsp+38h] [rbp-39h] BYREF
  void *TokenHandle; // [rsp+40h] [rbp-31h] BYREF
  _OWORD TokenInformation[3]; // [rsp+48h] [rbp-29h] BYREF
  __int64 v19; // [rsp+78h] [rbp+7h]

  v6 = 0;
  TokenHandle = 0;
  Pid = 0;
  result = RpcImpersonateClient(Binding);
  Reply = result;
  if ( !result )
  {
    v6 = 1;
    result = I_RpcBindingInqLocalClientPID(Binding, &Pid);
    Reply = result;
    if ( !result )
    {
      v11 = *(_DWORD *)(a3 + 256);
      *(_DWORD *)(a3 + 260) = Pid;
      v12 = v11 - 2;
      if ( v12 )
      {
        if ( (unsigned int)(v12 - 1) <= 1 )
        {
          result = CompareClientSidToLoggedOnUserSid(0);
          if ( result < 0 )
          {
LABEL_14:
            result = RtlNtStatusToDosError(result);
            Reply = result;
            goto LABEL_15;
          }
        }
      }
      else if ( *(_DWORD *)(a3 + 240) >= 0x34u )
      {
        v13 = *(_QWORD **)(a3 + 232);
        if ( *v13 == (_QWORD)CREDUIWIN_STRUCTURE_TYPE_SSPIPFC
          && v13[1] == _mm_srli_si128((__m128i)CREDUIWIN_STRUCTURE_TYPE_SSPIPFC, 8).m128i_u64[0] )
        {
          TokenInformationLength = 56;
          v19 = 0;
          memset(TokenInformation, 0, sizeof(TokenInformation));
          result = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
          if ( result < 0 )
            goto LABEL_14;
          result = NtQueryInformationToken(
                     TokenHandle,
                     TokenStatistics,
                     TokenInformation,
                     TokenInformationLength,
                     &TokenInformationLength);
          if ( result < 0 )
            goto LABEL_14;
          *(_QWORD *)((char *)v13 + 20) = *((_QWORD *)&TokenInformation[0] + 1);
        }
      }
      result = WlSecureDesktopiGenericRequest(pAsync, a3, a4, a5);
      if ( result >= 0 )
        goto LABEL_15;
      goto LABEL_14;
    }
  }
LABEL_15:
  if ( TokenHandle )
    result = NtClose(TokenHandle);
  if ( v6 )
    result = RpcRevertToSelf();
  if ( Reply )
    return RpcAsyncCompleteCall(pAsync, &Reply);
  return result;
}

```

## disassembly

```asm
0x1400949e0  push    rbp
0x1400949e2  push    rbx
0x1400949e3  push    rsi
0x1400949e4  push    rdi
0x1400949e5  push    r12
0x1400949e7  push    r14
0x1400949e9  push    r15
0x1400949eb  lea     rbp, [rsp-1Fh]
0x1400949f0  sub     rsp, 90h
0x1400949f7  mov     rax, cs:__security_cookie
0x1400949fe  xor     rax, rsp
0x140094a01  mov     [rbp+4Fh+var_40], rax
0x140094a05  mov     r12, [rbp+4Fh+arg_20]
0x140094a09  mov     r14, rcx
0x140094a0c  xor     esi, esi
0x140094a0e  mov     [rbp+4Fh+Reply], 0
0x140094a15  mov     rcx, rdx; BindingHandle
0x140094a18  mov     [rbp+4Fh+TokenHandle], rsi
0x140094a1c  mov     r15d, r9d
0x140094a1f  mov     [rbp+4Fh+Pid], 0
0x140094a26  mov     rbx, r8
0x140094a29  mov     rdi, rdx
0x140094a2c  call    cs:__imp_RpcImpersonateClient
0x140094a32  mov     [rbp+4Fh+Reply], eax
0x140094a35  test    eax, eax
0x140094a37  jnz     loc_140094B41
0x140094a3d  lea     rdx, [rbp+4Fh+Pid]; Pid
0x140094a41  mov     rcx, rdi; Binding
0x140094a44  lea     esi, [rax+1]
0x140094a47  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x140094a4d  mov     [rbp+4Fh+Reply], eax
0x140094a50  test    eax, eax
0x140094a52  jnz     loc_140094B41
0x140094a58  mov     ecx, [rbx+100h]
0x140094a5e  mov     eax, [rbp+4Fh+Pid]
0x140094a61  mov     [rbx+104h], eax
0x140094a67  sub     ecx, 2
0x140094a6a  jz      short loc_140094A8C
0x140094a6c  sub     ecx, esi
0x140094a6e  jz      short loc_140094A78
0x140094a70  cmp     ecx, esi
0x140094a72  jnz     loc_140094B21
0x140094a78  xor     ecx, ecx
0x140094a7a  call    CompareClientSidToLoggedOnUserSid
0x140094a7f  test    eax, eax
0x140094a81  jns     loc_140094B21
0x140094a87  jmp     loc_140094B36
0x140094a8c  cmp     dword ptr [rbx+0F0h], 34h ; '4'
0x140094a93  jb      loc_140094B21
0x140094a99  movups  xmm0, cs:CREDUIWIN_STRUCTURE_TYPE_SSPIPFC
0x140094aa0  mov     rdi, [rbx+0E8h]
0x140094aa7  movq    rax, xmm0
0x140094aac  cmp     [rdi], rax
0x140094aaf  jnz     short loc_140094B21
0x140094ab1  psrldq  xmm0, 8
0x140094ab6  movq    rax, xmm0
0x140094abb  cmp     [rdi+8], rax
0x140094abf  jnz     short loc_140094B21
0x140094ac1  xor     eax, eax
0x140094ac3  mov     [rbp+4Fh+TokenInformationLength], 38h ; '8'
0x140094aca  xorps   xmm0, xmm0
0x140094acd  mov     [rbp+4Fh+var_48], rax
0x140094ad1  lea     r9, [rbp+4Fh+TokenHandle]; TokenHandle
0x140094ad5  mov     r8b, sil; OpenAsSelf
0x140094ad8  movups  [rbp+4Fh+TokenInformation], xmm0
0x140094adc  lea     edx, [rax+8]; DesiredAccess
0x140094adf  lea     rcx, [rax-2]; ThreadHandle
0x140094ae3  movups  [rbp+4Fh+var_68], xmm0
0x140094ae7  movups  [rbp+4Fh+var_58], xmm0
0x140094aeb  call    cs:__imp_NtOpenThreadToken
0x140094af1  test    eax, eax
0x140094af3  js      short loc_140094B36
0x140094af5  mov     r9d, [rbp+4Fh+TokenInformationLength]; TokenInformationLength
0x140094af9  lea     rax, [rbp+4Fh+TokenInformationLength]
0x140094afd  mov     rcx, [rbp+4Fh+TokenHandle]; TokenHandle
0x140094b01  lea     r8, [rbp+4Fh+TokenInformation]; TokenInformation
0x140094b05  mov     edx, 0Ah; TokenInformationClass
0x140094b0a  mov     [rsp+0C0h+ReturnLength], rax; ReturnLength
0x140094b0f  call    cs:__imp_NtQueryInformationToken
0x140094b15  test    eax, eax
0x140094b17  js      short loc_140094B36
0x140094b19  mov     rax, qword ptr [rbp+4Fh+TokenInformation+8]
0x140094b1d  mov     [rdi+14h], rax
0x140094b21  mov     r9, r12
0x140094b24  mov     r8d, r15d
0x140094b27  mov     rdx, rbx
0x140094b2a  mov     rcx, r14
0x140094b2d  call    WlSecureDesktopiGenericRequest
0x140094b32  test    eax, eax
0x140094b34  jns     short loc_140094B41
0x140094b36  mov     ecx, eax; Status
0x140094b38  call    cs:__imp_RtlNtStatusToDosError
0x140094b3e  mov     [rbp+4Fh+Reply], eax
0x140094b41  mov     rcx, [rbp+4Fh+TokenHandle]; Handle
0x140094b45  test    rcx, rcx
0x140094b48  jz      short loc_140094B50
0x140094b4a  call    cs:__imp_NtClose
0x140094b50  test    esi, esi
0x140094b52  jz      short loc_140094B5A
0x140094b54  call    cs:__imp_RpcRevertToSelf
0x140094b5a  cmp     [rbp+4Fh+Reply], 0
0x140094b5e  jz      short loc_140094B6D
0x140094b60  lea     rdx, [rbp+4Fh+Reply]; Reply
0x140094b64  mov     rcx, r14; pAsync
0x140094b67  call    cs:__imp_RpcAsyncCompleteCall
0x140094b6d  mov     rcx, [rbp+4Fh+var_40]
0x140094b71  xor     rcx, rsp; StackCookie
0x140094b74  call    __security_check_cookie
0x140094b79  add     rsp, 90h
0x140094b80  pop     r15
0x140094b82  pop     r14
0x140094b84  pop     r12
0x140094b86  pop     rdi
0x140094b87  pop     rsi
0x140094b88  pop     rbx
0x140094b89  pop     rbp
0x140094b8a  retn
```
