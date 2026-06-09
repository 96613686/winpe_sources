# LUAGetUserType

- ea: `0x18001a088`
- end: `0x18001a187`
- name: `LUAGetUserType`
- size: `255`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180009730`

## callees

- `0x18001a088`
- `0x18001a190`

## import_xrefs

- `ntdll!NtOpenThreadToken` at `0x18001a0c6`
- `ntdll!NtOpenThreadToken` at `0x18001a0c6`
- `ntdll!NtClose` at `0x18001a172`
- `ntdll!NtClose` at `0x18001a172`
- `ntdll!NtOpenProcessToken` at `0x18001a0df`
- `ntdll!NtOpenProcessToken` at `0x18001a0df`
- `ntdll!NtQueryInformationToken` at `0x18001a149`
- `ntdll!NtQueryInformationToken` at `0x18001a149`

## pseudocode

```c
__int64 __fastcall LUAGetUserType(__int64 a1, int *a2)
{
  NTSTATUS v3; // ebx
  void *v4; // rsi
  int v5; // ecx
  int TokenInformation; // [rsp+50h] [rbp+20h] BYREF
  int TokenInformation_4; // [rsp+54h] [rbp+24h]
  ULONG ReturnLength; // [rsp+60h] [rbp+30h] BYREF
  void *TokenHandle; // [rsp+68h] [rbp+38h] BYREF

  TokenInformation_4 = HIDWORD(a1);
  TokenHandle = 0;
  TokenInformation = 0;
  ReturnLength = 0;
  v3 = NtOpenThreadToken((HANDLE)0xFFFFFFFFFFFFFFFELL, 8u, 0, &TokenHandle);
  if ( v3 == -1073741700 )
    v3 = NtOpenProcessToken((HANDLE)0xFFFFFFFFFFFFFFFFLL, 8u, &TokenHandle);
  if ( v3 >= 0 )
  {
    v4 = TokenHandle;
    v3 = LUAIsElevatedToken(TokenHandle);
    if ( v3 >= 0 )
    {
      *a2 = TokenInformation ? 0 : 2 - (ReturnLength != 0);
      TokenInformation = 0;
      ReturnLength = 4;
      v3 = NtQueryInformationToken(TokenHandle, TokenUIAccess, &TokenInformation, 4u, &ReturnLength);
      if ( v3 >= 0 )
      {
        if ( TokenInformation )
        {
          v5 = *a2;
          if ( (unsigned int)(*a2 - 16) > 2 )
            v5 += 16;
          *a2 = v5;
        }
      }
    }
    if ( v4 )
      NtClose(v4);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x18001a088  mov     [rsp-18h+arg_8], rbx
0x18001a08d  mov     [rsp-18h+TokenInformation], rcx
0x18001a092  push    rbp
0x18001a093  push    rsi
0x18001a094  push    rdi
0x18001a095  mov     rbp, rsp
0x18001a098  sub     rsp, 30h
0x18001a09c  xor     r8d, r8d; OpenAsSelf
0x18001a09f  mov     [rbp+TokenHandle], 0
0x18001a0a7  mov     rdi, rdx
0x18001a0aa  mov     dword ptr [rbp+TokenInformation], 0
0x18001a0b1  lea     r9, [rbp+TokenHandle]; TokenHandle
0x18001a0b5  mov     [rbp+arg_10], 0
0x18001a0bc  lea     esi, [r8+8]
0x18001a0c0  mov     edx, esi; DesiredAccess
0x18001a0c2  lea     rcx, [r8-2]; ThreadHandle
0x18001a0c6  call    cs:__imp_NtOpenThreadToken
0x18001a0cc  mov     ebx, eax
0x18001a0ce  cmp     eax, 0C000007Ch
0x18001a0d3  jnz     short loc_18001A0E7
0x18001a0d5  lea     r8, [rbp+TokenHandle]; TokenHandle
0x18001a0d9  mov     edx, esi; DesiredAccess
0x18001a0db  or      rcx, 0FFFFFFFFFFFFFFFFh; ProcessHandle
0x18001a0df  call    cs:__imp_NtOpenProcessToken
0x18001a0e5  mov     ebx, eax
0x18001a0e7  test    ebx, ebx
0x18001a0e9  js      loc_18001A178
0x18001a0ef  mov     rsi, [rbp+TokenHandle]
0x18001a0f3  lea     r8, [rbp+arg_10]
0x18001a0f7  mov     rcx, rsi; TokenHandle
0x18001a0fa  lea     rdx, [rbp+TokenInformation]
0x18001a0fe  call    LUAIsElevatedToken
0x18001a103  mov     ebx, eax
0x18001a105  test    eax, eax
0x18001a107  js      short loc_18001A16A
0x18001a109  cmp     dword ptr [rbp+TokenInformation], 0
0x18001a10d  jz      short loc_18001A117
0x18001a10f  mov     dword ptr [rdi], 0
0x18001a115  jmp     short loc_18001A123
0x18001a117  mov     eax, [rbp+arg_10]
0x18001a11a  neg     eax
0x18001a11c  sbb     ecx, ecx
0x18001a11e  add     ecx, 2
0x18001a121  mov     [rdi], ecx
0x18001a123  mov     rcx, [rbp+TokenHandle]; TokenHandle
0x18001a127  lea     rax, [rbp+arg_10]
0x18001a12b  mov     r9d, 4; TokenInformationLength
0x18001a131  mov     dword ptr [rbp+TokenInformation], 0
0x18001a138  lea     r8, [rbp+TokenInformation]; TokenInformation
0x18001a13c  mov     [rbp+arg_10], r9d
0x18001a140  mov     [rsp+30h+ReturnLength], rax; ReturnLength
0x18001a145  lea     edx, [r9+16h]; TokenInformationClass
0x18001a149  call    cs:__imp_NtQueryInformationToken
0x18001a14f  mov     ebx, eax
0x18001a151  test    eax, eax
0x18001a153  js      short loc_18001A16A
0x18001a155  cmp     dword ptr [rbp+TokenInformation], 0
0x18001a159  jz      short loc_18001A16A
0x18001a15b  mov     ecx, [rdi]
0x18001a15d  lea     eax, [rcx-10h]
0x18001a160  cmp     eax, 2
0x18001a163  jbe     short loc_18001A168
0x18001a165  add     ecx, 10h
0x18001a168  mov     [rdi], ecx
0x18001a16a  test    rsi, rsi
0x18001a16d  jz      short loc_18001A178
0x18001a16f  mov     rcx, rsi; Handle
0x18001a172  call    cs:__imp_NtClose
0x18001a178  mov     eax, ebx
0x18001a17a  mov     rbx, [rsp+30h+arg_8]
0x18001a17f  add     rsp, 30h
0x18001a183  pop     rdi
0x18001a184  pop     rsi
0x18001a185  pop     rbp
0x18001a186  retn
```
