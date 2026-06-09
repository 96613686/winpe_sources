# VhdmpiProcessCTLogSrbExtension

- ea: `0x14002b7f0`
- end: `0x14002baae`
- name: `VhdmpiProcessCTLogSrbExtension`
- size: `702`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `1`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x14002ab10`

## callees

- `0x14001c050`
- `0x140023980`
- `0x14002ae7c`
- `0x14002b7f0`
- `0x14002bab4`
- `0x14002c8a4`
- `0x140036284`
- `0x1400b2e6c`

## import_xrefs

- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b92b`
- `ntoskrnl!MmMapLockedPagesSpecifyCache` at `0x14002b92b`
- `ntoskrnl!MmProtectMdlSystemAddress` at `0x14002b95a`
- `ntoskrnl!MmProtectMdlSystemAddress` at `0x14002b95a`
- `ntoskrnl!ExAllocatePool2` at `0x14002b86d`
- `ntoskrnl!ExAllocatePool2` at `0x14002b86d`

## string_xrefs

- `0x14002b8b7`: `VhdmpiProcessCTLogSrbExtension: could not allocate CTLogMetadata`
- `0x14002b8ce`: `VhdmpiProcessCTLogSrbExtension`

## pseudocode

```c
__int64 __fastcall VhdmpiProcessCTLogSrbExtension(unsigned int *P, _BYTE *a2, unsigned __int8 a3)
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
      if ( (unsigned int)dword_1400876D0 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1400876D0, 4096) )
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
0x14002b7f0  mov     [rsp+arg_0], rbx
0x14002b7f5  push    rbp
0x14002b7f6  push    rsi
0x14002b7f7  push    rdi
0x14002b7f8  push    r14
0x14002b7fa  push    r15
0x14002b7fc  sub     rsp, 30h
0x14002b800  mov     [rsp+58h+arg_10], 0
0x14002b808  mov     r14, rdx
0x14002b80b  mov     rbx, rcx
0x14002b80e  test    rdx, rdx
0x14002b811  jz      loc_14002BA95
0x14002b817  test    rcx, rcx
0x14002b81a  jz      loc_14002BA95
0x14002b820  mov     rdi, [rcx+30h]
0x14002b824  test    rdi, rdi
0x14002b827  jz      loc_14002BA95
0x14002b82d  cmp     qword ptr [rdi+1054h], 0
0x14002b835  mov     r15, [rcx+8]
0x14002b839  mov     byte ptr [rdx], 0
0x14002b83c  jnz     short loc_14002B84F
0x14002b83e  mov     eax, [rdi+1154h]
0x14002b844  test    al, 2
0x14002b846  jz      short loc_14002B84F
0x14002b848  mov     byte ptr [rdi+1158h], 1
0x14002b84f  cmp     qword ptr [rdi+1078h], 0
0x14002b857  lea     rsi, [rdi+8Ch]
0x14002b85e  jnz     short loc_14002B8DF
0x14002b860  mov     edx, [rsi]
0x14002b862  mov     ecx, 48h ; 'H'
0x14002b867  mov     r8d, 68444856h
0x14002b86d  call    cs:__imp_ExAllocatePool2
0x14002b874  nop     dword ptr [rax+rax+00h]
0x14002b879  mov     [rdi+1078h], rax
0x14002b880  test    rax, rax
0x14002b883  jnz     short loc_14002B8DF
0x14002b885  mov     eax, cs:dword_1400876D0
0x14002b88b  mov     esi, 0C000009Ah
0x14002b890  cmp     eax, 2
0x14002b893  jbe     loc_14002BA9A
0x14002b899  mov     edx, 1000h
0x14002b89e  lea     rcx, dword_1400876D0
0x14002b8a5  call    _tlgKeywordOn
0x14002b8aa  test    al, al
0x14002b8ac  jz      loc_14002BA9A
0x14002b8b2  mov     ecx, 5C3h
0x14002b8b7  lea     rax, aVhdmpiprocessc_0; "VhdmpiProcessCTLogSrbExtension: could n"...
0x14002b8be  mov     r9d, edx; int
0x14002b8c1  mov     qword ptr [rsp+58h+BugCheckOnFailure], rax; char *
0x14002b8c6  mov     edx, ecx; int
0x14002b8c8  mov     r8d, 2; int
0x14002b8ce  lea     rcx, aVhdmpiprocessc; "VhdmpiProcessCTLogSrbExtension"
0x14002b8d5  call    TraceEvents
0x14002b8da  jmp     loc_14002BA9A
0x14002b8df  mov     eax, [rsi]
0x14002b8e1  sub     rax, 20h ; ' '
0x14002b8e5  shr     rax, 5
0x14002b8e9  cmp     [rdi+105Ch], eax
0x14002b8ef  jz      loc_14002BA8D
0x14002b8f5  cmp     byte ptr [rdi+1158h], 0
0x14002b8fc  jnz     loc_14002BA8D
0x14002b902  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x14002b906  test    byte ptr [rcx+0Ah], 5
0x14002b90a  jz      short loc_14002B912
0x14002b90c  mov     rbp, [rcx+18h]
0x14002b910  jmp     short loc_14002B93A
0x14002b912  xor     r9d, r9d; RequestedAddress
0x14002b915  mov     [rsp+58h+Priority], 40000010h; Priority
0x14002b91d  xor     edx, edx; AccessMode
0x14002b91f  mov     [rsp+58h+BugCheckOnFailure], 0; BugCheckOnFailure
0x14002b927  lea     r8d, [r9+1]; CacheType
0x14002b92b  call    cs:__imp_MmMapLockedPagesSpecifyCache
0x14002b932  nop     dword ptr [rax+rax+00h]
0x14002b937  mov     rbp, rax
0x14002b93a  test    rbp, rbp
0x14002b93d  jz      loc_14002BA95
0x14002b943  mov     rax, [rbx]
0x14002b946  mov     ecx, [rax+860h]
0x14002b94c  test    cl, 20h
0x14002b94f  jz      short loc_14002B966
0x14002b951  mov     rcx, [rbx+18h]; MemoryDescriptorList
0x14002b955  mov     edx, 2; NewProtect
0x14002b95a  call    cs:__imp_MmProtectMdlSystemAddress
0x14002b961  nop     dword ptr [rax+rax+00h]
0x14002b966  mov     edx, [rbx+38h]
0x14002b969  lea     r9, [rsp+58h+arg_8]; unsigned int *
0x14002b96e  mov     eax, [rbx+14h]
0x14002b971  mov     rcx, [rbx+30h]; struct _CTLOG_BACKING_STORE *
0x14002b975  sub     eax, edx
0x14002b977  add     rdx, rbp; void *
0x14002b97a  mov     dword ptr [rsp+58h+arg_8], eax
0x14002b97e  mov     qword ptr [rsp+58h+BugCheckOnFailure], 0; unsigned __int64 *
0x14002b987  call    ?VhdmpiCTWriteBufferSynchronously@@YAJPEAU_CTLOG_BACKING_STORE@@PEAXEPEAKPEA_K@Z; VhdmpiCTWriteBufferSynchronously(_CTLOG_BACKING_STORE *,void *,uchar,ulong *,unsigned __int64 *)
0x14002b98c  mov     esi, eax
0x14002b98e  test    eax, eax
0x14002b990  js      loc_14002BA9A
0x14002b996  mov     ecx, dword ptr [rsp+58h+arg_8]
0x14002b99a  add     [rbx+38h], ecx
0x14002b99d  mov     ecx, [rbx+38h]
0x14002b9a0  cmp     ecx, [rbx+14h]
0x14002b9a3  jnz     loc_14002BA8F
0x14002b9a9  mov     r10d, [rdi+105Ch]
0x14002b9b0  lea     rdx, [rsp+58h+arg_10]
0x14002b9b5  inc     r10
0x14002b9b8  lea     rcx, [rsp+58h+arg_8]
0x14002b9bd  mov     rax, 0FFFFF78000000014h
0x14002b9c7  shl     r10, 5
0x14002b9cb  add     r10, [rdi+1078h]
0x14002b9d2  mov     rax, [rax]
0x14002b9d5  mov     [rsp+58h+arg_8], rax
0x14002b9da  call    VhdmpiTimeToSecondsSince2000
0x14002b9df  mov     [r10], r15
0x14002b9e2  lea     r8, [r10+8]
0x14002b9e6  mov     eax, [rbx+14h]
0x14002b9e9  mov     edx, 20h ; ' '
0x14002b9ee  mov     [r10+0Ch], eax
0x14002b9f2  mov     rcx, r10
0x14002b9f5  mov     eax, [rsp+58h+arg_10]
0x14002b9f9  mov     [r10+10h], eax
0x14002b9fd  mov     byte ptr [r10+14h], 1
0x14002ba02  call    VhdmpiCalculateChecksum
0x14002ba07  mov     [r8], eax
0x14002ba0a  inc     dword ptr [rdi+105Ch]
0x14002ba10  mov     rcx, [rdi+48h]
0x14002ba14  cmp     byte ptr [rcx+841h], 1
0x14002ba1b  jnz     short loc_14002BA31
0x14002ba1d  cmp     byte ptr [rdi+1150h], 0
0x14002ba24  jnz     short loc_14002BA31
0x14002ba26  mov     eax, [rbx+14h]
0x14002ba29  lock add [rcx+830h], rax
0x14002ba31  mov     r10, [rbx+28h]
0x14002ba35  mov     r8d, 4
0x14002ba3b  mov     rax, [r10]
0x14002ba3e  mov     edx, [rax+860h]
0x14002ba44  test    dl, 1
0x14002ba47  jz      short loc_14002BA5C
0x14002ba49  mov     ecx, [r10+3Ch]
0x14002ba4d  cmp     ecx, 1
0x14002ba50  jz      short loc_14002BA68
0x14002ba52  cmp     ecx, r8d
0x14002ba55  jz      short loc_14002BA68
0x14002ba57  cmp     ecx, 7
0x14002ba5a  jz      short loc_14002BA68
0x14002ba5c  test    r8b, dl
0x14002ba5f  jz      short loc_14002BA76
0x14002ba61  cmp     dword ptr [r10+3Ch], 8
0x14002ba66  jnz     short loc_14002BA76
0x14002ba68  xor     r9d, r9d
0x14002ba6b  mov     rdx, rbp
0x14002ba6e  mov     rcx, r10
0x14002ba71  call    VhdmpiWriteSrbToTraceFile
0x14002ba76  or      eax, 0FFFFFFFFh
0x14002ba79  lock xadd [rbx+10h], eax
0x14002ba7e  cmp     eax, 1
0x14002ba81  jnz     short loc_14002BA9A
0x14002ba83  mov     rcx, rbx; P
0x14002ba86  call    VhdmpiCompleteCTLogRequest
0x14002ba8b  jmp     short loc_14002BA9A
0x14002ba8d  xor     esi, esi
0x14002ba8f  mov     byte ptr [r14], 1
0x14002ba93  jmp     short loc_14002BA9A
0x14002ba95  mov     esi, 0C000000Dh
0x14002ba9a  mov     rbx, [rsp+58h+arg_0]
0x14002ba9f  mov     eax, esi
0x14002baa1  add     rsp, 30h
0x14002baa5  pop     r15
0x14002baa7  pop     r14
0x14002baa9  pop     rdi
0x14002baaa  pop     rsi
0x14002baab  pop     rbp
0x14002baac  retn
```
