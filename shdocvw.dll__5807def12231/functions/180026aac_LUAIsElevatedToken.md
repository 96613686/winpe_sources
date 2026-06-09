# LUAIsElevatedToken

- ea: `0x180026aac`
- end: `0x180026b52`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180026b58`
- `0x180026c68`

## callees

- `0x180026aac`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x180026af9`
- `ntdll!NtQueryInformationToken` at `0x180026b33`
- `ntdll!NtQueryInformationToken` at `0x180026af9`
- `ntdll!NtQueryInformationToken` at `0x180026b33`

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
0x180026aac  mov     rax, rsp
0x180026aaf  push    rbx
0x180026ab0  push    rsi
0x180026ab1  push    rdi
0x180026ab2  sub     rsp, 30h
0x180026ab6  mov     r9d, 4; TokenInformationLength
0x180026abc  mov     dword ptr [rax+18h], 0
0x180026ac3  mov     dword ptr [rax+20h], 0
0x180026aca  mov     rdi, r8
0x180026acd  mov     dword ptr [rax+10h], 1
0x180026ad4  lea     rax, [rax+18h]
0x180026ad8  mov     rbx, rdx
0x180026adb  mov     dword ptr [r8], 1
0x180026ae2  mov     dword ptr [rdx], 0
0x180026ae8  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x180026aed  lea     edx, [r9+0Eh]; TokenInformationClass
0x180026af1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180026af6  mov     rsi, rcx
0x180026af9  call    cs:__imp_NtQueryInformationToken
0x180026aff  test    eax, eax
0x180026b01  js      short loc_180026B4A
0x180026b03  cmp     [rsp+48h+TokenInformation], 2
0x180026b08  jz      short loc_180026B44
0x180026b0a  cmp     [rsp+48h+TokenInformation], 1
0x180026b0f  jnz     short loc_180026B4A
0x180026b11  mov     r9d, 4; TokenInformationLength
0x180026b17  mov     dword ptr [rdi], 0
0x180026b1d  lea     rax, [rsp+48h+arg_10]
0x180026b22  mov     rcx, rsi; TokenHandle
0x180026b25  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x180026b2a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x180026b2f  lea     edx, [r9+10h]; TokenInformationClass
0x180026b33  call    cs:__imp_NtQueryInformationToken
0x180026b39  test    eax, eax
0x180026b3b  js      short loc_180026B4A
0x180026b3d  cmp     [rsp+48h+arg_18], 0
0x180026b42  jz      short loc_180026B4A
0x180026b44  mov     dword ptr [rbx], 1
0x180026b4a  add     rsp, 30h
0x180026b4e  pop     rdi
0x180026b4f  pop     rsi
0x180026b50  pop     rbx
0x180026b51  retn
```
