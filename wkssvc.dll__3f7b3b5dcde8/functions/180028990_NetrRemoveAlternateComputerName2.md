# NetrRemoveAlternateComputerName2

- ea: `0x180028990`
- end: `0x180028a6e`
- name: `NetrRemoveAlternateComputerName2`
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
- `0x180028990`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a26`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028a26`

## string_xrefs

- `0x180028a1f`: `NetrRemoveAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveAlternateComputerName2(
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
          NetpLogPrintHelper(L"NetrRemoveAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v13);
      }
      else
      {
        v13 = NetpManageAltComputerName((__int64)a1, a3, 2u, a4, v14, a6);
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
0x180028990  push    rbx
0x180028992  push    rbp
0x180028993  push    rsi
0x180028994  push    rdi
0x180028995  push    r14
0x180028997  sub     rsp, 50h
0x18002899b  mov     rbp, r9
0x18002899e  mov     [rsp+78h+var_38], 0
0x1800289a7  mov     r14, r8
0x1800289aa  mov     rsi, rcx
0x1800289ad  call    WsValidateRpcProtSeq
0x1800289b2  test    eax, eax
0x1800289b4  jnz     loc_180028A63
0x1800289ba  mov     rax, cs:NetApiSd
0x1800289c1  lea     rcx, WsNetApiMapping
0x1800289c8  mov     [rsp+78h+var_48], rcx
0x1800289cd  lea     r8, aNetapi; "NetAPI"
0x1800289d4  mov     [rsp+78h+var_50], 1
0x1800289dc  mov     [rsp+78h+var_58], rax
0x1800289e1  call    NetpAccessCheckAndAuditEx
0x1800289e6  test    eax, eax
0x1800289e8  jz      short loc_1800289F1
0x1800289ea  mov     eax, 5
0x1800289ef  jmp     short loc_180028A63
0x1800289f1  mov     rdx, [rsp+78h+arg_20]
0x1800289f9  lea     r9, [rsp+78h+var_38]
0x1800289fe  xor     r8d, r8d
0x180028a01  mov     rcx, rsi
0x180028a04  call    JoinpDecryptPasswordWithKeyAES
0x180028a09  mov     rdi, [rsp+78h+var_38]
0x180028a0e  mov     ebx, eax
0x180028a10  test    eax, eax
0x180028a12  jz      short loc_180028A2E
0x180028a14  call    IsNetpManageIPCConnectPresent
0x180028a19  test    al, al
0x180028a1b  jz      short loc_180028A54
0x180028a1d  mov     edx, ebx
0x180028a1f  lea     rcx, aNetrremovealte; "NetrRemoveAlternateComputerName2: Joinp"...
0x180028a26  call    cs:__imp_NetpLogPrintHelper
0x180028a2c  jmp     short loc_180028A54
0x180028a2e  mov     eax, [rsp+78h+arg_28]
0x180028a35  mov     r9, rbp
0x180028a38  mov     [rsp+78h+var_50], eax
0x180028a3c  mov     r8d, 2
0x180028a42  mov     rdx, r14
0x180028a45  mov     [rsp+78h+var_58], rdi
0x180028a4a  mov     rcx, rsi
0x180028a4d  call    NetpManageAltComputerName
0x180028a52  mov     ebx, eax
0x180028a54  test    rdi, rdi
0x180028a57  jz      short loc_180028A61
0x180028a59  mov     rcx, rdi
0x180028a5c  call    NetpMemoryFree
0x180028a61  mov     eax, ebx
0x180028a63  add     rsp, 50h
0x180028a67  pop     r14
0x180028a69  pop     rdi
0x180028a6a  pop     rsi
0x180028a6b  pop     rbp
0x180028a6c  pop     rbx
0x180028a6d  retn
```
