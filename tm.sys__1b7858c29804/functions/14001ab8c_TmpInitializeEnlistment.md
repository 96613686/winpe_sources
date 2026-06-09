# TmpInitializeEnlistment

- ea: `0x14001ab8c`
- end: `0x14001b331`
- name: `TmpInitializeEnlistment`
- size: `1957`
- prototype: `__int64 __usercall@<rax>(PVOID Object@<rcx>, int, int, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14001a870`

## callees

- `0x140002940`
- `0x14000cbf8`
- `0x14000cc60`
- `0x14000cf28`
- `0x140010c70`
- `0x1400110f4`
- `0x140015a50`
- `0x14001a7cc`
- `0x14001a828`
- `0x14001ab8c`
- `0x14001b338`
- `0x14001b3d0`
- `0x14001b570`

## import_xrefs

- `ntoskrnl!KeWaitForSingleObject` at `0x14001ad46`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b116`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001ad46`
- `ntoskrnl!KeWaitForSingleObject` at `0x14001b116`
- `ntoskrnl!KeReleaseMutex` at `0x14001ad9f`
- `ntoskrnl!KeReleaseMutex` at `0x14001addd`
- `ntoskrnl!KeReleaseMutex` at `0x14001af71`
- `ntoskrnl!KeReleaseMutex` at `0x14001b05b`
- `ntoskrnl!KeReleaseMutex` at `0x14001b28d`
- `ntoskrnl!KeReleaseMutex` at `0x14001b2a7`
- `ntoskrnl!KeReleaseMutex` at `0x1400214b5`
- `ntoskrnl!KeReleaseMutex` at `0x1400214d8`
- `ntoskrnl!KeReleaseMutex` at `0x14001ad9f`
- `ntoskrnl!KeReleaseMutex` at `0x14001addd`
- `ntoskrnl!KeReleaseMutex` at `0x14001af71`
- `ntoskrnl!KeReleaseMutex` at `0x14001b05b`
- `ntoskrnl!KeReleaseMutex` at `0x14001b28d`
- `ntoskrnl!KeReleaseMutex` at `0x14001b2a7`
- `ntoskrnl!KeReleaseMutex` at `0x1400214b5`
- `ntoskrnl!KeReleaseMutex` at `0x1400214d8`
- `ntoskrnl!ObfDereferenceObject` at `0x14001adfe`
- `ntoskrnl!ObfDereferenceObject` at `0x14001af80`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b06a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b272`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b2bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002148a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400214f1`
- `ntoskrnl!ObfDereferenceObject` at `0x14001adfe`
- `ntoskrnl!ObfDereferenceObject` at `0x14001af80`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b06a`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b272`
- `ntoskrnl!ObfDereferenceObject` at `0x14001b2bb`
- `ntoskrnl!ObfDereferenceObject` at `0x14002148a`
- `ntoskrnl!ObfDereferenceObject` at `0x1400214f1`
- `ntoskrnl!ObfReferenceObject` at `0x14001ac66`
- `ntoskrnl!ObfReferenceObject` at `0x14001ac7c`
- `ntoskrnl!ObfReferenceObject` at `0x14001ad70`
- `ntoskrnl!ObfReferenceObject` at `0x14001ae1a`
- `ntoskrnl!ObfReferenceObject` at `0x14001af5b`
- `ntoskrnl!ObfReferenceObject` at `0x14001b1c3`
- `ntoskrnl!ObfReferenceObject` at `0x14001b228`
- `ntoskrnl!ObfReferenceObject` at `0x14001b237`
- `ntoskrnl!ObfReferenceObject` at `0x14001ac66`
- `ntoskrnl!ObfReferenceObject` at `0x14001ac7c`
- `ntoskrnl!ObfReferenceObject` at `0x14001ad70`
- `ntoskrnl!ObfReferenceObject` at `0x14001ae1a`
- `ntoskrnl!ObfReferenceObject` at `0x14001af5b`
- `ntoskrnl!ObfReferenceObject` at `0x14001b1c3`
- `ntoskrnl!ObfReferenceObject` at `0x14001b228`
- `ntoskrnl!ObfReferenceObject` at `0x14001b237`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac18`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14001ac18`
- `ntoskrnl!KeInitializeMutex` at `0x14001acf0`
- `ntoskrnl!KeInitializeMutex` at `0x14001acf0`
- `ntoskrnl!ExUuidCreate` at `0x14001acc5`
- `ntoskrnl!ExUuidCreate` at `0x14001acc5`

## pseudocode

```c
__int64 __fastcall TmpInitializeEnlistment(
        char *Object,
        __int64 a2,
        PKTRANSACTION a3,
        _OWORD *a4,
        unsigned int a5,
        unsigned int a6,
        __int64 a7)
{
  _DWORD *v10; // r14
  _DWORD *v11; // r15
  __int64 v12; // rdx
  int inserted; // ebx
  void *v14; // r13
  _OWORD *PoolWithTag; // rbx
  __int64 v16; // r12
  _QWORD *v17; // r12
  _QWORD *v18; // rbx
  char v19; // r15
  _QWORD *i; // rax
  struct _KTRANSACTION *v21; // r15
  PKTRANSACTION v22; // rbx
  _DWORD *v23; // rdx
  __int64 v24; // r15
  int v25; // eax
  PKTRANSACTION v26; // rbx
  _QWORD *v27; // r15
  volatile signed __int32 *v28; // rcx
  char *v29; // rdx
  char *v30; // rax
  __int64 v31; // rcx
  char **v32; // rcx
  __int64 v33; // rax
  int v34; // ecx
  char v36; // [rsp+30h] [rbp-58h]
  char v37; // [rsp+31h] [rbp-57h]
  __int64 v38; // [rsp+40h] [rbp-48h] BYREF
  _DWORD *v39; // [rsp+48h] [rbp-40h]
  PKTRANSACTION Transaction[2]; // [rsp+50h] [rbp-38h] BYREF

  Transaction[0] = 0;
  v36 = 0;
  v37 = 0;
  v10 = 0;
  v39 = 0;
  v11 = 0;
  v12 = a5;
  LOBYTE(v12) = a5 & 1;
  if ( !(unsigned __int8)TmpIsNotificationMaskValid(a6, v12) )
  {
    inserted = -1073741811;
LABEL_3:
    v14 = 0;
    goto LABEL_78;
  }
  *((_QWORD *)Object + 1) = 0;
  Object[40] = 0;
  PoolWithTag = ExAllocatePoolWithTag((POOL_TYPE)512, 0x38u, 0x4E466D54u);
  if ( !PoolWithTag )
  {
    inserted = -1073741670;
    goto LABEL_3;
  }
  *PoolWithTag = 0;
  PoolWithTag[1] = 0;
  PoolWithTag[2] = 0;
  *((_QWORD *)PoolWithTag + 6) = 0;
  *((_DWORD *)Object + 42) = 274;
  *(_DWORD *)Object = -1341456381;
  *((_QWORD *)Object + 19) = a2;
  ObfReferenceObject((PVOID)a2);
  *((_QWORD *)Object + 20) = a3;
  ObfReferenceObject(a3);
  *((_QWORD *)Object + 23) = a7;
  *((_DWORD *)Object + 48) = 1;
  *((_DWORD *)Object + 44) = a6;
  *((_DWORD *)Object + 43) = 0;
  *((_QWORD *)Object + 29) = PoolWithTag;
  if ( a4 )
    *((_OWORD *)Object + 3) = *a4;
  else
    ExUuidCreate((UUID *)Object + 3);
  *((_QWORD *)Object + 25) = 0;
  *((_DWORD *)Object + 52) = 0;
  KeInitializeMutex((PRKMUTEX)(Object + 64), 0);
  *((_QWORD *)Object + 30) = 0;
  *((_QWORD *)Object + 31) = 0;
  *((_QWORD *)Object + 32) = 0;
  *((_DWORD *)Object + 78) = 0;
  memset(Object + 316, 0, 0xA0u);
  v16 = a2;
  KeWaitForSingleObject((PVOID)(a2 + 40), Executive, 0, 0, 0);
  v37 = 1;
  v10 = *(_DWORD **)(a2 + 360);
  v39 = v10;
  if ( v10 && ((ObfReferenceObject(v10), *(_DWORD *)(a2 + 28) != 1) || v10[16] == 2) )
  {
    KeReleaseMutex((PRKMUTEX)(a2 + 40), 0);
    v37 = 0;
    if ( *((_DWORD **)a3 + 64) != v10 )
      v11 = v10;
    v38 = (__int64)v11;
    v17 = (_QWORD *)((char *)a3 + 88);
    v14 = 0;
    while ( 1 )
    {
      v18 = v17;
      if ( v36 )
      {
        KeReleaseMutex((PRKMUTEX)(*v17 + 32LL), 0);
        v36 = 0;
      }
      if ( v14 )
      {
        TmpReleaseTxTableTransactionManager(v14);
        ObfDereferenceObject(v14);
        v14 = 0;
      }
      if ( v11 )
      {
        ObfReferenceObject(v11);
        TmpAcquireTxTableTransactionManager(v11);
        v14 = v11;
        v38 = 0;
        if ( v11[16] == 5 )
        {
          inserted = -1072103342;
          goto LABEL_78;
        }
      }
      TmpAcquireTransactionMutex(a3);
      v19 = 1;
      v36 = 1;
      if ( !TmIsTransactionActiveExt(a3) && *((_DWORD *)a3 + 48) != 10 )
        goto LABEL_24;
      if ( *((_DWORD *)a3 + 48) != 1 && (a6 & 1) != 0 )
      {
        inserted = -1072103330;
        goto LABEL_25;
      }
      if ( !*((_QWORD *)a3 + 64) )
      {
        inserted = TmpInsertTxTransactionManager(v10);
        v16 = a2;
        if ( inserted >= 0 )
          goto LABEL_51;
        goto LABEL_80;
      }
      if ( (a5 & 1) != 0
        && (*((_DWORD *)a3 + 49) & 0x100) != 0
        && (*((_DWORD *)a3 + 49) & 0x400) != 0
        && *((_DWORD **)a3 + 64) != v10 )
      {
        for ( i = (_QWORD *)*((_QWORD *)a3 + 32); ; i = (_QWORD *)*i )
        {
          if ( i == (_QWORD *)((char *)a3 + 256) )
          {
            inserted = -1073741811;
            goto LABEL_78;
          }
          v21 = (struct _KTRANSACTION *)(i - 32);
          if ( (_DWORD *)i[32] == v10 && !*((_QWORD *)v21 + 30) )
            break;
        }
        v22 = a3;
        a3 = (PKTRANSACTION)(i - 32);
        ObfReferenceObject(i - 32);
        KeReleaseMutex((PRKMUTEX)(*v17 + 32LL), 0);
        ObfDereferenceObject(v22);
        TmpAcquireTransactionMutex(v21);
        v36 = 1;
        *((_QWORD *)Object + 20) = v21;
        if ( !TmIsTransactionActiveExt(v21) )
        {
          inserted = -1072103421;
          goto LABEL_78;
        }
LABEL_50:
        v16 = a2;
LABEL_51:
        v27 = (_QWORD *)((char *)a3 + 240);
        if ( (a5 & 1) != 0 )
        {
          if ( *v27 )
          {
            inserted = (*((_DWORD *)a3 + 49) & 0x100) != 0 ? -1072103406 : -1072103340;
            goto LABEL_79;
          }
          if ( (*(_DWORD *)(v16 + 32) & 4) != 0 && (*(_DWORD *)(*((_QWORD *)a3 + 64) + 128LL) & 1) == 0 )
          {
            inserted = -1072103365;
            goto LABEL_79;
          }
        }
        KeWaitForSingleObject((PVOID)(v16 + 40), Executive, 0, 0, 0);
        v37 = 1;
        if ( *(_DWORD *)(v16 + 28) == 1 && v10[16] != 2 )
        {
          inserted = -1072103342;
          goto LABEL_79;
        }
        inserted = TmpInsertEnlistmentResourceManager(Object, v16);
        if ( inserted >= 0 )
        {
          *((_DWORD *)Object + 42) = 256;
          v28 = (volatile signed __int32 *)((char *)a3 + 196);
          if ( (a5 & 1) != 0 )
          {
            _InterlockedOr((volatile signed __int32 *)Object + 43, 1u);
            *v27 = Object;
            if ( (*v28 & 0x100) != 0 && (a6 & 0x4000000) != 0 )
              _InterlockedOr(v28, 0x1000u);
          }
          if ( v14 && (v10[32] & 0x10) != 0 )
            _InterlockedOr(v28, 0x10000u);
          if ( (*(_DWORD *)(v16 + 32) & 4) == 0 )
            _InterlockedOr((volatile signed __int32 *)Object + 43, 2u);
          ObfReferenceObject(Object);
          TmpAddTransactionEnlistmentCounts(Object);
          v29 = Object + 120;
          v30 = (char *)a3 + 200;
          if ( (*((_DWORD *)Object + 44) & 0x200) != 0 )
          {
            v31 = *(_QWORD *)v30;
            if ( *(char **)(*(_QWORD *)v30 + 8LL) == v30 )
            {
              *(_QWORD *)v29 = v31;
              *((_QWORD *)Object + 16) = v30;
              *(_QWORD *)(v31 + 8) = v29;
              *(_QWORD *)v30 = v29;
              goto LABEL_76;
            }
LABEL_74:
            __fastfail(3u);
          }
          v32 = (char **)*((_QWORD *)a3 + 26);
          if ( *v32 != v30 )
            goto LABEL_74;
          *(_QWORD *)v29 = v30;
          *((_QWORD *)Object + 16) = v32;
          *v32 = v29;
          *((_QWORD *)a3 + 26) = v29;
LABEL_76:
          ObfReferenceObject(Object);
          ObfReferenceObject(Object);
        }
        goto LABEL_79;
      }
      v23 = (_DWORD *)*((_QWORD *)a3 + 64);
      v16 = a2;
      if ( v23 == v10
        || *(__int64 (__fastcall **)(PKENLISTMENT *, PVOID, PVOID, ULONG, PLARGE_INTEGER))(a2 + 296) == TmpInternalCrmNotification )
      {
        goto LABEL_51;
      }
      v17 = v18;
      v24 = *v18;
      v25 = TmpEnlistMultiTm(v10, v23, (__int64)Transaction, (__int64)&v38);
      inserted = v25;
      if ( v25 != -1073741794 )
        break;
      v11 = (_DWORD *)v38;
    }
    if ( v25 >= 0 )
    {
      v26 = a3;
      a3 = Transaction[0];
      KeReleaseMutex((PRKMUTEX)(v24 + 32), 0);
      ObfDereferenceObject(v26);
      TmpAcquireTransactionMutex(a3);
      v19 = 1;
      v36 = 1;
      *((_QWORD *)Object + 20) = a3;
      if ( TmIsTransactionActiveExt(a3) )
        goto LABEL_50;
LABEL_24:
      inserted = -1072103421;
LABEL_25:
      v16 = a2;
      goto LABEL_80;
    }
LABEL_78:
    v16 = a2;
  }
  else
  {
    inserted = -1072103342;
    v14 = 0;
  }
LABEL_79:
  v19 = v36;
LABEL_80:
  if ( v14 )
  {
    TmpReleaseTxTableTransactionManager(v14);
    ObfDereferenceObject(v14);
  }
  if ( v19 )
    KeReleaseMutex((PRKMUTEX)(*((_QWORD *)a3 + 11) + 32LL), 0);
  if ( v37 )
    KeReleaseMutex((PRKMUTEX)(v16 + 40), 0);
  if ( v10 )
    ObfDereferenceObject(v10);
  if ( inserted >= 0 && (a5 & 1) != 0 )
  {
    v33 = *((_QWORD *)a3 + 34);
    if ( v33 )
      v34 = *(_DWORD *)(v33 + 196);
    else
      v34 = *((_DWORD *)a3 + 49);
    if ( (v34 & 0x4000) != 0 && (int)TmpForwardCommitTransaction(*((PKTRANSACTION *)Object + 20)) < 0 )
      TmRollbackTransactionExt(*((PKTRANSACTION *)Object + 20), 0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x14001ab8c  mov     rax, rsp
0x14001ab8f  mov     [rax+8], rbx
0x14001ab93  mov     [rax+20h], rsi
0x14001ab97  mov     [rax+18h], r8
0x14001ab9b  mov     [rax+10h], rdx
0x14001ab9f  push    rdi
0x14001aba0  push    r12
0x14001aba2  push    r13
0x14001aba4  push    r14
0x14001aba6  push    r15
0x14001aba8  sub     rsp, 60h
0x14001abac  mov     r12, r9
0x14001abaf  mov     rsi, r8
0x14001abb2  mov     rdi, rcx
0x14001abb5  mov     qword ptr [rax-38h], 0
0x14001abbd  mov     byte ptr [rax-58h], 0
0x14001abc1  mov     byte ptr [rax-57h], 0
0x14001abc5  xor     r14d, r14d
0x14001abc8  mov     [rax-40h], r14
0x14001abcc  mov     [rax-50h], r14
0x14001abd0  xor     r15d, r15d
0x14001abd3  mov     edx, [rax+28h]
0x14001abd6  and     dl, 1
0x14001abd9  mov     r13d, [rax+30h]
0x14001abdd  mov     ecx, r13d
0x14001abe0  call    TmpIsNotificationMaskValid
0x14001abe5  test    al, al
0x14001abe7  jnz     short loc_14001ABFC
0x14001abe9  mov     ebx, 0C000000Dh
0x14001abee  mov     [rsp+88h+var_54], ebx
0x14001abf2  mov     r13, [rsp+88h+var_50]
0x14001abf7  jmp     loc_14001B255
0x14001abfc  mov     qword ptr [rdi+8], 0
0x14001ac04  mov     byte ptr [rdi+28h], 0
0x14001ac08  mov     edx, 38h ; '8'; NumberOfBytes
0x14001ac0d  mov     ecx, 200h; PoolType
0x14001ac12  mov     r8d, 4E466D54h; Tag
0x14001ac18  call    cs:__imp_ExAllocatePoolWithTag
0x14001ac1f  nop     dword ptr [rax+rax+00h]
0x14001ac24  mov     rbx, rax
0x14001ac27  test    rax, rax
0x14001ac2a  jnz     short loc_14001AC33
0x14001ac2c  mov     ebx, 0C000009Ah
0x14001ac31  jmp     short loc_14001ABEE
0x14001ac33  xorps   xmm0, xmm0
0x14001ac36  xor     eax, eax
0x14001ac38  movups  xmmword ptr [rbx], xmm0
0x14001ac3b  movups  xmmword ptr [rbx+10h], xmm0
0x14001ac3f  movups  xmmword ptr [rbx+20h], xmm0
0x14001ac43  mov     [rbx+30h], rax
0x14001ac47  mov     dword ptr [rdi+0A8h], 112h
0x14001ac51  mov     dword ptr [rdi], 0B00B0003h
0x14001ac57  mov     rcx, [rsp+88h+Object]; Object
0x14001ac5f  mov     [rdi+98h], rcx
0x14001ac66  call    cs:__imp_ObfReferenceObject
0x14001ac6d  nop     dword ptr [rax+rax+00h]
0x14001ac72  mov     [rdi+0A0h], rsi
0x14001ac79  mov     rcx, rsi; Object
0x14001ac7c  call    cs:__imp_ObfReferenceObject
0x14001ac83  nop     dword ptr [rax+rax+00h]
0x14001ac88  mov     rax, [rsp+88h+arg_30]
0x14001ac90  mov     [rdi+0B8h], rax
0x14001ac97  mov     dword ptr [rdi+0C0h], 1
0x14001aca1  mov     [rdi+0B0h], r13d
0x14001aca8  xor     r14d, r14d
0x14001acab  mov     [rdi+0ACh], r14d
0x14001acb2  mov     [rdi+0E8h], rbx
0x14001acb9  lea     rax, [rdi+30h]
0x14001acbd  test    r12, r12
0x14001acc0  jnz     short loc_14001ACD3
0x14001acc2  mov     rcx, rax; Uuid
0x14001acc5  call    cs:__imp_ExUuidCreate
0x14001accc  nop     dword ptr [rax+rax+00h]
0x14001acd1  jmp     short loc_14001ACDC
0x14001acd3  movups  xmm0, xmmword ptr [r12]
0x14001acd8  movdqu  xmmword ptr [rax], xmm0
0x14001acdc  mov     [rdi+0C8h], r14
0x14001ace3  mov     [rdi+0D0h], r14d
0x14001acea  lea     rcx, [rdi+40h]; Mutex
0x14001acee  xor     edx, edx; Level
0x14001acf0  call    cs:__imp_KeInitializeMutex
0x14001acf7  nop     dword ptr [rax+rax+00h]
0x14001acfc  mov     [rdi+0F0h], r14
0x14001ad03  mov     [rdi+0F8h], r14
0x14001ad0a  mov     [rdi+100h], r14
0x14001ad11  mov     [rdi+138h], r14d
0x14001ad18  lea     rcx, [rdi+13Ch]; void *
0x14001ad1f  xor     edx, edx; Val
0x14001ad21  mov     r8d, 0A0h; Size
0x14001ad27  call    memset
0x14001ad2c  mov     r12, [rsp+88h+Object]
0x14001ad34  mov     [rsp+88h+Timeout], r14; Timeout
0x14001ad39  xor     r9d, r9d; Alertable
0x14001ad3c  xor     r8d, r8d; WaitMode
0x14001ad3f  xor     edx, edx; WaitReason
0x14001ad41  lea     rcx, [r12+28h]; Object
0x14001ad46  call    cs:__imp_KeWaitForSingleObject
0x14001ad4d  nop     dword ptr [rax+rax+00h]
0x14001ad52  mov     [rsp+88h+var_57], 1
0x14001ad57  mov     r14, [r12+168h]
0x14001ad5f  mov     [rsp+88h+var_40], r14
0x14001ad64  test    r14, r14
0x14001ad67  jz      loc_14001B245
0x14001ad6d  mov     rcx, r14; Object
0x14001ad70  call    cs:__imp_ObfReferenceObject
0x14001ad77  nop     dword ptr [rax+rax+00h]
0x14001ad7c  test    r14, r14
0x14001ad7f  jz      loc_14001B245
0x14001ad85  cmp     dword ptr [r12+1Ch], 1
0x14001ad8b  jnz     short loc_14001AD98
0x14001ad8d  cmp     dword ptr [r14+40h], 2
0x14001ad92  jnz     loc_14001B245
0x14001ad98  xor     edx, edx; Wait
0x14001ad9a  lea     rcx, [r12+28h]; Mutex
0x14001ad9f  call    cs:__imp_KeReleaseMutex
0x14001ada6  nop     dword ptr [rax+rax+00h]
0x14001adab  mov     [rsp+88h+var_57], 0
0x14001adb0  cmp     [rsi+200h], r14
0x14001adb7  cmovnz  r15, r14
0x14001adbb  mov     [rsp+88h+var_48], r15
0x14001adc0  lea     r12, [rsi+58h]
0x14001adc4  mov     r13, [rsp+88h+var_50]
0x14001adc9  mov     rbx, r12
0x14001adcc  cmp     [rsp+88h+var_58], 0
0x14001add1  jz      short loc_14001ADEE
0x14001add3  mov     rcx, [r12]
0x14001add7  add     rcx, 20h ; ' '; Mutex
0x14001addb  xor     edx, edx; Wait
0x14001addd  call    cs:__imp_KeReleaseMutex
0x14001ade4  nop     dword ptr [rax+rax+00h]
0x14001ade9  mov     [rsp+88h+var_58], 0
0x14001adee  test    r13, r13
0x14001adf1  jz      short loc_14001AE12
0x14001adf3  mov     rcx, r13
0x14001adf6  call    TmpReleaseTxTableTransactionManager
0x14001adfb  mov     rcx, r13; Object
0x14001adfe  call    cs:__imp_ObfDereferenceObject
0x14001ae05  nop     dword ptr [rax+rax+00h]
0x14001ae0a  xor     r13d, r13d
0x14001ae0d  mov     [rsp+88h+var_50], r13
0x14001ae12  test    r15, r15
0x14001ae15  jz      short loc_14001AE54
0x14001ae17  mov     rcx, r15; Object
0x14001ae1a  call    cs:__imp_ObfReferenceObject
0x14001ae21  nop     dword ptr [rax+rax+00h]
0x14001ae26  mov     rcx, r15
0x14001ae29  call    TmpAcquireTxTableTransactionManager
0x14001ae2e  mov     r13, r15
0x14001ae31  mov     [rsp+88h+var_50], r15
0x14001ae36  mov     [rsp+88h+var_48], 0
0x14001ae3f  cmp     dword ptr [r15+40h], 5
0x14001ae44  jnz     short loc_14001AE54
0x14001ae46  mov     ebx, 0C0190052h
0x14001ae4b  mov     [rsp+88h+var_54], ebx
0x14001ae4f  jmp     loc_14001B255
0x14001ae54  mov     rcx, rsi
0x14001ae57  call    TmpAcquireTransactionMutex
0x14001ae5c  mov     r15b, 1
0x14001ae5f  mov     [rsp+88h+var_58], r15b
0x14001ae64  mov     rcx, rsi; Transaction
0x14001ae67  call    TmIsTransactionActiveExt
0x14001ae6c  test    al, al
0x14001ae6e  jnz     short loc_14001AE8F
0x14001ae70  cmp     dword ptr [rsi+0C0h], 0Ah
0x14001ae77  jz      short loc_14001AE8F
0x14001ae79  mov     ebx, 0C0190003h
0x14001ae7e  mov     [rsp+88h+var_54], ebx
0x14001ae82  mov     r12, [rsp+88h+Object]
0x14001ae8a  jmp     loc_14001B262
0x14001ae8f  cmp     dword ptr [rsi+0C0h], 1
0x14001ae96  jz      short loc_14001AEAB
0x14001ae98  mov     eax, [rsp+88h+arg_28]
0x14001ae9f  test    r15b, al
0x14001aea2  jz      short loc_14001AEAB
0x14001aea4  mov     ebx, 0C019005Eh
0x14001aea9  jmp     short loc_14001AE7E
0x14001aeab  cmp     qword ptr [rsi+200h], 0
0x14001aeb3  jnz     short loc_14001AEDB
0x14001aeb5  mov     rdx, rsi
0x14001aeb8  mov     rcx, r14; Object
0x14001aebb  call    TmpInsertTxTransactionManager
0x14001aec0  mov     ebx, eax
0x14001aec2  mov     [rsp+88h+var_54], eax
0x14001aec6  mov     r12, [rsp+88h+Object]
0x14001aece  test    eax, eax
0x14001aed0  js      loc_14001B262
0x14001aed6  jmp     loc_14001B0A5
0x14001aedb  mov     eax, [rsp+88h+arg_20]
0x14001aee2  test    r15b, al
0x14001aee5  jz      loc_14001AFCC
0x14001aeeb  mov     eax, [rsi+0C4h]
0x14001aef1  bt      eax, 8
0x14001aef5  jnb     loc_14001AFCC
0x14001aefb  mov     eax, [rsi+0C4h]
0x14001af01  bt      eax, 0Ah
0x14001af05  jnb     loc_14001AFCC
0x14001af0b  cmp     [rsi+200h], r14
0x14001af12  jz      loc_14001AFCC
0x14001af18  lea     rcx, [rsi+100h]
0x14001af1f  mov     rax, [rcx]
0x14001af22  cmp     rax, rcx
0x14001af25  jz      loc_14001AFC2
0x14001af2b  lea     r15, [rax-100h]
0x14001af32  cmp     [r15+200h], r14
0x14001af39  jnz     short loc_14001AFBA
0x14001af3b  cmp     qword ptr [r15+0F0h], 0
0x14001af43  jnz     short loc_14001AFBA
0x14001af45  mov     rbx, rsi
0x14001af48  mov     rsi, r15
0x14001af4b  mov     [rsp+88h+arg_10], r15
0x14001af53  mov     [rsp+88h+var_58], 0
0x14001af58  mov     rcx, r15; Object
0x14001af5b  call    cs:__imp_ObfReferenceObject
0x14001af62  nop     dword ptr [rax+rax+00h]
0x14001af67  mov     rcx, [r12]
0x14001af6b  add     rcx, 20h ; ' '; Mutex
0x14001af6f  xor     edx, edx; Wait
0x14001af71  call    cs:__imp_KeReleaseMutex
0x14001af78  nop     dword ptr [rax+rax+00h]
0x14001af7d  mov     rcx, rbx; Object
0x14001af80  call    cs:__imp_ObfDereferenceObject
0x14001af87  nop     dword ptr [rax+rax+00h]
0x14001af8c  mov     rcx, r15
0x14001af8f  call    TmpAcquireTransactionMutex
0x14001af94  mov     [rsp+88h+var_58], 1
0x14001af99  mov     [rdi+0A0h], r15
0x14001afa0  mov     rcx, r15; Transaction
0x14001afa3  call    TmIsTransactionActiveExt
0x14001afa8  test    al, al
0x14001afaa  jnz     loc_14001B09D
0x14001afb0  mov     ebx, 0C0190003h
0x14001afb5  jmp     loc_14001AE4B
0x14001afba  mov     rax, [rax]
0x14001afbd  jmp     loc_14001AF22
0x14001afc2  mov     ebx, 0C000000Dh
0x14001afc7  jmp     loc_14001AE4B
0x14001afcc  mov     rdx, [rsi+200h]; PVOID
0x14001afd3  mov     r12, [rsp+88h+Object]
0x14001afdb  cmp     rdx, r14
0x14001afde  jz      loc_14001B0A5
0x14001afe4  lea     rax, TmpInternalCrmNotification
0x14001afeb  cmp     [r12+128h], rax
0x14001aff3  jz      loc_14001B0A5
0x14001aff9  mov     r12, rbx
0x14001affc  mov     r15, [rbx]
0x14001afff  lea     rax, [rsp+88h+var_48]
0x14001b004  mov     [rsp+88h+var_60], rax; __int64
0x14001b009  lea     rax, [rsp+88h+Transaction]
0x14001b00e  mov     [rsp+88h+Timeout], rax; __int64
0x14001b013  mov     r9, rsi
0x14001b016  mov     r8, r13
0x14001b019  mov     rcx, r14; Object
0x14001b01c  call    TmpEnlistMultiTm
0x14001b021  mov     ebx, eax
0x14001b023  mov     [rsp+88h+var_54], eax
0x14001b027  cmp     eax, 0C000001Eh
0x14001b02c  jnz     short loc_14001B038
0x14001b02e  mov     r15, [rsp+88h+var_48]
0x14001b033  jmp     loc_14001ADC9
0x14001b038  test    eax, eax
0x14001b03a  js      loc_14001B255
0x14001b040  mov     rbx, rsi
0x14001b043  mov     rsi, [rsp+88h+Transaction]
0x14001b048  mov     [rsp+88h+arg_10], rsi
0x14001b050  mov     [rsp+88h+var_58], 0
0x14001b055  lea     rcx, [r15+20h]; Mutex
0x14001b059  xor     edx, edx; Wait
0x14001b05b  call    cs:__imp_KeReleaseMutex
0x14001b062  nop     dword ptr [rax+rax+00h]
0x14001b067  mov     rcx, rbx; Object
0x14001b06a  call    cs:__imp_ObfDereferenceObject
0x14001b071  nop     dword ptr [rax+rax+00h]
0x14001b076  mov     rcx, rsi
0x14001b079  call    TmpAcquireTransactionMutex
0x14001b07e  mov     r15b, 1
0x14001b081  mov     [rsp+88h+var_58], r15b
0x14001b086  mov     [rdi+0A0h], rsi
0x14001b08d  mov     rcx, rsi; Transaction
0x14001b090  call    TmIsTransactionActiveExt
0x14001b095  test    al, al
0x14001b097  jz      loc_14001AE79
0x14001b09d  mov     r12, [rsp+88h+Object]
0x14001b0a5  mov     eax, [rsp+88h+arg_20]
0x14001b0ac  lea     r15, [rsi+0F0h]
0x14001b0b3  test    al, 1
0x14001b0b5  jz      short loc_14001B100
0x14001b0b7  cmp     qword ptr [r15], 0
0x14001b0bb  jz      short loc_14001B0DE
0x14001b0bd  mov     eax, [rsi+0C4h]
0x14001b0c3  and     eax, 100h
0x14001b0c8  neg     eax
0x14001b0ca  sbb     ebx, ebx
0x14001b0cc  and     ebx, 0FFFFFFBEh
0x14001b0cf  add     ebx, 0C0190054h
0x14001b0d5  mov     [rsp+88h+var_54], ebx
0x14001b0d9  jmp     loc_14001B25D
0x14001b0de  mov     eax, [r12+20h]
0x14001b0e3  test    al, 4
0x14001b0e5  jz      short loc_14001B100
0x14001b0e7  mov     rax, [rsi+200h]
  ... truncated ...
```
