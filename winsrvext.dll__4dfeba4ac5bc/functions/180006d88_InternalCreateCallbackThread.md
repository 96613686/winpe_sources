# InternalCreateCallbackThread

- ea: `0x180006d88`
- end: `0x180006f77`
- name: `InternalCreateCallbackThread`
- size: `495`
- prototype: `NTSTATUS __fastcall(PVOID ThreadContext, PVOID Reserved5, PVOID Reserved6, HANDLE *)`
- caller_count: `2`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180005474`
- `0x18000592c`

## callees

- `0x180006d88`

## import_xrefs

- `KERNELBASE!LocalAlloc` at `0x180006e2d`
- `KERNELBASE!LocalAlloc` at `0x180006e2d`
- `ntdll!NtOpenProcessToken` at `0x180006de7`
- `ntdll!NtOpenProcessToken` at `0x180006de7`
- `ntdll!NtQueryInformationToken` at `0x180006e1c`
- `ntdll!NtQueryInformationToken` at `0x180006e61`
- `ntdll!NtQueryInformationToken` at `0x180006e1c`
- `ntdll!NtQueryInformationToken` at `0x180006e61`
- `ntdll!NtSetInformationThread` at `0x180006f15`
- `ntdll!NtSetInformationThread` at `0x180006f15`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006ea3`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180006ea3`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180006e80`
- `ntdll!RtlCreateSecurityDescriptor` at `0x180006e80`
- `ntdll!RtlCreateUserThread` at `0x180006eea`
- `ntdll!RtlCreateUserThread` at `0x180006eea`
- `ntdll!NtClose` at `0x180006f34`
- `ntdll!NtClose` at `0x180006f56`
- `ntdll!NtClose` at `0x180006f34`
- `ntdll!NtClose` at `0x180006f56`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f24`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180006f24`

## pseudocode

```c
NTSTATUS __fastcall InternalCreateCallbackThread(PVOID ThreadContext, PVOID Reserved5, PVOID Reserved6, HANDLE *a4)
{
  NTSTATUS result; // eax
  PACL *v9; // rdi
  NTSTATUS v10; // ebx
  ULONG TokenInformationLength; // [rsp+50h] [rbp-29h] BYREF
  int ThreadInformation; // [rsp+54h] [rbp-25h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-21h] BYREF
  HANDLE ThreadHandle; // [rsp+60h] [rbp-19h] BYREF
  __int64 TokenInformation; // [rsp+68h] [rbp-11h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v17; // [rsp+90h] [rbp+17h]

  ThreadInformation = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v17 = 0;
  ThreadHandle = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  result = NtOpenProcessToken(ThreadContext, 8u, &TokenHandle);
  if ( result >= 0 )
  {
    TokenInformationLength = 0;
    NtQueryInformationToken(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u, &TokenInformationLength);
    v9 = (PACL *)LocalAlloc(0, TokenInformationLength);
    if ( v9 )
    {
      v10 = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, v9, TokenInformationLength, &TokenInformationLength);
      if ( v10 >= 0 )
      {
        v10 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( v10 >= 0 )
        {
          RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, *v9, 1u);
          v10 = RtlCreateUserThread(
                  ThreadContext,
                  (HANDLE *)SecurityDescriptor,
                  0,
                  0,
                  0,
                  0,
                  Reserved5,
                  Reserved6,
                  &ThreadHandle,
                  0);
          if ( v10 >= 0 )
          {
            ThreadInformation = 2;
            NtSetInformationThread(ThreadHandle, ThreadBasePriority, &ThreadInformation, 4u);
          }
        }
      }
      LocalFree(v9);
    }
    else
    {
      v10 = -1073741801;
    }
    NtClose(TokenHandle);
    if ( v10 < 0 )
    {
      if ( ThreadHandle )
        NtClose(ThreadHandle);
    }
    else
    {
      *a4 = ThreadHandle;
    }
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x180006d88  push    rbp
0x180006d8a  push    rbx
0x180006d8b  push    rsi
0x180006d8c  push    rdi
0x180006d8d  push    r12
0x180006d8f  push    r14
0x180006d91  push    r15
0x180006d93  lea     rbp, [rsp-27h]
0x180006d98  sub     rsp, 0A0h
0x180006d9f  xor     eax, eax
0x180006da1  mov     [rbp+57h+ThreadInformation], 0
0x180006da8  xorps   xmm0, xmm0
0x180006dab  mov     [rbp+57h+TokenHandle], 0
0x180006db3  mov     r15, r8
0x180006db6  mov     [rbp+57h+TokenInformation], 0
0x180006dbe  mov     r12, rdx
0x180006dc1  mov     [rbp+57h+TokenInformationLength], 0
0x180006dc8  lea     ebx, [rax+8]
0x180006dcb  mov     [rbp+57h+var_40], rax
0x180006dcf  mov     edx, ebx; DesiredAccess
0x180006dd1  mov     [rbp+57h+ThreadHandle], rax
0x180006dd5  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180006dd9  mov     rsi, r9
0x180006ddc  mov     r14, rcx
0x180006ddf  movups  [rbp+57h+SecurityDescriptor], xmm0
0x180006de3  movups  [rbp+57h+var_50], xmm0
0x180006de7  call    cs:__imp_NtOpenProcessToken
0x180006dee  nop     dword ptr [rax+rax+00h]
0x180006df3  test    eax, eax
0x180006df5  js      loc_180006F64
0x180006dfb  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180006dff  lea     rax, [rbp+57h+TokenInformationLength]
0x180006e03  mov     r9d, ebx; TokenInformationLength
0x180006e06  mov     [rbp+57h+TokenInformationLength], 0
0x180006e0d  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180006e11  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180006e16  lea     ebx, [r9-2]
0x180006e1a  mov     edx, ebx; TokenInformationClass
0x180006e1c  call    cs:__imp_NtQueryInformationToken
0x180006e23  nop     dword ptr [rax+rax+00h]
0x180006e28  mov     edx, [rbp+57h+TokenInformationLength]; uBytes
0x180006e2b  xor     ecx, ecx; uFlags
0x180006e2d  call    cs:__imp_LocalAlloc
0x180006e34  nop     dword ptr [rax+rax+00h]
0x180006e39  mov     rdi, rax
0x180006e3c  test    rax, rax
0x180006e3f  jnz     short loc_180006E4B
0x180006e41  mov     ebx, 0C0000017h
0x180006e46  jmp     loc_180006F30
0x180006e4b  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180006e4f  lea     rax, [rbp+57h+TokenInformationLength]
0x180006e53  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180006e57  mov     r8, rdi; TokenInformation
0x180006e5a  mov     edx, ebx; TokenInformationClass
0x180006e5c  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x180006e61  call    cs:__imp_NtQueryInformationToken
0x180006e68  nop     dword ptr [rax+rax+00h]
0x180006e6d  mov     ebx, eax
0x180006e6f  test    eax, eax
0x180006e71  js      loc_180006F21
0x180006e77  mov     edx, 1; Revision
0x180006e7c  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180006e80  call    cs:__imp_RtlCreateSecurityDescriptor
0x180006e87  nop     dword ptr [rax+rax+00h]
0x180006e8c  mov     ebx, eax
0x180006e8e  test    eax, eax
0x180006e90  js      loc_180006F21
0x180006e96  mov     r8, [rdi]; Dacl
0x180006e99  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180006e9d  mov     r9b, 1; DaclDefaulted
0x180006ea0  mov     dl, r9b; DaclPresent
0x180006ea3  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180006eaa  nop     dword ptr [rax+rax+00h]
0x180006eaf  mov     [rsp+0D0h+Reserved8], 0; Reserved8
0x180006eb8  lea     rax, [rbp+57h+ThreadHandle]
0x180006ebc  mov     [rsp+0D0h+Reserved7], rax; Reserved7
0x180006ec1  lea     rdx, [rbp+57h+SecurityDescriptor]; OutThreadHandle
0x180006ec5  mov     [rsp+0D0h+Reserved6], r15; Reserved6
0x180006eca  xor     r9d, r9d; Reserved2
0x180006ecd  mov     [rsp+0D0h+Reserved5], r12; Reserved5
0x180006ed2  xor     r8d, r8d; Reserved1
0x180006ed5  mov     [rsp+0D0h+Reserved4], 0; Reserved4
0x180006ede  mov     rcx, r14; ThreadContext
0x180006ee1  mov     [rsp+0D0h+ReturnLength], 0; Reserved3
0x180006eea  call    cs:__imp_RtlCreateUserThread
0x180006ef1  nop     dword ptr [rax+rax+00h]
0x180006ef6  mov     ebx, eax
0x180006ef8  test    eax, eax
0x180006efa  js      short loc_180006F21
0x180006efc  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x180006f00  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x180006f04  mov     r9d, 4; ThreadInformationLength
0x180006f0a  mov     [rbp+57h+ThreadInformation], 2
0x180006f11  lea     edx, [r9-1]; ThreadInformationClass
0x180006f15  call    cs:__imp_NtSetInformationThread
0x180006f1c  nop     dword ptr [rax+rax+00h]
0x180006f21  mov     rcx, rdi; hMem
0x180006f24  call    cs:__imp_LocalFree
0x180006f2b  nop     dword ptr [rax+rax+00h]
0x180006f30  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x180006f34  call    cs:__imp_NtClose
0x180006f3b  nop     dword ptr [rax+rax+00h]
0x180006f40  test    ebx, ebx
0x180006f42  js      short loc_180006F4D
0x180006f44  mov     rax, [rbp+57h+ThreadHandle]
0x180006f48  mov     [rsi], rax
0x180006f4b  jmp     short loc_180006F62
0x180006f4d  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x180006f51  test    rcx, rcx
0x180006f54  jz      short loc_180006F62
0x180006f56  call    cs:__imp_NtClose
0x180006f5d  nop     dword ptr [rax+rax+00h]
0x180006f62  mov     eax, ebx
0x180006f64  add     rsp, 0A0h
0x180006f6b  pop     r15
0x180006f6d  pop     r14
0x180006f6f  pop     r12
0x180006f71  pop     rdi
0x180006f72  pop     rsi
0x180006f73  pop     rbx
0x180006f74  pop     rbp
0x180006f75  retn
```
