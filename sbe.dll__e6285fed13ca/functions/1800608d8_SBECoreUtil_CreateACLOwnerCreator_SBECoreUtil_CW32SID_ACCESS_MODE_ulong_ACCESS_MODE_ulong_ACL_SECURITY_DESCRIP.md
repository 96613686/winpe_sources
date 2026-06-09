# SBECoreUtil::CreateACLOwnerCreator(SBECoreUtil::CW32SID *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * *,_SECURITY_DESCRIPTOR * *)

- ea: `0x1800608d8`
- end: `0x180060a5a`
- name: `?CreateACLOwnerCreator@SBECoreUtil@@YAKPEAVCW32SID@1@W4_ACCESS_MODE@@K1KPEAPEAU_ACL@@PEAPEAU_SECURITY_DESCRIPTOR@@@Z`
- size: `386`
- prototype: `unsigned int __fastcall(SBECoreUtil *__hidden this, struct SBECoreUtil::CW32SID *, enum _ACCESS_MODE, unsigned int, enum _ACCESS_MODE, PACL *NewAcl, struct _ACL **, struct _SECURITY_DESCRIPTOR **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18005ff10`

## callees

- `0x1800017e0`
- `0x1800017ec`
- `0x18000256c`
- `0x1800608d8`
- `0x180060e40`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180060a3e`
- `KERNEL32!GetLastError` at `0x180060a3e`
- `KERNEL32!LocalAlloc` at `0x180060a0c`
- `KERNEL32!LocalAlloc` at `0x180060a0c`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180060a1f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x180060a1f`
- `ADVAPI32!SetEntriesInAclW` at `0x1800609f6`
- `ADVAPI32!SetEntriesInAclW` at `0x1800609f6`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180060a34`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x180060a34`

## pseudocode

```c
__int64 __fastcall SBECoreUtil::CreateACLOwnerCreator(
        SBECoreUtil *this,
        struct SBECoreUtil::CW32SID *a2,
        struct _SECURITY_DESCRIPTOR *a3,
        __int64 a4,
        enum _ACCESS_MODE a5,
        PACL *NewAcl,
        struct _ACL **a7)
{
  int v7; // ebp
  _DWORD *v9; // rdi
  DWORD LastError; // ebx
  unsigned __int64 v11; // rdx
  unsigned int v13; // r8d
  ULONG v14; // ecx
  __int64 v15; // rcx
  __int64 v16; // rdx
  struct _ACL *v17; // rax

  v7 = (int)a3;
  *NewAcl = 0;
  *a7 = 0;
  if ( !*((_DWORD *)this + 6) )
  {
    v9 = 0;
    LastError = 87;
LABEL_3:
    SBECoreUtil::FreeSecurityDescriptors((SBECoreUtil *)*NewAcl, *a7, a3);
    *NewAcl = 0;
    *a7 = 0;
    goto LABEL_4;
  }
  v9 = operator new[](saturated_mul(*((unsigned int *)this + 6), 0x30u));
  if ( !v9 )
  {
    LastError = 8;
    goto LABEL_3;
  }
  memset_0(v9, 0, 48LL * *((unsigned int *)this + 6));
  *v9 = v7;
  *(_QWORD *)(v9 + 1) = 2;
  v9[7] = 0;
  v9[8] = 5;
  v13 = 1;
  *((_QWORD *)v9 + 5) = **((_QWORD **)this + 2);
  v14 = *((_DWORD *)this + 6);
  if ( v14 > 1 )
  {
    do
    {
      v15 = v13++;
      v16 = 6 * v15;
      v9[2 * v16] = a5;
      *(_QWORD *)&v9[2 * v16 + 1] = 2;
      v9[2 * v16 + 7] = 0;
      v9[2 * v16 + 8] = 2;
      *(_QWORD *)&v9[2 * v16 + 10] = *(_QWORD *)(*((_QWORD *)this + 2) + 8 * v15);
      v14 = *((_DWORD *)this + 6);
    }
    while ( v13 < v14 );
  }
  LastError = SetEntriesInAclW(v14, (PEXPLICIT_ACCESS_W)v9, 0, NewAcl);
  if ( LastError )
    goto LABEL_3;
  v17 = (struct _ACL *)LocalAlloc(0x40u, 0x28u);
  *a7 = v17;
  if ( v17 && InitializeSecurityDescriptor(v17, 1u) && SetSecurityDescriptorDacl(*a7, 1, *NewAcl, 0) )
  {
    LastError = 0;
    goto LABEL_4;
  }
  LastError = GetLastError();
  if ( LastError )
    goto LABEL_3;
LABEL_4:
  operator delete(v9, v11);
  return LastError;
}

```

## disassembly

```asm
0x1800608d8  push    rbx
0x1800608da  push    rbp
0x1800608db  push    rsi
0x1800608dc  push    rdi
0x1800608dd  push    r14
0x1800608df  sub     rsp, 20h
0x1800608e3  mov     r14, [rsp+48h+NewAcl]
0x1800608e8  mov     ebp, r8d
0x1800608eb  mov     rsi, [rsp+48h+arg_30]
0x1800608f3  mov     rbx, rcx
0x1800608f6  mov     qword ptr [r14], 0
0x1800608fd  mov     qword ptr [rsi], 0
0x180060904  cmp     dword ptr [rcx+18h], 0
0x180060908  jnz     short loc_18006093D
0x18006090a  xor     edi, edi
0x18006090c  lea     ebx, [rdi+57h]
0x18006090f  mov     rdx, [rsi]; struct _ACL *
0x180060912  mov     rcx, [r14]; this
0x180060915  call    ?FreeSecurityDescriptors@SBECoreUtil@@YAXPEAU_ACL@@PEAU_SECURITY_DESCRIPTOR@@@Z; SBECoreUtil::FreeSecurityDescriptors(_ACL *,_SECURITY_DESCRIPTOR *)
0x18006091a  mov     qword ptr [r14], 0
0x180060921  mov     qword ptr [rsi], 0
0x180060928  mov     rcx, rdi; void *
0x18006092b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180060930  mov     eax, ebx
0x180060932  add     rsp, 20h
0x180060936  pop     r14
0x180060938  pop     rdi
0x180060939  pop     rsi
0x18006093a  pop     rbp
0x18006093b  pop     rbx
0x18006093c  retn
0x18006093d  mov     ecx, [rcx+18h]
0x180060940  mov     eax, 30h ; '0'
0x180060945  mul     rcx
0x180060948  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18006094f  cmovb   rax, rcx
0x180060953  mov     rcx, rax; unsigned __int64
0x180060956  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18006095b  mov     rdi, rax
0x18006095e  test    rax, rax
0x180060961  jnz     short loc_180060968
0x180060963  lea     ebx, [rax+8]
0x180060966  jmp     short loc_18006090F
0x180060968  mov     eax, [rbx+18h]
0x18006096b  xor     edx, edx; Val
0x18006096d  mov     rcx, rdi; void *
0x180060970  lea     r8, [rax+rax*2]
0x180060974  shl     r8, 4; Size
0x180060978  call    memset_0
0x18006097d  mov     [rdi], ebp
0x18006097f  mov     r10d, 2
0x180060985  mov     [rdi+4], r10
0x180060989  mov     dword ptr [rdi+1Ch], 0
0x180060990  mov     dword ptr [rdi+20h], 5
0x180060997  mov     rax, [rbx+10h]
0x18006099b  lea     ebp, [r10-1]
0x18006099f  mov     r8d, ebp
0x1800609a2  mov     rcx, [rax]
0x1800609a5  mov     [rdi+28h], rcx
0x1800609a9  mov     ecx, [rbx+18h]
0x1800609ac  cmp     ecx, ebp
0x1800609ae  jbe     short loc_1800609ED
0x1800609b0  mov     r9d, [rsp+48h+arg_20]
0x1800609b5  mov     ecx, r8d
0x1800609b8  add     r8d, ebp
0x1800609bb  lea     rdx, [rcx+rcx*2]
0x1800609bf  add     rdx, rdx
0x1800609c2  mov     [rdi+rdx*8], r9d
0x1800609c6  mov     [rdi+rdx*8+4], r10
0x1800609cb  mov     dword ptr [rdi+rdx*8+1Ch], 0
0x1800609d3  mov     [rdi+rdx*8+20h], r10d
0x1800609d8  mov     rax, [rbx+10h]
0x1800609dc  mov     rcx, [rax+rcx*8]
0x1800609e0  mov     [rdi+rdx*8+28h], rcx
0x1800609e5  mov     ecx, [rbx+18h]; cCountOfExplicitEntries
0x1800609e8  cmp     r8d, ecx
0x1800609eb  jb      short loc_1800609B5
0x1800609ed  mov     r9, r14; NewAcl
0x1800609f0  xor     r8d, r8d; OldAcl
0x1800609f3  mov     rdx, rdi; pListOfExplicitEntries
0x1800609f6  call    cs:__imp_SetEntriesInAclW
0x1800609fc  mov     ebx, eax
0x1800609fe  test    eax, eax
0x180060a00  jnz     loc_18006090F
0x180060a06  lea     edx, [rax+28h]; uBytes
0x180060a09  lea     ecx, [rax+40h]; uFlags
0x180060a0c  call    cs:__imp_LocalAlloc
0x180060a12  mov     [rsi], rax
0x180060a15  test    rax, rax
0x180060a18  jz      short loc_180060A3E
0x180060a1a  mov     edx, ebp; dwRevision
0x180060a1c  mov     rcx, rax; pSecurityDescriptor
0x180060a1f  call    cs:__imp_InitializeSecurityDescriptor
0x180060a25  test    eax, eax
0x180060a27  jz      short loc_180060A3E
0x180060a29  mov     r8, [r14]; pDacl
0x180060a2c  xor     r9d, r9d; bDaclDefaulted
0x180060a2f  mov     rcx, [rsi]; pSecurityDescriptor
0x180060a32  mov     edx, ebp; bDaclPresent
0x180060a34  call    cs:__imp_SetSecurityDescriptorDacl
0x180060a3a  test    eax, eax
0x180060a3c  jnz     short loc_180060A53
0x180060a3e  call    cs:__imp_GetLastError
0x180060a44  mov     ebx, eax
0x180060a46  test    eax, eax
0x180060a48  jz      loc_180060928
0x180060a4e  jmp     loc_18006090F
0x180060a53  xor     ebx, ebx
0x180060a55  jmp     loc_180060928
```
