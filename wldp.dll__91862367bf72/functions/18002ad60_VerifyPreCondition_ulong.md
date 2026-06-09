# VerifyPreCondition(ulong *)

- ea: `0x18002ad60`
- end: `0x18002addd`
- name: `?VerifyPreCondition@@YAJPEAK@Z`
- size: `125`
- prototype: `__int64 __fastcall(unsigned int *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d220`

## callees

- `0x18001b50c`
- `0x18002ad60`
- `0x18002b390`
- `0x18002b670`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ada6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ada6`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18002ad9c`
- `api-ms-win-core-sysinfo-l1-2-3!GetOsManufacturingMode` at `0x18002ad9c`

## string_xrefs

- `0x18002adc4`: `TEST FAIL: ManufacturingMode is on\n`

## pseudocode

```c
signed int __fastcall VerifyPreCondition(unsigned int *a1)
{
  signed int result; // eax
  int v3; // [rsp+38h] [rbp+10h] BYREF
  int v4; // [rsp+40h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  CheckRetailUnlock(1, &v3);
  if ( v3 )
  {
    *a1 |= 2u;
    WldpResetProductionConfiguration();
  }
  if ( (unsigned int)GetOsManufacturingMode(&v4) )
  {
    if ( v4 )
    {
      *a1 |= 2u;
      LogFormatOut("TEST FAIL: ManufacturingMode is on\n");
      WldpResetProductionConfiguration();
    }
    return 0;
  }
  else
  {
    result = GetLastError();
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
  }
  return result;
}

```

## disassembly

```asm
0x18002ad60  push    rbx
0x18002ad62  sub     rsp, 20h
0x18002ad66  mov     rbx, rcx
0x18002ad69  mov     [rsp+28h+arg_8], 0
0x18002ad71  mov     ecx, 1; int
0x18002ad76  mov     [rsp+28h+arg_10], 0
0x18002ad7e  lea     rdx, [rsp+28h+arg_8]; int *
0x18002ad83  call    ?CheckRetailUnlock@@YAJHPEAH@Z; CheckRetailUnlock(int,int *)
0x18002ad88  cmp     [rsp+28h+arg_8], 0
0x18002ad8d  jz      short loc_18002AD97
0x18002ad8f  or      dword ptr [rbx], 2
0x18002ad92  call    ?WldpResetProductionConfiguration@@YAJXZ; WldpResetProductionConfiguration(void)
0x18002ad97  lea     rcx, [rsp+28h+arg_10]
0x18002ad9c  call    cs:__imp_GetOsManufacturingMode
0x18002ada2  test    eax, eax
0x18002ada4  jnz     short loc_18002ADBA
0x18002ada6  call    cs:__imp_GetLastError
0x18002adac  test    eax, eax
0x18002adae  jle     short loc_18002ADD7
0x18002adb0  movzx   eax, ax
0x18002adb3  or      eax, 80070000h
0x18002adb8  jmp     short loc_18002ADD7
0x18002adba  cmp     [rsp+28h+arg_10], 0
0x18002adbf  jz      short loc_18002ADD5
0x18002adc1  or      dword ptr [rbx], 2
0x18002adc4  lea     rcx, aTestFailManufa; "TEST FAIL: ManufacturingMode is on\n"
0x18002adcb  call    LogFormatOut
0x18002add0  call    ?WldpResetProductionConfiguration@@YAJXZ; WldpResetProductionConfiguration(void)
0x18002add5  xor     eax, eax
0x18002add7  add     rsp, 20h
0x18002addb  pop     rbx
0x18002addc  retn
```
