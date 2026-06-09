# RegConfigGetSettings

- ea: `0x18000abfc`
- end: `0x18000ad80`
- name: `RegConfigGetSettings`
- size: `388`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, installer_update`

## callers

- `0x180024e98`

## callees

- `0x18000a714`
- `0x18000abfc`
- `0x18000ad88`
- `0x18000ade8`
- `0x18000ae64`
- `0x18000afd8`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad5c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000ad5c`

## pseudocode

```c
__int64 __fastcall RegConfigGetSettings(_DWORD *a1)
{
  unsigned int DwordValue; // ebx
  HKEY hKey; // [rsp+38h] [rbp+18h] BYREF

  hKey = 0;
  DwordValue = RegOpenProviderKey(&hKey);
  if ( !DwordValue )
  {
    DwordValue = RegConfigReadDwordValue(hKey, L"DefaultPrivateKeyLenBits", a1 + 1);
    if ( !DwordValue )
    {
      DwordValue = RegConfigReadFlag(hKey, L"RequireOnCardPrivateKeyGen", a1 + 2);
      if ( !DwordValue )
      {
        DwordValue = RegConfigReadDwordValue(hKey, L"TransactionTimeoutMilliseconds", a1 + 3);
        if ( !DwordValue )
        {
          DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateSignatureKeyImport", a1 + 4);
          if ( !DwordValue )
          {
            DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateExchangeKeyImport", a1 + 5);
            if ( !DwordValue )
            {
              DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateECDSAKeyImport", a1 + 6);
              if ( !DwordValue )
              {
                DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateECDHEKeyImport", a1 + 7);
                if ( !DwordValue
                  && (!(unsigned int)Feature_Servicing_SmartCardKspPqcSupport__private_IsEnabledDeviceUsageNoInline()
                   || (DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateMLDSAKeyImport", a1 + 8)) == 0
                   && (DwordValue = RegConfigReadFlag(hKey, L"AllowPrivateMLKEMKeyImport", a1 + 9)) == 0) )
                {
                  DwordValue = RegConfigReadFlag(hKey, L"DisableUncaughtExceptionHandler", a1 + 10);
                  if ( !DwordValue )
                    *a1 = 1;
                }
              }
            }
          }
        }
      }
    }
  }
  if ( hKey )
    RegCloseKey(hKey);
  if ( DwordValue )
    RegConfigInitialize(a1);
  return DwordValue;
}

```

## disassembly

```asm
0x18000abfc  mov     [rsp-8+arg_0], rbx
0x18000ac01  mov     [rsp-8+arg_10], rdi
0x18000ac06  push    rbp
0x18000ac07  mov     rbp, rsp
0x18000ac0a  sub     rsp, 20h
0x18000ac0e  mov     rdi, rcx
0x18000ac11  mov     [rbp+hKey], 0
0x18000ac19  lea     rcx, [rbp+hKey]; phkResult
0x18000ac1d  call    RegOpenProviderKey
0x18000ac22  mov     ebx, eax
0x18000ac24  test    eax, eax
0x18000ac26  jnz     loc_18000AD53
0x18000ac2c  mov     rcx, [rbp+hKey]
0x18000ac30  lea     r8, [rdi+4]
0x18000ac34  lea     rdx, aDefaultprivate; "DefaultPrivateKeyLenBits"
0x18000ac3b  call    RegConfigReadDwordValue
0x18000ac40  mov     ebx, eax
0x18000ac42  test    eax, eax
0x18000ac44  jnz     loc_18000AD53
0x18000ac4a  mov     rcx, [rbp+hKey]
0x18000ac4e  lea     r8, [rdi+8]
0x18000ac52  lea     rdx, aRequireoncardp; "RequireOnCardPrivateKeyGen"
0x18000ac59  call    RegConfigReadFlag
0x18000ac5e  mov     ebx, eax
0x18000ac60  test    eax, eax
0x18000ac62  jnz     loc_18000AD53
0x18000ac68  mov     rcx, [rbp+hKey]
0x18000ac6c  lea     r8, [rdi+0Ch]
0x18000ac70  lea     rdx, aTransactiontim; "TransactionTimeoutMilliseconds"
0x18000ac77  call    RegConfigReadDwordValue
0x18000ac7c  mov     ebx, eax
0x18000ac7e  test    eax, eax
0x18000ac80  jnz     loc_18000AD53
0x18000ac86  mov     rcx, [rbp+hKey]
0x18000ac8a  lea     r8, [rdi+10h]
0x18000ac8e  lea     rdx, aAllowprivatesi; "AllowPrivateSignatureKeyImport"
0x18000ac95  call    RegConfigReadFlag
0x18000ac9a  mov     ebx, eax
0x18000ac9c  test    eax, eax
0x18000ac9e  jnz     loc_18000AD53
0x18000aca4  mov     rcx, [rbp+hKey]
0x18000aca8  lea     r8, [rdi+14h]
0x18000acac  lea     rdx, aAllowprivateex; "AllowPrivateExchangeKeyImport"
0x18000acb3  call    RegConfigReadFlag
0x18000acb8  mov     ebx, eax
0x18000acba  test    eax, eax
0x18000acbc  jnz     loc_18000AD53
0x18000acc2  mov     rcx, [rbp+hKey]
0x18000acc6  lea     r8, [rdi+18h]
0x18000acca  lea     rdx, aAllowprivateec; "AllowPrivateECDSAKeyImport"
0x18000acd1  call    RegConfigReadFlag
0x18000acd6  mov     ebx, eax
0x18000acd8  test    eax, eax
0x18000acda  jnz     short loc_18000AD53
0x18000acdc  mov     rcx, [rbp+hKey]
0x18000ace0  lea     r8, [rdi+1Ch]
0x18000ace4  lea     rdx, aAllowprivateec_0; "AllowPrivateECDHEKeyImport"
0x18000aceb  call    RegConfigReadFlag
0x18000acf0  mov     ebx, eax
0x18000acf2  test    eax, eax
0x18000acf4  jnz     short loc_18000AD53
0x18000acf6  call    Feature_Servicing_SmartCardKspPqcSupport__private_IsEnabledDeviceUsageNoInline
0x18000acfb  test    eax, eax
0x18000acfd  jz      short loc_18000AD33
0x18000acff  mov     rcx, [rbp+hKey]
0x18000ad03  lea     r8, [rdi+20h]
0x18000ad07  lea     rdx, aAllowprivateml; "AllowPrivateMLDSAKeyImport"
0x18000ad0e  call    RegConfigReadFlag
0x18000ad13  mov     ebx, eax
0x18000ad15  test    eax, eax
0x18000ad17  jnz     short loc_18000AD53
0x18000ad19  mov     rcx, [rbp+hKey]
0x18000ad1d  lea     r8, [rdi+24h]
0x18000ad21  lea     rdx, aAllowprivateml_0; "AllowPrivateMLKEMKeyImport"
0x18000ad28  call    RegConfigReadFlag
0x18000ad2d  mov     ebx, eax
0x18000ad2f  test    eax, eax
0x18000ad31  jnz     short loc_18000AD53
0x18000ad33  mov     rcx, [rbp+hKey]
0x18000ad37  lea     r8, [rdi+28h]
0x18000ad3b  lea     rdx, aDisableuncaugh; "DisableUncaughtExceptionHandler"
0x18000ad42  call    RegConfigReadFlag
0x18000ad47  mov     ebx, eax
0x18000ad49  test    eax, eax
0x18000ad4b  jnz     short loc_18000AD53
0x18000ad4d  mov     dword ptr [rdi], 1
0x18000ad53  mov     rcx, [rbp+hKey]; hKey
0x18000ad57  test    rcx, rcx
0x18000ad5a  jz      short loc_18000AD62
0x18000ad5c  call    cs:__imp_RegCloseKey
0x18000ad62  test    ebx, ebx
0x18000ad64  jz      short loc_18000AD6E
0x18000ad66  mov     rcx, rdi
0x18000ad69  call    RegConfigInitialize
0x18000ad6e  mov     rdi, [rsp+20h+arg_10]
0x18000ad73  mov     eax, ebx
0x18000ad75  mov     rbx, [rsp+20h+arg_0]
0x18000ad7a  add     rsp, 20h
0x18000ad7e  pop     rbp
0x18000ad7f  retn
```
