# NetrRemoveAlternateComputerName2

- ea: `0x18002ad80`
- end: `0x18002ae65`
- name: `NetrRemoveAlternateComputerName2`
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
- `0x18002ad80`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002ae16`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x18002ae16`

## string_xrefs

- `0x18002ae0f`: `NetrRemoveAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveAlternateComputerName2(
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
          NetpLogPrintHelper(L"NetrRemoveAlternateComputerName2: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v14);
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
0x18002ad80  push    rbx
0x18002ad82  push    rbp
0x18002ad83  push    rsi
0x18002ad84  push    rdi
0x18002ad85  push    r14
0x18002ad87  sub     rsp, 50h
0x18002ad8b  mov     rbp, r9
0x18002ad8e  mov     [rsp+78h+var_38], 0
0x18002ad97  mov     r14, r8
0x18002ad9a  mov     rsi, rcx
0x18002ad9d  call    WsValidateRpcProtSeq
0x18002ada2  test    eax, eax
0x18002ada4  jnz     loc_18002AE59
0x18002adaa  mov     rax, cs:NetApiSd
0x18002adb1  lea     rcx, WsNetApiMapping
0x18002adb8  mov     [rsp+78h+var_48], rcx
0x18002adbd  lea     r8, aNetapi; "NetAPI"
0x18002adc4  mov     [rsp+78h+var_50], 1
0x18002adcc  mov     [rsp+78h+var_58], rax
0x18002add1  call    NetpAccessCheckAndAuditEx
0x18002add6  test    eax, eax
0x18002add8  jz      short loc_18002ADE1
0x18002adda  mov     eax, 5
0x18002addf  jmp     short loc_18002AE59
0x18002ade1  mov     rdx, [rsp+78h+arg_20]
0x18002ade9  lea     r9, [rsp+78h+var_38]
0x18002adee  xor     r8d, r8d
0x18002adf1  mov     rcx, rsi
0x18002adf4  call    JoinpDecryptPasswordWithKeyAES
0x18002adf9  mov     rdi, [rsp+78h+var_38]
0x18002adfe  mov     ebx, eax
0x18002ae00  test    eax, eax
0x18002ae02  jz      short loc_18002AE24
0x18002ae04  call    IsNetpManageIPCConnectPresent
0x18002ae09  test    al, al
0x18002ae0b  jz      short loc_18002AE4A
0x18002ae0d  mov     edx, ebx
0x18002ae0f  lea     rcx, aNetrremovealte; "NetrRemoveAlternateComputerName2: Joinp"...
0x18002ae16  call    cs:__imp_NetpLogPrintHelper
0x18002ae1d  nop     dword ptr [rax+rax+00h]
0x18002ae22  jmp     short loc_18002AE4A
0x18002ae24  mov     eax, [rsp+78h+arg_28]
0x18002ae2b  mov     r9, rbp
0x18002ae2e  mov     [rsp+78h+var_50], eax
0x18002ae32  mov     r8d, 2
0x18002ae38  mov     rdx, r14
0x18002ae3b  mov     [rsp+78h+var_58], rdi
0x18002ae40  mov     rcx, rsi
0x18002ae43  call    NetpManageAltComputerName
0x18002ae48  mov     ebx, eax
0x18002ae4a  test    rdi, rdi
0x18002ae4d  jz      short loc_18002AE57
0x18002ae4f  mov     rcx, rdi
0x18002ae52  call    NetpMemoryFree
0x18002ae57  mov     eax, ebx
0x18002ae59  add     rsp, 50h
0x18002ae5d  pop     r14
0x18002ae5f  pop     rdi
0x18002ae60  pop     rsi
0x18002ae61  pop     rbp
0x18002ae62  pop     rbx
0x18002ae63  retn
```
