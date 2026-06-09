# VMX_PHYSICAL_DISK::ZeroSectors(unsigned __int64,ulong)

- ea: `0x1400484a4`
- end: `0x1400486c1`
- name: `?ZeroSectors@VMX_PHYSICAL_DISK@@QEAAJ_KK@Z`
- size: `541`
- prototype: `__int64 __fastcall(VMX_PHYSICAL_DISK *__hidden this, unsigned __int64, unsigned int)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1400483bc`
- `0x14004b3dc`

## callees

- `0x1400099d8`
- `0x14001be80`
- `0x1400465b0`
- `0x140047e38`
- `0x1400484a4`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14004856c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485f0`
- `ntoskrnl!ExFreePoolWithTag` at `0x14004856c`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485da`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400485f0`
- `ntoskrnl!RtlCompareMemory` at `0x140048554`
- `ntoskrnl!RtlCompareMemory` at `0x1400485c2`
- `ntoskrnl!RtlCompareMemory` at `0x140048554`
- `ntoskrnl!RtlCompareMemory` at `0x1400485c2`

## pseudocode

```c
__int64 __fastcall VMX_PHYSICAL_DISK::ZeroSectors(VMX_PHYSICAL_DISK *this, unsigned __int64 a2, unsigned int a3)
{
  __int64 v3; // rax
  __int64 v5; // r14
  unsigned int v7; // r12d
  void *v8; // r15
  unsigned __int64 v9; // r14
  unsigned int i; // edi
  int Sectors; // eax
  SIZE_T v12; // rax
  void *v13; // rcx
  unsigned int v14; // ebx
  SIZE_T v15; // rax
  VMX_NOTIFICATION_QUEUE *v16; // rcx
  __int64 v17; // rdx
  void *Source1; // [rsp+50h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 2);
  v5 = a3;
  Source1 = 0;
  v7 = *(_DWORD *)(v3 + 36);
  v8 = (void *)*((_QWORD *)Global + 32);
  memset(v8, 0, 0x8000u);
  v9 = a2 + v5;
  for ( i = 0x8000 / v7; ; a2 += i )
  {
    if ( a2 >= v9 )
      return 0;
    if ( a2 + i > v9 )
      i = v9 - a2;
    VMX_PHYSICAL_DISK::WriteSectors(this, a2, i, (unsigned __int8 *)v8);
    Sectors = VMX_PHYSICAL_DISK::ReadSectors(this, a2, i, (unsigned __int8 **)&Source1);
    if ( Sectors < 0 )
      break;
    v12 = RtlCompareMemory(Source1, v8, i * v7);
    v13 = Source1;
    if ( v12 == i * v7 )
      goto LABEL_11;
    ExFreePoolWithTag(Source1, 0);
LABEL_9:
    VMX_PHYSICAL_DISK::WriteSectors(this, a2, i, (unsigned __int8 *)v8);
    v14 = VMX_PHYSICAL_DISK::ReadSectors(this, a2, i, (unsigned __int8 **)&Source1);
    if ( (v14 & 0x80000000) != 0 )
    {
      v16 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v17 = 14;
LABEL_20:
        WPP_SF_d(*((_QWORD *)v16 + 3), v17, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, v14);
      }
      return v14;
    }
    v15 = RtlCompareMemory(Source1, v8, i * v7);
    v13 = Source1;
    if ( v15 != i * v7 )
    {
      ExFreePoolWithTag(Source1, 0);
      v16 = WPP_GLOBAL_Control;
      v14 = -1070071788;
      if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
      {
        v17 = 15;
        goto LABEL_20;
      }
      return v14;
    }
LABEL_11:
    ExFreePoolWithTag(v13, 0);
  }
  if ( Sectors != -1073741670 )
    goto LABEL_9;
  if ( WPP_GLOBAL_Control != (VMX_NOTIFICATION_QUEUE *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 11) & 0x10) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 41) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 3), 13, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids, 3221225626LL);
  }
  return 3221225626LL;
}

```

## disassembly

```asm
0x1400484a4  mov     [rsp+arg_8], rbx
0x1400484a9  mov     [rsp+arg_10], rsi
0x1400484ae  push    rdi
0x1400484af  push    r12
0x1400484b1  push    r13
0x1400484b3  push    r14
0x1400484b5  push    r15
0x1400484b7  sub     rsp, 20h
0x1400484bb  mov     rax, [rcx+10h]
0x1400484bf  mov     rsi, rdx
0x1400484c2  mov     r14d, r8d
0x1400484c5  mov     r13, rcx
0x1400484c8  mov     edi, 8000h
0x1400484cd  mov     [rsp+48h+Source1], 0
0x1400484d6  mov     r8d, edi; Size
0x1400484d9  xor     edx, edx; Val
0x1400484db  mov     r12d, [rax+24h]
0x1400484df  mov     rax, cs:?Global@@3PEAVVMX_GLOBAL_DATA@@EA; VMX_GLOBAL_DATA * Global
0x1400484e6  mov     r15, [rax+100h]
0x1400484ed  mov     rcx, r15; void *
0x1400484f0  call    memset
0x1400484f5  mov     eax, edi
0x1400484f7  xor     edx, edx
0x1400484f9  add     r14, rsi
0x1400484fc  div     r12d
0x1400484ff  mov     edi, eax
0x140048501  cmp     rsi, r14
0x140048504  jnb     loc_1400486A6
0x14004850a  mov     ecx, edi
0x14004850c  add     rcx, rsi
0x14004850f  cmp     rcx, r14
0x140048512  jbe     short loc_140048519
0x140048514  mov     edi, r14d
0x140048517  sub     edi, esi
0x140048519  mov     r9, r15; unsigned __int8 *
0x14004851c  mov     r8d, edi; unsigned int
0x14004851f  mov     rdx, rsi; unsigned __int64
0x140048522  mov     rcx, r13; this
0x140048525  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x14004852a  lea     r9, [rsp+48h+Source1]; unsigned __int8 **
0x14004852f  mov     r8d, edi; unsigned int
0x140048532  mov     rdx, rsi; unsigned __int64
0x140048535  mov     rcx, r13; this
0x140048538  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x14004853d  test    eax, eax
0x14004853f  js      short loc_14004857A
0x140048541  mov     rcx, [rsp+48h+Source1]; Source1
0x140048546  mov     eax, r12d
0x140048549  imul    eax, edi
0x14004854c  mov     rdx, r15; Source2
0x14004854f  mov     r8d, eax; Length
0x140048552  mov     ebx, eax
0x140048554  call    cs:__imp_RtlCompareMemory
0x14004855b  nop     dword ptr [rax+rax+00h]
0x140048560  mov     rcx, [rsp+48h+Source1]; P
0x140048565  xor     edx, edx; Tag
0x140048567  cmp     rax, rbx
0x14004856a  jz      short loc_1400485DA
0x14004856c  call    cs:__imp_ExFreePoolWithTag
0x140048573  nop     dword ptr [rax+rax+00h]
0x140048578  jmp     short loc_140048585
0x14004857a  cmp     eax, 0C000009Ah
0x14004857f  jz      loc_140048664
0x140048585  mov     r9, r15; unsigned __int8 *
0x140048588  mov     r8d, edi; unsigned int
0x14004858b  mov     rdx, rsi; unsigned __int64
0x14004858e  mov     rcx, r13; this
0x140048591  call    ?WriteSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAE@Z; VMX_PHYSICAL_DISK::WriteSectors(unsigned __int64,ulong,uchar *)
0x140048596  lea     r9, [rsp+48h+Source1]; unsigned __int8 **
0x14004859b  mov     r8d, edi; unsigned int
0x14004859e  mov     rdx, rsi; unsigned __int64
0x1400485a1  mov     rcx, r13; this
0x1400485a4  call    ?ReadSectors@VMX_PHYSICAL_DISK@@QEAAJ_KKPEAPEAE@Z; VMX_PHYSICAL_DISK::ReadSectors(unsigned __int64,ulong,uchar * *)
0x1400485a9  mov     ebx, eax
0x1400485ab  test    eax, eax
0x1400485ad  js      short loc_140048628
0x1400485af  mov     rcx, [rsp+48h+Source1]; Source1
0x1400485b4  mov     eax, r12d
0x1400485b7  imul    eax, edi
0x1400485ba  mov     rdx, r15; Source2
0x1400485bd  mov     r8d, eax; Length
0x1400485c0  mov     ebx, eax
0x1400485c2  call    cs:__imp_RtlCompareMemory
0x1400485c9  nop     dword ptr [rax+rax+00h]
0x1400485ce  mov     rcx, [rsp+48h+Source1]; P
0x1400485d3  xor     edx, edx; Tag
0x1400485d5  cmp     rax, rbx
0x1400485d8  jnz     short loc_1400485F0
0x1400485da  call    cs:__imp_ExFreePoolWithTag
0x1400485e1  nop     dword ptr [rax+rax+00h]
0x1400485e6  mov     eax, edi
0x1400485e8  add     rsi, rax
0x1400485eb  jmp     loc_140048501
0x1400485f0  call    cs:__imp_ExFreePoolWithTag
0x1400485f7  nop     dword ptr [rax+rax+00h]
0x1400485fc  mov     rcx, cs:WPP_GLOBAL_Control
0x140048603  lea     rax, WPP_GLOBAL_Control
0x14004860a  mov     ebx, 0C0380014h
0x14004860f  cmp     rcx, rax
0x140048612  jz      short loc_140048660
0x140048614  mov     eax, [rcx+2Ch]
0x140048617  test    al, 10h
0x140048619  jz      short loc_140048660
0x14004861b  cmp     byte ptr [rcx+29h], 2
0x14004861f  jb      short loc_140048660
0x140048621  mov     edx, 0Fh
0x140048626  jmp     short loc_14004864D
0x140048628  mov     rcx, cs:WPP_GLOBAL_Control
0x14004862f  lea     rax, WPP_GLOBAL_Control
0x140048636  cmp     rcx, rax
0x140048639  jz      short loc_140048660
0x14004863b  mov     eax, [rcx+2Ch]
0x14004863e  test    al, 10h
0x140048640  jz      short loc_140048660
0x140048642  cmp     byte ptr [rcx+29h], 2
0x140048646  jb      short loc_140048660
0x140048648  mov     edx, 0Eh
0x14004864d  mov     rcx, [rcx+18h]
0x140048651  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x140048658  mov     r9d, ebx
0x14004865b  call    WPP_SF_d
0x140048660  mov     eax, ebx
0x140048662  jmp     short loc_1400486A8
0x140048664  mov     rcx, cs:WPP_GLOBAL_Control
0x14004866b  lea     rax, WPP_GLOBAL_Control
0x140048672  cmp     rcx, rax
0x140048675  jz      short loc_14004869F
0x140048677  mov     eax, [rcx+2Ch]
0x14004867a  test    al, 10h
0x14004867c  jz      short loc_14004869F
0x14004867e  cmp     byte ptr [rcx+29h], 2
0x140048682  jb      short loc_14004869F
0x140048684  mov     rcx, [rcx+18h]
0x140048688  lea     r8, WPP_8fc838f4cc4a31c19dec3603b8b90f6a_Traceguids
0x14004868f  mov     edx, 0Dh
0x140048694  mov     r9d, 0C000009Ah
0x14004869a  call    WPP_SF_d
0x14004869f  mov     eax, 0C000009Ah
0x1400486a4  jmp     short loc_1400486A8
0x1400486a6  xor     eax, eax
0x1400486a8  mov     rbx, [rsp+48h+arg_8]
0x1400486ad  mov     rsi, [rsp+48h+arg_10]
0x1400486b2  add     rsp, 20h
0x1400486b6  pop     r15
0x1400486b8  pop     r14
0x1400486ba  pop     r13
0x1400486bc  pop     r12
0x1400486be  pop     rdi
0x1400486bf  retn
```
