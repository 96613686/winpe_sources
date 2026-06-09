# NetrRenameMachineInDomain3

- ea: `0x18002b0d0`
- end: `0x18002b322`
- name: `NetrRenameMachineInDomain3`
- size: `594`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180007cb0`
- `0x180009010`
- `0x180009090`
- `0x18000a240`
- `0x18000b330`
- `0x18002191c`
- `0x1800282dc`
- `0x18002b0d0`
- `0x180035edc`
- `0x180036191`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18002b2dc`
- `netutils!NetApiBufferFree` at `0x18002b2f1`
- `netutils!NetApiBufferFree` at `0x18002b2dc`
- `netutils!NetApiBufferFree` at `0x18002b2f1`
- `netutils!NetApiBufferAllocate` at `0x18002b1e6`
- `netutils!NetApiBufferAllocate` at `0x18002b1e6`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002b227`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002b227`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x18002b1c1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x18002b1c1`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x18002b2ae`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x18002b2ae`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x18002b260`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x18002b260`

## pseudocode

```c
__int64 __fastcall NetrRenameMachineInDomain3(__int64 a1, __int64 a2, LPVOID a3, __int64 a4, __int64 a5, int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  DWORD v11; // eax
  __int64 v12; // rcx
  __int64 v13; // rsi
  DWORD LsaPrimaryDomain; // ebx
  __int64 v15; // rcx
  __int64 v16; // rcx
  PVOID v17; // [rsp+40h] [rbp-28h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v19; // [rsp+50h] [rbp-18h] BYREF
  __int64 v20; // [rsp+58h] [rbp-10h] BYREF

  v17 = 0;
  v19 = 0;
  Buffer = 0;
  v20 = 0;
  result = WsValidateRpcProtSeq(a1);
  if ( (_DWORD)result )
    return result;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    return 5;
  if ( _InterlockedExchange(&JoinpCallInProgress, 1) == 1 )
    return 1791;
  v11 = JoinpDecryptPasswordWithKeyAES(a1, a5, 1, &v20);
  v13 = v20;
  LsaPrimaryDomain = v11;
  if ( !v11 )
  {
    if ( a3 )
    {
LABEL_10:
      if ( !(unsigned __int8)IsNetpManageIPCConnectPresent(v12) )
      {
        LsaPrimaryDomain = 50;
        goto LABEL_26;
      }
      LsaPrimaryDomain = NetpGetLsaPrimaryDomain(0, 1, &v17, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = NetApiBufferAllocate(*((unsigned __int16 *)v17 + 8) + 2, &Buffer);
      if ( !LsaPrimaryDomain )
      {
        memcpy_0(Buffer, *((const void **)v17 + 3), *((unsigned __int16 *)v17 + 8));
        *((_WORD *)Buffer + ((unsigned __int64)*((unsigned __int16 *)v17 + 8) >> 1)) = 0;
      }
      LsaFreeMemory(v17);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = WsImpersonateClient2(0, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      if ( !(unsigned __int8)IsNetpManageIPCConnectPresent(v15) )
        goto LABEL_23;
      LsaPrimaryDomain = NetpMachineValidToJoin(a3, 1, 0);
      if ( ((LsaPrimaryDomain - 2691) & 0xFFFFFFFD) != 0 )
      {
        if ( !LsaPrimaryDomain || LsaPrimaryDomain == 2700 )
          LsaPrimaryDomain = 2692;
        goto LABEL_24;
      }
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v16) )
        LsaPrimaryDomain = NetpChangeMachineName(0, a3, Buffer, a4, v13, a6);
      else
LABEL_23:
        LsaPrimaryDomain = 50;
LABEL_24:
      WsRevertToSelf2(0, 0);
      goto LABEL_26;
    }
    LsaPrimaryDomain = NetpGetNewMachineName(&v19);
    if ( !LsaPrimaryDomain )
    {
      a3 = v19;
      goto LABEL_10;
    }
  }
LABEL_26:
  if ( v19 )
    NetApiBufferFree(v19);
  if ( Buffer )
    NetApiBufferFree(Buffer);
  if ( v13 )
    NetpMemoryFree(v13);
  _InterlockedExchange(&JoinpCallInProgress, 0);
  return LsaPrimaryDomain;
}

```

## disassembly

```asm
0x18002b0d0  push    rbp
0x18002b0d2  push    rbx
0x18002b0d3  push    rsi
0x18002b0d4  push    rdi
0x18002b0d5  push    r12
0x18002b0d7  push    r14
0x18002b0d9  mov     rbp, rsp
0x18002b0dc  sub     rsp, 68h
0x18002b0e0  mov     r14, r9
0x18002b0e3  mov     [rbp+var_28], 0
0x18002b0eb  mov     rdi, r8
0x18002b0ee  mov     [rbp+var_18], 0
0x18002b0f6  mov     rbx, rcx
0x18002b0f9  mov     [rbp+Buffer], 0
0x18002b101  mov     [rbp+var_10], 0
0x18002b109  call    WsValidateRpcProtSeq
0x18002b10e  test    eax, eax
0x18002b110  jnz     loc_18002B314
0x18002b116  mov     rax, cs:NetApiSd
0x18002b11d  lea     rcx, WsNetApiMapping
0x18002b124  mov     [rsp+68h+var_38], rcx
0x18002b129  lea     r8, aNetapi; "NetAPI"
0x18002b130  mov     r12d, 1
0x18002b136  mov     [rsp+68h+var_40], r12d
0x18002b13b  mov     [rsp+68h+var_48], rax
0x18002b140  call    NetpAccessCheckAndAuditEx
0x18002b145  test    eax, eax
0x18002b147  jz      short loc_18002B153
0x18002b149  lea     eax, [r12+4]
0x18002b14e  jmp     loc_18002B314
0x18002b153  mov     eax, r12d
0x18002b156  xchg    eax, cs:JoinpCallInProgress
0x18002b15c  cmp     eax, r12d
0x18002b15f  jnz     short loc_18002B16B
0x18002b161  mov     eax, 6FFh
0x18002b166  jmp     loc_18002B314
0x18002b16b  mov     rdx, [rbp+arg_20]
0x18002b16f  lea     r9, [rbp+var_10]
0x18002b173  mov     r8d, r12d
0x18002b176  mov     rcx, rbx
0x18002b179  call    JoinpDecryptPasswordWithKeyAES
0x18002b17e  mov     rsi, [rbp+var_10]
0x18002b182  mov     ebx, eax
0x18002b184  test    eax, eax
0x18002b186  jnz     loc_18002B2D3
0x18002b18c  test    rdi, rdi
0x18002b18f  jnz     short loc_18002B1A8
0x18002b191  lea     rcx, [rbp+var_18]; Buffer
0x18002b195  call    NetpGetNewMachineName
0x18002b19a  mov     ebx, eax
0x18002b19c  test    eax, eax
0x18002b19e  jnz     loc_18002B2D3
0x18002b1a4  mov     rdi, [rbp+var_18]
0x18002b1a8  call    IsNetpManageIPCConnectPresent
0x18002b1ad  test    al, al
0x18002b1af  jz      loc_18002B2CE
0x18002b1b5  xor     r9d, r9d
0x18002b1b8  lea     r8, [rbp+var_28]
0x18002b1bc  mov     edx, r12d
0x18002b1bf  xor     ecx, ecx
0x18002b1c1  call    cs:__imp_NetpGetLsaPrimaryDomain
0x18002b1c8  nop     dword ptr [rax+rax+00h]
0x18002b1cd  mov     ebx, eax
0x18002b1cf  test    eax, eax
0x18002b1d1  jnz     loc_18002B2D3
0x18002b1d7  mov     rax, [rbp+var_28]
0x18002b1db  lea     rdx, [rbp+Buffer]; Buffer
0x18002b1df  movzx   ecx, word ptr [rax+10h]
0x18002b1e3  add     ecx, 2; ByteCount
0x18002b1e6  call    cs:__imp_NetApiBufferAllocate
0x18002b1ed  nop     dword ptr [rax+rax+00h]
0x18002b1f2  mov     ebx, eax
0x18002b1f4  test    eax, eax
0x18002b1f6  jnz     short loc_18002B223
0x18002b1f8  mov     rdx, [rbp+var_28]
0x18002b1fc  mov     rcx, [rbp+Buffer]; void *
0x18002b200  movzx   r8d, word ptr [rdx+10h]; Size
0x18002b205  mov     rdx, [rdx+18h]; Src
0x18002b209  call    memcpy_0
0x18002b20e  mov     rax, [rbp+var_28]
0x18002b212  movzx   edx, word ptr [rax+10h]
0x18002b216  mov     rax, [rbp+Buffer]
0x18002b21a  shr     rdx, 1
0x18002b21d  xor     ecx, ecx
0x18002b21f  mov     [rax+rdx*2], cx
0x18002b223  mov     rcx, [rbp+var_28]; Buffer
0x18002b227  call    cs:__imp_LsaFreeMemory
0x18002b22e  nop     dword ptr [rax+rax+00h]
0x18002b233  test    ebx, ebx
0x18002b235  jnz     loc_18002B2D3
0x18002b23b  xor     edx, edx
0x18002b23d  xor     ecx, ecx
0x18002b23f  call    WsImpersonateClient2
0x18002b244  mov     ebx, eax
0x18002b246  test    eax, eax
0x18002b248  jnz     loc_18002B2D3
0x18002b24e  call    IsNetpManageIPCConnectPresent
0x18002b253  test    al, al
0x18002b255  jz      short loc_18002B2BE
0x18002b257  xor     r8d, r8d
0x18002b25a  mov     edx, r12d
0x18002b25d  mov     rcx, rdi
0x18002b260  call    cs:__imp_NetpMachineValidToJoin
0x18002b267  nop     dword ptr [rax+rax+00h]
0x18002b26c  mov     ebx, eax
0x18002b26e  add     eax, 0FFFFF57Dh
0x18002b273  test    eax, 0FFFFFFFDh
0x18002b278  jz      short loc_18002B28D
0x18002b27a  test    ebx, ebx
0x18002b27c  jz      short loc_18002B286
0x18002b27e  cmp     ebx, 0A8Ch
0x18002b284  jnz     short loc_18002B2C3
0x18002b286  mov     ebx, 0A84h
0x18002b28b  jmp     short loc_18002B2C3
0x18002b28d  call    IsNetpManageIPCConnectPresent
0x18002b292  test    al, al
0x18002b294  jz      short loc_18002B2BE
0x18002b296  mov     eax, [rbp+arg_28]
0x18002b299  mov     r9, r14
0x18002b29c  mov     r8, [rbp+Buffer]
0x18002b2a0  mov     rdx, rdi
0x18002b2a3  mov     [rsp+68h+var_40], eax
0x18002b2a7  xor     ecx, ecx
0x18002b2a9  mov     [rsp+68h+var_48], rsi
0x18002b2ae  call    cs:__imp_NetpChangeMachineName
0x18002b2b5  nop     dword ptr [rax+rax+00h]
0x18002b2ba  mov     ebx, eax
0x18002b2bc  jmp     short loc_18002B2C3
0x18002b2be  mov     ebx, 32h ; '2'
0x18002b2c3  xor     edx, edx
0x18002b2c5  xor     ecx, ecx
0x18002b2c7  call    WsRevertToSelf2
0x18002b2cc  jmp     short loc_18002B2D3
0x18002b2ce  mov     ebx, 32h ; '2'
0x18002b2d3  mov     rcx, [rbp+var_18]; Buffer
0x18002b2d7  test    rcx, rcx
0x18002b2da  jz      short loc_18002B2E8
0x18002b2dc  call    cs:__imp_NetApiBufferFree
0x18002b2e3  nop     dword ptr [rax+rax+00h]
0x18002b2e8  mov     rcx, [rbp+Buffer]; Buffer
0x18002b2ec  test    rcx, rcx
0x18002b2ef  jz      short loc_18002B2FD
0x18002b2f1  call    cs:__imp_NetApiBufferFree
0x18002b2f8  nop     dword ptr [rax+rax+00h]
0x18002b2fd  test    rsi, rsi
0x18002b300  jz      short loc_18002B30A
0x18002b302  mov     rcx, rsi
0x18002b305  call    NetpMemoryFree
0x18002b30a  xor     eax, eax
0x18002b30c  xchg    eax, cs:JoinpCallInProgress
0x18002b312  mov     eax, ebx
0x18002b314  add     rsp, 68h
0x18002b318  pop     r14
0x18002b31a  pop     r12
0x18002b31c  pop     rdi
0x18002b31d  pop     rsi
0x18002b31e  pop     rbx
0x18002b31f  pop     rbp
0x18002b320  retn
```
