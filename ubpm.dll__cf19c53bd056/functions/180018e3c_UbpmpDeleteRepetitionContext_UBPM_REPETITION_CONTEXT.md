# UbpmpDeleteRepetitionContext(_UBPM_REPETITION_CONTEXT * *)

- ea: `0x180018e3c`
- end: `0x180018edc`
- name: `?UbpmpDeleteRepetitionContext@@YAXPEAPEAU_UBPM_REPETITION_CONTEXT@@@Z`
- size: `160`
- prototype: `void __fastcall(struct _UBPM_REPETITION_CONTEXT **)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013244`
- `0x180013510`
- `0x180018ad0`

## callees

- `0x180018e3c`
- `0x180019d90`

## import_xrefs

- `EventAggregation!EaDeleteAggregation` at `0x180018ebc`
- `EventAggregation!EaDeleteAggregation` at `0x180018ec4`
- `EventAggregation!EaDeleteAggregation` at `0x180018ecc`
- `EventAggregation!EaDeleteAggregation` at `0x180018ebc`
- `EventAggregation!EaDeleteAggregation` at `0x180018ec4`
- `EventAggregation!EaDeleteAggregation` at `0x180018ecc`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180018e69`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180018e8b`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180018e69`
- `TimeBrokerClient!TbDeleteCEvent` at `0x180018e8b`

## pseudocode

```c
void __fastcall UbpmpDeleteRepetitionContext(struct _UBPM_REPETITION_CONTEXT **a1)
{
  __int64 v1; // rbx

  if ( a1 )
  {
    v1 = (__int64)*a1;
    if ( *a1 )
    {
      if ( *(_QWORD *)(v1 + 64) )
        EaDeleteAggregation();
      if ( *(_DWORD *)(v1 + 72) || *(_DWORD *)(v1 + 76) )
        TbDeleteCEvent(*(_QWORD *)(v1 + 72));
      if ( *(_QWORD *)(v1 + 40) )
        EaDeleteAggregation();
      if ( *(_QWORD *)(v1 + 56) )
        EaDeleteAggregation();
      if ( *(_DWORD *)(v1 + 48) || *(_DWORD *)(v1 + 52) )
        TbDeleteCEvent(*(_QWORD *)(v1 + 48));
      UBPM_MIDL_user_free(*(_QWORD *)(v1 + 88));
      UBPM_MIDL_user_free(v1);
    }
    *a1 = 0;
  }
}

```

## disassembly

```asm
0x180018e3c  test    rcx, rcx
0x180018e3f  jz      short locret_180018EB3
0x180018e41  mov     [rsp+arg_0], rbx
0x180018e46  push    rdi
0x180018e47  sub     rsp, 20h
0x180018e4b  mov     rbx, [rcx]
0x180018e4e  mov     rdi, rcx
0x180018e51  test    rbx, rbx
0x180018e54  jz      short loc_180018EA2
0x180018e56  mov     rcx, [rbx+40h]
0x180018e5a  test    rcx, rcx
0x180018e5d  jnz     short loc_180018ECC
0x180018e5f  cmp     dword ptr [rbx+48h], 0
0x180018e63  jz      short loc_180018EB4
0x180018e65  mov     rcx, [rbx+48h]
0x180018e69  call    cs:__imp_TbDeleteCEvent
0x180018e6f  mov     rcx, [rbx+28h]
0x180018e73  test    rcx, rcx
0x180018e76  jnz     short loc_180018EC4
0x180018e78  mov     rcx, [rbx+38h]
0x180018e7c  test    rcx, rcx
0x180018e7f  jnz     short loc_180018EBC
0x180018e81  cmp     dword ptr [rbx+30h], 0
0x180018e85  jz      short loc_180018ED4
0x180018e87  mov     rcx, [rbx+30h]
0x180018e8b  call    cs:__imp_TbDeleteCEvent
0x180018e91  mov     rcx, [rbx+58h]
0x180018e95  call    UBPM_MIDL_user_free
0x180018e9a  mov     rcx, rbx
0x180018e9d  call    UBPM_MIDL_user_free
0x180018ea2  mov     rbx, [rsp+28h+arg_0]
0x180018ea7  mov     qword ptr [rdi], 0
0x180018eae  add     rsp, 20h
0x180018eb2  pop     rdi
0x180018eb3  retn
0x180018eb4  cmp     dword ptr [rbx+4Ch], 0
0x180018eb8  jz      short loc_180018E6F
0x180018eba  jmp     short loc_180018E65
0x180018ebc  call    cs:__imp_EaDeleteAggregation
0x180018ec2  jmp     short loc_180018E81
0x180018ec4  call    cs:__imp_EaDeleteAggregation
0x180018eca  jmp     short loc_180018E78
0x180018ecc  call    cs:__imp_EaDeleteAggregation
0x180018ed2  jmp     short loc_180018E5F
0x180018ed4  cmp     dword ptr [rbx+34h], 0
0x180018ed8  jz      short loc_180018E91
0x180018eda  jmp     short loc_180018E87
```
