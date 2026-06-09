# NetpWkstarClientCertificateMappingAdd

- ea: `0x1800214c0`
- end: `0x18002152f`
- name: `NetpWkstarClientCertificateMappingAdd`
- size: `111`
- prototype: `__int64 __fastcall(__int64, __int64, int, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callees

- `0x180009a40`
- `0x180020d14`
- `0x1800214c0`

## string_xrefs

- `0x1800214ed`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingAdd(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  unsigned int v4; // ebx
  unsigned int v6; // esi

  v4 = a3 != 0 ? 2 : 0;
  v6 = a2;
  if ( (unsigned int)NetpAccessCheckAndAuditEx(&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  else
    return I_ClientCertificateMappingAdd(v6, a4, v4);
}

```

## disassembly

```asm
0x1800214c0  mov     r11, rsp
0x1800214c3  mov     [r11+8], rbx
0x1800214c7  mov     [r11+10h], rsi
0x1800214cb  push    rdi
0x1800214cc  sub     rsp, 40h
0x1800214d0  mov     rax, cs:ConfigurationInfoSd
0x1800214d7  lea     rcx, WsConfigInfoMapping
0x1800214de  neg     r8d
0x1800214e1  mov     [r11-18h], rcx
0x1800214e5  mov     [rsp+48h+var_20], 8
0x1800214ed  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x1800214f4  sbb     ebx, ebx
0x1800214f6  mov     [r11-28h], rax
0x1800214fa  and     ebx, 2
0x1800214fd  mov     rdi, r9
0x180021500  mov     esi, edx
0x180021502  call    NetpAccessCheckAndAuditEx
0x180021507  test    eax, eax
0x180021509  jz      short loc_180021512
0x18002150b  mov     eax, 5
0x180021510  jmp     short loc_18002151F
0x180021512  mov     r8d, ebx
0x180021515  mov     rdx, rdi
0x180021518  mov     ecx, esi
0x18002151a  call    I_ClientCertificateMappingAdd
0x18002151f  mov     rbx, [rsp+48h+arg_0]
0x180021524  mov     rsi, [rsp+48h+arg_8]
0x180021529  add     rsp, 40h
0x18002152d  pop     rdi
0x18002152e  retn
```
