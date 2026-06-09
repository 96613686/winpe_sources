# CWcnIdentity::CopySelfIdentity(CWcnIdentity *)

- ea: `0x18000b4a0`
- end: `0x18000b74d`
- name: `?CopySelfIdentity@CWcnIdentity@@QEAAJPEAV1@@Z`
- size: `685`
- prototype: `__int64 __fastcall(RTL_SRWLOCK *this, RTL_SRWLOCK *)`
- caller_count: `4`
- callee_count: `6`
- tags: ``

## callers

- `0x180003840`
- `0x18002ba28`
- `0x18002bce8`
- `0x18002c55c`

## callees

- `0x180004f78`
- `0x180004fb8`
- `0x180005014`
- `0x18000b4a0`
- `0x18001cdd0`
- `0x180053004`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6f1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000b6f1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b53e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000b53e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b6fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18000b6fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b531`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18000b531`

## pseudocode

```c
__int64 __fastcall CWcnIdentity::CopySelfIdentity(RTL_SRWLOCK *this, RTL_SRWLOCK *a2)
{
  _QWORD *v4; // r10
  const char *Indent; // rax
  __int64 v6; // r10
  RTL_SRWLOCK *v8; // r12
  CWcnAttributeDatabase *v9; // r14
  _QWORD *v10; // r10
  const char *v11; // rax
  __int64 v12; // r10
  int v13; // esi
  __int64 *v14; // rbx
  const struct CWcnAttribute **i; // rdi
  int appended; // eax
  __int64 *j; // rax
  __int64 *v18; // rcx
  unsigned int v19; // eax
  __int64 v20; // r10
  unsigned int v21; // eax
  __int64 v22; // r10

  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    Indent = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v6 + 16), 75, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, Indent);
    v4 = WPP_GLOBAL_Control;
  }
  if ( !a2 )
  {
    if ( v4 != &WPP_GLOBAL_Control && *((_BYTE *)v4 + 25) >= 2u )
      WPP_SF_s(v4[2], 76, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, "pDestination");
    return 2147500035LL;
  }
  AcquireSRWLockShared(this + 4);
  v8 = a2 + 4;
  AcquireSRWLockExclusive(a2 + 4);
  v9 = (CWcnAttributeDatabase *)&a2[5];
  *(_OWORD *)&a2[2].Ptr = *(_OWORD *)&this[2].Ptr;
  LODWORD(a2[14].Ptr) = this[14].Ptr;
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u )
  {
    v11 = GetIndent(1);
    WPP_SF_s(*(_QWORD *)(v12 + 16), 20, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids, v11);
    v10 = WPP_GLOBAL_Control;
  }
  if ( a2 == (RTL_SRWLOCK *)-40LL )
  {
    if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
    {
      WPP_SF_s(v10[2], 21, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids, "pRhs");
      v10 = WPP_GLOBAL_Control;
    }
    v13 = -2147467261;
    goto LABEL_42;
  }
  v13 = 0;
  v14 = *(__int64 **)this[7].Ptr;
LABEL_18:
  if ( v14 == this[7].Ptr )
    goto LABEL_36;
  for ( i = (const struct CWcnAttribute **)v14[5]; ; ++i )
  {
    if ( i == (const struct CWcnAttribute **)v14[6] )
    {
      if ( *((_BYTE *)v14 + 25) )
        goto LABEL_18;
      j = (__int64 *)v14[2];
      if ( *((_BYTE *)j + 25) )
      {
        for ( j = (__int64 *)v14[1]; !*((_BYTE *)j + 25) && v14 == (__int64 *)j[2]; j = (__int64 *)j[1] )
          v14 = j;
LABEL_32:
        v14 = j;
        goto LABEL_18;
      }
      v18 = (__int64 *)*j;
      if ( *(_BYTE *)(*j + 25) )
        goto LABEL_32;
      do
      {
        v14 = v18;
        v18 = (__int64 *)*v18;
      }
      while ( !*((_BYTE *)v18 + 25) );
      goto LABEL_18;
    }
    appended = CWcnAttributeDatabase::AppendAttribute(v9, *i);
    v13 = appended;
    if ( appended < 0 )
      break;
  }
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        22,
        WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids,
        (unsigned int)appended);
LABEL_36:
      v10 = WPP_GLOBAL_Control;
    }
    if ( v10 != &WPP_GLOBAL_Control && (v13 < 0 || *((_BYTE *)v10 + 25) >= 6u) )
    {
      v19 = (unsigned int)GetIndent(-1);
      WPP_SF_sd(*(_QWORD *)(v20 + 16), 23, (unsigned int)WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids, v19, v13);
      v10 = WPP_GLOBAL_Control;
    }
  }
  if ( v13 < 0 )
  {
LABEL_42:
    if ( v10 != &WPP_GLOBAL_Control && *((_BYTE *)v10 + 25) >= 2u )
      WPP_SF_d(v10[2], 77, WPP_e632221d673033b22bf624a0da3869d5_Traceguids, (unsigned int)v13);
  }
  ReleaseSRWLockExclusive(v8);
  ReleaseSRWLockShared(this + 4);
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (v13 < 0 || *((_BYTE *)WPP_GLOBAL_Control + 25) >= 6u) )
  {
    v21 = (unsigned int)GetIndent(-1);
    WPP_SF_sd(*(_QWORD *)(v22 + 16), 78, (unsigned int)WPP_e632221d673033b22bf624a0da3869d5_Traceguids, v21, v13);
  }
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18000b4a0  push    rbx
0x18000b4a2  push    rbp
0x18000b4a3  push    rsi
0x18000b4a4  push    rdi
0x18000b4a5  push    r12
0x18000b4a7  push    r14
0x18000b4a9  push    r15
0x18000b4ab  sub     rsp, 30h
0x18000b4af  mov     rbx, rdx
0x18000b4b2  mov     rbp, rcx
0x18000b4b5  mov     r10, cs:WPP_GLOBAL_Control
0x18000b4bc  lea     rdi, WPP_GLOBAL_Control
0x18000b4c3  mov     esi, 1
0x18000b4c8  cmp     r10, rdi
0x18000b4cb  jz      short loc_18000B4F8
0x18000b4cd  cmp     byte ptr [r10+19h], 6
0x18000b4d2  jb      short loc_18000B4F8
0x18000b4d4  mov     ecx, esi; int
0x18000b4d6  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b4db  mov     rcx, [r10+10h]
0x18000b4df  lea     edx, [rsi+4Ah]
0x18000b4e2  mov     r9, rax
0x18000b4e5  lea     r8, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000b4ec  call    WPP_SF_s
0x18000b4f1  mov     r10, cs:WPP_GLOBAL_Control
0x18000b4f8  test    rbx, rbx
0x18000b4fb  jnz     short loc_18000B52D
0x18000b4fd  cmp     r10, rdi
0x18000b500  jz      short loc_18000B523
0x18000b502  cmp     byte ptr [r10+19h], 2
0x18000b507  jb      short loc_18000B523
0x18000b509  mov     rcx, [r10+10h]
0x18000b50d  lea     edx, [rbx+4Ch]
0x18000b510  lea     r9, aPdestination; "pDestination"
0x18000b517  lea     r8, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000b51e  call    WPP_SF_s
0x18000b523  mov     eax, 80004003h
0x18000b528  jmp     loc_18000B73E
0x18000b52d  lea     rcx, [rbp+20h]; SRWLock
0x18000b531  call    cs:__imp_AcquireSRWLockShared
0x18000b537  lea     r12, [rbx+20h]
0x18000b53b  mov     rcx, r12; SRWLock
0x18000b53e  call    cs:__imp_AcquireSRWLockExclusive
0x18000b544  movups  xmm0, xmmword ptr [rbp+10h]
0x18000b548  lea     r14, [rbx+28h]
0x18000b54c  movdqu  xmmword ptr [rbx+10h], xmm0
0x18000b551  mov     eax, [rbp+70h]
0x18000b554  mov     [rbx+70h], eax
0x18000b557  mov     r10, cs:WPP_GLOBAL_Control
0x18000b55e  cmp     r10, rdi
0x18000b561  jz      short loc_18000B590
0x18000b563  cmp     byte ptr [r10+19h], 6
0x18000b568  jb      short loc_18000B590
0x18000b56a  mov     ecx, esi; int
0x18000b56c  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b571  mov     rcx, [r10+10h]
0x18000b575  lea     r8, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids
0x18000b57c  mov     edx, 14h
0x18000b581  mov     r9, rax
0x18000b584  call    WPP_SF_s
0x18000b589  mov     r10, cs:WPP_GLOBAL_Control
0x18000b590  test    r14, r14
0x18000b593  jnz     short loc_18000B5CD
0x18000b595  cmp     r10, rdi
0x18000b598  jz      short loc_18000B5C3
0x18000b59a  cmp     byte ptr [r10+19h], 2
0x18000b59f  jb      short loc_18000B5C3
0x18000b5a1  mov     rcx, [r10+10h]
0x18000b5a5  lea     edx, [r14+15h]
0x18000b5a9  lea     r9, aPrhs; "pRhs"
0x18000b5b0  lea     r8, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids
0x18000b5b7  call    WPP_SF_s
0x18000b5bc  mov     r10, cs:WPP_GLOBAL_Control
0x18000b5c3  mov     esi, 80004003h
0x18000b5c8  jmp     loc_18000B6CA
0x18000b5cd  mov     rbx, [rbp+38h]
0x18000b5d1  xor     esi, esi
0x18000b5d3  mov     rbx, [rbx]
0x18000b5d6  cmp     rbx, [rbp+38h]
0x18000b5da  jz      loc_18000B67D
0x18000b5e0  mov     rdi, [rbx+28h]
0x18000b5e4  cmp     rdi, [rbx+30h]
0x18000b5e8  jz      short loc_18000B601
0x18000b5ea  mov     rdx, [rdi]; struct CWcnAttribute *
0x18000b5ed  mov     rcx, r14; this
0x18000b5f0  call    ?AppendAttribute@CWcnAttributeDatabase@@QEAAJPEBVCWcnAttribute@@@Z; CWcnAttributeDatabase::AppendAttribute(CWcnAttribute const *)
0x18000b5f5  mov     esi, eax
0x18000b5f7  test    eax, eax
0x18000b5f9  js      short loc_18000B649
0x18000b5fb  add     rdi, 8
0x18000b5ff  jmp     short loc_18000B5E4
0x18000b601  cmp     byte ptr [rbx+19h], 0
0x18000b605  jnz     short loc_18000B5D6
0x18000b607  mov     rax, [rbx+10h]
0x18000b60b  cmp     byte ptr [rax+19h], 0
0x18000b60f  jnz     short loc_18000B62B
0x18000b611  mov     rcx, [rax]
0x18000b614  cmp     byte ptr [rcx+19h], 0
0x18000b618  jnz     short loc_18000B644
0x18000b61a  mov     rax, [rcx]
0x18000b61d  mov     rbx, rcx
0x18000b620  mov     rcx, rax
0x18000b623  cmp     byte ptr [rax+19h], 0
0x18000b627  jz      short loc_18000B61A
0x18000b629  jmp     short loc_18000B5D6
0x18000b62b  mov     rax, [rbx+8]
0x18000b62f  jmp     short loc_18000B63E
0x18000b631  cmp     rbx, [rax+10h]
0x18000b635  jnz     short loc_18000B644
0x18000b637  mov     rbx, rax
0x18000b63a  mov     rax, [rax+8]
0x18000b63e  cmp     byte ptr [rax+19h], 0
0x18000b642  jz      short loc_18000B631
0x18000b644  mov     rbx, rax
0x18000b647  jmp     short loc_18000B5D6
0x18000b649  mov     r10, cs:WPP_GLOBAL_Control
0x18000b650  lea     rdi, WPP_GLOBAL_Control
0x18000b657  cmp     r10, rdi
0x18000b65a  jz      short loc_18000B6C6
0x18000b65c  cmp     byte ptr [r10+19h], 2
0x18000b661  jb      short loc_18000B68B
0x18000b663  mov     rcx, [r10+10h]
0x18000b667  lea     r8, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids
0x18000b66e  mov     edx, 16h
0x18000b673  mov     r9d, eax
0x18000b676  call    WPP_SF_d
0x18000b67b  jmp     short loc_18000B684
0x18000b67d  lea     rdi, WPP_GLOBAL_Control
0x18000b684  mov     r10, cs:WPP_GLOBAL_Control
0x18000b68b  cmp     r10, rdi
0x18000b68e  jz      short loc_18000B6C6
0x18000b690  test    esi, esi
0x18000b692  js      short loc_18000B69B
0x18000b694  cmp     byte ptr [r10+19h], 6
0x18000b699  jb      short loc_18000B6C6
0x18000b69b  or      ecx, 0FFFFFFFFh; int
0x18000b69e  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b6a3  mov     rcx, [r10+10h]
0x18000b6a7  lea     r8, WPP_31adfde4b55e3bd9a7d2a1b4141c04b1_Traceguids
0x18000b6ae  mov     edx, 17h
0x18000b6b3  mov     [rsp+68h+var_48], esi
0x18000b6b7  mov     r9, rax
0x18000b6ba  call    WPP_SF_sd
0x18000b6bf  mov     r10, cs:WPP_GLOBAL_Control
0x18000b6c6  test    esi, esi
0x18000b6c8  jns     short loc_18000B6EE
0x18000b6ca  cmp     r10, rdi
0x18000b6cd  jz      short loc_18000B6EE
0x18000b6cf  cmp     byte ptr [r10+19h], 2
0x18000b6d4  jb      short loc_18000B6EE
0x18000b6d6  mov     rcx, [r10+10h]
0x18000b6da  lea     r8, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000b6e1  mov     edx, 4Dh ; 'M'
0x18000b6e6  mov     r9d, esi
0x18000b6e9  call    WPP_SF_d
0x18000b6ee  mov     rcx, r12; SRWLock
0x18000b6f1  call    cs:__imp_ReleaseSRWLockExclusive
0x18000b6f7  lea     rcx, [rbp+20h]; SRWLock
0x18000b6fb  call    cs:__imp_ReleaseSRWLockShared
0x18000b701  mov     r10, cs:WPP_GLOBAL_Control
0x18000b708  cmp     r10, rdi
0x18000b70b  jz      short loc_18000B73C
0x18000b70d  test    esi, esi
0x18000b70f  js      short loc_18000B718
0x18000b711  cmp     byte ptr [r10+19h], 6
0x18000b716  jb      short loc_18000B73C
0x18000b718  or      ecx, 0FFFFFFFFh; int
0x18000b71b  call    ?GetIndent@@YAPEBDH@Z; GetIndent(int)
0x18000b720  mov     rcx, [r10+10h]
0x18000b724  lea     r8, WPP_e632221d673033b22bf624a0da3869d5_Traceguids
0x18000b72b  mov     edx, 4Eh ; 'N'
0x18000b730  mov     [rsp+68h+var_48], esi
0x18000b734  mov     r9, rax
0x18000b737  call    WPP_SF_sd
0x18000b73c  mov     eax, esi
0x18000b73e  add     rsp, 30h
0x18000b742  pop     r15
0x18000b744  pop     r14
0x18000b746  pop     r12
0x18000b748  pop     rdi
0x18000b749  pop     rsi
0x18000b74a  pop     rbp
0x18000b74b  pop     rbx
0x18000b74c  retn
```
