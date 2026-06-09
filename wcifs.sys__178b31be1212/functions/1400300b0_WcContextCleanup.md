# WcContextCleanup

- ea: `0x1400300b0`
- end: `0x1400302c4`
- name: `WcContextCleanup`
- size: `532`
- prototype: `void __fastcall(__int64, __int16)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002048`
- `0x14001c5d8`
- `0x14001d56c`
- `0x140029cc8`
- `0x14002eea4`
- `0x1400300b0`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400301d4`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x1400301d4`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301f2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301f2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003015c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003021f`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003015c`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003021f`
- `ntoskrnl!ExDeleteResourceLite` at `0x140030127`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400302a7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140030127`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400302a7`
- `ntoskrnl!ExReleaseFastMutex` at `0x140030194`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003026e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140030194`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003026e`
- `FLTMGR!FltReleaseContext` at `0x140030101`
- `FLTMGR!FltReleaseContext` at `0x140030140`
- `FLTMGR!FltReleaseContext` at `0x1400301b8`
- `FLTMGR!FltReleaseContext` at `0x140030101`
- `FLTMGR!FltReleaseContext` at `0x140030140`
- `FLTMGR!FltReleaseContext` at `0x1400301b8`

## pseudocode

```c
void __fastcall WcContextCleanup(__int64 a1, __int16 a2)
{
  void *v3; // rcx
  struct _RTL_DYNAMIC_HASH_TABLE *v4; // rcx
  __int64 v5; // rsi
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  void *v8; // rdx
  void *v9; // rcx
  int *v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rdx
  __int64 v13; // rcx

  switch ( a2 )
  {
    case 2:
      if ( byte_14000E680 )
      {
        v10 = (int *)P;
        if ( P )
        {
          ExAcquireFastMutex(&FastMutex);
          v11 = *(_QWORD *)(a1 + 32);
          v12 = 3LL * *v10;
          *(_QWORD *)&v10[v12 + 1] = *(_QWORD *)v11;
          v10[v12 + 3] = *(_DWORD *)(v11 + 8);
          *v10 = (*v10 + 1) % 3;
          ExReleaseFastMutex(&FastMutex);
        }
      }
      v13 = *(_QWORD *)(a1 + 56);
      if ( v13 )
      {
        WcReleaseUnionContext(v13);
      }
      else if ( *(_DWORD *)(a1 + 64) )
      {
        WcClearUnionTable((PRTL_AVL_TABLE)(a1 + 176));
        *(_DWORD *)(a1 + 64) = 0;
      }
      ExDeleteResourceLite((PERESOURCE)(a1 + 72));
      break;
    case 4:
      FltReleaseContext(*(PFLT_CONTEXT *)a1);
      v8 = *(void **)(a1 + 80);
      if ( v8 )
        ExFreeToNPagedLookasideList(&stru_14000E580, v8);
      v9 = *(void **)(a1 + 64);
      if ( v9 )
        ExFreePoolWithTag(v9, 0x69724357u);
      break;
    case 8:
      v4 = *(struct _RTL_DYNAMIC_HASH_TABLE **)(a1 + 256);
      if ( v4 )
        WcFreeInMemoryTombstoneHashTable(v4);
      ExDeleteResourceLite((PERESOURCE)(a1 + 120));
      WcFreeSourceList(a1 + 56);
      FltReleaseContext(*(PFLT_CONTEXT *)(a1 + 32));
      if ( *(_QWORD *)a1 != a1 )
      {
        v5 = *(_QWORD *)(a1 + 40);
        ExAcquireFastMutex((PFAST_MUTEX)(v5 + 200));
        v6 = *(_QWORD **)a1;
        if ( *(_QWORD *)a1 != a1 )
        {
          if ( v6[1] != a1 || (v7 = *(_QWORD **)(a1 + 8), *v7 != a1) )
            __fastfail(3u);
          *v7 = v6;
          v6[1] = v7;
          *(_QWORD *)(a1 + 8) = a1;
          *(_QWORD *)a1 = a1;
        }
        ExReleaseFastMutex((PFAST_MUTEX)(v5 + 200));
      }
      WcReleaseUnionContext(*(_QWORD *)(a1 + 40));
      break;
    case 16:
      WcFreeEnumContexts(a1);
      WcFreeSourceList(a1 + 48);
      v3 = *(void **)(a1 + 64);
      if ( v3 )
        FltReleaseContext(v3);
      break;
  }
}

```

## disassembly

```asm
0x1400300b0  mov     [rsp+arg_0], rbx
0x1400300b5  mov     [rsp+arg_8], rsi
0x1400300ba  push    rdi
0x1400300bb  sub     rsp, 20h
0x1400300bf  mov     rbx, rcx
0x1400300c2  cmp     dx, 2
0x1400300c6  jz      loc_140030203
0x1400300cc  cmp     dx, 4
0x1400300d0  jz      loc_1400301B5
0x1400300d6  cmp     dx, 8
0x1400300da  jz      short loc_140030112
0x1400300dc  cmp     dx, 10h
0x1400300e0  jnz     loc_1400302B3
0x1400300e6  call    WcFreeEnumContexts
0x1400300eb  lea     rcx, [rbx+30h]
0x1400300ef  call    WcFreeSourceList
0x1400300f4  mov     rcx, [rbx+40h]; Context
0x1400300f8  test    rcx, rcx
0x1400300fb  jz      loc_1400302B3
0x140030101  call    cs:__imp_FltReleaseContext
0x140030108  nop     dword ptr [rax+rax+00h]
0x14003010d  jmp     loc_1400302B3
0x140030112  mov     rcx, [rcx+100h]; HashTable
0x140030119  test    rcx, rcx
0x14003011c  jz      short loc_140030123
0x14003011e  call    WcFreeInMemoryTombstoneHashTable
0x140030123  lea     rcx, [rbx+78h]; Resource
0x140030127  call    cs:__imp_ExDeleteResourceLite
0x14003012e  nop     dword ptr [rax+rax+00h]
0x140030133  lea     rcx, [rbx+38h]
0x140030137  call    WcFreeSourceList
0x14003013c  mov     rcx, [rbx+20h]; Context
0x140030140  call    cs:__imp_FltReleaseContext
0x140030147  nop     dword ptr [rax+rax+00h]
0x14003014c  cmp     [rbx], rbx
0x14003014f  jz      short loc_1400301A0
0x140030151  mov     rsi, [rbx+28h]
0x140030155  lea     rcx, [rsi+0C8h]; FastMutex
0x14003015c  call    cs:__imp_ExAcquireFastMutex
0x140030163  nop     dword ptr [rax+rax+00h]
0x140030168  mov     rax, [rbx]
0x14003016b  cmp     rax, rbx
0x14003016e  jz      short loc_14003018D
0x140030170  cmp     [rax+8], rbx
0x140030174  jnz     short loc_1400301AE
0x140030176  mov     rcx, [rbx+8]
0x14003017a  cmp     [rcx], rbx
0x14003017d  jnz     short loc_1400301AE
0x14003017f  mov     [rcx], rax
0x140030182  mov     [rax+8], rcx
0x140030186  mov     [rbx+8], rbx
0x14003018a  mov     [rbx], rbx
0x14003018d  lea     rcx, [rsi+0C8h]; FastMutex
0x140030194  call    cs:__imp_ExReleaseFastMutex
0x14003019b  nop     dword ptr [rax+rax+00h]
0x1400301a0  mov     rcx, [rbx+28h]
0x1400301a4  call    WcReleaseUnionContext
0x1400301a9  jmp     loc_1400302B3
0x1400301ae  mov     ecx, 3
0x1400301b3  int     29h; Win8: RtlFailFast(ecx)
0x1400301b5  mov     rcx, [rcx]; Context
0x1400301b8  call    cs:__imp_FltReleaseContext
0x1400301bf  nop     dword ptr [rax+rax+00h]
0x1400301c4  mov     rdx, [rbx+50h]; Entry
0x1400301c8  test    rdx, rdx
0x1400301cb  jz      short loc_1400301E0
0x1400301cd  lea     rcx, stru_14000E580; Lookaside
0x1400301d4  call    cs:__imp_ExFreeToNPagedLookasideList
0x1400301db  nop     dword ptr [rax+rax+00h]
0x1400301e0  mov     rcx, [rbx+40h]; P
0x1400301e4  test    rcx, rcx
0x1400301e7  jz      loc_1400302B3
0x1400301ed  mov     edx, 69724357h; Tag
0x1400301f2  call    cs:__imp_ExFreePoolWithTag
0x1400301f9  nop     dword ptr [rax+rax+00h]
0x1400301fe  jmp     loc_1400302B3
0x140030203  cmp     cs:byte_14000E680, 0
0x14003020a  jz      short loc_14003027A
0x14003020c  mov     rdi, cs:P
0x140030213  test    rdi, rdi
0x140030216  jz      short loc_14003027A
0x140030218  lea     rcx, FastMutex; FastMutex
0x14003021f  call    cs:__imp_ExAcquireFastMutex
0x140030226  nop     dword ptr [rax+rax+00h]
0x14003022b  movsxd  rax, dword ptr [rdi]
0x14003022e  lea     rcx, FastMutex; FastMutex
0x140030235  mov     r8, [rbx+20h]
0x140030239  lea     rdx, [rax+rax*2]
0x14003023d  movsd   xmm0, qword ptr [r8]
0x140030242  movsd   qword ptr [rdi+rdx*4+4], xmm0
0x140030248  mov     eax, [r8+8]
0x14003024c  mov     [rdi+rdx*4+0Ch], eax
0x140030250  mov     eax, 55555556h
0x140030255  mov     r8d, [rdi]
0x140030258  inc     r8d
0x14003025b  imul    r8d
0x14003025e  mov     eax, edx
0x140030260  shr     eax, 1Fh
0x140030263  add     edx, eax
0x140030265  lea     eax, [rdx+rdx*2]
0x140030268  sub     r8d, eax
0x14003026b  mov     [rdi], r8d
0x14003026e  call    cs:__imp_ExReleaseFastMutex
0x140030275  nop     dword ptr [rax+rax+00h]
0x14003027a  mov     rcx, [rbx+38h]
0x14003027e  test    rcx, rcx
0x140030281  jz      short loc_14003028A
0x140030283  call    WcReleaseUnionContext
0x140030288  jmp     short loc_1400302A3
0x14003028a  cmp     dword ptr [rbx+40h], 0
0x14003028e  jbe     short loc_1400302A3
0x140030290  lea     rcx, [rbx+0B0h]; Table
0x140030297  call    WcClearUnionTable
0x14003029c  mov     dword ptr [rbx+40h], 0
0x1400302a3  lea     rcx, [rbx+48h]; Resource
0x1400302a7  call    cs:__imp_ExDeleteResourceLite
0x1400302ae  nop     dword ptr [rax+rax+00h]
0x1400302b3  mov     rbx, [rsp+28h+arg_0]
0x1400302b8  mov     rsi, [rsp+28h+arg_8]
0x1400302bd  add     rsp, 20h
0x1400302c1  pop     rdi
0x1400302c2  retn
```
