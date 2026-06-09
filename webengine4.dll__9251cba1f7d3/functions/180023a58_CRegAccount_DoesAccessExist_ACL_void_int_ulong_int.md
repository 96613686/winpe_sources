# CRegAccount::DoesAccessExist(_ACL *,void * *,int,ulong,int *)

- ea: `0x180023a58`
- end: `0x180023c22`
- name: `?DoesAccessExist@CRegAccount@@CAJPEAU_ACL@@PEAPEAXHKPEAH@Z`
- size: `458`
- prototype: `__int64 __usercall@<rax>(PACL pAcl@<rcx>, void **@<rdx>, int@<r8d>, unsigned int@<r9d>, int *)`
- caller_count: `5`
- callee_count: `4`
- tags: `authz_impersonation`

## callers

- `0x180021730`
- `0x180021ca8`
- `0x180024d70`
- `0x1800251a8`
- `0x180026634`

## callees

- `0x180023740`
- `0x180023a58`
- `0x18004d030`
- `0x18004d350`

## import_xrefs

- `ADVAPI32!EqualSid` at `0x180023b93`
- `ADVAPI32!EqualSid` at `0x180023bb7`
- `ADVAPI32!EqualSid` at `0x180023b93`
- `ADVAPI32!EqualSid` at `0x180023bb7`
- `ADVAPI32!GetAce` at `0x180023b4c`
- `ADVAPI32!GetAce` at `0x180023b4c`
- `ADVAPI32!GetAclInformation` at `0x180023ad9`
- `ADVAPI32!GetAclInformation` at `0x180023ad9`

## pseudocode

```c
__int64 __fastcall CRegAccount::DoesAccessExist(PACL pAcl, void **a2, int a3, int a4, int *a5)
{
  unsigned int v5; // ebx
  __int64 v6; // r13
  int v7; // r15d
  int v9; // esi
  __int64 i; // rcx
  int v11; // eax
  DWORD v12; // r14d
  unsigned int v13; // ecx
  char *v14; // r15
  __int64 v15; // rdi
  int *v16; // rdi
  __int64 j; // rcx
  LPVOID pAce; // [rsp+28h] [rbp-70h] BYREF
  PACL pAcla; // [rsp+30h] [rbp-68h]
  void **v22; // [rsp+38h] [rbp-60h]
  __int64 pAclInformation; // [rsp+40h] [rbp-58h] BYREF
  int v24; // [rsp+48h] [rbp-50h]

  v5 = 0;
  v6 = a3;
  v7 = a4;
  v22 = a2;
  pAcla = pAcl;
  v9 = a3;
  if ( pAcl && a2 && a4 )
  {
    pAclInformation = 0;
    v24 = 0;
    if ( GetAclInformation(pAcl, &pAclInformation, 0xCu, AclSizeInformation) )
    {
      if ( !g_pSidWorld )
        CreateWorldSid();
      if ( (int)v6 > 0 )
      {
        for ( i = 0; i < v6; ++i )
        {
          v11 = v9 - 1;
          if ( a2[i] )
            v11 = v9;
          v9 = v11;
          a5[i] = a2[i] == 0;
        }
      }
      if ( v9 < 1 )
      {
LABEL_30:
        if ( (int)v6 > 0 )
        {
          v16 = a5;
          for ( j = v6; j; --j )
            *v16++ = 1;
        }
      }
      else
      {
        v12 = pAclInformation;
        while ( (--v12 & 0x80000000) == 0 )
        {
          pAce = 0;
          if ( GetAce(pAcla, v12, &pAce) && pAce && !*(_BYTE *)pAce )
          {
            v13 = *((_DWORD *)pAce + 1) | 0xE0000000;
            if ( (*((_DWORD *)pAce + 1) & 0x10000000) == 0 )
              v13 = *((_DWORD *)pAce + 1);
            if ( (v7 & v13) == v7 )
            {
              v14 = (char *)pAce + 8;
              if ( g_pSidWorld && EqualSid(v14, g_pSidWorld) )
                goto LABEL_30;
              v15 = 0;
              if ( (int)v6 > 0 )
              {
                do
                {
                  if ( !a5[v15] )
                  {
                    if ( EqualSid(v22[v15], v14) )
                    {
                      --v9;
                      a5[v15] = 1;
                      if ( v9 < 1 )
                        goto LABEL_30;
                    }
                  }
                }
                while ( ++v15 < v6 );
              }
              v7 = a4;
            }
          }
        }
      }
    }
    else
    {
      return (unsigned int)GetLastWin32Error();
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return v5;
}

```

## disassembly

```asm
0x180023a58  mov     [rsp+arg_10], rbx
0x180023a5d  push    rbp
0x180023a5e  push    rsi
0x180023a5f  push    rdi
0x180023a60  push    r12
0x180023a62  push    r13
0x180023a64  push    r14
0x180023a66  push    r15
0x180023a68  sub     rsp, 60h
0x180023a6c  mov     rax, cs:__security_cookie
0x180023a73  xor     rax, rsp
0x180023a76  mov     [rsp+98h+var_48], rax
0x180023a7b  mov     r12, [rsp+98h+arg_20]
0x180023a83  xor     ebx, ebx
0x180023a85  movsxd  r13, r8d
0x180023a88  mov     r15d, r9d
0x180023a8b  mov     [rsp+98h+var_78], r9d
0x180023a90  mov     rdi, rdx
0x180023a93  mov     [rsp+98h+var_60], rdx
0x180023a98  mov     rax, rcx
0x180023a9b  mov     [rsp+98h+pAcl], rcx
0x180023aa0  mov     esi, r13d
0x180023aa3  test    rcx, rcx
0x180023aa6  jz      loc_180023BF6
0x180023aac  test    rdx, rdx
0x180023aaf  jz      loc_180023BF6
0x180023ab5  test    r9d, r9d
0x180023ab8  jz      loc_180023BF6
0x180023abe  xor     ecx, ecx
0x180023ac0  lea     r9d, [rbx+2]; dwAclInformationClass
0x180023ac4  mov     [rsp+98h+pAclInformation], rcx
0x180023ac9  lea     r8d, [rbx+0Ch]; nAclInformationLength
0x180023acd  mov     [rsp+98h+var_50], ecx
0x180023ad1  lea     rdx, [rsp+98h+pAclInformation]; pAclInformation
0x180023ad6  mov     rcx, rax; pAcl
0x180023ad9  call    cs:__imp_GetAclInformation
0x180023adf  test    eax, eax
0x180023ae1  jnz     short loc_180023AEF
0x180023ae3  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x180023ae8  mov     ebx, eax
0x180023aea  jmp     loc_180023BFB
0x180023aef  cmp     cs:?g_pSidWorld@@3PEAXEA, rbx; void * g_pSidWorld
0x180023af6  jnz     short loc_180023AFD
0x180023af8  call    ?CreateWorldSid@@YAXXZ; CreateWorldSid(void)
0x180023afd  test    r13d, r13d
0x180023b00  jle     short loc_180023B22
0x180023b02  mov     rcx, rbx
0x180023b05  cmp     [rdi+rcx*8], rbx
0x180023b09  lea     eax, [rsi-1]
0x180023b0c  cmovnz  eax, esi
0x180023b0f  mov     esi, eax
0x180023b11  mov     eax, ebx
0x180023b13  setz    al
0x180023b16  mov     [r12+rcx*4], eax
0x180023b1a  inc     rcx
0x180023b1d  cmp     rcx, r13
0x180023b20  jl      short loc_180023B05
0x180023b22  cmp     esi, 1
0x180023b25  jl      loc_180023BE2
0x180023b2b  mov     r14d, dword ptr [rsp+98h+pAclInformation]
0x180023b30  sub     r14d, 1
0x180023b34  js      loc_180023BFB
0x180023b3a  mov     rcx, [rsp+98h+pAcl]; pAcl
0x180023b3f  lea     r8, [rsp+98h+pAce]; pAce
0x180023b44  mov     edx, r14d; dwAceIndex
0x180023b47  mov     [rsp+98h+pAce], rbx
0x180023b4c  call    cs:__imp_GetAce
0x180023b52  test    eax, eax
0x180023b54  jz      short loc_180023B30
0x180023b56  mov     rdx, [rsp+98h+pAce]
0x180023b5b  test    rdx, rdx
0x180023b5e  jz      short loc_180023B30
0x180023b60  cmp     [rdx], bl
0x180023b62  jnz     short loc_180023B30
0x180023b64  mov     eax, [rdx+4]
0x180023b67  mov     ecx, eax
0x180023b69  or      ecx, 0E0000000h
0x180023b6f  and     eax, 10000000h
0x180023b74  cmovz   ecx, [rdx+4]
0x180023b78  and     ecx, r15d
0x180023b7b  cmp     ecx, r15d
0x180023b7e  jnz     short loc_180023B30
0x180023b80  lea     r15, [rdx+8]
0x180023b84  mov     rdx, cs:?g_pSidWorld@@3PEAXEA; pSid2
0x180023b8b  test    rdx, rdx
0x180023b8e  jz      short loc_180023B9D
0x180023b90  mov     rcx, r15; pSid1
0x180023b93  call    cs:__imp_EqualSid
0x180023b99  test    eax, eax
0x180023b9b  jnz     short loc_180023BE2
0x180023b9d  mov     rdi, rbx
0x180023ba0  test    r13d, r13d
0x180023ba3  jle     short loc_180023BD8
0x180023ba5  cmp     [r12+rdi*4], ebx
0x180023ba9  jnz     short loc_180023BD0
0x180023bab  mov     rax, [rsp+98h+var_60]
0x180023bb0  mov     rdx, r15; pSid2
0x180023bb3  mov     rcx, [rax+rdi*8]; pSid1
0x180023bb7  call    cs:__imp_EqualSid
0x180023bbd  test    eax, eax
0x180023bbf  jz      short loc_180023BD0
0x180023bc1  dec     esi
0x180023bc3  mov     dword ptr [r12+rdi*4], 1
0x180023bcb  cmp     esi, 1
0x180023bce  jl      short loc_180023BE2
0x180023bd0  inc     rdi
0x180023bd3  cmp     rdi, r13
0x180023bd6  jl      short loc_180023BA5
0x180023bd8  mov     r15d, [rsp+98h+var_78]
0x180023bdd  jmp     loc_180023B30
0x180023be2  test    r13d, r13d
0x180023be5  jle     short loc_180023BFB
0x180023be7  mov     rdi, r12
0x180023bea  mov     eax, 1
0x180023bef  mov     rcx, r13
0x180023bf2  rep stosd
0x180023bf4  jmp     short loc_180023BFB
0x180023bf6  mov     ebx, 80070057h
0x180023bfb  mov     eax, ebx
0x180023bfd  mov     rcx, [rsp+98h+var_48]
0x180023c02  xor     rcx, rsp; StackCookie
0x180023c05  call    __security_check_cookie
0x180023c0a  mov     rbx, [rsp+98h+arg_10]
0x180023c12  add     rsp, 60h
0x180023c16  pop     r15
0x180023c18  pop     r14
0x180023c1a  pop     r13
0x180023c1c  pop     r12
0x180023c1e  pop     rdi
0x180023c1f  pop     rsi
0x180023c20  pop     rbp
0x180023c21  retn
```
