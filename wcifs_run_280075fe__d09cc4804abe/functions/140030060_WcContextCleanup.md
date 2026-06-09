# WcContextCleanup

- ea: `0x140030060`
- end: `0x140030274`
- name: `WcContextCleanup`
- size: `532`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callees

- `0x140002048`
- `0x14001c5d8`
- `0x14001d56c`
- `0x140029c78`
- `0x14002ee54`
- `0x140030060`

## import_xrefs

- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030184`
- `ntoskrnl!ExFreeToNPagedLookasideList` at `0x140030184`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301a2`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400301a2`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003010c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400301cf`
- `ntoskrnl!ExAcquireFastMutex` at `0x14003010c`
- `ntoskrnl!ExAcquireFastMutex` at `0x1400301cf`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400300d7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140030257`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400300d7`
- `ntoskrnl!ExDeleteResourceLite` at `0x140030257`
- `ntoskrnl!ExReleaseFastMutex` at `0x140030144`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003021e`
- `ntoskrnl!ExReleaseFastMutex` at `0x140030144`
- `ntoskrnl!ExReleaseFastMutex` at `0x14003021e`
- `FLTMGR!FltReleaseContext` at `0x1400300b1`
- `FLTMGR!FltReleaseContext` at `0x1400300f0`
- `FLTMGR!FltReleaseContext` at `0x140030168`
- `FLTMGR!FltReleaseContext` at `0x1400300b1`
- `FLTMGR!FltReleaseContext` at `0x1400300f0`
- `FLTMGR!FltReleaseContext` at `0x140030168`

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
      WcFreeEnumContexts();
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
0x140030060  mov     [rsp+arg_0], rbx
0x140030065  mov     [rsp+arg_8], rsi
0x14003006a  push    rdi
0x14003006b  sub     rsp, 20h
0x14003006f  mov     rbx, rcx
0x140030072  cmp     dx, 2
0x140030076  jz      loc_1400301B3
0x14003007c  cmp     dx, 4
0x140030080  jz      loc_140030165
0x140030086  cmp     dx, 8
0x14003008a  jz      short loc_1400300C2
0x14003008c  cmp     dx, 10h
0x140030090  jnz     loc_140030263
0x140030096  call    WcFreeEnumContexts
0x14003009b  lea     rcx, [rbx+30h]
0x14003009f  call    WcFreeSourceList
0x1400300a4  mov     rcx, [rbx+40h]; Context
0x1400300a8  test    rcx, rcx
0x1400300ab  jz      loc_140030263
0x1400300b1  call    cs:__imp_FltReleaseContext
0x1400300b8  nop     dword ptr [rax+rax+00h]
0x1400300bd  jmp     loc_140030263
0x1400300c2  mov     rcx, [rcx+100h]; HashTable
0x1400300c9  test    rcx, rcx
0x1400300cc  jz      short loc_1400300D3
0x1400300ce  call    WcFreeInMemoryTombstoneHashTable
0x1400300d3  lea     rcx, [rbx+78h]; Resource
0x1400300d7  call    cs:__imp_ExDeleteResourceLite
0x1400300de  nop     dword ptr [rax+rax+00h]
0x1400300e3  lea     rcx, [rbx+38h]
0x1400300e7  call    WcFreeSourceList
0x1400300ec  mov     rcx, [rbx+20h]; Context
0x1400300f0  call    cs:__imp_FltReleaseContext
0x1400300f7  nop     dword ptr [rax+rax+00h]
0x1400300fc  cmp     [rbx], rbx
0x1400300ff  jz      short loc_140030150
0x140030101  mov     rsi, [rbx+28h]
0x140030105  lea     rcx, [rsi+0C8h]; FastMutex
0x14003010c  call    cs:__imp_ExAcquireFastMutex
0x140030113  nop     dword ptr [rax+rax+00h]
0x140030118  mov     rax, [rbx]
0x14003011b  cmp     rax, rbx
0x14003011e  jz      short loc_14003013D
0x140030120  cmp     [rax+8], rbx
0x140030124  jnz     short loc_14003015E
0x140030126  mov     rcx, [rbx+8]
0x14003012a  cmp     [rcx], rbx
0x14003012d  jnz     short loc_14003015E
0x14003012f  mov     [rcx], rax
0x140030132  mov     [rax+8], rcx
0x140030136  mov     [rbx+8], rbx
0x14003013a  mov     [rbx], rbx
0x14003013d  lea     rcx, [rsi+0C8h]; FastMutex
0x140030144  call    cs:__imp_ExReleaseFastMutex
0x14003014b  nop     dword ptr [rax+rax+00h]
0x140030150  mov     rcx, [rbx+28h]
0x140030154  call    WcReleaseUnionContext
0x140030159  jmp     loc_140030263
0x14003015e  mov     ecx, 3
0x140030163  int     29h; Win8: RtlFailFast(ecx)
0x140030165  mov     rcx, [rcx]; Context
0x140030168  call    cs:__imp_FltReleaseContext
0x14003016f  nop     dword ptr [rax+rax+00h]
0x140030174  mov     rdx, [rbx+50h]; Entry
0x140030178  test    rdx, rdx
0x14003017b  jz      short loc_140030190
0x14003017d  lea     rcx, stru_14000E580; Lookaside
0x140030184  call    cs:__imp_ExFreeToNPagedLookasideList
0x14003018b  nop     dword ptr [rax+rax+00h]
0x140030190  mov     rcx, [rbx+40h]; P
0x140030194  test    rcx, rcx
0x140030197  jz      loc_140030263
0x14003019d  mov     edx, 69724357h; Tag
0x1400301a2  call    cs:__imp_ExFreePoolWithTag
0x1400301a9  nop     dword ptr [rax+rax+00h]
0x1400301ae  jmp     loc_140030263
0x1400301b3  cmp     cs:byte_14000E680, 0
0x1400301ba  jz      short loc_14003022A
0x1400301bc  mov     rdi, cs:P
0x1400301c3  test    rdi, rdi
0x1400301c6  jz      short loc_14003022A
0x1400301c8  lea     rcx, FastMutex; FastMutex
0x1400301cf  call    cs:__imp_ExAcquireFastMutex
0x1400301d6  nop     dword ptr [rax+rax+00h]
0x1400301db  movsxd  rax, dword ptr [rdi]
0x1400301de  lea     rcx, FastMutex; FastMutex
0x1400301e5  mov     r8, [rbx+20h]
0x1400301e9  lea     rdx, [rax+rax*2]
0x1400301ed  movsd   xmm0, qword ptr [r8]
0x1400301f2  movsd   qword ptr [rdi+rdx*4+4], xmm0
0x1400301f8  mov     eax, [r8+8]
0x1400301fc  mov     [rdi+rdx*4+0Ch], eax
0x140030200  mov     eax, 55555556h
0x140030205  mov     r8d, [rdi]
0x140030208  inc     r8d
0x14003020b  imul    r8d
0x14003020e  mov     eax, edx
0x140030210  shr     eax, 1Fh
0x140030213  add     edx, eax
0x140030215  lea     eax, [rdx+rdx*2]
0x140030218  sub     r8d, eax
0x14003021b  mov     [rdi], r8d
0x14003021e  call    cs:__imp_ExReleaseFastMutex
0x140030225  nop     dword ptr [rax+rax+00h]
0x14003022a  mov     rcx, [rbx+38h]
0x14003022e  test    rcx, rcx
0x140030231  jz      short loc_14003023A
0x140030233  call    WcReleaseUnionContext
0x140030238  jmp     short loc_140030253
0x14003023a  cmp     dword ptr [rbx+40h], 0
0x14003023e  jbe     short loc_140030253
0x140030240  lea     rcx, [rbx+0B0h]; Table
0x140030247  call    WcClearUnionTable
0x14003024c  mov     dword ptr [rbx+40h], 0
0x140030253  lea     rcx, [rbx+48h]; Resource
0x140030257  call    cs:__imp_ExDeleteResourceLite
0x14003025e  nop     dword ptr [rax+rax+00h]
0x140030263  mov     rbx, [rsp+28h+arg_0]
0x140030268  mov     rsi, [rsp+28h+arg_8]
0x14003026d  add     rsp, 20h
0x140030271  pop     rdi
0x140030272  retn
```
