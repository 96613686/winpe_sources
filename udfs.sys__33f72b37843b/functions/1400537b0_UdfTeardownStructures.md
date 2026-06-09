# UdfTeardownStructures

- ea: `0x1400537b0`
- end: `0x1400541a0`
- name: `UdfTeardownStructures`
- size: `2544`
- prototype: ``
- caller_count: `11`
- callee_count: `15`
- tags: ``

## callers

- `0x14002dc50`
- `0x14002e4fc`
- `0x1400312c0`
- `0x14003a700`
- `0x140042c40`
- `0x140044f90`
- `0x14004e020`
- `0x140052864`
- `0x1400534d0`
- `0x1400537b0`
- `0x140058898`

## callees

- `0x140009730`
- `0x14000b8d8`
- `0x14000c490`
- `0x14000ca10`
- `0x14000ca54`
- `0x14000cad4`
- `0x14000f8cc`
- `0x140010b14`
- `0x140011c94`
- `0x140015558`
- `0x14001588c`
- `0x140015978`
- `0x14002cca0`
- `0x1400537b0`
- `0x140058aac`

## import_xrefs

- `ntoskrnl!ExRaiseStatus` at `0x140053dc9`
- `ntoskrnl!ExRaiseStatus` at `0x140053dc9`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053d96`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053dea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053f61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005418f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ab8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053d96`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053dea`
- `ntoskrnl!ExReleaseResourceLite` at `0x140053f61`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005418f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14005ab8c`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053b5f`
- `ntoskrnl!ExAcquireResourceExclusiveLite` at `0x140053b5f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005386d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400539a4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400539c3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140053b83`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14005386d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400539a4`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x1400539c3`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140053b83`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400538b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053954`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053973`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053a4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053a68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053c31`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053c5f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053f19`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053f33`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400538b9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053954`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053973`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053a4b`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053a68`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053c31`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053c5f`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053f19`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140053f33`

## pseudocode

```c
int *__fastcall UdfTeardownStructures(__int64 a1, __int16 *a2, char a3, unsigned __int8 a4, _BYTE *a5)
{
  __int64 v8; // r12
  __int64 v9; // rsi
  __int16 *v10; // rbx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // ecx
  __int64 v14; // rax
  __int64 v15; // rdx
  int v16; // r8d
  __int16 *v17; // rax
  __int16 *j; // rcx
  __int64 v19; // rcx
  __int64 v20; // r8
  __int64 v21; // r8
  int v22; // eax
  __int64 v23; // rcx
  __int64 v24; // r9
  bool v25; // dl
  __int16 *v26; // rax
  __int16 *v27; // rcx
  struct _ERESOURCE *v28; // rcx
  BOOLEAN v29; // dl
  __int64 v30; // rcx
  __int16 *v31; // r8
  __int64 v32; // rdx
  __int16 **v33; // rcx
  __int16 *v34; // rcx
  _QWORD **v35; // rdx
  _QWORD *i; // rax
  __int64 v37; // rcx
  __int64 v38; // rax
  __int16 *v39; // rcx
  _BYTE *v40; // rdx
  int *result; // rax
  char v42; // al
  __int64 v43; // rcx
  __int64 v44; // r9
  int v45; // [rsp+20h] [rbp-C8h]
  __int64 v46; // [rsp+60h] [rbp-88h] BYREF
  __int16 *v47; // [rsp+68h] [rbp-80h]
  char v48; // [rsp+70h] [rbp-78h]
  int v49; // [rsp+74h] [rbp-74h] BYREF
  __int16 *v50; // [rsp+78h] [rbp-70h]
  __int16 *v51; // [rsp+80h] [rbp-68h]
  __int16 *v52; // [rsp+88h] [rbp-60h]
  _QWORD *v53; // [rsp+90h] [rbp-58h]
  __int16 *v54; // [rsp+98h] [rbp-50h]
  __int64 v55; // [rsp+A0h] [rbp-48h]
  char v56; // [rsp+F8h] [rbp+10h]

  v49 = 0;
  v8 = *((_QWORD *)a2 + 17);
  v9 = *(_QWORD *)(v8 + 8);
  v10 = a2;
  v50 = a2;
  *(_WORD *)((char *)&v46 + 1) = 0;
  v56 = 0;
  v47 = 0;
  v55 = v8;
  *(_WORD *)((char *)&v46 + 3) = 0;
  *a5 = 0;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    v42 = 89;
    if ( !a3 )
      v42 = 78;
    WPP_SF_qc(
      *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
      44,
      WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids,
      a2,
      v42);
  }
  if ( !a3 )
  {
    v43 = *(_QWORD *)(a1 + 48);
    result = (int *)*(unsigned int *)(v43 + 28);
    if ( (char)result >= 0 )
    {
      *(_DWORD *)(v43 + 28) = (unsigned int)result | 0x80;
      goto LABEL_3;
    }
    return result;
  }
  while ( 1 )
  {
LABEL_3:
    v11 = *(_QWORD *)&WPP_GLOBAL_Control;
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
    {
      WPP_SF_q(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        45,
        WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids,
        v10);
    }
    if ( *v10 != 2356 && !*((_DWORD *)v10 + 52) && *((_QWORD *)v10 + 63) )
      UdfDeleteInternalStream(v11, (__int64)v10);
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
    *(_QWORD *)(v9 + 1640) = KeGetCurrentThread();
    v12 = *((_DWORD *)v10 + 51);
    if ( !v12 )
      break;
    v13 = *((_DWORD *)v10 + 53);
    if ( (v13 & 0x18) != 0
      || v12 != 1
      || (v14 = *((_QWORD *)v10 + 17), (v15 = *(_QWORD *)(v14 + 24)) == 0)
      || *(_DWORD *)(v15 + 204) )
    {
      if ( (v13 & 8) == 0 )
        goto LABEL_8;
      v34 = 0;
      v53 = 0;
      v35 = (_QWORD **)(*((_QWORD *)v10 + 17) + 32LL);
      for ( i = *v35; i != v35; i = (_QWORD *)*i )
      {
        v34 = (__int16 *)(i - 15);
        v53 = i - 15;
        if ( !*((_DWORD *)i + 21) )
        {
          v10 = (__int16 *)(i - 15);
          v50 = (__int16 *)(i - 15);
          break;
        }
      }
      if ( v10 != v34 )
      {
LABEL_8:
        *(_QWORD *)(v9 + 1640) = 0;
        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
        goto LABEL_89;
      }
    }
    else
    {
      v10 = *(__int16 **)(v14 + 24);
      v50 = v10;
    }
    *(_QWORD *)(v9 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
LABEL_34:
    if ( !v10 )
      goto LABEL_89;
  }
  *(_QWORD *)(v9 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
  v17 = v10 + 80;
  for ( j = (__int16 *)*((_QWORD *)v10 + 20); j != v17; j = v54 )
  {
    v26 = j - 16;
    v51 = j - 16;
    v54 = *(__int16 **)j;
    if ( v47 != *((__int16 **)j - 1) )
    {
      if ( v47 )
      {
        LOBYTE(v16) = 1;
        UdfTeardownStructures(a1, (_DWORD)v47, v16, a4, (__int64)&v46 + 2);
        if ( !BYTE2(v46) )
          ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)v47 + 17) + 80LL) + 8LL));
        v56 = 0;
        LOBYTE(v46) = 0;
        v26 = v51;
      }
      v27 = (__int16 *)*((_QWORD *)v26 + 3);
      v47 = v27;
      v52 = v27;
      if ( (*((_DWORD *)v10 + 53) & 0x18) == 0 )
      {
        v28 = (struct _ERESOURCE *)(*(_QWORD *)(*((_QWORD *)v27 + 17) + 80LL) + 8LL);
        v29 = 0;
        BYTE5(v46) = 0;
        if ( !a1 || (*(_DWORD *)(a1 + 28) & 4) != 0 )
        {
          v29 = 1;
          BYTE5(v46) = 1;
        }
        if ( !ExAcquireResourceExclusiveLite(v28, v29) )
        {
          *(_DWORD *)(a1 + 24) = -1073741608;
          ExRaiseStatus(-1073741608);
        }
        v56 = 1;
        LOBYTE(v46) = 1;
      }
    }
    ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
    *(_QWORD *)(v9 + 1640) = KeGetCurrentThread();
    v30 = (__int64)v51;
    if ( *((_DWORD *)v51 + 16) )
    {
      *(_QWORD *)(v9 + 1640) = 0;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
      if ( v56 )
      {
        ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)v47 + 17) + 80LL) + 8LL));
        v56 = 0;
      }
      BYTE3(v46) = 1;
      v48 = 1;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
      {
        WPP_SF_(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 46, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
      }
      break;
    }
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
    {
      WPP_SF_qqqdddddd(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        *(_QWORD *)&WPP_GLOBAL_Control,
        v47,
        v51,
        v47,
        v10,
        *(_DWORD *)(v9 + 256),
        *(_DWORD *)(v9 + 260),
        *((_DWORD *)v47 + 51),
        *((_DWORD *)v47 + 52),
        *((_DWORD *)v10 + 51),
        *((_DWORD *)v10 + 52),
        v46);
      v30 = (__int64)v51;
    }
    UdfRemovePrefix(v30, v30, 1, 1);
    v31 = v47;
    --*((_DWORD *)v47 + 51);
    --*((_DWORD *)v31 + 52);
    --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v31 + 17) + 8LL) + 256LL);
    --*(_DWORD *)(*(_QWORD *)(*((_QWORD *)v31 + 17) + 8LL) + 260LL);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
    {
      WPP_SF_DDDD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        48,
        WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids,
        *(unsigned int *)(v9 + 256),
        *(_DWORD *)(v9 + 260),
        *((_DWORD *)v31 + 51),
        *((_DWORD *)v31 + 52));
    }
    *(_QWORD *)(v9 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
    v17 = v10 + 80;
  }
  if ( BYTE3(v46) )
    goto LABEL_89;
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1648));
  *(_QWORD *)(v9 + 1704) = KeGetCurrentThread();
  ExAcquireFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
  *(_QWORD *)(v9 + 1640) = KeGetCurrentThread();
  v20 = *((unsigned int *)v10 + 51);
  if ( !(_DWORD)v20 )
  {
    UdfDeleteScbTable(v19, (__int64)v10);
    if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
    {
      WPP_SF_qddD(
        *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
        50,
        v21,
        v10,
        *((_DWORD *)v10 + 51),
        *((_DWORD *)v10 + 52),
        *v10);
    }
    if ( *((_DWORD *)v10 + 82) )
    {
      v37 = *(_QWORD *)&WPP_GLOBAL_Control;
      if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
      {
        WPP_SF_d(
          *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
          51,
          WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids);
      }
      LOBYTE(v21) = 1;
      UdfReleaseBlockReservation(v37, v10, v21);
    }
    v22 = *((_DWORD *)v10 + 53);
    if ( (v22 & 8) == 0 || v10 == *(__int16 **)(v9 + 304) )
    {
      if ( (v22 & 0x10) != 0 )
      {
        v32 = *((_QWORD *)v10 + 15);
        if ( *(__int16 **)(v32 + 8) != v10 + 60 || (v33 = (__int16 **)*((_QWORD *)v10 + 16), *v33 != v10 + 60) )
          __fastfail(3u);
        *v33 = (__int16 *)v32;
        *(_QWORD *)(v32 + 8) = v33;
        v47 = *(__int16 **)(*((_QWORD *)v10 + 17) + 16LL);
        v52 = v47;
      }
    }
    else
    {
      v38 = *((_QWORD *)v10 + 17);
      v39 = *(__int16 **)(v38 + 16);
      v47 = v39;
      v52 = v39;
      *(_QWORD *)(v38 + 24) = 0;
      --*((_DWORD *)v39 + 51);
    }
    if ( a2 == v10 )
      *a5 = 1;
    *(_QWORD *)(v9 + 1640) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
    *(_QWORD *)(v9 + 1704) = 0;
    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1648));
    v24 = *((unsigned int *)v10 + 75);
    if ( *((_DWORD *)v10 + 74) != (_DWORD)v24 && *(_DWORD *)(v9 + 52) == 2 )
    {
      LOBYTE(v45) = 0;
      UdfFreeAllocation(a1, v10, v10 + 132, v24, v45, &v49);
      *((_DWORD *)v10 + 74) -= v49;
    }
    UdfDeleteScb(v23, (ULONG_PTR)v10);
    v10 = v47;
    v50 = v47;
    v47 = 0;
    v52 = 0;
    v25 = v56 || BYTE1(v46);
    BYTE1(v46) = v25;
    BYTE4(v46) = v25;
    v56 = 0;
    LOBYTE(v46) = 0;
    goto LABEL_34;
  }
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    WPP_SF_qddD(*(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL), 49, v20, v10, v20, *((_DWORD *)v10 + 52), *v10);
  }
  *(_QWORD *)(v9 + 1640) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1584));
  *(_QWORD *)(v9 + 1704) = 0;
  ExReleaseFastMutexUnsafe((PFAST_MUTEX)(v9 + 1648));
  if ( v56 )
    ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)v47 + 17) + 80LL) + 8LL));
LABEL_89:
  if ( v10 )
  {
    if ( BYTE1(v46) || (v40 = a5, *a5) && *((_QWORD *)v10 + 17) == v8 && !a4 )
    {
      ExReleaseResourceLite((PERESOURCE)(*(_QWORD *)(*((_QWORD *)v10 + 17) + 80LL) + 8LL));
      goto LABEL_90;
    }
  }
  else
  {
LABEL_90:
    v40 = a5;
  }
  if ( !a3 )
    *(_DWORD *)(*(_QWORD *)(a1 + 48) + 28LL) &= ~0x80u;
  result = &WPP_GLOBAL_Control;
  if ( *(int **)&WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*(_DWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 44LL) & 0x40000) != 0 )
  {
    v44 = 89;
    if ( !*v40 )
      v44 = 78;
    return (int *)WPP_SF_c(
                    *(_QWORD *)(*(_QWORD *)&WPP_GLOBAL_Control + 24LL),
                    52,
                    WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids,
                    v44);
  }
  return result;
}

```

## disassembly

```asm
0x1400537b0  mov     rax, rsp
0x1400537b3  mov     [rax+20h], r9b
0x1400537b7  mov     [rax+18h], r8b
0x1400537bb  mov     [rax+8], rcx
0x1400537bf  push    rbx
0x1400537c0  push    rsi
0x1400537c1  push    rdi
0x1400537c2  push    r12
0x1400537c4  push    r13
0x1400537c6  push    r14
0x1400537c8  push    r15
0x1400537ca  sub     rsp, 0B0h
0x1400537d1  movzx   edi, r8b
0x1400537d5  mov     r13, rdx
0x1400537d8  mov     r14, rcx
0x1400537db  xor     r15d, r15d
0x1400537de  mov     [rax-74h], r15d
0x1400537e2  mov     r12, [rdx+88h]
0x1400537e9  mov     rsi, [r12+8]
0x1400537ee  mov     rbx, rdx
0x1400537f1  mov     [rax-70h], rdx
0x1400537f5  xor     dl, dl
0x1400537f7  mov     [rsp+0E8h+var_87], dl
0x1400537fb  mov     [rsp+0E8h+var_84], dl
0x1400537ff  mov     [rax+10h], dl
0x140053802  mov     [rax-80h], r15
0x140053806  mov     [rsp+0E8h+var_48], r12
0x14005380e  mov     [rsp+0E8h+var_85], dl
0x140053812  mov     [rsp+0E8h+var_86], dl
0x140053816  mov     rax, [rsp+0E8h+arg_20]
0x14005381e  mov     [rax], dl
0x140053820  lea     rdx, WPP_GLOBAL_Control
0x140053827  mov     rcx, cs:WPP_GLOBAL_Control
0x14005382e  cmp     rcx, rdx
0x140053831  jnz     loc_1400540C3
0x140053837  lea     rdx, WPP_GLOBAL_Control
0x14005383e  test    dil, dil
0x140053841  jz      loc_140054101
0x140053847  mov     r15d, 934h
0x14005384d  mov     rcx, cs:WPP_GLOBAL_Control
0x140053854  cmp     rcx, rdx
0x140053857  jnz     short loc_1400538CA
0x140053859  cmp     [rbx], r15w
0x14005385d  jnz     loc_1400538F0
0x140053863  lea     r15, [rsi+630h]
0x14005386a  mov     rcx, r15; FastMutex
0x14005386d  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140053874  nop     dword ptr [rax+rax+00h]
0x140053879  mov     rax, gs:188h
0x140053882  mov     [rsi+668h], rax
0x140053889  mov     eax, [rbx+0CCh]
0x14005388f  test    eax, eax
0x140053891  jz      loc_140053965
0x140053897  mov     ecx, [rbx+0D4h]
0x14005389d  test    cl, 18h
0x1400538a0  jz      short loc_140053918
0x1400538a2  test    cl, 8
0x1400538a5  jnz     loc_140053D0D
0x1400538ab  mov     qword ptr [rsi+668h], 0
0x1400538b6  mov     rcx, r15; FastMutex
0x1400538b9  call    cs:__imp_ExReleaseFastMutexUnsafe
0x1400538c0  nop     dword ptr [rax+rax+00h]
0x1400538c5  jmp     loc_14005407B
0x1400538ca  test    dword ptr [rcx+2Ch], 40000h
0x1400538d1  jz      short loc_140053859
0x1400538d3  mov     edx, 2Dh ; '-'
0x1400538d8  mov     r9, rbx
0x1400538db  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
0x1400538e2  mov     rcx, [rcx+18h]
0x1400538e6  call    WPP_SF_q
0x1400538eb  jmp     loc_140053859
0x1400538f0  cmp     dword ptr [rbx+0D0h], 0
0x1400538f7  jnz     loc_140053863
0x1400538fd  cmp     qword ptr [rbx+1F8h], 0
0x140053905  jz      loc_140053863
0x14005390b  mov     rdx, rbx
0x14005390e  call    UdfDeleteInternalStream
0x140053913  jmp     loc_140053863
0x140053918  cmp     eax, 1
0x14005391b  jnz     short loc_1400538A2
0x14005391d  mov     rax, [rbx+88h]
0x140053924  mov     rdx, [rax+18h]
0x140053928  test    rdx, rdx
0x14005392b  jz      loc_1400538A2
0x140053931  cmp     dword ptr [rdx+0CCh], 0
0x140053938  jnz     loc_1400538A2
0x14005393e  mov     rbx, rdx
0x140053941  mov     [rsp+0E8h+var_70], rdx
0x140053946  mov     qword ptr [rsi+668h], 0
0x140053951  mov     rcx, r15; FastMutex
0x140053954  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005395b  nop     dword ptr [rax+rax+00h]
0x140053960  jmp     loc_140053AD6
0x140053965  mov     qword ptr [rsi+668h], 0
0x140053970  mov     rcx, r15; FastMutex
0x140053973  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14005397a  nop     dword ptr [rax+rax+00h]
0x14005397f  lea     rax, [rbx+0A0h]
0x140053986  mov     rcx, [rax]
0x140053989  cmp     rcx, rax
0x14005398c  jnz     loc_140053AF1
0x140053992  cmp     [rsp+0E8h+var_85], 0
0x140053997  jnz     loc_14005407B
0x14005399d  lea     rcx, [rsi+670h]; FastMutex
0x1400539a4  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400539ab  nop     dword ptr [rax+rax+00h]
0x1400539b0  mov     rax, gs:188h
0x1400539b9  mov     [rsi+6A8h], rax
0x1400539c0  mov     rcx, r15; FastMutex
0x1400539c3  call    cs:__imp_ExAcquireFastMutexUnsafe
0x1400539ca  nop     dword ptr [rax+rax+00h]
0x1400539cf  mov     rax, gs:188h
0x1400539d8  mov     [rsi+668h], rax
0x1400539df  mov     r8d, [rbx+0CCh]
0x1400539e6  test    r8d, r8d
0x1400539e9  jnz     loc_140053EC9
0x1400539ef  mov     rdx, rbx
0x1400539f2  call    UdfDeleteScbTable
0x1400539f7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400539fe  lea     rax, WPP_GLOBAL_Control
0x140053a05  cmp     rcx, rax
0x140053a08  jnz     loc_140053F77
0x140053a0e  mov     r9d, [rbx+148h]
0x140053a15  test    r9d, r9d
0x140053a18  jnz     loc_140053FB8
0x140053a1e  mov     eax, [rbx+0D4h]
0x140053a24  test    al, 8
0x140053a26  jnz     loc_140053FF2
0x140053a2c  test    al, 10h
0x140053a2e  jnz     loc_140053CC8
0x140053a34  cmp     r13, rbx
0x140053a37  jz      loc_140054031
0x140053a3d  mov     qword ptr [rsi+668h], 0
0x140053a48  mov     rcx, r15; FastMutex
0x140053a4b  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140053a52  nop     dword ptr [rax+rax+00h]
0x140053a57  xor     r15d, r15d
0x140053a5a  mov     [rsi+6A8h], r15
0x140053a61  lea     rcx, [rsi+670h]; FastMutex
0x140053a68  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140053a6f  nop     dword ptr [rax+rax+00h]
0x140053a74  mov     r9d, [rbx+12Ch]
0x140053a7b  cmp     [rbx+128h], r9d
0x140053a82  jnz     loc_140054041
0x140053a88  mov     rdx, rbx
0x140053a8b  call    UdfDeleteScb
0x140053a90  mov     rbx, [rsp+0E8h+var_80]
0x140053a95  mov     [rsp+0E8h+var_70], rbx
0x140053a9a  mov     rax, r15
0x140053a9d  mov     [rsp+0E8h+var_80], rax
0x140053aa2  mov     [rsp+0E8h+var_60], rax
0x140053aaa  cmp     [rsp+0E8h+arg_8], al
0x140053ab1  jnz     loc_140053CC1
0x140053ab7  cmp     [rsp+0E8h+var_87], al
0x140053abb  jnz     loc_140053CC1
0x140053ac1  xor     dl, dl
0x140053ac3  mov     [rsp+0E8h+var_87], dl
0x140053ac7  mov     [rsp+0E8h+var_84], dl
0x140053acb  mov     [rsp+0E8h+arg_8], al
0x140053ad2  mov     [rsp+0E8h+var_88], al
0x140053ad6  test    rbx, rbx
0x140053ad9  mov     r15d, 934h
0x140053adf  jz      loc_14005407B
0x140053ae5  lea     rdx, WPP_GLOBAL_Control
0x140053aec  jmp     loc_14005384D
0x140053af1  lea     rax, [rcx-20h]
0x140053af5  mov     [rsp+0E8h+var_68], rax
0x140053afd  mov     rcx, [rcx]
0x140053b00  mov     [rsp+0E8h+var_50], rcx
0x140053b08  mov     rcx, [rsp+0E8h+var_80]
0x140053b0d  cmp     rcx, [rax+18h]
0x140053b11  jz      short loc_140053B80
0x140053b13  test    rcx, rcx
0x140053b16  jnz     loc_140053D5A
0x140053b1c  mov     rcx, [rax+18h]
0x140053b20  mov     [rsp+0E8h+var_80], rcx
0x140053b25  mov     [rsp+0E8h+var_60], rcx
0x140053b2d  mov     eax, [rbx+0D4h]
0x140053b33  test    al, 18h
0x140053b35  jnz     short loc_140053B80
0x140053b37  mov     rax, [rcx+88h]
0x140053b3e  mov     rcx, [rax+50h]
0x140053b42  add     rcx, 8; Resource
0x140053b46  xor     dl, dl
0x140053b48  mov     [rsp+0E8h+var_83], dl
0x140053b4c  test    r14, r14
0x140053b4f  jz      short loc_140053B59
0x140053b51  mov     eax, [r14+1Ch]
0x140053b55  test    al, 4
0x140053b57  jz      short loc_140053B5F
0x140053b59  mov     dl, 1; Wait
0x140053b5b  mov     [rsp+0E8h+var_83], dl
0x140053b5f  call    cs:__imp_ExAcquireResourceExclusiveLite
0x140053b66  nop     dword ptr [rax+rax+00h]
0x140053b6b  test    al, al
0x140053b6d  jz      loc_140053DBC
0x140053b73  mov     al, 1
0x140053b75  mov     [rsp+0E8h+arg_8], al
0x140053b7c  mov     [rsp+0E8h+var_88], al
0x140053b80  mov     rcx, r15; FastMutex
0x140053b83  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140053b8a  nop     dword ptr [rax+rax+00h]
0x140053b8f  mov     rax, gs:188h
0x140053b98  mov     [rsi+668h], rax
0x140053b9f  mov     rcx, [rsp+0E8h+var_68]
0x140053ba7  cmp     dword ptr [rcx+40h], 0
0x140053bab  jnz     loc_140053C51
0x140053bb1  mov     rdx, cs:WPP_GLOBAL_Control
0x140053bb8  lea     rax, WPP_GLOBAL_Control
0x140053bbf  cmp     rdx, rax
0x140053bc2  jnz     loc_140053E08
0x140053bc8  mov     r9b, 1
0x140053bcb  movzx   r8d, r9b
0x140053bcf  mov     rdx, rcx
0x140053bd2  call    UdfRemovePrefix
0x140053bd7  mov     r8, [rsp+0E8h+var_80]
0x140053bdc  dec     dword ptr [r8+0CCh]
0x140053be3  dec     dword ptr [r8+0D0h]
0x140053bea  mov     rax, [r8+88h]
0x140053bf1  mov     rcx, [rax+8]
0x140053bf5  dec     dword ptr [rcx+100h]
0x140053bfb  mov     rax, [r8+88h]
0x140053c02  mov     rcx, [rax+8]
0x140053c06  dec     dword ptr [rcx+104h]
0x140053c0c  mov     rcx, cs:WPP_GLOBAL_Control
0x140053c13  lea     rax, WPP_GLOBAL_Control
0x140053c1a  cmp     rcx, rax
0x140053c1d  jnz     loc_140053E7B
0x140053c23  mov     qword ptr [rsi+668h], 0
0x140053c2e  mov     rcx, r15; FastMutex
0x140053c31  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140053c38  nop     dword ptr [rax+rax+00h]
0x140053c3d  lea     rax, [rbx+0A0h]
0x140053c44  mov     rcx, [rsp+0E8h+var_50]
0x140053c4c  jmp     loc_140053989
0x140053c51  mov     qword ptr [rsi+668h], 0
0x140053c5c  mov     rcx, r15; FastMutex
0x140053c5f  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140053c66  nop     dword ptr [rax+rax+00h]
0x140053c6b  cmp     [rsp+0E8h+arg_8], 0
0x140053c73  jnz     loc_140053DD6
0x140053c79  mov     cl, 1
0x140053c7b  mov     [rsp+0E8h+var_85], cl
0x140053c7f  mov     [rsp+0E8h+var_78], cl
0x140053c83  mov     rcx, cs:WPP_GLOBAL_Control
0x140053c8a  lea     rax, WPP_GLOBAL_Control
0x140053c91  cmp     rcx, rax
0x140053c94  jz      loc_140053992
0x140053c9a  test    dword ptr [rcx+2Ch], 40000h
0x140053ca1  jz      loc_140053992
0x140053ca7  mov     edx, 2Eh ; '.'
0x140053cac  lea     r8, WPP_1e13c5e073ed3a5a06b38dac69e77137_Traceguids
0x140053cb3  mov     rcx, [rcx+18h]
0x140053cb7  call    WPP_SF_
0x140053cbc  jmp     loc_140053992
0x140053cc1  mov     dl, 1
0x140053cc3  jmp     loc_140053AC3
0x140053cc8  lea     rax, [rbx+78h]
0x140053ccc  mov     rdx, [rax]
0x140053ccf  cmp     [rdx+8], rax
0x140053cd3  jnz     loc_14005402A
0x140053cd9  mov     rcx, [rbx+80h]
0x140053ce0  cmp     [rcx], rax
0x140053ce3  jnz     loc_14005402A
0x140053ce9  mov     [rcx], rdx
0x140053cec  mov     [rdx+8], rcx
0x140053cf0  mov     rax, [rbx+88h]
0x140053cf7  mov     rax, [rax+10h]
0x140053cfb  mov     [rsp+0E8h+var_80], rax
0x140053d00  mov     [rsp+0E8h+var_60], rax
0x140053d08  jmp     loc_140053A34
0x140053d0d  xor     ecx, ecx
0x140053d0f  mov     [rsp+0E8h+var_58], rcx
0x140053d17  mov     rdx, [rbx+88h]
0x140053d1e  add     rdx, 20h ; ' '
0x140053d22  mov     rax, [rdx]
0x140053d25  cmp     rax, rdx
0x140053d28  jz      short loc_140053D47
0x140053d2a  lea     rcx, [rax-78h]
0x140053d2e  mov     [rsp+0E8h+var_58], rcx
0x140053d36  cmp     dword ptr [rcx+0CCh], 0
0x140053d3d  jnz     short loc_140053D55
0x140053d3f  mov     rbx, rcx
0x140053d42  mov     [rsp+0E8h+var_70], rcx
0x140053d47  cmp     rbx, rcx
0x140053d4a  jz      loc_140053946
0x140053d50  jmp     loc_1400538AB
0x140053d55  mov     rax, [rax]
0x140053d58  jmp     short loc_140053D25
0x140053d5a  lea     rax, [rsp+0E8h+var_86]
0x140053d5f  mov     [rsp+0E8h+var_C8], rax
0x140053d64  movzx   r9d, [rsp+0E8h+arg_18]
0x140053d6d  mov     r8b, 1
0x140053d70  mov     rdx, rcx
0x140053d73  mov     rcx, r14
0x140053d76  call    UdfTeardownStructures
0x140053d7b  cmp     [rsp+0E8h+var_86], 0
0x140053d80  jnz     short loc_140053DA2
0x140053d82  mov     rax, [rsp+0E8h+var_80]
0x140053d87  mov     rax, [rax+88h]
  ... truncated ...
```
