# CleanupAfterDeregister

- ea: `0x180008ebc`
- end: `0x180009110`
- name: `CleanupAfterDeregister`
- size: `596`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x18000a820`

## callees

- `0x180005c00`
- `0x180005dc0`
- `0x1800060a0`
- `0x180006780`
- `0x180006990`
- `0x180008ba0`
- `0x180008ebc`
- `0x18000a298`
- `0x18000b294`
- `0x18000b2d8`
- `0x18000c560`
- `0x18000d9d0`

## import_xrefs

- `ntdll!RtlReleaseResource` at `0x180008fef`
- `ntdll!RtlReleaseResource` at `0x180008fef`
- `ntdll!RtlAcquireResourceShared` at `0x180008fd4`
- `ntdll!RtlAcquireResourceShared` at `0x180008fd4`
- `KERNEL32!HeapAlloc` at `0x180008f0f`
- `KERNEL32!HeapAlloc` at `0x180008f0f`
- `KERNEL32!GetProcessHeap` at `0x180008f01`
- `KERNEL32!GetProcessHeap` at `0x1800090eb`
- `KERNEL32!GetProcessHeap` at `0x180008f01`
- `KERNEL32!GetProcessHeap` at `0x1800090eb`
- `KERNEL32!HeapFree` at `0x1800090f9`
- `KERNEL32!HeapFree` at `0x1800090f9`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000901e`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18000901e`

## pseudocode

```c
int __fastcall CleanupAfterDeregister(__int64 a1)
{
  __int64 *v1; // r12
  __int64 v2; // r13
  HANDLE *v4; // rax
  unsigned int v5; // ebx
  HANDLE ProcessHeap; // rax
  HANDLE *v7; // r14
  void *v8; // rsi
  DWORD EnumRoutes; // eax
  HANDLE v10; // rdi
  unsigned int v11; // ebx
  unsigned int i; // r15d
  __int64 v13; // r15
  struct _RTL_RESOURCE *v14; // rdi
  __int64 v15; // rbx
  void *v16; // rcx
  void *j; // rbx
  HANDLE *v18; // rdx
  _QWORD *v19; // rdx
  DWORD EnumNextHops; // eax
  HANDLE v21; // rbx
  unsigned int v22; // r15d
  __int64 k; // rdi
  HANDLE v24; // rax
  unsigned int NumRoutes; // [rsp+A0h] [rbp+48h] BYREF
  DWORD ChangeFlags; // [rsp+A8h] [rbp+50h] BYREF
  LPVOID lpMem; // [rsp+B0h] [rbp+58h] BYREF
  HANDLE EnumHandle; // [rsp+B8h] [rbp+60h] BYREF

  v1 = (__int64 *)(a1 + 16);
  v2 = *(_QWORD *)(a1 + 16);
  ChangeFlags = 0;
  EnumHandle = 0;
  v4 = (HANDLE *)(8LL * *(unsigned int *)(v2 + 304));
  if ( (unsigned __int64)v4 <= 0xFFFFFFFF )
  {
    v5 = 8 * *(_DWORD *)(v2 + 304);
    ProcessHeap = GetProcessHeap();
    v4 = (HANDLE *)HeapAlloc(ProcessHeap, 0, v5);
    v7 = v4;
    if ( v4 )
    {
      v8 = (void *)(a1 ^ 0x7754DF32);
      EnumRoutes = RtmCreateRouteEnum(v8, 0, 0, 0x10000u, 0, 0, 0, 0, &EnumHandle);
      v10 = EnumHandle;
      while ( !EnumRoutes )
      {
        NumRoutes = *(_DWORD *)(v2 + 304);
        EnumRoutes = RtmGetEnumRoutes(v8, v10, &NumRoutes, v7);
        v11 = 0;
        for ( i = NumRoutes; v11 < i; ++v11 )
          EnumRoutes = RtmDeleteRouteToDest(v8, v7[v11], &ChangeFlags);
      }
      if ( v10 )
        RtmDeleteEnumHandle(v8, v10);
      lpMem = 0;
      v13 = *v1;
      v14 = (struct _RTL_RESOURCE *)(*v1 + 608);
      v15 = **(_QWORD **)(*v1 + 712);
      RtlAcquireResourceShared(v14, 1u);
      GetHoldDownRoutes(v13, v15, v8, &lpMem);
      RtlReleaseResource(v14);
      v16 = lpMem;
      for ( j = lpMem; v16; lpMem = v16 )
      {
        v18 = *(HANDLE **)(*(_QWORD *)v16 + 40LL);
        if ( v18 )
        {
          DeleteTimerQueueTimer(*(HANDLE *)(v13 + 728), *v18, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
          v16 = lpMem;
          v19 = *(_QWORD **)(*(_QWORD *)lpMem + 40LL);
          if ( v19 )
          {
            *v19 = 0;
            RouteHolddownTimeoutCallback(*(PVOID *)(*(_QWORD *)lpMem + 40LL), 1u);
            v16 = lpMem;
          }
        }
        if ( _InterlockedExchangeAdd(*(volatile signed __int32 **)v16, 0xFFFFFFFF) == 1 )
          DestroyRoute(*(LPVOID *)lpMem);
        v16 = (void *)*((_QWORD *)lpMem + 1);
      }
      DestroyRouteList(j);
      EnumNextHops = RtmCreateNextHopEnum(v8, 0, 0, &EnumHandle);
      v21 = EnumHandle;
      while ( !EnumNextHops )
      {
        NumRoutes = *(_DWORD *)(v2 + 304);
        EnumNextHops = RtmGetEnumNextHops(v8, v21, &NumRoutes, v7);
        v22 = NumRoutes;
        for ( k = 0; (unsigned int)k < v22; k = (unsigned int)(k + 1) )
          EnumNextHops = RtmDeleteNextHop(v8, v7[k], 0);
      }
      if ( v21 )
        RtmDeleteEnumHandle(v8, v21);
      v24 = GetProcessHeap();
      LODWORD(v4) = HeapFree(v24, 0, v7);
    }
  }
  return (int)v4;
}

```

## disassembly

```asm
0x180008ebc  push    rbp
0x180008ebe  push    rbx
0x180008ebf  push    rsi
0x180008ec0  push    rdi
0x180008ec1  push    r12
0x180008ec3  push    r13
0x180008ec5  push    r14
0x180008ec7  push    r15
0x180008ec9  mov     rbp, rsp
0x180008ecc  sub     rsp, 58h
0x180008ed0  xor     r15d, r15d
0x180008ed3  lea     r12, [rcx+10h]
0x180008ed7  mov     r13, [r12]
0x180008edb  mov     rsi, rcx
0x180008ede  mov     [rbp+ChangeFlags], r15d
0x180008ee2  mov     ecx, 0FFFFFFFFh
0x180008ee7  mov     [rbp+EnumHandle], r15
0x180008eeb  mov     eax, [r13+130h]
0x180008ef2  shl     rax, 3
0x180008ef6  cmp     rax, rcx
0x180008ef9  ja      loc_1800090FF
0x180008eff  mov     ebx, eax
0x180008f01  call    cs:__imp_GetProcessHeap
0x180008f07  mov     r8d, ebx; dwBytes
0x180008f0a  xor     edx, edx; dwFlags
0x180008f0c  mov     rcx, rax; hHeap
0x180008f0f  call    cs:__imp_HeapAlloc
0x180008f15  mov     r14, rax
0x180008f18  test    rax, rax
0x180008f1b  jz      loc_1800090FF
0x180008f21  lea     rax, [rbp+EnumHandle]
0x180008f25  xor     rsi, 7754DF32h
0x180008f2c  mov     [rsp+58h+RtmEnumHandle], rax; RtmEnumHandle
0x180008f31  mov     r9d, 10000h; EnumFlags
0x180008f37  mov     [rsp+58h+CriteriaInterface], r15d; CriteriaInterface
0x180008f3c  xor     r8d, r8d; TargetViews
0x180008f3f  mov     [rsp+58h+CriteriaRoute], r15; CriteriaRoute
0x180008f44  xor     edx, edx; DestHandle
0x180008f46  mov     [rsp+58h+MatchingFlags], r15d; MatchingFlags
0x180008f4b  mov     rcx, rsi; RtmRegHandle
0x180008f4e  mov     [rsp+58h+StartDest], r15; StartDest
0x180008f53  call    RtmCreateRouteEnum
0x180008f58  mov     rdi, [rbp+EnumHandle]
0x180008f5c  jmp     short loc_180008FA2
0x180008f5e  mov     eax, [r13+130h]
0x180008f65  lea     r8, [rbp+NumRoutes]; NumRoutes
0x180008f69  mov     r9, r14; RouteHandles
0x180008f6c  mov     [rbp+NumRoutes], eax
0x180008f6f  mov     rdx, rdi; EnumHandle
0x180008f72  mov     rcx, rsi; RtmRegHandle
0x180008f75  call    RtmGetEnumRoutes
0x180008f7a  mov     ebx, r15d
0x180008f7d  mov     r15d, [rbp+NumRoutes]
0x180008f81  test    r15d, r15d
0x180008f84  jz      short loc_180008F9F
0x180008f86  mov     edx, ebx
0x180008f88  lea     r8, [rbp+ChangeFlags]; ChangeFlags
0x180008f8c  mov     rcx, rsi; RtmRegHandle
0x180008f8f  mov     rdx, [r14+rdx*8]; RouteHandle
0x180008f93  call    RtmDeleteRouteToDest
0x180008f98  inc     ebx
0x180008f9a  cmp     ebx, r15d
0x180008f9d  jb      short loc_180008F86
0x180008f9f  xor     r15d, r15d
0x180008fa2  test    eax, eax
0x180008fa4  jz      short loc_180008F5E
0x180008fa6  test    rdi, rdi
0x180008fa9  jz      short loc_180008FB6
0x180008fab  mov     rdx, rdi; EnumHandle
0x180008fae  mov     rcx, rsi; RtmRegHandle
0x180008fb1  call    RtmDeleteEnumHandle
0x180008fb6  mov     [rbp+lpMem], r15
0x180008fba  mov     dl, 1; Wait
0x180008fbc  mov     r15, [r12]
0x180008fc0  mov     rax, [r15+2C8h]
0x180008fc7  lea     rdi, [r15+260h]
0x180008fce  mov     rcx, rdi; Resource
0x180008fd1  mov     rbx, [rax]
0x180008fd4  call    cs:__imp_RtlAcquireResourceShared
0x180008fda  lea     r9, [rbp+lpMem]
0x180008fde  mov     r8, rsi
0x180008fe1  mov     rdx, rbx
0x180008fe4  mov     rcx, r15
0x180008fe7  call    GetHoldDownRoutes
0x180008fec  mov     rcx, rdi; Resource
0x180008fef  call    cs:__imp_RtlReleaseResource
0x180008ff5  mov     rcx, [rbp+lpMem]
0x180008ff9  mov     rbx, rcx
0x180008ffc  test    rcx, rcx
0x180008fff  jz      short loc_18000907B
0x180009001  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180009005  mov     rax, [rcx]
0x180009008  mov     rdx, [rax+28h]
0x18000900c  test    rdx, rdx
0x18000900f  jz      short loc_180009051
0x180009011  mov     rdx, [rdx]; Timer
0x180009014  mov     r8, rdi; CompletionEvent
0x180009017  mov     rcx, [r15+2D8h]; TimerQueue
0x18000901e  call    cs:__imp_DeleteTimerQueueTimer
0x180009024  mov     rcx, [rbp+lpMem]
0x180009028  mov     rax, [rcx]
0x18000902b  mov     rdx, [rax+28h]
0x18000902f  test    rdx, rdx
0x180009032  jz      short loc_180009051
0x180009034  mov     qword ptr [rdx], 0
0x18000903b  mov     dl, 1; BOOLEAN
0x18000903d  mov     rax, [rbp+lpMem]
0x180009041  mov     rcx, [rax]
0x180009044  mov     rcx, [rcx+28h]; PVOID
0x180009048  call    RouteHolddownTimeoutCallback
0x18000904d  mov     rcx, [rbp+lpMem]
0x180009051  mov     rax, [rcx]
0x180009054  mov     ecx, edi
0x180009056  lock xadd [rax], ecx
0x18000905a  add     ecx, edi
0x18000905c  jnz     short loc_18000906A
0x18000905e  mov     rcx, [rbp+lpMem]
0x180009062  mov     rcx, [rcx]; lpMem
0x180009065  call    DestroyRoute
0x18000906a  mov     rax, [rbp+lpMem]
0x18000906e  mov     rcx, [rax+8]
0x180009072  mov     [rbp+lpMem], rcx
0x180009076  test    rcx, rcx
0x180009079  jnz     short loc_180009005
0x18000907b  mov     rcx, rbx; lpMem
0x18000907e  call    DestroyRouteList
0x180009083  lea     r9, [rbp+EnumHandle]; RtmEnumHandle
0x180009087  xor     r8d, r8d; NetAddress
0x18000908a  xor     edx, edx; EnumFlags
0x18000908c  mov     rcx, rsi; RtmRegHandle
0x18000908f  call    RtmCreateNextHopEnum
0x180009094  mov     rbx, [rbp+EnumHandle]
0x180009098  jmp     short loc_1800090D7
0x18000909a  mov     eax, [r13+130h]
0x1800090a1  lea     r8, [rbp+NumRoutes]; NumNextHops
0x1800090a5  mov     r9, r14; NextHopHandles
0x1800090a8  mov     [rbp+NumRoutes], eax
0x1800090ab  mov     rdx, rbx; EnumHandle
0x1800090ae  mov     rcx, rsi; RtmRegHandle
0x1800090b1  call    RtmGetEnumNextHops
0x1800090b6  mov     r15d, [rbp+NumRoutes]
0x1800090ba  xor     edi, edi
0x1800090bc  test    r15d, r15d
0x1800090bf  jz      short loc_1800090D7
0x1800090c1  mov     rdx, [r14+rdi*8]; NextHopHandle
0x1800090c5  xor     r8d, r8d; NextHopInfo
0x1800090c8  mov     rcx, rsi; RtmRegHandle
0x1800090cb  call    RtmDeleteNextHop
0x1800090d0  inc     edi
0x1800090d2  cmp     edi, r15d
0x1800090d5  jb      short loc_1800090C1
0x1800090d7  test    eax, eax
0x1800090d9  jz      short loc_18000909A
0x1800090db  test    rbx, rbx
0x1800090de  jz      short loc_1800090EB
0x1800090e0  mov     rdx, rbx; EnumHandle
0x1800090e3  mov     rcx, rsi; RtmRegHandle
0x1800090e6  call    RtmDeleteEnumHandle
0x1800090eb  call    cs:__imp_GetProcessHeap
0x1800090f1  mov     r8, r14; lpMem
0x1800090f4  xor     edx, edx; dwFlags
0x1800090f6  mov     rcx, rax; hHeap
0x1800090f9  call    cs:__imp_HeapFree
0x1800090ff  add     rsp, 58h
0x180009103  pop     r15
0x180009105  pop     r14
0x180009107  pop     r13
0x180009109  pop     r12
0x18000910b  pop     rdi
0x18000910c  pop     rsi
0x18000910d  pop     rbx
0x18000910e  pop     rbp
0x18000910f  retn
```
