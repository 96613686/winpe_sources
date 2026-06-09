# RefreshContext::TryExecute__lambda_b6c6b55743265851d8992bb150fd21a9___

- ea: `0x18002dab0`
- end: `0x18002db1b`
- name: `RefreshContext::TryExecute__lambda_b6c6b55743265851d8992bb150fd21a9___`
- size: `107`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config`

## callers

- `0x18002db48`

## callees

- `0x180003110`
- `0x1800101e0`
- `0x18002dab0`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18002dad8`
- `api-ms-win-core-kernel32-legacy-l1-1-0!GetSystemPowerStatus` at `0x18002dad8`

## string_xrefs

- `0x18002dae7`: `onecore\base\flighting\onesettings\libs\configurationsmanager\refreshcontext.cpp`

## pseudocode

```c
__int64 __fastcall RefreshContext::TryExecute__lambda_b6c6b55743265851d8992bb150fd21a9___(__int64 *a1)
{
  BOOL v2; // eax
  const char *v3; // r9
  __int64 result; // rax
  _SYSTEM_POWER_STATUS SystemPowerStatus; // [rsp+20h] [rbp-28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  *(_QWORD *)&SystemPowerStatus.ACLineStatus = 0;
  SystemPowerStatus.BatteryFullLifeTime = 0;
  v2 = GetSystemPowerStatus(&SystemPowerStatus);
  try
  {
    if ( !v2 )
      wil::details::in1diag3::_Throw_GetLastError(
        retaddr,
        (void *)0xE7,
        (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
        v3);
    result = *a1;
    *(_BYTE *)(*a1 + 9) = SystemPowerStatus.ACLineStatus == 0;
  }
  catch ( ... )
  {
    return wil::details::in1diag3::Log_CaughtException(
             retaddr,
             (void *)0x11B,
             (unsigned int)"onecore\\base\\flighting\\onesettings\\libs\\configurationsmanager\\refreshcontext.cpp",
             v3);
  }
  return result;
}

```

## disassembly

```asm
0x18002dab0  push    rbx
0x18002dab2  sub     rsp, 40h
0x18002dab6  mov     rax, cs:__security_cookie
0x18002dabd  xor     rax, rsp
0x18002dac0  mov     [rsp+48h+var_18], rax
0x18002dac5  mov     rbx, rcx
0x18002dac8  xor     eax, eax
0x18002daca  mov     qword ptr [rsp+48h+SystemPowerStatus.ACLineStatus], rax
0x18002dacf  mov     [rsp+48h+SystemPowerStatus.BatteryFullLifeTime], eax
0x18002dad3  lea     rcx, [rsp+48h+SystemPowerStatus]; lpSystemPowerStatus
0x18002dad8  call    cs:__imp_GetSystemPowerStatus
0x18002dade  mov     rcx, [rsp+48h]; this
0x18002dae3  test    eax, eax
0x18002dae5  jnz     short loc_18002DAF8
0x18002dae7  lea     r8, aOnecoreBaseFli_20; "onecore\\base\\flighting\\onesettings\\"...
0x18002daee  mov     edx, 0E7h; void *
0x18002daf3  call    ?_Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_GetLastError(void *,uint,char const *)
0x18002daf8  cmp     [rsp+48h+SystemPowerStatus.ACLineStatus], 0
0x18002dafd  setz    cl
0x18002db00  mov     rax, [rbx]
0x18002db03  mov     [rax+9], cl
0x18002db06  jmp     short $+2
0x18002db08  mov     rcx, [rsp+48h+var_18]
0x18002db0d  xor     rcx, rsp; StackCookie
0x18002db10  call    __security_check_cookie
0x18002db15  add     rsp, 40h
0x18002db19  pop     rbx
0x18002db1a  retn
```
