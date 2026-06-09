# SkmmAccessFault

- ea: `0x1400855c0`
- end: `0x140085bf1`
- name: `SkmmAccessFault`
- size: `1585`
- prototype: `__int64 __fastcall(__int64, int, char)`
- caller_count: `6`
- callee_count: `24`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400280b0`
- `0x140031148`
- `0x1400341c8`
- `0x1400671bc`
- `0x14006977c`
- `0x1400f6b00`

## callees

- `0x1400017f4`
- `0x14000e460`
- `0x14000e810`
- `0x14000ff70`
- `0x1400119c4`
- `0x1400202b0`
- `0x1400202ec`
- `0x14003a10c`
- `0x1400801fc`
- `0x1400802ac`
- `0x140083484`
- `0x1400834c0`
- `0x1400839bc`
- `0x140083bc8`
- `0x1400843c8`
- `0x14008451c`
- `0x1400848dc`
- `0x140084a38`
- `0x140084afc`
- `0x140084c54`
- `0x140085398`
- `0x1400853c8`
- `0x1400855c0`
- `0x1400f3620`

## pseudocode

```c
__int64 __fastcall SkmmAccessFault(ULONG_PTR BugCheckParameter4, unsigned __int64 a2, char a3, ULONG_PTR a4)
{
  char v4; // bl
  unsigned __int64 v7; // rcx
  __int64 result; // rax
  _QWORD *ValidPteAddress; // rax
  unsigned __int64 v10; // rax
  _QWORD *StackBase; // rdi
  __int64 v12; // rdi
  __int64 v13; // r12
  int v14; // edx
  __int64 *v15; // rax
  __int64 *v16; // rcx
  __int64 v17; // r14
  __int64 v18; // rax
  char v19; // r13
  int IsLeafPteValid; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  int v23; // eax
  int v24; // ebx
  unsigned int v25; // r13d
  unsigned __int64 v26; // r8
  int v27; // r9d
  __int64 v28; // r9
  int v29; // r8d
  int v30; // r8d
  char v31; // [rsp+50h] [rbp-B0h]
  int v33; // [rsp+54h] [rbp-ACh] BYREF
  __int64 *v34; // [rsp+58h] [rbp-A8h]
  ULONG_PTR BugCheckParameter3; // [rsp+60h] [rbp-A0h]
  __int64 i; // [rsp+68h] [rbp-98h]
  __int64 v37; // [rsp+70h] [rbp-90h]
  __int128 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+88h] [rbp-78h]
  _QWORD v40[8]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v41[16]; // [rsp+D0h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-20h]
  __int64 v43; // [rsp+E8h] [rbp-18h]
  int v44; // [rsp+F0h] [rbp-10h]
  __int64 v45; // [rsp+F8h] [rbp-8h]

  BugCheckParameter3 = a4;
  v39 = 0;
  v4 = a3;
  v38 = 0;
  if ( (BugCheckParameter4 & 8) != 0 )
    SkeBugCheckEx(0x1Au, 0x56534Du, 0x61941u, a2, BugCheckParameter4);
  if ( (__int64)a2 >> 47 != -1 && (__int64)a2 >> 47 != 0 )
  {
    if ( a3 == 1 )
      return 3221225477LL;
    goto LABEL_99;
  }
  if ( a2 < 0xFFFF800000000000uLL )
  {
    if ( SkeSmapSupported )
    {
      if ( !a3 && a2 < 0x7FFFFFFF0000LL )
      {
        if ( a4 )
        {
          v10 = __readcr4();
          if ( (v10 & 0x200000) != 0 && (*(_DWORD *)(a4 + 376) & 0x40000) == 0 )
            goto LABEL_99;
        }
      }
    }
    StackBase = KeGetPcr()->NtTib.StackBase;
    if ( !StackBase )
      goto LABEL_99;
    v12 = StackBase[10];
    if ( !v12 )
      return 3221225477LL;
    v13 = 0;
    if ( (*(_DWORD *)v12 & 0x200) != 0 )
    {
      v14 = *(_DWORD *)(v12 + 568);
      if ( a2 >> 12 < (*(unsigned int *)(v12 + 560) | ((unsigned __int64)(v14 & 0xFFF) << 32))
        || a2 >> 12 > (((unsigned __int64)(v14 & 0xFFF000) << 20) | *(unsigned int *)(v12 + 564)) )
      {
        if ( (*(_DWORD *)(v12 + 676) & 1) != 0 && (BugCheckParameter4 & 0x20000) == 0
          || (BugCheckParameter4 & 0x10) != 0 )
        {
          return 3221225477LL;
        }
        v13 = v12;
        v12 = *(_QWORD *)(v12 + 624);
        SkiAttachProcess(v12);
      }
    }
    v15 = *(__int64 **)(v12 + 72);
    v16 = SkmiSystemPartition;
    v33 = 0;
    if ( v15 )
      v16 = v15;
    v34 = v16;
    v17 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
    v18 = v12 + 8;
    v37 = v12 + 8;
LABEL_34:
    v31 = SkAcquireSpinLockShared(v18);
    v19 = v31;
    if ( v13 )
      SkAcquireSpinLockSharedAtDpcLevel(v12 + 192);
    IsLeafPteValid = SkmiIsLeafPteValid(v17);
    if ( !IsLeafPteValid && !v13 )
    {
      v24 = -1073741819;
LABEL_91:
      LOBYTE(v21) = v19;
      RtlpReleasePropStoreLockShared(v37, v21);
      if ( v24 == -2147483647 )
        v24 = SkmiCheckForUserStackOverflow(a2);
LABEL_95:
      if ( v33 )
        SkmiTrimIntegrityTable();
      return (unsigned int)v24;
    }
    v22 = v17 & -(__int64)(IsLeafPteValid != 0);
    for ( i = v22; ; v22 = i )
    {
      v43 = *(_QWORD *)(v12 + 200);
      if ( v13 )
      {
        v24 = -1073741802;
        if ( v22 && (*(_QWORD *)v17 & 1) != 0 )
        {
          v24 = SkmiAccessAllowed(*(_QWORD *)v17, BugCheckParameter4);
          if ( v24 >= 0 )
            v40[0] = (v26 >> 12) & 0xFFFFFFFFFFLL | 0x10000000000000LL;
          else
            v24 = v27;
        }
        _InterlockedDecrement((volatile signed __int32 *)(v12 + 192));
        SkTrackSpinLockRelease();
      }
      else
      {
        v23 = SkmiJoinFaultChain(v12, v19, v4, BugCheckParameter4, BugCheckParameter3);
        v24 = v23;
        if ( v23 == -1073741267 )
        {
          LOBYTE(v21) = v19;
          RtlpReleasePropStoreLockShared(v12 + 8, v21);
LABEL_80:
          v4 = a3;
          v18 = v12 + 8;
          goto LABEL_34;
        }
        if ( v23 != -1073741802 )
          goto LABEL_91;
        if ( BugCheckParameter4 != 0x10000 && *(_QWORD *)(v12 + 144) == v12 + 144 )
        {
          v25 = SkmiBuildFaultCluster(a2, v17, v41);
          goto LABEL_52;
        }
      }
      v25 = 1;
LABEL_52:
      LOBYTE(v21) = v31;
      RtlpReleasePropStoreLockShared(v12 + 8, v21);
      if ( v24 == -1073741802 )
      {
        if ( v13 )
        {
          v28 = v34[31];
          v29 = ((BugCheckParameter4 & 2) != 0) + 1;
        }
        else
        {
          if ( (v42 & 0x800) != 0 || (v42 & 0x7000) != 0x5000 )
          {
            if ( (BugCheckParameter4 & 2) != 0 )
              v29 = (v45 != 0) + 65;
            else
              v29 = 65;
          }
          else
          {
            v29 = ((v42 & 0x80u) != 0LL) + 1;
          }
          LODWORD(v28) = 0;
        }
        v24 = SkmiDispatchNormalFault(v12, a2, v29, v28, v25, v40);
      }
      if ( v13 )
      {
        if ( v24 < 0 )
          goto LABEL_84;
        if ( (v40[0] & 0x80000000000000LL) != 0 )
        {
          v24 = -1073741819;
        }
        else
        {
          result = SkmiCompleteEnclaveContainerFault(
                     v13,
                     (_DWORD)v34,
                     (unsigned int)(a2 >> 9) & 0xFFFFFFF8,
                     (unsigned int)v40,
                     v43);
          v24 = result;
          if ( (int)result >= 0 )
            return result;
LABEL_84:
          if ( v24 == -1073741802 )
            goto LABEL_80;
        }
        SkiAttachProcess(v13);
        goto LABEL_95;
      }
      v31 = SkAcquireSpinLockShared(v12 + 8);
      if ( v25 > 1 )
        SkmiCompleteFaultCluster(
          v12,
          (a2 >> 9) & 0xFFFFFFF8,
          v30,
          BugCheckParameter4,
          v24,
          v25,
          (__int64)v41,
          (__int64)v40,
          (__int64)&v33);
      if ( v24 >= 0 && (v40[0] & 0x80000000000000LL) != 0 )
        v24 = -1073741755;
      if ( !(unsigned int)SkmiIsLeafPteValid(v17) )
      {
        v24 = -1073741819;
LABEL_90:
        v19 = v31;
        goto LABEL_91;
      }
      if ( v24 < 0 )
      {
        if ( ((a2 >> 9) & 0x7FFFFFFFF8LL) != 0x98000000000LL )
          SkmiDisconnectFromFaultChain(v17, v41);
        goto LABEL_90;
      }
      v24 = SkmiBeginFaultCompletion(v12, (unsigned int)(a2 >> 9) & 0xFFFFFFF8, (unsigned int)v41, (unsigned int)v40, 1);
      if ( v24 == 259 )
      {
        if ( (v44 & 1) == 0 )
        {
          while ( (v44 & 2) == 0 )
            _mm_pause();
          goto LABEL_75;
        }
        v39 = ((a2 >> 9) & 0x7FFFFFFFF8LL) - 0x98000000000LL;
        *(_QWORD *)&v38 = v41;
        *((_QWORD *)&v38 + 1) = v40;
        v24 = SkmiCompleteFaults((unsigned int)&v38, 1, 1, v12, BugCheckParameter4, (__int64)&v33);
      }
      if ( v24 != -1073741802 )
        goto LABEL_90;
LABEL_75:
      v19 = v31;
      v4 = a3;
    }
  }
  if ( a3 == 1 )
    return 3221225477LL;
  v7 = a2;
  if ( a2 >= 0xFFFFF68000000000uLL )
  {
    do
    {
      if ( v7 > 0xFFFFF6FFFFFFFFFFuLL )
        break;
      v7 = (__int64)(v7 << 25) >> 16;
    }
    while ( v7 >= 0xFFFFF68000000000uLL );
    if ( v7 < 0xFFFF800000000000uLL )
      goto LABEL_103;
  }
  result = SkmiResolveReplicationFault();
  if ( (int)result < 0 )
  {
LABEL_103:
    ValidPteAddress = (_QWORD *)SkmiGetValidPteAddress(a2, 1);
    if ( !ValidPteAddress
      || (*ValidPteAddress & 1) == 0
      || (result = SkmiAccessAllowed(*ValidPteAddress, BugCheckParameter4), (int)result < 0) )
    {
      if ( (unsigned int)SkmiGenerateAccessViolation(a2) )
        return 3221225477LL;
LABEL_99:
      SkmiNonPagedAccessFault(BugCheckParameter4);
    }
  }
  return result;
}

```

## disassembly

```asm
0x1400855c0  mov     [rsp-8+arg_10], rbx
0x1400855c5  push    rbp
0x1400855c6  push    rsi
0x1400855c7  push    rdi
0x1400855c8  push    r12
0x1400855ca  push    r13
0x1400855cc  push    r14
0x1400855ce  push    r15
0x1400855d0  lea     rbp, [rsp-160h]
0x1400855d8  sub     rsp, 260h
0x1400855df  mov     rax, cs:__security_cookie
0x1400855e6  xor     rax, rsp
0x1400855e9  mov     [rbp+190h+var_40], rax
0x1400855f0  xor     eax, eax
0x1400855f2  mov     [rsp+290h+var_230], r9
0x1400855f7  mov     [rbp+190h+var_208], rax
0x1400855fb  mov     bl, r8b
0x1400855fe  mov     [rsp+290h+var_23F], bl
0x140085602  xorps   xmm0, xmm0
0x140085605  mov     r14, r9
0x140085608  mov     rsi, rdx
0x14008560b  mov     r15, rcx
0x14008560e  movups  [rsp+290h+var_218], xmm0
0x140085613  test    cl, 8
0x140085616  jnz     loc_140085BD3
0x14008561c  mov     rax, rdx
0x14008561f  sar     rax, 2Fh
0x140085623  inc     rax
0x140085626  cmp     rax, 1
0x14008562a  ja      loc_140085BBB
0x140085630  mov     r8, 0FFFF800000000000h
0x14008563a  cmp     rdx, r8
0x14008563d  jb      loc_1400856FE
0x140085643  cmp     bl, 1
0x140085646  jz      loc_1400856CE
0x14008564c  mov     rcx, rdx
0x14008564f  mov     rdx, 0FFFFF68000000000h
0x140085659  mov     rax, rdx
0x14008565c  cmp     rcx, rax
0x14008565f  jb      short loc_14008568F
0x140085661  mov     rax, 0FFFFF6FFFFFFFFFFh
0x14008566b  cmp     rcx, rax
0x14008566e  ja      short loc_14008568A
0x140085670  shl     rcx, 19h
0x140085674  mov     rax, rdx
0x140085677  shl     rax, 19h
0x14008567b  sub     rcx, rax
0x14008567e  sar     rcx, 10h
0x140085682  mov     rax, rdx
0x140085685  cmp     rcx, rax
0x140085688  jnb     short loc_140085661
0x14008568a  cmp     rcx, r8
0x14008568d  jb      short loc_140085698
0x14008568f  call    SkmiResolveReplicationFault
0x140085694  test    eax, eax
0x140085696  jns     short loc_1400856D3
0x140085698  mov     edx, 1
0x14008569d  mov     rcx, rsi
0x1400856a0  call    SkmiGetValidPteAddress
0x1400856a5  test    rax, rax
0x1400856a8  jz      short loc_1400856BE
0x1400856aa  mov     rcx, [rax]
0x1400856ad  test    cl, 1
0x1400856b0  jz      short loc_1400856BE
0x1400856b2  mov     rdx, r15
0x1400856b5  call    SkmiAccessAllowed
0x1400856ba  test    eax, eax
0x1400856bc  jns     short loc_1400856D3
0x1400856be  mov     rcx, rsi
0x1400856c1  call    SkmiGenerateAccessViolation
0x1400856c6  test    eax, eax
0x1400856c8  jz      loc_140085BC4
0x1400856ce  mov     eax, 0C0000005h
0x1400856d3  mov     rcx, [rbp+190h+var_40]
0x1400856da  xor     rcx, rsp; StackCookie
0x1400856dd  call    __security_check_cookie
0x1400856e2  mov     rbx, [rsp+290h+arg_10]
0x1400856ea  add     rsp, 260h
0x1400856f1  pop     r15
0x1400856f3  pop     r14
0x1400856f5  pop     r13
0x1400856f7  pop     r12
0x1400856f9  pop     rdi
0x1400856fa  pop     rsi
0x1400856fb  pop     rbp
0x1400856fc  retn
0x1400856fe  cmp     cs:SkeSmapSupported, 0
0x140085705  jz      short loc_14008573A
0x140085707  test    bl, bl
0x140085709  jnz     short loc_14008573A
0x14008570b  mov     rax, 7FFFFFFF0000h
0x140085715  cmp     rsi, rax
0x140085718  jnb     short loc_14008573A
0x14008571a  test    r14, r14
0x14008571d  jz      short loc_14008573A
0x14008571f  mov     rax, cr4
0x140085722  bt      rax, 15h
0x140085727  jnb     short loc_14008573A
0x140085729  test    dword ptr [r9+178h], 40000h
0x140085734  jz      loc_140085BC4
0x14008573a  mov     rdi, gs:8
0x140085743  test    rdi, rdi
0x140085746  jz      loc_140085BC4
0x14008574c  mov     rdi, [rdi+50h]
0x140085750  test    rdi, rdi
0x140085753  jz      loc_1400856CE
0x140085759  xor     r12d, r12d
0x14008575c  test    dword ptr [rdi], 200h
0x140085762  jz      short loc_1400857D4
0x140085764  mov     edx, [rdi+238h]
0x14008576a  mov     r8, rsi
0x14008576d  mov     eax, [rdi+230h]
0x140085773  mov     ecx, edx
0x140085775  and     ecx, 0FFFh
0x14008577b  shr     r8, 0Ch
0x14008577f  shl     rcx, 20h
0x140085783  or      rcx, rax
0x140085786  cmp     r8, rcx
0x140085789  jb      short loc_1400857A3
0x14008578b  mov     eax, [rdi+234h]
0x140085791  and     edx, 0FFF000h
0x140085797  shl     rdx, 14h
0x14008579b  or      rax, rdx
0x14008579e  cmp     r8, rax
0x1400857a1  jbe     short loc_1400857D4
0x1400857a3  mov     eax, [rdi+2A4h]
0x1400857a9  test    al, 1
0x1400857ab  jz      short loc_1400857B8
0x1400857ad  bt      r15, 11h
0x1400857b2  jnb     loc_1400856CE
0x1400857b8  test    r15b, 10h
0x1400857bc  jnz     loc_1400856CE
0x1400857c2  mov     rcx, [rdi+270h]
0x1400857c9  mov     r12, rdi
0x1400857cc  mov     rdi, rcx
0x1400857cf  call    SkiAttachProcess
0x1400857d4  mov     rax, [rdi+48h]
0x1400857d8  lea     rcx, SkmiSystemPartition
0x1400857df  test    rax, rax
0x1400857e2  mov     [rsp+290h+var_23C], 0
0x1400857ea  mov     r14, rsi
0x1400857ed  mov     rdx, 0FFFFF68000000000h
0x1400857f7  cmovnz  rcx, rax
0x1400857fb  shr     r14, 9
0x1400857ff  mov     rax, 7FFFFFFFF8h
0x140085809  mov     [rsp+290h+var_238], rcx
0x14008580e  and     r14, rax
0x140085811  mov     rax, rdx
0x140085814  add     r14, rax
0x140085817  lea     rax, [rdi+8]
0x14008581b  mov     [rsp+290h+var_220], rax
0x140085820  mov     rcx, rax
0x140085823  call    SkAcquireSpinLockShared
0x140085828  mov     [rsp+290h+var_240], al
0x14008582c  mov     r13b, al
0x14008582f  test    r12, r12
0x140085832  jz      short loc_140085840
0x140085834  lea     rcx, [rdi+0C0h]
0x14008583b  call    SkAcquireSpinLockSharedAtDpcLevel
0x140085840  mov     rcx, r14
0x140085843  call    SkmiIsLeafPteValid
0x140085848  test    eax, eax
0x14008584a  jnz     short loc_140085855
0x14008584c  test    r12, r12
0x14008584f  jz      loc_140085B51
0x140085855  neg     eax
0x140085857  sbb     rcx, rcx
0x14008585a  and     rcx, r14
0x14008585d  mov     [rsp+290h+var_228], rcx
0x140085862  mov     rax, [rdi+0C8h]
0x140085869  mov     [rbp+190h+var_1A8], rax
0x14008586d  test    r12, r12
0x140085870  jnz     short loc_1400858DD
0x140085872  mov     rax, [rsp+290h+var_230]
0x140085877  lea     r9, [rbp+190h+var_1C0]
0x14008587b  mov     [rsp+290h+BugCheckParameter3], rax; BugCheckParameter3
0x140085880  mov     r8, r14
0x140085883  mov     [rsp+290h+var_260], r15; __int64
0x140085888  mov     rdx, rsi
0x14008588b  mov     byte ptr [rsp+290h+var_268], bl; char
0x14008588f  mov     rcx, rdi; int
0x140085892  mov     byte ptr [rsp+290h+BugCheckParameter4], r13b; char
0x140085897  call    SkmiJoinFaultChain
0x14008589c  mov     ebx, eax
0x14008589e  cmp     eax, 0C000022Dh
0x1400858a3  jz      loc_140085AF3
0x1400858a9  cmp     eax, 0C0000016h
0x1400858ae  jnz     loc_140085B75
0x1400858b4  cmp     r15, 10000h
0x1400858bb  jz      short loc_140085938
0x1400858bd  lea     rcx, [rdi+90h]
0x1400858c4  cmp     [rcx], rcx
0x1400858c7  jnz     short loc_140085938
0x1400858c9  lea     r8, [rbp+190h+var_1C0]
0x1400858cd  mov     rdx, r14
0x1400858d0  mov     rcx, rsi
0x1400858d3  call    SkmiBuildFaultCluster
0x1400858d8  mov     r13d, eax
0x1400858db  jmp     short loc_14008593E
0x1400858dd  mov     r9d, 0C0000016h
0x1400858e3  mov     ebx, r9d
0x1400858e6  test    rcx, rcx
0x1400858e9  jz      short loc_14008592C
0x1400858eb  mov     r8, [r14]
0x1400858ee  test    r8b, 1
0x1400858f2  jz      short loc_14008592C
0x1400858f4  mov     rdx, r15
0x1400858f7  mov     rcx, r8
0x1400858fa  call    SkmiAccessAllowed
0x1400858ff  mov     ebx, eax
0x140085901  test    eax, eax
0x140085903  jns     short loc_14008590A
0x140085905  mov     ebx, r9d
0x140085908  jmp     short loc_14008592C
0x14008590a  shr     r8, 0Ch
0x14008590e  mov     rax, 0FFFFFFFFFFh
0x140085918  and     r8, rax
0x14008591b  mov     rax, 10000000000000h
0x140085925  or      r8, rax
0x140085928  mov     [rbp+190h+var_200], r8
0x14008592c  lock dec dword ptr [rdi+0C0h]
0x140085933  call    SkTrackSpinLockRelease
0x140085938  mov     r13d, 1
0x14008593e  mov     dl, [rsp+290h+var_240]
0x140085942  lea     rcx, [rdi+8]
0x140085946  call    RtlpReleasePropStoreLockShared
0x14008594b  cmp     ebx, 0C0000016h
0x140085951  jnz     loc_1400859E2
0x140085957  test    r12, r12
0x14008595a  jz      short loc_14008597A
0x14008595c  mov     rax, [rsp+290h+var_238]
0x140085961  mov     r9, [rax+0F8h]
0x140085968  mov     al, r15b
0x14008596b  and     al, 2
0x14008596d  neg     al
0x14008596f  sbb     r8d, r8d
0x140085972  neg     r8d
0x140085975  inc     r8d
0x140085978  jmp     short loc_1400859C7
0x14008597a  mov     rcx, [rbp+190h+var_1B0]
0x14008597e  bt      rcx, 0Bh
0x140085983  jb      short loc_1400859A5
0x140085985  mov     rax, rcx
0x140085988  and     eax, 7000h
0x14008598d  cmp     rax, 5000h
0x140085993  jnz     short loc_1400859A5
0x140085995  and     cl, 80h
0x140085998  neg     cl
0x14008599a  sbb     r8d, r8d
0x14008599d  neg     r8d
0x1400859a0  inc     r8d
0x1400859a3  jmp     short loc_1400859C4
0x1400859a5  test    r15b, 2
0x1400859a9  jnz     short loc_1400859B3
0x1400859ab  mov     r8d, 41h ; 'A'
0x1400859b1  jmp     short loc_1400859C4
0x1400859b3  mov     rax, [rbp+190h+var_198]
0x1400859b7  neg     rax
0x1400859ba  sbb     r8d, r8d
0x1400859bd  neg     r8d
0x1400859c0  add     r8d, 41h ; 'A'; int
0x1400859c4  xor     r9d, r9d; int
0x1400859c7  lea     rax, [rbp+190h+var_200]
0x1400859cb  mov     rdx, rsi; int
0x1400859ce  mov     [rsp+290h+var_268], rax; void *
0x1400859d3  mov     rcx, rdi; int
0x1400859d6  mov     dword ptr [rsp+290h+BugCheckParameter4], r13d; int
0x1400859db  call    SkmiDispatchNormalFault
0x1400859e0  mov     ebx, eax
0x1400859e2  test    r12, r12
0x1400859e5  jnz     loc_140085B0C
0x1400859eb  lea     rcx, [rdi+8]
0x1400859ef  call    SkAcquireSpinLockShared
0x1400859f4  mov     [rsp+290h+var_240], al
0x1400859f8  cmp     r13d, 1
0x1400859fc  jbe     short loc_140085A31
0x1400859fe  lea     rax, [rsp+290h+var_23C]
0x140085a03  mov     r9, r15
0x140085a06  mov     [rsp+290h+var_250], rax
0x140085a0b  mov     rdx, r14
0x140085a0e  lea     rax, [rbp+190h+var_200]
0x140085a12  mov     rcx, rdi
0x140085a15  mov     [rsp+290h+BugCheckParameter3], rax
0x140085a1a  lea     rax, [rbp+190h+var_1C0]
0x140085a1e  mov     [rsp+290h+var_260], rax
0x140085a23  mov     dword ptr [rsp+290h+var_268], r13d
0x140085a28  mov     dword ptr [rsp+290h+BugCheckParameter4], ebx
0x140085a2c  call    SkmiCompleteFaultCluster
0x140085a31  test    ebx, ebx
0x140085a33  js      short loc_140085A4B
0x140085a35  mov     rax, 80000000000000h
0x140085a3f  test    [rbp+190h+var_200], rax
0x140085a43  mov     eax, 0C0000045h
0x140085a48  cmovnz  ebx, eax
0x140085a4b  mov     rcx, r14
0x140085a4e  call    SkmiIsLeafPteValid
0x140085a53  test    eax, eax
0x140085a55  jz      loc_140085B6B
0x140085a5b  test    ebx, ebx
0x140085a5d  js      loc_140085B58
  ... truncated ...
```
