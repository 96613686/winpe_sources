# UserCreateCallbackThread

- ea: `0x180001740`
- end: `0x180001952`
- name: `UserCreateCallbackThread`
- size: `530`
- prototype: `NTSTATUS __fastcall(PVOID ThreadContext, PVOID Reserved5, PVOID Reserved6, HANDLE *)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180001580`

## callees

- `0x180001740`

## import_xrefs

- `ntdll!NtOpenProcessToken` at `0x18000179f`
- `ntdll!NtOpenProcessToken` at `0x18000179f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000184a`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18000184a`
- `ntdll!RtlCreateUserThread` at `0x1800018b4`
- `ntdll!RtlCreateUserThread` at `0x1800018b4`
- `ntdll!NtClose` at `0x18000190f`
- `ntdll!NtClose` at `0x180001931`
- `ntdll!NtClose` at `0x18000190f`
- `ntdll!NtClose` at `0x180001931`
- `ntdll!NtQueryInformationToken` at `0x1800017d1`
- `ntdll!NtQueryInformationToken` at `0x18000182b`
- `ntdll!NtQueryInformationToken` at `0x1800017d1`
- `ntdll!NtQueryInformationToken` at `0x18000182b`
- `ntdll!NtSetInformationThread` at `0x1800018df`
- `ntdll!NtSetInformationThread` at `0x1800018df`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000186d`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x18000186d`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800017f4`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800017f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800017e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018eb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800017e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800018eb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800018ff`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800018ff`

## pseudocode

```c
NTSTATUS __fastcall UserCreateCallbackThread(PVOID ThreadContext, PVOID Reserved5, PVOID Reserved6, HANDLE *a4)
{
  NTSTATUS result; // eax
  ULONG v9; // ebx
  HANDLE ProcessHeap; // rax
  PACL *v11; // rdi
  NTSTATUS v12; // ebx
  HANDLE v13; // rax
  ULONG TokenInformationLength; // [rsp+50h] [rbp-29h] BYREF
  int ThreadInformation; // [rsp+54h] [rbp-25h] BYREF
  void *TokenHandle; // [rsp+58h] [rbp-21h] BYREF
  HANDLE ThreadHandle; // [rsp+60h] [rbp-19h] BYREF
  __int64 TokenInformation; // [rsp+68h] [rbp-11h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+70h] [rbp-9h] BYREF
  __int64 v20; // [rsp+90h] [rbp+17h]

  ThreadInformation = 0;
  TokenHandle = 0;
  TokenInformation = 0;
  TokenInformationLength = 0;
  v20 = 0;
  ThreadHandle = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  result = NtOpenProcessToken(ThreadContext, 8u, &TokenHandle);
  if ( result >= 0 )
  {
    TokenInformationLength = 0;
    NtQueryInformationToken(TokenHandle, TokenDefaultDacl, &TokenInformation, 8u, &TokenInformationLength);
    v9 = TokenInformationLength;
    ProcessHeap = GetProcessHeap();
    v11 = (PACL *)HeapAlloc(ProcessHeap, 8u, v9);
    if ( v11 )
    {
      v12 = NtQueryInformationToken(TokenHandle, TokenDefaultDacl, v11, TokenInformationLength, &TokenInformationLength);
      if ( v12 >= 0 )
      {
        v12 = RtlCreateSecurityDescriptor(SecurityDescriptor, 1u);
        if ( v12 >= 0 )
        {
          RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, *v11, 1u);
          v12 = RtlCreateUserThread(
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
          if ( v12 >= 0 )
          {
            ThreadInformation = 2;
            NtSetInformationThread(ThreadHandle, ThreadBasePriority, &ThreadInformation, 4u);
          }
        }
      }
      v13 = GetProcessHeap();
      HeapFree(v13, 0, v11);
    }
    else
    {
      v12 = -1073741801;
    }
    NtClose(TokenHandle);
    if ( v12 < 0 )
    {
      if ( ThreadHandle )
        NtClose(ThreadHandle);
    }
    else
    {
      *a4 = ThreadHandle;
    }
    return v12;
  }
  return result;
}

```

## disassembly

```asm
0x180001740  push    rbp
0x180001742  push    rbx
0x180001743  push    rsi
0x180001744  push    rdi
0x180001745  push    r12
0x180001747  push    r14
0x180001749  push    r15
0x18000174b  lea     rbp, [rsp-27h]
0x180001750  sub     rsp, 0A0h
0x180001757  xor     eax, eax
0x180001759  mov     [rbp+57h+ThreadInformation], 0
0x180001760  xorps   xmm0, xmm0
0x180001763  mov     [rbp+57h+TokenHandle], 0
0x18000176b  mov     r15, r8
0x18000176e  mov     [rbp+57h+TokenInformation], 0
0x180001776  mov     r12, rdx
0x180001779  mov     [rbp+57h+TokenInformationLength], 0
0x180001780  lea     edi, [rax+8]
0x180001783  mov     [rbp+57h+var_40], rax
0x180001787  mov     edx, edi; DesiredAccess
0x180001789  mov     [rbp+57h+ThreadHandle], rax
0x18000178d  lea     r8, [rbp+57h+TokenHandle]; TokenHandle
0x180001791  mov     rsi, r9
0x180001794  mov     r14, rcx
0x180001797  movups  [rbp+57h+SecurityDescriptor], xmm0
0x18000179b  movups  [rbp+57h+var_50], xmm0
0x18000179f  call    cs:__imp_NtOpenProcessToken
0x1800017a6  nop     dword ptr [rax+rax+00h]
0x1800017ab  test    eax, eax
0x1800017ad  js      loc_18000193F
0x1800017b3  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1800017b7  lea     rax, [rbp+57h+TokenInformationLength]
0x1800017bb  mov     r9d, edi; TokenInformationLength
0x1800017be  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x1800017c3  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x1800017c7  mov     [rbp+57h+TokenInformationLength], 0
0x1800017ce  lea     edx, [rdi-2]; TokenInformationClass
0x1800017d1  call    cs:__imp_NtQueryInformationToken
0x1800017d8  nop     dword ptr [rax+rax+00h]
0x1800017dd  mov     ebx, [rbp+57h+TokenInformationLength]
0x1800017e0  call    cs:__imp_GetProcessHeap
0x1800017e7  nop     dword ptr [rax+rax+00h]
0x1800017ec  mov     r8d, ebx; dwBytes
0x1800017ef  mov     edx, edi; dwFlags
0x1800017f1  mov     rcx, rax; hHeap
0x1800017f4  call    cs:__imp_HeapAlloc
0x1800017fb  nop     dword ptr [rax+rax+00h]
0x180001800  mov     rdi, rax
0x180001803  test    rax, rax
0x180001806  jnz     short loc_180001812
0x180001808  mov     ebx, 0C0000017h
0x18000180d  jmp     loc_18000190B
0x180001812  mov     r9d, [rbp+57h+TokenInformationLength]; TokenInformationLength
0x180001816  lea     rax, [rbp+57h+TokenInformationLength]
0x18000181a  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x18000181e  mov     r8, rdi; TokenInformation
0x180001821  mov     edx, 6; TokenInformationClass
0x180001826  mov     [rsp+0D0h+ReturnLength], rax; ReturnLength
0x18000182b  call    cs:__imp_NtQueryInformationToken
0x180001832  nop     dword ptr [rax+rax+00h]
0x180001837  mov     ebx, eax
0x180001839  test    eax, eax
0x18000183b  js      loc_1800018EB
0x180001841  mov     edx, 1; Revision
0x180001846  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x18000184a  call    cs:__imp_RtlCreateSecurityDescriptor
0x180001851  nop     dword ptr [rax+rax+00h]
0x180001856  mov     ebx, eax
0x180001858  test    eax, eax
0x18000185a  js      loc_1800018EB
0x180001860  mov     r8, [rdi]; Dacl
0x180001863  lea     rcx, [rbp+57h+SecurityDescriptor]; SecurityDescriptor
0x180001867  mov     r9b, 1; DaclDefaulted
0x18000186a  mov     dl, r9b; DaclPresent
0x18000186d  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180001874  nop     dword ptr [rax+rax+00h]
0x180001879  mov     [rsp+0D0h+Reserved8], 0; Reserved8
0x180001882  lea     rax, [rbp+57h+ThreadHandle]
0x180001886  mov     [rsp+0D0h+Reserved7], rax; Reserved7
0x18000188b  lea     rdx, [rbp+57h+SecurityDescriptor]; OutThreadHandle
0x18000188f  mov     [rsp+0D0h+Reserved6], r15; Reserved6
0x180001894  xor     r9d, r9d; Reserved2
0x180001897  mov     [rsp+0D0h+Reserved5], r12; Reserved5
0x18000189c  xor     r8d, r8d; Reserved1
0x18000189f  mov     [rsp+0D0h+Reserved4], 0; Reserved4
0x1800018a8  mov     rcx, r14; ThreadContext
0x1800018ab  mov     [rsp+0D0h+ReturnLength], 0; Reserved3
0x1800018b4  call    cs:__imp_RtlCreateUserThread
0x1800018bb  nop     dword ptr [rax+rax+00h]
0x1800018c0  mov     ebx, eax
0x1800018c2  test    eax, eax
0x1800018c4  js      short loc_1800018EB
0x1800018c6  mov     rcx, [rbp+57h+ThreadHandle]; ThreadHandle
0x1800018ca  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x1800018ce  mov     r9d, 4; ThreadInformationLength
0x1800018d4  mov     [rbp+57h+ThreadInformation], 2
0x1800018db  lea     edx, [r9-1]; ThreadInformationClass
0x1800018df  call    cs:__imp_NtSetInformationThread
0x1800018e6  nop     dword ptr [rax+rax+00h]
0x1800018eb  call    cs:__imp_GetProcessHeap
0x1800018f2  nop     dword ptr [rax+rax+00h]
0x1800018f7  mov     r8, rdi; lpMem
0x1800018fa  xor     edx, edx; dwFlags
0x1800018fc  mov     rcx, rax; hHeap
0x1800018ff  call    cs:__imp_HeapFree
0x180001906  nop     dword ptr [rax+rax+00h]
0x18000190b  mov     rcx, [rbp+57h+TokenHandle]; Handle
0x18000190f  call    cs:__imp_NtClose
0x180001916  nop     dword ptr [rax+rax+00h]
0x18000191b  test    ebx, ebx
0x18000191d  js      short loc_180001928
0x18000191f  mov     rax, [rbp+57h+ThreadHandle]
0x180001923  mov     [rsi], rax
0x180001926  jmp     short loc_18000193D
0x180001928  mov     rcx, [rbp+57h+ThreadHandle]; Handle
0x18000192c  test    rcx, rcx
0x18000192f  jz      short loc_18000193D
0x180001931  call    cs:__imp_NtClose
0x180001938  nop     dword ptr [rax+rax+00h]
0x18000193d  mov     eax, ebx
0x18000193f  add     rsp, 0A0h
0x180001946  pop     r15
0x180001948  pop     r14
0x18000194a  pop     r12
0x18000194c  pop     rdi
0x18000194d  pop     rsi
0x18000194e  pop     rbx
0x18000194f  pop     rbp
0x180001950  retn
```
