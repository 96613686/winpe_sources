# MpAsyncSendNotification

- ea: `0x140034b50`
- end: `0x14003507e`
- name: `MpAsyncSendNotification`
- size: `1326`
- prototype: ``
- caller_count: `25`
- callee_count: `7`
- tags: `authz_impersonation`

## callers

- `0x140005c30`
- `0x14002e3c4`
- `0x140030380`
- `0x140033a50`
- `0x140033db0`
- `0x1400346f0`
- `0x140035130`
- `0x14003a660`
- `0x14003be04`
- `0x140040388`
- `0x1400451c0`
- `0x1400544a0`
- `0x140063a70`
- `0x140070214`
- `0x140070e84`
- `0x1400740f0`
- `0x1400773e0`
- `0x1400783ec`
- `0x14007af3c`
- `0x14007b128`
- `0x14007b3dc`
- `0x14007c758`
- `0x140082380`
- `0x140084340`
- `0x140085000`

## callees

- `0x140003460`
- `0x140003d20`
- `0x1400051bc`
- `0x1400059dc`
- `0x140011890`
- `0x140034b50`
- `0x140035080`

## import_xrefs

- `ntoskrnl!ExAcquireFastMutex` at `0x140034c29`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034e9b`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034c29`
- `ntoskrnl!ExAcquireFastMutex` at `0x140034e9b`
- `ntoskrnl!KeReleaseSemaphore` at `0x140034d66`
- `ntoskrnl!KeReleaseSemaphore` at `0x140034d66`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034cab`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034ec0`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034cab`
- `ntoskrnl!ExReleaseFastMutex` at `0x140034ec0`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140034be6`
- `ntoskrnl!ExpInterlockedPopEntrySList` at `0x140034be6`

## pseudocode

```c
__int64 __fastcall MpAsyncSendNotification(__int64 a1, unsigned int a2, int a3, int a4, __int64 a5)
{
  __int64 v6; // r14
  unsigned int v8; // edi
  _QWORD *v9; // r15
  char v10; // r12
  union _SLIST_HEADER *v11; // rsi
  PSLIST_ENTRY v12; // rax
  char *v13; // rsi
  char *v14; // rdx
  char *v15; // rax
  char **v16; // rcx
  char *v17; // rcx
  char *v19; // rax
  _QWORD *v20; // rcx
  __int64 v21; // r8
  char **v22; // rcx
  char *v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rcx

  v6 = a2;
  v8 = 0;
  v9 = 0;
  v10 = 0;
  if ( a1 && a2 )
  {
    if ( !*(_QWORD *)(MpData + 416) && !*(_QWORD *)(MpData + 432) )
    {
      v8 = -1073741769;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
        WPP_SF_qD(
          WPP_GLOBAL_Control->AttachedDevice,
          30,
          WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
          KeGetCurrentThread(),
          -1073741769);
      return v8;
    }
    if ( *(int *)(a1 + 16) < 10 )
      *(_QWORD *)a1 = _InterlockedIncrement64((volatile signed __int64 *)(MpData + 856));
    if ( a5 )
      _InterlockedIncrement((volatile signed __int32 *)(a5 + 100));
    v11 = (union _SLIST_HEADER *)((char *)MpAsync + 192);
    ++*((_DWORD *)MpAsync + 53);
    v12 = ExpInterlockedPopEntrySList(v11);
    if ( !v12 )
    {
      ++*((_DWORD *)&v11[1].HeaderX64 + 2);
      v12 = (PSLIST_ENTRY)((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD))v11[3].Alignment)(
                            *((unsigned int *)&v11[2].HeaderX64 + 1),
                            *((unsigned int *)&v11[2].HeaderX64 + 3),
                            *((unsigned int *)&v11[2].HeaderX64 + 2));
      if ( !v12 )
      {
        v8 = -1073741670;
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          WPP_SF_q(
            WPP_GLOBAL_Control->AttachedDevice,
            31,
            WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
            KeGetCurrentThread());
        return v8;
      }
    }
    v12[2].Next = (struct _SLIST_ENTRY *)a1;
    *((_DWORD *)&v12[2].Next + 2) = v6;
    LODWORD(v12->Next) = 1628680;
    *((_DWORD *)&v12[1].Next + 2) = a4;
    v13 = (char *)(&v12->Next + 1);
    v12[1].Next = (struct _SLIST_ENTRY *)(&v12->Next + 1);
    *((_QWORD *)&v12->Next + 1) = &v12->Next + 1;
    ExAcquireFastMutex((PFAST_MUTEX)((char *)MpAsync + 104));
    _InterlockedIncrement((volatile signed __int32 *)(a1 + 12));
    v14 = (char *)MpAsync;
    if ( *((_DWORD *)MpAsync + 40) < (unsigned int)dword_1400269DC )
    {
      if ( a3 )
        v15 = (char *)MpAsync + 8;
      else
        v15 = (char *)MpAsync + 24;
      v16 = (char **)*((_QWORD *)v15 + 1);
      if ( *v16 == v15 )
      {
        *(_QWORD *)v13 = v15;
        *((_QWORD *)v13 + 1) = v16;
        *v16 = v13;
        *((_QWORD *)v15 + 1) = v13;
        *((_DWORD *)MpAsync + 40) = *((_DWORD *)v14 + 40) + 1;
        v10 = 1;
LABEL_14:
        v17 = (char *)MpAsync;
        *((_QWORD *)MpAsync + 41) += v6;
        ExReleaseFastMutex((PFAST_MUTEX)(v17 + 104));
        if ( v10 )
          KeReleaseSemaphore((PRKSEMAPHORE)((char *)MpAsync + 72), 0, 1, 0);
        if ( v9 )
        {
          if ( v9[3] )
          {
            if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
              && (HIDWORD(WPP_GLOBAL_Control->Timer) & 2) != 0 )
            {
              WPP_SF_qidd(
                WPP_GLOBAL_Control->AttachedDevice,
                33,
                v9[3],
                KeGetCurrentThread(),
                *(_QWORD *)v9[3],
                *(_DWORD *)(v9[3] + 16LL),
                *((_DWORD *)MpAsync + 84));
            }
            ExAcquireFastMutex((PFAST_MUTEX)((char *)MpAsync + 104));
            v23 = (char *)MpAsync;
            *((_QWORD *)MpAsync + 41) -= *(unsigned int *)(v9[3] + 8LL);
            ExReleaseFastMutex((PFAST_MUTEX)(v23 + 104));
            MpAsyncDereferenceNotification(v9[3]);
          }
          else if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
                 && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
          {
            WPP_SF_q(
              WPP_GLOBAL_Control->AttachedDevice,
              34,
              WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
              KeGetCurrentThread());
          }
          *((_DWORD *)v9 - 2) = -1162151174;
          ExFreeToNPagedLookasideList((PNPAGED_LOOKASIDE_LIST)((char *)MpAsync + 192), v9 - 1);
        }
        return v8;
      }
LABEL_22:
      __fastfail(3u);
    }
    v19 = (char *)MpAsync + 24;
    if ( a3 )
    {
      v9 = *(_QWORD **)v19;
      if ( *(char **)v19 == v19 )
      {
        v19 = (char *)MpAsync + 8;
        v9 = (_QWORD *)*((_QWORD *)MpAsync + 1);
        v25 = *v9;
        if ( (PVOID)v9[1] != (char *)MpAsync + 8 )
          goto LABEL_22;
        if ( *(_QWORD **)(v25 + 8) != v9 )
          goto LABEL_22;
        *(_QWORD *)v19 = v25;
        *(_QWORD *)(v25 + 8) = v19;
        v22 = (char **)*((_QWORD *)v14 + 2);
        if ( *v22 != v19 )
          goto LABEL_22;
      }
      else
      {
        v24 = *v9;
        if ( (char *)v9[1] != v19 )
          goto LABEL_22;
        if ( *(_QWORD **)(v24 + 8) != v9 )
          goto LABEL_22;
        *(_QWORD *)v19 = v24;
        *(_QWORD *)(v24 + 8) = v19;
        v19 = v14 + 8;
        v22 = (char **)*((_QWORD *)v14 + 2);
        if ( *v22 != v14 + 8 )
          goto LABEL_22;
      }
    }
    else
    {
      v20 = *(_QWORD **)v19;
      if ( *(char **)v19 == v19 )
      {
LABEL_30:
        _InterlockedIncrement((volatile signed __int32 *)v14 + 84);
        goto LABEL_14;
      }
      v21 = *v20;
      if ( (char *)v20[1] != v19 )
        goto LABEL_22;
      if ( *(_QWORD **)(v21 + 8) != v20 )
        goto LABEL_22;
      *(_QWORD *)v19 = v21;
      *(_QWORD *)(v21 + 8) = v19;
      v9 = v20;
      v22 = (char **)*((_QWORD *)v14 + 4);
      if ( *v22 != v19 )
        goto LABEL_22;
    }
    *(_QWORD *)v13 = v19;
    *((_QWORD *)v13 + 1) = v22;
    *v22 = v13;
    *((_QWORD *)v19 + 1) = v13;
    goto LABEL_30;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    WPP_SF_q(
      WPP_GLOBAL_Control->AttachedDevice,
      29,
      WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids,
      KeGetCurrentThread());
  return (unsigned int)-1073741811;
}

```

## disassembly

```asm
0x140034b50  mov     [rsp+arg_8], rbx
0x140034b55  mov     [rsp+arg_10], rsi
0x140034b5a  mov     [rsp+arg_18], r9d
0x140034b5f  push    rdi
0x140034b60  push    r12
0x140034b62  push    r13
0x140034b64  push    r14
0x140034b66  push    r15
0x140034b68  sub     rsp, 40h
0x140034b6c  mov     r13d, r8d
0x140034b6f  mov     r14d, edx
0x140034b72  mov     rbx, rcx
0x140034b75  xor     edi, edi
0x140034b77  mov     r15d, edi
0x140034b7a  mov     [rsp+68h+arg_0], rdi
0x140034b7f  xor     r12b, r12b
0x140034b82  test    rcx, rcx
0x140034b85  jz      loc_140034EF9
0x140034b8b  test    edx, edx
0x140034b8d  jz      loc_140034EF9
0x140034b93  mov     r9, cs:MpData
0x140034b9a  cmp     [r9+1A0h], rdi
0x140034ba1  jz      loc_140034F1A
0x140034ba7  cmp     dword ptr [rcx+10h], 0Ah
0x140034bab  jge     short loc_140034BC1
0x140034bad  mov     eax, 1
0x140034bb2  lock xadd [r9+358h], rax
0x140034bbb  inc     rax
0x140034bbe  mov     [rcx], rax
0x140034bc1  mov     rax, [rsp+68h+arg_20]
0x140034bc9  test    rax, rax
0x140034bcc  jz      short loc_140034BD2
0x140034bce  lock inc dword ptr [rax+64h]
0x140034bd2  mov     rsi, cs:MpAsync
0x140034bd9  add     rsi, 0C0h
0x140034be0  inc     dword ptr [rsi+14h]
0x140034be3  mov     rcx, rsi; ListHead
0x140034be6  call    cs:__imp_ExpInterlockedPopEntrySList
0x140034bed  nop     dword ptr [rax+rax+00h]
0x140034bf2  test    rax, rax
0x140034bf5  jz      loc_140034CE7
0x140034bfb  mov     [rax+20h], rbx
0x140034bff  mov     [rax+28h], r14d
0x140034c03  mov     dword ptr [rax], 18DA08h
0x140034c09  mov     ecx, [rsp+68h+arg_18]
0x140034c10  mov     [rax+18h], ecx
0x140034c13  lea     rsi, [rax+8]
0x140034c17  mov     [rsi+8], rsi
0x140034c1b  mov     [rsi], rsi
0x140034c1e  mov     rcx, cs:MpAsync
0x140034c25  add     rcx, 68h ; 'h'; FastMutex
0x140034c29  call    cs:__imp_ExAcquireFastMutex
0x140034c30  nop     dword ptr [rax+rax+00h]
0x140034c35  lock inc dword ptr [rbx+0Ch]
0x140034c39  mov     rax, cs:MpAsync
0x140034c40  mov     ecx, [rax+0A0h]
0x140034c46  mov     rdx, cs:MpAsync
0x140034c4d  cmp     ecx, cs:dword_1400269DC
0x140034c53  jnb     loc_140034DD2
0x140034c59  test    r13d, r13d
0x140034c5c  jnz     loc_140034DC9
0x140034c62  lea     rax, [rdx+18h]
0x140034c66  mov     rcx, [rax+8]
0x140034c6a  cmp     [rcx], rax
0x140034c6d  jnz     loc_140034DC2
0x140034c73  mov     [rsi], rax
0x140034c76  mov     [rsi+8], rcx
0x140034c7a  mov     [rcx], rsi
0x140034c7d  mov     [rax+8], rsi
0x140034c81  mov     ecx, [rdx+0A0h]
0x140034c87  inc     ecx
0x140034c89  mov     rax, cs:MpAsync
0x140034c90  mov     [rax+0A0h], ecx
0x140034c96  mov     r12b, 1
0x140034c99  mov     rcx, cs:MpAsync
0x140034ca0  add     [rcx+148h], r14
0x140034ca7  add     rcx, 68h ; 'h'; FastMutex
0x140034cab  call    cs:__imp_ExReleaseFastMutex
0x140034cb2  nop     dword ptr [rax+rax+00h]
0x140034cb7  test    r12b, r12b
0x140034cba  jnz     loc_140034D50
0x140034cc0  test    r15, r15
0x140034cc3  jnz     loc_140034E28
0x140034cc9  mov     eax, edi
0x140034ccb  mov     rbx, [rsp+68h+arg_8]
0x140034cd0  mov     rsi, [rsp+68h+arg_10]
0x140034cd8  add     rsp, 40h
0x140034cdc  pop     r15
0x140034cde  pop     r14
0x140034ce0  pop     r13
0x140034ce2  pop     r12
0x140034ce4  pop     rdi
0x140034ce5  retn
0x140034ce7  inc     dword ptr [rsi+18h]
0x140034cea  mov     edx, [rsi+2Ch]
0x140034ced  mov     rax, [rsi+30h]
0x140034cf1  mov     r8d, [rsi+28h]
0x140034cf5  mov     ecx, [rsi+24h]
0x140034cf8  call    cs:__guard_dispatch_icall_fptr
0x140034cfe  test    rax, rax
0x140034d01  jnz     loc_140034BFB
0x140034d07  mov     edi, 0C000009Ah
0x140034d0c  lea     rax, WPP_GLOBAL_Control
0x140034d13  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d1a  cmp     rcx, rax
0x140034d1d  jz      short loc_140034CC9
0x140034d1f  mov     eax, [rcx+2Ch]
0x140034d22  test    al, 1
0x140034d24  jz      short loc_140034CC9
0x140034d26  mov     r9, gs:188h
0x140034d2f  mov     edx, 1Fh
0x140034d34  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140034d3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034d42  mov     rcx, [rcx+18h]
0x140034d46  call    WPP_SF_q
0x140034d4b  jmp     loc_140034CC9
0x140034d50  mov     rcx, cs:MpAsync
0x140034d57  add     rcx, 48h ; 'H'; Semaphore
0x140034d5b  xor     r9d, r9d; Wait
0x140034d5e  xor     edx, edx; Increment
0x140034d60  mov     r8d, 1; Adjustment
0x140034d66  call    cs:__imp_KeReleaseSemaphore
0x140034d6d  nop     dword ptr [rax+rax+00h]
0x140034d72  jmp     loc_140034CC0
0x140034d77  lea     rcx, WPP_GLOBAL_Control
0x140034d7e  mov     rax, cs:WPP_GLOBAL_Control
0x140034d85  cmp     rax, rcx
0x140034d88  jz      short loc_140034DB6
0x140034d8a  mov     eax, [rax+2Ch]
0x140034d8d  test    al, 1
0x140034d8f  jz      short loc_140034DB6
0x140034d91  mov     r9, gs:188h
0x140034d9a  mov     edx, 20h ; ' '
0x140034d9f  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140034da6  mov     rcx, cs:WPP_GLOBAL_Control
0x140034dad  mov     rcx, [rcx+18h]
0x140034db1  call    WPP_SF_q
0x140034db6  xor     edi, edi
0x140034db8  mov     r15, [rsp+68h+arg_0]
0x140034dbd  jmp     loc_140034CC0
0x140034dc2  mov     ecx, 3
0x140034dc7  int     29h; Win8: RtlFailFast(ecx)
0x140034dc9  lea     rax, [rdx+8]
0x140034dcd  jmp     loc_140034C66
0x140034dd2  lea     rax, [rdx+18h]
0x140034dd6  test    r13d, r13d
0x140034dd9  jnz     loc_140034F80
0x140034ddf  mov     rcx, [rax]
0x140034de2  cmp     rcx, rax
0x140034de5  jz      short loc_140034E1C
0x140034de7  mov     r8, [rcx]
0x140034dea  cmp     [rcx+8], rax
0x140034dee  jnz     short loc_140034DC2
0x140034df0  cmp     [r8+8], rcx
0x140034df4  jnz     short loc_140034DC2
0x140034df6  mov     [rax], r8
0x140034df9  mov     [r8+8], rax
0x140034dfd  mov     r15, rcx
0x140034e00  mov     [rsp+68h+arg_0], rcx
0x140034e05  mov     rcx, [rax+8]
0x140034e09  cmp     [rcx], rax
0x140034e0c  jnz     short loc_140034DC2
0x140034e0e  mov     [rsi], rax
0x140034e11  mov     [rsi+8], rcx
0x140034e15  mov     [rcx], rsi
0x140034e18  mov     [rax+8], rsi
0x140034e1c  lock inc dword ptr [rdx+150h]
0x140034e23  jmp     loc_140034C99
0x140034e28  cmp     qword ptr [r15+18h], 0
0x140034e2d  jz      loc_140034FFD
0x140034e33  lea     rax, WPP_GLOBAL_Control
0x140034e3a  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e41  cmp     rcx, rax
0x140034e44  jz      short loc_140034E90
0x140034e46  mov     eax, [rcx+2Ch]
0x140034e49  test    al, 2
0x140034e4b  jz      short loc_140034E90
0x140034e4d  mov     r9, gs:188h
0x140034e56  mov     rax, cs:MpAsync
0x140034e5d  mov     ecx, [rax+150h]
0x140034e63  mov     r8, [r15+18h]
0x140034e67  mov     edx, 21h ; '!'
0x140034e6c  mov     [rsp+68h+var_38], ecx
0x140034e70  mov     eax, [r8+10h]
0x140034e74  mov     [rsp+68h+var_40], eax
0x140034e78  mov     rax, [r8]
0x140034e7b  mov     [rsp+68h+var_48], rax
0x140034e80  mov     rcx, cs:WPP_GLOBAL_Control
0x140034e87  mov     rcx, [rcx+18h]
0x140034e8b  call    WPP_SF_qidd
0x140034e90  mov     rcx, cs:MpAsync
0x140034e97  add     rcx, 68h ; 'h'; FastMutex
0x140034e9b  call    cs:__imp_ExAcquireFastMutex
0x140034ea2  nop     dword ptr [rax+rax+00h]
0x140034ea7  mov     rdx, cs:MpAsync
0x140034eae  mov     rax, [r15+18h]
0x140034eb2  mov     ecx, [rax+8]
0x140034eb5  sub     [rdx+148h], rcx
0x140034ebc  lea     rcx, [rdx+68h]; FastMutex
0x140034ec0  call    cs:__imp_ExReleaseFastMutex
0x140034ec7  nop     dword ptr [rax+rax+00h]
0x140034ecc  mov     rcx, [r15+18h]
0x140034ed0  call    MpAsyncDereferenceNotification
0x140034ed5  mov     dword ptr [r15-8], 0BABAFAFAh
0x140034edd  mov     rcx, cs:MpAsync
0x140034ee4  add     rcx, 0C0h; Lookaside
0x140034eeb  lea     rdx, [r15-8]; Entry
0x140034eef  call    ExFreeToNPagedLookasideList
0x140034ef4  jmp     loc_140034CC9
0x140034ef9  lea     rax, WPP_GLOBAL_Control
0x140034f00  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f07  cmp     rcx, rax
0x140034f0a  jnz     loc_140035049
0x140034f10  mov     edi, 0C000000Dh
0x140034f15  jmp     loc_140034CC9
0x140034f1a  cmp     [r9+1B0h], rdi
0x140034f21  jnz     loc_140034BA7
0x140034f27  mov     edi, 0C0000037h
0x140034f2c  lea     rax, WPP_GLOBAL_Control
0x140034f33  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f3a  cmp     rcx, rax
0x140034f3d  jz      loc_140034CC9
0x140034f43  mov     eax, [rcx+2Ch]
0x140034f46  test    al, 2
0x140034f48  jz      loc_140034CC9
0x140034f4e  mov     r9, gs:188h
0x140034f57  mov     edx, 1Eh
0x140034f5c  mov     dword ptr [rsp+68h+var_48], 0C0000037h
0x140034f64  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140034f6b  mov     rcx, cs:WPP_GLOBAL_Control
0x140034f72  mov     rcx, [rcx+18h]
0x140034f76  call    WPP_SF_qD
0x140034f7b  jmp     loc_140034CC9
0x140034f80  mov     r15, [rax]
0x140034f83  cmp     r15, rax
0x140034f86  jz      short loc_140034FC1
0x140034f88  mov     rcx, [r15]
0x140034f8b  cmp     [r15+8], rax
0x140034f8f  jnz     loc_140034DC2
0x140034f95  cmp     [rcx+8], r15
0x140034f99  jnz     loc_140034DC2
0x140034f9f  mov     [rax], rcx
0x140034fa2  mov     [rcx+8], rax
0x140034fa6  mov     [rsp+68h+arg_0], r15
0x140034fab  lea     rax, [rdx+8]
0x140034faf  mov     rcx, [rax+8]
0x140034fb3  cmp     [rcx], rax
0x140034fb6  jnz     loc_140034DC2
0x140034fbc  jmp     loc_140034E0E
0x140034fc1  lea     rax, [rdx+8]
0x140034fc5  mov     r15, [rax]
0x140034fc8  mov     rcx, [r15]
0x140034fcb  cmp     [r15+8], rax
0x140034fcf  jnz     loc_140034DC2
0x140034fd5  cmp     [rcx+8], r15
0x140034fd9  jnz     loc_140034DC2
0x140034fdf  mov     [rax], rcx
0x140034fe2  mov     [rcx+8], rax
0x140034fe6  mov     [rsp+68h+arg_0], r15
0x140034feb  mov     rcx, [rax+8]
0x140034fef  cmp     [rcx], rax
0x140034ff2  jnz     loc_140034DC2
0x140034ff8  jmp     loc_140034E0E
0x140034ffd  lea     rax, WPP_GLOBAL_Control
0x140035004  mov     rcx, cs:WPP_GLOBAL_Control
0x14003500b  cmp     rcx, rax
0x14003500e  jz      loc_140034ED5
0x140035014  mov     eax, [rcx+2Ch]
0x140035017  test    al, 1
0x140035019  jz      loc_140034ED5
0x14003501f  mov     r9, gs:188h
0x140035028  mov     edx, 22h ; '"'
0x14003502d  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140035034  mov     rcx, cs:WPP_GLOBAL_Control
0x14003503b  mov     rcx, [rcx+18h]
0x14003503f  call    WPP_SF_q
0x140035044  jmp     loc_140034ED5
0x140035049  mov     eax, [rcx+2Ch]
0x14003504c  test    al, 1
0x14003504e  jz      loc_140034F10
0x140035054  mov     r9, gs:188h
0x14003505d  mov     edx, 1Dh
0x140035062  lea     r8, WPP_5c114a40c3de3145ebb792b3b9433cba_Traceguids
0x140035069  mov     rcx, cs:WPP_GLOBAL_Control
0x140035070  mov     rcx, [rcx+18h]
0x140035074  call    WPP_SF_q
0x140035079  jmp     loc_140034F10
0x14008c890  push    rbp
0x14008c892  sub     rsp, 40h
0x14008c896  mov     rbp, rdx
0x14008c899  mov     rax, [rcx]
0x14008c89c  mov     ecx, [rax]
0x14008c89e  xor     eax, eax
0x14008c8a0  cmp     ecx, 0C0000047h
0x14008c8a6  setz    al
0x14008c8a9  add     rsp, 40h
0x14008c8ad  pop     rbp
0x14008c8ae  retn
```
