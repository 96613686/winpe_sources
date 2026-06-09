# RaidUnitSubmitResetRequest

- ea: `0x140033b18`
- end: `0x1400340d6`
- name: `RaidUnitSubmitResetRequest`
- size: `1470`
- prototype: ``
- caller_count: `3`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x140015200`
- `0x140017e80`
- `0x1400c2588`

## callees

- `0x140005c50`
- `0x14000684c`
- `0x14000ff50`
- `0x140012590`
- `0x140017ae8`
- `0x1400290b0`
- `0x140033b18`
- `0x1400340e0`
- `0x14006d1c0`
- `0x14006d298`
- `0x1400848c4`
- `0x1400c5658`
- `0x14014b400`

## import_xrefs

- `ntoskrnl!IoGetActivityIdIrp` at `0x140033c31`
- `ntoskrnl!IoGetActivityIdIrp` at `0x140033c31`
- `ntoskrnl!KeLowerIrql` at `0x14003409d`
- `ntoskrnl!KeLowerIrql` at `0x14003409d`
- `ntoskrnl!KfRaiseIrql` at `0x14003407d`
- `ntoskrnl!KfRaiseIrql` at `0x14003407d`
- `ntoskrnl!IofCompleteRequest` at `0x140033ee0`
- `ntoskrnl!IofCompleteRequest` at `0x140033ee0`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003403c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034061`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x14003403c`
- `ntoskrnl!ExReleaseRundownProtectionCacheAware` at `0x140034061`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140033fb5`
- `ntoskrnl!KeAcquireInStackQueuedSpinLock` at `0x140033fb5`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033f71`
- `ntoskrnl!KeGetCurrentIrql` at `0x140033f71`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003401b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003404e`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003401b`
- `ntoskrnl!KeReleaseInStackQueuedSpinLock` at `0x14003404e`

## pseudocode

```c
__int64 __fastcall RaidUnitSubmitResetRequest(__int64 a1, __int64 a2)
{
  __int64 v2; // rax
  char v3; // r13
  char v4; // bl
  __int64 v7; // r14
  int v8; // eax
  _DWORD *v9; // r8
  __int64 v10; // rax
  __int64 ContiguousIoResources; // rax
  char v12; // al
  bool v13; // zf
  int v14; // ecx
  unsigned __int64 v15; // rcx
  __int64 v16; // rdx
  int *v17; // rax
  int v18; // ecx
  __int64 *v19; // rdx
  __int64 v20; // rdx
  unsigned int v21; // r15d
  unsigned __int8 v22; // r10
  char *v23; // r11
  char v24; // r12
  _BYTE *v25; // r9
  unsigned int v26; // r14d
  unsigned __int64 v27; // rdi
  __int64 v28; // r8
  int v29; // ecx
  char v30; // cl
  char v31; // di
  char v32; // r11
  _BYTE *v33; // rax
  char v34; // r8
  char *v35; // r8
  unsigned int v36; // eax
  KIRQL CurrentIrql; // al
  __int64 v38; // rcx
  __int64 v39; // r8
  KSPIN_LOCK *v40; // rcx
  _QWORD *Pool; // rax
  __int64 v42; // rcx
  __int64 v43; // rdx
  KIRQL v44; // bl
  struct _KLOCK_QUEUE_HANDLE LockHandle; // [rsp+88h] [rbp-1h] BYREF

  v2 = *(_QWORD *)(a2 + 184);
  v3 = 0;
  v4 = 1;
  v7 = *(_QWORD *)(v2 + 8);
  *(_BYTE *)(v2 + 3) |= 1u;
  v8 = *(unsigned __int8 *)(v7 + 2);
  *(_BYTE *)(v7 + 3) = 0;
  if ( (_BYTE)v8 == 40 )
    v8 = *(_DWORD *)(v7 + 20);
  if ( v8 != 16 )
  {
    if ( !_InterlockedCompareExchange((volatile signed __int32 *)(a1 + 1856), 1, 0) )
      goto LABEL_73;
LABEL_9:
    v12 = RaidNtStatusToSrbStatus(3221225626LL);
    v13 = StorEtwLoggingEnabled == 0;
    *(_BYTE *)(v7 + 3) = v12;
    *(_QWORD *)(a2 + 56) = 0;
    *(_BYTE *)(a2 + 141) = -84;
    *(_DWORD *)(a2 + 48) = v14;
    if ( v13 )
      goto LABEL_72;
    LockHandle.LockQueue = 0;
    IoGetActivityIdIrp(a2, &LockHandle);
    v16 = *(_QWORD *)(a2 + 184);
    if ( *(_BYTE *)v16 == 14 )
    {
      if ( (byte_140177432 & 8) == 0 )
        goto LABEL_72;
      v19 = EventNonReadWriteRequestComplete;
      goto LABEL_71;
    }
    if ( *(_BYTE *)v16 != 15 )
    {
      if ( *(_BYTE *)v16 != 27 )
        goto LABEL_72;
      if ( *(_BYTE *)(v16 + 1) == 7 && !*(_DWORD *)(v16 + 8) )
      {
        if ( (byte_140177432 & 0x40) != 0 )
        {
          v17 = *(int **)(a2 + 56);
          if ( v17 )
            v18 = *v17;
          else
            v18 = 0;
          McTemplateK0pqd_EtwWriteTransfer(v18, v16, (unsigned int)&LockHandle, a2, v18, *(_DWORD *)(a2 + 48));
        }
        goto LABEL_72;
      }
      if ( (byte_140177432 & 0x20) == 0 )
        goto LABEL_72;
      v19 = EventPnpRequestComplete;
LABEL_71:
      McTemplateK0pd_EtwWriteTransfer(v15, v19, &LockHandle, a2, *(_DWORD *)(a2 + 48));
      goto LABEL_72;
    }
    if ( byte_140177431 >= 0 )
      goto LABEL_72;
    v20 = *(_QWORD *)(v16 + 8);
    if ( *(_BYTE *)(v20 + 2) == 40 )
    {
      if ( *(_DWORD *)(v20 + 20) )
        goto LABEL_72;
      v21 = *(_DWORD *)(v20 + 56);
      if ( !v21 )
        goto LABEL_72;
      v22 = 0;
      v23 = 0;
      v24 = 0;
      v25 = 0;
      v26 = 0;
      while ( 1 )
      {
        v15 = *(unsigned int *)(v20 + 4LL * v26 + 120);
        if ( (unsigned int)v15 >= 0x80 )
        {
          v27 = *(unsigned int *)(v20 + 16);
          if ( (unsigned int)v15 < (unsigned int)v27 )
          {
            v28 = (unsigned int)v15;
            v29 = *(_DWORD *)(v15 + v20) - 64;
            if ( v29 )
            {
              LODWORD(v15) = v29 - 1;
              if ( (_DWORD)v15 )
              {
                if ( (_DWORD)v15 == 1 )
                {
                  LODWORD(v15) = v28 + 40;
                  if ( v28 + 40 <= v27 )
                  {
                    if ( *(_DWORD *)(v28 + v20 + 12) )
                      v23 = (char *)(v28 + v20 + 32);
                    v25 = *(_BYTE **)(v28 + v20 + 24);
                    goto LABEL_36;
                  }
                }
              }
              else
              {
                LODWORD(v15) = v28 + 56;
                if ( v28 + 56 <= v27 )
                {
                  v3 = 1;
                  if ( *(_BYTE *)(v28 + v20 + 10) )
                    v23 = (char *)(v28 + v20 + 24);
                  v24 = *(_BYTE *)(v28 + v20 + 8);
                  v25 = *(_BYTE **)(v28 + v20 + 16);
                  v22 = *(_BYTE *)(v28 + v20 + 9);
                }
              }
            }
            else
            {
              LODWORD(v15) = v28 + 40;
              if ( v28 + 40 <= v27 )
              {
                if ( *(_BYTE *)(v28 + v20 + 10) )
                  v23 = (char *)(v28 + v20 + 24);
                v25 = *(_BYTE **)(v28 + v20 + 16);
LABEL_36:
                v24 = *(_BYTE *)(v28 + v20 + 8);
                v22 = *(_BYTE *)(v28 + v20 + 9);
LABEL_44:
                if ( v23 )
                {
                  v30 = *v23;
                  goto LABEL_50;
                }
                goto LABEL_72;
              }
            }
            if ( v3 )
              goto LABEL_44;
          }
        }
        if ( ++v26 >= v21 )
          goto LABEL_44;
      }
    }
    v30 = *(_BYTE *)(v20 + 72);
    v25 = *(_BYTE **)(v20 + 32);
    v22 = *(_BYTE *)(v20 + 11);
    v24 = *(_BYTE *)(v20 + 4);
    if ( *(_BYTE *)(v20 + 2) )
      goto LABEL_72;
LABEL_50:
    LOBYTE(v15) = v30 - 8;
    if ( (v15 & 0x5D) != 0 )
    {
LABEL_72:
      IofCompleteRequest((PIRP)a2, 0);
      return 259;
    }
    v31 = *(_BYTE *)(v20 + 3);
    if ( v31 == 1 || !v25 || !v22 )
      goto LABEL_67;
    LOBYTE(v20) = 0;
    v15 = (unsigned __int64)&v25[v22];
    v32 = 0;
    v33 = v25 + 8;
    v34 = 0;
    if ( (unsigned __int8)((*v25 & 0x7F) - 114) <= 1u )
    {
      if ( (unsigned __int64)v33 <= v15 )
      {
        v32 = v25[2];
        LOBYTE(v20) = v25[1] & 0xF;
        v34 = v25[3];
        goto LABEL_66;
      }
    }
    else if ( (unsigned __int64)v33 <= v15 )
    {
      v35 = v25 + 13;
      LOBYTE(v20) = v25[2] & 0xF;
      v36 = v22;
      if ( (unsigned int)(unsigned __int8)v25[7] + 8 <= v22 )
        v36 = (unsigned __int8)v25[7] + 8;
      v15 = (unsigned __int64)&v25[v36];
      if ( (unsigned __int64)v35 <= v15 )
        v32 = v25[12];
      if ( (unsigned __int64)(v25 + 14) > v15 )
        v34 = 0;
      else
        v34 = *v35;
LABEL_66:
      if ( v4 )
      {
LABEL_68:
        McTemplateK0pduuuuup_EtwWriteTransfer(
          v15,
          v20,
          (unsigned int)&LockHandle,
          a2,
          *(_DWORD *)(a2 + 48),
          v31,
          v24,
          v20,
          v32,
          v34,
          a2);
        goto LABEL_72;
      }
LABEL_67:
      LOBYTE(v20) = 0;
      v32 = 0;
      v34 = 0;
      goto LABEL_68;
    }
    v4 = 0;
    goto LABEL_66;
  }
  v9 = *(_DWORD **)(a1 + 24);
  v10 = 81;
  if ( *v9 != 1314275652 )
    v10 = 127;
  ContiguousIoResources = StorAllocateContiguousIoResources(((v9[v10] + 7) & 0xFFFFFFF8) + 1200, a2, v9);
  if ( !ContiguousIoResources )
    goto LABEL_9;
  RaidZeroXrb(ContiguousIoResources + 48, ContiguousIoResources, 0, 0);
LABEL_73:
  if ( (qword_140176450 & 0x20) != 0 )
    DbgLogRequest(
      *(_QWORD *)(a1 + 24),
      3,
      a2,
      (unsigned __int8)BYTE2(*(_DWORD *)(a1 + 104))
    | ((((unsigned __int8)*(_DWORD *)(a1 + 104) << 8) | (unsigned __int8)BYTE1(*(_DWORD *)(a1 + 104))) << 8),
      0,
      0,
      0);
  if ( (*(_BYTE *)(a1 + 505) & 1) != 0 || *(char *)(a1 + 504) < 0 )
    goto LABEL_87;
  CurrentIrql = KeGetCurrentIrql();
  v38 = a1;
  if ( CurrentIrql < 2u )
  {
    v39 = 1;
LABEL_86:
    RaidUnitStartDeviceBusy(v38, a2, v39);
    goto LABEL_87;
  }
  if ( !(unsigned __int8)RaidUnitCheckAndAcquirePoFx(a1) )
  {
LABEL_87:
    v44 = KfRaiseIrql(2u);
    RaUnitStartResetIo(*(_QWORD *)(a1 + 8), a2);
    KeLowerIrql(v44);
    return 259;
  }
  v40 = (KSPIN_LOCK *)(*(_QWORD *)(a1 + 1872) + 96LL);
  memset(&LockHandle, 0, sizeof(LockHandle));
  KeAcquireInStackQueuedSpinLock(v40, &LockHandle);
  if ( (*(_DWORD *)(*(_QWORD *)(a1 + 1872) + 32LL) & 2) != 0
    || (Pool = (_QWORD *)RaidAllocatePool(64, 32, 1330667858, *(_QWORD *)(a1 + 8))) == 0 )
  {
    KeReleaseInStackQueuedSpinLock(&LockHandle);
    ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
    v39 = 0;
    v38 = a1;
    goto LABEL_86;
  }
  Pool[2] = a2;
  v42 = *(_QWORD *)(a1 + 1872) + 80LL;
  v43 = *(_QWORD *)v42;
  if ( *(_QWORD *)(*(_QWORD *)v42 + 8LL) != v42 )
    __fastfail(3u);
  Pool[1] = v42;
  *Pool = v43;
  *(_QWORD *)(v43 + 8) = Pool;
  *(_QWORD *)v42 = Pool;
  KeReleaseInStackQueuedSpinLock(&LockHandle);
  RaidUnitStartDeviceBusy(a1, a2, 0);
  ExReleaseRundownProtectionCacheAware(*(PEX_RUNDOWN_REF_CACHE_AWARE *)(a1 + 1864));
  return 259;
}

```

## disassembly

```asm
0x140033b18  mov     [rsp-8+arg_10], rbx
0x140033b1d  push    rbp
0x140033b1e  push    rsi
0x140033b1f  push    rdi
0x140033b20  push    r12
0x140033b22  push    r13
0x140033b24  push    r14
0x140033b26  push    r15
0x140033b28  lea     rbp, [rsp-27h]
0x140033b2d  sub     rsp, 0B0h
0x140033b34  mov     rax, cs:__security_cookie
0x140033b3b  xor     rax, rsp
0x140033b3e  mov     [rbp+57h+var_40], rax
0x140033b42  xor     eax, eax
0x140033b44  xorps   xmm0, xmm0
0x140033b47  mov     rax, [rdx+0B8h]
0x140033b4e  xor     r13d, r13d
0x140033b51  mov     ebx, 1
0x140033b56  mov     rsi, rdx
0x140033b59  movups  [rbp+57h+var_80], xmm0
0x140033b5d  mov     rdi, rcx
0x140033b60  mov     r14, [rax+8]
0x140033b64  or      [rax+3], bl
0x140033b67  movups  [rbp+57h+var_80+0Ch], xmm0
0x140033b6b  movzx   eax, byte ptr [r14+2]
0x140033b70  mov     [r14+3], r13b
0x140033b74  cmp     al, 28h ; '('
0x140033b76  jnz     short loc_140033B7C
0x140033b78  mov     eax, [r14+14h]
0x140033b7c  cmp     eax, 10h
0x140033b7f  jnz     short loc_140033BEA
0x140033b81  mov     r8, [rcx+18h]
0x140033b85  mov     eax, 144h
0x140033b8a  mov     ecx, 1FCh
0x140033b8f  cmp     dword ptr [r8], 4E564144h
0x140033b96  cmovnz  eax, ecx
0x140033b99  mov     ecx, [rax+r8]
0x140033b9d  add     ecx, 7
0x140033ba0  and     ecx, 0FFFFFFF8h
0x140033ba3  add     ecx, 4B0h
0x140033ba9  call    StorAllocateContiguousIoResources
0x140033bae  mov     rdx, rax
0x140033bb1  test    rax, rax
0x140033bb4  jz      short loc_140033BFA
0x140033bb6  lea     rcx, [rax+30h]
0x140033bba  xor     r9d, r9d
0x140033bbd  add     rax, 3B0h
0x140033bc3  mov     qword ptr [rbp+57h+var_70], rcx
0x140033bc7  mov     qword ptr [rbp+57h+var_70+8], rax
0x140033bcb  xor     r8d, r8d
0x140033bce  lea     rax, [rdx+4B0h]
0x140033bd5  mov     qword ptr [rbp+57h+var_80+8], rax
0x140033bd9  call    RaidZeroXrb
0x140033bde  mov     dword ptr [rbp+57h+var_80], 0FFFFFFFFh
0x140033be5  jmp     loc_140033F07
0x140033bea  xor     eax, eax
0x140033bec  lock cmpxchg [rcx+740h], ebx
0x140033bf4  jz      loc_140033EF1
0x140033bfa  mov     ecx, 0C000009Ah
0x140033bff  call    RaidNtStatusToSrbStatus
0x140033c04  cmp     cs:StorEtwLoggingEnabled, r13b
0x140033c0b  mov     [r14+3], al
0x140033c0f  mov     [rsi+38h], r13
0x140033c13  mov     byte ptr [rsi+8Dh], 0ACh
0x140033c1a  mov     [rsi+30h], ecx
0x140033c1d  jz      loc_140033EDB
0x140033c23  xorps   xmm0, xmm0
0x140033c26  lea     rdx, [rbp+57h+LockHandle]
0x140033c2a  mov     rcx, rsi
0x140033c2d  movups  xmmword ptr [rbp+57h+LockHandle.LockQueue.Next], xmm0
0x140033c31  call    cs:__imp_IoGetActivityIdIrp
0x140033c38  nop     dword ptr [rax+rax+00h]
0x140033c3d  mov     rdx, [rsi+0B8h]
0x140033c44  movzx   eax, byte ptr [rdx]
0x140033c47  sub     eax, 0Eh
0x140033c4a  jz      loc_140033EB8
0x140033c50  sub     eax, ebx
0x140033c52  jz      short loc_140033CBB
0x140033c54  cmp     eax, 0Ch
0x140033c57  jnz     loc_140033EDB
0x140033c5d  cmp     byte ptr [rdx+1], 7
0x140033c61  jnz     short loc_140033CA2
0x140033c63  cmp     [rdx+8], r13d
0x140033c67  jnz     short loc_140033CA2
0x140033c69  test    cs:byte_140177432, 40h
0x140033c70  jz      loc_140033EDB
0x140033c76  mov     rax, [rsi+38h]
0x140033c7a  test    rax, rax
0x140033c7d  jz      short loc_140033C83
0x140033c7f  mov     ecx, [rax]
0x140033c81  jmp     short loc_140033C86
0x140033c83  mov     ecx, r13d
0x140033c86  mov     eax, [rsi+30h]
0x140033c89  lea     r8, [rbp+57h+LockHandle]
0x140033c8d  mov     dword ptr [rsp+0E0h+var_B8], eax
0x140033c91  mov     r9, rsi
0x140033c94  mov     dword ptr [rsp+0E0h+var_C0], ecx
0x140033c98  call    McTemplateK0pqd_EtwWriteTransfer
0x140033c9d  jmp     loc_140033EDB
0x140033ca2  test    cs:byte_140177432, 20h
0x140033ca9  jz      loc_140033EDB
0x140033caf  lea     rdx, EventPnpRequestComplete
0x140033cb6  jmp     loc_140033EC8
0x140033cbb  cmp     cs:byte_140177431, r13b
0x140033cc2  jge     loc_140033EDB
0x140033cc8  mov     rdx, [rdx+8]
0x140033ccc  movzx   eax, byte ptr [rdx+2]
0x140033cd0  cmp     al, 28h ; '('
0x140033cd2  jnz     loc_140033DC1
0x140033cd8  cmp     [rdx+14h], r13d
0x140033cdc  jnz     loc_140033EDB
0x140033ce2  mov     r15d, [rdx+38h]
0x140033ce6  test    r15d, r15d
0x140033ce9  jz      loc_140033EDB
0x140033cef  mov     r10b, r13b
0x140033cf2  mov     r11, r13
0x140033cf5  mov     r12b, r13b
0x140033cf8  mov     r9, r13
0x140033cfb  mov     r14d, r13d
0x140033cfe  mov     eax, r14d
0x140033d01  mov     ecx, [rdx+rax*4+78h]
0x140033d05  cmp     ecx, 80h
0x140033d0b  jb      short loc_140033D8C
0x140033d0d  mov     edi, [rdx+10h]
0x140033d10  cmp     ecx, edi
0x140033d12  jnb     short loc_140033D8C
0x140033d14  mov     r8d, ecx
0x140033d17  mov     ecx, [rcx+rdx]
0x140033d1a  sub     ecx, 40h ; '@'
0x140033d1d  jz      short loc_140033D7E
0x140033d1f  sub     ecx, ebx
0x140033d21  jz      short loc_140033D52
0x140033d23  cmp     ecx, ebx
0x140033d25  jnz     short loc_140033D87
0x140033d27  lea     rcx, [r8+28h]
0x140033d2b  cmp     rcx, rdi
0x140033d2e  ja      short loc_140033D87
0x140033d30  xor     r13d, r13d
0x140033d33  cmp     [r8+rdx+0Ch], r13d
0x140033d38  jbe     short loc_140033D41
0x140033d3a  lea     r11, [rdx+20h]
0x140033d3e  add     r11, r8
0x140033d41  mov     r9, [r8+rdx+18h]
0x140033d46  mov     r12b, [r8+rdx+8]
0x140033d4b  mov     r10b, [r8+rdx+9]
0x140033d50  jmp     short loc_140033D9B
0x140033d52  lea     rcx, [r8+38h]
0x140033d56  cmp     rcx, rdi
0x140033d59  ja      short loc_140033D87
0x140033d5b  cmp     byte ptr [r8+rdx+0Ah], 0
0x140033d61  mov     r13b, bl
0x140033d64  jbe     short loc_140033D6D
0x140033d66  lea     r11, [rdx+18h]
0x140033d6a  add     r11, r8
0x140033d6d  mov     r12b, [r8+rdx+8]
0x140033d72  mov     r9, [r8+rdx+10h]
0x140033d77  mov     r10b, [r8+rdx+9]
0x140033d7c  jmp     short loc_140033D87
0x140033d7e  lea     rcx, [r8+28h]
0x140033d82  cmp     rcx, rdi
0x140033d85  jbe     short loc_140033DA9
0x140033d87  test    r13b, r13b
0x140033d8a  jnz     short loc_140033D98
0x140033d8c  add     r14d, ebx
0x140033d8f  cmp     r14d, r15d
0x140033d92  jb      loc_140033CFE
0x140033d98  xor     r13d, r13d
0x140033d9b  test    r11, r11
0x140033d9e  jz      loc_140033EDB
0x140033da4  mov     cl, [r11]
0x140033da7  jmp     short loc_140033DD8
0x140033da9  xor     r13d, r13d
0x140033dac  cmp     [r8+rdx+0Ah], r13b
0x140033db1  jbe     short loc_140033DBA
0x140033db3  lea     r11, [rdx+18h]
0x140033db7  add     r11, r8
0x140033dba  mov     r9, [r8+rdx+10h]
0x140033dbf  jmp     short loc_140033D46
0x140033dc1  mov     cl, [rdx+48h]
0x140033dc4  mov     r9, [rdx+20h]
0x140033dc8  mov     r10b, [rdx+0Bh]
0x140033dcc  mov     r12b, [rdx+4]
0x140033dd0  test    eax, eax
0x140033dd2  jnz     loc_140033EDB
0x140033dd8  sub     cl, 8
0x140033ddb  test    cl, 5Dh
0x140033dde  jnz     loc_140033EDB
0x140033de4  mov     dil, [rdx+3]
0x140033de8  cmp     dil, bl
0x140033deb  jz      loc_140033E7D
0x140033df1  test    r9, r9
0x140033df4  jz      loc_140033E7D
0x140033dfa  test    r10b, r10b
0x140033dfd  jz      short loc_140033E7D
0x140033dff  mov     al, [r9]
0x140033e02  mov     dl, r13b
0x140033e05  and     al, 7Fh
0x140033e07  movzx   ecx, r10b
0x140033e0b  sub     al, 72h ; 'r'
0x140033e0d  add     rcx, r9
0x140033e10  cmp     al, bl
0x140033e12  mov     r11b, r13b
0x140033e15  lea     rax, [r9+8]
0x140033e19  mov     r8b, r13b
0x140033e1c  jbe     short loc_140033E60
0x140033e1e  cmp     rax, rcx
0x140033e21  ja      short loc_140033E76
0x140033e23  movzx   ecx, byte ptr [r9+7]
0x140033e28  lea     r8, [r9+0Dh]
0x140033e2c  mov     dl, [r9+2]
0x140033e30  add     ecx, 8
0x140033e33  and     dl, 0Fh
0x140033e36  movzx   eax, r10b
0x140033e3a  cmp     ecx, eax
0x140033e3c  cmovbe  eax, ecx
0x140033e3f  mov     ecx, eax
0x140033e41  add     rcx, r9
0x140033e44  cmp     r8, rcx
0x140033e47  ja      short loc_140033E4D
0x140033e49  mov     r11b, [r9+0Ch]
0x140033e4d  lea     rax, [r9+0Eh]
0x140033e51  cmp     rax, rcx
0x140033e54  ja      short loc_140033E5B
0x140033e56  mov     r8b, [r8]
0x140033e59  jmp     short loc_140033E79
0x140033e5b  mov     r8b, r13b
0x140033e5e  jmp     short loc_140033E79
0x140033e60  cmp     rax, rcx
0x140033e63  ja      short loc_140033E76
0x140033e65  mov     dl, [r9+1]
0x140033e69  mov     r11b, [r9+2]
0x140033e6d  and     dl, 0Fh
0x140033e70  mov     r8b, [r9+3]
0x140033e74  jmp     short loc_140033E79
0x140033e76  mov     bl, r13b
0x140033e79  test    bl, bl
0x140033e7b  jnz     short loc_140033E86
0x140033e7d  mov     dl, r13b
0x140033e80  mov     r11b, r13b
0x140033e83  mov     r8b, r13b
0x140033e86  mov     eax, [rsi+30h]
0x140033e89  mov     r9, rsi
0x140033e8c  mov     [rsp+0E0h+var_90], rsi
0x140033e91  mov     [rsp+0E0h+var_98], r8b
0x140033e96  lea     r8, [rbp+57h+LockHandle]
0x140033e9a  mov     [rsp+0E0h+var_A0], r11b
0x140033e9f  mov     [rsp+0E0h+var_A8], dl
0x140033ea3  mov     byte ptr [rsp+0E0h+var_B0], r12b
0x140033ea8  mov     byte ptr [rsp+0E0h+var_B8], dil
0x140033ead  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140033eb1  call    McTemplateK0pduuuuup_EtwWriteTransfer
0x140033eb6  jmp     short loc_140033EDB
0x140033eb8  test    cs:byte_140177432, 8
0x140033ebf  jz      short loc_140033EDB
0x140033ec1  lea     rdx, EventNonReadWriteRequestComplete
0x140033ec8  mov     eax, [rsi+30h]
0x140033ecb  lea     r8, [rbp+57h+LockHandle]
0x140033ecf  mov     r9, rsi
0x140033ed2  mov     dword ptr [rsp+0E0h+var_C0], eax
0x140033ed6  call    McTemplateK0pd_EtwWriteTransfer
0x140033edb  xor     edx, edx; PriorityBoost
0x140033edd  mov     rcx, rsi; Irp
0x140033ee0  call    cs:__imp_IofCompleteRequest
0x140033ee7  nop     dword ptr [rax+rax+00h]
0x140033eec  jmp     loc_1400340A9
0x140033ef1  movups  xmm0, xmmword ptr [rcx+720h]
0x140033ef8  movups  xmm1, xmmword ptr [rcx+730h]
0x140033eff  movups  [rbp+57h+var_80], xmm0
0x140033f03  movups  [rbp+57h+var_70], xmm1
0x140033f07  mov     rax, cs:qword_140176450
0x140033f0e  mov     r14d, 3
0x140033f14  test    al, 20h
0x140033f16  jz      short loc_140033F58
0x140033f18  mov     eax, [rdi+68h]
0x140033f1b  mov     r8, rsi
0x140033f1e  mov     rcx, [rdi+18h]
0x140033f22  mov     edx, eax
0x140033f24  shr     edx, 8
0x140033f27  movzx   r9d, dl
0x140033f2b  movzx   edx, al
0x140033f2e  shl     edx, 8
0x140033f31  or      r9d, edx
0x140033f34  shr     eax, 10h
0x140033f37  movzx   edx, al
0x140033f3a  shl     r9d, 8
0x140033f3e  or      r9, rdx
0x140033f41  mov     [rsp+0E0h+var_B0], r13
0x140033f46  mov     edx, r14d
0x140033f49  mov     [rsp+0E0h+var_B8], r13
0x140033f4e  mov     [rsp+0E0h+var_C0], r13
0x140033f53  call    DbgLogRequest
0x140033f58  test    [rdi+1F9h], bl
0x140033f5e  jnz     loc_14003407B
0x140033f64  cmp     [rdi+1F8h], r13b
0x140033f6b  jl      loc_14003407B
0x140033f71  call    cs:__imp_KeGetCurrentIrql
0x140033f78  nop     dword ptr [rax+rax+00h]
0x140033f7d  mov     rcx, rdi
0x140033f80  cmp     al, 2
0x140033f82  jnb     short loc_140033F8C
  ... truncated ...
```
