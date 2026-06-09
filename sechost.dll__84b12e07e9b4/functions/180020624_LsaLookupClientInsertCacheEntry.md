# LsaLookupClientInsertCacheEntry

- ea: `0x180020624`
- end: `0x1800207fc`
- name: `LsaLookupClientInsertCacheEntry`
- size: `472`
- prototype: `__int64 __fastcall(PSID SourceSid, PSID, PCUNICODE_STRING String2, PCUNICODE_STRING, __int64, __int64, int)`
- caller_count: `2`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, installer_update`

## callers

- `0x180020adc`
- `0x180020d40`

## callees

- `0x180013ea8`
- `0x1800194cc`
- `0x18001bedc`
- `0x18001fdb4`
- `0x180020624`
- `0x180020804`
- `0x180020964`
- `0x1800215c8`

## import_xrefs

- `ntdll!RtlCopySid` at `0x180020698`
- `ntdll!RtlCopySid` at `0x1800206c1`
- `ntdll!RtlCopySid` at `0x180020698`
- `ntdll!RtlCopySid` at `0x1800206c1`
- `ntdll!RtlEqualUnicodeString` at `0x180020736`
- `ntdll!RtlEqualUnicodeString` at `0x180020759`
- `ntdll!RtlEqualUnicodeString` at `0x180020736`
- `ntdll!RtlEqualUnicodeString` at `0x180020759`
- `ntdll!RtlLengthSid` at `0x180020679`
- `ntdll!RtlLengthSid` at `0x1800206a1`
- `ntdll!RtlLengthSid` at `0x180020679`
- `ntdll!RtlLengthSid` at `0x1800206a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800207b1`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800207b1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020706`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180020706`

## pseudocode

```c
__int64 __fastcall LsaLookupClientInsertCacheEntry(
        PSID SourceSid,
        PSID a2,
        PCUNICODE_STRING String2,
        PCUNICODE_STRING a4,
        __int64 a5,
        __int64 a6,
        int a7)
{
  int updated; // edi
  __int64 Memory; // rax
  _QWORD *v13; // rbx
  __int64 v14; // rdi
  void *v15; // rax
  __int64 v16; // rdi
  void *v17; // rax
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // r14
  bool v21; // bp
  bool v22; // si
  __int64 inserted; // rax
  _BYTE v25[8]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v26[8]; // [rsp+38h] [rbp-40h] BYREF

  updated = 0;
  v25[0] = 0;
  if ( (unsigned __int8)LsaLookupClientIsWellKnownSid(SourceSid) )
  {
    Memory = LsaLookupClientAllocateMemory(96);
    v26[0] = Memory;
    v13 = (_QWORD *)Memory;
    if ( !Memory )
      goto LABEL_3;
    *(_BYTE *)(Memory + 88) = 0;
    v14 = RtlLengthSid(SourceSid);
    v15 = (void *)LsaLookupClientAllocateMemory(v14);
    *v13 = v15;
    if ( !v15 )
      goto LABEL_3;
    RtlCopySid(v14, v15, SourceSid);
    v16 = RtlLengthSid(a2);
    v17 = (void *)LsaLookupClientAllocateMemory(v16);
    v13[1] = v17;
    if ( v17 )
    {
      RtlCopySid(v16, v17, a2);
      updated = LsaLookupClientUpdateCacheNames((_DWORD)v13, (_DWORD)String2, (_DWORD)a4, a5, a6, a7);
      if ( updated >= 0 )
      {
        AcquireSRWLockExclusive(&LsaLookupClientSidCacheLock);
        v20 = RtlLookupElementGenericTable2(v18, v13);
        if ( !v20 )
          goto LABEL_14;
        v21 = 0;
        v22 = 0;
        if ( String2 )
          v21 = RtlEqualUnicodeString((PCUNICODE_STRING)(v20 + 24), String2, 1u) != 0;
        if ( a4 )
          v22 = RtlEqualUnicodeString((PCUNICODE_STRING)(v20 + 40), a4, 1u) != 0;
        if ( !v21 || !v22 )
        {
LABEL_14:
          inserted = RtlInsertElementGenericTable2(v19, v13, v25);
          if ( inserted )
          {
            v13 = 0;
            *(_BYTE *)(inserted + 88) = 1;
            v26[0] = 0;
          }
          else
          {
            updated = -1073741823;
          }
        }
        ReleaseSRWLockExclusive(&LsaLookupClientSidCacheLock);
      }
    }
    else
    {
LABEL_3:
      updated = -1073741801;
    }
    if ( v13 )
    {
      if ( v13[1] )
        ((void (*)(void))LsaLookupClientFreeMemory)();
      if ( *v13 )
        LsaLookupClientFreeMemory(v13);
      LsaLookupClientInvalidateNamesByEntry(v13);
      LsaLookupClientFreeMemory(v26);
    }
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x180020624  push    rbx
0x180020626  push    rbp
0x180020627  push    rsi
0x180020628  push    rdi
0x180020629  push    r12
0x18002062b  push    r14
0x18002062d  push    r15
0x18002062f  sub     rsp, 40h
0x180020633  xor     edi, edi
0x180020635  mov     r12, r9
0x180020638  mov     [rsp+78h+var_48], dil
0x18002063d  mov     r15, r8
0x180020640  mov     rbp, rdx
0x180020643  mov     rsi, rcx
0x180020646  call    LsaLookupClientIsWellKnownSid
0x18002064b  test    al, al
0x18002064d  jz      loc_1800207EB
0x180020653  lea     ecx, [rdi+60h]
0x180020656  call    LsaLookupClientAllocateMemory
0x18002065b  mov     [rsp+78h+var_40], rax
0x180020660  mov     rbx, rax
0x180020663  test    rax, rax
0x180020666  jnz     short loc_180020672
0x180020668  mov     edi, 0C0000017h
0x18002066d  jmp     loc_1800207B7
0x180020672  mov     rcx, rsi; Sid
0x180020675  mov     [rax+58h], dil
0x180020679  call    cs:__imp_RtlLengthSid
0x18002067f  mov     ecx, eax
0x180020681  mov     edi, eax
0x180020683  call    LsaLookupClientAllocateMemory
0x180020688  mov     [rbx], rax
0x18002068b  test    rax, rax
0x18002068e  jz      short loc_180020668
0x180020690  mov     r8, rsi; SourceSid
0x180020693  mov     rdx, rax; DestinationSid
0x180020696  mov     ecx, edi; DestinationSidLength
0x180020698  call    cs:__imp_RtlCopySid
0x18002069e  mov     rcx, rbp; Sid
0x1800206a1  call    cs:__imp_RtlLengthSid
0x1800206a7  mov     ecx, eax
0x1800206a9  mov     edi, eax
0x1800206ab  call    LsaLookupClientAllocateMemory
0x1800206b0  mov     [rbx+8], rax
0x1800206b4  test    rax, rax
0x1800206b7  jz      short loc_180020668
0x1800206b9  mov     r8, rbp; SourceSid
0x1800206bc  mov     rdx, rax; DestinationSid
0x1800206bf  mov     ecx, edi; DestinationSidLength
0x1800206c1  call    cs:__imp_RtlCopySid
0x1800206c7  mov     eax, [rsp+78h+arg_30]
0x1800206ce  mov     r8, r12
0x1800206d1  mov     r9, [rsp+78h+arg_20]
0x1800206d9  mov     rdx, r15
0x1800206dc  mov     [rsp+78h+var_50], eax
0x1800206e0  mov     rcx, rbx
0x1800206e3  mov     rax, [rsp+78h+arg_28]
0x1800206eb  mov     [rsp+78h+var_58], rax
0x1800206f0  call    LsaLookupClientUpdateCacheNames
0x1800206f5  mov     edi, eax
0x1800206f7  test    eax, eax
0x1800206f9  js      loc_1800207B7
0x1800206ff  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x180020706  call    cs:__imp_AcquireSRWLockExclusive
0x18002070c  mov     rdx, rbx
0x18002070f  call    RtlLookupElementGenericTable2
0x180020714  mov     r14, rax
0x180020717  mov     eax, 1
0x18002071c  test    r14, r14
0x18002071f  jz      short loc_180020783
0x180020721  xor     bpl, bpl
0x180020724  xor     sil, sil
0x180020727  test    r15, r15
0x18002072a  jz      short loc_18002074A
0x18002072c  lea     rcx, [r14+18h]; String1
0x180020730  mov     r8b, al; CaseInsensitive
0x180020733  mov     rdx, r15; String2
0x180020736  call    cs:__imp_RtlEqualUnicodeString
0x18002073c  test    al, al
0x18002073e  movzx   ebp, bpl
0x180020742  mov     eax, 1
0x180020747  cmovnz  ebp, eax
0x18002074a  test    r12, r12
0x18002074d  jz      short loc_180020771
0x18002074f  lea     rcx, [r14+28h]; String1
0x180020753  mov     r8b, al; CaseInsensitive
0x180020756  mov     rdx, r12; String2
0x180020759  call    cs:__imp_RtlEqualUnicodeString
0x18002075f  movzx   esi, sil
0x180020763  mov     r14d, 1
0x180020769  test    al, al
0x18002076b  cmovnz  esi, r14d
0x18002076f  jmp     short loc_180020777
0x180020771  mov     r14d, 1
0x180020777  test    bpl, bpl
0x18002077a  jz      short loc_180020786
0x18002077c  test    sil, sil
0x18002077f  jnz     short loc_1800207AA
0x180020781  jmp     short loc_180020786
0x180020783  mov     r14d, eax
0x180020786  lea     r8, [rsp+78h+var_48]
0x18002078b  mov     rdx, rbx
0x18002078e  call    RtlInsertElementGenericTable2
0x180020793  test    rax, rax
0x180020796  jnz     short loc_18002079F
0x180020798  mov     edi, 0C0000001h
0x18002079d  jmp     short loc_1800207AA
0x18002079f  xor     ebx, ebx
0x1800207a1  mov     [rax+58h], r14b
0x1800207a5  mov     [rsp+78h+var_40], rbx
0x1800207aa  lea     rcx, LsaLookupClientSidCacheLock; SRWLock
0x1800207b1  call    cs:__imp_ReleaseSRWLockExclusive
0x1800207b7  test    rbx, rbx
0x1800207ba  jz      short loc_1800207EB
0x1800207bc  lea     rcx, [rbx+8]
0x1800207c0  cmp     qword ptr [rcx], 0
0x1800207c4  jz      short loc_1800207CB
0x1800207c6  call    LsaLookupClientFreeMemory
0x1800207cb  cmp     qword ptr [rbx], 0
0x1800207cf  jz      short loc_1800207D9
0x1800207d1  mov     rcx, rbx
0x1800207d4  call    LsaLookupClientFreeMemory
0x1800207d9  mov     rcx, rbx
0x1800207dc  call    LsaLookupClientInvalidateNamesByEntry
0x1800207e1  lea     rcx, [rsp+78h+var_40]
0x1800207e6  call    LsaLookupClientFreeMemory
0x1800207eb  mov     eax, edi
0x1800207ed  add     rsp, 40h
0x1800207f1  pop     r15
0x1800207f3  pop     r14
0x1800207f5  pop     r12
0x1800207f7  pop     rdi
0x1800207f8  pop     rsi
0x1800207f9  pop     rbp
0x1800207fa  pop     rbx
0x1800207fb  retn
```
