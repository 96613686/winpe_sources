# wsm_stable_path::assign(ushort const *)

- ea: `0x14000c410`
- end: `0x14000c561`
- name: `?assign@wsm_stable_path@@UEAAJPEBG@Z`
- size: `337`
- prototype: `__int64 __fastcall(wsm_stable_path *__hidden this, PCWSTR SourceString)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14000960c`
- `0x14000b550`

## callees

- `0x14000c410`
- `0x14000ce88`
- `0x14000dc24`
- `0x14000eb0c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14000c458`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c539`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c458`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c46a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c4f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c50f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000c539`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4aa`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000c4aa`

## pseudocode

```c
__int64 __fastcall wsm_stable_path::assign(wsm_stable_path *this, PCWSTR SourceString)
{
  void **v2; // rdi
  int StablePathWithFallback; // ebx
  void *v6; // rcx
  PVOID *v7; // rsi
  void *v8; // rdi
  int v9; // eax
  PVOID v10; // rcx
  PVOID P[2]; // [rsp+20h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _UNICODE_STRING v14; // [rsp+40h] [rbp-30h] BYREF
  void *v15; // [rsp+50h] [rbp-20h] BYREF
  PVOID *v16; // [rsp+58h] [rbp-18h]
  PVOID v17; // [rsp+A0h] [rbp+30h] BYREF

  v2 = (void **)*((_QWORD *)this + 1);
  StablePathWithFallback = 0;
  *((_QWORD *)this + 1) = 0;
  if ( v2 )
  {
    v6 = *v2;
    if ( *v2 != v2 + 2 && v6 )
      ExFreePoolWithTag(v6, 0x6E6D7377u);
    ExFreePoolWithTag(v2, 0x6E6D7377u);
  }
  if ( SourceString )
  {
    v17 = 0;
    v7 = &v17;
    v8 = 0;
    v16 = &v17;
    v15 = 0;
    DestinationString = 0;
    *(_OWORD *)P = 0;
    v14 = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    StablePathWithFallback = GetStablePathWithFallback(&DestinationString, (PUNICODE_STRING)P, &v14);
    if ( StablePathWithFallback >= 0 )
    {
      v9 = Duplicate(P, &v15);
      v7 = v16;
      StablePathWithFallback = v9;
      v8 = v15;
    }
    if ( P[1] )
      ExFreePoolWithTag(P[1], 0x6E6D7377u);
    if ( v8 )
    {
      v10 = *v7;
      *v7 = v8;
      if ( v10 )
        ExFreePoolWithTag(v10, 0x6E6D7377u);
    }
    if ( StablePathWithFallback >= 0 )
      StablePathWithFallback = wsm_wstring::init(this, (const unsigned __int16 *)v17);
    if ( v17 )
      ExFreePoolWithTag(v17, 0x6E6D7377u);
  }
  return (unsigned int)StablePathWithFallback;
}

```

## disassembly

```asm
0x14000c410  mov     [rsp-28h+arg_8], rbx
0x14000c415  mov     [rsp-28h+arg_10], rsi
0x14000c41a  push    rbp
0x14000c41b  push    rdi
0x14000c41c  push    r12
0x14000c41e  push    r14
0x14000c420  push    r15
0x14000c422  mov     rbp, rsp
0x14000c425  sub     rsp, 70h
0x14000c429  mov     rdi, [rcx+8]
0x14000c42d  xor     ebx, ebx
0x14000c42f  mov     [rcx+8], rbx
0x14000c433  mov     r15, rdx
0x14000c436  mov     r14, rcx
0x14000c439  mov     r12d, 6E6D7377h
0x14000c43f  test    rdi, rdi
0x14000c442  jz      short loc_14000C476
0x14000c444  mov     rcx, [rdi]; P
0x14000c447  lea     rax, [rdi+10h]
0x14000c44b  cmp     rcx, rax
0x14000c44e  jz      short loc_14000C464
0x14000c450  test    rcx, rcx
0x14000c453  jz      short loc_14000C464
0x14000c455  mov     edx, r12d; Tag
0x14000c458  call    cs:__imp_ExFreePoolWithTag
0x14000c45f  nop     dword ptr [rax+rax+00h]
0x14000c464  mov     edx, r12d; Tag
0x14000c467  mov     rcx, rdi; P
0x14000c46a  call    cs:__imp_ExFreePoolWithTag
0x14000c471  nop     dword ptr [rax+rax+00h]
0x14000c476  test    r15, r15
0x14000c479  jz      loc_14000C545
0x14000c47f  xorps   xmm0, xmm0
0x14000c482  mov     [rbp+arg_0], rbx
0x14000c486  xorps   xmm1, xmm1
0x14000c489  lea     rsi, [rbp+arg_0]
0x14000c48d  xor     edi, edi
0x14000c48f  mov     [rbp+var_18], rsi
0x14000c493  mov     rdx, r15; SourceString
0x14000c496  mov     [rbp+var_20], rdi
0x14000c49a  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000c49e  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000c4a2  movups  xmmword ptr [rbp+P], xmm1
0x14000c4a6  movups  xmmword ptr [rbp+var_30.Length], xmm0
0x14000c4aa  call    cs:__imp_RtlInitUnicodeString
0x14000c4b1  nop     dword ptr [rax+rax+00h]
0x14000c4b6  lea     r8, [rbp+var_30]; struct _UNICODE_STRING *
0x14000c4ba  lea     rdx, [rbp+P]; DestinationString
0x14000c4be  lea     rcx, [rbp+DestinationString]; String2
0x14000c4c2  call    ?GetStablePathWithFallback@@YAJPEBU_UNICODE_STRING@@PEAU1@1@Z; GetStablePathWithFallback(_UNICODE_STRING const *,_UNICODE_STRING *,_UNICODE_STRING *)
0x14000c4c7  mov     ebx, eax
0x14000c4c9  test    eax, eax
0x14000c4cb  js      short loc_14000C4E4
0x14000c4cd  lea     rdx, [rbp+var_20]
0x14000c4d1  lea     rcx, [rbp+P]
0x14000c4d5  call    Duplicate
0x14000c4da  mov     rsi, [rbp+var_18]
0x14000c4de  mov     ebx, eax
0x14000c4e0  mov     rdi, [rbp+var_20]
0x14000c4e4  mov     rcx, [rbp+P+8]; P
0x14000c4e8  test    rcx, rcx
0x14000c4eb  jz      short loc_14000C4FC
0x14000c4ed  mov     edx, r12d; Tag
0x14000c4f0  call    cs:__imp_ExFreePoolWithTag
0x14000c4f7  nop     dword ptr [rax+rax+00h]
0x14000c4fc  test    rdi, rdi
0x14000c4ff  jz      short loc_14000C51B
0x14000c501  mov     rcx, [rsi]; P
0x14000c504  mov     [rsi], rdi
0x14000c507  test    rcx, rcx
0x14000c50a  jz      short loc_14000C51B
0x14000c50c  mov     edx, r12d; Tag
0x14000c50f  call    cs:__imp_ExFreePoolWithTag
0x14000c516  nop     dword ptr [rax+rax+00h]
0x14000c51b  test    ebx, ebx
0x14000c51d  js      short loc_14000C52D
0x14000c51f  mov     rdx, [rbp+arg_0]; unsigned __int16 *
0x14000c523  mov     rcx, r14; this
0x14000c526  call    ?init@wsm_wstring@@IEAAJPEBG@Z; wsm_wstring::init(ushort const *)
0x14000c52b  mov     ebx, eax
0x14000c52d  mov     rcx, [rbp+arg_0]; P
0x14000c531  test    rcx, rcx
0x14000c534  jz      short loc_14000C545
0x14000c536  mov     edx, r12d; Tag
0x14000c539  call    cs:__imp_ExFreePoolWithTag
0x14000c540  nop     dword ptr [rax+rax+00h]
0x14000c545  lea     r11, [rsp+70h+var_s0]
0x14000c54a  mov     eax, ebx
0x14000c54c  mov     rbx, [r11+38h]
0x14000c550  mov     rsi, [r11+40h]
0x14000c554  mov     rsp, r11
0x14000c557  pop     r15
0x14000c559  pop     r14
0x14000c55b  pop     r12
0x14000c55d  pop     rdi
0x14000c55e  pop     rbp
0x14000c55f  retn
```
