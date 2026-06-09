# NetpWkstarClientCertificateMappingAdd

- ea: `0x180022d50`
- end: `0x180022dc0`
- name: `NetpWkstarClientCertificateMappingAdd`
- size: `112`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x18000a240`
- `0x180022510`
- `0x180022d50`

## string_xrefs

- `0x180022d7d`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingAdd(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int v6; // esi

  v4 = a3 != 0 ? 2 : 0;
  v6 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  else
    return I_ClientCertificateMappingAdd(v6, a4, v4);
}

```

## disassembly

```asm
0x180022d50  mov     r11, rsp
0x180022d53  mov     [r11+8], rbx
0x180022d57  mov     [r11+10h], rsi
0x180022d5b  push    rdi
0x180022d5c  sub     rsp, 40h
0x180022d60  mov     rax, cs:ConfigurationInfoSd
0x180022d67  lea     rcx, WsConfigInfoMapping
0x180022d6e  neg     r8d
0x180022d71  mov     [r11-18h], rcx
0x180022d75  mov     [rsp+48h+var_20], 8
0x180022d7d  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180022d84  sbb     ebx, ebx
0x180022d86  mov     [r11-28h], rax
0x180022d8a  and     ebx, 2
0x180022d8d  mov     rdi, r9
0x180022d90  mov     esi, edx
0x180022d92  call    NetpAccessCheckAndAuditEx
0x180022d97  test    eax, eax
0x180022d99  jz      short loc_180022DA2
0x180022d9b  mov     eax, 5
0x180022da0  jmp     short loc_180022DAF
0x180022da2  mov     r8d, ebx
0x180022da5  mov     rdx, rdi
0x180022da8  mov     ecx, esi
0x180022daa  call    I_ClientCertificateMappingAdd
0x180022daf  mov     rbx, [rsp+48h+arg_0]
0x180022db4  mov     rsi, [rsp+48h+arg_8]
0x180022db9  add     rsp, 40h
0x180022dbd  pop     rdi
0x180022dbe  retn
```
