# _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)

- ea: `0x18000e648`
- end: `0x18000e6ee`
- name: `?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, int *, int *)`
- caller_count: `2`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e520`
- `0x18000e700`

## callees

- `0x18000e648`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000e695`
- `ntdll!NtQueryInformationToken` at `0x18000e6cf`
- `ntdll!NtQueryInformationToken` at `0x18000e695`
- `ntdll!NtQueryInformationToken` at `0x18000e6cf`

## pseudocode

```c
NTSTATUS __fastcall _werDetail::UtilLUAIsElevatedToken(HANDLE TokenHandle, _DWORD *a2, int *a3, int *a4)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  ULONG ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v10; // [rsp+68h] [rbp+20h] BYREF

  ReturnLength = 0;
  v10 = 0;
  TokenInformation = 1;
  *a3 = 1;
  *a2 = 0;
  result = NtQueryInformationToken(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength);
  if ( result >= 0 )
  {
    if ( TokenInformation == 2
      || TokenInformation == 1
      && (*a3 = 0, result = NtQueryInformationToken(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength), result >= 0)
      && v10 )
    {
      *a2 = 1;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18000e648  mov     rax, rsp
0x18000e64b  push    rbx
0x18000e64c  push    rsi
0x18000e64d  push    rdi
0x18000e64e  sub     rsp, 30h
0x18000e652  mov     r9d, 4; TokenInformationLength
0x18000e658  mov     dword ptr [rax+18h], 0
0x18000e65f  mov     dword ptr [rax+20h], 0
0x18000e666  mov     rdi, r8
0x18000e669  mov     dword ptr [rax+10h], 1
0x18000e670  lea     rax, [rax+18h]
0x18000e674  mov     rbx, rdx
0x18000e677  mov     dword ptr [r8], 1
0x18000e67e  mov     dword ptr [rdx], 0
0x18000e684  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18000e689  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000e68d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000e692  mov     rsi, rcx
0x18000e695  call    cs:__imp_NtQueryInformationToken
0x18000e69b  test    eax, eax
0x18000e69d  js      short loc_18000E6E6
0x18000e69f  cmp     [rsp+48h+TokenInformation], 2
0x18000e6a4  jz      short loc_18000E6E0
0x18000e6a6  cmp     [rsp+48h+TokenInformation], 1
0x18000e6ab  jnz     short loc_18000E6E6
0x18000e6ad  mov     r9d, 4; TokenInformationLength
0x18000e6b3  mov     dword ptr [rdi], 0
0x18000e6b9  lea     rax, [rsp+48h+arg_10]
0x18000e6be  mov     rcx, rsi; TokenHandle
0x18000e6c1  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18000e6c6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000e6cb  lea     edx, [r9+10h]; TokenInformationClass
0x18000e6cf  call    cs:__imp_NtQueryInformationToken
0x18000e6d5  test    eax, eax
0x18000e6d7  js      short loc_18000E6E6
0x18000e6d9  cmp     [rsp+48h+arg_18], 0
0x18000e6de  jz      short loc_18000E6E6
0x18000e6e0  mov     dword ptr [rbx], 1
0x18000e6e6  add     rsp, 30h
0x18000e6ea  pop     rdi
0x18000e6eb  pop     rsi
0x18000e6ec  pop     rbx
0x18000e6ed  retn
```
