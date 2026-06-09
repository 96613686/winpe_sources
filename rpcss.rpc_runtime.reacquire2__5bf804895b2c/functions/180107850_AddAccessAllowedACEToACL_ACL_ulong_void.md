# AddAccessAllowedACEToACL(_ACL * *,ulong,void *)

- ea: `0x180107850`
- end: `0x180107986`
- name: `?AddAccessAllowedACEToACL@@YAKPEAPEAU_ACL@@KPEAX@Z`
- size: `310`
- prototype: `unsigned int(struct _ACL **, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009b67c`

## callees

- `0x1800b7ac0`
- `0x180107850`
- `0x18010798c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180107951`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180107951`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801078d6`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1801078d6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107937`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180107937`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801078a7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801078a7`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180107927`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x180107927`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801078be`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801078be`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801078fa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801078fa`

## pseudocode

```c
__int64 __fastcall AddAccessAllowedACEToACL(struct _ACL **a1, DWORD a2, void *a3)
{
  struct _ACL *v7; // rdi
  struct _ACL *v8; // rbx
  DWORD LengthSid; // eax
  signed int v10; // ebp
  struct _ACL *v11; // rax
  DWORD LastError; // edi
  __int64 pAclInformation; // [rsp+20h] [rbp-48h] BYREF
  int v14; // [rsp+28h] [rbp-40h]

  pAclInformation = 0;
  v14 = 0;
  if ( !a1 )
    return 160;
  v7 = *a1;
  if ( !GetAclInformation(*a1, &pAclInformation, 0xCu, AclSizeInformation) )
  {
    v8 = 0;
    goto LABEL_10;
  }
  LengthSid = GetLengthSid(a3);
  v10 = LengthSid + HIDWORD(pAclInformation) + 16;
  v11 = (struct _ACL *)malloc(v10);
  v8 = v11;
  if ( v11 )
  {
    if ( InitializeAcl(v11, v10, 2u) )
    {
      LastError = CopyACL(v7, v8);
      if ( LastError )
      {
LABEL_12:
        free(v8);
        return LastError;
      }
      if ( AddAccessAllowedAce(v8, 2u, a2, a3) )
      {
        *a1 = v8;
        return LastError;
      }
    }
LABEL_10:
    LastError = GetLastError();
    if ( !LastError || !v8 )
      return LastError;
    goto LABEL_12;
  }
  return 14;
}

```

## disassembly

```asm
0x180107850  mov     [rsp+arg_18], rbx
0x180107855  push    rbp
0x180107856  push    rsi
0x180107857  push    rdi
0x180107858  push    r14
0x18010785a  push    r15
0x18010785c  sub     rsp, 40h
0x180107860  mov     rax, cs:__security_cookie
0x180107867  xor     rax, rsp
0x18010786a  mov     [rsp+68h+var_38], rax
0x18010786f  xor     eax, eax
0x180107871  mov     r14, r8
0x180107874  mov     [rsp+68h+pAclInformation], rax
0x180107879  mov     r15d, edx
0x18010787c  mov     [rsp+68h+var_40], eax
0x180107880  mov     rsi, rcx
0x180107883  test    rcx, rcx
0x180107886  jnz     short loc_180107892
0x180107888  mov     eax, 0A0h
0x18010788d  jmp     loc_18010795F
0x180107892  mov     rdi, [rcx]
0x180107895  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x18010789a  mov     r9d, 2; dwAclInformationClass
0x1801078a0  mov     rcx, rdi; pAcl
0x1801078a3  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1801078a7  call    cs:__imp_GetAclInformation
0x1801078ae  nop     dword ptr [rax+rax+00h]
0x1801078b3  test    eax, eax
0x1801078b5  jnz     short loc_1801078BB
0x1801078b7  xor     ebx, ebx
0x1801078b9  jmp     short loc_180107937
0x1801078bb  mov     rcx, r14; pSid
0x1801078be  call    cs:__imp_GetLengthSid
0x1801078c5  nop     dword ptr [rax+rax+00h]
0x1801078ca  mov     ebp, dword ptr [rsp+68h+pAclInformation+4]
0x1801078ce  add     ebp, 10h
0x1801078d1  add     ebp, eax
0x1801078d3  movsxd  rcx, ebp; Size
0x1801078d6  call    cs:__imp_malloc
0x1801078dd  nop     dword ptr [rax+rax+00h]
0x1801078e2  mov     rbx, rax
0x1801078e5  test    rax, rax
0x1801078e8  jnz     short loc_1801078EF
0x1801078ea  lea     edi, [rax+0Eh]
0x1801078ed  jmp     short loc_18010795D
0x1801078ef  mov     r8d, 2; dwAclRevision
0x1801078f5  mov     edx, ebp; nAclLength
0x1801078f7  mov     rcx, rbx; pAcl
0x1801078fa  call    cs:__imp_InitializeAcl
0x180107901  nop     dword ptr [rax+rax+00h]
0x180107906  test    eax, eax
0x180107908  jz      short loc_180107937
0x18010790a  mov     rdx, rbx; PACL
0x18010790d  mov     rcx, rdi; pAcl
0x180107910  call    ?CopyACL@@YAKPEAU_ACL@@0@Z; CopyACL(_ACL *,_ACL *)
0x180107915  mov     edi, eax
0x180107917  test    eax, eax
0x180107919  jnz     short loc_18010794E
0x18010791b  mov     r9, r14; pSid
0x18010791e  lea     edx, [rax+2]; dwAceRevision
0x180107921  mov     r8d, r15d; AccessMask
0x180107924  mov     rcx, rbx; pAcl
0x180107927  call    cs:__imp_AddAccessAllowedAce
0x18010792e  nop     dword ptr [rax+rax+00h]
0x180107933  test    eax, eax
0x180107935  jnz     short loc_180107981
0x180107937  call    cs:__imp_GetLastError
0x18010793e  nop     dword ptr [rax+rax+00h]
0x180107943  mov     edi, eax
0x180107945  test    eax, eax
0x180107947  jz      short loc_18010795D
0x180107949  test    rbx, rbx
0x18010794c  jz      short loc_18010795D
0x18010794e  mov     rcx, rbx; Block
0x180107951  call    cs:__imp_free
0x180107958  nop     dword ptr [rax+rax+00h]
0x18010795d  mov     eax, edi
0x18010795f  mov     rcx, [rsp+68h+var_38]
0x180107964  xor     rcx, rsp; StackCookie
0x180107967  call    __security_check_cookie
0x18010796c  mov     rbx, [rsp+68h+arg_18]
0x180107974  add     rsp, 40h
0x180107978  pop     r15
0x18010797a  pop     r14
0x18010797c  pop     rdi
0x18010797d  pop     rsi
0x18010797e  pop     rbp
0x18010797f  retn
0x180107981  mov     [rsi], rbx
0x180107984  jmp     short loc_18010795D
```
