# IsUserAdmin(bool &,void *)

- ea: `0x180024d48`
- end: `0x180024e25`
- name: `?IsUserAdmin@@YAKAEA_NPEAX@Z`
- size: `221`
- prototype: `unsigned int __fastcall(bool *, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180020ad0`
- `0x180020dcc`

## callees

- `0x18001c414`
- `0x180024d48`
- `0x18002dec0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024df0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024dd7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180024df0`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024dc1`
- `api-ms-win-security-base-l1-1-0!CheckTokenMembership` at `0x180024dc1`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180024dad`
- `api-ms-win-security-base-l1-1-0!AllocateAndInitializeSid` at `0x180024dad`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180024dcd`
- `api-ms-win-security-base-l1-1-0!FreeSid` at `0x180024dcd`

## string_xrefs

- `0x180024dfe`: `base\winsat\common\winsatutilities.cpp`

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
0x180024d48  push    rbp
0x180024d4a  push    rbx
0x180024d4b  push    rsi
0x180024d4c  push    rdi
0x180024d4d  lea     rbp, [rsp-3Fh]
0x180024d52  sub     rsp, 88h
0x180024d59  mov     rax, cs:__security_cookie
0x180024d60  xor     rax, rsp
0x180024d63  mov     [rbp+57h+var_28], rax
0x180024d67  xor     esi, esi
0x180024d69  mov     word ptr [rbp+57h+pIdentifierAuthority.Value+4], 500h
0x180024d6f  lea     rax, [rbp+57h+SidToCheck]
0x180024d73  mov     dword ptr [rbp+57h+pIdentifierAuthority.Value], esi
0x180024d76  mov     [rsp+0A0h+pSid], rax; pSid
0x180024d7b  mov     rdi, rcx
0x180024d7e  mov     [rsp+0A0h+nSubAuthority7], esi; nSubAuthority7
0x180024d82  lea     rcx, [rbp+57h+pIdentifierAuthority]; pIdentifierAuthority
0x180024d86  mov     [rsp+0A0h+nSubAuthority6], esi; nSubAuthority6
0x180024d8a  lea     r8d, [rsi+20h]; nSubAuthority0
0x180024d8e  mov     [rsp+0A0h+nSubAuthority5], esi; nSubAuthority5
0x180024d92  mov     r9d, 220h; nSubAuthority1
0x180024d98  mov     [rsp+0A0h+nSubAuthority4], esi; nSubAuthority4
0x180024d9c  mov     dl, 2; nSubAuthorityCount
0x180024d9e  mov     [rsp+0A0h+nSubAuthority3], esi; nSubAuthority3
0x180024da2  mov     dword ptr [rsp+0A0h+nSubAuthority2], esi; char
0x180024da6  mov     [rbp+57h+SidToCheck], rsi
0x180024daa  mov     [rbp+57h+IsMember], esi
0x180024dad  call    cs:__imp_AllocateAndInitializeSid
0x180024db3  test    eax, eax
0x180024db5  jz      short loc_180024DF0
0x180024db7  mov     rdx, [rbp+57h+SidToCheck]; SidToCheck
0x180024dbb  lea     r8, [rbp+57h+IsMember]; IsMember
0x180024dbf  xor     ecx, ecx; TokenHandle
0x180024dc1  call    cs:__imp_CheckTokenMembership
0x180024dc7  mov     rcx, [rbp+57h+SidToCheck]; pSid
0x180024dcb  mov     ebx, eax
0x180024dcd  call    cs:__imp_FreeSid
0x180024dd3  test    ebx, ebx
0x180024dd5  jnz     short loc_180024DE4
0x180024dd7  call    cs:__imp_GetLastError
0x180024ddd  mov     edx, 60Ch
0x180024de2  jmp     short loc_180024DFB
0x180024de4  cmp     [rbp+57h+IsMember], esi
0x180024de7  setnz   al
0x180024dea  mov     [rdi], al
0x180024dec  xor     eax, eax
0x180024dee  jmp     short loc_180024E0D
0x180024df0  call    cs:__imp_GetLastError
0x180024df6  mov     edx, 618h
0x180024dfb  xor     r9d, r9d
0x180024dfe  lea     rcx, aBaseWinsatComm; "base\\winsat\\common\\winsatutilities.c"...
0x180024e05  mov     r8d, eax
0x180024e08  call    Record_Win32Error_w
0x180024e0d  mov     rcx, [rbp+57h+var_28]
0x180024e11  xor     rcx, rsp; StackCookie
0x180024e14  call    __security_check_cookie
0x180024e19  add     rsp, 88h
0x180024e20  pop     rdi
0x180024e21  pop     rsi
0x180024e22  pop     rbx
0x180024e23  pop     rbp
0x180024e24  retn
```
