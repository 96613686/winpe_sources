# NfsResMgrResourceRegister

- ea: `0x14001318c`
- end: `0x1400134cd`
- name: `NfsResMgrResourceRegister`
- size: `833`
- prototype: ``
- caller_count: `5`
- callee_count: `12`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000a2d0`
- `0x140010da8`
- `0x140012468`
- `0x140024078`
- `0x140024514`

## callees

- `0x1400122e0`
- `0x140012bf0`
- `0x140012d8c`
- `0x14001318c`
- `0x140013738`
- `0x140013828`
- `0x140014814`
- `0x140014984`
- `0x140014b34`
- `0x140014ce0`
- `0x140015230`
- `0x140015b40`

## import_xrefs

- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140013446`
- `ntoskrnl!RtlInsertElementGenericTableAvl` at `0x140013446`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001341d`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14001341d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001345d`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14001345d`
- `ntoskrnl!KeInitializeSpinLock` at `0x140013286`
- `ntoskrnl!KeInitializeSpinLock` at `0x140013286`
- `ntoskrnl!ExAllocatePool2` at `0x14001322a`
- `ntoskrnl!ExAllocatePool2` at `0x14001322a`

## pseudocode

```c
__int64 __fastcall NfsResMgrResourceRegister(unsigned int *a1, __int64 *a2)
{
  __int64 v4; // rcx
  int v5; // eax
  int v6; // edi
  __int64 v7; // rbx
  unsigned __int32 v8; // eax
  void *Pool2; // rax
  int v10; // ecx
  __int128 v11; // xmm0
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // r9
  PVOID inserted; // rax
  PVOID v17; // rsi
  int v18; // ecx
  __int64 v19; // rax
  _BYTE LockHandle[32]; // [rsp+20h] [rbp-50h] BYREF
  __int128 Buffer; // [rsp+40h] [rbp-30h] BYREF
  __int128 v23; // [rsp+50h] [rbp-20h]
  __int64 v24; // [rsp+60h] [rbp-10h]
  unsigned __int8 NewElement; // [rsp+A0h] [rbp+30h] BYREF
  __int64 v26; // [rsp+A8h] [rbp+38h] BYREF

  v4 = *a1;
  v26 = 0;
  Buffer = 0;
  v24 = 0;
  v23 = 0;
  NewElement = 0;
  memset(LockHandle, 0, sizeof(LockHandle));
  v5 = NfsResMgrpResourceRecordLookupAndReference(v4, &v26);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v7 = v26;
    v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v26 + 4), 0, 0);
    if ( NfsRefHistoryTracingpGlobal )
      NfsReferenceHistoryCaptureRecord(v7, v8, 1);
    _InterlockedDecrement((volatile signed __int32 *)(v7 + 4));
    v6 = -1068285911;
    goto LABEL_29;
  }
  if ( v5 != -1068285916 )
  {
    v7 = v26;
    goto LABEL_29;
  }
  Pool2 = (void *)ExAllocatePool2(66, 416, 1128616530);
  v7 = (__int64)Pool2;
  if ( !Pool2 )
  {
    v6 = -1073741670;
    goto LABEL_26;
  }
  memset(Pool2, 0, 0x1A0u);
  *(_DWORD *)v7 = 1128616530;
  *(_DWORD *)(v7 + 4) = 0;
  *(_WORD *)(v7 + 8) = 0;
  *(_QWORD *)(v7 + 408) = 0;
  *(_QWORD *)(v7 + 400) = 0;
  *(_DWORD *)(v7 + 40) = *a1;
  *(_DWORD *)(v7 + 44) = a1[1];
  *(_DWORD *)(v7 + 48) = a1[2];
  KeInitializeSpinLock((PKSPIN_LOCK)(v7 + 24));
  *(_DWORD *)(v7 + 256) = 655360;
  *(_QWORD *)(v7 + 264) = v7 + 272;
  *(_WORD *)(v7 + 272) = 0;
  v6 = NfsCfgMgrpResourceRegistrationTransfer(a1, v7);
  if ( v6 >= 0 )
  {
    if ( (*(_DWORD *)(v7 + 412) & 0x446) != 2
      || (v10 = *(_DWORD *)(v7 + 412) | 4,
          *(_OWORD *)(v7 + 128) = *(_OWORD *)(a1 + 22),
          *(_QWORD *)(v7 + 144) = *((_QWORD *)a1 + 13),
          *(_DWORD *)(v7 + 412) = v10,
          (v10 & 0x28A) != 2) )
    {
LABEL_25:
      v6 = -1068285909;
      goto LABEL_26;
    }
    *(_OWORD *)(v7 + 152) = *((_OWORD *)a1 + 7);
    *(_OWORD *)(v7 + 168) = *((_OWORD *)a1 + 8);
    *(_OWORD *)(v7 + 184) = *((_OWORD *)a1 + 9);
    *(_OWORD *)(v7 + 200) = *((_OWORD *)a1 + 10);
    v11 = *((_OWORD *)a1 + 11);
    *(_DWORD *)(v7 + 412) = v10 | 8;
    *(_OWORD *)(v7 + 216) = v11;
    v6 = NfsCfgMgrpResourceRegistrationApplyDefaultValues(v7);
    if ( v6 >= 0 )
    {
      v6 = NfsCfgMgrpResourceRegistrationValidate(
             v13,
             v12,
             v14,
             v15,
             *(_QWORD *)LockHandle,
             *(_QWORD *)&LockHandle[8],
             *(_QWORD *)&LockHandle[16],
             *(_QWORD *)&LockHandle[24],
             Buffer);
      if ( v6 >= 0 )
      {
        v6 = NfsPolMgrpResourceRegistrationValidate(v7);
        if ( v6 >= 0 )
        {
          v6 = NfsMemMgrpResourceRegistrationValidate(v7);
          if ( v6 >= 0 )
          {
            v6 = NfsCfgMgrpResourceRegistrationInitialize();
            if ( v6 >= 0 )
            {
              if ( (*(_BYTE *)(v7 + 412) & 0x36) == 0x36 )
              {
                if ( (*(_DWORD *)(v7 + 48) & 8) == 0 )
                  goto LABEL_20;
                if ( (*(_DWORD *)(v7 + 412) & 0x440) == 0x40 )
                {
                  *(_DWORD *)(v7 + 412) |= 0x400u;
LABEL_20:
                  v6 = NfsMemMgrpResourceRegistrationInitialize(v7);
                  if ( v6 >= 0 )
                  {
                    DWORD2(v23) = *(_DWORD *)(v7 + 40);
                    v24 = v7;
                    *(_QWORD *)&v23 = 0;
                    *(_QWORD *)&Buffer = 1163154002;
                    WORD4(Buffer) = 0;
                    KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)NfsResMgrpRoot + 3, (PKLOCK_QUEUE_HANDLE)LockHandle);
                    LockHandle[24] = 1;
                    inserted = RtlInsertElementGenericTableAvl(
                                 (PRTL_AVL_TABLE)((char *)NfsResMgrpRoot + 48),
                                 &Buffer,
                                 0x28u,
                                 &NewElement);
                    LockHandle[24] = 0;
                    v17 = inserted;
                    KeReleaseInStackQueuedSpinLock((PKLOCK_QUEUE_HANDLE)LockHandle);
                    if ( NewElement )
                      goto LABEL_29;
                    v18 = -1068285911;
                    if ( !v17 )
                      v18 = -1073741670;
                    v6 = v18;
                  }
                  goto LABEL_26;
                }
              }
              goto LABEL_25;
            }
          }
        }
      }
    }
  }
LABEL_26:
  if ( v7 )
  {
    *(_DWORD *)(v7 + 412) |= 1u;
    NfsResMgrpResourceRecordCleanAndDelete((struct _LOOKASIDE_LIST_EX *)v7);
    v7 = 0;
  }
LABEL_29:
  if ( a2 )
  {
    v19 = 0;
    if ( v6 >= 0 )
      v19 = v7;
    *a2 = v19;
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x14001318c  mov     [rsp-28h+arg_10], rbx
0x140013191  push    rbp
0x140013192  push    rsi
0x140013193  push    rdi
0x140013194  push    r14
0x140013196  push    r15
0x140013198  mov     rbp, rsp
0x14001319b  sub     rsp, 70h
0x14001319f  xorps   xmm0, xmm0
0x1400131a2  mov     r14, rdx
0x1400131a5  mov     rsi, rcx
0x1400131a8  lea     rdx, [rbp+arg_8]
0x1400131ac  mov     ecx, [rcx]
0x1400131ae  xor     r15d, r15d
0x1400131b1  xor     eax, eax
0x1400131b3  mov     [rbp+arg_8], r15
0x1400131b7  movups  [rbp+Buffer], xmm0
0x1400131bb  mov     [rbp+var_10], rax
0x1400131bf  movups  [rbp+var_20], xmm0
0x1400131c3  mov     [rbp+NewElement], r15b
0x1400131c7  movups  xmmword ptr [rbp+LockHandle], xmm0
0x1400131cb  movups  xmmword ptr [rbp+LockHandle+10h], xmm0
0x1400131cf  call    NfsResMgrpResourceRecordLookupAndReference
0x1400131d4  mov     edi, eax
0x1400131d6  test    eax, eax
0x1400131d8  js      short loc_14001320D
0x1400131da  mov     rbx, [rbp+arg_8]
0x1400131de  mov     ecx, r15d
0x1400131e1  xor     eax, eax
0x1400131e3  lock cmpxchg [rbx+4], ecx
0x1400131e8  cmp     cs:NfsRefHistoryTracingpGlobal, r15
0x1400131ef  jz      short loc_1400131FF
0x1400131f1  lea     r8d, [r15+1]
0x1400131f5  mov     edx, eax
0x1400131f7  mov     rcx, rbx
0x1400131fa  call    NfsReferenceHistoryCaptureRecord
0x1400131ff  lock dec dword ptr [rbx+4]
0x140013203  mov     edi, 0C0534029h
0x140013208  jmp     loc_1400134A5
0x14001320d  cmp     eax, 0C0534024h
0x140013212  jnz     loc_1400134A1
0x140013218  mov     edi, 43455252h
0x14001321d  mov     edx, 1A0h
0x140013222  mov     r8d, edi
0x140013225  mov     ecx, 42h ; 'B'
0x14001322a  call    cs:__imp_ExAllocatePool2
0x140013231  nop     dword ptr [rax+rax+00h]
0x140013236  mov     rbx, rax
0x140013239  test    rax, rax
0x14001323c  jnz     short loc_140013248
0x14001323e  mov     edi, 0C000009Ah
0x140013243  jmp     loc_140013488
0x140013248  xor     edx, edx; Val
0x14001324a  mov     r8d, 1A0h; Size
0x140013250  mov     rcx, rbx; void *
0x140013253  call    memset
0x140013258  mov     [rbx], edi
0x14001325a  lea     rcx, [rbx+18h]; SpinLock
0x14001325e  mov     [rbx+4], r15d
0x140013262  mov     [rbx+8], r15w
0x140013267  mov     [rbx+198h], r15
0x14001326e  mov     [rbx+190h], r15
0x140013275  mov     eax, [rsi]
0x140013277  mov     [rbx+28h], eax
0x14001327a  mov     eax, [rsi+4]
0x14001327d  mov     [rbx+2Ch], eax
0x140013280  mov     eax, [rsi+8]
0x140013283  mov     [rbx+30h], eax
0x140013286  call    cs:__imp_KeInitializeSpinLock
0x14001328d  nop     dword ptr [rax+rax+00h]
0x140013292  lea     rcx, [rbx+110h]
0x140013299  mov     dword ptr [rbx+100h], 0A0000h
0x1400132a3  mov     [rbx+108h], rcx
0x1400132aa  mov     rdx, rbx
0x1400132ad  mov     [rcx], r15w
0x1400132b1  mov     rcx, rsi
0x1400132b4  call    NfsCfgMgrpResourceRegistrationTransfer
0x1400132b9  mov     edi, eax
0x1400132bb  test    eax, eax
0x1400132bd  js      loc_140013488
0x1400132c3  mov     ecx, [rbx+19Ch]
0x1400132c9  mov     eax, ecx
0x1400132cb  and     eax, 446h
0x1400132d0  cmp     eax, 2
0x1400132d3  jnz     loc_140013483
0x1400132d9  movups  xmm0, xmmword ptr [rsi+58h]
0x1400132dd  or      ecx, 4
0x1400132e0  mov     eax, ecx
0x1400132e2  movups  xmmword ptr [rbx+80h], xmm0
0x1400132e9  and     eax, 28Ah
0x1400132ee  movsd   xmm1, qword ptr [rsi+68h]
0x1400132f3  movsd   qword ptr [rbx+90h], xmm1
0x1400132fb  mov     [rbx+19Ch], ecx
0x140013301  cmp     eax, 2
0x140013304  jnz     loc_140013483
0x14001330a  movups  xmm0, xmmword ptr [rsi+70h]
0x14001330e  or      ecx, 8
0x140013311  movups  xmmword ptr [rbx+98h], xmm0
0x140013318  movups  xmm1, xmmword ptr [rsi+80h]
0x14001331f  movups  xmmword ptr [rbx+0A8h], xmm1
0x140013326  movups  xmm0, xmmword ptr [rsi+90h]
0x14001332d  movups  xmmword ptr [rbx+0B8h], xmm0
0x140013334  movups  xmm1, xmmword ptr [rsi+0A0h]
0x14001333b  movups  xmmword ptr [rbx+0C8h], xmm1
0x140013342  movups  xmm0, xmmword ptr [rsi+0B0h]
0x140013349  mov     [rbx+19Ch], ecx
0x14001334f  mov     rcx, rbx
0x140013352  movups  xmmword ptr [rbx+0D8h], xmm0
0x140013359  call    NfsCfgMgrpResourceRegistrationApplyDefaultValues
0x14001335e  mov     edi, eax
0x140013360  test    eax, eax
0x140013362  js      loc_140013488
0x140013368  call    NfsCfgMgrpResourceRegistrationValidate
0x14001336d  mov     edi, eax
0x14001336f  test    eax, eax
0x140013371  js      loc_140013488
0x140013377  mov     rcx, rbx
0x14001337a  call    NfsPolMgrpResourceRegistrationValidate
0x14001337f  mov     edi, eax
0x140013381  test    eax, eax
0x140013383  js      loc_140013488
0x140013389  mov     rcx, rbx
0x14001338c  call    NfsMemMgrpResourceRegistrationValidate
0x140013391  mov     edi, eax
0x140013393  test    eax, eax
0x140013395  js      loc_140013488
0x14001339b  call    NfsCfgMgrpResourceRegistrationInitialize
0x1400133a0  mov     edi, eax
0x1400133a2  test    eax, eax
0x1400133a4  js      loc_140013488
0x1400133aa  mov     ecx, [rbx+19Ch]
0x1400133b0  mov     eax, ecx
0x1400133b2  and     eax, 36h
0x1400133b5  cmp     al, 36h ; '6'
0x1400133b7  jnz     loc_140013483
0x1400133bd  mov     eax, [rbx+30h]
0x1400133c0  test    al, 8
0x1400133c2  jz      short loc_1400133DE
0x1400133c4  mov     eax, ecx
0x1400133c6  and     eax, 440h
0x1400133cb  cmp     eax, 40h ; '@'
0x1400133ce  jnz     loc_140013483
0x1400133d4  bts     ecx, 0Ah
0x1400133d8  mov     [rbx+19Ch], ecx
0x1400133de  mov     rcx, rbx
0x1400133e1  call    NfsMemMgrpResourceRegistrationInitialize
0x1400133e6  mov     edi, eax
0x1400133e8  test    eax, eax
0x1400133ea  js      loc_140013488
0x1400133f0  mov     eax, [rbx+28h]
0x1400133f3  lea     rdx, [rbp+LockHandle]; LockHandle
0x1400133f7  mov     rcx, cs:NfsResMgrpRoot
0x1400133fe  mov     dword ptr [rbp+var_20+8], eax
0x140013401  add     rcx, 18h; SpinLock
0x140013405  mov     [rbp+var_10], rbx
0x140013409  mov     qword ptr [rbp+var_20], r15
0x14001340d  mov     dword ptr [rbp+Buffer], 45545252h
0x140013414  mov     dword ptr [rbp+Buffer+4], r15d
0x140013418  mov     word ptr [rbp+Buffer+8], r15w
0x14001341d  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x140013424  nop     dword ptr [rax+rax+00h]
0x140013429  mov     rcx, cs:NfsResMgrpRoot
0x140013430  lea     r9, [rbp+NewElement]; NewElement
0x140013434  add     rcx, 30h ; '0'; Table
0x140013438  mov     [rbp+LockHandle+18h], 1
0x14001343c  mov     r8d, 28h ; '('; BufferSize
0x140013442  lea     rdx, [rbp+Buffer]; Buffer
0x140013446  call    cs:__imp_RtlInsertElementGenericTableAvl
0x14001344d  nop     dword ptr [rax+rax+00h]
0x140013452  lea     rcx, [rbp+LockHandle]; LockHandle
0x140013456  mov     [rbp+LockHandle+18h], r15b
0x14001345a  mov     rsi, rax
0x14001345d  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x140013464  nop     dword ptr [rax+rax+00h]
0x140013469  cmp     [rbp+NewElement], r15b
0x14001346d  jnz     short loc_1400134A5
0x14001346f  mov     edi, 0C000009Ah
0x140013474  test    rsi, rsi
0x140013477  mov     ecx, 0C0534029h
0x14001347c  cmovz   ecx, edi
0x14001347f  mov     edi, ecx
0x140013481  jmp     short loc_140013488
0x140013483  mov     edi, 0C053402Bh
0x140013488  test    rbx, rbx
0x14001348b  jz      short loc_1400134A5
0x14001348d  or      dword ptr [rbx+19Ch], 1
0x140013494  mov     rcx, rbx; P
0x140013497  call    NfsResMgrpResourceRecordCleanAndDelete
0x14001349c  mov     rbx, r15
0x14001349f  jmp     short loc_1400134A5
0x1400134a1  mov     rbx, [rbp+arg_8]
0x1400134a5  test    r14, r14
0x1400134a8  jz      short loc_1400134B6
0x1400134aa  test    edi, edi
0x1400134ac  mov     rax, r15
0x1400134af  cmovns  rax, rbx
0x1400134b3  mov     [r14], rax
0x1400134b6  mov     rbx, [rsp+70h+arg_10]
0x1400134be  mov     eax, edi
0x1400134c0  add     rsp, 70h
0x1400134c4  pop     r15
0x1400134c6  pop     r14
0x1400134c8  pop     rdi
0x1400134c9  pop     rsi
0x1400134ca  pop     rbp
0x1400134cb  retn
```
