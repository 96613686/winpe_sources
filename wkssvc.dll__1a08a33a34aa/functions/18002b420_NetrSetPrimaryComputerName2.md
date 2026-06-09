# NetrSetPrimaryComputerName2

- ea: `0x18002b420`
- end: `0x18002b505`
- name: `NetrSetPrimaryComputerName2`
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
- `0x1800282dc`
- `0x1800288a8`
- `0x18002b420`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002b4b6`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002b4b6`

## string_xrefs

- `0x18002b4af`: `NetrSetPrimaryComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrSetPrimaryComputerName2(
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
      v11 = JoinpDecryptPasswordWithKeyAES(a1, a5, 0, &v15);
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
0x18002b420  push    rbx
0x18002b422  push    rbp
0x18002b423  push    rsi
0x18002b424  push    rdi
0x18002b425  push    r14
0x18002b427  sub     rsp, 50h
0x18002b42b  mov     rbp, r9
0x18002b42e  mov     [rsp+78h+var_38], 0
0x18002b437  mov     r14, r8
0x18002b43a  mov     rsi, rcx
0x18002b43d  call    WsValidateRpcProtSeq
0x18002b442  test    eax, eax
0x18002b444  jnz     loc_18002B4F9
0x18002b44a  mov     rax, cs:NetApiSd
0x18002b451  lea     rcx, WsNetApiMapping
0x18002b458  mov     [rsp+78h+var_48], rcx
0x18002b45d  lea     r8, aNetapi; "NetAPI"
0x18002b464  mov     [rsp+78h+var_50], 1
0x18002b46c  mov     [rsp+78h+var_58], rax
0x18002b471  call    NetpAccessCheckAndAuditEx
0x18002b476  test    eax, eax
0x18002b478  jz      short loc_18002B481
0x18002b47a  mov     eax, 5
0x18002b47f  jmp     short loc_18002B4F9
0x18002b481  mov     rdx, [rsp+78h+arg_20]
0x18002b489  lea     r9, [rsp+78h+var_38]
0x18002b48e  xor     r8d, r8d
0x18002b491  mov     rcx, rsi
0x18002b494  call    JoinpDecryptPasswordWithKeyAES
0x18002b499  mov     rdi, [rsp+78h+var_38]
0x18002b49e  mov     ebx, eax
0x18002b4a0  test    eax, eax
0x18002b4a2  jz      short loc_18002B4C4
0x18002b4a4  call    IsNetpManageIPCConnectPresent
0x18002b4a9  test    al, al
0x18002b4ab  jz      short loc_18002B4EA
0x18002b4ad  mov     edx, ebx
0x18002b4af  lea     rcx, aNetrsetprimary; "NetrSetPrimaryComputerName: JoinpDecryp"...
0x18002b4b6  call    cs:__imp_NetpLogPrintHelper
0x18002b4bd  nop     dword ptr [rax+rax+00h]
0x18002b4c2  jmp     short loc_18002B4EA
0x18002b4c4  mov     eax, [rsp+78h+arg_28]
0x18002b4cb  mov     r9, rbp
0x18002b4ce  mov     [rsp+78h+var_50], eax
0x18002b4d2  mov     r8d, 3
0x18002b4d8  mov     rdx, r14
0x18002b4db  mov     [rsp+78h+var_58], rdi
0x18002b4e0  mov     rcx, rsi
0x18002b4e3  call    NetpManageAltComputerName
0x18002b4e8  mov     ebx, eax
0x18002b4ea  test    rdi, rdi
0x18002b4ed  jz      short loc_18002B4F7
0x18002b4ef  mov     rcx, rdi
0x18002b4f2  call    NetpMemoryFree
0x18002b4f7  mov     eax, ebx
0x18002b4f9  add     rsp, 50h
0x18002b4fd  pop     r14
0x18002b4ff  pop     rdi
0x18002b500  pop     rsi
0x18002b501  pop     rbp
0x18002b502  pop     rbx
0x18002b503  retn
```
