# NetrAddAlternateComputerName2

- ea: `0x180027d80`
- end: `0x180027e5e`
- name: `NetrAddAlternateComputerName2`
- size: `222`
- prototype: `__int64 __fastcall(void *, __int64, const WCHAR *, __int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007604`
- `0x180009a40`
- `0x18000a0c0`
- `0x18002016c`
- `0x180026300`
- `0x180026840`
- `0x180027d80`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027e16`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180027e16`

## string_xrefs

- `0x180027e0f`: `NetrAddAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrAddAlternateComputerName2(
        void *a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  WCHAR *v12; // rdi
  unsigned int v13; // ebx
  WCHAR *v14; // [rsp+40h] [rbp-38h] BYREF

  v14 = 0;
  result = WsValidateRpcProtSeq(a1);
  if ( !(_DWORD)result )
  {
    if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    {
      return 5;
    }
    else
    {
      v11 = JoinpDecryptPasswordWithKeyAES((__int64)a1, a5, 0, (__int64)&v14);
      v12 = v14;
      v13 = v11;
      if ( v11 )
      {
        if ( IsNetpManageIPCConnectPresent() )
          NetpLogPrintHelper(L"NetrAddAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v13);
      }
      else
      {
        v13 = NetpManageAltComputerName((__int64)a1, a3, 1u, a4, v14, a6);
      }
      if ( v12 )
        NetpMemoryFree(v12);
      return v13;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180027d80  push    rbx
0x180027d82  push    rbp
0x180027d83  push    rsi
0x180027d84  push    rdi
0x180027d85  push    r14
0x180027d87  sub     rsp, 50h
0x180027d8b  mov     rbp, r9
0x180027d8e  mov     [rsp+78h+var_38], 0
0x180027d97  mov     r14, r8
0x180027d9a  mov     rsi, rcx
0x180027d9d  call    WsValidateRpcProtSeq
0x180027da2  test    eax, eax
0x180027da4  jnz     loc_180027E53
0x180027daa  mov     rax, cs:NetApiSd
0x180027db1  lea     rcx, WsNetApiMapping
0x180027db8  mov     [rsp+78h+var_48], rcx
0x180027dbd  lea     r8, aNetapi; "NetAPI"
0x180027dc4  mov     [rsp+78h+var_50], 1
0x180027dcc  mov     [rsp+78h+var_58], rax
0x180027dd1  call    NetpAccessCheckAndAuditEx
0x180027dd6  test    eax, eax
0x180027dd8  jz      short loc_180027DE1
0x180027dda  mov     eax, 5
0x180027ddf  jmp     short loc_180027E53
0x180027de1  mov     rdx, [rsp+78h+arg_20]
0x180027de9  lea     r9, [rsp+78h+var_38]
0x180027dee  xor     r8d, r8d
0x180027df1  mov     rcx, rsi
0x180027df4  call    JoinpDecryptPasswordWithKeyAES
0x180027df9  mov     rdi, [rsp+78h+var_38]
0x180027dfe  mov     ebx, eax
0x180027e00  test    eax, eax
0x180027e02  jz      short loc_180027E1E
0x180027e04  call    IsNetpManageIPCConnectPresent
0x180027e09  test    al, al
0x180027e0b  jz      short loc_180027E44
0x180027e0d  mov     edx, ebx
0x180027e0f  lea     rcx, aNetraddalterna_0; "NetrAddAlternateComputerName2: JoinpDec"...
0x180027e16  call    cs:__imp_NetpLogPrintHelper
0x180027e1c  jmp     short loc_180027E44
0x180027e1e  mov     eax, [rsp+78h+arg_28]
0x180027e25  mov     r9, rbp
0x180027e28  mov     [rsp+78h+var_50], eax
0x180027e2c  mov     r8d, 1
0x180027e32  mov     rdx, r14
0x180027e35  mov     [rsp+78h+var_58], rdi
0x180027e3a  mov     rcx, rsi
0x180027e3d  call    NetpManageAltComputerName
0x180027e42  mov     ebx, eax
0x180027e44  test    rdi, rdi
0x180027e47  jz      short loc_180027E51
0x180027e49  mov     rcx, rdi
0x180027e4c  call    NetpMemoryFree
0x180027e51  mov     eax, ebx
0x180027e53  add     rsp, 50h
0x180027e57  pop     r14
0x180027e59  pop     rdi
0x180027e5a  pop     rsi
0x180027e5b  pop     rbp
0x180027e5c  pop     rbx
0x180027e5d  retn
```
