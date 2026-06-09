# CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)

- ea: `0x180073368`
- end: `0x1800734fe`
- name: `?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z`
- size: `406`
- prototype: `unsigned int __usercall@<eax>(ULONG cCountOfExplicitEntries@<ecx>, void **@<rdx>, enum _ACCESS_MODE@<r8d>, unsigned int@<r9d>, enum _ACCESS_MODE, unsigned int, struct _ACL **, void **)`
- caller_count: `8`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180070c30`
- `0x180071424`
- `0x180073504`
- `0x1800739f8`
- `0x1800754a4`
- `0x180075bb8`
- `0x180077d14`
- `0x18007a188`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x18000256c`
- `0x180073368`
- `0x180073ebc`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007348d`
- `KERNEL32!GetLastError` at `0x18007348d`
- `KERNEL32!LocalAlloc` at `0x18007347f`
- `KERNEL32!LocalAlloc` at `0x18007347f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18007349d`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18007349d`
- `ADVAPI32!SetEntriesInAclW` at `0x180073465`
- `ADVAPI32!SetEntriesInAclW` at `0x180073465`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800734b3`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x1800734b3`

## pseudocode

```c
__int64 __fastcall CreateACL(
        ULONG cCountOfExplicitEntries,
        void **a2,
        enum _ACCESS_MODE a3,
        int a4,
        enum _ACCESS_MODE a5,
        unsigned int a6,
        struct _ACL **NewAcl,
        void **a8)
{
  __int64 v10; // rbx
  char *v11; // rax
  unsigned __int64 v12; // rdx
  char *v13; // rdi
  DWORD LastError; // ebx
  unsigned int i; // edx
  __int64 v16; // rcx
  HLOCAL v17; // rax

  v10 = cCountOfExplicitEntries;
  if ( !cCountOfExplicitEntries || !a2 )
    return 87;
  *NewAcl = 0;
  *a8 = 0;
  v11 = (char *)operator new[](saturated_mul(cCountOfExplicitEntries, 0x30u));
  v13 = v11;
  if ( v11 )
  {
    memset_0(v11, 0, 48 * v10);
    *(_DWORD *)v13 = a4;
    *(_QWORD *)(v13 + 4) = 2;
    *((_DWORD *)v13 + 7) = 0;
    *((_DWORD *)v13 + 8) = 5;
    *((_QWORD *)v13 + 5) = *a2;
    for ( i = 1; i < (unsigned int)v10; ++i )
    {
      v16 = 6LL * i;
      *(_DWORD *)&v13[8 * v16] = a6;
      *(_QWORD *)&v13[8 * v16 + 4] = 2;
      *(_DWORD *)&v13[8 * v16 + 28] = 0;
      *(_DWORD *)&v13[8 * v16 + 32] = 2;
      *(_QWORD *)&v13[8 * v16 + 40] = a2[i];
    }
    LastError = SetEntriesInAclW(v10, (PEXPLICIT_ACCESS_W)v13, 0, NewAcl);
    if ( !LastError )
    {
      v17 = LocalAlloc(0x40u, 0x28u);
      *a8 = v17;
      if ( v17 && InitializeSecurityDescriptor(v17, 1u) && SetSecurityDescriptorDacl(*a8, 1, *NewAcl, 0) )
        LastError = 0;
      else
        LastError = GetLastError();
    }
  }
  else
  {
    LastError = 8;
  }
  operator delete(v13, v12);
  if ( LastError )
    FreeSecurityDescriptors(NewAcl, a8);
  return LastError;
}

```

## disassembly

```asm
0x180073368  push    rbx
0x18007336a  push    rsi
0x18007336b  push    rdi
0x18007336c  push    r12
0x18007336e  push    r13
0x180073370  push    r14
0x180073372  push    r15
0x180073374  sub     rsp, 30h
0x180073378  mov     r13d, r9d
0x18007337b  mov     r15, rdx
0x18007337e  mov     ebx, ecx
0x180073380  xor     eax, eax
0x180073382  test    ecx, ecx
0x180073384  jz      loc_1800734E9
0x18007338a  test    rdx, rdx
0x18007338d  jz      loc_1800734E9
0x180073393  mov     [rsp+68h+var_40], rax
0x180073398  mov     [rsp+68h+var_48], eax
0x18007339c  mov     r14, [rsp+68h+NewAcl]
0x1800733a4  mov     [r14], rax
0x1800733a7  mov     rsi, [rsp+68h+arg_38]
0x1800733af  mov     [rsi], rax
0x1800733b2  mov     eax, 30h ; '0'
0x1800733b7  mul     rbx
0x1800733ba  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x1800733c1  cmovb   rax, rcx
0x1800733c5  mov     rcx, rax; unsigned __int64
0x1800733c8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1800733cd  mov     rdi, rax
0x1800733d0  mov     [rsp+68h+var_40], rax
0x1800733d5  test    rax, rax
0x1800733d8  jnz     short loc_1800733E2
0x1800733da  lea     ebx, [rax+8]
0x1800733dd  jmp     loc_1800734BF
0x1800733e2  lea     r8, [rbx+rbx*2]
0x1800733e6  shl     r8, 4; Size
0x1800733ea  xor     edx, edx; Val
0x1800733ec  mov     rcx, rdi; void *
0x1800733ef  call    memset_0
0x1800733f4  mov     [rdi], r13d
0x1800733f7  mov     r9d, 2
0x1800733fd  mov     [rdi+4], r9
0x180073401  mov     dword ptr [rdi+1Ch], 0
0x180073408  mov     dword ptr [rdi+20h], 5
0x18007340f  mov     rax, [r15]
0x180073412  mov     [rdi+28h], rax
0x180073416  lea     r12d, [r9-1]
0x18007341a  mov     edx, r12d
0x18007341d  mov     r8d, [rsp+68h+arg_28]
0x180073425  mov     [rsp+68h+var_44], edx
0x180073429  cmp     edx, ebx
0x18007342b  jnb     short loc_18007345A
0x18007342d  mov     eax, edx
0x18007342f  lea     rcx, [rax+rax*2]
0x180073433  add     rcx, rcx
0x180073436  mov     [rdi+rcx*8], r8d
0x18007343a  mov     [rdi+rcx*8+4], r9
0x18007343f  mov     dword ptr [rdi+rcx*8+1Ch], 0
0x180073447  mov     [rdi+rcx*8+20h], r9d
0x18007344c  mov     rax, [r15+rax*8]
0x180073450  mov     [rdi+rcx*8+28h], rax
0x180073455  add     edx, r12d
0x180073458  jmp     short loc_180073425
0x18007345a  mov     r9, r14; NewAcl
0x18007345d  xor     r8d, r8d; OldAcl
0x180073460  mov     rdx, rdi; pListOfExplicitEntries
0x180073463  mov     ecx, ebx; cCountOfExplicitEntries
0x180073465  call    cs:__imp_SetEntriesInAclW
0x18007346b  mov     ebx, eax
0x18007346d  test    eax, eax
0x18007346f  jz      short loc_180073477
0x180073471  mov     [rsp+68h+var_48], eax
0x180073475  jmp     short loc_1800734C3
0x180073477  mov     edx, 28h ; '('; uBytes
0x18007347c  lea     ecx, [rdx+18h]; uFlags
0x18007347f  call    cs:__imp_LocalAlloc
0x180073485  mov     [rsi], rax
0x180073488  test    rax, rax
0x18007348b  jnz     short loc_180073497
0x18007348d  call    cs:__imp_GetLastError
0x180073493  mov     ebx, eax
0x180073495  jmp     short loc_180073471
0x180073497  mov     edx, r12d; dwRevision
0x18007349a  mov     rcx, rax; pSecurityDescriptor
0x18007349d  call    cs:__imp_InitializeSecurityDescriptor
0x1800734a3  test    eax, eax
0x1800734a5  jz      short loc_18007348D
0x1800734a7  xor     r9d, r9d; bDaclDefaulted
0x1800734aa  mov     r8, [r14]; pDacl
0x1800734ad  mov     edx, r12d; bDaclPresent
0x1800734b0  mov     rcx, [rsi]; pSecurityDescriptor
0x1800734b3  call    cs:__imp_SetSecurityDescriptorDacl
0x1800734b9  test    eax, eax
0x1800734bb  jz      short loc_18007348D
0x1800734bd  xor     ebx, ebx
0x1800734bf  mov     [rsp+68h+var_48], ebx
0x1800734c3  mov     rcx, rdi; void *
0x1800734c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800734cb  test    ebx, ebx
0x1800734cd  jz      short loc_1800734DA
0x1800734cf  mov     rdx, rsi; void **
0x1800734d2  mov     rcx, r14; struct _ACL **
0x1800734d5  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x1800734da  jmp     short loc_1800734E5
0x1800734dc  mov     ebx, 0C0000005h
0x1800734e1  mov     [rsp+68h+var_48], ebx
0x1800734e5  mov     eax, ebx
0x1800734e7  jmp     short loc_1800734EE
0x1800734e9  mov     eax, 57h ; 'W'
0x1800734ee  add     rsp, 30h
0x1800734f2  pop     r15
0x1800734f4  pop     r14
0x1800734f6  pop     r13
0x1800734f8  pop     r12
0x1800734fa  pop     rdi
0x1800734fb  pop     rsi
0x1800734fc  pop     rbx
0x1800734fd  retn
0x1800b511b  push    rbp
0x1800b511d  sub     rsp, 20h
0x1800b5121  mov     rbp, rdx
0x1800b5124  mov     rcx, [rbp+28h]; void *
0x1800b5128  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800b512d  cmp     dword ptr [rbp+20h], 0
0x1800b5131  jz      short loc_1800B5147
0x1800b5133  mov     rdx, [rbp+0A8h]; void **
0x1800b513a  mov     rcx, [rbp+0A0h]; struct _ACL **
0x1800b5141  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x1800b5146  nop
0x1800b5147  add     rsp, 20h
0x1800b514b  pop     rbp
0x1800b514c  retn
0x1800b514e  push    rbp
0x1800b5150  sub     rsp, 20h
0x1800b5154  mov     rbp, rdx
0x1800b5157  mov     rax, [rcx]
0x1800b515a  xor     ecx, ecx
0x1800b515c  cmp     dword ptr [rax], 0C0000005h
0x1800b5162  setz    cl
0x1800b5165  mov     eax, ecx
0x1800b5167  add     rsp, 20h
0x1800b516b  pop     rbp
0x1800b516c  retn
```
