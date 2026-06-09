# NetrRemoveAlternateComputerName

- ea: `0x1800288a0`
- end: `0x18002897e`
- name: `NetrRemoveAlternateComputerName`
- size: `222`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x180007604`
- `0x180009a40`
- `0x18000a0c0`
- `0x18002016c`
- `0x180026088`
- `0x180026840`
- `0x1800288a0`

## import_xrefs

- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028936`
- `ext-ms-win-domainjoin-netjoin-l1-1-0!NetpLogPrintHelper` at `0x180028936`

## string_xrefs

- `0x18002892f`: `NetrRemoveAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n`

## pseudocode

```c
__int64 __fastcall NetrRemoveAlternateComputerName(__int64 a1, __int64 a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  __int64 result; // rax
  __int64 v10; // rdx
  unsigned int v11; // eax
  __int64 v12; // rdi
  unsigned int v13; // ebx
  PSECURITY_DESCRIPTOR v14; // [rsp+20h] [rbp-58h]
  _QWORD v15[7]; // [rsp+40h] [rbp-38h] BYREF

  v15[0] = 0;
  result = WsValidateRpcProtSeq();
  if ( !(_DWORD)result )
  {
    v14 = NetApiSd;
    if ( NetpAccessCheckAndAuditEx((__int64)&WsNetApiMapping, v10, L"NetAPI") )
    {
      return 5;
    }
    else
    {
      v11 = JoinpDecryptPasswordWithKey(a1, a5, 0, v15, v14, 1, &WsNetApiMapping);
      v12 = v15[0];
      v13 = v11;
      if ( v11 )
      {
        if ( (unsigned __int8)IsNetpManageIPCConnectPresent() )
          NetpLogPrintHelper(L"NetrRemoveAlternateComputerName: JoinpDecryptPasswordWithKey failed: 0x%lx\n", v13);
      }
      else
      {
        v13 = NetpManageAltComputerName(a1, a3, 2, a4, v15[0], a6);
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
0x1800288a0  push    rbx
0x1800288a2  push    rbp
0x1800288a3  push    rsi
0x1800288a4  push    rdi
0x1800288a5  push    r14
0x1800288a7  sub     rsp, 50h
0x1800288ab  mov     rbp, r9
0x1800288ae  mov     [rsp+78h+var_38], 0
0x1800288b7  mov     r14, r8
0x1800288ba  mov     rsi, rcx
0x1800288bd  call    WsValidateRpcProtSeq
0x1800288c2  test    eax, eax
0x1800288c4  jnz     loc_180028973
0x1800288ca  mov     rax, cs:NetApiSd
0x1800288d1  lea     rcx, WsNetApiMapping
0x1800288d8  mov     [rsp+78h+var_48], rcx
0x1800288dd  lea     r8, aNetapi; "NetAPI"
0x1800288e4  mov     [rsp+78h+var_50], 1
0x1800288ec  mov     [rsp+78h+var_58], rax
0x1800288f1  call    NetpAccessCheckAndAuditEx
0x1800288f6  test    eax, eax
0x1800288f8  jz      short loc_180028901
0x1800288fa  mov     eax, 5
0x1800288ff  jmp     short loc_180028973
0x180028901  mov     rdx, [rsp+78h+arg_20]
0x180028909  lea     r9, [rsp+78h+var_38]
0x18002890e  xor     r8d, r8d
0x180028911  mov     rcx, rsi
0x180028914  call    JoinpDecryptPasswordWithKey
0x180028919  mov     rdi, [rsp+78h+var_38]
0x18002891e  mov     ebx, eax
0x180028920  test    eax, eax
0x180028922  jz      short loc_18002893E
0x180028924  call    IsNetpManageIPCConnectPresent
0x180028929  test    al, al
0x18002892b  jz      short loc_180028964
0x18002892d  mov     edx, ebx
0x18002892f  lea     rcx, aNetrremovealte_0; "NetrRemoveAlternateComputerName: JoinpD"...
0x180028936  call    cs:__imp_NetpLogPrintHelper
0x18002893c  jmp     short loc_180028964
0x18002893e  mov     eax, [rsp+78h+arg_28]
0x180028945  mov     r9, rbp
0x180028948  mov     [rsp+78h+var_50], eax
0x18002894c  mov     r8d, 2
0x180028952  mov     rdx, r14
0x180028955  mov     [rsp+78h+var_58], rdi
0x18002895a  mov     rcx, rsi
0x18002895d  call    NetpManageAltComputerName
0x180028962  mov     ebx, eax
0x180028964  test    rdi, rdi
0x180028967  jz      short loc_180028971
0x180028969  mov     rcx, rdi
0x18002896c  call    NetpMemoryFree
0x180028971  mov     eax, ebx
0x180028973  add     rsp, 50h
0x180028977  pop     r14
0x180028979  pop     rdi
0x18002897a  pop     rsi
0x18002897b  pop     rbp
0x18002897c  pop     rbx
0x18002897d  retn
```
