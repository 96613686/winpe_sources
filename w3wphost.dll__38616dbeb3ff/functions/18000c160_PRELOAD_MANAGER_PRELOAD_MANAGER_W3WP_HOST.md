# PRELOAD_MANAGER::PRELOAD_MANAGER(W3WP_HOST *)

- ea: `0x18000c160`
- end: `0x18000c240`
- name: `??0PRELOAD_MANAGER@@QEAA@PEAVW3WP_HOST@@@Z`
- size: `224`
- prototype: `PRELOAD_MANAGER *__fastcall(PRELOAD_MANAGER *__hidden this, struct W3WP_HOST *)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800068bc`

## callees

- `0x18000e010`

## import_xrefs

- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000c1e6`
- `iisutil!??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z` at `0x18000c1e6`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000c17e`
- `iisutil!??0CReaderWriterLock3@@QEAA@XZ` at `0x18000c17e`

## pseudocode

```c
PRELOAD_MANAGER *__fastcall PRELOAD_MANAGER::PRELOAD_MANAGER(PRELOAD_MANAGER *this, struct W3WP_HOST *a2)
{
  PRELOAD_MANAGER *result; // rax

  *(_QWORD *)this = &PRELOAD_MANAGER::`vftable';
  CReaderWriterLock3::CReaderWriterLock3((PRELOAD_MANAGER *)((char *)this + 16));
  *((_QWORD *)this + 3) = 0;
  CLKRHashTable::CLKRHashTable(
    (PRELOAD_MANAGER *)((char *)this + 72),
    "PRELOAD_STATE_TABLE",
    (unsigned __int64 (*)(const void *))CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_ExtractKey,
    (unsigned int (*)(unsigned __int64))CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_CalcKeyHash,
    (bool (*)(unsigned __int64, unsigned __int64))CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_EqualKeys,
    (void (*)(const void *, int))CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,unsigned short const *,CLKRHashTable>::_AddRefRecord,
    4.0,
    1u,
    0,
    0);
  *((_DWORD *)this + 3) = 1;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_DWORD *)this + 16) = -1;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 4) = a2;
  (**(void (__fastcall ***)(struct W3WP_HOST *))a2)(a2);
  result = this;
  *((_DWORD *)this + 2) = 1296847440;
  return result;
}

```

## disassembly

```asm
0x18000c160  mov     [rsp+arg_0], rbx
0x18000c165  push    rdi
0x18000c166  sub     rsp, 50h
0x18000c16a  lea     rax, ??_7PRELOAD_MANAGER@@6B@; const PRELOAD_MANAGER::`vftable'
0x18000c171  mov     rdi, rcx
0x18000c174  mov     [rcx], rax
0x18000c177  mov     rbx, rdx
0x18000c17a  add     rcx, 10h
0x18000c17e  call    cs:__imp_??0CReaderWriterLock3@@QEAA@XZ; CReaderWriterLock3::CReaderWriterLock3(void)
0x18000c185  nop     dword ptr [rax+rax+00h]
0x18000c18a  movsd   xmm0, cs:__real@4010000000000000
0x18000c192  lea     rax, ?_AddRefRecord@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAXPEBXH@Z; CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_AddRefRecord(void const *,int)
0x18000c199  mov     [rsp+58h+var_10], 0
0x18000c19e  lea     rcx, [rdi+48h]
0x18000c1a2  mov     [rsp+58h+var_18], 0
0x18000c1aa  lea     r9, ?_CalcKeyHash@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CAK_K@Z; CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_CalcKeyHash(unsigned __int64)
0x18000c1b1  mov     [rsp+58h+var_20], 1
0x18000c1b9  lea     r8, ?_ExtractKey@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CA?B_KPEBX@Z; CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_ExtractKey(void const *)
0x18000c1c0  movsd   [rsp+58h+var_28], xmm0
0x18000c1c6  lea     rdx, aPreloadStateTa; "PRELOAD_STATE_TABLE"
0x18000c1cd  mov     [rsp+58h+var_30], rax
0x18000c1d2  lea     rax, ?_EqualKeys@?$CTypedHashTable@VPRELOAD_STATE_TABLE@@VPRELOAD_PATH_STATE@@PEBGVCLKRHashTable@@@@CA_N_K0@Z; CTypedHashTable<PRELOAD_STATE_TABLE,PRELOAD_PATH_STATE,ushort const *,CLKRHashTable>::_EqualKeys(unsigned __int64,unsigned __int64)
0x18000c1d9  mov     [rsp+58h+var_38], rax
0x18000c1de  mov     qword ptr [rdi+18h], 0
0x18000c1e6  call    cs:__imp_??0CLKRHashTable@@QEAA@PEBDP6A?B_KPEBX@ZP6AK_K@ZP6A_N33@ZP6AX1H@ZNKK_N@Z; CLKRHashTable::CLKRHashTable(char const *,unsigned __int64 const (*)(void const *),ulong (*)(unsigned __int64),bool (*)(unsigned __int64,unsigned __int64),void (*)(void const *,int),double,ulong,ulong,bool)
0x18000c1ed  nop     dword ptr [rax+rax+00h]
0x18000c1f2  mov     dword ptr [rdi+0Ch], 1
0x18000c1f9  mov     rcx, rbx
0x18000c1fc  mov     qword ptr [rdi+28h], 0
0x18000c204  mov     qword ptr [rdi+30h], 0
0x18000c20c  mov     dword ptr [rdi+40h], 0FFFFFFFFh
0x18000c213  mov     qword ptr [rdi+38h], 0
0x18000c21b  mov     [rdi+20h], rbx
0x18000c21f  mov     rax, [rbx]
0x18000c222  mov     rax, [rax]
0x18000c225  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c22a  mov     rbx, [rsp+58h+arg_0]
0x18000c22f  mov     rax, rdi
0x18000c232  mov     dword ptr [rdi+8], 4D4C5250h
0x18000c239  add     rsp, 50h
0x18000c23d  pop     rdi
0x18000c23e  retn
```
