# NetrRenameMachineInDomain2

- ea: `0x18002ae70`
- end: `0x18002b0c2`
- name: `NetrRenameMachineInDomain2`
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
- `0x180028030`
- `0x18002ae70`
- `0x180035edc`
- `0x180036191`

## import_xrefs

- `netutils!NetApiBufferFree` at `0x18002b07c`
- `netutils!NetApiBufferFree` at `0x18002b091`
- `netutils!NetApiBufferFree` at `0x18002b07c`
- `netutils!NetApiBufferFree` at `0x18002b091`
- `netutils!NetApiBufferAllocate` at `0x18002af86`
- `netutils!NetApiBufferAllocate` at `0x18002af86`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002afc7`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x18002afc7`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x18002af61`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpGetLsaPrimaryDomain` at `0x18002af61`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x18002b04e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpChangeMachineName` at `0x18002b04e`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x18002b000`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpMachineValidToJoin` at `0x18002b000`

## pseudocode

```c
__int64 __fastcall NetrRenameMachineInDomain2(__int64 a1, __int64 a2, LPVOID a3, __int64 a4, __int64 a5, int a6)
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
  v11 = JoinpDecryptPasswordWithKey(a1, a5, 1, &v20);
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
0x18002ae70  push    rbp
0x18002ae72  push    rbx
0x18002ae73  push    rsi
0x18002ae74  push    rdi
0x18002ae75  push    r12
0x18002ae77  push    r14
0x18002ae79  mov     rbp, rsp
0x18002ae7c  sub     rsp, 68h
0x18002ae80  mov     r14, r9
0x18002ae83  mov     [rbp+var_28], 0
0x18002ae8b  mov     rdi, r8
0x18002ae8e  mov     [rbp+var_18], 0
0x18002ae96  mov     rbx, rcx
0x18002ae99  mov     [rbp+Buffer], 0
0x18002aea1  mov     [rbp+var_10], 0
0x18002aea9  call    WsValidateRpcProtSeq
0x18002aeae  test    eax, eax
0x18002aeb0  jnz     loc_18002B0B4
0x18002aeb6  mov     rax, cs:NetApiSd
0x18002aebd  lea     rcx, WsNetApiMapping
0x18002aec4  mov     [rsp+68h+var_38], rcx
0x18002aec9  lea     r8, aNetapi; "NetAPI"
0x18002aed0  mov     r12d, 1
0x18002aed6  mov     [rsp+68h+var_40], r12d
0x18002aedb  mov     [rsp+68h+var_48], rax
0x18002aee0  call    NetpAccessCheckAndAuditEx
0x18002aee5  test    eax, eax
0x18002aee7  jz      short loc_18002AEF3
0x18002aee9  lea     eax, [r12+4]
0x18002aeee  jmp     loc_18002B0B4
0x18002aef3  mov     eax, r12d
0x18002aef6  xchg    eax, cs:JoinpCallInProgress
0x18002aefc  cmp     eax, r12d
0x18002aeff  jnz     short loc_18002AF0B
0x18002af01  mov     eax, 6FFh
0x18002af06  jmp     loc_18002B0B4
0x18002af0b  mov     rdx, [rbp+arg_20]
0x18002af0f  lea     r9, [rbp+var_10]
0x18002af13  mov     r8d, r12d
0x18002af16  mov     rcx, rbx
0x18002af19  call    JoinpDecryptPasswordWithKey
0x18002af1e  mov     rsi, [rbp+var_10]
0x18002af22  mov     ebx, eax
0x18002af24  test    eax, eax
0x18002af26  jnz     loc_18002B073
0x18002af2c  test    rdi, rdi
0x18002af2f  jnz     short loc_18002AF48
0x18002af31  lea     rcx, [rbp+var_18]; Buffer
0x18002af35  call    NetpGetNewMachineName
0x18002af3a  mov     ebx, eax
0x18002af3c  test    eax, eax
0x18002af3e  jnz     loc_18002B073
0x18002af44  mov     rdi, [rbp+var_18]
0x18002af48  call    IsNetpManageIPCConnectPresent
0x18002af4d  test    al, al
0x18002af4f  jz      loc_18002B06E
0x18002af55  xor     r9d, r9d
0x18002af58  lea     r8, [rbp+var_28]
0x18002af5c  mov     edx, r12d
0x18002af5f  xor     ecx, ecx
0x18002af61  call    cs:__imp_NetpGetLsaPrimaryDomain
0x18002af68  nop     dword ptr [rax+rax+00h]
0x18002af6d  mov     ebx, eax
0x18002af6f  test    eax, eax
0x18002af71  jnz     loc_18002B073
0x18002af77  mov     rax, [rbp+var_28]
0x18002af7b  lea     rdx, [rbp+Buffer]; Buffer
0x18002af7f  movzx   ecx, word ptr [rax+10h]
0x18002af83  add     ecx, 2; ByteCount
0x18002af86  call    cs:__imp_NetApiBufferAllocate
0x18002af8d  nop     dword ptr [rax+rax+00h]
0x18002af92  mov     ebx, eax
0x18002af94  test    eax, eax
0x18002af96  jnz     short loc_18002AFC3
0x18002af98  mov     rdx, [rbp+var_28]
0x18002af9c  mov     rcx, [rbp+Buffer]; void *
0x18002afa0  movzx   r8d, word ptr [rdx+10h]; Size
0x18002afa5  mov     rdx, [rdx+18h]; Src
0x18002afa9  call    memcpy_0
0x18002afae  mov     rax, [rbp+var_28]
0x18002afb2  movzx   edx, word ptr [rax+10h]
0x18002afb6  mov     rax, [rbp+Buffer]
0x18002afba  shr     rdx, 1
0x18002afbd  xor     ecx, ecx
0x18002afbf  mov     [rax+rdx*2], cx
0x18002afc3  mov     rcx, [rbp+var_28]; Buffer
0x18002afc7  call    cs:__imp_LsaFreeMemory
0x18002afce  nop     dword ptr [rax+rax+00h]
0x18002afd3  test    ebx, ebx
0x18002afd5  jnz     loc_18002B073
0x18002afdb  xor     edx, edx
0x18002afdd  xor     ecx, ecx
0x18002afdf  call    WsImpersonateClient2
0x18002afe4  mov     ebx, eax
0x18002afe6  test    eax, eax
0x18002afe8  jnz     loc_18002B073
0x18002afee  call    IsNetpManageIPCConnectPresent
0x18002aff3  test    al, al
0x18002aff5  jz      short loc_18002B05E
0x18002aff7  xor     r8d, r8d
0x18002affa  mov     edx, r12d
0x18002affd  mov     rcx, rdi
0x18002b000  call    cs:__imp_NetpMachineValidToJoin
0x18002b007  nop     dword ptr [rax+rax+00h]
0x18002b00c  mov     ebx, eax
0x18002b00e  add     eax, 0FFFFF57Dh
0x18002b013  test    eax, 0FFFFFFFDh
0x18002b018  jz      short loc_18002B02D
0x18002b01a  test    ebx, ebx
0x18002b01c  jz      short loc_18002B026
0x18002b01e  cmp     ebx, 0A8Ch
0x18002b024  jnz     short loc_18002B063
0x18002b026  mov     ebx, 0A84h
0x18002b02b  jmp     short loc_18002B063
0x18002b02d  call    IsNetpManageIPCConnectPresent
0x18002b032  test    al, al
0x18002b034  jz      short loc_18002B05E
0x18002b036  mov     eax, [rbp+arg_28]
0x18002b039  mov     r9, r14
0x18002b03c  mov     r8, [rbp+Buffer]
0x18002b040  mov     rdx, rdi
0x18002b043  mov     [rsp+68h+var_40], eax
0x18002b047  xor     ecx, ecx
0x18002b049  mov     [rsp+68h+var_48], rsi
0x18002b04e  call    cs:__imp_NetpChangeMachineName
0x18002b055  nop     dword ptr [rax+rax+00h]
0x18002b05a  mov     ebx, eax
0x18002b05c  jmp     short loc_18002B063
0x18002b05e  mov     ebx, 32h ; '2'
0x18002b063  xor     edx, edx
0x18002b065  xor     ecx, ecx
0x18002b067  call    WsRevertToSelf2
0x18002b06c  jmp     short loc_18002B073
0x18002b06e  mov     ebx, 32h ; '2'
0x18002b073  mov     rcx, [rbp+var_18]; Buffer
0x18002b077  test    rcx, rcx
0x18002b07a  jz      short loc_18002B088
0x18002b07c  call    cs:__imp_NetApiBufferFree
0x18002b083  nop     dword ptr [rax+rax+00h]
0x18002b088  mov     rcx, [rbp+Buffer]; Buffer
0x18002b08c  test    rcx, rcx
0x18002b08f  jz      short loc_18002B09D
0x18002b091  call    cs:__imp_NetApiBufferFree
0x18002b098  nop     dword ptr [rax+rax+00h]
0x18002b09d  test    rsi, rsi
0x18002b0a0  jz      short loc_18002B0AA
0x18002b0a2  mov     rcx, rsi
0x18002b0a5  call    NetpMemoryFree
0x18002b0aa  xor     eax, eax
0x18002b0ac  xchg    eax, cs:JoinpCallInProgress
0x18002b0b2  mov     eax, ebx
0x18002b0b4  add     rsp, 68h
0x18002b0b8  pop     r14
0x18002b0ba  pop     r12
0x18002b0bc  pop     rdi
0x18002b0bd  pop     rsi
0x18002b0be  pop     rbx
0x18002b0bf  pop     rbp
0x18002b0c0  retn
```
