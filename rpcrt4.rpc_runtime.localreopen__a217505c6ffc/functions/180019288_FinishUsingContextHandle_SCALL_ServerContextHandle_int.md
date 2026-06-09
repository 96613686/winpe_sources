# FinishUsingContextHandle(SCALL *,ServerContextHandle *,int)

- ea: `0x180019288`
- end: `0x18001952a`
- name: `?FinishUsingContextHandle@@YAXPEAVSCALL@@PEAVServerContextHandle@@H@Z`
- size: `674`
- prototype: `void __fastcall(struct SCALL *, struct ServerContextHandle *, int)`
- caller_count: `6`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180005cd0`
- `0x180018410`
- `0x1800189f0`
- `0x180018fe0`
- `0x18007d814`
- `0x1800c1704`

## callees

- `0x180017d24`
- `0x180017dc0`
- `0x180019288`
- `0x180019530`
- `0x1800196d0`
- `0x1800d7010`

## import_xrefs

- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180019496`
- `ntdll!RtlDeleteElementGenericTableAvl` at `0x180019496`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001946c`
- `ntdll!RtlReleaseSRWLockExclusive` at `0x18001946c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001937c`
- `ntdll!RtlAcquireSRWLockExclusive` at `0x18001937c`

## pseudocode

```c
void __fastcall FinishUsingContextHandle(struct SCALL *a1, struct ServerContextHandle *a2, int a3)
{
  unsigned int i; // eax
  __int64 v5; // rdx
  struct ServerContextHandle *v6; // rdi
  volatile signed __int32 *v7; // r8
  signed __int32 k; // ecx
  signed __int32 v9; // eax
  unsigned int v10; // edx
  int v11; // esi
  int v12; // eax
  PRTL_AVL_TABLE v13; // rcx
  int RightChild; // r8d
  struct _RTL_BALANCED_LINKS *j; // r8
  CHAR *p_Balance; // r10
  unsigned __int64 v17; // rdx
  signed __int32 v18; // eax
  struct _RTL_BALANCED_LINKS *v19; // rax
  struct _RTL_BALANCED_LINKS *Parent; // r8
  struct _RTL_BALANCED_LINKS *v21; // rdx
  struct _RTL_BALANCED_LINKS *v22; // rax
  __int64 v23; // rdx
  signed __int32 v24; // edx
  PRTL_AVL_TABLE Table; // [rsp+40h] [rbp+8h] BYREF
  signed __int32 v26; // [rsp+50h] [rbp+18h]

  Table = 0;
  if ( a2 )
  {
    for ( i = 0; i < *((_DWORD *)a1 + 64); ++i )
    {
      v5 = *((_QWORD *)a1 + 31);
      if ( *(struct ServerContextHandle **)(v5 + 8LL * i) == a2 )
      {
        *(_QWORD *)(v5 + 8LL * i) = 0;
        v6 = a2;
        --*((_DWORD *)a1 + 65);
        if ( (*((_DWORD *)a1 + 58) & 2) != 0 )
        {
          do
          {
            v24 = *((_DWORD *)a2 + 48);
            v26 = v24;
            if ( !(_WORD)v24 )
              break;
            LOWORD(v26) = v24 - 1;
          }
          while ( v24 != _InterlockedCompareExchange((volatile signed __int32 *)a2 + 48, v26, v24) );
          if ( !*((_DWORD *)a1 + 65) )
            *((_DWORD *)a1 + 58) &= ~2u;
        }
        goto LABEL_6;
      }
    }
  }
  v6 = 0;
LABEL_6:
  if ( a3 )
  {
    (*(void (__fastcall **)(struct SCALL *, PRTL_AVL_TABLE *))(*(_QWORD *)a1 + 360LL))(a1, &Table);
    v11 = 0;
    RtlAcquireSRWLockExclusive(&Table[1].BalancedRoot.LeftChild);
    v12 = *((_DWORD *)a2 + 47);
    if ( (v12 & 2) == 0 )
    {
      v13 = Table;
      *((_DWORD *)a2 + 47) = v12 | 2;
      v11 = 1;
      RightChild = (int)v13[1].BalancedRoot.RightChild;
      if ( RightChild )
      {
        if ( RightChild == 1 )
          RtlDeleteElementGenericTableAvl(v13, (char *)a2 + 104);
      }
      else
      {
        for ( j = v13->BalancedRoot.Parent; j != (struct _RTL_BALANCED_LINKS *)v13; j = j->Parent )
        {
          p_Balance = &j[-3].Balance;
          v17 = (unsigned __int64)j[1].Parent - *((_QWORD *)a2 + 13);
          if ( !v17 )
          {
            v17 = (unsigned __int64)j[1].LeftChild - *((_QWORD *)a2 + 14);
            if ( !v17 )
              v17 = LODWORD(j[1].RightChild) - (unsigned __int64)*((unsigned int *)a2 + 30);
          }
          if ( !v17 )
          {
            if ( j != (struct _RTL_BALANCED_LINKS *)72 )
            {
              v19 = j;
              Parent = j->Parent;
              if ( (CHAR *)Parent->LeftChild != p_Balance + 72
                || (v21 = (struct _RTL_BALANCED_LINKS *)*((_QWORD *)p_Balance + 10), v21->Parent != v19) )
              {
                __fastfail(3u);
              }
              v21->Parent = Parent;
              Parent->LeftChild = v21;
              v22 = v13->BalancedRoot.Parent;
              --LODWORD(v13->BalancedRoot.RightChild);
              *(_QWORD *)&v13->BalancedRoot.Balance = v22;
            }
            break;
          }
        }
      }
    }
    RtlReleaseSRWLockExclusive(&Table[1].BalancedRoot.LeftChild);
    if ( v11 )
      ServerContextHandle::RemoveReference(a2);
  }
  if ( !v6 )
    goto LABEL_13;
  v7 = (volatile signed __int32 *)((char *)a2 + 136);
  if ( *((_DWORD *)a2 + 42) )
  {
    *((_DWORD *)a2 + 42) = 0;
    for ( k = 1; (k & 2) == 0; k = v9 )
    {
      v9 = _InterlockedCompareExchange(v7, 0, k);
      if ( k == v9 )
      {
        if ( (k & 1) != 0 )
          goto LABEL_13;
LABEL_30:
        __fastfail(0x24u);
      }
    }
    v23 = 1;
    goto LABEL_40;
  }
  v18 = _InterlockedExchangeAdd(v7, 0xFFFFFFFC);
  if ( (v18 & 2) != 0 )
  {
    v23 = 0;
LABEL_40:
    SWMRLock::Wake((char *)a2 + 136, v23);
    goto LABEL_13;
  }
  if ( (v18 & 0xFFFFFFFC) == 0 || (v18 & 1) != 0 )
    goto LABEL_30;
LABEL_13:
  if ( !(unsigned int)ServerContextHandle::RemoveReference(a2) )
  {
    if ( (*((_BYTE *)a2 + 188) & 4) != 0 )
      NDRSRundownContextHandle(a2);
    ServerContextHandle::`scalar deleting destructor'(a2, v10);
  }
}

```

## disassembly

```asm
0x180019288  mov     [rsp+arg_8], rbx
0x18001928d  mov     [rsp+arg_18], rbp
0x180019292  push    rsi
0x180019293  push    rdi
0x180019294  push    r14
0x180019296  sub     rsp, 20h
0x18001929a  xor     ebp, ebp
0x18001929c  mov     rbx, rdx
0x18001929f  mov     [rsp+38h+Table], rbp
0x1800192a4  mov     r9, rcx
0x1800192a7  lea     r14d, [rbp+1]
0x1800192ab  test    rdx, rdx
0x1800192ae  jz      loc_18001950E
0x1800192b4  mov     eax, ebp
0x1800192b6  cmp     eax, [r9+100h]
0x1800192bd  jnb     loc_18001950E
0x1800192c3  mov     rdx, [r9+0F8h]
0x1800192ca  mov     ecx, eax
0x1800192cc  cmp     [rdx+rcx*8], rbx
0x1800192d0  jnz     loc_18001951B
0x1800192d6  mov     [rdx+rcx*8], rbp
0x1800192da  mov     rdi, rbx
0x1800192dd  dec     dword ptr [r9+104h]
0x1800192e4  mov     eax, [r9+0E8h]
0x1800192eb  test    al, 2
0x1800192ed  jnz     loc_1800194C0
0x1800192f3  test    r8d, r8d
0x1800192f6  jnz     short loc_18001935A
0x1800192f8  test    rdi, rdi
0x1800192fb  jz      short loc_180019336
0x1800192fd  lea     r8, [rbx+88h]
0x180019304  cmp     [r8+20h], ebp
0x180019308  jz      loc_180019406
0x18001930e  mov     [r8+20h], ebp
0x180019312  mov     ecx, r14d
0x180019315  test    cl, 2
0x180019318  jnz     loc_180019516
0x18001931e  mov     edx, ebp
0x180019320  mov     eax, ecx
0x180019322  lock cmpxchg [r8], edx
0x180019327  jnz     loc_180019507
0x18001932d  test    r14b, cl
0x180019330  jz      loc_180019428
0x180019336  mov     rcx, rbx; this
0x180019339  call    ?RemoveReference@ServerContextHandle@@QEAAJXZ; ServerContextHandle::RemoveReference(void)
0x18001933e  test    eax, eax
0x180019340  jz      loc_1800193EC
0x180019346  mov     rbx, [rsp+38h+arg_8]
0x18001934b  mov     rbp, [rsp+38h+arg_18]
0x180019350  add     rsp, 20h
0x180019354  pop     r14
0x180019356  pop     rdi
0x180019357  pop     rsi
0x180019358  retn
0x18001935a  mov     rax, [r9]
0x18001935d  lea     rdx, [rsp+38h+Table]
0x180019362  mov     rcx, r9
0x180019365  mov     rax, [rax+168h]
0x18001936c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019371  mov     rcx, [rsp+38h+Table]
0x180019376  mov     esi, ebp
0x180019378  add     rcx, 70h ; 'p'
0x18001937c  call    cs:__imp_RtlAcquireSRWLockExclusive
0x180019383  nop     dword ptr [rax+rax+00h]
0x180019388  mov     eax, [rbx+0BCh]
0x18001938e  test    al, 2
0x180019390  jnz     loc_180019463
0x180019396  mov     rcx, [rsp+38h+Table]; Table
0x18001939b  or      eax, 2
0x18001939e  mov     [rbx+0BCh], eax
0x1800193a4  mov     esi, r14d
0x1800193a7  mov     r8d, [rcx+78h]
0x1800193ab  test    r8d, r8d
0x1800193ae  jnz     loc_18001948D
0x1800193b4  mov     r8, [rcx]
0x1800193b7  cmp     r8, rcx
0x1800193ba  jz      loc_180019463
0x1800193c0  mov     rdx, [r8+20h]
0x1800193c4  lea     r10, [r8-48h]
0x1800193c8  sub     rdx, [rbx+68h]
0x1800193cc  jnz     short loc_1800193E2
0x1800193ce  mov     rdx, [r8+28h]
0x1800193d2  sub     rdx, [rbx+70h]
0x1800193d6  jnz     short loc_1800193E2
0x1800193d8  mov     edx, [r8+30h]
0x1800193dc  mov     eax, [rbx+78h]
0x1800193df  sub     rdx, rax
0x1800193e2  test    rdx, rdx
0x1800193e5  jz      short loc_18001942F
0x1800193e7  mov     r8, [r8]
0x1800193ea  jmp     short loc_1800193B7
0x1800193ec  test    byte ptr [rbx+0BCh], 4
0x1800193f3  jnz     loc_1800194B3
0x1800193f9  mov     rcx, rbx; this
0x1800193fc  call    ??_GServerContextHandle@@QEAAPEAXI@Z; ServerContextHandle::`scalar deleting destructor'(uint)
0x180019401  jmp     loc_180019346
0x180019406  mov     eax, 0FFFFFFFCh
0x18001940b  lock xadd [r8], eax
0x180019410  test    al, 2
0x180019412  jnz     loc_1800194A4
0x180019418  test    eax, 0FFFFFFFCh
0x18001941d  jbe     short loc_180019428
0x18001941f  test    r14b, al
0x180019422  jz      loc_180019336
0x180019428  mov     ecx, 24h ; '$'
0x18001942d  int     29h; Win8: RtlFailFast(ecx)
0x18001942f  test    r10, r10
0x180019432  jz      short loc_180019463
0x180019434  lea     rax, [r10+48h]
0x180019438  mov     r8, [rax]
0x18001943b  cmp     [r8+8], rax
0x18001943f  jnz     loc_180019523
0x180019445  mov     rdx, [rax+8]
0x180019449  cmp     [rdx], rax
0x18001944c  jnz     loc_180019523
0x180019452  mov     [rdx], r8
0x180019455  mov     [r8+8], rdx
0x180019459  mov     rax, [rcx]
0x18001945c  dec     dword ptr [rcx+10h]
0x18001945f  mov     [rcx+18h], rax
0x180019463  mov     rcx, [rsp+38h+Table]
0x180019468  add     rcx, 70h ; 'p'
0x18001946c  call    cs:__imp_RtlReleaseSRWLockExclusive
0x180019473  nop     dword ptr [rax+rax+00h]
0x180019478  test    esi, esi
0x18001947a  jz      loc_1800192F8
0x180019480  mov     rcx, rbx; this
0x180019483  call    ?RemoveReference@ServerContextHandle@@QEAAJXZ; ServerContextHandle::RemoveReference(void)
0x180019488  jmp     loc_1800192F8
0x18001948d  cmp     r8d, esi
0x180019490  jnz     short loc_180019463
0x180019492  lea     rdx, [rbx+68h]; Buffer
0x180019496  call    cs:__imp_RtlDeleteElementGenericTableAvl
0x18001949d  nop     dword ptr [rax+rax+00h]
0x1800194a2  jmp     short loc_180019463
0x1800194a4  xor     edx, edx
0x1800194a6  mov     rcx, r8
0x1800194a9  call    ?Wake@SWMRLock@@AEAAXW4RequestorType@1@@Z; SWMRLock::Wake(SWMRLock::RequestorType)
0x1800194ae  jmp     loc_180019336
0x1800194b3  mov     rcx, rbx; struct ServerContextHandle *
0x1800194b6  call    ?NDRSRundownContextHandle@@YAXPEAVServerContextHandle@@@Z; NDRSRundownContextHandle(ServerContextHandle *)
0x1800194bb  jmp     loc_1800193F9
0x1800194c0  mov     edx, [rbx+0C0h]
0x1800194c6  mov     [rsp+38h+arg_10], edx
0x1800194ca  test    dx, dx
0x1800194cd  jz      short loc_1800194ED
0x1800194cf  movzx   eax, dx
0x1800194d2  sub     ax, r14w
0x1800194d6  mov     word ptr [rsp+38h+arg_10], ax
0x1800194db  mov     eax, edx
0x1800194dd  mov     ecx, [rsp+38h+arg_10]
0x1800194e1  lock cmpxchg [rbx+0C0h], ecx
0x1800194e9  cmp     edx, eax
0x1800194eb  jnz     short loc_1800194C0
0x1800194ed  cmp     [r9+104h], ebp
0x1800194f4  jnz     loc_1800192F3
0x1800194fa  and     dword ptr [r9+0E8h], 0FFFFFFFDh
0x180019502  jmp     loc_1800192F3
0x180019507  mov     ecx, eax
0x180019509  jmp     loc_180019315
0x18001950e  mov     rdi, rbp
0x180019511  jmp     loc_1800192F3
0x180019516  mov     edx, r14d
0x180019519  jmp     short loc_1800194A6
0x18001951b  add     eax, r14d
0x18001951e  jmp     loc_1800192B6
0x180019523  mov     ecx, 3
0x180019528  int     29h; Win8: RtlFailFast(ecx)
```
