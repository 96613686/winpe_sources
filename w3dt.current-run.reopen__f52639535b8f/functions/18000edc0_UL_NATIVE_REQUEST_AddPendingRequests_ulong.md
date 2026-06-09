# UL_NATIVE_REQUEST::AddPendingRequests(ulong)

- ea: `0x18000edc0`
- end: `0x18000ee7b`
- name: `?AddPendingRequests@UL_NATIVE_REQUEST@@SAJK@Z`
- size: `187`
- prototype: `__int64 __fastcall(unsigned int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000ec08`
- `0x180012b00`

## callees

- `0x18000edc0`
- `0x18000eef0`
- `0x18000f510`

## import_xrefs

- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ee27`
- `iisutil!?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ` at `0x18000ee27`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000ee12`
- `iisutil!?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ` at `0x18000ee12`

## pseudocode

```c
__int64 __fastcall UL_NATIVE_REQUEST::AddPendingRequests(unsigned int a1)
{
  unsigned int v2; // esi
  unsigned int i; // ebx
  UL_NATIVE_REQUEST *v5; // rax
  UL_NATIVE_REQUEST *v6; // rax

  v2 = 0;
  if ( !UL_NATIVE_REQUEST::sm_fAddingRequests
    && !_InterlockedCompareExchange(&UL_NATIVE_REQUEST::sm_fAddingRequests, 1, 0) )
  {
    for ( i = 0;
          i < a1
       && ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(UL_NATIVE_REQUEST::sm_pachNativeRequests) < UL_NATIVE_REQUEST::sm_cMaxRequests;
          ++i )
    {
      v5 = (UL_NATIVE_REQUEST *)ALLOC_CACHE_HANDLER::Alloc(UL_NATIVE_REQUEST::sm_pachNativeRequests);
      if ( !v5 || (v6 = UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(v5)) == 0 )
      {
        v2 = -2147024888;
        break;
      }
      *((_QWORD *)v6 + 381) = (char *)v6 + 3152;
      UL_NATIVE_REQUEST::DoWork(v6, 0, 0, 0, 0);
    }
    UL_NATIVE_REQUEST::sm_fAddingRequests = 0;
  }
  return v2;
}

```

## disassembly

```asm
0x18000edc0  mov     [rsp+arg_8], rbp
0x18000edc5  mov     [rsp+arg_10], rsi
0x18000edca  push    rdi
0x18000edcb  sub     rsp, 30h
0x18000edcf  xor     ebp, ebp
0x18000edd1  mov     edi, ecx
0x18000edd3  cmp     cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, ebp; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000edd9  mov     esi, ebp
0x18000eddb  jz      short loc_18000EDEF
0x18000eddd  mov     rbp, [rsp+38h+arg_8]
0x18000ede2  mov     eax, esi
0x18000ede4  mov     rsi, [rsp+38h+arg_10]
0x18000ede9  add     rsp, 30h
0x18000eded  pop     rdi
0x18000edee  retn
0x18000edef  mov     ecx, 1
0x18000edf4  xor     eax, eax
0x18000edf6  lock cmpxchg cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, ecx; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000edfe  jnz     short loc_18000EDDD
0x18000ee00  mov     [rsp+38h+arg_0], rbx
0x18000ee05  mov     ebx, ebp
0x18000ee07  cmp     ebx, edi
0x18000ee09  jnb     short loc_18000EE6B
0x18000ee0b  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000ee12  call    cs:__imp_?QueryOutstandingAllocationCount@ALLOC_CACHE_HANDLER@@QEBAKXZ; ALLOC_CACHE_HANDLER::QueryOutstandingAllocationCount(void)
0x18000ee18  cmp     eax, cs:?sm_cMaxRequests@UL_NATIVE_REQUEST@@0KA; ulong UL_NATIVE_REQUEST::sm_cMaxRequests
0x18000ee1e  jnb     short loc_18000EE6B
0x18000ee20  mov     rcx, cs:?sm_pachNativeRequests@UL_NATIVE_REQUEST@@0PEAVALLOC_CACHE_HANDLER@@EA; ALLOC_CACHE_HANDLER * UL_NATIVE_REQUEST::sm_pachNativeRequests
0x18000ee27  call    cs:__imp_?Alloc@ALLOC_CACHE_HANDLER@@QEAAPEAXXZ; ALLOC_CACHE_HANDLER::Alloc(void)
0x18000ee2d  test    rax, rax
0x18000ee30  jz      short loc_18000EE66
0x18000ee32  mov     rcx, rax; this
0x18000ee35  call    ??0UL_NATIVE_REQUEST@@QEAA@XZ; UL_NATIVE_REQUEST::UL_NATIVE_REQUEST(void)
0x18000ee3a  test    rax, rax
0x18000ee3d  jz      short loc_18000EE66
0x18000ee3f  lea     rcx, [rax+0C50h]
0x18000ee46  mov     qword ptr [rsp+38h+var_18], rbp; ULONG
0x18000ee4b  mov     [rax+0BE8h], rcx
0x18000ee52  xor     r9d, r9d; unsigned int
0x18000ee55  mov     rcx, rax; this
0x18000ee58  xor     r8d, r8d; unsigned int
0x18000ee5b  xor     edx, edx; unsigned int
0x18000ee5d  call    ?DoWork@UL_NATIVE_REQUEST@@QEAAXKKKPEAU_OVERLAPPED@@@Z; UL_NATIVE_REQUEST::DoWork(ulong,ulong,ulong,_OVERLAPPED *)
0x18000ee62  inc     ebx
0x18000ee64  jmp     short loc_18000EE07
0x18000ee66  mov     esi, 80070008h
0x18000ee6b  mov     rbx, [rsp+38h+arg_0]
0x18000ee70  mov     cs:?sm_fAddingRequests@UL_NATIVE_REQUEST@@0HA, ebp; int UL_NATIVE_REQUEST::sm_fAddingRequests
0x18000ee76  jmp     loc_18000EDDD
```
