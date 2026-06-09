# NetpCreateSecurityObject

- ea: `0x18002e1ec`
- end: `0x18002e283`
- name: `NetpCreateSecurityObject`
- size: `151`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002d308`

## callees

- `0x18002def8`
- `0x18002e1ec`
- `0x18002e4d4`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18002e22b`
- `ntdll!NtOpenProcessToken` at `0x18002e22b`
- `ntdll!NtClose` at `0x18002e26b`
- `ntdll!NtClose` at `0x18002e26b`
- `ntdll!RtlNewSecurityObject` at `0x18002e25e`
- `ntdll!RtlNewSecurityObject` at `0x18002e25e`

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
0x18002e1ec  mov     r11, rsp
0x18002e1ef  mov     [r11+20h], r9
0x18002e1f3  mov     [r11+18h], r8
0x18002e1f7  push    rbx
0x18002e1f8  sub     rsp, 30h
0x18002e1fc  lea     rax, [r11+20h]
0x18002e200  mov     qword ptr [r11+20h], 0
0x18002e208  mov     [r11-18h], rax
0x18002e20c  mov     qword ptr [r11+18h], 0
0x18002e214  call    NetpCreateSecurityDescriptor
0x18002e219  test    eax, eax
0x18002e21b  js      short loc_18002E27D
0x18002e21d  lea     r8, [rsp+38h+TokenHandle]; TokenHandle
0x18002e222  mov     edx, 8; DesiredAccess
0x18002e227  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18002e22b  call    cs:__imp_NtOpenProcessToken
0x18002e231  mov     ebx, eax
0x18002e233  test    eax, eax
0x18002e235  js      short loc_18002E271
0x18002e237  mov     rdx, [rsp+38h+CreatorDescriptor]; CreatorDescriptor
0x18002e23c  lea     rax, ?AtGlobalInformationMapping@@3U_GENERIC_MAPPING@@A; _GENERIC_MAPPING AtGlobalInformationMapping
0x18002e243  mov     [rsp+38h+GenericMapping], rax; GenericMapping
0x18002e248  lea     r8, ?AtGlobalSecurityDescriptor@@3PEAXEA; NewDescriptor
0x18002e24f  mov     rax, [rsp+38h+TokenHandle]
0x18002e254  xor     r9d, r9d; IsDirectoryObject
0x18002e257  xor     ecx, ecx; ParentDescriptor
0x18002e259  mov     [rsp+38h+Token], rax; Token
0x18002e25e  call    cs:__imp_RtlNewSecurityObject
0x18002e264  mov     rcx, [rsp+38h+TokenHandle]; Handle
0x18002e269  mov     ebx, eax
0x18002e26b  call    cs:__imp_NtClose
0x18002e271  mov     rcx, [rsp+38h+CreatorDescriptor]
0x18002e276  call    NetpMemoryFree
0x18002e27b  mov     eax, ebx
0x18002e27d  add     rsp, 30h
0x18002e281  pop     rbx
0x18002e282  retn
```
