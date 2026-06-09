# RtmCreateRouteListEnum

- ea: `0x180007470`
- end: `0x180007528`
- name: `RtmCreateRouteListEnum`
- size: `184`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_ROUTE_LIST_HANDLE RouteListHandle, PRTM_ENUM_HANDLE RtmEnumHandle)`
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting`

## callees

- `0x180007470`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800074d4`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800074d4`
- `ntdll!RtlReleaseResource` at `0x180007503`
- `ntdll!RtlReleaseResource` at `0x180007503`
- `KERNEL32!HeapAlloc` at `0x1800074b4`
- `KERNEL32!HeapAlloc` at `0x1800074b4`
- `KERNEL32!GetProcessHeap` at `0x1800074a0`
- `KERNEL32!GetProcessHeap` at `0x1800074a0`

## pseudocode

```c
DWORD __stdcall RtmCreateRouteListEnum(
        RTM_ENTITY_HANDLE RtmRegHandle,
        RTM_ROUTE_LIST_HANDLE RouteListHandle,
        PRTM_ENUM_HANDLE RtmEnumHandle)
{
  unsigned __int64 v3; // rbx
  unsigned __int64 v5; // rsi
  HANDLE ProcessHeap; // rax
  _BYTE *v7; // rax
  unsigned __int64 v8; // rdi
  unsigned __int64 v10; // rsi
  __int64 v11; // rcx

  v3 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RtmRegHandle == 0x7754DF32 )
    return 6;
  if ( *(_DWORD *)(((unsigned __int64)RtmRegHandle ^ 0x7754DF32) + 0x30) == 1 )
    return 6;
  v5 = (unsigned __int64)RouteListHandle ^ 0x7754DF32;
  if ( (unsigned __int64)RouteListHandle == 0x7754DF32 )
    return 6;
  ProcessHeap = GetProcessHeap();
  v7 = HeapAlloc(ProcessHeap, 8u, 0x80u);
  v8 = (unsigned __int64)v7;
  if ( !v7 )
    return 8;
  v7[4] = 12;
  *((_QWORD *)v7 + 1) = v5;
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v3 + 56), 1u);
  v10 = v5 + 8;
  v11 = *(_QWORD *)v10;
  if ( *(_QWORD *)(*(_QWORD *)v10 + 8LL) != v10 )
    __fastfail(3u);
  *(_QWORD *)(v8 + 40) = v11;
  *(_QWORD *)(v8 + 48) = v10;
  *(_QWORD *)(v11 + 8) = v8 + 40;
  *(_QWORD *)v10 = v8 + 40;
  RtlReleaseResource((PRTL_RESOURCE)(v3 + 56));
  _InterlockedIncrement((volatile signed __int32 *)v3);
  *RtmEnumHandle = (HANDLE)(v8 ^ 0x7754DF32);
  return 0;
}

```

## disassembly

```asm
0x180007470  push    rbx
0x180007472  push    rbp
0x180007473  push    rsi
0x180007474  push    rdi
0x180007475  push    r14
0x180007477  push    r15
0x180007479  sub     rsp, 28h
0x18000747d  mov     rbx, rcx
0x180007480  mov     r15d, 7754DF32h
0x180007486  xor     rbx, r15
0x180007489  mov     r14, r8
0x18000748c  mov     rsi, rdx
0x18000748f  jz      loc_180007516
0x180007495  cmp     dword ptr [rbx+30h], 1
0x180007499  jz      short loc_180007516
0x18000749b  xor     rsi, r15
0x18000749e  jz      short loc_180007516
0x1800074a0  call    cs:__imp_GetProcessHeap
0x1800074a6  mov     ebp, 8
0x1800074ab  mov     rcx, rax; hHeap
0x1800074ae  mov     edx, ebp; dwFlags
0x1800074b0  lea     r8d, [rbp+78h]; dwBytes
0x1800074b4  call    cs:__imp_HeapAlloc
0x1800074ba  mov     rdi, rax
0x1800074bd  test    rax, rax
0x1800074c0  jnz     short loc_1800074C6
0x1800074c2  mov     eax, ebp
0x1800074c4  jmp     short loc_18000751B
0x1800074c6  mov     dl, 1; Wait
0x1800074c8  mov     byte ptr [rax+4], 0Ch
0x1800074cc  lea     rcx, [rbx+38h]; Resource
0x1800074d0  mov     [rax+8], rsi
0x1800074d4  call    cs:__imp_RtlAcquireResourceExclusive
0x1800074da  add     rsi, rbp
0x1800074dd  mov     rcx, [rsi]
0x1800074e0  cmp     [rcx+8], rsi
0x1800074e4  jz      short loc_1800074ED
0x1800074e6  mov     ecx, 3
0x1800074eb  int     29h; Win8: RtlFailFast(ecx)
0x1800074ed  lea     rax, [rdi+28h]
0x1800074f1  mov     [rax], rcx
0x1800074f4  mov     [rax+8], rsi
0x1800074f8  mov     [rcx+8], rax
0x1800074fc  lea     rcx, [rbx+38h]; Resource
0x180007500  mov     [rsi], rax
0x180007503  call    cs:__imp_RtlReleaseResource
0x180007509  lock inc dword ptr [rbx]
0x18000750c  xor     rdi, r15
0x18000750f  mov     [r14], rdi
0x180007512  xor     eax, eax
0x180007514  jmp     short loc_18000751B
0x180007516  mov     eax, 6
0x18000751b  add     rsp, 28h
0x18000751f  pop     r15
0x180007521  pop     r14
0x180007523  pop     rdi
0x180007524  pop     rsi
0x180007525  pop     rbp
0x180007526  pop     rbx
0x180007527  retn
```
