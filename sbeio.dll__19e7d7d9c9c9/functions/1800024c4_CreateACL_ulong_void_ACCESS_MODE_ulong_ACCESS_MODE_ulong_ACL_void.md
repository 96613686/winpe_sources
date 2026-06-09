# CreateACL(ulong,void * *,_ACCESS_MODE,ulong,_ACCESS_MODE,ulong,_ACL * &,void * &)

- ea: `0x1800024c4`
- end: `0x18000264f`
- name: `?CreateACL@@YAKKPEAPEAXW4_ACCESS_MODE@@K1KAEAPEAU_ACL@@AEAPEAX@Z`
- size: `395`
- prototype: `unsigned int __usercall@<eax>(ULONG cCountOfExplicitEntries@<ecx>, void **@<rdx>, enum _ACCESS_MODE@<r8d>, unsigned int@<r9d>, enum _ACCESS_MODE, unsigned int, struct _ACL **, void **)`
- caller_count: `4`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180003220`
- `0x1800039f0`
- `0x18000569c`
- `0x180006fbc`

## callees

- `0x180001194`
- `0x1800011ec`
- `0x180001f1c`
- `0x1800024c4`
- `0x1800027c4`

## import_xrefs

- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000260f`
- `ADVAPI32!SetSecurityDescriptorDacl` at `0x18000260f`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800025f9`
- `ADVAPI32!InitializeSecurityDescriptor` at `0x1800025f9`
- `ADVAPI32!SetEntriesInAclW` at `0x1800025c1`
- `ADVAPI32!SetEntriesInAclW` at `0x1800025c1`
- `KERNEL32!GetLastError` at `0x1800025e9`
- `KERNEL32!GetLastError` at `0x1800025e9`
- `KERNEL32!LocalAlloc` at `0x1800025db`
- `KERNEL32!LocalAlloc` at `0x1800025db`

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
0x1800024c4  push    rbx
0x1800024c6  push    rsi
0x1800024c7  push    rdi
0x1800024c8  push    r12
0x1800024ca  push    r13
0x1800024cc  push    r14
0x1800024ce  push    r15
0x1800024d0  sub     rsp, 30h
0x1800024d4  mov     r13d, r9d
0x1800024d7  mov     r15, rdx
0x1800024da  mov     ebx, ecx
0x1800024dc  xor     eax, eax
0x1800024de  test    ecx, ecx
0x1800024e0  jz      loc_18000263A
0x1800024e6  test    rdx, rdx
0x1800024e9  jz      loc_18000263A
0x1800024ef  mov     [rsp+68h+var_40], rax
0x1800024f4  mov     [rsp+68h+var_48], eax
0x1800024f8  mov     r14, [rsp+68h+NewAcl]
0x180002500  mov     [r14], rax
0x180002503  mov     rsi, [rsp+68h+arg_38]
0x18000250b  mov     [rsi], rax
0x18000250e  mov     eax, 30h ; '0'
0x180002513  mul     rbx
0x180002516  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18000251d  cmovb   rax, rcx
0x180002521  mov     rcx, rax; unsigned __int64
0x180002524  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x180002529  mov     rdi, rax
0x18000252c  mov     [rsp+68h+var_40], rax
0x180002531  test    rax, rax
0x180002534  jnz     short loc_18000253E
0x180002536  lea     ebx, [rax+8]
0x180002539  jmp     loc_18000261B
0x18000253e  lea     r8, [rbx+rbx*2]
0x180002542  shl     r8, 4; Size
0x180002546  xor     edx, edx; Val
0x180002548  mov     rcx, rdi; void *
0x18000254b  call    memset_0
0x180002550  mov     [rdi], r13d
0x180002553  mov     r9d, 2
0x180002559  mov     [rdi+4], r9
0x18000255d  mov     dword ptr [rdi+1Ch], 0
0x180002564  mov     dword ptr [rdi+20h], 5
0x18000256b  mov     rax, [r15]
0x18000256e  mov     [rdi+28h], rax
0x180002572  lea     r12d, [r9-1]
0x180002576  mov     edx, r12d
0x180002579  mov     r8d, [rsp+68h+arg_28]
0x180002581  mov     [rsp+68h+var_44], edx
0x180002585  cmp     edx, ebx
0x180002587  jnb     short loc_1800025B6
0x180002589  mov     eax, edx
0x18000258b  lea     rcx, [rax+rax*2]
0x18000258f  add     rcx, rcx
0x180002592  mov     [rdi+rcx*8], r8d
0x180002596  mov     [rdi+rcx*8+4], r9
0x18000259b  mov     dword ptr [rdi+rcx*8+1Ch], 0
0x1800025a3  mov     [rdi+rcx*8+20h], r9d
0x1800025a8  mov     rax, [r15+rax*8]
0x1800025ac  mov     [rdi+rcx*8+28h], rax
0x1800025b1  add     edx, r12d
0x1800025b4  jmp     short loc_180002581
0x1800025b6  mov     r9, r14; NewAcl
0x1800025b9  xor     r8d, r8d; OldAcl
0x1800025bc  mov     rdx, rdi; pListOfExplicitEntries
0x1800025bf  mov     ecx, ebx; cCountOfExplicitEntries
0x1800025c1  call    cs:__imp_SetEntriesInAclW
0x1800025c7  mov     ebx, eax
0x1800025c9  test    eax, eax
0x1800025cb  jz      short loc_1800025D3
0x1800025cd  mov     [rsp+68h+var_48], eax
0x1800025d1  jmp     short loc_18000261F
0x1800025d3  mov     edx, 28h ; '('; uBytes
0x1800025d8  lea     ecx, [rdx+18h]; uFlags
0x1800025db  call    cs:__imp_LocalAlloc
0x1800025e1  mov     [rsi], rax
0x1800025e4  test    rax, rax
0x1800025e7  jnz     short loc_1800025F3
0x1800025e9  call    cs:__imp_GetLastError
0x1800025ef  mov     ebx, eax
0x1800025f1  jmp     short loc_1800025CD
0x1800025f3  mov     edx, r12d; dwRevision
0x1800025f6  mov     rcx, rax; pSecurityDescriptor
0x1800025f9  call    cs:__imp_InitializeSecurityDescriptor
0x1800025ff  test    eax, eax
0x180002601  jz      short loc_1800025E9
0x180002603  xor     r9d, r9d; bDaclDefaulted
0x180002606  mov     r8, [r14]; pDacl
0x180002609  mov     edx, r12d; bDaclPresent
0x18000260c  mov     rcx, [rsi]; pSecurityDescriptor
0x18000260f  call    cs:__imp_SetSecurityDescriptorDacl
0x180002615  test    eax, eax
0x180002617  jz      short loc_1800025E9
0x180002619  xor     ebx, ebx
0x18000261b  mov     [rsp+68h+var_48], ebx
0x18000261f  mov     rcx, rdi; void *
0x180002622  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002627  test    ebx, ebx
0x180002629  jz      short loc_180002636
0x18000262b  mov     rdx, rsi; void **
0x18000262e  mov     rcx, r14; struct _ACL **
0x180002631  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x180002636  mov     eax, ebx
0x180002638  jmp     short loc_18000263F
0x18000263a  mov     eax, 57h ; 'W'
0x18000263f  add     rsp, 30h
0x180002643  pop     r15
0x180002645  pop     r14
0x180002647  pop     r13
0x180002649  pop     r12
0x18000264b  pop     rdi
0x18000264c  pop     rsi
0x18000264d  pop     rbx
0x18000264e  retn
0x18002a1a6  push    rbp
0x18002a1a8  sub     rsp, 20h
0x18002a1ac  mov     rbp, rdx
0x18002a1af  mov     rcx, [rbp+28h]; void *
0x18002a1b3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18002a1b8  cmp     dword ptr [rbp+20h], 0
0x18002a1bc  jz      short loc_18002A1D2
0x18002a1be  mov     rdx, [rbp+0A8h]; void **
0x18002a1c5  mov     rcx, [rbp+0A0h]; struct _ACL **
0x18002a1cc  call    ?FreeSecurityDescriptors@@YAXAEAPEAU_ACL@@AEAPEAX@Z; FreeSecurityDescriptors(_ACL * &,void * &)
0x18002a1d1  nop
0x18002a1d2  add     rsp, 20h
0x18002a1d6  pop     rbp
0x18002a1d7  retn
```
