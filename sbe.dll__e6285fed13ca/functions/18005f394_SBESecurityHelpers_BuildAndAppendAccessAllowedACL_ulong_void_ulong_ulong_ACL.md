# SBESecurityHelpers::BuildAndAppendAccessAllowedACL(ulong,void * *,ulong,ulong,_ACL * *)

- ea: `0x18005f394`
- end: `0x18005f460`
- name: `?BuildAndAppendAccessAllowedACL@SBESecurityHelpers@@SAKKPEAPEAXKKPEAPEAU_ACL@@@Z`
- size: `204`
- prototype: `unsigned int __fastcall(unsigned int, void **, unsigned int, unsigned int, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055d7c`

## callees

- `0x18005f394`
- `0x18005f95c`
- `0x18005fa18`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18005f447`
- `KERNEL32!GetLastError` at `0x18005f447`
- `ADVAPI32!GetLengthSid` at `0x18005f3d7`
- `ADVAPI32!GetLengthSid` at `0x18005f3d7`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18005f439`
- `ADVAPI32!AddAccessAllowedAceEx` at `0x18005f439`

## pseudocode

```c
__int64 __fastcall SBESecurityHelpers::BuildAndAppendAccessAllowedACL(
        unsigned int a1,
        void **a2,
        __int64 a3,
        __int64 a4,
        struct _ACL **a5)
{
  unsigned int v7; // ebx
  unsigned __int16 v8; // di
  unsigned int v9; // edx
  unsigned int i; // edi

  v7 = 0;
  if ( a1 )
  {
    v8 = 0;
    do
    {
      if ( !(unsigned int)SBESecurityHelpers::IsAccessAllowedACEPresent(*a5, (unsigned int)a2, a2[v7]) )
        v8 += GetLengthSid(a2[v7]) + 8;
      ++v7;
    }
    while ( v7 < a1 );
    if ( v8 )
    {
      v7 = SBESecurityHelpers::MaybeGrowACL(v8, a5);
      if ( !v7 )
      {
        for ( i = 0; i < a1; ++i )
        {
          if ( !(unsigned int)SBESecurityHelpers::IsAccessAllowedACEPresent(*a5, v9, a2[i])
            && !AddAccessAllowedAceEx(*a5, 4u, 1u, 0xC0000040, a2[i]) )
          {
            return GetLastError();
          }
        }
      }
    }
    else
    {
      return 0;
    }
  }
  return v7;
}

```

## disassembly

```asm
0x18005f394  push    rbx
0x18005f396  push    rbp
0x18005f397  push    rsi
0x18005f398  push    rdi
0x18005f399  push    r12
0x18005f39b  push    r14
0x18005f39d  push    r15
0x18005f39f  sub     rsp, 30h
0x18005f3a3  xor     r12d, r12d
0x18005f3a6  mov     r14, rdx
0x18005f3a9  mov     esi, ecx
0x18005f3ab  mov     ebx, r12d
0x18005f3ae  test    ecx, ecx
0x18005f3b0  jz      loc_18005F44F
0x18005f3b6  mov     r15, [rsp+68h+arg_20]
0x18005f3be  mov     edi, r12d
0x18005f3c1  mov     rcx, [r15]; pAcl
0x18005f3c4  mov     ebp, ebx
0x18005f3c6  mov     r8, [r14+rbp*8]; void *
0x18005f3ca  call    ?IsAccessAllowedACEPresent@SBESecurityHelpers@@SAHPEAU_ACL@@KPEAX@Z; SBESecurityHelpers::IsAccessAllowedACEPresent(_ACL *,ulong,void *)
0x18005f3cf  test    eax, eax
0x18005f3d1  jnz     short loc_18005F3E4
0x18005f3d3  mov     rcx, [r14+rbp*8]; pSid
0x18005f3d7  call    cs:__imp_GetLengthSid
0x18005f3dd  add     ax, 8
0x18005f3e1  add     di, ax
0x18005f3e4  inc     ebx
0x18005f3e6  cmp     ebx, esi
0x18005f3e8  jb      short loc_18005F3C1
0x18005f3ea  test    di, di
0x18005f3ed  jnz     short loc_18005F3F4
0x18005f3ef  mov     ebx, r12d
0x18005f3f2  jmp     short loc_18005F44F
0x18005f3f4  mov     rdx, r15; struct _ACL **
0x18005f3f7  movzx   ecx, di; unsigned __int16
0x18005f3fa  call    ?MaybeGrowACL@SBESecurityHelpers@@SAKGPEAPEAU_ACL@@@Z; SBESecurityHelpers::MaybeGrowACL(ushort,_ACL * *)
0x18005f3ff  mov     ebx, eax
0x18005f401  test    eax, eax
0x18005f403  jnz     short loc_18005F44F
0x18005f405  mov     edi, r12d
0x18005f408  cmp     edi, esi
0x18005f40a  jnb     short loc_18005F44F
0x18005f40c  mov     rcx, [r15]; pAcl
0x18005f40f  mov     ebp, edi
0x18005f411  mov     r8, [r14+rbp*8]; void *
0x18005f415  call    ?IsAccessAllowedACEPresent@SBESecurityHelpers@@SAHPEAU_ACL@@KPEAX@Z; SBESecurityHelpers::IsAccessAllowedACEPresent(_ACL *,ulong,void *)
0x18005f41a  test    eax, eax
0x18005f41c  jnz     short loc_18005F443
0x18005f41e  mov     rax, [r14+rbp*8]
0x18005f422  mov     edx, 4; dwAceRevision
0x18005f427  mov     rcx, [r15]; pAcl
0x18005f42a  mov     r9d, 0C0000040h; AccessMask
0x18005f430  mov     [rsp+68h+pSid], rax; pSid
0x18005f435  lea     r8d, [rdx-3]; AceFlags
0x18005f439  call    cs:__imp_AddAccessAllowedAceEx
0x18005f43f  test    eax, eax
0x18005f441  jz      short loc_18005F447
0x18005f443  inc     edi
0x18005f445  jmp     short loc_18005F408
0x18005f447  call    cs:__imp_GetLastError
0x18005f44d  mov     ebx, eax
0x18005f44f  mov     eax, ebx
0x18005f451  add     rsp, 30h
0x18005f455  pop     r15
0x18005f457  pop     r14
0x18005f459  pop     r12
0x18005f45b  pop     rdi
0x18005f45c  pop     rsi
0x18005f45d  pop     rbp
0x18005f45e  pop     rbx
0x18005f45f  retn
```
