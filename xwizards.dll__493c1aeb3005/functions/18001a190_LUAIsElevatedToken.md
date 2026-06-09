# LUAIsElevatedToken

- ea: `0x18001a190`
- end: `0x18001a236`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18001a088`

## callees

- `0x18001a190`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18001a1dd`
- `ntdll!NtQueryInformationToken` at `0x18001a217`
- `ntdll!NtQueryInformationToken` at `0x18001a1dd`
- `ntdll!NtQueryInformationToken` at `0x18001a217`

## pseudocode

```c
NTSTATUS __fastcall LUAIsElevatedToken(HANDLE TokenHandle, _DWORD *a2, _DWORD *a3)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v9; // [rsp+68h] [rbp+20h] BYREF

  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 1;
  *a3 = 1;
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
0x18001a190  mov     rax, rsp
0x18001a193  push    rbx
0x18001a194  push    rsi
0x18001a195  push    rdi
0x18001a196  sub     rsp, 30h
0x18001a19a  mov     r9d, 4; TokenInformationLength
0x18001a1a0  mov     dword ptr [rax+18h], 0
0x18001a1a7  mov     dword ptr [rax+20h], 0
0x18001a1ae  mov     rdi, r8
0x18001a1b1  mov     dword ptr [rax+10h], 1
0x18001a1b8  lea     rax, [rax+18h]
0x18001a1bc  mov     rbx, rdx
0x18001a1bf  mov     dword ptr [r8], 1
0x18001a1c6  mov     dword ptr [rdx], 0
0x18001a1cc  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18001a1d1  lea     edx, [r9+0Eh]; TokenInformationClass
0x18001a1d5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001a1da  mov     rsi, rcx
0x18001a1dd  call    cs:__imp_NtQueryInformationToken
0x18001a1e3  test    eax, eax
0x18001a1e5  js      short loc_18001A22E
0x18001a1e7  cmp     [rsp+48h+TokenInformation], 2
0x18001a1ec  jz      short loc_18001A228
0x18001a1ee  cmp     [rsp+48h+TokenInformation], 1
0x18001a1f3  jnz     short loc_18001A22E
0x18001a1f5  mov     r9d, 4; TokenInformationLength
0x18001a1fb  mov     dword ptr [rdi], 0
0x18001a201  lea     rax, [rsp+48h+arg_10]
0x18001a206  mov     rcx, rsi; TokenHandle
0x18001a209  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18001a20e  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001a213  lea     edx, [r9+10h]; TokenInformationClass
0x18001a217  call    cs:__imp_NtQueryInformationToken
0x18001a21d  test    eax, eax
0x18001a21f  js      short loc_18001A22E
0x18001a221  cmp     [rsp+48h+arg_18], 0
0x18001a226  jz      short loc_18001A22E
0x18001a228  mov     dword ptr [rbx], 1
0x18001a22e  add     rsp, 30h
0x18001a232  pop     rdi
0x18001a233  pop     rsi
0x18001a234  pop     rbx
0x18001a235  retn
```
