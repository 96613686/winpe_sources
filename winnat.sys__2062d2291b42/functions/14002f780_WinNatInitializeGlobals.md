# WinNatInitializeGlobals

- ea: `0x14002f780`
- end: `0x14002f9fa`
- name: `WinNatInitializeGlobals`
- size: `634`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140036078`

## callees

- `0x14000caa0`
- `0x14000d898`
- `0x14000da98`
- `0x14000dda4`
- `0x14001f320`
- `0x14001f680`
- `0x14001f980`
- `0x14002f780`

## import_xrefs

- `ntoskrnl!KeInitializeDpc` at `0x14002f908`
- `ntoskrnl!KeInitializeDpc` at `0x14002f908`
- `ntoskrnl!ExAllocatePool2` at `0x14002f83e`
- `ntoskrnl!ExAllocatePool2` at `0x14002f8be`
- `ntoskrnl!ExAllocatePool2` at `0x14002f83e`
- `ntoskrnl!ExAllocatePool2` at `0x14002f8be`
- `ntoskrnl!KeInitializeEvent` at `0x14002f816`
- `ntoskrnl!KeInitializeEvent` at `0x14002f816`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f7f7`
- `ntoskrnl!KeInitializeSpinLock` at `0x14002f7f7`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002f7a0`
- `ntoskrnl!KeQueryMaximumProcessorCountEx` at `0x14002f7a0`
- `NETIO!MdpCreatePool` at `0x14002f967`
- `NETIO!MdpCreatePool` at `0x14002f967`
- `NETIO!NetioInitializeWorkQueue` at `0x14002f88d`
- `NETIO!NetioInitializeWorkQueue` at `0x14002f88d`

## pseudocode

```c
__int64 __fastcall WinNatInitializeGlobals(struct _DRIVER_OBJECT *a1)
{
  __int64 MaximumProcessorCount; // rsi
  __int64 result; // rax
  int v4; // edx
  _QWORD *v5; // rcx
  int v6; // r8d
  int v7; // r9d
  unsigned int i; // edi
  __int64 v9; // rbx
  size_t v10; // rdx
  __int64 v11; // rdx
  __int64 v12; // rcx
  NTSTATUS v13; // ebx
  __int64 v14; // r8
  __int64 v15; // r8
  int v16; // [rsp+20h] [rbp-78h]
  int v17; // [rsp+38h] [rbp-60h]
  wchar_t pszSrc[12]; // [rsp+50h] [rbp-48h] BYREF

  MaximumProcessorCount = KeQueryMaximumProcessorCountEx(0xFFFFu);
  qword_140027AA8 = (__int64)&qword_140027AA0;
  qword_140027AA0 = (__int64)&qword_140027AA0;
  qword_140027AB8 = (__int64)&qword_140027AB0;
  qword_140027AB0 = (__int64)&qword_140027AB0;
  wcscpy(pszSrc, L"Wildcard");
  KeInitializeSpinLock(&SpinLock);
  DriverObject = a1;
  KeInitializeEvent(&Event, NotificationEvent, 0);
  dword_140027B60 = MaximumProcessorCount;
  qword_140027B68 = (PVOID)ExAllocatePool2(64, 136 * MaximumProcessorCount, 1668304471);
  if ( !qword_140027B68 )
    return 3221225626LL;
  qword_140027B10 = (__int64)&qword_140027B08;
  qword_140027B08 = &qword_140027B08;
  result = NetioInitializeWorkQueue(qword_140027B18, WinNatGlobalWorkQueueRoutine, DriverObject, deviceObject);
  if ( (int)result < 0 )
    return result;
  dword_140027A84 = 2;
  WinNatGlobalDriverState = 1;
  P = (PVOID)ExAllocatePool2(64, 104LL * (unsigned int)MaximumProcessorCount, 1668566615);
  if ( !P )
    return 3221225626LL;
  for ( i = 0; i < (unsigned int)MaximumProcessorCount; *v5 = v5 )
  {
    v9 = 104LL * i;
    *(_DWORD *)((char *)P + v9) = i;
    KeInitializeDpc((PRKDPC)((char *)P + v9 + 24), WinNatTranslationDpc, 0);
    ++i;
    v5 = (char *)P + v9 + 88;
    v5[1] = v5;
  }
  qword_140027B00 = (PVOID)PplCreateLookasideList((int)v5, v4, v6, v7, v16, 0x28u, 0x63744E57u, v17, 0x63744E57u);
  if ( !qword_140027B00 )
    return 3221225626LL;
  qword_140027AE8 = MdpCreatePool(120, 1651396183);
  WinNatReadRegistryConfig();
  memset(&pszDest, 0, 0x50u);
  v13 = RtlStringCchCopyW(&pszDest, v10, pszSrc);
  if ( v13 < 0 )
    MicrosoftTelemetryAssertTriggeredNoArgsKM(v12, v11, v14);
  v15 = -1;
  do
    ++v15;
  while ( pszSrc[v15] );
  memmove(&pszDest, pszSrc, 2 * v15);
  result = (unsigned int)v13;
  qword_140027BD8 = 1;
  return result;
}

```

## disassembly

```asm
0x14002f780  push    rbx
0x14002f782  push    rbp
0x14002f783  push    rsi
0x14002f784  push    rdi
0x14002f785  sub     rsp, 78h
0x14002f789  mov     rax, cs:__security_cookie
0x14002f790  xor     rax, rsp
0x14002f793  mov     [rsp+98h+var_30], rax
0x14002f798  mov     rbx, rcx
0x14002f79b  mov     ecx, 0FFFFh; GroupNumber
0x14002f7a0  call    cs:__imp_KeQueryMaximumProcessorCountEx
0x14002f7a7  nop     dword ptr [rax+rax+00h]
0x14002f7ac  movups  xmm0, xmmword ptr cs:aWildcard; "Wildcard"
0x14002f7b3  movzx   edx, word ptr cs:aWildcard+10h; ""
0x14002f7ba  lea     rcx, SpinLock; SpinLock
0x14002f7c1  mov     esi, eax
0x14002f7c3  lea     rax, qword_140027AA0
0x14002f7ca  mov     cs:qword_140027AA8, rax
0x14002f7d1  mov     cs:qword_140027AA0, rax
0x14002f7d8  lea     rax, qword_140027AB0
0x14002f7df  mov     cs:qword_140027AB8, rax
0x14002f7e6  mov     cs:qword_140027AB0, rax
0x14002f7ed  movups  xmmword ptr [rsp+98h+pszSrc], xmm0
0x14002f7f2  mov     [rsp+98h+var_38], dx
0x14002f7f7  call    cs:__imp_KeInitializeSpinLock
0x14002f7fe  nop     dword ptr [rax+rax+00h]
0x14002f803  xor     r8d, r8d; State
0x14002f806  mov     cs:DriverObject, rbx
0x14002f80d  xor     edx, edx; Type
0x14002f80f  lea     rcx, Event; Event
0x14002f816  call    cs:__imp_KeInitializeEvent
0x14002f81d  nop     dword ptr [rax+rax+00h]
0x14002f822  imul    rdx, rsi, 88h
0x14002f829  mov     edi, 40h ; '@'
0x14002f82e  mov     cs:dword_140027B60, esi
0x14002f834  mov     r8d, 63704E57h
0x14002f83a  mov     ecx, edi
0x14002f83c  mov     ebx, esi
0x14002f83e  call    cs:__imp_ExAllocatePool2
0x14002f845  nop     dword ptr [rax+rax+00h]
0x14002f84a  xor     ebp, ebp
0x14002f84c  mov     cs:qword_140027B68, rax
0x14002f853  test    rax, rax
0x14002f856  jz      loc_14002F9DE
0x14002f85c  mov     r9, cs:deviceObject
0x14002f863  lea     rax, qword_140027B08
0x14002f86a  mov     r8, cs:DriverObject
0x14002f871  lea     rdx, WinNatGlobalWorkQueueRoutine
0x14002f878  lea     rcx, qword_140027B18
0x14002f87f  mov     cs:qword_140027B10, rax
0x14002f886  mov     cs:qword_140027B08, rax
0x14002f88d  call    cs:__imp_NetioInitializeWorkQueue
0x14002f894  nop     dword ptr [rax+rax+00h]
0x14002f899  test    eax, eax
0x14002f89b  js      loc_14002F9E3
0x14002f8a1  imul    rdx, rbx, 68h ; 'h'
0x14002f8a5  mov     r8d, 63744E57h
0x14002f8ab  mov     cs:dword_140027A84, 2
0x14002f8b5  mov     ecx, edi
0x14002f8b7  mov     cs:WinNatGlobalDriverState, 1
0x14002f8be  call    cs:__imp_ExAllocatePool2
0x14002f8c5  nop     dword ptr [rax+rax+00h]
0x14002f8ca  mov     cs:P, rax
0x14002f8d1  test    rax, rax
0x14002f8d4  jz      loc_14002F9DE
0x14002f8da  mov     edi, ebp
0x14002f8dc  test    esi, esi
0x14002f8de  jz      short loc_14002F92F
0x14002f8e0  mov     eax, edi
0x14002f8e2  lea     rdx, WinNatTranslationDpc; DeferredRoutine
0x14002f8e9  imul    rbx, rax, 68h ; 'h'
0x14002f8ed  mov     rax, cs:P
0x14002f8f4  xor     r8d, r8d; DeferredContext
0x14002f8f7  mov     [rbx+rax], edi
0x14002f8fa  mov     rcx, cs:P
0x14002f901  add     rcx, 18h
0x14002f905  add     rcx, rbx; Dpc
0x14002f908  call    cs:__imp_KeInitializeDpc
0x14002f90f  nop     dword ptr [rax+rax+00h]
0x14002f914  mov     rcx, cs:P
0x14002f91b  inc     edi
0x14002f91d  add     rcx, 58h ; 'X'
0x14002f921  add     rcx, rbx; int
0x14002f924  mov     [rcx+8], rcx
0x14002f928  mov     [rcx], rcx
0x14002f92b  cmp     edi, esi
0x14002f92d  jb      short loc_14002F8E0
0x14002f92f  mov     [rsp+98h+var_58], 63744E57h; ULONG
0x14002f937  mov     [rsp+98h+var_68], 63744E57h; ULONG
0x14002f93f  mov     [rsp+98h+var_70], 28h ; '('; SIZE_T
0x14002f948  call    PplCreateLookasideList
0x14002f94d  mov     cs:qword_140027B00, rax
0x14002f954  test    rax, rax
0x14002f957  jz      loc_14002F9DE
0x14002f95d  mov     ecx, 78h ; 'x'
0x14002f962  mov     edx, 626E4E57h
0x14002f967  call    cs:__imp_MdpCreatePool
0x14002f96e  nop     dword ptr [rax+rax+00h]
0x14002f973  mov     cs:qword_140027AE8, rax
0x14002f97a  call    WinNatReadRegistryConfig
0x14002f97f  xor     edx, edx; Val
0x14002f981  lea     rdi, pszDest
0x14002f988  mov     rcx, rdi; void *
0x14002f98b  lea     r8d, [rdx+50h]; Size
0x14002f98f  call    memset
0x14002f994  lea     r8, [rsp+98h+pszSrc]; pszSrc
0x14002f999  mov     rcx, rdi; pszDest
0x14002f99c  call    RtlStringCchCopyW
0x14002f9a1  mov     ebx, eax
0x14002f9a3  test    eax, eax
0x14002f9a5  jns     short loc_14002F9AC
0x14002f9a7  call    MicrosoftTelemetryAssertTriggeredNoArgsKM
0x14002f9ac  lea     rax, [rsp+98h+pszSrc]
0x14002f9b1  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002f9b5  inc     r8
0x14002f9b8  cmp     [rax+r8*2], bp
0x14002f9bd  jnz     short loc_14002F9B5
0x14002f9bf  add     r8, r8; Size
0x14002f9c2  lea     rdx, [rsp+98h+pszSrc]; Src
0x14002f9c7  mov     rcx, rdi; void *
0x14002f9ca  call    memmove
0x14002f9cf  mov     eax, ebx
0x14002f9d1  mov     cs:qword_140027BD8, 1
0x14002f9dc  jmp     short loc_14002F9E3
0x14002f9de  mov     eax, 0C000009Ah
0x14002f9e3  mov     rcx, [rsp+98h+var_30]
0x14002f9e8  xor     rcx, rsp; StackCookie
0x14002f9eb  call    __security_check_cookie
0x14002f9f0  add     rsp, 78h
0x14002f9f4  pop     rdi
0x14002f9f5  pop     rsi
0x14002f9f6  pop     rbp
0x14002f9f7  pop     rbx
0x14002f9f8  retn
```
