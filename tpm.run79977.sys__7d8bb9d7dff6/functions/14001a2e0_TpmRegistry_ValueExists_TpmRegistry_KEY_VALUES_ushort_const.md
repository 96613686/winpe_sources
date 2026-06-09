# TpmRegistry::ValueExists(TpmRegistry::KEY_VALUES,ushort const *)

- ea: `0x14001a2e0`
- end: `0x14001a376`
- name: `?ValueExists@TpmRegistry@@SAHW4KEY_VALUES@1@PEBG@Z`
- size: `150`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140012568`

## callees

- `0x140005a88`
- `0x14001a2e0`
- `0x14001a37c`

## import_xrefs

- `ntoskrnl!ZwQueryValueKey` at `0x14001a34f`
- `ntoskrnl!ZwQueryValueKey` at `0x14001a34f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a324`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001a324`

## pseudocode

```c
__int64 TpmRegistry::ValueExists()
{
  unsigned int v0; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-18h] BYREF
  ULONG ResultLength; // [rsp+50h] [rbp+8h] BYREF
  HANDLE KeyHandle; // [rsp+58h] [rbp+10h] BYREF

  v0 = 0;
  ResultLength = 0;
  KeyHandle = 0;
  DestinationString = 0;
  if ( (int)TpmRegistry::OpenKey(1u, 0x20019u, &KeyHandle) >= 0 )
  {
    ResultLength = 0;
    RtlInitUnicodeString(&DestinationString, L"PlatformLogFile");
    LOBYTE(v0) = ZwQueryValueKey(KeyHandle, &DestinationString, KeyValuePartialInformation, 0, 0, &ResultLength) == -1073741789;
  }
  TpmRegistry::CloseKey(KeyHandle);
  return v0;
}

```

## disassembly

```asm
0x14001a2e0  mov     rax, rsp
0x14001a2e3  mov     [rax+10h], rdx
0x14001a2e7  mov     [rax+8], ecx
0x14001a2ea  push    rbx
0x14001a2eb  sub     rsp, 40h
0x14001a2ef  xor     ebx, ebx
0x14001a2f1  lea     r8, [rax+10h]
0x14001a2f5  xorps   xmm0, xmm0
0x14001a2f8  mov     [rax+8], ebx
0x14001a2fb  mov     edx, 20019h
0x14001a300  mov     [rax+10h], rbx
0x14001a304  movups  xmmword ptr [rax-18h], xmm0
0x14001a308  lea     ecx, [rbx+1]
0x14001a30b  call    ?OpenKey@TpmRegistry@@CAJW4KEY_VALUES@1@KPEAPEAX@Z; TpmRegistry::OpenKey(TpmRegistry::KEY_VALUES,ulong,void * *)
0x14001a310  test    eax, eax
0x14001a312  js      short loc_14001A363
0x14001a314  lea     rdx, aPlatformlogfil; "PlatformLogFile"
0x14001a31b  mov     [rsp+48h+arg_0], ebx
0x14001a31f  lea     rcx, [rsp+48h+DestinationString]; DestinationString
0x14001a324  call    cs:__imp_RtlInitUnicodeString
0x14001a32b  nop     dword ptr [rax+rax+00h]
0x14001a330  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x14001a335  lea     rax, [rsp+48h+arg_0]
0x14001a33a  mov     [rsp+48h+ResultLength], rax; ResultLength
0x14001a33f  lea     r8d, [rbx+2]; KeyValueInformationClass
0x14001a343  xor     r9d, r9d; KeyValueInformation
0x14001a346  mov     [rsp+48h+Length], ebx; Length
0x14001a34a  lea     rdx, [rsp+48h+DestinationString]; ValueName
0x14001a34f  call    cs:__imp_ZwQueryValueKey
0x14001a356  nop     dword ptr [rax+rax+00h]
0x14001a35b  cmp     eax, 0C0000023h
0x14001a360  setz    bl
0x14001a363  mov     rcx, [rsp+48h+KeyHandle]; void *
0x14001a368  call    ?CloseKey@TpmRegistry@@CAXPEAX@Z; TpmRegistry::CloseKey(void *)
0x14001a36d  mov     eax, ebx
0x14001a36f  add     rsp, 40h
0x14001a373  pop     rbx
0x14001a374  retn
```
