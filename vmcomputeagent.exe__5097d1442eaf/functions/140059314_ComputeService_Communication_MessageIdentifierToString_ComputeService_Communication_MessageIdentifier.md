# ComputeService::Communication::MessageIdentifierToString(ComputeService::Communication::MessageIdentifier)

- ea: `0x140059314`
- end: `0x1400594d5`
- name: `?MessageIdentifierToString@Communication@ComputeService@@YAPEBGW4MessageIdentifier@12@@Z`
- size: `449`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1400594dc`

## callees

- `0x140059314`

## string_xrefs

- `0x14005938e`: `ComputeSystemCreate_v1`
- `0x14005936e`: `ComputeSystemExecuteProcess_v1`
- `0x140059376`: `ComputeSystemShutdownForced_v1`
- `0x14005937e`: `ComputeSystemShutdownGraceful_v1`
- `0x140059386`: `ComputeSystemStart_v1`
- `0x1400593ef`: `ComputeSystemGetProperties_v1`
- `0x1400593f7`: `ComputeSystemResizeConsole_v1`
- `0x140059396`: `ComputeSystemSignalProcess_v1`
- `0x14005935c`: `ComputeSystemWaitForProcess_v1`
- `0x1400593c8`: `ComputeServiceModifyServiceSettings_v1`
- `0x1400593d7`: `ComputeSystemLifecycleNotification_v1`
- `0x1400593df`: `ComputeSystemNegotiateProtocol_v1`
- `0x1400593e7`: `ComputeSystemModifySettings_v1`
- `0x140059461`: `ComputeSystemResponseShutdownForced_v1`
- `0x140059469`: `ComputeSystemResponseShutdownGraceful_v1`
- `0x140059471`: `ComputeSystemResponseStart_v1`
- `0x1400593ff`: `ComputeSystemResponseCreate_v1`
- `0x140059479`: `ComputeSystemResponseResizeConsole_v1`
- `0x14005943c`: `ComputeSystemResponseSignalProcess_v1`
- `0x140059451`: `ComputeSystemResponseWaitForProcess_v1`
- `0x140059459`: `ComputeSystemResponseExecuteProcess_v1`
- `0x1400594b5`: `ComputeServiceResponseModifyServiceSettings_v1`
- `0x1400594bd`: `ComputeSystemResponseNegotiateProtocol_v1`
- `0x1400594c5`: `ComputeSystemResponseModifySettings_v1`
- `0x1400594cd`: `ComputeSystemResponseGetProperties_v1`
- `0x1400594a3`: `ComputeSystemNotification_v1`

## pseudocode

```c
const wchar_t *__fastcall ComputeService::Communication::MessageIdentifierToString(unsigned int a1)
{
  __int64 v1; // rdx
  const wchar_t *v2; // rax
  bool v3; // zf
  const wchar_t *result; // rax

  if ( a1 <= 0x20100101 )
  {
    if ( a1 == 537919745 )
      return L"ComputeSystemResponseCreate_v1";
    if ( a1 > 0x10100701 )
    {
      switch ( a1 )
      {
        case 0x10100801u:
          return L"ComputeSystemResizeConsole_v1";
        case 0x10100901u:
          return L"ComputeSystemGetProperties_v1";
        case 0x10100A01u:
          return L"ComputeSystemModifySettings_v1";
        case 0x10100B01u:
          return L"ComputeSystemNegotiateProtocol_v1";
        case 0x10100C01u:
          return L"ComputeSystemLifecycleNotification_v1";
      }
      v1 = 0;
      v2 = L"ComputeServiceModifyServiceSettings_v1";
      v3 = a1 == 270532865;
    }
    else
    {
      switch ( a1 )
      {
        case 0x10100701u:
          return L"ComputeSystemSignalProcess_v1";
        case 0x10100101u:
          return L"ComputeSystemCreate_v1";
        case 0x10100201u:
          return L"ComputeSystemStart_v1";
        case 0x10100301u:
          return L"ComputeSystemShutdownGraceful_v1";
        case 0x10100401u:
          return L"ComputeSystemShutdownForced_v1";
        case 0x10100501u:
          return L"ComputeSystemExecuteProcess_v1";
      }
      v1 = 0;
      v2 = L"ComputeSystemWaitForProcess_v1";
      v3 = a1 == 269485569;
    }
LABEL_37:
    if ( v3 )
      return v2;
    return (const wchar_t *)v1;
  }
  if ( a1 <= 0x20100801 )
  {
    switch ( a1 )
    {
      case 0x20100801u:
        return L"ComputeSystemResponseResizeConsole_v1";
      case 0x20100201u:
        return L"ComputeSystemResponseStart_v1";
      case 0x20100301u:
        return L"ComputeSystemResponseShutdownGraceful_v1";
      case 0x20100401u:
        return L"ComputeSystemResponseShutdownForced_v1";
      case 0x20100501u:
        return L"ComputeSystemResponseExecuteProcess_v1";
      case 0x20100601u:
        return L"ComputeSystemResponseWaitForProcess_v1";
    }
    v1 = 0;
    v2 = L"ComputeSystemResponseSignalProcess_v1";
    v3 = a1 == 537921281;
    goto LABEL_37;
  }
  switch ( a1 )
  {
    case 0x20100901u:
      return L"ComputeSystemResponseGetProperties_v1";
    case 0x20100A01u:
      return L"ComputeSystemResponseModifySettings_v1";
    case 0x20100B01u:
      return L"ComputeSystemResponseNegotiateProtocol_v1";
    case 0x20200101u:
      return L"ComputeServiceResponseModifyServiceSettings_v1";
  }
  result = L"ComputeSystemNotification_v1";
  if ( a1 != 806355201 )
    return 0;
  return result;
}

```

## disassembly

```asm
0x140059314  mov     eax, 20100101h
0x140059319  cmp     ecx, eax
0x14005931b  ja      loc_140059407
0x140059321  jz      loc_1400593FF
0x140059327  mov     eax, 10100701h
0x14005932c  cmp     ecx, eax
0x14005932e  ja      short loc_14005939E
0x140059330  jz      short loc_140059396
0x140059332  cmp     ecx, 10100101h
0x140059338  jz      short loc_14005938E
0x14005933a  cmp     ecx, 10100201h
0x140059340  jz      short loc_140059386
0x140059342  cmp     ecx, 10100301h
0x140059348  jz      short loc_14005937E
0x14005934a  cmp     ecx, 10100401h
0x140059350  jz      short loc_140059376
0x140059352  cmp     ecx, 10100501h
0x140059358  jz      short loc_14005936E
0x14005935a  xor     edx, edx
0x14005935c  lea     rax, aComputesystemw; "ComputeSystemWaitForProcess_v1"
0x140059363  cmp     ecx, 10100601h
0x140059369  jmp     loc_140059449
0x14005936e  lea     rax, aComputesysteme; "ComputeSystemExecuteProcess_v1"
0x140059375  retn
0x140059376  lea     rax, aComputesystems_2; "ComputeSystemShutdownForced_v1"
0x14005937d  retn
0x14005937e  lea     rax, aComputesystems_1; "ComputeSystemShutdownGraceful_v1"
0x140059385  retn
0x140059386  lea     rax, aComputesystems; "ComputeSystemStart_v1"
0x14005938d  retn
0x14005938e  lea     rax, aComputesystemc; "ComputeSystemCreate_v1"
0x140059395  retn
0x140059396  lea     rax, aComputesystems_0; "ComputeSystemSignalProcess_v1"
0x14005939d  retn
0x14005939e  cmp     ecx, 10100801h
0x1400593a4  jz      short loc_1400593F7
0x1400593a6  cmp     ecx, 10100901h
0x1400593ac  jz      short loc_1400593EF
0x1400593ae  cmp     ecx, 10100A01h
0x1400593b4  jz      short loc_1400593E7
0x1400593b6  cmp     ecx, 10100B01h
0x1400593bc  jz      short loc_1400593DF
0x1400593be  cmp     ecx, 10100C01h
0x1400593c4  jz      short loc_1400593D7
0x1400593c6  xor     edx, edx
0x1400593c8  lea     rax, aComputeservice; "ComputeServiceModifyServiceSettings_v1"
0x1400593cf  cmp     ecx, 10200101h
0x1400593d5  jmp     short loc_140059449
0x1400593d7  lea     rax, aComputesysteml; "ComputeSystemLifecycleNotification_v1"
0x1400593de  retn
0x1400593df  lea     rax, aComputesystemn; "ComputeSystemNegotiateProtocol_v1"
0x1400593e6  retn
0x1400593e7  lea     rax, aComputesystemm; "ComputeSystemModifySettings_v1"
0x1400593ee  retn
0x1400593ef  lea     rax, aComputesystemg; "ComputeSystemGetProperties_v1"
0x1400593f6  retn
0x1400593f7  lea     rax, aComputesystemr_0; "ComputeSystemResizeConsole_v1"
0x1400593fe  retn
0x1400593ff  lea     rax, aComputesystemr_7; "ComputeSystemResponseCreate_v1"
0x140059406  retn
0x140059407  mov     eax, 20100801h
0x14005940c  cmp     ecx, eax
0x14005940e  ja      short loc_140059481
0x140059410  jz      short loc_140059479
0x140059412  cmp     ecx, 20100201h
0x140059418  jz      short loc_140059471
0x14005941a  cmp     ecx, 20100301h
0x140059420  jz      short loc_140059469
0x140059422  cmp     ecx, 20100401h
0x140059428  jz      short loc_140059461
0x14005942a  cmp     ecx, 20100501h
0x140059430  jz      short loc_140059459
0x140059432  cmp     ecx, 20100601h
0x140059438  jz      short loc_140059451
0x14005943a  xor     edx, edx
0x14005943c  lea     rax, aComputesystemr_3; "ComputeSystemResponseSignalProcess_v1"
0x140059443  cmp     ecx, 20100701h
0x140059449  cmovz   rdx, rax
0x14005944d  mov     rax, rdx
0x140059450  retn
0x140059451  lea     rax, aComputesystemr_5; "ComputeSystemResponseWaitForProcess_v1"
0x140059458  retn
0x140059459  lea     rax, aComputesystemr; "ComputeSystemResponseExecuteProcess_v1"
0x140059460  retn
0x140059461  lea     rax, aComputesystemr_10; "ComputeSystemResponseShutdownForced_v1"
0x140059468  retn
0x140059469  lea     rax, aComputesystemr_9; "ComputeSystemResponseShutdownGraceful_v"...
0x140059470  retn
0x140059471  lea     rax, aComputesystemr_2; "ComputeSystemResponseStart_v1"
0x140059478  retn
0x140059479  lea     rax, aComputesystemr_1; "ComputeSystemResponseResizeConsole_v1"
0x140059480  retn
0x140059481  cmp     ecx, 20100901h
0x140059487  jz      short loc_1400594CD
0x140059489  cmp     ecx, 20100A01h
0x14005948f  jz      short loc_1400594C5
0x140059491  cmp     ecx, 20100B01h
0x140059497  jz      short loc_1400594BD
0x140059499  cmp     ecx, 20200101h
0x14005949f  jz      short loc_1400594B5
0x1400594a1  xor     edx, edx
0x1400594a3  lea     rax, aComputesystemn_0; "ComputeSystemNotification_v1"
0x1400594aa  cmp     ecx, 30100101h
0x1400594b0  cmovnz  rax, rdx
0x1400594b4  retn
0x1400594b5  lea     rax, aComputeservice_0; "ComputeServiceResponseModifyServiceSett"...
0x1400594bc  retn
0x1400594bd  lea     rax, aComputesystemr_8; "ComputeSystemResponseNegotiateProtocol_"...
0x1400594c4  retn
0x1400594c5  lea     rax, aComputesystemr_6; "ComputeSystemResponseModifySettings_v1"
0x1400594cc  retn
0x1400594cd  lea     rax, aComputesystemr_4; "ComputeSystemResponseGetProperties_v1"
0x1400594d4  retn
```
