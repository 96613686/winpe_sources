# OpenCurrentUserKey

- ea: `0x180007184`
- end: `0x180007255`
- name: `OpenCurrentUserKey`
- size: `209`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000acac`

## callees

- `0x180007184`

## import_xrefs

- `ntdll!RtlOpenCurrentUser` at `0x1800071c2`
- `ntdll!RtlOpenCurrentUser` at `0x1800071c2`
- `ntdll!NtOpenKey` at `0x18000721d`
- `ntdll!NtOpenKey` at `0x18000721d`
- `ntdll!RtlInitUnicodeString` at `0x1800071df`
- `ntdll!RtlInitUnicodeString` at `0x1800071df`
- `ntdll!NtClose` at `0x180007234`
- `ntdll!NtClose` at `0x180007234`

## pseudocode

```c
__int64 __fastcall OpenCurrentUserKey(__int64 a1, __int64 a2, void **a3)
{
  NTSTATUS v4; // ebx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+70h] [rbp+10h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  DestinationString = 0;
  v4 = RtlOpenCurrentUser(1u, &KeyHandle);
  if ( v4 >= 0 )
  {
    RtlInitUnicodeString(&DestinationString, L"Software\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon");
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v4 = NtOpenKey(a3, 1u, &ObjectAttributes);
  }
  if ( KeyHandle )
    NtClose(KeyHandle);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180007184  mov     [rsp-8+arg_8], rbx
0x180007189  mov     [rsp-8+arg_10], rdi
0x18000718e  mov     [rsp-8+KeyHandle], rcx
0x180007193  push    rbp
0x180007194  mov     rbp, rsp
0x180007197  sub     rsp, 60h
0x18000719b  xorps   xmm0, xmm0
0x18000719e  mov     [rbp+KeyHandle], 0
0x1800071a6  xor     eax, eax
0x1800071a8  lea     rdx, [rbp+KeyHandle]; KeyHandle
0x1800071ac  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800071b0  mov     rdi, r8
0x1800071b3  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800071b7  lea     ecx, [rax+1]; DesiredAccess
0x1800071ba  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x1800071be  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800071c2  call    cs:__imp_RtlOpenCurrentUser
0x1800071c9  nop     dword ptr [rax+rax+00h]
0x1800071ce  mov     ebx, eax
0x1800071d0  test    eax, eax
0x1800071d2  js      short loc_18000722B
0x1800071d4  lea     rdx, aSoftwareMicros_1; "Software\\Microsoft\\Windows NT\\Curren"...
0x1800071db  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800071df  call    cs:__imp_RtlInitUnicodeString
0x1800071e6  nop     dword ptr [rax+rax+00h]
0x1800071eb  mov     rax, [rbp+KeyHandle]
0x1800071ef  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800071f3  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x1800071f7  xorps   xmm0, xmm0
0x1800071fa  lea     rax, [rbp+DestinationString]
0x1800071fe  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180007205  mov     edx, 1; DesiredAccess
0x18000720a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18000720e  mov     rcx, rdi; KeyHandle
0x180007211  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x180007218  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18000721d  call    cs:__imp_NtOpenKey
0x180007224  nop     dword ptr [rax+rax+00h]
0x180007229  mov     ebx, eax
0x18000722b  mov     rcx, [rbp+KeyHandle]; Handle
0x18000722f  test    rcx, rcx
0x180007232  jz      short loc_180007240
0x180007234  call    cs:__imp_NtClose
0x18000723b  nop     dword ptr [rax+rax+00h]
0x180007240  lea     r11, [rsp+60h+var_s0]
0x180007245  mov     eax, ebx
0x180007247  mov     rbx, [r11+18h]
0x18000724b  mov     rdi, [r11+20h]
0x18000724f  mov     rsp, r11
0x180007252  pop     rbp
0x180007253  retn
```
