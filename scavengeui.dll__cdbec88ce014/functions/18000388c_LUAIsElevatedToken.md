# LUAIsElevatedToken

- ea: `0x18000388c`
- end: `0x180003932`
- name: `LUAIsElevatedToken`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180002a78`

## callees

- `0x18000388c`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x1800038d9`
- `ntdll!NtQueryInformationToken` at `0x180003913`
- `ntdll!NtQueryInformationToken` at `0x1800038d9`
- `ntdll!NtQueryInformationToken` at `0x180003913`

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
0x18000388c  mov     rax, rsp
0x18000388f  push    rbx
0x180003890  push    rsi
0x180003891  push    rdi
0x180003892  sub     rsp, 30h
0x180003896  mov     r9d, 4; TokenInformationLength
0x18000389c  mov     dword ptr [rax+18h], 0
0x1800038a3  mov     dword ptr [rax+20h], 0
0x1800038aa  mov     rdi, r8
0x1800038ad  mov     dword ptr [rax+10h], 1
0x1800038b4  lea     rax, [rax+18h]
0x1800038b8  mov     rbx, rdx
0x1800038bb  mov     dword ptr [r8], 1
0x1800038c2  mov     dword ptr [rdx], 0
0x1800038c8  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800038cd  lea     edx, [r9+0Eh]; TokenInformationClass
0x1800038d1  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x1800038d6  mov     rsi, rcx
0x1800038d9  call    cs:__imp_NtQueryInformationToken
0x1800038df  test    eax, eax
0x1800038e1  js      short loc_18000392A
0x1800038e3  cmp     [rsp+48h+TokenInformation], 2
0x1800038e8  jz      short loc_180003924
0x1800038ea  cmp     [rsp+48h+TokenInformation], 1
0x1800038ef  jnz     short loc_18000392A
0x1800038f1  mov     r9d, 4; TokenInformationLength
0x1800038f7  mov     dword ptr [rdi], 0
0x1800038fd  lea     rax, [rsp+48h+arg_10]
0x180003902  mov     rcx, rsi; TokenHandle
0x180003905  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18000390a  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000390f  lea     edx, [r9+10h]; TokenInformationClass
0x180003913  call    cs:__imp_NtQueryInformationToken
0x180003919  test    eax, eax
0x18000391b  js      short loc_18000392A
0x18000391d  cmp     [rsp+48h+arg_18], 0
0x180003922  jz      short loc_18000392A
0x180003924  mov     dword ptr [rbx], 1
0x18000392a  add     rsp, 30h
0x18000392e  pop     rdi
0x18000392f  pop     rsi
0x180003930  pop     rbx
0x180003931  retn
```
