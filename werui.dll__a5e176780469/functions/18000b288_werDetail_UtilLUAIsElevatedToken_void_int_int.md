# _werDetail::UtilLUAIsElevatedToken(void *,int *,int *)

- ea: `0x18000b288`
- end: `0x18000b32e`
- name: `?UtilLUAIsElevatedToken@_werDetail@@YAJPEAXPEAH1@Z`
- size: `166`
- prototype: `NTSTATUS __fastcall(HANDLE TokenHandle, _DWORD *, int *, int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000b1b4`

## callees

- `0x18000b288`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000b2d5`
- `ntdll!NtQueryInformationToken` at `0x18000b30f`
- `ntdll!NtQueryInformationToken` at `0x18000b2d5`
- `ntdll!NtQueryInformationToken` at `0x18000b30f`

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
0x18000b288  mov     rax, rsp
0x18000b28b  push    rbx
0x18000b28c  push    rsi
0x18000b28d  push    rdi
0x18000b28e  sub     rsp, 30h
0x18000b292  mov     r9d, 4; TokenInformationLength
0x18000b298  mov     dword ptr [rax+18h], 0
0x18000b29f  mov     dword ptr [rax+20h], 0
0x18000b2a6  mov     rdi, r8
0x18000b2a9  mov     dword ptr [rax+10h], 1
0x18000b2b0  lea     rax, [rax+18h]
0x18000b2b4  mov     rbx, rdx
0x18000b2b7  mov     dword ptr [r8], 1
0x18000b2be  mov     dword ptr [rdx], 0
0x18000b2c4  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18000b2c9  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000b2cd  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b2d2  mov     rsi, rcx
0x18000b2d5  call    cs:__imp_NtQueryInformationToken
0x18000b2db  test    eax, eax
0x18000b2dd  js      short loc_18000B326
0x18000b2df  cmp     [rsp+48h+TokenInformation], 2
0x18000b2e4  jz      short loc_18000B320
0x18000b2e6  cmp     [rsp+48h+TokenInformation], 1
0x18000b2eb  jnz     short loc_18000B326
0x18000b2ed  mov     r9d, 4; TokenInformationLength
0x18000b2f3  mov     dword ptr [rdi], 0
0x18000b2f9  lea     rax, [rsp+48h+arg_10]
0x18000b2fe  mov     rcx, rsi; TokenHandle
0x18000b301  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18000b306  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18000b30b  lea     edx, [r9+10h]; TokenInformationClass
0x18000b30f  call    cs:__imp_NtQueryInformationToken
0x18000b315  test    eax, eax
0x18000b317  js      short loc_18000B326
0x18000b319  cmp     [rsp+48h+arg_18], 0
0x18000b31e  jz      short loc_18000B326
0x18000b320  mov     dword ptr [rbx], 1
0x18000b326  add     rsp, 30h
0x18000b32a  pop     rdi
0x18000b32b  pop     rsi
0x18000b32c  pop     rbx
0x18000b32d  retn
```
