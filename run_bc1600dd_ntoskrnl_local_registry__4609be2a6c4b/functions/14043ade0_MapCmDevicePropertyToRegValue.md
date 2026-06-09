# _MapCmDevicePropertyToRegValue

- ea: `0x14043ade0`
- end: `0x14043aee6`
- name: `_MapCmDevicePropertyToRegValue`
- size: `262`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14090df54`

## callees

- `0x14043ade0`

## string_xrefs

- `0x14043ae38`: `Service`
- `0x14043ae4a`: `CompatibleIDs`
- `0x14043aea4`: `Security`
- `0x14043ae2f`: `ConfigFlags`

## pseudocode

```c
const wchar_t *__fastcall MapCmDevicePropertyToRegValue(__int64 a1, int a2)
{
  const wchar_t *result; // rax

  switch ( a2 )
  {
    case 2:
      return L"HardwareID";
    case 10:
      return L"Driver";
    case 11:
      return L"ConfigFlags";
  }
  switch ( a2 )
  {
    case 1:
      result = L"DeviceDesc";
      break;
    case 3:
      result = L"CompatibleIDs";
      break;
    case 5:
      result = L"Service";
      break;
    case 8:
      result = L"Class";
      break;
    case 9:
      result = L"ClassGUID";
      break;
    case 12:
      result = L"Mfg";
      break;
    case 13:
      result = L"FriendlyName";
      break;
    case 14:
      result = L"LocationInformation";
      break;
    case 16:
      result = L"Capabilities";
      break;
    case 17:
      result = L"UINumber";
      break;
    case 18:
      result = L"UpperFilters";
      break;
    case 19:
      result = L"LowerFilters";
      break;
    case 24:
      result = L"Security";
      break;
    case 26:
      result = L"DeviceType";
      break;
    case 27:
      result = L"Exclusive";
      break;
    case 28:
      result = L"DeviceCharacteristics";
      break;
    case 29:
      result = L"Address";
      break;
    case 30:
      result = L"UINumberDescFormat";
      break;
    case 34:
      result = L"RemovalPolicy";
      break;
    case 37:
      result = L"ContainerID";
      break;
    default:
      result = 0;
      break;
  }
  return result;
}

```

## disassembly

```asm
0x14043ade0  cmp     edx, 2
0x14043ade3  jz      short loc_14043AE1D
0x14043ade5  cmp     edx, 0Ah
0x14043ade8  jz      short loc_14043AE26
0x14043adea  cmp     edx, 0Bh
0x14043aded  jz      short loc_14043AE2F
0x14043adef  dec     edx; switch 37 cases
0x14043adf1  cmp     edx, 24h
0x14043adf4  ja      def_14043AE0E; jumptable 000000014043AE0E default case, cases 2,4,6,7,10,11,15,20-23,25,31-33,35,36
0x14043adfa  movsxd  rax, edx
0x14043adfd  lea     rdx, cs:140000000h
0x14043ae04  mov     ecx, ds:(jpt_14043AE0E - 140000000h)[rdx+rax*4]
0x14043ae0b  add     rcx, rdx
0x14043ae0e  jmp     rcx; switch jump
0x14043ae14  lea     rax, aDevicedesc; jumptable 000000014043AE0E case 1
0x14043ae1b  retn
0x14043ae1d  lea     rax, aHardwareid; "HardwareID"
0x14043ae24  retn
0x14043ae26  lea     rax, aDriver_2; "Driver"
0x14043ae2d  retn
0x14043ae2f  lea     rax, aConfigflags_0; "ConfigFlags"
0x14043ae36  retn
0x14043ae38  lea     rax, aService; jumptable 000000014043AE0E case 5
0x14043ae3f  retn
0x14043ae41  lea     rax, aFriendlyname_0; jumptable 000000014043AE0E case 13
0x14043ae48  retn
0x14043ae4a  lea     rax, aCompatibleids; jumptable 000000014043AE0E case 3
0x14043ae51  retn
0x14043ae53  lea     rax, aUpperfilters; jumptable 000000014043AE0E case 18
0x14043ae5a  retn
0x14043ae5c  lea     rax, aLowerfilters_0; jumptable 000000014043AE0E case 19
0x14043ae63  retn
0x14043ae65  lea     rax, aMfg; jumptable 000000014043AE0E case 12
0x14043ae6c  retn
0x14043ae6e  lea     rax, aContainerid_0; jumptable 000000014043AE0E case 37
0x14043ae75  retn
0x14043ae77  lea     rax, aUinumber; jumptable 000000014043AE0E case 17
0x14043ae7e  retn
0x14043ae80  lea     rax, aCapabilities_0; jumptable 000000014043AE0E case 16
0x14043ae87  retn
0x14043ae89  lea     rax, aAddress; jumptable 000000014043AE0E case 29
0x14043ae90  retn
0x14043ae92  lea     rax, aLocationinform; jumptable 000000014043AE0E case 14
0x14043ae99  retn
0x14043ae9b  lea     rax, aDevicecharacte_0; jumptable 000000014043AE0E case 28
0x14043aea2  retn
0x14043aea4  lea     rax, aSecurity_1; jumptable 000000014043AE0E case 24
0x14043aeab  retn
0x14043aead  lea     rax, aRemovalpolicy; jumptable 000000014043AE0E case 34
0x14043aeb4  retn
0x14043aeb6  lea     rax, aDevicetype; jumptable 000000014043AE0E case 26
0x14043aebd  retn
0x14043aebf  lea     rax, aExclusive_0; jumptable 000000014043AE0E case 27
0x14043aec6  retn
0x14043aec8  lea     rax, aUinumberdescfo; jumptable 000000014043AE0E case 30
0x14043aecf  retn
0x14043aed1  lea     rax, aClassguid; jumptable 000000014043AE0E case 9
0x14043aed8  retn
0x14043aeda  lea     rax, aClass_0; jumptable 000000014043AE0E case 8
0x14043aee1  retn
0x14043aee3  xor     eax, eax; jumptable 000000014043AE0E default case, cases 2,4,6,7,10,11,15,20-23,25,31-33,35,36
0x14043aee5  retn
```
