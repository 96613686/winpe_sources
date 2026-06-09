# LUAIsElevatedToken(void *,int *,int *)

- ea: `0x18001cf44`
- end: `0x18001cffc`
- name: `?LUAIsElevatedToken@@YAJPEAXPEAH1@Z`
- size: `184`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, int *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18001ce3c`

## callees

- `0x180010680`
- `0x18001cf44`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cf88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cfcd`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cf88`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18001cfcd`

## pseudocode

```c
__int64 __fastcall LUAIsElevatedToken(HANDLE TokenHandle, int *a2, int *a3)
{
  int Error; // ebx
  int TokenInformation; // [rsp+58h] [rbp+10h] BYREF
  DWORD ReturnLength; // [rsp+60h] [rbp+18h] BYREF
  int v10; // [rsp+68h] [rbp+20h] BYREF

  Error = 0;
  TokenInformation = 1;
  ReturnLength = 0;
  v10 = 0;
  *a3 = 1;
  *a2 = 0;
  if ( GetTokenInformation(TokenHandle, TokenElevationType, &TokenInformation, 4u, &ReturnLength)
    || (Error = ResultFromLastError(), Error >= 0) )
  {
    if ( TokenInformation == 2 )
      goto LABEL_8;
    if ( TokenInformation == 1 )
    {
      *a3 = 0;
      if ( !GetTokenInformation(TokenHandle, TokenElevation, &v10, 4u, &ReturnLength) )
        return (unsigned int)ResultFromLastError();
      if ( !v10 )
        return (unsigned int)Error;
LABEL_8:
      *a2 = 1;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18001cf44  mov     rax, rsp
0x18001cf47  mov     [rax+8], rbx
0x18001cf4b  push    rbp
0x18001cf4c  push    rsi
0x18001cf4d  push    rdi
0x18001cf4e  sub     rsp, 30h
0x18001cf52  xor     ebx, ebx
0x18001cf54  mov     dword ptr [rax+10h], 1
0x18001cf5b  mov     [rax+18h], ebx
0x18001cf5e  mov     rsi, r8
0x18001cf61  mov     [rax+20h], ebx
0x18001cf64  lea     rax, [rax+18h]
0x18001cf68  mov     rdi, rdx
0x18001cf6b  mov     dword ptr [r8], 1
0x18001cf72  mov     [rdx], ebx
0x18001cf74  lea     r9d, [rbx+4]; TokenInformationLength
0x18001cf78  lea     edx, [rbx+12h]; TokenInformationClass
0x18001cf7b  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001cf80  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x18001cf85  mov     rbp, rcx
0x18001cf88  call    cs:__imp_GetTokenInformation
0x18001cf8e  test    eax, eax
0x18001cf90  jnz     short loc_18001CF9D
0x18001cf92  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001cf97  mov     ebx, eax
0x18001cf99  test    eax, eax
0x18001cf9b  js      short loc_18001CFED
0x18001cf9d  cmp     [rsp+48h+TokenInformation], 2
0x18001cfa2  jz      short loc_18001CFE7
0x18001cfa4  cmp     [rsp+48h+TokenInformation], 1
0x18001cfa9  jnz     short loc_18001CFED
0x18001cfab  mov     r9d, 4; TokenInformationLength
0x18001cfb1  mov     dword ptr [rsi], 0
0x18001cfb7  lea     rax, [rsp+48h+arg_10]
0x18001cfbc  mov     rcx, rbp; TokenHandle
0x18001cfbf  lea     r8, [rsp+48h+arg_18]; TokenInformation
0x18001cfc4  mov     [rsp+48h+ReturnLength], rax; ReturnLength
0x18001cfc9  lea     edx, [r9+10h]; TokenInformationClass
0x18001cfcd  call    cs:__imp_GetTokenInformation
0x18001cfd3  test    eax, eax
0x18001cfd5  jnz     short loc_18001CFE0
0x18001cfd7  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x18001cfdc  mov     ebx, eax
0x18001cfde  jmp     short loc_18001CFED
0x18001cfe0  cmp     [rsp+48h+arg_18], 0
0x18001cfe5  jz      short loc_18001CFED
0x18001cfe7  mov     dword ptr [rdi], 1
0x18001cfed  mov     eax, ebx
0x18001cfef  mov     rbx, [rsp+48h+arg_0]
0x18001cff4  add     rsp, 30h
0x18001cff8  pop     rdi
0x18001cff9  pop     rsi
0x18001cffa  pop     rbp
0x18001cffb  retn
```
