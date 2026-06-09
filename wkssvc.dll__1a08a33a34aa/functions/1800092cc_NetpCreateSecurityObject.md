# NetpCreateSecurityObject

- ea: `0x1800092cc`
- end: `0x18000936a`
- name: `NetpCreateSecurityObject`
- size: `158`
- prototype: `__int64 __fastcall(int, int, int, int, PGENERIC_MAPPING, PSECURITY_DESCRIPTOR *NewDescriptor)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800091d4`
- `0x1800316e8`

## callees

- `0x180007cb0`
- `0x1800084a0`
- `0x1800092cc`

## import_xrefs

- `ntdll!NtClose` at `0x18000934b`
- `ntdll!NtClose` at `0x18000934b`
- `ntdll!NtOpenProcessToken` at `0x180009303`
- `ntdll!NtOpenProcessToken` at `0x180009303`
- `ntdll!RtlNewSecurityObject` at `0x180009338`
- `ntdll!RtlNewSecurityObject` at `0x180009338`

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
0x1800092cc  mov     r11, rsp
0x1800092cf  push    rbx
0x1800092d0  sub     rsp, 40h
0x1800092d4  lea     rax, [r11-18h]
0x1800092d8  mov     qword ptr [r11-18h], 0
0x1800092e0  mov     [r11-28h], rax
0x1800092e4  mov     qword ptr [r11-10h], 0
0x1800092ec  call    NetpCreateSecurityDescriptor
0x1800092f1  test    eax, eax
0x1800092f3  js      short loc_180009363
0x1800092f5  lea     r8, [rsp+48h+TokenHandle]; TokenHandle
0x1800092fa  mov     edx, 8; DesiredAccess
0x1800092ff  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x180009303  call    cs:__imp_NtOpenProcessToken
0x18000930a  nop     dword ptr [rax+rax+00h]
0x18000930f  mov     ebx, eax
0x180009311  test    eax, eax
0x180009313  js      short loc_180009357
0x180009315  mov     rax, [rsp+48h+arg_20]
0x18000931a  xor     r9d, r9d; IsDirectoryObject
0x18000931d  mov     r8, [rsp+48h+NewDescriptor]; NewDescriptor
0x180009322  xor     ecx, ecx; ParentDescriptor
0x180009324  mov     rdx, [rsp+48h+CreatorDescriptor]; CreatorDescriptor
0x180009329  mov     [rsp+48h+GenericMapping], rax; GenericMapping
0x18000932e  mov     rax, [rsp+48h+TokenHandle]
0x180009333  mov     [rsp+48h+Token], rax; Token
0x180009338  call    cs:__imp_RtlNewSecurityObject
0x18000933f  nop     dword ptr [rax+rax+00h]
0x180009344  mov     rcx, [rsp+48h+TokenHandle]; Handle
0x180009349  mov     ebx, eax
0x18000934b  call    cs:__imp_NtClose
0x180009352  nop     dword ptr [rax+rax+00h]
0x180009357  mov     rcx, [rsp+48h+CreatorDescriptor]
0x18000935c  call    NetpMemoryFree
0x180009361  mov     eax, ebx
0x180009363  add     rsp, 40h
0x180009367  pop     rbx
0x180009368  retn
```
