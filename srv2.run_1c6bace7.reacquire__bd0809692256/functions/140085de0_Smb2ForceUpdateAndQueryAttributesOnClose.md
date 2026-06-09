# Smb2ForceUpdateAndQueryAttributesOnClose

- ea: `0x140085de0`
- end: `0x140085f38`
- name: `Smb2ForceUpdateAndQueryAttributesOnClose`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x140087510`

## callees

- `0x1400152a0`
- `0x140038490`
- `0x140085de0`

## import_xrefs

- `ntoskrnl!NtQueryInformationFile` at `0x140085ead`
- `ntoskrnl!NtQueryInformationFile` at `0x140085ead`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140085ed2`
- `ntoskrnl!PsAssignImpersonationToken` at `0x140085ed2`
- `ntoskrnl!NtSetInformationFile` at `0x140085e79`
- `ntoskrnl!NtSetInformationFile` at `0x140085e79`

## pseudocode

```c
__int64 __fastcall Smb2ForceUpdateAndQueryAttributesOnClose(__int64 a1)
{
  _QWORD *v1; // rbx
  SECURITY_STATUS v2; // esi
  int v3; // edx
  NTSTATUS v4; // edi
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+30h] [rbp-48h] BYREF
  __int128 FileInformation; // [rsp+40h] [rbp-38h] BYREF
  __int128 v8; // [rsp+50h] [rbp-28h]
  __int64 v9; // [rsp+60h] [rbp-18h]

  v1 = *(_QWORD **)(a1 + 560);
  FileInformation = 0;
  v8 = 0;
  v9 = 0;
  IoStatusBlock = 0;
  if ( !v1[10] )
    return 3221225768LL;
  v2 = Smb2ImpersonateWorkItem((__int64)v1);
  v3 = *(_DWORD *)(v1[9] + 184LL);
  if ( (v3 & 2) == 0
    && (v3 & 0x100) == 0
    && (v3 & 0x10) == 0
    && (v3 & 4) == 0
    && (v3 & 0x40000) == 0
    && (v3 & 0x80000) == 0
    || (FileInformation = 0,
        v8 = 0,
        v9 = 0,
        v4 = NtSetInformationFile(
               *(HANDLE *)(v1[10] + 88LL),
               &IoStatusBlock,
               &FileInformation,
               0x28u,
               FileBasicInformation),
        v4 >= 0) )
  {
    v4 = NtQueryInformationFile(*(HANDLE *)(v1[10] + 88LL), &IoStatusBlock, v1 + 25, 0x38u, FileNetworkOpenInformation);
  }
  if ( v2 >= 0 )
    PsAssignImpersonationToken(KeGetCurrentThread(), 0);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x140085de0  mov     r11, rsp
0x140085de3  push    rbx
0x140085de4  sub     rsp, 70h
0x140085de8  mov     rax, cs:__security_cookie
0x140085def  xor     rax, rsp
0x140085df2  mov     [rsp+78h+var_10], rax
0x140085df7  mov     rbx, [rcx+230h]
0x140085dfe  xorps   xmm0, xmm0
0x140085e01  xor     eax, eax
0x140085e03  movups  [rsp+78h+FileInformation], xmm0
0x140085e08  movups  [rsp+78h+var_28], xmm0
0x140085e0d  mov     [r11-18h], rax
0x140085e11  movups  xmmword ptr [rsp+78h+IoStatusBlock], xmm0
0x140085e16  cmp     [rbx+50h], rax
0x140085e1a  jz      loc_140085F31
0x140085e20  mov     [r11+10h], rsi
0x140085e24  mov     rcx, rbx
0x140085e27  mov     [r11+18h], rdi
0x140085e2b  call    Smb2ImpersonateWorkItem
0x140085e30  mov     rcx, [rbx+48h]
0x140085e34  mov     esi, eax
0x140085e36  mov     edx, [rcx+0B8h]
0x140085e3c  test    dl, 2
0x140085e3f  jz      loc_140085EFC
0x140085e45  xorps   xmm0, xmm0
0x140085e48  mov     [rsp+78h+FileInformationClass], 4; FileInformationClass
0x140085e50  movups  [rsp+78h+FileInformation], xmm0
0x140085e55  xor     eax, eax
0x140085e57  mov     r9d, 28h ; '('; Length
0x140085e5d  movups  [rsp+78h+var_28], xmm0
0x140085e62  mov     [rsp+78h+var_18], rax
0x140085e67  lea     r8, [rsp+78h+FileInformation]; FileInformation
0x140085e6c  mov     rcx, [rbx+50h]
0x140085e70  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x140085e75  mov     rcx, [rcx+58h]; FileHandle
0x140085e79  call    cs:__imp_NtSetInformationFile
0x140085e80  nop     dword ptr [rax+rax+00h]
0x140085e85  mov     edi, eax
0x140085e87  test    eax, eax
0x140085e89  js      short loc_140085EBB
0x140085e8b  mov     rcx, [rbx+50h]
0x140085e8f  lea     r8, [rbx+0C8h]; FileInformation
0x140085e96  mov     r9d, 38h ; '8'; Length
0x140085e9c  mov     [rsp+78h+FileInformationClass], 22h ; '"'; FileInformationClass
0x140085ea4  lea     rdx, [rsp+78h+IoStatusBlock]; IoStatusBlock
0x140085ea9  mov     rcx, [rcx+58h]; FileHandle
0x140085ead  call    cs:__imp_NtQueryInformationFile
0x140085eb4  nop     dword ptr [rax+rax+00h]
0x140085eb9  mov     edi, eax
0x140085ebb  test    esi, esi
0x140085ebd  mov     rsi, [rsp+78h+arg_8]
0x140085ec5  js      short loc_140085EDE
0x140085ec7  mov     rcx, gs:188h; Thread
0x140085ed0  xor     edx, edx; Token
0x140085ed2  call    cs:__imp_PsAssignImpersonationToken
0x140085ed9  nop     dword ptr [rax+rax+00h]
0x140085ede  mov     eax, edi
0x140085ee0  mov     rdi, [rsp+78h+arg_10]
0x140085ee8  mov     rcx, [rsp+78h+var_10]
0x140085eed  xor     rcx, rsp; StackCookie
0x140085ef0  call    __security_check_cookie
0x140085ef5  add     rsp, 70h
0x140085ef9  pop     rbx
0x140085efa  retn
0x140085efc  bt      edx, 8
0x140085f00  jb      loc_140085E45
0x140085f06  test    dl, 10h
0x140085f09  jnz     loc_140085E45
0x140085f0f  test    dl, 4
0x140085f12  jnz     loc_140085E45
0x140085f18  bt      edx, 12h
0x140085f1c  jb      loc_140085E45
0x140085f22  bt      edx, 13h
0x140085f26  jnb     loc_140085E8B
0x140085f2c  jmp     loc_140085E45
0x140085f31  mov     eax, 0C0000128h
0x140085f36  jmp     short loc_140085EE8
```
