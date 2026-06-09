# RtmDeleteRouteList

- ea: `0x180007530`
- end: `0x18000763a`
- name: `RtmDeleteRouteList`
- size: `266`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ROUTE_LIST_HANDLE RouteListHandle)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting`

## callees

- `0x180007530`
- `0x180009adc`
- `0x18000a298`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x18000756f`
- `ntdll!RtlAcquireResourceExclusive` at `0x18000756f`
- `ntdll!RtlReleaseResource` at `0x1800075f0`
- `ntdll!RtlReleaseResource` at `0x1800075f0`
- `KERNEL32!GetProcessHeap` at `0x1800075cf`
- `KERNEL32!GetProcessHeap` at `0x18000760a`
- `KERNEL32!GetProcessHeap` at `0x1800075cf`
- `KERNEL32!GetProcessHeap` at `0x18000760a`
- `KERNEL32!HeapFree` at `0x1800075dd`
- `KERNEL32!HeapFree` at `0x180007618`
- `KERNEL32!HeapFree` at `0x1800075dd`
- `KERNEL32!HeapFree` at `0x180007618`

## pseudocode

```c
DWORD __stdcall RtmDeleteRouteList(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ROUTE_LIST_HANDLE RouteListHandle)
{
  unsigned __int64 v2; // rbx
  _QWORD **v3; // rdi
  _QWORD **v4; // rsi
  _QWORD *v5; // rax
  _QWORD *v6; // rcx
  _QWORD *v7; // rcx
  _QWORD *v8; // rbp
  HANDLE ProcessHeap; // rax
  HANDLE v10; // rax

  v2 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v3 = (_QWORD **)((unsigned __int64)RouteListHandle ^ 0x7754DF32);
  if ( (unsigned __int64)RouteListHandle == 0x7754DF32 )
    return 6;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v2 + 56), 1u);
  v4 = v3 + 1;
  while ( 1 )
  {
    v5 = *v4;
    if ( *v4 == v4 )
      break;
    if ( (_QWORD **)v5[1] != v4 || (v6 = (_QWORD *)*v5, *(_QWORD **)(*v5 + 8LL) != v5) )
      __fastfail(3u);
    *v4 = v6;
    v6[1] = v4;
    v7 = v5 - 3;
    if ( v5[3] )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7, 0xFFFFFFFF) == 1 )
        DestroyRoute(v7);
    }
    else
    {
      v8 = v5 - 5;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
        DestroyEntity((char *)v2);
      if ( v8 )
      {
        ProcessHeap = GetProcessHeap();
        HeapFree(ProcessHeap, 0, v8);
      }
    }
  }
  RtlReleaseResource((PRTL_RESOURCE)(v2 + 56));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v2, 0xFFFFFFFF) == 1 )
    DestroyEntity((char *)v2);
  v10 = GetProcessHeap();
  HeapFree(v10, 0, v3);
  return 0;
}

```

## disassembly

```asm
0x180007530  mov     [rsp+arg_8], rbx
0x180007535  mov     [rsp+arg_10], rbp
0x18000753a  push    rsi
0x18000753b  push    rdi
0x18000753c  push    r14
0x18000753e  sub     rsp, 20h
0x180007542  mov     rbx, rcx
0x180007545  mov     eax, 7754DF32h
0x18000754a  xor     rbx, rax
0x18000754d  mov     rdi, rdx
0x180007550  jz      loc_180007622
0x180007556  cmp     dword ptr [rbx+30h], 1
0x18000755a  jz      loc_180007622
0x180007560  xor     rdi, rax
0x180007563  jz      loc_180007622
0x180007569  mov     dl, 1; Wait
0x18000756b  lea     rcx, [rbx+38h]; Resource
0x18000756f  call    cs:__imp_RtlAcquireResourceExclusive
0x180007575  lea     rsi, [rdi+8]
0x180007579  mov     rax, [rsi]
0x18000757c  cmp     rax, rsi
0x18000757f  jz      short loc_1800075EC
0x180007581  cmp     [rax+8], rsi
0x180007585  jnz     short loc_1800075E5
0x180007587  mov     rcx, [rax]
0x18000758a  cmp     [rcx+8], rax
0x18000758e  jnz     short loc_1800075E5
0x180007590  mov     [rsi], rcx
0x180007593  mov     [rcx+8], rsi
0x180007597  lea     rcx, [rax-18h]; lpMem
0x18000759b  or      eax, 0FFFFFFFFh
0x18000759e  cmp     qword ptr [rcx+30h], 0
0x1800075a3  jz      short loc_1800075B5
0x1800075a5  lock xadd [rcx], eax
0x1800075a9  cmp     eax, 1
0x1800075ac  jnz     short loc_180007579
0x1800075ae  call    DestroyRoute
0x1800075b3  jmp     short loc_180007579
0x1800075b5  lea     rbp, [rcx-10h]
0x1800075b9  lock xadd [rbx], eax
0x1800075bd  cmp     eax, 1
0x1800075c0  jnz     short loc_1800075CA
0x1800075c2  mov     rcx, rbx; lpMem
0x1800075c5  call    DestroyEntity
0x1800075ca  test    rbp, rbp
0x1800075cd  jz      short loc_180007579
0x1800075cf  call    cs:__imp_GetProcessHeap
0x1800075d5  mov     r8, rbp; lpMem
0x1800075d8  xor     edx, edx; dwFlags
0x1800075da  mov     rcx, rax; hHeap
0x1800075dd  call    cs:__imp_HeapFree
0x1800075e3  jmp     short loc_180007579
0x1800075e5  mov     ecx, 3
0x1800075ea  int     29h; Win8: RtlFailFast(ecx)
0x1800075ec  lea     rcx, [rbx+38h]; Resource
0x1800075f0  call    cs:__imp_RtlReleaseResource
0x1800075f6  or      eax, 0FFFFFFFFh
0x1800075f9  lock xadd [rbx], eax
0x1800075fd  cmp     eax, 1
0x180007600  jnz     short loc_18000760A
0x180007602  mov     rcx, rbx; lpMem
0x180007605  call    DestroyEntity
0x18000760a  call    cs:__imp_GetProcessHeap
0x180007610  mov     r8, rdi; lpMem
0x180007613  xor     edx, edx; dwFlags
0x180007615  mov     rcx, rax; hHeap
0x180007618  call    cs:__imp_HeapFree
0x18000761e  xor     eax, eax
0x180007620  jmp     short loc_180007627
0x180007622  mov     eax, 6
0x180007627  mov     rbx, [rsp+38h+arg_8]
0x18000762c  mov     rbp, [rsp+38h+arg_10]
0x180007631  add     rsp, 20h
0x180007635  pop     r14
0x180007637  pop     rdi
0x180007638  pop     rsi
0x180007639  retn
```
