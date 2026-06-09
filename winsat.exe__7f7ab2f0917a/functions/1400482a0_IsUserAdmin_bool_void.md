# IsUserAdmin(bool &,void *)

- ea: `0x1400482a0`
- end: `0x14004837d`
- name: `?IsUserAdmin@@YAKAEA_NPEAX@Z`
- size: `221`
- prototype: `unsigned int __fastcall(bool *, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001a54c`

## callees

- `0x14003fa8c`
- `0x1400482a0`
- `0x140113220`

## import_xrefs

- `ADVAPI32!AllocateAndInitializeSid` at `0x140048305`
- `ADVAPI32!AllocateAndInitializeSid` at `0x140048305`
- `ADVAPI32!FreeSid` at `0x140048325`
- `ADVAPI32!FreeSid` at `0x140048325`
- `ADVAPI32!CheckTokenMembership` at `0x140048319`
- `ADVAPI32!CheckTokenMembership` at `0x140048319`
- `KERNEL32!GetLastError` at `0x14004832f`
- `KERNEL32!GetLastError` at `0x140048348`
- `KERNEL32!GetLastError` at `0x14004832f`
- `KERNEL32!GetLastError` at `0x140048348`

## string_xrefs

- `0x140048356`: `base\winsat\common\winsatutilities.cpp`

## pseudocode

```c
__int64 __fastcall IsUserAdmin(bool *a1, void *a2)
{
  BOOL v3; // ebx
  char nSubAuthority2; // [rsp+20h] [rbp-29h]
  WINBOOL IsMember; // [rsp+60h] [rbp+17h] BYREF
  PSID SidToCheck; // [rsp+68h] [rbp+1Fh] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp+27h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  SidToCheck = 0;
  IsMember = 0;
  if ( AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &SidToCheck) )
  {
    v3 = CheckTokenMembership(0, SidToCheck, &IsMember);
    FreeSid(SidToCheck);
    if ( v3 )
    {
      *a1 = IsMember != 0;
      return 0;
    }
    GetLastError();
  }
  else
  {
    GetLastError();
  }
  return Record_Win32Error_w("base\\winsat\\common\\winsatutilities.cpp", nSubAuthority2);
}

```

## disassembly

```asm
0x1400482a0  push    rbp
0x1400482a2  push    rbx
0x1400482a3  push    rsi
0x1400482a4  push    rdi
0x1400482a5  lea     rbp, [rsp-3Fh]
0x1400482aa  sub     rsp, 88h
0x1400482b1  mov     rax, cs:__security_cookie
0x1400482b8  xor     rax, rsp
0x1400482bb  mov     [rbp+57h+var_28], rax
0x1400482bf  xor     esi, esi
0x1400482c1  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x1400482c7  lea     rax, [rbp+57h+SidToCheck]
0x1400482cb  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x1400482ce  mov     [rsp+0A0h+pSid], rax; pSid
0x1400482d3  mov     rdi, rcx
0x1400482d6  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x1400482da  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x1400482de  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x1400482e2  lea     r8d, [rsi+20h]; nSubAuthority0
0x1400482e6  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x1400482ea  mov     r9d, 220h; nSubAuthority1
0x1400482f0  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x1400482f4  mov     dl, 2; nSubAuthorityCount
0x1400482f6  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x1400482fa  mov     dword ptr [rsp+0A0h+nSubAuthority2], esi; char
0x1400482fe  mov     [rbp+57h+SidToCheck], rsi
0x140048302  mov     [rbp+57h+IsMember], esi
0x140048305  call    cs:__imp_AllocateAndInitializeSid
0x14004830b  test    eax, eax
0x14004830d  jz      short loc_140048348
0x14004830f  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x140048313  lea     r8, [rbp+57h+IsMember]; IsMember
0x140048317  xor     ecx, ecx; TokenHandle
0x140048319  call    cs:__imp_CheckTokenMembership
0x14004831f  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x140048323  mov     ebx, eax
0x140048325  call    cs:__imp_FreeSid
0x14004832b  test    ebx, ebx
0x14004832d  jnz     short loc_14004833C
0x14004832f  call    cs:__imp_GetLastError
0x140048335  mov     edx, 60Ch
0x14004833a  jmp     short loc_140048353
0x14004833c  cmp     [rbp+57h+IsMember], esi
0x14004833f  setnz   al
0x140048342  mov     [rdi], al
0x140048344  xor     eax, eax
0x140048346  jmp     short loc_140048365
0x140048348  call    cs:__imp_GetLastError
0x14004834e  mov     edx, 618h
0x140048353  xor     r9d, r9d
0x140048356  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x14004835d  mov     r8d, eax
0x140048360  call    Record_Win32Error_w
0x140048365  mov     rcx, [rbp+57h+var_28]
0x140048369  xor     rcx, rsp; StackCookie
0x14004836c  call    __security_check_cookie
0x140048371  add     rsp, 88h
0x140048378  pop     rdi
0x140048379  pop     rsi
0x14004837a  pop     rbx
0x14004837b  pop     rbp
0x14004837c  retn
```
