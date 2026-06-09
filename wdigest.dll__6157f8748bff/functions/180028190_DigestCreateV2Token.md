# DigestCreateV2Token

- ea: `0x180028190`
- end: `0x1800283d2`
- name: `DigestCreateV2Token`
- size: `578`
- prototype: `__int64 __usercall@<rax>(PLUID AuthenticationId@<rcx>, int, PHANDLE TokenHandle)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180028ff0`

## callees

- `0x180009770`
- `0x180011fec`
- `0x180012880`
- `0x1800185b8`
- `0x180027e2c`
- `0x180028190`

## import_xrefs

- `ntdll!NtCreateToken` at `0x180028330`
- `ntdll!NtCreateToken` at `0x180028330`

## pseudocode

```c
__int64 __fastcall DigestCreateV2Token(
        PLUID AuthenticationId,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        PHANDLE TokenHandle)
{
  struct _TOKEN_PRIVILEGES *TokenPrivileges; // rdi
  struct _TOKEN_DEFAULT_DACL *TokenDefaultDacl; // r14
  int TokenDacl; // eax
  unsigned int v11; // ebx
  PVOID *v12; // rcx
  __int64 v13; // rdx
  struct _TOKEN_GROUPS *TokenGroups; // [rsp+38h] [rbp-A1h]
  HLOCAL hMem; // [rsp+70h] [rbp-69h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+78h] [rbp-61h] BYREF
  _OWORD SecurityDescriptor[2]; // [rsp+A8h] [rbp-31h] BYREF
  __int64 v19; // [rsp+C8h] [rbp-11h]
  __int64 v20; // [rsp+D0h] [rbp-9h] BYREF
  int v21; // [rsp+D8h] [rbp-1h]
  __int128 v22; // [rsp+E0h] [rbp+7h] BYREF

  v20 = 0;
  v21 = 0;
  v22 = 0;
  hMem = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  v19 = 0;
  memset(SecurityDescriptor, 0, sizeof(SecurityDescriptor));
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 185, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids);
  TokenPrivileges = *(struct _TOKEN_PRIVILEGES **)(a3 + 40);
  TokenDefaultDacl = (struct _TOKEN_DEFAULT_DACL *)((a3 + 56) & -(__int64)(*(_QWORD *)(a3 + 56) != 0));
  if ( !TokenPrivileges )
  {
    TokenPrivileges = (struct _TOKEN_PRIVILEGES *)&v22;
    LODWORD(v22) = 0;
  }
  TokenDacl = DigestCreateTokenDacl(SecurityDescriptor, (struct _ACL **)&hMem);
  v11 = TokenDacl;
  if ( TokenDacl >= 0 )
  {
    ObjectAttributes.Length = 48;
    memset(&ObjectAttributes.RootDirectory, 0, 20);
    ObjectAttributes.SecurityDescriptor = SecurityDescriptor;
    ObjectAttributes.SecurityQualityOfService = &v20;
    TokenGroups = *(struct _TOKEN_GROUPS **)(a3 + 24);
    LOWORD(v21) = 1;
    v20 = 0x10000000CLL;
    TokenDacl = NtCreateToken(
                  TokenHandle,
                  0xF01FFu,
                  &ObjectAttributes,
                  TokenImpersonation,
                  AuthenticationId,
                  (PLARGE_INTEGER)a3,
                  (PTOKEN_USER)(a3 + 8),
                  TokenGroups,
                  TokenPrivileges,
                  0,
                  (PTOKEN_PRIMARY_GROUP)(a3 + 32),
                  TokenDefaultDacl,
                  &g_DigestSource);
    v11 = TokenDacl;
    if ( TokenDacl >= 0 )
      goto LABEL_15;
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 187;
      goto LABEL_10;
    }
  }
  else
  {
    v12 = (PVOID *)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v13 = 186;
LABEL_10:
      WPP_SF_d(v12[2], v13, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, (unsigned int)TokenDacl);
LABEL_15:
      v12 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  if ( hMem )
  {
    DigestFreeMemory(hMem);
    v12 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( v12 != &WPP_GLOBAL_Control && *((char *)v12 + 28) < 0 )
    WPP_SF_d(v12[2], 188, &WPP_57c72a8c831a31d68b40d535909494f1_Traceguids, v11);
  return v11;
}

```

## disassembly

```asm
0x180028190  mov     [rsp-8+arg_8], rbx
0x180028195  mov     [rsp-8+arg_18], rsi
0x18002819a  push    rbp
0x18002819b  push    rdi
0x18002819c  push    r12
0x18002819e  push    r14
0x1800281a0  push    r15
0x1800281a2  lea     rbp, [rsp-27h]
0x1800281a7  sub     rsp, 100h
0x1800281ae  mov     rax, cs:__security_cookie
0x1800281b5  xor     rax, rsp
0x1800281b8  mov     [rbp+47h+var_30], rax
0x1800281bc  mov     r12, [rbp+47h+TokenHandle]
0x1800281c0  xor     eax, eax
0x1800281c2  xorps   xmm0, xmm0
0x1800281c5  mov     [rbp+47h+var_50], rax
0x1800281c9  xorps   xmm1, xmm1
0x1800281cc  mov     [rbp+47h+var_48], eax
0x1800281cf  movups  [rbp+47h+var_40], xmm0
0x1800281d3  mov     [rbp+47h+hMem], rax
0x1800281d7  mov     rsi, r8
0x1800281da  movups  xmmword ptr [rbp+47h+ObjectAttributes.Length], xmm1
0x1800281de  mov     [rbp+47h+var_58], rax
0x1800281e2  mov     r15, rcx
0x1800281e5  movups  xmmword ptr [rbp+47h+ObjectAttributes.ObjectName], xmm1
0x1800281e9  movups  xmmword ptr [rbp+47h+ObjectAttributes.SecurityDescriptor], xmm1
0x1800281ed  movups  [rbp+47h+SecurityDescriptor], xmm0
0x1800281f1  movups  [rbp+47h+var_68], xmm0
0x1800281f5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800281fc  lea     rax, WPP_GLOBAL_Control
0x180028203  cmp     rcx, rax
0x180028206  jz      short loc_180028223
0x180028208  test    byte ptr [rcx+1Ch], 80h
0x18002820c  jz      short loc_180028223
0x18002820e  mov     rcx, [rcx+10h]
0x180028212  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x180028219  mov     edx, 0B9h
0x18002821e  call    WPP_SF_
0x180028223  mov     rdi, [rsi+28h]
0x180028227  lea     rcx, [rsi+38h]
0x18002822b  mov     rax, [rcx]
0x18002822e  neg     rax
0x180028231  sbb     r14, r14
0x180028234  and     r14, rcx
0x180028237  test    rdi, rdi
0x18002823a  jnz     short loc_180028247
0x18002823c  lea     rdi, [rbp+47h+var_40]
0x180028240  mov     dword ptr [rbp+47h+var_40], 0
0x180028247  lea     rdx, [rbp+47h+hMem]
0x18002824b  lea     rcx, [rbp+47h+SecurityDescriptor]; SecurityDescriptor
0x18002824f  call    DigestCreateTokenDacl
0x180028254  mov     ebx, eax
0x180028256  test    eax, eax
0x180028258  jns     short loc_180028298
0x18002825a  mov     rcx, cs:WPP_GLOBAL_Control
0x180028261  lea     rdi, WPP_GLOBAL_Control
0x180028268  cmp     rcx, rdi
0x18002826b  jz      loc_18002836D
0x180028271  test    byte ptr [rcx+1Ch], 1
0x180028275  jz      loc_18002836D
0x18002827b  mov     edx, 0BAh
0x180028280  mov     rcx, [rcx+10h]
0x180028284  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002828b  mov     r9d, eax
0x18002828e  call    WPP_SF_d
0x180028293  jmp     loc_180028366
0x180028298  lea     rdx, [rsi+8]
0x18002829c  mov     [rbp+47h+ObjectAttributes.Length], 30h ; '0'
0x1800282a3  lea     rax, [rbp+47h+SecurityDescriptor]
0x1800282a7  mov     [rbp+47h+ObjectAttributes.RootDirectory], 0
0x1800282af  mov     [rbp+47h+ObjectAttributes.SecurityDescriptor], rax
0x1800282b3  lea     rcx, g_DigestSource
0x1800282ba  mov     [rsp+120h+TokenSource], rcx; TokenSource
0x1800282bf  lea     rax, [rbp+47h+var_50]
0x1800282c3  mov     [rsp+120h+TokenDefaultDacl], r14; TokenDefaultDacl
0x1800282c8  lea     r8, [rbp+47h+ObjectAttributes]; ObjectAttributes
0x1800282cc  mov     [rbp+47h+ObjectAttributes.SecurityQualityOfService], rax
0x1800282d0  mov     r9d, 2; TokenType
0x1800282d6  lea     rax, [rsi+20h]
0x1800282da  mov     [rbp+47h+ObjectAttributes.Attributes], 0
0x1800282e1  mov     [rsp+120h+TokenPrimaryGroup], rax; TokenPrimaryGroup
0x1800282e6  mov     rcx, r12; TokenHandle
0x1800282e9  mov     rax, [rsi+18h]
0x1800282ed  mov     [rsp+120h+TokenOwner], 0; TokenOwner
0x1800282f6  mov     [rsp+120h+TokenPrivileges], rdi; TokenPrivileges
0x1800282fb  mov     [rsp+120h+TokenGroups], rax; TokenGroups
0x180028300  mov     [rsp+120h+TokenUser], rdx; TokenUser
0x180028305  mov     edx, 0F01FFh; DesiredAccess
0x18002830a  mov     [rsp+120h+ExpirationTime], rsi; ExpirationTime
0x18002830f  mov     [rsp+120h+AuthenticationId], r15; AuthenticationId
0x180028314  mov     [rbp+47h+ObjectAttributes.ObjectName], 0
0x18002831c  mov     dword ptr [rbp+47h+var_50+4], 1
0x180028323  mov     word ptr [rbp+47h+var_48], 1
0x180028329  mov     dword ptr [rbp+47h+var_50], 0Ch
0x180028330  call    cs:__imp_NtCreateToken
0x180028336  mov     ebx, eax
0x180028338  test    eax, eax
0x18002833a  jns     short loc_18002835F
0x18002833c  mov     rcx, cs:WPP_GLOBAL_Control
0x180028343  lea     rdi, WPP_GLOBAL_Control
0x18002834a  cmp     rcx, rdi
0x18002834d  jz      short loc_18002836D
0x18002834f  test    byte ptr [rcx+1Ch], 1
0x180028353  jz      short loc_18002836D
0x180028355  mov     edx, 0BBh
0x18002835a  jmp     loc_180028280
0x18002835f  lea     rdi, WPP_GLOBAL_Control
0x180028366  mov     rcx, cs:WPP_GLOBAL_Control
0x18002836d  mov     rax, [rbp+47h+hMem]
0x180028371  test    rax, rax
0x180028374  jz      short loc_180028385
0x180028376  mov     rcx, rax; hMem
0x180028379  call    DigestFreeMemory
0x18002837e  mov     rcx, cs:WPP_GLOBAL_Control
0x180028385  cmp     rcx, rdi
0x180028388  jz      short loc_1800283A8
0x18002838a  test    byte ptr [rcx+1Ch], 80h
0x18002838e  jz      short loc_1800283A8
0x180028390  mov     rcx, [rcx+10h]
0x180028394  lea     r8, WPP_57c72a8c831a31d68b40d535909494f1_Traceguids
0x18002839b  mov     edx, 0BCh
0x1800283a0  mov     r9d, ebx
0x1800283a3  call    WPP_SF_d
0x1800283a8  mov     eax, ebx
0x1800283aa  mov     rcx, [rbp+47h+var_30]
0x1800283ae  xor     rcx, rsp; StackCookie
0x1800283b1  call    __security_check_cookie
0x1800283b6  lea     r11, [rsp+120h+var_20]
0x1800283be  mov     rbx, [r11+38h]
0x1800283c2  mov     rsi, [r11+48h]
0x1800283c6  mov     rsp, r11
0x1800283c9  pop     r15
0x1800283cb  pop     r14
0x1800283cd  pop     r12
0x1800283cf  pop     rdi
0x1800283d0  pop     rbp
0x1800283d1  retn
```
