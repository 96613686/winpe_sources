# _LUAGetUserFromToken(void *,_TOKEN_USER * *)

- ea: `0x1800dbb88`
- end: `0x1800dbc26`
- name: `?_LUAGetUserFromToken@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `158`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800dbed0`

## callees

- `0x1800dbb88`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbc15`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800dbc15`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dbbd2`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800dbbd2`
- `ntdll!NtQueryInformationToken` at `0x1800dbbba`
- `ntdll!NtQueryInformationToken` at `0x1800dbc01`
- `ntdll!NtQueryInformationToken` at `0x1800dbbba`
- `ntdll!NtQueryInformationToken` at `0x1800dbc01`

## pseudocode

```c
__int64 __fastcall _LUAGetUserFromToken(HANDLE TokenHandle, struct _TOKEN_USER **a2)
{
  NTSTATUS v4; // edi
  struct _TOKEN_USER *v5; // rbx
  ULONG TokenInformationLength; // [rsp+68h] [rbp+10h] BYREF

  *a2 = 0;
  TokenInformationLength = 0;
  v4 = NtQueryInformationToken(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  if ( v4 == -1073741789 )
  {
    v5 = (struct _TOKEN_USER *)LocalAlloc(0x40u, TokenInformationLength);
    if ( v5 )
    {
      v4 = NtQueryInformationToken(TokenHandle, TokenUser, v5, TokenInformationLength, &TokenInformationLength);
      if ( v4 < 0 )
        LocalFree(v5);
      else
        *a2 = v5;
    }
    else
    {
      return (unsigned int)-1073741801;
    }
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800dbb88  push    rbx
0x1800dbb8a  push    rbp
0x1800dbb8b  push    rsi
0x1800dbb8c  push    rdi
0x1800dbb8d  sub     rsp, 38h
0x1800dbb91  xor     r9d, r9d; TokenInformationLength
0x1800dbb94  mov     qword ptr [rdx], 0
0x1800dbb9b  mov     rsi, rdx
0x1800dbb9e  mov     [rsp+58h+TokenInformationLength], 0
0x1800dbba6  lea     rax, [rsp+58h+TokenInformationLength]
0x1800dbbab  xor     r8d, r8d; TokenInformation
0x1800dbbae  mov     rbp, rcx
0x1800dbbb1  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800dbbb6  lea     edx, [r9+1]; TokenInformationClass
0x1800dbbba  call    cs:__imp_NtQueryInformationToken
0x1800dbbc0  mov     edi, eax
0x1800dbbc2  cmp     eax, 0C0000023h
0x1800dbbc7  jnz     short loc_1800DBC1B
0x1800dbbc9  mov     edx, [rsp+58h+TokenInformationLength]; uBytes
0x1800dbbcd  mov     ecx, 40h ; '@'; uFlags
0x1800dbbd2  call    cs:__imp_LocalAlloc
0x1800dbbd8  mov     rbx, rax
0x1800dbbdb  test    rax, rax
0x1800dbbde  jnz     short loc_1800DBBE7
0x1800dbbe0  mov     edi, 0C0000017h
0x1800dbbe5  jmp     short loc_1800DBC1B
0x1800dbbe7  mov     r9d, [rsp+58h+TokenInformationLength]; TokenInformationLength
0x1800dbbec  lea     rax, [rsp+58h+TokenInformationLength]
0x1800dbbf1  mov     r8, rbx; TokenInformation
0x1800dbbf4  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x1800dbbf9  mov     edx, 1; TokenInformationClass
0x1800dbbfe  mov     rcx, rbp; TokenHandle
0x1800dbc01  call    cs:__imp_NtQueryInformationToken
0x1800dbc07  mov     edi, eax
0x1800dbc09  test    eax, eax
0x1800dbc0b  js      short loc_1800DBC12
0x1800dbc0d  mov     [rsi], rbx
0x1800dbc10  jmp     short loc_1800DBC1B
0x1800dbc12  mov     rcx, rbx; hMem
0x1800dbc15  call    cs:__imp_LocalFree
0x1800dbc1b  mov     eax, edi
0x1800dbc1d  add     rsp, 38h
0x1800dbc21  pop     rdi
0x1800dbc22  pop     rsi
0x1800dbc23  pop     rbp
0x1800dbc24  pop     rbx
0x1800dbc25  retn
```
