# NetrSetPrimaryComputerName

- ea: `0x18002b330`
- end: `0x18002b415`
- name: `NetrSetPrimaryComputerName`
- size: `229`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007cb0`
- `0x18000a240`
- `0x18000b330`
- `0x18002191c`
- `0x180028030`
- `0x1800288a8`
- `0x18002b330`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002b3c6`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002b3c6`

## string_xrefs

- `0x18002b3bf`: `NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrSetPrimaryComputerName(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rcx
  const WCHAR *v13; // rdi
  unsigned int v14; // ebx
  const WCHAR *v15; // [rsp+40h] [rbp-38h] BYREF

  v15 = 0;
  result = WsValidateRpcProtSeq(a1);
  if ( !(_DWORD)result )
  {
    if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    {
      return 5;
    }
    else
    {
      v11 = JoinpDecryptPasswordWithKey(a1, a5, 0, (__int64 *)&v15);
      v13 = v15;
      v14 = v11;
      if ( v11 )
      {
        if ( (unsigned __int8)IsNetpManageIPCConnectPresent(v12) )
          NetpLogPrintHelper(L"NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
      }
      else
      {
        v14 = NetpManageAltComputerName(a1, a3, 3u, a4, v15, a6);
      }
      if ( v13 )
        NetpMemoryFree(v13);
      return v14;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002b330  push    rbx
0x18002b332  push    rbp
0x18002b333  push    rsi
0x18002b334  push    rdi
0x18002b335  push    r14
0x18002b337  sub     rsp, 50h
0x18002b33b  mov     rbp, r9
0x18002b33e  mov     [rsp+78h+var_38], 0
0x18002b347  mov     r14, r8
0x18002b34a  mov     rsi, rcx
0x18002b34d  call    WsValidateRpcProtSeq
0x18002b352  test    eax, eax
0x18002b354  jnz     loc_18002B409
0x18002b35a  mov     rax, cs:NetApiSd
0x18002b361  lea     rcx, WsNetApiMapping
0x18002b368  mov     [rsp+78h+var_48], rcx
0x18002b36d  lea     r8, aNetapi; "NetAPI"
0x18002b374  mov     [rsp+78h+var_50], 1
0x18002b37c  mov     [rsp+78h+var_58], rax
0x18002b381  call    NetpAccessCheckAndAuditEx
0x18002b386  test    eax, eax
0x18002b388  jz      short loc_18002B391
0x18002b38a  mov     eax, 5
0x18002b38f  jmp     short loc_18002B409
0x18002b391  mov     rdx, [rsp+78h+arg_20]
0x18002b399  lea     r9, [rsp+78h+var_38]
0x18002b39e  xor     r8d, r8d
0x18002b3a1  mov     rcx, rsi
0x18002b3a4  call    JoinpDecryptPasswordWithKey
0x18002b3a9  mov     rdi, [rsp+78h+var_38]
0x18002b3ae  mov     ebx, eax
0x18002b3b0  test    eax, eax
0x18002b3b2  jz      short loc_18002B3D4
0x18002b3b4  call    IsNetpManageIPCConnectPresent
0x18002b3b9  test    al, al
0x18002b3bb  jz      short loc_18002B3FA
0x18002b3bd  mov     edx, ebx
0x18002b3bf  lea     rcx, aNetrsetprimary; "NetrSetPrimaryComputerName: JoinpDecryp"...
0x18002b3c6  call    cs:__imp_NetpLogPrintHelper
0x18002b3cd  nop     dword ptr [rax+rax+00h]
0x18002b3d2  jmp     short loc_18002B3FA
0x18002b3d4  mov     eax, [rsp+78h+arg_28]
0x18002b3db  mov     r9, rbp
0x18002b3de  mov     [rsp+78h+var_50], eax
0x18002b3e2  mov     r8d, 3
0x18002b3e8  mov     rdx, r14
0x18002b3eb  mov     [rsp+78h+var_58], rdi
0x18002b3f0  mov     rcx, rsi
0x18002b3f3  call    NetpManageAltComputerName
0x18002b3f8  mov     ebx, eax
0x18002b3fa  test    rdi, rdi
0x18002b3fd  jz      short loc_18002B407
0x18002b3ff  mov     rcx, rdi
0x18002b402  call    NetpMemoryFree
0x18002b407  mov     eax, ebx
0x18002b409  add     rsp, 50h
0x18002b40d  pop     r14
0x18002b40f  pop     rdi
0x18002b410  pop     rsi
0x18002b411  pop     rbp
0x18002b412  pop     rbx
0x18002b413  retn
```
