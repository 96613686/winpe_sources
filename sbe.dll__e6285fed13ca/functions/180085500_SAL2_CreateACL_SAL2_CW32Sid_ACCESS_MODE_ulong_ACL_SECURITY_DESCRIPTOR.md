# SAL2::CreateACL(SAL2::CW32Sid *,_ACCESS_MODE,ulong,_ACL * *,_SECURITY_DESCRIPTOR * *)

- ea: `0x180085500`
- end: `0x180085677`
- name: `?CreateACL@SAL2@@YAKPEAVCW32Sid@1@W4_ACCESS_MODE@@KPEAPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `375`
- prototype: `unsigned int(SAL2 *__hidden this, struct SAL2::CW32Sid *, enum _ACCESS_MODE, unsigned int, struct _ACL **, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180080b28`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x18000256c`
- `0x180060e40`
- `0x180085500`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18008565b`
- `KERNEL32!GetLastError` at `0x18008565b`
- `KERNEL32!LocalAlloc` at `0x180085627`
- `KERNEL32!LocalAlloc` at `0x180085627`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18008563b`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x18008563b`
- `ADVAPI32!SetEntriesInAclW` at `0x180085611`
- `ADVAPI32!SetEntriesInAclW` at `0x180085611`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180085651`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180085651`

## pseudocode

```c
__int64 __fastcall SAL2::CreateACL(
        SAL2 *this,
        struct SAL2::CW32Sid *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        SBECoreUtil **a4,
        struct _ACL **a5)
{
  int v5; // edx
  DWORD v8; // r12d
  __int64 v9; // rbx
  int v10; // edx
  int v11; // ecx
  struct _EXPLICIT_ACCESS_W *v12; // rdi
  DWORD LastError; // ebx
  unsigned __int64 v14; // rdx
  struct _EXPLICIT_ACCESS_W *v16; // rax
  unsigned int v17; // r9d
  __int64 v18; // rcx
  __int64 v19; // r8
  WCHAR *v20; // rax
  struct _ACL *v21; // rax

  v5 = *((_DWORD *)this + 6);
  *a4 = 0;
  v8 = (unsigned int)a3;
  v9 = (unsigned int)(v5 - 1);
  if ( !v5 )
    v9 = 0;
  *a5 = 0;
  v10 = *((_DWORD *)this + 6);
  v11 = v10 - 1;
  if ( !v10 )
    v11 = 0;
  if ( !v11 )
  {
    v12 = 0;
    LastError = 87;
LABEL_7:
    SBECoreUtil::FreeSecurityDescriptors(*a4, *a5, a3);
    *a4 = 0;
    *a5 = 0;
    goto LABEL_8;
  }
  v16 = (struct _EXPLICIT_ACCESS_W *)operator new[](saturated_mul((unsigned int)v9, 0x30u));
  v12 = v16;
  if ( !v16 )
  {
    LastError = 8;
    goto LABEL_7;
  }
  memset_0(v16, 0, 48 * v9);
  v17 = 0;
  if ( (_DWORD)v9 )
  {
    v18 = 0;
    do
    {
      v19 = v18;
      v12[v19].grfAccessPermissions = v8;
      *(_QWORD *)&v12[v19].grfAccessMode = 2;
      v12[v19].Trustee.TrusteeForm = TRUSTEE_IS_SID;
      v12[v19].Trustee.TrusteeType = TRUSTEE_IS_GROUP;
      ++v17;
      v20 = *(WCHAR **)(((*((_QWORD *)this + 2) + 8LL) & -(__int64)(*((_QWORD *)this + 2) != 0)) + 8 * v18++);
      v12[v19].Trustee.ptstrName = v20;
    }
    while ( v17 < (unsigned int)v9 );
  }
  LastError = SetEntriesInAclW(v9, v12, 0, (PACL *)a4);
  if ( LastError )
    goto LABEL_7;
  v21 = (struct _ACL *)LocalAlloc(0x40u, 0x28u);
  *a5 = v21;
  if ( v21 && InitializeSecurityDescriptor(v21, 1u) && SetSecurityDescriptorDacl(*a5, 1, (PACL)*a4, 0) )
  {
    LastError = 0;
    goto LABEL_8;
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_7;
LABEL_8:
  operator delete(v12, v14);
  return LastError;
}

```

## disassembly

```asm
0x180085500  push    rbx
0x180085502  push    rbp
0x180085503  push    rsi
0x180085504  push    rdi
0x180085505  push    r12
0x180085507  push    r14
0x180085509  push    r15
0x18008550b  sub     rsp, 20h
0x18008550f  mov     edx, [rcx+18h]
0x180085512  xor     eax, eax
0x180085514  mov     rsi, [rsp+58h+arg_20]
0x18008551c  test    edx, edx
0x18008551e  mov     [r9], rax
0x180085521  mov     rbp, rcx
0x180085524  mov     r14, r9
0x180085527  mov     r12d, r8d
0x18008552a  lea     ebx, [rdx-1]
0x18008552d  cmovz   ebx, eax
0x180085530  mov     [rsi], rax
0x180085533  mov     edx, [rcx+18h]
0x180085536  test    edx, edx
0x180085538  lea     ecx, [rdx-1]
0x18008553b  cmovz   ecx, eax
0x18008553e  test    ecx, ecx
0x180085540  jnz     short loc_180085579
0x180085542  xor     edi, edi
0x180085544  lea     ebx, [rax+57h]
0x180085547  mov     rdx, [rsi]; struct _ACL *
0x18008554a  mov     rcx, [r14]; this
0x18008554d  call    ?FreeSecurityDescriptors@SBECoreUtil@@YAXPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; SBECoreUtil::FreeSecurityDescriptors(_ACL *,_SECURITY_DESCRIPTOR *)
0x180085552  mov     qword ptr [r14], 0
0x180085559  mov     qword ptr [rsi], 0
0x180085560  mov     rcx, rdi; void *
0x180085563  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180085568  mov     eax, ebx
0x18008556a  add     rsp, 20h
0x18008556e  pop     r15
0x180085570  pop     r14
0x180085572  pop     r12
0x180085574  pop     rdi
0x180085575  pop     rsi
0x180085576  pop     rbp
0x180085577  pop     rbx
0x180085578  retn
0x180085579  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180085580  mov     r15d, ebx
0x180085583  mov     eax, 30h ; '0'
0x180085588  mul     r15
0x18008558b  cmovb   rax, rcx
0x18008558f  mov     rcx, rax; unsigned __int64
0x180085592  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180085597  mov     rdi, rax
0x18008559a  test    rax, rax
0x18008559d  jnz     short loc_1800855A4
0x18008559f  lea     ebx, [rax+8]
0x1800855a2  jmp     short loc_180085547
0x1800855a4  lea     r8, [rbx+rbx*2]
0x1800855a8  xor     edx, edx; Val
0x1800855aa  shl     r8, 4; Size
0x1800855ae  mov     rcx, rdi; void *
0x1800855b1  call    memset_0
0x1800855b6  xor     r9d, r9d
0x1800855b9  test    ebx, ebx
0x1800855bb  jz      short loc_180085606
0x1800855bd  xor     ecx, ecx
0x1800855bf  lea     r10d, [r9+2]
0x1800855c3  lea     r8, [rcx+rcx*2]
0x1800855c7  add     r8, r8
0x1800855ca  mov     [rdi+r8*8], r12d
0x1800855ce  mov     [rdi+r8*8+4], r10
0x1800855d3  mov     dword ptr [rdi+r8*8+1Ch], 0
0x1800855dc  mov     [rdi+r8*8+20h], r10d
0x1800855e1  mov     rax, [rbp+10h]
0x1800855e5  lea     rdx, [rax+8]
0x1800855e9  neg     rax
0x1800855ec  sbb     rax, rax
0x1800855ef  inc     r9d
0x1800855f2  and     rax, rdx
0x1800855f5  mov     rax, [rax+rcx*8]
0x1800855f9  inc     rcx
0x1800855fc  mov     [rdi+r8*8+28h], rax
0x180085601  cmp     r9d, ebx
0x180085604  jb      short loc_1800855C3
0x180085606  mov     r9, r14; NewAcl
0x180085609  xor     r8d, r8d; OldAcl
0x18008560c  mov     rdx, rdi; pListOfExplicitEntries
0x18008560f  mov     ecx, ebx; cCountOfExplicitEntries
0x180085611  call    cs:__imp_SetEntriesInAclW
0x180085617  mov     ebx, eax
0x180085619  test    eax, eax
0x18008561b  jnz     loc_180085547
0x180085621  lea     edx, [rax+28h]; uBytes
0x180085624  lea     ecx, [rax+40h]; uFlags
0x180085627  call    cs:__imp_LocalAlloc
0x18008562d  mov     [rsi], rax
0x180085630  test    rax, rax
0x180085633  jz      short loc_18008565B
0x180085635  lea     edx, [rbx+1]; dwRevision
0x180085638  mov     rcx, rax; pSecurityDescriptor
0x18008563b  call    cs:__imp_InitializeSecurityDescriptor
0x180085641  test    eax, eax
0x180085643  jz      short loc_18008565B
0x180085645  mov     r8, [r14]; pDacl
0x180085648  lea     edx, [rbx+1]; bDaclPresent
0x18008564b  mov     rcx, [rsi]; pSecurityDescriptor
0x18008564e  xor     r9d, r9d; bDaclDefaulted
0x180085651  call    cs:__imp_SetSecurityDescriptorDacl
0x180085657  test    eax, eax
0x180085659  jnz     short loc_180085670
0x18008565b  call    cs:__imp_GetLastError
0x180085661  mov     ebx, eax
0x180085663  test    eax, eax
0x180085665  jz      loc_180085560
0x18008566b  jmp     loc_180085547
0x180085670  xor     ebx, ebx
0x180085672  jmp     loc_180085560
```
