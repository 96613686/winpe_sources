# WintrustUserWriteabilityCheckWorker(void *)

- ea: `0x180042a4c`
- end: `0x180042b8d`
- name: `?WintrustUserWriteabilityCheckWorker@@YAHPEAX@Z`
- size: `321`
- prototype: `__int64 __fastcall(HANDLE Handle)`
- caller_count: `3`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800268a0`
- `0x180040550`
- `0x180043f70`

## callees

- `0x180042a4c`
- `0x18004b91c`
- `0x18004deb0`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042b3e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180042b3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b6e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b30`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180042b6e`
- `ntdll!NtQuerySecurityObject` at `0x180042b10`
- `ntdll!NtQuerySecurityObject` at `0x180042b10`
- `ntdll!ZwQueryVolumeInformationFile` at `0x180042a9f`
- `ntdll!ZwQueryVolumeInformationFile` at `0x180042ac4`
- `ntdll!ZwQueryVolumeInformationFile` at `0x180042a9f`
- `ntdll!ZwQueryVolumeInformationFile` at `0x180042ac4`

## pseudocode

```c
__int64 __fastcall WintrustUserWriteabilityCheckWorker(HANDLE Handle)
{
  void *v1; // rbx
  unsigned __int8 v2; // di
  NTSTATUS v4; // eax
  ULONG v5; // r9d
  NTSTATUS v6; // eax
  HLOCAL v7; // rax
  ULONG LengthNeeded; // [rsp+34h] [rbp-44h] BYREF
  __int64 FsInformation; // [rsp+38h] [rbp-40h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+40h] [rbp-38h] BYREF
  __int128 v12; // [rsp+50h] [rbp-28h] BYREF

  v1 = 0;
  LengthNeeded = 0;
  FsInformation = 0;
  v2 = 1;
  IoStatusBlock = 0;
  v12 = 0;
  if ( ZwQueryVolumeInformationFile(Handle, &IoStatusBlock, &FsInformation, 8u, FileFsDeviceInformation) >= 0 )
  {
    v4 = ZwQueryVolumeInformationFile(Handle, &IoStatusBlock, &v12, 0x10u, FileFsAttributeInformation);
    if ( v4 >= 0 || v4 == -2147483643 && IoStatusBlock.Information >= 0xC )
    {
      if ( (v12 & 8) == 0 )
        return v2;
      if ( (FsInformation & 0x1000000000LL) != 0 )
        return 0;
      v5 = 0;
      while ( 1 )
      {
        v6 = NtQuerySecurityObject(Handle, 5u, v1, v5, &LengthNeeded);
        if ( v6 >= 0 )
          break;
        if ( v6 != -2147483643 && v6 != -1073741789 )
          goto LABEL_18;
        if ( v1 )
          LocalFree(v1);
        v7 = LocalAlloc(0x40u, LengthNeeded);
        if ( !v7 )
          goto LABEL_18;
        v5 = LengthNeeded;
        v1 = v7;
      }
      if ( (int)SIPolicyIsSecurityDescriptorUserWriteable(v1) >= 0 )
        v2 = 1;
    }
  }
LABEL_18:
  if ( v1 )
    LocalFree(v1);
  return v2;
}

```

## disassembly

```asm
0x180042a4c  push    rbp
0x180042a4e  push    rbx
0x180042a4f  push    rsi
0x180042a50  push    rdi
0x180042a51  mov     rbp, rsp
0x180042a54  sub     rsp, 78h
0x180042a58  mov     rax, cs:__security_cookie
0x180042a5f  xor     rax, rsp
0x180042a62  mov     [rbp+var_18], rax
0x180042a66  xor     ebx, ebx
0x180042a68  mov     [rbp+LengthNeeded], 0
0x180042a6f  xorps   xmm0, xmm0
0x180042a72  mov     [rbp+FsInformation], rbx
0x180042a76  xorps   xmm1, xmm1
0x180042a79  mov     [rsp+78h+FsInformationClass], 4; FsInformationClass
0x180042a81  mov     dil, 1
0x180042a84  lea     r8, [rbp+FsInformation]; FsInformation
0x180042a88  lea     r9d, [rbx+8]; Length
0x180042a8c  mov     [rbp+var_48], dil
0x180042a90  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180042a94  mov     rsi, rcx
0x180042a97  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x180042a9b  movups  [rbp+var_28], xmm1
0x180042a9f  call    cs:__imp_ZwQueryVolumeInformationFile
0x180042aa5  test    eax, eax
0x180042aa7  js      loc_180042B66
0x180042aad  lea     r9d, [rbx+10h]; Length
0x180042ab1  mov     [rsp+78h+FsInformationClass], 5; FsInformationClass
0x180042ab9  lea     r8, [rbp+var_28]; FsInformation
0x180042abd  mov     rcx, rsi; FileHandle
0x180042ac0  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180042ac4  call    cs:__imp_ZwQueryVolumeInformationFile
0x180042aca  test    eax, eax
0x180042acc  jns     short loc_180042AE4
0x180042ace  cmp     eax, 80000005h
0x180042ad3  jnz     loc_180042B66
0x180042ad9  cmp     [rbp+IoStatusBlock.Information], 0Ch
0x180042ade  jb      loc_180042B66
0x180042ae4  test    byte ptr [rbp+var_28], 8
0x180042ae8  jz      loc_180042B74
0x180042aee  test    byte ptr [rbp+FsInformation+4], 10h
0x180042af2  jz      short loc_180042AF9
0x180042af4  xor     dil, dil
0x180042af7  jmp     short loc_180042B74
0x180042af9  xor     r9d, r9d; Length
0x180042afc  lea     rax, [rbp+LengthNeeded]
0x180042b00  mov     r8, rbx; SecurityDescriptor
0x180042b03  mov     edx, 5; SecurityInformation
0x180042b08  mov     qword ptr [rsp+78h+FsInformationClass], rax; LengthNeeded
0x180042b0d  mov     rcx, rsi; Handle
0x180042b10  call    cs:__imp_NtQuerySecurityObject
0x180042b16  test    eax, eax
0x180042b18  jns     short loc_180042B52
0x180042b1a  cmp     eax, 80000005h
0x180042b1f  jz      short loc_180042B28
0x180042b21  cmp     eax, 0C0000023h
0x180042b26  jnz     short loc_180042B66
0x180042b28  test    rbx, rbx
0x180042b2b  jz      short loc_180042B36
0x180042b2d  mov     rcx, rbx; hMem
0x180042b30  call    cs:__imp_LocalFree
0x180042b36  mov     edx, [rbp+LengthNeeded]; uBytes
0x180042b39  mov     ecx, 40h ; '@'; uFlags
0x180042b3e  call    cs:__imp_LocalAlloc
0x180042b44  test    rax, rax
0x180042b47  jz      short loc_180042B66
0x180042b49  mov     r9d, [rbp+LengthNeeded]
0x180042b4d  mov     rbx, rax
0x180042b50  jmp     short loc_180042AFC
0x180042b52  lea     rdx, [rbp+var_48]
0x180042b56  mov     rcx, rbx; SecurityDescriptor
0x180042b59  call    SIPolicyIsSecurityDescriptorUserWriteable
0x180042b5e  test    eax, eax
0x180042b60  js      short loc_180042B66
0x180042b62  mov     dil, [rbp+var_48]
0x180042b66  test    rbx, rbx
0x180042b69  jz      short loc_180042B74
0x180042b6b  mov     rcx, rbx; hMem
0x180042b6e  call    cs:__imp_LocalFree
0x180042b74  movzx   eax, dil
0x180042b78  mov     rcx, [rbp+var_18]
0x180042b7c  xor     rcx, rsp; StackCookie
0x180042b7f  call    __security_check_cookie
0x180042b84  add     rsp, 78h
0x180042b88  pop     rdi
0x180042b89  pop     rsi
0x180042b8a  pop     rbx
0x180042b8b  pop     rbp
0x180042b8c  retn
```
