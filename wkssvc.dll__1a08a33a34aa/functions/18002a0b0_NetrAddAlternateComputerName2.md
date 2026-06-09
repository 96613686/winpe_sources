# NetrAddAlternateComputerName2

- ea: `0x18002a0b0`
- end: `0x18002a195`
- name: `NetrAddAlternateComputerName2`
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
- `0x18002a0b0`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a146`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002a146`

## string_xrefs

- `0x18002a13f`: `NetrAddAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrAddAlternateComputerName2(
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
          NetpLogPrintHelper(L"NetrAddAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
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
0x18002a0b0  push    rbx
0x18002a0b2  push    rbp
0x18002a0b3  push    rsi
0x18002a0b4  push    rdi
0x18002a0b5  push    r14
0x18002a0b7  sub     rsp, 50h
0x18002a0bb  mov     rbp, r9
0x18002a0be  mov     [rsp+78h+var_38], 0
0x18002a0c7  mov     r14, r8
0x18002a0ca  mov     rsi, rcx
0x18002a0cd  call    WsValidateRpcProtSeq
0x18002a0d2  test    eax, eax
0x18002a0d4  jnz     loc_18002A189
0x18002a0da  mov     rax, cs:NetApiSd
0x18002a0e1  lea     rcx, WsNetApiMapping
0x18002a0e8  mov     [rsp+78h+var_48], rcx
0x18002a0ed  lea     r8, aNetapi; "NetAPI"
0x18002a0f4  mov     [rsp+78h+var_50], 1
0x18002a0fc  mov     [rsp+78h+var_58], rax
0x18002a101  call    NetpAccessCheckAndAuditEx
0x18002a106  test    eax, eax
0x18002a108  jz      short loc_18002A111
0x18002a10a  mov     eax, 5
0x18002a10f  jmp     short loc_18002A189
0x18002a111  mov     rdx, [rsp+78h+arg_20]
0x18002a119  lea     r9, [rsp+78h+var_38]
0x18002a11e  xor     r8d, r8d
0x18002a121  mov     rcx, rsi
0x18002a124  call    JoinpDecryptPasswordWithKeyAES
0x18002a129  mov     rdi, [rsp+78h+var_38]
0x18002a12e  mov     ebx, eax
0x18002a130  test    eax, eax
0x18002a132  jz      short loc_18002A154
0x18002a134  call    IsNetpManageIPCConnectPresent
0x18002a139  test    al, al
0x18002a13b  jz      short loc_18002A17A
0x18002a13d  mov     edx, ebx
0x18002a13f  lea     rcx, aNetraddalterna_0; "NetrAddAlternateComputerName2: JoinpDec"...
0x18002a146  call    cs:__imp_NetpLogPrintHelper
0x18002a14d  nop     dword ptr [rax+rax+00h]
0x18002a152  jmp     short loc_18002A17A
0x18002a154  mov     eax, [rsp+78h+arg_28]
0x18002a15b  mov     r9, rbp
0x18002a15e  mov     [rsp+78h+var_50], eax
0x18002a162  mov     r8d, 1
0x18002a168  mov     rdx, r14
0x18002a16b  mov     [rsp+78h+var_58], rdi
0x18002a170  mov     rcx, rsi
0x18002a173  call    NetpManageAltComputerName
0x18002a178  mov     ebx, eax
0x18002a17a  test    rdi, rdi
0x18002a17d  jz      short loc_18002A187
0x18002a17f  mov     rcx, rdi
0x18002a182  call    NetpMemoryFree
0x18002a187  mov     eax, ebx
0x18002a189  add     rsp, 50h
0x18002a18d  pop     r14
0x18002a18f  pop     rdi
0x18002a190  pop     rsi
0x18002a191  pop     rbp
0x18002a192  pop     rbx
0x18002a193  retn
```
