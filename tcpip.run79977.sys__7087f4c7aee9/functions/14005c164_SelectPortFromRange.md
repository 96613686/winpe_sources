# SelectPortFromRange

- ea: `0x14005c164`
- end: `0x14005c4df`
- name: `SelectPortFromRange`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14005bb84`

## callees

- `0x14005c164`
- `0x14005e190`
- `0x14005e300`
- `0x14005e360`
- `0x14005e5a0`
- `0x14005e5c4`
- `0x14005e920`
- `0x14005ea60`
- `0x140060600`
- `0x1400f0c60`
- `0x14014f600`
- `0x1401528fc`
- `0x140152cc8`
- `0x1401bf4d0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c5098`
- `ntoskrnl!RtlClearBit` at `0x1401c5098`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c4b9`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c4b9`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c35b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401c4eb7`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c35b`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401c4eb7`
- `ntoskrnl!PsGetProcessId` at `0x14005c4cb`
- `ntoskrnl!PsGetProcessId` at `0x14005c4cb`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c2ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c37e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c3f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4f92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c50a8`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c2ee`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c37e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c3f5`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4f92`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c50a8`
- `cng!SystemPrng` at `0x14005c3ba`
- `cng!SystemPrng` at `0x14005c3ba`

## pseudocode

```c
__int64 __fastcall SelectPortFromRange(
        __int64 a1,
        int a2,
        struct _KPROCESS *a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        volatile __int32 *a7,
        _WORD *a8,
        __int64 a9,
        __int64 a10,
        __int64 a11,
        char a12)
{
  int v13; // r12d
  __int16 v14; // ax
  unsigned __int16 v15; // ax
  int v16; // edi
  char v18; // r8
  __int64 v19; // r9
  int *v20; // r14
  char v21; // dl
  __int64 v22; // rcx
  _WORD *v23; // rdi
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  volatile __int32 v27; // r15d
  unsigned __int32 v28; // r15d
  unsigned __int64 v29; // rsi
  __int64 v30; // rax
  unsigned int v31; // eax
  struct _KPROCESS *v32; // r12
  char ProcessSequenceNumber; // r15
  unsigned int ProcessId; // r9d
  __int64 v35; // rbx
  int v36; // eax
  char v37; // al
  char v39; // [rsp+50h] [rbp-69h]
  __int16 v40; // [rsp+54h] [rbp-65h] BYREF
  _WORD v41[2]; // [rsp+58h] [rbp-61h] BYREF
  int v42; // [rsp+5Ch] [rbp-5Dh]
  __int64 v43; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v44; // [rsp+68h] [rbp-51h]
  int v45; // [rsp+6Ch] [rbp-4Dh]
  _WORD *v46; // [rsp+70h] [rbp-49h]
  __int64 v47; // [rsp+78h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-39h] BYREF
  PEPROCESS Process; // [rsp+98h] [rbp-21h]
  volatile __int32 *v50; // [rsp+A0h] [rbp-19h]
  __int64 v51; // [rsp+A8h] [rbp-11h] BYREF
  int v52; // [rsp+B0h] [rbp-9h]

  v13 = a2;
  v43 = a10;
  v47 = a11;
  v46 = a8;
  v14 = *a8;
  v45 = a2;
  Process = a3;
  v51 = a4;
  v50 = a7;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( v14 )
  {
    v15 = __ROR2__(v14, 8);
    if ( v15 < (unsigned __int16)a5 || v15 > (unsigned __int16)a6 )
      return (unsigned int)-1073741811;
    v42 = 0;
    v28 = 0;
    v44 = 1;
    LODWORD(v29) = v15;
    v39 = 1;
  }
  else
  {
    v42 = 0;
    v44 = (unsigned __int16)a6 - (unsigned __int16)a5 + 1;
    if ( (a2 & 4) != 0 )
    {
      v41[0] = 0;
      SystemPrng(v41, 2);
      v27 = v41[0];
    }
    else
    {
      v27 = *a7;
    }
    v28 = v27 - (unsigned __int16)a5;
    v39 = 0;
    LODWORD(v29) = (unsigned __int16)a5 + v28 % ((unsigned __int16)a6 - (unsigned int)(unsigned __int16)a5 + 1);
  }
  v35 = *(_QWORD *)(a1 + 8 * ((unsigned __int64)(unsigned int)v29 >> 8) + 224);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v35, &LockHandle);
  while ( *(_DWORD *)(v35 + 8) )
    ;
  if ( !(unsigned __int8)InitializeAssignmentArray(v35) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 3221225626LL;
  }
  v18 = v39;
  LOBYTE(v40) = 0;
  v16 = 0;
  LODWORD(v19) = 0;
  while ( 1 )
  {
    v20 = (int *)(*(_QWORD *)(v35 + 24) + 32LL * (unsigned __int8)v29);
    if ( v18 || (unsigned int)*v20 < 0x20 )
    {
      if ( (unsigned __int8)IsEmptyAssignment(*(_QWORD *)(v35 + 24) + 32LL * (unsigned __int8)v29) )
      {
        if ( (v13 & 8) != 0 )
        {
          *v20 = *v20 & 0xFFFFFFE0 | 2;
          InitializeAssignmentPerProcEndpointTable(v22);
        }
        LOBYTE(v19) = a12;
        InsertEndpointInAssignment(a1, (_DWORD)v20, v47, v19, a9, v43, v13);
        v23 = v46;
        ++*(_WORD *)(v35 + 16);
        LODWORD(v19) = 0;
        if ( !*v23 )
          _InterlockedExchange(v50, v29);
        *v23 = __ROR2__(v29, 8);
      }
      else
      {
        if ( *v46 == (_WORD)v19 )
          goto LABEL_34;
        if ( v43 )
          v30 = *(_QWORD *)(v43 + 16);
        else
          v30 = v19;
        v36 = IsReusableAssignment(a1, v35, v20, v29, v13, Process, (struct _KTHREAD *)v51, a9, v30, &LockHandle);
        LODWORD(v19) = 0;
        v16 = v36;
        if ( v36 < 0 )
          goto LABEL_16;
        LOBYTE(v19) = a12;
        InsertEndpointInAssignment(a1, (_DWORD)v20, v47, v19, a9, v43, v13);
        LODWORD(v19) = 0;
        *v46 = __ROR2__(v29, 8);
      }
      v16 = 0;
LABEL_16:
      v18 = v39;
      v21 = v40;
      goto LABEL_17;
    }
    v21 = 1;
    LOBYTE(v40) = 1;
LABEL_17:
    if ( *v46 != (_WORD)v19 )
      goto LABEL_18;
LABEL_34:
    v31 = v42 + 1;
    v42 = v31;
    if ( v31 < v44 )
      goto LABEL_47;
    if ( v18 || v21 != 1 )
      break;
    v18 = 1;
    v39 = 1;
    v31 = v19;
    v42 = v19;
LABEL_47:
    v29 = (v28 + v31) % v44 + (unsigned __int16)a5;
    if ( v35 != *(_QWORD *)(a1 + 8 * (v29 >> 8) + 224) )
    {
      if ( *(_WORD *)(v35 + 16) == (_WORD)v19 )
        DereferenceAssignmentArray(v35);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v35 = *(_QWORD *)(a1 + 8 * (v29 >> 8) + 224);
      RtlAcquireWriteLock(v35, &LockHandle);
      v37 = InitializeAssignmentArray(v35);
      LODWORD(v19) = 0;
      if ( !v37 )
      {
        LOBYTE(v13) = v45;
        v16 = -1073741670;
        goto LABEL_18;
      }
      v18 = v39;
    }
    v13 = v45;
  }
  v16 = -1073741303;
  if ( !*(_WORD *)(v35 + 16) )
    DereferenceAssignmentArray(v35);
LABEL_18:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v16 >= 0 && PortTrackerEnabled )
  {
    HIDWORD(v51) = *(_DWORD *)(a1 + 104);
    v40 = 0;
    v43 = 0;
    LOWORD(v51) = v29;
    WORD1(v51) = v29;
    v52 = (v13 & 0x10) != 0 ? 8 : 4;
    v16 = PtClientReservePortRange(&v51, &v43, &v40);
    if ( v16 )
    {
      if ( SBYTE1(WPP_MAIN_CB.Reserved) < 0 )
      {
        v32 = Process;
        if ( Process )
        {
          ProcessSequenceNumber = PsGetProcessSequenceNumber(Process);
          ProcessId = (unsigned int)PsGetProcessId(v32);
        }
        else
        {
          ProcessId = -1;
          ProcessSequenceNumber = -1;
        }
        McTemplateK0qqqqhhx_EtwWriteTransfer(
          v25,
          v24,
          v26,
          ProcessId,
          v16,
          v52,
          *(_DWORD *)(a1 + 104),
          v29,
          1,
          ProcessSequenceNumber);
      }
      RtlAcquireWriteLock(v35, &LockHandle);
      RemoveEndpointFromAssignment(v20, v47);
      if ( (unsigned __int8)IsEmptyAssignment(v20) )
      {
        if ( (*v20 & 2) != 0 )
          CleanupAssignmentPerProcEndpointTable();
        *v20 &= 0xFFFFFFE0;
        if ( (*(_WORD *)(v35 + 16))-- == 1 )
          DereferenceAssignmentArray(v35);
        if ( !IsPortInExclusion(*(_QWORD *)(a1 + 136), (unsigned __int16)v29) )
          RtlClearBit((PRTL_BITMAP)(a1 + 208), v29);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v16 = -1073741670;
      *v46 = 0;
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v35, &LockHandle);
      while ( *(_DWORD *)(v35 + 8) )
        ;
      *(_QWORD *)(v47 + 8) = v43;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x14005c164  mov     [rsp-8+arg_8], rbx
0x14005c169  push    rbp
0x14005c16a  push    rsi
0x14005c16b  push    rdi
0x14005c16c  push    r12
0x14005c16e  push    r13
0x14005c170  push    r14
0x14005c172  push    r15
0x14005c174  lea     rbp, [rsp-7]
0x14005c179  sub     rsp, 0C0h
0x14005c180  mov     rax, cs:__security_cookie
0x14005c187  xor     rax, rsp
0x14005c18a  mov     [rbp+37h+var_38], rax
0x14005c18e  mov     rax, [rbp+37h+arg_38]
0x14005c192  mov     r13, rcx
0x14005c195  mov     rcx, [rbp+37h+arg_48]
0x14005c19c  mov     r12d, edx
0x14005c19f  mov     [rbp+37h+var_90], rcx
0x14005c1a3  xor     r14d, r14d
0x14005c1a6  mov     rcx, [rbp+37h+arg_50]
0x14005c1ad  xorps   xmm0, xmm0
0x14005c1b0  mov     [rbp+37h+var_78], rcx
0x14005c1b4  xor     ecx, ecx
0x14005c1b6  mov     [rbp+37h+var_80], rax
0x14005c1ba  movzx   eax, word ptr [rax]
0x14005c1bd  mov     [rbp+37h+var_84], edx
0x14005c1c0  mov     rdx, [rbp+37h+arg_30]
0x14005c1c4  mov     [rbp+37h+Process], r8
0x14005c1c8  lea     r8d, [rcx+1]
0x14005c1cc  mov     [rbp+37h+var_48], r9
0x14005c1d0  mov     [rbp+37h+var_50], rdx
0x14005c1d4  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x14005c1d8  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14005c1dc  test    ax, ax
0x14005c1df  jz      loc_14005C38F
0x14005c1e5  ror     ax, 8
0x14005c1e9  cmp     ax, word ptr [rbp+37h+arg_20]
0x14005c1ed  jnb     loc_14005C3D0
0x14005c1f3  mov     edi, 0C000000Dh
0x14005c1f8  mov     eax, edi
0x14005c1fa  mov     rcx, [rbp+37h+var_38]
0x14005c1fe  xor     rcx, rsp; StackCookie
0x14005c201  call    __security_check_cookie
0x14005c206  mov     rbx, [rsp+0F0h+arg_8]
0x14005c20e  add     rsp, 0C0h
0x14005c215  pop     r15
0x14005c217  pop     r14
0x14005c219  pop     r13
0x14005c21b  pop     r12
0x14005c21d  pop     rdi
0x14005c21e  pop     rsi
0x14005c21f  pop     rbp
0x14005c220  retn
0x14005c222  mov     eax, [rbx+8]
0x14005c225  test    eax, eax
0x14005c227  jnz     short loc_14005C222
0x14005c229  mov     rcx, rbx
0x14005c22c  call    InitializeAssignmentArray
0x14005c231  test    al, al
0x14005c233  jz      loc_14005C3F1
0x14005c239  mov     r8b, [rbp+37h+var_A0]
0x14005c23d  mov     dl, r14b
0x14005c240  mov     byte ptr [rbp+37h+var_9C], dl
0x14005c243  mov     edi, r14d
0x14005c246  xor     r9d, r9d
0x14005c249  movzx   eax, sil
0x14005c24d  mov     r14d, eax
0x14005c250  shl     r14, 5
0x14005c254  add     r14, [rbx+18h]
0x14005c258  test    r8b, r8b
0x14005c25b  jz      loc_14005C40B
0x14005c261  mov     rcx, r14
0x14005c264  call    IsEmptyAssignment
0x14005c269  test    al, al
0x14005c26b  jz      loc_14005C442
0x14005c271  test    r12b, 8
0x14005c275  jnz     loc_14005C41F
0x14005c27b  mov     rax, [rbp+37h+var_90]
0x14005c27f  mov     rdx, r14
0x14005c282  mov     r9b, [rbp+37h+arg_58]
0x14005c289  mov     rcx, r13
0x14005c28c  mov     r8, [rbp+37h+var_78]
0x14005c290  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x14005c295  mov     [rsp+0F0h+var_C8], rax
0x14005c29a  movzx   eax, word ptr [rbp+37h+arg_40]
0x14005c2a1  mov     word ptr [rsp+0F0h+var_D0], ax
0x14005c2a6  call    InsertEndpointInAssignment
0x14005c2ab  mov     rdi, [rbp+37h+var_80]
0x14005c2af  mov     eax, 1
0x14005c2b4  add     [rbx+10h], ax
0x14005c2b8  xor     r9d, r9d
0x14005c2bb  cmp     [rdi], r9w
0x14005c2bf  jz      loc_14005C435
0x14005c2c5  movzx   eax, si
0x14005c2c8  ror     ax, 8
0x14005c2cc  mov     [rdi], ax
0x14005c2cf  mov     edi, r9d
0x14005c2d2  mov     r8b, [rbp+37h+var_A0]
0x14005c2d6  mov     dl, byte ptr [rbp+37h+var_9C]
0x14005c2d9  mov     rax, [rbp+37h+var_80]
0x14005c2dd  cmp     [rax], r9w
0x14005c2e1  jz      loc_14005C462
0x14005c2e7  xor     r15d, r15d
0x14005c2ea  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c2ee  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c2f5  nop     dword ptr [rax+rax+00h]
0x14005c2fa  test    edi, edi
0x14005c2fc  js      loc_14005C1F8
0x14005c302  cmp     cs:PortTrackerEnabled, r15b
0x14005c309  jz      loc_14005C1F8
0x14005c30f  mov     eax, [r13+68h]
0x14005c313  lea     r8, [rbp+37h+var_9C]
0x14005c317  mov     dword ptr [rbp+37h+var_48+4], eax
0x14005c31a  lea     rdx, [rbp+37h+var_90]
0x14005c31e  and     r12b, 10h
0x14005c322  mov     [rbp+37h+var_9C], r15w
0x14005c327  neg     r12b
0x14005c32a  mov     [rbp+37h+var_90], r15
0x14005c32e  lea     rcx, [rbp+37h+var_48]
0x14005c332  mov     word ptr [rbp+37h+var_48], si
0x14005c336  sbb     eax, eax
0x14005c338  mov     word ptr [rbp+37h+var_48+2], si
0x14005c33c  and     eax, 4
0x14005c33f  add     eax, 4
0x14005c342  mov     [rbp+37h+var_40], eax
0x14005c345  call    PtClientReservePortRange
0x14005c34a  mov     edi, eax
0x14005c34c  test    eax, eax
0x14005c34e  jnz     loc_14005C49C
0x14005c354  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005c358  mov     rcx, rbx; SpinLock
0x14005c35b  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005c362  nop     dword ptr [rax+rax+00h]
0x14005c367  mov     eax, [rbx+8]
0x14005c36a  test    eax, eax
0x14005c36c  jnz     short loc_14005C367
0x14005c36e  mov     rcx, [rbp+37h+var_78]
0x14005c372  mov     rax, [rbp+37h+var_90]
0x14005c376  mov     [rcx+8], rax
0x14005c37a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c37e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c385  nop     dword ptr [rax+rax+00h]
0x14005c38a  jmp     loc_14005C1F8
0x14005c38f  movzx   ebx, word ptr [rbp+37h+arg_20]
0x14005c393  movzx   edi, word ptr [rbp+37h+arg_28]
0x14005c397  sub     edi, ebx
0x14005c399  mov     [rbp+37h+var_94], r14d
0x14005c39d  inc     edi
0x14005c39f  mov     [rbp+37h+var_88], edi
0x14005c3a2  test    r12b, 4
0x14005c3a6  jz      loc_1401C4E8E
0x14005c3ac  mov     edx, 2
0x14005c3b1  mov     [rbp+37h+var_98], r14w
0x14005c3b6  lea     rcx, [rbp+37h+var_98]
0x14005c3ba  call    cs:__imp_SystemPrng
0x14005c3c1  nop     dword ptr [rax+rax+00h]
0x14005c3c6  movzx   r15d, [rbp+37h+var_98]
0x14005c3cb  jmp     loc_1401C4E91
0x14005c3d0  cmp     ax, word ptr [rbp+37h+arg_28]
0x14005c3d4  ja      loc_14005C1F3
0x14005c3da  mov     [rbp+37h+var_94], r14d
0x14005c3de  mov     r15d, r14d
0x14005c3e1  mov     [rbp+37h+var_88], r8d
0x14005c3e5  movzx   esi, ax
0x14005c3e8  mov     [rbp+37h+var_A0], r8b
0x14005c3ec  jmp     loc_1401C4EA2
0x14005c3f1  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c3f5  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c3fc  nop     dword ptr [rax+rax+00h]
0x14005c401  mov     eax, 0C000009Ah
0x14005c406  jmp     loc_14005C1FA
0x14005c40b  cmp     dword ptr [r14], 20h ; ' '
0x14005c40f  jb      loc_14005C261
0x14005c415  mov     dl, 1
0x14005c417  mov     byte ptr [rbp+37h+var_9C], dl
0x14005c41a  jmp     loc_14005C2D9
0x14005c41f  mov     eax, [r14]
0x14005c422  and     eax, 0FFFFFFE2h
0x14005c425  or      eax, 2
0x14005c428  mov     [r14], eax
0x14005c42b  call    InitializeAssignmentPerProcEndpointTable
0x14005c430  jmp     loc_14005C27B
0x14005c435  mov     rcx, [rbp+37h+var_50]
0x14005c439  mov     eax, esi
0x14005c43b  xchg    eax, [rcx]
0x14005c43d  jmp     loc_14005C2C5
0x14005c442  mov     rax, [rbp+37h+var_80]
0x14005c446  cmp     [rax], r9w
0x14005c44a  jz      short loc_14005C462
0x14005c44c  mov     rax, [rbp+37h+var_90]
0x14005c450  test    rax, rax
0x14005c453  jz      loc_1401C4EC9
0x14005c459  mov     rax, [rax+10h]
0x14005c45d  jmp     loc_1401C4ECC
0x14005c462  mov     eax, [rbp+37h+var_94]
0x14005c465  mov     ecx, [rbp+37h+var_88]
0x14005c468  inc     eax
0x14005c46a  mov     [rbp+37h+var_94], eax
0x14005c46d  cmp     eax, ecx
0x14005c46f  jb      loc_1401C4F61
0x14005c475  test    r8b, r8b
0x14005c478  jnz     loc_1401C4FD1
0x14005c47e  mov     eax, 1
0x14005c483  cmp     dl, al
0x14005c485  jnz     loc_1401C4FD1
0x14005c48b  mov     r8b, al
0x14005c48e  mov     [rbp+37h+var_A0], al
0x14005c491  mov     eax, r9d
0x14005c494  mov     [rbp+37h+var_94], eax
0x14005c497  jmp     loc_1401C4F61
0x14005c49c  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r15b
0x14005c4a3  jge     loc_1401C5034
0x14005c4a9  mov     r12, [rbp+37h+Process]
0x14005c4ad  test    r12, r12
0x14005c4b0  jz      loc_1401C5000
0x14005c4b6  mov     rcx, r12
0x14005c4b9  call    cs:__imp_PsGetProcessSequenceNumber
0x14005c4c0  nop     dword ptr [rax+rax+00h]
0x14005c4c5  mov     rcx, r12; Process
0x14005c4c8  mov     r15, rax
0x14005c4cb  call    cs:__imp_PsGetProcessId
0x14005c4d2  nop     dword ptr [rax+rax+00h]
0x14005c4d7  mov     r9, rax
0x14005c4da  jmp     loc_1401C5008
0x1401c4e8e  mov     r15d, [rdx]
0x1401c4e91  sub     r15d, ebx
0x1401c4e94  mov     [rbp+37h+var_A0], r14b
0x1401c4e98  mov     eax, r15d
0x1401c4e9b  xor     edx, edx
0x1401c4e9d  div     edi
0x1401c4e9f  lea     esi, [rbx+rdx]
0x1401c4ea2  mov     eax, esi
0x1401c4ea4  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1401c4ea8  shr     rax, 8
0x1401c4eac  mov     rbx, [r13+rax*8+0E0h]
0x1401c4eb4  mov     rcx, rbx; SpinLock
0x1401c4eb7  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401c4ebe  nop     dword ptr [rax+rax+00h]
0x1401c4ec3  nop
0x1401c4ec4  jmp     loc_14005C222
0x1401c4ec9  mov     rax, r9
0x1401c4ecc  lea     rcx, [rbp+37h+LockHandle]
0x1401c4ed0  mov     r9d, esi; int
0x1401c4ed3  mov     [rsp+0F0h+var_A8], rcx; LockHandle
0x1401c4ed8  mov     r8, r14; int
0x1401c4edb  mov     [rsp+0F0h+var_B0], rax; __int64
0x1401c4ee0  mov     rdx, rbx; int
0x1401c4ee3  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401c4eea  mov     rcx, r13; int
0x1401c4eed  mov     [rsp+0F0h+var_B8], ax; __int16
0x1401c4ef2  mov     rax, [rbp+37h+var_48]
0x1401c4ef6  mov     [rsp+0F0h+var_C0], rax; __int64
0x1401c4efb  mov     rax, [rbp+37h+Process]
0x1401c4eff  mov     [rsp+0F0h+var_C8], rax; __int64
0x1401c4f04  mov     [rsp+0F0h+var_D0], r12d; int
0x1401c4f09  call    IsReusableAssignment
0x1401c4f0e  xor     r9d, r9d
0x1401c4f11  mov     edi, eax
0x1401c4f13  test    eax, eax
0x1401c4f15  js      loc_14005C2D2
0x1401c4f1b  mov     rax, [rbp+37h+var_90]
0x1401c4f1f  mov     rdx, r14
0x1401c4f22  mov     r9b, [rbp+37h+arg_58]
0x1401c4f29  mov     rcx, r13
0x1401c4f2c  mov     r8, [rbp+37h+var_78]
0x1401c4f30  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1401c4f35  mov     [rsp+0F0h+var_C8], rax
0x1401c4f3a  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401c4f41  mov     word ptr [rsp+0F0h+var_D0], ax
0x1401c4f46  call    InsertEndpointInAssignment
0x1401c4f4b  mov     rcx, [rbp+37h+var_80]
0x1401c4f4f  movzx   eax, si
0x1401c4f52  ror     ax, 8
0x1401c4f56  xor     r9d, r9d
0x1401c4f59  mov     [rcx], ax
0x1401c4f5c  jmp     loc_14005C2CF
0x1401c4f61  movzx   esi, word ptr [rbp+37h+arg_20]
0x1401c4f65  add     eax, r15d
0x1401c4f68  xor     edx, edx
0x1401c4f6a  div     ecx
0x1401c4f6c  add     esi, edx
0x1401c4f6e  mov     r12d, esi
0x1401c4f71  shr     r12, 8
0x1401c4f75  cmp     rbx, [r13+r12*8+0E0h]
0x1401c4f7d  jz      short loc_1401C4FC5
0x1401c4f7f  cmp     [rbx+10h], r9w
0x1401c4f84  jnz     short loc_1401C4F8E
0x1401c4f86  mov     rcx, rbx
0x1401c4f89  call    DereferenceAssignmentArray
0x1401c4f8e  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1401c4f92  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401c4f99  nop     dword ptr [rax+rax+00h]
0x1401c4f9e  mov     rbx, [r13+r12*8+0E0h]
0x1401c4fa6  lea     rdx, [rbp+37h+LockHandle]
0x1401c4faa  mov     rcx, rbx
0x1401c4fad  call    RtlAcquireWriteLock
0x1401c4fb2  mov     rcx, rbx
0x1401c4fb5  call    InitializeAssignmentArray
0x1401c4fba  xor     r9d, r9d
0x1401c4fbd  test    al, al
  ... truncated ...
```
