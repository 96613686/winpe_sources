# SelectPortFromRange

- ea: `0x14005bec4`
- end: `0x14005c23f`
- name: `SelectPortFromRange`
- size: `891`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x14005b8e4`

## callees

- `0x14005bec4`
- `0x14005def0`
- `0x14005e060`
- `0x14005e0c0`
- `0x14005e300`
- `0x14005e324`
- `0x14005e680`
- `0x14005e7c0`
- `0x140060360`
- `0x1400f0d70`
- `0x14014f4c0`
- `0x1401527bc`
- `0x140152b88`
- `0x1401bf390`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401c4f58`
- `ntoskrnl!RtlClearBit` at `0x1401c4f58`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c219`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x14005c219`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c0bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401c4d77`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x14005c0bb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401c4d77`
- `ntoskrnl!PsGetProcessId` at `0x14005c22b`
- `ntoskrnl!PsGetProcessId` at `0x14005c22b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c04e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c0de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c155`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4e52`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4f68`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c04e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c0de`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14005c155`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4e52`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401c4f68`
- `cng!SystemPrng` at `0x14005c11a`
- `cng!SystemPrng` at `0x14005c11a`

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
0x14005bec4  mov     [rsp-8+arg_8], rbx
0x14005bec9  push    rbp
0x14005beca  push    rsi
0x14005becb  push    rdi
0x14005becc  push    r12
0x14005bece  push    r13
0x14005bed0  push    r14
0x14005bed2  push    r15
0x14005bed4  lea     rbp, [rsp-7]
0x14005bed9  sub     rsp, 0C0h
0x14005bee0  mov     rax, cs:__security_cookie
0x14005bee7  xor     rax, rsp
0x14005beea  mov     [rbp+37h+var_38], rax
0x14005beee  mov     rax, [rbp+37h+arg_38]
0x14005bef2  mov     r13, rcx
0x14005bef5  mov     rcx, [rbp+37h+arg_48]
0x14005befc  mov     r12d, edx
0x14005beff  mov     [rbp+37h+var_90], rcx
0x14005bf03  xor     r14d, r14d
0x14005bf06  mov     rcx, [rbp+37h+arg_50]
0x14005bf0d  xorps   xmm0, xmm0
0x14005bf10  mov     [rbp+37h+var_78], rcx
0x14005bf14  xor     ecx, ecx
0x14005bf16  mov     [rbp+37h+var_80], rax
0x14005bf1a  movzx   eax, word ptr [rax]
0x14005bf1d  mov     [rbp+37h+var_84], edx
0x14005bf20  mov     rdx, [rbp+37h+arg_30]
0x14005bf24  mov     [rbp+37h+Process], r8
0x14005bf28  lea     r8d, [rcx+1]
0x14005bf2c  mov     [rbp+37h+var_48], r9
0x14005bf30  mov     [rbp+37h+var_50], rdx
0x14005bf34  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x14005bf38  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x14005bf3c  test    ax, ax
0x14005bf3f  jz      loc_14005C0EF
0x14005bf45  ror     ax, 8
0x14005bf49  cmp     ax, word ptr [rbp+37h+arg_20]
0x14005bf4d  jnb     loc_14005C130
0x14005bf53  mov     edi, 0C000000Dh
0x14005bf58  mov     eax, edi
0x14005bf5a  mov     rcx, [rbp+37h+var_38]
0x14005bf5e  xor     rcx, rsp; StackCookie
0x14005bf61  call    __security_check_cookie
0x14005bf66  mov     rbx, [rsp+0F0h+arg_8]
0x14005bf6e  add     rsp, 0C0h
0x14005bf75  pop     r15
0x14005bf77  pop     r14
0x14005bf79  pop     r13
0x14005bf7b  pop     r12
0x14005bf7d  pop     rdi
0x14005bf7e  pop     rsi
0x14005bf7f  pop     rbp
0x14005bf80  retn
0x14005bf82  mov     eax, [rbx+8]
0x14005bf85  test    eax, eax
0x14005bf87  jnz     short loc_14005BF82
0x14005bf89  mov     rcx, rbx
0x14005bf8c  call    InitializeAssignmentArray
0x14005bf91  test    al, al
0x14005bf93  jz      loc_14005C151
0x14005bf99  mov     r8b, [rbp+37h+var_A0]
0x14005bf9d  mov     dl, r14b
0x14005bfa0  mov     byte ptr [rbp+37h+var_9C], dl
0x14005bfa3  mov     edi, r14d
0x14005bfa6  xor     r9d, r9d
0x14005bfa9  movzx   eax, sil
0x14005bfad  mov     r14d, eax
0x14005bfb0  shl     r14, 5
0x14005bfb4  add     r14, [rbx+18h]
0x14005bfb8  test    r8b, r8b
0x14005bfbb  jz      loc_14005C16B
0x14005bfc1  mov     rcx, r14
0x14005bfc4  call    IsEmptyAssignment
0x14005bfc9  test    al, al
0x14005bfcb  jz      loc_14005C1A2
0x14005bfd1  test    r12b, 8
0x14005bfd5  jnz     loc_14005C17F
0x14005bfdb  mov     rax, [rbp+37h+var_90]
0x14005bfdf  mov     rdx, r14
0x14005bfe2  mov     r9b, [rbp+37h+arg_58]
0x14005bfe9  mov     rcx, r13
0x14005bfec  mov     r8, [rbp+37h+var_78]
0x14005bff0  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x14005bff5  mov     [rsp+0F0h+var_C8], rax
0x14005bffa  movzx   eax, word ptr [rbp+37h+arg_40]
0x14005c001  mov     word ptr [rsp+0F0h+var_D0], ax
0x14005c006  call    InsertEndpointInAssignment
0x14005c00b  mov     rdi, [rbp+37h+var_80]
0x14005c00f  mov     eax, 1
0x14005c014  add     [rbx+10h], ax
0x14005c018  xor     r9d, r9d
0x14005c01b  cmp     [rdi], r9w
0x14005c01f  jz      loc_14005C195
0x14005c025  movzx   eax, si
0x14005c028  ror     ax, 8
0x14005c02c  mov     [rdi], ax
0x14005c02f  mov     edi, r9d
0x14005c032  mov     r8b, [rbp+37h+var_A0]
0x14005c036  mov     dl, byte ptr [rbp+37h+var_9C]
0x14005c039  mov     rax, [rbp+37h+var_80]
0x14005c03d  cmp     [rax], r9w
0x14005c041  jz      loc_14005C1C2
0x14005c047  xor     r15d, r15d
0x14005c04a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c04e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c055  nop     dword ptr [rax+rax+00h]
0x14005c05a  test    edi, edi
0x14005c05c  js      loc_14005BF58
0x14005c062  cmp     cs:PortTrackerEnabled, r15b
0x14005c069  jz      loc_14005BF58
0x14005c06f  mov     eax, [r13+68h]
0x14005c073  lea     r8, [rbp+37h+var_9C]
0x14005c077  mov     dword ptr [rbp+37h+var_48+4], eax
0x14005c07a  lea     rdx, [rbp+37h+var_90]
0x14005c07e  and     r12b, 10h
0x14005c082  mov     [rbp+37h+var_9C], r15w
0x14005c087  neg     r12b
0x14005c08a  mov     [rbp+37h+var_90], r15
0x14005c08e  lea     rcx, [rbp+37h+var_48]
0x14005c092  mov     word ptr [rbp+37h+var_48], si
0x14005c096  sbb     eax, eax
0x14005c098  mov     word ptr [rbp+37h+var_48+2], si
0x14005c09c  and     eax, 4
0x14005c09f  add     eax, 4
0x14005c0a2  mov     [rbp+37h+var_40], eax
0x14005c0a5  call    PtClientReservePortRange
0x14005c0aa  mov     edi, eax
0x14005c0ac  test    eax, eax
0x14005c0ae  jnz     loc_14005C1FC
0x14005c0b4  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x14005c0b8  mov     rcx, rbx; SpinLock
0x14005c0bb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x14005c0c2  nop     dword ptr [rax+rax+00h]
0x14005c0c7  mov     eax, [rbx+8]
0x14005c0ca  test    eax, eax
0x14005c0cc  jnz     short loc_14005C0C7
0x14005c0ce  mov     rcx, [rbp+37h+var_78]
0x14005c0d2  mov     rax, [rbp+37h+var_90]
0x14005c0d6  mov     [rcx+8], rax
0x14005c0da  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c0de  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c0e5  nop     dword ptr [rax+rax+00h]
0x14005c0ea  jmp     loc_14005BF58
0x14005c0ef  movzx   ebx, word ptr [rbp+37h+arg_20]
0x14005c0f3  movzx   edi, word ptr [rbp+37h+arg_28]
0x14005c0f7  sub     edi, ebx
0x14005c0f9  mov     [rbp+37h+var_94], r14d
0x14005c0fd  inc     edi
0x14005c0ff  mov     [rbp+37h+var_88], edi
0x14005c102  test    r12b, 4
0x14005c106  jz      loc_1401C4D4E
0x14005c10c  mov     edx, 2
0x14005c111  mov     [rbp+37h+var_98], r14w
0x14005c116  lea     rcx, [rbp+37h+var_98]
0x14005c11a  call    cs:__imp_SystemPrng
0x14005c121  nop     dword ptr [rax+rax+00h]
0x14005c126  movzx   r15d, [rbp+37h+var_98]
0x14005c12b  jmp     loc_1401C4D51
0x14005c130  cmp     ax, word ptr [rbp+37h+arg_28]
0x14005c134  ja      loc_14005BF53
0x14005c13a  mov     [rbp+37h+var_94], r14d
0x14005c13e  mov     r15d, r14d
0x14005c141  mov     [rbp+37h+var_88], r8d
0x14005c145  movzx   esi, ax
0x14005c148  mov     [rbp+37h+var_A0], r8b
0x14005c14c  jmp     loc_1401C4D62
0x14005c151  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x14005c155  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x14005c15c  nop     dword ptr [rax+rax+00h]
0x14005c161  mov     eax, 0C000009Ah
0x14005c166  jmp     loc_14005BF5A
0x14005c16b  cmp     dword ptr [r14], 20h ; ' '
0x14005c16f  jb      loc_14005BFC1
0x14005c175  mov     dl, 1
0x14005c177  mov     byte ptr [rbp+37h+var_9C], dl
0x14005c17a  jmp     loc_14005C039
0x14005c17f  mov     eax, [r14]
0x14005c182  and     eax, 0FFFFFFE2h
0x14005c185  or      eax, 2
0x14005c188  mov     [r14], eax
0x14005c18b  call    InitializeAssignmentPerProcEndpointTable
0x14005c190  jmp     loc_14005BFDB
0x14005c195  mov     rcx, [rbp+37h+var_50]
0x14005c199  mov     eax, esi
0x14005c19b  xchg    eax, [rcx]
0x14005c19d  jmp     loc_14005C025
0x14005c1a2  mov     rax, [rbp+37h+var_80]
0x14005c1a6  cmp     [rax], r9w
0x14005c1aa  jz      short loc_14005C1C2
0x14005c1ac  mov     rax, [rbp+37h+var_90]
0x14005c1b0  test    rax, rax
0x14005c1b3  jz      loc_1401C4D89
0x14005c1b9  mov     rax, [rax+10h]
0x14005c1bd  jmp     loc_1401C4D8C
0x14005c1c2  mov     eax, [rbp+37h+var_94]
0x14005c1c5  mov     ecx, [rbp+37h+var_88]
0x14005c1c8  inc     eax
0x14005c1ca  mov     [rbp+37h+var_94], eax
0x14005c1cd  cmp     eax, ecx
0x14005c1cf  jb      loc_1401C4E21
0x14005c1d5  test    r8b, r8b
0x14005c1d8  jnz     loc_1401C4E91
0x14005c1de  mov     eax, 1
0x14005c1e3  cmp     dl, al
0x14005c1e5  jnz     loc_1401C4E91
0x14005c1eb  mov     r8b, al
0x14005c1ee  mov     [rbp+37h+var_A0], al
0x14005c1f1  mov     eax, r9d
0x14005c1f4  mov     [rbp+37h+var_94], eax
0x14005c1f7  jmp     loc_1401C4E21
0x14005c1fc  cmp     byte ptr cs:WPP_MAIN_CB.Reserved+1, r15b
0x14005c203  jge     loc_1401C4EF4
0x14005c209  mov     r12, [rbp+37h+Process]
0x14005c20d  test    r12, r12
0x14005c210  jz      loc_1401C4EC0
0x14005c216  mov     rcx, r12
0x14005c219  call    cs:__imp_PsGetProcessSequenceNumber
0x14005c220  nop     dword ptr [rax+rax+00h]
0x14005c225  mov     rcx, r12; Process
0x14005c228  mov     r15, rax
0x14005c22b  call    cs:__imp_PsGetProcessId
0x14005c232  nop     dword ptr [rax+rax+00h]
0x14005c237  mov     r9, rax
0x14005c23a  jmp     loc_1401C4EC8
0x1401c4d4e  mov     r15d, [rdx]
0x1401c4d51  sub     r15d, ebx
0x1401c4d54  mov     [rbp+37h+var_A0], r14b
0x1401c4d58  mov     eax, r15d
0x1401c4d5b  xor     edx, edx
0x1401c4d5d  div     edi
0x1401c4d5f  lea     esi, [rbx+rdx]
0x1401c4d62  mov     eax, esi
0x1401c4d64  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1401c4d68  shr     rax, 8
0x1401c4d6c  mov     rbx, [r13+rax*8+0E0h]
0x1401c4d74  mov     rcx, rbx; SpinLock
0x1401c4d77  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401c4d7e  nop     dword ptr [rax+rax+00h]
0x1401c4d83  nop
0x1401c4d84  jmp     loc_14005BF82
0x1401c4d89  mov     rax, r9
0x1401c4d8c  lea     rcx, [rbp+37h+LockHandle]
0x1401c4d90  mov     r9d, esi; int
0x1401c4d93  mov     [rsp+0F0h+var_A8], rcx; LockHandle
0x1401c4d98  mov     r8, r14; int
0x1401c4d9b  mov     [rsp+0F0h+var_B0], rax; __int64
0x1401c4da0  mov     rdx, rbx; int
0x1401c4da3  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401c4daa  mov     rcx, r13; int
0x1401c4dad  mov     [rsp+0F0h+var_B8], ax; __int16
0x1401c4db2  mov     rax, [rbp+37h+var_48]
0x1401c4db6  mov     [rsp+0F0h+var_C0], rax; __int64
0x1401c4dbb  mov     rax, [rbp+37h+Process]
0x1401c4dbf  mov     [rsp+0F0h+var_C8], rax; __int64
0x1401c4dc4  mov     [rsp+0F0h+var_D0], r12d; int
0x1401c4dc9  call    IsReusableAssignment
0x1401c4dce  xor     r9d, r9d
0x1401c4dd1  mov     edi, eax
0x1401c4dd3  test    eax, eax
0x1401c4dd5  js      loc_14005C032
0x1401c4ddb  mov     rax, [rbp+37h+var_90]
0x1401c4ddf  mov     rdx, r14
0x1401c4de2  mov     r9b, [rbp+37h+arg_58]
0x1401c4de9  mov     rcx, r13
0x1401c4dec  mov     r8, [rbp+37h+var_78]
0x1401c4df0  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1401c4df5  mov     [rsp+0F0h+var_C8], rax
0x1401c4dfa  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401c4e01  mov     word ptr [rsp+0F0h+var_D0], ax
0x1401c4e06  call    InsertEndpointInAssignment
0x1401c4e0b  mov     rcx, [rbp+37h+var_80]
0x1401c4e0f  movzx   eax, si
0x1401c4e12  ror     ax, 8
0x1401c4e16  xor     r9d, r9d
0x1401c4e19  mov     [rcx], ax
0x1401c4e1c  jmp     loc_14005C02F
0x1401c4e21  movzx   esi, word ptr [rbp+37h+arg_20]
0x1401c4e25  add     eax, r15d
0x1401c4e28  xor     edx, edx
0x1401c4e2a  div     ecx
0x1401c4e2c  add     esi, edx
0x1401c4e2e  mov     r12d, esi
0x1401c4e31  shr     r12, 8
0x1401c4e35  cmp     rbx, [r13+r12*8+0E0h]
0x1401c4e3d  jz      short loc_1401C4E85
0x1401c4e3f  cmp     [rbx+10h], r9w
0x1401c4e44  jnz     short loc_1401C4E4E
0x1401c4e46  mov     rcx, rbx
0x1401c4e49  call    DereferenceAssignmentArray
0x1401c4e4e  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1401c4e52  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401c4e59  nop     dword ptr [rax+rax+00h]
0x1401c4e5e  mov     rbx, [r13+r12*8+0E0h]
0x1401c4e66  lea     rdx, [rbp+37h+LockHandle]
0x1401c4e6a  mov     rcx, rbx
0x1401c4e6d  call    RtlAcquireWriteLock
0x1401c4e72  mov     rcx, rbx
0x1401c4e75  call    InitializeAssignmentArray
0x1401c4e7a  xor     r9d, r9d
0x1401c4e7d  test    al, al
  ... truncated ...
```
