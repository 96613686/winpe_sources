# NetpWkstarClientCertificateMappingRemove

- ea: `0x180023dc0`
- end: `0x180023e4e`
- name: `NetpWkstarClientCertificateMappingRemove`
- size: `142`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000a240`
- `0x180021ea8`
- `0x180023dc0`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180023e0f`
- `ntdll!RtlAcquireResourceExclusive` at `0x180023e0f`
- `ntdll!RtlReleaseResource` at `0x180023e34`
- `ntdll!RtlReleaseResource` at `0x180023e34`

## string_xrefs

- `0x180023de8`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetpWkstarClientCertificateMappingRemove(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned int v4; // edi
  unsigned int v6; // ebx

  v4 = a2;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  RtlAcquireResourceExclusive(&stru_180051B90, 1u);
  v6 = ClientCertificateMappingActionImpl(a3, v4, 1);
  RtlReleaseResource(&stru_180051B90);
  return v6;
}

```

## disassembly

```asm
0x180023dc0  mov     [rsp+arg_0], rbx
0x180023dc5  push    rdi
0x180023dc6  sub     rsp, 40h
0x180023dca  mov     rax, cs:ConfigurationInfoSd
0x180023dd1  lea     rcx, WsConfigInfoMapping
0x180023dd8  mov     [rsp+48h+var_18], rcx
0x180023ddd  mov     rbx, r8
0x180023de0  mov     [rsp+48h+var_20], 8
0x180023de8  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x180023def  mov     [rsp+48h+var_28], rax
0x180023df4  mov     edi, edx
0x180023df6  call    NetpAccessCheckAndAuditEx
0x180023dfb  test    eax, eax
0x180023dfd  jz      short loc_180023E06
0x180023dff  mov     eax, 5
0x180023e04  jmp     short loc_180023E42
0x180023e06  mov     dl, 1; Wait
0x180023e08  lea     rcx, stru_180051B90; Resource
0x180023e0f  call    cs:__imp_RtlAcquireResourceExclusive
0x180023e16  nop     dword ptr [rax+rax+00h]
0x180023e1b  mov     r8d, 1
0x180023e21  mov     edx, edi
0x180023e23  mov     rcx, rbx
0x180023e26  call    ClientCertificateMappingActionImpl
0x180023e2b  lea     rcx, stru_180051B90; Resource
0x180023e32  mov     ebx, eax
0x180023e34  call    cs:__imp_RtlReleaseResource
0x180023e3b  nop     dword ptr [rax+rax+00h]
0x180023e40  mov     eax, ebx
0x180023e42  mov     rbx, [rsp+48h+arg_0]
0x180023e47  add     rsp, 40h
0x180023e4b  pop     rdi
0x180023e4c  retn
```
