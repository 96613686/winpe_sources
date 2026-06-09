# SsCreateSecurityObjects

- ea: `0x18000a5d4`
- end: `0x18000a877`
- name: `SsCreateSecurityObjects`
- size: `675`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180015500`

## callees

- `0x18000a5d4`
- `0x18000a880`
- `0x18000a994`
- `0x18000ad5c`
- `0x18000ae90`
- `0x1800271c4`
- `0x1800273c0`
- `0x18002747c`
- `0x180027504`
- `0x1800275a0`
- `0x180027ec0`
- `0x180028718`

## import_xrefs

- `ntdll!RtlWriteRegistryValue` at `0x18000a7a2`
- `ntdll!RtlWriteRegistryValue` at `0x18000a7e7`
- `ntdll!RtlWriteRegistryValue` at `0x18000a822`
- `ntdll!RtlWriteRegistryValue` at `0x18000a85d`
- `ntdll!RtlWriteRegistryValue` at `0x18000a7a2`
- `ntdll!RtlWriteRegistryValue` at `0x18000a7e7`
- `ntdll!RtlWriteRegistryValue` at `0x18000a822`
- `ntdll!RtlWriteRegistryValue` at `0x18000a85d`

## string_xrefs

- `0x18000a604`: `AnonymousDescriptorsUpgraded`
- `0x18000a78f`: `AnonymousDescriptorsUpgraded`
- `0x18000a5e1`: `\Registry\Machine\System\CurrentControlSet\Services\lanmanserver\DefaultSecurity`
- `0x18000a799`: `LanmanServer\DefaultSecurity`
- `0x18000a7cd`: `LanmanServer\DefaultSecurity`
- `0x18000a819`: `LanmanServer\DefaultSecurity`
- `0x18000a854`: `LanmanServer\DefaultSecurity`
- `0x18000a69c`: `SessionSecurityDescriptorRegenerated`
- `0x18000a80b`: `SessionSecurityDescriptorRegenerated`
- `0x18000a678`: `InteractiveDescriptorsRegenerated`
- `0x18000a846`: `InteractiveDescriptorsRegenerated`

## pseudocode

```c
__int64 SsCreateSecurityObjects()
{
  __int64 result; // rax
  char v1; // bl
  int v2; // eax
  int ValueData; // [rsp+60h] [rbp+28h] BYREF
  int v4; // [rsp+68h] [rbp+30h]
  int v5; // [rsp+70h] [rbp+38h]
  int v6; // [rsp+78h] [rbp+40h]

  v4 = 0;
  v6 = 0;
  ValueData = 0;
  v5 = 0;
  if ( (int)QueryRegDWord(
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\lanmanserver\\DefaultSecurity",
              L"AnonymousDescriptorsUpgraded") < 0 )
    SsUpgradeSecurityDescriptors = 1;
  result = CheckNullSessionAccess();
  if ( !(_DWORD)result )
  {
    if ( (int)QueryRegDWord(
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\lanmanserver\\DefaultSecurity",
                L"PreviousAnonymousRestriction") < 0 )
    {
      v1 = 1;
      if ( SsUpgradeSecurityDescriptors )
        goto LABEL_9;
    }
    else
    {
      v1 = 0;
      if ( ValueData == (unsigned __int8)SsRestrictNullSessions )
        goto LABEL_9;
      v1 = 1;
    }
    SsRegenerateSecurityDescriptors = 1;
LABEL_9:
    if ( (int)QueryRegDWord(
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\lanmanserver\\DefaultSecurity",
                L"InteractiveDescriptorsRegenerated") < 0
      || v4 != 5 )
    {
      SsRegenerateShareSecurityDescriptors = 1;
    }
    if ( (int)QueryRegDWord(
                L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\lanmanserver\\DefaultSecurity",
                L"SessionSecurityDescriptorRegenerated") < 0
      || v5 != 2 )
    {
      SsRegenerateSessionSecurityDescriptor = 1;
    }
    result = SsCreateWellKnownSid(WinInteractiveSid);
    if ( !(_DWORD)result )
    {
      result = SsCreateWellKnownSid(WinServiceSid);
      if ( !(_DWORD)result )
      {
        result = SsCreateWellKnownSid(WinBatchSid);
        if ( !(_DWORD)result )
        {
          result = SsCreateWellKnownSid(WinBuiltinAccessControlAssistanceOperatorsSid);
          if ( !(_DWORD)result )
          {
            result = CreateConfigInfoSecurityObject();
            if ( !(_DWORD)result )
            {
              result = CreateConnectionSecurityObject();
              if ( !(_DWORD)result )
              {
                result = CreateDiskSecurityObject();
                if ( !(_DWORD)result )
                {
                  result = CreateFileSecurityObject();
                  if ( !(_DWORD)result )
                  {
                    result = CreateSessionSecurityObject();
                    if ( !(_DWORD)result )
                    {
                      result = CreateShareSecurityObjects();
                      if ( !(_DWORD)result )
                      {
                        result = CreateStatisticsSecurityObject();
                        if ( !(_DWORD)result )
                        {
                          if ( SsUpgradeSecurityDescriptors )
                          {
                            ValueData = 1;
                            v2 = RtlWriteRegistryValue(
                                   1u,
                                   L"LanmanServer\\DefaultSecurity",
                                   L"AnonymousDescriptorsUpgraded",
                                   4u,
                                   &ValueData,
                                   4u);
                            if ( v2 < 0 )
                              return NetpNtStatusToApiStatus(v2);
                          }
                          if ( v1 )
                          {
                            ValueData = (unsigned __int8)SsRestrictNullSessions;
                            v2 = RtlWriteRegistryValue(
                                   1u,
                                   L"LanmanServer\\DefaultSecurity",
                                   L"PreviousAnonymousRestriction",
                                   4u,
                                   &ValueData,
                                   4u);
                            if ( v2 < 0 )
                              return NetpNtStatusToApiStatus(v2);
                          }
                          if ( SsRegenerateSessionSecurityDescriptor )
                          {
                            ValueData = 2;
                            v2 = RtlWriteRegistryValue(
                                   1u,
                                   L"LanmanServer\\DefaultSecurity",
                                   L"SessionSecurityDescriptorRegenerated",
                                   4u,
                                   &ValueData,
                                   4u);
                            if ( v2 < 0 )
                              return NetpNtStatusToApiStatus(v2);
                          }
                          if ( SsRegenerateShareSecurityDescriptors
                            && (ValueData = 5,
                                v2 = RtlWriteRegistryValue(
                                       1u,
                                       L"LanmanServer\\DefaultSecurity",
                                       L"InteractiveDescriptorsRegenerated",
                                       4u,
                                       &ValueData,
                                       4u),
                                v2 < 0) )
                          {
                            return NetpNtStatusToApiStatus(v2);
                          }
                          else
                          {
                            return 0;
                          }
                        }
                      }
                    }
                  }
                }
              }
            }
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000a5d4  push    rbp
0x18000a5d6  push    rbx
0x18000a5d7  push    rsi
0x18000a5d8  push    r14
0x18000a5da  mov     rbp, rsp
0x18000a5dd  sub     rsp, 38h
0x18000a5e1  lea     r14, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x18000a5e8  mov     [rbp+arg_8], 0
0x18000a5ef  mov     rcx, r14; SourceString
0x18000a5f2  mov     [rbp+arg_18], 0
0x18000a5f9  lea     r8, [rbp+arg_18]
0x18000a5fd  mov     [rbp+arg_0], 0
0x18000a604  lea     rdx, aAnonymousdescr; "AnonymousDescriptorsUpgraded"
0x18000a60b  mov     [rbp+arg_10], 0
0x18000a612  call    QueryRegDWord
0x18000a617  mov     esi, 1
0x18000a61c  test    eax, eax
0x18000a61e  jns     short loc_18000A627
0x18000a620  mov     cs:SsUpgradeSecurityDescriptors, sil
0x18000a627  call    CheckNullSessionAccess
0x18000a62c  test    eax, eax
0x18000a62e  jnz     loc_18000A86D
0x18000a634  lea     r8, [rbp+arg_0]
0x18000a638  mov     rcx, r14; SourceString
0x18000a63b  lea     rdx, aPreviousanonym; "PreviousAnonymousRestriction"
0x18000a642  call    QueryRegDWord
0x18000a647  test    eax, eax
0x18000a649  js      short loc_18000A65E
0x18000a64b  movzx   eax, cs:SsRestrictNullSessions
0x18000a652  xor     bl, bl
0x18000a654  cmp     [rbp+arg_0], eax
0x18000a657  jz      short loc_18000A671
0x18000a659  mov     bl, sil
0x18000a65c  jmp     short loc_18000A66A
0x18000a65e  cmp     cs:SsUpgradeSecurityDescriptors, 0
0x18000a665  mov     bl, sil
0x18000a668  jnz     short loc_18000A671
0x18000a66a  mov     cs:SsRegenerateSecurityDescriptors, sil
0x18000a671  lea     r8, [rbp+arg_8]
0x18000a675  mov     rcx, r14; SourceString
0x18000a678  lea     rdx, aInteractivedes; "InteractiveDescriptorsRegenerated"
0x18000a67f  call    QueryRegDWord
0x18000a684  test    eax, eax
0x18000a686  js      short loc_18000A68E
0x18000a688  cmp     [rbp+arg_8], 5
0x18000a68c  jz      short loc_18000A695
0x18000a68e  mov     cs:SsRegenerateShareSecurityDescriptors, sil
0x18000a695  lea     r8, [rbp+arg_10]
0x18000a699  mov     rcx, r14; SourceString
0x18000a69c  lea     rdx, aSessionsecurit; "SessionSecurityDescriptorRegenerated"
0x18000a6a3  call    QueryRegDWord
0x18000a6a8  test    eax, eax
0x18000a6aa  js      short loc_18000A6B2
0x18000a6ac  cmp     [rbp+arg_10], 2
0x18000a6b0  jz      short loc_18000A6B9
0x18000a6b2  mov     cs:SsRegenerateSessionSecurityDescriptor, sil
0x18000a6b9  lea     rdx, SsInteractiveSid
0x18000a6c0  mov     ecx, 0Bh; WellKnownSidType
0x18000a6c5  call    SsCreateWellKnownSid
0x18000a6ca  test    eax, eax
0x18000a6cc  jnz     loc_18000A86D
0x18000a6d2  lea     rdx, SsServiceSid
0x18000a6d9  lea     ecx, [rax+0Ch]; WellKnownSidType
0x18000a6dc  call    SsCreateWellKnownSid
0x18000a6e1  test    eax, eax
0x18000a6e3  jnz     loc_18000A86D
0x18000a6e9  lea     rdx, SsBatchSid
0x18000a6f0  lea     ecx, [rax+0Ah]; WellKnownSidType
0x18000a6f3  call    SsCreateWellKnownSid
0x18000a6f8  test    eax, eax
0x18000a6fa  jnz     loc_18000A86D
0x18000a700  lea     rdx, SsAccessControlAssistanceOperatorsSid
0x18000a707  lea     ecx, [rax+65h]; WellKnownSidType
0x18000a70a  call    SsCreateWellKnownSid
0x18000a70f  test    eax, eax
0x18000a711  jnz     loc_18000A86D
0x18000a717  call    CreateConfigInfoSecurityObject
0x18000a71c  test    eax, eax
0x18000a71e  jnz     loc_18000A86D
0x18000a724  call    CreateConnectionSecurityObject
0x18000a729  test    eax, eax
0x18000a72b  jnz     loc_18000A86D
0x18000a731  call    CreateDiskSecurityObject
0x18000a736  test    eax, eax
0x18000a738  jnz     loc_18000A86D
0x18000a73e  call    CreateFileSecurityObject
0x18000a743  test    eax, eax
0x18000a745  jnz     loc_18000A86D
0x18000a74b  call    CreateSessionSecurityObject
0x18000a750  test    eax, eax
0x18000a752  jnz     loc_18000A86D
0x18000a758  call    CreateShareSecurityObjects
0x18000a75d  test    eax, eax
0x18000a75f  jnz     loc_18000A86D
0x18000a765  call    CreateStatisticsSecurityObject
0x18000a76a  test    eax, eax
0x18000a76c  jnz     loc_18000A86D
0x18000a772  cmp     cs:SsUpgradeSecurityDescriptors, al
0x18000a778  lea     r14d, [rax+4]
0x18000a77c  jz      short loc_18000A7B8
0x18000a77e  lea     rax, [rbp+arg_0]
0x18000a782  mov     [rsp+38h+ValueLength], r14d; ValueLength
0x18000a787  mov     r9d, r14d; ValueType
0x18000a78a  mov     [rsp+38h+ValueData], rax; ValueData
0x18000a78f  lea     r8, aAnonymousdescr; "AnonymousDescriptorsUpgraded"
0x18000a796  mov     [rbp+arg_0], esi
0x18000a799  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18000a7a0  mov     ecx, esi; RelativeTo
0x18000a7a2  call    cs:__imp_RtlWriteRegistryValue
0x18000a7a8  test    eax, eax
0x18000a7aa  jns     short loc_18000A7B8
0x18000a7ac  mov     ecx, eax; Status
0x18000a7ae  call    NetpNtStatusToApiStatus
0x18000a7b3  jmp     loc_18000A86D
0x18000a7b8  test    bl, bl
0x18000a7ba  jz      short loc_18000A7F1
0x18000a7bc  movzx   eax, cs:SsRestrictNullSessions
0x18000a7c3  lea     r8, aPreviousanonym; "PreviousAnonymousRestriction"
0x18000a7ca  mov     [rbp+arg_0], eax
0x18000a7cd  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18000a7d4  lea     rax, [rbp+arg_0]
0x18000a7d8  mov     [rsp+38h+ValueLength], r14d; ValueLength
0x18000a7dd  mov     r9d, r14d; ValueType
0x18000a7e0  mov     [rsp+38h+ValueData], rax; ValueData
0x18000a7e5  mov     ecx, esi; RelativeTo
0x18000a7e7  call    cs:__imp_RtlWriteRegistryValue
0x18000a7ed  test    eax, eax
0x18000a7ef  js      short loc_18000A7AC
0x18000a7f1  cmp     cs:SsRegenerateSessionSecurityDescriptor, 0
0x18000a7f8  jz      short loc_18000A82C
0x18000a7fa  lea     rax, [rbp+arg_0]
0x18000a7fe  mov     [rsp+38h+ValueLength], r14d; ValueLength
0x18000a803  mov     r9d, r14d; ValueType
0x18000a806  mov     [rsp+38h+ValueData], rax; ValueData
0x18000a80b  lea     r8, aSessionsecurit; "SessionSecurityDescriptorRegenerated"
0x18000a812  mov     [rbp+arg_0], 2
0x18000a819  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18000a820  mov     ecx, esi; RelativeTo
0x18000a822  call    cs:__imp_RtlWriteRegistryValue
0x18000a828  test    eax, eax
0x18000a82a  js      short loc_18000A7AC
0x18000a82c  cmp     cs:SsRegenerateShareSecurityDescriptors, 0
0x18000a833  jz      short loc_18000A86B
0x18000a835  lea     rax, [rbp+arg_0]
0x18000a839  mov     [rsp+38h+ValueLength], r14d; ValueLength
0x18000a83e  mov     r9d, r14d; ValueType
0x18000a841  mov     [rsp+38h+ValueData], rax; ValueData
0x18000a846  lea     r8, aInteractivedes; "InteractiveDescriptorsRegenerated"
0x18000a84d  mov     [rbp+arg_0], 5
0x18000a854  lea     rdx, aLanmanserverDe; "LanmanServer\\DefaultSecurity"
0x18000a85b  mov     ecx, esi; RelativeTo
0x18000a85d  call    cs:__imp_RtlWriteRegistryValue
0x18000a863  test    eax, eax
0x18000a865  js      loc_18000A7AC
0x18000a86b  xor     eax, eax
0x18000a86d  add     rsp, 38h
0x18000a871  pop     r14
0x18000a873  pop     rsi
0x18000a874  pop     rbx
0x18000a875  pop     rbp
0x18000a876  retn
```
