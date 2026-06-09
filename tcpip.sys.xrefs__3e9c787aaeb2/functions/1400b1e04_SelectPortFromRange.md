# SelectPortFromRange

- ea: `0x1400b1e04`
- end: `0x1400b217f`
- name: `SelectPortFromRange`
- size: `891`
- prototype: `__int64 __fastcall(__int64, int, struct _KPROCESS *, __int64, __int64, __int64, volatile __int32 *, _WORD *, __int64, __int64, __int64, char)`
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation`

## callers

- `0x1400b1824`

## callees

- `0x1400b1e04`
- `0x1400b3de0`
- `0x1400b3f50`
- `0x1400b3fb0`
- `0x1400b41f0`
- `0x1400b4214`
- `0x1400b4570`
- `0x1400b46b0`
- `0x1400b6b20`
- `0x1400f7cd0`
- `0x140151200`
- `0x1401547dc`
- `0x140154ba8`
- `0x1401c0fd0`

## import_xrefs

- `ntoskrnl!RtlClearBit` at `0x1401cee34`
- `ntoskrnl!RtlClearBit` at `0x1401cee34`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b2159`
- `ntoskrnl!PsGetProcessSequenceNumber` at `0x1400b2159`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b1ffb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401cec53`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1400b1ffb`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x1401cec53`
- `ntoskrnl!PsGetProcessId` at `0x1400b216b`
- `ntoskrnl!PsGetProcessId` at `0x1400b216b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b1f8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b201e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b2095`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401ced2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401cee44`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b1f8e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b201e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1400b2095`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401ced2e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x1401cee44`
- `cng!SystemPrng` at `0x1400b205a`
- `cng!SystemPrng` at `0x1400b205a`

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
  __int64 v18; // rdx
  __int64 v19; // r8
  __int64 v20; // r9
  int *v21; // r14
  __int64 v22; // rcx
  _WORD *v23; // rdi
  int v24; // edx
  int v25; // ecx
  int v26; // r8d
  volatile __int32 v27; // r15d
  unsigned __int32 v28; // r15d
  unsigned int v29; // esi
  __int64 v30; // rax
  unsigned int v31; // eax
  struct _KPROCESS *v32; // r12
  char ProcessSequenceNumber; // r15
  unsigned int ProcessId; // r9d
  __int64 v35; // rbx
  int v36; // eax
  unsigned __int64 v37; // r12
  char v38; // al
  __int64 v39; // rdx
  __int64 v40; // r8
  __int64 v41; // r9
  __int64 v42; // rdx
  char v44; // [rsp+50h] [rbp-69h]
  __int16 v45; // [rsp+54h] [rbp-65h] BYREF
  _WORD v46[2]; // [rsp+58h] [rbp-61h] BYREF
  int v47; // [rsp+5Ch] [rbp-5Dh]
  __int64 v48; // [rsp+60h] [rbp-59h] BYREF
  unsigned int v49; // [rsp+68h] [rbp-51h]
  int v50; // [rsp+6Ch] [rbp-4Dh]
  _WORD *v51; // [rsp+70h] [rbp-49h]
  __int64 v52; // [rsp+78h] [rbp-41h]
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+80h] [rbp-39h] BYREF
  PEPROCESS Process; // [rsp+98h] [rbp-21h]
  volatile __int32 *v55; // [rsp+A0h] [rbp-19h]
  __int64 v56; // [rsp+A8h] [rbp-11h] BYREF
  int v57; // [rsp+B0h] [rbp-9h]

  v13 = a2;
  v48 = a10;
  v52 = a11;
  v51 = a8;
  v14 = *a8;
  v50 = a2;
  Process = a3;
  v56 = a4;
  v55 = a7;
  memset(&LockHandle, 0, sizeof(LockHandle));
  if ( v14 )
  {
    v15 = __ROR2__(v14, 8);
    if ( v15 < (unsigned __int16)a5 || v15 > (unsigned __int16)a6 )
      return (unsigned int)-1073741811;
    v47 = 0;
    v28 = 0;
    v49 = 1;
    v29 = v15;
    v44 = 1;
  }
  else
  {
    v47 = 0;
    v49 = (unsigned __int16)a6 - (unsigned __int16)a5 + 1;
    if ( (a2 & 4) != 0 )
    {
      v46[0] = 0;
      SystemPrng(v46, 2);
      v27 = v46[0];
    }
    else
    {
      v27 = *a7;
    }
    v28 = v27 - (unsigned __int16)a5;
    v44 = 0;
    v29 = (unsigned __int16)a5 + v28 % ((unsigned __int16)a6 - (unsigned int)(unsigned __int16)a5 + 1);
  }
  v35 = *(_QWORD *)(a1 + 8 * ((unsigned __int64)v29 >> 8) + 224);
  KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v35, &LockHandle);
  while ( *(_DWORD *)(v35 + 8) )
    ;
  if ( !(unsigned __int8)InitializeAssignmentArray(v35) )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    return 3221225626LL;
  }
  LOBYTE(v19) = v44;
  LOBYTE(v18) = 0;
  LOBYTE(v45) = 0;
  v16 = 0;
  v20 = 0;
  while ( 1 )
  {
    v21 = (int *)(*(_QWORD *)(v35 + 24) + 32LL * (unsigned __int8)v29);
    if ( (_BYTE)v19 || (unsigned int)*v21 < 0x20 )
    {
      if ( (unsigned __int8)IsEmptyAssignment(*(_QWORD *)(v35 + 24) + 32LL * (unsigned __int8)v29, v18, v19, v20) )
      {
        if ( (v13 & 8) != 0 )
        {
          *v21 = *v21 & 0xFFFFFFE0 | 2;
          InitializeAssignmentPerProcEndpointTable(v22);
        }
        LOBYTE(v20) = a12;
        InsertEndpointInAssignment(a1, (_DWORD)v21, v52, v20, a9, v48, v13);
        v23 = v51;
        ++*(_WORD *)(v35 + 16);
        v20 = 0;
        if ( !*v23 )
          _InterlockedExchange(v55, v29);
        *v23 = __ROR2__(v29, 8);
      }
      else
      {
        if ( *v51 == (_WORD)v20 )
          goto LABEL_34;
        if ( v48 )
          v30 = *(_QWORD *)(v48 + 16);
        else
          v30 = v20;
        v36 = IsReusableAssignment(a1, v35, v21, v29, v13, Process, (struct _KTHREAD *)v56, a9, v30, &LockHandle);
        v20 = 0;
        v16 = v36;
        if ( v36 < 0 )
          goto LABEL_16;
        LOBYTE(v20) = a12;
        InsertEndpointInAssignment(a1, (_DWORD)v21, v52, v20, a9, v48, v13);
        v20 = 0;
        *v51 = __ROR2__(v29, 8);
      }
      v16 = 0;
LABEL_16:
      LOBYTE(v19) = v44;
      LOBYTE(v18) = v45;
      goto LABEL_17;
    }
    LOBYTE(v18) = 1;
    LOBYTE(v45) = 1;
LABEL_17:
    if ( *v51 != (_WORD)v20 )
      goto LABEL_18;
LABEL_34:
    v31 = v47 + 1;
    v47 = v31;
    if ( v31 < v49 )
      goto LABEL_47;
    if ( (_BYTE)v19 || (_BYTE)v18 != 1 )
      break;
    LOBYTE(v19) = 1;
    v44 = 1;
    v31 = v20;
    v47 = v20;
LABEL_47:
    v18 = (v28 + v31) % v49;
    v29 = v18 + (unsigned __int16)a5;
    v37 = (unsigned __int64)v29 >> 8;
    if ( v35 != *(_QWORD *)(a1 + 8 * v37 + 224) )
    {
      if ( *(_WORD *)(v35 + 16) == (_WORD)v20 )
        DereferenceAssignmentArray(v35, v18);
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v35 = *(_QWORD *)(a1 + 8 * v37 + 224);
      RtlAcquireWriteLock(v35, &LockHandle);
      v38 = InitializeAssignmentArray(v35);
      v20 = 0;
      if ( !v38 )
      {
        LOBYTE(v13) = v50;
        v16 = -1073741670;
        goto LABEL_18;
      }
      LOBYTE(v19) = v44;
    }
    v13 = v50;
    LOBYTE(v18) = v45;
  }
  v16 = -1073741303;
  if ( !*(_WORD *)(v35 + 16) )
    DereferenceAssignmentArray(v35, v18);
LABEL_18:
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  if ( v16 >= 0 && PortTrackerEnabled )
  {
    HIDWORD(v56) = *(_DWORD *)(a1 + 104);
    v45 = 0;
    v48 = 0;
    LOWORD(v56) = v29;
    WORD1(v56) = v29;
    v57 = (v13 & 0x10) != 0 ? 8 : 4;
    v16 = PtClientReservePortRange(&v56, &v48, &v45);
    if ( v16 )
    {
      if ( SBYTE1(WPP_MAIN_CB.Dpc.DeferredRoutine) < 0 )
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
          v57,
          *(_DWORD *)(a1 + 104),
          v29,
          1,
          ProcessSequenceNumber);
      }
      RtlAcquireWriteLock(v35, &LockHandle);
      RemoveEndpointFromAssignment(v21, v52);
      if ( (unsigned __int8)IsEmptyAssignment(v21, v39, v40, v41) )
      {
        if ( (*v21 & 2) != 0 )
          CleanupAssignmentPerProcEndpointTable();
        *v21 &= 0xFFFFFFE0;
        if ( (*(_WORD *)(v35 + 16))-- == 1 )
          DereferenceAssignmentArray(v35, v42);
        if ( !IsPortInExclusion(*(_QWORD *)(a1 + 136), (unsigned __int16)v29) )
          RtlClearBit((PRTL_BITMAP)(a1 + 208), v29);
      }
      KeReleaseInStackQueuedSpinLock(&LockHandle);
      v16 = -1073741670;
      *v51 = 0;
    }
    else
    {
      KeAcquireInStackQueuedSpinLock((PKSPIN_LOCK)v35, &LockHandle);
      while ( *(_DWORD *)(v35 + 8) )
        ;
      *(_QWORD *)(v52 + 8) = v48;
      KeReleaseInStackQueuedSpinLock(&LockHandle);
    }
  }
  return (unsigned int)v16;
}

```

## disassembly

```asm
0x1400b1e04  mov     [rsp-8+arg_8], rbx
0x1400b1e09  push    rbp
0x1400b1e0a  push    rsi
0x1400b1e0b  push    rdi
0x1400b1e0c  push    r12
0x1400b1e0e  push    r13
0x1400b1e10  push    r14
0x1400b1e12  push    r15
0x1400b1e14  lea     rbp, [rsp-7]
0x1400b1e19  sub     rsp, 0C0h
0x1400b1e20  mov     rax, cs:__security_cookie
0x1400b1e27  xor     rax, rsp
0x1400b1e2a  mov     [rbp+37h+var_38], rax
0x1400b1e2e  mov     rax, [rbp+37h+arg_38]
0x1400b1e32  mov     r13, rcx
0x1400b1e35  mov     rcx, [rbp+37h+arg_48]
0x1400b1e3c  mov     r12d, edx
0x1400b1e3f  mov     [rbp+37h+var_90], rcx
0x1400b1e43  xor     r14d, r14d
0x1400b1e46  mov     rcx, [rbp+37h+arg_50]
0x1400b1e4d  xorps   xmm0, xmm0
0x1400b1e50  mov     [rbp+37h+var_78], rcx
0x1400b1e54  xor     ecx, ecx
0x1400b1e56  mov     [rbp+37h+var_80], rax
0x1400b1e5a  movzx   eax, word ptr [rax]
0x1400b1e5d  mov     [rbp+37h+var_84], edx
0x1400b1e60  mov     rdx, [rbp+37h+arg_30]
0x1400b1e64  mov     [rbp+37h+Process], r8
0x1400b1e68  lea     r8d, [rcx+1]
0x1400b1e6c  mov     [rbp+37h+var_48], r9
0x1400b1e70  mov     [rbp+37h+var_50], rdx
0x1400b1e74  mov     qword ptr [rbp+37h+LockHandle.OldIrql], rcx
0x1400b1e78  movups  xmmword ptr [rbp+37h+LockHandle.LockQueue.Next], xmm0
0x1400b1e7c  test    ax, ax
0x1400b1e7f  jz      loc_1400B202F
0x1400b1e85  ror     ax, 8
0x1400b1e89  cmp     ax, word ptr [rbp+37h+arg_20]
0x1400b1e8d  jnb     loc_1400B2070
0x1400b1e93  mov     edi, 0C000000Dh
0x1400b1e98  mov     eax, edi
0x1400b1e9a  mov     rcx, [rbp+37h+var_38]
0x1400b1e9e  xor     rcx, rsp; StackCookie
0x1400b1ea1  call    __security_check_cookie
0x1400b1ea6  mov     rbx, [rsp+0F0h+arg_8]
0x1400b1eae  add     rsp, 0C0h
0x1400b1eb5  pop     r15
0x1400b1eb7  pop     r14
0x1400b1eb9  pop     r13
0x1400b1ebb  pop     r12
0x1400b1ebd  pop     rdi
0x1400b1ebe  pop     rsi
0x1400b1ebf  pop     rbp
0x1400b1ec0  retn
0x1400b1ec2  mov     eax, [rbx+8]
0x1400b1ec5  test    eax, eax
0x1400b1ec7  jnz     short loc_1400B1EC2
0x1400b1ec9  mov     rcx, rbx
0x1400b1ecc  call    InitializeAssignmentArray
0x1400b1ed1  test    al, al
0x1400b1ed3  jz      loc_1400B2091
0x1400b1ed9  mov     r8b, [rbp+37h+var_A0]
0x1400b1edd  mov     dl, r14b
0x1400b1ee0  mov     byte ptr [rbp+37h+var_9C], dl
0x1400b1ee3  mov     edi, r14d
0x1400b1ee6  xor     r9d, r9d
0x1400b1ee9  movzx   eax, sil
0x1400b1eed  mov     r14d, eax
0x1400b1ef0  shl     r14, 5
0x1400b1ef4  add     r14, [rbx+18h]
0x1400b1ef8  test    r8b, r8b
0x1400b1efb  jz      loc_1400B20AB
0x1400b1f01  mov     rcx, r14
0x1400b1f04  call    IsEmptyAssignment
0x1400b1f09  test    al, al
0x1400b1f0b  jz      loc_1400B20E2
0x1400b1f11  test    r12b, 8
0x1400b1f15  jnz     loc_1400B20BF
0x1400b1f1b  mov     rax, [rbp+37h+var_90]
0x1400b1f1f  mov     rdx, r14
0x1400b1f22  mov     r9b, [rbp+37h+arg_58]
0x1400b1f29  mov     rcx, r13
0x1400b1f2c  mov     r8, [rbp+37h+var_78]
0x1400b1f30  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1400b1f35  mov     [rsp+0F0h+var_C8], rax
0x1400b1f3a  movzx   eax, word ptr [rbp+37h+arg_40]
0x1400b1f41  mov     word ptr [rsp+0F0h+var_D0], ax
0x1400b1f46  call    InsertEndpointInAssignment
0x1400b1f4b  mov     rdi, [rbp+37h+var_80]
0x1400b1f4f  mov     eax, 1
0x1400b1f54  add     [rbx+10h], ax
0x1400b1f58  xor     r9d, r9d
0x1400b1f5b  cmp     [rdi], r9w
0x1400b1f5f  jz      loc_1400B20D5
0x1400b1f65  movzx   eax, si
0x1400b1f68  ror     ax, 8
0x1400b1f6c  mov     [rdi], ax
0x1400b1f6f  mov     edi, r9d
0x1400b1f72  mov     r8b, [rbp+37h+var_A0]
0x1400b1f76  mov     dl, byte ptr [rbp+37h+var_9C]
0x1400b1f79  mov     rax, [rbp+37h+var_80]
0x1400b1f7d  cmp     [rax], r9w
0x1400b1f81  jz      loc_1400B2102
0x1400b1f87  xor     r15d, r15d
0x1400b1f8a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b1f8e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b1f95  nop     dword ptr [rax+rax+00h]
0x1400b1f9a  test    edi, edi
0x1400b1f9c  js      loc_1400B1E98
0x1400b1fa2  cmp     cs:PortTrackerEnabled, r15b
0x1400b1fa9  jz      loc_1400B1E98
0x1400b1faf  mov     eax, [r13+68h]
0x1400b1fb3  lea     r8, [rbp+37h+var_9C]
0x1400b1fb7  mov     dword ptr [rbp+37h+var_48+4], eax
0x1400b1fba  lea     rdx, [rbp+37h+var_90]
0x1400b1fbe  and     r12b, 10h
0x1400b1fc2  mov     [rbp+37h+var_9C], r15w
0x1400b1fc7  neg     r12b
0x1400b1fca  mov     [rbp+37h+var_90], r15
0x1400b1fce  lea     rcx, [rbp+37h+var_48]
0x1400b1fd2  mov     word ptr [rbp+37h+var_48], si
0x1400b1fd6  sbb     eax, eax
0x1400b1fd8  mov     word ptr [rbp+37h+var_48+2], si
0x1400b1fdc  and     eax, 4
0x1400b1fdf  add     eax, 4
0x1400b1fe2  mov     [rbp+37h+var_40], eax
0x1400b1fe5  call    PtClientReservePortRange
0x1400b1fea  mov     edi, eax
0x1400b1fec  test    eax, eax
0x1400b1fee  jnz     loc_1400B213C
0x1400b1ff4  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1400b1ff8  mov     rcx, rbx; SpinLock
0x1400b1ffb  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1400b2002  nop     dword ptr [rax+rax+00h]
0x1400b2007  mov     eax, [rbx+8]
0x1400b200a  test    eax, eax
0x1400b200c  jnz     short loc_1400B2007
0x1400b200e  mov     rcx, [rbp+37h+var_78]
0x1400b2012  mov     rax, [rbp+37h+var_90]
0x1400b2016  mov     [rcx+8], rax
0x1400b201a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b201e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b2025  nop     dword ptr [rax+rax+00h]
0x1400b202a  jmp     loc_1400B1E98
0x1400b202f  movzx   ebx, word ptr [rbp+37h+arg_20]
0x1400b2033  movzx   edi, word ptr [rbp+37h+arg_28]
0x1400b2037  sub     edi, ebx
0x1400b2039  mov     [rbp+37h+var_94], r14d
0x1400b203d  inc     edi
0x1400b203f  mov     [rbp+37h+var_88], edi
0x1400b2042  test    r12b, 4
0x1400b2046  jz      loc_1401CEC2A
0x1400b204c  mov     edx, 2
0x1400b2051  mov     [rbp+37h+var_98], r14w
0x1400b2056  lea     rcx, [rbp+37h+var_98]
0x1400b205a  call    cs:__imp_SystemPrng
0x1400b2061  nop     dword ptr [rax+rax+00h]
0x1400b2066  movzx   r15d, [rbp+37h+var_98]
0x1400b206b  jmp     loc_1401CEC2D
0x1400b2070  cmp     ax, word ptr [rbp+37h+arg_28]
0x1400b2074  ja      loc_1400B1E93
0x1400b207a  mov     [rbp+37h+var_94], r14d
0x1400b207e  mov     r15d, r14d
0x1400b2081  mov     [rbp+37h+var_88], r8d
0x1400b2085  movzx   esi, ax
0x1400b2088  mov     [rbp+37h+var_A0], r8b
0x1400b208c  jmp     loc_1401CEC3E
0x1400b2091  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1400b2095  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1400b209c  nop     dword ptr [rax+rax+00h]
0x1400b20a1  mov     eax, 0C000009Ah
0x1400b20a6  jmp     loc_1400B1E9A
0x1400b20ab  cmp     dword ptr [r14], 20h ; ' '
0x1400b20af  jb      loc_1400B1F01
0x1400b20b5  mov     dl, 1
0x1400b20b7  mov     byte ptr [rbp+37h+var_9C], dl
0x1400b20ba  jmp     loc_1400B1F79
0x1400b20bf  mov     eax, [r14]
0x1400b20c2  and     eax, 0FFFFFFE2h
0x1400b20c5  or      eax, 2
0x1400b20c8  mov     [r14], eax
0x1400b20cb  call    InitializeAssignmentPerProcEndpointTable
0x1400b20d0  jmp     loc_1400B1F1B
0x1400b20d5  mov     rcx, [rbp+37h+var_50]
0x1400b20d9  mov     eax, esi
0x1400b20db  xchg    eax, [rcx]
0x1400b20dd  jmp     loc_1400B1F65
0x1400b20e2  mov     rax, [rbp+37h+var_80]
0x1400b20e6  cmp     [rax], r9w
0x1400b20ea  jz      short loc_1400B2102
0x1400b20ec  mov     rax, [rbp+37h+var_90]
0x1400b20f0  test    rax, rax
0x1400b20f3  jz      loc_1401CEC65
0x1400b20f9  mov     rax, [rax+10h]
0x1400b20fd  jmp     loc_1401CEC68
0x1400b2102  mov     eax, [rbp+37h+var_94]
0x1400b2105  mov     ecx, [rbp+37h+var_88]
0x1400b2108  inc     eax
0x1400b210a  mov     [rbp+37h+var_94], eax
0x1400b210d  cmp     eax, ecx
0x1400b210f  jb      loc_1401CECFD
0x1400b2115  test    r8b, r8b
0x1400b2118  jnz     loc_1401CED6D
0x1400b211e  mov     eax, 1
0x1400b2123  cmp     dl, al
0x1400b2125  jnz     loc_1401CED6D
0x1400b212b  mov     r8b, al
0x1400b212e  mov     [rbp+37h+var_A0], al
0x1400b2131  mov     eax, r9d
0x1400b2134  mov     [rbp+37h+var_94], eax
0x1400b2137  jmp     loc_1401CECFD
0x1400b213c  cmp     byte ptr cs:WPP_MAIN_CB.Dpc.DeferredRoutine+1, r15b
0x1400b2143  jge     loc_1401CEDD0
0x1400b2149  mov     r12, [rbp+37h+Process]
0x1400b214d  test    r12, r12
0x1400b2150  jz      loc_1401CED9C
0x1400b2156  mov     rcx, r12
0x1400b2159  call    cs:__imp_PsGetProcessSequenceNumber
0x1400b2160  nop     dword ptr [rax+rax+00h]
0x1400b2165  mov     rcx, r12; Process
0x1400b2168  mov     r15, rax
0x1400b216b  call    cs:__imp_PsGetProcessId
0x1400b2172  nop     dword ptr [rax+rax+00h]
0x1400b2177  mov     r9, rax
0x1400b217a  jmp     loc_1401CEDA4
0x1401cec2a  mov     r15d, [rdx]
0x1401cec2d  sub     r15d, ebx
0x1401cec30  mov     [rbp+37h+var_A0], r14b
0x1401cec34  mov     eax, r15d
0x1401cec37  xor     edx, edx
0x1401cec39  div     edi
0x1401cec3b  lea     esi, [rbx+rdx]
0x1401cec3e  mov     eax, esi
0x1401cec40  lea     rdx, [rbp+37h+LockHandle]; LockHandle
0x1401cec44  shr     rax, 8
0x1401cec48  mov     rbx, [r13+rax*8+0E0h]
0x1401cec50  mov     rcx, rbx; SpinLock
0x1401cec53  call    cs:__imp_KeAcquireInStackQueuedSpinLock
0x1401cec5a  nop     dword ptr [rax+rax+00h]
0x1401cec5f  nop
0x1401cec60  jmp     loc_1400B1EC2
0x1401cec65  mov     rax, r9
0x1401cec68  lea     rcx, [rbp+37h+LockHandle]
0x1401cec6c  mov     r9d, esi; int
0x1401cec6f  mov     [rsp+0F0h+var_A8], rcx; LockHandle
0x1401cec74  mov     r8, r14; int
0x1401cec77  mov     [rsp+0F0h+var_B0], rax; __int64
0x1401cec7c  mov     rdx, rbx; int
0x1401cec7f  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401cec86  mov     rcx, r13; int
0x1401cec89  mov     [rsp+0F0h+var_B8], ax; __int16
0x1401cec8e  mov     rax, [rbp+37h+var_48]
0x1401cec92  mov     [rsp+0F0h+var_C0], rax; __int64
0x1401cec97  mov     rax, [rbp+37h+Process]
0x1401cec9b  mov     [rsp+0F0h+var_C8], rax; __int64
0x1401ceca0  mov     [rsp+0F0h+var_D0], r12d; int
0x1401ceca5  call    IsReusableAssignment
0x1401cecaa  xor     r9d, r9d
0x1401cecad  mov     edi, eax
0x1401cecaf  test    eax, eax
0x1401cecb1  js      loc_1400B1F72
0x1401cecb7  mov     rax, [rbp+37h+var_90]
0x1401cecbb  mov     rdx, r14
0x1401cecbe  mov     r9b, [rbp+37h+arg_58]
0x1401cecc5  mov     rcx, r13
0x1401cecc8  mov     r8, [rbp+37h+var_78]
0x1401ceccc  mov     dword ptr [rsp+0F0h+var_C0], r12d
0x1401cecd1  mov     [rsp+0F0h+var_C8], rax
0x1401cecd6  movzx   eax, word ptr [rbp+37h+arg_40]
0x1401cecdd  mov     word ptr [rsp+0F0h+var_D0], ax
0x1401cece2  call    InsertEndpointInAssignment
0x1401cece7  mov     rcx, [rbp+37h+var_80]
0x1401ceceb  movzx   eax, si
0x1401cecee  ror     ax, 8
0x1401cecf2  xor     r9d, r9d
0x1401cecf5  mov     [rcx], ax
0x1401cecf8  jmp     loc_1400B1F6F
0x1401cecfd  movzx   esi, word ptr [rbp+37h+arg_20]
0x1401ced01  add     eax, r15d
0x1401ced04  xor     edx, edx
0x1401ced06  div     ecx
0x1401ced08  add     esi, edx
0x1401ced0a  mov     r12d, esi
0x1401ced0d  shr     r12, 8
0x1401ced11  cmp     rbx, [r13+r12*8+0E0h]
0x1401ced19  jz      short loc_1401CED61
0x1401ced1b  cmp     [rbx+10h], r9w
0x1401ced20  jnz     short loc_1401CED2A
0x1401ced22  mov     rcx, rbx
0x1401ced25  call    DereferenceAssignmentArray
0x1401ced2a  lea     rcx, [rbp+37h+LockHandle]; LockHandle
0x1401ced2e  call    cs:__imp_KeReleaseInStackQueuedSpinLock
0x1401ced35  nop     dword ptr [rax+rax+00h]
0x1401ced3a  mov     rbx, [r13+r12*8+0E0h]
0x1401ced42  lea     rdx, [rbp+37h+LockHandle]
0x1401ced46  mov     rcx, rbx
0x1401ced49  call    RtlAcquireWriteLock
0x1401ced4e  mov     rcx, rbx
0x1401ced51  call    InitializeAssignmentArray
0x1401ced56  xor     r9d, r9d
0x1401ced59  test    al, al
  ... truncated ...
```
