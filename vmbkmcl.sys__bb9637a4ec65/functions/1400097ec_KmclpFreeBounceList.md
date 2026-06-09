# KmclpFreeBounceList

- ea: `0x1400097ec`
- end: `0x14000991a`
- name: `KmclpFreeBounceList`
- size: `302`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `4`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x1400026f0`
- `0x1400037e0`
- `0x140005b90`
- `0x14000933c`

## callees

- `0x1400097ec`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400098e9`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400098e9`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140009876`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x140009876`

## pseudocode

```c
void __fastcall KmclpFreeBounceList(__int64 a1, _QWORD *a2)
{
  _QWORD *v2; // rsi
  _QWORD *v4; // r15
  __int64 **v5; // r14
  __int64 *v6; // rdi
  __int64 *v7; // rax
  __int64 v8; // rax
  __int64 **v9; // rcx
  __int64 v10; // rax
  __int64 v11; // rbx
  __int64 v12; // rax
  __int64 v13; // rcx
  _QWORD *v14; // rdx
  _QWORD *v15; // rdx
  _QWORD *v16; // rax
  void *v17; // rdx

  v2 = a2;
  if ( a2 )
  {
    do
    {
      v4 = (_QWORD *)*v2;
      v5 = (__int64 **)(v2 + 2);
      while ( 1 )
      {
        v6 = *v5;
        if ( *v5 == (__int64 *)v5 )
          break;
        if ( (__int64 **)v6[1] != v5
          || (v7 = (__int64 *)*v6, *(__int64 **)(*v6 + 8) != v6)
          || (*v5 = v7, v7[1] = (__int64)v5, v8 = v6[3] + 16, v9 = *(__int64 ***)(v6[3] + 24), *v9 != (__int64 *)v8) )
        {
LABEL_17:
          __fastfail(3u);
        }
        *v6 = v8;
        v6[1] = (__int64)v9;
        *v9 = v6;
        *(_QWORD *)(v8 + 8) = v6;
        --*(_DWORD *)(v6[3] + 40);
        v10 = v6[3];
        if ( !*(_DWORD *)(v10 + 40) && !*(_BYTE *)(v10 + 49) )
        {
          v11 = v6[3];
          *(_QWORD *)(v11 + 56) = KeQueryUnbiasedInterruptTime();
        }
        v12 = v6[3];
        if ( *(_BYTE *)(v12 + 50) )
        {
          v13 = *(_QWORD *)v12;
          if ( *(_QWORD *)(*(_QWORD *)v12 + 8LL) != v12 )
            goto LABEL_17;
          v14 = *(_QWORD **)(v12 + 8);
          if ( *v14 != v12 )
            goto LABEL_17;
          *v14 = v13;
          *(_QWORD *)(v13 + 8) = v14;
          v15 = *(_QWORD **)(a1 + 2912);
          if ( *v15 != a1 + 2904 )
            goto LABEL_17;
          v16 = (_QWORD *)v6[3];
          *v16 = a1 + 2904;
          v16[1] = v15;
          *v15 = v16;
          *(_QWORD *)(a1 + 2912) = v16;
          *(_BYTE *)(v6[3] + 50) = 0;
        }
      }
      v17 = v2;
      v2 = v4;
      ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)(a1 + 2944), v17);
    }
    while ( v4 );
  }
  ++*(_QWORD *)(a1 + 576);
}

```

## disassembly

```asm
0x1400097ec  push    rbx
0x1400097ee  push    rbp
0x1400097ef  push    rsi
0x1400097f0  push    rdi
0x1400097f1  push    r14
0x1400097f3  push    r15
0x1400097f5  sub     rsp, 28h
0x1400097f9  mov     rsi, rdx
0x1400097fc  mov     rbp, rcx
0x1400097ff  test    rdx, rdx
0x140009802  jz      loc_1400098FE
0x140009808  mov     r15, [rsi]
0x14000980b  lea     r14, [rsi+10h]
0x14000980f  mov     rdi, [r14]
0x140009812  cmp     rdi, r14
0x140009815  jz      loc_1400098DC
0x14000981b  cmp     [rdi+8], r14
0x14000981f  jnz     loc_140009913
0x140009825  mov     rax, [rdi]
0x140009828  cmp     [rax+8], rdi
0x14000982c  jnz     loc_140009913
0x140009832  mov     [r14], rax
0x140009835  mov     [rax+8], r14
0x140009839  mov     rax, [rdi+18h]
0x14000983d  add     rax, 10h
0x140009841  mov     rcx, [rax+8]
0x140009845  cmp     [rcx], rax
0x140009848  jnz     loc_140009913
0x14000984e  mov     [rdi], rax
0x140009851  mov     [rdi+8], rcx
0x140009855  mov     [rcx], rdi
0x140009858  mov     [rax+8], rdi
0x14000985c  mov     rax, [rdi+18h]
0x140009860  dec     dword ptr [rax+28h]
0x140009863  mov     rax, [rdi+18h]
0x140009867  cmp     dword ptr [rax+28h], 0
0x14000986b  jnz     short loc_140009886
0x14000986d  cmp     byte ptr [rax+31h], 0
0x140009871  jnz     short loc_140009886
0x140009873  mov     rbx, rax
0x140009876  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x14000987d  nop     dword ptr [rax+rax+00h]
0x140009882  mov     [rbx+38h], rax
0x140009886  mov     rax, [rdi+18h]
0x14000988a  cmp     byte ptr [rax+32h], 0
0x14000988e  jz      loc_14000980F
0x140009894  mov     rcx, [rax]
0x140009897  cmp     [rcx+8], rax
0x14000989b  jnz     short loc_140009913
0x14000989d  mov     rdx, [rax+8]
0x1400098a1  cmp     [rdx], rax
0x1400098a4  jnz     short loc_140009913
0x1400098a6  mov     [rdx], rcx
0x1400098a9  mov     [rcx+8], rdx
0x1400098ad  lea     rcx, [rbp+0B58h]
0x1400098b4  mov     rdx, [rcx+8]
0x1400098b8  cmp     [rdx], rcx
0x1400098bb  jnz     short loc_140009913
0x1400098bd  mov     rax, [rdi+18h]
0x1400098c1  mov     [rax], rcx
0x1400098c4  mov     [rax+8], rdx
0x1400098c8  mov     [rdx], rax
0x1400098cb  mov     [rcx+8], rax
0x1400098cf  mov     rax, [rdi+18h]
0x1400098d3  mov     byte ptr [rax+32h], 0
0x1400098d7  jmp     loc_14000980F
0x1400098dc  mov     rdx, rsi; Entry
0x1400098df  lea     rcx, [rbp+0B80h]; Lookaside
0x1400098e6  mov     rsi, r15
0x1400098e9  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400098f0  nop     dword ptr [rax+rax+00h]
0x1400098f5  test    r15, r15
0x1400098f8  jnz     loc_140009808
0x1400098fe  inc     qword ptr [rbp+240h]
0x140009905  add     rsp, 28h
0x140009909  pop     r15
0x14000990b  pop     r14
0x14000990d  pop     rdi
0x14000990e  pop     rsi
0x14000990f  pop     rbp
0x140009910  pop     rbx
0x140009911  retn
0x140009913  mov     ecx, 3
0x140009918  int     29h; Win8: RtlFailFast(ecx)
```
