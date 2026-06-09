# KmclpAllocateBounceBlock

- ea: `0x140009028`
- end: `0x140009333`
- name: `KmclpAllocateBounceBlock`
- size: `779`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x1400064a0`
- `0x14000b3d8`
- `0x14000faa0`

## callees

- `0x140009028`
- `0x140011ed0`

## import_xrefs

- `ntoskrnl!ExAllocatePool2` at `0x14000906a`
- `ntoskrnl!ExAllocatePool2` at `0x140009184`
- `ntoskrnl!ExAllocatePool2` at `0x14000906a`
- `ntoskrnl!ExAllocatePool2` at `0x140009184`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400091b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009230`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009244`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400091b0`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009230`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009244`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400092d5`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400092d5`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000930b`
- `ntoskrnl!KeReleaseSpinLock` at `0x14000930b`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400090b0`
- `ntoskrnl!MmAllocatePagesForMdlEx` at `0x1400090b0`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400092bb`
- `ntoskrnl!KeQueryUnbiasedInterruptTime` at `0x1400092bb`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000921e`
- `ntoskrnl!MmFreePagesFromMdl` at `0x14000921e`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400091da`
- `ntoskrnl!MmUnmapLockedPages` at `0x1400091da`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000915b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14000915b`

## pseudocode

```c
__int64 __fastcall KmclpAllocateBounceBlock(__int64 a1, int a2, char a3)
{
  __int64 Pool2; // rbx
  int v8; // edi
  PMDL PagesForMdl; // rax
  __int64 v10; // r14
  __int64 ByteCount; // rbp
  __int64 v12; // rcx
  unsigned __int64 v13; // rbp
  __int64 v14; // rdi
  char *v15; // r15
  __int64 v16; // rax
  void *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 *v20; // rdi
  __int64 v21; // r8
  __int64 *v22; // rdx
  __int64 **v23; // rax
  KIRQL v24; // al
  __int64 *v25; // rdx

  if ( !*(_BYTE *)(a1 + 2897) )
    return *(_BYTE *)(a1 + 2896) == 0 ? 0xC00000BB : 0;
  Pool2 = ExAllocatePool2(64, 72, 1668115286);
  if ( Pool2 )
  {
    PagesForMdl = MmAllocatePagesForMdlEx(0, (PHYSICAL_ADDRESS)-1LL, 0, (a2 + 4095) & 0xFFFFF000, MmCached, 4u);
    *(_QWORD *)(Pool2 + 64) = PagesForMdl;
    if ( PagesForMdl )
    {
      v10 = Pool2 + 16;
      ByteCount = PagesForMdl->ByteCount;
      v12 = (LODWORD(PagesForMdl->StartVa) + PagesForMdl->ByteOffset) & 0xFFF;
      *(_QWORD *)(Pool2 + 8) = Pool2;
      *(_QWORD *)Pool2 = Pool2;
      *(_QWORD *)(Pool2 + 24) = Pool2 + 16;
      *(_QWORD *)(Pool2 + 16) = Pool2 + 16;
      v13 = (unsigned __int64)(v12 + ByteCount + 4095) >> 12;
      *(_DWORD *)(Pool2 + 44) = v13;
      *(_BYTE *)(Pool2 + 49) = a3;
      if ( *(_BYTE *)(a1 + 2896) )
      {
        v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 2656))(
               *(_QWORD *)(a1 + 2368),
               *(_QWORD *)(Pool2 + 64),
               1);
        if ( v8 < 0 )
        {
LABEL_15:
          v17 = *(void **)(Pool2 + 32);
          if ( v17 )
          {
            ExFreePoolWithTag(v17, 0x636D6B56u);
            *(_QWORD *)(Pool2 + 32) = 0;
          }
          v18 = *(_QWORD *)(Pool2 + 64);
          if ( v18 )
          {
            if ( (*(_BYTE *)(v18 + 10) & 1) != 0 )
              MmUnmapLockedPages(*(PVOID *)(v18 + 24), *(PMDL *)(Pool2 + 64));
            if ( *(_BYTE *)(Pool2 + 48) )
            {
              v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(a1 + 2656))(
                     *(_QWORD *)(a1 + 2368),
                     *(_QWORD *)(Pool2 + 64),
                     3);
              if ( v8 < 0 )
                __fastfail(0x3Au);
              *(_BYTE *)(Pool2 + 48) = 0;
            }
            MmFreePagesFromMdl(*(PMDL *)(Pool2 + 64));
            ExFreePoolWithTag(*(PVOID *)(Pool2 + 64), 0);
          }
          ExFreePoolWithTag((PVOID)Pool2, 0x636D6B56u);
          goto LABEL_26;
        }
        *(_BYTE *)(Pool2 + 48) = 1;
      }
      v14 = *(_QWORD *)(Pool2 + 64);
      if ( (*(_BYTE *)(v14 + 10) & 5) != 0 )
        v15 = *(char **)(v14 + 24);
      else
        v15 = (char *)MmMapLockedPagesSpecifyCache((PMDL)v14, 0, MmCached, 0, 0, 0x40000010u);
      if ( v15 )
      {
        v16 = ExAllocatePool2(64, 40LL * (unsigned int)v13, 1668115286);
        *(_QWORD *)(Pool2 + 32) = v16;
        if ( v16 )
        {
          v20 = (__int64 *)(v14 + 48);
          v21 = 0;
          if ( (_DWORD)v13 )
          {
            while ( 1 )
            {
              v22 = (__int64 *)(*(_QWORD *)(Pool2 + 32) + 40 * v21);
              v22[1] = (__int64)v22;
              *v22 = (__int64)v22;
              v22[2] = *v20;
              v22[4] = (__int64)&v15[(_DWORD)v21 << 12];
              v22[3] = Pool2;
              v23 = *(__int64 ***)(Pool2 + 24);
              if ( *v23 != (__int64 *)v10 )
                break;
              *v22 = v10;
              v21 = (unsigned int)(v21 + 1);
              v22[1] = (__int64)v23;
              *v23 = v22;
              *(_QWORD *)(Pool2 + 24) = v22;
              if ( (unsigned int)v21 >= (unsigned int)v13 )
                goto LABEL_31;
              ++v20;
            }
          }
          else
          {
LABEL_31:
            if ( !*(_BYTE *)(Pool2 + 49) )
              *(_QWORD *)(Pool2 + 56) = KeQueryUnbiasedInterruptTime();
            v24 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1 + 256));
            v25 = *(__int64 **)(a1 + 2912);
            if ( *v25 == a1 + 2904 )
            {
              *(_QWORD *)Pool2 = a1 + 2904;
              *(_QWORD *)(Pool2 + 8) = v25;
              *v25 = Pool2;
              *(_QWORD *)(a1 + 2912) = Pool2;
              KeReleaseSpinLock((PKSPIN_LOCK)(a1 + 256), v24);
              v8 = 0;
              v19 = 536;
              goto LABEL_36;
            }
          }
          __fastfail(3u);
        }
      }
    }
    v8 = -1073741670;
    goto LABEL_15;
  }
  v8 = -1073741670;
LABEL_26:
  v19 = 544;
LABEL_36:
  _InterlockedIncrement64((volatile signed __int64 *)(v19 + a1));
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x140009028  push    rbx
0x14000902a  push    rbp
0x14000902b  push    rsi
0x14000902c  push    rdi
0x14000902d  push    r14
0x14000902f  push    r15
0x140009031  sub     rsp, 38h
0x140009035  cmp     byte ptr [rcx+0B51h], 0
0x14000903c  mov     r15b, r8b
0x14000903f  mov     edi, edx
0x140009041  mov     rsi, rcx
0x140009044  jnz     short loc_14000905C
0x140009046  mov     al, [rcx+0B50h]
0x14000904c  neg     al
0x14000904e  sbb     eax, eax
0x140009050  not     eax
0x140009052  and     eax, 0C00000BBh
0x140009057  jmp     loc_140009325
0x14000905c  mov     edx, 48h ; 'H'
0x140009061  mov     r8d, 636D6B56h
0x140009067  lea     ecx, [rdx-8]
0x14000906a  call    cs:__imp_ExAllocatePool2
0x140009071  nop     dword ptr [rax+rax+00h]
0x140009076  mov     rbx, rax
0x140009079  test    rax, rax
0x14000907c  jnz     short loc_140009088
0x14000907e  mov     edi, 0C000009Ah
0x140009083  jmp     loc_140009250
0x140009088  mov     eax, 0FFFFF000h
0x14000908d  mov     [rsp+68h+Flags], 4; Flags
0x140009095  lea     r9d, [rdi+0FFFh]
0x14000909c  mov     [rsp+68h+CacheType], 1; CacheType
0x1400090a4  and     r9, rax; TotalBytes
0x1400090a7  xor     ecx, ecx; LowAddress
0x1400090a9  xor     r8d, r8d; SkipBytes
0x1400090ac  or      rdx, 0FFFFFFFFFFFFFFFFh; HighAddress
0x1400090b0  call    cs:__imp_MmAllocatePagesForMdlEx
0x1400090b7  nop     dword ptr [rax+rax+00h]
0x1400090bc  mov     [rbx+40h], rax
0x1400090c0  test    rax, rax
0x1400090c3  jz      loc_14000919D
0x1400090c9  mov     ecx, [rax+2Ch]
0x1400090cc  lea     r14, [rbx+10h]
0x1400090d0  add     ecx, [rax+20h]
0x1400090d3  mov     ebp, [rax+28h]
0x1400090d6  and     ecx, 0FFFh
0x1400090dc  mov     [rbx+8], rbx
0x1400090e0  add     rbp, 0FFFh
0x1400090e7  mov     [rbx], rbx
0x1400090ea  add     rbp, rcx
0x1400090ed  mov     [r14+8], r14
0x1400090f1  mov     [r14], r14
0x1400090f4  shr     rbp, 0Ch
0x1400090f8  mov     [rbx+2Ch], ebp
0x1400090fb  mov     [rbx+31h], r15b
0x1400090ff  cmp     byte ptr [rsi+0B50h], 0
0x140009106  jz      short loc_14000912F
0x140009108  mov     rax, [rsi+0A60h]
0x14000910f  mov     r8d, 1
0x140009115  mov     rdx, [rbx+40h]
0x140009119  mov     rcx, [rsi+940h]
0x140009120  call    _guard_dispatch_icall
0x140009125  mov     edi, eax
0x140009127  test    eax, eax
0x140009129  js      short loc_1400091A2
0x14000912b  mov     byte ptr [rbx+30h], 1
0x14000912f  mov     rdi, [rbx+40h]
0x140009133  test    byte ptr [rdi+0Ah], 5
0x140009137  jz      short loc_14000913F
0x140009139  mov     r15, [rdi+18h]
0x14000913d  jmp     short loc_14000916A
0x14000913f  xor     r9d, r9d; RequestedAddress
0x140009142  mov     [rsp+68h+Flags], 40000010h; Priority
0x14000914a  xor     edx, edx; AccessMode
0x14000914c  mov     [rsp+68h+CacheType], 0; BugCheckOnFailure
0x140009154  mov     rcx, rdi; MemoryDescriptorList
0x140009157  lea     r8d, [r9+1]; CacheType
0x14000915b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x140009162  nop     dword ptr [rax+rax+00h]
0x140009167  mov     r15, rax
0x14000916a  test    r15, r15
0x14000916d  jz      short loc_14000919D
0x14000916f  mov     eax, ebp
0x140009171  mov     ecx, 40h ; '@'
0x140009176  mov     r8d, 636D6B56h
0x14000917c  lea     rdx, [rax+rax*4]
0x140009180  shl     rdx, 3
0x140009184  call    cs:__imp_ExAllocatePool2
0x14000918b  nop     dword ptr [rax+rax+00h]
0x140009190  mov     [rbx+20h], rax
0x140009194  test    rax, rax
0x140009197  jnz     loc_14000925A
0x14000919d  mov     edi, 0C000009Ah
0x1400091a2  mov     rcx, [rbx+20h]; P
0x1400091a6  test    rcx, rcx
0x1400091a9  jz      short loc_1400091C4
0x1400091ab  mov     edx, 636D6B56h; Tag
0x1400091b0  call    cs:__imp_ExFreePoolWithTag
0x1400091b7  nop     dword ptr [rax+rax+00h]
0x1400091bc  mov     qword ptr [rbx+20h], 0
0x1400091c4  mov     rcx, [rbx+40h]
0x1400091c8  test    rcx, rcx
0x1400091cb  jz      short loc_14000923C
0x1400091cd  test    byte ptr [rcx+0Ah], 1
0x1400091d1  jz      short loc_1400091E6
0x1400091d3  mov     rdx, rcx; MemoryDescriptorList
0x1400091d6  mov     rcx, [rcx+18h]; BaseAddress
0x1400091da  call    cs:__imp_MmUnmapLockedPages
0x1400091e1  nop     dword ptr [rax+rax+00h]
0x1400091e6  cmp     byte ptr [rbx+30h], 0
0x1400091ea  jz      short loc_14000921A
0x1400091ec  mov     rax, [rsi+0A60h]
0x1400091f3  mov     r8d, 3
0x1400091f9  mov     rdx, [rbx+40h]
0x1400091fd  mov     rcx, [rsi+940h]
0x140009204  call    _guard_dispatch_icall
0x140009209  mov     edi, eax
0x14000920b  test    eax, eax
0x14000920d  jns     short loc_140009216
0x14000920f  mov     ecx, 3Ah ; ':'
0x140009214  int     29h; Win8: RtlFailFast(ecx)
0x140009216  mov     byte ptr [rbx+30h], 0
0x14000921a  mov     rcx, [rbx+40h]; MemoryDescriptorList
0x14000921e  call    cs:__imp_MmFreePagesFromMdl
0x140009225  nop     dword ptr [rax+rax+00h]
0x14000922a  mov     rcx, [rbx+40h]; P
0x14000922e  xor     edx, edx; Tag
0x140009230  call    cs:__imp_ExFreePoolWithTag
0x140009237  nop     dword ptr [rax+rax+00h]
0x14000923c  mov     edx, 636D6B56h; Tag
0x140009241  mov     rcx, rbx; P
0x140009244  call    cs:__imp_ExFreePoolWithTag
0x14000924b  nop     dword ptr [rax+rax+00h]
0x140009250  mov     eax, 220h
0x140009255  jmp     loc_14000931E
0x14000925a  add     rdi, 30h ; '0'
0x14000925e  xor     r8d, r8d
0x140009261  test    ebp, ebp
0x140009263  jz      short loc_1400092B5
0x140009265  mov     rax, [rbx+20h]
0x140009269  lea     rcx, [r8+r8*4]
0x14000926d  lea     rdx, [rax+rcx*8]
0x140009271  mov     ecx, r8d
0x140009274  mov     [rdx+8], rdx
0x140009278  mov     [rdx], rdx
0x14000927b  mov     rax, [rdi]
0x14000927e  shl     ecx, 0Ch
0x140009281  add     rcx, r15
0x140009284  mov     [rdx+10h], rax
0x140009288  mov     [rdx+20h], rcx
0x14000928c  mov     [rdx+18h], rbx
0x140009290  mov     rax, [r14+8]
0x140009294  cmp     [rax], r14
0x140009297  jnz     short loc_1400092F1
0x140009299  mov     [rdx], r14
0x14000929c  inc     r8d
0x14000929f  mov     [rdx+8], rax
0x1400092a3  mov     [rax], rdx
0x1400092a6  mov     [r14+8], rdx
0x1400092aa  cmp     r8d, ebp
0x1400092ad  jnb     short loc_1400092B5
0x1400092af  add     rdi, 8
0x1400092b3  jmp     short loc_140009265
0x1400092b5  cmp     byte ptr [rbx+31h], 0
0x1400092b9  jnz     short loc_1400092CB
0x1400092bb  call    cs:__imp_KeQueryUnbiasedInterruptTime
0x1400092c2  nop     dword ptr [rax+rax+00h]
0x1400092c7  mov     [rbx+38h], rax
0x1400092cb  lea     rdi, [rsi+100h]
0x1400092d2  mov     rcx, rdi; SpinLock
0x1400092d5  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400092dc  nop     dword ptr [rax+rax+00h]
0x1400092e1  lea     rcx, [rsi+0B58h]
0x1400092e8  mov     rdx, [rcx+8]
0x1400092ec  cmp     [rdx], rcx
0x1400092ef  jz      short loc_1400092F8
0x1400092f1  mov     ecx, 3
0x1400092f6  int     29h; Win8: RtlFailFast(ecx)
0x1400092f8  mov     [rbx], rcx
0x1400092fb  mov     [rbx+8], rdx
0x1400092ff  mov     [rdx], rbx
0x140009302  mov     dl, al; NewIrql
0x140009304  mov     [rcx+8], rbx
0x140009308  mov     rcx, rdi; SpinLock
0x14000930b  call    cs:__imp_KeReleaseSpinLock
0x140009312  nop     dword ptr [rax+rax+00h]
0x140009317  xor     edi, edi
0x140009319  mov     eax, 218h
0x14000931e  lock inc qword ptr [rax+rsi]
0x140009323  mov     eax, edi
0x140009325  add     rsp, 38h
0x140009329  pop     r15
0x14000932b  pop     r14
0x14000932d  pop     rdi
0x14000932e  pop     rsi
0x14000932f  pop     rbp
0x140009330  pop     rbx
0x140009331  retn
```
