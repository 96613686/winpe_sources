# TdhpFindOrAddEntry(TDH_CACHE_BUCKET *,_GUID const *,ulong *)

- ea: `0x180006660`
- end: `0x18000675c`
- name: `?TdhpFindOrAddEntry@@YAPEAUTDH_MOF_INFO@@PEAUTDH_CACHE_BUCKET@@PEBU_GUID@@PEAK@Z`
- size: `252`
- prototype: `struct TDH_MOF_INFO *__fastcall(struct TDH_CACHE_BUCKET *, const struct _GUID *, unsigned int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800010c0`
- `0x180001730`
- `0x180003270`
- `0x180004ca0`
- `0x1800064d0`
- `0x1800244d8`

## callees

- `0x1800059e8`
- `0x180006660`
- `0x180007720`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006751`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006751`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006743`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006743`

## pseudocode

```c
struct TDH_MOF_INFO *__fastcall TdhpFindOrAddEntry(
        struct TDH_CACHE_BUCKET *a1,
        const struct _GUID *a2,
        unsigned int *a3)
{
  struct TDH_MOF_INFO *v3; // rbp
  struct TDH_MOF_INFO *v4; // r14
  __int64 i; // rbx
  _DWORD *v9; // rax
  volatile signed __int64 *v10; // rsi
  struct TDH_MOF_INFO *result; // rax
  struct TDH_MOF_INFO *v12; // r8
  HANDLE ProcessHeap; // rax

  v3 = 0;
  v4 = 0;
  if ( a3 )
    *a3 = 0;
  for ( i = 0; ; i = (unsigned int)(i + 1) )
  {
    if ( (unsigned int)i >= 7 )
      goto LABEL_12;
    v9 = (_DWORD *)*((_QWORD *)a1 + i + 1);
    v10 = (volatile signed __int64 *)((char *)a1 + 8 * i);
    if ( v9 )
    {
      if ( v9[2] == a2->Data1
        && v9[3] == *(_DWORD *)&a2->Data2
        && v9[4] == *(_DWORD *)a2->Data4
        && v9[5] == *(_DWORD *)&a2->Data4[4] )
      {
        v3 = (struct TDH_MOF_INFO *)*((_QWORD *)a1 + i + 1);
LABEL_12:
        if ( v3 != v4 )
        {
          if ( v4 )
          {
            ProcessHeap = GetProcessHeap();
            HeapFree(ProcessHeap, 0, v4);
          }
        }
        return v3;
      }
      continue;
    }
    if ( !v4 )
    {
      v4 = TdhpCacheEntryAllocate(a2);
      if ( !v4 )
        break;
    }
    if ( !_InterlockedCompareExchange64(v10 + 1, (signed __int64)v4, 0) )
      return v4;
    if ( (unsigned int)InlineIsEqualGUID((const struct _GUID *)(*((_QWORD *)v10 + 1) + 8LL), a2) )
    {
      v3 = v12;
      goto LABEL_12;
    }
  }
  result = 0;
  if ( a3 )
    *a3 = 8;
  return result;
}

```

## disassembly

```asm
0x180006660  mov     [rsp+arg_8], rbx
0x180006665  push    rbp
0x180006666  push    rdi
0x180006667  push    r12
0x180006669  push    r14
0x18000666b  push    r15
0x18000666d  sub     rsp, 20h
0x180006671  xor     ebp, ebp
0x180006673  xor     r14d, r14d
0x180006676  mov     r12, r8
0x180006679  mov     rdi, rdx
0x18000667c  mov     r15, rcx
0x18000667f  test    r8, r8
0x180006682  jnz     loc_180006736
0x180006688  xor     ebx, ebx
0x18000668a  mov     [rsp+48h+arg_0], rsi
0x18000668f  cmp     ebx, 7
0x180006692  jnb     short loc_1800066C8
0x180006694  mov     rax, [r15+rbx*8+8]
0x180006699  lea     rsi, [r15+rbx*8]
0x18000669d  test    rax, rax
0x1800066a0  jz      short loc_1800066EC
0x1800066a2  mov     ecx, [rdi]
0x1800066a4  cmp     [rax+8], ecx
0x1800066a7  jnz     short loc_1800066B1
0x1800066a9  mov     ecx, [rdi+4]
0x1800066ac  cmp     [rax+0Ch], ecx
0x1800066af  jz      short loc_1800066B5
0x1800066b1  inc     ebx
0x1800066b3  jmp     short loc_18000668F
0x1800066b5  mov     ecx, [rdi+8]
0x1800066b8  cmp     [rax+10h], ecx
0x1800066bb  jnz     short loc_1800066B1
0x1800066bd  mov     ecx, [rdi+0Ch]
0x1800066c0  cmp     [rax+14h], ecx
0x1800066c3  jnz     short loc_1800066B1
0x1800066c5  mov     rbp, rax
0x1800066c8  cmp     rbp, r14
0x1800066cb  jz      short loc_1800066D2
0x1800066cd  test    r14, r14
0x1800066d0  jnz     short loc_180006743
0x1800066d2  mov     rax, rbp
0x1800066d5  mov     rsi, [rsp+48h+arg_0]
0x1800066da  mov     rbx, [rsp+48h+arg_8]
0x1800066df  add     rsp, 20h
0x1800066e3  pop     r15
0x1800066e5  pop     r14
0x1800066e7  pop     r12
0x1800066e9  pop     rdi
0x1800066ea  pop     rbp
0x1800066eb  retn
0x1800066ec  test    r14, r14
0x1800066ef  jnz     short loc_180006713
0x1800066f1  mov     rcx, rdi; struct _GUID *
0x1800066f4  call    ?TdhpCacheEntryAllocate@@YAPEAUTDH_MOF_INFO@@PEBU_GUID@@@Z; TdhpCacheEntryAllocate(_GUID const *)
0x1800066f9  mov     r14, rax
0x1800066fc  test    rax, rax
0x1800066ff  jnz     short loc_180006713
0x180006701  mov     rax, rbp
0x180006704  test    r12, r12
0x180006707  jz      short loc_1800066D5
0x180006709  mov     dword ptr [r12], 8
0x180006711  jmp     short loc_1800066D5
0x180006713  xor     eax, eax
0x180006715  lock cmpxchg [rsi+8], r14
0x18000671b  jz      short loc_18000673E
0x18000671d  mov     r8, [rsi+8]
0x180006721  mov     rdx, rdi; struct _GUID *
0x180006724  lea     rcx, [r8+8]; struct _GUID *
0x180006728  call    ?InlineIsEqualGUID@@YAHAEBU_GUID@@0@Z; InlineIsEqualGUID(_GUID const &,_GUID const &)
0x18000672d  test    eax, eax
0x18000672f  jz      short loc_1800066B1
0x180006731  mov     rbp, r8
0x180006734  jmp     short loc_1800066C8
0x180006736  mov     [r8], ebp
0x180006739  jmp     loc_180006688
0x18000673e  mov     rax, r14
0x180006741  jmp     short loc_1800066D5
0x180006743  call    cs:__imp_GetProcessHeap
0x180006749  mov     r8, r14; lpMem
0x18000674c  xor     edx, edx; dwFlags
0x18000674e  mov     rcx, rax; hHeap
0x180006751  call    cs:__imp_HeapFree
0x180006757  jmp     loc_1800066D2
```
