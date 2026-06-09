# WerpCreateRegistryKey

- ea: `0x14000dfd0`
- end: `0x14000e18e`
- name: `WerpCreateRegistryKey`
- size: `446`
- prototype: `__int64 __fastcall(void *, const WCHAR *, ACCESS_MASK, char, void **KeyHandle, bool *)`
- caller_count: `4`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14000d1d0`
- `0x14000e464`
- `0x14000e83c`
- `0x1400122c0`

## callees

- `0x140002750`
- `0x14000dfd0`

## import_xrefs

- `ntoskrnl!DbgPrintEx` at `0x14000e125`
- `ntoskrnl!DbgPrintEx` at `0x14000e155`
- `ntoskrnl!DbgPrintEx` at `0x14000e125`
- `ntoskrnl!DbgPrintEx` at `0x14000e155`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e083`
- `ntoskrnl!RtlSetOwnerSecurityDescriptor` at `0x14000e083`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a0`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000e0a0`
- `ntoskrnl!ZwCreateKey` at `0x14000e101`
- `ntoskrnl!ZwCreateKey` at `0x14000e101`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e062`
- `ntoskrnl!RtlCreateSecurityDescriptor` at `0x14000e062`

## string_xrefs

- `0x14000e118`: `WERKERNELHOST: ZwCreateKey failed with scode 0x%x\n`

## pseudocode

```c
__int64 __fastcall WerpCreateRegistryKey(
        void *a1,
        const WCHAR *a2,
        ACCESS_MASK a3,
        char a4,
        void **KeyHandle,
        bool *a6)
{
  NTSTATUS v10; // ebx
  NTSTATUS v11; // eax
  ULONG Disposition; // [rsp+40h] [rbp-79h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-71h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+78h] [rbp-41h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+88h] [rbp-31h] BYREF
  __int64 v17; // [rsp+A8h] [rbp-11h]
  _DWORD Owner[4]; // [rsp+B0h] [rbp-9h] BYREF

  v17 = 0;
  Owner[0] = 257;
  Owner[1] = 83886080;
  Owner[2] = 18;
  Disposition = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( a2 && KeyHandle )
  {
    v10 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
    if ( v10 >= 0 )
    {
      v10 = RtlSetOwnerSecurityDescriptor(SecurityDescriptor, Owner, 0);
      if ( v10 >= 0 )
      {
        RtlInitUnicodeString(&DestinationString, a2);
        ObjectAttributes.Length = 48;
        ObjectAttributes.ObjectName = &DestinationString;
        ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
        ObjectAttributes.RootDirectory = a1;
        ObjectAttributes.Attributes = 576;
        ObjectAttributes.SecurityQualityOfService = 0;
        v11 = ZwCreateKey(KeyHandle, a3, &ObjectAttributes, 0, 0, a4 != 0, &Disposition);
        v10 = v11;
        if ( v11 >= 0 )
        {
          if ( a6 )
            *a6 = Disposition == 1;
          return 0;
        }
        else
        {
          DbgPrintEx(5u, 1u, "WERKERNELHOST: ZwCreateKey failed with scode 0x%x\n", v11);
        }
      }
    }
    return (unsigned int)v10;
  }
  else
  {
    DbgPrintEx(5u, 1u, "WERKERNELHOST: Invalid params\n");
    return 3221225485LL;
  }
}

```

## disassembly

```asm
0x14000dfd0  mov     [rsp-8+arg_18], rbx
0x14000dfd5  push    rbp
0x14000dfd6  push    rsi
0x14000dfd7  push    rdi
0x14000dfd8  push    r12
0x14000dfda  push    r13
0x14000dfdc  push    r14
0x14000dfde  push    r15
0x14000dfe0  lea     rbp, [rsp-17h]
0x14000dfe5  sub     rsp, 0D0h
0x14000dfec  mov     rax, cs:__security_cookie
0x14000dff3  xor     rax, rsp
0x14000dff6  mov     [rbp+47h+var_40], rax
0x14000dffa  mov     rsi, [rbp+47h+KeyHandle]
0x14000dffe  xorps   xmm0, xmm0
0x14000e001  mov     rdi, [rbp+47h+arg_28]
0x14000e005  xor     eax, eax
0x14000e007  mov     [rbp+47h+var_58], rax
0x14000e00b  mov     r12, rcx
0x14000e00e  mov     [rbp+47h+Owner], 101h
0x14000e015  mov     r15b, r9b
0x14000e018  mov     [rbp+47h+var_4C], 5000000h
0x14000e01f  mov     r13d, r8d
0x14000e022  mov     [rbp+47h+var_48], 12h
0x14000e029  lea     ecx, [rax+1]
0x14000e02c  mov     [rbp+47h+var_C0], eax
0x14000e02f  mov     r14, rdx
0x14000e032  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm0
0x14000e036  movups  xmmword ptr [rbp+47h+DestinationString.Length], xmm0
0x14000e03a  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm0
0x14000e03e  movups  xmmword ptr [rbp+47h+ObjectAttributes+1Ch], xmm0
0x14000e042  movups  [rbp+47h+SecurityDescriptor], xmm0
0x14000e046  movups  [rbp+47h+var_68], xmm0
0x14000e04a  test    rdx, rdx
0x14000e04d  jz      loc_14000E147
0x14000e053  test    rsi, rsi
0x14000e056  jz      loc_14000E147
0x14000e05c  mov     edx, ecx; Revision
0x14000e05e  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x14000e062  call    cs:__imp_RtlCreateSecurityDescriptor
0x14000e069  nop     dword ptr [rax+rax+00h]
0x14000e06e  mov     ebx, eax
0x14000e070  test    eax, eax
0x14000e072  js      loc_14000E143
0x14000e078  xor     r8d, r8d; OwnerDefaulted
0x14000e07b  lea     rdx, [rbp+47h+Owner]; Owner
0x14000e07f  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x14000e083  call    cs:__imp_RtlSetOwnerSecurityDescriptor
0x14000e08a  nop     dword ptr [rax+rax+00h]
0x14000e08f  mov     ebx, eax
0x14000e091  test    eax, eax
0x14000e093  js      loc_14000E143
0x14000e099  mov     rdx, r14; SourceString
0x14000e09c  lea     rcx, [rbp+47h+DestinationString]; DestinationString
0x14000e0a0  call    cs:__imp_RtlInitUnicodeString
0x14000e0a7  nop     dword ptr [rax+rax+00h]
0x14000e0ac  lea     rax, [rbp+47h+DestinationString]
0x14000e0b0  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x14000e0b7  mov     [rbp+47h+ObjectAttributes.ObjectName], rax
0x14000e0bb  lea     rcx, [rbp+47h+var_C0]
0x14000e0bf  mov     [rsp+100h+Disposition], rcx; Disposition
0x14000e0c4  lea     rax, [rbp+47h+SecurityDescriptor]
0x14000e0c8  mov     [rbp+47h+ObjectAttributes.SecurityDescriptor], rax
0x14000e0cc  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x14000e0d0  xor     eax, eax
0x14000e0d2  mov     [rbp+47h+ObjectAttributes.RootDirectory], r12
0x14000e0d6  test    r15b, r15b
0x14000e0d9  mov     [rbp+47h+ObjectAttributes.Attributes], 240h
0x14000e0e0  mov     edx, r13d; DesiredAccess
0x14000e0e3  mov     [rbp+47h+ObjectAttributes.SecurityQualityOfService], 0
0x14000e0eb  setnz   al
0x14000e0ee  mov     rcx, rsi; KeyHandle
0x14000e0f1  mov     [rsp+100h+CreateOptions], eax; CreateOptions
0x14000e0f5  xor     r9d, r9d; TitleIndex
0x14000e0f8  mov     [rsp+100h+Class], 0; Class
0x14000e101  call    cs:__imp_ZwCreateKey
0x14000e108  nop     dword ptr [rax+rax+00h]
0x14000e10d  mov     ebx, eax
0x14000e10f  test    eax, eax
0x14000e111  jns     short loc_14000E133
0x14000e113  mov     edx, 1; Level
0x14000e118  lea     r8, aWerkernelhostZ_9; "WERKERNELHOST: ZwCreateKey failed with "...
0x14000e11f  mov     r9d, eax
0x14000e122  lea     ecx, [rdx+4]; ComponentId
0x14000e125  call    cs:__imp_DbgPrintEx
0x14000e12c  nop     dword ptr [rax+rax+00h]
0x14000e131  jmp     short loc_14000E143
0x14000e133  test    rdi, rdi
0x14000e136  jz      short loc_14000E141
0x14000e138  cmp     [rbp+47h+var_C0], 1
0x14000e13c  setz    al
0x14000e13f  mov     [rdi], al
0x14000e141  xor     ebx, ebx
0x14000e143  mov     eax, ebx
0x14000e145  jmp     short loc_14000E166
0x14000e147  mov     edx, ecx; Level
0x14000e149  lea     r8, aWerkernelhostI_0; "WERKERNELHOST: Invalid params\n"
0x14000e150  mov     ecx, 5; ComponentId
0x14000e155  call    cs:__imp_DbgPrintEx
0x14000e15c  nop     dword ptr [rax+rax+00h]
0x14000e161  mov     eax, 0C000000Dh
0x14000e166  mov     rcx, [rbp+47h+var_40]
0x14000e16a  xor     rcx, rsp; StackCookie
0x14000e16d  call    __security_check_cookie
0x14000e172  mov     rbx, [rsp+100h+arg_18]
0x14000e17a  add     rsp, 0D0h
0x14000e181  pop     r15
0x14000e183  pop     r14
0x14000e185  pop     r13
0x14000e187  pop     r12
0x14000e189  pop     rdi
0x14000e18a  pop     rsi
0x14000e18b  pop     rbp
0x14000e18c  retn
```
