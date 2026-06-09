# FilterSendNetBufferListsCompleteLegacy

- ea: `0x14000ab50`
- end: `0x14000ada2`
- name: `FilterSendNetBufferListsCompleteLegacy`
- size: `594`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x14000a850`

## callees

- `0x14000ab50`
- `0x14000ada8`
- `0x14000cd98`
- `0x14000f150`

## import_xrefs

- `NDIS!NdisFreeCloneNetBufferList` at `0x14000abee`
- `NDIS!NdisFreeCloneNetBufferList` at `0x14000abee`

## pseudocode

```c
void __fastcall FilterSendNetBufferListsCompleteLegacy(__int64 a1, struct _NET_BUFFER_LIST *a2, unsigned int a3)
{
  __int64 v3; // rsi
  unsigned int *v4; // rbx
  __int64 *v5; // r12
  int v6; // ebp
  struct _NET_BUFFER_LIST *v7; // rdi
  __int64 i; // rax
  unsigned int *v9; // r15
  struct _NET_BUFFER_LIST *Alignment; // r13
  __int64 *v11; // r14
  __int64 v12; // rdi
  __int64 v13; // r8
  __int64 v14; // r8
  __int64 v16; // [rsp+78h] [rbp+10h] BYREF
  unsigned int v17; // [rsp+80h] [rbp+18h]

  if ( a2 )
  {
    v17 = a3;
    v3 = 0;
    v4 = 0;
    v16 = 0;
    v5 = &v16;
    v6 = 0;
    v7 = a2;
    for ( i = a1; ; i = a1 )
    {
      v9 = (unsigned int *)v7->ProtocolReserved[0];
      Alignment = (struct _NET_BUFFER_LIST *)v7->Link.Alignment;
      v11 = (__int64 *)v7->ProtocolReserved[1];
      if ( !v9 || !v11 )
      {
        TraceAssert("pFilterMpCtx && OriginalNbl", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3482);
        i = a1;
      }
      if ( v4 != v9 )
      {
        if ( v3 && v4 )
        {
          if ( *((_BYTE *)v4 + 2)
            || (TraceAssert("pLastFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3493),
                v14 = v17,
                *((_BYTE *)v4 + 2)) )
          {
            (*((void (__fastcall **)(_QWORD, __int64))v4 + 9))(*((_QWORD *)v4 + 7), v3);
          }
          _InterlockedAdd((volatile signed __int32 *)v4 + 31, -v6);
          if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
            && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
          {
            WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 221, v14, v4[26], v6);
          }
          i = a1;
        }
        v5 = &v16;
        v6 = 0;
        v4 = v9;
      }
      *v11 = 0;
      ++v6;
      *v5 = (__int64)v11;
      v5 = v11;
      if ( v7->SourceHandle != *(NDIS_HANDLE *)(i + 128) )
        TraceAssert("CurrNbl->SourceHandle == pFilter->FilterHandle", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3521);
      NdisFreeCloneNetBufferList(v7, 2u);
      v7 = Alignment;
      if ( !Alignment )
        break;
      v3 = v16;
    }
    v12 = v16;
    if ( v16 && v4 )
    {
      if ( *((_BYTE *)v4 + 2)
        || (TraceAssert("pLastFilterMpCtx->fMpStarted", "onecoreuap\\net\\vwifi\\filter\\filter.c", 3537),
            *((_BYTE *)v4 + 2)) )
      {
        (*((void (__fastcall **)(_QWORD, __int64, _QWORD))v4 + 9))(*((_QWORD *)v4 + 7), v12, v17);
      }
      _InterlockedAdd((volatile signed __int32 *)v4 + 31, -v6);
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 4) != 0 )
        WPP_SF_Dd(WPP_GLOBAL_Control->AttachedDevice, 222, v13, v4[26], v6);
    }
  }
}

```

## disassembly

```asm
0x14000ab50  test    rdx, rdx
0x14000ab53  jz      locret_14000AC8C
0x14000ab59  mov     r11, rsp
0x14000ab5c  mov     [r11+18h], r8d
0x14000ab60  mov     [r11+8], rcx
0x14000ab64  push    rbx
0x14000ab65  push    rbp
0x14000ab66  push    rsi
0x14000ab67  push    rdi
0x14000ab68  push    r12
0x14000ab6a  sub     rsp, 40h
0x14000ab6e  xor     esi, esi
0x14000ab70  mov     [r11+20h], r13
0x14000ab74  xor     ebx, ebx
0x14000ab76  mov     [r11-30h], r14
0x14000ab7a  mov     [r11+10h], rsi
0x14000ab7e  lea     r12, [r11+10h]
0x14000ab82  xor     ebp, ebp
0x14000ab84  mov     [r11-38h], r15
0x14000ab88  mov     rdi, rdx
0x14000ab8b  mov     rax, rcx
0x14000ab8e  xchg    ax, ax
0x14000ab90  mov     r15, [rdi+40h]
0x14000ab94  mov     r13, [rdi]
0x14000ab97  mov     r14, [rdi+48h]
0x14000ab9b  test    r15, r15
0x14000ab9e  jz      loc_14000AC8E
0x14000aba4  test    r14, r14
0x14000aba7  jz      loc_14000AC8E
0x14000abad  cmp     rbx, r15
0x14000abb0  jz      short loc_14000ABC5
0x14000abb2  test    rsi, rsi
0x14000abb5  jnz     loc_14000ACB9
0x14000abbb  lea     r12, [rsp+68h+arg_8]
0x14000abc0  xor     ebp, ebp
0x14000abc2  mov     rbx, r15
0x14000abc5  mov     qword ptr [r14], 0
0x14000abcc  inc     ebp
0x14000abce  mov     [r12], r14
0x14000abd2  mov     r12, r14
0x14000abd5  mov     rax, [rax+80h]
0x14000abdc  cmp     [rdi+78h], rax
0x14000abe0  jnz     loc_14000AD41
0x14000abe6  mov     edx, 2; FreeCloneFlags
0x14000abeb  mov     rcx, rdi; CloneNetBufferList
0x14000abee  call    cs:__imp_NdisFreeCloneNetBufferList
0x14000abf5  nop     dword ptr [rax+rax+00h]
0x14000abfa  mov     rdi, r13
0x14000abfd  test    r13, r13
0x14000ac00  jz      short loc_14000AC19
0x14000ac02  mov     rsi, [rsp+68h+arg_8]
0x14000ac07  mov     r8d, [rsp+68h+arg_10]
0x14000ac0f  mov     rax, [rsp+68h+arg_0]
0x14000ac14  jmp     loc_14000AB90
0x14000ac19  mov     rdi, [rsp+68h+arg_8]
0x14000ac1e  mov     r15, [rsp+68h+var_38]
0x14000ac23  mov     r14, [rsp+68h+var_30]
0x14000ac28  mov     r13, [rsp+68h+arg_18]
0x14000ac30  test    rdi, rdi
0x14000ac33  jz      short loc_14000AC82
0x14000ac35  test    rbx, rbx
0x14000ac38  jz      short loc_14000AC82
0x14000ac3a  cmp     byte ptr [rbx+2], 0
0x14000ac3e  jz      loc_14000AD5F
0x14000ac44  mov     rax, [rbx+48h]
0x14000ac48  mov     rdx, rdi
0x14000ac4b  mov     r8d, [rsp+68h+arg_10]
0x14000ac53  mov     rcx, [rbx+38h]
0x14000ac57  call    _guard_dispatch_icall
0x14000ac5c  mov     eax, ebp
0x14000ac5e  neg     eax
0x14000ac60  lock add [rbx+7Ch], eax
0x14000ac64  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ac6b  lea     rax, WPP_GLOBAL_Control
0x14000ac72  cmp     rcx, rax
0x14000ac75  jz      short loc_14000AC82
0x14000ac77  mov     eax, [rcx+2Ch]
0x14000ac7a  test    al, 4
0x14000ac7c  jnz     loc_14000AD87
0x14000ac82  add     rsp, 40h
0x14000ac86  pop     r12
0x14000ac88  pop     rdi
0x14000ac89  pop     rsi
0x14000ac8a  pop     rbp
0x14000ac8b  pop     rbx
0x14000ac8c  retn
0x14000ac8e  mov     r8d, 0D9Ah
0x14000ac94  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000ac9b  lea     rcx, aPfiltermpctxOr; "pFilterMpCtx && OriginalNbl"
0x14000aca2  call    TraceAssert
0x14000aca7  mov     r8d, [rsp+68h+arg_10]
0x14000acaf  mov     rax, [rsp+68h+arg_0]
0x14000acb4  jmp     loc_14000ABAD
0x14000acb9  test    rbx, rbx
0x14000acbc  jz      loc_14000ABBB
0x14000acc2  cmp     byte ptr [rbx+2], 0
0x14000acc6  jnz     short loc_14000ACEF
0x14000acc8  mov     r8d, 0DA5h
0x14000acce  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000acd5  lea     rcx, aPlastfiltermpc; "pLastFilterMpCtx->fMpStarted"
0x14000acdc  call    TraceAssert
0x14000ace1  cmp     byte ptr [rbx+2], 0
0x14000ace5  mov     r8d, [rsp+68h+arg_10]
0x14000aced  jz      short loc_14000ACFF
0x14000acef  mov     rax, [rbx+48h]
0x14000acf3  mov     rdx, rsi
0x14000acf6  mov     rcx, [rbx+38h]
0x14000acfa  call    _guard_dispatch_icall
0x14000acff  mov     eax, ebp
0x14000ad01  neg     eax
0x14000ad03  lock add [rbx+7Ch], eax
0x14000ad07  mov     rcx, cs:WPP_GLOBAL_Control
0x14000ad0e  lea     rax, WPP_GLOBAL_Control
0x14000ad15  cmp     rcx, rax
0x14000ad18  jz      short loc_14000AD37
0x14000ad1a  mov     eax, [rcx+2Ch]
0x14000ad1d  test    al, 4
0x14000ad1f  jz      short loc_14000AD37
0x14000ad21  mov     r9d, [rbx+68h]
0x14000ad25  mov     edx, 0DDh
0x14000ad2a  mov     rcx, [rcx+18h]
0x14000ad2e  mov     [rsp+68h+var_48], ebp
0x14000ad32  call    WPP_SF_Dd
0x14000ad37  mov     rax, [rsp+68h+arg_0]
0x14000ad3c  jmp     loc_14000ABBB
0x14000ad41  mov     r8d, 0DC1h
0x14000ad47  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000ad4e  lea     rcx, aCurrnblSourceh; "CurrNbl->SourceHandle == pFilter->Filte"...
0x14000ad55  call    TraceAssert
0x14000ad5a  jmp     loc_14000ABE6
0x14000ad5f  mov     r8d, 0DD1h
0x14000ad65  lea     rdx, aOnecoreuapNetV_1; "onecoreuap\\net\\vwifi\\filter\\filter."...
0x14000ad6c  lea     rcx, aPlastfiltermpc; "pLastFilterMpCtx->fMpStarted"
0x14000ad73  call    TraceAssert
0x14000ad78  cmp     byte ptr [rbx+2], 0
0x14000ad7c  jz      loc_14000AC5C
0x14000ad82  jmp     loc_14000AC44
0x14000ad87  mov     r9d, [rbx+68h]
0x14000ad8b  mov     edx, 0DEh
0x14000ad90  mov     rcx, [rcx+18h]
0x14000ad94  mov     [rsp+68h+var_48], ebp
0x14000ad98  call    WPP_SF_Dd
0x14000ad9d  jmp     loc_14000AC82
```
