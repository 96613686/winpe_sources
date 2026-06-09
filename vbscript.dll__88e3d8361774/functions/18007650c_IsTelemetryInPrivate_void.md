# IsTelemetryInPrivate(void)

- ea: `0x18007650c`
- end: `0x1800765b0`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `164`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800428e4`

## callees

- `0x1800470c0`
- `0x18007650c`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180076581`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x180076581`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180076577`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x180076577`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180076551`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x180076551`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076533`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076547`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076533`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180076547`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180076526`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x180076526`

## string_xrefs

- `0x180076560`: `onecoreuap\inetcore\lib\tracelogging\legacydll.cpp`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  const char *v1; // r9
  char v2; // bl
  bool v3; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dword_18008FDBC != 2 )
    return dword_18008FDBC == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_18008FDBC = v3;
    }
  }
  else
  {
    if ( !(unsigned __int8)IEConfiguration_GetBool(268435512) )
      wil::details::in1diag3::FailFast_Unexpected(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecoreuap\\inetcore\\lib\\tracelogging\\legacydll.cpp",
        v1);
    return LCIEIsCurrentProcessUsingInPrivateComponents();
  }
  return v2;
}

```

## disassembly

```asm
0x18007650c  mov     [rsp+arg_0], rbx
0x180076511  push    rdi
0x180076512  sub     rsp, 20h
0x180076516  mov     eax, cs:dword_18008FDBC
0x18007651c  cmp     eax, 2
0x18007651f  jnz     short loc_180076599
0x180076521  mov     ecx, 1000002Dh
0x180076526  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x18007652c  mov     ecx, 20000002h
0x180076531  mov     edi, eax
0x180076533  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180076539  test    al, al
0x18007653b  jnz     short loc_180076572
0x18007653d  cmp     edi, 2
0x180076540  jnz     short loc_180076572
0x180076542  mov     ecx, 10000038h
0x180076547  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007654d  test    al, al
0x18007654f  jz      short loc_18007655B
0x180076551  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180076557  mov     bl, al
0x180076559  jmp     short loc_1800765A3
0x18007655b  mov     rcx, [rsp+28h]; this
0x180076560  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\tracelogging"...
0x180076567  mov     edx, 10h; void *
0x18007656c  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180076572  mov     ebx, 1
0x180076577  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x18007657d  test    al, al
0x18007657f  jz      short loc_1800765A3
0x180076581  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180076587  mov     bl, al
0x180076589  cmp     edi, 3
0x18007658c  jz      short loc_1800765A3
0x18007658e  movzx   eax, al
0x180076591  mov     cs:dword_18008FDBC, eax
0x180076597  jmp     short loc_1800765A3
0x180076599  mov     ebx, 1
0x18007659e  cmp     eax, ebx
0x1800765a0  setz    bl
0x1800765a3  mov     al, bl
0x1800765a5  mov     rbx, [rsp+28h+arg_0]
0x1800765aa  add     rsp, 20h
0x1800765ae  pop     rdi
0x1800765af  retn
```
