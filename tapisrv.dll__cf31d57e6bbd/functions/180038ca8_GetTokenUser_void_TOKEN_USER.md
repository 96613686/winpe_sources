# GetTokenUser(void *,_TOKEN_USER * *)

- ea: `0x180038ca8`
- end: `0x180038d6a`
- name: `?GetTokenUser@@YAJPEAXPEAPEAU_TOKEN_USER@@@Z`
- size: `194`
- prototype: `signed int __fastcall(HANDLE TokenHandle, struct _TOKEN_USER **)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1800384f4`
- `0x18003cb8c`
- `0x18003cd30`

## callees

- `0x18002c8d4`
- `0x180038ca8`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x180038d0c`
- `KERNEL32!HeapAlloc` at `0x180038d0c`
- `KERNEL32!GetLastError` at `0x180038ce2`
- `KERNEL32!GetLastError` at `0x180038d4d`
- `KERNEL32!GetLastError` at `0x180038ce2`
- `KERNEL32!GetLastError` at `0x180038d4d`
- `ADVAPI32!GetTokenInformation` at `0x180038cd8`
- `ADVAPI32!GetTokenInformation` at `0x180038d3b`
- `ADVAPI32!GetTokenInformation` at `0x180038cd8`
- `ADVAPI32!GetTokenInformation` at `0x180038d3b`

## pseudocode

```c
signed int __fastcall GetTokenUser(HANDLE TokenHandle, struct _TOKEN_USER **a2)
{
  signed int result; // eax
  struct _TOKEN_USER *v5; // rbx
  SIZE_T dwBytes; // [rsp+50h] [rbp+18h] BYREF

  LODWORD(dwBytes) = 0;
  if ( GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&dwBytes) || (result = GetLastError(), result == 122) )
  {
    v5 = (struct _TOKEN_USER *)HeapAlloc(ghTapisrvHeap, 8u, (unsigned int)dwBytes);
    if ( !v5 )
      return -2147483580;
    if ( GetTokenInformation(TokenHandle, TokenUser, v5, dwBytes, (PDWORD)&dwBytes) )
    {
      result = 0;
      *a2 = v5;
      return result;
    }
    ServerFree(v5);
    result = GetLastError();
  }
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180038ca8  mov     rax, rsp
0x180038cab  mov     [rax+8], rbx
0x180038caf  mov     [rax+10h], rsi
0x180038cb3  push    rdi
0x180038cb4  sub     rsp, 30h
0x180038cb8  xor     r9d, r9d; TokenInformationLength
0x180038cbb  mov     dword ptr [rax+18h], 0
0x180038cc2  mov     rdi, rdx
0x180038cc5  lea     rax, [rax+18h]
0x180038cc9  xor     r8d, r8d; TokenInformation
0x180038ccc  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180038cd1  mov     rsi, rcx
0x180038cd4  lea     edx, [r9+1]; TokenInformationClass
0x180038cd8  call    cs:__imp_GetTokenInformation
0x180038cde  test    eax, eax
0x180038ce0  jnz     short loc_180038CFB
0x180038ce2  call    cs:__imp_GetLastError
0x180038ce8  cmp     eax, 7Ah ; 'z'
0x180038ceb  jz      short loc_180038CFB
0x180038ced  test    eax, eax
0x180038cef  jle     short loc_180038D5A
0x180038cf1  movzx   eax, ax
0x180038cf4  or      eax, 80070000h
0x180038cf9  jmp     short loc_180038D5A
0x180038cfb  mov     r8d, dword ptr [rsp+38h+dwBytes]; dwBytes
0x180038d00  mov     edx, 8; dwFlags
0x180038d05  mov     rcx, cs:ghTapisrvHeap; hHeap
0x180038d0c  call    cs:__imp_HeapAlloc
0x180038d12  mov     rbx, rax
0x180038d15  test    rax, rax
0x180038d18  jnz     short loc_180038D21
0x180038d1a  mov     eax, 80000044h
0x180038d1f  jmp     short loc_180038D5A
0x180038d21  mov     r9d, dword ptr [rsp+38h+dwBytes]; TokenInformationLength
0x180038d26  lea     rax, [rsp+38h+dwBytes]
0x180038d2b  mov     r8, rbx; TokenInformation
0x180038d2e  mov     [rsp+38h+ReturnLength], rax; ReturnLength
0x180038d33  mov     edx, 1; TokenInformationClass
0x180038d38  mov     rcx, rsi; TokenHandle
0x180038d3b  call    cs:__imp_GetTokenInformation
0x180038d41  test    eax, eax
0x180038d43  jnz     short loc_180038D55
0x180038d45  mov     rcx, rbx; lpMem
0x180038d48  call    ServerFree
0x180038d4d  call    cs:__imp_GetLastError
0x180038d53  jmp     short loc_180038CED
0x180038d55  xor     eax, eax
0x180038d57  mov     [rdi], rbx
0x180038d5a  mov     rbx, [rsp+38h+arg_0]
0x180038d5f  mov     rsi, [rsp+38h+arg_8]
0x180038d64  add     rsp, 30h
0x180038d68  pop     rdi
0x180038d69  retn
```
