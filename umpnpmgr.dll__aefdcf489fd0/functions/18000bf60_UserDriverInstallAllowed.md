# UserDriverInstallAllowed

- ea: `0x18000bf60`
- end: `0x18000c040`
- name: `UserDriverInstallAllowed`
- size: `224`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000bc30`
- `0x1800121f0`
- `0x1800144b0`

## callees

- `0x18000bf60`
- `0x18000c650`
- `0x18000f210`

## import_xrefs

- `ntdll!NtClose` at `0x18000bfd6`
- `ntdll!NtClose` at `0x18000c017`
- `ntdll!NtClose` at `0x18000bfd6`
- `ntdll!NtClose` at `0x18000c017`

## string_xrefs

- `0x18000bf79`: `Software\Policies\Microsoft\Windows\DriverInstall`

## pseudocode

```c
_BOOL8 UserDriverInstallAllowed()
{
  _BOOL8 result; // rax
  int v1; // ebx
  int Value; // ebx
  HANDLE Handle; // [rsp+50h] [rbp+8h] BYREF
  __int64 v4; // [rsp+58h] [rbp+10h] BYREF
  int v5; // [rsp+60h] [rbp+18h]
  HANDLE KeyHandle; // [rsp+68h] [rbp+20h] BYREF

  Handle = 0;
  KeyHandle = 0;
  v5 = 0;
  result = 0;
  if ( !(unsigned int)pSetupOpenKeyEx(-2147483646, L"Software\\Policies\\Microsoft\\Windows\\DriverInstall", 1, &Handle) )
  {
    v1 = pSetupOpenKeyEx(Handle, L"Restrictions", 1, &KeyHandle);
    NtClose((HANDLE)(unsigned int)Handle);
    if ( !v1 )
    {
      LODWORD(Handle) = 0;
      LODWORD(v4) = 4;
      Value = pSetupQueryValue(KeyHandle, L"AllowUserDeviceClasses", (__int64)&v4);
      NtClose((HANDLE)(unsigned int)KeyHandle);
      if ( !Value && (_DWORD)Handle == 4 && (_DWORD)v4 == 4 && v5 )
        return 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000bf60  push    rbx
0x18000bf62  push    rsi
0x18000bf63  sub     rsp, 38h
0x18000bf67  xor     esi, esi
0x18000bf69  lea     r9, [rsp+48h+Handle]
0x18000bf6e  mov     r8d, 1
0x18000bf74  mov     [rsp+48h+Handle], rsi
0x18000bf79  lea     rdx, aSoftwarePolici; "Software\\Policies\\Microsoft\\Windows"...
0x18000bf80  mov     [rsp+48h+KeyHandle], rsi
0x18000bf85  mov     rcx, 0FFFFFFFF80000002h
0x18000bf8c  mov     [rsp+48h+arg_10], esi
0x18000bf90  call    pSetupOpenKeyEx
0x18000bf95  test    eax, eax
0x18000bf97  jz      short loc_18000BFB4
0x18000bf99  mov     eax, esi
0x18000bf9b  add     rsp, 38h
0x18000bf9f  pop     rsi
0x18000bfa0  pop     rbx
0x18000bfa1  retn
0x18000bfa2  cmp     [rsp+48h+arg_10], esi
0x18000bfa6  jz      short loc_18000BF99
0x18000bfa8  mov     eax, 1
0x18000bfad  add     rsp, 38h
0x18000bfb1  pop     rsi
0x18000bfb2  pop     rbx
0x18000bfb3  retn
0x18000bfb4  mov     rcx, [rsp+48h+Handle]
0x18000bfb9  lea     r9, [rsp+48h+KeyHandle]
0x18000bfbe  mov     r8d, 1
0x18000bfc4  lea     rdx, aRestrictions; "Restrictions"
0x18000bfcb  call    pSetupOpenKeyEx
0x18000bfd0  mov     ecx, dword ptr [rsp+48h+Handle]; Handle
0x18000bfd4  mov     ebx, eax
0x18000bfd6  call    cs:__imp_NtClose
0x18000bfdc  test    ebx, ebx
0x18000bfde  jnz     short loc_18000BF99
0x18000bfe0  mov     rcx, [rsp+48h+KeyHandle]; KeyHandle
0x18000bfe5  lea     rax, [rsp+48h+arg_8]
0x18000bfea  lea     r9, [rsp+48h+arg_10]
0x18000bfef  mov     [rsp+48h+var_28], rax; __int64
0x18000bff4  lea     r8, [rsp+48h+Handle]
0x18000bff9  mov     dword ptr [rsp+48h+Handle], esi
0x18000bffd  lea     rdx, SourceString; "AllowUserDeviceClasses"
0x18000c004  mov     dword ptr [rsp+48h+arg_8], 4
0x18000c00c  call    pSetupQueryValue
0x18000c011  mov     ecx, dword ptr [rsp+48h+KeyHandle]; Handle
0x18000c015  mov     ebx, eax
0x18000c017  call    cs:__imp_NtClose
0x18000c01d  test    ebx, ebx
0x18000c01f  jnz     loc_18000BF99
0x18000c025  cmp     dword ptr [rsp+48h+Handle], 4
0x18000c02a  jnz     loc_18000BF99
0x18000c030  cmp     dword ptr [rsp+48h+arg_8], 4
0x18000c035  jnz     loc_18000BF99
0x18000c03b  jmp     loc_18000BFA2
```
