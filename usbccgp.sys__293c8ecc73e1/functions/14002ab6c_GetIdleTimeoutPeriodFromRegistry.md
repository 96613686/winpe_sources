# GetIdleTimeoutPeriodFromRegistry

- ea: `0x14002ab6c`
- end: `0x14002ad59`
- name: `GetIdleTimeoutPeriodFromRegistry`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14002a2e0`

## callees

- `0x14000b4bc`
- `0x140014e00`
- `0x14002ab6c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002abf6`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002abf6`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002ab9c`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002ab9c`
- `ntoskrnl!ZwQueryValueKey` at `0x14002acbf`
- `ntoskrnl!ZwQueryValueKey` at `0x14002acbf`
- `ntoskrnl!ZwClose` at `0x14002ac0a`
- `ntoskrnl!ZwClose` at `0x14002ac0a`
- `ntoskrnl!ExAllocatePool2` at `0x14002ac86`
- `ntoskrnl!ExAllocatePool2` at `0x14002ac86`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ac68`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002ac68`

## pseudocode

```c
__int64 __fastcall GetIdleTimeoutPeriodFromRegistry(__int64 a1)
{
  int v2; // edx
  NTSTATUS v3; // ebx
  int v5; // r9d
  _DWORD *Pool2; // rsi
  NTSTATUS v7; // eax
  unsigned int v8; // eax
  int v9; // r14d
  int v10; // ebp
  int v11; // [rsp+30h] [rbp-48h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-38h] BYREF
  ULONG ResultLength; // [rsp+80h] [rbp+8h] BYREF
  HANDLE Handle; // [rsp+88h] [rbp+10h] BYREF

  Handle = 0;
  v3 = IoOpenDeviceRegistryKey(*(PDEVICE_OBJECT *)(a1 + 24), 1u, 0x1F0000u, &Handle);
  if ( v3 < 0 )
    goto LABEL_2;
  ResultLength = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"IdleTimeoutPeriodInMilliSec");
  Pool2 = (_DWORD *)ExAllocatePool2(256, 16, 1130525525);
  if ( Pool2 )
  {
    v7 = ZwQueryValueKey(Handle, &DestinationString, KeyValuePartialInformation, Pool2, 0x10u, &ResultLength);
    v3 = 0;
    if ( v7 != -2147483643 )
      v3 = v7;
    if ( v3 < 0 )
    {
      v9 = 0;
      v10 = 0;
    }
    else
    {
      if ( a1 != -864 )
      {
        v8 = Pool2[2];
        if ( v8 > 4 )
          v8 = 4;
        memmove((void *)(a1 + 864), Pool2 + 3, v8);
      }
      v9 = Pool2[1];
      v10 = Pool2[2];
    }
    ExFreePoolWithTag(Pool2, 0x43627355u);
  }
  else
  {
    v9 = 0;
    v3 = -1073741670;
    v10 = 0;
  }
  ZwClose(Handle);
  if ( v3 >= 0 && v9 == 4 && v10 == 4 )
  {
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = 23;
      v11 = *(_DWORD *)(a1 + 864);
LABEL_22:
      LOBYTE(v2) = 4;
      WPP_RECORDER_SF_qD(
        *(_QWORD *)(a1 + 1368),
        v2,
        1,
        v5,
        (__int64)WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids,
        *(_QWORD *)(a1 + 32),
        v11);
    }
  }
  else
  {
LABEL_2:
    *(_DWORD *)(a1 + 864) = 1000;
    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v5 = 22;
      LOBYTE(v11) = -24;
      goto LABEL_22;
    }
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x14002ab6c  mov     rax, rsp
0x14002ab6f  mov     [rax+18h], rbx
0x14002ab73  push    rbp
0x14002ab74  push    rsi
0x14002ab75  push    rdi
0x14002ab76  push    r14
0x14002ab78  push    r15
0x14002ab7a  sub     rsp, 50h
0x14002ab7e  mov     rdi, rcx
0x14002ab81  mov     qword ptr [rax+10h], 0
0x14002ab89  mov     rcx, [rcx+18h]; DeviceObject
0x14002ab8d  lea     r9, [rax+10h]; DeviceRegKey
0x14002ab91  mov     edx, 1; DevInstKeyType
0x14002ab96  mov     r8d, 1F0000h; DesiredAccess
0x14002ab9c  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002aba3  nop     dword ptr [rax+rax+00h]
0x14002aba8  mov     ebx, eax
0x14002abaa  mov     r15d, 4
0x14002abb0  test    eax, eax
0x14002abb2  jns     loc_14002AC49
0x14002abb8  mov     ecx, 3E8h
0x14002abbd  mov     [rdi+360h], ecx
0x14002abc3  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002abca  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002abd1  jnz     loc_14002AD20
0x14002abd7  mov     eax, ebx
0x14002abd9  mov     rbx, [rsp+78h+arg_10]
0x14002abe1  add     rsp, 50h
0x14002abe5  pop     r15
0x14002abe7  pop     r14
0x14002abe9  pop     rdi
0x14002abea  pop     rsi
0x14002abeb  pop     rbp
0x14002abec  retn
0x14002abee  mov     edx, 43627355h; Tag
0x14002abf3  mov     rcx, rsi; P
0x14002abf6  call    cs:__imp_ExFreePoolWithTag
0x14002abfd  nop     dword ptr [rax+rax+00h]
0x14002ac02  mov     rcx, [rsp+78h+Handle]; Handle
0x14002ac0a  call    cs:__imp_ZwClose
0x14002ac11  nop     dword ptr [rax+rax+00h]
0x14002ac16  test    ebx, ebx
0x14002ac18  js      short loc_14002ABB8
0x14002ac1a  cmp     r14d, r15d
0x14002ac1d  jnz     short loc_14002ABB8
0x14002ac1f  cmp     ebp, r15d
0x14002ac22  jnz     short loc_14002ABB8
0x14002ac24  lea     rax, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x14002ac2b  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x14002ac32  jz      short loc_14002ABD7
0x14002ac34  mov     eax, [rdi+360h]
0x14002ac3a  mov     r9d, 17h
0x14002ac40  mov     [rsp+78h+var_48], eax
0x14002ac44  jmp     loc_14002AD2A
0x14002ac49  xorps   xmm0, xmm0
0x14002ac4c  mov     [rsp+78h+arg_0], 0
0x14002ac57  lea     rdx, aIdletimeoutper; "IdleTimeoutPeriodInMilliSec"
0x14002ac5e  lea     rcx, [rsp+78h+DestinationString]; DestinationString
0x14002ac63  movups  xmmword ptr [rsp+78h+DestinationString.Length], xmm0
0x14002ac68  call    cs:__imp_RtlInitUnicodeString
0x14002ac6f  nop     dword ptr [rax+rax+00h]
0x14002ac74  mov     ebx, 10h
0x14002ac79  mov     r8d, 43627355h
0x14002ac7f  mov     edx, ebx
0x14002ac81  mov     ecx, 100h
0x14002ac86  call    cs:__imp_ExAllocatePool2
0x14002ac8d  nop     dword ptr [rax+rax+00h]
0x14002ac92  mov     rsi, rax
0x14002ac95  test    rax, rax
0x14002ac98  jz      short loc_14002AD11
0x14002ac9a  mov     rcx, [rsp+78h+Handle]; KeyHandle
0x14002aca2  lea     rax, [rsp+78h+arg_0]
0x14002acaa  mov     [rsp+78h+ResultLength], rax; ResultLength
0x14002acaf  lea     r8d, [rbx-0Eh]; KeyValueInformationClass
0x14002acb3  mov     r9, rsi; KeyValueInformation
0x14002acb6  mov     [rsp+78h+Length], ebx; Length
0x14002acba  lea     rdx, [rsp+78h+DestinationString]; ValueName
0x14002acbf  call    cs:__imp_ZwQueryValueKey
0x14002acc6  nop     dword ptr [rax+rax+00h]
0x14002accb  xor     ebx, ebx
0x14002accd  cmp     eax, 80000005h
0x14002acd2  cmovnz  ebx, eax
0x14002acd5  test    ebx, ebx
0x14002acd7  js      short loc_14002AD07
0x14002acd9  lea     rcx, [rdi+360h]; void *
0x14002ace0  test    rcx, rcx
0x14002ace3  jz      short loc_14002ACFB
0x14002ace5  mov     eax, [rsi+8]
0x14002ace8  lea     rdx, [rsi+0Ch]; Src
0x14002acec  cmp     eax, r15d
0x14002acef  cmova   eax, r15d
0x14002acf3  mov     r8d, eax; Size
0x14002acf6  call    memmove
0x14002acfb  mov     r14d, [rsi+4]
0x14002acff  mov     ebp, [rsi+8]
0x14002ad02  jmp     loc_14002ABEE
0x14002ad07  xor     r14d, r14d
0x14002ad0a  xor     ebp, ebp
0x14002ad0c  jmp     loc_14002ABEE
0x14002ad11  xor     r14d, r14d
0x14002ad14  mov     ebx, 0C000009Ah
0x14002ad19  xor     ebp, ebp
0x14002ad1b  jmp     loc_14002AC02
0x14002ad20  mov     r9d, 16h
0x14002ad26  mov     [rsp+78h+var_48], ecx
0x14002ad2a  mov     rax, [rdi+20h]
0x14002ad2e  mov     r8d, 1
0x14002ad34  mov     rcx, [rdi+558h]
0x14002ad3b  mov     dl, r15b
0x14002ad3e  mov     [rsp+78h+ResultLength], rax
0x14002ad43  lea     rax, WPP_e84aa8ae2d9034c0d4fedfbc39bcd7a4_Traceguids
0x14002ad4a  mov     qword ptr [rsp+78h+Length], rax
0x14002ad4f  call    WPP_RECORDER_SF_qD
0x14002ad54  jmp     loc_14002ABD7
```
