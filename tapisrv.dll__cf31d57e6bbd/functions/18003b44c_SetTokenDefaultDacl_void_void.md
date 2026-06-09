# SetTokenDefaultDacl(void *,void *)

- ea: `0x18003b44c`
- end: `0x18003b5d0`
- name: `?SetTokenDefaultDacl@@YAJPEAX0@Z`
- size: `388`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, PSID pSid)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation`

## callers

- `0x1800384f4`

## callees

- `0x180001600`
- `0x18002c8d4`
- `0x18003b44c`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18003b4f1`
- `KERNEL32!HeapAlloc` at `0x18003b4f1`
- `KERNEL32!GetLastError` at `0x18003b578`
- `KERNEL32!GetLastError` at `0x18003b578`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b535`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b54e`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b535`
- `ADVAPI32!AddAccessAllowedAce` at `0x18003b54e`
- `ADVAPI32!GetLengthSid` at `0x18003b4cc`
- `ADVAPI32!GetLengthSid` at `0x18003b4d8`
- `ADVAPI32!GetLengthSid` at `0x18003b4cc`
- `ADVAPI32!GetLengthSid` at `0x18003b4d8`
- `ADVAPI32!InitializeAcl` at `0x18003b516`
- `ADVAPI32!InitializeAcl` at `0x18003b516`
- `ADVAPI32!FreeSid` at `0x18003b596`
- `ADVAPI32!FreeSid` at `0x18003b596`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003b4bb`
- `ADVAPI32!AllocateAndInitializeSid` at `0x18003b4bb`
- `ADVAPI32!SetTokenInformation` at `0x18003b569`
- `ADVAPI32!SetTokenInformation` at `0x18003b569`

## pseudocode

```c
__int64 __fastcall SetTokenDefaultDacl(HANDLE TokenHandle, PSID pSid)
{
  DWORD LengthSid; // ebx
  DWORD v5; // ebx
  unsigned int v6; // ebx
  signed int LastError; // eax
  PACL pAcl; // [rsp+60h] [rbp-20h] BYREF
  PSID pSida; // [rsp+68h] [rbp-18h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+70h] [rbp-10h] BYREF

  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  pSida = 0;
  pAcl = 0;
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 1u, 0x12u, 0, 0, 0, 0, 0, 0, 0, &pSida) )
    goto LABEL_9;
  LengthSid = GetLengthSid(pSid);
  v5 = GetLengthSid(pSida) + 32 + LengthSid;
  pAcl = (PACL)HeapAlloc(ghTapisrvHeap, 8u, v5);
  if ( !pAcl )
  {
    v6 = -2147483580;
    goto LABEL_11;
  }
  if ( InitializeAcl(pAcl, v5, 2u)
    && AddAccessAllowedAce(pAcl, 2u, 0x10000000u, pSida)
    && AddAccessAllowedAce(pAcl, 2u, 0x10000000u, pSid)
    && SetTokenInformation(TokenHandle, TokenDefaultDacl, &pAcl, 8u) )
  {
    v6 = 0;
  }
  else
  {
LABEL_9:
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      v6 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_11:
  if ( pSida )
    FreeSid(pSida);
  if ( pAcl )
    ServerFree(pAcl);
  return v6;
}

```

## disassembly

```asm
0x18003b44c  mov     r11, rsp
0x18003b44f  mov     [r11+18h], rbx
0x18003b453  mov     [r11+20h], rsi
0x18003b457  push    rbp
0x18003b458  push    rdi
0x18003b459  push    r14
0x18003b45b  mov     rbp, rsp
0x18003b45e  sub     rsp, 80h
0x18003b465  mov     rax, cs:__security_cookie
0x18003b46c  xor     rax, rsp
0x18003b46f  mov     [rbp+var_8], rax
0x18003b473  xor     r14d, r14d
0x18003b476  mov     word ptr [rbp+pIdentifierAuthority.Value+4], 500h
0x18003b47c  lea     rax, [rbp+pSid]
0x18003b480  mov     dword ptr [rbp+pIdentifierAuthority.Value], r14d
0x18003b484  mov     [r11-48h], rax
0x18003b488  mov     rdi, rdx
0x18003b48b  mov     [r11-50h], r14d
0x18003b48f  mov     rsi, rcx
0x18003b492  mov     [r11-58h], r14d
0x18003b496  lea     r8d, [r14+12h]; nSubAuthority0
0x18003b49a  mov     [r11-60h], r14d
0x18003b49e  lea     rcx, [rbp+pIdentifierAuthority]; pIdentifierAuthority
0x18003b4a2  mov     [r11-68h], r14d
0x18003b4a6  xor     r9d, r9d; nSubAuthority1
0x18003b4a9  mov     [r11-70h], r14d
0x18003b4ad  mov     dl, 1; nSubAuthorityCount
0x18003b4af  mov     [r11-78h], r14d
0x18003b4b3  mov     [rbp+pSid], r14
0x18003b4b7  mov     [rbp+pAcl], r14
0x18003b4bb  call    cs:__imp_AllocateAndInitializeSid
0x18003b4c1  test    eax, eax
0x18003b4c3  jz      loc_18003B578
0x18003b4c9  mov     rcx, rdi; pSid
0x18003b4cc  call    cs:__imp_GetLengthSid
0x18003b4d2  mov     rcx, [rbp+pSid]; pSid
0x18003b4d6  mov     ebx, eax
0x18003b4d8  call    cs:__imp_GetLengthSid
0x18003b4de  mov     rcx, cs:ghTapisrvHeap; hHeap
0x18003b4e5  lea     edx, [r14+8]; dwFlags
0x18003b4e9  add     eax, 20h ; ' '
0x18003b4ec  add     ebx, eax
0x18003b4ee  mov     r8d, ebx; dwBytes
0x18003b4f1  call    cs:__imp_HeapAlloc
0x18003b4f7  mov     [rbp+pAcl], rax
0x18003b4fb  test    rax, rax
0x18003b4fe  jnz     short loc_18003B50A
0x18003b500  mov     ebx, 80000044h
0x18003b505  jmp     loc_18003B58D
0x18003b50a  mov     rcx, [rbp+pAcl]; pAcl
0x18003b50e  mov     r8d, 2; dwAclRevision
0x18003b514  mov     edx, ebx; nAclLength
0x18003b516  call    cs:__imp_InitializeAcl
0x18003b51c  test    eax, eax
0x18003b51e  jz      short loc_18003B578
0x18003b520  mov     r9, [rbp+pSid]; pSid
0x18003b524  mov     ebx, 10000000h
0x18003b529  mov     rcx, [rbp+pAcl]; pAcl
0x18003b52d  mov     r8d, ebx; AccessMask
0x18003b530  mov     edx, 2; dwAceRevision
0x18003b535  call    cs:__imp_AddAccessAllowedAce
0x18003b53b  test    eax, eax
0x18003b53d  jz      short loc_18003B578
0x18003b53f  mov     rcx, [rbp+pAcl]; pAcl
0x18003b543  mov     r9, rdi; pSid
0x18003b546  mov     r8d, ebx; AccessMask
0x18003b549  mov     edx, 2; dwAceRevision
0x18003b54e  call    cs:__imp_AddAccessAllowedAce
0x18003b554  test    eax, eax
0x18003b556  jz      short loc_18003B578
0x18003b558  mov     r9d, 8; TokenInformationLength
0x18003b55e  lea     r8, [rbp+pAcl]; TokenInformation
0x18003b562  mov     rcx, rsi; TokenHandle
0x18003b565  lea     edx, [r9-2]; TokenInformationClass
0x18003b569  call    cs:__imp_SetTokenInformation
0x18003b56f  test    eax, eax
0x18003b571  jz      short loc_18003B578
0x18003b573  mov     ebx, r14d
0x18003b576  jmp     short loc_18003B58D
0x18003b578  call    cs:__imp_GetLastError
0x18003b57e  mov     ebx, eax
0x18003b580  test    eax, eax
0x18003b582  jle     short loc_18003B58D
0x18003b584  movzx   ebx, ax
0x18003b587  or      ebx, 80070000h
0x18003b58d  mov     rcx, [rbp+pSid]; pSid
0x18003b591  test    rcx, rcx
0x18003b594  jz      short loc_18003B59C
0x18003b596  call    cs:__imp_FreeSid
0x18003b59c  mov     rcx, [rbp+pAcl]; lpMem
0x18003b5a0  test    rcx, rcx
0x18003b5a3  jz      short loc_18003B5AA
0x18003b5a5  call    ServerFree
0x18003b5aa  mov     eax, ebx
0x18003b5ac  mov     rcx, [rbp+var_8]
0x18003b5b0  xor     rcx, rsp; StackCookie
0x18003b5b3  call    __security_check_cookie
0x18003b5b8  lea     r11, [rsp+80h+var_s0]
0x18003b5c0  mov     rbx, [r11+30h]
0x18003b5c4  mov     rsi, [r11+38h]
0x18003b5c8  mov     rsp, r11
0x18003b5cb  pop     r14
0x18003b5cd  pop     rdi
0x18003b5ce  pop     rbp
0x18003b5cf  retn
```
