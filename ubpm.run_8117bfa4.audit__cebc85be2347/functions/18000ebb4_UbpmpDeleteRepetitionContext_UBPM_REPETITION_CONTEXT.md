# UbpmpDeleteRepetitionContext(_UBPM_REPETITION_CONTEXT * *)

- ea: `0x18000ebb4`
- end: `0x18000ec7e`
- name: `?UbpmpDeleteRepetitionContext@@YAXPEAPEAU_UBPM_REPETITION_CONTEXT@@@Z`
- size: `202`
- prototype: `void __fastcall(struct _UBPM_REPETITION_CONTEXT **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e690`
- `0x18000fea0`
- `0x180024d08`

## callees

- `0x18000ebb4`
- `0x18000fbf0`

## import_xrefs

- `EventAggregation!EaDeleteAggregation` at `0x18000ec49`
- `EventAggregation!EaDeleteAggregation` at `0x18000ec57`
- `EventAggregation!EaDeleteAggregation` at `0x18000ec65`
- `EventAggregation!EaDeleteAggregation` at `0x18000ec49`
- `EventAggregation!EaDeleteAggregation` at `0x18000ec57`
- `EventAggregation!EaDeleteAggregation` at `0x18000ec65`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000ebe9`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000ec11`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000ebe9`
- `TimeBrokerClient!TbDeleteCEvent` at `0x18000ec11`

## pseudocode

```c
void __fastcall UbpmpDeleteRepetitionContext(struct _UBPM_REPETITION_CONTEXT **a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v4; // rbx
  __int64 v6; // rdx
  __int64 v7; // r8
  __int64 v8; // r9

  if ( a1 )
  {
    v4 = (__int64)*a1;
    if ( *a1 )
    {
      if ( *(_QWORD *)(v4 + 64) )
        EaDeleteAggregation();
      if ( *(_DWORD *)(v4 + 72) || *(_DWORD *)(v4 + 76) )
        TbDeleteCEvent(*(_QWORD *)(v4 + 72));
      if ( *(_QWORD *)(v4 + 40) )
        EaDeleteAggregation();
      if ( *(_QWORD *)(v4 + 56) )
        EaDeleteAggregation();
      if ( *(_DWORD *)(v4 + 48) || *(_DWORD *)(v4 + 52) )
        TbDeleteCEvent(*(_QWORD *)(v4 + 48));
      UBPM_MIDL_user_free(*(_QWORD *)(v4 + 88), a2, a3, a4);
      UBPM_MIDL_user_free(v4, v6, v7, v8);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x18000ebb4  test    rcx, rcx
0x18000ebb7  jz      locret_18000EC3F
0x18000ebbd  mov     [rsp+arg_0], rbx
0x18000ebc2  push    rdi
0x18000ebc3  sub     rsp, 20h
0x18000ebc7  mov     rbx, [rcx]
0x18000ebca  mov     rdi, rcx
0x18000ebcd  test    rbx, rbx
0x18000ebd0  jz      short loc_18000EC2E
0x18000ebd2  mov     rcx, [rbx+40h]
0x18000ebd6  test    rcx, rcx
0x18000ebd9  jnz     loc_18000EC65
0x18000ebdf  cmp     dword ptr [rbx+48h], 0
0x18000ebe3  jz      short loc_18000EC41
0x18000ebe5  mov     rcx, [rbx+48h]
0x18000ebe9  call    cs:__imp_TbDeleteCEvent
0x18000ebf0  nop     dword ptr [rax+rax+00h]
0x18000ebf5  mov     rcx, [rbx+28h]
0x18000ebf9  test    rcx, rcx
0x18000ebfc  jnz     short loc_18000EC57
0x18000ebfe  mov     rcx, [rbx+38h]
0x18000ec02  test    rcx, rcx
0x18000ec05  jnz     short loc_18000EC49
0x18000ec07  cmp     dword ptr [rbx+30h], 0
0x18000ec0b  jz      short loc_18000EC76
0x18000ec0d  mov     rcx, [rbx+30h]
0x18000ec11  call    cs:__imp_TbDeleteCEvent
0x18000ec18  nop     dword ptr [rax+rax+00h]
0x18000ec1d  mov     rcx, [rbx+58h]
0x18000ec21  call    UBPM_MIDL_user_free
0x18000ec26  mov     rcx, rbx
0x18000ec29  call    UBPM_MIDL_user_free
0x18000ec2e  mov     rbx, [rsp+28h+arg_0]
0x18000ec33  mov     qword ptr [rdi], 0
0x18000ec3a  add     rsp, 20h
0x18000ec3e  pop     rdi
0x18000ec3f  retn
0x18000ec41  cmp     dword ptr [rbx+4Ch], 0
0x18000ec45  jz      short loc_18000EBF5
0x18000ec47  jmp     short loc_18000EBE5
0x18000ec49  call    cs:__imp_EaDeleteAggregation
0x18000ec50  nop     dword ptr [rax+rax+00h]
0x18000ec55  jmp     short loc_18000EC07
0x18000ec57  call    cs:__imp_EaDeleteAggregation
0x18000ec5e  nop     dword ptr [rax+rax+00h]
0x18000ec63  jmp     short loc_18000EBFE
0x18000ec65  call    cs:__imp_EaDeleteAggregation
0x18000ec6c  nop     dword ptr [rax+rax+00h]
0x18000ec71  jmp     loc_18000EBDF
0x18000ec76  cmp     dword ptr [rbx+34h], 0
0x18000ec7a  jz      short loc_18000EC1D
0x18000ec7c  jmp     short loc_18000EC0D
```
