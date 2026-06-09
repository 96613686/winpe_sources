# NetrAddAlternateComputerName

- ea: `0x180029fc0`
- end: `0x18002a0a5`
- name: `NetrAddAlternateComputerName`
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
- `0x180029fc0`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a056`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a056`

## string_xrefs

- `0x18002a04f`: `NetrAddAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrAddAlternateComputerName(
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
          NetpLogPrintHelper(L"NetrAddAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
      }
      else
      {
        v14 = NetpManageAltComputerName(a1, a3, 1u, a4, v15, a6);
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
0x180029fc0  push    rbx
0x180029fc2  push    rbp
0x180029fc3  push    rsi
0x180029fc4  push    rdi
0x180029fc5  push    r14
0x180029fc7  sub     rsp, 50h
0x180029fcb  mov     rbp, r9
0x180029fce  mov     [rsp+78h+var_38], 0
0x180029fd7  mov     r14, r8
0x180029fda  mov     rsi, rcx
0x180029fdd  call    WsValidateRpcProtSeq
0x180029fe2  test    eax, eax
0x180029fe4  jnz     loc_18002A099
0x180029fea  mov     rax, cs:NetApiSd
0x180029ff1  lea     rcx, WsNetApiMapping
0x180029ff8  mov     [rsp+78h+var_48], rcx
0x180029ffd  lea     r8, aNetapi; "NetAPI"
0x18002a004  mov     [rsp+78h+var_50], 1
0x18002a00c  mov     [rsp+78h+var_58], rax
0x18002a011  call    NetpAccessCheckAndAuditEx
0x18002a016  test    eax, eax
0x18002a018  jz      short loc_18002A021
0x18002a01a  mov     eax, 5
0x18002a01f  jmp     short loc_18002A099
0x18002a021  mov     rdx, [rsp+78h+arg_20]
0x18002a029  lea     r9, [rsp+78h+var_38]
0x18002a02e  xor     r8d, r8d
0x18002a031  mov     rcx, rsi
0x18002a034  call    JoinpDecryptPasswordWithKey
0x18002a039  mov     rdi, [rsp+78h+var_38]
0x18002a03e  mov     ebx, eax
0x18002a040  test    eax, eax
0x18002a042  jz      short loc_18002A064
0x18002a044  call    IsNetpManageIPCConnectPresent
0x18002a049  test    al, al
0x18002a04b  jz      short loc_18002A08A
0x18002a04d  mov     edx, ebx
0x18002a04f  lea     rcx, aNetraddalterna; "NetrAddAlternateComputerName: JoinpDecr"...
0x18002a056  call    cs:__imp_NetpLogPrintHelper
0x18002a05d  nop     dword ptr [rax+rax+00h]
0x18002a062  jmp     short loc_18002A08A
0x18002a064  mov     eax, [rsp+78h+arg_28]
0x18002a06b  mov     r9, rbp
0x18002a06e  mov     [rsp+78h+var_50], eax
0x18002a072  mov     r8d, 1
0x18002a078  mov     rdx, r14
0x18002a07b  mov     [rsp+78h+var_58], rdi
0x18002a080  mov     rcx, rsi
0x18002a083  call    NetpManageAltComputerName
0x18002a088  mov     ebx, eax
0x18002a08a  test    rdi, rdi
0x18002a08d  jz      short loc_18002A097
0x18002a08f  mov     rcx, rdi
0x18002a092  call    NetpMemoryFree
0x18002a097  mov     eax, ebx
0x18002a099  add     rsp, 50h
0x18002a09d  pop     r14
0x18002a09f  pop     rdi
0x18002a0a0  pop     rsi
0x18002a0a1  pop     rbp
0x18002a0a2  pop     rbx
0x18002a0a3  retn
```
