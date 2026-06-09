# IsTelemetryInPrivate(void)

- ea: `0x1800791d4`
- end: `0x1800792a1`
- name: `?IsTelemetryInPrivate@@YA_NXZ`
- size: `205`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180043f64`

## callees

- `0x180048554`
- `0x1800791d4`

## import_xrefs

- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18007926b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ` at `0x18007926b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18007925b`
- `iertutil!__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ` at `0x18007925b`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18007922f`
- `iertutil!__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ` at `0x18007922f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180079205`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007921f`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x180079205`
- `iertutil!__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z` at `0x18007921f`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800791f2`
- `iertutil!__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z` at `0x1800791f2`

## string_xrefs

- `0x180079244`: `onecoreuap\inetcore\lib\tracelogging\legacydll.cpp`

## pseudocode

```c
char IsTelemetryInPrivate(void)
{
  int DWORD; // edi
  const char *v1; // r9
  char v2; // bl
  bool v3; // al
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( dword_180092DBC != 2 )
    return dword_180092DBC == 1;
  DWORD = IEConfiguration_GetDWORD(268435501);
  if ( (unsigned __int8)IEConfiguration_GetBool(536870914) || DWORD != 2 )
  {
    v2 = 1;
    if ( LCIEIsCurrentProcessInPrivateOverrideSet() )
    {
      v3 = LCIEIsCurrentProcessInPrivate();
      v2 = v3;
      if ( DWORD != 3 )
        dword_180092DBC = v3;
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
0x1800791d4  mov     [rsp+arg_0], rbx
0x1800791d9  push    rdi
0x1800791da  sub     rsp, 20h
0x1800791de  mov     eax, cs:dword_180092DBC
0x1800791e4  cmp     eax, 2
0x1800791e7  jnz     loc_180079289
0x1800791ed  mov     ecx, 1000002Dh
0x1800791f2  call    cs:__imp_?IEConfiguration_GetDWORD@@YAKW4IEConfigurationID@@@Z; IEConfiguration_GetDWORD(IEConfigurationID)
0x1800791f9  nop     dword ptr [rax+rax+00h]
0x1800791fe  mov     ecx, 20000002h
0x180079203  mov     edi, eax
0x180079205  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x18007920c  nop     dword ptr [rax+rax+00h]
0x180079211  test    al, al
0x180079213  jnz     short loc_180079256
0x180079215  cmp     edi, 2
0x180079218  jnz     short loc_180079256
0x18007921a  mov     ecx, 10000038h
0x18007921f  call    cs:__imp_?IEConfiguration_GetBool@@YA_NW4IEConfigurationID@@@Z; IEConfiguration_GetBool(IEConfigurationID)
0x180079226  nop     dword ptr [rax+rax+00h]
0x18007922b  test    al, al
0x18007922d  jz      short loc_18007923F
0x18007922f  call    cs:__imp_?LCIEIsCurrentProcessUsingInPrivateComponents@@YA_NXZ; LCIEIsCurrentProcessUsingInPrivateComponents(void)
0x180079236  nop     dword ptr [rax+rax+00h]
0x18007923b  mov     bl, al
0x18007923d  jmp     short loc_180079293
0x18007923f  mov     rcx, [rsp+28h]; this
0x180079244  lea     r8, aOnecoreuapInet; "onecoreuap\\inetcore\\lib\\tracelogging"...
0x18007924b  mov     edx, 10h; void *
0x180079250  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x180079256  mov     ebx, 1
0x18007925b  call    cs:__imp_?LCIEIsCurrentProcessInPrivateOverrideSet@@YA_NXZ; LCIEIsCurrentProcessInPrivateOverrideSet(void)
0x180079262  nop     dword ptr [rax+rax+00h]
0x180079267  test    al, al
0x180079269  jz      short loc_180079293
0x18007926b  call    cs:__imp_?LCIEIsCurrentProcessInPrivate@@YA_NXZ; LCIEIsCurrentProcessInPrivate(void)
0x180079272  nop     dword ptr [rax+rax+00h]
0x180079277  mov     bl, al
0x180079279  cmp     edi, 3
0x18007927c  jz      short loc_180079293
0x18007927e  movzx   eax, al
0x180079281  mov     cs:dword_180092DBC, eax
0x180079287  jmp     short loc_180079293
0x180079289  mov     ebx, 1
0x18007928e  cmp     eax, ebx
0x180079290  setz    bl
0x180079293  mov     al, bl
0x180079295  mov     rbx, [rsp+28h+arg_0]
0x18007929a  add     rsp, 20h
0x18007929e  pop     rdi
0x18007929f  retn
```
