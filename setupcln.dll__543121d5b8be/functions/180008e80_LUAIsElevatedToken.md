# LUAIsElevatedToken

- ea: `0x180008e80`
- end: `0x180008f26`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800055e0`

## callees

- `0x180008e80`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180008ecd`
- `ntdll!NtQueryInformationToken` at `0x180008f07`
- `ntdll!NtQueryInformationToken` at `0x180008ecd`
- `ntdll!NtQueryInformationToken` at `0x180008f07`

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
0x180008e80  mov     rax, rsp
0x180008e83  push    rbx
0x180008e84  push    rsi
0x180008e85  push    rdi
0x180008e86  sub     rsp, 30h
0x180008e8a  mov     r9d, 4; TokenInformationLength
0x180008e90  mov     dword ptr [rax+18h], 0
0x180008e97  mov     dword ptr [rax+20h], 0
0x180008e9e  mov     rdi, r8
0x180008ea1  mov     dword ptr [rax+10h], 1
0x180008ea8  lea     rax, [rax+18h]
0x180008eac  mov     rbx, rdx
0x180008eaf  mov     dword ptr [r8], 1
0x180008eb6  mov     dword ptr [rdx], 0
0x180008ebc  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180008ec1  lea     edx, [r9+0Eh]; TokenInformationClass
0x180008ec5  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008eca  mov     rsi, rcx
0x180008ecd  call    cs:__imp_NtQueryInformationToken
0x180008ed3  test    eax, eax
0x180008ed5  js      short loc_180008F1E
0x180008ed7  cmp     [rsp+48h+TokenInformation], 2
0x180008edc  jz      short loc_180008F18
0x180008ede  cmp     [rsp+48h+TokenInformation], 1
0x180008ee3  jnz     short loc_180008F1E
0x180008ee5  mov     r9d, 4; TokenInformationLength
0x180008eeb  mov     dword ptr [rdi], 0
0x180008ef1  lea     rax, [rsp+48h+arg_10]
0x180008ef6  mov     rcx, rsi; TokenHandle
0x180008ef9  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180008efe  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180008f03  lea     edx, [r9+10h]; TokenInformationClass
0x180008f07  call    cs:__imp_NtQueryInformationToken
0x180008f0d  test    eax, eax
0x180008f0f  js      short loc_180008F1E
0x180008f11  cmp     [rsp+48h+arg_18], 0
0x180008f16  jz      short loc_180008F1E
0x180008f18  mov     dword ptr [rbx], 1
0x180008f1e  add     rsp, 30h
0x180008f22  pop     rdi
0x180008f23  pop     rsi
0x180008f24  pop     rbx
0x180008f25  retn
```
