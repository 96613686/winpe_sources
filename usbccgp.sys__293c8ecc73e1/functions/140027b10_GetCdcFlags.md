# GetCdcFlags

- ea: `0x140027b10`
- end: `0x140027c6b`
- name: `GetCdcFlags`
- size: `347`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400275b0`

## callees

- `0x140014a18`
- `0x140027b10`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140027c3b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140027c3b`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140027b3f`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140027b3f`
- `ntoskrnl!ZwQueryValueKey` at `0x140027b9a`
- `ntoskrnl!ZwQueryValueKey` at `0x140027c00`
- `ntoskrnl!ZwQueryValueKey` at `0x140027b9a`
- `ntoskrnl!ZwQueryValueKey` at `0x140027c00`
- `ntoskrnl!ZwClose` at `0x140027c4f`
- `ntoskrnl!ZwClose` at `0x140027c4f`
- `ntoskrnl!ExAllocatePool2` at `0x140027bcb`
- `ntoskrnl!ExAllocatePool2` at `0x140027bcb`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027b6e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140027b6e`

## pseudocode

```c
__int64 __fastcall GetCdcFlags(struct _DEVICE_OBJECT *a1, _DWORD *a2)
{
  NTSTATUS v3; // edi
  _DWORD *Pool2; // rbx
  int v5; // edx
  int v6; // r8d
  int v7; // r9d
  int v8; // eax
  ULONG Length; // [rsp+20h] [rbp-30h]
  int ResultLength; // [rsp+28h] [rbp-28h]
  struct _UNICODE_STRING DestinationString; // [rsp+40h] [rbp-10h] BYREF
  ULONG v13; // [rsp+78h] [rbp+28h] BYREF
  void *DeviceRegKey; // [rsp+80h] [rbp+30h] BYREF

  *a2 = 0;
  DeviceRegKey = 0;
  v3 = IoOpenDeviceRegistryKey(a1, 2u, 0xF003Fu, &DeviceRegKey);
  if ( v3 >= 0 )
  {
    v13 = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, L"CdcFlags");
    v3 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, 0, 0, &v13);
    if ( v3 == -1073741772 || !v13 )
    {
      v3 = 0;
    }
    else
    {
      Pool2 = (_DWORD *)ExAllocatePool2(256, v13, 1130525525);
      if ( Pool2 )
      {
        v3 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, Pool2, v13, &v13);
        if ( v3 >= 0 && Pool2[2] == 4 )
        {
          v8 = Pool2[3];
          *a2 = v8;
          if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
            WPP_RECORDER_SF_SD((unsigned int)&WPP_RECORDER_INITIALIZED, v5, v6, v7, Length, ResultLength, v8);
        }
        ExFreePoolWithTag(Pool2, 0);
      }
    }
    ZwClose(DeviceRegKey);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x140027b10  mov     [rsp-18h+arg_0], rbx
0x140027b15  push    rbp
0x140027b16  push    rsi
0x140027b17  push    rdi
0x140027b18  mov     rbp, rsp
0x140027b1b  sub     rsp, 50h
0x140027b1f  mov     rsi, rdx
0x140027b22  mov     dword ptr [rdx], 0
0x140027b28  mov     edx, 2; DevInstKeyType
0x140027b2d  mov     [rbp+DeviceRegKey], 0
0x140027b35  lea     r9, [rbp+DeviceRegKey]; DeviceRegKey
0x140027b39  mov     r8d, 0F003Fh; DesiredAccess
0x140027b3f  call    cs:__imp_IoOpenDeviceRegistryKey
0x140027b46  nop     dword ptr [rax+rax+00h]
0x140027b4b  mov     edi, eax
0x140027b4d  test    eax, eax
0x140027b4f  js      loc_140027C5B
0x140027b55  xorps   xmm0, xmm0
0x140027b58  mov     [rbp+arg_8], 0
0x140027b5f  lea     rdx, aCdcflags; "CdcFlags"
0x140027b66  lea     rcx, [rbp+DestinationString]; DestinationString
0x140027b6a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140027b6e  call    cs:__imp_RtlInitUnicodeString
0x140027b75  nop     dword ptr [rax+rax+00h]
0x140027b7a  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140027b7e  lea     rax, [rbp+arg_8]
0x140027b82  xor     r9d, r9d; KeyValueInformation
0x140027b85  mov     [rsp+50h+ResultLength], rax; ResultLength
0x140027b8a  lea     rdx, [rbp+DestinationString]; ValueName
0x140027b8e  mov     [rsp+50h+Length], 0; Length
0x140027b96  lea     r8d, [r9+2]; KeyValueInformationClass
0x140027b9a  call    cs:__imp_ZwQueryValueKey
0x140027ba1  nop     dword ptr [rax+rax+00h]
0x140027ba6  mov     edi, eax
0x140027ba8  cmp     eax, 0C0000034h
0x140027bad  jz      loc_140027C49
0x140027bb3  mov     eax, [rbp+arg_8]
0x140027bb6  test    eax, eax
0x140027bb8  jz      loc_140027C49
0x140027bbe  mov     edx, eax
0x140027bc0  mov     ecx, 100h
0x140027bc5  mov     r8d, 43627355h
0x140027bcb  call    cs:__imp_ExAllocatePool2
0x140027bd2  nop     dword ptr [rax+rax+00h]
0x140027bd7  mov     rbx, rax
0x140027bda  test    rax, rax
0x140027bdd  jz      short loc_140027C4B
0x140027bdf  mov     ecx, [rbp+arg_8]
0x140027be2  lea     rax, [rbp+arg_8]
0x140027be6  mov     [rsp+50h+ResultLength], rax; ResultLength
0x140027beb  lea     rdx, [rbp+DestinationString]; ValueName
0x140027bef  mov     [rsp+50h+Length], ecx; Length
0x140027bf3  mov     r9, rbx; KeyValueInformation
0x140027bf6  mov     rcx, [rbp+DeviceRegKey]; KeyHandle
0x140027bfa  mov     r8d, 2; KeyValueInformationClass
0x140027c00  call    cs:__imp_ZwQueryValueKey
0x140027c07  nop     dword ptr [rax+rax+00h]
0x140027c0c  mov     edi, eax
0x140027c0e  test    eax, eax
0x140027c10  js      short loc_140027C36
0x140027c12  cmp     dword ptr [rbx+8], 4
0x140027c16  jnz     short loc_140027C36
0x140027c18  mov     eax, [rbx+0Ch]
0x140027c1b  mov     [rsi], eax
0x140027c1d  lea     rcx, WPP_RECORDER_INITIALIZED; __annotation("TMF:",
0x140027c24  cmp     cs:WPP_RECORDER_INITIALIZED, rcx
0x140027c2b  jz      short loc_140027C36
0x140027c2d  mov     [rsp+50h+var_20], eax
0x140027c31  call    WPP_RECORDER_SF_SD
0x140027c36  xor     edx, edx; Tag
0x140027c38  mov     rcx, rbx; P
0x140027c3b  call    cs:__imp_ExFreePoolWithTag
0x140027c42  nop     dword ptr [rax+rax+00h]
0x140027c47  jmp     short loc_140027C4B
0x140027c49  xor     edi, edi
0x140027c4b  mov     rcx, [rbp+DeviceRegKey]; Handle
0x140027c4f  call    cs:__imp_ZwClose
0x140027c56  nop     dword ptr [rax+rax+00h]
0x140027c5b  mov     rbx, [rsp+50h+arg_0]
0x140027c60  mov     eax, edi
0x140027c62  add     rsp, 50h
0x140027c66  pop     rdi
0x140027c67  pop     rsi
0x140027c68  pop     rbp
0x140027c69  retn
```
