# NetpCreateSecurityObject

- ea: `0x1800302e4`
- end: `0x18003038e`
- name: `NetpCreateSecurityObject`
- size: `170`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002f27c`

## callees

- `0x18002ffa0`
- `0x1800302e4`
- `0x18003061c`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x180030323`
- `ntdll!NtOpenProcessToken` at `0x180030323`
- `ntdll!NtClose` at `0x18003036f`
- `ntdll!NtClose` at `0x18003036f`
- `ntdll!RtlNewSecurityObject` at `0x18003035c`
- `ntdll!RtlNewSecurityObject` at `0x18003035c`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityObject(__int64 a1, unsigned int a2, __int64 a3, __int64 a4)
{
  __int64 result; // rax
  NTSTATUS v5; // ebx
  void *TokenHandle; // [rsp+50h] [rbp+18h] BYREF
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+58h] [rbp+20h] BYREF

  CreatorDescriptor = 0;
  TokenHandle = 0;
  result = NetpCreateSecurityDescriptor(a1, a2, a3, a4, (struct _ACL **)&CreatorDescriptor);
  if ( (int)result >= 0 )
  {
    v5 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v5 >= 0 )
    {
      v5 = RtlNewSecurityObject(
             0,
             CreatorDescriptor,
             &AtGlobalSecurityDescriptor,
             0,
             TokenHandle,
             &AtGlobalInformationMapping);
      NtClose(TokenHandle);
    }
    NetpMemoryFree(CreatorDescriptor);
    return (unsigned int)v5;
  }
  return result;
}

```

## disassembly

```asm
0x1800302e4  mov     r11, rsp
0x1800302e7  mov     [r11+20h], r9
0x1800302eb  mov     [r11+18h], r8
0x1800302ef  push    rbx
0x1800302f0  sub     rsp, 30h
0x1800302f4  lea     rax, [r11+20h]
0x1800302f8  mov     qword ptr [r11+20h], 0
0x180030300  mov     [r11-18h], rax
0x180030304  mov     qword ptr [r11+18h], 0
0x18003030c  call    NetpCreateSecurityDescriptor
0x180030311  test    eax, eax
0x180030313  js      short loc_180030387
0x180030315  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18003031a  mov     edx, 8; DesiredAccess
0x18003031f  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180030323  call    cs:__imp_NtOpenProcessToken
0x18003032a  nop     dword ptr [rax+rax+00h]
0x18003032f  mov     ebx, eax
0x180030331  test    eax, eax
0x180030333  js      short loc_18003037B
0x180030335  mov     rdx, [rsp+38h+CreatorDescriptor]; CreatorDescriptor
0x18003033a  lea     rax, ?AtGlobalInformationMapping@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING AtGlobalInformationMapping
0x180030341  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x180030346  lea     r8, ?AtGlobalSecurityDescriptor@@3PEAXEA; NewDescriptor
0x18003034d  mov     rax, [rsp+38h+TokenHandle]
0x180030352  xor     r9d, r9d; IsDirectoryObject
0x180030355  xor     ecx, ecx; ParentDescriptor
0x180030357  mov     [rsp+38h+Token], rax; Token
0x18003035c  call    cs:__imp_RtlNewSecurityObject
0x180030363  nop     dword ptr [rax+rax+00h]
0x180030368  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18003036d  mov     ebx, eax
0x18003036f  call    cs:__imp_NtClose
0x180030376  nop     dword ptr [rax+rax+00h]
0x18003037b  mov     rcx, [rsp+38h+CreatorDescriptor]
0x180030380  call    NetpMemoryFree
0x180030385  mov     eax, ebx
0x180030387  add     rsp, 30h
0x18003038b  pop     rbx
0x18003038c  retn
```
