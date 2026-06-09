# NetpCreateSecurityObject

- ea: `0x18001d9ac`
- end: `0x18001da37`
- name: `NetpCreateSecurityObject`
- size: `139`
- prototype: `__int64 __fastcall(__int64, unsigned int, void *, void *, PGENERIC_MAPPING GenericMapping, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000aa8c`

## callees

- `0x180013510`
- `0x18001d9ac`
- `0x1800427f0`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18001d9e3`
- `ntdll!NtOpenProcessToken` at `0x18001d9e3`
- `ntdll!RtlNewSecurityObject` at `0x18001da12`
- `ntdll!RtlNewSecurityObject` at `0x18001da12`
- `ntdll!NtClose` at `0x18001da1f`
- `ntdll!NtClose` at `0x18001da1f`

## pseudocode

```c
__int64 __fastcall NetpCreateSecurityObject(
        __int64 a1,
        unsigned int a2,
        void *a3,
        void *a4,
        PGENERIC_MAPPING GenericMapping,
        PSECURITY_DESCRIPTOR *NewDescriptor)
{
  __int64 result; // rax
  NTSTATUS v7; // ebx
  PSECURITY_DESCRIPTOR CreatorDescriptor; // [rsp+30h] [rbp-18h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-10h] BYREF

  CreatorDescriptor = 0;
  TokenHandle = 0;
  result = NetpCreateSecurityDescriptor(a1, a2, a3, a4, (struct _ACL **)&CreatorDescriptor);
  if ( (int)result >= 0 )
  {
    v7 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
    if ( v7 >= 0 )
    {
      v7 = RtlNewSecurityObject(0, CreatorDescriptor, NewDescriptor, 0, TokenHandle, GenericMapping);
      NtClose(TokenHandle);
    }
    NetpMemoryFree(CreatorDescriptor);
    return (unsigned int)v7;
  }
  return result;
}

```

## disassembly

```asm
0x18001d9ac  mov     r11, rsp
0x18001d9af  push    rbx
0x18001d9b0  sub     rsp, 40h
0x18001d9b4  lea     rax, [r11-18h]
0x18001d9b8  mov     qword ptr [r11-18h], 0
0x18001d9c0  mov     [r11-28h], rax
0x18001d9c4  mov     qword ptr [r11-10h], 0
0x18001d9cc  call    NetpCreateSecurityDescriptor
0x18001d9d1  test    eax, eax
0x18001d9d3  js      short loc_18001DA31
0x18001d9d5  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x18001d9da  mov     edx, 8; DesiredAccess
0x18001d9df  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001d9e3  call    cs:__imp_NtOpenProcessToken
0x18001d9e9  mov     ebx, eax
0x18001d9eb  test    eax, eax
0x18001d9ed  js      short loc_18001DA25
0x18001d9ef  mov     rax, [rsp+48h+arg_20]
0x18001d9f4  xor     r9d, r9d; IsDirectoryObject
0x18001d9f7  mov     r8, [rsp+48h+NewDescriptor]; NewDescriptor
0x18001d9fc  xor     ecx, ecx; ParentDescriptor
0x18001d9fe  mov     rdx, [rsp+48h+CreatorDescriptor]; CreatorDescriptor
0x18001da03  mov     [rsp+48h+GenericMapping], rax; GenericMapping
0x18001da08  mov     rax, [rsp+48h+TokenHandle]
0x18001da0d  mov     [rsp+48h+Token], rax; Token
0x18001da12  call    cs:__imp_RtlNewSecurityObject
0x18001da18  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x18001da1d  mov     ebx, eax
0x18001da1f  call    cs:__imp_NtClose
0x18001da25  mov     rcx, [rsp+48h+CreatorDescriptor]
0x18001da2a  call    NetpMemoryFree
0x18001da2f  mov     eax, ebx
0x18001da31  add     rsp, 40h
0x18001da35  pop     rbx
0x18001da36  retn
```
