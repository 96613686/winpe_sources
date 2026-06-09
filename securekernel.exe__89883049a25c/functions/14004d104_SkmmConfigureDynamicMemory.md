# SkmmConfigureDynamicMemory

- ea: `0x14004d104`
- end: `0x14004d4b3`
- name: `SkmmConfigureDynamicMemory`
- size: `943`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `20`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140014dd0`

## callees

- `0x140002900`
- `0x140008d00`
- `0x140009520`
- `0x14000b084`
- `0x14000d020`
- `0x140020aec`
- `0x14002ca58`
- `0x14002cb4c`
- `0x140037e68`
- `0x14004c54c`
- `0x14004c800`
- `0x14004c8e0`
- `0x14004c9ac`
- `0x14004cc74`
- `0x14004ce4c`
- `0x14004cf28`
- `0x14004d000`
- `0x14004d104`
- `0x1400521c4`
- `0x140095cd8`

## pseudocode

```c
__int64 __fastcall SkmmConfigureDynamicMemory(unsigned __int64 a1, unsigned __int64 a2, unsigned int a3)
{
  bool v6; // r12
  __int64 v7; // r14
  int v8; // eax
  int inserted; // ebx
  char v10; // r13
  _QWORD *StackBase; // rcx
  __int64 v12; // rcx
  __int64 v13; // rdx
  int v14; // ecx
  unsigned __int64 v15; // r15
  unsigned __int64 v16; // rsi
  __int64 v17; // r8
  unsigned __int64 v18; // r15
  __int64 v19; // r9
  _QWORD *v20; // rcx
  __int64 v21; // rdx
  __int64 v24; // [rsp+78h] [rbp+20h] BYREF

  v6 = (a3 & 0xFFFFFFFD) == 0;
  v7 = 0;
  if ( (a3 & 0xFFFFFFFD) != 0 )
  {
    if ( a3 > 8 || (v8 = 274, !_bittest(&v8, a3)) )
    {
      inserted = -1073741811;
      SkmiDynamicMemorySupport = 0;
      return (unsigned int)inserted;
    }
  }
  v10 = 0;
  if ( a1 > a2 || a1 > 0xFFFFFFFFFFLL || a2 > 0xFFFFFFFFFFLL )
  {
    inserted = -1073741811;
    goto LABEL_56;
  }
  StackBase = KeGetPcr()->NtTib.StackBase;
  if ( StackBase )
  {
    v12 = StackBase[18];
    if ( v12 )
      --*(_WORD *)(v12 + xmmword_140167150);
  }
  SkAcquirePushLockExclusive(&SkmiDynamicMemoryPushLock);
  v7 = SkmiDynamicMemorySupport;
  v24 = SkmiDynamicMemorySupport;
  v10 = 1;
  if ( SkmiDynamicMemorySupport )
  {
    v13 = *(_QWORD *)(SkmiDynamicMemorySupport + 8);
    inserted = -1073741811;
    if ( *(_QWORD *)(v13 + 24) != a1 || (v14 = 0, *(_QWORD *)(v13 + 32) != a2 - a1 + 1) )
      v14 = -1073741811;
    if ( !v6 )
    {
      if ( a3 != 8 )
      {
        if ( *(_BYTE *)(SkmiDynamicMemorySupport + 1) )
        {
          if ( a3 != 1 )
          {
LABEL_57:
            SkmiDynamicMemorySupport = 0;
            if ( v7 )
              SkmiFreeDynamicMemorySupport(v7);
LABEL_59:
            if ( !v10 )
              return (unsigned int)inserted;
            goto LABEL_60;
          }
        }
        else if ( a3 != 4 )
        {
          v14 = -1073741811;
        }
      }
      inserted = v14;
      if ( v14 < 0 )
        goto LABEL_57;
      v15 = a2 - a1;
LABEL_31:
      if ( a3 <= 1 )
      {
        inserted = SkmiSplitNonPfnRegions(a1 >> 18);
        if ( inserted < 0 )
          goto LABEL_56;
        inserted = SkmiSplitNonPfnRegions((unsigned int)(a2 >> 18) + 1);
        if ( inserted < 0 )
          goto LABEL_56;
        inserted = SkmiDemoteNonPfnRegions(a1, a2);
        if ( inserted < 0 )
          goto LABEL_56;
      }
      if ( a3 == 8 )
        goto LABEL_56;
      inserted = SkmiExpandPfnDatabase(a1, a2, 1, 0xFFFFFFFFLL);
      if ( inserted < 0 )
        goto LABEL_56;
      if ( a3 != 1 )
      {
        if ( a3 == 4 )
        {
          v18 = v15 + 1;
          if ( (unsigned int)SkmiInterlockedFillPfnEntries(a1, v18, 1, 1025) )
          {
            inserted = SkmiRemoveMemoryRange(a1, v18, &v24);
            if ( inserted >= 0 )
              SkmiFillPfnEntries(a1, v18, 0);
          }
          else
          {
            SKMI_SECURITY(2050);
            inserted = -1073741800;
          }
        }
        goto LABEL_56;
      }
      v16 = v15 + 1;
      if ( (unsigned __int8)SkmmIsAddressRangeValidMemory(a1, v15 + 1) )
      {
LABEL_39:
        inserted = 255;
        goto LABEL_56;
      }
      if ( !(unsigned int)SkmiPreparePfnsForHotAdd(a1, a2) )
      {
        if ( (unsigned __int8)SkmmIsAddressRangeValidMemory(a1, v16) )
          goto LABEL_39;
        SKMI_SECURITY(2049);
        inserted = -1073741800;
LABEL_56:
        if ( v6 )
          goto LABEL_59;
        goto LABEL_57;
      }
      v24 = 0;
      inserted = SkmiInsertMemoryRange(a1, v16, &v24);
      if ( inserted >= 0 )
      {
        inserted = SkmiProtectHotAddPfns(a1, a2);
        if ( inserted >= 0 )
        {
          SkmiCoalesceMemoryRanges();
          v17 = 0;
LABEL_50:
          SkmiCompletePfnHotAdd(a1, a2, v17);
          goto LABEL_56;
        }
        if ( v24 )
          SkFreePool(512, v24);
        SkmiRemoveMemoryRange(a1, v16, 0);
      }
      v17 = 1;
      goto LABEL_50;
    }
  }
  else
  {
    if ( !v6 )
    {
      inserted = -1073741811;
      goto LABEL_57;
    }
    inserted = SkmiAllocateAndInitializeDynamicMemorySupport(&v24);
    if ( inserted >= 0 )
    {
      v7 = v24;
      v15 = a2 - a1;
      *(_QWORD *)(*(_QWORD *)(v24 + 8) + 24LL) = a1;
      *(_QWORD *)(*(_QWORD *)(v7 + 8) + 32LL) = a2 - a1 + 1;
      if ( !a3 )
        *(_BYTE *)(v7 + 1) = 1;
      SkmiDynamicMemorySupport = v7;
      goto LABEL_31;
    }
  }
LABEL_60:
  RtlReleaseSRWLockExclusive(&SkmiDynamicMemoryPushLock);
  v20 = KeGetPcr()->NtTib.StackBase;
  if ( v20 )
  {
    v21 = v20[18];
    if ( v21 )
    {
      if ( (*(_WORD *)(v21 + xmmword_140167150))++ == 0xFFFF
        && *(_QWORD *)(v21 + xmmword_140167160) != (_QWORD)xmmword_140167160 + v20[17]
        && !*(_WORD *)(v21 + *((_QWORD *)&xmmword_140167150 + 1)) )
      {
        SkiCheckForKernelApcDelivery(xmmword_140167160, v21, 1, v19);
      }
    }
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14004d104  mov     [rsp+arg_0], rbx
0x14004d109  push    rbp
0x14004d10a  push    rsi
0x14004d10b  push    rdi
0x14004d10c  push    r12
0x14004d10e  push    r13
0x14004d110  push    r14
0x14004d112  push    r15
0x14004d114  sub     rsp, 20h
0x14004d118  test    r8d, 0FFFFFFFDh
0x14004d11f  mov     esi, r8d
0x14004d122  mov     rbp, rdx
0x14004d125  mov     rdi, rcx
0x14004d128  setz    r12b
0x14004d12c  xor     r15d, r15d
0x14004d12f  mov     r14d, r15d
0x14004d132  test    r12b, r12b
0x14004d135  jnz     short loc_14004D159
0x14004d137  cmp     r8d, 8
0x14004d13b  ja      short loc_14004D148
0x14004d13d  mov     eax, 112h
0x14004d142  bt      eax, r8d
0x14004d146  jb      short loc_14004D159
0x14004d148  mov     ebx, 0C000000Dh
0x14004d14d  mov     cs:SkmiDynamicMemorySupport, r15
0x14004d154  jmp     loc_14004D49B
0x14004d159  mov     r13b, r15b
0x14004d15c  cmp     rdi, rbp
0x14004d15f  jbe     short loc_14004D16B
0x14004d161  mov     ebx, 0C000000Dh
0x14004d166  jmp     loc_14004D417
0x14004d16b  mov     rax, 0FFFFEFFFFFFFFFFFh
0x14004d175  mov     rcx, 0FFFFE80000000000h
0x14004d17f  sub     rax, rcx
0x14004d182  sar     rax, 3
0x14004d186  cmp     rdi, rax
0x14004d189  ja      short loc_14004D161
0x14004d18b  cmp     rbp, rax
0x14004d18e  ja      short loc_14004D161
0x14004d190  mov     rcx, gs:8
0x14004d199  test    rcx, rcx
0x14004d19c  jz      short loc_14004D1B6
0x14004d19e  mov     rcx, [rcx+90h]
0x14004d1a5  test    rcx, rcx
0x14004d1a8  jz      short loc_14004D1B6
0x14004d1aa  mov     rax, qword ptr cs:xmmword_140167150
0x14004d1b1  dec     word ptr [rcx+rax]
0x14004d1b5  nop
0x14004d1b6  lea     rcx, SkmiDynamicMemoryPushLock
0x14004d1bd  call    SkAcquirePushLockExclusive
0x14004d1c2  mov     r14, cs:SkmiDynamicMemorySupport
0x14004d1c9  mov     r8d, 1
0x14004d1cf  mov     [rsp+58h+arg_18], r14
0x14004d1d4  mov     r13b, r8b
0x14004d1d7  test    r14, r14
0x14004d1da  jz      short loc_14004D235
0x14004d1dc  mov     rdx, [r14+8]
0x14004d1e0  mov     ebx, 0C000000Dh
0x14004d1e5  cmp     [rdx+18h], rdi
0x14004d1e9  jnz     short loc_14004D1FD
0x14004d1eb  mov     rax, rbp
0x14004d1ee  mov     ecx, r15d
0x14004d1f1  sub     rax, rdi
0x14004d1f4  add     rax, r8
0x14004d1f7  cmp     [rdx+20h], rax
0x14004d1fb  jz      short loc_14004D1FF
0x14004d1fd  mov     ecx, ebx
0x14004d1ff  test    r12b, r12b
0x14004d202  jnz     loc_14004D435
0x14004d208  cmp     esi, 8
0x14004d20b  jz      short loc_14004D223
0x14004d20d  cmp     [r14+1], r15b
0x14004d211  jz      short loc_14004D21D
0x14004d213  cmp     esi, r8d
0x14004d216  jz      short loc_14004D223
0x14004d218  jmp     loc_14004D41C
0x14004d21d  cmp     esi, 4
0x14004d220  cmovnz  ecx, ebx
0x14004d223  mov     ebx, ecx
0x14004d225  test    ecx, ecx
0x14004d227  js      loc_14004D41C
0x14004d22d  mov     r15, rbp
0x14004d230  sub     r15, rdi
0x14004d233  jmp     short loc_14004D28C
0x14004d235  test    r12b, r12b
0x14004d238  jnz     short loc_14004D244
0x14004d23a  mov     ebx, 0C000000Dh
0x14004d23f  jmp     loc_14004D41C
0x14004d244  lea     rcx, [rsp+58h+arg_18]
0x14004d249  call    SkmiAllocateAndInitializeDynamicMemorySupport
0x14004d24e  mov     ebx, eax
0x14004d250  test    eax, eax
0x14004d252  js      loc_14004D435
0x14004d258  mov     r14, [rsp+58h+arg_18]
0x14004d25d  mov     r15, rbp
0x14004d260  sub     r15, rdi
0x14004d263  mov     r8d, 1
0x14004d269  mov     rcx, [r14+8]
0x14004d26d  lea     rdx, [r15+1]
0x14004d271  mov     [rcx+18h], rdi
0x14004d275  mov     rcx, [r14+8]
0x14004d279  mov     [rcx+20h], rdx
0x14004d27d  test    esi, esi
0x14004d27f  jnz     short loc_14004D285
0x14004d281  mov     [r14+1], r8b
0x14004d285  mov     cs:SkmiDynamicMemorySupport, r14
0x14004d28c  cmp     esi, r8d
0x14004d28f  ja      short loc_14004D2DA
0x14004d291  mov     rcx, rdi
0x14004d294  shr     rcx, 12h
0x14004d298  call    SkmiSplitNonPfnRegions
0x14004d29d  mov     ebx, eax
0x14004d29f  test    eax, eax
0x14004d2a1  js      loc_14004D414
0x14004d2a7  mov     rcx, rbp
0x14004d2aa  shr     rcx, 12h
0x14004d2ae  inc     ecx
0x14004d2b0  call    SkmiSplitNonPfnRegions
0x14004d2b5  mov     ebx, eax
0x14004d2b7  test    eax, eax
0x14004d2b9  js      loc_14004D414
0x14004d2bf  mov     rdx, rbp
0x14004d2c2  mov     rcx, rdi
0x14004d2c5  call    SkmiDemoteNonPfnRegions
0x14004d2ca  mov     ebx, eax
0x14004d2cc  test    eax, eax
0x14004d2ce  js      loc_14004D414
0x14004d2d4  mov     r8d, 1
0x14004d2da  cmp     esi, 8
0x14004d2dd  jz      loc_14004D414
0x14004d2e3  or      r9d, 0FFFFFFFFh
0x14004d2e7  mov     rdx, rbp
0x14004d2ea  mov     rcx, rdi
0x14004d2ed  call    SkmiExpandPfnDatabase
0x14004d2f2  mov     ebx, eax
0x14004d2f4  test    eax, eax
0x14004d2f6  js      loc_14004D414
0x14004d2fc  mov     r8d, 1
0x14004d302  cmp     esi, r8d
0x14004d305  jnz     loc_14004D3C2
0x14004d30b  lea     rsi, [r15+1]
0x14004d30f  mov     rcx, rdi
0x14004d312  mov     rdx, rsi
0x14004d315  call    SkmmIsAddressRangeValidMemory
0x14004d31a  xor     r15d, r15d
0x14004d31d  test    al, al
0x14004d31f  jz      short loc_14004D32B
0x14004d321  mov     ebx, 0FFh
0x14004d326  jmp     loc_14004D417
0x14004d32b  mov     rdx, rbp
0x14004d32e  mov     rcx, rdi
0x14004d331  call    SkmiPreparePfnsForHotAdd
0x14004d336  mov     rdx, rsi
0x14004d339  mov     rcx, rdi
0x14004d33c  test    eax, eax
0x14004d33e  jnz     short loc_14004D35D
0x14004d340  call    SkmmIsAddressRangeValidMemory
0x14004d345  test    al, al
0x14004d347  jnz     short loc_14004D321
0x14004d349  mov     ecx, 801h
0x14004d34e  call    SKMI_SECURITY
0x14004d353  mov     ebx, 0C0000018h
0x14004d358  jmp     loc_14004D417
0x14004d35d  lea     r8, [rsp+58h+arg_18]
0x14004d362  mov     [rsp+58h+arg_18], r15
0x14004d367  call    SkmiInsertMemoryRange
0x14004d36c  mov     ebx, eax
0x14004d36e  test    eax, eax
0x14004d370  js      short loc_14004D3AF
0x14004d372  mov     rdx, rbp
0x14004d375  mov     rcx, rdi
0x14004d378  call    SkmiProtectHotAddPfns
0x14004d37d  mov     ebx, eax
0x14004d37f  test    eax, eax
0x14004d381  js      short loc_14004D38D
0x14004d383  call    SkmiCoalesceMemoryRanges
0x14004d388  mov     r8d, r15d
0x14004d38b  jmp     short loc_14004D3B5
0x14004d38d  mov     rdx, [rsp+58h+arg_18]
0x14004d392  test    rdx, rdx
0x14004d395  jz      short loc_14004D3A1
0x14004d397  mov     ecx, 200h
0x14004d39c  call    SkFreePool
0x14004d3a1  xor     r8d, r8d
0x14004d3a4  mov     rdx, rsi
0x14004d3a7  mov     rcx, rdi
0x14004d3aa  call    SkmiRemoveMemoryRange
0x14004d3af  mov     r8d, 1
0x14004d3b5  mov     rdx, rbp
0x14004d3b8  mov     rcx, rdi
0x14004d3bb  call    SkmiCompletePfnHotAdd
0x14004d3c0  jmp     short loc_14004D417
0x14004d3c2  cmp     esi, 4
0x14004d3c5  jnz     short loc_14004D414
0x14004d3c7  inc     r15
0x14004d3ca  mov     r9d, 401h
0x14004d3d0  mov     rdx, r15
0x14004d3d3  mov     rcx, rdi
0x14004d3d6  call    SkmiInterlockedFillPfnEntries
0x14004d3db  test    eax, eax
0x14004d3dd  jnz     short loc_14004D3F0
0x14004d3df  mov     ecx, 802h
0x14004d3e4  call    SKMI_SECURITY
0x14004d3e9  mov     ebx, 0C0000018h
0x14004d3ee  jmp     short loc_14004D414
0x14004d3f0  lea     r8, [rsp+58h+arg_18]
0x14004d3f5  mov     rdx, r15
0x14004d3f8  mov     rcx, rdi
0x14004d3fb  call    SkmiRemoveMemoryRange
0x14004d400  mov     ebx, eax
0x14004d402  test    eax, eax
0x14004d404  js      short loc_14004D414
0x14004d406  xor     r8d, r8d
0x14004d409  mov     rdx, r15
0x14004d40c  mov     rcx, rdi
0x14004d40f  call    SkmiFillPfnEntries
0x14004d414  xor     r15d, r15d
0x14004d417  test    r12b, r12b
0x14004d41a  jnz     short loc_14004D430
0x14004d41c  mov     cs:SkmiDynamicMemorySupport, r15
0x14004d423  test    r14, r14
0x14004d426  jz      short loc_14004D430
0x14004d428  mov     rcx, r14
0x14004d42b  call    SkmiFreeDynamicMemorySupport
0x14004d430  test    r13b, r13b
0x14004d433  jz      short loc_14004D49B
0x14004d435  lea     rcx, SkmiDynamicMemoryPushLock
0x14004d43c  call    RtlReleaseSRWLockExclusive
0x14004d441  mov     rcx, gs:8
0x14004d44a  test    rcx, rcx
0x14004d44d  jz      short loc_14004D49B
0x14004d44f  mov     rdx, [rcx+90h]
0x14004d456  test    rdx, rdx
0x14004d459  jz      short loc_14004D49B
0x14004d45b  nop
0x14004d45c  mov     r8d, 1
0x14004d462  mov     rax, qword ptr cs:xmmword_140167150
0x14004d469  add     [rdx+rax], r8w
0x14004d46e  jnz     short loc_14004D49B
0x14004d470  mov     rax, [rcx+88h]
0x14004d477  nop
0x14004d478  mov     rcx, qword ptr cs:xmmword_140167160
0x14004d47f  add     rax, rcx
0x14004d482  cmp     [rdx+rcx], rax
0x14004d486  jz      short loc_14004D49B
0x14004d488  mov     rax, qword ptr cs:xmmword_140167150+8
0x14004d48f  cmp     [rdx+rax], r15w
0x14004d494  jnz     short loc_14004D49B
0x14004d496  call    SkiCheckForKernelApcDelivery
0x14004d49b  mov     eax, ebx
0x14004d49d  mov     rbx, [rsp+58h+arg_0]
0x14004d4a2  add     rsp, 20h
0x14004d4a6  pop     r15
0x14004d4a8  pop     r14
0x14004d4aa  pop     r13
0x14004d4ac  pop     r12
0x14004d4ae  pop     rdi
0x14004d4af  pop     rsi
0x14004d4b0  pop     rbp
0x14004d4b1  retn
```
