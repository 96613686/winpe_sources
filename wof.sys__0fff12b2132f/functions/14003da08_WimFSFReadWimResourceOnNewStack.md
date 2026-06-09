# WimFSFReadWimResourceOnNewStack

- ea: `0x14003da08`
- end: `0x14003dfc7`
- name: `WimFSFReadWimResourceOnNewStack`
- size: `1471`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cfc0`

## callees

- `0x1400094f0`
- `0x14000c074`
- `0x14000d3b8`
- `0x14000fb60`
- `0x140010078`
- `0x1400105e8`
- `0x1400106a8`
- `0x1400107e8`
- `0x140011560`
- `0x1400119c0`
- `0x14002e1f4`
- `0x14003ccf0`
- `0x14003da08`

## import_xrefs

- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003de73`
- `ntoskrnl!ExAllocateFromPagedLookasideList` at `0x14003de73`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003db89`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003db89`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de1d`
- `ntoskrnl!ExAllocatePoolWithTag` at `0x14003de1d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003db71`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003db71`

## pseudocode

```c
__int64 __fastcall WimFSFReadWimResourceOnNewStack(__int64 a1, __int64 a2)
{
  __int64 v3; // rbx
  void *v4; // rdi
  void *v5; // r14
  __int64 v6; // r12
  __int64 v7; // r13
  __int64 v8; // rax
  _DWORD *v9; // r15
  __int64 result; // rax
  struct _FLT_CALLBACK_DATA *v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // r8
  int v14; // edi
  __int64 v15; // r13
  __int64 v16; // r8
  __int64 v17; // r9
  unsigned __int64 v18; // r15
  __int64 v19; // rdi
  struct _FLT_CALLBACK_DATA *v20; // rbx
  unsigned int v21; // ecx
  unsigned int v22; // edi
  char v23; // al
  char v24; // dl
  const char *v25; // r9
  char *PoolWithTag; // r15
  PVOID v27; // r12
  char *v28; // rax
  __int64 v29; // rsi
  __int64 v30; // rdx
  char *v31; // rcx
  PDEVICE_OBJECT v32; // r8
  const char *v33; // r9
  unsigned __int8 v34; // [rsp+40h] [rbp-C0h]
  char v35; // [rsp+41h] [rbp-BFh]
  char v36; // [rsp+42h] [rbp-BEh]
  unsigned int v37; // [rsp+44h] [rbp-BCh]
  SIZE_T NumberOfBytes; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v39; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v40; // [rsp+58h] [rbp-A8h]
  __int64 v41; // [rsp+60h] [rbp-A0h] BYREF
  int v42[2]; // [rsp+68h] [rbp-98h] BYREF
  _DWORD Context[72]; // [rsp+70h] [rbp-90h] BYREF

  v3 = *(_QWORD *)(a1 + 64);
  v4 = *(void **)(a1 + 96);
  v5 = *(void **)(a1 + 72);
  v6 = *(unsigned int *)(a1 + 88);
  v7 = *(_QWORD *)(a1 + 80);
  v40 = *(_QWORD *)(a1 + 24);
  v34 = *(_BYTE *)(a1 + 56);
  v39 = 0;
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 26, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
  *(_DWORD *)(a1 + 92) = 0;
  v8 = *(_QWORD *)(a1 + 40);
  v9 = (_DWORD *)((v7 + 64) & -(__int64)(v7 != 0));
  if ( v3 >= v8 )
    return 0;
  if ( v8 == *(_QWORD *)(a1 + 32) )
  {
    memset(Context, 0, sizeof(Context));
    v11 = (struct _FLT_CALLBACK_DATA *)(*(_QWORD *)(a1 + 48) + v3);
    WimFSFInitializeCompletionContextOnStack(a1, v12, Context);
    LOBYTE(v13) = 1;
    result = WimFSFReadWim(v34, 0, v13, v11, v4, v5, v6, (char *)Context);
    *(_DWORD *)(a1 + 92) = Context[29];
    return result;
  }
  if ( v7 )
  {
    v14 = 0;
    if ( (*v9 & 1) == 0 )
    {
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 27, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
      LOBYTE(a2) = v34;
      v14 = WimFSFBuildChunkTable(a1, a2, v9 + 8);
      if ( v14 < 0 )
        goto LABEL_68;
      ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
      *v9 |= 1u;
      ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v7 + 32LL));
    }
    if ( !v39 )
      v39 = *(_QWORD *)(((v7 + 64) & -(__int64)(v7 != 0)) + 0x20);
  }
  else
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 28, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    LOBYTE(a2) = v34;
    v14 = WimFSFBuildChunkTable(a1, a2, &v39);
    if ( v14 < 0 )
      goto LABEL_68;
  }
  if ( v3 + v6 > *(_QWORD *)(a1 + 40) )
  {
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        29,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        (unsigned int)v6,
        *(_DWORD *)(a1 + 40) - v3);
    LODWORD(v6) = *(_DWORD *)(a1 + 40) - v3;
  }
  if ( (_DWORD)v6 )
  {
    *(_QWORD *)v42 = 0;
    v37 = 0;
    NumberOfBytes = 0;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_d(
        WPP_GLOBAL_Control->AttachedDevice,
        30,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        (unsigned int)v6);
    v15 = v40;
    v16 = *(unsigned int *)(v40 + 104);
    v17 = v3 / v16;
    v40 = v3 / v16;
    v18 = (-v16 & (v3 + v16 + (unsigned __int64)(unsigned int)v6 - 1)) / v16;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      WPP_SF_dd(WPP_GLOBAL_Control->AttachedDevice, 31, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v17, v18);
      LODWORD(v17) = v40;
    }
    v19 = v39;
    if ( v39 )
    {
      v41 = WimFSFGetChunkOffset(v39, (unsigned int)v17);
      v20 = (struct _FLT_CALLBACK_DATA *)v41;
      v21 = WimFSFGetChunkOffset(v19, (unsigned int)v18) - (_DWORD)v20;
    }
    else
    {
      v20 = *(struct _FLT_CALLBACK_DATA **)(a1 + 48);
      v21 = *(_DWORD *)(a1 + 32);
      v41 = (__int64)v20;
    }
    v22 = v21 + 4;
    if ( (*(_DWORD *)(v15 + 96) & 0x40000) == 0 )
      v22 = v21;
    if ( v34 )
    {
      v23 = WimFSFGetAlignedSizesForIntegrity(
              v15,
              (unsigned int)&v41,
              v22,
              *(_DWORD *)(v15 + 92),
              (__int64)v42,
              (__int64)&NumberOfBytes,
              (__int64)&NumberOfBytes + 4);
      v20 = *(struct _FLT_CALLBACK_DATA **)v42;
      v24 = v23;
      v22 = NumberOfBytes;
      v37 = HIDWORD(NumberOfBytes);
      v36 = 1;
    }
    else
    {
      v36 = 0;
      v24 = 1;
    }
    v35 = v24;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v25 = "IS";
      if ( !v24 )
        v25 = "IS NOT";
      WPP_SF_s(WPP_GLOBAL_Control->AttachedDevice, 32, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v25);
    }
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
      WPP_SF_dd(
        WPP_GLOBAL_Control->AttachedDevice,
        33,
        WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids,
        v22,
        *(_DWORD *)(v15 + 448));
    if ( v22 <= *(_DWORD *)(v15 + 448) )
    {
      v28 = (char *)ExAllocateFromPagedLookasideList((PPAGED_LOOKASIDE_LIST)(v15 + 512));
      v27 = v28;
      if ( !v28 )
        goto LABEL_51;
      PoolWithTag = v28;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 35, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids);
    }
    else
    {
      PoolWithTag = (char *)ExAllocatePoolWithTag(PagedPool, v22, 0x44527077u);
      if ( !PoolWithTag )
      {
LABEL_51:
        v14 = -1073741670;
        goto LABEL_68;
      }
      v27 = 0;
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
        WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 34, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, v22);
    }
    v29 = a1 - 24;
    *(_QWORD *)(v29 + 272) = v27;
    *(_QWORD *)(v29 + 240) = WimFSFReadWimResourceOnNewStackExtendedCompletion;
    *(_QWORD *)(v29 + 248) = v39;
    *(_DWORD *)(v29 + 264) = v40;
    *(_QWORD *)(v29 + 280) = PoolWithTag;
    v30 = v37;
    if ( v34 )
      v31 = &PoolWithTag[v37];
    else
      v31 = PoolWithTag;
    *(_QWORD *)(v29 + 256) = v31;
    v32 = WPP_GLOBAL_Control;
    if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 5u )
    {
      v33 = "PAGING";
      if ( !v34 )
        v33 = "NORMAL";
      WPP_SF_sqD(WPP_GLOBAL_Control->AttachedDevice, v37, (_DWORD)WPP_GLOBAL_Control, (_DWORD)v33, (char)v31, v37);
    }
    LOBYTE(v32) = v35;
    LOBYTE(v30) = v36;
    v14 = WimFSFReadWim(v34, v30, (__int64)v32, v20, PoolWithTag, 0, v22, (char *)v29);
  }
LABEL_68:
  if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x20) != 0 && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
    WPP_SF_d(WPP_GLOBAL_Control->AttachedDevice, 37, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids, (unsigned int)v14);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x14003da08  push    rbp
0x14003da0a  push    rbx
0x14003da0b  push    rsi
0x14003da0c  push    rdi
0x14003da0d  push    r12
0x14003da0f  push    r13
0x14003da11  push    r14
0x14003da13  push    r15
0x14003da15  lea     rbp, [rsp-0A8h]
0x14003da1d  sub     rsp, 1A8h
0x14003da24  mov     rax, cs:__security_cookie
0x14003da2b  xor     rax, rsp
0x14003da2e  mov     [rbp+0E0h+var_50], rax
0x14003da35  mov     rax, [rcx+18h]
0x14003da39  mov     rsi, rcx
0x14003da3c  mov     rbx, [rcx+40h]
0x14003da40  mov     rdi, [rcx+60h]
0x14003da44  mov     r14, [rcx+48h]
0x14003da48  mov     r12d, [rcx+58h]
0x14003da4c  mov     r13, [rcx+50h]
0x14003da50  mov     [rsp+1E0h+var_188], rax
0x14003da55  mov     al, [rcx+38h]
0x14003da58  mov     byte ptr [rsp+1E0h+var_1A0], al
0x14003da5c  mov     [rsp+1E0h+var_190], 0
0x14003da65  mov     rcx, cs:WPP_GLOBAL_Control
0x14003da6c  mov     eax, [rcx+2Ch]
0x14003da6f  test    al, 20h
0x14003da71  jz      short loc_14003DA8E
0x14003da73  cmp     byte ptr [rcx+29h], 4
0x14003da77  jb      short loc_14003DA8E
0x14003da79  mov     rcx, [rcx+18h]
0x14003da7d  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003da84  mov     edx, 1Ah
0x14003da89  call    WPP_SF_
0x14003da8e  mov     rax, r13
0x14003da91  mov     dword ptr [rsi+5Ch], 0
0x14003da98  neg     rax
0x14003da9b  lea     rcx, [r13+40h]
0x14003da9f  mov     rax, [rsi+28h]
0x14003daa3  sbb     r15, r15
0x14003daa6  and     r15, rcx
0x14003daa9  cmp     rbx, rax
0x14003daac  jl      short loc_14003DAB5
0x14003daae  xor     eax, eax
0x14003dab0  jmp     loc_14003DFA3
0x14003dab5  cmp     rax, [rsi+20h]
0x14003dab9  jnz     short loc_14003DB13
0x14003dabb  xor     edx, edx; Val
0x14003dabd  lea     rcx, [rsp+1E0h+var_170]; void *
0x14003dac2  mov     r8d, 120h; Size
0x14003dac8  call    memset
0x14003dacd  add     rbx, [rsi+30h]
0x14003dad1  lea     r8, [rsp+1E0h+var_170]
0x14003dad6  mov     rcx, rsi
0x14003dad9  call    WimFSFInitializeCompletionContextOnStack
0x14003dade  mov     cl, byte ptr [rsp+1E0h+var_1A0]; int
0x14003dae2  lea     rax, [rsp+1E0h+var_170]
0x14003dae7  mov     [rsp+1E0h+Context], rax; Context
0x14003daec  mov     r9, rbx; int
0x14003daef  mov     [rsp+1E0h+var_1B0], r12d; int
0x14003daf4  mov     r8b, 1; int
0x14003daf7  mov     [rsp+1E0h+var_1B8], r14; __int64
0x14003dafc  xor     edx, edx; int
0x14003dafe  mov     [rsp+1E0h+var_1C0], rdi; PVOID
0x14003db03  call    WimFSFReadWim
0x14003db08  mov     ecx, [rbp+0E0h+var_FC]
0x14003db0b  mov     [rsi+5Ch], ecx
0x14003db0e  jmp     loc_14003DFA3
0x14003db13  mov     r14b, 5
0x14003db16  test    r13, r13
0x14003db19  jz      loc_14003DBA8
0x14003db1f  mov     eax, [r15]
0x14003db22  xor     edi, edi
0x14003db24  test    al, 1
0x14003db26  jnz     short loc_14003DB95
0x14003db28  mov     rcx, cs:WPP_GLOBAL_Control
0x14003db2f  mov     eax, [rcx+2Ch]
0x14003db32  test    al, 20h
0x14003db34  jz      short loc_14003DB4F
0x14003db36  cmp     [rcx+29h], r14b
0x14003db3a  jb      short loc_14003DB4F
0x14003db3c  mov     rcx, [rcx+18h]
0x14003db40  lea     edx, [rdi+1Bh]
0x14003db43  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003db4a  call    WPP_SF_
0x14003db4f  mov     dl, byte ptr [rsp+1E0h+var_1A0]
0x14003db53  lea     r8, [r15+20h]
0x14003db57  mov     rcx, rsi
0x14003db5a  call    WimFSFBuildChunkTable
0x14003db5f  mov     edi, eax
0x14003db61  test    eax, eax
0x14003db63  js      loc_14003DF75
0x14003db69  mov     rcx, [r13+0]
0x14003db6d  add     rcx, 20h ; ' '; FastMutex
0x14003db71  call    cs:__imp_ExAcquireFastMutexUnsafe
0x14003db78  nop     dword ptr [rax+rax+00h]
0x14003db7d  or      dword ptr [r15], 1
0x14003db81  mov     rcx, [r13+0]
0x14003db85  add     rcx, 20h ; ' '; FastMutex
0x14003db89  call    cs:__imp_ExReleaseFastMutexUnsafe
0x14003db90  nop     dword ptr [rax+rax+00h]
0x14003db95  cmp     [rsp+1E0h+var_190], 0
0x14003db9b  jnz     short loc_14003DBEC
0x14003db9d  mov     rax, [r15+20h]
0x14003dba1  mov     [rsp+1E0h+var_190], rax
0x14003dba6  jmp     short loc_14003DBEC
0x14003dba8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dbaf  mov     eax, [rcx+2Ch]
0x14003dbb2  test    al, 20h
0x14003dbb4  jz      short loc_14003DBD1
0x14003dbb6  cmp     [rcx+29h], r14b
0x14003dbba  jb      short loc_14003DBD1
0x14003dbbc  mov     rcx, [rcx+18h]
0x14003dbc0  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dbc7  mov     edx, 1Ch
0x14003dbcc  call    WPP_SF_
0x14003dbd1  mov     dl, byte ptr [rsp+1E0h+var_1A0]
0x14003dbd5  lea     r8, [rsp+1E0h+var_190]
0x14003dbda  mov     rcx, rsi
0x14003dbdd  call    WimFSFBuildChunkTable
0x14003dbe2  mov     edi, eax
0x14003dbe4  test    eax, eax
0x14003dbe6  js      loc_14003DF75
0x14003dbec  lea     rax, [rbx+r12]
0x14003dbf0  cmp     rax, [rsi+28h]
0x14003dbf4  jle     short loc_14003DC32
0x14003dbf6  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dbfd  mov     eax, [rcx+2Ch]
0x14003dc00  test    al, 20h
0x14003dc02  jz      short loc_14003DC2B
0x14003dc04  cmp     [rcx+29h], r14b
0x14003dc08  jb      short loc_14003DC2B
0x14003dc0a  mov     eax, [rsi+28h]
0x14003dc0d  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dc14  mov     rcx, [rcx+18h]
0x14003dc18  sub     eax, ebx
0x14003dc1a  mov     edx, 1Dh
0x14003dc1f  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x14003dc23  mov     r9d, r12d
0x14003dc26  call    WPP_SF_dd
0x14003dc2b  mov     r12d, [rsi+28h]
0x14003dc2f  sub     r12d, ebx
0x14003dc32  test    r12d, r12d
0x14003dc35  jz      loc_14003DF75
0x14003dc3b  xor     eax, eax
0x14003dc3d  mov     qword ptr [rsp+1E0h+var_178], 0
0x14003dc46  mov     [rsp+1E0h+var_19C], eax
0x14003dc4a  mov     dword ptr [rsp+1E0h+NumberOfBytes+4], eax
0x14003dc4e  mov     dword ptr [rsp+1E0h+NumberOfBytes], 0
0x14003dc56  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dc5d  mov     eax, [rcx+2Ch]
0x14003dc60  test    al, 20h
0x14003dc62  jz      short loc_14003DC82
0x14003dc64  cmp     [rcx+29h], r14b
0x14003dc68  jb      short loc_14003DC82
0x14003dc6a  mov     rcx, [rcx+18h]
0x14003dc6e  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dc75  mov     edx, 1Eh
0x14003dc7a  mov     r9d, r12d
0x14003dc7d  call    WPP_SF_d
0x14003dc82  mov     r13, [rsp+1E0h+var_188]
0x14003dc87  mov     rax, rbx
0x14003dc8a  cqo
0x14003dc8c  mov     r8d, [r13+68h]
0x14003dc90  idiv    r8
0x14003dc93  mov     ecx, r8d
0x14003dc96  xor     edx, edx
0x14003dc98  mov     r9, rax
0x14003dc9b  mov     [rsp+1E0h+var_188], rax
0x14003dca0  neg     rcx
0x14003dca3  mov     eax, r12d
0x14003dca6  dec     rax
0x14003dca9  add     rax, r8
0x14003dcac  add     rax, rbx
0x14003dcaf  and     rax, rcx
0x14003dcb2  div     r8
0x14003dcb5  mov     r15, rax
0x14003dcb8  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dcbf  mov     edx, [rcx+2Ch]
0x14003dcc2  test    dl, 20h
0x14003dcc5  jz      short loc_14003DCEC
0x14003dcc7  cmp     [rcx+29h], r14b
0x14003dccb  jb      short loc_14003DCEC
0x14003dccd  mov     rcx, [rcx+18h]
0x14003dcd1  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dcd8  mov     edx, 1Fh
0x14003dcdd  mov     dword ptr [rsp+1E0h+var_1C0], r15d
0x14003dce2  call    WPP_SF_dd
0x14003dce7  mov     r9, [rsp+1E0h+var_188]
0x14003dcec  mov     rdi, [rsp+1E0h+var_190]
0x14003dcf1  test    rdi, rdi
0x14003dcf4  jz      short loc_14003DD1B
0x14003dcf6  mov     edx, r9d
0x14003dcf9  mov     rcx, rdi
0x14003dcfc  call    WimFSFGetChunkOffset
0x14003dd01  mov     edx, r15d
0x14003dd04  mov     [rsp+1E0h+var_180], rax
0x14003dd09  mov     rcx, rdi
0x14003dd0c  mov     rbx, rax
0x14003dd0f  call    WimFSFGetChunkOffset
0x14003dd14  mov     rcx, rax
0x14003dd17  sub     ecx, ebx
0x14003dd19  jmp     short loc_14003DD27
0x14003dd1b  mov     rbx, [rsi+30h]
0x14003dd1f  mov     ecx, [rsi+20h]
0x14003dd22  mov     [rsp+1E0h+var_180], rbx
0x14003dd27  test    dword ptr [r13+60h], 40000h
0x14003dd2f  lea     edi, [rcx+4]
0x14003dd32  cmovz   edi, ecx
0x14003dd35  cmp     byte ptr [rsp+1E0h+var_1A0], 0
0x14003dd3a  jz      short loc_14003DD88
0x14003dd3c  mov     r9d, [r13+5Ch]
0x14003dd40  lea     rax, [rsp+1E0h+NumberOfBytes+4]
0x14003dd45  mov     qword ptr [rsp+1E0h+var_1B0], rax
0x14003dd4a  lea     rdx, [rsp+1E0h+var_180]
0x14003dd4f  lea     rax, [rsp+1E0h+NumberOfBytes]
0x14003dd54  mov     r8d, edi
0x14003dd57  mov     [rsp+1E0h+var_1B8], rax
0x14003dd5c  mov     rcx, r13
0x14003dd5f  lea     rax, [rsp+1E0h+var_178]
0x14003dd64  mov     [rsp+1E0h+var_1C0], rax
0x14003dd69  call    WimFSFGetAlignedSizesForIntegrity
0x14003dd6e  mov     rbx, qword ptr [rsp+1E0h+var_178]
0x14003dd73  mov     dl, al
0x14003dd75  mov     eax, dword ptr [rsp+1E0h+NumberOfBytes+4]
0x14003dd79  mov     edi, dword ptr [rsp+1E0h+NumberOfBytes]
0x14003dd7d  mov     [rsp+1E0h+var_19C], eax
0x14003dd81  mov     byte ptr [rsp+1E0h+var_1A0+2], 1
0x14003dd86  jmp     short loc_14003DD8F
0x14003dd88  mov     byte ptr [rsp+1E0h+var_1A0+2], 0
0x14003dd8d  mov     dl, 1
0x14003dd8f  mov     byte ptr [rsp+1E0h+var_1A0+1], dl
0x14003dd93  mov     rcx, cs:WPP_GLOBAL_Control
0x14003dd9a  mov     eax, [rcx+2Ch]
0x14003dd9d  test    al, 20h
0x14003dd9f  jz      short loc_14003DDD0
0x14003dda1  cmp     [rcx+29h], r14b
0x14003dda5  jb      short loc_14003DDD0
0x14003dda7  mov     rcx, [rcx+18h]
0x14003ddab  lea     rax, aIsNot; "IS NOT"
0x14003ddb2  test    dl, dl
0x14003ddb4  lea     r9, aIs; "IS"
0x14003ddbb  mov     edx, 20h ; ' '
0x14003ddc0  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003ddc7  cmovz   r9, rax
0x14003ddcb  call    WPP_SF_s
0x14003ddd0  mov     rcx, cs:WPP_GLOBAL_Control
0x14003ddd7  mov     eax, [rcx+2Ch]
0x14003ddda  test    al, 20h
0x14003dddc  jz      short loc_14003DE07
0x14003ddde  cmp     [rcx+29h], r14b
0x14003dde2  jb      short loc_14003DE07
0x14003dde4  mov     eax, [r13+1C0h]
0x14003ddeb  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003ddf2  mov     rcx, [rcx+18h]
0x14003ddf6  mov     edx, 21h ; '!'
0x14003ddfb  mov     r9d, edi
0x14003ddfe  mov     dword ptr [rsp+1E0h+var_1C0], eax
0x14003de02  call    WPP_SF_dd
0x14003de07  cmp     edi, [r13+1C0h]
0x14003de0e  jbe     short loc_14003DE6C
0x14003de10  mov     edx, edi; NumberOfBytes
0x14003de12  mov     ecx, 1; PoolType
0x14003de17  mov     r8d, 44527077h; Tag
0x14003de1d  call    cs:__imp_ExAllocatePoolWithTag
0x14003de24  nop     dword ptr [rax+rax+00h]
0x14003de29  mov     r15, rax
0x14003de2c  test    rax, rax
0x14003de2f  jnz     short loc_14003DE3B
0x14003de31  mov     edi, 0C000009Ah
0x14003de36  jmp     loc_14003DF75
0x14003de3b  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de42  xor     r12d, r12d
0x14003de45  mov     eax, [rcx+2Ch]
0x14003de48  test    al, 20h
0x14003de4a  jz      short loc_14003DEB3
0x14003de4c  cmp     [rcx+29h], r14b
0x14003de50  jb      short loc_14003DEB3
0x14003de52  mov     rcx, [rcx+18h]
0x14003de56  lea     edx, [r12+22h]
0x14003de5b  mov     r9d, edi
0x14003de5e  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003de65  call    WPP_SF_d
0x14003de6a  jmp     short loc_14003DEB3
0x14003de6c  lea     rcx, [r13+200h]; Lookaside
0x14003de73  call    cs:__imp_ExAllocateFromPagedLookasideList
0x14003de7a  nop     dword ptr [rax+rax+00h]
0x14003de7f  mov     r12, rax
0x14003de82  test    rax, rax
0x14003de85  jz      short loc_14003DE31
0x14003de87  mov     r15, rax
0x14003de8a  mov     rcx, cs:WPP_GLOBAL_Control
0x14003de91  mov     eax, [rcx+2Ch]
0x14003de94  test    al, 20h
0x14003de96  jz      short loc_14003DEB3
0x14003de98  cmp     [rcx+29h], r14b
0x14003de9c  jb      short loc_14003DEB3
0x14003de9e  mov     rcx, [rcx+18h]
0x14003dea2  lea     r8, WPP_3158cc7d99213f3216ee7f88e8d8f42f_Traceguids
0x14003dea9  mov     edx, 23h ; '#'
  ... truncated ...
```
