# NetrWkstaTransportDel

- ea: `0x18002d0a0`
- end: `0x18002d117`
- name: `NetrWkstaTransportDel`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005df0`
- `0x18000a240`
- `0x18002d0a0`

## string_xrefs

- `0x18002d0c8`: `WkstaConfigurationInfo`

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
0x18002d0a0  mov     [rsp+arg_0], rbx
0x18002d0a5  push    rdi
0x18002d0a6  sub     rsp, 40h
0x18002d0aa  mov     rax, cs:ConfigurationInfoSd
0x18002d0b1  lea     rcx, WsConfigInfoMapping
0x18002d0b8  mov     [rsp+48h+var_18], rcx
0x18002d0bd  mov     ebx, r8d
0x18002d0c0  mov     [rsp+48h+var_20], 8
0x18002d0c8  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002d0cf  mov     [rsp+48h+var_28], rax
0x18002d0d4  mov     rdi, rdx
0x18002d0d7  call    NetpAccessCheckAndAuditEx
0x18002d0dc  test    eax, eax
0x18002d0de  jz      short loc_18002D0E7
0x18002d0e0  mov     eax, 5
0x18002d0e5  jmp     short loc_18002D10B
0x18002d0e7  test    rdi, rdi
0x18002d0ea  jz      short loc_18002D106
0x18002d0ec  test    ebx, ebx
0x18002d0ee  jz      short loc_18002D0FA
0x18002d0f0  sub     ebx, 1
0x18002d0f3  jz      short loc_18002D0FA
0x18002d0f5  cmp     ebx, 1
0x18002d0f8  jnz     short loc_18002D106
0x18002d0fa  mov     ecx, 0C0000010h
0x18002d0ff  call    WsMapStatus
0x18002d104  jmp     short loc_18002D10B
0x18002d106  mov     eax, 57h ; 'W'
0x18002d10b  mov     rbx, [rsp+48h+arg_0]
0x18002d110  add     rsp, 40h
0x18002d114  pop     rdi
0x18002d115  retn
```
