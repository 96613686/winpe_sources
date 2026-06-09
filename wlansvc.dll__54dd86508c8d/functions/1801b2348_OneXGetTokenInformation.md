# OneXGetTokenInformation

- ea: `0x1801b2348`
- end: `0x1801b243c`
- name: `OneXGetTokenInformation`
- size: `244`
- prototype: `__int64 __fastcall(HANDLE TokenHandle)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18013dd4c`
- `0x1801b2614`

## callees

- `0x1801b2348`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b239f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b23fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b239f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1801b23fc`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801b2395`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801b23f2`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801b2395`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1801b23f2`
- `MobileNetworking!AllocateMemory` at `0x1801b23c6`
- `MobileNetworking!AllocateMemory` at `0x1801b23c6`
- `MobileNetworking!FreeMemory` at `0x1801b241a`
- `MobileNetworking!FreeMemory` at `0x1801b241a`

## string_xrefs

- `0x1801b23b4`: `OneXGetTokenInformation`
- `0x1801b240e`: `OneXGetTokenInformation`

## pseudocode

```c
__int64 __fastcall OneXGetTokenInformation(HANDLE TokenHandle, LPVOID *a2)
{
  DWORD v4; // ebx
  DWORD LastError; // eax
  DWORD TokenInformationLength; // [rsp+40h] [rbp+8h] BYREF
  LPVOID TokenInformation; // [rsp+48h] [rbp+10h] BYREF

  TokenInformationLength = 0;
  TokenInformation = 0;
  *a2 = 0;
  if ( TokenHandle )
  {
    if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength) )
    {
      v4 = 0;
    }
    else
    {
      LastError = GetLastError();
      v4 = LastError;
      if ( LastError != 122 && LastError )
        goto LABEL_11;
      v4 = AllocateMemory(TokenInformationLength, &TokenInformation, "OneXGetTokenInformation", 949);
      if ( v4 )
        goto LABEL_11;
    }
    if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, TokenInformationLength, &TokenInformationLength)
      || (v4 = GetLastError()) == 0 )
    {
      *a2 = TokenInformation;
      return v4;
    }
  }
  else
  {
    v4 = 6;
  }
LABEL_11:
  FreeMemory(&TokenInformation, "OneXGetTokenInformation", 965);
  return v4;
}

```

## disassembly

```asm
0x1801b2348  mov     rax, rsp
0x1801b234b  mov     [rax+18h], rbx
0x1801b234f  mov     [rax+20h], rsi
0x1801b2353  push    rdi
0x1801b2354  sub     rsp, 30h
0x1801b2358  mov     dword ptr [rax+8], 0
0x1801b235f  mov     rdi, rdx
0x1801b2362  mov     qword ptr [rax+10h], 0
0x1801b236a  mov     rsi, rcx
0x1801b236d  mov     qword ptr [rdx], 0
0x1801b2374  test    rcx, rcx
0x1801b2377  jnz     short loc_1801B2381
0x1801b2379  lea     ebx, [rcx+6]
0x1801b237c  jmp     loc_1801B2408
0x1801b2381  xor     r9d, r9d; TokenInformationLength
0x1801b2384  lea     rax, [rsp+38h+TokenInformationLength]
0x1801b2389  xor     r8d, r8d; TokenInformation
0x1801b238c  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1801b2391  lea     edx, [r9+1]; TokenInformationClass
0x1801b2395  call    cs:__imp_GetTokenInformation
0x1801b239b  test    eax, eax
0x1801b239d  jnz     short loc_1801B23D4
0x1801b239f  call    cs:__imp_GetLastError
0x1801b23a5  mov     ebx, eax
0x1801b23a7  cmp     eax, 7Ah ; 'z'
0x1801b23aa  jz      short loc_1801B23B0
0x1801b23ac  test    eax, eax
0x1801b23ae  jnz     short loc_1801B2408
0x1801b23b0  mov     ecx, [rsp+38h+TokenInformationLength]
0x1801b23b4  lea     r8, aOnexgettokenin; "OneXGetTokenInformation"
0x1801b23bb  mov     r9d, 3B5h
0x1801b23c1  lea     rdx, [rsp+38h+TokenInformation]
0x1801b23c6  call    cs:__imp_AllocateMemory
0x1801b23cc  mov     ebx, eax
0x1801b23ce  test    eax, eax
0x1801b23d0  jnz     short loc_1801B2408
0x1801b23d2  jmp     short loc_1801B23D6
0x1801b23d4  xor     ebx, ebx
0x1801b23d6  mov     r9d, [rsp+38h+TokenInformationLength]; TokenInformationLength
0x1801b23db  lea     rax, [rsp+38h+TokenInformationLength]
0x1801b23e0  mov     r8, [rsp+38h+TokenInformation]; TokenInformation
0x1801b23e5  mov     edx, 1; TokenInformationClass
0x1801b23ea  mov     rcx, rsi; TokenHandle
0x1801b23ed  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x1801b23f2  call    cs:__imp_GetTokenInformation
0x1801b23f8  test    eax, eax
0x1801b23fa  jnz     short loc_1801B2422
0x1801b23fc  call    cs:__imp_GetLastError
0x1801b2402  mov     ebx, eax
0x1801b2404  test    eax, eax
0x1801b2406  jz      short loc_1801B2422
0x1801b2408  mov     r8d, 3C5h
0x1801b240e  lea     rdx, aOnexgettokenin; "OneXGetTokenInformation"
0x1801b2415  lea     rcx, [rsp+38h+TokenInformation]
0x1801b241a  call    cs:__imp_FreeMemory
0x1801b2420  jmp     short loc_1801B242A
0x1801b2422  mov     rax, [rsp+38h+TokenInformation]
0x1801b2427  mov     [rdi], rax
0x1801b242a  mov     rsi, [rsp+38h+arg_18]
0x1801b242f  mov     eax, ebx
0x1801b2431  mov     rbx, [rsp+38h+arg_10]
0x1801b2436  add     rsp, 30h
0x1801b243a  pop     rdi
0x1801b243b  retn
```
