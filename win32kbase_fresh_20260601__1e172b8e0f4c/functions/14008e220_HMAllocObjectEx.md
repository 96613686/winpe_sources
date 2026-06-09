# HMAllocObjectEx

- ea: `0x14008e220`
- end: `0x14008e7e1`
- name: `HMAllocObjectEx`
- size: `1473`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14008d3cc`
- `0x14008e200`
- `0x1401111ec`
- `0x140140e6c`
- `0x1401bc1b0`

## callees

- `0x140029fe8`
- `0x1400411c0`
- `0x140043810`
- `0x14008de48`
- `0x14008deb0`
- `0x14008e220`
- `0x14008e7e8`
- `0x14008e854`
- `0x14008e8d0`
- `0x14008e9c0`
- `0x14008ec0c`
- `0x1400dfafc`
- `0x140144250`
- `0x14017bb90`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14008e4be`
- `ntoskrnl!PsGetProcessId` at `0x14008e614`
- `ntoskrnl!PsGetProcessId` at `0x14008e4be`
- `ntoskrnl!PsGetProcessId` at `0x14008e614`
- `ntoskrnl!PsGetThreadId` at `0x14008e417`
- `ntoskrnl!PsGetThreadId` at `0x14008e417`
- `WIN32K!W32GetUserSessionState` at `0x14008e252`
- `WIN32K!W32GetUserSessionState` at `0x14008e2c3`
- `WIN32K!W32GetUserSessionState` at `0x14008e34a`
- `WIN32K!W32GetUserSessionState` at `0x14008e364`
- `WIN32K!W32GetUserSessionState` at `0x14008e387`
- `WIN32K!W32GetUserSessionState` at `0x14008e45f`
- `WIN32K!W32GetUserSessionState` at `0x14008e471`
- `WIN32K!W32GetUserSessionState` at `0x14008e483`
- `WIN32K!W32GetUserSessionState` at `0x14008e6c6`
- `WIN32K!W32GetUserSessionState` at `0x14008e6e2`
- `WIN32K!W32GetUserSessionState` at `0x14008e6f4`
- `WIN32K!W32GetUserSessionState` at `0x14008e76d`
- `WIN32K!W32GetUserSessionState` at `0x14008e252`
- `WIN32K!W32GetUserSessionState` at `0x14008e2c3`
- `WIN32K!W32GetUserSessionState` at `0x14008e34a`
- `WIN32K!W32GetUserSessionState` at `0x14008e364`
- `WIN32K!W32GetUserSessionState` at `0x14008e387`
- `WIN32K!W32GetUserSessionState` at `0x14008e45f`
- `WIN32K!W32GetUserSessionState` at `0x14008e471`
- `WIN32K!W32GetUserSessionState` at `0x14008e483`
- `WIN32K!W32GetUserSessionState` at `0x14008e6c6`
- `WIN32K!W32GetUserSessionState` at `0x14008e6e2`
- `WIN32K!W32GetUserSessionState` at `0x14008e6f4`
- `WIN32K!W32GetUserSessionState` at `0x14008e76d`

## pseudocode

```c
__int64 __fastcall HMAllocObjectEx(__int64 a1, __int64 a2, __int64 a3, unsigned int a4, int a5)
{
  __int64 v5; // r12
  __int64 v7; // rbx
  __int64 v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  unsigned __int16 v13; // bp
  __int64 v14; // rdx
  __int64 UserSessionState; // rdi
  __int64 v16; // r8
  __int64 v17; // rcx
  __int64 *v18; // r15
  __int16 v19; // r14
  __int64 *v20; // rdi
  __int64 v21; // rbx
  __int64 v22; // rsi
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // rax
  _QWORD *v27; // rcx
  __int64 v28; // r12
  __int64 v29; // rdx
  __int64 v30; // r8
  __int64 v31; // rdx
  __int64 v32; // r8
  __int64 v33; // rax
  __int64 v34; // r8
  _QWORD *v35; // rcx
  __int64 v36; // rax
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  unsigned int v40; // ebx
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 v43; // r8
  __int64 v44; // rdx
  __int64 v45; // rcx
  __int64 v46; // r8
  unsigned int EtwUserHandleType; // ebx
  unsigned __int64 v48; // rax
  __int64 result; // rax
  __int64 v50; // rcx
  __int64 v51; // rax
  __int64 v52; // rdx
  __int64 v53; // rcx
  unsigned int v54; // eax
  int v55; // eax
  int v56; // ebx
  __int64 v57; // rdx
  __int64 v58; // rcx
  __int64 v59; // r8
  __int64 v60; // rax
  __int64 v61; // rdx
  __int64 v62; // rcx
  __int64 v63; // r8
  void *v64; // rax
  int v65; // [rsp+20h] [rbp-68h]
  __int64 v66; // [rsp+30h] [rbp-58h]
  __int64 v67; // [rsp+38h] [rbp-50h]
  _QWORD *v68; // [rsp+40h] [rbp-48h] BYREF
  char v71; // [rsp+A0h] [rbp+18h]

  v71 = a3;
  v5 = a4;
  v7 = (unsigned __int8)a3;
  v9 = 0;
  v68 = *(_QWORD **)(W32GetUserSessionState(a1, a2, a3) + 42160);
  LockRefactorStagingAssertOwned((const struct tagDomLock *)&v68);
  v13 = *((_WORD *)&gahti + 12 * v7 + 6);
  v67 = 3 * v7;
  if ( (v13 & 3) != 0 )
  {
    v11 = 0;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 1) != 0 )
      return 0;
    v9 = *(_QWORD *)(a1 + 456);
    if ( *(_DWORD *)(v9 + 68) >= gUserProcessHandleQuota )
      goto LABEL_57;
  }
  UserSessionState = W32GetUserSessionState(v11, v10, v12);
  v17 = 0;
  while ( 1 )
  {
    if ( (_BYTE)v7 != 1 )
    {
      v18 = (__int64 *)(UserSessionState + 19536);
      v68 = (_QWORD *)(UserSessionState + 19536);
      if ( *(_QWORD *)(UserSessionState + 19536) )
        break;
    }
    v18 = (__int64 *)(UserSessionState + 19528);
    v68 = (_QWORD *)(UserSessionState + 19528);
    if ( *(_QWORD *)(UserSessionState + 19528) )
      break;
    v55 = HMGrowHandleTable();
    v17 = 0;
    if ( !v55 )
      goto LABEL_57;
  }
  if ( !v18 )
  {
LABEL_57:
    v50 = 1158;
    goto LABEL_35;
  }
  v65 = 0;
  if ( (v13 & 0x10) != 0 && a2 )
  {
    LOBYTE(v16) = v7;
    v20 = (__int64 *)HMAllocateUserOrIsolatedType(v5, v13, v16);
    if ( v20 )
    {
      v51 = DesktopAlloc(a2, *((unsigned int *)&gahti + 6 * v7 + 4), ((_DWORD)v7 << 16) | 5u);
      v20[5] = v51;
      if ( v51 )
      {
        LockObjectAssignment(v20 + 3, a2);
        v53 = v20[5];
        v20[4] = (__int64)v20;
        v17 = v53 - *(_QWORD *)(a2 + 136);
        v20[6] = v17;
      }
      else
      {
        LOBYTE(v52) = v7;
        HMFreeUserOrIsolatedType(v13, v52, v20);
        v20 = 0;
      }
    }
    v19 = v13 & 0x40;
  }
  else
  {
    v19 = v13 & 0x40;
    if ( (v13 & 0x40) != 0 )
    {
      v20 = 0;
      if ( *((_DWORD *)&gahti + 6 * v7 + 4) )
      {
        LOBYTE(v16) = v7;
        v20 = (__int64 *)HMAllocateUserOrIsolatedType(v5, v13, v16);
        if ( v20 )
        {
          v60 = SharedAlloc(*((unsigned int *)&gahti + 6 * v7 + 4));
          v20[5] = v60;
          if ( v60 )
          {
            v20[3] = 0;
            v20[4] = 0;
            v17 = *(_QWORD *)(W32GetUserSessionState(v62, v61, v63) + 19696);
            v20[6] = v20[5] - v17;
          }
          else
          {
            GreDeleteFastMutex(v20);
            v20 = 0;
          }
        }
      }
    }
    else
    {
      if ( a2 || (v65 = 1, (v13 & 0x20) == 0) )
        v65 = 0;
      LOBYTE(v16) = v7;
      v20 = (__int64 *)HMAllocateUserOrIsolatedType(v5, v13, v16);
      if ( !v20 )
        goto LABEL_34;
      if ( (_BYTE)v7 == 1 )
      {
        v64 = Win32AllocPoolWithQuotaZInitImpl(
                (unsigned __int64)&gahti,
                *((unsigned int *)&gahti + 6 * v7 + 4),
                *((_DWORD *)&gahti + 6 * v7 + 2));
        v20[5] = (__int64)v64;
        if ( !v64 )
        {
          LOBYTE(v14) = 1;
          HMFreeUserOrIsolatedType(v13, v14, v20);
          v20 = 0;
        }
      }
      if ( (v13 & 0x100) != 0 )
      {
        LockObjectAssignment(v20 + 3, a2);
        v20[4] = (__int64)v20;
      }
      v19 = 0;
    }
  }
  if ( !v20 )
  {
LABEL_34:
    v50 = 8;
LABEL_35:
    UserSetLastError(v50);
    return 0;
  }
  v66 = *v18;
  v21 = 32 * *v18;
  v22 = *(_QWORD *)(W32GetUserSessionState(v17, v14, v16) + 19720);
  v26 = W32GetUserSessionState(v24, v23, v25);
  v27 = v68;
  v28 = *(_QWORD *)(v26 + 19664);
  *v68 = *(_QWORD *)(v28 + 40 * v66);
  if ( (unsigned int)v66 > *(_DWORD *)(W32GetUserSessionState(v27, v29, v30) + 19648) )
    *(_DWORD *)(W32GetUserSessionState(v66, v31, v32) + 19648) = v66;
  *(_BYTE *)(v22 + v21 + 24) = v71;
  *(_QWORD *)(v28 + 40 * v66) = v20;
  *(_QWORD *)(v28 + 40 * v66 + 24) = 0;
  *(_QWORD *)(v28 + 40 * v66 + 32) = _InterlockedIncrement64(&HandleSequenceNumber);
  if ( v19 )
  {
    *(_QWORD *)(v22 + v21) = v20[6];
  }
  else if ( (v13 & 0x10) != 0 && a2 )
  {
    *(_QWORD *)(v22 + v21) = v20[6];
    *(_QWORD *)(v22 + v21 + 16) = ***(_QWORD ***)(a2 + 8);
  }
  else
  {
    *(_QWORD *)(v22 + v21) = 0;
  }
  if ( v65 )
    *(_BYTE *)(v22 + v21 + 25) |= 0x40u;
  if ( a5 )
    *(_BYTE *)(v22 + v21 + 25) |= 0x80u;
  if ( (v13 & 2) != 0 )
  {
    v20[2] = 0;
    *(_QWORD *)(v28 + 40 * v66 + 8) = *(_QWORD *)(a1 + 456);
    *(_QWORD *)(v22 + v21 + 8) = PsGetProcessId(**(PEPROCESS **)(a1 + 456));
    if ( (v13 & 4) != 0 )
      v20[3] = *(_QWORD *)(a1 + 456);
  }
  else if ( (v13 & 1) != 0 )
  {
    *(_QWORD *)(v28 + 40 * v66 + 8) = a1;
    *(_QWORD *)(v22 + v21 + 8) = PsGetThreadId(*(PETHREAD *)a1);
    v20[2] = *(_QWORD *)(v28 + 40 * v66 + 8);
  }
  v33 = HMHandleFromIndex(v66);
  v35 = (_QWORD *)v67;
  *v20 = v33;
  if ( *((_DWORD *)&gahti + 2 * v67 + 4) )
  {
    v35 = (_QWORD *)v20[5];
    *v35 = v33;
    v35[1] = v20[6];
  }
  if ( v9 )
  {
    v54 = ++*(_DWORD *)(v9 + 68);
    if ( v54 > *(_DWORD *)(v9 + 72) )
      *(_DWORD *)(v9 + 72) = v54;
  }
  v36 = W32GetUserSessionState(v35, &gahti, v34);
  ++*(_DWORD *)(v36 + 19652);
  v40 = *(_DWORD *)(W32GetUserSessionState(v38, v37, v39) + 19652);
  if ( v40 > *(_DWORD *)(W32GetUserSessionState(v42, v41, v43) + 19656) )
  {
    v56 = *(_DWORD *)(W32GetUserSessionState(v45, v44, v46) + 19652);
    *(_DWORD *)(W32GetUserSessionState(v58, v57, v59) + 19656) = v56;
  }
  LOBYTE(v45) = v71;
  EtwUserHandleType = GetEtwUserHandleType(v45);
  if ( (v13 & 3) != 0 )
    v48 = (unsigned __int64)PsGetProcessId(**(PEPROCESS **)(a1 + 456)) & 0xFFFFFFFC;
  else
    LODWORD(v48) = 0;
  EtwTraceUserCreateHandle(*v20, EtwUserHandleType, (unsigned int)v48);
  result = *(_QWORD *)(v28 + 40 * v66);
  *(_QWORD *)(v28 + 40 * v66 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x14008e220  mov     rax, rsp
0x14008e223  mov     [rax+20h], rbx
0x14008e227  mov     [rax+18h], r8b
0x14008e22b  mov     [rax+10h], rdx
0x14008e22f  mov     [rax+8], rcx
0x14008e233  push    rbp
0x14008e234  push    rsi
0x14008e235  push    rdi
0x14008e236  push    r12
0x14008e238  push    r13
0x14008e23a  push    r14
0x14008e23c  push    r15
0x14008e23e  sub     rsp, 50h
0x14008e242  mov     r12d, r9d
0x14008e245  mov     rsi, rdx
0x14008e248  movzx   ebx, r8b
0x14008e24c  mov     rdi, rcx
0x14008e24f  xor     r13d, r13d
0x14008e252  call    cs:__imp_W32GetUserSessionState
0x14008e259  nop     dword ptr [rax+rax+00h]
0x14008e25e  lea     rcx, [rsp+88h+var_48]; struct tagDomLock *
0x14008e263  mov     r10, [rax+0A4B0h]
0x14008e26a  mov     [rsp+88h+var_48], r10
0x14008e26f  call    ?LockRefactorStagingAssertOwned@@YAXAEBUtagDomLock@@@Z; LockRefactorStagingAssertOwned(tagDomLock const &)
0x14008e274  lea     rax, gahti
0x14008e27b  lea     r14, [rbx+rbx*2]
0x14008e27f  movzx   ebp, word ptr [rax+r14*8+0Ch]
0x14008e285  movzx   eax, bp
0x14008e288  mov     [rsp+88h+var_50], r14
0x14008e28d  and     ax, 3
0x14008e291  mov     [rsp+88h+var_60], ax
0x14008e296  jz      short loc_14008E2C3
0x14008e298  xor     ecx, ecx
0x14008e29a  xor     eax, eax
0x14008e29c  lock cmpxchg [rdi+208h], ecx
0x14008e2a4  test    al, 1
0x14008e2a6  jnz     loc_14008E52F
0x14008e2ac  mov     r13, [rdi+1C8h]
0x14008e2b3  mov     eax, cs:?gUserProcessHandleQuota@@3JA; long gUserProcessHandleQuota
0x14008e2b9  cmp     [r13+44h], eax
0x14008e2bd  jge     loc_14008E68C
0x14008e2c3  call    cs:__imp_W32GetUserSessionState
0x14008e2ca  nop     dword ptr [rax+rax+00h]
0x14008e2cf  mov     rdi, rax
0x14008e2d2  xor     ecx, ecx
0x14008e2d4  cmp     bl, 1
0x14008e2d7  jz      loc_14008E668
0x14008e2dd  lea     r15, [rdi+4C50h]
0x14008e2e4  mov     [rsp+88h+var_48], r15
0x14008e2e9  cmp     [r15], rcx
0x14008e2ec  jz      loc_14008E668
0x14008e2f2  test    r15, r15
0x14008e2f5  jz      loc_14008E68C
0x14008e2fb  movzx   eax, bp
0x14008e2fe  mov     [rsp+88h+var_68], ecx
0x14008e302  and     ax, 10h
0x14008e306  mov     [rsp+88h+var_64], ax
0x14008e30b  jnz     loc_14008E557
0x14008e311  movzx   r14d, bp
0x14008e315  and     r14w, 40h
0x14008e31a  jz      loc_14008E4FC
0x14008e320  mov     rsi, [rsp+88h+var_50]
0x14008e325  lea     rax, gahti
0x14008e32c  mov     rdi, rcx
0x14008e32f  cmp     [rax+rsi*8+10h], ecx
0x14008e333  jnz     loc_14008E721
0x14008e339  test    rdi, rdi
0x14008e33c  jz      loc_14008E525
0x14008e342  mov     r15, [r15]
0x14008e345  mov     [rsp+88h+var_58], r15
0x14008e34a  call    cs:__imp_W32GetUserSessionState
0x14008e351  nop     dword ptr [rax+rax+00h]
0x14008e356  mov     rbx, r15
0x14008e359  shl     rbx, 5
0x14008e35d  mov     rsi, [rax+4D08h]
0x14008e364  call    cs:__imp_W32GetUserSessionState
0x14008e36b  nop     dword ptr [rax+rax+00h]
0x14008e370  mov     rcx, [rsp+88h+var_48]
0x14008e375  lea     r15, [r15+r15*4]
0x14008e379  mov     r12, [rax+4CD0h]
0x14008e380  mov     rax, [r12+r15*8]
0x14008e384  mov     [rcx], rax
0x14008e387  call    cs:__imp_W32GetUserSessionState
0x14008e38e  nop     dword ptr [rax+rax+00h]
0x14008e393  mov     rcx, [rsp+88h+var_58]
0x14008e398  cmp     ecx, [rax+4CC0h]
0x14008e39e  ja      loc_14008E6C6
0x14008e3a4  mov     al, [rsp+88h+arg_10]
0x14008e3ab  xor     edx, edx
0x14008e3ad  mov     [rsi+rbx+18h], al
0x14008e3b1  mov     [r12+r15*8], rdi
0x14008e3b5  mov     [r12+r15*8+18h], rdx
0x14008e3ba  lea     eax, [rdx+1]
0x14008e3bd  lock xadd cs:?HandleSequenceNumber@@3_JC, rax; __int64 volatile HandleSequenceNumber
0x14008e3c6  inc     rax
0x14008e3c9  mov     [r12+r15*8+20h], rax
0x14008e3ce  test    r14w, r14w
0x14008e3d2  jz      loc_14008E5EA
0x14008e3d8  mov     rax, [rdi+30h]
0x14008e3dc  mov     [rsi+rbx], rax
0x14008e3e0  cmp     [rsp+88h+var_68], edx
0x14008e3e4  jnz     loc_14008E7CD
0x14008e3ea  cmp     [rsp+88h+arg_20], edx
0x14008e3f1  jnz     loc_14008E7D7
0x14008e3f7  mov     r14, [rsp+88h+arg_0]
0x14008e3ff  test    bpl, 2
0x14008e403  jnz     loc_14008E5FA
0x14008e409  test    bpl, 1
0x14008e40d  jz      short loc_14008E431
0x14008e40f  mov     [r12+r15*8+8], r14
0x14008e414  mov     rcx, [r14]; Thread
0x14008e417  call    cs:__imp_PsGetThreadId
0x14008e41e  nop     dword ptr [rax+rax+00h]
0x14008e423  mov     [rsi+rbx+8], rax
0x14008e428  mov     rax, [r12+r15*8+8]
0x14008e42d  mov     [rdi+10h], rax
0x14008e431  mov     rcx, [rsp+88h+var_58]
0x14008e436  call    HMHandleFromIndex
0x14008e43b  mov     rcx, [rsp+88h+var_50]
0x14008e440  lea     rdx, gahti
0x14008e447  xor     esi, esi
0x14008e449  mov     [rdi], rax
0x14008e44c  cmp     [rdx+rcx*8+10h], esi
0x14008e450  jnz     loc_14008E6B2
0x14008e456  test    r13, r13
0x14008e459  jnz     loc_14008E5CF
0x14008e45f  call    cs:__imp_W32GetUserSessionState
0x14008e466  nop     dword ptr [rax+rax+00h]
0x14008e46b  inc     dword ptr [rax+4CC4h]
0x14008e471  call    cs:__imp_W32GetUserSessionState
0x14008e478  nop     dword ptr [rax+rax+00h]
0x14008e47d  mov     ebx, [rax+4CC4h]
0x14008e483  call    cs:__imp_W32GetUserSessionState
0x14008e48a  nop     dword ptr [rax+rax+00h]
0x14008e48f  cmp     ebx, [rax+4CC8h]
0x14008e495  ja      loc_14008E6E2
0x14008e49b  mov     cl, [rsp+88h+arg_10]
0x14008e4a2  call    ?GetEtwUserHandleType@@YA?AW4EtwUserHandleType@@E@Z; GetEtwUserHandleType(uchar)
0x14008e4a7  mov     ebx, eax
0x14008e4a9  cmp     [rsp+88h+var_60], si
0x14008e4ae  jz      loc_14008E6AB
0x14008e4b4  mov     rcx, [r14+1C8h]
0x14008e4bb  mov     rcx, [rcx]; Process
0x14008e4be  call    cs:__imp_PsGetProcessId
0x14008e4c5  nop     dword ptr [rax+rax+00h]
0x14008e4ca  and     eax, 0FFFFFFFCh
0x14008e4cd  mov     rcx, [rdi]
0x14008e4d0  mov     r8d, eax
0x14008e4d3  mov     edx, ebx
0x14008e4d5  call    EtwTraceUserCreateHandle
0x14008e4da  mov     rax, [r12+r15*8]
0x14008e4de  mov     [r12+r15*8+10h], rsi
0x14008e4e3  mov     rbx, [rsp+88h+arg_18]
0x14008e4eb  add     rsp, 50h
0x14008e4ef  pop     r15
0x14008e4f1  pop     r14
0x14008e4f3  pop     r13
0x14008e4f5  pop     r12
0x14008e4f7  pop     rdi
0x14008e4f8  pop     rsi
0x14008e4f9  pop     rbp
0x14008e4fa  retn
0x14008e4fc  test    rsi, rsi
0x14008e4ff  jnz     short loc_14008E533
0x14008e501  mov     [rsp+88h+var_68], 1
0x14008e509  test    bpl, 20h
0x14008e50d  jz      short loc_14008E533
0x14008e50f  mov     rcx, r12
0x14008e512  mov     r8b, bl
0x14008e515  movzx   edx, bp
0x14008e518  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14008e51d  mov     rdi, rax
0x14008e520  test    rax, rax
0x14008e523  jnz     short loc_14008E539
0x14008e525  mov     ecx, 8
0x14008e52a  call    UserSetLastError
0x14008e52f  xor     eax, eax
0x14008e531  jmp     short loc_14008E4E3
0x14008e533  mov     [rsp+88h+var_68], ecx
0x14008e537  jmp     short loc_14008E50F
0x14008e539  cmp     bl, 1
0x14008e53c  jz      loc_14008E790
0x14008e542  xor     ebx, ebx
0x14008e544  bt      bp, 8
0x14008e549  jb      loc_14008E696
0x14008e54f  mov     r14d, ebx
0x14008e552  jmp     loc_14008E339
0x14008e557  test    rsi, rsi
0x14008e55a  jz      loc_14008E311
0x14008e560  mov     rcx, r12
0x14008e563  mov     r8b, bl
0x14008e566  movzx   edx, bp
0x14008e569  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14008e56e  mov     rdi, rax
0x14008e571  test    rax, rax
0x14008e574  jz      short loc_14008E5C1
0x14008e576  mov     r8d, ebx
0x14008e579  lea     rax, gahti
0x14008e580  mov     edx, [rax+r14*8+10h]
0x14008e585  mov     rcx, rsi
0x14008e588  shl     r8d, 10h
0x14008e58c  or      r8d, 5
0x14008e590  call    DesktopAlloc
0x14008e595  mov     [rdi+28h], rax
0x14008e599  test    rax, rax
0x14008e59c  jz      loc_14008E70B
0x14008e5a2  lea     rcx, [rdi+18h]
0x14008e5a6  mov     rdx, rsi
0x14008e5a9  call    LockObjectAssignment
0x14008e5ae  mov     rcx, [rdi+28h]
0x14008e5b2  mov     [rdi+20h], rdi
0x14008e5b6  sub     rcx, [rsi+88h]
0x14008e5bd  mov     [rdi+30h], rcx
0x14008e5c1  movzx   r14d, bp
0x14008e5c5  and     r14w, 40h
0x14008e5ca  jmp     loc_14008E339
0x14008e5cf  inc     dword ptr [r13+44h]
0x14008e5d3  mov     eax, [r13+44h]
0x14008e5d7  cmp     eax, [r13+48h]
0x14008e5db  jbe     loc_14008E45F
0x14008e5e1  mov     [r13+48h], eax
0x14008e5e5  jmp     loc_14008E45F
0x14008e5ea  cmp     [rsp+88h+var_64], dx
0x14008e5ef  jnz     short loc_14008E63F
0x14008e5f1  mov     [rsi+rbx], rdx
0x14008e5f5  jmp     loc_14008E3E0
0x14008e5fa  mov     [rdi+10h], rdx
0x14008e5fe  mov     rax, [r14+1C8h]
0x14008e605  mov     [r12+r15*8+8], rax
0x14008e60a  mov     rcx, [r14+1C8h]
0x14008e611  mov     rcx, [rcx]; Process
0x14008e614  call    cs:__imp_PsGetProcessId
0x14008e61b  nop     dword ptr [rax+rax+00h]
0x14008e620  mov     [rsi+rbx+8], rax
0x14008e625  test    bpl, 4
0x14008e629  jz      loc_14008E431
0x14008e62f  mov     rax, [r14+1C8h]
0x14008e636  mov     [rdi+18h], rax
0x14008e63a  jmp     loc_14008E431
0x14008e63f  mov     rcx, [rsp+88h+arg_8]
0x14008e647  test    rcx, rcx
0x14008e64a  jz      short loc_14008E5F1
0x14008e64c  mov     rax, [rdi+30h]
0x14008e650  mov     [rsi+rbx], rax
0x14008e654  mov     rax, [rcx+8]
0x14008e658  mov     rcx, [rax]
0x14008e65b  mov     rax, [rcx]
0x14008e65e  mov     [rsi+rbx+10h], rax
0x14008e663  jmp     loc_14008E3E0
0x14008e668  lea     r15, [rdi+4C48h]
0x14008e66f  mov     [rsp+88h+var_48], r15
0x14008e674  cmp     [r15], rcx
0x14008e677  jnz     loc_14008E2F2
0x14008e67d  call    ?HMGrowHandleTable@@YAHXZ; HMGrowHandleTable(void)
0x14008e682  xor     ecx, ecx
0x14008e684  test    eax, eax
0x14008e686  jnz     loc_14008E2D4
0x14008e68c  mov     ecx, 486h
0x14008e691  jmp     loc_14008E52A
0x14008e696  lea     rcx, [rdi+18h]
0x14008e69a  mov     rdx, rsi
0x14008e69d  call    LockObjectAssignment
0x14008e6a2  mov     [rdi+20h], rdi
0x14008e6a6  jmp     loc_14008E54F
0x14008e6ab  mov     eax, esi
0x14008e6ad  jmp     loc_14008E4CD
0x14008e6b2  mov     rcx, [rdi+28h]
0x14008e6b6  mov     [rcx], rax
0x14008e6b9  mov     rax, [rdi+30h]
0x14008e6bd  mov     [rcx+8], rax
0x14008e6c1  jmp     loc_14008E456
0x14008e6c6  call    cs:__imp_W32GetUserSessionState
0x14008e6cd  nop     dword ptr [rax+rax+00h]
0x14008e6d2  mov     rcx, [rsp+88h+var_58]
0x14008e6d7  mov     [rax+4CC0h], ecx
0x14008e6dd  jmp     loc_14008E3A4
0x14008e6e2  call    cs:__imp_W32GetUserSessionState
0x14008e6e9  nop     dword ptr [rax+rax+00h]
0x14008e6ee  mov     ebx, [rax+4CC4h]
0x14008e6f4  call    cs:__imp_W32GetUserSessionState
0x14008e6fb  nop     dword ptr [rax+rax+00h]
0x14008e700  mov     [rax+4CC8h], ebx
0x14008e706  jmp     loc_14008E49B
0x14008e70b  mov     r8, rdi
0x14008e70e  mov     dl, bl
0x14008e710  movzx   ecx, bp
0x14008e713  call    ?HMFreeUserOrIsolatedType@@YAXW4HM_OBJ_CREATE_FLAGS@@EPEAX@Z; HMFreeUserOrIsolatedType(HM_OBJ_CREATE_FLAGS,uchar,void *)
0x14008e718  xor     ebx, ebx
0x14008e71a  mov     edi, ebx
0x14008e71c  jmp     loc_14008E5C1
0x14008e721  mov     rcx, r12
0x14008e724  mov     r8b, bl
0x14008e727  movzx   edx, bp
0x14008e72a  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14008e72f  xor     ebx, ebx
0x14008e731  mov     rdi, rax
0x14008e734  test    rax, rax
0x14008e737  jz      loc_14008E339
0x14008e73d  lea     rax, gahti
0x14008e744  mov     ecx, [rax+rsi*8+10h]; Size
  ... truncated ...
```
