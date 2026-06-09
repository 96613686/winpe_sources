# LUAIsElevatedToken

- ea: `0x18002d438`
- end: `0x18002d4de`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000ac28`

## callees

- `0x18002d438`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002d485`
- `ntdll!NtQueryInformationToken` at `0x18002d4bf`
- `ntdll!NtQueryInformationToken` at `0x18002d485`
- `ntdll!NtQueryInformationToken` at `0x18002d4bf`

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
0x18002d438  mov     rax, rsp
0x18002d43b  push    rbx
0x18002d43c  push    rsi
0x18002d43d  push    rdi
0x18002d43e  sub     rsp, 30h
0x18002d442  mov     dword ptr [r8], 1
0x18002d449  mov     r9d, 4; TokenInformationLength
0x18002d44f  mov     dword ptr [rax+18h], 0
0x18002d456  mov     rdi, r8
0x18002d459  mov     dword ptr [rax+20h], 0
0x18002d460  mov     rbx, rdx
0x18002d463  mov     dword ptr [rax+10h], 1
0x18002d46a  lea     rax, [rax+18h]
0x18002d46e  mov     dword ptr [rdx], 0
0x18002d474  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18002d479  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002d47d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002d482  mov     rsi, rcx
0x18002d485  call    cs:__imp_NtQueryInformationToken
0x18002d48b  test    eax, eax
0x18002d48d  js      short loc_18002D4D6
0x18002d48f  cmp     [rsp+48h+TokenInformation], 2
0x18002d494  jz      short loc_18002D4D0
0x18002d496  cmp     [rsp+48h+TokenInformation], 1
0x18002d49b  jnz     short loc_18002D4D6
0x18002d49d  mov     r9d, 4; TokenInformationLength
0x18002d4a3  mov     dword ptr [rdi], 0
0x18002d4a9  lea     rax, [rsp+48h+arg_10]
0x18002d4ae  mov     rcx, rsi; TokenHandle
0x18002d4b1  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18002d4b6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002d4bb  lea     edx, [r9+10h]; TokenInformationClass
0x18002d4bf  call    cs:__imp_NtQueryInformationToken
0x18002d4c5  test    eax, eax
0x18002d4c7  js      short loc_18002D4D6
0x18002d4c9  cmp     [rsp+48h+arg_18], 0
0x18002d4ce  jz      short loc_18002D4D6
0x18002d4d0  mov     dword ptr [rbx], 1
0x18002d4d6  add     rsp, 30h
0x18002d4da  pop     rdi
0x18002d4db  pop     rsi
0x18002d4dc  pop     rbx
0x18002d4dd  retn
```
