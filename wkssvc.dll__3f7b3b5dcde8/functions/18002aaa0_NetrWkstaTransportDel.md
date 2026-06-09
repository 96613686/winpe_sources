# NetrWkstaTransportDel

- ea: `0x18002aaa0`
- end: `0x18002ab16`
- name: `NetrWkstaTransportDel`
- size: `118`
- prototype: `__int64 __fastcall(__int64, __int64, int)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005a60`
- `0x180009a40`
- `0x18002aaa0`

## string_xrefs

- `0x18002aac8`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaTransportDel(__int64 a1, __int64 a2, int a3)
{
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  if ( !a2 || a3 && (unsigned int)(a3 - 1) > 1 )
    return 87;
  return WsMapStatus(3221225488LL);
}

```

## disassembly

```asm
0x18002aaa0  mov     [rsp+arg_0], rbx
0x18002aaa5  push    rdi
0x18002aaa6  sub     rsp, 40h
0x18002aaaa  mov     rax, cs:ConfigurationInfoSd
0x18002aab1  lea     rcx, WsConfigInfoMapping
0x18002aab8  mov     [rsp+48h+var_18], rcx
0x18002aabd  mov     ebx, r8d
0x18002aac0  mov     [rsp+48h+var_20], 8
0x18002aac8  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002aacf  mov     [rsp+48h+var_28], rax
0x18002aad4  mov     rdi, rdx
0x18002aad7  call    NetpAccessCheckAndAuditEx
0x18002aadc  test    eax, eax
0x18002aade  jz      short loc_18002AAE7
0x18002aae0  mov     eax, 5
0x18002aae5  jmp     short loc_18002AB0B
0x18002aae7  test    rdi, rdi
0x18002aaea  jz      short loc_18002AB06
0x18002aaec  test    ebx, ebx
0x18002aaee  jz      short loc_18002AAFA
0x18002aaf0  sub     ebx, 1
0x18002aaf3  jz      short loc_18002AAFA
0x18002aaf5  cmp     ebx, 1
0x18002aaf8  jnz     short loc_18002AB06
0x18002aafa  mov     ecx, 0C0000010h
0x18002aaff  call    WsMapStatus
0x18002ab04  jmp     short loc_18002AB0B
0x18002ab06  mov     eax, 57h ; 'W'
0x18002ab0b  mov     rbx, [rsp+48h+arg_0]
0x18002ab10  add     rsp, 40h
0x18002ab14  pop     rdi
0x18002ab15  retn
```
