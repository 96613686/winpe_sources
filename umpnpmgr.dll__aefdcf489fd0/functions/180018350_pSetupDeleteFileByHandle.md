# pSetupDeleteFileByHandle

- ea: `0x180018350`
- end: `0x180018458`
- name: `pSetupDeleteFileByHandle`
- size: `264`
- prototype: `_BOOL8 __fastcall(HANDLE FileHandle)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18001725c`

## callees

- `0x180018350`
- `0x180018970`

## import_xrefs

- `ntdll!NtSetInformationFile` at `0x1800183f5`
- `ntdll!NtSetInformationFile` at `0x180018414`
- `ntdll!NtSetInformationFile` at `0x1800183f5`
- `ntdll!NtSetInformationFile` at `0x180018414`
- `ntdll!NtQueryInformationFile` at `0x1800183b6`
- `ntdll!NtQueryInformationFile` at `0x1800183b6`
- `ntdll!RtlNtStatusToDosError` at `0x180018420`
- `ntdll!RtlNtStatusToDosError` at `0x180018420`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001842a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001842a`

## pseudocode

```c
_BOOL8 __fastcall pSetupDeleteFileByHandle(HANDLE FileHandle)
{
  DWORD v2; // ebx
  int v3; // eax
  char v5[8]; // [rsp+30h] [rbp-50h] BYREF
  _IO_STATUS_BLOCK IoStatusBlock; // [rsp+38h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+48h] [rbp-38h] BYREF
  __int128 v8; // [rsp+58h] [rbp-28h]
  __int64 v9; // [rsp+68h] [rbp-18h]

  v5[0] = 1;
  v9 = 0;
  IoStatusBlock = 0;
  FileInformation = 0;
  v8 = 0;
  if ( FileHandle == (HANDLE)-1LL )
  {
    v2 = 87;
  }
  else
  {
    v2 = 0;
    if ( NtQueryInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation) >= 0
      && (v9 & 1) != 0 )
    {
      v9 = 128;
      FileInformation = 0;
      v8 = 0;
      NtSetInformationFile(FileHandle, &IoStatusBlock, &FileInformation, 0x28u, FileBasicInformation);
    }
    v3 = NtSetInformationFile(FileHandle, &IoStatusBlock, v5, 1u, FileDispositionInformation);
    if ( v3 < 0 )
      v2 = RtlNtStatusToDosError(v3);
  }
  SetLastError(v2);
  return v2 == 0;
}

```

## disassembly

```asm
0x180018350  mov     [rsp-8+arg_8], rbx
0x180018355  mov     [rsp-8+arg_10], rdi
0x18001835a  push    rbp
0x18001835b  mov     rbp, rsp
0x18001835e  sub     rsp, 80h
0x180018365  mov     rax, cs:__security_cookie
0x18001836c  xor     rax, rsp
0x18001836f  mov     [rbp+var_10], rax
0x180018373  xor     eax, eax
0x180018375  mov     [rbp+var_50], 1
0x180018379  mov     [rbp+var_18], rax
0x18001837d  xorps   xmm1, xmm1
0x180018380  xorps   xmm0, xmm0
0x180018383  mov     rdi, rcx
0x180018386  movups  xmmword ptr [rbp+IoStatusBlock], xmm0
0x18001838a  movups  [rbp+FileInformation], xmm1
0x18001838e  movups  [rbp+var_28], xmm1
0x180018392  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180018396  jnz     short loc_1800183A0
0x180018398  lea     ebx, [rcx+58h]
0x18001839b  jmp     loc_180018428
0x1800183a0  xor     ebx, ebx
0x1800183a2  mov     [rsp+80h+FileInformationClass], 4; FileInformationClass
0x1800183aa  lea     r8, [rbp+FileInformation]; FileInformation
0x1800183ae  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1800183b2  lea     r9d, [rbx+28h]; Length
0x1800183b6  call    cs:__imp_NtQueryInformationFile
0x1800183bc  test    eax, eax
0x1800183be  js      short loc_1800183FB
0x1800183c0  test    byte ptr [rbp+var_18], 1
0x1800183c4  jz      short loc_1800183FB
0x1800183c6  xorps   xmm0, xmm0
0x1800183c9  mov     [rsp+80h+FileInformationClass], 4; FileInformationClass
0x1800183d1  xor     eax, eax
0x1800183d3  lea     r9d, [rbx+28h]; Length
0x1800183d7  mov     [rbp+var_18], rax
0x1800183db  lea     r8, [rbp+FileInformation]; FileInformation
0x1800183df  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x1800183e3  mov     dword ptr [rbp+var_18], 80h
0x1800183ea  mov     rcx, rdi; FileHandle
0x1800183ed  movups  [rbp+FileInformation], xmm0
0x1800183f1  movups  [rbp+var_28], xmm0
0x1800183f5  call    cs:__imp_NtSetInformationFile
0x1800183fb  mov     r9d, 1; Length
0x180018401  mov     [rsp+80h+FileInformationClass], 0Dh; FileInformationClass
0x180018409  lea     r8, [rbp+var_50]; FileInformation
0x18001840d  mov     rcx, rdi; FileHandle
0x180018410  lea     rdx, [rbp+IoStatusBlock]; IoStatusBlock
0x180018414  call    cs:__imp_NtSetInformationFile
0x18001841a  test    eax, eax
0x18001841c  jns     short loc_180018428
0x18001841e  mov     ecx, eax; Status
0x180018420  call    cs:__imp_RtlNtStatusToDosError
0x180018426  mov     ebx, eax
0x180018428  mov     ecx, ebx; dwErrCode
0x18001842a  call    cs:__imp_SetLastError
0x180018430  xor     eax, eax
0x180018432  test    ebx, ebx
0x180018434  setz    al
0x180018437  mov     rcx, [rbp+var_10]
0x18001843b  xor     rcx, rsp; StackCookie
0x18001843e  call    __security_check_cookie
0x180018443  lea     r11, [rsp+80h+var_s0]
0x18001844b  mov     rbx, [r11+18h]
0x18001844f  mov     rdi, [r11+20h]
0x180018453  mov     rsp, r11
0x180018456  pop     rbp
0x180018457  retn
```
