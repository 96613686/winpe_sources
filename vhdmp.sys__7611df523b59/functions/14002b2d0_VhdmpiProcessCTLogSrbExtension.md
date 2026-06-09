# VhdmpiProcessCTLogSrbExtension

- ea: `0x14002b2d0`
- end: `0x14002b58e`
- name: `VhdmpiProcessCTLogSrbExtension`
- size: `702`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002a5f0`

## callees

- `0x14001bc30`
- `0x140023560`
- `0x14002a95c`
- `0x14002b2d0`
- `0x14002b594`
- `0x14002c384`
- `0x140035e94`
- `0x1400b2e6c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b40b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b40b`
- `ntoskrnl!MmProtectMdlSystemAddress` at `0x14002b43a`
- `ntoskrnl!MmProtectMdlSystemAddress` at `0x14002b43a`
- `ntoskrnl!ExAllocatePool2` at `0x14002b34d`
- `ntoskrnl!ExAllocatePool2` at `0x14002b34d`

## string_xrefs

- `0x14002b3ae`: `VhdmpiProcessCTLogSrbExtension`
- `0x14002b397`: `VhdmpiProcessCTLogSrbExtension: could not allocate CTLogMetadata`

## pseudocode

```c
__int64 __fastcall VhdmpiProcessCTLogSrbExtension(unsigned int *P, _BYTE *a2, __int64 a3)
{
  __int64 v5; // rdi
  bool v6; // zf
  __int64 v7; // r15
  unsigned int *v8; // rsi
  __int64 Pool2; // rax
  unsigned int v10; // esi
  unsigned int v11; // edx
  __int64 v12; // rcx
  char *v13; // rbp
  __int64 v14; // rdx
  struct _CTLOG_BACKING_STORE *v15; // rcx
  __int64 v16; // r10
  int v17; // eax
  _DWORD *v18; // r8
  __int64 v19; // rcx
  _DWORD *v20; // r10
  int v21; // edx
  int v22; // ecx
  __int64 v24; // [rsp+68h] [rbp+10h] BYREF
  int v25; // [rsp+70h] [rbp+18h] BYREF

  v25 = 0;
  if ( !a2 )
    return (unsigned int)-1073741811;
  if ( !P )
    return (unsigned int)-1073741811;
  v5 = *((_QWORD *)P + 6);
  if ( !v5 )
    return (unsigned int)-1073741811;
  v6 = *(_QWORD *)(v5 + 4180) == 0;
  v7 = *((_QWORD *)P + 1);
  *a2 = 0;
  if ( v6 && (*(_DWORD *)(v5 + 4436) & 2) != 0 )
    *(_BYTE *)(v5 + 4440) = 1;
  v8 = (unsigned int *)(v5 + 140);
  if ( !*(_QWORD *)(v5 + 4216) )
  {
    Pool2 = ExAllocatePool2(72, *v8, 1749305430);
    *(_QWORD *)(v5 + 4216) = Pool2;
    if ( !Pool2 )
    {
      v10 = -1073741670;
      if ( (unsigned int)dword_140087708 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140087708, 4096) )
        TraceEvents(
          "VhdmpiProcessCTLogSrbExtension",
          0x5C3u,
          2u,
          v11,
          "VhdmpiProcessCTLogSrbExtension: could not allocate CTLogMetadata");
      return v10;
    }
  }
  if ( *(_DWORD *)(v5 + 4188) == (unsigned int)(((unsigned __int64)*v8 - 32) >> 5) || *(_BYTE *)(v5 + 4440) )
  {
    v10 = 0;
    goto LABEL_35;
  }
  v12 = *((_QWORD *)P + 3);
  v13 = (*(_BYTE *)(v12 + 10) & 5) != 0
      ? *(char **)(v12 + 24)
      : (char *)MmMapLockedPagesSpecifyCache((PMDL)v12, 0, MmCached, 0, 0, 0x40000010u);
  if ( !v13 )
    return (unsigned int)-1073741811;
  if ( (*(_DWORD *)(*(_QWORD *)P + 2144LL) & 0x20) != 0 )
    MmProtectMdlSystemAddress(*((PMDL *)P + 3), 2u);
  v14 = P[14];
  v15 = (struct _CTLOG_BACKING_STORE *)*((_QWORD *)P + 6);
  LODWORD(v24) = P[5] - v14;
  v10 = VhdmpiCTWriteBufferSynchronously(v15, &v13[v14], a3, (unsigned int *)&v24, 0);
  if ( (v10 & 0x80000000) == 0 )
  {
    P[14] += v24;
    if ( P[14] == P[5] )
    {
      v24 = MEMORY[0xFFFFF78000000014];
      VhdmpiTimeToSecondsSince2000(&v24, &v25);
      *(_QWORD *)v16 = v7;
      *(_DWORD *)(v16 + 12) = P[5];
      *(_DWORD *)(v16 + 16) = v25;
      *(_BYTE *)(v16 + 20) = 1;
      v17 = VhdmpiCalculateChecksum(v16, 32, v16 + 8);
      *v18 = v17;
      ++*(_DWORD *)(v5 + 4188);
      v19 = *(_QWORD *)(v5 + 72);
      if ( *(_BYTE *)(v19 + 2113) == 1 && !*(_BYTE *)(v5 + 4432) )
        _InterlockedAdd64((volatile signed __int64 *)(v19 + 2096), P[5]);
      v20 = (_DWORD *)*((_QWORD *)P + 5);
      v21 = *(_DWORD *)(*(_QWORD *)v20 + 2144LL);
      if ( (v21 & 1) != 0 && ((v22 = v20[15], v22 == 1) || v22 == 4 || v22 == 7) || (v21 & 4) != 0 && v20[15] == 8 )
        VhdmpiWriteSrbToTraceFile(*((__int64 **)P + 5), v13, 4, 0);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)P + 4, 0xFFFFFFFF) == 1 )
        VhdmpiCompleteCTLogRequest(P);
      return v10;
    }
LABEL_35:
    *a2 = 1;
  }
  return v10;
}

```

## disassembly

```asm
0x14002b2d0  mov     [rsp+arg_0], rbx
0x14002b2d5  push    rbp
0x14002b2d6  push    rsi
0x14002b2d7  push    rdi
0x14002b2d8  push    r14
0x14002b2da  push    r15
0x14002b2dc  sub     rsp, 30h
0x14002b2e0  mov     [rsp+58h+arg_10], 0
0x14002b2e8  mov     r14, rdx
0x14002b2eb  mov     rbx, rcx
0x14002b2ee  test    rdx, rdx
0x14002b2f1  jz      loc_14002B575
0x14002b2f7  test    rcx, rcx
0x14002b2fa  jz      loc_14002B575
0x14002b300  mov     rdi, [rcx+30h]
0x14002b304  test    rdi, rdi
0x14002b307  jz      loc_14002B575
0x14002b30d  cmp     qword ptr [rdi+1054h], 0
0x14002b315  mov     r15, [rcx+8]
0x14002b319  mov     byte ptr [rdx], 0
0x14002b31c  jnz     short loc_14002B32F
0x14002b31e  mov     eax, [rdi+1154h]
0x14002b324  test    al, 2
0x14002b326  jz      short loc_14002B32F
0x14002b328  mov     byte ptr [rdi+1158h], 1
0x14002b32f  cmp     qword ptr [rdi+1078h], 0
0x14002b337  lea     rsi, [rdi+8Ch]
0x14002b33e  jnz     short loc_14002B3BF
0x14002b340  mov     edx, [rsi]
0x14002b342  mov     ecx, 48h ; 'H'
0x14002b347  mov     r8d, 68444856h
0x14002b34d  call    cs:__imp_ExAllocatePool2
0x14002b354  nop     dword ptr [rax+rax+00h]
0x14002b359  mov     [rdi+1078h], rax
0x14002b360  test    rax, rax
0x14002b363  jnz     short loc_14002B3BF
0x14002b365  mov     eax, cs:dword_140087708
0x14002b36b  mov     esi, 0C000009Ah
0x14002b370  cmp     eax, 2
0x14002b373  jbe     loc_14002B57A
0x14002b379  mov     edx, 1000h
0x14002b37e  lea     rcx, dword_140087708
0x14002b385  call    _tlgKeywordOn
0x14002b38a  test    al, al
0x14002b38c  jz      loc_14002B57A
0x14002b392  mov     ecx, 5C3h
0x14002b397  lea     rax, aVhdmpiprocessc_0; "VhdmpiProcessCTLogSrbExtension: could n"...
0x14002b39e  mov     r9d, edx; int
0x14002b3a1  mov     qword ptr [rsp+58h+BugCheckOnFailure], rax; char *
0x14002b3a6  mov     edx, ecx; int
0x14002b3a8  mov     r8d, 2; int
0x14002b3ae  lea     rcx, aVhdmpiprocessc; "VhdmpiProcessCTLogSrbExtension"
0x14002b3b5  call    TraceEvents
0x14002b3ba  jmp     loc_14002B57A
0x14002b3bf  mov     eax, [rsi]
0x14002b3c1  sub     rax, 20h ; ' '
0x14002b3c5  shr     rax, 5
0x14002b3c9  cmp     [rdi+105Ch], eax
0x14002b3cf  jz      loc_14002B56D
0x14002b3d5  cmp     byte ptr [rdi+1158h], 0
0x14002b3dc  jnz     loc_14002B56D
0x14002b3e2  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x14002b3e6  test    byte ptr [rcx+0Ah], 5
0x14002b3ea  jz      short loc_14002B3F2
0x14002b3ec  mov     rbp, [rcx+18h]
0x14002b3f0  jmp     short loc_14002B41A
0x14002b3f2  xor     r9d, r9d; RequestedAddress
0x14002b3f5  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002b3fd  xor     edx, edx; AccessMode
0x14002b3ff  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002b407  lea     r8d, [r9+1]; CacheType
0x14002b40b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002b412  nop     dword ptr [rax+rax+00h]
0x14002b417  mov     rbp, rax
0x14002b41a  test    rbp, rbp
0x14002b41d  jz      loc_14002B575
0x14002b423  mov     rax, [rbx]
0x14002b426  mov     ecx, [rax+860h]
0x14002b42c  test    cl, 20h
0x14002b42f  jz      short loc_14002B446
0x14002b431  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x14002b435  mov     edx, 2; NewProtect
0x14002b43a  call    cs:__imp_MmProtectMdlSystemAddress
0x14002b441  nop     dword ptr [rax+rax+00h]
0x14002b446  mov     edx, [rbx+38h]
0x14002b449  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x14002b44e  mov     eax, [rbx+14h]
0x14002b451  mov     rcx, [rbx+30h]; struct _CTLOG_BACKING_STORE *
0x14002b455  sub     eax, edx
0x14002b457  add     rdx, rbp; void *
0x14002b45a  mov     dword ptr [rsp+58h+arg_8], eax
0x14002b45e  mov     qword ptr [rsp+58h+BugCheckOnFailure], 0; unsigned __int64 *
0x14002b467  call    ?VhdmpiCTWriteBufferSynchronously@@YAJPEAU_CTLOG_BACKING_STORE@@PEAXEPEAKPEA_K@Z; VhdmpiCTWriteBufferSynchronously(_CTLOG_BACKING_STORE *,void *,uchar,ulong *,unsigned __int64 *)
0x14002b46c  mov     esi, eax
0x14002b46e  test    eax, eax
0x14002b470  js      loc_14002B57A
0x14002b476  mov     ecx, dword ptr [rsp+58h+arg_8]
0x14002b47a  add     [rbx+38h], ecx
0x14002b47d  mov     ecx, [rbx+38h]
0x14002b480  cmp     ecx, [rbx+14h]
0x14002b483  jnz     loc_14002B56F
0x14002b489  mov     r10d, [rdi+105Ch]
0x14002b490  lea     rdx, [rsp+58h+arg_10]
0x14002b495  inc     r10
0x14002b498  lea     rcx, [rsp+58h+arg_8]
0x14002b49d  mov     rax, 0FFFFF78000000014h
0x14002b4a7  shl     r10, 5
0x14002b4ab  add     r10, [rdi+1078h]
0x14002b4b2  mov     rax, [rax]
0x14002b4b5  mov     [rsp+58h+arg_8], rax
0x14002b4ba  call    VhdmpiTimeToSecondsSince2000
0x14002b4bf  mov     [r10], r15
0x14002b4c2  lea     r8, [r10+8]
0x14002b4c6  mov     eax, [rbx+14h]
0x14002b4c9  mov     edx, 20h ; ' '
0x14002b4ce  mov     [r10+0Ch], eax
0x14002b4d2  mov     rcx, r10
0x14002b4d5  mov     eax, [rsp+58h+arg_10]
0x14002b4d9  mov     [r10+10h], eax
0x14002b4dd  mov     byte ptr [r10+14h], 1
0x14002b4e2  call    VhdmpiCalculateChecksum
0x14002b4e7  mov     [r8], eax
0x14002b4ea  inc     dword ptr [rdi+105Ch]
0x14002b4f0  mov     rcx, [rdi+48h]
0x14002b4f4  cmp     byte ptr [rcx+841h], 1
0x14002b4fb  jnz     short loc_14002B511
0x14002b4fd  cmp     byte ptr [rdi+1150h], 0
0x14002b504  jnz     short loc_14002B511
0x14002b506  mov     eax, [rbx+14h]
0x14002b509  lock add [rcx+830h], rax
0x14002b511  mov     r10, [rbx+28h]
0x14002b515  mov     r8d, 4
0x14002b51b  mov     rax, [r10]
0x14002b51e  mov     edx, [rax+860h]
0x14002b524  test    dl, 1
0x14002b527  jz      short loc_14002B53C
0x14002b529  mov     ecx, [r10+3Ch]
0x14002b52d  cmp     ecx, 1
0x14002b530  jz      short loc_14002B548
0x14002b532  cmp     ecx, r8d
0x14002b535  jz      short loc_14002B548
0x14002b537  cmp     ecx, 7
0x14002b53a  jz      short loc_14002B548
0x14002b53c  test    r8b, dl
0x14002b53f  jz      short loc_14002B556
0x14002b541  cmp     dword ptr [r10+3Ch], 8
0x14002b546  jnz     short loc_14002B556
0x14002b548  xor     r9d, r9d
0x14002b54b  mov     rdx, rbp
0x14002b54e  mov     rcx, r10
0x14002b551  call    VhdmpiWriteSrbToTraceFile
0x14002b556  or      eax, 0FFFFFFFFh
0x14002b559  lock xadd [rbx+10h], eax
0x14002b55e  cmp     eax, 1
0x14002b561  jnz     short loc_14002B57A
0x14002b563  mov     rcx, rbx; P
0x14002b566  call    VhdmpiCompleteCTLogRequest
0x14002b56b  jmp     short loc_14002B57A
0x14002b56d  xor     esi, esi
0x14002b56f  mov     byte ptr [r14], 1
0x14002b573  jmp     short loc_14002B57A
0x14002b575  mov     esi, 0C000000Dh
0x14002b57a  mov     rbx, [rsp+58h+arg_0]
0x14002b57f  mov     eax, esi
0x14002b581  add     rsp, 30h
0x14002b585  pop     r15
0x14002b587  pop     r14
0x14002b589  pop     rdi
0x14002b58a  pop     rsi
0x14002b58b  pop     rbp
0x14002b58c  retn
```
