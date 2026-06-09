# NetrRemoveAlternateComputerName

- ea: `0x18002ac90`
- end: `0x18002ad75`
- name: `NetrRemoveAlternateComputerName`
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
- `0x18002ac90`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002ad26`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002ad26`

## string_xrefs

- `0x18002ad1f`: `NetrRemoveAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveAlternateComputerName(
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
          NetpLogPrintHelper(L"NetrRemoveAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
      }
      else
      {
        v14 = NetpManageAltComputerName(a1, a3, 2u, a4, v15, a6);
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
0x18002ac90  push    rbx
0x18002ac92  push    rbp
0x18002ac93  push    rsi
0x18002ac94  push    rdi
0x18002ac95  push    r14
0x18002ac97  sub     rsp, 50h
0x18002ac9b  mov     rbp, r9
0x18002ac9e  mov     [rsp+78h+var_38], 0
0x18002aca7  mov     r14, r8
0x18002acaa  mov     rsi, rcx
0x18002acad  call    WsValidateRpcProtSeq
0x18002acb2  test    eax, eax
0x18002acb4  jnz     loc_18002AD69
0x18002acba  mov     rax, cs:NetApiSd
0x18002acc1  lea     rcx, WsNetApiMapping
0x18002acc8  mov     [rsp+78h+var_48], rcx
0x18002accd  lea     r8, aNetapi; "NetAPI"
0x18002acd4  mov     [rsp+78h+var_50], 1
0x18002acdc  mov     [rsp+78h+var_58], rax
0x18002ace1  call    NetpAccessCheckAndAuditEx
0x18002ace6  test    eax, eax
0x18002ace8  jz      short loc_18002ACF1
0x18002acea  mov     eax, 5
0x18002acef  jmp     short loc_18002AD69
0x18002acf1  mov     rdx, [rsp+78h+arg_20]
0x18002acf9  lea     r9, [rsp+78h+var_38]
0x18002acfe  xor     r8d, r8d
0x18002ad01  mov     rcx, rsi
0x18002ad04  call    JoinpDecryptPasswordWithKey
0x18002ad09  mov     rdi, [rsp+78h+var_38]
0x18002ad0e  mov     ebx, eax
0x18002ad10  test    eax, eax
0x18002ad12  jz      short loc_18002AD34
0x18002ad14  call    IsNetpManageIPCConnectPresent
0x18002ad19  test    al, al
0x18002ad1b  jz      short loc_18002AD5A
0x18002ad1d  mov     edx, ebx
0x18002ad1f  lea     rcx, aNetrremovealte_0; "NetrRemoveAlternateComputerName: JoinpD"...
0x18002ad26  call    cs:__imp_NetpLogPrintHelper
0x18002ad2d  nop     dword ptr [rax+rax+00h]
0x18002ad32  jmp     short loc_18002AD5A
0x18002ad34  mov     eax, [rsp+78h+arg_28]
0x18002ad3b  mov     r9, rbp
0x18002ad3e  mov     [rsp+78h+var_50], eax
0x18002ad42  mov     r8d, 2
0x18002ad48  mov     rdx, r14
0x18002ad4b  mov     [rsp+78h+var_58], rdi
0x18002ad50  mov     rcx, rsi
0x18002ad53  call    NetpManageAltComputerName
0x18002ad58  mov     ebx, eax
0x18002ad5a  test    rdi, rdi
0x18002ad5d  jz      short loc_18002AD67
0x18002ad5f  mov     rcx, rdi
0x18002ad62  call    NetpMemoryFree
0x18002ad67  mov     eax, ebx
0x18002ad69  add     rsp, 50h
0x18002ad6d  pop     r14
0x18002ad6f  pop     rdi
0x18002ad70  pop     rsi
0x18002ad71  pop     rbp
0x18002ad72  pop     rbx
0x18002ad73  retn
```
