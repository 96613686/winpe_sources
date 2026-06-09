# USBD_InstallExtPropDescSections

- ea: `0x140013a6c`
- end: `0x140013b7f`
- name: `USBD_InstallExtPropDescSections`
- size: `275`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x1400242a4`

## callees

- `0x140013a6c`

## import_xrefs

- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140013acf`
- `ntoskrnl!IoOpenDeviceRegistryKey` at `0x140013acf`
- `ntoskrnl!ZwClose` at `0x140013b56`
- `ntoskrnl!ZwClose` at `0x140013b56`
- `ntoskrnl!ZwSetValueKey` at `0x140013b36`
- `ntoskrnl!ZwSetValueKey` at `0x140013b36`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b05`
- `ntoskrnl!RtlInitUnicodeString` at `0x140013b05`

## pseudocode

```c
NTSTATUS __fastcall USBD_InstallExtPropDescSections(struct _DEVICE_OBJECT *a1, __int64 a2, unsigned int a3)
{
  unsigned int v4; // ebp
  NTSTATUS result; // eax
  NTSTATUS v6; // ebx
  const WCHAR *v7; // rdi
  unsigned int i; // esi
  __int64 v9; // rbx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-28h] BYREF
  void *DeviceRegKey; // [rsp+68h] [rbp+10h] BYREF

  DeviceRegKey = 0;
  if ( !a2 || !a1 )
    return -1073741811;
  v4 = *(unsigned __int16 *)(a2 + 8);
  if ( !(_WORD)v4 )
    return 0;
  if ( *(_DWORD *)a2 < 0xAu || *(_DWORD *)a2 > a3 )
    return -1073741811;
  result = IoOpenDeviceRegistryKey(a1, 1u, 0x1F0000u, &DeviceRegKey);
  v6 = result;
  if ( result >= 0 )
  {
    v7 = (const WCHAR *)(a2 + 10);
    for ( i = 0; i < v4; ++i )
    {
      DestinationString = 0;
      v9 = v7[4];
      RtlInitUnicodeString(&DestinationString, v7 + 5);
      v6 = ZwSetValueKey(
             DeviceRegKey,
             &DestinationString,
             0,
             *((_DWORD *)v7 + 1),
             (char *)v7 + v9 + 14,
             *(_DWORD *)((char *)v7 + v9 + 10));
      if ( v6 < 0 )
        break;
      v7 = (const WCHAR *)((char *)v7 + *(unsigned int *)v7);
    }
    ZwClose(DeviceRegKey);
    return v6;
  }
  return result;
}

```

## disassembly

```asm
0x140013a6c  mov     [rsp+arg_0], rbx
0x140013a71  mov     [rsp+arg_10], rbp
0x140013a76  push    rsi
0x140013a77  push    rdi
0x140013a78  push    r14
0x140013a7a  sub     rsp, 40h
0x140013a7e  xor     r14d, r14d
0x140013a81  mov     rdi, rdx
0x140013a84  mov     [rsp+58h+DeviceRegKey], r14
0x140013a89  test    rdx, rdx
0x140013a8c  jz      loc_140013B66
0x140013a92  test    rcx, rcx
0x140013a95  jz      loc_140013B66
0x140013a9b  movzx   ebp, word ptr [rdx+8]
0x140013a9f  test    bp, bp
0x140013aa2  jnz     short loc_140013AAB
0x140013aa4  xor     eax, eax
0x140013aa6  jmp     loc_140013B6B
0x140013aab  mov     eax, [rdx]
0x140013aad  cmp     eax, 0Ah
0x140013ab0  jb      loc_140013B66
0x140013ab6  cmp     eax, r8d
0x140013ab9  ja      loc_140013B66
0x140013abf  lea     r9, [rsp+58h+DeviceRegKey]; DeviceRegKey
0x140013ac4  mov     edx, 1; DevInstKeyType
0x140013ac9  mov     r8d, 1F0000h; DesiredAccess
0x140013acf  call    cs:__imp_IoOpenDeviceRegistryKey
0x140013ad6  nop     dword ptr [rax+rax+00h]
0x140013adb  mov     ebx, eax
0x140013add  test    eax, eax
0x140013adf  js      loc_140013B6B
0x140013ae5  add     rdi, 0Ah
0x140013ae9  mov     esi, r14d
0x140013aec  cmp     esi, ebp
0x140013aee  jnb     short loc_140013B51
0x140013af0  xorps   xmm0, xmm0
0x140013af3  lea     rdx, [rdi+0Ah]; SourceString
0x140013af7  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x140013afc  movzx   ebx, word ptr [rdi+8]
0x140013b00  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x140013b05  call    cs:__imp_RtlInitUnicodeString
0x140013b0c  nop     dword ptr [rax+rax+00h]
0x140013b11  mov     eax, [rbx+rdi+0Ah]
0x140013b15  lea     rcx, [rbx+0Eh]
0x140013b19  mov     r9d, [rdi+4]; Type
0x140013b1d  lea     rdx, [rsp+58h+DestinationString]; ValueName
0x140013b22  add     rcx, rdi
0x140013b25  mov     [rsp+58h+DataSize], eax; DataSize
0x140013b29  mov     [rsp+58h+Data], rcx; Data
0x140013b2e  xor     r8d, r8d; TitleIndex
0x140013b31  mov     rcx, [rsp+58h+DeviceRegKey]; KeyHandle
0x140013b36  call    cs:__imp_ZwSetValueKey
0x140013b3d  nop     dword ptr [rax+rax+00h]
0x140013b42  mov     ebx, eax
0x140013b44  test    eax, eax
0x140013b46  js      short loc_140013B51
0x140013b48  mov     eax, [rdi]
0x140013b4a  add     rdi, rax
0x140013b4d  inc     esi
0x140013b4f  jmp     short loc_140013AEC
0x140013b51  mov     rcx, [rsp+58h+DeviceRegKey]; Handle
0x140013b56  call    cs:__imp_ZwClose
0x140013b5d  nop     dword ptr [rax+rax+00h]
0x140013b62  mov     eax, ebx
0x140013b64  jmp     short loc_140013B6B
0x140013b66  mov     eax, 0C000000Dh
0x140013b6b  mov     rbx, [rsp+58h+arg_0]
0x140013b70  mov     rbp, [rsp+58h+arg_10]
0x140013b75  add     rsp, 40h
0x140013b79  pop     r14
0x140013b7b  pop     rdi
0x140013b7c  pop     rsi
0x140013b7d  retn
```
