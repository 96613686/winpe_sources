# PgmSendRDataCompletion

- ea: `0x1400192d0`
- end: `0x14001941b`
- name: `PgmSendRDataCompletion`
- size: `331`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140005068`
- `0x1400051c8`
- `0x1400067f4`
- `0x140008364`
- `0x140008400`
- `0x1400192d0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400193bf`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400193bf`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400193a0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400193a0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019334`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140019334`

## pseudocode

```c
__int64 __fastcall PgmSendRDataCompletion(__int64 a1, void *a2, int a3)
{
  __int64 v3; // rdi
  KIRQL v7; // r15
  bool v8; // zf

  v3 = *(_QWORD *)(a1 + 48);
  if ( a3 < 0
    && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
  {
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 33, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids, (unsigned int)a3);
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v3 + 360));
  v8 = (*(_WORD *)(a1 + 56))-- == 1;
  if ( v8 && !(unsigned __int8)AnyMoreNaks(a1) )
  {
    if ( *(_QWORD *)(a1 + 32) )
    {
      if ( !*(_QWORD *)(a1 + 40) )
        --*(_DWORD *)(*(_QWORD *)(v3 + 40) + 148LL);
      *(_QWORD *)(a1 + 40) = *(_QWORD *)(a1 + 32) + *(_QWORD *)(*(_QWORD *)(v3 + 40) + 296LL);
    }
    else
    {
      DestroyEntry(*(_QWORD *)(*(_QWORD *)(v3 + 40) + 264LL), a1);
    }
  }
  KeReleaseSpinLock((PKSPIN_LOCK)(v3 + 360), v7);
  if ( a2 )
    ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(*(_QWORD *)(v3 + 40) + 448LL), a2);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x10) != 0 )
    WPP_SF_dq(
      WPP_GLOBAL_Control->AttachedDevice,
      34,
      WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids,
      (unsigned int)a3,
      a2);
  return PgmDereferenceSessionCommon(v3);
}

```

## disassembly

```asm
0x1400192d0  mov     [rsp+arg_0], rbx
0x1400192d5  mov     [rsp+arg_8], rbp
0x1400192da  push    rsi
0x1400192db  push    rdi
0x1400192dc  push    r12
0x1400192de  push    r14
0x1400192e0  push    r15
0x1400192e2  sub     rsp, 30h
0x1400192e6  mov     rdi, [rcx+30h]
0x1400192ea  mov     ebp, r8d
0x1400192ed  lea     r12, WPP_GLOBAL_Control
0x1400192f4  mov     rsi, rdx
0x1400192f7  mov     rbx, rcx
0x1400192fa  test    r8d, r8d
0x1400192fd  jns     short loc_14001932A
0x1400192ff  mov     rcx, cs:WPP_GLOBAL_Control
0x140019306  cmp     rcx, r12
0x140019309  jz      short loc_14001932A
0x14001930b  mov     eax, [rcx+2Ch]
0x14001930e  test    al, 2
0x140019310  jz      short loc_14001932A
0x140019312  mov     rcx, [rcx+18h]
0x140019316  mov     r9d, r8d
0x140019319  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x140019320  mov     edx, 21h ; '!'
0x140019325  call    WPP_SF_d
0x14001932a  lea     r14, [rdi+168h]
0x140019331  mov     rcx, r14; SpinLock
0x140019334  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001933b  nop     dword ptr [rax+rax+00h]
0x140019340  mov     r15b, al
0x140019343  mov     eax, 0FFFFh
0x140019348  add     [rbx+38h], ax
0x14001934c  jnz     short loc_14001939A
0x14001934e  mov     rcx, rbx
0x140019351  call    AnyMoreNaks
0x140019356  test    al, al
0x140019358  jnz     short loc_14001939A
0x14001935a  cmp     qword ptr [rbx+20h], 0
0x14001935f  jz      short loc_140019387
0x140019361  cmp     qword ptr [rbx+28h], 0
0x140019366  jnz     short loc_140019372
0x140019368  mov     rax, [rdi+28h]
0x14001936c  dec     dword ptr [rax+94h]
0x140019372  mov     rax, [rdi+28h]
0x140019376  mov     rcx, [rax+128h]
0x14001937d  add     rcx, [rbx+20h]
0x140019381  mov     [rbx+28h], rcx
0x140019385  jmp     short loc_14001939A
0x140019387  mov     rcx, [rdi+28h]
0x14001938b  mov     rdx, rbx
0x14001938e  mov     rcx, [rcx+108h]
0x140019395  call    DestroyEntry
0x14001939a  mov     dl, r15b; NewIrql
0x14001939d  mov     rcx, r14; SpinLock
0x1400193a0  call    cs:__imp_KeReleaseSpinLock
0x1400193a7  nop     dword ptr [rax+rax+00h]
0x1400193ac  test    rsi, rsi
0x1400193af  jz      short loc_1400193CB
0x1400193b1  mov     rcx, [rdi+28h]
0x1400193b5  mov     rdx, rsi; Entry
0x1400193b8  add     rcx, 1C0h; Lookaside
0x1400193bf  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400193c6  nop     dword ptr [rax+rax+00h]
0x1400193cb  mov     rcx, cs:WPP_GLOBAL_Control
0x1400193d2  cmp     rcx, r12
0x1400193d5  jz      short loc_1400193FB
0x1400193d7  mov     eax, [rcx+2Ch]
0x1400193da  test    al, 10h
0x1400193dc  jz      short loc_1400193FB
0x1400193de  mov     rcx, [rcx+18h]
0x1400193e2  lea     r8, WPP_ad5a23d009db360b9b5fbd08776dfa43_Traceguids
0x1400193e9  mov     edx, 22h ; '"'
0x1400193ee  mov     [rsp+58h+var_38], rsi
0x1400193f3  mov     r9d, ebp
0x1400193f6  call    WPP_SF_dq
0x1400193fb  mov     rcx, rdi
0x1400193fe  call    PgmDereferenceSessionCommon
0x140019403  mov     rbx, [rsp+58h+arg_0]
0x140019408  mov     rbp, [rsp+58h+arg_8]
0x14001940d  add     rsp, 30h
0x140019411  pop     r15
0x140019413  pop     r14
0x140019415  pop     r12
0x140019417  pop     rdi
0x140019418  pop     rsi
0x140019419  retn
```
