# DestroyEntity

- ea: `0x180009adc`
- end: `0x180009c10`
- name: `DestroyEntity`
- size: `308`
- prototype: `__int64 __fastcall(LPVOID lpMem)`
- caller_count: `12`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180003730`
- `0x1800060a0`
- `0x180007220`
- `0x1800072f0`
- `0x180007350`
- `0x180007530`
- `0x180007c50`
- `0x1800094a8`
- `0x18000a230`
- `0x18000a298`
- `0x18000a820`
- `0x18000b1d0`

## callees

- `0x180001f00`
- `0x18000995c`
- `0x180009adc`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x180009af2`
- `ntdll!RtlAcquireResourceExclusive` at `0x180009af2`
- `ntdll!RtlReleaseResource` at `0x180009bf6`
- `ntdll!RtlReleaseResource` at `0x180009bf6`
- `ntdll!RtlDeleteResource` at `0x180009b08`
- `ntdll!RtlDeleteResource` at `0x180009b2f`
- `ntdll!RtlDeleteResource` at `0x180009b58`
- `ntdll!RtlDeleteResource` at `0x180009b08`
- `ntdll!RtlDeleteResource` at `0x180009b2f`
- `ntdll!RtlDeleteResource` at `0x180009b58`
- `KERNEL32!GetProcessHeap` at `0x180009bdb`
- `KERNEL32!GetProcessHeap` at `0x180009bdb`
- `KERNEL32!HeapFree` at `0x180009be9`
- `KERNEL32!HeapFree` at `0x180009be9`
- `KERNEL32!DeleteCriticalSection` at `0x180009b45`
- `KERNEL32!DeleteCriticalSection` at `0x180009b45`

## pseudocode

```c
__int64 __fastcall DestroyEntity(char *lpMem)
{
  void *v2; // rcx
  __int64 v3; // rdi
  char **v4; // rcx
  LPVOID *v5; // rdx
  HANDLE ProcessHeap; // rax

  RtlAcquireResourceExclusive(&Resource, 1u);
  if ( *((_DWORD *)lpMem + 110) )
    RtlDeleteResource((PRTL_RESOURCE)(lpMem + 344));
  v2 = (void *)*((_QWORD *)lpMem + 41);
  if ( v2 )
    DestroyTable(v2);
  if ( *((_DWORD *)lpMem + 80) )
    RtlDeleteResource((PRTL_RESOURCE)(lpMem + 224));
  if ( *((_DWORD *)lpMem + 50) )
    DeleteCriticalSection((LPCRITICAL_SECTION)lpMem + 4);
  if ( *((_DWORD *)lpMem + 38) )
    RtlDeleteResource((PRTL_RESOURCE)(lpMem + 56));
  v3 = *((_QWORD *)lpMem + 2);
  if ( *((_DWORD *)lpMem + 13) != -1 )
  {
    *(_QWORD *)(*(_QWORD *)(v3 + 320) + 8LL * *((int *)lpMem + 13)) = 0;
    --*(_DWORD *)(v3 + 316);
  }
  v4 = (char **)*((_QWORD *)lpMem + 3);
  if ( v4[1] != lpMem + 24 || (v5 = (LPVOID *)*((_QWORD *)lpMem + 4), *v5 != lpMem + 24) )
    __fastfail(3u);
  *v5 = v4;
  v4[1] = (char *)v5;
  --*(_DWORD *)(v3 + 328);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
    DestroyAddressFamily((char *)v3);
  if ( !*(_DWORD *)(v3 + 328) && _InterlockedExchangeAdd((volatile signed __int32 *)v3, 0xFFFFFFFF) == 1 )
    DestroyAddressFamily((char *)v3);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, lpMem);
  RtlReleaseResource(&Resource);
  return 0;
}

```

## disassembly

```asm
0x180009adc  mov     [rsp+arg_8], rbx
0x180009ae1  push    rdi
0x180009ae2  sub     rsp, 20h
0x180009ae6  mov     rbx, rcx
0x180009ae9  mov     dl, 1; Wait
0x180009aeb  lea     rcx, Resource; Resource
0x180009af2  call    cs:__imp_RtlAcquireResourceExclusive
0x180009af8  cmp     dword ptr [rbx+1B8h], 0
0x180009aff  jz      short loc_180009B0E
0x180009b01  lea     rcx, [rbx+158h]; Resource
0x180009b08  call    cs:__imp_RtlDeleteResource
0x180009b0e  mov     rcx, [rbx+148h]; lpMem
0x180009b15  test    rcx, rcx
0x180009b18  jz      short loc_180009B1F
0x180009b1a  call    DestroyTable
0x180009b1f  cmp     dword ptr [rbx+140h], 0
0x180009b26  jz      short loc_180009B35
0x180009b28  lea     rcx, [rbx+0E0h]; Resource
0x180009b2f  call    cs:__imp_RtlDeleteResource
0x180009b35  cmp     dword ptr [rbx+0C8h], 0
0x180009b3c  jz      short loc_180009B4B
0x180009b3e  lea     rcx, [rbx+0A0h]; lpCriticalSection
0x180009b45  call    cs:__imp_DeleteCriticalSection
0x180009b4b  cmp     dword ptr [rbx+98h], 0
0x180009b52  jz      short loc_180009B5E
0x180009b54  lea     rcx, [rbx+38h]; Resource
0x180009b58  call    cs:__imp_RtlDeleteResource
0x180009b5e  mov     rdi, [rbx+10h]
0x180009b62  or      r8d, 0FFFFFFFFh
0x180009b66  cmp     dword ptr [rbx+34h], 0FFFFFFFFh
0x180009b6a  jz      short loc_180009B86
0x180009b6c  movsxd  rcx, dword ptr [rbx+34h]
0x180009b70  mov     rax, [rdi+140h]
0x180009b77  mov     qword ptr [rax+rcx*8], 0
0x180009b7f  add     [rdi+13Ch], r8d
0x180009b86  lea     rax, [rbx+18h]
0x180009b8a  mov     rcx, [rax]
0x180009b8d  cmp     [rcx+8], rax
0x180009b91  jnz     short loc_180009C09
0x180009b93  mov     rdx, [rax+8]
0x180009b97  cmp     [rdx], rax
0x180009b9a  jnz     short loc_180009C09
0x180009b9c  mov     [rdx], rcx
0x180009b9f  mov     [rcx+8], rdx
0x180009ba3  add     [rdi+148h], r8d
0x180009baa  or      eax, 0FFFFFFFFh
0x180009bad  lock xadd [rdi], eax
0x180009bb1  cmp     eax, 1
0x180009bb4  jnz     short loc_180009BBE
0x180009bb6  mov     rcx, rdi; lpMem
0x180009bb9  call    DestroyAddressFamily
0x180009bbe  cmp     dword ptr [rdi+148h], 0
0x180009bc5  jnz     short loc_180009BDB
0x180009bc7  or      eax, 0FFFFFFFFh
0x180009bca  lock xadd [rdi], eax
0x180009bce  cmp     eax, 1
0x180009bd1  jnz     short loc_180009BDB
0x180009bd3  mov     rcx, rdi; lpMem
0x180009bd6  call    DestroyAddressFamily
0x180009bdb  call    cs:__imp_GetProcessHeap
0x180009be1  mov     r8, rbx; lpMem
0x180009be4  xor     edx, edx; dwFlags
0x180009be6  mov     rcx, rax; hHeap
0x180009be9  call    cs:__imp_HeapFree
0x180009bef  lea     rcx, Resource; Resource
0x180009bf6  call    cs:__imp_RtlReleaseResource
0x180009bfc  mov     rbx, [rsp+28h+arg_8]
0x180009c01  xor     eax, eax
0x180009c03  add     rsp, 20h
0x180009c07  pop     rdi
0x180009c08  retn
0x180009c09  mov     ecx, 3
0x180009c0e  int     29h; Win8: RtlFailFast(ecx)
```
