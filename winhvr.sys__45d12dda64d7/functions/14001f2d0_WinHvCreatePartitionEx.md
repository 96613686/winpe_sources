# WinHvCreatePartitionEx

- ea: `0x14001f2d0`
- end: `0x14001f738`
- name: `WinHvCreatePartitionEx`
- size: `1128`
- prototype: ``
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops`

## callers

- `0x14001f260`
- `0x14001f740`

## callees

- `0x140001008`
- `0x140001038`
- `0x140007310`
- `0x1400077f8`
- `0x140007828`
- `0x140008ef0`
- `0x140009c50`
- `0x14000b008`
- `0x14000b040`
- `0x14001f2d0`
- `0x14001ffd0`
- `0x140020130`
- `0x14002078c`
- `0x140022af0`

## import_xrefs

- `ntoskrnl!KeGenericCallDpc` at `0x14001f649`
- `ntoskrnl!KeGenericCallDpc` at `0x14001f649`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f411`
- `ntoskrnl!KeEnterCriticalRegion` at `0x14001f411`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001f426`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001f426`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f579`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f628`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f579`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14001f628`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f585`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f634`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f585`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14001f634`
- `HAL!KeQueryPerformanceCounter` at `0x14001f538`
- `HAL!KeQueryPerformanceCounter` at `0x14001f538`

## string_xrefs

- `0x14001f69e`: `WinHvCreatePartitionEx`

## pseudocode

```c
__int64 __fastcall WinHvCreatePartitionEx(
        char a1,
        __int64 a2,
        int a3,
        int a4,
        __int64 a5,
        __int64 a6,
        _QWORD *a7,
        __int64 a8,
        __int64 a9,
        __int64 a10,
        __int64 a11)
{
  char v13; // bl
  _QWORD *v14; // rsi
  volatile signed __int64 *v15; // r12
  int Partition; // edi
  __int16 v17; // bx
  __int64 v18; // r13
  int PartitionObject; // eax
  __int64 v20; // rdx
  __int64 v21; // r8
  __int64 v22; // r9
  int v23; // ebx
  int *Pool; // rax
  __int64 v25; // r15
  int v26; // edx
  int i; // edx
  __int64 v28; // r8
  int v29; // ecx
  int v30; // r9d
  __int64 v31; // r10
  __int64 v32; // rbx
  volatile signed __int64 *v33; // rax
  __int64 v34; // rcx
  __int64 v35; // rcx
  __int16 v37; // [rsp+50h] [rbp-A1h] BYREF
  _QWORD *v38; // [rsp+58h] [rbp-99h] BYREF
  volatile signed __int64 *v39; // [rsp+60h] [rbp-91h] BYREF
  _QWORD *v40; // [rsp+68h] [rbp-89h] BYREF
  __int64 v41; // [rsp+70h] [rbp-81h]
  char v42[8]; // [rsp+78h] [rbp-79h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v43; // [rsp+80h] [rbp-71h] BYREF
  const char *v44; // [rsp+A0h] [rbp-51h]
  __int64 v45; // [rsp+A8h] [rbp-49h]
  __int16 *v46; // [rsp+B0h] [rbp-41h]
  __int64 v47; // [rsp+B8h] [rbp-39h]
  _QWORD *v48; // [rsp+C0h] [rbp-31h]
  __int64 v49; // [rsp+C8h] [rbp-29h]
  _QWORD **v50; // [rsp+D0h] [rbp-21h]
  __int64 v51; // [rsp+D8h] [rbp-19h]

  v40 = a7;
  v13 = a2;
  v14 = 0;
  v15 = 0;
  v38 = 0;
  v39 = 0;
  if ( (a2 & 0xFFFFFFFFFFFFFFF8uLL) != 0 )
  {
    Partition = -1073741811;
    v17 = 1208;
    goto LABEL_48;
  }
  v18 = 0;
  v41 = a2 & 4;
  if ( (a2 & 4) != 0 )
  {
    v14 = (_QWORD *)*a7;
    if ( (int)WinHvGetMemoryBalance(*a7, 2147549183LL, v42, &v38) < 0 )
    {
      Partition = -1070268409;
      v17 = 1245;
      goto LABEL_43;
    }
  }
  else
  {
    Partition = WinHvpCreatePartition(a1, a3, a4, a5, a6, 0, (__int64)&v38);
    if ( Partition < 0 )
    {
      v14 = v38;
      v17 = 1225;
      goto LABEL_36;
    }
    v14 = v38;
  }
  PartitionObject = WinHvpCreatePartitionObject((_DWORD)v14, a3, a8, a9, a10, a11, a1, v13, (__int64)&v39);
  v15 = v39;
  Partition = PartitionObject;
  if ( PartitionObject < 0 )
  {
    v17 = 1262;
    goto LABEL_35;
  }
  KeEnterCriticalRegion();
  ExAcquirePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
  if ( WinHvpPartitionArray )
    v23 = *(_DWORD *)WinHvpPartitionArray + 1;
  else
    v23 = 1;
  Pool = (int *)WinHvpAllocatePool(66, 16LL * v23 + 8, 1098270807);
  v25 = (__int64)Pool;
  if ( !Pool )
  {
    Partition = -1073741670;
    v17 = 1306;
    goto LABEL_34;
  }
  *Pool = v23;
  if ( v23 == 1 )
  {
    v26 = 0;
LABEL_24:
    v28 = WinHvpPartitionArray;
    v17 = 1197;
    if ( !WinHvpPartitionArray )
    {
LABEL_40:
      v33 = v39;
      v15 = 0;
      v34 = 2LL * v26;
      *(_QWORD *)(v25 + 8 * v34 + 8) = v14;
      *(_QWORD *)(v25 + 8 * v34 + 16) = v33;
      v18 = WinHvpPartitionArray;
      WinHvpPartitionArray = v25;
      if ( v41 )
        WinHvpRemoveUnlinkedPartitionId(v14);
      ExReleasePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
      KeLeaveCriticalRegion();
      KeGenericCallDpc(WinHvpSynchronizationDpc, 0);
      Partition = 0;
      *v40 = v14;
      goto LABEL_43;
    }
    v29 = 0;
    v30 = 0;
    while ( 1 )
    {
      if ( v29 == v26 )
        goto LABEL_38;
      v31 = 2LL * v30++;
      if ( *(_QWORD *)(v28 + 8 * v31 + 16) )
        break;
      --*Pool;
      --v26;
LABEL_39:
      v28 = WinHvpPartitionArray;
      if ( v30 >= *(_DWORD *)WinHvpPartitionArray )
        goto LABEL_40;
    }
    *(_OWORD *)&Pool[4 * v29 + 2] = *(_OWORD *)(v28 + 8 * v31 + 8);
LABEL_38:
    ++v29;
    goto LABEL_39;
  }
  for ( i = v23 - 2; ; --i )
  {
    if ( i <= -1 )
    {
LABEL_23:
      v26 = i + 1;
      goto LABEL_24;
    }
    if ( *(_QWORD **)(WinHvpPartitionArray + 16LL * i + 8) == v14 )
      break;
    if ( *(_QWORD *)(WinHvpPartitionArray + 16LL * i + 8) < (unsigned __int64)v14 )
      goto LABEL_23;
  }
  Partition = -1073741270;
  if ( *(_QWORD *)&WinHvpBlackbox )
  {
    v32 = 2LL * (_InterlockedExchangeAdd((volatile signed __int32 *)(*(_QWORD *)&WinHvpBlackbox + 4LL), 1u) & 0x3F);
    *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v32 + 8) = 6;
    *(_DWORD *)(*(_QWORD *)&WinHvpBlackbox + 8 * v32 + 12) = (_DWORD)v14;
    *(LARGE_INTEGER *)(*(_QWORD *)&WinHvpBlackbox + 8 * v32 + 16) = KeQueryPerformanceCounter(0);
  }
  if ( _InterlockedDecrement64(v15) <= -1 )
    __fastfail(0xEu);
  v18 = v25;
  v17 = 1366;
LABEL_34:
  ExReleasePushLockExclusiveEx(&WinHvpPartitionArrayLock, 0);
  KeLeaveCriticalRegion();
LABEL_35:
  if ( !v41 )
  {
LABEL_36:
    WinHvFinalizePartition(v14);
    WinHvWithdrawAllMemoryWithCount(v14, 0);
    WinHvpDeleteHvPartition(v14);
  }
LABEL_43:
  if ( v15 )
    WinHvpDeletePartitionObject(v15, v20, v21, v22);
  if ( v18 )
    WinHvpFreePoolWithTag(v18, 1098270807);
  if ( Partition < 0 )
  {
LABEL_48:
    if ( (unsigned int)dword_140011000 > 2 && (unsigned __int8)tlgKeywordOn() )
    {
      v45 = 23;
      v44 = "WinHvCreatePartitionEx";
      v37 = v17;
      v46 = &v37;
      v47 = 2;
      v48 = &v38;
      LODWORD(v38) = Partition;
      v50 = &v40;
      v49 = 4;
      v40 = v14;
      v51 = 8;
      tlgWriteTransfer_EtwWriteTransfer(v35, (unsigned __int8 *)&byte_14000E957, 0, 0, 6u, &v43);
    }
  }
  return (unsigned int)Partition;
}

```

## disassembly

```asm
0x14001f2d0  push    rbp
0x14001f2d2  push    rbx
0x14001f2d3  push    rsi
0x14001f2d4  push    rdi
0x14001f2d5  push    r12
0x14001f2d7  push    r13
0x14001f2d9  push    r14
0x14001f2db  push    r15
0x14001f2dd  lea     rbp, [rsp-7]
0x14001f2e2  sub     rsp, 0F8h
0x14001f2e9  mov     rax, cs:__security_cookie
0x14001f2f0  xor     rax, rsp
0x14001f2f3  mov     [rbp+3Fh+var_50], rax
0x14001f2f7  mov     r14, rcx
0x14001f2fa  mov     r10d, r9d
0x14001f2fd  mov     rcx, [rbp+3Fh+arg_30]
0x14001f301  mov     r15d, r8d
0x14001f304  mov     [rsp+130h+var_C8], rcx
0x14001f309  mov     rbx, rdx
0x14001f30c  xor     esi, esi
0x14001f30e  xor     r12d, r12d
0x14001f311  mov     [rsp+130h+var_D8], rsi
0x14001f316  mov     [rsp+130h+var_D0], r12
0x14001f31b  test    rdx, 0FFFFFFFFFFFFFFF8h
0x14001f322  jz      short loc_14001F333
0x14001f324  mov     edi, 0C000000Dh
0x14001f329  mov     ebx, 4B8h
0x14001f32e  jmp     loc_14001F686
0x14001f333  mov     rax, rbx
0x14001f336  xor     r13d, r13d
0x14001f339  and     eax, 4
0x14001f33c  mov     [rsp+130h+var_C0], rax
0x14001f341  jnz     loc_14001F3E5
0x14001f347  mov     r9, [rbp+3Fh+arg_20]
0x14001f34b  lea     rax, [rsp+130h+var_D8]
0x14001f350  mov     [rsp+130h+var_100], rax
0x14001f355  mov     r8d, r10d
0x14001f358  mov     rax, [rbp+3Fh+arg_28]
0x14001f35c  mov     edx, r15d
0x14001f35f  mov     byte ptr [rsp+130h+var_108], sil
0x14001f364  mov     rcx, r14
0x14001f367  mov     [rsp+130h+var_110], rax
0x14001f36c  call    WinHvpCreatePartition
0x14001f371  mov     edi, eax
0x14001f373  test    eax, eax
0x14001f375  jns     short loc_14001F386
0x14001f377  mov     rsi, [rsp+130h+var_D8]
0x14001f37c  mov     ebx, 4C9h
0x14001f381  jmp     loc_14001F5A5
0x14001f386  mov     rsi, [rsp+130h+var_D8]
0x14001f38b  mov     r9, [rbp+3Fh+arg_40]
0x14001f392  lea     rax, [rsp+130h+var_D0]
0x14001f397  mov     r8, [rbp+3Fh+arg_38]
0x14001f39e  mov     edx, r15d
0x14001f3a1  mov     [rsp+130h+var_F0], rax
0x14001f3a6  mov     rcx, rsi
0x14001f3a9  mov     rax, [rbp+3Fh+arg_50]
0x14001f3b0  mov     [rsp+130h+var_F8], rbx
0x14001f3b5  mov     [rsp+130h+var_100], r14
0x14001f3ba  mov     [rsp+130h+var_108], rax
0x14001f3bf  mov     rax, [rbp+3Fh+arg_48]
0x14001f3c6  mov     [rsp+130h+var_110], rax
0x14001f3cb  call    WinHvpCreatePartitionObject
0x14001f3d0  mov     r12, [rsp+130h+var_D0]
0x14001f3d5  mov     edi, eax
0x14001f3d7  test    eax, eax
0x14001f3d9  jns     short loc_14001F411
0x14001f3db  mov     ebx, 4EEh
0x14001f3e0  jmp     loc_14001F599
0x14001f3e5  mov     rsi, [rcx]
0x14001f3e8  lea     r9, [rsp+130h+var_D8]
0x14001f3ed  mov     rcx, rsi
0x14001f3f0  lea     r8, [rbp+3Fh+var_B8]
0x14001f3f4  mov     edx, 8000FFFFh
0x14001f3f9  call    WinHvGetMemoryBalance
0x14001f3fe  test    eax, eax
0x14001f400  jns     short loc_14001F38B
0x14001f402  mov     edi, 0C0350007h
0x14001f407  mov     ebx, 4DDh
0x14001f40c  jmp     loc_14001F65F
0x14001f411  call    cs:__imp_KeEnterCriticalRegion
0x14001f418  nop     dword ptr [rax+rax+00h]
0x14001f41d  xor     edx, edx
0x14001f41f  lea     rcx, WinHvpPartitionArrayLock
0x14001f426  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14001f42d  nop     dword ptr [rax+rax+00h]
0x14001f432  mov     rbx, cs:WinHvpPartitionArray
0x14001f439  mov     r14d, 1
0x14001f43f  test    rbx, rbx
0x14001f442  jnz     short loc_14001F449
0x14001f444  mov     ebx, r14d
0x14001f447  jmp     short loc_14001F44E
0x14001f449  mov     ebx, [rbx]
0x14001f44b  add     ebx, r14d
0x14001f44e  movsxd  rdx, ebx
0x14001f451  mov     ecx, 42h ; 'B'
0x14001f456  shl     rdx, 4
0x14001f45a  mov     r8d, 41764857h
0x14001f460  add     rdx, 8
0x14001f464  call    WinHvpAllocatePool
0x14001f469  mov     r15, rax
0x14001f46c  test    rax, rax
0x14001f46f  jnz     short loc_14001F480
0x14001f471  mov     edi, 0C000009Ah
0x14001f476  mov     ebx, 51Ah
0x14001f47b  jmp     loc_14001F570
0x14001f480  or      r13, 0FFFFFFFFFFFFFFFFh
0x14001f484  mov     [rax], ebx
0x14001f486  cmp     ebx, r14d
0x14001f489  jnz     short loc_14001F48F
0x14001f48b  xor     edx, edx
0x14001f48d  jmp     short loc_14001F4B5
0x14001f48f  lea     edx, [rbx-2]
0x14001f492  jmp     short loc_14001F4AD
0x14001f494  mov     rax, cs:WinHvpPartitionArray
0x14001f49b  movsxd  rcx, edx
0x14001f49e  add     rcx, rcx
0x14001f4a1  cmp     [rax+rcx*8+8], rsi
0x14001f4a6  jz      short loc_14001F4F7
0x14001f4a8  jb      short loc_14001F4B2
0x14001f4aa  sub     edx, r14d
0x14001f4ad  cmp     edx, r13d
0x14001f4b0  jg      short loc_14001F494
0x14001f4b2  add     edx, r14d
0x14001f4b5  mov     r8, cs:WinHvpPartitionArray
0x14001f4bc  mov     ebx, 4ADh
0x14001f4c1  test    r8, r8
0x14001f4c4  jz      loc_14001F5EA
0x14001f4ca  xor     ecx, ecx
0x14001f4cc  xor     r9d, r9d
0x14001f4cf  cmp     ecx, edx
0x14001f4d1  jz      loc_14001F5D7
0x14001f4d7  movsxd  r10, r9d
0x14001f4da  add     r10, r10
0x14001f4dd  inc     r9d
0x14001f4e0  cmp     qword ptr [r8+r10*8+10h], 0
0x14001f4e6  jnz     loc_14001F5C4
0x14001f4ec  add     [r15], r13d
0x14001f4ef  sub     edx, r14d
0x14001f4f2  jmp     loc_14001F5DA
0x14001f4f7  mov     rcx, cs:WinHvpBlackbox
0x14001f4fe  mov     edi, 0C000022Ah
0x14001f503  test    rcx, rcx
0x14001f506  jz      short loc_14001F550
0x14001f508  mov     ebx, r14d
0x14001f50b  lock xadd [rcx+4], ebx
0x14001f510  mov     rax, cs:WinHvpBlackbox
0x14001f517  add     ebx, r14d
0x14001f51a  sub     ebx, r14d
0x14001f51d  xor     ecx, ecx; PerformanceFrequency
0x14001f51f  and     ebx, 3Fh
0x14001f522  add     rbx, rbx
0x14001f525  mov     dword ptr [rax+rbx*8+8], 6
0x14001f52d  mov     rax, cs:WinHvpBlackbox
0x14001f534  mov     [rax+rbx*8+0Ch], esi
0x14001f538  call    cs:__imp_KeQueryPerformanceCounter
0x14001f53f  nop     dword ptr [rax+rax+00h]
0x14001f544  mov     rcx, cs:WinHvpBlackbox
0x14001f54b  mov     [rcx+rbx*8+10h], rax
0x14001f550  mov     rax, r13
0x14001f553  lock xadd [r12], rax
0x14001f559  add     rax, r13
0x14001f55c  cmp     rax, r13
0x14001f55f  jg      short loc_14001F568
0x14001f561  mov     ecx, 0Eh
0x14001f566  int     29h; Win8: RtlFailFast(ecx)
0x14001f568  mov     r13, r15
0x14001f56b  mov     ebx, 556h
0x14001f570  xor     edx, edx
0x14001f572  lea     rcx, WinHvpPartitionArrayLock
0x14001f579  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001f580  nop     dword ptr [rax+rax+00h]
0x14001f585  call    cs:__imp_KeLeaveCriticalRegion
0x14001f58c  nop     dword ptr [rax+rax+00h]
0x14001f591  test    edi, edi
0x14001f593  jns     loc_14001F65F
0x14001f599  cmp     [rsp+130h+var_C0], 0
0x14001f59f  jnz     loc_14001F65F
0x14001f5a5  mov     rcx, rsi
0x14001f5a8  call    WinHvFinalizePartition
0x14001f5ad  xor     edx, edx
0x14001f5af  mov     rcx, rsi
0x14001f5b2  call    WinHvWithdrawAllMemoryWithCount
0x14001f5b7  mov     rcx, rsi
0x14001f5ba  call    WinHvpDeleteHvPartition
0x14001f5bf  jmp     loc_14001F65F
0x14001f5c4  movups  xmm0, xmmword ptr [r8+r10*8+8]
0x14001f5ca  movsxd  rax, ecx
0x14001f5cd  add     rax, rax
0x14001f5d0  movdqu  xmmword ptr [r15+rax*8+8], xmm0
0x14001f5d7  add     ecx, r14d
0x14001f5da  mov     r8, cs:WinHvpPartitionArray
0x14001f5e1  cmp     r9d, [r8]
0x14001f5e4  jl      loc_14001F4CF
0x14001f5ea  mov     rax, [rsp+130h+var_D0]
0x14001f5ef  xor     r12d, r12d
0x14001f5f2  movsxd  rcx, edx
0x14001f5f5  add     rcx, rcx
0x14001f5f8  mov     [r15+rcx*8+8], rsi
0x14001f5fd  mov     [r15+rcx*8+10h], rax
0x14001f602  mov     r13, cs:WinHvpPartitionArray
0x14001f609  mov     cs:WinHvpPartitionArray, r15
0x14001f610  cmp     [rsp+130h+var_C0], r12
0x14001f615  jz      short loc_14001F61F
0x14001f617  mov     rcx, rsi
0x14001f61a  call    WinHvpRemoveUnlinkedPartitionId
0x14001f61f  xor     edx, edx
0x14001f621  lea     rcx, WinHvpPartitionArrayLock
0x14001f628  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14001f62f  nop     dword ptr [rax+rax+00h]
0x14001f634  call    cs:__imp_KeLeaveCriticalRegion
0x14001f63b  nop     dword ptr [rax+rax+00h]
0x14001f640  xor     edx, edx
0x14001f642  lea     rcx, WinHvpSynchronizationDpc
0x14001f649  call    cs:__imp_KeGenericCallDpc
0x14001f650  nop     dword ptr [rax+rax+00h]
0x14001f655  mov     rax, [rsp+130h+var_C8]
0x14001f65a  xor     edi, edi
0x14001f65c  mov     [rax], rsi
0x14001f65f  test    r12, r12
0x14001f662  jz      short loc_14001F66C
0x14001f664  mov     rcx, r12
0x14001f667  call    WinHvpDeletePartitionObject
0x14001f66c  test    r13, r13
0x14001f66f  jz      short loc_14001F67E
0x14001f671  mov     edx, 41764857h
0x14001f676  mov     rcx, r13
0x14001f679  call    WinHvpFreePoolWithTag
0x14001f67e  test    edi, edi
0x14001f680  jns     loc_14001F715
0x14001f686  mov     eax, cs:dword_140011000
0x14001f68c  cmp     eax, 2
0x14001f68f  jbe     loc_14001F715
0x14001f695  call    _tlgKeywordOn
0x14001f69a  test    al, al
0x14001f69c  jz      short loc_14001F715
0x14001f69e  lea     rax, aWinhvcreatepar; "WinHvCreatePartitionEx"
0x14001f6a5  mov     [rbp+3Fh+var_88], 17h
0x14001f6ad  mov     [rbp+3Fh+var_90], rax
0x14001f6b1  lea     rdx, byte_14000E957
0x14001f6b8  lea     rax, [rsp+130h+var_E0]
0x14001f6bd  mov     [rsp+130h+var_E0], bx
0x14001f6c2  mov     [rbp+3Fh+var_80], rax
0x14001f6c6  xor     r9d, r9d
0x14001f6c9  lea     rax, [rsp+130h+var_D8]
0x14001f6ce  mov     [rbp+3Fh+var_78], 2
0x14001f6d6  mov     [rbp+3Fh+var_70], rax
0x14001f6da  xor     r8d, r8d
0x14001f6dd  lea     rax, [rsp+130h+var_C8]
0x14001f6e2  mov     dword ptr [rsp+130h+var_D8], edi
0x14001f6e6  mov     [rbp+3Fh+var_60], rax
0x14001f6ea  lea     rax, [rbp+3Fh+var_B0]
0x14001f6ee  mov     [rsp+130h+var_108], rax
0x14001f6f3  mov     dword ptr [rsp+130h+var_110], 6
0x14001f6fb  mov     [rbp+3Fh+var_68], 4
0x14001f703  mov     [rsp+130h+var_C8], rsi
0x14001f708  mov     [rbp+3Fh+var_58], 8
0x14001f710  call    _tlgWriteTransfer_EtwWriteTransfer
0x14001f715  mov     eax, edi
0x14001f717  mov     rcx, [rbp+3Fh+var_50]
0x14001f71b  xor     rcx, rsp; StackCookie
0x14001f71e  call    __security_check_cookie
0x14001f723  add     rsp, 0F8h
0x14001f72a  pop     r15
0x14001f72c  pop     r14
0x14001f72e  pop     r13
0x14001f730  pop     r12
0x14001f732  pop     rdi
0x14001f733  pop     rsi
0x14001f734  pop     rbx
0x14001f735  pop     rbp
0x14001f736  retn
```
