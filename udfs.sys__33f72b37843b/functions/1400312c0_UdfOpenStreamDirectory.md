# UdfOpenStreamDirectory

- ea: `0x1400312c0`
- end: `0x1400316e1`
- name: `UdfOpenStreamDirectory`
- size: `1057`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `3`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400177ac`
- `0x14003269c`
- `0x140042c40`

## callees

- `0x140005e80`
- `0x140009730`
- `0x14000b128`
- `0x14000c0ec`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x14001758c`
- `0x14001c080`
- `0x140030818`
- `0x1400312c0`
- `0x14003dec8`
- `0x14003f360`
- `0x14004cf74`
- `0x14004fc70`
- `0x1400537b0`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003155a`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003155a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003163f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b583`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003163f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14005b583`

## pseudocode

```c
__int64 __fastcall UdfOpenStreamDirectory(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 v4; // r15
  __int64 v5; // r14
  int v6; // r8d
  int v8; // edi
  __int64 Scb; // rsi
  char v10; // al
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // r8
  __int64 *v14; // rsi
  __int16 v15; // cx
  __int64 v16; // rcx
  int v17; // edx
  unsigned __int16 v18; // cx
  __int64 v19; // rcx
  char v20; // [rsp+78h] [rbp-F8h]
  char v21; // [rsp+79h] [rbp-F7h]
  _BYTE v22[2]; // [rsp+7Ah] [rbp-F6h] BYREF
  int v23; // [rsp+7Ch] [rbp-F4h]
  int v24; // [rsp+80h] [rbp-F0h] BYREF
  __int64 v25; // [rsp+88h] [rbp-E8h]
  __int64 v26; // [rsp+90h] [rbp-E0h]
  __int64 v27; // [rsp+98h] [rbp-D8h]
  __int64 *v28; // [rsp+A0h] [rbp-D0h]
  __int64 v29; // [rsp+A8h] [rbp-C8h]
  _OWORD v30[2]; // [rsp+B0h] [rbp-C0h] BYREF
  __int64 v31; // [rsp+D0h] [rbp-A0h]
  _BYTE v32[96]; // [rsp+D8h] [rbp-98h] BYREF
  char v35; // [rsp+190h] [rbp+20h] BYREF

  v35 = 0;
  v24 = 0;
  memset(v30, 0, sizeof(v30));
  v31 = 0;
  v4 = *(_QWORD *)(a2 + 136);
  v26 = v4;
  v5 = *(_QWORD *)(v4 + 8);
  v27 = v5;
  memset(v32, 0, sizeof(v32));
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_q(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      23,
      WPP_962a5ab0fb873cc757a84452495a3943_Traceguids,
      v4);
  }
  v28 = (__int64 *)(v4 + 24);
  if ( *(_QWORD *)(v4 + 24) )
    return 0;
  v21 = 0;
  v8 = 0;
  v23 = 0;
  v29 = v5;
  Scb = 0;
  v25 = 0;
  v10 = 0;
  v20 = 0;
  if ( *(_DWORD *)(v4 + 56) )
    goto LABEL_26;
  v11 = a3;
  if ( a3 != 1 && a3 != 4 )
  {
    v12 = *(_DWORD *)(v5 + 48);
    if ( (v12 & 0x10) != 0 )
    {
      v8 = (v12 & 0x20) != 0 ? -1073739770 : -1073741790;
      v23 = v8;
LABEL_28:
      v10 = v20;
      goto LABEL_29;
    }
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
    {
      WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 24, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
    }
    LOBYTE(v6) = 13;
    UdfCreateNewIcb(a1, a2, v6, 0, (__int64)&v24, *(_QWORD *)(a2 + 136) + 96LL, 0);
    v30[0] = 0;
    UdfPrepareModifyIcbForScb(a1, a2, v30);
    v13 = *(_QWORD *)&v30[0];
    *(_DWORD *)(*(_QWORD *)&v30[0] + 156LL) = v24;
    v14 = (__int64 *)(v5 + 16);
    if ( *(_QWORD *)(v5 + 352) )
    {
      v15 = *(_WORD *)(*v14 + 90);
    }
    else
    {
      v16 = *v14;
      if ( (*(_DWORD *)(v5 + 48) & 0x4000000) != 0 )
        v15 = *(_WORD *)(v16 + 84);
      else
        v15 = *(_WORD *)(v16 + 92);
    }
    *(_WORD *)(v13 + 160) = v15;
    v17 = *(_DWORD *)(v5 + 68);
    *(_DWORD *)(v13 + 152) ^= (v17 ^ *(_DWORD *)(v13 + 152)) & 0x3FFFFFFF;
    *(_DWORD *)(v13 + 152) = v17 & 0x3FFFFFFF;
    ++*(_WORD *)(a2 + 500);
    LOBYTE(v13) = 1;
    UdfFinishModifyIcb(a1, v30, v13, a2);
    *(_DWORD *)(v4 + 56) = v24;
    if ( *(_QWORD *)(v5 + 352) )
    {
      v18 = *(_WORD *)(*v14 + 90);
    }
    else
    {
      v19 = *v14;
      if ( (*(_DWORD *)(v5 + 48) & 0x4000000) != 0 )
        v18 = *(_WORD *)(v19 + 84);
      else
        v18 = *(_WORD *)(v19 + 92);
    }
    *(_DWORD *)(v4 + 60) = v18;
    *(_DWORD *)(v4 + 60) = v18 | 0x80000000;
    *(_DWORD *)(v4 + 48) = *(_DWORD *)(v5 + 68);
LABEL_26:
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v5 + 1648));
    *(_QWORD *)(v5 + 1704) = KeGetCurrentThread();
    v20 = 1;
    Scb = UdfCreateScb(a1, *(_QWORD *)(v4 + 56), 2355, v4, (__int64)&v35);
    v25 = Scb;
    *(_BYTE *)(Scb + 5) = 0;
    UdfInitializeIcbContextFromScb(a1, v32, Scb);
    v21 = 1;
    UdfLookupActiveIcb(a1, v32, *(unsigned int *)(v4 + 48));
    UdfInitializeScbFromIcbContext(a1, Scb, v32, 0);
    ++*(_DWORD *)(*(_QWORD *)(v4 + 16) + 204LL);
    *v28 = Scb;
    goto LABEL_28;
  }
  v8 = -1073741772;
  v23 = -1073741772;
LABEL_29:
  if ( v10 )
  {
    *(_QWORD *)(v5 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v5 + 1648));
  }
  if ( v21 )
    UdfCleanupIcbContext(a1, v32);
  if ( Scb )
  {
    if ( (*(_DWORD *)(Scb + 212) & 1) != 0 )
    {
      if ( v8 < 0 && !v35 )
      {
        v22[0] = 0;
        UdfTeardownStructures(a1, Scb, 0, 0, (__int64)v22);
      }
    }
    else
    {
      UdfDeleteScb(v11, Scb);
    }
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x10) != 0 )
  {
    WPP_SF_d(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 25, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids);
  }
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400312c0  mov     rax, rsp
0x1400312c3  mov     [rax+18h], r8d
0x1400312c7  mov     [rax+10h], rdx
0x1400312cb  mov     [rax+8], rcx
0x1400312cf  push    rbx
0x1400312d0  push    rsi
0x1400312d1  push    rdi
0x1400312d2  push    r12
0x1400312d4  push    r13
0x1400312d6  push    r14
0x1400312d8  push    r15
0x1400312da  sub     rsp, 100h
0x1400312e1  mov     r13, rcx
0x1400312e4  xor     ebx, ebx
0x1400312e6  mov     [rax+20h], bl
0x1400312e9  mov     [rsp+138h+var_F0], ebx
0x1400312ed  xorps   xmm0, xmm0
0x1400312f0  xor     ecx, ecx
0x1400312f2  movups  [rsp+138h+var_C0], xmm0
0x1400312f7  movups  xmmword ptr [rax-0B0h], xmm0
0x1400312fe  mov     [rax-0A0h], rcx
0x140031305  mov     r15, [rdx+88h]
0x14003130c  mov     [rsp+138h+var_E0], r15
0x140031311  mov     r14, [r15+8]
0x140031315  mov     [rsp+138h+var_D8], r14
0x14003131a  xor     edx, edx; Val
0x14003131c  lea     r8d, [rbx+60h]; Size
0x140031320  lea     rcx, [rax-98h]; void *
0x140031327  call    memset
0x14003132c  lea     rdx, WPP_GLOBAL_Control
0x140031333  mov     rcx, cs:WPP_GLOBAL_Control
0x14003133a  cmp     rcx, rdx
0x14003133d  jz      short loc_140031363
0x14003133f  mov     eax, [rcx+2Ch]
0x140031342  test    al, 10h
0x140031344  jz      short loc_140031363
0x140031346  lea     edx, [rbx+17h]
0x140031349  mov     r9, r15
0x14003134c  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x140031353  mov     rcx, [rcx+18h]
0x140031357  call    WPP_SF_q
0x14003135c  lea     rdx, WPP_GLOBAL_Control
0x140031363  lea     rax, [r15+18h]
0x140031367  mov     [rsp+138h+var_D0], rax
0x14003136c  cmp     [rax], rbx
0x14003136f  jz      short loc_140031387
0x140031371  xor     eax, eax
0x140031373  add     rsp, 100h
0x14003137a  pop     r15
0x14003137c  pop     r14
0x14003137e  pop     r13
0x140031380  pop     r12
0x140031382  pop     rdi
0x140031383  pop     rsi
0x140031384  pop     rbx
0x140031385  retn
0x140031387  mov     [rsp+138h+var_F7], bl
0x14003138b  mov     edi, ebx
0x14003138d  mov     [rsp+138h+var_F4], ebx
0x140031391  mov     [rsp+138h+var_C8], r14
0x140031396  mov     rsi, rbx
0x140031399  mov     [rsp+138h+var_E8], rbx
0x14003139e  mov     al, bl
0x1400313a0  mov     [rsp+138h+var_F8], bl
0x1400313a4  mov     r12d, 1
0x1400313aa  cmp     [r15+38h], ebx
0x1400313ae  jnz     loc_140031553
0x1400313b4  mov     ecx, [rsp+138h+arg_10]
0x1400313bb  cmp     ecx, r12d
0x1400313be  jz      loc_140031545
0x1400313c4  cmp     ecx, 4
0x1400313c7  jz      loc_140031545
0x1400313cd  mov     eax, [r14+30h]
0x1400313d1  test    al, 10h
0x1400313d3  jz      short loc_1400313F0
0x1400313d5  and     al, 20h
0x1400313d7  neg     al
0x1400313d9  sbb     edi, edi
0x1400313db  and     edi, 7E4h
0x1400313e1  add     edi, 0C0000022h
0x1400313e7  mov     [rsp+138h+var_F4], edi
0x1400313eb  jmp     loc_140031629
0x1400313f0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400313f7  cmp     rcx, rdx
0x1400313fa  jz      short loc_140031418
0x1400313fc  mov     eax, [rcx+2Ch]
0x1400313ff  test    al, 10h
0x140031401  jz      short loc_140031418
0x140031403  mov     edx, 18h
0x140031408  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x14003140f  mov     rcx, [rcx+18h]
0x140031413  call    WPP_SF_
0x140031418  mov     rsi, [rsp+138h+arg_8]
0x140031420  mov     rax, [rsi+88h]
0x140031427  add     rax, 60h ; '`'
0x14003142b  mov     [rsp+138h+var_108], ebx
0x14003142f  mov     [rsp+138h+var_110], rax
0x140031434  lea     rax, [rsp+138h+var_F0]
0x140031439  mov     [rsp+138h+var_118], rax
0x14003143e  xor     r9d, r9d
0x140031441  mov     r8b, 0Dh
0x140031444  mov     rdx, rsi
0x140031447  mov     rcx, r13
0x14003144a  call    UdfCreateNewIcb
0x14003144f  xorps   xmm0, xmm0
0x140031452  movdqu  [rsp+138h+var_C0], xmm0
0x140031458  lea     r8, [rsp+138h+var_C0]
0x14003145d  mov     rdx, rsi
0x140031460  mov     rcx, r13
0x140031463  call    UdfPrepareModifyIcbForScb
0x140031468  mov     r8, qword ptr [rsp+138h+var_C0]
0x14003146d  mov     eax, [rsp+138h+var_F0]
0x140031471  mov     [r8+9Ch], eax
0x140031478  lea     rsi, [r14+10h]
0x14003147c  cmp     [r14+160h], rbx
0x140031483  jz      short loc_14003148E
0x140031485  mov     rax, [rsi]
0x140031488  movzx   ecx, word ptr [rax+5Ah]
0x14003148c  jmp     short loc_1400314A5
0x14003148e  mov     rcx, [rsi]
0x140031491  test    dword ptr [r14+30h], 4000000h
0x140031499  jz      short loc_1400314A1
0x14003149b  movzx   ecx, word ptr [rcx+54h]
0x14003149f  jmp     short loc_1400314A5
0x1400314a1  movzx   ecx, word ptr [rcx+5Ch]
0x1400314a5  mov     [r8+0A0h], cx
0x1400314ad  mov     edx, [r14+44h]
0x1400314b1  mov     eax, [r8+98h]
0x1400314b8  mov     ecx, eax
0x1400314ba  xor     ecx, edx
0x1400314bc  mov     r9d, 3FFFFFFFh
0x1400314c2  and     ecx, r9d
0x1400314c5  xor     ecx, eax
0x1400314c7  mov     [r8+98h], ecx
0x1400314ce  and     edx, r9d
0x1400314d1  mov     [r8+98h], edx
0x1400314d8  mov     rax, [rsp+138h+arg_8]
0x1400314e0  add     [rax+1F4h], r12w
0x1400314e8  mov     r9, rax
0x1400314eb  mov     r8b, r12b
0x1400314ee  lea     rdx, [rsp+138h+var_C0]
0x1400314f3  mov     rcx, r13
0x1400314f6  call    UdfFinishModifyIcb
0x1400314fb  mov     eax, [rsp+138h+var_F0]
0x1400314ff  mov     [r15+38h], eax
0x140031503  cmp     [r14+160h], rbx
0x14003150a  jz      short loc_140031515
0x14003150c  mov     rax, [rsi]
0x14003150f  movzx   ecx, word ptr [rax+5Ah]
0x140031513  jmp     short loc_14003152C
0x140031515  mov     rcx, [rsi]
0x140031518  test    dword ptr [r14+30h], 4000000h
0x140031520  jz      short loc_140031528
0x140031522  movzx   ecx, word ptr [rcx+54h]
0x140031526  jmp     short loc_14003152C
0x140031528  movzx   ecx, word ptr [rcx+5Ch]
0x14003152c  movzx   eax, cx
0x14003152f  mov     [r15+3Ch], eax
0x140031533  bts     eax, 1Fh
0x140031537  mov     [r15+3Ch], eax
0x14003153b  mov     eax, [r14+44h]
0x14003153f  mov     [r15+30h], eax
0x140031543  jmp     short loc_140031553
0x140031545  mov     edi, 0C0000034h
0x14003154a  mov     [rsp+138h+var_F4], edi
0x14003154e  jmp     loc_14003162D
0x140031553  lea     rcx, [r14+670h]; FastMutex
0x14003155a  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140031561  nop     dword ptr [rax+rax+00h]
0x140031566  mov     rax, gs:188h
0x14003156f  mov     [r14+6A8h], rax
0x140031576  mov     [rsp+138h+var_F8], r12b
0x14003157b  mov     r8d, 933h
0x140031581  lea     rax, [rsp+138h+arg_18]
0x140031589  mov     [rsp+138h+var_118], rax
0x14003158e  mov     r9, r15
0x140031591  mov     rdx, [r15+38h]
0x140031595  mov     rcx, r13
0x140031598  call    UdfCreateScb
0x14003159d  mov     rsi, rax
0x1400315a0  mov     [rsp+138h+var_E8], rax
0x1400315a5  mov     [rax+5], bl
0x1400315a8  mov     r8, rax
0x1400315ab  lea     rdx, [rsp+138h+var_98]
0x1400315b3  mov     rcx, r13
0x1400315b6  call    UdfInitializeIcbContextFromScb
0x1400315bb  mov     [rsp+138h+var_F7], r12b
0x1400315c0  mov     r8d, [r15+30h]
0x1400315c4  lea     rdx, [rsp+138h+var_98]
0x1400315cc  mov     rcx, r13
0x1400315cf  call    UdfLookupActiveIcb
0x1400315d4  xor     r9d, r9d
0x1400315d7  lea     r8, [rsp+138h+var_98]
0x1400315df  mov     rdx, rsi
0x1400315e2  mov     rcx, r13
0x1400315e5  call    UdfInitializeScbFromIcbContext
0x1400315ea  jmp     short loc_140031612
0x1400315ec  mov     edi, 0C0000102h
0x1400315f1  mov     [rsp+138h+var_F4], edi
0x1400315f5  xor     ebx, ebx
0x1400315f7  lea     r12d, [rbx+1]
0x1400315fb  mov     r13, [rsp+138h+arg_0]
0x140031603  mov     r15, [rsp+138h+var_E0]
0x140031608  mov     rsi, [rsp+138h+var_E8]
0x14003160d  mov     r14, [rsp+138h+var_D8]
0x140031612  test    edi, edi
0x140031614  js      short loc_140031629
0x140031616  mov     rax, [r15+10h]
0x14003161a  add     [rax+0CCh], r12d
0x140031621  mov     rax, [rsp+138h+var_D0]
0x140031626  mov     [rax], rsi
0x140031629  mov     al, [rsp+138h+var_F8]
0x14003162d  test    al, al
0x14003162f  jz      short loc_14003164B
0x140031631  mov     [r14+6A8h], rbx
0x140031638  lea     rcx, [r14+670h]; FastMutex
0x14003163f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140031646  nop     dword ptr [rax+rax+00h]
0x14003164b  cmp     [rsp+138h+var_F7], bl
0x14003164f  jz      short loc_140031661
0x140031651  lea     rdx, [rsp+138h+var_98]
0x140031659  mov     rcx, r13
0x14003165c  call    UdfCleanupIcbContext
0x140031661  test    rsi, rsi
0x140031664  jz      short loc_1400316A7
0x140031666  mov     eax, [rsi+0D4h]
0x14003166c  test    r12b, al
0x14003166f  jnz     short loc_14003167B
0x140031671  mov     rdx, rsi
0x140031674  call    UdfDeleteScb
0x140031679  jmp     short loc_1400316A7
0x14003167b  test    edi, edi
0x14003167d  jns     short loc_1400316A7
0x14003167f  cmp     [rsp+138h+arg_18], bl
0x140031686  jnz     short loc_1400316A7
0x140031688  mov     [rsp+138h+var_F6], bl
0x14003168c  lea     rax, [rsp+138h+var_F6]
0x140031691  mov     [rsp+138h+var_118], rax
0x140031696  xor     r9d, r9d
0x140031699  xor     r8d, r8d
0x14003169c  mov     rdx, rsi
0x14003169f  mov     rcx, r13
0x1400316a2  call    UdfTeardownStructures
0x1400316a7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400316ae  lea     rax, WPP_GLOBAL_Control
0x1400316b5  cmp     rcx, rax
0x1400316b8  jz      short loc_1400316DA
0x1400316ba  mov     edx, [rcx+2Ch]
0x1400316bd  test    dl, 10h
0x1400316c0  jz      short loc_1400316DA
0x1400316c2  mov     edx, 19h
0x1400316c7  mov     r9d, edi
0x1400316ca  lea     r8, WPP_962a5ab0fb873cc757a84452495a3943_Traceguids
0x1400316d1  mov     rcx, [rcx+18h]
0x1400316d5  call    WPP_SF_d
0x1400316da  mov     eax, edi
0x1400316dc  jmp     loc_140031373
0x14005b53a  push    rbp
0x14005b53c  sub     rsp, 40h
0x14005b540  mov     rbp, rdx
0x14005b543  mov     rdx, rcx
0x14005b546  mov     rcx, [rbp+140h]
0x14005b54d  call    UdfExceptionFilter
0x14005b552  nop
0x14005b553  add     rsp, 40h
0x14005b557  pop     rbp
0x14005b558  retn
0x14005b55a  push    rbx
0x14005b55c  push    rbp
0x14005b55d  sub     rsp, 48h
0x14005b561  mov     rbp, rdx
0x14005b564  movzx   ebx, cl
0x14005b567  cmp     byte ptr [rbp+40h], 0
0x14005b56b  jz      short loc_14005B590
0x14005b56d  mov     rcx, [rbp+70h]
0x14005b571  mov     qword ptr [rcx+6A8h], 0
0x14005b57c  add     rcx, 670h; FastMutex
0x14005b583  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005b58a  nop     dword ptr [rax+rax+00h]
0x14005b58f  nop
0x14005b590  cmp     byte ptr [rbp+41h], 0
0x14005b594  jz      short loc_14005B5AA
0x14005b596  lea     rdx, [rbp+0A0h]
0x14005b59d  mov     rcx, [rbp+140h]
0x14005b5a4  call    UdfCleanupIcbContext
0x14005b5a9  nop
0x14005b5aa  mov     rdx, [rbp+50h]
0x14005b5ae  test    rdx, rdx
0x14005b5b1  jz      short loc_14005B5F9
0x14005b5b3  mov     eax, [rdx+0D4h]
0x14005b5b9  test    al, 1
0x14005b5bb  jnz     short loc_14005B5C4
0x14005b5bd  call    UdfDeleteScb
0x14005b5c2  jmp     short loc_14005B5F9
0x14005b5c4  cmp     dword ptr [rbp+44h], 0
0x14005b5c8  jl      short loc_14005B5D0
0x14005b5ca  mov     eax, ebx
0x14005b5cc  test    bl, bl
0x14005b5ce  jz      short loc_14005B5F9
0x14005b5d0  cmp     byte ptr [rbp+158h], 0
  ... truncated ...
```
