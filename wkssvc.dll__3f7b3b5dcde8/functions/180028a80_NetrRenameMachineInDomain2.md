# NetrRenameMachineInDomain2

- ea: `0x180028a80`
- end: `0x180028ca3`
- name: `NetrRenameMachineInDomain2`
- size: `547`
- prototype: `__int64 __fastcall(__int64, __int64, LPVOID, __int64, __int64, int)`
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
- `0x180026088`
- `0x180028a80`
- `0x180032ec8`
- `0x180033159`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x180028c6a`
- `netutils!NetApiBufferFree` at `0x180028c79`
- `netutils!NetApiBufferFree` at `0x180028c6a`
- `netutils!NetApiBufferFree` at `0x180028c79`
- `netutils!NetApiBufferAllocate` at `0x180028b90`
- `netutils!NetApiBufferAllocate` at `0x180028b90`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180028bcb`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x180028bcb`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x180028b71`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x180028b71`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x180028c42`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x180028c42`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x180028bfa`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x180028bfa`

## pseudocode

```c
__int64 __fastcall NetrRenameMachineInDomain2(__int64 a1, __int64 a2, LPVOID a3, __int64 a4, __int64 a5, int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  DWORD v11; // eax
  __int64 v12; // rsi
  DWORD LsaPrimaryDomain; // ebx
  PSECURITY_DESCRIPTOR v14; // [rsp+20h] [rbp-48h]
  PVOID v15; // [rsp+40h] [rbp-28h] BYREF
  LPVOID Buffer; // [rsp+48h] [rbp-20h] BYREF
  LPVOID v17; // [rsp+50h] [rbp-18h] BYREF
  __int64 v18; // [rsp+58h] [rbp-10h] BYREF

  v15 = 0;
  v17 = 0;
  Buffer = 0;
  v18 = 0;
  result = WsValidateRpcProtSeq();
  if ( (_DWORD)result )
    return result;
  v14 = NetApiSd;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    return 5;
  if ( _InterlockedExchange(&JoinpCallInProgress, 1) == 1 )
    return 1791;
  v11 = JoinpDecryptPasswordWithKey(a1, a5, 1, &v18, v14, 1, &WsNetApiMapping);
  v12 = v18;
  LsaPrimaryDomain = v11;
  if ( !v11 )
  {
    if ( a3 )
    {
LABEL_10:
      if ( !(unsigned __int8)IsNetpManageIPCConnectPresent() )
      {
        LsaPrimaryDomain = 50;
        goto LABEL_26;
      }
      LsaPrimaryDomain = NetpGetLsaPrimaryDomain(0, 1, &v15, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = NetApiBufferAllocate(*((unsigned __int16 *)v15 + 8) + 2, &Buffer);
      if ( !LsaPrimaryDomain )
      {
        memcpy_0(Buffer, *((const void **)v15 + 3), *((unsigned __int16 *)v15 + 8));
        *((_WORD *)Buffer + ((unsigned __int64)*((unsigned __int16 *)v15 + 8) >> 1)) = 0;
      }
      LsaFreeMemory(v15);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      LsaPrimaryDomain = WsImpersonateClient2(0, 0);
      if ( LsaPrimaryDomain )
        goto LABEL_26;
      if ( !(unsigned __int8)IsNetpManageIPCConnectPresent() )
        goto LABEL_23;
      LsaPrimaryDomain = NetpMachineValidToJoin(a3, 1, 0);
      if ( ((LsaPrimaryDomain - 2691) & 0xFFFFFFFD) != 0 )
      {
        if ( !LsaPrimaryDomain || LsaPrimaryDomain == 2700 )
          LsaPrimaryDomain = 2692;
        goto LABEL_24;
      }
      if ( (unsigned __int8)IsNetpManageIPCConnectPresent() )
        LsaPrimaryDomain = NetpChangeMachineName(0, a3, Buffer, a4, v12, a6);
      else
LABEL_23:
        LsaPrimaryDomain = 50;
LABEL_24:
      WsRevertToSelf2(0, 0);
      goto LABEL_26;
    }
    LsaPrimaryDomain = NetpGetNewMachineName(&v17);
    if ( !LsaPrimaryDomain )
    {
      a3 = v17;
      goto LABEL_10;
    }
  }
LABEL_26:
  if ( v17 )
    NetApiBufferFree(v17);
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
0x180028a80  push    rbp
0x180028a82  push    rbx
0x180028a83  push    rsi
0x180028a84  push    rdi
0x180028a85  push    r12
0x180028a87  push    r14
0x180028a89  mov     rbp, rsp
0x180028a8c  sub     rsp, 68h
0x180028a90  mov     r14, r9
0x180028a93  mov     [rbp+var_28], 0
0x180028a9b  mov     rdi, r8
0x180028a9e  mov     [rbp+var_18], 0
0x180028aa6  mov     rbx, rcx
0x180028aa9  mov     [rbp+Buffer], 0
0x180028ab1  mov     [rbp+var_10], 0
0x180028ab9  call    WsValidateRpcProtSeq
0x180028abe  test    eax, eax
0x180028ac0  jnz     loc_180028C96
0x180028ac6  mov     rax, cs:NetApiSd
0x180028acd  lea     rcx, WsNetApiMapping
0x180028ad4  mov     [rsp+68h+var_38], rcx
0x180028ad9  lea     r8, aNetapi; "NetAPI"
0x180028ae0  mov     r12d, 1
0x180028ae6  mov     [rsp+68h+var_40], r12d
0x180028aeb  mov     [rsp+68h+var_48], rax
0x180028af0  call    NetpAccessCheckAndAuditEx
0x180028af5  test    eax, eax
0x180028af7  jz      short loc_180028B03
0x180028af9  lea     eax, [r12+4]
0x180028afe  jmp     loc_180028C96
0x180028b03  mov     eax, r12d
0x180028b06  xchg    eax, cs:JoinpCallInProgress
0x180028b0c  cmp     eax, r12d
0x180028b0f  jnz     short loc_180028B1B
0x180028b11  mov     eax, 6FFh
0x180028b16  jmp     loc_180028C96
0x180028b1b  mov     rdx, [rbp+arg_20]
0x180028b1f  lea     r9, [rbp+var_10]
0x180028b23  mov     r8d, r12d
0x180028b26  mov     rcx, rbx
0x180028b29  call    JoinpDecryptPasswordWithKey
0x180028b2e  mov     rsi, [rbp+var_10]
0x180028b32  mov     ebx, eax
0x180028b34  test    eax, eax
0x180028b36  jnz     loc_180028C61
0x180028b3c  test    rdi, rdi
0x180028b3f  jnz     short loc_180028B58
0x180028b41  lea     rcx, [rbp+var_18]; Buffer
0x180028b45  call    NetpGetNewMachineName
0x180028b4a  mov     ebx, eax
0x180028b4c  test    eax, eax
0x180028b4e  jnz     loc_180028C61
0x180028b54  mov     rdi, [rbp+var_18]
0x180028b58  call    IsNetpManageIPCConnectPresent
0x180028b5d  test    al, al
0x180028b5f  jz      loc_180028C5C
0x180028b65  xor     r9d, r9d
0x180028b68  lea     r8, [rbp+var_28]
0x180028b6c  mov     edx, r12d
0x180028b6f  xor     ecx, ecx
0x180028b71  call    cs:__imp_NetpGetLsaPrimaryDomain
0x180028b77  mov     ebx, eax
0x180028b79  test    eax, eax
0x180028b7b  jnz     loc_180028C61
0x180028b81  mov     rax, [rbp+var_28]
0x180028b85  lea     rdx, [rbp+Buffer]; Buffer
0x180028b89  movzx   ecx, word ptr [rax+10h]
0x180028b8d  add     ecx, 2; ByteCount
0x180028b90  call    cs:__imp_NetApiBufferAllocate
0x180028b96  mov     ebx, eax
0x180028b98  test    eax, eax
0x180028b9a  jnz     short loc_180028BC7
0x180028b9c  mov     rdx, [rbp+var_28]
0x180028ba0  mov     rcx, [rbp+Buffer]; void *
0x180028ba4  movzx   r8d, word ptr [rdx+10h]; Size
0x180028ba9  mov     rdx, [rdx+18h]; Src
0x180028bad  call    memcpy_0
0x180028bb2  mov     rax, [rbp+var_28]
0x180028bb6  movzx   edx, word ptr [rax+10h]
0x180028bba  mov     rax, [rbp+Buffer]
0x180028bbe  shr     rdx, 1
0x180028bc1  xor     ecx, ecx
0x180028bc3  mov     [rax+rdx*2], cx
0x180028bc7  mov     rcx, [rbp+var_28]; Buffer
0x180028bcb  call    cs:__imp_LsaFreeMemory
0x180028bd1  test    ebx, ebx
0x180028bd3  jnz     loc_180028C61
0x180028bd9  xor     edx, edx
0x180028bdb  xor     ecx, ecx
0x180028bdd  call    WsImpersonateClient2
0x180028be2  mov     ebx, eax
0x180028be4  test    eax, eax
0x180028be6  jnz     short loc_180028C61
0x180028be8  call    IsNetpManageIPCConnectPresent
0x180028bed  test    al, al
0x180028bef  jz      short loc_180028C4C
0x180028bf1  xor     r8d, r8d
0x180028bf4  mov     edx, r12d
0x180028bf7  mov     rcx, rdi
0x180028bfa  call    cs:__imp_NetpMachineValidToJoin
0x180028c00  mov     ebx, eax
0x180028c02  add     eax, 0FFFFF57Dh
0x180028c07  test    eax, 0FFFFFFFDh
0x180028c0c  jz      short loc_180028C21
0x180028c0e  test    ebx, ebx
0x180028c10  jz      short loc_180028C1A
0x180028c12  cmp     ebx, 0A8Ch
0x180028c18  jnz     short loc_180028C51
0x180028c1a  mov     ebx, 0A84h
0x180028c1f  jmp     short loc_180028C51
0x180028c21  call    IsNetpManageIPCConnectPresent
0x180028c26  test    al, al
0x180028c28  jz      short loc_180028C4C
0x180028c2a  mov     eax, [rbp+arg_28]
0x180028c2d  mov     r9, r14
0x180028c30  mov     r8, [rbp+Buffer]
0x180028c34  mov     rdx, rdi
0x180028c37  mov     [rsp+68h+var_40], eax
0x180028c3b  xor     ecx, ecx
0x180028c3d  mov     [rsp+68h+var_48], rsi
0x180028c42  call    cs:__imp_NetpChangeMachineName
0x180028c48  mov     ebx, eax
0x180028c4a  jmp     short loc_180028C51
0x180028c4c  mov     ebx, 32h ; '2'
0x180028c51  xor     edx, edx
0x180028c53  xor     ecx, ecx
0x180028c55  call    WsRevertToSelf2
0x180028c5a  jmp     short loc_180028C61
0x180028c5c  mov     ebx, 32h ; '2'
0x180028c61  mov     rcx, [rbp+var_18]; Buffer
0x180028c65  test    rcx, rcx
0x180028c68  jz      short loc_180028C70
0x180028c6a  call    cs:__imp_NetApiBufferFree
0x180028c70  mov     rcx, [rbp+Buffer]; Buffer
0x180028c74  test    rcx, rcx
0x180028c77  jz      short loc_180028C7F
0x180028c79  call    cs:__imp_NetApiBufferFree
0x180028c7f  test    rsi, rsi
0x180028c82  jz      short loc_180028C8C
0x180028c84  mov     rcx, rsi
0x180028c87  call    NetpMemoryFree
0x180028c8c  xor     eax, eax
0x180028c8e  xchg    eax, cs:JoinpCallInProgress
0x180028c94  mov     eax, ebx
0x180028c96  add     rsp, 68h
0x180028c9a  pop     r14
0x180028c9c  pop     r12
0x180028c9e  pop     rdi
0x180028c9f  pop     rsi
0x180028ca0  pop     rbx
0x180028ca1  pop     rbp
0x180028ca2  retn
```
