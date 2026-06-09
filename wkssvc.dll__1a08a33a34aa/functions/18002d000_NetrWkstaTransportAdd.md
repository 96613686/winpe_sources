# NetrWkstaTransportAdd

- ea: `0x18002d000`
- end: `0x18002d08c`
- name: `NetrWkstaTransportAdd`
- size: `140`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180005df0`
- `0x18000a240`
- `0x18002d000`

## string_xrefs

- `0x18002d02d`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaTransportAdd(__int64 a1, __int64 a2, __int64 a3, _DWORD *a4)
{
  int v6; // esi

  v6 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  if ( v6 )
    return 124;
  if ( *(_QWORD *)(a3 + 8) )
    return WsMapStatus(3221225488LL);
  if ( a4 )
    *a4 = 202;
  return 87;
}

```

## disassembly

```asm
0x18002d000  mov     r11, rsp
0x18002d003  mov     [r11+8], rbx
0x18002d007  mov     [r11+10h], rsi
0x18002d00b  push    rdi
0x18002d00c  sub     rsp, 40h
0x18002d010  mov     rax, cs:ConfigurationInfoSd
0x18002d017  lea     rcx, WsConfigInfoMapping
0x18002d01e  mov     [r11-18h], rcx
0x18002d022  mov     rdi, r8
0x18002d025  mov     [rsp+48h+var_20], 8
0x18002d02d  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002d034  mov     [r11-28h], rax
0x18002d038  mov     rbx, r9
0x18002d03b  mov     esi, edx
0x18002d03d  call    NetpAccessCheckAndAuditEx
0x18002d042  test    eax, eax
0x18002d044  jz      short loc_18002D04D
0x18002d046  mov     eax, 5
0x18002d04b  jmp     short loc_18002D07B
0x18002d04d  test    esi, esi
0x18002d04f  jz      short loc_18002D058
0x18002d051  mov     eax, 7Ch ; '|'
0x18002d056  jmp     short loc_18002D07B
0x18002d058  cmp     qword ptr [rdi+8], 0
0x18002d05d  jnz     short loc_18002D071
0x18002d05f  test    rbx, rbx
0x18002d062  jz      short loc_18002D06A
0x18002d064  mov     dword ptr [rbx], 0CAh
0x18002d06a  mov     eax, 57h ; 'W'
0x18002d06f  jmp     short loc_18002D07B
0x18002d071  mov     ecx, 0C0000010h
0x18002d076  call    WsMapStatus
0x18002d07b  mov     rbx, [rsp+48h+arg_0]
0x18002d080  mov     rsi, [rsp+48h+arg_8]
0x18002d085  add     rsp, 40h
0x18002d089  pop     rdi
0x18002d08a  retn
```
