# AddAccessAllowedACEToACL(_ACL * *,ulong,void *)

- ea: `0x1800fef9c`
- end: `0x1800ff0a7`
- name: `?AddAccessAllowedACEToACL@@YAKPEAPEAU_ACL@@KPEAX@Z`
- size: `267`
- prototype: `unsigned int(struct _ACL **, unsigned int, void *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18009617c`

## callees

- `0x1800b27e0`
- `0x1800fef9c`
- `0x1800ff0b0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ff079`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x1800ff079`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ff016`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800ff016`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff065`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ff065`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800feff3`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1800feff3`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800ff05b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x1800ff05b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ff004`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800ff004`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ff034`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800ff034`

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
0x1800fef9c  mov     [rsp+arg_18], rbx
0x1800fefa1  push    rbp
0x1800fefa2  push    rsi
0x1800fefa3  push    rdi
0x1800fefa4  push    r14
0x1800fefa6  push    r15
0x1800fefa8  sub     rsp, 40h
0x1800fefac  mov     rax, cs:__security_cookie
0x1800fefb3  xor     rax, rsp
0x1800fefb6  mov     [rsp+68h+var_38], rax
0x1800fefbb  xor     eax, eax
0x1800fefbd  mov     r14, r8
0x1800fefc0  mov     [rsp+68h+pAclInformation], rax
0x1800fefc5  mov     r15d, edx
0x1800fefc8  mov     [rsp+68h+var_40], eax
0x1800fefcc  mov     rsi, rcx
0x1800fefcf  test    rcx, rcx
0x1800fefd2  jnz     short loc_1800FEFDE
0x1800fefd4  mov     eax, 0A0h
0x1800fefd9  jmp     loc_1800FF081
0x1800fefde  mov     rdi, [rcx]
0x1800fefe1  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x1800fefe6  mov     r9d, 2; dwAclInformationClass
0x1800fefec  mov     rcx, rdi; pAcl
0x1800fefef  lea     r8d, [r9+0Ah]; nAclInformationLength
0x1800feff3  call    cs:__imp_GetAclInformation
0x1800feff9  test    eax, eax
0x1800feffb  jnz     short loc_1800FF001
0x1800feffd  xor     ebx, ebx
0x1800fefff  jmp     short loc_1800FF065
0x1800ff001  mov     rcx, r14; pSid
0x1800ff004  call    cs:__imp_GetLengthSid
0x1800ff00a  mov     ebp, dword ptr [rsp+68h+pAclInformation+4]
0x1800ff00e  add     ebp, 10h
0x1800ff011  add     ebp, eax
0x1800ff013  movsxd  rcx, ebp; Size
0x1800ff016  call    cs:__imp_malloc
0x1800ff01c  mov     rbx, rax
0x1800ff01f  test    rax, rax
0x1800ff022  jnz     short loc_1800FF029
0x1800ff024  lea     edi, [rax+0Eh]
0x1800ff027  jmp     short loc_1800FF07F
0x1800ff029  mov     r8d, 2; dwAclRevision
0x1800ff02f  mov     edx, ebp; nAclLength
0x1800ff031  mov     rcx, rbx; pAcl
0x1800ff034  call    cs:__imp_InitializeAcl
0x1800ff03a  test    eax, eax
0x1800ff03c  jz      short loc_1800FF065
0x1800ff03e  mov     rdx, rbx; PACL
0x1800ff041  mov     rcx, rdi; pAcl
0x1800ff044  call    ?CopyACL@@YAKPEAU_ACL@@0@Z; CopyACL(_ACL *,_ACL *)
0x1800ff049  mov     edi, eax
0x1800ff04b  test    eax, eax
0x1800ff04d  jnz     short loc_1800FF076
0x1800ff04f  mov     r9, r14; pSid
0x1800ff052  lea     edx, [rax+2]; dwAceRevision
0x1800ff055  mov     r8d, r15d; AccessMask
0x1800ff058  mov     rcx, rbx; pAcl
0x1800ff05b  call    cs:__imp_AddAccessAllowedAce
0x1800ff061  test    eax, eax
0x1800ff063  jnz     short loc_1800FF0A2
0x1800ff065  call    cs:__imp_GetLastError
0x1800ff06b  mov     edi, eax
0x1800ff06d  test    eax, eax
0x1800ff06f  jz      short loc_1800FF07F
0x1800ff071  test    rbx, rbx
0x1800ff074  jz      short loc_1800FF07F
0x1800ff076  mov     rcx, rbx; Block
0x1800ff079  call    cs:__imp_free
0x1800ff07f  mov     eax, edi
0x1800ff081  mov     rcx, [rsp+68h+var_38]
0x1800ff086  xor     rcx, rsp; StackCookie
0x1800ff089  call    __security_check_cookie
0x1800ff08e  mov     rbx, [rsp+68h+arg_18]
0x1800ff096  add     rsp, 40h
0x1800ff09a  pop     r15
0x1800ff09c  pop     r14
0x1800ff09e  pop     rdi
0x1800ff09f  pop     rsi
0x1800ff0a0  pop     rbp
0x1800ff0a1  retn
0x1800ff0a2  mov     [rsi], rbx
0x1800ff0a5  jmp     short loc_1800FF07F
```
