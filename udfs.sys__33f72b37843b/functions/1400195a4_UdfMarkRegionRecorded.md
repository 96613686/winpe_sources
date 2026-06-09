# UdfMarkRegionRecorded

- ea: `0x1400195a4`
- end: `0x140019784`
- name: `UdfMarkRegionRecorded`
- size: `480`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400010f0`
- `0x140004514`

## callees

- `0x1400195a4`
- `0x1400197b0`

## import_xrefs

- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140019619`
- `ntoskrnl!FsRtlLookupLargeMcbEntry` at `0x140019619`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001970c`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x140019743`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x14001970c`
- `ntoskrnl!FsRtlGetNextLargeMcbEntry` at `0x140019743`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x1400196b9`
- `ntoskrnl!FsRtlRemoveLargeMcbEntry` at `0x1400196b9`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400196a3`
- `ntoskrnl!FsRtlAddLargeMcbEntry` at `0x1400196a3`

## pseudocode

```c
void __fastcall UdfMarkRegionRecorded(__int64 a1, __int64 a2, unsigned int a3, unsigned int a4)
{
  LARGE_MCB *v4; // r15
  __int64 v5; // r14
  __int64 v6; // rbx
  BOOLEAN NextLargeMcbEntry; // si
  LONGLONG v9; // r8
  __int64 v10; // rdx
  ULONG v11; // edx
  unsigned int v12; // eax
  bool v13; // cc
  __int64 Vbn; // [rsp+40h] [rbp-10h] BYREF
  LONGLONG v15; // [rsp+48h] [rbp-8h] BYREF
  __int64 SectorCountFromLbn; // [rsp+90h] [rbp+40h] BYREF
  __int64 Lbn; // [rsp+98h] [rbp+48h] BYREF
  ULONG v18; // [rsp+A0h] [rbp+50h] BYREF

  v4 = (LARGE_MCB *)(a2 + 264);
  v5 = a4;
  v6 = a3;
  v18 = 0;
  Vbn = 0;
  Lbn = 0;
  v15 = 0;
  SectorCountFromLbn = 0;
  NextLargeMcbEntry = FsRtlLookupLargeMcbEntry((PLARGE_MCB)(a2 + 264), a3, &Lbn, &SectorCountFromLbn, &v15, 0, &v18);
  if ( NextLargeMcbEntry )
  {
    v9 = Lbn;
    v10 = SectorCountFromLbn;
    while ( 1 )
    {
      if ( (unsigned int)v6 > (unsigned int)v5 )
        return;
      if ( v9 != -1 )
      {
        if ( v6 + v10 > v5 )
        {
          v10 = (unsigned int)(v5 - v6 + 1);
          SectorCountFromLbn = v10;
        }
        if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x4000000) != 0 )
        {
          WPP_SF_Di(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), v10, v9, (unsigned int)v6, v10);
          v9 = Lbn;
          v10 = SectorCountFromLbn;
        }
        FsRtlAddLargeMcbEntry((PLARGE_MCB)(a2 + 232), (unsigned int)v6, v9, v10);
        FsRtlRemoveLargeMcbEntry(v4, (unsigned int)v6, SectorCountFromLbn);
        v10 = SectorCountFromLbn;
        *(_DWORD *)(a2 + 320) += SectorCountFromLbn;
        v9 = Lbn;
      }
      v6 = (unsigned int)(v10 + v6);
      if ( (unsigned int)v6 <= (unsigned int)v5 )
        break;
LABEL_23:
      if ( !NextLargeMcbEntry )
        return;
    }
    if ( v9 == -1 || v9 > v15 )
      v11 = ++v18;
    else
      v11 = v18;
    NextLargeMcbEntry = FsRtlGetNextLargeMcbEntry(v4, v11, &Vbn, &Lbn, &SectorCountFromLbn);
    if ( NextLargeMcbEntry )
    {
      v12 = Vbn;
      v13 = (unsigned int)Vbn <= (unsigned int)v6;
      if ( (unsigned int)Vbn >= (unsigned int)v6 )
        goto LABEL_20;
      NextLargeMcbEntry = FsRtlGetNextLargeMcbEntry(v4, ++v18, &Vbn, &Lbn, &SectorCountFromLbn);
      if ( NextLargeMcbEntry )
      {
        v12 = Vbn;
        v13 = (unsigned int)Vbn <= (unsigned int)v6;
LABEL_20:
        if ( !v13 )
          v6 = v12;
      }
    }
    v9 = Lbn;
    v10 = SectorCountFromLbn;
    v15 = Lbn;
    goto LABEL_23;
  }
}

```

## disassembly

```asm
0x1400195a4  mov     r11, rsp
0x1400195a7  mov     [r11+8], rcx
0x1400195ab  push    rbp
0x1400195ac  push    rbx
0x1400195ad  push    rsi
0x1400195ae  push    rdi
0x1400195af  push    r13
0x1400195b1  push    r14
0x1400195b3  push    r15
0x1400195b5  mov     rbp, rsp
0x1400195b8  sub     rsp, 50h
0x1400195bc  lea     r15, [rdx+108h]
0x1400195c3  mov     r14d, r9d
0x1400195c6  lea     rax, [rbp+arg_10]
0x1400195ca  mov     ebx, r8d
0x1400195cd  mov     [r11-58h], rax
0x1400195d1  lea     r9, [rbp+SectorCountFromLbn]; SectorCountFromLbn
0x1400195d5  mov     r13, rdx
0x1400195d8  mov     qword ptr [r11-60h], 0
0x1400195e0  lea     rax, [rbp+var_8]
0x1400195e4  mov     edx, r8d; Vbn
0x1400195e7  lea     r8, [rbp+Lbn]; Lbn
0x1400195eb  mov     [r11-68h], rax
0x1400195ef  mov     rcx, r15; Mcb
0x1400195f2  mov     [rbp+arg_10], 0
0x1400195f9  mov     [rbp+Vbn], 0
0x140019601  mov     [rbp+Lbn], 0
0x140019609  mov     [rbp+var_8], 0
0x140019611  mov     [rbp+SectorCountFromLbn], 0
0x140019619  call    cs:__imp_FsRtlLookupLargeMcbEntry
0x140019620  nop     dword ptr [rax+rax+00h]
0x140019625  mov     sil, al
0x140019628  test    al, al
0x14001962a  jz      loc_140019774
0x140019630  mov     r8, [rbp+Lbn]
0x140019634  mov     rdx, [rbp+SectorCountFromLbn]
0x140019638  cmp     ebx, r14d
0x14001963b  ja      loc_140019774
0x140019641  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x140019645  jz      loc_1400196D4
0x14001964b  lea     rcx, [rbx+rdx]
0x14001964f  mov     edi, ebx
0x140019651  cmp     rcx, r14
0x140019654  jle     short loc_140019661
0x140019656  mov     edx, r14d
0x140019659  sub     edx, ebx
0x14001965b  inc     edx
0x14001965d  mov     [rbp+SectorCountFromLbn], rdx
0x140019661  mov     rcx, cs:WPP_GLOBAL_Control
0x140019668  lea     rax, WPP_GLOBAL_Control
0x14001966f  cmp     rcx, rax
0x140019672  jz      short loc_140019696
0x140019674  test    dword ptr [rcx+2Ch], 4000000h
0x14001967b  jz      short loc_140019696
0x14001967d  mov     rcx, [rcx+18h]
0x140019681  mov     r9d, ebx
0x140019684  mov     [rsp+50h+SectorCount], rdx
0x140019689  call    WPP_SF_Di
0x14001968e  mov     r8, [rbp+Lbn]; Lbn
0x140019692  mov     rdx, [rbp+SectorCountFromLbn]
0x140019696  mov     r9, rdx; SectorCount
0x140019699  lea     rcx, [r13+0E8h]; Mcb
0x1400196a0  mov     rdx, rdi; Vbn
0x1400196a3  call    cs:__imp_FsRtlAddLargeMcbEntry
0x1400196aa  nop     dword ptr [rax+rax+00h]
0x1400196af  mov     r8, [rbp+SectorCountFromLbn]; SectorCount
0x1400196b3  mov     rdx, rdi; Vbn
0x1400196b6  mov     rcx, r15; Mcb
0x1400196b9  call    cs:__imp_FsRtlRemoveLargeMcbEntry
0x1400196c0  nop     dword ptr [rax+rax+00h]
0x1400196c5  mov     rdx, [rbp+SectorCountFromLbn]
0x1400196c9  add     [r13+140h], edx
0x1400196d0  mov     r8, [rbp+Lbn]
0x1400196d4  add     ebx, edx
0x1400196d6  cmp     ebx, r14d
0x1400196d9  ja      loc_14001976B
0x1400196df  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x1400196e3  jz      short loc_1400196F0
0x1400196e5  cmp     r8, [rbp+var_8]
0x1400196e9  jg      short loc_1400196F0
0x1400196eb  mov     edx, [rbp+arg_10]
0x1400196ee  jmp     short loc_1400196F8
0x1400196f0  mov     edx, [rbp+arg_10]
0x1400196f3  inc     edx; RunIndex
0x1400196f5  mov     [rbp+arg_10], edx
0x1400196f8  lea     rax, [rbp+SectorCountFromLbn]
0x1400196fc  mov     rcx, r15; Mcb
0x1400196ff  lea     r9, [rbp+Lbn]; Lbn
0x140019703  mov     [rsp+50h+SectorCount], rax; SectorCount
0x140019708  lea     r8, [rbp+Vbn]; Vbn
0x14001970c  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x140019713  nop     dword ptr [rax+rax+00h]
0x140019718  mov     sil, al
0x14001971b  test    al, al
0x14001971d  jz      short loc_14001975F
0x14001971f  mov     rax, [rbp+Vbn]
0x140019723  cmp     eax, ebx
0x140019725  jnb     short loc_14001975C
0x140019727  mov     edx, [rbp+arg_10]
0x14001972a  lea     rax, [rbp+SectorCountFromLbn]
0x14001972e  inc     edx; RunIndex
0x140019730  mov     [rsp+50h+SectorCount], rax; SectorCount
0x140019735  lea     r9, [rbp+Lbn]; Lbn
0x140019739  mov     [rbp+arg_10], edx
0x14001973c  lea     r8, [rbp+Vbn]; Vbn
0x140019740  mov     rcx, r15; Mcb
0x140019743  call    cs:__imp_FsRtlGetNextLargeMcbEntry
0x14001974a  nop     dword ptr [rax+rax+00h]
0x14001974f  mov     sil, al
0x140019752  test    al, al
0x140019754  jz      short loc_14001975F
0x140019756  mov     rax, [rbp+Vbn]
0x14001975a  cmp     eax, ebx
0x14001975c  cmova   ebx, eax
0x14001975f  mov     r8, [rbp+Lbn]
0x140019763  mov     rdx, [rbp+SectorCountFromLbn]
0x140019767  mov     [rbp+var_8], r8
0x14001976b  test    sil, sil
0x14001976e  jnz     loc_140019638
0x140019774  add     rsp, 50h
0x140019778  pop     r15
0x14001977a  pop     r14
0x14001977c  pop     r13
0x14001977e  pop     rdi
0x14001977f  pop     rsi
0x140019780  pop     rbx
0x140019781  pop     rbp
0x140019782  retn
```
