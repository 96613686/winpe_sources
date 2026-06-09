# LUAIsElevatedToken

- ea: `0x18002f3c8`
- end: `0x18002f47b`
- name: `LUAIsElevatedToken`
- size: `179`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b218`

## callees

- `0x18002f3c8`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002f415`
- `ntdll!NtQueryInformationToken` at `0x18002f455`
- `ntdll!NtQueryInformationToken` at `0x18002f415`
- `ntdll!NtQueryInformationToken` at `0x18002f455`

## pseudocode

```c
NTSTATUS __fastcall LUAIsElevatedToken(HANDLE TokenHandle, _DWORD *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  *a3 = 1;
  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 1;
  *a2 = 0;
  result = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
  {
    if ( TokenInformation == 2
      || TokenInformation == 1
      && (*a3 = 0, result = NtQueryInformationToken(TokenHandle, TokenElevation, &v9, 4u, &ReturnLength), result >= 0)
      && v9 )
    {
      *a2 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18002f3c8  mov     rax, rsp
0x18002f3cb  push    rbx
0x18002f3cc  push    rsi
0x18002f3cd  push    rdi
0x18002f3ce  sub     rsp, 30h
0x18002f3d2  mov     dword ptr [r8], 1
0x18002f3d9  mov     r9d, 4; TokenInformationLength
0x18002f3df  mov     dword ptr [rax+18h], 0
0x18002f3e6  mov     rdi, r8
0x18002f3e9  mov     dword ptr [rax+20h], 0
0x18002f3f0  mov     rbx, rdx
0x18002f3f3  mov     dword ptr [rax+10h], 1
0x18002f3fa  lea     rax, [rax+18h]
0x18002f3fe  mov     dword ptr [rdx], 0
0x18002f404  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18002f409  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002f40d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002f412  mov     rsi, rcx
0x18002f415  call    cs:__imp_NtQueryInformationToken
0x18002f41c  nop     dword ptr [rax+rax+00h]
0x18002f421  test    eax, eax
0x18002f423  js      short loc_18002F472
0x18002f425  cmp     [rsp+48h+TokenInformation], 2
0x18002f42a  jz      short loc_18002F46C
0x18002f42c  cmp     [rsp+48h+TokenInformation], 1
0x18002f431  jnz     short loc_18002F472
0x18002f433  mov     r9d, 4; TokenInformationLength
0x18002f439  mov     dword ptr [rdi], 0
0x18002f43f  lea     rax, [rsp+48h+arg_10]
0x18002f444  mov     rcx, rsi; TokenHandle
0x18002f447  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18002f44c  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002f451  lea     edx, [r9+10h]; TokenInformationClass
0x18002f455  call    cs:__imp_NtQueryInformationToken
0x18002f45c  nop     dword ptr [rax+rax+00h]
0x18002f461  test    eax, eax
0x18002f463  js      short loc_18002F472
0x18002f465  cmp     [rsp+48h+arg_18], 0
0x18002f46a  jz      short loc_18002F472
0x18002f46c  mov     dword ptr [rbx], 1
0x18002f472  add     rsp, 30h
0x18002f476  pop     rdi
0x18002f477  pop     rsi
0x18002f478  pop     rbx
0x18002f479  retn
```
