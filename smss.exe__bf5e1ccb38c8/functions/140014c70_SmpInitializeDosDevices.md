# SmpInitializeDosDevices

- ea: `0x140014c70`
- end: `0x140014e24`
- name: `SmpInitializeDosDevices`
- size: `436`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x14000c638`

## callees

- `0x1400010ec`
- `0x14000d494`
- `0x140014c70`

## import_xrefs

- `ntdll!NtClose` at `0x140014d89`
- `ntdll!NtClose` at `0x140014ddb`
- `ntdll!NtClose` at `0x140014d89`
- `ntdll!NtClose` at `0x140014ddb`
- `ntdll!NtOpenDirectoryObject` at `0x140014cdb`
- `ntdll!NtOpenDirectoryObject` at `0x140014cdb`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140014d6c`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140014daa`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140014d6c`
- `ntdll!NtCreateSymbolicLinkObject` at `0x140014daa`
- `ntdll!NtMakeTemporaryObject` at `0x140014d7f`
- `ntdll!NtMakeTemporaryObject` at `0x140014d7f`

## pseudocode

```c
__int64 SmpInitializeDosDevices()
{
  NTSTATUS v0; // edi
  const wchar_t *v1; // r8
  __int64 v2; // rdx
  __int64 v3; // rsi
  __int16 v4; // r14
  __int64 v5; // rbx
  __int64 v7; // [rsp+20h] [rbp-40h] BYREF
  const wchar_t *v8; // [rsp+28h] [rbp-38h]
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *SymbolicLinkHandle; // [rsp+90h] [rbp+30h] BYREF

  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 208;
  v8 = L"\\??";
  SymbolicLinkHandle = 0;
  ObjectAttributes.ObjectName = (PUNICODE_STRING)&v7;
  v7 = 524294;
  ObjectAttributes.RootDirectory = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenDirectoryObject(&SmpDosDevicesObjectDirectory, 0xF000Fu, &ObjectAttributes);
  if ( v0 >= 0 )
  {
    v3 = SmpDosDevicesList;
    v4 = 0;
    while ( (__int64 *)v3 != &SmpDosDevicesList )
    {
      ObjectAttributes.RootDirectory = SmpDosDevicesObjectDirectory;
      ObjectAttributes.ObjectName = (PUNICODE_STRING)(v3 + 16);
      ObjectAttributes.Length = 48;
      ObjectAttributes.Attributes = 208;
      ObjectAttributes.SecurityDescriptor = SmpPrimarySecurityDescriptor;
      ObjectAttributes.SecurityQualityOfService = 0;
      if ( SmpPrimarySecurityDescriptor )
      {
        v4 = *((_WORD *)SmpPrimarySecurityDescriptor + 1) & 8;
        *((_WORD *)SmpPrimarySecurityDescriptor + 1) |= 8u;
      }
      v0 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)(v3 + 32));
      if ( v0 == 0x40000000 )
      {
        NtMakeTemporaryObject(SymbolicLinkHandle);
        NtClose(SymbolicLinkHandle);
        if ( *(_WORD *)(v3 + 32) )
        {
          ObjectAttributes.Attributes &= ~0x80u;
          v0 = NtCreateSymbolicLinkObject(&SymbolicLinkHandle, 0xF0001u, &ObjectAttributes, (PUNICODE_STRING)(v3 + 32));
        }
        else
        {
          v0 = 0;
        }
      }
      if ( ObjectAttributes.SecurityDescriptor )
        *((_WORD *)ObjectAttributes.SecurityDescriptor + 1) ^= (v4
                                                              ^ *((_WORD *)ObjectAttributes.SecurityDescriptor + 1))
                                                             & 8;
      if ( v0 < 0 )
      {
        v1 = *(const wchar_t **)(v3 + 24);
        v2 = 3625;
        goto LABEL_16;
      }
      v5 = v3;
      NtClose(SymbolicLinkHandle);
      v3 = *(_QWORD *)v3;
      SmpFreeSavedRegistryEntry(v5);
    }
  }
  else
  {
    v1 = v8;
    v2 = 3573;
LABEL_16:
    SmpLogFailureString("SmpInitializeDosDevices", v2, v1, (unsigned int)v0);
  }
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x140014c70  mov     [rsp-28h+arg_8], rbx
0x140014c75  mov     [rsp-28h+arg_10], rsi
0x140014c7a  push    rbp
0x140014c7b  push    rdi
0x140014c7c  push    r12
0x140014c7e  push    r14
0x140014c80  push    r15
0x140014c82  mov     rbp, rsp
0x140014c85  sub     rsp, 60h
0x140014c89  xor     r15d, r15d
0x140014c8c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140014c94  lea     rax, asc_140028040; "\\??"
0x140014c9b  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0D0h
0x140014ca3  mov     [rbp+var_38], rax
0x140014ca7  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140014cab  lea     rax, [rbp+var_40]
0x140014caf  mov     [rbp+SymbolicLinkHandle], r15
0x140014cb3  xorps   xmm0, xmm0
0x140014cb6  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140014cba  mov     edx, 0F000Fh; DesiredAccess
0x140014cbf  mov     [rbp+var_40], 80006h
0x140014cc7  lea     rcx, SmpDosDevicesObjectDirectory; FileHandle
0x140014cce  mov     [rbp+ObjectAttributes.RootDirectory], r15
0x140014cd2  lea     r12d, [r15+8]
0x140014cd6  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140014cdb  call    cs:__imp_NtOpenDirectoryObject
0x140014ce1  mov     edi, eax
0x140014ce3  test    eax, eax
0x140014ce5  jns     short loc_140014CF5
0x140014ce7  mov     r8, [rbp+var_38]
0x140014ceb  mov     edx, 0DF5h
0x140014cf0  jmp     loc_140014DFA
0x140014cf5  mov     rsi, cs:SmpDosDevicesList
0x140014cfc  mov     r14d, r15d
0x140014cff  lea     rax, SmpDosDevicesList
0x140014d06  cmp     rsi, rax
0x140014d09  jz      loc_140014E09
0x140014d0f  mov     rax, cs:SmpDosDevicesObjectDirectory
0x140014d16  mov     rdx, cs:SmpPrimarySecurityDescriptor
0x140014d1d  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x140014d21  lea     rax, [rsi+10h]
0x140014d25  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140014d29  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140014d30  mov     [rbp+ObjectAttributes.Attributes], 0D0h
0x140014d37  mov     [rbp+ObjectAttributes.SecurityDescriptor], rdx
0x140014d3b  mov     [rbp+ObjectAttributes.SecurityQualityOfService], r15
0x140014d3f  test    rdx, rdx
0x140014d42  jz      short loc_140014D58
0x140014d44  movzx   ecx, word ptr [rdx+2]
0x140014d48  movzx   r14d, cx
0x140014d4c  and     r14w, r12w
0x140014d50  or      cx, r12w
0x140014d54  mov     [rdx+2], cx
0x140014d58  lea     rbx, [rsi+20h]
0x140014d5c  mov     edx, 0F0001h; DesiredAccess
0x140014d61  mov     r9, rbx; Name
0x140014d64  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140014d68  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x140014d6c  call    cs:__imp_NtCreateSymbolicLinkObject
0x140014d72  mov     edi, eax
0x140014d74  cmp     eax, 40000000h
0x140014d79  jnz     short loc_140014DB7
0x140014d7b  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x140014d7f  call    cs:__imp_NtMakeTemporaryObject
0x140014d85  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x140014d89  call    cs:__imp_NtClose
0x140014d8f  cmp     [rbx], r15w
0x140014d93  jz      short loc_140014DB4
0x140014d95  btr     [rbp+ObjectAttributes.Attributes], 7
0x140014d9a  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140014d9e  mov     r9, rbx; Name
0x140014da1  lea     rcx, [rbp+SymbolicLinkHandle]; SymbolicLinkHandle
0x140014da5  mov     edx, 0F0001h; DesiredAccess
0x140014daa  call    cs:__imp_NtCreateSymbolicLinkObject
0x140014db0  mov     edi, eax
0x140014db2  jmp     short loc_140014DB7
0x140014db4  mov     edi, r15d
0x140014db7  mov     rcx, [rbp+ObjectAttributes.SecurityDescriptor]
0x140014dbb  test    rcx, rcx
0x140014dbe  jz      short loc_140014DD0
0x140014dc0  movzx   eax, word ptr [rcx+2]
0x140014dc4  xor     ax, r14w
0x140014dc8  and     ax, r12w
0x140014dcc  xor     [rcx+2], ax
0x140014dd0  test    edi, edi
0x140014dd2  js      short loc_140014DF1
0x140014dd4  mov     rcx, [rbp+SymbolicLinkHandle]; Handle
0x140014dd8  mov     rbx, rsi
0x140014ddb  call    cs:__imp_NtClose
0x140014de1  mov     rsi, [rsi]
0x140014de4  mov     rcx, rbx
0x140014de7  call    SmpFreeSavedRegistryEntry
0x140014dec  jmp     loc_140014CFF
0x140014df1  mov     r8, [rsi+18h]
0x140014df5  mov     edx, 0E29h
0x140014dfa  mov     r9d, edi
0x140014dfd  lea     rcx, aSmpinitialized; "SmpInitializeDosDevices"
0x140014e04  call    SmpLogFailureString
0x140014e09  lea     r11, [rsp+60h+var_s0]
0x140014e0e  mov     eax, edi
0x140014e10  mov     rbx, [r11+38h]
0x140014e14  mov     rsi, [r11+40h]
0x140014e18  mov     rsp, r11
0x140014e1b  pop     r15
0x140014e1d  pop     r14
0x140014e1f  pop     r12
0x140014e21  pop     rdi
0x140014e22  pop     rbp
0x140014e23  retn
```
