# CAceList::GetAclForExplicitEntries(void *,_ACL * *)

- ea: `0x1800064d4`
- end: `0x18000671b`
- name: `?GetAclForExplicitEntries@CAceList@@QEAAJPEAXPEAPEAU_ACL@@@Z`
- size: `583`
- prototype: `__int64 __fastcall(struct _DPA **this, void *, struct _ACL **)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180006180`

## callees

- `0x1800064d4`
- `0x180006de8`
- `0x180007b90`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800065f6`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18000665b`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x1800065f6`
- `api-ms-win-security-base-l1-1-0!AddAccessDeniedAceEx` at `0x18000665b`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800065bb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800065bb`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066fe`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800066fe`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000659b`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000659b`

## pseudocode

```c
__int64 __fastcall CAceList::GetAclForExplicitEntries(struct _DPA **this, void *a2, struct _ACL **a3)
{
  int v3; // r14d
  int v5; // r15d
  int v7; // edi
  INT_PTR i; // rsi
  struct _DPA *v9; // rcx
  unsigned __int16 *Ptr; // rax
  int v11; // ebp
  INT_PTR j; // rsi
  struct _DPA *v13; // rcx
  unsigned __int16 *v14; // rax
  DWORD v15; // ebp
  INT_PTR k; // rsi
  struct _DPA *v17; // rcx
  unsigned __int16 *v18; // rax
  struct _ACL *v19; // rax
  struct _ACL *v20; // rsi
  INT_PTR m; // rbp
  struct _DPA *v22; // rcx
  unsigned __int8 *v23; // rax
  INT_PTR v24; // rbp
  struct _DPA *v25; // rcx
  PVOID v26; // rax
  INT_PTR n; // rbp
  struct _DPA *v28; // rcx
  struct CAce *v29; // rax
  INT_PTR v30; // rbp
  struct _DPA *v31; // rcx
  struct CAce *v32; // rax

  v3 = 8;
  v5 = 8;
  v7 = -2147024882;
  for ( i = 0; ; ++i )
  {
    v9 = *this;
    if ( !*this || i >= *(int *)v9 )
      break;
    Ptr = (unsigned __int16 *)g_pfn_DPA_GetPtr(v9, i);
    if ( Ptr )
      v5 += Ptr[1];
  }
  v11 = 8;
  for ( j = 0; ; ++j )
  {
    v13 = this[1];
    if ( !v13 || j >= *(int *)v13 )
      break;
    v14 = (unsigned __int16 *)g_pfn_DPA_GetPtr(v13, j);
    if ( v14 )
      v11 += v14[1];
  }
  v15 = v5 + v11 + 8;
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    for ( k = 0; ; ++k )
    {
      v17 = this[2];
      if ( !v17 || k >= *(int *)v17 )
        break;
      v18 = (unsigned __int16 *)g_pfn_DPA_GetPtr(v17, k);
      if ( v18 )
        v3 += v18[1];
    }
    v15 += v3;
  }
  v19 = (struct _ACL *)LocalAlloc(0x40u, v15);
  v20 = v19;
  if ( !v19 )
    goto LABEL_52;
  InitializeAcl(v19, v15, 2u);
  for ( m = 0; ; ++m )
  {
    v22 = *this;
    v7 = 0;
    if ( !*this || m >= *(int *)v22 )
      break;
    v23 = (unsigned __int8 *)g_pfn_DPA_GetPtr(v22, m);
    if ( !AddAccessDeniedAceEx(v20, 2u, v23[1], *((_DWORD *)v23 + 1), *((PSID *)v23 + 1)) )
    {
      v7 = -2147024882;
      break;
    }
  }
  if ( !*((_DWORD *)this + 6) && !*((_DWORD *)this + 7) )
  {
    v24 = 0;
    if ( v7 >= 0 )
    {
      while ( 1 )
      {
        v25 = this[2];
        if ( !v25 || v24 >= *(int *)v25 )
          break;
        v26 = g_pfn_DPA_GetPtr(v25, v24);
        if ( (*((_BYTE *)v26 + 28) & 1) == 0
          && !AddAccessDeniedAceEx(v20, 2u, *((_BYTE *)v26 + 1) & 0xEF, *((_DWORD *)v26 + 1), *((PSID *)v26 + 1)) )
        {
          v7 = -2147024882;
          goto LABEL_42;
        }
        ++v24;
      }
    }
  }
  for ( n = 0; v7 >= 0; v7 = CAceList::_AddAllowedAceToAcl((CAceList *)this, v29, 0, v20) )
  {
    v28 = this[1];
    if ( !v28 )
      break;
    if ( n >= *(int *)v28 )
      break;
    v29 = (struct CAce *)g_pfn_DPA_GetPtr(v28, n++);
  }
LABEL_42:
  if ( *((_DWORD *)this + 6) || *((_DWORD *)this + 7) )
  {
LABEL_50:
    if ( v7 >= 0 )
      goto LABEL_52;
LABEL_51:
    LocalFree(v20);
    v20 = 0;
    goto LABEL_52;
  }
  v30 = 0;
  if ( v7 < 0 )
    goto LABEL_51;
  while ( 1 )
  {
    v31 = this[2];
    if ( !v31 )
      break;
    if ( v30 < *(int *)v31 )
    {
      v32 = (struct CAce *)g_pfn_DPA_GetPtr(v31, v30);
      if ( (*((_BYTE *)v32 + 28) & 1) != 0 )
        v7 = CAceList::_AddAllowedAceToAcl((CAceList *)this, v32, 1, v20);
      ++v30;
      if ( v7 >= 0 )
        continue;
    }
    goto LABEL_50;
  }
LABEL_52:
  *a3 = v20;
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800064d4  push    rbx
0x1800064d6  push    rbp
0x1800064d7  push    rsi
0x1800064d8  push    rdi
0x1800064d9  push    r12
0x1800064db  push    r14
0x1800064dd  push    r15
0x1800064df  sub     rsp, 30h
0x1800064e3  mov     r14d, 8
0x1800064e9  mov     r12, r8
0x1800064ec  mov     r15d, r14d
0x1800064ef  mov     rbx, rcx
0x1800064f2  mov     edi, 8007000Eh
0x1800064f7  xor     esi, esi
0x1800064f9  mov     rcx, [rbx]; hdpa
0x1800064fc  test    rcx, rcx
0x1800064ff  jz      short loc_180006523
0x180006501  movsxd  rax, dword ptr [rcx]
0x180006504  cmp     rsi, rax
0x180006507  jge     short loc_180006523
0x180006509  mov     rdx, rsi; i
0x18000650c  call    cs:g_pfn_DPA_GetPtr
0x180006512  test    rax, rax
0x180006515  jz      short loc_18000651E
0x180006517  movzx   eax, word ptr [rax+2]
0x18000651b  add     r15d, eax
0x18000651e  inc     rsi
0x180006521  jmp     short loc_1800064F9
0x180006523  mov     ebp, r14d
0x180006526  xor     esi, esi
0x180006528  mov     rcx, [rbx+8]; hdpa
0x18000652c  test    rcx, rcx
0x18000652f  jz      short loc_180006552
0x180006531  movsxd  rax, dword ptr [rcx]
0x180006534  cmp     rsi, rax
0x180006537  jge     short loc_180006552
0x180006539  mov     rdx, rsi; i
0x18000653c  call    cs:g_pfn_DPA_GetPtr
0x180006542  test    rax, rax
0x180006545  jz      short loc_18000654D
0x180006547  movzx   eax, word ptr [rax+2]
0x18000654b  add     ebp, eax
0x18000654d  inc     rsi
0x180006550  jmp     short loc_180006528
0x180006552  add     ebp, r14d
0x180006555  add     ebp, r15d
0x180006558  cmp     dword ptr [rbx+18h], 0
0x18000655c  jnz     short loc_180006594
0x18000655e  cmp     dword ptr [rbx+1Ch], 0
0x180006562  jnz     short loc_180006594
0x180006564  xor     esi, esi
0x180006566  mov     rcx, [rbx+10h]; hdpa
0x18000656a  test    rcx, rcx
0x18000656d  jz      short loc_180006591
0x18000656f  movsxd  rax, dword ptr [rcx]
0x180006572  cmp     rsi, rax
0x180006575  jge     short loc_180006591
0x180006577  mov     rdx, rsi; i
0x18000657a  call    cs:g_pfn_DPA_GetPtr
0x180006580  test    rax, rax
0x180006583  jz      short loc_18000658C
0x180006585  movzx   eax, word ptr [rax+2]
0x180006589  add     r14d, eax
0x18000658c  inc     rsi
0x18000658f  jmp     short loc_180006566
0x180006591  add     ebp, r14d
0x180006594  mov     edx, ebp; uBytes
0x180006596  mov     ecx, 40h ; '@'; uFlags
0x18000659b  call    cs:__imp_LocalAlloc
0x1800065a1  mov     rsi, rax
0x1800065a4  test    rax, rax
0x1800065a7  jz      loc_180006706
0x1800065ad  mov     r14d, 2
0x1800065b3  mov     edx, ebp; nAclLength
0x1800065b5  mov     r8d, r14d; dwAclRevision
0x1800065b8  mov     rcx, rax; pAcl
0x1800065bb  call    cs:__imp_InitializeAcl
0x1800065c1  xor     ebp, ebp
0x1800065c3  mov     rcx, [rbx]; hdpa
0x1800065c6  xor     edi, edi
0x1800065c8  test    rcx, rcx
0x1800065cb  jz      short loc_18000660A
0x1800065cd  movsxd  rax, dword ptr [rcx]
0x1800065d0  cmp     rbp, rax
0x1800065d3  jge     short loc_18000660A
0x1800065d5  mov     rdx, rbp; i
0x1800065d8  call    cs:g_pfn_DPA_GetPtr
0x1800065de  mov     edx, r14d; dwAceRevision
0x1800065e1  mov     rcx, rsi; pAcl
0x1800065e4  mov     r9d, [rax+4]; AccessMask
0x1800065e8  movzx   r8d, byte ptr [rax+1]; AceFlags
0x1800065ed  mov     rax, [rax+8]
0x1800065f1  mov     [rsp+68h+pSid], rax; pSid
0x1800065f6  call    cs:__imp_AddAccessDeniedAceEx
0x1800065fc  test    eax, eax
0x1800065fe  jz      short loc_180006605
0x180006600  inc     rbp
0x180006603  jmp     short loc_1800065C3
0x180006605  mov     edi, 8007000Eh
0x18000660a  cmp     dword ptr [rbx+18h], 0
0x18000660e  jnz     short loc_180006671
0x180006610  cmp     dword ptr [rbx+1Ch], 0
0x180006614  jnz     short loc_180006671
0x180006616  xor     ebp, ebp
0x180006618  test    edi, edi
0x18000661a  js      short loc_180006671
0x18000661c  mov     rcx, [rbx+10h]; hdpa
0x180006620  test    rcx, rcx
0x180006623  jz      short loc_180006671
0x180006625  movsxd  rax, dword ptr [rcx]
0x180006628  cmp     rbp, rax
0x18000662b  jge     short loc_180006671
0x18000662d  mov     rdx, rbp; i
0x180006630  call    cs:g_pfn_DPA_GetPtr
0x180006636  mov     r9, rax
0x180006639  test    byte ptr [rax+1Ch], 1
0x18000663d  jnz     short loc_180006665
0x18000663f  movzx   r8d, byte ptr [rax+1]
0x180006644  mov     edx, r14d; dwAceRevision
0x180006647  mov     rax, [rax+8]
0x18000664b  and     r8d, 0FFFFFFEFh; AceFlags
0x18000664f  mov     r9d, [r9+4]; AccessMask
0x180006653  mov     rcx, rsi; pAcl
0x180006656  mov     [rsp+68h+pSid], rax; pSid
0x18000665b  call    cs:__imp_AddAccessDeniedAceEx
0x180006661  test    eax, eax
0x180006663  jz      short loc_18000666A
0x180006665  inc     rbp
0x180006668  jmp     short loc_18000661C
0x18000666a  mov     edi, 8007000Eh
0x18000666f  jmp     short loc_1800066AB
0x180006671  xor     ebp, ebp
0x180006673  test    edi, edi
0x180006675  js      short loc_1800066AB
0x180006677  mov     rcx, [rbx+8]; hdpa
0x18000667b  test    rcx, rcx
0x18000667e  jz      short loc_1800066AB
0x180006680  movsxd  rax, dword ptr [rcx]
0x180006683  cmp     rbp, rax
0x180006686  jge     short loc_1800066AB
0x180006688  mov     rdx, rbp; i
0x18000668b  call    cs:g_pfn_DPA_GetPtr
0x180006691  mov     r9, rsi; struct _ACL *
0x180006694  xor     r8d, r8d; bool
0x180006697  mov     rdx, rax; struct CAce *
0x18000669a  mov     rcx, rbx; this
0x18000669d  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800066a2  inc     rbp
0x1800066a5  mov     edi, eax
0x1800066a7  test    eax, eax
0x1800066a9  jns     short loc_180006677
0x1800066ab  cmp     dword ptr [rbx+18h], 0
0x1800066af  jnz     short loc_1800066F7
0x1800066b1  cmp     dword ptr [rbx+1Ch], 0
0x1800066b5  jnz     short loc_1800066F7
0x1800066b7  xor     ebp, ebp
0x1800066b9  test    edi, edi
0x1800066bb  js      short loc_1800066FB
0x1800066bd  mov     rcx, [rbx+10h]; hdpa
0x1800066c1  test    rcx, rcx
0x1800066c4  jz      short loc_180006706
0x1800066c6  movsxd  rax, dword ptr [rcx]
0x1800066c9  cmp     rbp, rax
0x1800066cc  jge     short loc_1800066F7
0x1800066ce  mov     rdx, rbp; i
0x1800066d1  call    cs:g_pfn_DPA_GetPtr
0x1800066d7  test    byte ptr [rax+1Ch], 1
0x1800066db  jz      short loc_1800066F0
0x1800066dd  mov     r9, rsi; struct _ACL *
0x1800066e0  mov     r8b, 1; bool
0x1800066e3  mov     rdx, rax; struct CAce *
0x1800066e6  mov     rcx, rbx; this
0x1800066e9  call    ?_AddAllowedAceToAcl@CAceList@@AEAAJQEAVCAce@@_NPEAU_ACL@@@Z; CAceList::_AddAllowedAceToAcl(CAce * const,bool,_ACL *)
0x1800066ee  mov     edi, eax
0x1800066f0  inc     rbp
0x1800066f3  test    edi, edi
0x1800066f5  jns     short loc_1800066BD
0x1800066f7  test    edi, edi
0x1800066f9  jns     short loc_180006706
0x1800066fb  mov     rcx, rsi; hMem
0x1800066fe  call    cs:__imp_LocalFree
0x180006704  xor     esi, esi
0x180006706  mov     [r12], rsi
0x18000670a  mov     eax, edi
0x18000670c  add     rsp, 30h
0x180006710  pop     r15
0x180006712  pop     r14
0x180006714  pop     r12
0x180006716  pop     rdi
0x180006717  pop     rsi
0x180006718  pop     rbp
0x180006719  pop     rbx
0x18000671a  retn
```
