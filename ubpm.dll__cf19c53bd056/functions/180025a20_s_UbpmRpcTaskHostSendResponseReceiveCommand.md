# s_UbpmRpcTaskHostSendResponseReceiveCommand

- ea: `0x180025a20`
- end: `0x180025b86`
- name: `s_UbpmRpcTaskHostSendResponseReceiveCommand`
- size: `358`
- prototype: `__int64 __fastcall(struct _RPC_ASYNC_STATE *, __int64, _OWORD *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x180025a20`
- `0x180030cec`
- `0x18003c54c`

## import_xrefs

- `ntdll!RtlReleaseSRWLockShared` at `0x180025ab6`
- `ntdll!RtlReleaseSRWLockShared` at `0x180025ab6`
- `ntdll!RtlAcquireSRWLockShared` at `0x180025a44`
- `ntdll!RtlAcquireSRWLockShared` at `0x180025a44`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025aa9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180025aa9`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025b01`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180025b01`

## pseudocode

```c
__int64 __fastcall s_UbpmRpcTaskHostSendResponseReceiveCommand(
        struct _RPC_ASYNC_STATE *a1,
        __int64 a2,
        _OWORD *a3,
        __int64 a4)
{
  __int64 v8; // rdx
  __int64 v9; // r8
  char v10; // al
  int v12; // r8d
  _QWORD *v13; // rcx
  __int64 v14; // rdx
  signed __int32 v15[8]; // [rsp+0h] [rbp-68h] BYREF
  unsigned int Reply; // [rsp+70h] [rbp+8h] BYREF

  Reply = 0;
  RtlAcquireSRWLockShared(&g_TaskHostContextListLock);
  if ( *(_DWORD *)a2 != 1665679957 )
  {
    Reply = 5;
    goto LABEL_8;
  }
  v10 = *(_BYTE *)(a2 + 104);
  if ( (v10 & 4) != 0 )
  {
    v12 = 1067;
    Reply = 1067;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_8;
    v14 = 25;
LABEL_17:
    WPP_SF_dd(v13[2], v14, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids, *(unsigned int *)(a2 + 32), v12);
    goto LABEL_8;
  }
  if ( (v10 & 8) == 0 )
  {
    v12 = 1237;
    Reply = 1237;
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0 )
      goto LABEL_8;
    v14 = 26;
    goto LABEL_17;
  }
  *(_QWORD *)(a2 + 56) = a1;
  a1 = 0;
  *(_QWORD *)(a2 + 168) = a4;
  *(_OWORD *)(a2 + 112) = *a3;
  *(_OWORD *)(a2 + 128) = a3[1];
  _InterlockedOr(v15, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_Lqii(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v8,
      v9,
      *(unsigned int *)(a2 + 32),
      a2,
      *(_QWORD *)(a2 + 96),
      *(_QWORD *)(a2 + 120));
  SetEvent(*(HANDLE *)(a2 + 48));
LABEL_8:
  RtlReleaseSRWLockShared(&g_TaskHostContextListLock);
  if ( a1 )
    RpcAsyncCompleteCall(a1, &Reply);
  return Reply;
}

```

## disassembly

```asm
0x180025a20  push    rbx
0x180025a22  push    rbp
0x180025a23  push    rsi
0x180025a24  push    rdi
0x180025a25  sub     rsp, 48h
0x180025a29  mov     rdi, rcx
0x180025a2c  mov     [rsp+68h+Reply], 0
0x180025a34  lea     rcx, g_TaskHostContextListLock
0x180025a3b  mov     rbp, r9
0x180025a3e  mov     rsi, r8
0x180025a41  mov     rbx, rdx
0x180025a44  call    cs:__imp_RtlAcquireSRWLockShared
0x180025a4a  cmp     dword ptr [rbx], 63484255h
0x180025a50  jnz     loc_180025B50
0x180025a56  mov     al, [rbx+68h]
0x180025a59  test    al, 4
0x180025a5b  jnz     short loc_180025ACE
0x180025a5d  test    al, 8
0x180025a5f  jz      loc_180025B09
0x180025a65  mov     [rbx+38h], rdi
0x180025a69  xor     edi, edi
0x180025a6b  mov     [rbx+0A8h], rbp
0x180025a72  movups  xmm0, xmmword ptr [rsi]
0x180025a75  movups  xmmword ptr [rbx+70h], xmm0
0x180025a79  movups  xmm1, xmmword ptr [rsi+10h]
0x180025a7d  movups  xmmword ptr [rbx+80h], xmm1
0x180025a84  lock or [rsp+68h+var_68], edi
0x180025a88  mov     rcx, cs:WPP_GLOBAL_Control
0x180025a8f  lea     rax, WPP_GLOBAL_Control
0x180025a96  cmp     rcx, rax
0x180025a99  jz      short loc_180025AA5
0x180025a9b  test    byte ptr [rcx+1Ch], 80h
0x180025a9f  jnz     loc_180025B5D
0x180025aa5  mov     rcx, [rbx+30h]; hEvent
0x180025aa9  call    cs:__imp_SetEvent
0x180025aaf  lea     rcx, g_TaskHostContextListLock
0x180025ab6  call    cs:__imp_RtlReleaseSRWLockShared
0x180025abc  test    rdi, rdi
0x180025abf  jnz     short loc_180025AF9
0x180025ac1  mov     eax, [rsp+68h+Reply]
0x180025ac5  add     rsp, 48h
0x180025ac9  pop     rdi
0x180025aca  pop     rsi
0x180025acb  pop     rbp
0x180025acc  pop     rbx
0x180025acd  retn
0x180025ace  mov     r8d, 42Bh
0x180025ad4  mov     [rsp+68h+Reply], r8d
0x180025ad9  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ae0  lea     rax, WPP_GLOBAL_Control
0x180025ae7  cmp     rcx, rax
0x180025aea  jz      short loc_180025AAF
0x180025aec  test    byte ptr [rcx+1Ch], 1
0x180025af0  jz      short loc_180025AAF
0x180025af2  mov     edx, 19h
0x180025af7  jmp     short loc_180025B32
0x180025af9  lea     rdx, [rsp+68h+Reply]; Reply
0x180025afe  mov     rcx, rdi; pAsync
0x180025b01  call    cs:__imp_RpcAsyncCompleteCall
0x180025b07  jmp     short loc_180025AC1
0x180025b09  mov     r8d, 4D5h
0x180025b0f  mov     [rsp+68h+Reply], r8d
0x180025b14  mov     rcx, cs:WPP_GLOBAL_Control
0x180025b1b  lea     rax, WPP_GLOBAL_Control
0x180025b22  cmp     rcx, rax
0x180025b25  jz      short loc_180025AAF
0x180025b27  test    byte ptr [rcx+1Ch], 2
0x180025b2b  jz      short loc_180025AAF
0x180025b2d  mov     edx, 1Ah
0x180025b32  mov     r9d, [rbx+20h]
0x180025b36  mov     rcx, [rcx+10h]
0x180025b3a  mov     dword ptr [rsp+68h+var_48], r8d
0x180025b3f  lea     r8, WPP_cec58dd89b8f35da5261aa1d7c90d214_Traceguids
0x180025b46  call    WPP_SF_dd
0x180025b4b  jmp     loc_180025AAF
0x180025b50  mov     [rsp+68h+Reply], 5
0x180025b58  jmp     loc_180025AAF
0x180025b5d  mov     rax, [rbx+78h]
0x180025b61  mov     r9d, [rbx+20h]
0x180025b65  mov     rcx, [rcx+10h]
0x180025b69  mov     [rsp+68h+var_38], rax
0x180025b6e  mov     rax, [rbx+60h]
0x180025b72  mov     [rsp+68h+var_40], rax
0x180025b77  mov     [rsp+68h+var_48], rbx
0x180025b7c  call    WPP_SF_Lqii
0x180025b81  jmp     loc_180025AA5
```
