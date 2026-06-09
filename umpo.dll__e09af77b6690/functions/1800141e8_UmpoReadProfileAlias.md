# UmpoReadProfileAlias

- ea: `0x1800141e8`
- end: `0x1800142f7`
- name: `UmpoReadProfileAlias`
- size: `271`
- prototype: `__int64 __fastcall(GUID *Guid, LPBYTE lpData, LPDWORD lpcbData)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180014c80`

## callees

- `0x18000f3dc`
- `0x1800141e8`

## import_xrefs

- `ntdll!RtlStringFromGUID` at `0x18001424b`
- `ntdll!RtlStringFromGUID` at `0x18001424b`
- `ntdll!RtlFreeUnicodeString` at `0x1800142c3`
- `ntdll!RtlFreeUnicodeString` at `0x1800142c3`
- `ntdll!RtlInitUnicodeString` at `0x18001423d`
- `ntdll!RtlInitUnicodeString` at `0x18001423d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800142aa`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800142aa`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014276`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180014276`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142d8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800142d8`

## pseudocode

```c
__int64 __fastcall UmpoReadProfileAlias(GUID *Guid, LPBYTE lpData, LPDWORD lpcbData)
{
  unsigned int Value; // ebx
  LSTATUS v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  HKEY hKey; // [rsp+60h] [rbp+18h] BYREF

  DestinationString = 0;
  if ( !lpcbData || !Guid )
    return 87;
  hKey = HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL;
  if ( UmpoPpmProfileEventsRootKey == HKEY_CURRENT_USER_LOCAL_SETTINGS|0x7FFFFFF8LL )
  {
    Value = 2;
  }
  else
  {
    RtlInitUnicodeString(&DestinationString, 0);
    Value = RtlStringFromGUID(Guid, &DestinationString);
    if ( !Value )
    {
      v7 = RegOpenKeyExW(UmpoPpmProfileEventsRootKey, DestinationString.Buffer, 0, 0x20019u, &hKey);
      Value = v7;
      if ( v7 )
      {
        if ( v7 == 2 )
          goto LABEL_11;
      }
      else
      {
        Value = RegQueryValueExW(hKey, L"Name", 0, 0, lpData, lpcbData);
        if ( (Value & 0xFFFFFFFD) == 0 )
          goto LABEL_11;
      }
      MicrosoftTelemetryAssertTriggeredNoArgs();
    }
  }
LABEL_11:
  RtlFreeUnicodeString(&DestinationString);
  if ( (unsigned __int64)hKey - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    RegCloseKey(hKey);
  return Value;
}

```

## disassembly

```asm
0x1800141e8  mov     rax, rsp
0x1800141eb  mov     [rax+8], rbx
0x1800141ef  mov     [rax+10h], rsi
0x1800141f3  push    rdi
0x1800141f4  sub     rsp, 40h
0x1800141f8  xorps   xmm0, xmm0
0x1800141fb  mov     rdi, r8
0x1800141fe  mov     rsi, rdx
0x180014201  mov     rbx, rcx
0x180014204  movups  xmmword ptr [rax-18h], xmm0
0x180014208  test    r8, r8
0x18001420b  jz      loc_1800142E2
0x180014211  test    rcx, rcx
0x180014214  jz      loc_1800142E2
0x18001421a  cmp     cs:UmpoPpmProfileEventsRootKey, 0FFFFFFFFFFFFFFFFh
0x180014222  mov     qword ptr [rax+18h], 0FFFFFFFFFFFFFFFFh
0x18001422a  jnz     short loc_180014236
0x18001422c  mov     ebx, 2
0x180014231  jmp     loc_1800142BE
0x180014236  xor     edx, edx; SourceString
0x180014238  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x18001423d  call    cs:__imp_RtlInitUnicodeString
0x180014243  lea     rdx, [rsp+48h+DestinationString]; GuidString
0x180014248  mov     rcx, rbx; Guid
0x18001424b  call    cs:__imp_RtlStringFromGUID
0x180014251  mov     ebx, eax
0x180014253  test    eax, eax
0x180014255  jnz     short loc_1800142BE
0x180014257  mov     rdx, [rsp+48h+DestinationString.Buffer]; lpSubKey
0x18001425c  lea     rax, [rsp+48h+hKey]
0x180014261  mov     rcx, cs:UmpoPpmProfileEventsRootKey; hKey
0x180014268  mov     r9d, 20019h; samDesired
0x18001426e  xor     r8d, r8d; ulOptions
0x180014271  mov     [rsp+48h+phkResult], rax; phkResult
0x180014276  call    cs:__imp_RegOpenKeyExW
0x18001427c  mov     ebx, eax
0x18001427e  test    eax, eax
0x180014280  jz      short loc_18001428E
0x180014282  cmp     eax, 2
0x180014285  jz      short loc_1800142BE
0x180014287  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001428c  jmp     short loc_1800142BE
0x18001428e  mov     rcx, [rsp+48h+hKey]; hKey
0x180014293  lea     rdx, aName; "Name"
0x18001429a  mov     [rsp+48h+lpcbData], rdi; lpcbData
0x18001429f  xor     r9d, r9d; lpType
0x1800142a2  xor     r8d, r8d; lpReserved
0x1800142a5  mov     [rsp+48h+phkResult], rsi; lpData
0x1800142aa  call    cs:__imp_RegQueryValueExW
0x1800142b0  mov     ebx, eax
0x1800142b2  test    eax, 0FFFFFFFDh
0x1800142b7  jz      short loc_1800142BE
0x1800142b9  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800142be  lea     rcx, [rsp+48h+DestinationString]; UnicodeString
0x1800142c3  call    cs:__imp_RtlFreeUnicodeString
0x1800142c9  mov     rcx, [rsp+48h+hKey]; hKey
0x1800142ce  lea     rax, [rcx-1]
0x1800142d2  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800142d6  ja      short loc_1800142DE
0x1800142d8  call    cs:__imp_RegCloseKey
0x1800142de  mov     eax, ebx
0x1800142e0  jmp     short loc_1800142E7
0x1800142e2  mov     eax, 57h ; 'W'
0x1800142e7  mov     rbx, [rsp+48h+arg_0]
0x1800142ec  mov     rsi, [rsp+48h+arg_8]
0x1800142f1  add     rsp, 40h
0x1800142f5  pop     rdi
0x1800142f6  retn
```
