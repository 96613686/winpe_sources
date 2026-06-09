# IsUserAdmin(int *)

- ea: `0x180006c50`
- end: `0x180006d2b`
- name: `?IsUserAdmin@@YAKPEAH@Z`
- size: `219`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180006c50`
- `0x18002f3e0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180006ce2`
- `KERNEL32!GetLastError` at `0x180006ce2`
- `ADVAPI32!FreeSid` at `0x180006cfa`
- `ADVAPI32!FreeSid` at `0x180006cfa`
- `ADVAPI32!CheckTokenMembership` at `0x180006cd2`
- `ADVAPI32!CheckTokenMembership` at `0x180006cd2`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180006cb8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x180006cb8`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(PBOOL IsMember)
{
  DWORD LastError; // ebx
  PSID SidToCheck; // [rsp+60h] [rbp-28h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v5; // [rsp+68h] [rbp-20h] BYREF

  *(_WORD *)&v5.Value[4] = 1280;
  *(_DWORD *)v5.Value = 0;
  LastError = 0;
  SidToCheck = 0;
  if ( !AllocateAndInitializeSid(&v5, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck)
    || !CheckTokenMembership(0, SidToCheck, IsMember) )
  {
    LastError = GetLastError();
  }
  if ( SidToCheck )
    FreeSid(SidToCheck);
  return LastError;
}

```

## disassembly

```asm
0x180006c50  mov     r11, rsp
0x180006c53  mov     [r11+10h], rbx
0x180006c57  mov     [r11+18h], rsi
0x180006c5b  push    rdi
0x180006c5c  sub     rsp, 80h
0x180006c63  mov     rax, cs:__security_cookie
0x180006c6a  xor     rax, rsp
0x180006c6d  mov     [rsp+88h+var_18], rax
0x180006c72  xor     esi, esi
0x180006c74  mov     [rsp+88h+var_1C], 500h
0x180006c7b  lea     rax, [r11-28h]
0x180006c7f  mov     [rsp+88h+var_20], esi
0x180006c83  mov     [r11-38h], rax
0x180006c87  mov     rdi, rcx
0x180006c8a  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x180006c8e  lea     rcx, [r11-20h]; pIdentifierAuthority
0x180006c92  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x180006c96  lea     r8d, [rsi+20h]; nSubAuthority0
0x180006c9a  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x180006c9e  mov     r9d, 220h; nSubAuthority1
0x180006ca4  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x180006ca8  mov     dl, 2; nSubAuthorityCount
0x180006caa  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x180006cae  mov     ebx, esi
0x180006cb0  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x180006cb4  mov     [r11-28h], rsi
0x180006cb8  call    cs:__imp_AllocateAndInitializeSid
0x180006cbf  nop     dword ptr [rax+rax+00h]
0x180006cc4  test    eax, eax
0x180006cc6  jz      short loc_180006CE2
0x180006cc8  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x180006ccd  mov     r8, rdi; IsMember
0x180006cd0  xor     ecx, ecx; TokenHandle
0x180006cd2  call    cs:__imp_CheckTokenMembership
0x180006cd9  nop     dword ptr [rax+rax+00h]
0x180006cde  test    eax, eax
0x180006ce0  jnz     short loc_180006CF0
0x180006ce2  call    cs:__imp_GetLastError
0x180006ce9  nop     dword ptr [rax+rax+00h]
0x180006cee  mov     ebx, eax
0x180006cf0  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x180006cf5  test    rcx, rcx
0x180006cf8  jz      short loc_180006D06
0x180006cfa  call    cs:__imp_FreeSid
0x180006d01  nop     dword ptr [rax+rax+00h]
0x180006d06  mov     eax, ebx
0x180006d08  mov     rcx, [rsp+88h+var_18]
0x180006d0d  xor     rcx, rsp; StackCookie
0x180006d10  call    __security_check_cookie
0x180006d15  lea     r11, [rsp+88h+var_8]
0x180006d1d  mov     rbx, [r11+18h]
0x180006d21  mov     rsi, [r11+20h]
0x180006d25  mov     rsp, r11
0x180006d28  pop     rdi
0x180006d29  retn
```
