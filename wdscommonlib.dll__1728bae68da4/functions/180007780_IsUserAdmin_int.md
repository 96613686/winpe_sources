# IsUserAdmin(int *)

- ea: `0x180007780`
- end: `0x18000785b`
- name: `?IsUserAdmin@@YAKPEAH@Z`
- size: `219`
- prototype: `unsigned int __fastcall(PBOOL IsMember)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation`

## callees

- `0x180007780`
- `0x180030390`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180007812`
- `KERNEL32!GetLastError` at `0x180007812`
- `ADVAPI32!FreeSid` at `0x18000782a`
- `ADVAPI32!FreeSid` at `0x18000782a`
- `ADVAPI32!CheckTokenMembership` at `0x180007802`
- `ADVAPI32!CheckTokenMembership` at `0x180007802`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800077e8`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800077e8`

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
0x180007780  mov     r11, rsp
0x180007783  mov     [r11+10h], rbx
0x180007787  mov     [r11+18h], rsi
0x18000778b  push    rdi
0x18000778c  sub     rsp, 80h
0x180007793  mov     rax, cs:__security_cookie
0x18000779a  xor     rax, rsp
0x18000779d  mov     [rsp+88h+var_18], rax
0x1800077a2  xor     esi, esi
0x1800077a4  mov     [rsp+88h+var_1C], 500h
0x1800077ab  lea     rax, [r11-28h]
0x1800077af  mov     [rsp+88h+var_20], esi
0x1800077b3  mov     [r11-38h], rax
0x1800077b7  mov     rdi, rcx
0x1800077ba  mov     [rsp+88h+nSubAuthority7], esi; nSubAuthority7
0x1800077be  lea     rcx, [r11-20h]; pIdentifierAuthority
0x1800077c2  mov     [rsp+88h+nSubAuthority6], esi; nSubAuthority6
0x1800077c6  lea     r8d, [rsi+20h]; nSubAuthority0
0x1800077ca  mov     [rsp+88h+nSubAuthority5], esi; nSubAuthority5
0x1800077ce  mov     r9d, 220h; nSubAuthority1
0x1800077d4  mov     [rsp+88h+nSubAuthority4], esi; nSubAuthority4
0x1800077d8  mov     dl, 2; nSubAuthorityCount
0x1800077da  mov     [rsp+88h+nSubAuthority3], esi; nSubAuthority3
0x1800077de  mov     ebx, esi
0x1800077e0  mov     [rsp+88h+nSubAuthority2], esi; nSubAuthority2
0x1800077e4  mov     [r11-28h], rsi
0x1800077e8  call    cs:__imp_AllocateAndInitializeSid
0x1800077ef  nop     dword ptr [rax+rax+00h]
0x1800077f4  test    eax, eax
0x1800077f6  jz      short loc_180007812
0x1800077f8  mov     rdx, [rsp+88h+SidToCheck]; SidToCheck
0x1800077fd  mov     r8, rdi; IsMember
0x180007800  xor     ecx, ecx; TokenHandle
0x180007802  call    cs:__imp_CheckTokenMembership
0x180007809  nop     dword ptr [rax+rax+00h]
0x18000780e  test    eax, eax
0x180007810  jnz     short loc_180007820
0x180007812  call    cs:__imp_GetLastError
0x180007819  nop     dword ptr [rax+rax+00h]
0x18000781e  mov     ebx, eax
0x180007820  mov     rcx, [rsp+88h+SidToCheck]; pSid
0x180007825  test    rcx, rcx
0x180007828  jz      short loc_180007836
0x18000782a  call    cs:__imp_FreeSid
0x180007831  nop     dword ptr [rax+rax+00h]
0x180007836  mov     eax, ebx
0x180007838  mov     rcx, [rsp+88h+var_18]
0x18000783d  xor     rcx, rsp; StackCookie
0x180007840  call    __security_check_cookie
0x180007845  lea     r11, [rsp+88h+var_8]
0x18000784d  mov     rbx, [r11+18h]
0x180007851  mov     rsi, [r11+20h]
0x180007855  mov     rsp, r11
0x180007858  pop     rdi
0x180007859  retn
```
