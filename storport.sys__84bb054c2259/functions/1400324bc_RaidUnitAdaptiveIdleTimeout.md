# RaidUnitAdaptiveIdleTimeout

- ea: `0x1400324bc`
- end: `0x140032779`
- name: `RaidUnitAdaptiveIdleTimeout`
- size: `701`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: ``

## callers

- `0x140031fd0`
- `0x1400a5660`
- `0x1400a58a0`
- `0x1400a58c0`
- `0x1401be6d8`

## callees

- `0x1400324bc`
- `0x1400a32f0`
- `0x1400a33bc`

## import_xrefs

- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400324e3`
- `ntoskrnl!ExAcquireRundownProtectionCacheAware` at `0x1400324e3`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400325be`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x1400325be`
- `ntoskrnl!ExSetTimer` at `0x14014ff70`
- `ntoskrnl!ExSetTimer` at `0x14014ff70`
- `ntoskrnl!ExAllocateTimer` at `0x140032720`
- `ntoskrnl!ExAllocateTimer` at `0x140032720`
- `ntoskrnl!ExCancelTimer` at `0x140032540`
- `ntoskrnl!ExCancelTimer` at `0x140032540`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x140032630`
- `ntoskrnl!PoFxSetDeviceIdleTimeout` at `0x140032630`

## pseudocode

```c
void __fastcall RaidUnitAdaptiveIdleTimeout(__int64 a1)
{
  int v2; // r8d
  __int64 v3; // rcx
  _DWORD *v4; // rbx
  unsigned int v5; // ebx
  __int64 v6; // rcx
  __int64 v7; // rcx
  unsigned int v8; // esi
  int v9; // edx
  __int64 v10; // r9
  int v11; // ebx
  unsigned int v12; // ecx
  __int64 v13; // rsi
  __int64 v14; // rcx
  int v15; // edx
  __int64 v16; // rcx
  int v17; // r8d
  int v18; // edx
  __int64 v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // r15
  __int64 v22; // rbp
  unsigned __int64 v23; // rdx
  unsigned __int64 v24; // r14
  int v25; // ecx
  __int64 v26; // r14
  __int64 v27; // rbx
  __int64 v28; // rcx

  if ( (*(_DWORD *)(a1 + 504) & 0x8000) != 0
    && ExAcquireRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864)) )
  {
    v3 = *(_QWORD *)(a1 + 1872);
    if ( (*(_DWORD *)(v3 + 32) & 0x100) == 0 )
      goto LABEL_20;
    if ( !v3 || (v4 = *(_DWORD **)(v3 + 8)) == 0 || *v4 != 3 || (v5 = v4[5]) == 0 )
      v5 = 300000;
    v6 = *(_QWORD *)(v3 + 120);
    if ( v6 )
      ExCancelTimer(v6, 0);
    v7 = *(_QWORD *)(a1 + 1872);
    v8 = v5;
    if ( v5 <= *(_DWORD *)(v7 + 20) )
      v8 = *(_DWORD *)(v7 + 20);
    if ( (*(_DWORD *)(v7 + 32) & 0x400) != 0 )
    {
      ++*(_QWORD *)(v7 + 56);
      v20 = MEMORY[0xFFFFF78000000014] - *(_QWORD *)(a1 + 3360);
      if ( v20 > 0 )
      {
        v21 = v5;
        v22 = v20 / 10000;
        v23 = v20 / 10000 % (unsigned __int64)v5;
        v24 = v20 / 10000 / (unsigned __int64)v5;
        if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
        {
          v25 = *(_DWORD *)(a1 + 3352);
          LOBYTE(v25) = *(_BYTE *)(a1 + 106);
          McTemplateK0quuuqqq_EtwWriteTransfer(
            v25,
            v23,
            v2,
            *(_DWORD *)(*(_QWORD *)(a1 + 24) + 56LL),
            *(_BYTE *)(a1 + 104),
            *(_BYTE *)(a1 + 105),
            v25,
            *(_DWORD *)(a1 + 3352),
            v24,
            v5);
        }
        if ( v24 <= *(unsigned int *)(a1 + 3352) )
        {
          ++*(_QWORD *)(*(_QWORD *)(a1 + 1872) + 48LL);
          v26 = *(unsigned int *)(a1 + 3352);
          if ( !*(_QWORD *)(*(_QWORD *)(a1 + 1872) + 120LL) )
          {
            v27 = *(_QWORD *)(a1 + 1872);
            *(_QWORD *)(v27 + 120) = ExAllocateTimer(RaidUnitPowerCycleCheck, a1, 0);
          }
          v28 = *(_QWORD *)(*(_QWORD *)(a1 + 1872) + 120LL);
          if ( v28 )
            ExSetTimer(v28, 10000 * (v22 - v21 * (v26 + 1)), 0, 0);
          v9 = 512;
          goto LABEL_14;
        }
        v8 = 100;
      }
    }
    v9 = 0;
LABEL_14:
    *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 32LL) = v9 | *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 32LL) & 0xFFFFFDFF;
    v10 = *(_QWORD *)(a1 + 24);
    if ( (*(_BYTE *)(v10 + 110) & 0x40) == 0 )
    {
      v11 = -1;
      if ( v8 == -1 )
      {
        v13 = -1;
      }
      else
      {
        v12 = *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 24LL);
        if ( v8 >= v12 )
          v12 = v8;
        v11 = v12;
        v13 = 10000LL * v12;
      }
      v14 = *(_QWORD *)(a1 + 1872);
      v15 = *(_DWORD *)(v14 + 28);
      if ( v11 == v15 )
        goto LABEL_20;
      if ( StorEtwLoggingEnabled )
      {
        if ( (byte_140177432 & 0x10) != 0 )
          McTemplateK0quuuqqtt_EtwWriteTransfer(
            (*(_DWORD *)(v14 + 32) >> 10) & 1,
            v15,
            v2,
            *(_DWORD *)(v10 + 56),
            *(_BYTE *)(a1 + 104),
            *(_BYTE *)(a1 + 105),
            *(_BYTE *)(a1 + 106),
            v15,
            v11,
            (*(_DWORD *)(v14 + 32) & 0x400) != 0,
            (*(_DWORD *)(v14 + 32) & 0x800) != 0);
      }
      v19 = v13;
      *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 28LL) = v11;
      goto LABEL_30;
    }
    v16 = *(_QWORD *)(a1 + 1872);
    v17 = *(_DWORD *)(v10 + 6088);
    v18 = *(_DWORD *)(v16 + 28);
    if ( v17 != v18 )
    {
      if ( StorEtwLoggingEnabled && (byte_140177432 & 0x10) != 0 )
        McTemplateK0quuuqqtt_EtwWriteTransfer(
          (*(_DWORD *)(v16 + 32) >> 10) & 1,
          v18,
          v17,
          *(_DWORD *)(v10 + 56),
          *(_BYTE *)(a1 + 104),
          *(_BYTE *)(a1 + 105),
          *(_BYTE *)(a1 + 106),
          v18,
          v17,
          (*(_DWORD *)(v16 + 32) & 0x400) != 0,
          (*(_DWORD *)(v16 + 32) & 0x800) != 0);
      *(_DWORD *)(*(_QWORD *)(a1 + 1872) + 28LL) = *(_DWORD *)(*(_QWORD *)(a1 + 24) + 6088LL);
      v19 = 10000LL * *(unsigned int *)(*(_QWORD *)(a1 + 24) + 6088LL);
LABEL_30:
      PoFxSetDeviceIdleTimeout(**(_QWORD **)(a1 + 1872), v19);
    }
LABEL_20:
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  }
}

```

## disassembly

```asm
0x1400324bc  push    rbx
0x1400324be  push    rbp
0x1400324bf  push    rsi
0x1400324c0  push    rdi
0x1400324c1  push    r14
0x1400324c3  push    r15
0x1400324c5  sub     rsp, 68h
0x1400324c9  mov     eax, [rcx+1F8h]
0x1400324cf  mov     rdi, rcx
0x1400324d2  bt      eax, 0Fh
0x1400324d6  jnb     loc_1400325CA
0x1400324dc  mov     rcx, [rcx+748h]; RunRefCacheAware
0x1400324e3  call    cs:__imp_ExAcquireRundownProtectionCacheAware
0x1400324ea  nop     dword ptr [rax+rax+00h]
0x1400324ef  test    al, al
0x1400324f1  jz      loc_1400325CA
0x1400324f7  mov     rcx, [rdi+750h]
0x1400324fe  test    dword ptr [rcx+20h], 100h
0x140032505  jz      loc_1400325B7
0x14003250b  test    rcx, rcx
0x14003250e  jz      loc_1400325D8
0x140032514  mov     rbx, [rcx+8]
0x140032518  test    rbx, rbx
0x14003251b  jz      loc_1400325D8
0x140032521  cmp     dword ptr [rbx], 3
0x140032524  jnz     loc_1400325D8
0x14003252a  mov     ebx, [rbx+14h]
0x14003252d  test    ebx, ebx
0x14003252f  jz      loc_1400325D8
0x140032535  mov     rcx, [rcx+78h]
0x140032539  test    rcx, rcx
0x14003253c  jz      short loc_14003254C
0x14003253e  xor     edx, edx
0x140032540  call    cs:__imp_ExCancelTimer
0x140032547  nop     dword ptr [rax+rax+00h]
0x14003254c  mov     rcx, [rdi+750h]
0x140032553  mov     esi, ebx
0x140032555  mov     eax, [rcx+14h]
0x140032558  cmp     ebx, eax
0x14003255a  cmovbe  esi, eax
0x14003255d  test    dword ptr [rcx+20h], 400h
0x140032564  jnz     loc_140032641
0x14003256a  xor     edx, edx
0x14003256c  mov     rcx, [rdi+750h]
0x140032573  mov     eax, [rcx+20h]
0x140032576  btr     eax, 9
0x14003257a  or      eax, edx
0x14003257c  mov     [rcx+20h], eax
0x14003257f  mov     r9, [rdi+18h]
0x140032583  test    byte ptr [r9+6Eh], 40h
0x140032588  jnz     short loc_1400325E2
0x14003258a  or      ebx, 0FFFFFFFFh
0x14003258d  cmp     esi, ebx
0x14003258f  jz      short loc_1400325FD
0x140032591  mov     rax, [rdi+750h]
0x140032598  mov     ecx, [rax+18h]
0x14003259b  cmp     esi, ecx
0x14003259d  cmovnb  ecx, esi
0x1400325a0  mov     ebx, ecx
0x1400325a2  imul    rsi, rbx, 2710h
0x1400325a9  mov     rcx, [rdi+750h]
0x1400325b0  mov     edx, [rcx+1Ch]
0x1400325b3  cmp     ebx, edx
0x1400325b5  jnz     short loc_140032603
0x1400325b7  mov     rcx, [rdi+748h]; RunRefCacheAware
0x1400325be  call    cs:__imp_ExReleaseRundownProtectionCacheAware
0x1400325c5  nop     dword ptr [rax+rax+00h]
0x1400325ca  add     rsp, 68h
0x1400325ce  pop     r15
0x1400325d0  pop     r14
0x1400325d2  pop     rdi
0x1400325d3  pop     rsi
0x1400325d4  pop     rbp
0x1400325d5  pop     rbx
0x1400325d6  retn
0x1400325d8  mov     ebx, 493E0h
0x1400325dd  jmp     loc_140032535
0x1400325e2  mov     rcx, [rdi+750h]
0x1400325e9  mov     r8d, [r9+17C8h]
0x1400325f0  mov     edx, [rcx+1Ch]
0x1400325f3  cmp     r8d, edx
0x1400325f6  jz      short loc_1400325B7
0x1400325f8  jmp     loc_14014FF86
0x1400325fd  or      rsi, 0FFFFFFFFFFFFFFFFh
0x140032601  jmp     short loc_1400325A9
0x140032603  cmp     cs:StorEtwLoggingEnabled, 0
0x14003260a  jz      short loc_140032619
0x14003260c  test    cs:byte_140177432, 10h
0x140032613  jnz     loc_140032735
0x140032619  mov     rax, [rdi+750h]
0x140032620  mov     rdx, rsi
0x140032623  mov     [rax+1Ch], ebx
0x140032626  mov     rcx, [rdi+750h]
0x14003262d  mov     rcx, [rcx]
0x140032630  call    cs:__imp_PoFxSetDeviceIdleTimeout
0x140032637  nop     dword ptr [rax+rax+00h]
0x14003263c  jmp     loc_1400325B7
0x140032641  inc     qword ptr [rcx+38h]
0x140032645  mov     rcx, 0FFFFF78000000014h
0x14003264f  mov     rcx, [rcx]
0x140032652  sub     rcx, [rdi+0D20h]
0x140032659  test    rcx, rcx
0x14003265c  jle     loc_14003256A
0x140032662  mov     rax, 346DC5D63886594Bh
0x14003266c  mov     r15d, ebx
0x14003266f  imul    rcx
0x140032672  mov     rbp, rdx
0x140032675  xor     edx, edx
0x140032677  sar     rbp, 0Bh
0x14003267b  mov     rax, rbp
0x14003267e  shr     rax, 3Fh
0x140032682  add     rbp, rax
0x140032685  mov     rax, rbp
0x140032688  div     r15
0x14003268b  cmp     cs:StorEtwLoggingEnabled, 0
0x140032692  mov     r14, rax
0x140032695  jnz     short loc_1400326AC
0x140032697  mov     eax, [rdi+0D18h]
0x14003269d  cmp     r14, rax
0x1400326a0  jbe     short loc_1400326EC
0x1400326a2  mov     esi, 64h ; 'd'
0x1400326a7  jmp     loc_14003256A
0x1400326ac  test    cs:byte_140177432, 10h
0x1400326b3  jz      short loc_140032697
0x1400326b5  mov     ecx, [rdi+0D18h]
0x1400326bb  mov     al, [rdi+69h]
0x1400326be  mov     r9, [rdi+18h]
0x1400326c2  mov     [rsp+98h+var_50], ebx
0x1400326c6  mov     [rsp+98h+var_58], r14d
0x1400326cb  mov     [rsp+98h+var_60], ecx
0x1400326cf  mov     cl, [rdi+6Ah]
0x1400326d2  mov     r9d, [r9+38h]
0x1400326d6  mov     [rsp+98h+var_68], cl
0x1400326da  mov     [rsp+98h+var_70], al
0x1400326de  mov     al, [rdi+68h]
0x1400326e1  mov     [rsp+98h+var_78], al
0x1400326e5  call    McTemplateK0quuuqqq_EtwWriteTransfer
0x1400326ea  jmp     short loc_140032697
0x1400326ec  mov     rax, [rdi+750h]
0x1400326f3  inc     qword ptr [rax+30h]
0x1400326f7  mov     rax, [rdi+750h]
0x1400326fe  mov     r14d, [rdi+0D18h]
0x140032705  cmp     qword ptr [rax+78h], 0
0x14003270a  jnz     loc_14014FF48
0x140032710  xor     r8d, r8d
0x140032713  lea     rcx, RaidUnitPowerCycleCheck
0x14003271a  mov     rdx, rdi
0x14003271d  mov     rbx, rax
0x140032720  call    cs:__imp_ExAllocateTimer
0x140032727  nop     dword ptr [rax+rax+00h]
0x14003272c  mov     [rbx+78h], rax
0x140032730  jmp     loc_14014FF48
0x140032735  mov     ecx, [rcx+20h]
0x140032738  mov     eax, ecx
0x14003273a  mov     r9d, [r9+38h]
0x14003273e  shr     eax, 0Bh
0x140032741  and     eax, 1
0x140032744  shr     ecx, 0Ah
0x140032747  mov     [rsp+98h+var_48], eax
0x14003274b  and     ecx, 1
0x14003274e  mov     al, [rdi+6Ah]
0x140032751  mov     [rsp+98h+var_50], ecx
0x140032755  mov     [rsp+98h+var_58], ebx
0x140032759  mov     [rsp+98h+var_60], edx
0x14003275d  mov     [rsp+98h+var_68], al
0x140032761  mov     al, [rdi+69h]
0x140032764  mov     [rsp+98h+var_70], al
0x140032768  mov     al, [rdi+68h]
0x14003276b  mov     [rsp+98h+var_78], al
0x14003276f  call    McTemplateK0quuuqqtt_EtwWriteTransfer
0x140032774  jmp     loc_140032619
0x14014ff48  mov     rax, [rdi+750h]
0x14014ff4f  mov     rcx, [rax+78h]
0x14014ff53  test    rcx, rcx
0x14014ff56  jz      short loc_14014FF7C
0x14014ff58  lea     rax, [r14+1]
0x14014ff5c  xor     r9d, r9d
0x14014ff5f  imul    rax, r15
0x14014ff63  xor     r8d, r8d
0x14014ff66  sub     rbp, rax
0x14014ff69  imul    rdx, rbp, 2710h
0x14014ff70  call    cs:__imp_ExSetTimer
0x14014ff77  nop     dword ptr [rax+rax+00h]
0x14014ff7c  mov     edx, 200h
0x14014ff81  jmp     loc_14003256C
0x14014ff86  cmp     cs:StorEtwLoggingEnabled, 0
0x14014ff8d  jz      short loc_14014FFD8
0x14014ff8f  test    cs:byte_140177432, 10h
0x14014ff96  jz      short loc_14014FFD8
0x14014ff98  mov     ecx, [rcx+20h]
0x14014ff9b  mov     eax, ecx
0x14014ff9d  mov     r9d, [r9+38h]
0x14014ffa1  shr     eax, 0Bh
0x14014ffa4  and     eax, 1
0x14014ffa7  shr     ecx, 0Ah
0x14014ffaa  mov     [rsp+98h+var_48], eax
0x14014ffae  and     ecx, 1
0x14014ffb1  mov     al, [rdi+6Ah]
0x14014ffb4  mov     [rsp+98h+var_50], ecx
0x14014ffb8  mov     [rsp+98h+var_58], r8d
0x14014ffbd  mov     [rsp+98h+var_60], edx
0x14014ffc1  mov     [rsp+98h+var_68], al
0x14014ffc5  mov     al, [rdi+69h]
0x14014ffc8  mov     [rsp+98h+var_70], al
0x14014ffcc  mov     al, [rdi+68h]
0x14014ffcf  mov     [rsp+98h+var_78], al
0x14014ffd3  call    McTemplateK0quuuqqtt_EtwWriteTransfer
0x14014ffd8  mov     rax, [rdi+18h]
0x14014ffdc  mov     rcx, [rdi+750h]
0x14014ffe3  mov     eax, [rax+17C8h]
0x14014ffe9  mov     [rcx+1Ch], eax
0x14014ffec  mov     rax, [rdi+18h]
0x14014fff0  mov     ecx, [rax+17C8h]
0x14014fff6  imul    rdx, rcx, 2710h
0x14014fffd  jmp     loc_140032626
```
