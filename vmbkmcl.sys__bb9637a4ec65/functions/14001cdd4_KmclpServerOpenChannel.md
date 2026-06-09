# KmclpServerOpenChannel

- ea: `0x14001cdd4`
- end: `0x14001d37b`
- name: `KmclpServerOpenChannel`
- size: `1447`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: ``

## callers

- `0x14000e9e0`
- `0x14001c758`

## callees

- `0x140007d58`
- `0x14000ab90`
- `0x14000e414`
- `0x14000f5c4`
- `0x140011a4c`
- `0x140011d18`
- `0x140011e90`
- `0x140011ed0`
- `0x14001cdd4`

## import_xrefs

- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001d09f`
- `ntoskrnl!KeQueryNodeActiveAffinity` at `0x14001d09f`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d0ba`
- `ntoskrnl!KeSetSystemGroupAffinityThread` at `0x14001d0ba`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d315`
- `ntoskrnl!KeRevertToUserGroupAffinityThread` at `0x14001d315`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001cf82`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14001cf82`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d067`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001d067`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d07f`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001d07f`

## pseudocode

```c
__int64 __fastcall KmclpServerOpenChannel(__int64 a1, __int64 a2, __int64 a3)
{
  char v3; // r15
  int v5; // eax
  __int64 v6; // r8
  int v7; // ebx
  __int64 v8; // rdx
  __int64 v9; // r8
  PMDL v10; // rcx
  ULONG ByteCount; // ebx
  int v12; // esi
  ULONG v13; // ebx
  unsigned int v14; // ebx
  PVOID MappedSystemVa; // r10
  bool v16; // zf
  __int64 v17; // r8
  PDEVICE_OBJECT v18; // rcx
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // rcx
  __int64 v23; // r8
  PMDL MemoryDescriptorList; // [rsp+40h] [rbp-40h] BYREF
  __int64 v26; // [rsp+48h] [rbp-38h] BYREF
  int v27; // [rsp+50h] [rbp-30h]
  struct _GROUP_AFFINITY Affinity; // [rsp+58h] [rbp-28h] BYREF
  struct _GROUP_AFFINITY PreviousAffinity; // [rsp+68h] [rbp-18h] BYREF

  v26 = 0;
  v27 = 0;
  v3 = 0;
  MemoryDescriptorList = 0;
  Affinity = 0;
  PreviousAffinity = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 82, a3, a1, *(_DWORD *)(a1 + 2200));
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, __int64 *))(a1 + 2400))(*(_QWORD *)(a1 + 2368), &v26);
  v7 = v5;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 83, v6, a1, v5);
  }
  if ( v7 < 0 )
    goto LABEL_63;
  v8 = (unsigned int)v26;
  *(_WORD *)(a1 + 3272) = v27;
  v3 = 1;
  v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, __int64, PMDL *))(a1 + 2464))(
         *(_QWORD *)(a1 + 2368),
         v8,
         2,
         &MemoryDescriptorList);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 84, v9, a1, v7);
  }
  if ( v7 < 0 )
    goto LABEL_63;
  v10 = MemoryDescriptorList;
  *(_DWORD *)(a1 + 3096) = v26;
  if ( v10->ByteOffset
    || (ByteCount = v10->ByteCount, (ByteCount & 0xFFF) != 0)
    || (v12 = HIDWORD(v26), v13 = ByteCount >> 12, HIDWORD(v26) >= v13)
    || HIDWORD(v26) < 2
    || (v14 = v13 - HIDWORD(v26), v14 < 2) )
  {
    v7 = -1073741811;
    goto LABEL_63;
  }
  if ( (v10->MdlFlags & 5) != 0 )
    MappedSystemVa = v10->MappedSystemVa;
  else
    MappedSystemVa = MmMapLockedPagesSpecifyCache(v10, 0, MmCached, 0, 0, 0x40000010u);
  *(_QWORD *)(a1 + 2704) = MappedSystemVa;
  if ( !MappedSystemVa )
  {
    v7 = -1073741670;
    goto LABEL_63;
  }
  v16 = *(_BYTE *)(a1 + 1729) == 0;
  *(_DWORD *)(a1 + 2712) = v12;
  *(_DWORD *)(a1 + 2716) = v14;
  if ( v16 )
  {
    v7 = PkInitializeRingBuffer(
           (void *)(a1 + 64),
           (__int64)MappedSystemVa + (unsigned int)(v12 << 12),
           (__int64)MappedSystemVa + (unsigned int)(v12 << 12) + 4096,
           v14 - 1);
    if ( v7 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v19 = 85;
LABEL_31:
        WPP_SF_qd(v18->AttachedDevice, v19, v17, a1, v7);
        goto LABEL_63;
      }
      goto LABEL_63;
    }
    PkSetInterruptMaskSkipCount(a1 + 64, a1 + 488);
  }
  ExAcquirePushLockExclusiveEx(a1 + 2808, 0);
  *(_BYTE *)(a1 + 2806) = 1;
  ExReleasePushLockExclusiveEx(a1 + 2808, 0);
  if ( !*(_BYTE *)(a1 + 1729) )
  {
    KeQueryNodeActiveAffinity(v27, &Affinity, 0);
    if ( Affinity.Mask )
      KeSetSystemGroupAffinityThread(&Affinity, &PreviousAffinity);
    v7 = InOpenChannel(a1);
    if ( v7 < 0 )
    {
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
      {
        v19 = 86;
        goto LABEL_31;
      }
LABEL_63:
      KmclpTeardownOpenChannelState(a1);
      if ( !v3 )
        goto LABEL_72;
      goto LABEL_64;
    }
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 87, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, a1);
  }
  if ( *(_BYTE *)(a1 + 2024) )
    v20 = (*(__int64 (__fastcall **)(__int64, _QWORD))(a1 + 2048))(a1, *(_QWORD *)(a1 + 2040));
  else
    v20 = (*(__int64 (__fastcall **)(__int64))(a1 + 2040))(a1);
  v7 = v20;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 88, v17, a1, v20);
  }
  if ( v7 < 0 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) >= 2u )
    {
      v19 = 89;
      goto LABEL_31;
    }
    goto LABEL_63;
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 90, v17, a1, v7);
  }
  *(_DWORD *)(a1 + 2200) = 4;
  v21 = _InterlockedIncrement((volatile signed __int32 *)(a1 + 3296)) % 24;
  v22 = v21 + 207;
  v21 *= 2;
  *(_QWORD *)(a1 + 8 * v21 + 3304) = MEMORY[0xFFFFF78000000008];
  *(_BYTE *)(a1 + 16 * v22) = *(_BYTE *)(a1 + 2200);
  *(_BYTE *)(a1 + 8 * v21 + 3313) = *(_BYTE *)(a1 + 2204);
  *(_WORD *)(a1 + 8 * v21 + 3314) = *(_DWORD *)(a1 + 2216);
  *(_WORD *)(a1 + 8 * v21 + 3316) = 3146;
  *(_BYTE *)(a1 + 2344) |= 0x10u;
  v7 = 0;
LABEL_64:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 91, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, a1);
  }
  (*(void (__fastcall **)(_QWORD, _QWORD))(a1 + 2408))(*(_QWORD *)(a1 + 2368), (unsigned int)v7);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 92, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids, a1);
  }
LABEL_72:
  KeRevertToUserGroupAffinityThread(&PreviousAffinity);
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qd(WPP_GLOBAL_Control->AttachedDevice, 93, v23, a1, v7);
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14001cdd4  mov     [rsp-28h+arg_8], rbx
0x14001cdd9  mov     [rsp-28h+arg_10], rsi
0x14001cdde  push    rbp
0x14001cddf  push    rdi
0x14001cde0  push    r12
0x14001cde2  push    r14
0x14001cde4  push    r15
0x14001cde6  mov     rbp, rsp
0x14001cde9  sub     rsp, 80h
0x14001cdf0  mov     rax, cs:__security_cookie
0x14001cdf7  xor     rax, rsp
0x14001cdfa  mov     [rbp+var_8], rax
0x14001cdfe  xor     eax, eax
0x14001ce00  xorps   xmm0, xmm0
0x14001ce03  xorps   xmm1, xmm1
0x14001ce06  mov     [rbp+var_38], rax
0x14001ce0a  mov     [rbp+var_30], eax
0x14001ce0d  xor     r15b, r15b
0x14001ce10  mov     [rbp+MemoryDescriptorList], rax
0x14001ce14  mov     rdi, rcx
0x14001ce17  movups  xmmword ptr [rbp+Affinity.Mask], xmm0
0x14001ce1b  movups  xmmword ptr [rbp+PreviousAffinity.Mask], xmm1
0x14001ce1f  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce26  lea     r14, WPP_GLOBAL_Control
0x14001ce2d  lea     r12d, [rax+1]
0x14001ce31  cmp     rcx, r14
0x14001ce34  jz      short loc_14001CE5F
0x14001ce36  mov     eax, [rcx+2Ch]
0x14001ce39  test    r12b, al
0x14001ce3c  jz      short loc_14001CE5F
0x14001ce3e  cmp     byte ptr [rcx+29h], 4
0x14001ce42  jb      short loc_14001CE5F
0x14001ce44  mov     eax, [rdi+898h]
0x14001ce4a  lea     edx, [r12+51h]
0x14001ce4f  mov     rcx, [rcx+18h]
0x14001ce53  mov     r9, rdi
0x14001ce56  mov     [rsp+80h+BugCheckOnFailure], eax
0x14001ce5a  call    WPP_SF_qd
0x14001ce5f  mov     rax, [rdi+960h]
0x14001ce66  lea     rdx, [rbp+var_38]
0x14001ce6a  mov     rcx, [rdi+940h]
0x14001ce71  call    _guard_dispatch_icall
0x14001ce76  mov     ebx, eax
0x14001ce78  mov     rcx, cs:WPP_GLOBAL_Control
0x14001ce7f  cmp     rcx, r14
0x14001ce82  jz      short loc_14001CEA7
0x14001ce84  mov     edx, [rcx+2Ch]
0x14001ce87  test    r12b, dl
0x14001ce8a  jz      short loc_14001CEA7
0x14001ce8c  cmp     byte ptr [rcx+29h], 4
0x14001ce90  jb      short loc_14001CEA7
0x14001ce92  mov     rcx, [rcx+18h]
0x14001ce96  mov     edx, 53h ; 'S'
0x14001ce9b  mov     r9, rdi
0x14001ce9e  mov     [rsp+80h+BugCheckOnFailure], eax
0x14001cea2  call    WPP_SF_qd
0x14001cea7  test    ebx, ebx
0x14001cea9  js      loc_14001D28B
0x14001ceaf  movzx   eax, word ptr [rbp+var_30]
0x14001ceb3  lea     r9, [rbp+MemoryDescriptorList]
0x14001ceb7  mov     edx, dword ptr [rbp+var_38]
0x14001ceba  mov     r8d, 2
0x14001cec0  mov     [rdi+0CC8h], ax
0x14001cec7  mov     r15b, r12b
0x14001ceca  mov     rax, [rdi+9A0h]
0x14001ced1  mov     rcx, [rdi+940h]
0x14001ced8  call    _guard_dispatch_icall
0x14001cedd  mov     ebx, eax
0x14001cedf  mov     rcx, cs:WPP_GLOBAL_Control
0x14001cee6  cmp     rcx, r14
0x14001cee9  jz      short loc_14001CF0E
0x14001ceeb  mov     eax, [rcx+2Ch]
0x14001ceee  test    r12b, al
0x14001cef1  jz      short loc_14001CF0E
0x14001cef3  cmp     byte ptr [rcx+29h], 4
0x14001cef7  jb      short loc_14001CF0E
0x14001cef9  mov     rcx, [rcx+18h]
0x14001cefd  mov     edx, 54h ; 'T'
0x14001cf02  mov     r9, rdi
0x14001cf05  mov     [rsp+80h+BugCheckOnFailure], ebx
0x14001cf09  call    WPP_SF_qd
0x14001cf0e  test    ebx, ebx
0x14001cf10  js      loc_14001D28B
0x14001cf16  mov     rcx, [rbp+MemoryDescriptorList]; MemoryDescriptorList
0x14001cf1a  mov     eax, dword ptr [rbp+var_38]
0x14001cf1d  mov     [rdi+0C18h], eax
0x14001cf23  cmp     dword ptr [rcx+2Ch], 0
0x14001cf27  jnz     loc_14001D286
0x14001cf2d  mov     ebx, [rcx+28h]
0x14001cf30  test    ebx, 0FFFh
0x14001cf36  jnz     loc_14001D286
0x14001cf3c  mov     esi, dword ptr [rbp+var_38+4]
0x14001cf3f  shr     ebx, 0Ch
0x14001cf42  cmp     esi, ebx
0x14001cf44  jnb     loc_14001D286
0x14001cf4a  cmp     esi, 2
0x14001cf4d  jb      loc_14001D286
0x14001cf53  sub     ebx, esi
0x14001cf55  cmp     ebx, 2
0x14001cf58  jb      loc_14001D286
0x14001cf5e  test    byte ptr [rcx+0Ah], 5
0x14001cf62  jz      short loc_14001CF6A
0x14001cf64  mov     r10, [rcx+18h]
0x14001cf68  jmp     short loc_14001CF91
0x14001cf6a  mov     [rsp+80h+Priority], 40000010h; Priority
0x14001cf72  xor     r9d, r9d; RequestedAddress
0x14001cf75  mov     r8d, r12d; CacheType
0x14001cf78  mov     [rsp+80h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14001cf80  xor     edx, edx; AccessMode
0x14001cf82  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14001cf89  nop     dword ptr [rax+rax+00h]
0x14001cf8e  mov     r10, rax
0x14001cf91  mov     [rdi+0A90h], r10
0x14001cf98  test    r10, r10
0x14001cf9b  jnz     short loc_14001CFA7
0x14001cf9d  mov     ebx, 0C000009Ah
0x14001cfa2  jmp     loc_14001D28B
0x14001cfa7  cmp     byte ptr [rdi+6C1h], 0
0x14001cfae  mov     [rdi+0A98h], esi
0x14001cfb4  mov     [rdi+0A9Ch], ebx
0x14001cfba  jnz     loc_14001D05B
0x14001cfc0  mov     edx, esi
0x14001cfc2  lea     eax, [rbx-1]
0x14001cfc5  shl     edx, 0Ch
0x14001cfc8  lea     r9d, [rsi-1]
0x14001cfcc  add     rdx, r10
0x14001cfcf  mov     [rsp+80h+var_50], eax; int
0x14001cfd3  lea     r8, [r10+1000h]
0x14001cfda  lea     rcx, [rdx+1000h]
0x14001cfe1  mov     qword ptr [rsp+80h+Priority], rcx; __int64
0x14001cfe6  lea     rcx, [rdi+40h]; void *
0x14001cfea  mov     qword ptr [rsp+80h+BugCheckOnFailure], rdx; __int64
0x14001cfef  mov     rdx, r10
0x14001cff2  call    PkInitializeRingBuffer
0x14001cff7  mov     ebx, eax
0x14001cff9  test    eax, eax
0x14001cffb  jns     short loc_14001D044
0x14001cffd  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d004  lea     r14, WPP_GLOBAL_Control
0x14001d00b  cmp     rcx, r14
0x14001d00e  jz      loc_14001D28B
0x14001d014  mov     eax, [rcx+2Ch]
0x14001d017  test    r12b, al
0x14001d01a  jz      loc_14001D28B
0x14001d020  cmp     byte ptr [rcx+29h], 2
0x14001d024  jb      loc_14001D28B
0x14001d02a  mov     edx, 55h ; 'U'
0x14001d02f  mov     rcx, [rcx+18h]
0x14001d033  mov     r9, rdi
0x14001d036  mov     [rsp+80h+BugCheckOnFailure], ebx
0x14001d03a  call    WPP_SF_qd
0x14001d03f  jmp     loc_14001D28B
0x14001d044  lea     rdx, [rdi+1E8h]
0x14001d04b  lea     rcx, [rdi+40h]
0x14001d04f  call    PkSetInterruptMaskSkipCount
0x14001d054  lea     r14, WPP_GLOBAL_Control
0x14001d05b  lea     rbx, [rdi+0AF8h]
0x14001d062  xor     edx, edx
0x14001d064  mov     rcx, rbx
0x14001d067  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001d06e  nop     dword ptr [rax+rax+00h]
0x14001d073  xor     edx, edx
0x14001d075  mov     [rdi+0AF6h], r12b
0x14001d07c  mov     rcx, rbx
0x14001d07f  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001d086  nop     dword ptr [rax+rax+00h]
0x14001d08b  cmp     byte ptr [rdi+6C1h], 0
0x14001d092  jnz     short loc_14001D104
0x14001d094  movzx   ecx, word ptr [rbp+var_30]; NodeNumber
0x14001d098  lea     rdx, [rbp+Affinity]; Affinity
0x14001d09c  xor     r8d, r8d; Count
0x14001d09f  call    cs:__imp_KeQueryNodeActiveAffinity
0x14001d0a6  nop     dword ptr [rax+rax+00h]
0x14001d0ab  cmp     [rbp+Affinity.Mask], 0
0x14001d0b0  jz      short loc_14001D0C6
0x14001d0b2  lea     rdx, [rbp+PreviousAffinity]; PreviousAffinity
0x14001d0b6  lea     rcx, [rbp+Affinity]; Affinity
0x14001d0ba  call    cs:__imp_KeSetSystemGroupAffinityThread
0x14001d0c1  nop     dword ptr [rax+rax+00h]
0x14001d0c6  mov     rcx, rdi
0x14001d0c9  call    InOpenChannel
0x14001d0ce  mov     ebx, eax
0x14001d0d0  test    eax, eax
0x14001d0d2  jns     short loc_14001D104
0x14001d0d4  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d0db  cmp     rcx, r14
0x14001d0de  jz      loc_14001D28B
0x14001d0e4  mov     eax, [rcx+2Ch]
0x14001d0e7  test    r12b, al
0x14001d0ea  jz      loc_14001D28B
0x14001d0f0  cmp     byte ptr [rcx+29h], 2
0x14001d0f4  jb      loc_14001D28B
0x14001d0fa  mov     edx, 56h ; 'V'
0x14001d0ff  jmp     loc_14001D02F
0x14001d104  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d10b  cmp     rcx, r14
0x14001d10e  jz      short loc_14001D136
0x14001d110  mov     eax, [rcx+2Ch]
0x14001d113  test    r12b, al
0x14001d116  jz      short loc_14001D136
0x14001d118  cmp     byte ptr [rcx+29h], 4
0x14001d11c  jb      short loc_14001D136
0x14001d11e  mov     rcx, [rcx+18h]
0x14001d122  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
0x14001d129  mov     edx, 57h ; 'W'
0x14001d12e  mov     r9, rdi
0x14001d131  call    WPP_SF_q
0x14001d136  cmp     byte ptr [rdi+7E8h], 0
0x14001d13d  mov     rcx, rdi
0x14001d140  jz      short loc_14001D157
0x14001d142  mov     rax, [rdi+800h]
0x14001d149  mov     rdx, [rdi+7F8h]
0x14001d150  call    _guard_dispatch_icall
0x14001d155  jmp     short loc_14001D163
0x14001d157  mov     rax, [rdi+7F8h]
0x14001d15e  call    _guard_dispatch_icall
0x14001d163  mov     ebx, eax
0x14001d165  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d16c  cmp     rcx, r14
0x14001d16f  jz      short loc_14001D194
0x14001d171  mov     eax, [rcx+2Ch]
0x14001d174  test    r12b, al
0x14001d177  jz      short loc_14001D194
0x14001d179  cmp     byte ptr [rcx+29h], 4
0x14001d17d  jb      short loc_14001D194
0x14001d17f  mov     rcx, [rcx+18h]
0x14001d183  mov     edx, 58h ; 'X'
0x14001d188  mov     r9, rdi
0x14001d18b  mov     [rsp+80h+BugCheckOnFailure], ebx
0x14001d18f  call    WPP_SF_qd
0x14001d194  test    ebx, ebx
0x14001d196  jns     short loc_14001D1C8
0x14001d198  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d19f  cmp     rcx, r14
0x14001d1a2  jz      loc_14001D28B
0x14001d1a8  mov     eax, [rcx+2Ch]
0x14001d1ab  test    r12b, al
0x14001d1ae  jz      loc_14001D28B
0x14001d1b4  cmp     byte ptr [rcx+29h], 2
0x14001d1b8  jb      loc_14001D28B
0x14001d1be  mov     edx, 59h ; 'Y'
0x14001d1c3  jmp     loc_14001D02F
0x14001d1c8  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d1cf  cmp     rcx, r14
0x14001d1d2  jz      short loc_14001D1F7
0x14001d1d4  mov     eax, [rcx+2Ch]
0x14001d1d7  test    r12b, al
0x14001d1da  jz      short loc_14001D1F7
0x14001d1dc  cmp     byte ptr [rcx+29h], 4
0x14001d1e0  jb      short loc_14001D1F7
0x14001d1e2  mov     rcx, [rcx+18h]
0x14001d1e6  mov     edx, 5Ah ; 'Z'
0x14001d1eb  mov     r9, rdi
0x14001d1ee  mov     [rsp+80h+BugCheckOnFailure], ebx
0x14001d1f2  call    WPP_SF_qd
0x14001d1f7  mov     dword ptr [rdi+898h], 4
0x14001d201  mov     ecx, r12d
0x14001d204  lock xadd [rdi+0CE0h], ecx
0x14001d20c  add     ecx, r12d
0x14001d20f  mov     eax, 2AAAAAABh
0x14001d214  imul    ecx
0x14001d216  sar     edx, 2
0x14001d219  mov     eax, edx
0x14001d21b  shr     eax, 1Fh
0x14001d21e  add     edx, eax
0x14001d220  lea     eax, [rdx+rdx*2]
0x14001d223  shl     eax, 3
0x14001d226  sub     ecx, eax
0x14001d228  mov     rax, ds:0FFFFF78000000008h
0x14001d232  movsxd  rcx, ecx
0x14001d235  mov     rdx, rcx
0x14001d238  add     rcx, 0CFh
0x14001d23f  add     rdx, rdx
0x14001d242  add     rcx, rcx
0x14001d245  mov     [rdi+rdx*8+0CE8h], rax
0x14001d24d  mov     al, [rdi+898h]
0x14001d253  mov     [rdi+rcx*8], al
0x14001d256  mov     al, [rdi+89Ch]
0x14001d25c  mov     [rdi+rdx*8+0CF1h], al
0x14001d263  mov     eax, [rdi+8A8h]
0x14001d269  mov     [rdi+rdx*8+0CF2h], ax
0x14001d271  mov     word ptr [rdi+rdx*8+0CF4h], 0C4Ah
0x14001d27b  or      byte ptr [rdi+928h], 10h
0x14001d282  xor     ebx, ebx
0x14001d284  jmp     short loc_14001D298
0x14001d286  mov     ebx, 0C000000Dh
0x14001d28b  mov     rcx, rdi
0x14001d28e  call    KmclpTeardownOpenChannelState
0x14001d293  test    r15b, r15b
0x14001d296  jz      short loc_14001D311
0x14001d298  mov     rcx, cs:WPP_GLOBAL_Control
0x14001d29f  cmp     rcx, r14
0x14001d2a2  jz      short loc_14001D2CA
0x14001d2a4  mov     eax, [rcx+2Ch]
0x14001d2a7  test    r12b, al
0x14001d2aa  jz      short loc_14001D2CA
0x14001d2ac  cmp     byte ptr [rcx+29h], 4
0x14001d2b0  jb      short loc_14001D2CA
0x14001d2b2  mov     rcx, [rcx+18h]
0x14001d2b6  lea     r8, WPP_fa014546bb113ca58de70d4b381949e7_Traceguids
  ... truncated ...
```
