# NetrRenameMachineInDomain3

- ea: `0x180028cb0`
- end: `0x180028ed3`
- name: `NetrRenameMachineInDomain3`
- size: `547`
- prototype: `__int64 __fastcall(void *, __int64, LPVOID, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007604`
- `0x180008950`
- `0x1800089d0`
- `0x180009a40`
- `0x18000a0c0`
- `0x18002016c`
- `0x180026300`
- `0x180028cb0`
- `0x180032ec8`
- `0x180033159`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180028e9a`
- `netutils!NetApiBufferFree` at `0x180028ea9`
- `netutils!NetApiBufferFree` at `0x180028e9a`
- `netutils!NetApiBufferFree` at `0x180028ea9`
- `netutils!NetApiBufferAllocate` at `0x180028dc0`
- `netutils!NetApiBufferAllocate` at `0x180028dc0`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180028dfb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180028dfb`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x180028da1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x180028da1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x180028e72`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x180028e72`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x180028e2a`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x180028e2a`

## pseudocode

```c
__int64 __fastcall NetrRenameMachineInDomain3(void *a1, __int64 a2, LPVOID a3, __int64 a4, __int64 a5, int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  DWORD v11; // eax
  void *v12; // rsi
  DWORD LsaPrimaryDomain; // ebx
  PVOID v14; // [rsp+40h] [rbp-28h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v16; // [rsp+50h] [rbp-18h] BYREF
  void *v17; // [rsp+58h] [rbp-10h] BYREF

  v14 = 0;
  v16 = 0;
  Buffer = 0;
  v17 = 0;
  result = WsValidateRpcProtSeq(a1);
  if ( (_DWORD)result )
    return result;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    return 5;
  if ( _InterlockedExchange(&JoinpCallInProgress, 1) == 1 )
    return 1791;
  v11 = JoinpDecryptPasswordWithKeyAES((__int64)a1, a5, 1, (__int64)&v17);
  v12 = v17;
  LsaPrimaryDomain = v11;
  if ( !v11 )
  {
    if ( a3 )
    {
LABEL_10:
      if ( !IsNetpManageIPCConnectPresent() )
      {
        LsaPrimaryDomain = 50;
        goto LABEL_26;
      }
      LsaPrimaryDomain = NetpGetLsaPrimaryDomain(0, 1, &v14, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = NetApiBufferAllocate(*((unsigned __int16 *)v14 + 8) + 2, &Buffer);
      if ( !LsaPrimaryDomain )
      {
        memcpy_0(Buffer, *((const void **)v14 + 3), *((unsigned __int16 *)v14 + 8));
        *((_WORD *)Buffer + ((unsigned __int64)*((unsigned __int16 *)v14 + 8) >> 1)) = 0;
      }
      LsaFreeMemory(v14);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = WsImpersonateClient2(0, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      if ( !IsNetpManageIPCConnectPresent() )
        goto LABEL_23;
      LsaPrimaryDomain = NetpMachineValidToJoin(a3, 1, 0);
      if ( ((LsaPrimaryDomain - 2691) & 0xFFFFFFFD) != 0 )
      {
        if ( !LsaPrimaryDomain || LsaPrimaryDomain == 2700 )
          LsaPrimaryDomain = 2692;
        goto LABEL_24;
      }
      if ( IsNetpManageIPCConnectPresent() )
        LsaPrimaryDomain = NetpChangeMachineName(0, a3, Buffer, a4, v12, a6);
      else
LABEL_23:
        LsaPrimaryDomain = 50;
LABEL_24:
      WsRevertToSelf2(0, 0);
      goto LABEL_26;
    }
    LsaPrimaryDomain = NetpGetNewMachineName(&v16);
    if ( !LsaPrimaryDomain )
    {
      a3 = v16;
      goto LABEL_10;
    }
  }
LABEL_26:
  if ( v16 )
    NetApiBufferFree(v16);
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v12 )
    NetpMemoryFree(v12);
  _InterlockedExchange(&JoinpCallInProgress, 0);
  return LsaPrimaryDomain;
}

```

## disassembly

```asm
0x180028cb0  push    rbp
0x180028cb2  push    rbx
0x180028cb3  push    rsi
0x180028cb4  push    rdi
0x180028cb5  push    r12
0x180028cb7  push    r14
0x180028cb9  mov     rbp, rsp
0x180028cbc  sub     rsp, 68h
0x180028cc0  mov     r14, r9
0x180028cc3  mov     [rbp+var_28], 0
0x180028ccb  mov     rdi, r8
0x180028cce  mov     [rbp+var_18], 0
0x180028cd6  mov     rbx, rcx
0x180028cd9  mov     [rbp+Buffer], 0
0x180028ce1  mov     [rbp+var_10], 0
0x180028ce9  call    WsValidateRpcProtSeq
0x180028cee  test    eax, eax
0x180028cf0  jnz     loc_180028EC6
0x180028cf6  mov     rax, cs:NetApiSd
0x180028cfd  lea     rcx, WsNetApiMapping
0x180028d04  mov     [rsp+68h+var_38], rcx
0x180028d09  lea     r8, aNetapi; "NetAPI"
0x180028d10  mov     r12d, 1
0x180028d16  mov     [rsp+68h+var_40], r12d
0x180028d1b  mov     [rsp+68h+var_48], rax
0x180028d20  call    NetpAccessCheckAndAuditEx
0x180028d25  test    eax, eax
0x180028d27  jz      short loc_180028D33
0x180028d29  lea     eax, [r12+4]
0x180028d2e  jmp     loc_180028EC6
0x180028d33  mov     eax, r12d
0x180028d36  xchg    eax, cs:JoinpCallInProgress
0x180028d3c  cmp     eax, r12d
0x180028d3f  jnz     short loc_180028D4B
0x180028d41  mov     eax, 6FFh
0x180028d46  jmp     loc_180028EC6
0x180028d4b  mov     rdx, [rbp+arg_20]
0x180028d4f  lea     r9, [rbp+var_10]
0x180028d53  mov     r8d, r12d
0x180028d56  mov     rcx, rbx
0x180028d59  call    JoinpDecryptPasswordWithKeyAES
0x180028d5e  mov     rsi, [rbp+var_10]
0x180028d62  mov     ebx, eax
0x180028d64  test    eax, eax
0x180028d66  jnz     loc_180028E91
0x180028d6c  test    rdi, rdi
0x180028d6f  jnz     short loc_180028D88
0x180028d71  lea     rcx, [rbp+var_18]; Buffer
0x180028d75  call    NetpGetNewMachineName
0x180028d7a  mov     ebx, eax
0x180028d7c  test    eax, eax
0x180028d7e  jnz     loc_180028E91
0x180028d84  mov     rdi, [rbp+var_18]
0x180028d88  call    IsNetpManageIPCConnectPresent
0x180028d8d  test    al, al
0x180028d8f  jz      loc_180028E8C
0x180028d95  xor     r9d, r9d
0x180028d98  lea     r8, [rbp+var_28]
0x180028d9c  mov     edx, r12d
0x180028d9f  xor     ecx, ecx
0x180028da1  call    cs:__imp_NetpGetLsaPrimaryDomain
0x180028da7  mov     ebx, eax
0x180028da9  test    eax, eax
0x180028dab  jnz     loc_180028E91
0x180028db1  mov     rax, [rbp+var_28]
0x180028db5  lea     rdx, [rbp+Buffer]; Buffer
0x180028db9  movzx   ecx, word ptr [rax+10h]
0x180028dbd  add     ecx, 2; ByteCount
0x180028dc0  call    cs:__imp_NetApiBufferAllocate
0x180028dc6  mov     ebx, eax
0x180028dc8  test    eax, eax
0x180028dca  jnz     short loc_180028DF7
0x180028dcc  mov     rdx, [rbp+var_28]
0x180028dd0  mov     rcx, [rbp+Buffer]; void *
0x180028dd4  movzx   r8d, word ptr [rdx+10h]; Size
0x180028dd9  mov     rdx, [rdx+18h]; Src
0x180028ddd  call    memcpy_0
0x180028de2  mov     rax, [rbp+var_28]
0x180028de6  movzx   edx, word ptr [rax+10h]
0x180028dea  mov     rax, [rbp+Buffer]
0x180028dee  shr     rdx, 1
0x180028df1  xor     ecx, ecx
0x180028df3  mov     [rax+rdx*2], cx
0x180028df7  mov     rcx, [rbp+var_28]; Buffer
0x180028dfb  call    cs:__imp_LsaFreeMemory
0x180028e01  test    ebx, ebx
0x180028e03  jnz     loc_180028E91
0x180028e09  xor     edx, edx
0x180028e0b  xor     ecx, ecx
0x180028e0d  call    WsImpersonateClient2
0x180028e12  mov     ebx, eax
0x180028e14  test    eax, eax
0x180028e16  jnz     short loc_180028E91
0x180028e18  call    IsNetpManageIPCConnectPresent
0x180028e1d  test    al, al
0x180028e1f  jz      short loc_180028E7C
0x180028e21  xor     r8d, r8d
0x180028e24  mov     edx, r12d
0x180028e27  mov     rcx, rdi
0x180028e2a  call    cs:__imp_NetpMachineValidToJoin
0x180028e30  mov     ebx, eax
0x180028e32  add     eax, 0FFFFF57Dh
0x180028e37  test    eax, 0FFFFFFFDh
0x180028e3c  jz      short loc_180028E51
0x180028e3e  test    ebx, ebx
0x180028e40  jz      short loc_180028E4A
0x180028e42  cmp     ebx, 0A8Ch
0x180028e48  jnz     short loc_180028E81
0x180028e4a  mov     ebx, 0A84h
0x180028e4f  jmp     short loc_180028E81
0x180028e51  call    IsNetpManageIPCConnectPresent
0x180028e56  test    al, al
0x180028e58  jz      short loc_180028E7C
0x180028e5a  mov     eax, [rbp+arg_28]
0x180028e5d  mov     r9, r14
0x180028e60  mov     r8, [rbp+Buffer]
0x180028e64  mov     rdx, rdi
0x180028e67  mov     [rsp+68h+var_40], eax
0x180028e6b  xor     ecx, ecx
0x180028e6d  mov     [rsp+68h+var_48], rsi
0x180028e72  call    cs:__imp_NetpChangeMachineName
0x180028e78  mov     ebx, eax
0x180028e7a  jmp     short loc_180028E81
0x180028e7c  mov     ebx, 32h ; '2'
0x180028e81  xor     edx, edx
0x180028e83  xor     ecx, ecx
0x180028e85  call    WsRevertToSelf2
0x180028e8a  jmp     short loc_180028E91
0x180028e8c  mov     ebx, 32h ; '2'
0x180028e91  mov     rcx, [rbp+var_18]; Buffer
0x180028e95  test    rcx, rcx
0x180028e98  jz      short loc_180028EA0
0x180028e9a  call    cs:__imp_NetApiBufferFree
0x180028ea0  mov     rcx, [rbp+Buffer]; Buffer
0x180028ea4  test    rcx, rcx
0x180028ea7  jz      short loc_180028EAF
0x180028ea9  call    cs:__imp_NetApiBufferFree
0x180028eaf  test    rsi, rsi
0x180028eb2  jz      short loc_180028EBC
0x180028eb4  mov     rcx, rsi
0x180028eb7  call    NetpMemoryFree
0x180028ebc  xor     eax, eax
0x180028ebe  xchg    eax, cs:JoinpCallInProgress
0x180028ec4  mov     eax, ebx
0x180028ec6  add     rsp, 68h
0x180028eca  pop     r14
0x180028ecc  pop     r12
0x180028ece  pop     rdi
0x180028ecf  pop     rsi
0x180028ed0  pop     rbx
0x180028ed1  pop     rbp
0x180028ed2  retn
```
