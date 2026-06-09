# HMAllocObjectEx

- ea: `0x140009dd0`
- end: `0x14000a391`
- name: `HMAllocObjectEx`
- size: `1473`
- prototype: ``
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008f7c`
- `0x140009db0`
- `0x140107d7c`
- `0x14014144c`
- `0x1401bbc50`

## callees

- `0x1400099f8`
- `0x140009a60`
- `0x140009dd0`
- `0x14000a398`
- `0x14000a404`
- `0x14000a480`
- `0x14000a570`
- `0x14000a7bc`
- `0x140033268`
- `0x14004a0d0`
- `0x14004c720`
- `0x1400d5e8c`
- `0x140144830`
- `0x14017c6f0`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x14000a06e`
- `ntoskrnl!PsGetProcessId` at `0x14000a1c4`
- `ntoskrnl!PsGetProcessId` at `0x14000a06e`
- `ntoskrnl!PsGetProcessId` at `0x14000a1c4`
- `ntoskrnl!PsGetThreadId` at `0x140009fc7`
- `ntoskrnl!PsGetThreadId` at `0x140009fc7`
- `WIN32K!W32GetUserSessionState` at `0x140009e02`
- `WIN32K!W32GetUserSessionState` at `0x140009e73`
- `WIN32K!W32GetUserSessionState` at `0x140009efa`
- `WIN32K!W32GetUserSessionState` at `0x140009f14`
- `WIN32K!W32GetUserSessionState` at `0x140009f37`
- `WIN32K!W32GetUserSessionState` at `0x14000a00f`
- `WIN32K!W32GetUserSessionState` at `0x14000a021`
- `WIN32K!W32GetUserSessionState` at `0x14000a033`
- `WIN32K!W32GetUserSessionState` at `0x14000a276`
- `WIN32K!W32GetUserSessionState` at `0x14000a292`
- `WIN32K!W32GetUserSessionState` at `0x14000a2a4`
- `WIN32K!W32GetUserSessionState` at `0x14000a31d`
- `WIN32K!W32GetUserSessionState` at `0x140009e02`
- `WIN32K!W32GetUserSessionState` at `0x140009e73`
- `WIN32K!W32GetUserSessionState` at `0x140009efa`
- `WIN32K!W32GetUserSessionState` at `0x140009f14`
- `WIN32K!W32GetUserSessionState` at `0x140009f37`
- `WIN32K!W32GetUserSessionState` at `0x14000a00f`
- `WIN32K!W32GetUserSessionState` at `0x14000a021`
- `WIN32K!W32GetUserSessionState` at `0x14000a033`
- `WIN32K!W32GetUserSessionState` at `0x14000a276`
- `WIN32K!W32GetUserSessionState` at `0x14000a292`
- `WIN32K!W32GetUserSessionState` at `0x14000a2a4`
- `WIN32K!W32GetUserSessionState` at `0x14000a31d`

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
0x140009dd0  mov     rax, rsp
0x140009dd3  mov     [rax+20h], rbx
0x140009dd7  mov     [rax+18h], r8b
0x140009ddb  mov     [rax+10h], rdx
0x140009ddf  mov     [rax+8], rcx
0x140009de3  push    rbp
0x140009de4  push    rsi
0x140009de5  push    rdi
0x140009de6  push    r12
0x140009de8  push    r13
0x140009dea  push    r14
0x140009dec  push    r15
0x140009dee  sub     rsp, 50h
0x140009df2  mov     r12d, r9d
0x140009df5  mov     rsi, rdx
0x140009df8  movzx   ebx, r8b
0x140009dfc  mov     rdi, rcx
0x140009dff  xor     r13d, r13d
0x140009e02  call    cs:__imp_W32GetUserSessionState
0x140009e09  nop     dword ptr [rax+rax+00h]
0x140009e0e  lea     rcx, [rsp+88h+var_48]; struct tagDomLock *
0x140009e13  mov     r10, [rax+0A4B0h]
0x140009e1a  mov     [rsp+88h+var_48], r10
0x140009e1f  call    ?LockRefactorStagingAssertOwned@@YAXAEBUtagDomLock@@@Z; LockRefactorStagingAssertOwned(tagDomLock const &)
0x140009e24  lea     rax, gahti
0x140009e2b  lea     r14, [rbx+rbx*2]
0x140009e2f  movzx   ebp, word ptr [rax+r14*8+0Ch]
0x140009e35  movzx   eax, bp
0x140009e38  mov     [rsp+88h+var_50], r14
0x140009e3d  and     ax, 3
0x140009e41  mov     [rsp+88h+var_60], ax
0x140009e46  jz      short loc_140009E73
0x140009e48  xor     ecx, ecx
0x140009e4a  xor     eax, eax
0x140009e4c  lock cmpxchg [rdi+208h], ecx
0x140009e54  test    al, 1
0x140009e56  jnz     loc_14000A0DF
0x140009e5c  mov     r13, [rdi+1C8h]
0x140009e63  mov     eax, cs:?gUserProcessHandleQuota@@3JA; long gUserProcessHandleQuota
0x140009e69  cmp     [r13+44h], eax
0x140009e6d  jge     loc_14000A23C
0x140009e73  call    cs:__imp_W32GetUserSessionState
0x140009e7a  nop     dword ptr [rax+rax+00h]
0x140009e7f  mov     rdi, rax
0x140009e82  xor     ecx, ecx
0x140009e84  cmp     bl, 1
0x140009e87  jz      loc_14000A218
0x140009e8d  lea     r15, [rdi+4C50h]
0x140009e94  mov     [rsp+88h+var_48], r15
0x140009e99  cmp     [r15], rcx
0x140009e9c  jz      loc_14000A218
0x140009ea2  test    r15, r15
0x140009ea5  jz      loc_14000A23C
0x140009eab  movzx   eax, bp
0x140009eae  mov     [rsp+88h+var_68], ecx
0x140009eb2  and     ax, 10h
0x140009eb6  mov     [rsp+88h+var_64], ax
0x140009ebb  jnz     loc_14000A107
0x140009ec1  movzx   r14d, bp
0x140009ec5  and     r14w, 40h
0x140009eca  jz      loc_14000A0AC
0x140009ed0  mov     rsi, [rsp+88h+var_50]
0x140009ed5  lea     rax, gahti
0x140009edc  mov     rdi, rcx
0x140009edf  cmp     [rax+rsi*8+10h], ecx
0x140009ee3  jnz     loc_14000A2D1
0x140009ee9  test    rdi, rdi
0x140009eec  jz      loc_14000A0D5
0x140009ef2  mov     r15, [r15]
0x140009ef5  mov     [rsp+88h+var_58], r15
0x140009efa  call    cs:__imp_W32GetUserSessionState
0x140009f01  nop     dword ptr [rax+rax+00h]
0x140009f06  mov     rbx, r15
0x140009f09  shl     rbx, 5
0x140009f0d  mov     rsi, [rax+4D08h]
0x140009f14  call    cs:__imp_W32GetUserSessionState
0x140009f1b  nop     dword ptr [rax+rax+00h]
0x140009f20  mov     rcx, [rsp+88h+var_48]
0x140009f25  lea     r15, [r15+r15*4]
0x140009f29  mov     r12, [rax+4CD0h]
0x140009f30  mov     rax, [r12+r15*8]
0x140009f34  mov     [rcx], rax
0x140009f37  call    cs:__imp_W32GetUserSessionState
0x140009f3e  nop     dword ptr [rax+rax+00h]
0x140009f43  mov     rcx, [rsp+88h+var_58]
0x140009f48  cmp     ecx, [rax+4CC0h]
0x140009f4e  ja      loc_14000A276
0x140009f54  mov     al, [rsp+88h+arg_10]
0x140009f5b  xor     edx, edx
0x140009f5d  mov     [rsi+rbx+18h], al
0x140009f61  mov     [r12+r15*8], rdi
0x140009f65  mov     [r12+r15*8+18h], rdx
0x140009f6a  lea     eax, [rdx+1]
0x140009f6d  lock xadd cs:?HandleSequenceNumber@@3_JC, rax; __int64 volatile HandleSequenceNumber
0x140009f76  inc     rax
0x140009f79  mov     [r12+r15*8+20h], rax
0x140009f7e  test    r14w, r14w
0x140009f82  jz      loc_14000A19A
0x140009f88  mov     rax, [rdi+30h]
0x140009f8c  mov     [rsi+rbx], rax
0x140009f90  cmp     [rsp+88h+var_68], edx
0x140009f94  jnz     loc_14000A37D
0x140009f9a  cmp     [rsp+88h+arg_20], edx
0x140009fa1  jnz     loc_14000A387
0x140009fa7  mov     r14, [rsp+88h+arg_0]
0x140009faf  test    bpl, 2
0x140009fb3  jnz     loc_14000A1AA
0x140009fb9  test    bpl, 1
0x140009fbd  jz      short loc_140009FE1
0x140009fbf  mov     [r12+r15*8+8], r14
0x140009fc4  mov     rcx, [r14]; Thread
0x140009fc7  call    cs:__imp_PsGetThreadId
0x140009fce  nop     dword ptr [rax+rax+00h]
0x140009fd3  mov     [rsi+rbx+8], rax
0x140009fd8  mov     rax, [r12+r15*8+8]
0x140009fdd  mov     [rdi+10h], rax
0x140009fe1  mov     rcx, [rsp+88h+var_58]
0x140009fe6  call    HMHandleFromIndex
0x140009feb  mov     rcx, [rsp+88h+var_50]
0x140009ff0  lea     rdx, gahti
0x140009ff7  xor     esi, esi
0x140009ff9  mov     [rdi], rax
0x140009ffc  cmp     [rdx+rcx*8+10h], esi
0x14000a000  jnz     loc_14000A262
0x14000a006  test    r13, r13
0x14000a009  jnz     loc_14000A17F
0x14000a00f  call    cs:__imp_W32GetUserSessionState
0x14000a016  nop     dword ptr [rax+rax+00h]
0x14000a01b  inc     dword ptr [rax+4CC4h]
0x14000a021  call    cs:__imp_W32GetUserSessionState
0x14000a028  nop     dword ptr [rax+rax+00h]
0x14000a02d  mov     ebx, [rax+4CC4h]
0x14000a033  call    cs:__imp_W32GetUserSessionState
0x14000a03a  nop     dword ptr [rax+rax+00h]
0x14000a03f  cmp     ebx, [rax+4CC8h]
0x14000a045  ja      loc_14000A292
0x14000a04b  mov     cl, [rsp+88h+arg_10]
0x14000a052  call    ?GetEtwUserHandleType@@YA?AW4EtwUserHandleType@@E@Z; GetEtwUserHandleType(uchar)
0x14000a057  mov     ebx, eax
0x14000a059  cmp     [rsp+88h+var_60], si
0x14000a05e  jz      loc_14000A25B
0x14000a064  mov     rcx, [r14+1C8h]
0x14000a06b  mov     rcx, [rcx]; Process
0x14000a06e  call    cs:__imp_PsGetProcessId
0x14000a075  nop     dword ptr [rax+rax+00h]
0x14000a07a  and     eax, 0FFFFFFFCh
0x14000a07d  mov     rcx, [rdi]
0x14000a080  mov     r8d, eax
0x14000a083  mov     edx, ebx
0x14000a085  call    EtwTraceUserCreateHandle
0x14000a08a  mov     rax, [r12+r15*8]
0x14000a08e  mov     [r12+r15*8+10h], rsi
0x14000a093  mov     rbx, [rsp+88h+arg_18]
0x14000a09b  add     rsp, 50h
0x14000a09f  pop     r15
0x14000a0a1  pop     r14
0x14000a0a3  pop     r13
0x14000a0a5  pop     r12
0x14000a0a7  pop     rdi
0x14000a0a8  pop     rsi
0x14000a0a9  pop     rbp
0x14000a0aa  retn
0x14000a0ac  test    rsi, rsi
0x14000a0af  jnz     short loc_14000A0E3
0x14000a0b1  mov     [rsp+88h+var_68], 1
0x14000a0b9  test    bpl, 20h
0x14000a0bd  jz      short loc_14000A0E3
0x14000a0bf  mov     rcx, r12
0x14000a0c2  mov     r8b, bl
0x14000a0c5  movzx   edx, bp
0x14000a0c8  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14000a0cd  mov     rdi, rax
0x14000a0d0  test    rax, rax
0x14000a0d3  jnz     short loc_14000A0E9
0x14000a0d5  mov     ecx, 8
0x14000a0da  call    UserSetLastError
0x14000a0df  xor     eax, eax
0x14000a0e1  jmp     short loc_14000A093
0x14000a0e3  mov     [rsp+88h+var_68], ecx
0x14000a0e7  jmp     short loc_14000A0BF
0x14000a0e9  cmp     bl, 1
0x14000a0ec  jz      loc_14000A340
0x14000a0f2  xor     ebx, ebx
0x14000a0f4  bt      bp, 8
0x14000a0f9  jb      loc_14000A246
0x14000a0ff  mov     r14d, ebx
0x14000a102  jmp     loc_140009EE9
0x14000a107  test    rsi, rsi
0x14000a10a  jz      loc_140009EC1
0x14000a110  mov     rcx, r12
0x14000a113  mov     r8b, bl
0x14000a116  movzx   edx, bp
0x14000a119  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14000a11e  mov     rdi, rax
0x14000a121  test    rax, rax
0x14000a124  jz      short loc_14000A171
0x14000a126  mov     r8d, ebx
0x14000a129  lea     rax, gahti
0x14000a130  mov     edx, [rax+r14*8+10h]
0x14000a135  mov     rcx, rsi
0x14000a138  shl     r8d, 10h
0x14000a13c  or      r8d, 5
0x14000a140  call    DesktopAlloc
0x14000a145  mov     [rdi+28h], rax
0x14000a149  test    rax, rax
0x14000a14c  jz      loc_14000A2BB
0x14000a152  lea     rcx, [rdi+18h]
0x14000a156  mov     rdx, rsi
0x14000a159  call    LockObjectAssignment
0x14000a15e  mov     rcx, [rdi+28h]
0x14000a162  mov     [rdi+20h], rdi
0x14000a166  sub     rcx, [rsi+88h]
0x14000a16d  mov     [rdi+30h], rcx
0x14000a171  movzx   r14d, bp
0x14000a175  and     r14w, 40h
0x14000a17a  jmp     loc_140009EE9
0x14000a17f  inc     dword ptr [r13+44h]
0x14000a183  mov     eax, [r13+44h]
0x14000a187  cmp     eax, [r13+48h]
0x14000a18b  jbe     loc_14000A00F
0x14000a191  mov     [r13+48h], eax
0x14000a195  jmp     loc_14000A00F
0x14000a19a  cmp     [rsp+88h+var_64], dx
0x14000a19f  jnz     short loc_14000A1EF
0x14000a1a1  mov     [rsi+rbx], rdx
0x14000a1a5  jmp     loc_140009F90
0x14000a1aa  mov     [rdi+10h], rdx
0x14000a1ae  mov     rax, [r14+1C8h]
0x14000a1b5  mov     [r12+r15*8+8], rax
0x14000a1ba  mov     rcx, [r14+1C8h]
0x14000a1c1  mov     rcx, [rcx]; Process
0x14000a1c4  call    cs:__imp_PsGetProcessId
0x14000a1cb  nop     dword ptr [rax+rax+00h]
0x14000a1d0  mov     [rsi+rbx+8], rax
0x14000a1d5  test    bpl, 4
0x14000a1d9  jz      loc_140009FE1
0x14000a1df  mov     rax, [r14+1C8h]
0x14000a1e6  mov     [rdi+18h], rax
0x14000a1ea  jmp     loc_140009FE1
0x14000a1ef  mov     rcx, [rsp+88h+arg_8]
0x14000a1f7  test    rcx, rcx
0x14000a1fa  jz      short loc_14000A1A1
0x14000a1fc  mov     rax, [rdi+30h]
0x14000a200  mov     [rsi+rbx], rax
0x14000a204  mov     rax, [rcx+8]
0x14000a208  mov     rcx, [rax]
0x14000a20b  mov     rax, [rcx]
0x14000a20e  mov     [rsi+rbx+10h], rax
0x14000a213  jmp     loc_140009F90
0x14000a218  lea     r15, [rdi+4C48h]
0x14000a21f  mov     [rsp+88h+var_48], r15
0x14000a224  cmp     [r15], rcx
0x14000a227  jnz     loc_140009EA2
0x14000a22d  call    ?HMGrowHandleTable@@YAHXZ; HMGrowHandleTable(void)
0x14000a232  xor     ecx, ecx
0x14000a234  test    eax, eax
0x14000a236  jnz     loc_140009E84
0x14000a23c  mov     ecx, 486h
0x14000a241  jmp     loc_14000A0DA
0x14000a246  lea     rcx, [rdi+18h]
0x14000a24a  mov     rdx, rsi
0x14000a24d  call    LockObjectAssignment
0x14000a252  mov     [rdi+20h], rdi
0x14000a256  jmp     loc_14000A0FF
0x14000a25b  mov     eax, esi
0x14000a25d  jmp     loc_14000A07D
0x14000a262  mov     rcx, [rdi+28h]
0x14000a266  mov     [rcx], rax
0x14000a269  mov     rax, [rdi+30h]
0x14000a26d  mov     [rcx+8], rax
0x14000a271  jmp     loc_14000A006
0x14000a276  call    cs:__imp_W32GetUserSessionState
0x14000a27d  nop     dword ptr [rax+rax+00h]
0x14000a282  mov     rcx, [rsp+88h+var_58]
0x14000a287  mov     [rax+4CC0h], ecx
0x14000a28d  jmp     loc_140009F54
0x14000a292  call    cs:__imp_W32GetUserSessionState
0x14000a299  nop     dword ptr [rax+rax+00h]
0x14000a29e  mov     ebx, [rax+4CC4h]
0x14000a2a4  call    cs:__imp_W32GetUserSessionState
0x14000a2ab  nop     dword ptr [rax+rax+00h]
0x14000a2b0  mov     [rax+4CC8h], ebx
0x14000a2b6  jmp     loc_14000A04B
0x14000a2bb  mov     r8, rdi
0x14000a2be  mov     dl, bl
0x14000a2c0  movzx   ecx, bp
0x14000a2c3  call    ?HMFreeUserOrIsolatedType@@YAXW4HM_OBJ_CREATE_FLAGS@@EPEAX@Z; HMFreeUserOrIsolatedType(HM_OBJ_CREATE_FLAGS,uchar,void *)
0x14000a2c8  xor     ebx, ebx
0x14000a2ca  mov     edi, ebx
0x14000a2cc  jmp     loc_14000A171
0x14000a2d1  mov     rcx, r12
0x14000a2d4  mov     r8b, bl
0x14000a2d7  movzx   edx, bp
0x14000a2da  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x14000a2df  xor     ebx, ebx
0x14000a2e1  mov     rdi, rax
0x14000a2e4  test    rax, rax
0x14000a2e7  jz      loc_140009EE9
0x14000a2ed  lea     rax, gahti
0x14000a2f4  mov     ecx, [rax+rsi*8+10h]; Size
  ... truncated ...
```
