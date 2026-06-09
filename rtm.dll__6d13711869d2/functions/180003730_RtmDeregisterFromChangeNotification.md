# RtmDeregisterFromChangeNotification

- ea: `0x180003730`
- end: `0x180003990`
- name: `RtmDeregisterFromChangeNotification`
- size: `608`
- prototype: `DWORD __stdcall(RTM_ENTITY_HANDLE RtmRegHandle, RTM_NOTIFY_HANDLE NotifyHandle)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180012100`

## callees

- `0x180002150`
- `0x180002dd0`
- `0x180003730`
- `0x180009adc`
- `0x18000a1bc`
- `0x18001f952`
- `0x18001f980`

## import_xrefs

- `ntdll!RtlAcquireResourceExclusive` at `0x1800037ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800038c2`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800037ac`
- `ntdll!RtlAcquireResourceExclusive` at `0x1800038c2`
- `ntdll!RtlReleaseResource` at `0x18000380b`
- `ntdll!RtlReleaseResource` at `0x1800038ae`
- `ntdll!RtlReleaseResource` at `0x1800038e0`
- `ntdll!RtlReleaseResource` at `0x18000380b`
- `ntdll!RtlReleaseResource` at `0x1800038ae`
- `ntdll!RtlReleaseResource` at `0x1800038e0`
- `ntdll!RtlAcquireResourceShared` at `0x18000383d`
- `ntdll!RtlAcquireResourceShared` at `0x18000383d`
- `KERNEL32!GetProcessHeap` at `0x180003948`
- `KERNEL32!GetProcessHeap` at `0x180003948`
- `KERNEL32!HeapFree` at `0x180003956`
- `KERNEL32!HeapFree` at `0x180003956`
- `KERNEL32!DeleteCriticalSection` at `0x180003930`
- `KERNEL32!DeleteCriticalSection` at `0x180003930`

## pseudocode

```c
DWORD __stdcall RtmDeregisterFromChangeNotification(RTM_ENTITY_HANDLE RtmRegHandle, RTM_NOTIFY_HANDLE NotifyHandle)
{
  unsigned __int64 v4; // rsi
  unsigned __int64 v5; // rbx
  __int64 v6; // rdi
  __int64 v7; // r12
  char v8; // cl
  int v9; // r13d
  unsigned int v10; // ecx
  int v11; // r8d
  __int64 v12; // rdx
  __int64 i; // rax
  int v14; // eax
  unsigned int v15; // r9d
  __int64 v16; // r8
  int j; // r14d
  __int64 v18; // rdx
  int v19; // eax
  unsigned int v20; // edx
  volatile signed __int32 *v21; // rdx
  HANDLE ProcessHeap; // rax
  int v24; // [rsp+40h] [rbp-138h] BYREF
  __int128 v25; // [rsp+48h] [rbp-130h] BYREF
  int v26; // [rsp+58h] [rbp-120h]
  _QWORD v27[26]; // [rsp+60h] [rbp-118h] BYREF

  memset_0(v27, 0, 0xC8u);
  v4 = (unsigned __int64)RtmRegHandle ^ 0x7754DF32;
  if ( !v4 )
    return 6;
  if ( *(_DWORD *)(v4 + 48) == 1 )
    return 6;
  v5 = (unsigned __int64)NotifyHandle ^ 0x7754DF32;
  if ( !v5 || *(int *)(v5 + 28) < 0 )
    return 6;
  v6 = *(_QWORD *)(v4 + 16);
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v6 + 744), 1u);
  v7 = *(int *)(v5 + 28);
  v8 = *(_DWORD *)(v5 + 28);
  *(_DWORD *)(v5 + 28) = -1;
  v9 = 1 << v8;
  v10 = -1;
  v11 = ~v9;
  *(_DWORD *)(v6 + 864) &= ~v9;
  *(_DWORD *)(v6 + 868) &= ~v9;
  v12 = 0;
  do
  {
    if ( (v10 & 1) != 0 )
      *(_DWORD *)(v6 + 4 * v12 + 872) &= v11;
    v12 = (unsigned int)(v12 + 1);
    v10 >>= 1;
  }
  while ( v10 );
  for ( i = 0; i != 3; ++i )
    *(_DWORD *)(v6 + 4 * i + 1000) &= v11;
  RtlReleaseResource((PRTL_RESOURCE)(v6 + 744));
  ProcessChangedDestLists((char *)v6);
  v25 = 0;
  v26 = 0;
  do
  {
    v24 = 25;
    RtlAcquireResourceShared((PRTL_RESOURCE)(v6 + 608), 1u);
    v14 = EnumOverTable(
            *(_QWORD *)(v6 + 712),
            (unsigned int)&v25 + 2,
            (unsigned int)&v25 + 4,
            0,
            0,
            0,
            (__int64)&v24,
            (__int64)v27);
    v15 = v24;
    v16 = 0;
    for ( j = v14; (unsigned int)v16 < v15; v16 = (unsigned int)(v16 + 1) )
    {
      v18 = v27[v16];
      if ( (v9 & *(_DWORD *)(v18 + 24)) != 0 )
        _InterlockedAdd((volatile signed __int32 *)(v18 + 24), -1 << v7);
    }
    RtlReleaseResource((PRTL_RESOURCE)(v6 + 608));
  }
  while ( !j );
  RtlAcquireResourceExclusive((PRTL_RESOURCE)(v6 + 744), 1u);
  *(_QWORD *)(*(_QWORD *)(v6 + 856) + 8 * v7) = 0;
  --*(_DWORD *)(v6 + 848);
  RtlReleaseResource((PRTL_RESOURCE)(v6 + 744));
  while ( 1 )
  {
    v19 = *(_DWORD *)(v5 + 80);
    if ( v19 == *(_DWORD *)(v5 + 84) )
      break;
    v20 = (unsigned int)(v19 + 1) % *(_DWORD *)(v5 + 88);
    *(_DWORD *)(v5 + 80) = v20;
    v21 = *(volatile signed __int32 **)(v5 + 8LL * v20 + 96);
    if ( !v21 )
      break;
    if ( (v9 & v21[12]) != 0 )
      _InterlockedAdd(v21 + 12, -1 << v7);
    if ( _InterlockedExchangeAdd(v21, 0xFFFFFFFF) == 1 )
      DestroyDest((LPVOID)v21);
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)(v5 + 32));
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4, 0xFFFFFFFF) == 1 )
    DestroyEntity((char *)v4);
  ProcessHeap = GetProcessHeap();
  HeapFree(ProcessHeap, 0, (LPVOID)v5);
  return 0;
}

```

## disassembly

```asm
0x180003730  mov     [rsp+arg_10], rbx
0x180003735  push    rbp
0x180003736  push    rsi
0x180003737  push    rdi
0x180003738  push    r12
0x18000373a  push    r13
0x18000373c  push    r14
0x18000373e  push    r15
0x180003740  sub     rsp, 140h
0x180003747  mov     rax, cs:__security_cookie
0x18000374e  xor     rax, rsp
0x180003751  mov     [rsp+178h+var_48], rax
0x180003759  mov     rbx, rdx
0x18000375c  mov     rsi, rcx
0x18000375f  xor     edx, edx; Val
0x180003761  lea     rcx, [rsp+178h+var_118]; void *
0x180003766  mov     r8d, 0C8h; Size
0x18000376c  call    memset_0
0x180003771  mov     eax, 7754DF32h
0x180003776  xor     rsi, rax
0x180003779  jz      loc_180003960
0x18000377f  cmp     dword ptr [rsi+30h], 1
0x180003783  jz      loc_180003960
0x180003789  xor     rbx, rax
0x18000378c  jz      loc_180003960
0x180003792  cmp     dword ptr [rbx+1Ch], 0
0x180003796  jl      loc_180003960
0x18000379c  mov     rdi, [rsi+10h]
0x1800037a0  mov     dl, 1; Wait
0x1800037a2  lea     r15, [rdi+2E8h]
0x1800037a9  mov     rcx, r15; Resource
0x1800037ac  call    cs:__imp_RtlAcquireResourceExclusive
0x1800037b2  movsxd  r12, dword ptr [rbx+1Ch]
0x1800037b6  mov     r13d, 1
0x1800037bc  mov     ecx, r12d
0x1800037bf  mov     dword ptr [rbx+1Ch], 0FFFFFFFFh
0x1800037c6  shl     r13d, cl
0x1800037c9  or      ecx, 0FFFFFFFFh
0x1800037cc  mov     r8d, r13d
0x1800037cf  not     r8d
0x1800037d2  and     [rdi+360h], r8d
0x1800037d9  and     [rdi+364h], r8d
0x1800037e0  xor     edx, edx
0x1800037e2  test    cl, 1
0x1800037e5  jz      short loc_1800037EF
0x1800037e7  and     [rdi+rdx*4+368h], r8d
0x1800037ef  inc     edx
0x1800037f1  shr     ecx, 1
0x1800037f3  jnz     short loc_1800037E2
0x1800037f5  xor     eax, eax
0x1800037f7  and     [rdi+rax*4+3E8h], r8d
0x1800037ff  inc     rax
0x180003802  cmp     rax, 3
0x180003806  jnz     short loc_1800037F7
0x180003808  mov     rcx, r15; Resource
0x18000380b  call    cs:__imp_RtlReleaseResource
0x180003811  xor     edx, edx; BOOLEAN
0x180003813  mov     rcx, rdi; PVOID
0x180003816  call    ProcessChangedDestLists
0x18000381b  xorps   xmm0, xmm0
0x18000381e  lea     rbp, [rdi+260h]
0x180003825  xor     eax, eax
0x180003827  movups  [rsp+178h+var_130], xmm0
0x18000382c  mov     [rsp+178h+var_120], eax
0x180003830  mov     dl, 1; Wait
0x180003832  mov     [rsp+178h+var_138], 19h
0x18000383a  mov     rcx, rbp; Resource
0x18000383d  call    cs:__imp_RtlAcquireResourceShared
0x180003843  xor     eax, eax
0x180003845  lea     rcx, [rsp+178h+var_118]
0x18000384a  mov     [rsp+178h+var_140], rcx
0x18000384f  lea     r8, [rsp+178h+var_130+4]
0x180003854  lea     rcx, [rsp+178h+var_138]
0x180003859  xor     r9d, r9d
0x18000385c  mov     [rsp+178h+var_148], rcx
0x180003861  lea     rdx, [rsp+178h+var_130+2]
0x180003866  mov     rcx, [rdi+2C8h]
0x18000386d  mov     [rsp+178h+var_150], rax
0x180003872  mov     [rsp+178h+var_158], ax
0x180003877  call    EnumOverTable
0x18000387c  mov     r9d, [rsp+178h+var_138]
0x180003881  xor     r8d, r8d
0x180003884  mov     r14d, eax
0x180003887  test    r9d, r9d
0x18000388a  jz      short loc_1800038AB
0x18000388c  mov     rdx, [rsp+r8*8+178h+var_118]
0x180003891  test    [rdx+18h], r13d
0x180003895  jz      short loc_1800038A3
0x180003897  mov     ecx, r12d
0x18000389a  or      eax, 0FFFFFFFFh
0x18000389d  shl     eax, cl
0x18000389f  lock add [rdx+18h], eax
0x1800038a3  inc     r8d
0x1800038a6  cmp     r8d, r9d
0x1800038a9  jb      short loc_18000388C
0x1800038ab  mov     rcx, rbp; Resource
0x1800038ae  call    cs:__imp_RtlReleaseResource
0x1800038b4  test    r14d, r14d
0x1800038b7  jz      loc_180003830
0x1800038bd  mov     dl, 1; Wait
0x1800038bf  mov     rcx, r15; Resource
0x1800038c2  call    cs:__imp_RtlAcquireResourceExclusive
0x1800038c8  mov     rax, [rdi+358h]
0x1800038cf  mov     rcx, r15; Resource
0x1800038d2  mov     qword ptr [rax+r12*8], 0
0x1800038da  dec     dword ptr [rdi+350h]
0x1800038e0  call    cs:__imp_RtlReleaseResource
0x1800038e6  or      edi, 0FFFFFFFFh
0x1800038e9  mov     eax, [rbx+50h]
0x1800038ec  cmp     eax, [rbx+54h]
0x1800038ef  jz      short loc_18000392C
0x1800038f1  xor     edx, edx
0x1800038f3  inc     eax
0x1800038f5  div     dword ptr [rbx+58h]
0x1800038f8  mov     ecx, edx
0x1800038fa  mov     [rbx+50h], ecx
0x1800038fd  mov     rdx, [rbx+rdx*8+60h]
0x180003902  test    rdx, rdx
0x180003905  jz      short loc_18000392C
0x180003907  test    [rdx+30h], r13d
0x18000390b  jz      short loc_180003918
0x18000390d  mov     ecx, r12d
0x180003910  mov     eax, edi
0x180003912  shl     eax, cl
0x180003914  lock add [rdx+30h], eax
0x180003918  mov     eax, edi
0x18000391a  lock xadd [rdx], eax
0x18000391e  add     eax, edi
0x180003920  jnz     short loc_1800038E9
0x180003922  mov     rcx, rdx; lpMem
0x180003925  call    DestroyDest
0x18000392a  jmp     short loc_1800038E9
0x18000392c  lea     rcx, [rbx+20h]; lpCriticalSection
0x180003930  call    cs:__imp_DeleteCriticalSection
0x180003936  mov     eax, edi
0x180003938  lock xadd [rsi], eax
0x18000393c  add     eax, edi
0x18000393e  jnz     short loc_180003948
0x180003940  mov     rcx, rsi; lpMem
0x180003943  call    DestroyEntity
0x180003948  call    cs:__imp_GetProcessHeap
0x18000394e  mov     r8, rbx; lpMem
0x180003951  xor     edx, edx; dwFlags
0x180003953  mov     rcx, rax; hHeap
0x180003956  call    cs:__imp_HeapFree
0x18000395c  xor     eax, eax
0x18000395e  jmp     short loc_180003965
0x180003960  mov     eax, 6
0x180003965  mov     rcx, [rsp+178h+var_48]
0x18000396d  xor     rcx, rsp; StackCookie
0x180003970  call    __security_check_cookie
0x180003975  mov     rbx, [rsp+178h+arg_10]
0x18000397d  add     rsp, 140h
0x180003984  pop     r15
0x180003986  pop     r14
0x180003988  pop     r13
0x18000398a  pop     r12
0x18000398c  pop     rdi
0x18000398d  pop     rsi
0x18000398e  pop     rbp
0x18000398f  retn
```
