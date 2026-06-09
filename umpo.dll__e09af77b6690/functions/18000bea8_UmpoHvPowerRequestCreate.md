# UmpoHvPowerRequestCreate

- ea: `0x18000bea8`
- end: `0x18000bfc5`
- name: `UmpoHvPowerRequestCreate`
- size: `285`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000be60`

## callees

- `0x18000bea8`
- `0x180018418`
- `0x180018600`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000bf7d`
- `RPCRT4!NdrClientCall3` at `0x18000bf7d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000bfba`

## pseudocode

```c
__int64 __fastcall UmpoHvPowerRequestCreate(int a1, __int64 a2)
{
  void *RequesterId; // r14
  unsigned int Pointer; // ebx
  unsigned __int16 *RequesterReason; // rsi
  __int64 v8; // rax
  int v9; // [rsp+90h] [rbp+18h] BYREF
  int v10; // [rsp+98h] [rbp+20h] BYREF

  v9 = 0;
  v10 = 0;
  if ( UmpoHvRpcPowerRequestClientHandle )
  {
    RequesterId = (void *)PowerHelperGetRequesterId(a2, a2, &v10);
    v8 = *(_QWORD *)(a2 + 32);
    if ( v8 )
      RequesterReason = PowerHelperGetRequesterReason(v8 + a2, &v9);
    else
      RequesterReason = L"None";
    Pointer = (unsigned int)NdrClientCall3(
                              (MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo,
                              0,
                              0,
                              UmpoHvRpcPowerRequestClientHandle,
                              a1,
                              RequesterId,
                              RequesterReason).Pointer;
  }
  else
  {
    RequesterId = 0;
    Pointer = 50;
    RequesterReason = 0;
  }
  if ( v9 )
    LocalFree(RequesterReason);
  if ( v10 )
    LocalFree(RequesterId);
  return Pointer;
}

```

## disassembly

```asm
0x18000bea8  mov     rax, rsp
0x18000beab  mov     [rax+8], rbx
0x18000beaf  push    rsi
0x18000beb0  push    r14
0x18000beb2  push    r15
0x18000beb4  sub     rsp, 60h
0x18000beb8  mov     rbx, rdx
0x18000bebb  mov     r15d, ecx
0x18000bebe  mov     dword ptr [rax+18h], 0
0x18000bec5  mov     dword ptr [rax+20h], 0
0x18000becc  cmp     cs:UmpoHvRpcPowerRequestClientHandle, 0
0x18000bed4  jnz     short loc_18000BF0F
0x18000bed6  xor     r14d, r14d
0x18000bed9  lea     ebx, [r14+32h]
0x18000bedd  xor     esi, esi
0x18000bedf  cmp     [rsp+78h+arg_10], 0
0x18000bee7  jnz     loc_18000BFA9
0x18000beed  cmp     [rsp+78h+arg_18], 0
0x18000bef5  jnz     loc_18000BFB7
0x18000befb  mov     eax, ebx
0x18000befd  mov     rbx, [rsp+78h+arg_0]
0x18000bf05  add     rsp, 60h
0x18000bf09  pop     r15
0x18000bf0b  pop     r14
0x18000bf0d  pop     rsi
0x18000bf0e  retn
0x18000bf0f  lea     r8, [rsp+78h+arg_18]
0x18000bf17  mov     rcx, rbx
0x18000bf1a  call    PowerHelperGetRequesterId
0x18000bf1f  mov     r14, rax
0x18000bf22  mov     [rsp+78h+var_20], rax
0x18000bf27  mov     rax, [rbx+20h]
0x18000bf2b  test    rax, rax
0x18000bf2e  jz      short loc_18000BF46
0x18000bf30  lea     rcx, [rax+rbx]
0x18000bf34  lea     rdx, [rsp+78h+arg_10]
0x18000bf3c  call    PowerHelperGetRequesterReason
0x18000bf41  mov     rsi, rax
0x18000bf44  jmp     short loc_18000BF4D
0x18000bf46  lea     rsi, aNone; "None"
0x18000bf4d  mov     [rsp+78h+var_30], rsi
0x18000bf52  mov     [rsp+78h+var_28], 0
0x18000bf5b  mov     [rsp+78h+var_48], rsi
0x18000bf60  mov     [rsp+78h+var_50], r14
0x18000bf65  mov     [rsp+78h+var_58], r15d
0x18000bf6a  mov     r9, cs:UmpoHvRpcPowerRequestClientHandle
0x18000bf71  xor     r8d, r8d; pReturnValue
0x18000bf74  xor     edx, edx; nProcNum
0x18000bf76  lea     rcx, pProxyInfo; pProxyInfo
0x18000bf7d  call    cs:__imp_NdrClientCall3
0x18000bf83  mov     rbx, rax
0x18000bf86  mov     [rsp+78h+var_28], rax
0x18000bf8b  mov     [rsp+78h+var_38], eax
0x18000bf8f  jmp     loc_18000BEDF
0x18000bf94  mov     ebx, eax
0x18000bf96  mov     [rsp+78h+var_38], eax
0x18000bf9a  mov     rsi, [rsp+78h+var_30]
0x18000bf9f  mov     r14, [rsp+78h+var_20]
0x18000bfa4  jmp     loc_18000BEDF
0x18000bfa9  mov     rcx, rsi; hMem
0x18000bfac  call    cs:__imp_LocalFree
0x18000bfb2  jmp     loc_18000BEED
0x18000bfb7  mov     rcx, r14; hMem
0x18000bfba  call    cs:__imp_LocalFree
0x18000bfc0  jmp     loc_18000BEFB
```
