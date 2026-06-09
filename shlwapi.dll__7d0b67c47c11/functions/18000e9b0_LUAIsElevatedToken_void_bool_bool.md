# _LUAIsElevatedToken(void *,bool *,bool *)

- ea: `0x18000e9b0`
- end: `0x18000ea68`
- name: `?_LUAIsElevatedToken@@YAJPEAXPEA_N1@Z`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, bool *, bool *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000fb88`

## callees

- `0x18000e9b0`
- `0x180012550`

## import_xrefs

- `ntdll!NtQueryInformationToken` at `0x18000ea08`
- `ntdll!NtQueryInformationToken` at `0x18000ea3f`
- `ntdll!NtQueryInformationToken` at `0x18000ea08`
- `ntdll!NtQueryInformationToken` at `0x18000ea3f`

## pseudocode

```c
NTSTATUS __fastcall _LUAIsElevatedToken(HANDLE TokenHandle, bool *a2, bool *a3)
{
  NTSTATUS result; // eax
  int TokenInformation; // [rsp+30h] [rbp-38h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-34h] BYREF
  int v9; // [rsp+38h] [rbp-30h] BYREF

  *a3 = 0;
  *a2 = 0;
  ReturnLength = 0;
  v9 = 0;
  TokenInformation = 1;
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
0x18000e9b0  push    rbx
0x18000e9b2  push    rsi
0x18000e9b3  push    rdi
0x18000e9b4  sub     rsp, 50h
0x18000e9b8  mov     rax, cs:__security_cookie
0x18000e9bf  xor     rax, rsp
0x18000e9c2  mov     [rsp+68h+var_28], rax
0x18000e9c7  mov     byte ptr [r8], 0
0x18000e9cb  lea     rax, [rsp+68h+var_34]
0x18000e9d0  mov     r9d, 4; TokenInformationLength
0x18000e9d6  mov     byte ptr [rdx], 0
0x18000e9d9  mov     rsi, r8
0x18000e9dc  mov     [rsp+68h+var_34], 0
0x18000e9e4  mov     rbx, rdx
0x18000e9e7  mov     [rsp+68h+var_30], 0
0x18000e9ef  lea     r8, [rsp+68h+TokenInformation]; TokenInformation
0x18000e9f4  mov     [rsp+68h+TokenInformation], 1
0x18000e9fc  lea     edx, [r9+0Eh]; TokenInformationClass
0x18000ea00  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000ea05  mov     rdi, rcx
0x18000ea08  call    cs:__imp_NtQueryInformationToken
0x18000ea0e  test    eax, eax
0x18000ea10  js      short loc_18000EA53
0x18000ea12  cmp     [rsp+68h+TokenInformation], 2
0x18000ea17  jz      short loc_18000EA50
0x18000ea19  cmp     [rsp+68h+TokenInformation], 1
0x18000ea1e  jnz     short loc_18000EA53
0x18000ea20  mov     r9d, 4; TokenInformationLength
0x18000ea26  mov     byte ptr [rsi], 0
0x18000ea29  lea     rax, [rsp+68h+var_34]
0x18000ea2e  mov     rcx, rdi; TokenHandle
0x18000ea31  lea     r8, [rsp+68h+var_30]; TokenInformation
0x18000ea36  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x18000ea3b  lea     edx, [r9+10h]; TokenInformationClass
0x18000ea3f  call    cs:__imp_NtQueryInformationToken
0x18000ea45  test    eax, eax
0x18000ea47  js      short loc_18000EA53
0x18000ea49  cmp     [rsp+68h+var_30], 0
0x18000ea4e  jz      short loc_18000EA53
0x18000ea50  mov     byte ptr [rbx], 1
0x18000ea53  mov     rcx, [rsp+68h+var_28]
0x18000ea58  xor     rcx, rsp; StackCookie
0x18000ea5b  call    __security_check_cookie
0x18000ea60  add     rsp, 50h
0x18000ea64  pop     rdi
0x18000ea65  pop     rsi
0x18000ea66  pop     rbx
0x18000ea67  retn
```
