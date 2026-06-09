# _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)

- ea: `0x18002f348`
- end: `0x18002f3ee`
- name: `?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z`
- size: `166`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180030a58`

## callees

- `0x18002f348`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18002f395`
- `ntdll!NtQueryInformationToken` at `0x18002f3cf`
- `ntdll!NtQueryInformationToken` at `0x18002f395`
- `ntdll!NtQueryInformationToken` at `0x18002f3cf`

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
0x18002f348  mov     rax, rsp
0x18002f34b  push    rbx
0x18002f34c  push    rsi
0x18002f34d  push    rdi
0x18002f34e  sub     rsp, 30h
0x18002f352  mov     r9d, 4; TokenInformationLength
0x18002f358  mov     dword ptr [rax+18h], 0
0x18002f35f  mov     dword ptr [rax+20h], 0
0x18002f366  mov     rdi, r8
0x18002f369  mov     dword ptr [rax+10h], 1
0x18002f370  lea     rax, [rax+18h]
0x18002f374  mov     rbx, rdx
0x18002f377  mov     dword ptr [r8], 1
0x18002f37e  mov     dword ptr [rdx], 0
0x18002f384  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18002f389  lea     edx, [r9+0Eh]; TokenInformationClass
0x18002f38d  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002f392  mov     rsi, rcx
0x18002f395  call    cs:__imp_NtQueryInformationToken
0x18002f39b  test    eax, eax
0x18002f39d  js      short loc_18002F3E6
0x18002f39f  cmp     [rsp+48h+TokenInformation], 2
0x18002f3a4  jz      short loc_18002F3E0
0x18002f3a6  cmp     [rsp+48h+TokenInformation], 1
0x18002f3ab  jnz     short loc_18002F3E6
0x18002f3ad  mov     r9d, 4; TokenInformationLength
0x18002f3b3  mov     dword ptr [rdi], 0
0x18002f3b9  lea     rax, [rsp+48h+arg_10]
0x18002f3be  mov     rcx, rsi; TokenHandle
0x18002f3c1  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18002f3c6  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18002f3cb  lea     edx, [r9+10h]; TokenInformationClass
0x18002f3cf  call    cs:__imp_NtQueryInformationToken
0x18002f3d5  test    eax, eax
0x18002f3d7  js      short loc_18002F3E6
0x18002f3d9  cmp     [rsp+48h+arg_18], 0
0x18002f3de  jz      short loc_18002F3E6
0x18002f3e0  mov     dword ptr [rbx], 1
0x18002f3e6  add     rsp, 30h
0x18002f3ea  pop     rdi
0x18002f3eb  pop     rsi
0x18002f3ec  pop     rbx
0x18002f3ed  retn
```
