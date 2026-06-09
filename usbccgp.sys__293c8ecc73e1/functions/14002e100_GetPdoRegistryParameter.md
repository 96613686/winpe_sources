# GetPdoRegistryParameter

- ea: `0x14002e100`
- end: `0x14002e275`
- name: `GetPdoRegistryParameter`
- size: `373`
- prototype: ``
- caller_count: `6`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x14000d444`
- `0x14000d900`
- `0x14001257c`
- `0x140022ee4`
- `0x1400242a4`
- `0x14002484c`

## callees

- `0x140014e00`
- `0x14002e100`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14002e241`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002e241`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002e165`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x14002e165`
- `ntoskrnl!ZwQueryValueKey` at `0x14002e1ee`
- `ntoskrnl!ZwQueryValueKey` at `0x14002e1ee`
- `ntoskrnl!ZwClose` at `0x14002e259`
- `ntoskrnl!ZwClose` at `0x14002e259`
- `ntoskrnl!ExAllocatePool2` at `0x14002e1b2`
- `ntoskrnl!ExAllocatePool2` at `0x14002e1b2`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e196`
- `ntoskrnl!RtlInitUnicodeString` at `0x14002e196`

## pseudocode

```c
__int64 __fastcall GetPdoRegistryParameter(
        struct _DEVICE_OBJECT *a1,
        const WCHAR *a2,
        void *a3,
        unsigned int a4,
        _DWORD *a5,
        _DWORD *a6,
        ULONG ResultLength)
{
  ULONG v10; // edx
  NTSTATUS v11; // ebx
  _DWORD *Pool2; // rdi
  NTSTATUS v13; // eax
  unsigned int v14; // eax
  void *DeviceRegKey; // [rsp+30h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-50h] BYREF

  DeviceRegKey = 0;
  if ( a5 )
    *a5 = 0;
  if ( a6 )
    *a6 = 0;
  v10 = 2;
  if ( !(_BYTE)ResultLength )
    v10 = 1;
  v11 = IoOpenDeviceRegistryKey(a1, v10, 0x1F0000u, &DeviceRegKey);
  if ( v11 >= 0 )
  {
    ResultLength = 0;
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, a2);
    Pool2 = (_DWORD *)ExAllocatePool2(256, a4 + 12, 1130525525);
    if ( Pool2 )
    {
      v13 = ZwQueryValueKey(DeviceRegKey, &DestinationString, KeyValuePartialInformation, Pool2, a4 + 12, &ResultLength);
      v11 = 0;
      if ( v13 != -2147483643 )
        v11 = v13;
      if ( v11 >= 0 )
      {
        if ( a3 )
        {
          v14 = Pool2[2];
          if ( a4 < v14 )
            v14 = a4;
          memmove(a3, Pool2 + 3, v14);
        }
        if ( a5 )
          *a5 = Pool2[1];
        if ( a6 )
          *a6 = Pool2[2];
      }
      ExFreePoolWithTag(Pool2, 0x43627355u);
    }
    else
    {
      v11 = -1073741670;
    }
    ZwClose(DeviceRegKey);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14002e100  push    rbx
0x14002e102  push    rbp
0x14002e103  push    rsi
0x14002e104  push    rdi
0x14002e105  push    r14
0x14002e107  push    r15
0x14002e109  sub     rsp, 58h
0x14002e10d  mov     r14, [rsp+88h+arg_20]
0x14002e115  mov     ebp, r9d
0x14002e118  mov     [rsp+88h+DeviceRegKey], 0
0x14002e121  mov     r15, r8
0x14002e124  mov     rdi, rdx
0x14002e127  test    r14, r14
0x14002e12a  jz      short loc_14002E133
0x14002e12c  mov     dword ptr [r14], 0
0x14002e133  mov     rsi, [rsp+88h+arg_28]
0x14002e13b  test    rsi, rsi
0x14002e13e  jz      short loc_14002E146
0x14002e140  mov     dword ptr [rsi], 0
0x14002e146  cmp     byte ptr [rsp+88h+arg_30], 0
0x14002e14e  lea     r9, [rsp+88h+DeviceRegKey]; DeviceRegKey
0x14002e153  mov     r8d, 1F0000h; DesiredAccess
0x14002e159  mov     edx, 2
0x14002e15e  jnz     short loc_14002E165
0x14002e160  mov     edx, 1; DevInstKeyType
0x14002e165  call    cs:__imp_IoOpenDeviceRegistryKey
0x14002e16c  nop     dword ptr [rax+rax+00h]
0x14002e171  mov     ebx, eax
0x14002e173  test    eax, eax
0x14002e175  js      loc_14002E265
0x14002e17b  xorps   xmm0, xmm0
0x14002e17e  mov     [rsp+88h+arg_30], 0
0x14002e189  mov     rdx, rdi; SourceString
0x14002e18c  lea     rcx, [rsp+88h+DestinationString]; DestinationString
0x14002e191  movups  xmmword ptr [rsp+88h+DestinationString.Length], xmm0
0x14002e196  call    cs:__imp_RtlInitUnicodeString
0x14002e19d  nop     dword ptr [rax+rax+00h]
0x14002e1a2  lea     ebx, [rbp+0Ch]
0x14002e1a5  mov     ecx, 100h
0x14002e1aa  mov     edx, ebx
0x14002e1ac  mov     r8d, 43627355h
0x14002e1b2  call    cs:__imp_ExAllocatePool2
0x14002e1b9  nop     dword ptr [rax+rax+00h]
0x14002e1be  mov     rdi, rax
0x14002e1c1  test    rax, rax
0x14002e1c4  jz      loc_14002E24F
0x14002e1ca  mov     rcx, [rsp+88h+DeviceRegKey]; KeyHandle
0x14002e1cf  lea     rax, [rsp+88h+arg_30]
0x14002e1d7  mov     [rsp+88h+ResultLength], rax; ResultLength
0x14002e1dc  lea     rdx, [rsp+88h+DestinationString]; ValueName
0x14002e1e1  mov     r9, rdi; KeyValueInformation
0x14002e1e4  mov     [rsp+88h+Length], ebx; Length
0x14002e1e8  mov     r8d, 2; KeyValueInformationClass
0x14002e1ee  call    cs:__imp_ZwQueryValueKey
0x14002e1f5  nop     dword ptr [rax+rax+00h]
0x14002e1fa  xor     ebx, ebx
0x14002e1fc  cmp     eax, 80000005h
0x14002e201  cmovnz  ebx, eax
0x14002e204  test    ebx, ebx
0x14002e206  js      short loc_14002E239
0x14002e208  test    r15, r15
0x14002e20b  jz      short loc_14002E224
0x14002e20d  mov     eax, [rdi+8]
0x14002e210  lea     rdx, [rdi+0Ch]; Src
0x14002e214  cmp     ebp, eax
0x14002e216  mov     rcx, r15; void *
0x14002e219  cmovb   eax, ebp
0x14002e21c  mov     r8d, eax; Size
0x14002e21f  call    memmove
0x14002e224  test    r14, r14
0x14002e227  jz      short loc_14002E22F
0x14002e229  mov     eax, [rdi+4]
0x14002e22c  mov     [r14], eax
0x14002e22f  test    rsi, rsi
0x14002e232  jz      short loc_14002E239
0x14002e234  mov     eax, [rdi+8]
0x14002e237  mov     [rsi], eax
0x14002e239  mov     edx, 43627355h; Tag
0x14002e23e  mov     rcx, rdi; P
0x14002e241  call    cs:__imp_ExFreePoolWithTag
0x14002e248  nop     dword ptr [rax+rax+00h]
0x14002e24d  jmp     short loc_14002E254
0x14002e24f  mov     ebx, 0C000009Ah
0x14002e254  mov     rcx, [rsp+88h+DeviceRegKey]; Handle
0x14002e259  call    cs:__imp_ZwClose
0x14002e260  nop     dword ptr [rax+rax+00h]
0x14002e265  mov     eax, ebx
0x14002e267  add     rsp, 58h
0x14002e26b  pop     r15
0x14002e26d  pop     r14
0x14002e26f  pop     rdi
0x14002e270  pop     rsi
0x14002e271  pop     rbp
0x14002e272  pop     rbx
0x14002e273  retn
```
