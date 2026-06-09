# CDeviceCache::s_EnsureDeviceCache(void)

- ea: `0x18000d338`
- end: `0x18000d537`
- name: `?s_EnsureDeviceCache@CDeviceCache@@CAJXZ`
- size: `511`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000ce68`

## callees

- `0x18000d338`
- `0x18000d540`
- `0x18002ff5c`
- `0x180078010`

## import_xrefs

- `KERNEL32!HeapAlloc` at `0x18000d379`
- `KERNEL32!HeapAlloc` at `0x18000d379`
- `KERNEL32!GetProcessHeap` at `0x18000d367`
- `KERNEL32!GetProcessHeap` at `0x18000d367`
- `KERNEL32!EnterCriticalSection` at `0x18000d348`
- `KERNEL32!EnterCriticalSection` at `0x18000d348`
- `KERNEL32!LeaveCriticalSection` at `0x18000d4f8`
- `KERNEL32!LeaveCriticalSection` at `0x18000d4f8`
- `KERNEL32!CreateEventW` at `0x18000d413`
- `KERNEL32!CreateEventW` at `0x18000d430`
- `KERNEL32!CreateEventW` at `0x18000d44d`
- `KERNEL32!CreateEventW` at `0x18000d466`
- `KERNEL32!CreateEventW` at `0x18000d413`
- `KERNEL32!CreateEventW` at `0x18000d430`
- `KERNEL32!CreateEventW` at `0x18000d44d`
- `KERNEL32!CreateEventW` at `0x18000d466`
- `KERNEL32!CreateThread` at `0x18000d48c`
- `KERNEL32!CreateThread` at `0x18000d48c`
- `KERNEL32!WaitForMultipleObjects` at `0x18000d4bc`
- `KERNEL32!WaitForMultipleObjects` at `0x18000d4bc`

## pseudocode

```c
__int64 CDeviceCache::s_EnsureDeviceCache(void)
{
  int v0; // ebx
  HANDLE ProcessHeap; // rax
  _QWORD *v2; // rdi
  __int64 v3; // rax
  HANDLE EventW; // rax
  HANDLE v5; // rax
  HANDLE v6; // rax
  HANDLE v7; // rax
  HANDLE Thread; // rax
  void *v9; // rcx
  void *v10; // rax
  HANDLE Handles[7]; // [rsp+30h] [rbp-38h] BYREF

  EnterCriticalSection(&g_csDeviceCache);
  if ( g_pDeviceCache )
  {
    v0 = 0;
  }
  else
  {
    ProcessHeap = GetProcessHeap();
    v2 = HeapAlloc(ProcessHeap, 8u, 0x58u);
    if ( !v2 )
    {
      v0 = -2147024882;
      goto LABEL_19;
    }
    *v2 = &CDeviceCache::`vftable';
    v2[1] = 0;
    v2[2] = 0;
    v2[3] = 0;
    v2[4] = 0;
    v2[5] = 0;
    v2[6] = 0;
    v2[7] = 0;
    v2[8] = 0;
    v2[9] = 0;
    *((_DWORD *)v2 + 20) = 0;
    v3 = IsolationAwareDPA_Create(10);
    v2[1] = v3;
    if ( v3 )
    {
      EventW = CreateEventW(0, 0, 0, 0);
      v2[3] = EventW;
      if ( EventW )
      {
        v5 = CreateEventW(0, 0, 0, 0);
        v2[4] = v5;
        if ( v5 )
        {
          v6 = CreateEventW(0, 0, 0, 0);
          v2[5] = v6;
          if ( v6 )
          {
            v7 = CreateEventW(0, 0, 0, 0);
            v2[6] = v7;
            if ( v7 )
            {
              Thread = CreateThread(0, 0, GlobalInterfaceThreadProc, v2, 0, 0);
              v2[2] = Thread;
              v9 = Thread;
              if ( Thread )
              {
                v10 = (void *)v2[4];
                Handles[1] = v9;
                Handles[0] = v10;
                WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
              }
              if ( *((_DWORD *)v2 + 14) )
              {
                v0 = 0;
                g_pDeviceCache = (struct CDeviceCache *)v2;
                goto LABEL_19;
              }
            }
          }
        }
      }
      v0 = -2147467259;
    }
    else
    {
      v0 = -2147024882;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, 2147942414LL);
    }
    (*(void (__fastcall **)(_QWORD *, __int64))*v2)(v2, 1);
  }
LABEL_19:
  LeaveCriticalSection(&g_csDeviceCache);
  if ( v0 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids, (unsigned int)v0);
  return (unsigned int)v0;
}

```

## disassembly

```asm
0x18000d338  push    rbx
0x18000d33a  push    rbp
0x18000d33b  push    rsi
0x18000d33c  push    rdi
0x18000d33d  sub     rsp, 48h
0x18000d341  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d348  call    cs:__imp_EnterCriticalSection
0x18000d34e  xor     esi, esi
0x18000d350  lea     rbp, WPP_GLOBAL_Control
0x18000d357  cmp     cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA, rsi; CDeviceCache * g_pDeviceCache
0x18000d35e  jz      short loc_18000D367
0x18000d360  mov     ebx, esi
0x18000d362  jmp     loc_18000D4F1
0x18000d367  call    cs:__imp_GetProcessHeap
0x18000d36d  mov     edx, 8; dwFlags
0x18000d372  mov     rcx, rax; hHeap
0x18000d375  lea     r8d, [rdx+50h]; dwBytes
0x18000d379  call    cs:__imp_HeapAlloc
0x18000d37f  mov     rdi, rax
0x18000d382  test    rax, rax
0x18000d385  jz      loc_18000D4EC
0x18000d38b  lea     rax, ??_7CDeviceCache@@6B@; const CDeviceCache::`vftable'
0x18000d392  mov     ecx, 0Ah
0x18000d397  mov     [rdi], rax
0x18000d39a  mov     [rdi+8], rsi
0x18000d39e  mov     [rdi+10h], rsi
0x18000d3a2  mov     [rdi+18h], rsi
0x18000d3a6  mov     [rdi+20h], rsi
0x18000d3aa  mov     [rdi+28h], rsi
0x18000d3ae  mov     [rdi+30h], rsi
0x18000d3b2  mov     [rdi+38h], rsi
0x18000d3b6  mov     [rdi+40h], rsi
0x18000d3ba  mov     [rdi+48h], rsi
0x18000d3be  mov     [rdi+50h], esi
0x18000d3c1  call    IsolationAwareDPA_Create
0x18000d3c6  mov     [rdi+8], rax
0x18000d3ca  test    rax, rax
0x18000d3cd  jnz     short loc_18000D409
0x18000d3cf  mov     ebx, 8007000Eh
0x18000d3d4  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d3db  cmp     rcx, rbp
0x18000d3de  jz      loc_18000D4CC
0x18000d3e4  test    byte ptr [rcx+1Ch], 2
0x18000d3e8  jz      loc_18000D4CC
0x18000d3ee  mov     rcx, [rcx+10h]
0x18000d3f2  lea     edx, [rax+0Bh]
0x18000d3f5  mov     r9d, ebx
0x18000d3f8  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d3ff  call    WPP_SF_d
0x18000d404  jmp     loc_18000D4CC
0x18000d409  xor     r9d, r9d; lpName
0x18000d40c  xor     r8d, r8d; bInitialState
0x18000d40f  xor     edx, edx; bManualReset
0x18000d411  xor     ecx, ecx; lpEventAttributes
0x18000d413  call    cs:__imp_CreateEventW
0x18000d419  mov     [rdi+18h], rax
0x18000d41d  test    rax, rax
0x18000d420  jz      loc_18000D4C7
0x18000d426  xor     r9d, r9d; lpName
0x18000d429  xor     r8d, r8d; bInitialState
0x18000d42c  xor     edx, edx; bManualReset
0x18000d42e  xor     ecx, ecx; lpEventAttributes
0x18000d430  call    cs:__imp_CreateEventW
0x18000d436  mov     [rdi+20h], rax
0x18000d43a  test    rax, rax
0x18000d43d  jz      loc_18000D4C7
0x18000d443  xor     r9d, r9d; lpName
0x18000d446  xor     r8d, r8d; bInitialState
0x18000d449  xor     edx, edx; bManualReset
0x18000d44b  xor     ecx, ecx; lpEventAttributes
0x18000d44d  call    cs:__imp_CreateEventW
0x18000d453  mov     [rdi+28h], rax
0x18000d457  test    rax, rax
0x18000d45a  jz      short loc_18000D4C7
0x18000d45c  xor     r9d, r9d; lpName
0x18000d45f  xor     r8d, r8d; bInitialState
0x18000d462  xor     edx, edx; bManualReset
0x18000d464  xor     ecx, ecx; lpEventAttributes
0x18000d466  call    cs:__imp_CreateEventW
0x18000d46c  mov     [rdi+30h], rax
0x18000d470  test    rax, rax
0x18000d473  jz      short loc_18000D4C7
0x18000d475  mov     [rsp+68h+lpThreadId], rsi; lpThreadId
0x18000d47a  lea     r8, ?GlobalInterfaceThreadProc@@YAKPEAX@Z; lpStartAddress
0x18000d481  mov     r9, rdi; lpParameter
0x18000d484  mov     [rsp+68h+dwCreationFlags], esi; dwCreationFlags
0x18000d488  xor     edx, edx; dwStackSize
0x18000d48a  xor     ecx, ecx; lpThreadAttributes
0x18000d48c  call    cs:__imp_CreateThread
0x18000d492  mov     [rdi+10h], rax
0x18000d496  mov     rcx, rax
0x18000d499  test    rax, rax
0x18000d49c  jz      short loc_18000D4C2
0x18000d49e  mov     rax, [rdi+20h]
0x18000d4a2  lea     rdx, [rsp+68h+Handles]; lpHandles
0x18000d4a7  xor     r8d, r8d; bWaitAll
0x18000d4aa  mov     [rsp+68h+var_30], rcx
0x18000d4af  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x18000d4b3  mov     [rsp+68h+Handles], rax
0x18000d4b8  lea     ecx, [r8+2]; nCount
0x18000d4bc  call    cs:__imp_WaitForMultipleObjects
0x18000d4c2  cmp     [rdi+38h], esi
0x18000d4c5  jnz     short loc_18000D4E1
0x18000d4c7  mov     ebx, 80004005h
0x18000d4cc  mov     rax, [rdi]
0x18000d4cf  mov     edx, 1
0x18000d4d4  mov     rcx, rdi
0x18000d4d7  mov     rax, [rax]
0x18000d4da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d4df  jmp     short loc_18000D4F1
0x18000d4e1  mov     ebx, esi
0x18000d4e3  mov     cs:?g_pDeviceCache@@3PEAVCDeviceCache@@EA, rdi; CDeviceCache * g_pDeviceCache
0x18000d4ea  jmp     short loc_18000D4F1
0x18000d4ec  mov     ebx, 8007000Eh
0x18000d4f1  lea     rcx, ?g_csDeviceCache@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18000d4f8  call    cs:__imp_LeaveCriticalSection
0x18000d4fe  test    ebx, ebx
0x18000d500  jns     short loc_18000D52C
0x18000d502  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d509  cmp     rcx, rbp
0x18000d50c  jz      short loc_18000D52C
0x18000d50e  test    byte ptr [rcx+1Ch], 2
0x18000d512  jz      short loc_18000D52C
0x18000d514  mov     rcx, [rcx+10h]
0x18000d518  lea     r8, WPP_97b3e7d056e530596454d4c68ce08f99_Traceguids
0x18000d51f  mov     edx, 0Ch
0x18000d524  mov     r9d, ebx
0x18000d527  call    WPP_SF_d
0x18000d52c  mov     eax, ebx
0x18000d52e  add     rsp, 48h
0x18000d532  pop     rdi
0x18000d533  pop     rsi
0x18000d534  pop     rbp
0x18000d535  pop     rbx
0x18000d536  retn
```
