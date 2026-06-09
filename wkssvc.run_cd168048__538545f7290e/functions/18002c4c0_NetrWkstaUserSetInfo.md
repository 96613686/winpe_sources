# NetrWkstaUserSetInfo

- ea: `0x18002c4c0`
- end: `0x18002c5a1`
- name: `NetrWkstaUserSetInfo`
- size: `225`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting`

## callees

- `0x18000a240`
- `0x18002c4c0`
- `0x18002c5a8`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18002c542`
- `ntdll!RtlAcquireResourceExclusive` at `0x18002c542`
- `ntdll!RtlReleaseResource` at `0x18002c591`
- `ntdll!RtlReleaseResource` at `0x18002c591`

## string_xrefs

- `0x18002c4ef`: `WkstaConfigurationInfo`

## pseudocode

```c
__int64 __fastcall NetrWkstaUserSetInfo(__int64 a1, __int64 a2, BYTE ***a3, _DWORD *a4)
{
  int v6; // esi
  unsigned int v8; // edi

  v6 = a2;
  if ( a1 )
    return 87;
  if ( NetpAccessCheckAndAuditEx((__int64)&WsConfigInfoMapping, a2, L"WkstaConfigurationInfo") )
    return 5;
  if ( !*a3 )
  {
    if ( a4 )
      *a4 = -1;
    return 87;
  }
  if ( !RtlAcquireResourceExclusive(&WsInfo, 1u) )
    return 2140;
  if ( v6 == 1 || v6 == 1101 )
  {
    v8 = WsSetOtherDomains(v6, *a3);
    if ( v8 == 87 && a4 )
      *a4 = 101;
  }
  else
  {
    v8 = 124;
  }
  RtlReleaseResource(&WsInfo);
  return v8;
}

```

## disassembly

```asm
0x18002c4c0  mov     r11, rsp
0x18002c4c3  mov     [r11+8], rbx
0x18002c4c7  mov     [r11+10h], rsi
0x18002c4cb  push    rdi
0x18002c4cc  sub     rsp, 40h
0x18002c4d0  mov     rbx, r9
0x18002c4d3  mov     rdi, r8
0x18002c4d6  mov     esi, edx
0x18002c4d8  test    rcx, rcx
0x18002c4db  jnz     short loc_18002C523
0x18002c4dd  mov     rax, cs:ConfigurationInfoSd
0x18002c4e4  lea     rcx, WsConfigInfoMapping
0x18002c4eb  mov     [r11-18h], rcx
0x18002c4ef  lea     r8, aWkstaconfigura; "WkstaConfigurationInfo"
0x18002c4f6  mov     [rsp+48h+var_20], 8
0x18002c4fe  mov     [r11-28h], rax
0x18002c502  call    NetpAccessCheckAndAuditEx
0x18002c507  test    eax, eax
0x18002c509  jz      short loc_18002C512
0x18002c50b  mov     eax, 5
0x18002c510  jmp     short loc_18002C528
0x18002c512  cmp     qword ptr [rdi], 0
0x18002c516  jnz     short loc_18002C539
0x18002c518  test    rbx, rbx
0x18002c51b  jz      short loc_18002C523
0x18002c51d  mov     dword ptr [rbx], 0FFFFFFFFh
0x18002c523  mov     eax, 57h ; 'W'
0x18002c528  mov     rbx, [rsp+48h+arg_0]
0x18002c52d  mov     rsi, [rsp+48h+arg_8]
0x18002c532  add     rsp, 40h
0x18002c536  pop     rdi
0x18002c537  retn
0x18002c539  mov     dl, 1; Wait
0x18002c53b  lea     rcx, WsInfo; Resource
0x18002c542  call    cs:__imp_RtlAcquireResourceExclusive
0x18002c549  nop     dword ptr [rax+rax+00h]
0x18002c54e  test    al, al
0x18002c550  jnz     short loc_18002C559
0x18002c552  mov     eax, 85Ch
0x18002c557  jmp     short loc_18002C528
0x18002c559  mov     eax, esi
0x18002c55b  sub     eax, 1
0x18002c55e  jz      short loc_18002C56E
0x18002c560  cmp     eax, 44Ch
0x18002c565  jz      short loc_18002C56E
0x18002c567  mov     edi, 7Ch ; '|'
0x18002c56c  jmp     short loc_18002C58A
0x18002c56e  mov     rdx, [rdi]
0x18002c571  mov     ecx, esi
0x18002c573  call    WsSetOtherDomains
0x18002c578  mov     edi, eax
0x18002c57a  cmp     eax, 57h ; 'W'
0x18002c57d  jnz     short loc_18002C58A
0x18002c57f  test    rbx, rbx
0x18002c582  jz      short loc_18002C58A
0x18002c584  mov     dword ptr [rbx], 65h ; 'e'
0x18002c58a  lea     rcx, WsInfo; Resource
0x18002c591  call    cs:__imp_RtlReleaseResource
0x18002c598  nop     dword ptr [rax+rax+00h]
0x18002c59d  mov     eax, edi
0x18002c59f  jmp     short loc_18002C528
```
