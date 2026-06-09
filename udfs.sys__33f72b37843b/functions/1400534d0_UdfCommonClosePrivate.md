# UdfCommonClosePrivate

- ea: `0x1400534d0`
- end: `0x1400537a8`
- name: `UdfCommonClosePrivate`
- size: `728`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140008790`
- `0x140053260`

## callees

- `0x14000c490`
- `0x140011c94`
- `0x140011ce8`
- `0x1400534d0`
- `0x1400537b0`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140053704`
- `ntoskrnl!ExRaiseStatus` at `0x140053704`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140053518`
- `ntoskrnl!ExAcquireResourceSharedLite` at `0x140053518`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005364b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005367a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400536e8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005364b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005367a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400536e8`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053550`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053550`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140053573`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140053573`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053606`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053606`

## pseudocode

```c
char __fastcall UdfCommonClosePrivate(__int64 a1, __int64 a2, __int64 a3, int a4, char a5)
{
  char v5; // bp
  BOOLEAN v7; // dl
  BOOLEAN v11; // dl
  __int64 v12; // rax
  char v13; // dl
  char v15; // al
  const char *v16; // r8
  int v17; // [rsp+20h] [rbp-58h]
  char v18; // [rsp+88h] [rbp+10h] BYREF

  v5 = a5;
  v7 = 0;
  v18 = 0;
  if ( !a5 && (!a1 || (*(_DWORD *)(a1 + 28) & 4) != 0) )
    v7 = 1;
  if ( !ExAcquireResourceSharedLite((PERESOURCE)(a2 + 1480), v7) )
  {
    if ( v5 )
      return 0;
    goto LABEL_28;
  }
  v11 = 0;
  if ( !v5 && (!a1 || (*(_DWORD *)(a1 + 28) & 4) != 0) )
    v11 = 1;
  if ( !ExAcquireResourceExclusiveLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 80LL) + 8LL), v11) )
  {
    if ( v5 )
    {
      ExReleaseResourceLite((PERESOURCE)(a2 + 1480));
      return 0;
    }
LABEL_28:
    *(_DWORD *)(a1 + 24) = -1073741608;
    ExRaiseStatus(-1073741608);
  }
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  *(_QWORD *)(a2 + 1640) = KeGetCurrentThread();
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 8) != 0 )
  {
    v16 = "USER";
    if ( !a4 )
      v16 = "SYS";
    WPP_SF_qsdddd(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      13,
      (_DWORD)v16,
      a3,
      (__int64)v16,
      *(_DWORD *)(a2 + 256),
      *(_DWORD *)(a2 + 260),
      *(_DWORD *)(a3 + 204),
      *(_DWORD *)(a3 + 208));
  }
  v12 = *(_QWORD *)(a3 + 136);
  --*(_DWORD *)(a3 + 204);
  *(_DWORD *)(a3 + 208) -= a4;
  --*(_DWORD *)(*(_QWORD *)(v12 + 8) + 256LL);
  *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 8LL) + 260LL) -= a4;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 8) != 0 )
  {
    WPP_SF_DDDD(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      14,
      WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids,
      *(unsigned int *)(a2 + 256),
      *(_DWORD *)(a2 + 260),
      *(_DWORD *)(a3 + 204),
      *(_DWORD *)(a3 + 208));
  }
  *(_QWORD *)(a2 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(a2 + 1584));
  UdfTeardownStructures(a1, (__int16 *)a3, 0, 0, &v18);
  v13 = v18;
  if ( !v18 )
  {
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*(_QWORD *)(a3 + 136) + 80LL) + 8LL));
    v13 = v18;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 8) != 0 )
  {
    v15 = 70;
    if ( v13 )
      v15 = 84;
    LOBYTE(v17) = v15;
    WPP_SF_qc(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      15,
      WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids,
      a3,
      v17);
  }
  ExReleaseResourceLite((PERESOURCE)(a2 + 1480));
  return 1;
}

```

## disassembly

```asm
0x1400534d0  mov     [rsp+arg_10], rbx
0x1400534d5  push    rbp
0x1400534d6  push    rsi
0x1400534d7  push    rdi
0x1400534d8  push    r14
0x1400534da  push    r15
0x1400534dc  sub     rsp, 50h
0x1400534e0  movzx   ebp, [rsp+78h+arg_20]
0x1400534e8  mov     rsi, rdx
0x1400534eb  xor     dl, dl
0x1400534ed  mov     [rsp+78h+arg_8], 0
0x1400534f5  mov     r15d, r9d
0x1400534f8  mov     rdi, r8
0x1400534fb  mov     rbx, rcx
0x1400534fe  test    bpl, bpl
0x140053501  jnz     short loc_140053511
0x140053503  test    rcx, rcx
0x140053506  jz      short loc_14005350F
0x140053508  mov     eax, [rcx+1Ch]
0x14005350b  test    al, 4
0x14005350d  jz      short loc_140053511
0x14005350f  mov     dl, 1; Wait
0x140053511  lea     rcx, [rsi+5C8h]; Resource
0x140053518  call    cs:__imp_ExAcquireResourceSharedLite
0x14005351f  nop     dword ptr [rax+rax+00h]
0x140053524  test    al, al
0x140053526  jz      loc_1400536D3
0x14005352c  mov     rax, [rdi+88h]
0x140053533  xor     dl, dl
0x140053535  mov     rcx, [rax+50h]
0x140053539  add     rcx, 8; Resource
0x14005353d  test    bpl, bpl
0x140053540  jnz     short loc_140053550
0x140053542  test    rbx, rbx
0x140053545  jz      short loc_14005354E
0x140053547  mov     eax, [rbx+1Ch]
0x14005354a  test    al, 4
0x14005354c  jz      short loc_140053550
0x14005354e  mov     dl, 1; Wait
0x140053550  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053557  nop     dword ptr [rax+rax+00h]
0x14005355c  test    al, al
0x14005355e  jz      loc_1400536DC
0x140053564  lea     rcx, [rsi+630h]; FastMutex
0x14005356b  mov     [rsp+78h+arg_0], r12
0x140053573  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14005357a  nop     dword ptr [rax+rax+00h]
0x14005357f  mov     rax, gs:188h
0x140053588  mov     [rsi+668h], rax
0x14005358f  mov     rcx, cs:WPP_GLOBAL_Control
0x140053596  lea     r12, WPP_GLOBAL_Control
0x14005359d  cmp     rcx, r12
0x1400535a0  jz      short loc_1400535AD
0x1400535a2  mov     eax, [rcx+2Ch]
0x1400535a5  test    al, 8
0x1400535a7  jnz     loc_140053711
0x1400535ad  mov     rax, [rdi+88h]
0x1400535b4  dec     dword ptr [rdi+0CCh]
0x1400535ba  sub     [rdi+0D0h], r15d
0x1400535c1  mov     rcx, [rax+8]
0x1400535c5  dec     dword ptr [rcx+100h]
0x1400535cb  mov     rax, [rdi+88h]
0x1400535d2  mov     rcx, [rax+8]
0x1400535d6  sub     [rcx+104h], r15d
0x1400535dd  mov     rcx, cs:WPP_GLOBAL_Control
0x1400535e4  cmp     rcx, r12
0x1400535e7  jz      short loc_1400535F4
0x1400535e9  mov     eax, [rcx+2Ch]
0x1400535ec  test    al, 8
0x1400535ee  jnz     loc_140053769
0x1400535f4  lea     rcx, [rsi+630h]; FastMutex
0x1400535fb  mov     qword ptr [rsi+668h], 0
0x140053606  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005360d  nop     dword ptr [rax+rax+00h]
0x140053612  lea     rax, [rsp+78h+arg_8]
0x14005361a  xor     r9d, r9d
0x14005361d  xor     r8d, r8d
0x140053620  mov     [rsp+78h+var_58], rax
0x140053625  mov     rdx, rdi
0x140053628  mov     rcx, rbx
0x14005362b  call    UdfTeardownStructures
0x140053630  movzx   edx, [rsp+78h+arg_8]
0x140053638  test    dl, dl
0x14005363a  jnz     short loc_14005365F
0x14005363c  mov     rax, [rdi+88h]
0x140053643  mov     rcx, [rax+50h]
0x140053647  add     rcx, 8; Resource
0x14005364b  call    cs:__imp_ExReleaseResourceLite
0x140053652  nop     dword ptr [rax+rax+00h]
0x140053657  movzx   edx, [rsp+78h+arg_8]
0x14005365f  mov     rcx, cs:WPP_GLOBAL_Control
0x140053666  cmp     rcx, r12
0x140053669  mov     r12, [rsp+78h+arg_0]
0x140053671  jnz     short loc_14005369D
0x140053673  lea     rcx, [rsi+5C8h]; Resource
0x14005367a  call    cs:__imp_ExReleaseResourceLite
0x140053681  nop     dword ptr [rax+rax+00h]
0x140053686  mov     al, 1
0x140053688  mov     rbx, [rsp+78h+arg_10]
0x140053690  add     rsp, 50h
0x140053694  pop     r15
0x140053696  pop     r14
0x140053698  pop     rdi
0x140053699  pop     rsi
0x14005369a  pop     rbp
0x14005369b  retn
0x14005369d  mov     eax, [rcx+2Ch]
0x1400536a0  test    al, 8
0x1400536a2  jz      short loc_140053673
0x1400536a4  mov     rcx, [rcx+18h]
0x1400536a8  lea     r8, WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids
0x1400536af  test    dl, dl
0x1400536b1  mov     eax, 46h ; 'F'
0x1400536b6  mov     r9d, 54h ; 'T'
0x1400536bc  mov     edx, 0Fh
0x1400536c1  cmovnz  eax, r9d
0x1400536c5  mov     r9, rdi
0x1400536c8  mov     byte ptr [rsp+78h+var_58], al
0x1400536cc  call    WPP_SF_qc
0x1400536d1  jmp     short loc_140053673
0x1400536d3  test    bpl, bpl
0x1400536d6  jz      short loc_1400536F8
0x1400536d8  xor     al, al
0x1400536da  jmp     short loc_140053688
0x1400536dc  test    bpl, bpl
0x1400536df  jz      short loc_1400536F8
0x1400536e1  lea     rcx, [rsi+5C8h]; Resource
0x1400536e8  call    cs:__imp_ExReleaseResourceLite
0x1400536ef  nop     dword ptr [rax+rax+00h]
0x1400536f4  xor     al, al
0x1400536f6  jmp     short loc_140053688
0x1400536f8  mov     ecx, 0C00000D8h; Status
0x1400536fd  mov     dword ptr [rbx+18h], 0C00000D8h
0x140053704  call    cs:__imp_ExRaiseStatus
0x140053711  mov     rcx, [rcx+18h]
0x140053715  lea     rax, aSys; "SYS"
0x14005371c  test    r15d, r15d
0x14005371f  lea     r8, aUser; "USER"
0x140053726  mov     edx, 0Dh
0x14005372b  mov     r9, rdi
0x14005372e  cmovz   r8, rax
0x140053732  mov     eax, [rdi+0D0h]
0x140053738  mov     [rsp+78h+var_38], eax
0x14005373c  mov     eax, [rdi+0CCh]
0x140053742  mov     [rsp+78h+var_40], eax
0x140053746  mov     eax, [rsi+104h]
0x14005374c  mov     [rsp+78h+var_48], eax
0x140053750  mov     eax, [rsi+100h]
0x140053756  mov     [rsp+78h+var_50], eax
0x14005375a  mov     [rsp+78h+var_58], r8
0x14005375f  call    WPP_SF_qsdddd
0x140053764  jmp     loc_1400535AD
0x140053769  mov     eax, [rdi+0D0h]
0x14005376f  lea     r8, WPP_48d000ed1a6b379815b8d910c350b5ab_Traceguids
0x140053776  mov     r9d, [rsi+100h]
0x14005377d  mov     edx, 0Eh
0x140053782  mov     rcx, [rcx+18h]
0x140053786  mov     [rsp+78h+var_48], eax
0x14005378a  mov     eax, [rdi+0CCh]
0x140053790  mov     [rsp+78h+var_50], eax
0x140053794  mov     eax, [rsi+104h]
0x14005379a  mov     dword ptr [rsp+78h+var_58], eax
0x14005379e  call    WPP_SF_DDDD
0x1400537a3  jmp     loc_1400535F4
```
