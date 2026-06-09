# ScGetClientSid(_TOKEN_USER * *)

- ea: `0x140081b6c`
- end: `0x140081db2`
- name: `?ScGetClientSid@@YAKPEAPEAU_TOKEN_USER@@@Z`
- size: `582`
- prototype: `unsigned int __fastcall(struct _TOKEN_USER **)`
- caller_count: `6`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x140008548`
- `0x14001e800`
- `0x14002ab00`
- `0x140035f80`
- `0x1400421b4`
- `0x1400685a4`

## callees

- `0x140004c58`
- `0x140013b0c`
- `0x14001f99c`
- `0x14004401c`
- `0x140081b6c`

## import_xrefs

- `RPCRT4!RpcImpersonateClient` at `0x140081b9b`
- `RPCRT4!RpcImpersonateClient` at `0x140081b9b`
- `RPCRT4!RpcRevertToSelf` at `0x140081d51`
- `RPCRT4!RpcRevertToSelf` at `0x140081d51`
- `ntdll!NtOpenThreadToken` at `0x140081bc9`
- `ntdll!NtOpenThreadToken` at `0x140081bc9`
- `ntdll!NtClose` at `0x140081d4b`
- `ntdll!NtClose` at `0x140081d4b`
- `ntdll!RtlNtStatusToDosError` at `0x140081bd3`
- `ntdll!RtlNtStatusToDosError` at `0x140081c70`
- `ntdll!RtlNtStatusToDosError` at `0x140081cf0`
- `ntdll!RtlNtStatusToDosError` at `0x140081bd3`
- `ntdll!RtlNtStatusToDosError` at `0x140081c70`
- `ntdll!RtlNtStatusToDosError` at `0x140081cf0`
- `ntdll!RtlFreeHeap` at `0x140081d34`
- `ntdll!RtlFreeHeap` at `0x140081d34`
- `ntdll!NtQueryInformationToken` at `0x140081c39`
- `ntdll!NtQueryInformationToken` at `0x140081ce6`
- `ntdll!NtQueryInformationToken` at `0x140081c39`
- `ntdll!NtQueryInformationToken` at `0x140081ce6`
- `ntdll!RtlAllocateHeap` at `0x140081c94`
- `ntdll!RtlAllocateHeap` at `0x140081c94`

## pseudocode

```c
__int64 __fastcall ScGetClientSid(PVOID *a1)
{
  RPC_STATUS v2; // eax
  unsigned int v3; // ebx
  int v5; // ebx
  ULONG v6; // esi
  unsigned int v7; // eax
  NTSTATUS v8; // ebx
  struct _TOKEN_USER *Heap; // rax
  int v10; // ebx
  unsigned int v11; // eax
  ULONG TokenInformationLength; // [rsp+50h] [rbp+8h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp+10h] BYREF

  *a1 = 0;
  TokenHandle = 0;
  TokenInformationLength = 0;
  v2 = RpcImpersonateClient(0);
  v3 = v2;
  if ( v2 )
  {
    ScLogImpersonateFailureEvent(v2);
    return v3;
  }
  v5 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 1u, &TokenHandle);
  v6 = RtlNtStatusToDosError(v5);
  if ( v5 >= 0 )
  {
    v7 = NtQueryInformationToken(TokenHandle, TokenUser, *a1, 0, &TokenInformationLength);
    v8 = v7;
    if ( v7 == -1073741789 )
    {
      Heap = (struct _TOKEN_USER *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, TokenInformationLength);
      *a1 = Heap;
      if ( Heap )
      {
        v10 = NtQueryInformationToken(TokenHandle, TokenUser, Heap, TokenInformationLength, &TokenInformationLength);
        v6 = RtlNtStatusToDosError(v10);
        if ( v10 < 0 )
        {
          if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
            && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
          {
            WPP_SF_d(
              WPP_GLOBAL_Control->StubInfo,
              55,
              WPP_8f086be6c6f937952c5e847c48275da5_Traceguids,
              (unsigned int)v10);
          }
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, *a1);
          *a1 = 0;
        }
      }
      else
      {
        if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
          && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        {
          WPP_SF_(WPP_GLOBAL_Control->StubInfo, 54, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids);
        }
        v6 = 8;
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
        WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 53, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v7);
      v6 = RtlNtStatusToDosError(v8);
    }
  }
  else if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control
         && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 52, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, (unsigned int)v5);
  }
  if ( TokenHandle )
    NtClose(TokenHandle);
  v11 = RpcRevertToSelf();
  v3 = v11;
  if ( v11 )
  {
    if ( WPP_GLOBAL_Control != (PRPC_ASYNC_STATE)&WPP_GLOBAL_Control && (BYTE4(WPP_GLOBAL_Control->UserInfo) & 1) != 0 )
      WPP_SF_d(WPP_GLOBAL_Control->StubInfo, 56, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids, v11);
    ScLogEvent(5u, L"RpcRevertToSelf", v3);
    return v3;
  }
  return v6;
}

```

## disassembly

```asm
0x140081b6c  mov     rax, rsp
0x140081b6f  mov     [rax+18h], rbx
0x140081b73  mov     [rax+20h], rsi
0x140081b77  push    rdi
0x140081b78  push    r12
0x140081b7a  push    r15
0x140081b7c  sub     rsp, 30h
0x140081b80  mov     rdi, rcx
0x140081b83  mov     qword ptr [rcx], 0
0x140081b8a  xor     ecx, ecx; BindingHandle
0x140081b8c  mov     qword ptr [rax+10h], 0
0x140081b94  mov     dword ptr [rax+8], 0
0x140081b9b  call    cs:__imp_RpcImpersonateClient
0x140081ba1  mov     ebx, eax
0x140081ba3  test    eax, eax
0x140081ba5  jz      short loc_140081BB5
0x140081ba7  mov     ecx, eax; int
0x140081ba9  call    ?ScLogImpersonateFailureEvent@@YAXJ@Z; ScLogImpersonateFailureEvent(long)
0x140081bae  mov     eax, ebx
0x140081bb0  jmp     loc_140081D9E
0x140081bb5  lea     r9, [rsp+48h+TokenHandle]; TokenHandle
0x140081bba  mov     r8b, 1; OpenAsSelf
0x140081bbd  mov     edx, 8; DesiredAccess
0x140081bc2  mov     rcx, 0FFFFFFFFFFFFFFFEh; ThreadHandle
0x140081bc9  call    cs:__imp_NtOpenThreadToken
0x140081bcf  mov     ecx, eax; Status
0x140081bd1  mov     ebx, eax
0x140081bd3  call    cs:__imp_RtlNtStatusToDosError
0x140081bd9  lea     r15, WPP_GLOBAL_Control
0x140081be0  mov     esi, eax
0x140081be2  lea     r12, WPP_8f086be6c6f937952c5e847c48275da5_Traceguids
0x140081be9  test    ebx, ebx
0x140081beb  jns     short loc_140081C20
0x140081bed  mov     rcx, cs:WPP_GLOBAL_Control
0x140081bf4  cmp     rcx, r15
0x140081bf7  jz      loc_140081D41
0x140081bfd  test    byte ptr [rcx+1Ch], 1
0x140081c01  jz      loc_140081D41
0x140081c07  mov     rcx, [rcx+10h]
0x140081c0b  mov     edx, 34h ; '4'
0x140081c10  mov     r9d, ebx
0x140081c13  mov     r8, r12
0x140081c16  call    WPP_SF_d
0x140081c1b  jmp     loc_140081D41
0x140081c20  mov     r8, [rdi]; TokenInformation
0x140081c23  lea     rax, [rsp+48h+TokenInformationLength]
0x140081c28  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140081c2d  xor     r9d, r9d; TokenInformationLength
0x140081c30  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x140081c35  lea     edx, [r9+1]; TokenInformationClass
0x140081c39  call    cs:__imp_NtQueryInformationToken
0x140081c3f  mov     ebx, eax
0x140081c41  cmp     eax, 0C0000023h
0x140081c46  jz      short loc_140081C7D
0x140081c48  mov     rcx, cs:WPP_GLOBAL_Control
0x140081c4f  cmp     rcx, r15
0x140081c52  jz      short loc_140081C6E
0x140081c54  test    byte ptr [rcx+1Ch], 1
0x140081c58  jz      short loc_140081C6E
0x140081c5a  mov     rcx, [rcx+10h]
0x140081c5e  mov     edx, 35h ; '5'
0x140081c63  mov     r9d, eax
0x140081c66  mov     r8, r12
0x140081c69  call    WPP_SF_d
0x140081c6e  mov     ecx, ebx; Status
0x140081c70  call    cs:__imp_RtlNtStatusToDosError
0x140081c76  mov     esi, eax
0x140081c78  jmp     loc_140081D41
0x140081c7d  mov     rcx, gs:60h
0x140081c86  mov     edx, 8; Flags
0x140081c8b  mov     r8d, [rsp+48h+TokenInformationLength]; Size
0x140081c90  mov     rcx, [rcx+30h]; HeapHandle
0x140081c94  call    cs:__imp_RtlAllocateHeap
0x140081c9a  mov     [rdi], rax
0x140081c9d  test    rax, rax
0x140081ca0  jnz     short loc_140081CCA
0x140081ca2  mov     rcx, cs:WPP_GLOBAL_Control
0x140081ca9  cmp     rcx, r15
0x140081cac  jz      short loc_140081CC3
0x140081cae  test    byte ptr [rcx+1Ch], 1
0x140081cb2  jz      short loc_140081CC3
0x140081cb4  mov     rcx, [rcx+10h]
0x140081cb8  lea     edx, [rax+36h]
0x140081cbb  mov     r8, r12
0x140081cbe  call    WPP_SF_
0x140081cc3  mov     esi, 8
0x140081cc8  jmp     short loc_140081D41
0x140081cca  mov     r9d, [rsp+48h+TokenInformationLength]; TokenInformationLength
0x140081ccf  lea     rcx, [rsp+48h+TokenInformationLength]
0x140081cd4  mov     [rsp+48h+ReturnLength], rcx; ReturnLength
0x140081cd9  mov     r8, rax; TokenInformation
0x140081cdc  mov     rcx, [rsp+48h+TokenHandle]; TokenHandle
0x140081ce1  mov     edx, 1; TokenInformationClass
0x140081ce6  call    cs:__imp_NtQueryInformationToken
0x140081cec  mov     ecx, eax; Status
0x140081cee  mov     ebx, eax
0x140081cf0  call    cs:__imp_RtlNtStatusToDosError
0x140081cf6  mov     esi, eax
0x140081cf8  test    ebx, ebx
0x140081cfa  jns     short loc_140081D41
0x140081cfc  mov     rcx, cs:WPP_GLOBAL_Control
0x140081d03  cmp     rcx, r15
0x140081d06  jz      short loc_140081D22
0x140081d08  test    byte ptr [rcx+1Ch], 1
0x140081d0c  jz      short loc_140081D22
0x140081d0e  mov     rcx, [rcx+10h]
0x140081d12  mov     edx, 37h ; '7'
0x140081d17  mov     r9d, ebx
0x140081d1a  mov     r8, r12
0x140081d1d  call    WPP_SF_d
0x140081d22  mov     rcx, gs:60h
0x140081d2b  xor     edx, edx; Flags
0x140081d2d  mov     r8, [rdi]; P
0x140081d30  mov     rcx, [rcx+30h]; HeapHandle
0x140081d34  call    cs:__imp_RtlFreeHeap
0x140081d3a  mov     qword ptr [rdi], 0
0x140081d41  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x140081d46  test    rcx, rcx
0x140081d49  jz      short loc_140081D51
0x140081d4b  call    cs:__imp_NtClose
0x140081d51  call    cs:__imp_RpcRevertToSelf
0x140081d57  mov     ebx, eax
0x140081d59  test    eax, eax
0x140081d5b  jz      short loc_140081D9C
0x140081d5d  mov     rcx, cs:WPP_GLOBAL_Control
0x140081d64  cmp     rcx, r15
0x140081d67  jz      short loc_140081D83
0x140081d69  test    byte ptr [rcx+1Ch], 1
0x140081d6d  jz      short loc_140081D83
0x140081d6f  mov     rcx, [rcx+10h]
0x140081d73  mov     edx, 38h ; '8'
0x140081d78  mov     r9d, eax
0x140081d7b  mov     r8, r12
0x140081d7e  call    WPP_SF_d
0x140081d83  mov     r8d, ebx
0x140081d86  lea     rdx, aRpcreverttosel; "RpcRevertToSelf"
0x140081d8d  mov     ecx, 5; unsigned int
0x140081d92  call    ?ScLogEvent@@YAXKZZ; ScLogEvent(ulong,...)
0x140081d97  jmp     loc_140081BAE
0x140081d9c  mov     eax, esi
0x140081d9e  mov     rbx, [rsp+48h+arg_10]
0x140081da3  mov     rsi, [rsp+48h+arg_18]
0x140081da8  add     rsp, 30h
0x140081dac  pop     r15
0x140081dae  pop     r12
0x140081db0  pop     rdi
0x140081db1  retn
```
