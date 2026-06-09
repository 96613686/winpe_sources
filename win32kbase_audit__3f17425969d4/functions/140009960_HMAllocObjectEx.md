# HMAllocObjectEx

- ea: `0x140009960`
- end: `0x140009f21`
- name: `HMAllocObjectEx`
- size: `1473`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned __int8, unsigned int, int)`
- caller_count: `5`
- callee_count: `14`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x140008b0c`
- `0x140009940`
- `0x140104b1c`
- `0x140113b8c`
- `0x1401bcd80`

## callees

- `0x140009588`
- `0x1400095f0`
- `0x140009960`
- `0x140009f28`
- `0x140009f94`
- `0x14000a010`
- `0x14000a2dc`
- `0x140035b38`
- `0x1400700d8`
- `0x14007b930`
- `0x14007df80`
- `0x1400c91fc`
- `0x1401463a0`
- `0x14017e300`

## import_xrefs

- `ntoskrnl!PsGetProcessId` at `0x140009bfe`
- `ntoskrnl!PsGetProcessId` at `0x140009d54`
- `ntoskrnl!PsGetProcessId` at `0x140009bfe`
- `ntoskrnl!PsGetProcessId` at `0x140009d54`
- `ntoskrnl!PsGetThreadId` at `0x140009b57`
- `ntoskrnl!PsGetThreadId` at `0x140009b57`
- `WIN32K!W32GetUserSessionState` at `0x140009992`
- `WIN32K!W32GetUserSessionState` at `0x140009a03`
- `WIN32K!W32GetUserSessionState` at `0x140009a8a`
- `WIN32K!W32GetUserSessionState` at `0x140009aa4`
- `WIN32K!W32GetUserSessionState` at `0x140009ac7`
- `WIN32K!W32GetUserSessionState` at `0x140009b9f`
- `WIN32K!W32GetUserSessionState` at `0x140009bb1`
- `WIN32K!W32GetUserSessionState` at `0x140009bc3`
- `WIN32K!W32GetUserSessionState` at `0x140009e06`
- `WIN32K!W32GetUserSessionState` at `0x140009e22`
- `WIN32K!W32GetUserSessionState` at `0x140009e34`
- `WIN32K!W32GetUserSessionState` at `0x140009ead`
- `WIN32K!W32GetUserSessionState` at `0x140009992`
- `WIN32K!W32GetUserSessionState` at `0x140009a03`
- `WIN32K!W32GetUserSessionState` at `0x140009a8a`
- `WIN32K!W32GetUserSessionState` at `0x140009aa4`
- `WIN32K!W32GetUserSessionState` at `0x140009ac7`
- `WIN32K!W32GetUserSessionState` at `0x140009b9f`
- `WIN32K!W32GetUserSessionState` at `0x140009bb1`
- `WIN32K!W32GetUserSessionState` at `0x140009bc3`
- `WIN32K!W32GetUserSessionState` at `0x140009e06`
- `WIN32K!W32GetUserSessionState` at `0x140009e22`
- `WIN32K!W32GetUserSessionState` at `0x140009e34`
- `WIN32K!W32GetUserSessionState` at `0x140009ead`

## pseudocode

```c
__int64 __fastcall HMAllocObjectEx(__int64 a1, __int64 a2, unsigned __int8 a3, unsigned int a4, int a5)
{
  __int64 v5; // r12
  __int64 v7; // rbx
  __int64 v9; // r13
  __int64 v10; // rdx
  __int64 v11; // rcx
  unsigned __int16 v12; // bp
  __int64 v13; // rdx
  __int64 UserSessionState; // rdi
  __int64 v15; // r8
  char *v16; // rcx
  __int64 *v17; // r15
  __int16 v18; // r14
  void **v19; // rdi
  __int64 v20; // rbx
  __int64 v21; // rsi
  __int64 v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rax
  _QWORD *v25; // rcx
  __int64 v26; // r12
  __int64 v27; // rdx
  __int64 v28; // rdx
  __int64 v29; // rax
  _QWORD *v30; // rcx
  __int64 v31; // rax
  __int64 v32; // rdx
  __int64 v33; // rcx
  unsigned int v34; // ebx
  __int64 v35; // rdx
  __int64 v36; // rcx
  __int64 v37; // rdx
  __int64 v38; // rcx
  __int64 v39; // r8
  unsigned int EtwUserHandleType; // ebx
  unsigned int v41; // eax
  __int64 result; // rax
  __int64 v43; // rcx
  __int64 (__fastcall *v44)(__int64, _QWORD, _QWORD); // rax
  __int64 v45; // rdx
  char *v46; // rcx
  unsigned int v47; // eax
  int v48; // eax
  int v49; // ebx
  __int64 v50; // rdx
  __int64 v51; // rcx
  __int64 v52; // rax
  __int64 v53; // rdx
  __int64 v54; // rcx
  void *v55; // rax
  int v56; // [rsp+20h] [rbp-68h]
  __int64 v57; // [rsp+30h] [rbp-58h]
  __int64 v58; // [rsp+38h] [rbp-50h]
  _QWORD *v59; // [rsp+40h] [rbp-48h] BYREF

  v5 = a4;
  v7 = a3;
  v9 = 0;
  v59 = *(_QWORD **)(W32GetUserSessionState(a1, a2) + 42160);
  LockRefactorStagingAssertOwned((const struct tagDomLock *)&v59);
  v12 = *((_WORD *)&gahti + 12 * v7 + 6);
  v58 = 3 * v7;
  if ( (v12 & 3) != 0 )
  {
    v11 = 0;
    if ( (_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 520), 0, 0) & 1) != 0 )
      return 0;
    v9 = *(_QWORD *)(a1 + 456);
    if ( *(_DWORD *)(v9 + 68) >= gUserProcessHandleQuota )
      goto LABEL_57;
  }
  UserSessionState = W32GetUserSessionState(v11, v10);
  v16 = 0;
  while ( 1 )
  {
    if ( (_BYTE)v7 != 1 )
    {
      v17 = (__int64 *)(UserSessionState + 19536);
      v59 = (_QWORD *)(UserSessionState + 19536);
      if ( *(_QWORD *)(UserSessionState + 19536) )
        break;
    }
    v17 = (__int64 *)(UserSessionState + 19528);
    v59 = (_QWORD *)(UserSessionState + 19528);
    if ( *(_QWORD *)(UserSessionState + 19528) )
      break;
    v48 = HMGrowHandleTable();
    v16 = 0;
    if ( !v48 )
      goto LABEL_57;
  }
  if ( !v17 )
  {
LABEL_57:
    v43 = 1158;
    goto LABEL_35;
  }
  v56 = 0;
  if ( (v12 & 0x10) != 0 && a2 )
  {
    LOBYTE(v15) = v7;
    v19 = (void **)HMAllocateUserOrIsolatedType(v5, v12, v15);
    if ( v19 )
    {
      v44 = DesktopAlloc(a2, *((_DWORD *)&gahti + 6 * v7 + 4), ((_DWORD)v7 << 16) | 5u);
      v19[5] = v44;
      if ( v44 )
      {
        LockObjectAssignment(v19 + 3, (void *)a2);
        v46 = (char *)v19[5];
        v19[4] = v19;
        v16 = &v46[-*(_QWORD *)(a2 + 136)];
        v19[6] = v16;
      }
      else
      {
        LOBYTE(v45) = v7;
        HMFreeUserOrIsolatedType(v12, v45, v19);
        v19 = 0;
      }
    }
    v18 = v12 & 0x40;
  }
  else
  {
    v18 = v12 & 0x40;
    if ( (v12 & 0x40) != 0 )
    {
      v19 = 0;
      if ( *((_DWORD *)&gahti + 6 * v7 + 4) )
      {
        LOBYTE(v15) = v7;
        v19 = (void **)HMAllocateUserOrIsolatedType(v5, v12, v15);
        if ( v19 )
        {
          v52 = SharedAlloc(*((unsigned int *)&gahti + 6 * v7 + 4));
          v19[5] = (void *)v52;
          if ( v52 )
          {
            v19[3] = 0;
            v19[4] = 0;
            v16 = *(char **)(W32GetUserSessionState(v54, v53) + 19696);
            v19[6] = (void *)((_BYTE *)v19[5] - v16);
          }
          else
          {
            GreDeleteFastMutex(v19);
            v19 = 0;
          }
        }
      }
    }
    else
    {
      if ( a2 || (v56 = 1, (v12 & 0x20) == 0) )
        v56 = 0;
      LOBYTE(v15) = v7;
      v19 = (void **)HMAllocateUserOrIsolatedType(v5, v12, v15);
      if ( !v19 )
        goto LABEL_34;
      if ( (_BYTE)v7 == 1 )
      {
        v55 = Win32AllocPoolWithQuotaZInitImpl(
                (unsigned __int64)&gahti,
                *((unsigned int *)&gahti + 6 * v7 + 4),
                *((_DWORD *)&gahti + 6 * v7 + 2));
        v19[5] = v55;
        if ( !v55 )
        {
          LOBYTE(v13) = 1;
          HMFreeUserOrIsolatedType(v12, v13, v19);
          v19 = 0;
        }
      }
      if ( (v12 & 0x100) != 0 )
      {
        LockObjectAssignment(v19 + 3, (void *)a2);
        v19[4] = v19;
      }
      v18 = 0;
    }
  }
  if ( !v19 )
  {
LABEL_34:
    v43 = 8;
LABEL_35:
    UserSetLastError(v43);
    return 0;
  }
  v57 = *v17;
  v20 = 32 * *v17;
  v21 = *(_QWORD *)(W32GetUserSessionState(v16, v13) + 19720);
  v24 = W32GetUserSessionState(v23, v22);
  v25 = v59;
  v26 = *(_QWORD *)(v24 + 19664);
  *v59 = *(_QWORD *)(v26 + 40 * v57);
  if ( (unsigned int)v57 > *(_DWORD *)(W32GetUserSessionState(v25, v27) + 19648) )
    *(_DWORD *)(W32GetUserSessionState(v57, v28) + 19648) = v57;
  *(_BYTE *)(v21 + v20 + 24) = a3;
  *(_QWORD *)(v26 + 40 * v57) = v19;
  *(_QWORD *)(v26 + 40 * v57 + 24) = 0;
  *(_QWORD *)(v26 + 40 * v57 + 32) = _InterlockedIncrement64(&HandleSequenceNumber);
  if ( v18 )
  {
    *(_QWORD *)(v21 + v20) = v19[6];
  }
  else if ( (v12 & 0x10) != 0 && a2 )
  {
    *(_QWORD *)(v21 + v20) = v19[6];
    *(_QWORD *)(v21 + v20 + 16) = ***(_QWORD ***)(a2 + 8);
  }
  else
  {
    *(_QWORD *)(v21 + v20) = 0;
  }
  if ( v56 )
    *(_BYTE *)(v21 + v20 + 25) |= 0x40u;
  if ( a5 )
    *(_BYTE *)(v21 + v20 + 25) |= 0x80u;
  if ( (v12 & 2) != 0 )
  {
    v19[2] = 0;
    *(_QWORD *)(v26 + 40 * v57 + 8) = *(_QWORD *)(a1 + 456);
    *(_QWORD *)(v21 + v20 + 8) = PsGetProcessId(**(PEPROCESS **)(a1 + 456));
    if ( (v12 & 4) != 0 )
      v19[3] = *(void **)(a1 + 456);
  }
  else if ( (v12 & 1) != 0 )
  {
    *(_QWORD *)(v26 + 40 * v57 + 8) = a1;
    *(_QWORD *)(v21 + v20 + 8) = PsGetThreadId(*(PETHREAD *)a1);
    v19[2] = *(void **)(v26 + 40 * v57 + 8);
  }
  v29 = HMHandleFromIndex(v57);
  v30 = (_QWORD *)v58;
  *v19 = (void *)v29;
  if ( *((_DWORD *)&gahti + 2 * v58 + 4) )
  {
    v30 = v19[5];
    *v30 = v29;
    v30[1] = v19[6];
  }
  if ( v9 )
  {
    v47 = ++*(_DWORD *)(v9 + 68);
    if ( v47 > *(_DWORD *)(v9 + 72) )
      *(_DWORD *)(v9 + 72) = v47;
  }
  v31 = W32GetUserSessionState(v30, &gahti);
  ++*(_DWORD *)(v31 + 19652);
  v34 = *(_DWORD *)(W32GetUserSessionState(v33, v32) + 19652);
  if ( v34 > *(_DWORD *)(W32GetUserSessionState(v36, v35) + 19656) )
  {
    v49 = *(_DWORD *)(W32GetUserSessionState(v38, v37) + 19652);
    *(_DWORD *)(W32GetUserSessionState(v51, v50) + 19656) = v49;
  }
  LOBYTE(v38) = a3;
  EtwUserHandleType = GetEtwUserHandleType(v38, v37, v39);
  if ( (v12 & 3) != 0 )
    v41 = (unsigned int)PsGetProcessId(**(PEPROCESS **)(a1 + 456)) & 0xFFFFFFFC;
  else
    v41 = 0;
  EtwTraceUserCreateHandle(*v19, EtwUserHandleType, v41);
  result = *(_QWORD *)(v26 + 40 * v57);
  *(_QWORD *)(v26 + 40 * v57 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x140009960  mov     rax, rsp
0x140009963  mov     [rax+20h], rbx
0x140009967  mov     [rax+18h], r8b
0x14000996b  mov     [rax+10h], rdx
0x14000996f  mov     [rax+8], rcx
0x140009973  push    rbp
0x140009974  push    rsi
0x140009975  push    rdi
0x140009976  push    r12
0x140009978  push    r13
0x14000997a  push    r14
0x14000997c  push    r15
0x14000997e  sub     rsp, 50h
0x140009982  mov     r12d, r9d
0x140009985  mov     rsi, rdx
0x140009988  movzx   ebx, r8b
0x14000998c  mov     rdi, rcx
0x14000998f  xor     r13d, r13d
0x140009992  call    cs:__imp_W32GetUserSessionState
0x140009999  nop     dword ptr [rax+rax+00h]
0x14000999e  lea     rcx, [rsp+88h+var_48]; struct tagDomLock *
0x1400099a3  mov     r10, [rax+0A4B0h]
0x1400099aa  mov     [rsp+88h+var_48], r10
0x1400099af  call    ?LockRefactorStagingAssertOwned@@YAXAEBUtagDomLock@@@Z; LockRefactorStagingAssertOwned(tagDomLock const &)
0x1400099b4  lea     rax, gahti
0x1400099bb  lea     r14, [rbx+rbx*2]
0x1400099bf  movzx   ebp, word ptr [rax+r14*8+0Ch]
0x1400099c5  movzx   eax, bp
0x1400099c8  mov     [rsp+88h+var_50], r14
0x1400099cd  and     ax, 3
0x1400099d1  mov     [rsp+88h+var_60], ax
0x1400099d6  jz      short loc_140009A03
0x1400099d8  xor     ecx, ecx
0x1400099da  xor     eax, eax
0x1400099dc  lock cmpxchg [rdi+208h], ecx
0x1400099e4  test    al, 1
0x1400099e6  jnz     loc_140009C6F
0x1400099ec  mov     r13, [rdi+1C8h]
0x1400099f3  mov     eax, cs:?gUserProcessHandleQuota@@3JA; long gUserProcessHandleQuota
0x1400099f9  cmp     [r13+44h], eax
0x1400099fd  jge     loc_140009DCC
0x140009a03  call    cs:__imp_W32GetUserSessionState
0x140009a0a  nop     dword ptr [rax+rax+00h]
0x140009a0f  mov     rdi, rax
0x140009a12  xor     ecx, ecx
0x140009a14  cmp     bl, 1
0x140009a17  jz      loc_140009DA8
0x140009a1d  lea     r15, [rdi+4C50h]
0x140009a24  mov     [rsp+88h+var_48], r15
0x140009a29  cmp     [r15], rcx
0x140009a2c  jz      loc_140009DA8
0x140009a32  test    r15, r15
0x140009a35  jz      loc_140009DCC
0x140009a3b  movzx   eax, bp
0x140009a3e  mov     [rsp+88h+var_68], ecx
0x140009a42  and     ax, 10h
0x140009a46  mov     [rsp+88h+var_64], ax
0x140009a4b  jnz     loc_140009C97
0x140009a51  movzx   r14d, bp
0x140009a55  and     r14w, 40h
0x140009a5a  jz      loc_140009C3C
0x140009a60  mov     rsi, [rsp+88h+var_50]
0x140009a65  lea     rax, gahti
0x140009a6c  mov     rdi, rcx
0x140009a6f  cmp     [rax+rsi*8+10h], ecx
0x140009a73  jnz     loc_140009E61
0x140009a79  test    rdi, rdi
0x140009a7c  jz      loc_140009C65
0x140009a82  mov     r15, [r15]
0x140009a85  mov     [rsp+88h+var_58], r15
0x140009a8a  call    cs:__imp_W32GetUserSessionState
0x140009a91  nop     dword ptr [rax+rax+00h]
0x140009a96  mov     rbx, r15
0x140009a99  shl     rbx, 5
0x140009a9d  mov     rsi, [rax+4D08h]
0x140009aa4  call    cs:__imp_W32GetUserSessionState
0x140009aab  nop     dword ptr [rax+rax+00h]
0x140009ab0  mov     rcx, [rsp+88h+var_48]
0x140009ab5  lea     r15, [r15+r15*4]
0x140009ab9  mov     r12, [rax+4CD0h]
0x140009ac0  mov     rax, [r12+r15*8]
0x140009ac4  mov     [rcx], rax
0x140009ac7  call    cs:__imp_W32GetUserSessionState
0x140009ace  nop     dword ptr [rax+rax+00h]
0x140009ad3  mov     rcx, [rsp+88h+var_58]
0x140009ad8  cmp     ecx, [rax+4CC0h]
0x140009ade  ja      loc_140009E06
0x140009ae4  mov     al, [rsp+88h+arg_10]
0x140009aeb  xor     edx, edx
0x140009aed  mov     [rsi+rbx+18h], al
0x140009af1  mov     [r12+r15*8], rdi
0x140009af5  mov     [r12+r15*8+18h], rdx
0x140009afa  lea     eax, [rdx+1]
0x140009afd  lock xadd cs:?HandleSequenceNumber@@3_JC, rax; __int64 volatile HandleSequenceNumber
0x140009b06  inc     rax
0x140009b09  mov     [r12+r15*8+20h], rax
0x140009b0e  test    r14w, r14w
0x140009b12  jz      loc_140009D2A
0x140009b18  mov     rax, [rdi+30h]
0x140009b1c  mov     [rsi+rbx], rax
0x140009b20  cmp     [rsp+88h+var_68], edx
0x140009b24  jnz     loc_140009F0D
0x140009b2a  cmp     [rsp+88h+arg_20], edx
0x140009b31  jnz     loc_140009F17
0x140009b37  mov     r14, [rsp+88h+arg_0]
0x140009b3f  test    bpl, 2
0x140009b43  jnz     loc_140009D3A
0x140009b49  test    bpl, 1
0x140009b4d  jz      short loc_140009B71
0x140009b4f  mov     [r12+r15*8+8], r14
0x140009b54  mov     rcx, [r14]; Thread
0x140009b57  call    cs:__imp_PsGetThreadId
0x140009b5e  nop     dword ptr [rax+rax+00h]
0x140009b63  mov     [rsi+rbx+8], rax
0x140009b68  mov     rax, [r12+r15*8+8]
0x140009b6d  mov     [rdi+10h], rax
0x140009b71  mov     rcx, [rsp+88h+var_58]
0x140009b76  call    HMHandleFromIndex
0x140009b7b  mov     rcx, [rsp+88h+var_50]
0x140009b80  lea     rdx, gahti
0x140009b87  xor     esi, esi
0x140009b89  mov     [rdi], rax
0x140009b8c  cmp     [rdx+rcx*8+10h], esi
0x140009b90  jnz     loc_140009DF2
0x140009b96  test    r13, r13
0x140009b99  jnz     loc_140009D0F
0x140009b9f  call    cs:__imp_W32GetUserSessionState
0x140009ba6  nop     dword ptr [rax+rax+00h]
0x140009bab  inc     dword ptr [rax+4CC4h]
0x140009bb1  call    cs:__imp_W32GetUserSessionState
0x140009bb8  nop     dword ptr [rax+rax+00h]
0x140009bbd  mov     ebx, [rax+4CC4h]
0x140009bc3  call    cs:__imp_W32GetUserSessionState
0x140009bca  nop     dword ptr [rax+rax+00h]
0x140009bcf  cmp     ebx, [rax+4CC8h]
0x140009bd5  ja      loc_140009E22
0x140009bdb  mov     cl, [rsp+88h+arg_10]
0x140009be2  call    ?GetEtwUserHandleType@@YA?AW4EtwUserHandleType@@E@Z; GetEtwUserHandleType(uchar)
0x140009be7  mov     ebx, eax
0x140009be9  cmp     [rsp+88h+var_60], si
0x140009bee  jz      loc_140009DEB
0x140009bf4  mov     rcx, [r14+1C8h]
0x140009bfb  mov     rcx, [rcx]; Process
0x140009bfe  call    cs:__imp_PsGetProcessId
0x140009c05  nop     dword ptr [rax+rax+00h]
0x140009c0a  and     eax, 0FFFFFFFCh
0x140009c0d  mov     rcx, [rdi]
0x140009c10  mov     r8d, eax
0x140009c13  mov     edx, ebx
0x140009c15  call    EtwTraceUserCreateHandle
0x140009c1a  mov     rax, [r12+r15*8]
0x140009c1e  mov     [r12+r15*8+10h], rsi
0x140009c23  mov     rbx, [rsp+88h+arg_18]
0x140009c2b  add     rsp, 50h
0x140009c2f  pop     r15
0x140009c31  pop     r14
0x140009c33  pop     r13
0x140009c35  pop     r12
0x140009c37  pop     rdi
0x140009c38  pop     rsi
0x140009c39  pop     rbp
0x140009c3a  retn
0x140009c3c  test    rsi, rsi
0x140009c3f  jnz     short loc_140009C73
0x140009c41  mov     [rsp+88h+var_68], 1
0x140009c49  test    bpl, 20h
0x140009c4d  jz      short loc_140009C73
0x140009c4f  mov     rcx, r12
0x140009c52  mov     r8b, bl
0x140009c55  movzx   edx, bp
0x140009c58  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x140009c5d  mov     rdi, rax
0x140009c60  test    rax, rax
0x140009c63  jnz     short loc_140009C79
0x140009c65  mov     ecx, 8
0x140009c6a  call    UserSetLastError
0x140009c6f  xor     eax, eax
0x140009c71  jmp     short loc_140009C23
0x140009c73  mov     [rsp+88h+var_68], ecx
0x140009c77  jmp     short loc_140009C4F
0x140009c79  cmp     bl, 1
0x140009c7c  jz      loc_140009ED0
0x140009c82  xor     ebx, ebx
0x140009c84  bt      bp, 8
0x140009c89  jb      loc_140009DD6
0x140009c8f  mov     r14d, ebx
0x140009c92  jmp     loc_140009A79
0x140009c97  test    rsi, rsi
0x140009c9a  jz      loc_140009A51
0x140009ca0  mov     rcx, r12
0x140009ca3  mov     r8b, bl
0x140009ca6  movzx   edx, bp
0x140009ca9  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x140009cae  mov     rdi, rax
0x140009cb1  test    rax, rax
0x140009cb4  jz      short loc_140009D01
0x140009cb6  mov     r8d, ebx
0x140009cb9  lea     rax, gahti
0x140009cc0  mov     edx, [rax+r14*8+10h]
0x140009cc5  mov     rcx, rsi
0x140009cc8  shl     r8d, 10h
0x140009ccc  or      r8d, 5
0x140009cd0  call    DesktopAlloc
0x140009cd5  mov     [rdi+28h], rax
0x140009cd9  test    rax, rax
0x140009cdc  jz      loc_140009E4B
0x140009ce2  lea     rcx, [rdi+18h]
0x140009ce6  mov     rdx, rsi
0x140009ce9  call    LockObjectAssignment
0x140009cee  mov     rcx, [rdi+28h]
0x140009cf2  mov     [rdi+20h], rdi
0x140009cf6  sub     rcx, [rsi+88h]
0x140009cfd  mov     [rdi+30h], rcx
0x140009d01  movzx   r14d, bp
0x140009d05  and     r14w, 40h
0x140009d0a  jmp     loc_140009A79
0x140009d0f  inc     dword ptr [r13+44h]
0x140009d13  mov     eax, [r13+44h]
0x140009d17  cmp     eax, [r13+48h]
0x140009d1b  jbe     loc_140009B9F
0x140009d21  mov     [r13+48h], eax
0x140009d25  jmp     loc_140009B9F
0x140009d2a  cmp     [rsp+88h+var_64], dx
0x140009d2f  jnz     short loc_140009D7F
0x140009d31  mov     [rsi+rbx], rdx
0x140009d35  jmp     loc_140009B20
0x140009d3a  mov     [rdi+10h], rdx
0x140009d3e  mov     rax, [r14+1C8h]
0x140009d45  mov     [r12+r15*8+8], rax
0x140009d4a  mov     rcx, [r14+1C8h]
0x140009d51  mov     rcx, [rcx]; Process
0x140009d54  call    cs:__imp_PsGetProcessId
0x140009d5b  nop     dword ptr [rax+rax+00h]
0x140009d60  mov     [rsi+rbx+8], rax
0x140009d65  test    bpl, 4
0x140009d69  jz      loc_140009B71
0x140009d6f  mov     rax, [r14+1C8h]
0x140009d76  mov     [rdi+18h], rax
0x140009d7a  jmp     loc_140009B71
0x140009d7f  mov     rcx, [rsp+88h+arg_8]
0x140009d87  test    rcx, rcx
0x140009d8a  jz      short loc_140009D31
0x140009d8c  mov     rax, [rdi+30h]
0x140009d90  mov     [rsi+rbx], rax
0x140009d94  mov     rax, [rcx+8]
0x140009d98  mov     rcx, [rax]
0x140009d9b  mov     rax, [rcx]
0x140009d9e  mov     [rsi+rbx+10h], rax
0x140009da3  jmp     loc_140009B20
0x140009da8  lea     r15, [rdi+4C48h]
0x140009daf  mov     [rsp+88h+var_48], r15
0x140009db4  cmp     [r15], rcx
0x140009db7  jnz     loc_140009A32
0x140009dbd  call    ?HMGrowHandleTable@@YAHXZ; HMGrowHandleTable(void)
0x140009dc2  xor     ecx, ecx
0x140009dc4  test    eax, eax
0x140009dc6  jnz     loc_140009A14
0x140009dcc  mov     ecx, 486h
0x140009dd1  jmp     loc_140009C6A
0x140009dd6  lea     rcx, [rdi+18h]
0x140009dda  mov     rdx, rsi
0x140009ddd  call    LockObjectAssignment
0x140009de2  mov     [rdi+20h], rdi
0x140009de6  jmp     loc_140009C8F
0x140009deb  mov     eax, esi
0x140009ded  jmp     loc_140009C0D
0x140009df2  mov     rcx, [rdi+28h]
0x140009df6  mov     [rcx], rax
0x140009df9  mov     rax, [rdi+30h]
0x140009dfd  mov     [rcx+8], rax
0x140009e01  jmp     loc_140009B96
0x140009e06  call    cs:__imp_W32GetUserSessionState
0x140009e0d  nop     dword ptr [rax+rax+00h]
0x140009e12  mov     rcx, [rsp+88h+var_58]
0x140009e17  mov     [rax+4CC0h], ecx
0x140009e1d  jmp     loc_140009AE4
0x140009e22  call    cs:__imp_W32GetUserSessionState
0x140009e29  nop     dword ptr [rax+rax+00h]
0x140009e2e  mov     ebx, [rax+4CC4h]
0x140009e34  call    cs:__imp_W32GetUserSessionState
0x140009e3b  nop     dword ptr [rax+rax+00h]
0x140009e40  mov     [rax+4CC8h], ebx
0x140009e46  jmp     loc_140009BDB
0x140009e4b  mov     r8, rdi
0x140009e4e  mov     dl, bl
0x140009e50  movzx   ecx, bp
0x140009e53  call    ?HMFreeUserOrIsolatedType@@YAXW4HM_OBJ_CREATE_FLAGS@@EPEAX@Z; HMFreeUserOrIsolatedType(HM_OBJ_CREATE_FLAGS,uchar,void *)
0x140009e58  xor     ebx, ebx
0x140009e5a  mov     edi, ebx
0x140009e5c  jmp     loc_140009D01
0x140009e61  mov     rcx, r12
0x140009e64  mov     r8b, bl
0x140009e67  movzx   edx, bp
0x140009e6a  call    ?HMAllocateUserOrIsolatedType@@YAPEAX_KW4HM_OBJ_CREATE_FLAGS@@E@Z; HMAllocateUserOrIsolatedType(unsigned __int64,HM_OBJ_CREATE_FLAGS,uchar)
0x140009e6f  xor     ebx, ebx
0x140009e71  mov     rdi, rax
0x140009e74  test    rax, rax
0x140009e77  jz      loc_140009A79
0x140009e7d  lea     rax, gahti
0x140009e84  mov     ecx, [rax+rsi*8+10h]; Size
  ... truncated ...
```
