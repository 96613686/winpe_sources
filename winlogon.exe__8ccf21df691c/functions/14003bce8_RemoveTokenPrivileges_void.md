# RemoveTokenPrivileges(void)

- ea: `0x14003bce8`
- end: `0x14003be14`
- name: `?RemoveTokenPrivileges@@YAJXZ`
- size: `300`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x1400877f0`

## callees

- `0x14003bce8`
- `0x140053720`

## import_xrefs

- `ntdll!RtlRemovePrivileges` at `0x14003bde1`
- `ntdll!RtlRemovePrivileges` at `0x14003bde1`
- `ntdll!NtOpenProcessToken` at `0x14003bdc5`
- `ntdll!NtOpenProcessToken` at `0x14003bdc5`
- `ntdll!NtClose` at `0x14003bdf3`
- `ntdll!NtClose` at `0x14009e6f4`
- `ntdll!NtClose` at `0x14003bdf3`
- `ntdll!NtClose` at `0x14009e6f4`

## pseudocode

```c
__int64 RemoveTokenPrivileges(void)
{
  NTSTATUS v0; // ebx
  void *TokenHandle; // [rsp+20h] [rbp-88h] BYREF
  _DWORD v3[24]; // [rsp+30h] [rbp-78h] BYREF

  TokenHandle = 0;
  v3[0] = 7;
  v3[1] = 20;
  v3[2] = 9;
  v3[3] = 31;
  v3[4] = 30;
  v3[5] = 3;
  v3[6] = 5;
  v3[7] = 13;
  v3[8] = 14;
  v3[9] = 16;
  v3[10] = 29;
  v3[11] = 21;
  v3[12] = 8;
  v3[13] = 22;
  v3[14] = 23;
  v3[15] = 17;
  v3[16] = 18;
  v3[17] = 19;
  v3[18] = 10;
  v3[19] = 28;
  v3[20] = 25;
  v0 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x28u, &TokenHandle);
  if ( v0 >= 0 )
    v0 = RtlRemovePrivileges(TokenHandle, v3, 21);
  if ( TokenHandle )
    NtClose(TokenHandle);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x14003bce8  push    rbx
0x14003bcea  sub     rsp, 0A0h
0x14003bcf1  mov     rax, cs:__security_cookie
0x14003bcf8  xor     rax, rsp
0x14003bcfb  mov     [rsp+0A8h+var_18], rax
0x14003bd03  mov     [rsp+0A8h+TokenHandle], 0
0x14003bd0c  mov     [rsp+0A8h+var_78], 7
0x14003bd14  mov     [rsp+0A8h+var_74], 14h
0x14003bd1c  mov     [rsp+0A8h+var_70], 9
0x14003bd24  mov     [rsp+0A8h+var_6C], 1Fh
0x14003bd2c  mov     [rsp+0A8h+var_68], 1Eh
0x14003bd34  mov     [rsp+0A8h+var_64], 3
0x14003bd3c  mov     [rsp+0A8h+var_60], 5
0x14003bd44  mov     [rsp+0A8h+var_5C], 0Dh
0x14003bd4c  mov     [rsp+0A8h+var_58], 0Eh
0x14003bd54  mov     [rsp+0A8h+var_54], 10h
0x14003bd5c  mov     [rsp+0A8h+var_50], 1Dh
0x14003bd64  mov     [rsp+0A8h+var_4C], 15h
0x14003bd6c  mov     [rsp+0A8h+var_48], 8
0x14003bd74  mov     [rsp+0A8h+var_44], 16h
0x14003bd7c  mov     [rsp+0A8h+var_40], 17h
0x14003bd84  mov     [rsp+0A8h+var_3C], 11h
0x14003bd8c  mov     [rsp+0A8h+var_38], 12h
0x14003bd94  mov     [rsp+0A8h+var_34], 13h
0x14003bd9c  mov     [rsp+0A8h+var_30], 0Ah
0x14003bda4  mov     [rsp+0A8h+var_2C], 1Ch
0x14003bdac  mov     [rsp+0A8h+var_28], 19h
0x14003bdb7  lea     r8, [rsp+0A8h+TokenHandle]; TokenHandle
0x14003bdbc  mov     edx, 28h ; '('; DesiredAccess
0x14003bdc1  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x14003bdc5  call    cs:__imp_NtOpenProcessToken
0x14003bdcb  mov     ebx, eax
0x14003bdcd  test    eax, eax
0x14003bdcf  js      short loc_14003BDE9
0x14003bdd1  mov     r8d, 15h
0x14003bdd7  lea     rdx, [rsp+0A8h+var_78]
0x14003bddc  mov     rcx, [rsp+0A8h+TokenHandle]
0x14003bde1  call    cs:__imp_RtlRemovePrivileges
0x14003bde7  mov     ebx, eax
0x14003bde9  mov     rcx, [rsp+0A8h+TokenHandle]; Handle
0x14003bdee  test    rcx, rcx
0x14003bdf1  jz      short loc_14003BDF9
0x14003bdf3  call    cs:__imp_NtClose
0x14003bdf9  mov     eax, ebx
0x14003bdfb  mov     rcx, [rsp+0A8h+var_18]
0x14003be03  xor     rcx, rsp; StackCookie
0x14003be06  call    __security_check_cookie
0x14003be0b  add     rsp, 0A0h
0x14003be12  pop     rbx
0x14003be13  retn
0x14009e6e2  push    rbp
0x14009e6e4  sub     rsp, 20h
0x14009e6e8  mov     rbp, rdx
0x14009e6eb  mov     rcx, [rbp+20h]; Handle
0x14009e6ef  test    rcx, rcx
0x14009e6f2  jz      short loc_14009E6FB
0x14009e6f4  call    cs:__imp_NtClose
0x14009e6fa  nop
0x14009e6fb  add     rsp, 20h
0x14009e6ff  pop     rbp
0x14009e700  retn
```
