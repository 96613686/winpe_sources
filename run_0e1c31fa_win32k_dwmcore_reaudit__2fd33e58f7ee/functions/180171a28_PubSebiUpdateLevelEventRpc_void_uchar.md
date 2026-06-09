# PubSebiUpdateLevelEventRpc(void *,uchar)

- ea: `0x180171a28`
- end: `0x180171b1b`
- name: `?PubSebiUpdateLevelEventRpc@@YAJPEAXE@Z`
- size: `243`
- prototype: `__int64 __fastcall(struct _SEB_RPC_PUBLISH_DATA *, unsigned __int8)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180171954`
- `0x1801ecf34`

## callees

- `0x180171a28`
- `0x180171c70`
- `0x180171de4`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180171a7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180171a7b`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180171a75`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x180171a75`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180171ac1`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x180171ac1`
- `RPCRT4!NdrClientCall3` at `0x180171ab1`
- `RPCRT4!NdrClientCall3` at `0x180171ab1`

## pseudocode

```c
__int64 __fastcall PubSebiUpdateLevelEventRpc(struct _SEB_RPC_PUBLISH_DATA *a1, unsigned __int8 a2)
{
  int v2; // esi
  ContextTable *v4; // rcx
  int RpcBindingHandle; // ebx
  void *v6; // rbx
  int v7; // eax
  bool v8; // zf
  int v10; // eax
  int v11; // ecx
  int v12; // eax
  void *v13; // [rsp+40h] [rbp+8h] BYREF

  v2 = a2;
  v13 = 0;
  if ( !a1 )
  {
    LOWORD(RpcBindingHandle) = 87;
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  }
  RpcBindingHandle = PubSebiGetRpcBindingHandle(&v13);
  if ( !RpcBindingHandle )
  {
    v6 = ContextTable::Find(v4, a1);
    if ( !v6 )
    {
      LOWORD(RpcBindingHandle) = 6;
      return (unsigned __int16)RpcBindingHandle | 0x80070000;
    }
    RtlAcquireSRWLockExclusive(a1);
    *((_DWORD *)a1 + 2) = GetCurrentThreadId();
    v7 = *((_DWORD *)a1 + 3);
    if ( (_BYTE)v2 )
    {
      v8 = v7 == 0;
    }
    else
    {
      if ( !v7 )
      {
        RpcBindingHandle = 50;
LABEL_9:
        RtlReleaseSRWLockExclusive(a1);
        *((_DWORD *)a1 + 2) = 0;
        goto LABEL_10;
      }
      v8 = v7 == 1;
    }
    if ( !v8
      || (RpcBindingHandle = (unsigned int)NdrClientCall3(
                                             (MIDL_STUBLESS_PROXY_INFO *)&CSystemEventBrokerPublisher_ProxyInfo,
                                             1u,
                                             0,
                                             v13,
                                             v2,
                                             v6).Pointer) == 0 )
    {
      v10 = *((_DWORD *)a1 + 3);
      v11 = v10 - 1;
      v12 = v10 + 1;
      if ( !(_BYTE)v2 )
        v12 = v11;
      RpcBindingHandle = 0;
      *((_DWORD *)a1 + 3) = v12;
    }
    goto LABEL_9;
  }
LABEL_10:
  if ( RpcBindingHandle > 0 )
    return (unsigned __int16)RpcBindingHandle | 0x80070000;
  return (unsigned int)RpcBindingHandle;
}

```

## disassembly

```asm
0x180171a28  mov     rax, rsp
0x180171a2b  mov     [rax+10h], rbx
0x180171a2f  mov     [rax+18h], rsi
0x180171a33  push    rdi
0x180171a34  sub     rsp, 30h
0x180171a38  movzx   esi, dl
0x180171a3b  mov     rdi, rcx
0x180171a3e  mov     qword ptr [rax+8], 0
0x180171a46  test    rcx, rcx
0x180171a49  jz      loc_180171AED
0x180171a4f  lea     rcx, [rax+8]; void **
0x180171a53  call    ?PubSebiGetRpcBindingHandle@@YAJPEAPEAX@Z; PubSebiGetRpcBindingHandle(void * *)
0x180171a58  mov     ebx, eax
0x180171a5a  test    eax, eax
0x180171a5c  jnz     short loc_180171ACE
0x180171a5e  mov     rdx, rdi; struct _SEB_RPC_PUBLISH_DATA *
0x180171a61  call    ?Find@ContextTable@@QEAAPEAXPEAU_SEB_RPC_PUBLISH_DATA@@@Z; ContextTable::Find(_SEB_RPC_PUBLISH_DATA *)
0x180171a66  mov     rbx, rax
0x180171a69  test    rax, rax
0x180171a6c  jz      loc_180171AF4
0x180171a72  mov     rcx, rdi
0x180171a75  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180171a7b  call    cs:__imp_GetCurrentThreadId
0x180171a81  mov     [rdi+8], eax
0x180171a84  mov     edx, 1; nProcNum
0x180171a89  mov     eax, [rdi+0Ch]
0x180171a8c  test    sil, sil
0x180171a8f  jnz     short loc_180171B02
0x180171a91  test    eax, eax
0x180171a93  jz      short loc_180171AFB
0x180171a95  cmp     eax, edx
0x180171a97  jnz     short loc_180171B06
0x180171a99  mov     r9, [rsp+38h+arg_0]
0x180171a9e  lea     rcx, ?CSystemEventBrokerPublisher_ProxyInfo@@3U_MIDL_STUBLESS_PROXY_INFO@@B; pProxyInfo
0x180171aa5  mov     [rsp+38h+var_10], rbx
0x180171aaa  xor     r8d, r8d; pReturnValue
0x180171aad  mov     [rsp+38h+var_18], esi
0x180171ab1  call    cs:__imp_NdrClientCall3
0x180171ab7  mov     rbx, rax
0x180171aba  test    eax, eax
0x180171abc  jz      short loc_180171B06
0x180171abe  mov     rcx, rdi
0x180171ac1  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180171ac7  mov     dword ptr [rdi+8], 0
0x180171ace  test    ebx, ebx
0x180171ad0  jle     short loc_180171ADB
0x180171ad2  movzx   ebx, bx
0x180171ad5  or      ebx, 80070000h
0x180171adb  mov     rsi, [rsp+38h+arg_10]
0x180171ae0  mov     eax, ebx
0x180171ae2  mov     rbx, [rsp+38h+arg_8]
0x180171ae7  add     rsp, 30h
0x180171aeb  pop     rdi
0x180171aec  retn
0x180171aed  mov     ebx, 57h ; 'W'
0x180171af2  jmp     short loc_180171AD2
0x180171af4  mov     ebx, 6
0x180171af9  jmp     short loc_180171AD2
0x180171afb  mov     ebx, 32h ; '2'
0x180171b00  jmp     short loc_180171ABE
0x180171b02  test    eax, eax
0x180171b04  jmp     short loc_180171A97
0x180171b06  mov     eax, [rdi+0Ch]
0x180171b09  lea     ecx, [rax-1]
0x180171b0c  inc     eax
0x180171b0e  test    sil, sil
0x180171b11  cmovz   eax, ecx
0x180171b14  xor     ebx, ebx
0x180171b16  mov     [rdi+0Ch], eax
0x180171b19  jmp     short loc_180171ABE
```
